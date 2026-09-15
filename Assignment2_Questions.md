The University of Sydney School of Computer Science Dr Suranga Seneviratne Associate Professor - Security 



## **CSEC5616/CSEC3616 — S2 2026 Assignment - 2** 

This is an **individual** assignment. 

This assignment worths 10% of the final marks of the course. It covers Weeks 4-6 (inclusive). Submit your final report as a `PDF` and codes as a `zip` file in Canvas. In Canvas, under Assignment 2, you will find two links to submit your report and code separately. 

You should explain any details of how to run your code in the report. 

Please read the below instructions carefully. 

## ***** IMPORTANT ***** 

1) **Note the answer release date:** Please note the answer release date mentioned below. Any submission after that will get zero marks, instead of a late penalty. 

2) **Typeset reports only:** We accept only typeset answers. Any hand written answers will get zero marks. This is because we can’t do plagiarism checks for hand written answers. 

3) **DO NOT repeat questions in the report:** Simply include the question number and your answer only. If you include question text in your answer sheet, your TurnItIn score will be high and there will be additional checks. This will cause a delay in releasing your marks. **We will also impose a penalty of 10% of the total marks.** 

3) **Cite your sources:** If you are referring to any internet sources include them as citations. We do not expect any specific citation style. You are free to select a style you think as appropriate. As mentioned in class announcements you are free to use GenAI. If you do so, make declaration in the report. If you are using material from the lecture slides or lecture notes, you do not need to cite them explicitly. 

## ***** SUBMISSION ***** 

## **Final Report & Code: Due by Week 8, Sunday the 27th of September, 2026 11:59PM** 

**Informal Extensions:** For this assignment, you can submit up to 5 days late (i.e., until **Friday 02/10/2026 23:59** ) without any late penalty. You do not have to lodge any request through the Special Considerations portal or contact the unit staff for this. Everyone is automatically entitled to this. Please note that this extension is not updated in Canvas, so it is normal if you see a late submission flag in Canvas. After this extension period, late penalties will apply as per the university policy. Please refer to the Administrivia slide in Week 1. 

**Answer release:** The answers to this assignment will be automatically released on **05 October 2026 at 00:00** . Any submissions after that will get **zero marks** . If you have a legitimate reason that requires an extension beyond that you will need to go through the university 

Cybersecurity Engineering - Lecture Notes 

September 7, 2026 

special considerations <u>process.</u> If approved, what you will be grant is a mark adjustment not an extension. 

# **1 Breaking the Vigenère Cipher (25 marks)** 

In the given `zip` file for Assignment 2 ( `Question1.zip` ), you will find a cipher text encrypted by the Vigenère cipher. Your task is to break it and find the original plain text. Please read the following instructions carefully. 

- You need to write your own code for this. However, there will be some guesswork and analysis involved. So we do not expect your code to give the decrypted result straight away. For example, if you are checking various substitutions, it is acceptable that you run your code multiple times to see which substitution results in a readable text. 

- The **spaces** and punctuations such as **.** and **’** are not encrypted. You can store their positions into an array, remove them, do the decryption using your method, and insert them back to the correct positions in the final plaintext. 

- You will need ideas from `Kasiski Test` to break this. However there can be other possible solutions. You are not allowed to use any online decryption tool to assist you. 

- The key length is less than 20 characters and contain only capital English characters. It is a random string, not a meaningful word. The final plain text is readable and meaningful. 

- In the report include a description of your approach, the key length, the key, and the final plaintext you obtained. Also, explain how your code works and how to run it so that the tutors can run your code. 

# **2 AES Calculation (25 marks)** 

In this question, you will perform some AES calculations manually. You are given the following information in hexadecimal notation. Here, "manually" means performing the calculations yourself step by step - without using any programs or scripts. Note that your submission must be typed; we do not accept handwritten work, even if the calculations are done by hand. 

- Plaintext 0C0B0A090807060504030201000F0E0D 

- First round key 05050505050505050505050505050505. 

Specifically, you will be **manually** calculating the initial steps in the AES calculation as illustrated in Figure 1. 

Answer the following questions. For each step you need to explain what you are doing, your calculation steps, and the answer. 

