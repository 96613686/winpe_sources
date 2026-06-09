# std::vector<char *,std::allocator<char *>>::_Insert_n(std::_Vector_iterator<char *,std::allocator<char *>>,unsigned __int64,char * const &)

- ea: `0x180059708`
- end: `0x180059925`
- name: `?_Insert_n@?$vector@PEADV?$allocator@PEAD@std@@@std@@IEAAXV?$_Vector_iterator@PEADV?$allocator@PEAD@std@@@2@_KAEBQEAD@Z`
- size: `541`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800535b4`

## callees

- `0x180004d91`
- `0x1800111d0`
- `0x180011540`
- `0x18001d810`
- `0x180059708`
- `0x18009bd1c`

## import_xrefs

- `msvcrt!free` at `0x180059866`
- `msvcrt!free` at `0x180059866`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800597c1`
- `msvcrt!??0exception@@QEAA@AEBQEBD@Z` at `0x1800597c1`
- `msvcrt!memmove_s` at `0x180059820`
- `msvcrt!memmove_s` at `0x18005984b`
- `msvcrt!memmove_s` at `0x1800598d2`
- `msvcrt!memmove_s` at `0x1800598fd`
- `msvcrt!memmove_s` at `0x180059820`
- `msvcrt!memmove_s` at `0x18005984b`
- `msvcrt!memmove_s` at `0x1800598d2`
- `msvcrt!memmove_s` at `0x1800598fd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall std::vector<char *>::_Insert_n(
        __int64 a1,
        unsigned __int64 *a2,
        const char *a3,
        const char **a4)
{
  const char *v6; // r12
  __int64 v7; // rdx
  unsigned __int64 v8; // rdx
  __int64 v9; // r8
  __int64 v10; // r14
  unsigned __int64 v11; // r14
  unsigned __int64 v12; // rcx
  unsigned __int64 v13; // rcx
  char *v14; // rdi
  _BYTE *v15; // r8
  __int64 v16; // rax
  __int64 v17; // r15
  __int64 v18; // rdx
  __int64 v19; // rbx
  void *v20; // rcx
  unsigned __int64 result; // rax
  _BYTE *v22; // rdi
  unsigned __int64 v23; // rcx
  unsigned __int64 *v24; // rdx
  __int64 v25; // rdx
  _QWORD pExceptionObject[11]; // [rsp+20h] [rbp-58h] BYREF
  char *v27; // [rsp+90h] [rbp+18h] BYREF

  v27 = (char *)a3;
  v6 = *a4;
  v27 = (char *)*a4;
  if ( *(_QWORD *)(a1 + 8) )
    v7 = (__int64)(*(_QWORD *)(a1 + 24) - *(_QWORD *)(a1 + 8)) >> 3;
  else
    v7 = 0;
  v10 = std::vector<CXdsReferenceValidateInfo *>::size(a1, v7);
  if ( 0x1FFFFFFFFFFFFFFFLL == v10 )
    std::vector<CAttachment>::_Xlen(1, v8, v9);
  v11 = v10 + 1;
  if ( v8 >= v11 )
  {
    v22 = *(_BYTE **)(a1 + 16);
    if ( (v22 - (_BYTE *)a2) >> 3 )
    {
      memmove_s(*(void *const *)(a1 + 16), 8u, v22 - 8, 8u);
      *(_QWORD *)(a1 + 16) = v22 + 8;
      v25 = (v22 - (_BYTE *)a2 - 8) >> 3;
      if ( v25 > 0 )
        memmove_s(&v22[-8 * v25], 8 * v25, a2, 8 * v25);
      v24 = a2 + 1;
    }
    else
    {
      v23 = 1 - ((v22 - (_BYTE *)a2) >> 3);
      if ( v23 )
        memset64(v22, (unsigned __int64)v6, v23);
      v24 = *(unsigned __int64 **)(a1 + 16);
      *(_QWORD *)(a1 + 16) = v24 + 1;
    }
    return std::fill<COldRemoteRead * *,COldRemoteRead *>(a2, v24, (unsigned __int64 *)&v27);
  }
  else
  {
    v12 = 0;
    if ( 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) >= v8 )
      v12 = v8 + (v8 >> 1);
    if ( v12 >= v11 )
      v11 = v12;
    if ( v11 )
    {
      if ( 0xFFFFFFFFFFFFFFFFuLL / v11 < 8 )
      {
        v27 = 0;
        exception::exception((exception *)pExceptionObject, (const char *const *)&v27);
        pExceptionObject[0] = &std::bad_alloc::`vftable';
        throw (std::bad_alloc *)pExceptionObject;
      }
      v13 = v11;
    }
    else
    {
      v13 = 0;
    }
    v14 = (char *)MmAllocate(8 * v13);
    v27 = v14;
    try
    {
      v15 = *(_BYTE **)(a1 + 8);
      v16 = ((char *)a2 - v15) >> 3;
      v17 = 8 * v16;
      if ( v16 )
        memmove_s(v14, 8 * v16, v15, 8 * v16);
      *(_QWORD *)&v14[v17] = v6;
      v18 = (__int64)(*(_QWORD *)(a1 + 16) - (_QWORD)a2) >> 3;
      if ( v18 )
        memmove_s(&v14[v17 + 8], 8 * v18, a2, 8 * v18);
    }
    catch ( ... )
    {
      free(v27);
      throw;
    }
    v19 = std::vector<CXdsReferenceValidateInfo *>::size(a1, v18);
    v20 = *(void **)(a1 + 8);
    if ( v20 )
      free(v20);
    *(_QWORD *)(a1 + 24) = &v14[8 * v11];
    result = (unsigned __int64)&v14[8 * v19 + 8];
    *(_QWORD *)(a1 + 16) = result;
    *(_QWORD *)(a1 + 8) = v14;
  }
  return result;
}

