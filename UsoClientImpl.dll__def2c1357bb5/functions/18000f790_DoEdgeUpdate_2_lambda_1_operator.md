# _DoEdgeUpdate_::_2_::_lambda_1_::operator()

- ea: `0x18000f790`
- end: `0x18000fb95`
- name: `_DoEdgeUpdate_::_2_::_lambda_1_::operator()`
- size: `1029`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x1800150a0`

## callees

- `0x180007804`
- `0x180007828`
- `0x180007848`
- `0x180009380`
- `0x18000f790`
- `0x1800183e0`
- `0x18002f938`
- `0x18002fe60`
- `0x18003359c`
- `0x180033f14`
- `0x180036b10`
- `0x180040cd0`
- `0x180056500`
- `0x180056524`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000fa4c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18000fa4c`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000fa66`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18000fa66`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000f8d8`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18000f8d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fb32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fb50`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fb32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000fb50`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f856`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f867`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f856`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000f867`

## string_xrefs

- `0x18000f7dd`: `%ProgramFiles(x86)%\Microsoft\EdgeUpdate\MicrosoftEdgeUpdate.exe`
- `0x18000f8ee`: `Unable to invoke MicrosoftEdgeUpdate: %ws`
- `0x18000f98c`: `EdgeUpdateTimeoutMinutes`
- `0x18000f9b7`: `EdgeUpdateTimeoutMinutes`
- `0x18000fb83`: `C:\__w\1\s\packages\Microsoft.Windows.Wil.Internal.0.3.30\inc\wil\opensource\wil\stl.h`

## pseudocode

```c
__int64 __fastcall DoEdgeUpdate_::_2_::_lambda_1_::operator()(__int64 a1)
{
  int v2; // eax
  unsigned int LastError; // edi
  char *v4; // rbx
  char *v6; // rsi
  __int16 *traits_2_unsigned_short; // rax
  const char *v8; // r9
  __int64 v9; // r11
  __int64 v10; // rax
  volatile signed __int32 *v11; // rdi
  int v12; // eax
  DWORD v13; // eax
  const char *v14; // r9
  unsigned int v15; // r8d
  const char *v16; // r9
  unsigned int v17; // r8d
  const char *v18; // r9
  int bInheritHandles; // [rsp+20h] [rbp-E0h]
  int bInheritHandlesa; // [rsp+20h] [rbp-E0h]
  LPVOID v21; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v22; // [rsp+58h] [rbp-A8h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v24[4]; // [rsp+70h] [rbp-90h] BYREF
  char v25[96]; // [rsp+90h] [rbp-70h] BYREF
  volatile signed __int32 *v26; // [rsp+F0h] [rbp-10h]
  char v27[40]; // [rsp+F8h] [rbp-8h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+120h] [rbp+20h] BYREF
  _DWORD v29[8]; // [rsp+138h] [rbp+38h] BYREF
  char v30; // [rsp+158h] [rbp+58h]
  char v31; // [rsp+160h] [rbp+60h]
  struct _STARTUPINFOW StartupInfo; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  **(_DWORD **)a1 = 0;
  **(_DWORD **)(a1 + 8) = 1;
  v21 = 0;
  wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(
    &v21,
    L"%ProgramFiles(x86)%\\Microsoft\\EdgeUpdate\\MicrosoftEdgeUpdate.exe");
  memset(&StartupInfo.cb + 1, 0, 0x64u);
  StartupInfo.cb = 104;
  pv = 0;
  v2 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(
         &pv,
         L"\"%ws\" %ws",
         v21,
         **(_QWORD **)(a1 + 16));
  LastError = v2;
  v4 = (char *)pv;
  if ( v2 >= 0 )
  {
    memset(&ProcessInformation, 0, sizeof(ProcessInformation));
    if ( CreateProcessW(0, (LPWSTR)pv, 0, 0, 0, 0, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      v6 = (char *)operator new(0x18u);
      *(_OWORD *)v6 = 0;
      *((_DWORD *)v6 + 2) = 1;
      *((_DWORD *)v6 + 3) = 1;
      *(_QWORD *)v6 = &std::_Ref_count_obj2<Windows::Registry>::`vftable';
      *((_QWORD *)v6 + 2) = &Windows::Registry::`vftable';
      v24[2] = v6 + 16;
      v24[3] = v6;
      v22 = 0;
      _InterlockedIncrement((volatile signed __int32 *)v6 + 2);
      *(_QWORD *)&v22 = v6 + 16;
      *((_QWORD *)&v22 + 1) = v6;
      Windows::Settings::Settings(v25, &v22, 0);
      traits_2_unsigned_short = (__int16 *)anonymous_namespace_::__std_find_trivial_impl__anonymous_namespace_::_Find_traits_2_unsigned_short_(
                                             L"EdgeUpdateTimeoutMinutes",
                                             word_1800685B2,
                                             0);
      if ( traits_2_unsigned_short == word_1800685B2
        || (v10 = ((char *)traits_2_unsigned_short - (char *)L"EdgeUpdateTimeoutMinutes") >> 1, v10 == -1) )
      {
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0xC9,
          (unsigned int)"C:\\__w\\1\\s\\packages\\Microsoft.Windows.Wil.Internal.0.3.30\\inc\\wil\\opensource\\wil\\stl.h",
          v8);
      }
      v24[0] = L"EdgeUpdateTimeoutMinutes";
      v24[1] = v10;
      Windows::Settings::TryGetSetting(v9, v29, v24);
      std::wstring::~wstring(v27);
      v11 = v26;
      if ( v26 )
      {
        if ( _InterlockedExchangeAdd(v26 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
      }
      if ( !v31 || (v12 = v29[0], v30) )
        v12 = 10;
      v13 = WaitForSingleObject(ProcessInformation.hProcess, 60000 * v12);
      if ( v13 == 258 )
      {
        LastError = -2147024638;
      }
      else if ( v13 == -1 )
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0x1F8,
                      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
                      v14);
      }
      else if ( GetExitCodeProcess(ProcessInformation.hProcess, *(LPDWORD *)(a1 + 8)) && **(_DWORD **)(a1 + 8) )
      {
        LastError = -2147467259;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1FD,
          (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
          (const char *)0x80004005LL,
          bInheritHandlesa);
      }
      else
      {
        **(_DWORD **)a1 = 1;
        LastError = 0;
      }
      if ( v31 && v30 != -1 && v30 && v30 != 1 )
        std::wstring::~wstring(v29);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v6)(v6);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v6 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(char *))(*(_QWORD *)v6 + 8LL))(v6);
      }
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastErrorMsg(
                    retaddr,
                    (void *)0x1ED,
                    (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
                    "Unable to invoke MicrosoftEdgeUpdate: %ws",
                    v4);
    }
    if ( ProcessInformation.hProcess && !CloseHandle(ProcessInformation.hProcess) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v15, v16);
    if ( ProcessInformation.hThread && !CloseHandle(ProcessInformation.hThread) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0x9D1, v17, v18);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1DE,
      (unsigned int)"C:\\__w\\1\\s\\src\\orchestrator\\clientImpl\\ClientImpl.cpp",
      (const char *)(unsigned int)v2,
      bInheritHandles);
  }
  if ( v4 )
    CoTaskMemFree(v4);
  if ( v21 )
    CoTaskMemFree(v21);
  return LastError;
}

