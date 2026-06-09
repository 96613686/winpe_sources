# Windows::UO::ExecuteBinary_0

- ea: `0x1403277d4`
- end: `0x140327f35`
- name: `Windows::UO::ExecuteBinary_0`
- size: `1889`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14032cdec`

## callees

- `0x14003fd58`
- `0x1400407f8`
- `0x140040964`
- `0x140043354`
- `0x140045404`
- `0x14004cdbc`
- `0x1400b425c`
- `0x140119004`
- `0x14024898c`
- `0x140254ca4`
- `0x140312df0`
- `0x140312fb0`
- `0x140314330`
- `0x1403277d4`
- `0x14036efd0`
- `0x140374388`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140327e40`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x140327e40`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140327c1f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x140327c1f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403279c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327a55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327c76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327e12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327ef6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327957`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1403279c0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327a55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327c76`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327dbe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327e12`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327e97`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x140327ef6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140327d78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140327d78`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140327d66`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x140327d66`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x140327b24`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x140327b24`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x140327a0a`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x140327a0a`

## string_xrefs

- `0x1403278cf`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`
- `0x14032793b`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`
- `0x1403279a4`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`
- `0x140327a2d`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`
- `0x140327c31`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`
- `0x140327e52`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall Windows::UO::ExecuteBinary_0(
        _QWORD *a1,
        _QWORD *a2,
        _QWORD *a3,
        __int64 a4,
        _QWORD *a5,
        int a6,
        unsigned __int8 a7)
{
  __int64 v9; // rbx
  __int128 *v11; // r8
  int v12; // eax
  unsigned int v13; // ebx
  int v14; // eax
  void *lpEnvironment; // rsi
  DWORD dwCreationFlags; // r14d
  LPWCH EnvironmentStringsW; // rax
  WCHAR *v18; // rbx
  __int64 v19; // r9
  LPWCH v20; // rcx
  __int64 v21; // rax
  __int64 v22; // rax
  void *v23; // rbx
  const wchar_t *v24; // rax
  const WCHAR *lpCurrentDirectory; // rax
  const char *v26; // r9
  unsigned int LastError; // edi
  struct _PROCESS_INFORMATION *v28; // rdx
  void (__fastcall ***v29)(_QWORD, GUID *, LPVOID *); // rcx
  LPVOID v30; // rcx
  DWORD v31; // eax
  signed int v32; // eax
  struct _PROCESS_INFORMATION *v33; // rdx
  struct _PROCESS_INFORMATION *v34; // rdx
  const char *v35; // r9
  struct _PROCESS_INFORMATION *v36; // rdx
  struct _PROCESS_INFORMATION *v37; // rdx
  BOOL bInheritHandles; // [rsp+20h] [rbp-198h]
  int v39; // [rsp+50h] [rbp-168h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-160h] BYREF
  const wchar_t *v41; // [rsp+60h] [rbp-158h] BYREF
  __int64 v42; // [rsp+68h] [rbp-150h]
  _QWORD v43[4]; // [rsp+70h] [rbp-148h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-128h] BYREF
  DWORD ExitCode; // [rsp+A8h] [rbp-110h] BYREF
  LPVOID v46; // [rsp+B0h] [rbp-108h] BYREF
  __int128 v47; // [rsp+B8h] [rbp-100h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-F0h]
  __int128 v49; // [rsp+D8h] [rbp-E0h] BYREF
  __int64 v50; // [rsp+E8h] [rbp-D0h]
  LPCWSTR v51[4]; // [rsp+F0h] [rbp-C8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+110h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v47 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v47) = 0;
  if ( *(_QWORD *)(a4 + 8) )
  {
    std::wstring::operator=<wil::basic_zstring_view<wchar_t>,0>(&v47);
  }
  else
  {
    v9 = Windows::PathVerification::VerifyUpdaterPath(v43, *a1, *a2);
    if ( &v47 != (__int128 *)v9 )
    {
      std::wstring::~wstring(&v47);
      v47 = *(_OWORD *)v9;
      si128 = *(__m128i *)(v9 + 16);
      *(_QWORD *)(v9 + 16) = 0;
      *(_QWORD *)(v9 + 24) = 7;
      *(_WORD *)v9 = 0;
    }
    std::wstring::~wstring(v43);
  }
  memset(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  pv = 0;
  if ( !a2[1] )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5E,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOUtils.hpp",
      (const char *)0x80070057LL,
      bInheritHandles);
    std::wstring::~wstring(&v47);
    return 2147942487LL;
  }
  v11 = &v47;
  if ( a3[1] )
  {
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (__int128 *)v47;
    v14 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            &pv,
            L"%ws %ws",
            v11,
            *a3);
    v13 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOUtils.hpp",
        (const char *)(unsigned int)v14,
        bInheritHandles);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_14;
    }
  }
  else
  {
    if ( si128.m128i_i64[1] > 7uLL )
      v11 = (__int128 *)v47;
    v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            &pv,
            L"%ws",
            v11);
    v13 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOUtils.hpp",
        (const char *)(unsigned int)v12,
        bInheritHandles);
      if ( pv )
        CoTaskMemFree(pv);
LABEL_14:
      std::wstring::~wstring(&v47);
      return v13;
    }
  }
  lpEnvironment = 0;
  dwCreationFlags = 0;
  v49 = 0;
  v50 = 0;
  if ( *a5 != a5[1] )
  {
    EnvironmentStringsW = GetEnvironmentStringsW();
    v18 = EnvironmentStringsW;
    v41 = EnvironmentStringsW;
    if ( !EnvironmentStringsW )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOUtils.hpp",
        (const char *)0x8007000ELL,
        bInheritHandles);
      std::vector<wchar_t>::_Tidy(&v49);
      if ( pv )
        CoTaskMemFree(pv);
      std::wstring::~wstring(&v47);
      return 2147942414LL;
    }
    v19 = 0;
    if ( *EnvironmentStringsW )
    {
      v20 = EnvironmentStringsW;
      do
      {
        v21 = -1;
        do
          ++v21;
        while ( v20[v21] );
        v22 = v21 + 1;
        v19 += v22;
        v20 += v22;
      }
      while ( *v20 );
    }
    std::vector<wchar_t>::_Insert_counted_range<wchar_t const *>(&v49, *((_QWORD *)&v49 + 1), v18, (2 * v19) >> 1);
    std::vector<wchar_t>::_Insert_counted_range<wchar_t const *>(
      &v49,
      *((_QWORD *)&v49 + 1),
      *a5,
      (__int64)(a5[1] - *a5) >> 1);
    LOWORD(v39) = 0;
    if ( *((_QWORD *)&v49 + 1) == v50 )
    {
      std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(&v49, *((_QWORD *)&v49 + 1), &v39);
    }
    else
    {
      **((_WORD **)&v49 + 1) = 0;
      *((_QWORD *)&v49 + 1) += 2LL;
    }
    lpEnvironment = (void *)v49;
    dwCreationFlags = 1024;
    FreeEnvironmentStringsW(v18);
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v23 = pv;
  v46 = pv;
  v41 = L"Starting callback: {}";
  v42 = 21;
  SystemInterface::Log<wchar_t *>(&v41, &v46);
  v24 = (const wchar_t *)&v47;
  if ( si128.m128i_i64[1] > 7uLL )
    v24 = (const wchar_t *)v47;
  v41 = v24;
  v42 = si128.m128i_i64[0];
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v43, &v41);
  std::filesystem::path::parent_path(v43, v51);
  std::wstring::~wstring(v43);
  lpCurrentDirectory = (const WCHAR *)v51;
  if ( v51[3] > (LPCWSTR)7 )
    lpCurrentDirectory = v51[0];
  if ( !CreateProcessW(
          0,
          (LPWSTR)v23,
          0,
          0,
          0,
          dwCreationFlags,
          lpEnvironment,
          lpCurrentDirectory,
          &StartupInfo,
          &ProcessInformation) )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x9F,
                  (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOUtils.hpp",
                  v26);
    std::wstring::~wstring(v51);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v28);
    std::vector<wchar_t>::_Tidy(&v49);
    if ( v23 )
      CoTaskMemFree(v23);
LABEL_69:
    std::wstring::~wstring(&v47);
    return LastError;
  }
  v46 = 0;
  v29 = *(void (__fastcall ****)(_QWORD, GUID *, LPVOID *))Windows::DockedHelpers::GetDockedSystem(&v41);
  v46 = 0;
  (**v29)(v29, &GUID_74d70212_eaa5_4298_b2f5_366da8756498, &v46);
  if ( v41 )
    (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v41 + 16LL))(v41);
  v30 = v46;
  if ( v46 )
  {
    v39 = (*(__int64 (__fastcall **)(LPVOID, HANDLE, _QWORD, __int64))(*(_QWORD *)v46 + 192LL))(
            v46,
            ProcessInformation.hProcess,
            a7,
            1);
    if ( v39 < 0 )
    {
      v43[0] = L"Failed to change process priority: {}";
      v43[1] = 37;
      SystemInterface::Log<long const &>(v43, &v39);
    }
    v30 = v46;
  }
  if ( v30 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v30 + 16LL))(v30);
  v31 = WaitForSingleObject(ProcessInformation.hProcess, 0xDBBA00u);
  ExitCode = v31;
  if ( v31 == -1 )
  {
    v32 = GetLastError();
    LastError = (unsigned __int16)v32 | 0x80070000;
    if ( v32 <= 0 )
      LastError = v32;
    std::wstring::~wstring(v51);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v33);
    std::vector<wchar_t>::_Tidy(&v49);
    if ( v23 )
      CoTaskMemFree(v23);
    goto LABEL_69;
  }
  if ( v31 != 258 )
  {
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      LastError = (unsigned __int16)ExitCode | 0x80070000;
      if ( (int)ExitCode <= 0 )
        LastError = ExitCode;
      std::wstring::~wstring(v51);
      wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v37);
      std::vector<wchar_t>::_Tidy(&v49);
      if ( v23 )
        CoTaskMemFree(v23);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xB7,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOUtils.hpp",
                    v35);
      std::wstring::~wstring(v51);
      wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v36);
      std::vector<wchar_t>::_Tidy(&v49);
      if ( v23 )
        CoTaskMemFree(v23);
    }
    goto LABEL_69;
  }
  std::wstring::~wstring(v51);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v34);
  std::vector<wchar_t>::_Tidy(&v49);
  if ( v23 )
    CoTaskMemFree(v23);
  std::wstring::~wstring(&v47);
  return 2147942658LL;
}

```

