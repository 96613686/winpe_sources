# PrepareAesCfb

- ea: `0x18009bfb8`
- end: `0x18009c106`
- name: `PrepareAesCfb`
- size: `334`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18009c110`
- `0x18009c2e0`

## callees

- `0x18009bfb8`

## import_xrefs

- `bcrypt!BCryptGenerateSymmetricKey` at `0x18009c034`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18009c034`
- `bcrypt!BCryptDestroyKey` at `0x18009c0d3`
- `bcrypt!BCryptDestroyKey` at `0x18009c0d3`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009c0ea`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18009c0ea`
- `bcrypt!BCryptSetProperty` at `0x18009c066`
- `bcrypt!BCryptSetProperty` at `0x18009c095`
- `bcrypt!BCryptSetProperty` at `0x18009c066`
- `bcrypt!BCryptSetProperty` at `0x18009c095`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009bfff`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18009bfff`

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
0x18009bfb8  push    rbp
0x18009bfba  push    rbx
0x18009bfbb  push    rsi
0x18009bfbc  push    rdi
0x18009bfbd  push    r14
0x18009bfbf  push    r15
0x18009bfc1  mov     rbp, rsp
0x18009bfc4  sub     rsp, 68h
0x18009bfc8  mov     r14, r9
0x18009bfcb  mov     [rbp+phAlgorithm], 0
0x18009bfd3  mov     r15, r8
0x18009bfd6  mov     [rbp+phKey], 0
0x18009bfde  mov     edi, edx
0x18009bfe0  mov     dword ptr [rbp+pbInput], 10h
0x18009bfe7  mov     rsi, rcx
0x18009bfea  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18009bff1  xor     r9d, r9d; dwFlags
0x18009bff4  lea     rdx, aAes; "AES"
0x18009bffb  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x18009bfff  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18009c006  nop     dword ptr [rax+rax+00h]
0x18009c00b  mov     ebx, eax
0x18009c00d  test    eax, eax
0x18009c00f  js      loc_18009C0C3
0x18009c015  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009c019  lea     rdx, [rbp+phKey]; phKey
0x18009c01d  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18009c025  xor     r9d, r9d; cbKeyObject
0x18009c028  mov     [rsp+68h+cbSecret], edi; cbSecret
0x18009c02c  xor     r8d, r8d; pbKeyObject
0x18009c02f  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x18009c034  call    cs:__imp_BCryptGenerateSymmetricKey
0x18009c03b  nop     dword ptr [rax+rax+00h]
0x18009c040  mov     ebx, eax
0x18009c042  test    eax, eax
0x18009c044  js      short loc_18009C0C3
0x18009c046  mov     rcx, [rbp+phKey]; hObject
0x18009c04a  lea     r8, pbInput; "ChainingModeCFB"
0x18009c051  mov     r9d, 20h ; ' '; cbInput
0x18009c057  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x18009c05f  lea     rdx, aChainingmode; "ChainingMode"
0x18009c066  call    cs:__imp_BCryptSetProperty
0x18009c06d  nop     dword ptr [rax+rax+00h]
0x18009c072  mov     ebx, eax
0x18009c074  test    eax, eax
0x18009c076  js      short loc_18009C0C3
0x18009c078  mov     rcx, [rbp+phKey]; hObject
0x18009c07c  lea     r8, [rbp+pbInput]; pbInput
0x18009c080  mov     r9d, 4; cbInput
0x18009c086  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x18009c08e  lea     rdx, aMessageblockle; "MessageBlockLength"
0x18009c095  call    cs:__imp_BCryptSetProperty
0x18009c09c  nop     dword ptr [rax+rax+00h]
0x18009c0a1  mov     ebx, eax
0x18009c0a3  test    eax, eax
0x18009c0a5  js      short loc_18009C0C3
0x18009c0a7  mov     rax, [rbp+phAlgorithm]
0x18009c0ab  xor     ecx, ecx
0x18009c0ad  mov     [r15], rax
0x18009c0b0  mov     rax, [rbp+phKey]
0x18009c0b4  mov     [r14], rax
0x18009c0b7  xor     eax, eax
0x18009c0b9  mov     [rbp+phKey], rax
0x18009c0bd  mov     [rbp+phAlgorithm], rcx
0x18009c0c1  jmp     short loc_18009C0CB
0x18009c0c3  mov     rcx, [rbp+phAlgorithm]
0x18009c0c7  mov     rax, [rbp+phKey]
0x18009c0cb  test    rax, rax
0x18009c0ce  jz      short loc_18009C0E3
0x18009c0d0  mov     rcx, rax; hKey
0x18009c0d3  call    cs:__imp_BCryptDestroyKey
0x18009c0da  nop     dword ptr [rax+rax+00h]
0x18009c0df  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x18009c0e3  test    rcx, rcx
0x18009c0e6  jz      short loc_18009C0F6
0x18009c0e8  xor     edx, edx; dwFlags
0x18009c0ea  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18009c0f1  nop     dword ptr [rax+rax+00h]
0x18009c0f6  mov     eax, ebx
0x18009c0f8  add     rsp, 68h
0x18009c0fc  pop     r15
0x18009c0fe  pop     r14
0x18009c100  pop     rdi
0x18009c101  pop     rsi
0x18009c102  pop     rbx
0x18009c103  pop     rbp
0x18009c104  retn
```
