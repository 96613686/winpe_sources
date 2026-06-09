# CHash::CHash(SmartPointer<CHashAlg> &,ulong,uchar *)

- ea: `0x180137718`
- end: `0x180137868`
- name: `??0CHash@@AEAA@AEAV?$SmartPointer@VCHashAlg@@@@KPEAE@Z`
- size: `336`
- prototype: `__int64 __fastcall(__int64, _QWORD *, ULONG, UCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180137e80`

## callees

- `0x1800024fc`
- `0x18000e81c`
- `0x1800201c0`
- `0x180137718`
- `0x180159010`

## import_xrefs

- `bcrypt!BCryptGetProperty` at `0x1801377b2`
- `bcrypt!BCryptGetProperty` at `0x1801377b2`
- `bcrypt!BCryptCreateHash` at `0x180137834`
- `bcrypt!BCryptCreateHash` at `0x180137834`

## string_xrefs

- `0x180137840`: `CHash::CHash - BCryptCreateHash`

## pseudocode

```c
__int64 __fastcall CHash::CHash(__int64 a1, _QWORD *a2, ULONG a3, UCHAR *a4)
{
  _QWORD *v7; // r14
  __int64 v8; // rdx
  BCRYPT_HANDLE *v9; // rax
  NTSTATUS Property; // eax
  unsigned int v11; // eax
  ULONG v12; // ebx
  UCHAR *v13; // rdi
  __int64 v14; // rdx
  BCRYPT_ALG_HANDLE *v15; // rax
  NTSTATUS Hash; // eax
  ULONG pcbResult; // [rsp+88h] [rbp+10h] BYREF
  ULONG pbOutput; // [rsp+90h] [rbp+18h] BYREF

  *(_QWORD *)a1 = &CHash::`vftable';
  *(_QWORD *)(a1 + 8) = 0;
  v7 = (_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = *a2;
  SmartPointer<CRepubJetSessionContext>::AddRef(a1 + 16);
  *(_QWORD *)(a1 + 24) = 0;
  *(_QWORD *)(a1 + 32) = 0;
  pbOutput = 0;
  pcbResult = 0;
  LOBYTE(v8) = a3 != 0;
  v9 = (BCRYPT_HANDLE *)(*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v7 + 56LL))(*v7, v8);
  Property = BCryptGetProperty(*v9, L"ObjectLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( Property < 0 )
    NtError::Throw(L"CHash::CHash - BCryptGetProperty", Property);
  *(_QWORD *)(a1 + 24) = operator new[](pbOutput);
  v11 = (*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)*v7 + 48LL))(*v7);
  *(_QWORD *)(a1 + 32) = operator new[](v11);
  v12 = pbOutput;
  v13 = *(UCHAR **)(a1 + 24);
  LOBYTE(v14) = a3 != 0;
  v15 = (BCRYPT_ALG_HANDLE *)(*(__int64 (__fastcall **)(_QWORD, __int64))(*(_QWORD *)*v7 + 56LL))(*v7, v14);
  if ( !a3 )
    a4 = 0;
  Hash = BCryptCreateHash(*v15, (BCRYPT_HASH_HANDLE *)(a1 + 8), v13, v12, a4, a3, 0);
  if ( Hash < 0 )
    NtError::Throw(L"CHash::CHash - BCryptCreateHash", Hash);
  return a1;
}