```

## disassembly

```asm
0x180059708  mov     rax, rsp
0x18005970b  mov     [rax+18h], r8
0x18005970f  push    rbx
0x180059710  push    rsi
0x180059711  push    rdi
0x180059712  push    r12
0x180059714  push    r14
0x180059716  push    r15
0x180059718  sub     rsp, 48h
0x18005971c  mov     rbx, rdx
0x18005971f  mov     rsi, rcx
0x180059722  mov     r12, [r9]
0x180059725  mov     [rax+18h], r12
0x180059729  cmp     qword ptr [rcx+8], 0
0x18005972e  jnz     short loc_180059734
0x180059730  xor     edx, edx
0x180059732  jmp     short loc_180059740
0x180059734  mov     rdx, [rcx+18h]
0x180059738  sub     rdx, [rcx+8]
0x18005973c  sar     rdx, 3
0x180059740  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x180059745  mov     r14, rax
0x180059748  mov     rdi, 1FFFFFFFFFFFFFFFh
0x180059752  mov     rax, rdi
0x180059755  sub     rax, r14
0x180059758  mov     ecx, 1
0x18005975d  cmp     rax, rcx
0x180059760  jnb     short loc_180059768
0x180059762  call    ?_Xlen@?$vector@VCAttachment@@V?$allocator@VCAttachment@@@std@@@std@@KAXXZ; std::vector<CAttachment>::_Xlen(void)
0x180059768  inc     r14
0x18005976b  cmp     rdx, r14
0x18005976e  jnb     loc_18005988A
0x180059774  mov     rax, rdx
0x180059777  shr     rax, 1
0x18005977a  sub     rdi, rax
0x18005977d  add     rax, rdx
0x180059780  xor     ecx, ecx
0x180059782  cmp     rdi, rdx
0x180059785  cmovnb  rcx, rax
0x180059789  cmp     rcx, r14
0x18005978c  cmovnb  r14, rcx
0x180059790  test    r14, r14
0x180059793  jnz     short loc_180059799
0x180059795  xor     ecx, ecx
0x180059797  jmp     short loc_1800597E8
0x180059799  xor     edx, edx
0x18005979b  or      rax, 0FFFFFFFFFFFFFFFFh
0x18005979f  div     r14
0x1800597a2  cmp     rax, 8
0x1800597a6  jnb     short loc_1800597E5
0x1800597a8  mov     [rsp+78h+arg_10], 0
0x1800597b4  lea     rdx, [rsp+78h+arg_10]
0x1800597bc  lea     rcx, [rsp+78h+pExceptionObject]
0x1800597c1  call    cs:__imp_??0exception@@QEAA@AEBQEBD@Z; exception::exception(char const * const &)
0x1800597c7  lea     rax, ??_7bad_alloc@std@@6B@; const std::bad_alloc::`vftable'
0x1800597ce  mov     [rsp+78h+pExceptionObject], rax
0x1800597d3  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x1800597da  lea     rcx, [rsp+78h+pExceptionObject]; pExceptionObject
0x1800597df  call    _CxxThrowException_0
0x1800597e5  mov     rcx, r14
0x1800597e8  shl     rcx, 3; unsigned __int64
0x1800597ec  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x1800597f1  mov     rdi, rax
0x1800597f4  mov     [rsp+78h+arg_10], rax
0x1800597fc  mov     r8, [rsi+8]; Source
0x180059800  mov     rax, rbx
0x180059803  sub     rax, r8
0x180059806  sar     rax, 3
0x18005980a  lea     r15, ds:0[rax*8]
0x180059812  test    rax, rax
0x180059815  jz      short loc_180059826
0x180059817  mov     r9, r15; SourceSize
0x18005981a  mov     rdx, r15; DestinationSize
0x18005981d  mov     rcx, rdi; Destination
0x180059820  call    cs:__imp_memmove_s
0x180059826  mov     [r15+rdi], r12
0x18005982a  mov     rdx, [rsi+10h]
0x18005982e  sub     rdx, rbx
0x180059831  sar     rdx, 3
0x180059835  test    rdx, rdx
0x180059838  jz      short loc_180059852
0x18005983a  shl     rdx, 3; DestinationSize
0x18005983e  lea     rcx, [r15+8]
0x180059842  add     rcx, rdi; Destination
0x180059845  mov     r9, rdx; SourceSize
0x180059848  mov     r8, rbx; Source
0x18005984b  call    cs:__imp_memmove_s
0x180059851  nop
0x180059852  mov     rcx, rsi
0x180059855  call    ?size@?$vector@PEAVCXdsReferenceValidateInfo@@V?$allocator@PEAVCXdsReferenceValidateInfo@@@std@@@std@@QEBA_KXZ; std::vector<CXdsReferenceValidateInfo *>::size(void)
0x18005985a  mov     rbx, rax
0x18005985d  mov     rcx, [rsi+8]; Block
0x180059861  test    rcx, rcx
0x180059864  jz      short loc_18005986D
0x180059866  call    cs:__imp_free
0x18005986c  nop
0x18005986d  lea     rax, [rdi+r14*8]
0x180059871  mov     [rsi+18h], rax
0x180059875  lea     rax, [rbx+1]
0x180059879  lea     rax, [rdi+rax*8]
0x18005987d  mov     [rsi+10h], rax
0x180059881  mov     [rsi+8], rdi
0x180059885  jmp     loc_180059917
0x18005988a  mov     rdi, [rsi+10h]
0x18005988e  mov     r14, rdi
0x180059891  sub     r14, rbx
0x180059894  mov     rax, r14
0x180059897  sar     rax, 3
0x18005989b  cmp     rax, rcx
0x18005989e  jnb     short loc_1800598C3
0x1800598a0  mov     rdx, rdi
0x1800598a3  sub     rdx, rbx
0x1800598a6  sar     rdx, 3
0x1800598aa  sub     rcx, rdx
0x1800598ad  jz      short loc_1800598B5
0x1800598af  mov     rax, r12
0x1800598b2  rep stosq
0x1800598b5  mov     rdx, [rsi+10h]
0x1800598b9  lea     rax, [rdx+8]
0x1800598bd  mov     [rsi+10h], rax
0x1800598c1  jmp     short loc_180059907
0x1800598c3  lea     r8, [rdi-8]; Source
0x1800598c7  mov     edx, 8; DestinationSize
0x1800598cc  mov     r9d, edx; SourceSize
0x1800598cf  mov     rcx, rdi; Destination
0x1800598d2  call    cs:__imp_memmove_s
0x1800598d8  lea     rax, [rdi+8]
0x1800598dc  mov     [rsi+10h], rax
0x1800598e0  lea     rdx, [r14-8]
0x1800598e4  sar     rdx, 3
0x1800598e8  test    rdx, rdx
0x1800598eb  jle     short loc_180059903
0x1800598ed  shl     rdx, 3; DestinationSize
0x1800598f1  sub     rdi, rdx
0x1800598f4  mov     r9, rdx; SourceSize
0x1800598f7  mov     r8, rbx; Source
0x1800598fa  mov     rcx, rdi; Destination
0x1800598fd  call    cs:__imp_memmove_s
0x180059903  lea     rdx, [rbx+8]
0x180059907  lea     r8, [rsp+78h+arg_10]
0x18005990f  mov     rcx, rbx
0x180059912  call    ??$fill@PEAPEAVCOldRemoteRead@@PEAV1@@std@@YAXPEAPEAVCOldRemoteRead@@0AEBQEAV1@@Z; std::fill<COldRemoteRead * *,COldRemoteRead *>(COldRemoteRead * *,COldRemoteRead * *,COldRemoteRead * const &)
0x180059917  add     rsp, 48h
0x18005991b  pop     r15
0x18005991d  pop     r14
0x18005991f  pop     r12
0x180059921  pop     rdi
0x180059922  pop     rsi
0x180059923  pop     rbx
0x180059924  retn
```