**Note:** We do not expect fine-granular step for each individual calculation. For example, it is ok to show detailed steps of one of the mix-column calculations and show the answers for other calculations. 

- i Show the original contents of State, displayed as a 4 * 4 matrix. Enter the bytes column-wise, i.e., fill the first column from top to bottom, then the second column, and continue in order. **(1 marks)** 

- ii Show the value of State after initial AddRoundKey. **(3 marks)** 

Cybersecurity Engineering - Lecture Notes 

September 7, 2026 

#### **Plain text – 16 bytes (128 bits)** 



<!-- Start of picture text -->
Initial state<br>(i)<br>Add Round Key Round Key<br>(ii)<br>Sub Bytes<br>(iii)<br>Shift Rows<br>(iv)<br>Mix Columns<br>(v)<br>? NA NA NA<br>? NA NA NA<br>? NA NA NA<br>D1 NA NA NA<br><!-- End of picture text -->

Figure 1: AES manual calculation 

iii Show the value of State after SubBytes. **(3 marks)** 

iv Show the value of State after ShiftRows. **(3 marks)** 

- v Calculate and show the missing values of the first column of the State after MixColumns (see the last matrix in Figure 1). (You can use the remaining value of the column to check whether you did the correct calculations in the previous steps. The rest of the values of the state marked as NA are not applicable to the question.) **(15 marks)** 

**Note:** Addition and multiplication for AES are done on _GF_ (2<sup>8</sup> ) with the irreducible polynomial _m_ ( _x_ ) = _x_<sup>8</sup> + _x_<sup>4</sup> + _x_<sup>3</sup> + _x_ + 1. 

Referring to following material will be helpful to complete this task 

- AES Rijndael Cipher explained as a Flash animation 

- AES wiki page Advanced Encryption Standard 

- Cryptography and Network Security (Seventh Edition - William Stallings) - Chapter 6 

# **3 RSA Calculation (25 marks)** 

Cybersecurity Engineering - Lecture Notes 

September 7, 2026 

Suppose Bob is generating a public and private key pair using RSA algorithm. Bob choses the prime numbers _p_ = 4 _,_ 201 and _q_ = 5 _,_ 701. He computed _n_ = _pq_ = 23 _,_ 949 _,_ 901 and _ϕ_ ( _n_ ) = ( _p −_ 1)( _q −_ 1) = 23 _,_ 940 _,_ 000. He then chooses the encryption exponent _e_ = 65 _,_ 537. 

- i Find the private key. i.e., d where _ed ≡_ 1 mod _ϕ_ ( _n_ ) using the Extended Euclidean algorithm **(14 marks - 11 marks for the missing values in the table and 3 marks for** _d_ **)** . First follow the explanation below. 

Recall the Euclidean Algorithm for finding the GCD of _a_ and _b_ . It goes like this 

- 1) Calculate _r_ 1 = _a_ mod _b_ which satisfies _a_ = _q_ 1 _b_ + _r_ 1 

- 2) Calculate _r_ 2 = _b_ mod _r_ 1 which satisfies _b_ = _q_ 2 _r_ 1 + _r_ 2 

- 3) Calculate _r_ 3 = _r_ 1 mod _r_ 2 which satisfies _r_ 1 = _q_ 3 _r_ 2 + _r_ 3 

- i) Calculate _ri_ = _ri−_ 2 mod _ri−_ 1 which satisfies _ri−_ 2 = _qiri−_ 1 + _ri_ ... 

- n) Calculate _rn_ +1 = _rn−_ 1 mod _rn_ = 0 which satisfies _rn−_ 1 = _qn_ +1 _rn_ + 0 

When _rn_ +1 becomes zero _gcd_ ( _a, b_ ) = _rn_ 

Next we assume that each step we can find _xi_ and _yi_ that satisfy _ri_ = _axi_ + _byi_ . We end up with the following sequence. 

_a_ = _q_ 1 _b_ + _r_ 1 and _r_ 1 = _ax_ 1 + _by_ 1 

_b_ = _q_ 2 _r_ 1 + _r_ 2 and _r_ 2 = _ax_ 2 + _by_ 2 

