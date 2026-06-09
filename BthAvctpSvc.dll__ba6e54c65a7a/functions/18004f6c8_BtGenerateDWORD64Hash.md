# BtGenerateDWORD64Hash

- ea: `0x18004f6c8`
- end: `0x18004f735`
- name: `BtGenerateDWORD64Hash`
- size: `109`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18004ebb8`
- `0x18004f274`

## callees

- `0x18004f6c8`
- `0x18004f73c`

## import_xrefs

- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004f724`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x18004f724`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004f6f8`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x18004f6f8`

## pseudocode

```c
__int64 __fastcall BtGenerateDWORD64Hash(PUCHAR pbInput, ULONG cbInput, _QWORD *a3)
{
  int DWORD64HashWithHandle; // ebx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+68h] [rbp+20h] BYREF

  phAlgorithm = 0;
  DWORD64HashWithHandle = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", L"Microsoft Primitive Provider", 0);
  if ( DWORD64HashWithHandle >= 0 )
    DWORD64HashWithHandle = BtGenerateDWORD64HashWithHandle(pbInput, cbInput, phAlgorithm, a3);
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  return (unsigned int)DWORD64HashWithHandle;
}

```

## disassembly

```asm
0x18004f6c8  push    rbx
0x18004f6ca  push    rbp
0x18004f6cb  push    rsi
0x18004f6cc  push    rdi
0x18004f6cd  sub     rsp, 28h
0x18004f6d1  mov     rdi, r8
0x18004f6d4  mov     [rsp+48h+phAlgorithm], 0
0x18004f6dd  mov     esi, edx
0x18004f6df  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x18004f6e6  mov     rbp, rcx
0x18004f6e9  lea     rdx, pszAlgId; "SHA256"
0x18004f6f0  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x18004f6f5  xor     r9d, r9d; dwFlags
0x18004f6f8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18004f6fe  mov     ebx, eax
0x18004f700  test    eax, eax
0x18004f702  js      short loc_18004F718
0x18004f704  mov     r8, [rsp+48h+phAlgorithm]; hObject
0x18004f709  mov     r9, rdi
0x18004f70c  mov     edx, esi; cbInput
0x18004f70e  mov     rcx, rbp; pbInput
0x18004f711  call    BtGenerateDWORD64HashWithHandle
0x18004f716  mov     ebx, eax
0x18004f718  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x18004f71d  test    rcx, rcx
0x18004f720  jz      short loc_18004F72A
0x18004f722  xor     edx, edx; dwFlags
0x18004f724  call    cs:__imp_BCryptCloseAlgorithmProvider
0x18004f72a  mov     eax, ebx
0x18004f72c  add     rsp, 28h
0x18004f730  pop     rdi
0x18004f731  pop     rsi
0x18004f732  pop     rbp
0x18004f733  pop     rbx
0x18004f734  retn
```
