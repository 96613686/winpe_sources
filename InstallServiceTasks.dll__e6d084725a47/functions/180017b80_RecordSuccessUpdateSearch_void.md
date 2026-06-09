# RecordSuccessUpdateSearch(void)

- ea: `0x180017b80`
- end: `0x180017dc9`
- name: `?RecordSuccessUpdateSearch@@YAXXZ`
- size: `585`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180016044`

## callees

- `0x18000c520`
- `0x180014750`
- `0x1800149f0`
- `0x180014a64`
- `0x180014d48`
- `0x18001540c`
- `0x1800156e8`
- `0x18001584c`
- `0x180015e78`
- `0x180015ed0`
- `0x1800170dc`
- `0x18001719c`
- `0x180017b80`
- `0x180029190`
- `0x180034240`
- `0x180034498`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x180017b87`
- `msvcp_win!_Xtime_get_ticks` at `0x180017b87`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017da0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017c85`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017da0`

## string_xrefs

- `0x180017bd3`: `HasFrameworkUpdates`
- `0x180017b95`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x180017c34`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x180017d04`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x180017c58`: `AutoUpdateLastSuccessTime`
- `0x180017cb2`: `AutoUpdateLastSuccessTime`
- `0x180017d28`: `AutoUpdateLastSuccessTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
void RecordSuccessUpdateSearch(void)
{
  const WCHAR *RegistryLocation; // rax
  __int64 SelfToken; // rax
  TokenHelpers *v2; // rcx
  HSTRING *LocalSystemSidString; // rax
  HSTRING v4; // r8
  const char *v5; // r9
  __int64 v6; // rcx
  __int64 v7; // rbx
  __int64 v8; // rdx
  __int64 v9; // rdi
  const char *v10; // r9
  _QWORD v11[2]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v12[16]; // [rsp+38h] [rbp-40h] BYREF
  __int64 v13; // [rsp+48h] [rbp-30h] BYREF
  __int64 v14; // [rsp+50h] [rbp-28h]
  __int64 v15; // [rsp+58h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  HKEY hKey; // [rsp+80h] [rbp+8h] BYREF
  HSTRING string; // [rsp+88h] [rbp+10h] BYREF
  HKEY phkResult; // [rsp+90h] [rbp+18h] BYREF
  __int64 ticks; // [rsp+98h] [rbp+20h]

  ticks = _Xtime_get_ticks();
  RegistryLocation = (const WCHAR *)_InitOnceAndGetRegistryLocation(
                                      &qword_18006A458,
                                      L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State");
  try
  {
    Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(&phkResult, HKEY_LOCAL_MACHINE, RegistryLocation);
    LODWORD(hKey) = 0;
    Registry::SetValue<unsigned long>(phkResult, 0, L"HasFrameworkUpdates", &hKey);
    SelfToken = TokenHelpers::GetSelfToken((__int64)v11);
    TokenHelpers::GetTokenSid(&string, SelfToken);
    v11[0] = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable';
    Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(v11);
    LocalSystemSidString = (HSTRING *)TokenHelpers::GetLocalSystemSidString(v2);
    if ( (unsigned int)Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(
                         (Microsoft::WRL::Wrappers::Details *)string,
                         *LocalSystemSidString,
                         v4) )
    {
      Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(
        &hKey,
        HKEY_CURRENT_USER,
        L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State");
      Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
        hKey,
        0,
        L"AutoUpdateLastSuccessTime");
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      WindowsDeleteString(string);
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
    else
    {
      Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
        phkResult,
        0,
        L"AutoUpdateLastSuccessTime");
      TokenHelpers::GetAllLoggedInUserTokens(&v13);
      v6 = v13;
      v7 = v13;
      v8 = v14;
      v9 = v14;
      v11[0] = v14;
      while ( v7 != v9 )
      {
        try
        {
          TokenHelpers::ImpersonateContext::ImpersonateContext((__int64)v12, v7);
          Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(
            &hKey,
            HKEY_CURRENT_USER,
            L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\State");
          Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(
            hKey,
            0,
            L"AutoUpdateLastSuccessTime");
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
          TokenHelpers::ImpersonateContext::~ImpersonateContext((TokenHelpers::ImpersonateContext *)v12);
        }
        catch ( ... )
        {
          wil::details::in1diag3::Log_CaughtException(
            retaddr,
            (void *)0x133,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
            v10);
          v9 = v11[0];
        }
        v7 += 16;
        v8 = v14;
        v6 = v13;
      }
      if ( v6 )
      {
        std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>>(
          v6,
          v8);
        std::_Deallocate<16>(v13, (v15 - v13) & 0xFFFFFFFFFFFFFFF0uLL);
      }
      WindowsDeleteString(string);
      string = 0;
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&phkResult);
    }
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x135,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\scanforupdatesworker.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x180017b80  push    rbx
0x180017b82  push    rdi
0x180017b83  sub     rsp, 68h
0x180017b87  call    cs:__imp__Xtime_get_ticks
0x180017b8d  mov     [rsp+78h+arg_18], rax
0x180017b95  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180017b9c  lea     rcx, qword_18006A458
0x180017ba3  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x180017ba8  mov     r8, rax; lpSubKey
0x180017bab  mov     rdx, 0FFFFFFFF80000002h; hKey
0x180017bb2  lea     rcx, [rsp+78h+phkResult]; phkResult
0x180017bba  call    ??$OpenKeyForWrite@UCreateNew@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(HKEY__ *,ushort const *)
0x180017bbf  nop
0x180017bc0  mov     dword ptr [rsp+78h+hKey], 0
0x180017bcb  lea     r9, [rsp+78h+hKey]
0x180017bd3  lea     r8, aHasframeworkup; "HasFrameworkUpdates"
0x180017bda  xor     edx, edx
0x180017bdc  mov     rcx, [rsp+78h+phkResult]
0x180017be4  call    ??$SetValue@K@Registry@@YAXPEAUHKEY__@@PEBG1AEBK@Z; Registry::SetValue<ulong>(HKEY__ *,ushort const *,ushort const *,ulong const &)
0x180017be9  lea     rcx, [rsp+78h+var_50]
0x180017bee  call    ?GetSelfToken@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetSelfToken(void)
0x180017bf3  nop
0x180017bf4  mov     rdx, rax
0x180017bf7  lea     rcx, [rsp+78h+string]
0x180017bff  call    ?GetTokenSid@TokenHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@345@@Z; TokenHelpers::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180017c04  nop
0x180017c05  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180017c0c  mov     [rsp+78h+var_50], rax
0x180017c11  lea     rcx, [rsp+78h+var_50]
0x180017c16  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180017c1b  call    ?GetLocalSystemSidString@TokenHelpers@@YAAEBVHString@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetLocalSystemSidString(void)
0x180017c20  mov     rdx, [rax]; HSTRING
0x180017c23  mov     rcx, [rsp+78h+string]; this
0x180017c2b  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180017c30  test    eax, eax
0x180017c32  jz      short loc_180017CAA
0x180017c34  lea     r8, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180017c3b  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180017c42  lea     rcx, [rsp+78h+hKey]; phkResult
0x180017c4a  call    ??$OpenKeyForWrite@UCreateNew@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(HKEY__ *,ushort const *)
0x180017c4f  nop
0x180017c50  lea     r9, [rsp+78h+arg_18]
0x180017c58  lea     r8, aAutoupdatelast; "AutoUpdateLastSuccessTime"
0x180017c5f  xor     edx, edx; lpSubKey
0x180017c61  mov     rcx, [rsp+78h+hKey]; hKey
0x180017c69  call    ??$SetValue@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Registry@@YAXPEAUHKEY__@@PEBG1AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(HKEY__ *,ushort const *,ushort const *,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180017c6e  nop
0x180017c6f  lea     rcx, [rsp+78h+hKey]
0x180017c77  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180017c7c  nop
0x180017c7d  mov     rcx, [rsp+78h+string]; string
0x180017c85  call    cs:__imp_WindowsDeleteString
0x180017c8b  mov     [rsp+78h+string], 0
0x180017c97  lea     rcx, [rsp+78h+phkResult]
0x180017c9f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180017ca4  nop
0x180017ca5  jmp     loc_180017DC2
0x180017caa  lea     r9, [rsp+78h+arg_18]
0x180017cb2  lea     r8, aAutoupdatelast; "AutoUpdateLastSuccessTime"
0x180017cb9  xor     edx, edx; lpSubKey
0x180017cbb  mov     rcx, [rsp+78h+phkResult]; hKey
0x180017cc3  call    ??$SetValue@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Registry@@YAXPEAUHKEY__@@PEBG1AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(HKEY__ *,ushort const *,ushort const *,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180017cc8  lea     rcx, [rsp+78h+var_30]
0x180017ccd  call    ?GetAllLoggedInUserTokens@TokenHelpers@@YA?AV?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@XZ; TokenHelpers::GetAllLoggedInUserTokens(void)
0x180017cd2  nop
0x180017cd3  mov     rcx, [rsp+78h+var_30]
0x180017cd8  mov     rbx, rcx
0x180017cdb  mov     rdx, [rsp+78h+var_28]
0x180017ce0  mov     rdi, rdx
0x180017ce3  mov     [rsp+78h+var_50], rdx
0x180017ce8  mov     [rsp+78h+var_58], rbx
0x180017ced  cmp     rbx, rdi
0x180017cf0  jz      loc_180017D77
0x180017cf6  mov     rdx, rbx
0x180017cf9  lea     rcx, [rsp+78h+var_40]
0x180017cfe  call    ??0ImpersonateContext@TokenHelpers@@QEAA@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; TokenHelpers::ImpersonateContext::ImpersonateContext(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x180017d03  nop
0x180017d04  lea     r8, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180017d0b  mov     rdx, 0FFFFFFFF80000001h; hKey
0x180017d12  lea     rcx, [rsp+78h+hKey]; phkResult
0x180017d1a  call    ??$OpenKeyForWrite@UCreateNew@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(HKEY__ *,ushort const *)
0x180017d1f  nop
0x180017d20  lea     r9, [rsp+78h+arg_18]
0x180017d28  lea     r8, aAutoupdatelast; "AutoUpdateLastSuccessTime"
0x180017d2f  xor     edx, edx; lpSubKey
0x180017d31  mov     rcx, [rsp+78h+hKey]; hKey
0x180017d39  call    ??$SetValue@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Registry@@YAXPEAUHKEY__@@PEBG1AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(HKEY__ *,ushort const *,ushort const *,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180017d3e  nop
0x180017d3f  lea     rcx, [rsp+78h+hKey]
0x180017d47  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180017d4c  nop
0x180017d4d  lea     rcx, [rsp+78h+var_40]; this
0x180017d52  call    ??1ImpersonateContext@TokenHelpers@@QEAA@XZ; TokenHelpers::ImpersonateContext::~ImpersonateContext(void)
0x180017d57  nop
0x180017d58  jmp     short loc_180017D64
0x180017d5a  mov     rbx, [rsp+78h+var_58]
0x180017d5f  mov     rdi, [rsp+78h+var_50]
0x180017d64  add     rbx, 10h
0x180017d68  mov     rdx, [rsp+78h+var_28]
0x180017d6d  mov     rcx, [rsp+78h+var_30]
0x180017d72  jmp     loc_180017CE8
0x180017d77  test    rcx, rcx
0x180017d7a  jz      short loc_180017D98
0x180017d7c  call    ??$_Destroy_range@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>>(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> *,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> * const,std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>> &)
0x180017d81  mov     rcx, [rsp+78h+var_30]
0x180017d86  mov     rdx, [rsp+78h+var_20]
0x180017d8b  sub     rdx, rcx
0x180017d8e  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180017d92  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017d97  nop
0x180017d98  mov     rcx, [rsp+78h+string]; string
0x180017da0  call    cs:__imp_WindowsDeleteString
0x180017da6  mov     [rsp+78h+string], 0
0x180017db2  lea     rcx, [rsp+78h+phkResult]
0x180017dba  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180017dbf  nop
0x180017dc0  jmp     short $+2
0x180017dc2  add     rsp, 68h
0x180017dc6  pop     rdi
0x180017dc7  pop     rbx
0x180017dc8  retn
```
