# ATL::CRegParser::PreProcessBuffer(ushort *,ushort * *)

- ea: `0x18000d3ac`
- end: `0x18000d610`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEAGPEAPEAG@Z`
- size: `612`
- prototype: `int(ATL::CRegParser *__hidden this, unsigned __int16 *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000e458`

## callees

- `0x180001720`
- `0x1800082ec`
- `0x180009ce0`
- `0x180009da8`
- `0x18000ba74`
- `0x18000d3ac`
- `0x18000fe0c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000d4e6`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x18000d4e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d44e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d44e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000d5da`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d433`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000d433`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d47c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d58b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d5a1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d47c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d58b`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x18000d5a1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d547`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d547`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4fe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d4fe`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000d51f`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x18000d51f`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(
        ATL::CRegParser *this,
        unsigned __int16 *a2,
        unsigned __int16 **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const unsigned __int16 *v12; // rdx
  unsigned int v13; // ebx
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 v20; // r14
  unsigned int i; // ebx
  const unsigned __int16 *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  unsigned __int16 *v26; // rcx
  __int64 v27; // [rsp+20h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+28h] [rbp-41h]
  __int64 v29; // [rsp+30h] [rbp-39h] BYREF
  WCHAR String2[32]; // [rsp+40h] [rbp-29h] BYREF

  v4 = a2;
  if ( !a2 || !a3 )
    return 2147500035LL;
  *a3 = 0;
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = 2 * v6;
  if ( v7 < 100 )
    v7 = 1000;
  LODWORD(v27) = 0;
  HIDWORD(v27) = v7;
  v8 = 2LL * (unsigned int)v7;
  if ( v8 <= 0xFFFFFFFF )
  {
    v9 = CoTaskMemAlloc((unsigned int)v8);
    pv = v9;
    if ( v9 )
      *v9 = 0;
  }
  else
  {
    v9 = 0;
    pv = 0;
  }
  if ( !v9 )
  {
    CoTaskMemFree(0);
    return 2147942414LL;
  }
  *(_QWORD *)this = v4;
  while ( *v4 )
  {
    if ( *v4 != 37 )
    {
      v12 = v4;
LABEL_18:
      if ( !ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
        goto LABEL_19;
      goto LABEL_36;
    }
    v11 = CharNextW(v4);
    *(_QWORD *)this = v11;
    if ( *v11 == 37 )
    {
      v12 = v11;
      goto LABEL_18;
    }
    v14 = ATL::CRegParser::StrChrW(v11, 0x25u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_39;
    v16 = ((__int64)v14 - *(_QWORD *)this) >> 1;
    if ( v16 > 31 )
    {
      v13 = -2147467259;
      goto LABEL_41;
    }
    v17 = _o_wcsncpy_s(String2, 32, *(_QWORD *)this, (int)v16, v27);
    ATL::AtlCrtErrorCheck(v17);
    v18 = *((_QWORD *)this + 1);
    v19 = (struct _RTL_CRITICAL_SECTION *)(v18 + 32);
    EnterCriticalSection((LPCRITICAL_SECTION)(v18 + 32));
    v20 = v18 + 8;
    for ( i = 0; (signed int)i < *(_DWORD *)(v20 + 16); ++i )
    {
      if ( !lstrcmpiW(*(LPCWSTR *)(*(_QWORD *)v20 + 8LL * (int)i), String2) )
      {
        if ( i != -1 )
        {
          v22 = *(const unsigned __int16 **)ATL::CSimpleMap<unsigned short *,unsigned short *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
                                              v20,
                                              i);
          goto LABEL_29;
        }
        break;
      }
    }
    v22 = 0;
LABEL_29:
    LeaveCriticalSection(v19);
    if ( !v22 )
    {
LABEL_39:
      v13 = -2147352567;
      goto LABEL_41;
    }
    v29 = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(&v29);
    if ( !v24 )
    {
LABEL_19:
      v13 = -2147024882;
      goto LABEL_41;
    }
    for ( j = *(const WCHAR **)this; j != v15; *(_QWORD *)this = j )
      j = CharNextW(j);
LABEL_36:
    v4 = CharNextW(*(LPCWSTR *)this);
    *(_QWORD *)this = v4;
  }
  v13 = 0;
  v26 = (unsigned __int16 *)pv;
  pv = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x18000d3ac  mov     [rsp-8+arg_8], rbx
0x18000d3b1  push    rbp
0x18000d3b2  push    rsi
0x18000d3b3  push    rdi
0x18000d3b4  push    r12
0x18000d3b6  push    r13
0x18000d3b8  push    r14
0x18000d3ba  push    r15
0x18000d3bc  lea     rbp, [rsp-27h]
0x18000d3c1  sub     rsp, 90h
0x18000d3c8  mov     rax, cs:__security_cookie
0x18000d3cf  xor     rax, rsp
0x18000d3d2  mov     [rbp+57h+var_40], rax
0x18000d3d6  mov     r15, r8
0x18000d3d9  mov     rbx, rdx
0x18000d3dc  mov     rdi, rcx
0x18000d3df  xor     r13d, r13d
0x18000d3e2  test    rdx, rdx
0x18000d3e5  jz      loc_18000D5E4
0x18000d3eb  test    r8, r8
0x18000d3ee  jz      loc_18000D5E4
0x18000d3f4  mov     [r8], r13
0x18000d3f7  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000d3fb  inc     rax
0x18000d3fe  cmp     [rdx+rax*2], r13w
0x18000d403  jnz     short loc_18000D3FB
0x18000d405  add     eax, eax
0x18000d407  mov     ecx, 3E8h
0x18000d40c  cmp     eax, 64h ; 'd'
0x18000d40f  cmovl   eax, ecx
0x18000d412  mov     [rbp+57h+var_A0], r13d
0x18000d416  mov     [rbp+57h+var_9C], eax
0x18000d419  mov     ecx, eax
0x18000d41b  add     rcx, rcx
0x18000d41e  mov     eax, 0FFFFFFFFh
0x18000d423  cmp     rcx, rax
0x18000d426  jbe     short loc_18000D431
0x18000d428  mov     rax, r13
0x18000d42b  mov     [rbp+57h+pv], r13
0x18000d42f  jmp     short loc_18000D446
0x18000d431  mov     ecx, ecx; cb
0x18000d433  call    cs:__imp_CoTaskMemAlloc
0x18000d439  mov     [rbp+57h+pv], rax
0x18000d43d  test    rax, rax
0x18000d440  jz      short loc_18000D446
0x18000d442  mov     [rax], r13w
0x18000d446  test    rax, rax
0x18000d449  jnz     short loc_18000D45E
0x18000d44b  mov     rcx, rax; pv
0x18000d44e  call    cs:__imp_CoTaskMemFree
0x18000d454  mov     eax, 8007000Eh
0x18000d459  jmp     loc_18000D5E9
0x18000d45e  mov     [rdi], rbx
0x18000d461  mov     esi, 25h ; '%'
0x18000d466  cmp     [rbx], r13w
0x18000d46a  jz      loc_18000D5C8
0x18000d470  cmp     [rbx], si
0x18000d473  jnz     loc_18000D5B2
0x18000d479  mov     rcx, rbx; lpsz
0x18000d47c  call    cs:__imp_CharNextW
0x18000d482  mov     [rdi], rax
0x18000d485  cmp     [rax], si
0x18000d488  jnz     short loc_18000D4AE
0x18000d48a  mov     rdx, rax; unsigned __int16 *
0x18000d48d  mov     r8d, 1; int
0x18000d493  lea     rcx, [rbp+57h+var_A0]; this
0x18000d497  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000d49c  test    eax, eax
0x18000d49e  jnz     loc_18000D59E
0x18000d4a4  mov     ebx, 8007000Eh
0x18000d4a9  jmp     loc_18000D5D6
0x18000d4ae  mov     edx, esi; unsigned __int16
0x18000d4b0  mov     rcx, rax; lpsz
0x18000d4b3  call    ?StrChrW@CRegParser@ATL@@KAPEAGPEAGG@Z; ATL::CRegParser::StrChrW(ushort *,ushort)
0x18000d4b8  mov     rsi, rax
0x18000d4bb  test    rax, rax
0x18000d4be  jz      loc_18000D5C1
0x18000d4c4  mov     rcx, rax
0x18000d4c7  sub     rcx, [rdi]
0x18000d4ca  sar     rcx, 1
0x18000d4cd  cmp     rcx, 1Fh
0x18000d4d1  jg      loc_18000D5BA
0x18000d4d7  movsxd  r9, ecx
0x18000d4da  mov     r8, [rdi]
0x18000d4dd  mov     edx, 20h ; ' '
0x18000d4e2  lea     rcx, [rbp+57h+String2]
0x18000d4e6  call    cs:__imp__o_wcsncpy_s
0x18000d4ec  mov     ecx, eax; int
0x18000d4ee  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x18000d4f3  mov     rbx, [rdi+8]
0x18000d4f7  lea     r12, [rbx+20h]
0x18000d4fb  mov     rcx, r12; lpCriticalSection
0x18000d4fe  call    cs:__imp_EnterCriticalSection
0x18000d504  lea     r14, [rbx+8]
0x18000d508  mov     ebx, r13d
0x18000d50b  cmp     ebx, [r14+10h]
0x18000d50f  jge     short loc_18000D541
0x18000d511  movsxd  rax, ebx
0x18000d514  mov     rcx, [r14]
0x18000d517  lea     rdx, [rbp+57h+String2]; lpString2
0x18000d51b  mov     rcx, [rcx+rax*8]; lpString1
0x18000d51f  call    cs:__imp_lstrcmpiW
0x18000d525  test    eax, eax
0x18000d527  jz      short loc_18000D52D
0x18000d529  inc     ebx
0x18000d52b  jmp     short loc_18000D50B
0x18000d52d  cmp     ebx, 0FFFFFFFFh
0x18000d530  jz      short loc_18000D541
0x18000d532  mov     edx, ebx
0x18000d534  mov     rcx, r14
0x18000d537  call    ?GetValueAt@?$CSimpleMap@PEAGPEAGVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEAGH@Z; ATL::CSimpleMap<ushort *,ushort *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x18000d53c  mov     rbx, [rax]
0x18000d53f  jmp     short loc_18000D544
0x18000d541  mov     rbx, r13
0x18000d544  mov     rcx, r12; lpCriticalSection
0x18000d547  call    cs:__imp_LeaveCriticalSection
0x18000d54d  test    rbx, rbx
0x18000d550  jz      short loc_18000D5C1
0x18000d552  mov     [rbp+57h+var_90], r13
0x18000d556  or      r8, 0FFFFFFFFFFFFFFFFh
0x18000d55a  inc     r8; int
0x18000d55d  cmp     [rbx+r8*2], r13w
0x18000d562  jnz     short loc_18000D55A
0x18000d564  mov     rdx, rbx; unsigned __int16 *
0x18000d567  lea     rcx, [rbp+57h+var_A0]; this
0x18000d56b  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEBGH@Z; ATL::CRegParser::CParseBuffer::Append(ushort const *,int)
0x18000d570  mov     ebx, eax
0x18000d572  lea     rcx, [rbp+57h+var_90]
0x18000d576  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x18000d57b  test    ebx, ebx
0x18000d57d  jz      loc_18000D4A4
0x18000d583  mov     rax, [rdi]
0x18000d586  jmp     short loc_18000D594
0x18000d588  mov     rcx, rax; lpsz
0x18000d58b  call    cs:__imp_CharNextW
0x18000d591  mov     [rdi], rax
0x18000d594  cmp     rax, rsi
0x18000d597  jnz     short loc_18000D588
0x18000d599  mov     esi, 25h ; '%'
0x18000d59e  mov     rcx, [rdi]; lpsz
0x18000d5a1  call    cs:__imp_CharNextW
0x18000d5a7  mov     rbx, rax
0x18000d5aa  mov     [rdi], rax
0x18000d5ad  jmp     loc_18000D466
0x18000d5b2  mov     rdx, rbx
0x18000d5b5  jmp     loc_18000D48D
0x18000d5ba  mov     ebx, 80004005h
0x18000d5bf  jmp     short loc_18000D5D6
0x18000d5c1  mov     ebx, 80020009h
0x18000d5c6  jmp     short loc_18000D5D6
0x18000d5c8  mov     ebx, r13d
0x18000d5cb  mov     rcx, [rbp+57h+pv]
0x18000d5cf  mov     [rbp+57h+pv], r13
0x18000d5d3  mov     [r15], rcx
0x18000d5d6  mov     rcx, [rbp+57h+pv]; pv
0x18000d5da  call    cs:__imp_CoTaskMemFree
0x18000d5e0  mov     eax, ebx
0x18000d5e2  jmp     short loc_18000D5E9
0x18000d5e4  mov     eax, 80004003h
0x18000d5e9  mov     rcx, [rbp+57h+var_40]
0x18000d5ed  xor     rcx, rsp; StackCookie
0x18000d5f0  call    __security_check_cookie
0x18000d5f5  mov     rbx, [rsp+0C0h+arg_8]
0x18000d5fd  add     rsp, 90h
0x18000d604  pop     r15
0x18000d606  pop     r14
0x18000d608  pop     r13
0x18000d60a  pop     r12
0x18000d60c  pop     rdi
0x18000d60d  pop     rsi
0x18000d60e  pop     rbp
0x18000d60f  retn
```
