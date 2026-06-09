# HcfDetector::PublishStatus(void)

- ea: `0x180021894`
- end: `0x180021bc7`
- name: `?PublishStatus@HcfDetector@@CAXXZ`
- size: `819`
- prototype: `void(void)`
- caller_count: `5`
- callee_count: `13`
- tags: `authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x180020724`
- `0x180020b74`
- `0x180020ed0`
- `0x1800226e0`
- `0x180022710`

## callees

- `0x180004ca0`
- `0x18000c478`
- `0x180012444`
- `0x180014428`
- `0x180018778`
- `0x1800189b8`
- `0x18001f328`
- `0x18001fbe8`
- `0x1800205f4`
- `0x180021290`
- `0x180021894`
- `0x180022848`
- `0x180089010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021b96`
- `api-ms-win-crt-private-l1-1-0!_o_abort` at `0x180021b96`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021941`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180021941`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b57`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180021b57`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800218d8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800218d8`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021988`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x180021988`

## string_xrefs

- `0x180021bb4`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800218f7`: `"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp"`
- `0x180021b0e`: `"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp"`
- `0x180021ba0`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\detecthcf.cpp`
- `0x1800218eb`: `[WSAIFabricHost][HcfDetection] CoCreateInstance for IUnknown. clsid=%s result=0x%08X`
- `0x180021b02`: `[WSAIFabricHost][HcfDetection] No installed HCF package found for current user.`
- `0x1800219ec`: `MicrosoftCorporationII.HybridComputeFramework_8wekyb3d8bbwe`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void HcfDetector::PublishStatus(void)
{
  HRESULT v0; // ebx
  unsigned int v1; // eax
  int v2; // eax
  const char *v3; // r9
  __int64 v4; // rcx
  __int128 *v5; // rcx
  __int64 v6; // rax
  const wchar_t *v7; // r9
  LPVOID *ppvb; // [rsp+20h] [rbp-D8h]
  unsigned int ppv; // [rsp+20h] [rbp-D8h]
  int ppva; // [rsp+20h] [rbp-D8h]
  __int64 Data; // [rsp+50h] [rbp-A8h] BYREF
  __int64 v12; // [rsp+58h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+60h] [rbp-98h] BYREF
  __int64 v14; // [rsp+68h] [rbp-90h] BYREF
  LPVOID v15; // [rsp+70h] [rbp-88h] BYREF
  _BYTE v16[8]; // [rsp+78h] [rbp-80h] BYREF
  _DWORD *v17; // [rsp+80h] [rbp-78h] BYREF
  _DWORD v18[4]; // [rsp+88h] [rbp-70h] BYREF
  const wchar_t *v19; // [rsp+98h] [rbp-60h]
  _DWORD *v20; // [rsp+A0h] [rbp-58h] BYREF
  _DWORD v21[4]; // [rsp+A8h] [rbp-50h] BYREF
  __int128 *v22; // [rsp+B8h] [rbp-40h]
  __int64 *v23; // [rsp+C0h] [rbp-38h]
  __int128 v24; // [rsp+C8h] [rbp-30h] BYREF
  __int128 v25; // [rsp+D8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+0h]

  v15 = 0;
  v0 = CoCreateInstance(&rclsid, 0, 4u, &GUID_00000000_0000_0000_c000_000000000046, &v15);
  LODWORD(ppvb) = v0;
  SearchIndexerTrace::Information(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\aifabrichosthelper\\\\lib\\\\detecthcf.cpp\"",
    (const wchar_t *)0x1C5,
    (unsigned int)L"[WSAIFabricHost][HcfDetection] CoCreateInstance for IUnknown. clsid=%s result=0x%08X",
    L"9D0C2974-9ED9-420F-9EB8-CCE41E387DCF",
    ppvb);
  hKey = 0;
  v1 = RegCreateKeyExW(
         HKEY_LOCAL_MACHINE,
         L"SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\WorkloadManager\\HCF\\Status",
         0,
         0,
         1u,
         0xF003Fu,
         0,
         &hKey,
         0);
  try
  {
    if ( v1 )
      wil::details::in1diag3::Throw_Win32(
        retaddr,
        (void *)0x1D1,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp",
        (const char *)v1,
        ppv);
    LODWORD(Data) = v0 >= 0;
    v2 = RegSetKeyValueW(hKey, 0, L"IsHcfPresent", 4u, &Data, 4u);
    if ( v2 > 0 )
      v2 = (unsigned __int16)v2 | 0x80070000;
    if ( v2 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x1CBE,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
        (const char *)(unsigned int)v2,
        ppva);
    if ( v0 >= 0 )
      goto LABEL_25;
    winrt::Windows::Management::Deployment::PackageManager::PackageManager((winrt::Windows::Management::Deployment::PackageManager *)&Data);
    v24 = 0;
    v25 = 0;
    std::wstring::_Construct<1,wchar_t const *>(&v24, &pszText);
    v4 = -1;
    do
      ++v4;
    while ( S2[v4] );
    if ( (_DWORD)v4 )
    {
      if ( S2[(unsigned int)v4] )
        goto LABEL_29;
      v18[0] = 1;
      v18[1] = v4;
      v19 = L"MicrosoftCorporationII.HybridComputeFramework_8wekyb3d8bbwe";
      v17 = v18;
    }
    else
    {
      v17 = 0;
    }
    v5 = &v24;
    if ( *((_QWORD *)&v25 + 1) > 7u )
      v5 = (__int128 *)v24;
    if ( !(_DWORD)v25 )
    {
      v20 = 0;
LABEL_19:
      winrt::impl::consume_Windows_Management_Deployment_IPackageManager<winrt::Windows::Management::Deployment::IPackageManager>::FindPackagesForUser(
        &Data,
        &v12,
        &v20,
        &v17);
      v23 = &v14;
      v14 = 0;
      v6 = winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::begin(
             &v12,
             v16);
      if ( !(unsigned __int8)std::any_of<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,_lambda_95e294c63c3cd6b2f52a1c8a20841356_>(
                               v6,
                               &v14,
                               &Data) )
        SearchIndexerTrace::Information(
          (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\search\\\\common\\\\aifabrichosthelper\\\\lib\\\\detecthcf.cpp\"",
          (const wchar_t *)0x1EC,
          (unsigned int)L"[WSAIFabricHost][HcfDetection] No installed HCF package found for current user.",
          v7);
      if ( v12 )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&v12);
      std::wstring::~wstring(&v24);
      if ( Data )
        winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(&Data);
LABEL_25:
      if ( hKey )
        RegCloseKey(hKey);
      if ( v15 )
        (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v15 + 16LL))(v15);
      return;
    }
    if ( !*((_WORD *)v5 + (unsigned int)v25) )
    {
      v21[0] = 1;
      v21[1] = v25;
      v22 = v5;
      v20 = v21;
      goto LABEL_19;
    }
LABEL_29:
    abort();
  }
  catch ( ... )
  {
    wil::details::in1diag3::Log_CaughtException(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\detecthcf.cpp",
      v3);
  }
}

```

