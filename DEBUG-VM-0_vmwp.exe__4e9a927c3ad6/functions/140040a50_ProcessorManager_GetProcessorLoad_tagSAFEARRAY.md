# ProcessorManager::GetProcessorLoad(tagSAFEARRAY * *)

- ea: `0x140040a50`
- end: `0x140040dd6`
- name: `?GetProcessorLoad@ProcessorManager@@UEAAXPEAPEAUtagSAFEARRAY@@@Z`
- size: `902`
- prototype: `void __fastcall(ProcessorManager *__hidden this, struct tagSAFEARRAY **)`
- caller_count: `0`
- callee_count: `13`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140023d20`
- `0x140023da0`
- `0x140023e00`
- `0x140040a50`
- `0x140040fd8`
- `0x140041a3c`
- `0x14006af38`
- `0x14009d7ac`
- `0x1400e4e74`
- `0x140132cb0`
- `0x1401335fc`
- `0x140135935`
- `0x140135941`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140040d4e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140040d4e`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140040c74`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x140040c74`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140040ca9`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x140040ca9`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140040c45`
- `OLEAUT32!__imp_SafeArrayCreateVectorEx` at `0x140040c45`

## string_xrefs

- `0x140040d78`: `onecore\vm\common\vml\VmReaderWriterLock.h`
- `0x140040d94`: `onecore\vm\common\vml\VmAutomation.h`
- `0x140040da9`: `onecore\vm\common\vml\VmAutomation.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ProcessorManager::GetProcessorLoad(ProcessorManager *this, struct tagSAFEARRAY **a2)
{
  __int64 v3; // rsi
  __int64 v4; // rdi
  __int64 size_of; // rax
  void *v6; // rbx
  signed __int32 *v7; // rdi
  signed __int32 v8; // eax
  signed __int32 v9; // ebx
  __int64 v10; // r11
  __int64 v11; // rbx
  unsigned __int64 v12; // r8
  __int64 i; // r9
  __int64 v14; // rax
  __int64 v15; // rcx
  double v16; // xmm0_8
  double v17; // xmm0_8
  double v18; // xmm0_8
  double v19; // xmm1_8
  signed __int64 v20; // rbx
  SAFEARRAY *Vector; // rax
  struct tagSAFEARRAY *v22; // rdi
  HRESULT v23; // eax
  void *v24; // rcx
  SAFEARRAY *v25; // rdx
  signed __int32 v26; // edx
  void *v27; // [rsp+20h] [rbp-30h] BYREF
  void *Src[2]; // [rsp+28h] [rbp-28h] BYREF
  __int64 v29; // [rsp+38h] [rbp-18h]
  SAFEARRAY *psa; // [rsp+40h] [rbp-10h] BYREF
  void *ppvData; // [rsp+48h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]

  *a2 = 0;
  v27 = 0;
  *(_OWORD *)Src = 0;
  v29 = 0;
  v3 = *((_QWORD *)this + 93);
  v4 = *(unsigned int *)(v3 + 80);
  if ( *(_DWORD *)(v3 + 80) )
  {
    size_of = std::_Get_size_of_n<4>((unsigned int)v4);
    v6 = (void *)std::_Allocate<16,std::_Default_allocate_traits>(size_of);
    memset_0(v6, 0, 4 * v4);
    memmove_0(v6, Src[0], (char *)Src[1] - (char *)Src[0]);
    std::vector<unsigned long>::_Change_array(Src, v6, (unsigned int)v4, (unsigned int)v4, v27);
  }
  v7 = (signed __int32 *)(v3 + 112);
  v8 = _InterlockedCompareExchange((volatile signed __int32 *)(v3 + 112), 4, 0);
  v9 = v8;
  if ( v8 )
  {
    if ( (v8 & 1) != 0 && *(_DWORD *)(v3 + 116) == GetCurrentThreadId() )
    {
      _InterlockedIncrement((volatile signed __int32 *)(v3 + 120));
    }
    else
    {
      do
      {
        while ( (v9 & 1) != 0 )
        {
          if ( !(unsigned int)RrwpLockWait(v3 + 112, 0xFFFFFFFFLL, 0) )
            wil::details::in1diag3::Throw_Win32(
              retaddr,
              (void *)0x249,
              (unsigned int)"onecore\\vm\\common\\vml\\VmReaderWriterLock.h",
              (const char *)0x102,
              (unsigned int)v27);
          _m_prefetchw(v7);
          v9 = *v7;
        }
        v26 = v9;
        v9 = _InterlockedCompareExchange(v7, v9 + 4, v9);
      }
      while ( v9 != v26 );
    }
  }
  if ( *(_DWORD *)(v3 + 164) >= 2u )
  {
    v10 = (*(_DWORD *)(v3 + 160) + 100) % 0x65u;
    v11 = ((int)v10 + 100) % 0x65u;
    v12 = *(_QWORD *)(16392 * v10 + v3 + 16552) - *(_QWORD *)(16392 * v11 + v3 + 16552);
    for ( i = 0; (unsigned int)i < *(_DWORD *)(v3 + 80); i = (unsigned int)(i + 1) )
    {
      if ( (unsigned int)i >= 0x800 )
        break;
      v14 = (unsigned int)i + 2049 * v11;
      v15 = v12;
      if ( v12 >= *(_QWORD *)(v3 + 8 * ((unsigned int)i + 2049 * v10) + 168) - *(_QWORD *)(v3 + 8 * v14 + 168) )
        v15 = *(_QWORD *)(v3 + 8 * ((unsigned int)i + 2049 * v10) + 168) - *(_QWORD *)(v3 + 8 * v14 + 168);
      v16 = 0.0;
      if ( v12 )
      {
        if ( v15 < 0 )
          v17 = (double)(int)(v15 & 1 | ((unsigned __int64)v15 >> 1))
              + (double)(int)(v15 & 1 | ((unsigned __int64)v15 >> 1));
        else
          v17 = (double)(int)v15;
        v18 = v17 * 100000.0;
        if ( (v12 & 0x8000000000000000uLL) != 0LL )
          v19 = (double)(int)(v12 & 1 | (v12 >> 1)) + (double)(int)(v12 & 1 | (v12 >> 1));
        else
          v19 = (double)(int)v12;
        v16 = v18 / v19;
      }
      *((_DWORD *)Src[0] + i) = (int)v16;
    }
  }
  RrwLockRelease(v3 + 112);
  v20 = ((char *)Src[1] - (char *)Src[0]) >> 2;
  Vector = SafeArrayCreateVectorEx(0x13u, 0, v20, 0);
  v22 = Vector;
  if ( !Vector )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x250,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)0x8007000ELL,
      (int)v27);
  v27 = Vector;
  psa = Vector;
  ppvData = 0;
  v23 = SafeArrayAccessData(Vector, &ppvData);
  if ( v23 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x7B2,
      (unsigned int)"onecore\\vm\\common\\vml\\VmAutomation.h",
      (const char *)(unsigned int)v23,
      (int)v27);
  memcpy_0(ppvData, Src[0], 4LL * (unsigned int)v20);
  if ( psa )
    SafeArrayUnaccessData(psa);
  *a2 = v22;
  v24 = Src[0];
  if ( Src[0] )
  {
    v25 = (SAFEARRAY *)((v29 - (unsigned __int64)Src[0]) & 0xFFFFFFFFFFFFFFFCuLL);
    psa = v25;
    v27 = Src[0];
    if ( (unsigned __int64)v25 >= 0x1000 )
    {
      std::_Adjust_manually_vector_aligned(&v27, (unsigned __int64 *)&psa);
      v25 = psa;
      v24 = v27;
    }
    operator delete(v24, (const struct std::nothrow_t *)v25);
  }
}

