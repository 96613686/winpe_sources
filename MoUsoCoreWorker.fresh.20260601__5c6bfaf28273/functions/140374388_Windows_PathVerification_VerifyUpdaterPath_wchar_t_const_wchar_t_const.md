# Windows::PathVerification::VerifyUpdaterPath(wchar_t const *,wchar_t const *)

- ea: `0x140374388`
- end: `0x14037490a`
- name: `?VerifyUpdaterPath@PathVerification@Windows@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z`
- size: `1410`
- prototype: `_QWORD *__fastcall(_QWORD *, const char *, __int64)`
- caller_count: `3`
- callee_count: `16`
- tags: `reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x14030abbc`
- `0x1403277d4`
- `0x140336d60`

## callees

- `0x1400289d4`
- `0x14002cd1c`
- `0x14003c578`
- `0x14003f998`
- `0x1400413a8`
- `0x140043284`
- `0x140043504`
- `0x140045404`
- `0x1400b3eb4`
- `0x1400e7728`
- `0x14023682c`
- `0x1403134ac`
- `0x140374388`
- `0x140378dd4`
- `0x140379070`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140374575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140374620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140374792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403748ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140374575`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140374620`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140374792`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403748ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14037441c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x14037441c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1403743d3`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1403743d3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1403747ab`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1403747ab`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x1403747e3`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalize` at `0x1403747e3`

## string_xrefs

