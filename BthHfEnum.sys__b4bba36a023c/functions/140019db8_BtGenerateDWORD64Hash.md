# BtGenerateDWORD64Hash

- ea: `0x140019db8`
- end: `0x140019e32`
- name: `BtGenerateDWORD64Hash`
- size: `122`
- prototype: `__int64 __fastcall(PUCHAR pbInput, ULONG cbInput)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14002f42c`

## callees

- `0x140019db8`
- `0x140019e38`

## import_xrefs

- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140019e1a`
- `ksecdd!BCryptCloseAlgorithmProvider` at `0x140019e1a`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140019de8`
- `ksecdd!BCryptOpenAlgorithmProvider` at `0x140019de8`

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
0x140019db8  push    rbx
0x140019dba  push    rbp
0x140019dbb  push    rsi
0x140019dbc  push    rdi
0x140019dbd  sub     rsp, 28h
0x140019dc1  mov     rdi, r8
0x140019dc4  mov     [rsp+48h+phAlgorithm], 0
0x140019dcd  mov     esi, edx
0x140019dcf  lea     r8, pszImplementation; "Microsoft Primitive Provider"
0x140019dd6  mov     rbp, rcx
0x140019dd9  lea     rdx, pszAlgId; "SHA256"
0x140019de0  lea     rcx, [rsp+48h+phAlgorithm]; phAlgorithm
0x140019de5  xor     r9d, r9d; dwFlags
0x140019de8  call    cs:__imp_BCryptOpenAlgorithmProvider
0x140019def  nop     dword ptr [rax+rax+00h]
0x140019df4  mov     ebx, eax
0x140019df6  test    eax, eax
0x140019df8  js      short loc_140019E0E
0x140019dfa  mov     r8, [rsp+48h+phAlgorithm]; hObject
0x140019dff  mov     r9, rdi
0x140019e02  mov     edx, esi; cbInput
0x140019e04  mov     rcx, rbp; pbInput
0x140019e07  call    BtGenerateDWORD64HashWithHandle
0x140019e0c  mov     ebx, eax
0x140019e0e  mov     rcx, [rsp+48h+phAlgorithm]; hAlgorithm
0x140019e13  test    rcx, rcx
0x140019e16  jz      short loc_140019E26
0x140019e18  xor     edx, edx; dwFlags
0x140019e1a  call    cs:__imp_BCryptCloseAlgorithmProvider
0x140019e21  nop     dword ptr [rax+rax+00h]
0x140019e26  mov     eax, ebx
0x140019e28  add     rsp, 28h
0x140019e2c  pop     rdi
0x140019e2d  pop     rsi
0x140019e2e  pop     rbp
0x140019e2f  pop     rbx
0x140019e30  retn
```