## disassembly

```asm
0x1403277d4  push    rbx
0x1403277d6  push    rsi
0x1403277d7  push    rdi
0x1403277d8  push    r14
0x1403277da  push    r15
0x1403277dc  sub     rsp, 190h
0x1403277e3  mov     rax, cs:__security_cookie
0x1403277ea  xor     rax, rsp
0x1403277ed  mov     [rsp+1B8h+var_38], rax
0x1403277f5  mov     rsi, r8
0x1403277f8  mov     rdi, rdx
0x1403277fb  xor     r15d, r15d
0x1403277fe  xorps   xmm0, xmm0
0x140327801  movups  [rsp+1B8h+var_100], xmm0
0x140327809  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140327811  movdqu  [rsp+1B8h+var_F0], xmm1
0x14032781a  mov     word ptr [rsp+1B8h+var_100], r15w
0x140327823  cmp     [r9+8], r15
0x140327827  jz      short loc_140327838
0x140327829  lea     rcx, [rsp+1B8h+var_100]; void *
0x140327831  call    ??$?4V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV?$basic_zstring_view@_W@wil@@@Z; std::wstring::operator=<wil::basic_zstring_view<wchar_t>,0>(wil::basic_zstring_view<wchar_t> const &)
0x140327836  jmp     short loc_140327896
0x140327838  mov     r8, [rdx]
0x14032783b  mov     rdx, [rcx]
0x14032783e  lea     rcx, [rsp+1B8h+var_148]
0x140327843  call    ?VerifyUpdaterPath@PathVerification@Windows@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z; Windows::PathVerification::VerifyUpdaterPath(wchar_t const *,wchar_t const *)
0x140327848  mov     rbx, rax
0x14032784b  lea     rax, [rsp+1B8h+var_100]
0x140327853  cmp     rax, rbx
0x140327856  jz      short loc_14032788C
0x140327858  lea     rcx, [rsp+1B8h+var_100]
0x140327860  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140327865  movups  xmm0, xmmword ptr [rbx]
0x140327868  movups  [rsp+1B8h+var_100], xmm0
0x140327870  movups  xmm1, xmmword ptr [rbx+10h]
0x140327874  movups  [rsp+1B8h+var_F0], xmm1
0x14032787c  mov     [rbx+10h], r15
0x140327880  mov     qword ptr [rbx+18h], 7
0x140327888  mov     [rbx], r15w
0x14032788c  lea     rcx, [rsp+1B8h+var_148]
0x140327891  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140327896  xor     edx, edx; Val
0x140327898  lea     r8d, [rdx+64h]; Size
0x14032789c  lea     rcx, [rsp+1B8h+StartupInfo+4]; void *
0x1403278a4  call    memset
0x1403278a9  mov     [rsp+1B8h+StartupInfo.cb], 68h ; 'h'
0x1403278b4  mov     [rsp+1B8h+pv], r15
0x1403278b9  cmp     [rdi+8], r15
0x1403278bd  jnz     short loc_1403278F5
0x1403278bf  mov     rcx, [rsp+1B8h]; this
0x1403278c7  mov     ebx, 80070057h
0x1403278cc  mov     r9d, ebx; char *
0x1403278cf  lea     r8, aCW1SSrcOrchest_12; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403278d6  mov     edx, 5Eh ; '^'; void *
0x1403278db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1403278e0  nop
0x1403278e1  lea     rcx, [rsp+1B8h+var_100]
0x1403278e9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403278ee  mov     eax, ebx
0x1403278f0  jmp     loc_140327F15
0x1403278f5  lea     r8, [rsp+1B8h+var_100]
0x1403278fd  lea     rcx, [rsp+1B8h+pv]
0x140327902  cmp     [rsi+8], r15
0x140327906  jnz     short loc_140327972
0x140327908  cmp     qword ptr [rsp+1B8h+var_F0+8], 7
0x140327911  cmova   r8, qword ptr [rsp+1B8h+var_100]
0x14032791a  lea     rdx, aWs; "%ws"
0x140327921  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)
0x140327926  mov     ebx, eax
0x140327928  test    eax, eax
0x14032792a  jns     loc_1403279DB
0x140327930  mov     rcx, [rsp+1B8h]; this
0x140327938  mov     r9d, eax; char *
0x14032793b  lea     r8, aCW1SSrcOrchest_12; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140327942  mov     edx, 62h ; 'b'; void *
0x140327947  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14032794c  nop
0x14032794d  mov     rcx, [rsp+1B8h+pv]; pv
0x140327952  test    rcx, rcx
0x140327955  jz      short loc_14032795E
0x140327957  call    cs:__imp_CoTaskMemFree
0x14032795d  nop
0x14032795e  lea     rcx, [rsp+1B8h+var_100]
0x140327966  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14032796b  mov     eax, ebx
0x14032796d  jmp     loc_140327F15
0x140327972  cmp     qword ptr [rsp+1B8h+var_F0+8], 7
0x14032797b  cmova   r8, qword ptr [rsp+1B8h+var_100]
0x140327984  mov     r9, [rsi]
0x140327987  lea     rdx, aWsWs_1; "%ws %ws"
0x14032798e  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)
0x140327993  mov     ebx, eax
0x140327995  test    eax, eax
0x140327997  jns     short loc_1403279DB
0x140327999  mov     rcx, [rsp+1B8h]; this
0x1403279a1  mov     r9d, eax; char *
0x1403279a4  lea     r8, aCW1SSrcOrchest_12; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x1403279ab  mov     edx, 66h ; 'f'; void *
0x1403279b0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1403279b5  nop
0x1403279b6  mov     rcx, [rsp+1B8h+pv]; pv
0x1403279bb  test    rcx, rcx
0x1403279be  jz      short loc_1403279C7
0x1403279c0  call    cs:__imp_CoTaskMemFree
0x1403279c6  nop
0x1403279c7  lea     rcx, [rsp+1B8h+var_100]
0x1403279cf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1403279d4  mov     eax, ebx
0x1403279d6  jmp     loc_140327F15
0x1403279db  mov     rsi, r15
0x1403279de  mov     r14d, r15d
0x1403279e1  xorps   xmm1, xmm1
0x1403279e4  movdqu  [rsp+1B8h+var_E0], xmm1
0x1403279ed  mov     [rsp+1B8h+var_D0], r15
0x1403279f5  mov     rdi, [rsp+1B8h+arg_20]
0x1403279fd  mov     rax, [rdi+8]
0x140327a01  cmp     [rdi], rax
0x140327a04  jz      loc_140327B2A
0x140327a0a  call    cs:__imp_GetEnvironmentStringsW
0x140327a10  mov     rbx, rax
0x140327a13  mov     [rsp+1B8h+var_158], rax
0x140327a18  test    rax, rax
0x140327a1b  jnz     short loc_140327A70
0x140327a1d  mov     rcx, [rsp+1B8h]; this
0x140327a25  mov     ebx, 8007000Eh
0x140327a2a  mov     r9d, ebx; char *
0x140327a2d  lea     r8, aCW1SSrcOrchest_12; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140327a34  lea     edx, [rax+72h]; void *
0x140327a37  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140327a3c  nop
0x140327a3d  lea     rcx, [rsp+1B8h+var_E0]
0x140327a45  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x140327a4a  nop
0x140327a4b  mov     rcx, [rsp+1B8h+pv]; pv
0x140327a50  test    rcx, rcx
0x140327a53  jz      short loc_140327A5C
0x140327a55  call    cs:__imp_CoTaskMemFree
0x140327a5b  nop
0x140327a5c  lea     rcx, [rsp+1B8h+var_100]
0x140327a64  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140327a69  mov     eax, ebx
0x140327a6b  jmp     loc_140327F15
0x140327a70  mov     r9, r15
0x140327a73  cmp     [rax], r15w
0x140327a77  jz      short loc_140327A9A
0x140327a79  mov     rcx, rbx
0x140327a7c  or      rax, 0FFFFFFFFFFFFFFFFh
0x140327a80  inc     rax
0x140327a83  cmp     [rcx+rax*2], r15w
0x140327a88  jnz     short loc_140327A80
0x140327a8a  inc     rax
0x140327a8d  add     r9, rax
0x140327a90  lea     rcx, [rcx+rax*2]
0x140327a94  cmp     [rcx], r15w
0x140327a98  jnz     short loc_140327A7C
0x140327a9a  add     r9, r9
0x140327a9d  sar     r9, 1
0x140327aa0  mov     r8, rbx
0x140327aa3  mov     rdx, qword ptr [rsp+1B8h+var_E0+8]
0x140327aab  lea     rcx, [rsp+1B8h+var_E0]
0x140327ab3  call    ??$_Insert_counted_range@PEB_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@_W@std@@@std@@@1@PEB_W_K@Z; std::vector<wchar_t>::_Insert_counted_range<wchar_t const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<wchar_t>>>,wchar_t const *,unsigned __int64)
0x140327ab8  mov     r9, [rdi+8]
0x140327abc  sub     r9, [rdi]
0x140327abf  sar     r9, 1
0x140327ac2  mov     r8, [rdi]
0x140327ac5  mov     rdx, qword ptr [rsp+1B8h+var_E0+8]
0x140327acd  lea     rcx, [rsp+1B8h+var_E0]
0x140327ad5  call    ??$_Insert_counted_range@PEB_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@_W@std@@@std@@@1@PEB_W_K@Z; std::vector<wchar_t>::_Insert_counted_range<wchar_t const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<wchar_t>>>,wchar_t const *,unsigned __int64)
0x140327ada  mov     word ptr [rsp+1B8h+var_168], r15w
0x140327ae0  mov     rdx, qword ptr [rsp+1B8h+var_E0+8]
0x140327ae8  cmp     rdx, [rsp+1B8h+var_D0]
0x140327af0  jz      short loc_140327B01
0x140327af2  mov     [rdx], r15w
0x140327af6  add     qword ptr [rsp+1B8h+var_E0+8], 2
0x140327aff  jmp     short loc_140327B13
0x140327b01  lea     r8, [rsp+1B8h+var_168]
0x140327b06  lea     rcx, [rsp+1B8h+var_E0]
0x140327b0e  call    ??$_Emplace_reallocate@_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAPEA_WQEA_W$$QEA_W@Z; std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(wchar_t * const,wchar_t &&)
0x140327b13  mov     rsi, qword ptr [rsp+1B8h+var_E0]
0x140327b1b  mov     r14d, 400h
0x140327b21  mov     rcx, rbx; penv
0x140327b24  call    cs:__imp_FreeEnvironmentStringsW
0x140327b2a  xorps   xmm0, xmm0
0x140327b2d  xor     eax, eax
0x140327b2f  movups  xmmword ptr [rsp+1B8h+ProcessInformation.hProcess], xmm0
0x140327b37  mov     qword ptr [rsp+1B8h+ProcessInformation.dwProcessId], rax
0x140327b3f  mov     rbx, [rsp+1B8h+pv]
0x140327b44  mov     [rsp+1B8h+var_108], rbx
0x140327b4c  lea     rax, aStartingCallba; "Starting callback: {}"
0x140327b53  mov     [rsp+1B8h+var_158], rax
0x140327b58  mov     [rsp+1B8h+var_150], 15h
0x140327b61  lea     rdx, [rsp+1B8h+var_108]
0x140327b69  lea     rcx, [rsp+1B8h+var_158]
0x140327b6e  call    ??$Log@PEA_W@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$$QEAPEA_W@Z; SystemInterface::Log<wchar_t *>(std::wstring_view,wchar_t * &&)
0x140327b73  lea     rax, [rsp+1B8h+var_100]
0x140327b7b  cmp     qword ptr [rsp+1B8h+var_F0+8], 7
0x140327b84  cmova   rax, qword ptr [rsp+1B8h+var_100]
0x140327b8d  mov     [rsp+1B8h+var_158], rax
0x140327b92  mov     rax, qword ptr [rsp+1B8h+var_F0]
0x140327b9a  mov     [rsp+1B8h+var_150], rax
0x140327b9f  lea     rdx, [rsp+1B8h+var_158]
0x140327ba4  lea     rcx, [rsp+1B8h+var_148]
0x140327ba9  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x140327bae  nop
0x140327baf  lea     rdx, [rsp+1B8h+var_C8]
0x140327bb7  lea     rcx, [rsp+1B8h+var_148]
0x140327bbc  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x140327bc1  nop
0x140327bc2  lea     rcx, [rsp+1B8h+var_148]
0x140327bc7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140327bcc  lea     rax, [rsp+1B8h+var_C8]
0x140327bd4  cmp     [rsp+1B8h+var_B0], 7
0x140327bdd  cmova   rax, [rsp+1B8h+var_C8]
0x140327be6  lea     rcx, [rsp+1B8h+ProcessInformation]
0x140327bee  mov     [rsp+1B8h+lpProcessInformation], rcx; lpProcessInformation
0x140327bf3  lea     rcx, [rsp+1B8h+StartupInfo]
0x140327bfb  mov     [rsp+1B8h+lpStartupInfo], rcx; lpStartupInfo
0x140327c00  mov     [rsp+1B8h+lpCurrentDirectory], rax; lpCurrentDirectory
0x140327c05  mov     [rsp+1B8h+lpEnvironment], rsi; lpEnvironment
0x140327c0a  mov     [rsp+1B8h+dwCreationFlags], r14d; dwCreationFlags
0x140327c0f  mov     [rsp+1B8h+bInheritHandles], r15d; bInheritHandles
0x140327c14  xor     r9d, r9d; lpThreadAttributes
0x140327c17  xor     r8d, r8d; lpProcessAttributes
0x140327c1a  mov     rdx, rbx; lpCommandLine
0x140327c1d  xor     ecx, ecx; lpApplicationName
0x140327c1f  call    cs:__imp_CreateProcessW
0x140327c25  test    eax, eax
0x140327c27  jnz     short loc_140327C91
0x140327c29  mov     rcx, [rsp+1B8h]; this
0x140327c31  lea     r8, aCW1SSrcOrchest_12; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x140327c38  mov     edx, 9Fh; void *
0x140327c3d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x140327c42  mov     edi, eax
0x140327c44  lea     rcx, [rsp+1B8h+var_C8]
0x140327c4c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140327c51  nop
0x140327c52  lea     rcx, [rsp+1B8h+ProcessInformation]; this
0x140327c5a  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x140327c5f  nop
0x140327c60  lea     rcx, [rsp+1B8h+var_E0]
0x140327c68  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x140327c6d  nop
0x140327c6e  test    rbx, rbx
0x140327c71  jz      short loc_140327C7D
0x140327c73  mov     rcx, rbx; pv
0x140327c76  call    cs:__imp_CoTaskMemFree
0x140327c7c  nop
0x140327c7d  lea     rcx, [rsp+1B8h+var_100]
0x140327c85  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140327c8a  mov     eax, edi
0x140327c8c  jmp     loc_140327F15
0x140327c91  mov     [rsp+1B8h+var_108], r15
0x140327c99  lea     rcx, [rsp+1B8h+var_158]
0x140327c9e  call    ?GetDockedSystem@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedSystem@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedSystem(void)
0x140327ca3  mov     rcx, [rax]
0x140327ca6  mov     [rsp+1B8h+var_108], r15
0x140327cae  mov     rax, [rcx]
0x140327cb1  lea     r8, [rsp+1B8h+var_108]
0x140327cb9  lea     rdx, _GUID_74d70212_eaa5_4298_b2f5_366da8756498
0x140327cc0  mov     rax, [rax]
0x140327cc3  call    _guard_dispatch_icall
0x140327cc8  nop
0x140327cc9  mov     rcx, [rsp+1B8h+var_158]
0x140327cce  test    rcx, rcx
0x140327cd1  jz      short loc_140327CE0
0x140327cd3  mov     rax, [rcx]
0x140327cd6  mov     rax, [rax+10h]
0x140327cda  call    _guard_dispatch_icall
0x140327cdf  nop
0x140327ce0  mov     rcx, [rsp+1B8h+var_108]
0x140327ce8  test    rcx, rcx
0x140327ceb  jz      short loc_140327D47
0x140327ced  movzx   r8d, [rsp+1B8h+arg_30]
0x140327cf6  mov     rax, [rcx]
0x140327cf9  mov     r9d, 1
0x140327cff  mov     rdx, [rsp+1B8h+ProcessInformation.hProcess]
0x140327d07  mov     rax, [rax+0C0h]
0x140327d0e  call    _guard_dispatch_icall
0x140327d13  mov     [rsp+1B8h+var_168], eax
0x140327d17  test    eax, eax
0x140327d19  jns     short loc_140327D3F
0x140327d1b  lea     rax, aFailedToChange; "Failed to change process priority: {}"
0x140327d22  mov     [rsp+1B8h+var_148], rax
0x140327d27  mov     [rsp+1B8h+var_140], 25h ; '%'
0x140327d30  lea     rdx, [rsp+1B8h+var_168]
0x140327d35  lea     rcx, [rsp+1B8h+var_148]
0x140327d3a  call    ??$Log@AEBJ@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBJ@Z; SystemInterface::Log<long const &>(std::wstring_view,long const &)
0x140327d3f  mov     rcx, [rsp+1B8h+var_108]
0x140327d47  test    rcx, rcx
0x140327d4a  jz      short loc_140327D59
0x140327d4c  mov     rax, [rcx]
0x140327d4f  mov     rax, [rax+10h]
0x140327d53  call    _guard_dispatch_icall
0x140327d58  nop
0x140327d59  mov     edx, 0DBBA00h; dwMilliseconds
0x140327d5e  mov     rcx, [rsp+1B8h+ProcessInformation.hProcess]; hHandle
0x140327d66  call    cs:__imp_WaitForSingleObject
0x140327d6c  mov     [rsp+1B8h+ExitCode], eax
0x140327d73  cmp     eax, 0FFFFFFFFh
0x140327d76  jnz     short loc_140327DD9
  ... truncated ...
```
