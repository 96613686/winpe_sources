# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x140022414`
- end: `0x140022681`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140022ad0`

## callees

- `0x1400030a0`
- `0x14001b6ec`
- `0x14001d3d4`
- `0x14001d49c`
- `0x1400212c8`
- `0x140022414`
- `0x1400247b8`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140022557`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x140022557`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400225b8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400225b8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002256f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14002256f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400224bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002264b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1400224bf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14002264b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400224a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1400224a4`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400224ed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400225fc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140022612`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400224ed`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400225fc`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x140022612`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022590`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140022590`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall ATL::CRegParser::PreProcessBuffer(ATL::CRegParser *this, wchar_t *a2, wchar_t **a3)
{
  LPWSTR v4; // rbx
  __int64 v6; // rax
  int v7; // eax
  unsigned __int64 v8; // rcx
  _WORD *v9; // rax
  LPWSTR v11; // rax
  const wchar_t *v12; // rdx
  unsigned int v13; // ebx
  wchar_t *v14; // rax
  wchar_t *v15; // rsi
  __int64 v16; // rcx
  int v17; // eax
  __int64 v18; // rbx
  struct _RTL_CRITICAL_SECTION *v19; // r12
  __int64 v20; // r14
  unsigned int i; // ebx
  const wchar_t *v22; // rbx
  __int64 v23; // r8
  int v24; // ebx
  const WCHAR *j; // rax
  wchar_t *v26; // rcx
  __int64 v27; // [rsp+28h] [rbp-49h] BYREF
  LPVOID pv; // [rsp+30h] [rbp-41h]
  _QWORD v29[2]; // [rsp+38h] [rbp-39h] BYREF
  WCHAR String2[32]; // [rsp+48h] [rbp-29h] BYREF

  v29[1] = -2;
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
      if ( !(unsigned int)ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v12, 1) )
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
          v22 = *(const wchar_t **)ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(
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
    v29[0] = 0;
    v23 = -1;
    do
      ++v23;
    while ( v22[v23] );
    v24 = ATL::CRegParser::CParseBuffer::Append((ATL::CRegParser::CParseBuffer *)&v27, v22, v23);
    ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(v29);
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
  v26 = (wchar_t *)pv;
  pv = 0;
  *a3 = v26;
LABEL_41:
  CoTaskMemFree(pv);
  return v13;
}