```

## disassembly

```asm
0x18000f790  mov     [rsp-8+arg_8], rbx
0x18000f795  mov     [rsp-8+arg_10], rsi
0x18000f79a  push    rbp
0x18000f79b  push    rdi
0x18000f79c  push    r12
0x18000f79e  push    r14
0x18000f7a0  push    r15
0x18000f7a2  lea     rbp, [rsp-0F0h]
0x18000f7aa  sub     rsp, 1F0h
0x18000f7b1  mov     rax, cs:__security_cookie
0x18000f7b8  xor     rax, rsp
0x18000f7bb  mov     [rbp+110h+var_30], rax
0x18000f7c2  mov     r14, rcx
0x18000f7c5  xor     r15d, r15d
0x18000f7c8  mov     rax, [rcx]
0x18000f7cb  mov     [rax], r15d
0x18000f7ce  mov     rax, [rcx+8]
0x18000f7d2  mov     dword ptr [rax], 1
0x18000f7d8  mov     [rsp+210h+var_1C0], r15
0x18000f7dd  lea     rdx, aProgramfilesX8; "%ProgramFiles(x86)%\\Microsoft\\EdgeUpd"...
0x18000f7e4  lea     rcx, [rsp+210h+var_1C0]
0x18000f7e9  call    ??$ExpandEnvironmentStringsW@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@$0BAA@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_W@Z; wil::ExpandEnvironmentStringsW<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>,256>(wchar_t const *)
0x18000f7ee  nop
0x18000f7ef  xor     edx, edx; Val
0x18000f7f1  lea     r8d, [r15+64h]; Size
0x18000f7f5  lea     rcx, [rbp+110h+StartupInfo+4]; void *
0x18000f7f9  call    memset
0x18000f7fe  mov     [rbp+110h+StartupInfo.cb], 68h ; 'h'
0x18000f805  mov     [rsp+210h+pv], r15
0x18000f80a  mov     r9, [r14+10h]
0x18000f80e  mov     r9, [r9]
0x18000f811  mov     r8, [rsp+210h+var_1C0]
0x18000f816  lea     rdx, aWsWs; "\"%ws\" %ws"
0x18000f81d  lea     rcx, [rsp+210h+pv]
0x18000f822  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEA_WP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@@0@PEB_WZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>> &,wchar_t const *,...)
0x18000f827  mov     edi, eax
0x18000f829  mov     rbx, [rsp+210h+pv]
0x18000f82e  test    eax, eax
0x18000f830  jns     short loc_18000F89A
0x18000f832  mov     rcx, [rbp+118h]; this
0x18000f839  mov     r9d, eax; char *
0x18000f83c  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000f843  mov     edx, 1DEh; void *
0x18000f848  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f84d  nop
0x18000f84e  test    rbx, rbx
0x18000f851  jz      short loc_18000F85D
0x18000f853  mov     rcx, rbx; pv
0x18000f856  call    cs:__imp_CoTaskMemFree
0x18000f85c  nop
0x18000f85d  mov     rcx, [rsp+210h+var_1C0]; pv
0x18000f862  test    rcx, rcx
0x18000f865  jz      short loc_18000F86D
0x18000f867  call    cs:__imp_CoTaskMemFree
0x18000f86d  mov     eax, edi
0x18000f86f  mov     rcx, [rbp+110h+var_30]
0x18000f876  xor     rcx, rsp; StackCookie
0x18000f879  call    __security_check_cookie
0x18000f87e  lea     r11, [rsp+210h+var_20]
0x18000f886  mov     rbx, [r11+38h]
0x18000f88a  mov     rsi, [r11+40h]
0x18000f88e  mov     rsp, r11
0x18000f891  pop     r15
0x18000f893  pop     r14
0x18000f895  pop     r12
0x18000f897  pop     rdi
0x18000f898  pop     rbp
0x18000f899  retn
0x18000f89a  xorps   xmm0, xmm0
0x18000f89d  xor     eax, eax
0x18000f89f  movups  xmmword ptr [rbp+110h+ProcessInformation.hProcess], xmm0
0x18000f8a3  mov     qword ptr [rbp+110h+ProcessInformation.dwProcessId], rax
0x18000f8a7  lea     rax, [rbp+110h+ProcessInformation]
0x18000f8ab  mov     [rsp+210h+lpProcessInformation], rax; lpProcessInformation
0x18000f8b0  lea     rax, [rbp+110h+StartupInfo]
0x18000f8b4  mov     [rsp+210h+lpStartupInfo], rax; lpStartupInfo
0x18000f8b9  mov     [rsp+210h+lpCurrentDirectory], r15; lpCurrentDirectory
0x18000f8be  mov     [rsp+210h+lpEnvironment], r15; lpEnvironment
0x18000f8c3  mov     [rsp+210h+dwCreationFlags], r15d; dwCreationFlags
0x18000f8c8  mov     [rsp+210h+bInheritHandles], r15d; int
0x18000f8cd  xor     r9d, r9d; lpThreadAttributes
0x18000f8d0  xor     r8d, r8d; lpProcessAttributes
0x18000f8d3  mov     rdx, rbx; lpCommandLine
0x18000f8d6  xor     ecx, ecx; lpApplicationName
0x18000f8d8  call    cs:__imp_CreateProcessW
0x18000f8de  test    eax, eax
0x18000f8e0  jnz     short loc_18000F90D
0x18000f8e2  mov     rcx, [rbp+118h]; this
0x18000f8e9  mov     qword ptr [rsp+210h+bInheritHandles], rbx; char *
0x18000f8ee  lea     r9, aUnableToInvoke; "Unable to invoke MicrosoftEdgeUpdate: %"...
0x18000f8f5  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000f8fc  mov     edx, 1EDh; void *
0x18000f901  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18000f906  mov     edi, eax
0x18000f908  jmp     loc_18000FB29
0x18000f90d  mov     ecx, 18h; Size
0x18000f912  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000f917  mov     rsi, rax
0x18000f91a  mov     qword ptr [rsp+210h+var_1B8], rax
0x18000f91f  xorps   xmm0, xmm0
0x18000f922  movups  xmmword ptr [rax], xmm0
0x18000f925  mov     dword ptr [rax+8], 1
0x18000f92c  mov     dword ptr [rax+0Ch], 1
0x18000f933  lea     rax, ??_7?$_Ref_count_obj2@VRegistry@Windows@@@std@@6B@; const std::_Ref_count_obj2<Windows::Registry>::`vftable'
0x18000f93a  mov     [rsi], rax
0x18000f93d  lea     rcx, [rsi+10h]
0x18000f941  lea     rax, ??_7Registry@Windows@@6B@; const Windows::Registry::`vftable'
0x18000f948  mov     [rcx], rax
0x18000f94b  movups  [rbp+110h+var_190], xmm0
0x18000f94f  mov     qword ptr [rbp+110h+var_190], rcx
0x18000f953  mov     qword ptr [rbp+110h+var_190+8], rsi
0x18000f957  movdqu  [rsp+210h+var_1B8], xmm0
0x18000f95d  lock inc dword ptr [rsi+8]
0x18000f961  mov     qword ptr [rsp+210h+var_1B8], rcx
0x18000f966  mov     qword ptr [rsp+210h+var_1B8+8], rsi
0x18000f96b  xor     r8d, r8d
0x18000f96e  lea     rdx, [rsp+210h+var_1B8]
0x18000f973  lea     rcx, [rbp+110h+var_180]
0x18000f977  call    ??0Settings@Windows@@QEAA@V?$shared_ptr@VRegistry@SystemInterface@@@std@@_N@Z; Windows::Settings::Settings(std::shared_ptr<SystemInterface::Registry>,bool)
0x18000f97c  mov     r11, rax
0x18000f97f  xor     r8d, r8d
0x18000f982  lea     rdi, word_1800685B2
0x18000f989  mov     rdx, rdi
0x18000f98c  lea     r12, aEdgeupdatetime; "EdgeUpdateTimeoutMinutes"
0x18000f993  mov     rcx, r12
0x18000f996  call    _anonymous_namespace_____std_find_trivial_impl__anonymous_namespace____Find_traits_2_unsigned_short_
0x18000f99b  cmp     rax, rdi
0x18000f99e  jz      loc_18000FB7C
0x18000f9a4  sub     rax, r12
0x18000f9a7  sar     rax, 1
0x18000f9aa  or      r12, 0FFFFFFFFFFFFFFFFh
0x18000f9ae  cmp     rax, r12
0x18000f9b1  jz      loc_18000FB7C
0x18000f9b7  lea     rcx, aEdgeupdatetime; "EdgeUpdateTimeoutMinutes"
0x18000f9be  mov     qword ptr [rsp+210h+var_1A0], rcx
0x18000f9c3  mov     qword ptr [rsp+210h+var_1A0+8], rax
0x18000f9c8  movaps  xmm0, [rsp+210h+var_1A0]
0x18000f9cd  movdqa  [rsp+210h+var_1A0], xmm0
0x18000f9d3  lea     r8, [rsp+210h+var_1A0]
0x18000f9d8  lea     rdx, [rbp+110h+var_D8]
0x18000f9dc  mov     rcx, r11
0x18000f9df  call    ?TryGetSetting@Settings@Windows@@UEAA?AV?$optional@V?$variant@I_KV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@std@@@std@@V?$basic_zstring_view@_W@wil@@@Z; Windows::Settings::TryGetSetting(wil::basic_zstring_view<wchar_t>)
0x18000f9e4  nop
0x18000f9e5  lea     rcx, [rbp+110h+var_118]; void *
0x18000f9e9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000f9ee  mov     rdi, [rbp+110h+var_120]
0x18000f9f2  test    rdi, rdi
0x18000f9f5  jz      short loc_18000FA2E
0x18000f9f7  mov     eax, r12d
0x18000f9fa  lock xadd [rdi+8], eax
0x18000f9ff  add     eax, r12d
0x18000fa02  jnz     short loc_18000FA2E
0x18000fa04  mov     rax, [rdi]
0x18000fa07  mov     rcx, rdi
0x18000fa0a  mov     rax, [rax]
0x18000fa0d  call    _guard_dispatch_icall
0x18000fa12  mov     eax, r12d
0x18000fa15  lock xadd [rdi+0Ch], eax
0x18000fa1a  add     eax, r12d
0x18000fa1d  jnz     short loc_18000FA2E
0x18000fa1f  mov     rax, [rdi]
0x18000fa22  mov     rcx, rdi
0x18000fa25  mov     rax, [rax+8]
0x18000fa29  call    _guard_dispatch_icall
0x18000fa2e  cmp     [rbp+110h+var_B0], r15b
0x18000fa32  jz      short loc_18000FA3D
0x18000fa34  cmp     [rbp+110h+var_B8], r15b
0x18000fa38  mov     eax, [rbp+110h+var_D8]
0x18000fa3b  jz      short loc_18000FA42
0x18000fa3d  mov     eax, 0Ah
0x18000fa42  imul    edx, eax, 0EA60h; dwMilliseconds
0x18000fa48  mov     rcx, [rbp+110h+ProcessInformation.hProcess]; hHandle
0x18000fa4c  call    cs:__imp_WaitForSingleObject
0x18000fa52  cmp     eax, 102h
0x18000fa57  jz      short loc_18000FAC5
0x18000fa59  cmp     eax, 0FFFFFFFFh
0x18000fa5c  jz      short loc_18000FAA9
0x18000fa5e  mov     rdx, [r14+8]; lpExitCode
0x18000fa62  mov     rcx, [rbp+110h+ProcessInformation.hProcess]; hProcess
0x18000fa66  call    cs:__imp_GetExitCodeProcess
0x18000fa6c  test    eax, eax
0x18000fa6e  jz      short loc_18000FA9B
0x18000fa70  mov     rax, [r14+8]
0x18000fa74  cmp     [rax], r15d
0x18000fa77  jz      short loc_18000FA9B
0x18000fa79  mov     rcx, [rbp+118h]; this
0x18000fa80  mov     edi, 80004005h
0x18000fa85  mov     r9d, edi; char *
0x18000fa88  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000fa8f  mov     edx, 1FDh; void *
0x18000fa94  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000fa99  jmp     short loc_18000FACA
0x18000fa9b  mov     rax, [r14]
0x18000fa9e  mov     dword ptr [rax], 1
0x18000faa4  mov     edi, r15d
0x18000faa7  jmp     short loc_18000FACA
0x18000faa9  mov     rcx, [rbp+118h]; this
0x18000fab0  lea     r8, aCW1SSrcOrchest_3; "C:\\__w\\1\\s\\src\\orchestrator\\clien"...
0x18000fab7  mov     edx, 1F8h; void *
0x18000fabc  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000fac1  mov     edi, eax
0x18000fac3  jmp     short loc_18000FACA
0x18000fac5  mov     edi, 80070102h
0x18000faca  cmp     [rbp+110h+var_B0], r15b
0x18000face  jz      short loc_18000FAF1
0x18000fad0  movsx   rax, [rbp+110h+var_B8]
0x18000fad5  add     rax, 1
0x18000fad9  jz      short loc_18000FAF1
0x18000fadb  sub     rax, 1
0x18000fadf  jz      short loc_18000FAF1
0x18000fae1  cmp     rax, 1
0x18000fae5  jz      short loc_18000FAF1
0x18000fae7  lea     rcx, [rbp+110h+var_D8]; void *
0x18000faeb  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000faf0  nop
0x18000faf1  mov     eax, r12d
0x18000faf4  lock xadd [rsi+8], eax
0x18000faf9  add     eax, r12d
0x18000fafc  jnz     short loc_18000FB29
0x18000fafe  mov     rax, [rsi]
0x18000fb01  mov     rcx, rsi
0x18000fb04  mov     rax, [rax]
0x18000fb07  call    _guard_dispatch_icall
0x18000fb0c  mov     eax, r12d
0x18000fb0f  lock xadd [rsi+0Ch], eax
0x18000fb14  add     eax, r12d
0x18000fb17  jnz     short loc_18000FB29
0x18000fb19  mov     rax, [rsi]
0x18000fb1c  mov     rcx, rsi
0x18000fb1f  mov     rax, [rax+8]
0x18000fb23  call    _guard_dispatch_icall
0x18000fb28  nop
0x18000fb29  mov     rcx, [rbp+110h+ProcessInformation.hProcess]; hObject
0x18000fb2d  test    rcx, rcx
0x18000fb30  jz      short loc_18000FB43
0x18000fb32  call    cs:__imp_CloseHandle
0x18000fb38  mov     rcx, [rbp+118h]; this
0x18000fb3f  test    eax, eax
0x18000fb41  jz      short loc_18000FB66
0x18000fb43  mov     rcx, [rbp+110h+ProcessInformation.hThread]; hObject
0x18000fb47  test    rcx, rcx
0x18000fb4a  jz      loc_18000F84E
0x18000fb50  call    cs:__imp_CloseHandle
0x18000fb56  mov     rcx, [rbp+118h]; this
0x18000fb5d  test    eax, eax
0x18000fb5f  jz      short loc_18000FB71
0x18000fb61  jmp     loc_18000F84E
0x18000fb66  mov     edx, 9D1h; void *
0x18000fb6b  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fb71  mov     edx, 9D1h; void *
0x18000fb76  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18000fb7c  mov     rcx, [rbp+118h]; this
0x18000fb83  lea     r8, aCW1SPackagesMi_0; "C:\\__w\\1\\s\\packages\\Microsoft.Wind"...
0x18000fb8a  mov     edx, 0C9h; void *
0x18000fb8f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