- `0x1403746e0`: `%ProgramData%\USOPrivate\Providers\Windows`
- `0x1403746b7`: `%ProgramData%\USOPrivate\Providers\Registered`
- `0x1403744be`: `%CommonProgramFiles%`
- `0x140374865`: `C:\__w\1\s\src\orchestrator\system\windows\common\PathVerification.cpp`
- `0x1403748e3`: `C:\__w\1\s\src\orchestrator\system\windows\common\PathVerification.cpp`
- `0x1403748f5`: `C:\__w\1\s\src\orchestrator\system\windows\common\PathVerification.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
_QWORD *__fastcall Windows::PathVerification::VerifyUpdaterPath(_QWORD *a1, const char *a2, __int64 a3)
{
  __int64 v6; // r14
  const char *v7; // r9
  __int64 v8; // r8
  __m128i *v9; // rdx
  __int64 v10; // r8
  __m128i *v11; // rdx
  __int64 v12; // rax
  __int64 v13; // r8
  __m128i *v14; // rdx
  __int64 v15; // rax
  __int64 v16; // r8
  __m128i *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 v23; // rcx
  HRESULT v24; // eax
  __int64 v25; // rbx
  __int64 v26; // rsi
  char v27; // di
  const wchar_t *v28; // rcx
  int v30; // [rsp+20h] [rbp-E0h]
  __int128 v31; // [rsp+40h] [rbp-C0h] BYREF
  __m128i si128; // [rsp+50h] [rbp-B0h]
  LPVOID v33; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  PCWSTR pszPathIn[3]; // [rsp+70h] [rbp-90h] BYREF
  __int128 v36; // [rsp+88h] [rbp-78h] BYREF
  __int64 v37; // [rsp+98h] [rbp-68h]
  WCHAR pszPathOut[264]; // [rsp+A0h] [rbp-60h] BYREF
  WCHAR Buffer[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+508h] [rbp+408h]

  pv = a1;
  EnterCriticalSection(&stru_14054A208);
  pszPathIn[2] = (PCWSTR)&stru_14054A208;
  v6 = -1;
  if ( qword_14054AF68 == qword_14054AF60 )
  {
    memset(Buffer, 0, 0x208u);
    if ( !GetSystemDirectoryW(Buffer, 0x104u) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x14,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PathVerification.cpp",
        v7);
    v36 = 0;
    v37 = 0;
    v31 = 0;
    si128 = 0;
    v8 = -1;
    do
      ++v8;
    while ( Buffer[v8] );
    std::wstring::_Construct<1,wchar_t const *>(&v31, Buffer, v8);
    v9 = (__m128i *)*((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1) == v37 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v36, *((_QWORD *)&v36 + 1), &v31);
    }
    else
    {
      **((_OWORD **)&v36 + 1) = v31;
      v9[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v31) = 0;
      *((_QWORD *)&v36 + 1) += 32LL;
    }
    std::wstring::~wstring(&v31);
    v33 = 0;
    wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
      &v33,
      L"%CommonProgramFiles%");
    v31 = 0;
    si128 = 0;
    v10 = -1;
    do
      ++v10;
    while ( *((_WORD *)v33 + v10) );
    std::wstring::_Construct<1,wchar_t const *>(&v31, v33, v10);
    v11 = (__m128i *)*((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1) == v37 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v36, *((_QWORD *)&v36 + 1), &v31);
    }
    else
    {
      **((_OWORD **)&v36 + 1) = v31;
      v11[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v31) = 0;
      *((_QWORD *)&v36 + 1) += 32LL;
    }
    std::wstring::~wstring(&v31);
    v12 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
            &pv,
            L"%ProgramFiles%\\Microsoft");
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      &v33,
      v12);
    if ( pv )
      CoTaskMemFree(pv);
    v31 = 0;
    si128 = 0;
    v13 = -1;
    do
      ++v13;
    while ( *((_WORD *)v33 + v13) );
    std::wstring::_Construct<1,wchar_t const *>(&v31, v33, v13);
    v14 = (__m128i *)*((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1) == v37 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v36, *((_QWORD *)&v36 + 1), &v31);
    }
    else
    {
      **((_OWORD **)&v36 + 1) = v31;
      v14[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v31) = 0;
      *((_QWORD *)&v36 + 1) += 32LL;
    }
    std::wstring::~wstring(&v31);
    v15 = wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
            &pv,
            L"%ProgramFiles(x86)%\\Microsoft");
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(
      &v33,
      v15);
    if ( pv )
      CoTaskMemFree(pv);
    v31 = 0;
    si128 = 0;
    v16 = -1;
    do
      ++v16;
    while ( *((_WORD *)v33 + v16) );
    std::wstring::_Construct<1,wchar_t const *>(&v31, v33, v16);
    v17 = (__m128i *)*((_QWORD *)&v36 + 1);
    if ( *((_QWORD *)&v36 + 1) == v37 )
    {
      std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v36, *((_QWORD *)&v36 + 1), &v31);
    }
    else
    {
      **((_OWORD **)&v36 + 1) = v31;
      v17[1] = si128;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v31) = 0;
      *((_QWORD *)&v36 + 1) += 32LL;
    }
    std::wstring::~wstring(&v31);
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl'::`2'::impl) )
    {
      v18 = wil::ExpandEnvironmentStringsW<std::wstring,256>(&v31, L"%ProgramData%\\USOPrivate\\Providers\\Registered");
      std::vector<std::wstring>::emplace_back<std::wstring>(&v36, v18);
      std::wstring::~wstring(&v31);
      v19 = wil::ExpandEnvironmentStringsW<std::wstring,256>(&v31, L"%ProgramData%\\USOPrivate\\Providers\\Windows");
      v20 = *((_QWORD *)&v36 + 1);
      if ( *((_QWORD *)&v36 + 1) == v37 )
      {
        std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(&v36, *((_QWORD *)&v36 + 1), v19);
      }
      else
      {
        **((_OWORD **)&v36 + 1) = 0;
        *(_QWORD *)(v20 + 16) = 0;
        *(_QWORD *)(v20 + 24) = 0;
        *(_OWORD *)v20 = *(_OWORD *)v19;
        *(_OWORD *)(v20 + 16) = *(_OWORD *)(v19 + 16);
        *(_WORD *)v19 = 0;
        *(_QWORD *)(v19 + 16) = 0;
        *(_QWORD *)(v19 + 24) = 7;
        *((_QWORD *)&v36 + 1) += 32LL;
      }
      std::wstring::~wstring(&v31);
    }
    v21 = qword_14054AF60;
    qword_14054AF60 = v36;
    *(_QWORD *)&v36 = v21;
    v22 = qword_14054AF68;
    qword_14054AF68 = *((_QWORD *)&v36 + 1);
    *((_QWORD *)&v36 + 1) = v22;
    v23 = qword_14054AF70;
    qword_14054AF70 = v37;
    v37 = v23;
    if ( v33 )
      CoTaskMemFree(v33);
    std::vector<std::filesystem::path>::_Tidy(&v36);
  }
  if ( &stru_14054A208 )
    LeaveCriticalSection(&stru_14054A208);
  pszPathIn[0] = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    pszPathIn,
    a3);
  memset(pszPathOut, 0, 0x208u);
  v24 = PathCchCanonicalize(pszPathOut, 0x104u, pszPathIn[0]);
  if ( v24 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x31,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PathVerification.cpp",
      (const char *)(unsigned int)v24,
      v30);
  v25 = qword_14054AF60;
  v26 = qword_14054AF68;
  v27 = 1;
  while ( v25 != v26 )
  {
    v28 = (const wchar_t *)v25;
    if ( *(_QWORD *)(v25 + 24) > 7u )
      v28 = *(const wchar_t **)v25;
    if ( !wcsnicmp(v28, pszPathOut, *(_QWORD *)(v25 + 16)) )
    {
      v27 = 0;
      break;
    }
    v25 += 32;
  }
  LOBYTE(v30) = v27;
  wil::details::in1diag3::Throw_HrIfMsg(
    retaddr,
    (void *)0x3D,
    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\common\\PathVerification.cpp",
    (const char *)0x80070057LL,
    v30,
    (bool)"Caller: %ws Cmdline: %ws",
    a2,
    pszPathOut,
    (_QWORD)v31);
  *(_OWORD *)a1 = 0;
  a1[2] = 0;
  a1[3] = 0;
  do
    ++v6;
  while ( pszPathOut[v6] );
  std::wstring::_Construct<1,wchar_t const *>(a1, pszPathOut, v6);
  if ( pszPathIn[0] )
    CoTaskMemFree((LPVOID)pszPathIn[0]);
  return a1;
}

