# PrepareAesCfb

- ea: `0x18003fc70`
- end: `0x18003fd99`
- name: `PrepareAesCfb`
- size: `297`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18003fda0`
- `0x18003ff60`

## callees

- `0x18003fc70`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x18003fd73`
- `bcrypt!BCryptDestroyKey` at `0x18003fd73`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18003fce6`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18003fce6`
- `bcrypt!BCryptSetProperty` at `0x18003fd12`
- `bcrypt!BCryptSetProperty` at `0x18003fd3b`
- `bcrypt!BCryptSetProperty` at `0x18003fd12`
- `bcrypt!BCryptSetProperty` at `0x18003fd3b`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003fd84`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18003fd84`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003fcb7`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18003fcb7`

## pseudocode

```c
__int64 __fastcall PrepareAesCfb(PUCHAR pbSecret, ULONG cbSecret, BCRYPT_ALG_HANDLE *a3, BCRYPT_KEY_HANDLE *a4)
{
  NTSTATUS v8; // ebx
  BCRYPT_ALG_HANDLE v9; // rcx
  BCRYPT_KEY_HANDLE v10; // rax
  UCHAR pbInput[8]; // [rsp+40h] [rbp-28h] BYREF
  BCRYPT_KEY_HANDLE phKey; // [rsp+48h] [rbp-20h] BYREF
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp-18h] BYREF

  phAlgorithm = 0;
  phKey = 0;
  *(_DWORD *)pbInput = 16;
  v8 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"AES", L"Microsoft Primitive Provider", 0);
  if ( v8 < 0
    || (v8 = BCryptGenerateSymmetricKey(phAlgorithm, &phKey, 0, 0, pbSecret, cbSecret, 0), v8 < 0)
    || (v8 = BCryptSetProperty(phKey, L"ChainingMode", (PUCHAR)L"ChainingModeCFB", 0x20u, 0), v8 < 0)
    || (v8 = BCryptSetProperty(phKey, L"MessageBlockLength", pbInput, 4u, 0), v8 < 0) )
  {
    v9 = phAlgorithm;
    v10 = phKey;
  }
  else
  {
    v9 = 0;
    *a3 = phAlgorithm;
    *a4 = phKey;
    v10 = 0;
    phKey = 0;
    phAlgorithm = 0;
  }
  if ( v10 )
  {
    BCryptDestroyKey(v10);
    v9 = phAlgorithm;
  }
  if ( v9 )
    BCryptCloseAlgorithmProvider(v9, 0);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18003fc70  push    rbp
0x18003fc72  push    rbx
0x18003fc73  push    rsi
0x18003fc74  push    rdi
0x18003fc75  push    r14
0x18003fc77  push    r15
0x18003fc79  mov     rbp, rsp
0x18003fc7c  sub     rsp, 68h
0x18003fc80  mov     r14, r9
0x18003fc83  mov     [rbp+phAlgorithm], 0
0x18003fc8b  mov     r15, r8
0x18003fc8e  mov     [rbp+phKey], 0
0x18003fc96  mov     edi, edx
0x18003fc98  mov     dword ptr [rbp+pbInput], 10h
0x18003fc9f  mov     rsi, rcx
0x18003fca2  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18003fca9  xor     r9d, r9d; dwFlags
0x18003fcac  lea     rdx, aAes; "AES"
0x18003fcb3  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18003fcb7  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18003fcbd  mov     ebx, eax
0x18003fcbf  test    eax, eax
0x18003fcc1  js      loc_18003FD63
0x18003fcc7  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18003fccb  lea     rdx, [rbp+phKey]; phKey
0x18003fccf  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18003fcd7  xor     r9d, r9d; cbKeyObject
0x18003fcda  mov     [rsp+68h+cbSecret], edi; cbSecret
0x18003fcde  xor     r8d, r8d; pbKeyObject
0x18003fce1  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x18003fce6  call    cs:__imp_BCryptGenerateSymmetricKey
0x18003fcec  mov     ebx, eax
0x18003fcee  test    eax, eax
0x18003fcf0  js      short loc_18003FD63
0x18003fcf2  mov     rcx, [rbp+phKey]; hObject
0x18003fcf6  lea     r8, pbInput; "ChainingModeCFB"
0x18003fcfd  mov     r9d, 20h ; ' '; cbInput
0x18003fd03  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x18003fd0b  lea     rdx, aChainingmode; "ChainingMode"
0x18003fd12  call    cs:__imp_BCryptSetProperty
0x18003fd18  mov     ebx, eax
0x18003fd1a  test    eax, eax
0x18003fd1c  js      short loc_18003FD63
0x18003fd1e  mov     rcx, [rbp+phKey]; hObject
0x18003fd22  lea     r8, [rbp+pbInput]; pbInput
0x18003fd26  mov     r9d, 4; cbInput
0x18003fd2c  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x18003fd34  lea     rdx, aMessageblockle; "MessageBlockLength"
0x18003fd3b  call    cs:__imp_BCryptSetProperty
0x18003fd41  mov     ebx, eax
0x18003fd43  test    eax, eax
0x18003fd45  js      short loc_18003FD63
0x18003fd47  mov     rax, [rbp+phAlgorithm]
0x18003fd4b  xor     ecx, ecx
0x18003fd4d  mov     [r15], rax
0x18003fd50  mov     rax, [rbp+phKey]
0x18003fd54  mov     [r14], rax
0x18003fd57  xor     eax, eax
0x18003fd59  mov     [rbp+phKey], rax
0x18003fd5d  mov     [rbp+phAlgorithm], rcx
0x18003fd61  jmp     short loc_18003FD6B
0x18003fd63  mov     rcx, [rbp+phAlgorithm]
0x18003fd67  mov     rax, [rbp+phKey]
0x18003fd6b  test    rax, rax
0x18003fd6e  jz      short loc_18003FD7D
0x18003fd70  mov     rcx, rax; hKey
0x18003fd73  call    cs:__imp_BCryptDestroyKey
0x18003fd79  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18003fd7d  test    rcx, rcx
0x18003fd80  jz      short loc_18003FD8A
0x18003fd82  xor     edx, edx; dwFlags
0x18003fd84  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18003fd8a  mov     eax, ebx
0x18003fd8c  add     rsp, 68h
0x18003fd90  pop     r15
0x18003fd92  pop     r14
0x18003fd94  pop     rdi
0x18003fd95  pop     rsi
0x18003fd96  pop     rbx
0x18003fd97  pop     rbp
0x18003fd98  retn
```
