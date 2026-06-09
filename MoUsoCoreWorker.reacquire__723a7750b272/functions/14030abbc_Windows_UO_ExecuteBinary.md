# Windows::UO::ExecuteBinary

- ea: `0x14030abbc`
- end: `0x14030b317`
- name: `Windows::UO::ExecuteBinary`
- size: `1883`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x14030d950`

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
- `0x14030abbc`
- `0x140312df0`
- `0x140312fb0`
- `0x140314330`
- `0x14036efd0`
- `0x140374388`
- `0x140379070`
- `0x140380b50`
- `0x140380bd0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14030b222`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x14030b222`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14030b007`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x14030b007`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030ad3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030ada8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030ae3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030b05e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030b1a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030b1f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030b279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030b2d8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030ad3f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030ada8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030ae3d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030b05e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030b1a0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030b1f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030b279`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14030b2d8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14030b15a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14030b15a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14030b148`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x14030b148`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x14030af0c`
- `api-ms-win-core-processenvironment-l1-1-0!FreeEnvironmentStringsW` at `0x14030af0c`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x14030adf2`
- `api-ms-win-core-processenvironment-l1-1-0!GetEnvironmentStringsW` at `0x14030adf2`

## string_xrefs

- `0x14030acb7`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`
- `0x14030ad23`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`
- `0x14030ad8c`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`
- `0x14030ae15`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`
- `0x14030b019`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`
- `0x14030b234`: `C:\__w\1\s\src\orchestrator\system\windows\updateproviders\uoproviders\UOUtils.hpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=11 #try_helpers=1
__int64 __fastcall Windows::UO::ExecuteBinary(_QWORD *a1, _QWORD *a2, _QWORD *a3, __int64 a4, _QWORD *a5)
{
  __int64 v7; // rbx
  __int128 *v9; // r8
  int v10; // eax
  unsigned int v11; // ebx
  int v12; // eax
  void *lpEnvironment; // rsi
  DWORD dwCreationFlags; // r14d
  LPWCH EnvironmentStringsW; // rax
  WCHAR *v16; // rbx
  __int64 v17; // r9
  LPWCH v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rax
  void *v21; // rbx
  const wchar_t *v22; // rax
  const WCHAR *lpCurrentDirectory; // rax
  const char *v24; // r9
  unsigned int LastError; // edi
  struct _PROCESS_INFORMATION *v26; // rdx
  void (__fastcall ***v27)(_QWORD, GUID *, LPVOID *); // rcx
  LPVOID v28; // rcx
  DWORD v29; // eax
  signed int v30; // eax
  struct _PROCESS_INFORMATION *v31; // rdx
  struct _PROCESS_INFORMATION *v32; // rdx
  const char *v33; // r9
  struct _PROCESS_INFORMATION *v34; // rdx
  struct _PROCESS_INFORMATION *v35; // rdx
  BOOL bInheritHandles; // [rsp+20h] [rbp-198h]
  int v37; // [rsp+50h] [rbp-168h] BYREF
  LPVOID pv; // [rsp+58h] [rbp-160h] BYREF
  const wchar_t *v39; // [rsp+60h] [rbp-158h] BYREF
  __int64 v40; // [rsp+68h] [rbp-150h]
  _QWORD v41[4]; // [rsp+70h] [rbp-148h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+90h] [rbp-128h] BYREF
  DWORD ExitCode; // [rsp+A8h] [rbp-110h] BYREF
  LPVOID v44; // [rsp+B0h] [rbp-108h] BYREF
  __int128 v45; // [rsp+B8h] [rbp-100h] BYREF
  __m128i si128; // [rsp+C8h] [rbp-F0h]
  __int128 v47; // [rsp+D8h] [rbp-E0h] BYREF
  __int64 v48; // [rsp+E8h] [rbp-D0h]
  LPCWSTR v49[4]; // [rsp+F0h] [rbp-C8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+110h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1B8h] [rbp+0h]

  v45 = 0;
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v45) = 0;
  if ( *(_QWORD *)(a4 + 8) )
  {
    std::wstring::operator=<wil::basic_zstring_view<wchar_t>,0>(&v45);
  }
  else
  {
    v7 = Windows::PathVerification::VerifyUpdaterPath(v41, *a1, *a2);
    if ( &v45 != (__int128 *)v7 )
    {
      std::wstring::~wstring(&v45);
      v45 = *(_OWORD *)v7;
      si128 = *(__m128i *)(v7 + 16);
      *(_QWORD *)(v7 + 16) = 0;
      *(_QWORD *)(v7 + 24) = 7;
      *(_WORD *)v7 = 0;
    }
    std::wstring::~wstring(v41);
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
    std::wstring::~wstring(&v45);
    return 2147942487LL;
  }
  v9 = &v45;
  if ( a3[1] )
  {
    if ( si128.m128i_i64[1] > 7uLL )
      v9 = (__int128 *)v45;
    v12 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            &pv,
            L"%ws %ws",
            v9,
            *a3);
    v11 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOUtils.hpp",
        (const char *)(unsigned int)v12,
        bInheritHandles);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_14;
    }
  }
  else
  {
    if ( si128.m128i_i64[1] > 7uLL )
      v9 = (__int128 *)v45;
    v10 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
            &pv,
            L"%ws",
            v9);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x62,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOUtils.hpp",
        (const char *)(unsigned int)v10,
        bInheritHandles);
      if ( pv )
        CoTaskMemFree(pv);
LABEL_14:
      std::wstring::~wstring(&v45);
      return v11;
    }
  }
  lpEnvironment = 0;
  dwCreationFlags = 0;
  v47 = 0;
  v48 = 0;
  if ( *a5 != a5[1] )
  {
    EnvironmentStringsW = GetEnvironmentStringsW();
    v16 = EnvironmentStringsW;
    v39 = EnvironmentStringsW;
    if ( !EnvironmentStringsW )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x72,
        (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOUtils.hpp",
        (const char *)0x8007000ELL,
        bInheritHandles);
      std::vector<wchar_t>::_Tidy(&v47);
      if ( pv )
        CoTaskMemFree(pv);
      std::wstring::~wstring(&v45);
      return 2147942414LL;
    }
    v17 = 0;
    if ( *EnvironmentStringsW )
    {
      v18 = EnvironmentStringsW;
      do
      {
        v19 = -1;
        do
          ++v19;
        while ( v18[v19] );
        v20 = v19 + 1;
        v17 += v20;
        v18 += v20;
      }
      while ( *v18 );
    }
    std::vector<wchar_t>::_Insert_counted_range<wchar_t const *>(&v47, *((_QWORD *)&v47 + 1), v16, (2 * v17) >> 1);
    std::vector<wchar_t>::_Insert_counted_range<wchar_t const *>(
      &v47,
      *((_QWORD *)&v47 + 1),
      *a5,
      (__int64)(a5[1] - *a5) >> 1);
    LOWORD(v37) = 0;
    if ( *((_QWORD *)&v47 + 1) == v48 )
    {
      std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(&v47, *((_QWORD *)&v47 + 1), &v37);
    }
    else
    {
      **((_WORD **)&v47 + 1) = 0;
      *((_QWORD *)&v47 + 1) += 2LL;
    }
    lpEnvironment = (void *)v47;
    dwCreationFlags = 1024;
    FreeEnvironmentStringsW(v16);
  }
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  v21 = pv;
  v44 = pv;
  v39 = L"Starting callback: {}";
  v40 = 21;
  SystemInterface::Log<wchar_t *>(&v39, &v44);
  v22 = (const wchar_t *)&v45;
  if ( si128.m128i_i64[1] > 7uLL )
    v22 = (const wchar_t *)v45;
  v39 = v22;
  v40 = si128.m128i_i64[0];
  std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(v41, &v39);
  std::filesystem::path::parent_path(v41, v49);
  std::wstring::~wstring(v41);
  lpCurrentDirectory = (const WCHAR *)v49;
  if ( v49[3] > (LPCWSTR)7 )
    lpCurrentDirectory = v49[0];
  if ( !CreateProcessW(
          0,
          (LPWSTR)v21,
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
                  v24);
    std::wstring::~wstring(v49);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v26);
    std::vector<wchar_t>::_Tidy(&v47);
    if ( v21 )
      CoTaskMemFree(v21);
LABEL_69:
    std::wstring::~wstring(&v45);
    return LastError;
  }
  v44 = 0;
  v27 = *(void (__fastcall ****)(_QWORD, GUID *, LPVOID *))Windows::DockedHelpers::GetDockedSystem(&v39);
  v44 = 0;
  (**v27)(v27, &GUID_74d70212_eaa5_4298_b2f5_366da8756498, &v44);
  if ( v39 )
    (*(void (__fastcall **)(const wchar_t *))(*(_QWORD *)v39 + 16LL))(v39);
  v28 = v44;
  if ( v44 )
  {
    v37 = (*(__int64 (__fastcall **)(LPVOID, HANDLE, _QWORD, __int64))(*(_QWORD *)v44 + 192LL))(
            v44,
            ProcessInformation.hProcess,
            0,
            1);
    if ( v37 < 0 )
    {
      v41[0] = L"Failed to change process priority: {}";
      v41[1] = 37;
      SystemInterface::Log<long const &>(v41, &v37);
    }
    v28 = v44;
  }
  if ( v28 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v28 + 16LL))(v28);
  v29 = WaitForSingleObject(ProcessInformation.hProcess, 0xDBBA0u);
  ExitCode = v29;
  if ( v29 == -1 )
  {
    v30 = GetLastError();
    LastError = (unsigned __int16)v30 | 0x80070000;
    if ( v30 <= 0 )
      LastError = v30;
    std::wstring::~wstring(v49);
    wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v31);
    std::vector<wchar_t>::_Tidy(&v47);
    if ( v21 )
      CoTaskMemFree(v21);
    goto LABEL_69;
  }
  if ( v29 != 258 )
  {
    if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
    {
      LastError = (unsigned __int16)ExitCode | 0x80070000;
      if ( (int)ExitCode <= 0 )
        LastError = ExitCode;
      std::wstring::~wstring(v49);
      wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v35);
      std::vector<wchar_t>::_Tidy(&v47);
      if ( v21 )
        CoTaskMemFree(v21);
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xB7,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\system\\windows\\updateproviders\\uoproviders\\UOUtils.hpp",
                    v33);
      std::wstring::~wstring(v49);
      wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v34);
      std::vector<wchar_t>::_Tidy(&v47);
      if ( v21 )
        CoTaskMemFree(v21);
    }
    goto LABEL_69;
  }
  std::wstring::~wstring(v49);
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v32);
  std::vector<wchar_t>::_Tidy(&v47);
  if ( v21 )
    CoTaskMemFree(v21);
  std::wstring::~wstring(&v45);
  return 2147942658LL;
}

```