_r_ 1 = _q_ 3 _r_ 2 + _r_ 3 and _r_ 3 = _ax_ 3 + _by_ 3 

- _rn−_ 2 = _qnrn−_ 1 + _rn_ and _rn_ = _axn_ + _byn_ 

_rn−_ 1 = _qn_ +1 _rn_ + 0 

We can rearrange the terms in above equations to obtain 



But we also know that _ri−_ 2 = _axi−_ 2 + _byi−_ 2 and _ri−_ 1 = _axi−_ 1 + _byi−_ 1 

By substituting in Equation (1) we get. 

- _ri_ = ( _axi−_ 2 + _byi−_ 2) _−_ ( _axi−_ 1 + _byi−_ 1) _qi_ 

- _ri_ = _a_ ( _xi−_ 2 _− qixi−_ 1) + _b_ ( _yi−_ 2) _− qiyi−_ 1) 

Since we assumed _ri_ = _axi_ + _byi_ by co-efficient matching we can get 

_xi_ = _xi−_ 2 _− qixi−_ 1 and _yi_ = _yi−_ 2 _− qiyi−_ 1 

Based on this information your task is to fill the blanks in Table 1 and find the value of _d_ . 

Cybersecurity Engineering - Lecture Notes 

September 7, 2026 

When marking, we do not expect fully worked-out details for every step in the table. You must explain the basic idea you used to fill the table and provide full details for the second step (i.e., _i_ = 2 in the table). We also expect some explaination of how you selected the final _d_ value. 

Table 1: Computing the decryption exponent _d_ . 

|_i_|_qi_|_ri_|_xi_|_yi_|
|---|---|---|---|---|
|-1|NA|23,940,000|1|0|
|0|NA|65,537|0|1|
|1|365|18,995|1|-365|
|2|-|-|-|-|
|3|-|-|-|-|
|4|-|-|-|-|
|5|-|-|-|-|
|6|-|-|-|-|
|7|-|-|-|-|
|8|-|-|-|-|
|9|-|-|-|-|
|10|-|-|-|-|
|11|-|-|-|-|
|12|-|-|-|-|
|13|10|0|NA|NA|



Cybersecurity Engineering - Lecture Notes 

September 7, 2026 

- ii Suppose Bob shared his public key _e_ with Alice. If Alice wants to send the message 3 to Bob, find the encrypted message. Show your steps of exponentiation by squaring (You don’t have to show all the steps but you can show first 2-3 steps of the exponential squaring and show the final answer - you can use an online calculator the find the final answer e.g. `https: //www.dcode.fr/modular-exponentiation` ). ( **6 marks)** . 

- iii Verify that Bob can decrypt what Alice sends. Describe the required computation and use an online calculator to obtain the final answer. ( **5 marks)** . 

# **4 Message Authentication Codes (25 marks)** 

### **a) Message Authentication Codes vs. Hashes** 

- i Explain what Authenticated Encryption (AE) is and why it is required. **(2 marks)** 

- ii Explain the difference between Authenticated Encryption (AE) and Authenticated Encryption with Associated Data (AEAD) **(2 marks)** 

### **b) Protocol Analysis** 

Consider the following two protocols that are used by Alice to send a message to Bob. 

**Protocol X** : _y_ = _Ek_ 1( _x||H_ ( _k_ 2 _||x_ )) 

Here _x_ is the plaintext message, _k_ 1 and _k_ 2 are shared keys between Alice and Bob, and H is a cryptographically secure hashing function such as SHA256. E stands for a AES encryption. Once y is computed Alice sends y to B. (Here, || denotes concatenation.) 

**Protocol Y** : _x, y_ = _EPK_ ( _H_ ( _x_ )) 

Here, _PK_ is the public key of Bob and it is assumed Bob has access to the corresponding private key _SK_ . H is again a cryptographic secure hashing function such as SHA256. E stands for RSA encryption. Once y is computed Alice sends x and y to Bob. 

- i Explain step by step what Bob will do after the reception of the message _y_ in each of the protocols. **(4 marks)** 

- ii Explain whether confidentiality and integrity is achieved in each of the two protocols. **(4 marks)** 

### **c) Flawed Hash** 