```

## disassembly

```asm
0x140374388  mov     [rsp-8+arg_18], rbx
0x14037438d  push    rbp
0x14037438e  push    rsi
0x14037438f  push    rdi
0x140374390  push    r12
0x140374392  push    r13
0x140374394  push    r14
0x140374396  push    r15
0x140374398  lea     rbp, [rsp-3D0h]
0x1403743a0  sub     rsp, 4D0h
0x1403743a7  mov     rax, cs:__security_cookie
0x1403743ae  xor     rax, rsp
0x1403743b1  mov     [rbp+400h+var_40], rax
0x1403743b8  mov     rsi, r8
0x1403743bb  mov     r12, rdx
0x1403743be  mov     r15, rcx
0x1403743c1  mov     [rsp+500h+pv], rcx
0x1403743c6  xor     r13d, r13d
0x1403743c9  lea     rbx, stru_14054A208
0x1403743d0  mov     rcx, rbx; lpCriticalSection
0x1403743d3  call    cs:__imp_EnterCriticalSection
0x1403743d9  mov     [rbp+400h+var_480], rbx
0x1403743dd  mov     rax, cs:qword_14054AF68
0x1403743e4  or      r14, 0FFFFFFFFFFFFFFFFh
0x1403743e8  cmp     rax, cs:qword_14054AF60
0x1403743ef  jnz     loc_1403747A3
0x1403743f5  xor     edx, edx; Val
0x1403743f7  mov     r8d, 208h; Size
0x1403743fd  lea     rcx, [rbp+400h+Buffer]; void *
0x140374404  call    memset
0x140374409  mov     rdi, [rbp+408h]
0x140374410  mov     edx, 104h; uSize
0x140374415  lea     rcx, [rbp+400h+Buffer]; lpBuffer
0x14037441c  call    cs:__imp_GetSystemDirectoryW
0x140374422  test    eax, eax
0x140374424  jz      loc_1403748F5
0x14037442a  xorps   xmm0, xmm0
0x14037442d  xorps   xmm1, xmm1
0x140374430  movdqu  [rbp+400h+var_478], xmm1
0x140374435  mov     [rbp+400h+var_468], r13
0x140374439  movups  [rsp+500h+var_4C0], xmm0
0x14037443e  movdqu  [rsp+500h+var_4B0], xmm1
0x140374444  lea     rax, [rbp+400h+Buffer]
0x14037444b  mov     r8, r14
0x14037444e  inc     r8
0x140374451  cmp     [rax+r8*2], r13w
0x140374456  jnz     short loc_14037444E
0x140374458  lea     rdx, [rbp+400h+Buffer]
0x14037445f  lea     rcx, [rsp+500h+var_4C0]
0x140374464  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140374469  nop
0x14037446a  mov     rdx, qword ptr [rbp+400h+var_478+8]
0x14037446e  cmp     rdx, [rbp+400h+var_468]
0x140374472  jz      short loc_1403744A0
0x140374474  movups  xmm0, [rsp+500h+var_4C0]
0x140374479  movups  xmmword ptr [rdx], xmm0
0x14037447c  movups  xmm1, [rsp+500h+var_4B0]
0x140374481  movups  xmmword ptr [rdx+10h], xmm1
0x140374485  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x14037448d  movdqu  [rsp+500h+var_4B0], xmm0
0x140374493  mov     word ptr [rsp+500h+var_4C0], r13w
0x140374499  add     qword ptr [rbp+400h+var_478+8], 20h ; ' '
0x14037449e  jmp     short loc_1403744AF
0x1403744a0  lea     r8, [rsp+500h+var_4C0]
0x1403744a5  lea     rcx, [rbp+400h+var_478]
0x1403744a9  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1403744ae  nop
0x1403744af  lea     rcx, [rsp+500h+var_4C0]
0x1403744b4  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403744b9  mov     [rsp+500h+var_4A0], r13
0x1403744be  lea     rdx, aCommonprogramf; "%CommonProgramFiles%"
0x1403744c5  lea     rcx, [rsp+500h+var_4A0]
0x1403744ca  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x1403744cf  nop
0x1403744d0  xorps   xmm0, xmm0
0x1403744d3  movups  [rsp+500h+var_4C0], xmm0
0x1403744d8  xorps   xmm1, xmm1
0x1403744db  movdqu  [rsp+500h+var_4B0], xmm1
0x1403744e1  mov     rdx, [rsp+500h+var_4A0]
0x1403744e6  mov     r8, r14
0x1403744e9  inc     r8
0x1403744ec  cmp     [rdx+r8*2], r13w
0x1403744f1  jnz     short loc_1403744E9
0x1403744f3  lea     rcx, [rsp+500h+var_4C0]
0x1403744f8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1403744fd  nop
0x1403744fe  mov     rdx, qword ptr [rbp+400h+var_478+8]
0x140374502  cmp     rdx, [rbp+400h+var_468]
0x140374506  jz      short loc_140374534
0x140374508  movups  xmm0, [rsp+500h+var_4C0]
0x14037450d  movups  xmmword ptr [rdx], xmm0
0x140374510  movups  xmm1, [rsp+500h+var_4B0]
0x140374515  movups  xmmword ptr [rdx+10h], xmm1
0x140374519  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140374521  movdqu  [rsp+500h+var_4B0], xmm0
0x140374527  mov     word ptr [rsp+500h+var_4C0], r13w
0x14037452d  add     qword ptr [rbp+400h+var_478+8], 20h ; ' '
0x140374532  jmp     short loc_140374543
0x140374534  lea     r8, [rsp+500h+var_4C0]
0x140374539  lea     rcx, [rbp+400h+var_478]
0x14037453d  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x140374542  nop
0x140374543  lea     rcx, [rsp+500h+var_4C0]
0x140374548  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14037454d  lea     rdx, aProgramfilesMi; "%ProgramFiles%\\Microsoft"
0x140374554  lea     rcx, [rsp+500h+pv]
0x140374559  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x14037455e  mov     rdx, rax
0x140374561  lea     rcx, [rsp+500h+var_4A0]
0x140374566  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x14037456b  mov     rcx, [rsp+500h+pv]; pv
0x140374570  test    rcx, rcx
0x140374573  jz      short loc_14037457B
0x140374575  call    cs:__imp_CoTaskMemFree
0x14037457b  xorps   xmm0, xmm0
0x14037457e  movups  [rsp+500h+var_4C0], xmm0
0x140374583  xorps   xmm1, xmm1
0x140374586  movdqu  [rsp+500h+var_4B0], xmm1
0x14037458c  mov     rdx, [rsp+500h+var_4A0]
0x140374591  mov     r8, r14
0x140374594  inc     r8
0x140374597  cmp     [rdx+r8*2], r13w
0x14037459c  jnz     short loc_140374594
0x14037459e  lea     rcx, [rsp+500h+var_4C0]
0x1403745a3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1403745a8  nop
0x1403745a9  mov     rdx, qword ptr [rbp+400h+var_478+8]
0x1403745ad  cmp     rdx, [rbp+400h+var_468]
0x1403745b1  jz      short loc_1403745DF
0x1403745b3  movups  xmm0, [rsp+500h+var_4C0]
0x1403745b8  movups  xmmword ptr [rdx], xmm0
0x1403745bb  movups  xmm1, [rsp+500h+var_4B0]
0x1403745c0  movups  xmmword ptr [rdx+10h], xmm1
0x1403745c4  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x1403745cc  movdqu  [rsp+500h+var_4B0], xmm0
0x1403745d2  mov     word ptr [rsp+500h+var_4C0], r13w
0x1403745d8  add     qword ptr [rbp+400h+var_478+8], 20h ; ' '
0x1403745dd  jmp     short loc_1403745EE
0x1403745df  lea     r8, [rsp+500h+var_4C0]
0x1403745e4  lea     rcx, [rbp+400h+var_478]
0x1403745e8  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x1403745ed  nop
0x1403745ee  lea     rcx, [rsp+500h+var_4C0]
0x1403745f3  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403745f8  lea     rdx, aProgramfilesX8; "%ProgramFiles(x86)%\\Microsoft"
0x1403745ff  lea     rcx, [rsp+500h+pv]
0x140374604  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x140374609  mov     rdx, rax
0x14037460c  lea     rcx, [rsp+500h+var_4A0]
0x140374611  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &&)
0x140374616  mov     rcx, [rsp+500h+pv]; pv
0x14037461b  test    rcx, rcx
0x14037461e  jz      short loc_140374626
0x140374620  call    cs:__imp_CoTaskMemFree
0x140374626  xorps   xmm0, xmm0
0x140374629  movups  [rsp+500h+var_4C0], xmm0
0x14037462e  xorps   xmm1, xmm1
0x140374631  movdqu  [rsp+500h+var_4B0], xmm1
0x140374637  mov     rdx, [rsp+500h+var_4A0]
0x14037463c  mov     r8, r14
0x14037463f  inc     r8
0x140374642  cmp     [rdx+r8*2], r13w
0x140374647  jnz     short loc_14037463F
0x140374649  lea     rcx, [rsp+500h+var_4C0]
0x14037464e  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140374653  nop
0x140374654  mov     rdx, qword ptr [rbp+400h+var_478+8]
0x140374658  cmp     rdx, [rbp+400h+var_468]
0x14037465c  jz      short loc_14037468A
0x14037465e  movups  xmm0, [rsp+500h+var_4C0]
0x140374663  movups  xmmword ptr [rdx], xmm0
0x140374666  movups  xmm1, [rsp+500h+var_4B0]
0x14037466b  movups  xmmword ptr [rdx+10h], xmm1
0x14037466f  movdqa  xmm0, cs:__xmm@00000000000000070000000000000000
0x140374677  movdqu  [rsp+500h+var_4B0], xmm0
0x14037467d  mov     word ptr [rsp+500h+var_4C0], r13w
0x140374683  add     qword ptr [rbp+400h+var_478+8], 20h ; ' '
0x140374688  jmp     short loc_140374699
0x14037468a  lea     r8, [rsp+500h+var_4C0]
0x14037468f  lea     rcx, [rbp+400h+var_478]
0x140374693  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x140374698  nop
0x140374699  lea     rcx, [rsp+500h+var_4C0]
0x14037469e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403746a3  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319> `wil::Feature<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::GetImpl(void)'::`2'::impl
0x1403746aa  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Containment_UUS_UOvNext_46833319>::__private_IsEnabled(void)
0x1403746af  test    al, al
0x1403746b1  jz      loc_140374746
0x1403746b7  lea     rdx, aProgramdataUso_0; "%ProgramData%\\USOPrivate\\Providers\\R"...
0x1403746be  lea     rcx, [rsp+500h+var_4C0]
0x1403746c3  call    ??$ExpandEnvironmentStringsW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0BAA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; wil::ExpandEnvironmentStringsW<std::wstring,256>(wchar_t const *)
0x1403746c8  nop
0x1403746c9  mov     rdx, rax
0x1403746cc  lea     rcx, [rbp+400h+var_478]
0x1403746d0  call    ??$emplace_back@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@QEAAAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::emplace_back<std::wstring>(std::wstring &&)
0x1403746d5  nop
0x1403746d6  lea     rcx, [rsp+500h+var_4C0]
0x1403746db  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403746e0  lea     rdx, aProgramdataUso_11; "%ProgramData%\\USOPrivate\\Providers\\W"...
0x1403746e7  lea     rcx, [rsp+500h+var_4C0]
0x1403746ec  call    ??$ExpandEnvironmentStringsW@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$0BAA@@wil@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W@Z; wil::ExpandEnvironmentStringsW<std::wstring,256>(wchar_t const *)
0x1403746f1  nop
0x1403746f2  mov     rdx, qword ptr [rbp+400h+var_478+8]
0x1403746f6  cmp     rdx, [rbp+400h+var_468]
0x1403746fa  jz      short loc_14037472F
0x1403746fc  xorps   xmm0, xmm0
0x1403746ff  movups  xmmword ptr [rdx], xmm0
0x140374702  mov     [rdx+10h], r13
0x140374706  mov     [rdx+18h], r13
0x14037470a  movups  xmm0, xmmword ptr [rax]
0x14037470d  movups  xmmword ptr [rdx], xmm0
0x140374710  movups  xmm1, xmmword ptr [rax+10h]
0x140374714  movups  xmmword ptr [rdx+10h], xmm1
0x140374718  mov     [rax], r13w
0x14037471c  mov     [rax+10h], r13
0x140374720  mov     qword ptr [rax+18h], 7
0x140374728  add     qword ptr [rbp+400h+var_478+8], 20h ; ' '
0x14037472d  jmp     short loc_14037473C
0x14037472f  mov     r8, rax
0x140374732  lea     rcx, [rbp+400h+var_478]
0x140374736  call    ??$_Emplace_reallocate@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@AEAAPEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@QEAV21@$$QEAV21@@Z; std::vector<std::wstring>::_Emplace_reallocate<std::wstring>(std::wstring * const,std::wstring &&)
0x14037473b  nop
0x14037473c  lea     rcx, [rsp+500h+var_4C0]
0x140374741  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140374746  mov     rcx, cs:qword_14054AF60
0x14037474d  mov     rax, qword ptr [rbp+400h+var_478]
0x140374751  mov     cs:qword_14054AF60, rax
0x140374758  mov     qword ptr [rbp+400h+var_478], rcx
0x14037475c  mov     rcx, cs:qword_14054AF68
0x140374763  mov     rax, qword ptr [rbp+400h+var_478+8]
0x140374767  mov     cs:qword_14054AF68, rax
0x14037476e  mov     qword ptr [rbp+400h+var_478+8], rcx
0x140374772  mov     rcx, cs:qword_14054AF70
0x140374779  mov     rax, [rbp+400h+var_468]
0x14037477d  mov     cs:qword_14054AF70, rax
0x140374784  mov     [rbp+400h+var_468], rcx
0x140374788  mov     rcx, [rsp+500h+var_4A0]; pv
0x14037478d  test    rcx, rcx
0x140374790  jz      short loc_140374799
0x140374792  call    cs:__imp_CoTaskMemFree
0x140374798  nop
0x140374799  lea     rcx, [rbp+400h+var_478]
0x14037479d  call    ?_Tidy@?$vector@Vpath@filesystem@std@@V?$allocator@Vpath@filesystem@std@@@3@@std@@AEAAXXZ; std::vector<std::filesystem::path>::_Tidy(void)
0x1403747a2  nop
0x1403747a3  test    rbx, rbx
0x1403747a6  jz      short loc_1403747B1
0x1403747a8  mov     rcx, rbx; lpCriticalSection
0x1403747ab  call    cs:__imp_LeaveCriticalSection
0x1403747b1  mov     [rsp+500h+pszPathIn], r13
0x1403747b6  mov     rdx, rsi
0x1403747b9  lea     rcx, [rsp+500h+pszPathIn]
0x1403747be  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x1403747c3  nop
0x1403747c4  xor     edx, edx; Val
0x1403747c6  mov     r8d, 208h; Size
0x1403747cc  lea     rcx, [rbp+400h+pszPathOut]; void *
0x1403747d0  call    memset
0x1403747d5  mov     r8, [rsp+500h+pszPathIn]; pszPathIn
0x1403747da  mov     edx, 104h; cchPathOut
0x1403747df  lea     rcx, [rbp+400h+pszPathOut]; pszPathOut
0x1403747e3  call    cs:__imp_PathCchCanonicalize
0x1403747e9  mov     rcx, [rbp+408h]; this
0x1403747f0  test    eax, eax
0x1403747f2  js      loc_1403748E0
0x1403747f8  mov     rbx, cs:qword_14054AF60
0x1403747ff  mov     rsi, cs:qword_14054AF68
0x140374806  mov     edi, 1
0x14037480b  jmp     short loc_14037482F
0x14037480d  mov     rcx, rbx
0x140374810  cmp     qword ptr [rbx+18h], 7
0x140374815  jbe     short loc_14037481A
0x140374817  mov     rcx, [rbx]; String1
0x14037481a  mov     r8, [rbx+10h]; MaxCount
0x14037481e  lea     rdx, [rbp+400h+pszPathOut]; String2
0x140374822  call    _wcsnicmp
0x140374827  test    eax, eax
0x140374829  jz      short loc_140374836
0x14037482b  add     rbx, 20h ; ' '
0x14037482f  cmp     rbx, rsi
0x140374832  jnz     short loc_14037480D
0x140374834  jmp     short loc_140374839
0x140374836  mov     edi, r13d
0x140374839  mov     rcx, [rbp+408h]; this
0x140374840  lea     rax, [rbp+400h+pszPathOut]
0x140374844  mov     [rsp+500h+var_4C8], rax
0x140374849  mov     [rsp+500h+var_4D0], r12; char *
0x14037484e  lea     rax, aCallerWsCmdlin; "Caller: %ws Cmdline: %ws"
0x140374855  mov     qword ptr [rsp+500h+var_4D8], rax; bool
0x14037485a  mov     byte ptr [rsp+500h+var_4E0], dil; int
0x14037485f  mov     r9d, 80070057h; char *
0x140374865  lea     r8, aCW1SSrcOrchest_65; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14037486c  mov     edx, 3Dh ; '='; void *
0x140374871  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x140374876  xorps   xmm0, xmm0
0x140374879  movups  xmmword ptr [r15], xmm0
0x14037487d  mov     [r15+10h], r13
0x140374881  mov     [r15+18h], r13
0x140374885  lea     rax, [rbp+400h+pszPathOut]
0x140374889  inc     r14
0x14037488c  cmp     [rax+r14*2], r13w
  ... truncated ...
```
