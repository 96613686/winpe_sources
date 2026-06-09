# RecordSuccessUpdatesSearch(void)

- ea: `0x180027178`
- end: `0x1800273bf`
- name: `?RecordSuccessUpdatesSearch@@YAXXZ`
- size: `583`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `16`
- tags: `authz_impersonation, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180020a1c`

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
- `0x180027178`
- `0x180029190`
- `0x180034240`
- `0x180034498`

## import_xrefs

- `msvcp_win!_Xtime_get_ticks` at `0x18002717f`
- `msvcp_win!_Xtime_get_ticks` at `0x18002717f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002727d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027398`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002727d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180027398`

## string_xrefs

- `0x1800271cb`: `HasFrameworkUpdates`
- `0x18002718d`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x18002722c`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x1800272fc`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\State`
- `0x180027250`: `AutoUpdateLastSuccessTime`
- `0x1800272aa`: `AutoUpdateLastSuccessTime`
- `0x180027320`: `AutoUpdateLastSuccessTime`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void RecordSuccessUpdatesSearch(void)
{
  const WCHAR *RegistryLocation; // rax
  __int64 SelfToken; // rax
  TokenHelpers *v2; // rcx
  HSTRING *LocalSystemSidString; // rax
  HSTRING v4; // r8
  const char *v5; // r9
  void *v6; // rcx
  char *v7; // rbx
  char *v8; // rdx
  char *v9; // rdi
  const char *v10; // r9
  _QWORD v11[2]; // [rsp+28h] [rbp-50h] BYREF
  _BYTE v12[16]; // [rsp+38h] [rbp-40h] BYREF
  char *v13; // [rsp+48h] [rbp-30h] BYREF
  char *v14; // [rsp+50h] [rbp-28h]
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
    Registry::SetValue<unsigned long>(phkResult, 0, L"HasFrameworkUpdates", (int *)&hKey);
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
          TokenHelpers::ImpersonateContext::ImpersonateContext((__int64)v12, (__int64)v7);
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
            (void *)0xE03,
            (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
            v10);
          v9 = (char *)v11[0];
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
        std::_Deallocate<16>(v13, (struct std::nothrow_t *)((v15 - (_QWORD)v13) & 0xFFFFFFFFFFFFFFF0uLL));
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
      (void *)0xE05,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      v5);
  }
}

