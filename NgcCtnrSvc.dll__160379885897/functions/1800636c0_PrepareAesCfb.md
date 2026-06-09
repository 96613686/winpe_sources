# PrepareAesCfb

- ea: `0x1800636c0`
- end: `0x18006380e`
- name: `PrepareAesCfb`
- size: `334`
- prototype: `__int64 __fastcall(PUCHAR pbSecret, ULONG cbSecret)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180063820`
- `0x1800639f0`

## callees

- `0x1800636c0`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x1800637db`
- `bcrypt!BCryptDestroyKey` at `0x1800637db`
- `bcrypt!BCryptSetProperty` at `0x18006376e`
- `bcrypt!BCryptSetProperty` at `0x18006379d`
- `bcrypt!BCryptSetProperty` at `0x18006376e`
- `bcrypt!BCryptSetProperty` at `0x18006379d`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18006373c`
- `bcrypt!BCryptGenerateSymmetricKey` at `0x18006373c`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063707`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180063707`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800637f2`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x1800637f2`

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
0x1800636c0  push    rbp
0x1800636c2  push    rbx
0x1800636c3  push    rsi
0x1800636c4  push    rdi
0x1800636c5  push    r14
0x1800636c7  push    r15
0x1800636c9  mov     rbp, rsp
0x1800636cc  sub     rsp, 68h
0x1800636d0  mov     r14, r9
0x1800636d3  mov     [rbp+phAlgorithm], 0
0x1800636db  mov     r15, r8
0x1800636de  mov     [rbp+phKey], 0
0x1800636e6  mov     edi, edx
0x1800636e8  mov     dword ptr [rbp+pbInput], 10h
0x1800636ef  mov     rsi, rcx
0x1800636f2  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x1800636f9  xor     r9d, r9d; dwFlags
0x1800636fc  lea     rdx, aAes; "AES"
0x180063703  lea     rcx, [rbp+phAlgorithm]; phAlgorithm
0x180063707  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18006370e  nop     dword ptr [rax+rax+00h]
0x180063713  mov     ebx, eax
0x180063715  test    eax, eax
0x180063717  js      loc_1800637CB
0x18006371d  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x180063721  lea     rdx, [rbp+phKey]; phKey
0x180063725  mov     [rsp+68h+dwFlags], 0; dwFlags
0x18006372d  xor     r9d, r9d; cbKeyObject
0x180063730  mov     [rsp+68h+cbSecret], edi; cbSecret
0x180063734  xor     r8d, r8d; pbKeyObject
0x180063737  mov     [rsp+68h+pbSecret], rsi; pbSecret
0x18006373c  call    cs:__imp_BCryptGenerateSymmetricKey
0x180063743  nop     dword ptr [rax+rax+00h]
0x180063748  mov     ebx, eax
0x18006374a  test    eax, eax
0x18006374c  js      short loc_1800637CB
0x18006374e  mov     rcx, [rbp+phKey]; hObject
0x180063752  lea     r8, pbInput; "ChainingModeCFB"
0x180063759  mov     r9d, 20h ; ' '; cbInput
0x18006375f  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x180063767  lea     rdx, aChainingmode; "ChainingMode"
0x18006376e  call    cs:__imp_BCryptSetProperty
0x180063775  nop     dword ptr [rax+rax+00h]
0x18006377a  mov     ebx, eax
0x18006377c  test    eax, eax
0x18006377e  js      short loc_1800637CB
0x180063780  mov     rcx, [rbp+phKey]; hObject
0x180063784  lea     r8, [rbp+pbInput]; pbInput
0x180063788  mov     r9d, 4; cbInput
0x18006378e  mov     dword ptr [rsp+68h+pbSecret], 0; dwFlags
0x180063796  lea     rdx, aMessageblockle; "MessageBlockLength"
0x18006379d  call    cs:__imp_BCryptSetProperty
0x1800637a4  nop     dword ptr [rax+rax+00h]
0x1800637a9  mov     ebx, eax
0x1800637ab  test    eax, eax
0x1800637ad  js      short loc_1800637CB
0x1800637af  mov     rax, [rbp+phAlgorithm]
0x1800637b3  xor     ecx, ecx
0x1800637b5  mov     [r15], rax
0x1800637b8  mov     rax, [rbp+phKey]
0x1800637bc  mov     [r14], rax
0x1800637bf  xor     eax, eax
0x1800637c1  mov     [rbp+phKey], rax
0x1800637c5  mov     [rbp+phAlgorithm], rcx
0x1800637c9  jmp     short loc_1800637D3
0x1800637cb  mov     rcx, [rbp+phAlgorithm]
0x1800637cf  mov     rax, [rbp+phKey]
0x1800637d3  test    rax, rax
0x1800637d6  jz      short loc_1800637EB
0x1800637d8  mov     rcx, rax; hKey
0x1800637db  call    cs:__imp_BCryptDestroyKey
0x1800637e2  nop     dword ptr [rax+rax+00h]
0x1800637e7  mov     rcx, [rbp+phAlgorithm]; hAlgorithm
0x1800637eb  test    rcx, rcx
0x1800637ee  jz      short loc_1800637FE
0x1800637f0  xor     edx, edx; dwFlags
0x1800637f2  call    cs:__imp_BCryptCloseAlgorithmProvider
0x1800637f9  nop     dword ptr [rax+rax+00h]
0x1800637fe  mov     eax, ebx
0x180063800  add     rsp, 68h
0x180063804  pop     r15
0x180063806  pop     r14
0x180063808  pop     rdi
0x180063809  pop     rsi
0x18006380a  pop     rbx
0x18006380b  pop     rbp
0x18006380c  retn
```
