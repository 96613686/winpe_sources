# ATL::CRegParser::PreProcessBuffer(wchar_t *,wchar_t * *)

- ea: `0x1400217e8`
- end: `0x140021a55`
- name: `?PreProcessBuffer@CRegParser@ATL@@QEAAJPEA_WPEAPEA_W@Z`
- size: `621`
- prototype: `int(ATL::CRegParser *__hidden this, wchar_t *, wchar_t **)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x140024714`

## callees

- `0x140005240`
- `0x14000e534`
- `0x1400123b8`
- `0x140012480`
- `0x14001e0a4`
- `0x1400217e8`
- `0x140029948`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14002192b`
- `api-ms-win-crt-private-l1-1-0!_o_wcsncpy_s` at `0x14002192b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140021943`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140021943`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002198c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14002198c`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400218c1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400219d0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400219e6`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400218c1`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400219d0`
- `api-ms-win-core-string-l2-1-0!CharNextW` at `0x1400219e6`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140021964`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrcmpiW` at `0x140021964`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140021878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x140021878`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021a1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140021a1f`

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
0x1400217e8  mov     rax, rsp
0x1400217eb  push    rbp
0x1400217ec  push    rsi
0x1400217ed  push    rdi
0x1400217ee  push    r12
0x1400217f0  push    r13
0x1400217f2  push    r14
0x1400217f4  push    r15
0x1400217f6  lea     rbp, [rax-5Fh]
0x1400217fa  sub     rsp, 90h
0x140021801  mov     [rbp+57h+var_88], 0FFFFFFFFFFFFFFFEh
0x140021809  mov     [rax+10h], rbx
0x14002180d  mov     rax, cs:__security_cookie
0x140021814  xor     rax, rsp
0x140021817  mov     [rbp+57h+var_40], rax
0x14002181b  mov     r15, r8
0x14002181e  mov     rbx, rdx
0x140021821  mov     rdi, rcx
0x140021824  xor     r13d, r13d
0x140021827  test    rdx, rdx
0x14002182a  jz      loc_140021A29
0x140021830  test    r8, r8
0x140021833  jz      loc_140021A29
0x140021839  mov     [r8], r13
0x14002183c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140021840  inc     rax
0x140021843  cmp     [rdx+rax*2], r13w
0x140021848  jnz     short loc_140021840
0x14002184a  add     eax, eax
0x14002184c  mov     ecx, 3E8h
0x140021851  cmp     eax, 64h ; 'd'
0x140021854  cmovl   eax, ecx
0x140021857  mov     [rbp+57h+var_A0], r13d
0x14002185b  mov     [rbp+57h+var_9C], eax
0x14002185e  mov     ecx, eax
0x140021860  add     rcx, rcx
0x140021863  mov     eax, 0FFFFFFFFh
0x140021868  cmp     rcx, rax
0x14002186b  jbe     short loc_140021876
0x14002186d  mov     rax, r13
0x140021870  mov     [rbp+57h+pv], r13
0x140021874  jmp     short loc_14002188B
0x140021876  mov     ecx, ecx; cb
0x140021878  call    cs:__imp_CoTaskMemAlloc
0x14002187e  mov     [rbp+57h+pv], rax
0x140021882  test    rax, rax
0x140021885  jz      short loc_14002188B
0x140021887  mov     [rax], r13w
0x14002188b  test    rax, rax
0x14002188e  jnz     short loc_1400218A3
0x140021890  mov     rcx, rax; pv
0x140021893  call    cs:__imp_CoTaskMemFree
0x140021899  mov     eax, 8007000Eh
0x14002189e  jmp     loc_140021A2E
0x1400218a3  mov     [rdi], rbx
0x1400218a6  mov     esi, 25h ; '%'
0x1400218ab  cmp     [rbx], r13w
0x1400218af  jz      loc_140021A0D
0x1400218b5  cmp     [rbx], si
0x1400218b8  jnz     loc_1400219F7
0x1400218be  mov     rcx, rbx; lpsz
0x1400218c1  call    cs:__imp_CharNextW
0x1400218c7  mov     [rdi], rax
0x1400218ca  cmp     [rax], si
0x1400218cd  jnz     short loc_1400218F3
0x1400218cf  mov     rdx, rax; wchar_t *
0x1400218d2  mov     r8d, 1; int
0x1400218d8  lea     rcx, [rbp+57h+var_A0]; this
0x1400218dc  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x1400218e1  test    eax, eax
0x1400218e3  jnz     loc_1400219E3
0x1400218e9  mov     ebx, 8007000Eh
0x1400218ee  jmp     loc_140021A1B
0x1400218f3  mov     edx, esi; wchar_t
0x1400218f5  mov     rcx, rax; lpsz
0x1400218f8  call    ?StrChrW@CRegParser@ATL@@KAPEA_WPEA_W_W@Z; ATL::CRegParser::StrChrW(wchar_t *,wchar_t)
0x1400218fd  mov     rsi, rax
0x140021900  test    rax, rax
0x140021903  jz      loc_140021A06
0x140021909  mov     rcx, rax
0x14002190c  sub     rcx, [rdi]
0x14002190f  sar     rcx, 1
0x140021912  cmp     rcx, 1Fh
0x140021916  jg      loc_1400219FF
0x14002191c  movsxd  r9, ecx
0x14002191f  mov     r8, [rdi]
0x140021922  mov     edx, 20h ; ' '
0x140021927  lea     rcx, [rbp+57h+String2]
0x14002192b  call    cs:__imp__o_wcsncpy_s
0x140021931  mov     ecx, eax; int
0x140021933  call    ?AtlCrtErrorCheck@ATL@@YAHH@Z; ATL::AtlCrtErrorCheck(int)
0x140021938  mov     rbx, [rdi+8]
0x14002193c  lea     r12, [rbx+20h]
0x140021940  mov     rcx, r12; lpCriticalSection
0x140021943  call    cs:__imp_EnterCriticalSection
0x140021949  lea     r14, [rbx+8]
0x14002194d  mov     ebx, r13d
0x140021950  cmp     ebx, [r14+10h]
0x140021954  jge     short loc_140021986
0x140021956  movsxd  rax, ebx
0x140021959  mov     rcx, [r14]
0x14002195c  lea     rdx, [rbp+57h+String2]; lpString2
0x140021960  mov     rcx, [rcx+rax*8]; lpString1
0x140021964  call    cs:__imp_lstrcmpiW
0x14002196a  test    eax, eax
0x14002196c  jz      short loc_140021972
0x14002196e  inc     ebx
0x140021970  jmp     short loc_140021950
0x140021972  cmp     ebx, 0FFFFFFFFh
0x140021975  jz      short loc_140021986
0x140021977  mov     edx, ebx
0x140021979  mov     rcx, r14
0x14002197c  call    ?GetValueAt@?$CSimpleMap@PEA_WPEA_WVCExpansionVectorEqualHelper@ATL@@@ATL@@QEBAAEAPEA_WH@Z; ATL::CSimpleMap<wchar_t *,wchar_t *,ATL::CExpansionVectorEqualHelper>::GetValueAt(int)
0x140021981  mov     rbx, [rax]
0x140021984  jmp     short loc_140021989
0x140021986  mov     rbx, r13
0x140021989  mov     rcx, r12; lpCriticalSection
0x14002198c  call    cs:__imp_LeaveCriticalSection
0x140021992  test    rbx, rbx
0x140021995  jz      short loc_140021A06
0x140021997  mov     [rbp+57h+var_90], r13
0x14002199b  or      r8, 0FFFFFFFFFFFFFFFFh
0x14002199f  inc     r8; int
0x1400219a2  cmp     [rbx+r8*2], r13w
0x1400219a7  jnz     short loc_14002199F
0x1400219a9  mov     rdx, rbx; wchar_t *
0x1400219ac  lea     rcx, [rbp+57h+var_A0]; this
0x1400219b0  call    ?Append@CParseBuffer@CRegParser@ATL@@QEAAHPEB_WH@Z; ATL::CRegParser::CParseBuffer::Append(wchar_t const *,int)
0x1400219b5  mov     ebx, eax
0x1400219b7  lea     rcx, [rbp+57h+var_90]
0x1400219bb  call    ??1?$CAtlSafeAllocBufferManager@VCCRTAllocator@ATL@@@_ATL_SAFE_ALLOCA_IMPL@ATL@@QEAA@XZ; ATL::_ATL_SAFE_ALLOCA_IMPL::CAtlSafeAllocBufferManager<ATL::CCRTAllocator>::~CAtlSafeAllocBufferManager<ATL::CCRTAllocator>(void)
0x1400219c0  test    ebx, ebx
0x1400219c2  jz      loc_1400218E9
0x1400219c8  mov     rax, [rdi]
0x1400219cb  jmp     short loc_1400219D9
0x1400219cd  mov     rcx, rax; lpsz
0x1400219d0  call    cs:__imp_CharNextW
0x1400219d6  mov     [rdi], rax
0x1400219d9  cmp     rax, rsi
0x1400219dc  jnz     short loc_1400219CD
0x1400219de  mov     esi, 25h ; '%'
0x1400219e3  mov     rcx, [rdi]; lpsz
0x1400219e6  call    cs:__imp_CharNextW
0x1400219ec  mov     rbx, rax
0x1400219ef  mov     [rdi], rax
0x1400219f2  jmp     loc_1400218AB
0x1400219f7  mov     rdx, rbx
0x1400219fa  jmp     loc_1400218D2
0x1400219ff  mov     ebx, 80004005h
0x140021a04  jmp     short loc_140021A1B
0x140021a06  mov     ebx, 80020009h
0x140021a0b  jmp     short loc_140021A1B
0x140021a0d  mov     ebx, r13d
0x140021a10  mov     rcx, [rbp+57h+pv]
0x140021a14  mov     [rbp+57h+pv], r13
0x140021a18  mov     [r15], rcx
0x140021a1b  mov     rcx, [rbp+57h+pv]; pv
0x140021a1f  call    cs:__imp_CoTaskMemFree
0x140021a25  mov     eax, ebx
0x140021a27  jmp     short loc_140021A2E
0x140021a29  mov     eax, 80004003h
0x140021a2e  mov     rcx, [rbp+57h+var_40]
0x140021a32  xor     rcx, rsp; StackCookie
0x140021a35  call    __security_check_cookie
0x140021a3a  mov     rbx, [rsp+0C0h+arg_8]
0x140021a42  add     rsp, 90h
0x140021a49  pop     r15
0x140021a4b  pop     r14
0x140021a4d  pop     r13
0x140021a4f  pop     r12
0x140021a51  pop     rdi
0x140021a52  pop     rsi
0x140021a53  pop     rbp
0x140021a54  retn
```
