# AppReadiness::BrokerSession::NotifyOfInstalledPackages(void)

- ea: `0x1800174ac`
- end: `0x1800178b1`
- name: `?NotifyOfInstalledPackages@BrokerSession@AppReadiness@@AEAAXXZ`
- size: `1029`
- prototype: `void __fastcall(AppReadiness::BrokerSession *__hidden this)`
- caller_count: `2`
- callee_count: `17`
- tags: `authz_impersonation, service_task, installer_update, broker_com_uri`

## callers

- `0x1800173c4`
- `0x1800266f8`

## callees

- `0x180002958`
- `0x180002a48`
- `0x18000b488`
- `0x18000c000`
- `0x1800174ac`
- `0x1800178d0`
- `0x18001870c`
- `0x1800187c4`
- `0x180027a4c`
- `0x18002a970`
- `0x18003235c`
- `0x180037e0c`
- `0x18003e210`
- `0x18003ecb4`
- `0x1800617f0`
- `0x180061a64`
- `0x180079010`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017643`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017643`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017512`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180017512`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800174fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800174fb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800176ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017736`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800176ad`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017736`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180017863`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800176d7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800176d7`

## string_xrefs

- `0x18001753f`: `AppReadiness::BrokerSession::NotifyOfInstalledPackages`
- `0x1800175c2`: `AppReadiness::BrokerSession::NotifyOfInstalledPackages`
- `0x18001777a`: `AppReadiness::BrokerSession::NotifyOfInstalledPackages`
- `0x1800177b8`: `AppReadiness::BrokerSession::NotifyOfInstalledPackages`
- `0x180017533`: `onecoreuap\shell\appreadiness\src\core\brokersession.cpp`
- `0x1800175b6`: `onecoreuap\shell\appreadiness\src\core\brokersession.cpp`
- `0x18001776e`: `onecoreuap\shell\appreadiness\src\core\brokersession.cpp`
- `0x1800177ac`: `onecoreuap\shell\appreadiness\src\core\brokersession.cpp`
- `0x1800175c9`: `packageManager->FindPackagesByUserSecurityId(userSid.Get(), &iterable)`

## pseudocode

```c
// Hidden C++ exception states: #wind=12
void __fastcall AppReadiness::BrokerSession::NotifyOfInstalledPackages(AppReadiness::BrokerSession *this)
{
  HRESULT StringReference; // eax
  int v3; // eax
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, HSTRING, __int64 *); // rbx
  int v6; // eax
  __int64 *v7; // r14
  __int64 *v8; // rsi
  unsigned __int64 v9; // rcx
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, unsigned __int64 *); // rbx
  int v12; // eax
  unsigned __int64 v13; // rdi
  __int64 (__fastcall *v14)(unsigned __int64, HSTRING *); // rbx
  int v15; // eax
  PCWSTR StringRawBuffer; // rax
  __int64 v17; // r8
  unsigned __int64 v18; // rcx
  _QWORD *v19; // rdx
  __int64 v20; // rcx
  __int64 v21; // rcx
  unsigned __int64 v22; // [rsp+30h] [rbp-99h] BYREF
  HSTRING v23; // [rsp+38h] [rbp-91h] BYREF
  __int64 v24; // [rsp+40h] [rbp-89h] BYREF
  __int64 v25; // [rsp+48h] [rbp-81h] BYREF
  HSTRING v26; // [rsp+50h] [rbp-79h] BYREF
  _QWORD v27[3]; // [rsp+58h] [rbp-71h] BYREF
  __int64 *v28; // [rsp+70h] [rbp-59h] BYREF
  __int64 *v29; // [rsp+78h] [rbp-51h]
  __int128 hstringHeader; // [rsp+88h] [rbp-41h] BYREF
  __int128 hstringHeader_16; // [rsp+98h] [rbp-31h] BYREF
  _QWORD v32[7]; // [rsp+B0h] [rbp-19h] BYREF
  _QWORD *v33; // [rsp+E8h] [rbp+1Fh]

  v25 = 0;
  *((_QWORD *)&hstringHeader_16 + 1) = 0;
  StringReference = WindowsCreateStringReference(
                      L"Windows.Management.Deployment.PackageManager",
                      0x2Cu,
                      (HSTRING_HEADER *)&hstringHeader,
                      (HSTRING *)&hstringHeader_16 + 1);
  if ( StringReference < 0 )
  {
    RaiseException(StringReference, 1u, 0, 0);
    __debugbreak();
  }
  v3 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(
         *((__int64 *)&hstringHeader_16 + 1),
         &v25);
  if ( v3 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&hstringHeader,
      v3,
      "Windows::Foundation::ActivateInstance(HStringReference(RuntimeClass_Windows_Management_Deployment_PackageManager)."
      "Get(), &packageManager)",
      "AppReadiness::BrokerSession::NotifyOfInstalledPackages",
      "onecoreuap\\shell\\appreadiness\\src\\core\\brokersession.cpp",
      300);
    throw (Windows::HResultException *)&hstringHeader;
  }
  to_winstring(&v26, (PCNZWCH)(*((_QWORD *)this + 4) + 64LL));
  v24 = 0;
  v4 = v25;
  v5 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64 *))(*(_QWORD *)v25 + 96LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v24);
  v6 = v5(v4, v26, &v24);
  if ( v6 < 0 )
  {
    Windows::HResultException::HResultException(
      (Windows::HResultException *)&hstringHeader,
      v6,
      "packageManager->FindPackagesByUserSecurityId(userSid.Get(), &iterable)",
      "AppReadiness::BrokerSession::NotifyOfInstalledPackages",
      "onecoreuap\\shell\\appreadiness\\src\\core\\brokersession.cpp",
      303);
    throw (Windows::HResultException *)&hstringHeader;
  }
  to_vector<Windows::ApplicationModel::IPackage,Windows::ApplicationModel::Package>(&v28, &v24);
  std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,enum AppReadiness::Impl::BaseTaskGroup::TaskState>>(v27);
  v7 = v29;
  v8 = v28;
  v9 = v29 - v28;
  v22 = v9;
  if ( v9 > (__int64)(v27[2] - v27[0]) >> 5 )
  {
    if ( v9 > 0x7FFFFFFFFFFFFFFLL )
      std::_Xlength_error("vector too long");
    std::vector<std::wstring>::_Reallocate<0>(v27, &v22);
    v7 = v29;
    v8 = v28;
  }
  while ( v8 != v7 )
  {
    v22 = 0;
    v10 = *v8;
    v11 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)*v8 + 48LL);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v22);
    v12 = v11(v10, &v22);
    if ( v12 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&hstringHeader,
        v12,
        "package->get_Id(&packageId)",
        "AppReadiness::BrokerSession::NotifyOfInstalledPackages",
        "onecoreuap\\shell\\appreadiness\\src\\core\\brokersession.cpp",
        311);
      throw (Windows::HResultException *)&hstringHeader;
    }
    v23 = 0;
    v13 = v22;
    v14 = *(__int64 (__fastcall **)(unsigned __int64, HSTRING *))(*(_QWORD *)v22 + 96LL);
    WindowsDeleteString(0);
    v23 = 0;
    v15 = v14(v13, &v23);
    if ( v15 < 0 )
    {
      Windows::HResultException::HResultException(
        (Windows::HResultException *)&hstringHeader,
        v15,
        "packageId->get_FullName(packageFullName.GetAddressOf())",
        "AppReadiness::BrokerSession::NotifyOfInstalledPackages",
        "onecoreuap\\shell\\appreadiness\\src\\core\\brokersession.cpp",
        314);
      throw (Windows::HResultException *)&hstringHeader;
    }
    StringRawBuffer = WindowsGetStringRawBuffer(v23, 0);
    hstringHeader = 0;
    hstringHeader_16 = 0;
    v17 = -1;
    do
      ++v17;
    while ( StringRawBuffer[v17] );
    std::wstring::_Construct<1,unsigned short const *>(&hstringHeader);
    std::vector<std::wstring>::emplace_back<std::wstring>(v27, &hstringHeader);
    if ( *((_QWORD *)&hstringHeader_16 + 1) > 7u )
      std::_Deallocate<16>((void *)hstringHeader, 2LL * *((_QWORD *)&hstringHeader_16 + 1) + 2);
    WindowsDeleteString(v23);
    v23 = 0;
    v18 = v22;
    if ( v22 )
    {
      v22 = 0;
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v18 + 16LL))(v18);
    }
    ++v8;
  }
  v32[0] = off_18007C350;
  v32[1] = this;
  v32[2] = v27;
  v33 = v32;
  AppReadiness::User::ExecuteUnderContext(*((_QWORD *)this + 4), (__int64)v32);
  if ( v33 )
  {
    v19 = v32;
    LOBYTE(v19) = v33 != v32;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v33 + 32LL))(v33, v19);
  }
  std::vector<std::wstring>::_Tidy(v27);
  std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(&v28);
  v20 = v24;
  if ( v24 )
  {
    v24 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
  }
  WindowsDeleteString(v26);
  v26 = 0;
  v21 = v25;
  if ( v25 )
  {
    v25 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  }
}

