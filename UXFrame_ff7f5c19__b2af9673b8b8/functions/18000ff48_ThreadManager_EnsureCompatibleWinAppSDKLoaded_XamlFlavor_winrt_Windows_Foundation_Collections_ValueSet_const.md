# ThreadManager::EnsureCompatibleWinAppSDKLoaded(XamlFlavor,winrt::Windows::Foundation::Collections::ValueSet const &)

- ea: `0x18000ff48`
- end: `0x180010133`
- name: `?EnsureCompatibleWinAppSDKLoaded@ThreadManager@@QEAA_NW4XamlFlavor@@AEBUValueSet@Collections@Foundation@Windows@winrt@@@Z`
- size: `491`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18004488c`

## callees

- `0x180002b20`
- `0x1800043f4`
- `0x18000959c`
- `0x18000ab8c`
- `0x18000d810`
- `0x18000ecac`
- `0x18000f200`
- `0x18000ff48`
- `0x180013708`
- `0x180017024`
- `0x180017290`
- `0x180017514`

## import_xrefs

- `api-ms-win-appmodel-runtime-internal-l1-1-7!AddDependencyToProcessPackageGraph` at `0x1800100d7`
- `api-ms-win-appmodel-runtime-internal-l1-1-7!AddDependencyToProcessPackageGraph` at `0x1800100d7`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001005d`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x18001005d`

## string_xrefs

- `0x180010121`: `pcshell\shell\uxframe\dll\ThreadManager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
char __fastcall ThreadManager::EnsureCompatibleWinAppSDKLoaded(_DWORD *a1, int a2)
{
  const wchar_t *v4; // rax
  __int64 v5; // r9
  const WCHAR *v6; // rax
  __int64 v7; // rdx
  const WCHAR *v8; // r8
  int v9; // r9d
  int v10; // eax
  char v11; // al
  const wchar_t *v12; // rax
  int v13; // eax
  BOOL bIgnoreCase; // [rsp+20h] [rbp-40h]
  const wchar_t *v15; // [rsp+30h] [rbp-30h] BYREF
  _QWORD v16[2]; // [rsp+38h] [rbp-28h] BYREF
  int v17; // [rsp+48h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+18h]

  if ( *a1 && *a1 != a2 )
  {
    UXFrameTelemetry::IncompatibleXamlFlavorForProcess();
    return 0;
  }
  *a1 = a2;
  if ( a2 == 2 )
  {
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::GetImpl'::`2'::impl) )
    {
      if ( !byte_180072B80 )
      {
        v17 = 4;
        winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::AddKnownPackageToProcessPackageGraph((const enum winrt::WindowsUdk::ApplicationModel::AppExtensions::KnownPackage *)&v17);
        byte_180072B80 = 1;
      }
    }
    else
    {
      v16[1] = v16;
      winrt::hstring::hstring((winrt::hstring *)v16, L"Microsoft.WindowsAppRuntime.CBS.1.6_8wekyb3d8bbwe");
      winrt::hstring::hstring((winrt::hstring *)&v15, L"TargetWASDKPackageName");
      ValueSetUtils::get_value_or<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>((winrt::hstring *)&v17);
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v15);
      if ( !*((_QWORD *)a1 + 1) )
        goto LABEL_22;
      v4 = winrt::hstring::c_str((winrt::hstring *)(a1 + 2));
      v5 = -1;
      do
        ++v5;
      while ( v4[v5] );
      v6 = winrt::hstring::c_str((winrt::hstring *)&v17);
      do
        ++v7;
      while ( v6[v7] );
      v10 = CompareStringOrdinal(v6, v7, v8, v9, 1);
      if ( v10 == 1 )
      {
        v11 = wistd::weak_ordering::less;
      }
      else if ( v10 == 3 )
      {
        v11 = wistd::weak_ordering::greater;
      }
      else
      {
        v11 = wistd::weak_ordering::equivalent;
      }
      if ( v11 )
      {
        v16[0] = winrt::hstring::c_str((winrt::hstring *)&v17);
        v15 = winrt::hstring::c_str((winrt::hstring *)(a1 + 2));
        UXFrameTelemetry::IncompatibleXamlVersionForProcess<wchar_t const *,wchar_t const *>(&v15, v16);
        winrt::handle_type<winrt::impl::hstring_traits>::close(&v17);
        return 0;
      }
      if ( !*((_QWORD *)a1 + 1) )
      {
LABEL_22:
        v12 = winrt::hstring::c_str((winrt::hstring *)&v17);
        v13 = AddDependencyToProcessPackageGraph(v12, 0, 0, 0);
        if ( v13 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0x55,
            (unsigned int)"pcshell\\shell\\uxframe\\dll\\ThreadManager.cpp",
            (const char *)(unsigned int)v13,
            bIgnoreCase);
        winrt::hstring::operator=(a1 + 2, &v17);
      }
      winrt::handle_type<winrt::impl::hstring_traits>::close(&v17);
    }
  }
  return 1;
}