## disassembly

```asm
0x180021894  mov     [rsp+arg_0], rbx
0x180021899  push    rdi
0x18002189a  sub     rsp, 0F0h
0x1800218a1  mov     rax, cs:__security_cookie
0x1800218a8  xor     rax, rsp
0x1800218ab  mov     [rsp+0F8h+var_10], rax
0x1800218b3  xor     edi, edi
0x1800218b5  mov     [rsp+0F8h+var_88], rdi
0x1800218ba  lea     rax, [rsp+0F8h+var_88]
0x1800218bf  mov     [rsp+0F8h+ppv], rax; ppv
0x1800218c4  lea     r9, _GUID_00000000_0000_0000_c000_000000000046; riid
0x1800218cb  xor     edx, edx; pUnkOuter
0x1800218cd  lea     r8d, [rdi+4]; dwClsContext
0x1800218d1  lea     rcx, rclsid; rclsid
0x1800218d8  call    cs:__imp_CoCreateInstance
0x1800218de  mov     ebx, eax
0x1800218e0  mov     dword ptr [rsp+0F8h+ppv], eax
0x1800218e4  lea     r9, a9d0c29749ed942; "9D0C2974-9ED9-420F-9EB8-CCE41E387DCF"
0x1800218eb  lea     r8, aWsaifabrichost_10; "[WSAIFabricHost][HcfDetection] CoCreate"...
0x1800218f2  mov     edx, 1C5h; wchar_t *
0x1800218f7  lea     rcx, aOnecoreuapBase_8; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x1800218fe  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180021903  nop
0x180021904  mov     [rsp+0F8h+hKey], rdi
0x180021909  mov     [rsp+0F8h+lpdwDisposition], rdi; lpdwDisposition
0x18002190e  lea     rax, [rsp+0F8h+hKey]
0x180021913  mov     [rsp+0F8h+phkResult], rax; phkResult
0x180021918  mov     [rsp+0F8h+lpSecurityAttributes], rdi; lpSecurityAttributes
0x18002191d  mov     [rsp+0F8h+samDesired], 0F003Fh; samDesired
0x180021925  mov     dword ptr [rsp+0F8h+ppv], 1; unsigned int
0x18002192d  xor     r9d, r9d; lpClass
0x180021930  xor     r8d, r8d; Reserved
0x180021933  lea     rdx, aSoftwareMicros_5; "SOFTWARE\\Microsoft\\Windows NT\\Curren"...
0x18002193a  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180021941  call    cs:__imp_RegCreateKeyExW
0x180021947  mov     rcx, [rsp+0F8h]; this
0x18002194f  test    eax, eax
0x180021951  jnz     loc_180021B9D
0x180021957  mov     eax, ebx
0x180021959  not     eax
0x18002195b  shr     eax, 1Fh
0x18002195e  mov     dword ptr [rsp+0F8h+Data], eax
0x180021962  mov     [rsp+0F8h+samDesired], 4; cbData
0x18002196a  lea     rax, [rsp+0F8h+Data]
0x18002196f  mov     [rsp+0F8h+ppv], rax; int
0x180021974  mov     r9d, 4; dwType
0x18002197a  lea     r8, ValueName; "IsHcfPresent"
0x180021981  xor     edx, edx; lpSubKey
0x180021983  mov     rcx, [rsp+0F8h+hKey]; hKey
0x180021988  call    cs:__imp_RegSetKeyValueW
0x18002198e  test    eax, eax
0x180021990  jle     short loc_18002199A
0x180021992  movzx   eax, ax
0x180021995  or      eax, 80070000h
0x18002199a  mov     rcx, [rsp+0F8h]; this
0x1800219a2  test    eax, eax
0x1800219a4  js      loc_180021BB1
0x1800219aa  test    ebx, ebx
0x1800219ac  jns     loc_180021B4D
0x1800219b2  lea     rcx, [rsp+0F8h+Data]; this
0x1800219b7  call    ??0PackageManager@Deployment@Management@Windows@winrt@@QEAA@XZ; winrt::Windows::Management::Deployment::PackageManager::PackageManager(void)
0x1800219bc  nop
0x1800219bd  xorps   xmm0, xmm0
0x1800219c0  movups  [rsp+0F8h+var_30], xmm0
0x1800219c8  xorps   xmm1, xmm1
0x1800219cb  movdqu  [rsp+0F8h+var_20], xmm1
0x1800219d4  xor     r8d, r8d
0x1800219d7  lea     rdx, pszText
0x1800219de  lea     rcx, [rsp+0F8h+var_30]
0x1800219e6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1800219eb  nop
0x1800219ec  lea     rdx, S2; "MicrosoftCorporationII.HybridComputeFra"...
0x1800219f3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x1800219f7  inc     rcx
0x1800219fa  cmp     [rdx+rcx*2], di
0x1800219fe  jnz     short loc_1800219F7
0x180021a00  test    ecx, ecx
0x180021a02  jnz     short loc_180021A0E
0x180021a04  mov     [rsp+0F8h+var_78], rdi
0x180021a0c  jmp     short loc_180021A44
0x180021a0e  mov     eax, ecx
0x180021a10  cmp     [rdx+rax*2], di
0x180021a14  jnz     loc_180021B96
0x180021a1a  mov     [rsp+0F8h+var_70], 1
0x180021a25  mov     [rsp+0F8h+var_6C], ecx
0x180021a2c  mov     [rsp+0F8h+var_60], rdx
0x180021a34  lea     rax, [rsp+0F8h+var_70]
0x180021a3c  mov     [rsp+0F8h+var_78], rax
0x180021a44  mov     rdx, qword ptr [rsp+0F8h+var_20]
0x180021a4c  lea     rcx, [rsp+0F8h+var_30]
0x180021a54  cmp     qword ptr [rsp+0F8h+var_20+8], 7
0x180021a5d  cmova   rcx, qword ptr [rsp+0F8h+var_30]
0x180021a66  test    edx, edx
0x180021a68  jnz     short loc_180021A74
0x180021a6a  mov     [rsp+0F8h+var_58], rdi
0x180021a72  jmp     short loc_180021AAA
0x180021a74  mov     eax, edx
0x180021a76  cmp     [rcx+rax*2], di
0x180021a7a  jnz     loc_180021B96
0x180021a80  mov     [rsp+0F8h+var_50], 1
0x180021a8b  mov     [rsp+0F8h+var_4C], edx
0x180021a92  mov     [rsp+0F8h+var_40], rcx
0x180021a9a  lea     rax, [rsp+0F8h+var_50]
0x180021aa2  mov     [rsp+0F8h+var_58], rax
0x180021aaa  lea     r9, [rsp+0F8h+var_78]
0x180021ab2  lea     r8, [rsp+0F8h+var_58]
0x180021aba  lea     rdx, [rsp+0F8h+var_A0]
0x180021abf  lea     rcx, [rsp+0F8h+Data]
0x180021ac4  call    ?FindPackagesForUser@?$consume_Windows_Management_Deployment_IPackageManager@UIPackageManager@Deployment@Management@Windows@winrt@@@impl@winrt@@QEBA@AEBUhstring@param@3@0@Z; winrt::impl::consume_Windows_Management_Deployment_IPackageManager<winrt::Windows::Management::Deployment::IPackageManager>::FindPackagesForUser(winrt::param::hstring const &,winrt::param::hstring const &)
0x180021ac9  nop
0x180021aca  lea     rax, [rsp+0F8h+var_90]
0x180021acf  mov     [rsp+0F8h+var_38], rax
0x180021ad7  mov     [rsp+0F8h+var_90], rdi
0x180021adc  lea     rdx, [rsp+0F8h+var_80]
0x180021ae1  lea     rcx, [rsp+0F8h+var_A0]
0x180021ae6  call    ?begin@?$consume_Windows_Foundation_Collections_IIterable@U?$IIterable@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@UPackage@ApplicationModel@45@@impl@winrt@@QEBA@XZ; winrt::impl::consume_Windows_Foundation_Collections_IIterable<winrt::Windows::Foundation::Collections::IIterable<winrt::Windows::ApplicationModel::Package>,winrt::Windows::ApplicationModel::Package>::begin(void)
0x180021aeb  nop
0x180021aec  lea     r8, [rsp+0F8h+Data]
0x180021af1  lea     rdx, [rsp+0F8h+var_90]
0x180021af6  mov     rcx, rax
0x180021af9  call    ??$any_of@U?$IIterator@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@V_lambda_95e294c63c3cd6b2f52a1c8a20841356_@@@std@@YA_NU?$IIterator@UPackage@ApplicationModel@Windows@winrt@@@Collections@Foundation@Windows@winrt@@0V_lambda_95e294c63c3cd6b2f52a1c8a20841356_@@@Z; std::any_of<winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,_lambda_95e294c63c3cd6b2f52a1c8a20841356_>(winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,winrt::Windows::Foundation::Collections::IIterator<winrt::Windows::ApplicationModel::Package>,_lambda_95e294c63c3cd6b2f52a1c8a20841356_)
0x180021afe  test    al, al
0x180021b00  jnz     short loc_180021B1B
0x180021b02  lea     r8, aWsaifabrichost_3; "[WSAIFabricHost][HcfDetection] No insta"...
0x180021b09  mov     edx, 1ECh; wchar_t *
0x180021b0e  lea     rcx, aOnecoreuapBase_8; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x180021b15  call    ?Information@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Information(wchar_t const *,uint,wchar_t const *,...)
0x180021b1a  nop
0x180021b1b  cmp     [rsp+0F8h+var_A0], rdi
0x180021b20  jz      short loc_180021B2D
0x180021b22  lea     rcx, [rsp+0F8h+var_A0]
0x180021b27  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180021b2c  nop
0x180021b2d  lea     rcx, [rsp+0F8h+var_30]
0x180021b35  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180021b3a  nop
0x180021b3b  cmp     [rsp+0F8h+Data], rdi
0x180021b40  jz      short loc_180021B4D
0x180021b42  lea     rcx, [rsp+0F8h+Data]
0x180021b47  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x180021b4c  nop
0x180021b4d  mov     rcx, [rsp+0F8h+hKey]; hKey
0x180021b52  test    rcx, rcx
0x180021b55  jz      short loc_180021B5E
0x180021b57  call    cs:__imp_RegCloseKey
0x180021b5d  nop
0x180021b5e  mov     rcx, [rsp+0F8h+var_88]
0x180021b63  test    rcx, rcx
0x180021b66  jz      short loc_180021B75
0x180021b68  mov     rax, [rcx]
0x180021b6b  mov     rax, [rax+10h]
0x180021b6f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021b74  nop
0x180021b75  mov     rcx, [rsp+0F8h+var_10]
0x180021b7d  xor     rcx, rsp; StackCookie
0x180021b80  call    __security_check_cookie
0x180021b85  mov     rbx, [rsp+0F8h+arg_0]
0x180021b8d  add     rsp, 0F0h
0x180021b94  pop     rdi
0x180021b95  retn
0x180021b96  call    cs:__imp_abort
0x180021b9d  mov     r9d, eax; char *
0x180021ba0  lea     r8, aOnecoreuapBase; "onecoreuap\\base\\appmodel\\search\\com"...
0x180021ba7  mov     edx, 1D1h; void *
0x180021bac  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x180021bb1  mov     r9d, eax; char *
0x180021bb4  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180021bbb  mov     edx, 1CBEh; void *
0x180021bc0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