```

## disassembly

```asm
0x140022414  mov     rax, rsp
0x140022417  push    rbp
0x140022418  push    rsi
0x140022419  push    rdi
0x14002241a  push    r12
0x14002241c  push    r13
0x14002241e  push    r14
0x140022420  push    r15
0x140022422  lea     rbp, [rax-5Fh]
0x140022426  sub     rsp, 90h
0x14002242d  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x140022435  mov     [rax+10h], rbx
0x140022439  mov     rax, cs:__security_cookie
0x140022440  xor     rax, rsp
0x140022443  mov     [rbp+57h+var_40], rax
0x140022447  mov     r15, r8
0x14002244a  mov     rbx, rdx
0x14002244d  mov     rdi, rcx
0x140022450  xor     r13d, r13d
0x140022453  test    rdx, rdx
0x140022456  jz      loc_140022655
0x14002245c  test    r8, r8
0x14002245f  jz      loc_140022655
0x140022465  mov     [r8], r13
0x140022468  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002246c  inc     rax
0x14002246f  cmp     [rdx+rax*2], r13w
0x140022474  jnz     short loc_14002246C
0x140022476  add     eax, eax
0x140022478  mov     ecx, 3E8h
0x14002247d  cmp     eax, 64h ; 'd'
0x140022480  cmovl   eax, ecx
0x140022483  mov     [rbp+57h+var_A0], r13d
0x140022487  mov     [rbp+57h+var_9C], eax
0x14002248a  mov     ecx, eax
0x14002248c  add     rcx, rcx
0x14002248f  mov     eax, 0FFFFFFFFh
0x140022494  cmp     rcx, rax
0x140022497  jbe     short loc_1400224A2
0x140022499  mov     rax, r13
0x14002249c  mov     [rbp+57h+pv], r13
0x1400224a0  jmp     short loc_1400224B7
0x1400224a2  mov     ecx, ecx; cb
0x1400224a4  call    cs:__imp_CoTaskMemAlloc
0x1400224aa  mov     [rbp+57h+pv], rax
0x1400224ae  test    rax, rax
0x1400224b1  jz      short loc_1400224B7
0x1400224b3  mov     [rax], r13w
0x1400224b7  test    rax, rax
0x1400224ba  jnz     short loc_1400224CF
0x1400224bc  mov     rcx, rax; pv
0x1400224bf  call    cs:__imp_CoTaskMemFree
0x1400224c5  mov     eax, 8007000Eh
0x1400224ca  jmp     loc_14002265A
0x1400224cf  mov     [rdi], rbx
0x1400224d2  mov     esi, 25h ; '%'
0x1400224d7  cmp     [rbx], r13w
0x1400224db  jz      loc_140022639
0x1400224e1  cmp     [rbx], si
0x1400224e4  jnz     loc_140022623
0x1400224ea  mov     rcx, rbx; lpsz
0x1400224ed  call    cs:__imp_CharNextW
0x1400224f3  mov     [rdi], rax
0x1400224f6  cmp     [rax], si
0x1400224f9  jnz     short loc_14002251F
0x1400224fb  mov     rdx, rax; wchar_t *
0x1400224fe  mov     r8d, 1; int
0x140022504  lea     rcx, [rbp+57h+var_A0]; this
0x140022508  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x14002250d  test    eax, eax
0x14002250f  jnz     loc_14002260F
0x140022515  mov     ebx, 8007000Eh
0x14002251a  jmp     loc_140022647
0x14002251f  mov     edx, esi; wchar_t
0x140022521  mov     rcx, rax; lpsz
0x140022524  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x140022529  mov     rsi, rax
0x14002252c  test    rax, rax
0x14002252f  jz      loc_140022632
0x140022535  mov     rcx, rax
0x140022538  sub     rcx, [rdi]
0x14002253b  sar     rcx, 1
0x14002253e  cmp     rcx, 1Fh
0x140022542  jg      loc_14002262B
0x140022548  movsxd  r9, ecx
0x14002254b  mov     r8, [rdi]
0x14002254e  mov     edx, 20h ; ' '
0x140022553  lea     rcx, [rbp+57h+String2]
0x140022557  call    cs:__imp__o_wcsncpy_s
0x14002255d  mov     ecx, eax; int
0x14002255f  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140022564  mov     rbx, [rdi+8]
0x140022568  lea     r12, [rbx+20h]
0x14002256c  mov     rcx, r12; lpCriticalSection
0x14002256f  call    cs:__imp_EnterCriticalSection
0x140022575  lea     r14, [rbx+8]
0x140022579  mov     ebx, r13d
0x14002257c  cmp     ebx, [r14+10h]
0x140022580  jge     short loc_1400225B2
0x140022582  movsxd  rax, ebx
0x140022585  mov     rcx, [r14]
0x140022588  lea     rdx, [rbp+57h+String2]; lpString2
0x14002258c  mov     rcx, [rcx+rax*8]; lpString1
0x140022590  call    cs:__imp_lstrcmpiW
0x140022596  test    eax, eax
0x140022598  jz      short loc_14002259E
0x14002259a  inc     ebx
0x14002259c  jmp     short loc_14002257C
0x14002259e  cmp     ebx, 0FFFFFFFFh
0x1400225a1  jz      short loc_1400225B2
0x1400225a3  mov     edx, ebx
0x1400225a5  mov     rcx, r14
0x1400225a8  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x1400225ad  mov     rbx, [rax]
0x1400225b0  jmp     short loc_1400225B5
0x1400225b2  mov     rbx, r13
0x1400225b5  mov     rcx, r12; lpCriticalSection
0x1400225b8  call    cs:__imp_LeaveCriticalSection
0x1400225be  test    rbx, rbx
0x1400225c1  jz      short loc_140022632
0x1400225c3  mov     [rbp+57h+var_90], r13
0x1400225c7  or      r8, 0FFFFFFFFFFFFFFFFh
0x1400225cb  inc     r8; int
0x1400225ce  cmp     [rbx+r8*2], r13w
0x1400225d3  jnz     short loc_1400225CB
0x1400225d5  mov     rdx, rbx; wchar_t *
0x1400225d8  lea     rcx, [rbp+57h+var_A0]; this
0x1400225dc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x1400225e1  mov     ebx, eax
0x1400225e3  lea     rcx, [rbp+57h+var_90]
0x1400225e7  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1400225ec  test    ebx, ebx
0x1400225ee  jz      loc_140022515
0x1400225f4  mov     rax, [rdi]
0x1400225f7  jmp     short loc_140022605
0x1400225f9  mov     rcx, rax; lpsz
0x1400225fc  call    cs:__imp_CharNextW
0x140022602  mov     [rdi], rax
0x140022605  cmp     rax, rsi
0x140022608  jnz     short loc_1400225F9
0x14002260a  mov     esi, 25h ; '%'
0x14002260f  mov     rcx, [rdi]; lpsz
0x140022612  call    cs:__imp_CharNextW
0x140022618  mov     rbx, rax
0x14002261b  mov     [rdi], rax
0x14002261e  jmp     loc_1400224D7
0x140022623  mov     rdx, rbx
0x140022626  jmp     loc_1400224FE
0x14002262b  mov     ebx, 80004005h
0x140022630  jmp     short loc_140022647
0x140022632  mov     ebx, 80020009h
0x140022637  jmp     short loc_140022647
0x140022639  mov     ebx, r13d
0x14002263c  mov     rcx, [rbp+57h+pv]
0x140022640  mov     [rbp+57h+pv], r13
0x140022644  mov     [r15], rcx
0x140022647  mov     rcx, [rbp+57h+pv]; pv
0x14002264b  call    cs:__imp_CoTaskMemFree
0x140022651  mov     eax, ebx
0x140022653  jmp     short loc_14002265A
0x140022655  mov     eax, 80004003h
0x14002265a  mov     rcx, [rbp+57h+var_40]
0x14002265e  xor     rcx, rsp; StackCookie
0x140022661  call    __security_check_cookie
0x140022666  mov     rbx, [rsp+0C0h+arg_8]
0x14002266e  add     rsp, 90h
0x140022675  pop     r15
0x140022677  pop     r14
0x140022679  pop     r13
0x14002267b  pop     r12
0x14002267d  pop     rdi
0x14002267e  pop     rsi
0x14002267f  pop     rbp
0x140022680  retn
```