```

## disassembly

```asm
0x180027178  push    rbx
0x18002717a  push    rdi
0x18002717b  sub     rsp, 68h
0x18002717f  call    cs:__imp__Xtime_get_ticks
0x180027185  mov     [rsp+78h+arg_18], rax
0x18002718d  lea     rdx, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180027194  lea     rcx, qword_18006A458
0x18002719b  call    ?_InitOnceAndGetRegistryLocation@@YAPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@PEBG@Z; _InitOnceAndGetRegistryLocation(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *)
0x1800271a0  mov     r8, rax; lpSubKey
0x1800271a3  mov     rdx, 0FFFFFFFF80000002h; hKey
0x1800271aa  lea     rcx, [rsp+78h+phkResult]; phkResult
0x1800271b2  call    ??$OpenKeyForWrite@UCreateNew@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(HKEY__ *,ushort const *)
0x1800271b7  nop
0x1800271b8  mov     dword ptr [rsp+78h+hKey], 0
0x1800271c3  lea     r9, [rsp+78h+hKey]
0x1800271cb  lea     r8, aHasframeworkup; "HasFrameworkUpdates"
0x1800271d2  xor     edx, edx
0x1800271d4  mov     rcx, [rsp+78h+phkResult]
0x1800271dc  call    ??$SetValue@K@Registry@@YAXPEAUHKEY__@@PEBG1AEBK@Z; Registry::SetValue<ulong>(HKEY__ *,ushort const *,ushort const *,ulong const &)
0x1800271e1  lea     rcx, [rsp+78h+var_50]
0x1800271e6  call    ?GetSelfToken@TokenHelpers@@YA?AV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetSelfToken(void)
0x1800271eb  nop
0x1800271ec  mov     rdx, rax
0x1800271ef  lea     rcx, [rsp+78h+string]
0x1800271f7  call    ?GetTokenSid@TokenHelpers@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@345@@Z; TokenHelpers::GetTokenSid(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x1800271fc  nop
0x1800271fd  lea     rax, ??_7?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::`vftable'
0x180027204  mov     [rsp+78h+var_50], rax
0x180027209  lea     rcx, [rsp+78h+var_50]
0x18002720e  call    ?Close@?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>::Close(void)
0x180027213  call    ?GetLocalSystemSidString@TokenHelpers@@YAAEBVHString@Wrappers@WRL@Microsoft@@XZ; TokenHelpers::GetLocalSystemSidString(void)
0x180027218  mov     rdx, [rax]; HSTRING
0x18002721b  mov     rcx, [rsp+78h+string]; this
0x180027223  call    ?CompareStringOrdinal@Details@Wrappers@WRL@Microsoft@@YAHPEAUHSTRING__@@0@Z; Microsoft::WRL::Wrappers::Details::CompareStringOrdinal(HSTRING__ *,HSTRING__ *)
0x180027228  test    eax, eax
0x18002722a  jz      short loc_1800272A2
0x18002722c  lea     r8, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180027233  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18002723a  lea     rcx, [rsp+78h+hKey]; phkResult
0x180027242  call    ??$OpenKeyForWrite@UCreateNew@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(HKEY__ *,ushort const *)
0x180027247  nop
0x180027248  lea     r9, [rsp+78h+arg_18]
0x180027250  lea     r8, aAutoupdatelast; "AutoUpdateLastSuccessTime"
0x180027257  xor     edx, edx; lpSubKey
0x180027259  mov     rcx, [rsp+78h+hKey]; hKey
0x180027261  call    ??$SetValue@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Registry@@YAXPEAUHKEY__@@PEBG1AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(HKEY__ *,ushort const *,ushort const *,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180027266  nop
0x180027267  lea     rcx, [rsp+78h+hKey]
0x18002726f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027274  nop
0x180027275  mov     rcx, [rsp+78h+string]; string
0x18002727d  call    cs:__imp_WindowsDeleteString
0x180027283  mov     [rsp+78h+string], 0
0x18002728f  lea     rcx, [rsp+78h+phkResult]
0x180027297  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18002729c  nop
0x18002729d  jmp     loc_1800273B8
0x1800272a2  lea     r9, [rsp+78h+arg_18]
0x1800272aa  lea     r8, aAutoupdatelast; "AutoUpdateLastSuccessTime"
0x1800272b1  xor     edx, edx; lpSubKey
0x1800272b3  mov     rcx, [rsp+78h+phkResult]; hKey
0x1800272bb  call    ??$SetValue@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Registry@@YAXPEAUHKEY__@@PEBG1AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(HKEY__ *,ushort const *,ushort const *,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x1800272c0  lea     rcx, [rsp+78h+var_30]
0x1800272c5  call    ?GetAllLoggedInUserTokens@TokenHelpers@@YA?AV?$vector@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@XZ; TokenHelpers::GetAllLoggedInUserTokens(void)
0x1800272ca  nop
0x1800272cb  mov     rcx, [rsp+78h+var_30]
0x1800272d0  mov     rbx, rcx
0x1800272d3  mov     rdx, [rsp+78h+var_28]
0x1800272d8  mov     rdi, rdx
0x1800272db  mov     [rsp+78h+var_50], rdx
0x1800272e0  mov     [rsp+78h+var_58], rbx
0x1800272e5  cmp     rbx, rdi
0x1800272e8  jz      loc_18002736F
0x1800272ee  mov     rdx, rbx
0x1800272f1  lea     rcx, [rsp+78h+var_40]
0x1800272f6  call    ??0ImpersonateContext@TokenHelpers@@QEAA@AEBV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@Z; TokenHelpers::ImpersonateContext::ImpersonateContext(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> const &)
0x1800272fb  nop
0x1800272fc  lea     r8, aSoftwareMicros_2; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180027303  mov     rdx, 0FFFFFFFF80000001h; hKey
0x18002730a  lea     rcx, [rsp+78h+hKey]; phkResult
0x180027312  call    ??$OpenKeyForWrite@UCreateNew@NotFoundPolicy@Registry@@@Registry@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@PEAUHKEY__@@PEBG@Z; Registry::OpenKeyForWrite<Registry::NotFoundPolicy::CreateNew>(HKEY__ *,ushort const *)
0x180027317  nop
0x180027318  lea     r9, [rsp+78h+arg_18]
0x180027320  lea     r8, aAutoupdatelast; "AutoUpdateLastSuccessTime"
0x180027327  xor     edx, edx; lpSubKey
0x180027329  mov     rcx, [rsp+78h+hKey]; hKey
0x180027331  call    ??$SetValue@V?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Registry@@YAXPEAUHKEY__@@PEBG1AEBV?$time_point@Usystem_clock@chrono@std@@V?$duration@_JU?$ratio@$00$0JIJGIA@@std@@@23@@chrono@std@@@Z; Registry::SetValue<std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>>>(HKEY__ *,ushort const *,ushort const *,std::chrono::time_point<std::chrono::system_clock,std::chrono::duration<__int64,std::ratio<1,10000000>>> const &)
0x180027336  nop
0x180027337  lea     rcx, [rsp+78h+hKey]
0x18002733f  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180027344  nop
0x180027345  lea     rcx, [rsp+78h+var_40]; this
0x18002734a  call    ??1ImpersonateContext@TokenHelpers@@QEAA@XZ; TokenHelpers::ImpersonateContext::~ImpersonateContext(void)
0x18002734f  nop
0x180027350  jmp     short loc_18002735C
0x180027352  mov     rbx, [rsp+78h+var_58]
0x180027357  mov     rdi, [rsp+78h+var_50]
0x18002735c  add     rbx, 10h
0x180027360  mov     rdx, [rsp+78h+var_28]
0x180027365  mov     rcx, [rsp+78h+var_30]
0x18002736a  jmp     loc_1800272E0
0x18002736f  test    rcx, rcx
0x180027372  jz      short loc_180027390
0x180027374  call    ??$_Destroy_range@V?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@std@@@std@@YAXPEAV?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAV1234@AEAV?$allocator@V?$HandleT@UHANDLENullTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@@0@@Z; std::_Destroy_range<std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>>>(Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> *,Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits> * const,std::allocator<Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits>> &)
0x180027379  mov     rcx, [rsp+78h+var_30]
0x18002737e  mov     rdx, [rsp+78h+var_20]
0x180027383  sub     rdx, rcx
0x180027386  and     rdx, 0FFFFFFFFFFFFFFF0h
0x18002738a  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18002738f  nop
0x180027390  mov     rcx, [rsp+78h+string]; string
0x180027398  call    cs:__imp_WindowsDeleteString
0x18002739e  mov     [rsp+78h+string], 0
0x1800273aa  lea     rcx, [rsp+78h+phkResult]
0x1800273b2  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800273b7  nop
0x1800273b8  add     rsp, 68h
0x1800273bc  pop     rdi
0x1800273bd  pop     rbx
0x1800273be  retn
```