```

## disassembly

```asm
0x180137718  mov     [rsp+arg_18], rbx
0x18013771d  mov     [rsp+arg_0], rcx
0x180137722  push    rbp
0x180137723  push    rsi
0x180137724  push    rdi
0x180137725  push    r12
0x180137727  push    r13
0x180137729  push    r14
0x18013772b  push    r15
0x18013772d  sub     rsp, 40h
0x180137731  mov     r13, r9
0x180137734  mov     ebp, r8d
0x180137737  mov     rsi, rcx
0x18013773a  lea     rax, ??_7CHash@@6B@; const CHash::`vftable'
0x180137741  mov     [rcx], rax
0x180137744  xor     ebx, ebx
0x180137746  mov     [rcx+8], rbx
0x18013774a  lea     r14, [rcx+10h]
0x18013774e  mov     rax, [rdx]
0x180137751  mov     [r14], rax
0x180137754  mov     rcx, r14
0x180137757  call    ?AddRef@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::AddRef(void)
0x18013775c  nop
0x18013775d  mov     [rsi+18h], rbx
0x180137761  mov     [rsi+20h], rbx
0x180137765  mov     [rsp+78h+pbOutput], ebx
0x18013776c  mov     [rsp+78h+arg_8], ebx
0x180137773  mov     rcx, [r14]
0x180137776  test    ebp, ebp
0x180137778  setnz   r12b
0x18013777c  mov     rax, [rcx]
0x18013777f  mov     dl, r12b
0x180137782  mov     rax, [rax+38h]
0x180137786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18013778b  mov     [rsp+78h+dwFlags], ebx; dwFlags
0x18013778f  lea     rcx, [rsp+78h+arg_8]
0x180137797  mov     [rsp+78h+pcbResult], rcx; pcbResult
0x18013779c  lea     r9d, [rbx+4]; cbOutput
0x1801377a0  lea     r8, [rsp+78h+pbOutput]; pbOutput
0x1801377a8  lea     rdx, aObjectlength; "ObjectLength"
0x1801377af  mov     rcx, [rax]; hObject
0x1801377b2  call    cs:__imp_BCryptGetProperty
0x1801377b8  test    eax, eax
0x1801377ba  jns     short loc_1801377CB
0x1801377bc  mov     edx, eax; int
0x1801377be  lea     rcx, aChashChashBcry_0; "CHash::CHash - BCryptGetProperty"
0x1801377c5  call    ?Throw@NtError@@SAXPEBGJ@Z; NtError::Throw(ushort const *,long)
0x1801377cb  mov     ecx, [rsp+78h+pbOutput]; unsigned __int64
0x1801377d2  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801377d7  mov     [rsi+18h], rax
0x1801377db  mov     rcx, [r14]
0x1801377de  mov     rax, [rcx]
0x1801377e1  mov     rax, [rax+30h]
0x1801377e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801377ea  mov     ecx, eax; unsigned __int64
0x1801377ec  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x1801377f1  mov     [rsi+20h], rax
0x1801377f5  mov     ebx, [rsp+78h+pbOutput]
0x1801377fc  mov     rdi, [rsi+18h]
0x180137800  mov     rcx, [r14]
0x180137803  mov     rax, [rcx]
0x180137806  mov     dl, r12b
0x180137809  mov     rax, [rax+38h]
0x18013780d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180137812  xor     ecx, ecx
0x180137814  test    ebp, ebp
0x180137816  cmovz   r13, rcx
0x18013781a  mov     [rsp+78h+var_48], ecx; dwFlags
0x18013781e  mov     [rsp+78h+dwFlags], ebp; cbSecret
0x180137822  mov     [rsp+78h+pcbResult], r13; pbSecret
0x180137827  mov     r9d, ebx; cbHashObject
0x18013782a  mov     r8, rdi; pbHashObject
0x18013782d  lea     rdx, [rsi+8]; phHash
0x180137831  mov     rcx, [rax]; hAlgorithm
0x180137834  call    cs:__imp_BCryptCreateHash
0x18013783a  test    eax, eax
0x18013783c  jns     short loc_18013784D
0x18013783e  mov     edx, eax; int
0x180137840  lea     rcx, aChashChashBcry; "CHash::CHash - BCryptCreateHash"
0x180137847  call    ?Throw@NtError@@SAXPEBGJ@Z; NtError::Throw(ushort const *,long)
0x18013784d  mov     rax, rsi
0x180137850  mov     rbx, [rsp+78h+arg_18]
0x180137858  add     rsp, 40h
0x18013785c  pop     r15
0x18013785e  pop     r14
0x180137860  pop     r13
0x180137862  pop     r12
0x180137864  pop     rdi
0x180137865  pop     rsi
0x180137866  pop     rbp
0x180137867  retn
```
