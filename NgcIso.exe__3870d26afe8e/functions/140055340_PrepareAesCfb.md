# PrepareAesCfb

- ea: `0x140055340`
- end: `0x140055469`
- name: `PrepareAesCfb`
- size: `297`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140055500`
- `0x1400556c0`

## callees

- `0x140055340`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x140055443`
- `bcrypt!BCryptDestroyKey` at `0x140055443`
- `bcrypt!BCryptSetProperty` at `0x1400553e2`
- `bcrypt!BCryptSetProperty` at `0x14005540b`
- `bcrypt!BCryptSetProperty` at `0x1400553e2`
- `bcrypt!BCryptSetProperty` at `0x14005540b`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1400553b6`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x1400553b6`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140055387`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x140055387`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140055454`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x140055454`

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
0x140055340  push    rbp
0x140055342  push    rbx
0x140055343  push    rsi
0x140055344  push    rdi
0x140055345  push    r14
0x140055347  push    r15
0x140055349  mov     rbp, rsp
0x14005534c  sub     rsp, 68h
0x140055350  mov     r14, r9
0x140055353  mov     [rbp+phAlgorithm], 0
0x14005535b  mov     r15, r8
0x14005535e  mov     [rbp+phKey], 0
0x140055366  mov     edi, edx
0x140055368  mov     dword ptr [rbp+pbInput], 10h
0x14005536f  mov     rsi, rcx
0x140055372  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140055379  xor     r9d, r9d; dwFlags
0x14005537c  lea     rdx, pszAlgId; "AES"
0x140055383  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x140055387  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14005538d  mov     ebx, eax
0x14005538f  test    eax, eax
0x140055391  js      loc_140055433
0x140055397  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14005539b  lea     rdx, [rbp+phKey]; phKey
0x14005539f  mov     [rsp+68h+dwFlags], 0; dwFlags
0x1400553a7  xor     r9d, r9d; cbKeyObject
0x1400553aa  mov     [rsp+68h+cbSecret], edi; cbSecret
0x1400553ae  xor     r8d, r8d; pbKeyObject
0x1400553b1  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x1400553b6  call    cs:__imp_BCryptGenerateSymmetricKey
0x1400553bc  mov     ebx, eax
0x1400553be  test    eax, eax
0x1400553c0  js      short loc_140055433
0x1400553c2  mov     rcx, [rbp+phKey]; hObject
0x1400553c6  lea     r8, aChainingmodecf; "ChainingModeCFB"
0x1400553cd  mov     r9d, 20h ; ' '; cbInput
0x1400553d3  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x1400553db  lea     rdx, aChainingmode; "ChainingMode"
0x1400553e2  call    cs:__imp_BCryptSetProperty
0x1400553e8  mov     ebx, eax
0x1400553ea  test    eax, eax
0x1400553ec  js      short loc_140055433
0x1400553ee  mov     rcx, [rbp+phKey]; hObject
0x1400553f2  lea     r8, [rbp+pbInput]; pbInput
0x1400553f6  mov     r9d, 4; cbInput
0x1400553fc  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x140055404  lea     rdx, aMessageblockle; "MessageBlockLength"
0x14005540b  call    cs:__imp_BCryptSetProperty
0x140055411  mov     ebx, eax
0x140055413  test    eax, eax
0x140055415  js      short loc_140055433
0x140055417  mov     rax, [rbp+phAlgorithm]
0x14005541b  xor     ecx, ecx
0x14005541d  mov     [r15], rax
0x140055420  mov     rax, [rbp+phKey]
0x140055424  mov     [r14], rax
0x140055427  xor     eax, eax
0x140055429  mov     [rbp+phKey], rax
0x14005542d  mov     [rbp+phAlgorithm], rcx
0x140055431  jmp     short loc_14005543B
0x140055433  mov     rcx, [rbp+phAlgorithm]
0x140055437  mov     rax, [rbp+phKey]
0x14005543b  test    rax, rax
0x14005543e  jz      short loc_14005544D
0x140055440  mov     rcx, rax; hKey
0x140055443  call    cs:__imp_BCryptDestroyKey
0x140055449  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x14005544d  test    rcx, rcx
0x140055450  jz      short loc_14005545A
0x140055452  xor     edx, edx; dwFlags
0x140055454  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14005545a  mov     eax, ebx
0x14005545c  add     rsp, 68h
0x140055460  pop     r15
0x140055462  pop     r14
0x140055464  pop     rdi
0x140055465  pop     rsi
0x140055466  pop     rbx
0x140055467  pop     rbp
0x140055468  retn
```
