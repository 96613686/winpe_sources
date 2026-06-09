# BtGenerateDWORD64Hash

- ea: `0x14001d83c`
- end: `0x14001d8b6`
- name: `BtGenerateDWORD64Hash`
- size: `122`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140086094`

## callees

- `0x140012500`
- `0x14001d83c`

## import_xrefs

- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14001d89e`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x14001d89e`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14001d86c`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x14001d86c`

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
0x14001d83c  push    rbx
0x14001d83e  push    rbp
0x14001d83f  push    rsi
0x14001d840  push    rdi
0x14001d841  sub     rsp, 28h
0x14001d845  mov     rdi, r8
0x14001d848  mov     [rsp+48h+phAlgorithm], 0
0x14001d851  mov     esi, edx
0x14001d853  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x14001d85a  mov     rbp, rcx
0x14001d85d  lea     rdx, pszAlgId; "SHA256"
0x14001d864  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x14001d869  xor     r9d, r9d; dwFlags
0x14001d86c  call    cs:__imp_BCryptOpenAlgorithmProvider
0x14001d873  nop     dword ptr [rax+rax+00h]
0x14001d878  mov     ebx, eax
0x14001d87a  test    eax, eax
0x14001d87c  js      short loc_14001D892
0x14001d87e  mov     r8, [rsp+48h+phAlgorithm]; hObject
0x14001d883  mov     r9, rdi
0x14001d886  mov     edx, esi; cbInput
0x14001d888  mov     rcx, rbp; pbInput
0x14001d88b  call    BtGenerateDWORD64HashWithHandle
0x14001d890  mov     ebx, eax
0x14001d892  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x14001d897  test    rcx, rcx
0x14001d89a  jz      short loc_14001D8AA
0x14001d89c  xor     edx, edx; dwFlags
0x14001d89e  call    cs:__imp_BCryptCloseAlgorithmProvider
0x14001d8a5  nop     dword ptr [rax+rax+00h]
0x14001d8aa  mov     eax, ebx
0x14001d8ac  add     rsp, 28h
0x14001d8b0  pop     rdi
0x14001d8b1  pop     rsi
0x14001d8b2  pop     rbp
0x14001d8b3  pop     rbx
0x14001d8b4  retn
```