This problem explores a letter-based hash function called the **Miniature Letter Hash (MLH)** . Like standard cryptographic hash functions, MLH takes a message of arbitrary length and produces a fixed-size digest, in this case, a sequence of four letters. 

Cybersecurity Engineering - Lecture Notes 

September 7, 2026 

**1) Preprocessing:** Extract only the letters from the input message, discarding everything else, and convert them to uppercase. Then divide what remains into blocks of 16 letters. If the final block has fewer than 16 letters, pad it with nulls (i.e., 0 - zero). A four-number accumulator is initialized to (0, 0, 0, 0) before processing begins. 

**Accumulator:** A four-number accumulator is initialized to (0, 0, 0, 0) before processing begins. After each round, the accumulator is updated using: new_accumulator[i] = (column_sum[i] + old_accumulator[i]) mod 26, for i = 1, 2, 3, 4. The updated accumulator is then carried into the next round. After both rounds of the final block are complete, the accumulator values are converted back to letters (0 = A, 1 = B, . . . , 25 = Z) to produce the hash. 

**2) Processing each block:** Every block is passed through a compression function consisting of two sequential rounds. The accumulator entering a block’s compression is the one output by the previous block (or (0, 0, 0, 0) for the first block). After both rounds complete, the updated accumulator is carried forward as the input to the next block’s compression. This continues until all blocks are processed, at which point the final accumulator values are converted to letters to form the hash. 

**2a) Round 1:** Arrange the 16-letter block into a 4×4 grid, filling row by row left to right. Assign each letter a numeric value (A = 0, B = 1, . . . , Z = 25). Sum each column modulo 26 to produce four intermediate values. Add each intermediate value to the corresponding position of the incoming accumulator, modulo 26. The resulting four values form the updated accumulator, which is passed into Round 2. See Figure 2. 



<!-- Start of picture text -->
A B C D 0 1 2 3<br>E F G H 4 5 6 7<br>I  J K L 8 9 10 11<br>M N O P 12 13 14 15<br>Column sum (24 , 28, 32, 36)<br>Old accumulator (0 , 0, 0, 0)<br>New accumulator = (Column Sum + Old Accumulator) mod 26<br>New accumulator = (24, 28, 32, 36)+(0,0,0,0) mod 26<br>New accumulator = (24, 2, 6, 10)<br><!-- End of picture text -->

Figure 2: MLH Round 1 - Example 

**2b) Round 2:** Using the same grid from Round 1, apply the following row transformations: shift row 1 left by one position, shift row 2 left by two positions, shift row 3 left by three positions, and reverse row 4. Sum each column of this transformed grid modulo 26 to produce four intermediate values. Add each to the corresponding position of the Round 1 accumulator, modulo 26. The result is the accumulator passed to the next block’s compression, or the final hash accumulator if this was the last block. See Figure 3. 

- i Draw a figure comparable to the figure in Week 6 - Slide 26 to depict the overall MLH logic and the compression function logic. **(2 marks)** 

- ii Calculate the hash function for the 32-letter message “Hello Dave everything is running well.” **(3 marks)** 

- iii To demonstrate the weakness of MLH, find a message of length 22-letter that produces the same 

Cybersecurity Engineering - Lecture Notes 

September 7, 2026 



<!-- Start of picture text -->
B C D A 1 2 3 0<br>G H E F 6 7 4 5<br>L I J K 11 8 9 10<br>P O N M 15 14 13 12<br>Column Sum (33 , 31, 29, 27)<br><!-- End of picture text -->

Old Accumulator (24 , 2, 6, 10) New Accumulator = (Column sum + Old Accumulator) mod 26 New Accumulator = (24, 2, 6, 10)+(33, 31, 29, 27) mod 26 New Accumulator = (5, 7, 9, 11) If the original message is only  ABCDEFGHIJKLMNOP we can get the hash by converting the new accumulator back to characters. That is (5, 7, 9, 11) = FHJL 

If there are other blocks in the original message, the new accumulator value goes to next block. 

Figure 3: MLH Round 2 - Example 

hash. Explain your thought process of deriving this text. (There can be more than one answer) **(8 marks)** 

Cybersecurity Engineering - Lecture Notes 

September 7, 2026 

