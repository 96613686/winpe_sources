# PrepareAesCfb

- ea: `0x18009ddd8`
- end: `0x18009df26`
- name: `PrepareAesCfb`
- size: `334`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18009df30`
- `0x18009e100`

## callees

- `0x18009ddd8`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18009de54`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18009de54`
- `bcrypt!BCryptSetProperty` at `0x18009de86`
- `bcrypt!BCryptSetProperty` at `0x18009deb5`
- `bcrypt!BCryptSetProperty` at `0x18009de86`
- `bcrypt!BCryptSetProperty` at `0x18009deb5`
- `bcrypt!BCryptDestroyKey` at `0x18009def3`
- `bcrypt!BCryptDestroyKey` at `0x18009def3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009df0a`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009df0a`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009de1f`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009de1f`

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
0x18009ddd8  push    rbp
0x18009ddda  push    rbx
0x18009dddb  push    rsi
0x18009dddc  push    rdi
0x18009dddd  push    r14
0x18009dddf  push    r15
0x18009dde1  mov     rbp, rsp
0x18009dde4  sub     rsp, 68h
0x18009dde8  mov     r14, r9
0x18009ddeb  mov     [rbp+phAlgorithm], 0
0x18009ddf3  mov     r15, r8
0x18009ddf6  mov     [rbp+phKey], 0
0x18009ddfe  mov     edi, edx
0x18009de00  mov     dword ptr [rbp+pbInput], 10h
0x18009de07  mov     rsi, rcx
0x18009de0a  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009de11  xor     r9d, r9d; dwFlags
0x18009de14  lea     rdx, aAes; "AES"
0x18009de1b  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18009de1f  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009de26  nop     dword ptr [rax+rax+00h]
0x18009de2b  mov     ebx, eax
0x18009de2d  test    eax, eax
0x18009de2f  js      loc_18009DEE3
0x18009de35  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009de39  lea     rdx, [rbp+phKey]; phKey
0x18009de3d  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18009de45  xor     r9d, r9d; cbKeyObject
0x18009de48  mov     [rsp+68h+cbSecret], edi; cbSecret
0x18009de4c  xor     r8d, r8d; pbKeyObject
0x18009de4f  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x18009de54  call    cs:__imp_BCryptGenerateSymmetricKey
0x18009de5b  nop     dword ptr [rax+rax+00h]
0x18009de60  mov     ebx, eax
0x18009de62  test    eax, eax
0x18009de64  js      short loc_18009DEE3
0x18009de66  mov     rcx, [rbp+phKey]; hObject
0x18009de6a  lea     r8, pbInput; "ChainingModeCFB"
0x18009de71  mov     r9d, 20h ; ' '; cbInput
0x18009de77  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x18009de7f  lea     rdx, aChainingmode; "ChainingMode"
0x18009de86  call    cs:__imp_BCryptSetProperty
0x18009de8d  nop     dword ptr [rax+rax+00h]
0x18009de92  mov     ebx, eax
0x18009de94  test    eax, eax
0x18009de96  js      short loc_18009DEE3
0x18009de98  mov     rcx, [rbp+phKey]; hObject
0x18009de9c  lea     r8, [rbp+pbInput]; pbInput
0x18009dea0  mov     r9d, 4; cbInput
0x18009dea6  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x18009deae  lea     rdx, aMessageblockle; "MessageBlockLength"
0x18009deb5  call    cs:__imp_BCryptSetProperty
0x18009debc  nop     dword ptr [rax+rax+00h]
0x18009dec1  mov     ebx, eax
0x18009dec3  test    eax, eax
0x18009dec5  js      short loc_18009DEE3
0x18009dec7  mov     rax, [rbp+phAlgorithm]
0x18009decb  xor     ecx, ecx
0x18009decd  mov     [r15], rax
0x18009ded0  mov     rax, [rbp+phKey]
0x18009ded4  mov     [r14], rax
0x18009ded7  xor     eax, eax
0x18009ded9  mov     [rbp+phKey], rax
0x18009dedd  mov     [rbp+phAlgorithm], rcx
0x18009dee1  jmp     short loc_18009DEEB
0x18009dee3  mov     rcx, [rbp+phAlgorithm]
0x18009dee7  mov     rax, [rbp+phKey]
0x18009deeb  test    rax, rax
0x18009deee  jz      short loc_18009DF03
0x18009def0  mov     rcx, rax; hKey
0x18009def3  call    cs:__imp_BCryptDestroyKey
0x18009defa  nop     dword ptr [rax+rax+00h]
0x18009deff  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009df03  test    rcx, rcx
0x18009df06  jz      short loc_18009DF16
0x18009df08  xor     edx, edx; dwFlags
0x18009df0a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18009df11  nop     dword ptr [rax+rax+00h]
0x18009df16  mov     eax, ebx
0x18009df18  add     rsp, 68h
0x18009df1c  pop     r15
0x18009df1e  pop     r14
0x18009df20  pop     rdi
0x18009df21  pop     rsi
0x18009df22  pop     rbx
0x18009df23  pop     rbp
0x18009df24  retn
```