```

## disassembly

```asm
0x140040a50  mov     [rsp-18h+arg_10], rbx
0x140040a55  mov     [rsp-18h+arg_18], rsi
0x140040a5a  push    rbp
0x140040a5b  push    rdi
0x140040a5c  push    r14
0x140040a5e  mov     rbp, rsp
0x140040a61  sub     rsp, 50h
0x140040a65  mov     r14, rdx
0x140040a68  mov     qword ptr [rdx], 0
0x140040a6f  mov     [rbp+var_30], 0
0x140040a77  xor     eax, eax
0x140040a79  xorps   xmm1, xmm1
0x140040a7c  movdqu  xmmword ptr [rbp+Src], xmm1
0x140040a81  mov     [rbp+var_18], rax
0x140040a85  mov     rsi, [rcx+2E8h]
0x140040a8c  mov     edi, [rsi+50h]
0x140040a8f  test    rdi, rdi
0x140040a92  jz      short loc_140040ADD
0x140040a94  mov     ecx, edi
0x140040a96  call    ??$_Get_size_of_n@$03@std@@YA_K_K@Z; std::_Get_size_of_n<4>(unsigned __int64)
0x140040a9b  mov     rcx, rax
0x140040a9e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x140040aa3  mov     rbx, rax
0x140040aa6  lea     r8, ds:0[rdi*4]; Size
0x140040aae  xor     edx, edx; Val
0x140040ab0  mov     rcx, rax; void *
0x140040ab3  call    memset_0
0x140040ab8  mov     rdx, [rbp+Src]; Src
0x140040abc  mov     r8, [rbp+Src+8]
0x140040ac0  sub     r8, rdx; Size
0x140040ac3  mov     rcx, rbx; void *
0x140040ac6  call    memmove_0
0x140040acb  mov     r9d, edi
0x140040ace  mov     r8d, edi
0x140040ad1  mov     rdx, rbx
0x140040ad4  lea     rcx, [rbp+Src]
0x140040ad8  call    ?_Change_array@?$vector@KV?$allocator@K@std@@@std@@AEAAXQEAK_K1@Z; std::vector<ulong>::_Change_array(ulong * const,unsigned __int64,unsigned __int64)
0x140040add  lea     rdi, [rsi+70h]
0x140040ae1  mov     ecx, 4
0x140040ae6  xor     eax, eax
0x140040ae8  lock cmpxchg [rdi], ecx
0x140040aec  mov     ebx, eax
0x140040aee  jz      short loc_140040B1E
0x140040af0  test    al, 1
0x140040af2  jnz     loc_140040D4E
0x140040af8  test    bl, 1
0x140040afb  jz      loc_140040CFD
0x140040b01  xor     r8d, r8d
0x140040b04  or      edx, 0FFFFFFFFh
0x140040b07  mov     rcx, rdi
0x140040b0a  call    RrwpLockWait
0x140040b0f  test    eax, eax
0x140040b11  jz      loc_140040D6E
0x140040b17  prefetchw byte ptr [rdi]
0x140040b1a  mov     ebx, [rdi]
0x140040b1c  jmp     short loc_140040AF8
0x140040b1e  cmp     dword ptr [rsi+0A4h], 2
0x140040b25  jb      loc_140040C24
0x140040b2b  mov     r8d, [rsi+0A0h]
0x140040b32  add     r8d, 64h ; 'd'
0x140040b36  mov     r9d, 446F8657h
0x140040b3c  mov     eax, r9d
0x140040b3f  mul     r8d
0x140040b42  mov     ecx, r8d
0x140040b45  sub     ecx, edx
0x140040b47  shr     ecx, 1
0x140040b49  add     ecx, edx
0x140040b4b  shr     ecx, 6
0x140040b4e  imul    ecx, 65h ; 'e'
0x140040b51  sub     r8d, ecx
0x140040b54  mov     r11d, r8d
0x140040b57  lea     ecx, [r8+64h]
0x140040b5b  mov     eax, r9d
0x140040b5e  mul     ecx
0x140040b60  mov     eax, ecx
0x140040b62  sub     eax, edx
0x140040b64  shr     eax, 1
0x140040b66  add     eax, edx
0x140040b68  shr     eax, 6
0x140040b6b  imul    eax, 65h ; 'e'
0x140040b6e  sub     ecx, eax
0x140040b70  mov     ebx, ecx
0x140040b72  imul    rcx, r11, 4008h
0x140040b79  imul    rax, rbx, 4008h
0x140040b80  mov     r8, [rcx+rsi+40A8h]
0x140040b88  sub     r8, [rax+rsi+40A8h]
0x140040b90  xor     r9d, r9d
0x140040b93  cmp     [rsi+50h], r9d
0x140040b97  jbe     loc_140040C24
0x140040b9d  cmp     r9d, 800h
0x140040ba4  jnb     short loc_140040C24
0x140040ba6  mov     r10d, r9d
0x140040ba9  imul    rcx, r11, 801h
0x140040bb0  add     rcx, r10
0x140040bb3  imul    rax, rbx, 801h
0x140040bba  add     rax, r10
0x140040bbd  mov     rdx, [rsi+rcx*8+0A8h]
0x140040bc5  sub     rdx, [rsi+rax*8+0A8h]
0x140040bcd  mov     rcx, r8
0x140040bd0  cmp     r8, rdx
0x140040bd3  cmovnb  rcx, rdx
0x140040bd7  xorps   xmm0, xmm0
0x140040bda  test    r8, r8
0x140040bdd  jz      short loc_140040C0A
0x140040bdf  test    rcx, rcx
0x140040be2  js      loc_140040D17
0x140040be8  cvtsi2sd xmm0, rcx
0x140040bed  mulsd   xmm0, cs:__real@40f86a0000000000
0x140040bf5  xorps   xmm1, xmm1
0x140040bf8  test    r8, r8
0x140040bfb  js      loc_140040D31
0x140040c01  cvtsi2sd xmm1, r8
0x140040c06  divsd   xmm0, xmm1
0x140040c0a  cvttsd2si rdx, xmm0
0x140040c0f  mov     rax, [rbp+Src]
0x140040c13  mov     [rax+r9*4], edx
0x140040c17  inc     r9d
0x140040c1a  cmp     r9d, [rsi+50h]
0x140040c1e  jb      loc_140040B9D
0x140040c24  mov     rcx, rdi
0x140040c27  call    RrwLockRelease
0x140040c2c  mov     rbx, [rbp+Src+8]
0x140040c30  sub     rbx, [rbp+Src]
0x140040c34  sar     rbx, 2
0x140040c38  mov     ecx, 13h; vt
0x140040c3d  xor     r9d, r9d; pvExtra
0x140040c40  mov     r8d, ebx; cElements
0x140040c43  xor     edx, edx; lLbound
0x140040c45  call    cs:__imp_SafeArrayCreateVectorEx
0x140040c4c  nop     dword ptr [rax+rax+00h]
0x140040c51  mov     rdi, rax
0x140040c54  test    rax, rax
0x140040c57  jz      loc_140040D8A
0x140040c5d  mov     [rbp+var_30], rax
0x140040c61  mov     [rbp+psa], rax
0x140040c65  mov     [rbp+ppvData], 0
0x140040c6d  lea     rdx, [rbp+ppvData]; ppvData
0x140040c71  mov     rcx, rax; psa
0x140040c74  call    cs:__imp_SafeArrayAccessData
0x140040c7b  nop     dword ptr [rax+rax+00h]
0x140040c80  mov     rcx, [rbp+18h]; this
0x140040c84  test    eax, eax
0x140040c86  js      loc_140040DA6
0x140040c8c  mov     r8d, ebx
0x140040c8f  shl     r8, 2; Size
0x140040c93  mov     rdx, [rbp+Src]; Src
0x140040c97  mov     rcx, [rbp+ppvData]; void *
0x140040c9b  call    memcpy_0
0x140040ca0  mov     rcx, [rbp+psa]; psa
0x140040ca4  test    rcx, rcx
0x140040ca7  jz      short loc_140040CB5
0x140040ca9  call    cs:__imp_SafeArrayUnaccessData
0x140040cb0  nop     dword ptr [rax+rax+00h]
0x140040cb5  mov     [r14], rdi
0x140040cb8  mov     rcx, [rbp+Src]; void *
0x140040cbc  test    rcx, rcx
0x140040cbf  jz      short loc_140040CE7
0x140040cc1  mov     rdx, [rbp+var_18]
0x140040cc5  sub     rdx, rcx
0x140040cc8  and     rdx, 0FFFFFFFFFFFFFFFCh; struct std::nothrow_t *
0x140040ccc  mov     [rbp+psa], rdx
0x140040cd0  mov     [rbp+var_30], rcx
0x140040cd4  cmp     rdx, 1000h
0x140040cdb  jnb     loc_140040DBB
0x140040ce1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140040ce6  nop
0x140040ce7  lea     r11, [rsp+50h+var_s0]
0x140040cec  mov     rbx, [r11+30h]
0x140040cf0  mov     rsi, [r11+38h]
0x140040cf4  mov     rsp, r11
0x140040cf7  pop     r14
0x140040cf9  pop     rdi
0x140040cfa  pop     rbp
0x140040cfb  retn
0x140040cfd  mov     edx, ebx
0x140040cff  lea     ecx, [rbx+4]
0x140040d02  mov     eax, ebx
0x140040d04  lock cmpxchg [rdi], ecx
0x140040d08  mov     ebx, eax
0x140040d0a  cmp     eax, edx
0x140040d0c  jnz     loc_140040AF8
0x140040d12  jmp     loc_140040B1E
0x140040d17  mov     rax, rcx
0x140040d1a  shr     rax, 1
0x140040d1d  and     ecx, 1
0x140040d20  or      rax, rcx
0x140040d23  cvtsi2sd xmm0, rax
0x140040d28  addsd   xmm0, xmm0
0x140040d2c  jmp     loc_140040BED
0x140040d31  mov     rcx, r8
0x140040d34  shr     rcx, 1
0x140040d37  mov     rax, r8
0x140040d3a  and     eax, 1
0x140040d3d  or      rcx, rax
0x140040d40  cvtsi2sd xmm1, rcx
0x140040d45  addsd   xmm1, xmm1
0x140040d49  jmp     loc_140040C06
0x140040d4e  call    cs:__imp_GetCurrentThreadId
0x140040d55  nop     dword ptr [rax+rax+00h]
0x140040d5a  mov     ecx, [rdi+4]
0x140040d5d  cmp     ecx, eax
0x140040d5f  jnz     loc_140040AF8
0x140040d65  lock inc dword ptr [rdi+8]
0x140040d69  jmp     loc_140040B1E
0x140040d6e  mov     rcx, [rbp+18h]; this
0x140040d72  mov     r9d, 102h; char *
0x140040d78  lea     r8, aOnecoreVmCommo_24; "onecore\\vm\\common\\vml\\VmReaderWrite"...
0x140040d7f  mov     edx, 249h; void *
0x140040d84  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x140040d8a  mov     rcx, [rbp+18h]; this
0x140040d8e  mov     r9d, 8007000Eh; char *
0x140040d94  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140040d9b  mov     edx, 250h; void *
0x140040da0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140040da6  mov     r9d, eax; char *
0x140040da9  lea     r8, aOnecoreVmCommo_54; "onecore\\vm\\common\\vml\\VmAutomation."...
0x140040db0  mov     edx, 7B2h; void *
0x140040db5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x140040dbb  lea     rdx, [rbp+psa]; unsigned __int64 *
0x140040dbf  lea     rcx, [rbp+var_30]; void **
0x140040dc3  call    ?_Adjust_manually_vector_aligned@std@@YAXAEAPEAXAEA_K@Z; std::_Adjust_manually_vector_aligned(void * &,unsigned __int64 &)
0x140040dc8  mov     rdx, [rbp+psa]
0x140040dcc  mov     rcx, [rbp+var_30]
0x140040dd0  jmp     loc_140040CE1
```