```

## disassembly

```asm
0x18000ff48  mov     [rsp-18h+arg_8], rbx
0x18000ff4d  mov     [rsp-18h+arg_18], rsi
0x18000ff52  push    rbp
0x18000ff53  push    rdi
0x18000ff54  push    r14
0x18000ff56  mov     rbp, rsp
0x18000ff59  sub     rsp, 60h
0x18000ff5d  mov     rax, cs:__security_cookie
0x18000ff64  xor     rax, rsp
0x18000ff67  mov     [rbp+var_10], rax
0x18000ff6b  mov     rsi, r8
0x18000ff6e  mov     rdi, rcx
0x18000ff71  xor     r14d, r14d
0x18000ff74  cmp     [rcx], r14d
0x18000ff77  jz      short loc_18000FF89
0x18000ff79  cmp     [rcx], edx
0x18000ff7b  jz      short loc_18000FF89
0x18000ff7d  call    ?IncompatibleXamlFlavorForProcess@UXFrameTelemetry@@SAXXZ; UXFrameTelemetry::IncompatibleXamlFlavorForProcess(void)
0x18000ff82  xor     al, al
0x18000ff84  jmp     loc_1800100FD
0x18000ff89  mov     [rcx], edx
0x18000ff8b  cmp     edx, 2
0x18000ff8e  jnz     loc_1800100FB
0x18000ff94  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion> `wil::Feature<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::GetImpl(void)'::`2'::impl
0x18000ff9b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UseCentralWindowsAppRuntimeVersion>::__private_IsEnabled(void)
0x18000ffa0  test    al, al
0x18000ffa2  jz      short loc_18000FFCD
0x18000ffa4  cmp     cs:byte_180072B80, r14b
0x18000ffab  jnz     loc_1800100FB
0x18000ffb1  mov     [rbp+var_18], 4
0x18000ffb8  lea     rcx, [rbp+var_18]; enum winrt::WindowsUdk::ApplicationModel::AppExtensions::KnownPackage *
0x18000ffbc  call    ?AddKnownPackageToProcessPackageGraph@AppExtension@AppExtensions@ApplicationModel@WindowsUdk@winrt@@SA@AEBW4KnownPackage@2345@@Z; winrt::WindowsUdk::ApplicationModel::AppExtensions::AppExtension::AddKnownPackageToProcessPackageGraph(winrt::WindowsUdk::ApplicationModel::AppExtensions::KnownPackage const &)
0x18000ffc1  mov     cs:byte_180072B80, 1
0x18000ffc8  jmp     loc_1800100FB
0x18000ffcd  lea     rax, [rbp+var_28]
0x18000ffd1  mov     [rbp+var_20], rax
0x18000ffd5  lea     rdx, aMicrosoftWindo; "Microsoft.WindowsAppRuntime.CBS.1.6_8we"...
0x18000ffdc  lea     rcx, [rbp+var_28]; this
0x18000ffe0  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18000ffe5  mov     rbx, rax
0x18000ffe8  lea     rdx, aTargetwasdkpac; "TargetWASDKPackageName"
0x18000ffef  lea     rcx, [rbp+var_30]; this
0x18000fff3  call    ??0hstring@winrt@@QEAA@PEB_W@Z; winrt::hstring::hstring(wchar_t const *)
0x18000fff8  nop
0x18000fff9  mov     r9, rbx
0x18000fffc  mov     r8, rsi
0x18000ffff  lea     rdx, [rbp+var_30]
0x180010003  lea     rcx, [rbp+var_18]; this
0x180010007  call    ??$get_value_or@Uhstring@winrt@@UValueSet@Collections@Foundation@Windows@2@@ValueSetUtils@@YA?AUhstring@winrt@@AEBU12@AEBUValueSet@Collections@Foundation@Windows@2@U12@@Z; ValueSetUtils::get_value_or<winrt::hstring,winrt::Windows::Foundation::Collections::ValueSet>(winrt::hstring const &,winrt::Windows::Foundation::Collections::ValueSet const &,winrt::hstring)
0x18001000c  nop
0x18001000d  lea     rcx, [rbp+var_30]
0x180010011  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x180010016  lea     rbx, [rdi+8]
0x18001001a  cmp     [rbx], r14
0x18001001d  jz      loc_1800100C3
0x180010023  mov     rcx, rbx; this
0x180010026  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18001002b  mov     r8, rax
0x18001002e  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180010032  mov     r9, rdx
0x180010035  inc     r9
0x180010038  cmp     [rax+r9*2], r14w
0x18001003d  jnz     short loc_180010035
0x18001003f  lea     rcx, [rbp+var_18]; this
0x180010043  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180010048  inc     rdx; cchCount1
0x18001004b  cmp     [rax+rdx*2], r14w
0x180010050  jnz     short loc_180010048
0x180010052  mov     [rsp+60h+bIgnoreCase], 1; int
0x18001005a  mov     rcx, rax; lpString1
0x18001005d  call    cs:__imp_CompareStringOrdinal
0x180010063  mov     ecx, eax
0x180010065  sub     ecx, 1
0x180010068  jz      short loc_18001007F
0x18001006a  cmp     ecx, 2
0x18001006d  jz      short loc_180010077
0x18001006f  mov     al, cs:?equivalent@weak_ordering@wistd@@2U12@B; wistd::weak_ordering const wistd::weak_ordering::equivalent
0x180010075  jmp     short loc_180010085
0x180010077  mov     al, cs:?greater@weak_ordering@wistd@@2U12@B; wistd::weak_ordering const wistd::weak_ordering::greater
0x18001007d  jmp     short loc_180010085
0x18001007f  mov     al, cs:?less@weak_ordering@wistd@@2U12@B; wistd::weak_ordering const wistd::weak_ordering::less
0x180010085  test    al, al
0x180010087  jz      short loc_1800100BE
0x180010089  lea     rcx, [rbp+var_18]; this
0x18001008d  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x180010092  mov     [rbp+var_28], rax
0x180010096  mov     rcx, rbx; this
0x180010099  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x18001009e  mov     [rbp+var_30], rax
0x1800100a2  lea     rdx, [rbp+var_28]
0x1800100a6  lea     rcx, [rbp+var_30]
0x1800100aa  call    ??$IncompatibleXamlVersionForProcess@PEB_WPEB_W@UXFrameTelemetry@@SAX$$QEAPEB_W0@Z; UXFrameTelemetry::IncompatibleXamlVersionForProcess<wchar_t const *,wchar_t const *>(wchar_t const * &&,wchar_t const * &&)
0x1800100af  nop
0x1800100b0  lea     rcx, [rbp+var_18]
0x1800100b4  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800100b9  jmp     loc_18000FF82
0x1800100be  cmp     [rbx], r14
0x1800100c1  jnz     short loc_1800100F2
0x1800100c3  lea     rcx, [rbp+var_18]; this
0x1800100c7  call    ?c_str@hstring@winrt@@QEBAPEB_WXZ; winrt::hstring::c_str(void)
0x1800100cc  mov     rcx, rax
0x1800100cf  xor     r9d, r9d
0x1800100d2  xor     r8d, r8d
0x1800100d5  xor     edx, edx
0x1800100d7  call    cs:__imp_AddDependencyToProcessPackageGraph
0x1800100dd  mov     rcx, [rbp+18h]; this
0x1800100e1  test    eax, eax
0x1800100e3  js      short loc_18001011E
0x1800100e5  lea     rdx, [rbp+var_18]
0x1800100e9  mov     rcx, rbx
0x1800100ec  call    ??4hstring@winrt@@QEAAAEAU01@AEBU01@@Z; winrt::hstring::operator=(winrt::hstring const &)
0x1800100f1  nop
0x1800100f2  lea     rcx, [rbp+var_18]
0x1800100f6  call    ?close@?$handle_type@Uhstring_traits@impl@winrt@@@winrt@@QEAAXXZ; winrt::handle_type<winrt::impl::hstring_traits>::close(void)
0x1800100fb  mov     al, 1
0x1800100fd  mov     rcx, [rbp+var_10]
0x180010101  xor     rcx, rsp; StackCookie
0x180010104  call    __security_check_cookie
0x180010109  lea     r11, [rsp+60h+var_s0]
0x18001010e  mov     rbx, [r11+28h]
0x180010112  mov     rsi, [r11+38h]
0x180010116  mov     rsp, r11
0x180010119  pop     r14
0x18001011b  pop     rdi
0x18001011c  pop     rbp
0x18001011d  retn
0x18001011e  mov     r9d, eax; char *
0x180010121  lea     r8, aPcshellShellUx_11; "pcshell\\shell\\uxframe\\dll\\ThreadMan"...
0x180010128  mov     edx, 55h ; 'U'; void *
0x18001012d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