```

## disassembly

```asm
0x1800174ac  mov     [rsp-8+arg_8], rbx
0x1800174b1  mov     [rsp-8+arg_10], rsi
0x1800174b6  push    rbp
0x1800174b7  push    rdi
0x1800174b8  push    r12
0x1800174ba  push    r14
0x1800174bc  push    r15
0x1800174be  lea     rbp, [rsp-37h]
0x1800174c3  sub     rsp, 100h
0x1800174ca  mov     rax, cs:__security_cookie
0x1800174d1  xor     rax, rsp
0x1800174d4  mov     [rbp+57h+var_30], rax
0x1800174d8  mov     r15, rcx
0x1800174db  xor     r12d, r12d
0x1800174de  mov     [rsp+120h+var_D8], r12
0x1800174e3  mov     [rbp+57h+string], r12
0x1800174e7  lea     r9, [rbp+57h+string]; string
0x1800174eb  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x1800174ef  lea     edx, [r12+2Ch]; length
0x1800174f4  lea     rcx, ?RuntimeClass_Windows_Management_Deployment_PackageManager@@3QBGB; "Windows.Management.Deployment.PackageMa"...
0x1800174fb  call    cs:__imp_WindowsCreateStringReference
0x180017501  test    eax, eax
0x180017503  jns     short loc_180017519
0x180017505  xor     r9d, r9d; lpArguments
0x180017508  xor     r8d, r8d; nNumberOfArguments
0x18001750b  lea     edx, [r12+1]; dwExceptionFlags
0x180017510  mov     ecx, eax; dwExceptionCode
0x180017512  call    cs:__imp_RaiseException
0x180017518  int     3; Trap to Debugger
0x180017519  lea     rdx, [rsp+120h+var_D8]
0x18001751e  mov     rcx, [rbp+57h+string]
0x180017522  call    ??$ActivateInstance@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPackageManager@Deployment@Management@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Management::Deployment::IPackageManager>>)
0x180017527  test    eax, eax
0x180017529  jns     short loc_180017569
0x18001752b  mov     [rsp+120h+var_F8], 12Ch; int
0x180017533  lea     rcx, aOnecoreuapShel_1; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x18001753a  mov     [rsp+120h+var_100], rcx; char *
0x18001753f  lea     r9, aAppreadinessBr; "AppReadiness::BrokerSession::NotifyOfIn"...
0x180017546  lea     r8, aWindowsFoundat_0; "Windows::Foundation::ActivateInstance(H"...
0x18001754d  mov     edx, eax; int
0x18001754f  lea     rcx, [rbp+57h+hstringHeader]; this
0x180017553  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180017558  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001755f  lea     rcx, [rbp+57h+hstringHeader]; pExceptionObject
0x180017563  call    _CxxThrowException_0
0x180017569  mov     rdx, [r15+20h]
0x18001756d  add     rdx, 40h ; '@'; sourceString
0x180017571  lea     rcx, [rbp+57h+var_D0]; string
0x180017575  call    ?to_winstring@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; to_winstring(std::wstring const &)
0x18001757a  nop
0x18001757b  mov     [rsp+120h+var_E0], r12
0x180017580  mov     rdi, [rsp+120h+var_D8]
0x180017585  mov     rax, [rdi]
0x180017588  mov     rbx, [rax+60h]
0x18001758c  lea     rcx, [rsp+120h+var_E0]
0x180017591  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017596  lea     r8, [rsp+120h+var_E0]
0x18001759b  mov     rdx, [rbp+57h+var_D0]
0x18001759f  mov     rcx, rdi
0x1800175a2  mov     rax, rbx
0x1800175a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175aa  test    eax, eax
0x1800175ac  jns     short loc_1800175EC
0x1800175ae  mov     [rsp+120h+var_F8], 12Fh; int
0x1800175b6  lea     rcx, aOnecoreuapShel_1; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800175bd  mov     [rsp+120h+var_100], rcx; char *
0x1800175c2  lea     r9, aAppreadinessBr; "AppReadiness::BrokerSession::NotifyOfIn"...
0x1800175c9  lea     r8, aPackagemanager_10; "packageManager->FindPackagesByUserSecur"...
0x1800175d0  mov     edx, eax; int
0x1800175d2  lea     rcx, [rbp+57h+hstringHeader]; this
0x1800175d6  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800175db  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800175e2  lea     rcx, [rbp+57h+hstringHeader]; pExceptionObject
0x1800175e6  call    _CxxThrowException_0
0x1800175ec  lea     rdx, [rsp+120h+var_E0]
0x1800175f1  lea     rcx, [rbp+57h+var_B0]
0x1800175f5  call    ??$to_vector@UIPackage@ApplicationModel@Windows@@VPackage@23@@@YA?AV?$vector@V?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UIPackage@ApplicationModel@Windows@@@WRL@Microsoft@@@std@@@std@@AEBV?$ComPtr@U?$IIterable@PEAVPackage@ApplicationModel@Windows@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Z; to_vector<Windows::ApplicationModel::IPackage,Windows::ApplicationModel::Package>(Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IIterable<Windows::ApplicationModel::Package *>> const &)
0x1800175fa  nop
0x1800175fb  lea     rcx, [rbp+57h+var_C8]
0x1800175ff  call    ??0?$vector@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@V?$allocator@U?$pair@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@W4TaskState@BaseTaskGroup@Impl@AppReadiness@@@std@@@2@@std@@QEAA@XZ; std::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>::vector<std::pair<Microsoft::WRL::ComPtr<AppReadiness::ITask>,AppReadiness::Impl::BaseTaskGroup::TaskState>>(void)
0x180017604  nop
0x180017605  mov     r14, [rbp+57h+var_A8]
0x180017609  mov     rcx, r14
0x18001760c  mov     rsi, [rbp+57h+var_B0]
0x180017610  sub     rcx, rsi
0x180017613  sar     rcx, 3
0x180017617  mov     [rsp+120h+var_F0], rcx
0x18001761c  mov     rax, [rbp+57h+var_B8]
0x180017620  sub     rax, [rbp+57h+var_C8]
0x180017624  sar     rax, 5
0x180017628  cmp     rcx, rax
0x18001762b  jbe     short loc_180017660
0x18001762d  mov     rax, 7FFFFFFFFFFFFFFh
0x180017637  cmp     rcx, rax
0x18001763a  jbe     short loc_18001764A
0x18001763c  lea     rcx, aVectorTooLong; "vector too long"
0x180017643  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x18001764a  lea     rdx, [rsp+120h+var_F0]
0x18001764f  lea     rcx, [rbp+57h+var_C8]
0x180017653  call    ??$_Reallocate@$0A@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXAEA_K@Z; std::vector<std::wstring>::_Reallocate<0>(unsigned __int64 &)
0x180017658  mov     r14, [rbp+57h+var_A8]
0x18001765c  mov     rsi, [rbp+57h+var_B0]
0x180017660  cmp     rsi, r14
0x180017663  jz      loc_1800177E2
0x180017669  mov     [rsp+120h+var_F0], r12
0x18001766e  mov     rdi, [rsi]
0x180017671  mov     rax, [rdi]
0x180017674  mov     rbx, [rax+30h]
0x180017678  lea     rcx, [rsp+120h+var_F0]
0x18001767d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180017682  lea     rdx, [rsp+120h+var_F0]
0x180017687  mov     rcx, rdi
0x18001768a  mov     rax, rbx
0x18001768d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017692  test    eax, eax
0x180017694  js      loc_1800177A4
0x18001769a  mov     [rsp+120h+var_E8], r12
0x18001769f  mov     rdi, [rsp+120h+var_F0]
0x1800176a4  mov     rax, [rdi]
0x1800176a7  mov     rbx, [rax+60h]
0x1800176ab  xor     ecx, ecx; string
0x1800176ad  call    cs:__imp_WindowsDeleteString
0x1800176b3  mov     [rsp+120h+var_E8], r12
0x1800176b8  lea     rdx, [rsp+120h+var_E8]
0x1800176bd  mov     rcx, rdi
0x1800176c0  mov     rax, rbx
0x1800176c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800176c8  test    eax, eax
0x1800176ca  js      loc_180017766
0x1800176d0  xor     edx, edx; length
0x1800176d2  mov     rcx, [rsp+120h+var_E8]; string
0x1800176d7  call    cs:__imp_WindowsGetStringRawBuffer
0x1800176dd  xorps   xmm0, xmm0
0x1800176e0  movups  xmmword ptr [rbp+57h+hstringHeader.Reserved], xmm0
0x1800176e4  xorps   xmm1, xmm1
0x1800176e7  movdqu  xmmword ptr [rbp-31h], xmm1
0x1800176ec  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800176f0  inc     r8
0x1800176f3  cmp     [rax+r8*2], r12w
0x1800176f8  jnz     short loc_1800176F0
0x1800176fa  mov     rdx, rax
0x1800176fd  lea     rcx, [rbp+57h+hstringHeader]
0x180017701  call    ??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z; std::wstring::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)
0x180017706  nop
0x180017707  lea     rdx, [rbp+57h+hstringHeader]
0x18001770b  lea     rcx, [rbp+57h+var_C8]
0x18001770f  call    ??$emplace_back@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@QEAAAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@$$QEAV21@@Z; std::vector<std::wstring>::emplace_back<std::wstring>(std::wstring &&)
0x180017714  nop
0x180017715  mov     rdx, [rbp+57h+string]
0x180017719  cmp     rdx, 7
0x18001771d  jbe     short loc_180017731
0x18001771f  lea     rdx, ds:2[rdx*2]
0x180017727  mov     rcx, qword ptr [rbp+57h+hstringHeader.Reserved]
0x18001772b  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x180017730  nop
0x180017731  mov     rcx, [rsp+120h+var_E8]; string
0x180017736  call    cs:__imp_WindowsDeleteString
0x18001773c  mov     [rsp+120h+var_E8], r12
0x180017741  mov     rcx, [rsp+120h+var_F0]
0x180017746  test    rcx, rcx
0x180017749  jz      short loc_18001775D
0x18001774b  mov     [rsp+120h+var_F0], r12
0x180017750  mov     rax, [rcx]
0x180017753  mov     rax, [rax+10h]
0x180017757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001775c  nop
0x18001775d  add     rsi, 8
0x180017761  jmp     loc_180017660
0x180017766  mov     [rsp+120h+var_F8], 13Ah; int
0x18001776e  lea     rcx, aOnecoreuapShel_1; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x180017775  mov     [rsp+120h+var_100], rcx; char *
0x18001777a  lea     r9, aAppreadinessBr; "AppReadiness::BrokerSession::NotifyOfIn"...
0x180017781  lea     r8, aPackageidGetFu; "packageId->get_FullName(packageFullName"...
0x180017788  mov     edx, eax; int
0x18001778a  lea     rcx, [rbp+57h+hstringHeader]; this
0x18001778e  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x180017793  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x18001779a  lea     rcx, [rbp+57h+hstringHeader]; pExceptionObject
0x18001779e  call    _CxxThrowException_0
0x1800177a4  mov     [rsp+120h+var_F8], 137h; int
0x1800177ac  lea     rcx, aOnecoreuapShel_1; "onecoreuap\\shell\\appreadiness\\src\\c"...
0x1800177b3  mov     [rsp+120h+var_100], rcx; char *
0x1800177b8  lea     r9, aAppreadinessBr; "AppReadiness::BrokerSession::NotifyOfIn"...
0x1800177bf  lea     r8, aPackageGetIdPa_0; "package->get_Id(&packageId)"
0x1800177c6  mov     edx, eax; int
0x1800177c8  lea     rcx, [rbp+57h+hstringHeader]; this
0x1800177cc  call    ??0HResultException@Windows@@QEAA@JPEBD00H@Z; Windows::HResultException::HResultException(long,char const *,char const *,char const *,int)
0x1800177d1  lea     rdx, _TI1?AVHResultException@Windows@@; pThrowInfo
0x1800177d8  lea     rcx, [rbp+57h+hstringHeader]; pExceptionObject
0x1800177dc  call    _CxxThrowException_0
0x1800177e2  lea     rax, off_18007C350
0x1800177e9  mov     [rbp+57h+var_70], rax
0x1800177ed  mov     [rbp+57h+var_68], r15
0x1800177f1  lea     rax, [rbp+57h+var_C8]
0x1800177f5  mov     [rbp+57h+var_60], rax
0x1800177f9  lea     rax, [rbp+57h+var_70]
0x1800177fd  mov     [rbp+57h+var_38], rax
0x180017801  lea     rdx, [rbp+57h+var_70]
0x180017805  mov     rcx, [r15+20h]
0x180017809  call    ?ExecuteUnderContext@User@AppReadiness@@QEAAJAEBV?$function@$$A6AXXZ@std@@@Z; AppReadiness::User::ExecuteUnderContext(std::function<void (void)> const &)
0x18001780e  nop
0x18001780f  mov     rcx, [rbp+57h+var_38]
0x180017813  test    rcx, rcx
0x180017816  jz      short loc_18001782F
0x180017818  mov     rax, [rcx]
0x18001781b  lea     rdx, [rbp+57h+var_70]
0x18001781f  cmp     rcx, rdx
0x180017822  setnz   dl
0x180017825  mov     rax, [rax+20h]
0x180017829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001782e  nop
0x18001782f  lea     rcx, [rbp+57h+var_C8]
0x180017833  call    ?_Tidy@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@AEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x180017838  nop
0x180017839  lea     rcx, [rbp+57h+var_B0]
0x18001783d  call    ?_Tidy@?$vector@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UITask@AppReadiness@@@WRL@Microsoft@@@std@@@std@@AEAAXXZ; std::vector<Microsoft::WRL::ComPtr<AppReadiness::ITask>>::_Tidy(void)
0x180017842  nop
0x180017843  mov     rcx, [rsp+120h+var_E0]
0x180017848  test    rcx, rcx
0x18001784b  jz      short loc_18001785F
0x18001784d  mov     [rsp+120h+var_E0], r12
0x180017852  mov     rax, [rcx]
0x180017855  mov     rax, [rax+10h]
0x180017859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001785e  nop
0x18001785f  mov     rcx, [rbp+57h+var_D0]; string
0x180017863  call    cs:__imp_WindowsDeleteString
0x180017869  mov     [rbp+57h+var_D0], r12
0x18001786d  mov     rcx, [rsp+120h+var_D8]
0x180017872  test    rcx, rcx
0x180017875  jz      short loc_180017889
0x180017877  mov     [rsp+120h+var_D8], r12
0x18001787c  mov     rax, [rcx]
0x18001787f  mov     rax, [rax+10h]
0x180017883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017888  nop
0x180017889  mov     rcx, [rbp+57h+var_30]
0x18001788d  xor     rcx, rsp; StackCookie
0x180017890  call    __security_check_cookie
0x180017895  lea     r11, [rsp+120h+var_20]
0x18001789d  mov     rbx, [r11+38h]
0x1800178a1  mov     rsi, [r11+40h]
0x1800178a5  mov     rsp, r11
0x1800178a8  pop     r15
0x1800178aa  pop     r14
0x1800178ac  pop     r12
0x1800178ae  pop     rdi
0x1800178af  pop     rbp
0x1800178b0  retn
```