## disassembly

```asm
0x14030abbc  push    rbx
0x14030abbe  push    rsi
0x14030abbf  push    rdi
0x14030abc0  push    r14
0x14030abc2  push    r15
0x14030abc4  sub     rsp, 190h
0x14030abcb  mov     rax, cs:__security_cookie
0x14030abd2  xor     rax, rsp
0x14030abd5  mov     [rsp+1B8h+var_38], rax
0x14030abdd  mov     rsi, r8
0x14030abe0  mov     rdi, rdx
0x14030abe3  xor     r15d, r15d
0x14030abe6  xorps   xmm0, xmm0
0x14030abe9  movups  [rsp+1B8h+var_100], xmm0
0x14030abf1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x14030abf9  movdqu  [rsp+1B8h+var_F0], xmm1
0x14030ac02  mov     word ptr [rsp+1B8h+var_100], r15w
0x14030ac0b  cmp     [r9+8], r15
0x14030ac0f  jz      short loc_14030AC20
0x14030ac11  lea     rcx, [rsp+1B8h+var_100]; void *
0x14030ac19  call    ??$?4V?$basic_zstring_view@_W@wil@@$0A@@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV01@AEBV?$basic_zstring_view@_W@wil@@@Z; std::wstring::operator=<wil::basic_zstring_view<wchar_t>,0>(wil::basic_zstring_view<wchar_t> const &)
0x14030ac1e  jmp     short loc_14030AC7E
0x14030ac20  mov     r8, [rdx]
0x14030ac23  mov     rdx, [rcx]
0x14030ac26  lea     rcx, [rsp+1B8h+var_148]
0x14030ac2b  call    ?VerifyUpdaterPath@PathVerification@Windows@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0@Z; Windows::PathVerification::VerifyUpdaterPath(wchar_t const *,wchar_t const *)
0x14030ac30  mov     rbx, rax
0x14030ac33  lea     rax, [rsp+1B8h+var_100]
0x14030ac3b  cmp     rax, rbx
0x14030ac3e  jz      short loc_14030AC74
0x14030ac40  lea     rcx, [rsp+1B8h+var_100]
0x14030ac48  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030ac4d  movups  xmm0, xmmword ptr [rbx]
0x14030ac50  movups  [rsp+1B8h+var_100], xmm0
0x14030ac58  movups  xmm1, xmmword ptr [rbx+10h]
0x14030ac5c  movups  [rsp+1B8h+var_F0], xmm1
0x14030ac64  mov     [rbx+10h], r15
0x14030ac68  mov     qword ptr [rbx+18h], 7
0x14030ac70  mov     [rbx], r15w
0x14030ac74  lea     rcx, [rsp+1B8h+var_148]
0x14030ac79  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030ac7e  xor     edx, edx; Val
0x14030ac80  lea     r8d, [rdx+64h]; Size
0x14030ac84  lea     rcx, [rsp+1B8h+StartupInfo+4]; void *
0x14030ac8c  call    memset
0x14030ac91  mov     [rsp+1B8h+StartupInfo.cb], 68h ; 'h'
0x14030ac9c  mov     [rsp+1B8h+pv], r15
0x14030aca1  cmp     [rdi+8], r15
0x14030aca5  jnz     short loc_14030ACDD
0x14030aca7  mov     rcx, [rsp+1B8h]; this
0x14030acaf  mov     ebx, 80070057h
0x14030acb4  mov     r9d, ebx; char *
0x14030acb7  lea     r8, aCW1SSrcOrchest_12; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14030acbe  mov     edx, 5Eh ; '^'; void *
0x14030acc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14030acc8  nop
0x14030acc9  lea     rcx, [rsp+1B8h+var_100]
0x14030acd1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030acd6  mov     eax, ebx
0x14030acd8  jmp     loc_14030B2F7
0x14030acdd  lea     r8, [rsp+1B8h+var_100]
0x14030ace5  lea     rcx, [rsp+1B8h+pv]
0x14030acea  cmp     [rsi+8], r15
0x14030acee  jnz     short loc_14030AD5A
0x14030acf0  cmp     qword ptr [rsp+1B8h+var_F0+8], 7
0x14030acf9  cmova   r8, qword ptr [rsp+1B8h+var_100]
0x14030ad02  lea     rdx, aWs; "%ws"
0x14030ad09  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)
0x14030ad0e  mov     ebx, eax
0x14030ad10  test    eax, eax
0x14030ad12  jns     loc_14030ADC3
0x14030ad18  mov     rcx, [rsp+1B8h]; this
0x14030ad20  mov     r9d, eax; char *
0x14030ad23  lea     r8, aCW1SSrcOrchest_12; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14030ad2a  mov     edx, 62h ; 'b'; void *
0x14030ad2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14030ad34  nop
0x14030ad35  mov     rcx, [rsp+1B8h+pv]; pv
0x14030ad3a  test    rcx, rcx
0x14030ad3d  jz      short loc_14030AD46
0x14030ad3f  call    cs:__imp_CoTaskMemFree
0x14030ad45  nop
0x14030ad46  lea     rcx, [rsp+1B8h+var_100]
0x14030ad4e  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030ad53  mov     eax, ebx
0x14030ad55  jmp     loc_14030B2F7
0x14030ad5a  cmp     qword ptr [rsp+1B8h+var_F0+8], 7
0x14030ad63  cmova   r8, qword ptr [rsp+1B8h+var_100]
0x14030ad6c  mov     r9, [rsi]
0x14030ad6f  lea     rdx, aWsWs_1; "%ws %ws"
0x14030ad76  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)
0x14030ad7b  mov     ebx, eax
0x14030ad7d  test    eax, eax
0x14030ad7f  jns     short loc_14030ADC3
0x14030ad81  mov     rcx, [rsp+1B8h]; this
0x14030ad89  mov     r9d, eax; char *
0x14030ad8c  lea     r8, aCW1SSrcOrchest_12; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14030ad93  mov     edx, 66h ; 'f'; void *
0x14030ad98  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14030ad9d  nop
0x14030ad9e  mov     rcx, [rsp+1B8h+pv]; pv
0x14030ada3  test    rcx, rcx
0x14030ada6  jz      short loc_14030ADAF
0x14030ada8  call    cs:__imp_CoTaskMemFree
0x14030adae  nop
0x14030adaf  lea     rcx, [rsp+1B8h+var_100]
0x14030adb7  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030adbc  mov     eax, ebx
0x14030adbe  jmp     loc_14030B2F7
0x14030adc3  mov     rsi, r15
0x14030adc6  mov     r14d, r15d
0x14030adc9  xorps   xmm1, xmm1
0x14030adcc  movdqu  [rsp+1B8h+var_E0], xmm1
0x14030add5  mov     [rsp+1B8h+var_D0], r15
0x14030addd  mov     rdi, [rsp+1B8h+arg_20]
0x14030ade5  mov     rax, [rdi+8]
0x14030ade9  cmp     [rdi], rax
0x14030adec  jz      loc_14030AF12
0x14030adf2  call    cs:__imp_GetEnvironmentStringsW
0x14030adf8  mov     rbx, rax
0x14030adfb  mov     [rsp+1B8h+var_158], rax
0x14030ae00  test    rax, rax
0x14030ae03  jnz     short loc_14030AE58
0x14030ae05  mov     rcx, [rsp+1B8h]; this
0x14030ae0d  mov     ebx, 8007000Eh
0x14030ae12  mov     r9d, ebx; char *
0x14030ae15  lea     r8, aCW1SSrcOrchest_12; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14030ae1c  lea     edx, [rax+72h]; void *
0x14030ae1f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x14030ae24  nop
0x14030ae25  lea     rcx, [rsp+1B8h+var_E0]
0x14030ae2d  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x14030ae32  nop
0x14030ae33  mov     rcx, [rsp+1B8h+pv]; pv
0x14030ae38  test    rcx, rcx
0x14030ae3b  jz      short loc_14030AE44
0x14030ae3d  call    cs:__imp_CoTaskMemFree
0x14030ae43  nop
0x14030ae44  lea     rcx, [rsp+1B8h+var_100]
0x14030ae4c  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030ae51  mov     eax, ebx
0x14030ae53  jmp     loc_14030B2F7
0x14030ae58  mov     r9, r15
0x14030ae5b  cmp     [rax], r15w
0x14030ae5f  jz      short loc_14030AE82
0x14030ae61  mov     rcx, rbx
0x14030ae64  or      rax, 0FFFFFFFFFFFFFFFFh
0x14030ae68  inc     rax
0x14030ae6b  cmp     [rcx+rax*2], r15w
0x14030ae70  jnz     short loc_14030AE68
0x14030ae72  inc     rax
0x14030ae75  add     r9, rax
0x14030ae78  lea     rcx, [rcx+rax*2]
0x14030ae7c  cmp     [rcx], r15w
0x14030ae80  jnz     short loc_14030AE64
0x14030ae82  add     r9, r9
0x14030ae85  sar     r9, 1
0x14030ae88  mov     r8, rbx
0x14030ae8b  mov     rdx, qword ptr [rsp+1B8h+var_E0+8]
0x14030ae93  lea     rcx, [rsp+1B8h+var_E0]
0x14030ae9b  call    ??$_Insert_counted_range@PEB_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@_W@std@@@std@@@1@PEB_W_K@Z; std::vector<wchar_t>::_Insert_counted_range<wchar_t const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<wchar_t>>>,wchar_t const *,unsigned __int64)
0x14030aea0  mov     r9, [rdi+8]
0x14030aea4  sub     r9, [rdi]
0x14030aea7  sar     r9, 1
0x14030aeaa  mov     r8, [rdi]
0x14030aead  mov     rdx, qword ptr [rsp+1B8h+var_E0+8]
0x14030aeb5  lea     rcx, [rsp+1B8h+var_E0]
0x14030aebd  call    ??$_Insert_counted_range@PEB_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXV?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@_W@std@@@std@@@1@PEB_W_K@Z; std::vector<wchar_t>::_Insert_counted_range<wchar_t const *>(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<wchar_t>>>,wchar_t const *,unsigned __int64)
0x14030aec2  mov     word ptr [rsp+1B8h+var_168], r15w
0x14030aec8  mov     rdx, qword ptr [rsp+1B8h+var_E0+8]
0x14030aed0  cmp     rdx, [rsp+1B8h+var_D0]
0x14030aed8  jz      short loc_14030AEE9
0x14030aeda  mov     [rdx], r15w
0x14030aede  add     qword ptr [rsp+1B8h+var_E0+8], 2
0x14030aee7  jmp     short loc_14030AEFB
0x14030aee9  lea     r8, [rsp+1B8h+var_168]
0x14030aeee  lea     rcx, [rsp+1B8h+var_E0]
0x14030aef6  call    ??$_Emplace_reallocate@_W@?$vector@_WV?$allocator@_W@std@@@std@@AEAAPEA_WQEA_W$$QEA_W@Z; std::vector<wchar_t>::_Emplace_reallocate<wchar_t>(wchar_t * const,wchar_t &&)
0x14030aefb  mov     rsi, qword ptr [rsp+1B8h+var_E0]
0x14030af03  mov     r14d, 400h
0x14030af09  mov     rcx, rbx; penv
0x14030af0c  call    cs:__imp_FreeEnvironmentStringsW
0x14030af12  xorps   xmm0, xmm0
0x14030af15  xor     eax, eax
0x14030af17  movups  xmmword ptr [rsp+1B8h+ProcessInformation.hProcess], xmm0
0x14030af1f  mov     qword ptr [rsp+1B8h+ProcessInformation.dwProcessId], rax
0x14030af27  mov     rbx, [rsp+1B8h+pv]
0x14030af2c  mov     [rsp+1B8h+var_108], rbx
0x14030af34  lea     rax, aStartingCallba; "Starting callback: {}"
0x14030af3b  mov     [rsp+1B8h+var_158], rax
0x14030af40  mov     [rsp+1B8h+var_150], 15h
0x14030af49  lea     rdx, [rsp+1B8h+var_108]
0x14030af51  lea     rcx, [rsp+1B8h+var_158]
0x14030af56  call    ??$Log@PEA_W@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@$$QEAPEA_W@Z; SystemInterface::Log<wchar_t *>(std::wstring_view,wchar_t * &&)
0x14030af5b  lea     rax, [rsp+1B8h+var_100]
0x14030af63  cmp     qword ptr [rsp+1B8h+var_F0+8], 7
0x14030af6c  cmova   rax, qword ptr [rsp+1B8h+var_100]
0x14030af75  mov     [rsp+1B8h+var_158], rax
0x14030af7a  mov     rax, qword ptr [rsp+1B8h+var_F0]
0x14030af82  mov     [rsp+1B8h+var_150], rax
0x14030af87  lea     rdx, [rsp+1B8h+var_158]
0x14030af8c  lea     rcx, [rsp+1B8h+var_148]
0x14030af91  call    ??$_Convert_stringoid_to_wide@U_Normal_conversion@filesystem@std@@@filesystem@std@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@1@V?$basic_string_view@_WU?$char_traits@_W@std@@@1@U_Normal_conversion@01@@Z; std::filesystem::_Convert_stringoid_to_wide<std::filesystem::_Normal_conversion>(std::wstring_view,std::filesystem::_Normal_conversion)
0x14030af96  nop
0x14030af97  lea     rdx, [rsp+1B8h+var_C8]
0x14030af9f  lea     rcx, [rsp+1B8h+var_148]
0x14030afa4  call    ?parent_path@path@filesystem@std@@QEBA?AV123@XZ; std::filesystem::path::parent_path(void)
0x14030afa9  nop
0x14030afaa  lea     rcx, [rsp+1B8h+var_148]
0x14030afaf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030afb4  lea     rax, [rsp+1B8h+var_C8]
0x14030afbc  cmp     [rsp+1B8h+var_B0], 7
0x14030afc5  cmova   rax, [rsp+1B8h+var_C8]
0x14030afce  lea     rcx, [rsp+1B8h+ProcessInformation]
0x14030afd6  mov     [rsp+1B8h+lpProcessInformation], rcx; lpProcessInformation
0x14030afdb  lea     rcx, [rsp+1B8h+StartupInfo]
0x14030afe3  mov     [rsp+1B8h+lpStartupInfo], rcx; lpStartupInfo
0x14030afe8  mov     [rsp+1B8h+lpCurrentDirectory], rax; lpCurrentDirectory
0x14030afed  mov     [rsp+1B8h+lpEnvironment], rsi; lpEnvironment
0x14030aff2  mov     [rsp+1B8h+dwCreationFlags], r14d; dwCreationFlags
0x14030aff7  mov     [rsp+1B8h+bInheritHandles], r15d; bInheritHandles
0x14030affc  xor     r9d, r9d; lpThreadAttributes
0x14030afff  xor     r8d, r8d; lpProcessAttributes
0x14030b002  mov     rdx, rbx; lpCommandLine
0x14030b005  xor     ecx, ecx; lpApplicationName
0x14030b007  call    cs:__imp_CreateProcessW
0x14030b00d  test    eax, eax
0x14030b00f  jnz     short loc_14030B079
0x14030b011  mov     rcx, [rsp+1B8h]; this
0x14030b019  lea     r8, aCW1SSrcOrchest_12; "C:\\__w\\1\\s\\src\\orchestrator\\syste"...
0x14030b020  mov     edx, 9Fh; void *
0x14030b025  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x14030b02a  mov     edi, eax
0x14030b02c  lea     rcx, [rsp+1B8h+var_C8]
0x14030b034  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030b039  nop
0x14030b03a  lea     rcx, [rsp+1B8h+ProcessInformation]; this
0x14030b042  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x14030b047  nop
0x14030b048  lea     rcx, [rsp+1B8h+var_E0]
0x14030b050  call    ?_Tidy@?$vector@_WV?$allocator@_W@std@@@std@@AEAAXXZ; std::vector<wchar_t>::_Tidy(void)
0x14030b055  nop
0x14030b056  test    rbx, rbx
0x14030b059  jz      short loc_14030B065
0x14030b05b  mov     rcx, rbx; pv
0x14030b05e  call    cs:__imp_CoTaskMemFree
0x14030b064  nop
0x14030b065  lea     rcx, [rsp+1B8h+var_100]
0x14030b06d  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14030b072  mov     eax, edi
0x14030b074  jmp     loc_14030B2F7
0x14030b079  mov     [rsp+1B8h+var_108], r15
0x14030b081  lea     rcx, [rsp+1B8h+var_158]
0x14030b086  call    ?GetDockedSystem@DockedHelpers@Windows@@YA?AV?$com_ptr_t@UIDockedSystem@@Uerr_exception_policy@wil@@@wil@@XZ; Windows::DockedHelpers::GetDockedSystem(void)
0x14030b08b  mov     rcx, [rax]
0x14030b08e  mov     [rsp+1B8h+var_108], r15
0x14030b096  mov     rax, [rcx]
0x14030b099  lea     r8, [rsp+1B8h+var_108]
0x14030b0a1  lea     rdx, _GUID_74d70212_eaa5_4298_b2f5_366da8756498
0x14030b0a8  mov     rax, [rax]
0x14030b0ab  call    _guard_dispatch_icall
0x14030b0b0  nop
0x14030b0b1  mov     rcx, [rsp+1B8h+var_158]
0x14030b0b6  test    rcx, rcx
0x14030b0b9  jz      short loc_14030B0C8
0x14030b0bb  mov     rax, [rcx]
0x14030b0be  mov     rax, [rax+10h]
0x14030b0c2  call    _guard_dispatch_icall
0x14030b0c7  nop
0x14030b0c8  mov     rcx, [rsp+1B8h+var_108]
0x14030b0d0  test    rcx, rcx
0x14030b0d3  jz      short loc_14030B129
0x14030b0d5  mov     rax, [rcx]
0x14030b0d8  mov     r9d, 1
0x14030b0de  xor     r8d, r8d
0x14030b0e1  mov     rdx, [rsp+1B8h+ProcessInformation.hProcess]
0x14030b0e9  mov     rax, [rax+0C0h]
0x14030b0f0  call    _guard_dispatch_icall
0x14030b0f5  mov     [rsp+1B8h+var_168], eax
0x14030b0f9  test    eax, eax
0x14030b0fb  jns     short loc_14030B121
0x14030b0fd  lea     rax, aFailedToChange; "Failed to change process priority: {}"
0x14030b104  mov     [rsp+1B8h+var_148], rax
0x14030b109  mov     [rsp+1B8h+var_140], 25h ; '%'
0x14030b112  lea     rdx, [rsp+1B8h+var_168]
0x14030b117  lea     rcx, [rsp+1B8h+var_148]
0x14030b11c  call    ??$Log@AEBJ@SystemInterface@@YAXV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@AEBJ@Z; SystemInterface::Log<long const &>(std::wstring_view,long const &)
0x14030b121  mov     rcx, [rsp+1B8h+var_108]
0x14030b129  test    rcx, rcx
0x14030b12c  jz      short loc_14030B13B
0x14030b12e  mov     rax, [rcx]
0x14030b131  mov     rax, [rax+10h]
0x14030b135  call    _guard_dispatch_icall
0x14030b13a  nop
0x14030b13b  mov     edx, 0DBBA0h; dwMilliseconds
0x14030b140  mov     rcx, [rsp+1B8h+ProcessInformation.hProcess]; hHandle
0x14030b148  call    cs:__imp_WaitForSingleObject
0x14030b14e  mov     [rsp+1B8h+ExitCode], eax
0x14030b155  cmp     eax, 0FFFFFFFFh
0x14030b158  jnz     short loc_14030B1BB
  ... truncated ...
```
