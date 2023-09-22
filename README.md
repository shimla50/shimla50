import random
import string
def generate_password(length, lowercase, uppercase, digit, special_char):
    lowercase_char = string.ascii_lowercase if lowercase else ''
    uppercase_char = string.ascii_uppercase if uppercase else ''
    digits_char = string.digits if digit else ''
    special_character = string.punctuation if special_char else ''

    all_char = lowercase_char + uppercase_char + digits_char + special_character

    if not all_char:
        print("Please select at least one character set.")
        return None

    password = ''.join(random.choice(all_char) for i in range(length))
    return password
def main():
    print("Random Password Generator")

    length = int(input("Enter the desired password length: "))
    lowercase = input("Include lowercase letters? (Yes/No): ").lower()== "yes"
    uppercase = input("Include uppercase letters? (Yes/No): ").lower() == "yes"
    digit = input("Include digits? (Yes/No): ").lower() == "yes"
    special_char = input("Include special characters letters? (Yes/No): ").lower()== "yes"

    password = generate_password(length, lowercase, uppercase, digit, special_char)

    if password:
        print("Generated Password:",password)
if __name__ == "__main__":
  main()
