# SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::InsertPackage(SystemSettings::BatteryUsageHandlers::IPackageInfo *)

- ea: `0x180043f80`
- end: `0x180044303`
- name: `?InsertPackage@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@AEAAJPEAUIPackageInfo@23@@Z`
- size: `899`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *__hidden this, struct SystemSettings::BatteryUsageHandlers::IPackageInfo *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ea14`

## callees

- `0x1800028d0`
- `0x180004cfc`
- `0x18000a13c`
- `0x18000f9a0`
- `0x180013c70`
- `0x18001e360`
- `0x18001e5c8`
- `0x180023c78`
- `0x180025db0`
- `0x18002b900`
- `0x18003b77c`
- `0x18003d7ec`
- `0x180042b88`
- `0x180043258`
- `0x180043f80`
- `0x18004719c`
- `0x1800512e0`
- `0x180055cf4`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800440c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800441d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800442b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044006`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800440c7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044115`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800441d9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800442b6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004407f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180044146`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004407f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180044146`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::InsertPackage(
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton2 *this,
        struct SystemSettings::BatteryUsageHandlers::IPackageInfo *a2)
{
  __int64 (__fastcall *v5)(struct SystemSettings::BatteryUsageHandlers::IPackageInfo *, HSTRING *); // rbx
  int v6; // eax
  unsigned int v7; // ebx
  const wchar_t *StringRawBuffer; // rbx
  __int64 (__fastcall *v9)(struct SystemSettings::BatteryUsageHandlers::IPackageInfo *, HSTRING *); // rbx
  int v10; // eax
  unsigned int v11; // ebx
  PCWSTR v12; // rax
  __int64 v13; // r8
  __int64 v14; // rdx
  __int64 v15; // r8
  __int64 PackageFamilyNameFromPackageFullName; // rax
  __int64 v17; // rdx
  __int64 v18; // r8
  __int64 v19; // rax
  int PackageFromFamilyName; // ebx
  __int64 PackageDisplayName; // rax
  __int64 v22; // rax
  __int64 *v23; // rax
  __int64 v24; // rdi
  __int64 v25; // rbx
  HSTRING string; // [rsp+20h] [rbp-98h] BYREF
  UINT32 length; // [rsp+28h] [rbp-90h] BYREF
  __int64 v28; // [rsp+30h] [rbp-88h] BYREF
  struct SystemSettings::BatteryUsageHandlers::IPackageInfo *v29; // [rsp+38h] [rbp-80h] BYREF
  _BYTE v30[16]; // [rsp+40h] [rbp-78h] BYREF
  _OWORD v31[2]; // [rsp+50h] [rbp-68h] BYREF
  _BYTE v32[40]; // [rsp+70h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v28 = 0;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE5,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)0x80004005LL,
      (int)string);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    return 2147500037LL;
  }
  v29 = a2;
  Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(&v29);
  string = 0;
  v5 = *(__int64 (__fastcall **)(struct SystemSettings::BatteryUsageHandlers::IPackageInfo *, HSTRING *))(*(_QWORD *)a2 + 72LL);
  WindowsDeleteString(0);
  string = 0;
  v6 = v5(a2, &string);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE9,
      (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
      (const char *)(unsigned int)v6,
      (int)string);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    return v7;
  }
  length = 0;
  StringRawBuffer = WindowsGetStringRawBuffer(string, &length);
  v31[0] = 0;
  v31[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v31[0]) = 0;
  if ( !wcscmp_0(StringRawBuffer, L"Inbox") )
  {
    v9 = *(__int64 (__fastcall **)(struct SystemSettings::BatteryUsageHandlers::IPackageInfo *, HSTRING *))(*(_QWORD *)a2 + 48LL);
    WindowsDeleteString(string);
    string = 0;
    v10 = v9(a2, &string);
    v11 = v10;
    if ( v10 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF1,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)v10,
        (int)string);
      std::wstring::_Tidy_deallocate(v31);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      return v11;
    }
    v12 = WindowsGetStringRawBuffer(string, &length);
    v13 = -1;
    do
      ++v13;
    while ( v12[v13] );
    std::wstring::_Assign<unsigned short>(v31, v12);
  }
  else
  {
    Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
    PackageFamilyNameFromPackageFullName = SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(
                                             v32,
                                             StringRawBuffer);
    v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(PackageFamilyNameFromPackageFullName, v17, v18);
    PackageFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFromFamilyName(
                              this,
                              v19,
                              &v28);
    std::wstring::_Tidy_deallocate(v32);
    if ( PackageFromFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAF8,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\batteryusage\\lib\\usagedatasingleton.cpp",
        (const char *)(unsigned int)PackageFromFamilyName,
        (int)string);
      std::wstring::_Tidy_deallocate(v31);
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
      return (unsigned int)PackageFromFamilyName;
    }
    PackageDisplayName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageDisplayName(
                           this,
                           v32,
                           v28);
    std::wstring::operator=(v31, PackageDisplayName);
    std::wstring::_Tidy_deallocate(v32);
  }
  v22 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v31, v14, v15);
  std::wstring::wstring((__int64)v32, v22);
  v23 = (__int64 *)std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(
                     (char *)this + 272,
                     v30,
                     v32);
  v24 = *((_QWORD *)this + 34);
  v25 = *v23;
  std::wstring::_Tidy_deallocate(v32);
  if ( v25 == v24 )
  {
    std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>(
      (__int64)v32,
      (__int64)v31,
      &v29);
    std::_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>>,0>>::insert<0,0>(
      (__int64 *)this + 34,
      (__int64)v30,
      (__int64)v32);
    std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>((__int64)v32);
  }
  std::wstring::_Tidy_deallocate(v31);
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  return 0;
}

```

## disassembly

```asm
0x180043f80  mov     [rsp+arg_10], rbx
0x180043f85  push    rsi
0x180043f86  push    rdi
0x180043f87  push    r14
0x180043f89  sub     rsp, 0A0h
0x180043f90  mov     rax, cs:__security_cookie
0x180043f97  xor     rax, rsp
0x180043f9a  mov     [rsp+0B8h+var_20], rax
0x180043fa2  mov     rdi, rdx
0x180043fa5  mov     rsi, rcx
0x180043fa8  xor     r14d, r14d
0x180043fab  mov     [rsp+0B8h+var_88], r14
0x180043fb0  test    rdx, rdx
0x180043fb3  jnz     short loc_180043FE8
0x180043fb5  mov     rcx, [rsp+0B8h]; this
0x180043fbd  mov     ebx, 80004005h
0x180043fc2  mov     r9d, ebx; char *
0x180043fc5  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180043fcc  mov     edx, 0AE5h; void *
0x180043fd1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043fd6  nop
0x180043fd7  lea     rcx, [rsp+0B8h+var_88]
0x180043fdc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180043fe1  mov     eax, ebx
0x180043fe3  jmp     loc_1800442DE
0x180043fe8  mov     [rsp+0B8h+var_80], rdi
0x180043fed  lea     rcx, [rsp+0B8h+var_80]
0x180043ff2  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180043ff7  nop
0x180043ff8  mov     [rsp+0B8h+string], r14
0x180043ffd  mov     rax, [rdi]
0x180044000  mov     rbx, [rax+48h]
0x180044004  xor     ecx, ecx; string
0x180044006  call    cs:__imp_WindowsDeleteString
0x18004400c  mov     [rsp+0B8h+string], r14; int
0x180044011  lea     rdx, [rsp+0B8h+string]
0x180044016  mov     rcx, rdi
0x180044019  mov     rax, rbx
0x18004401c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180044021  mov     ebx, eax
0x180044023  test    eax, eax
0x180044025  jns     short loc_180044070
0x180044027  mov     rcx, [rsp+0B8h]; this
0x18004402f  mov     r9d, eax; char *
0x180044032  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180044039  mov     edx, 0AE9h; void *
0x18004403e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044043  nop
0x180044044  mov     rcx, [rsp+0B8h+string]; string
0x180044049  call    cs:__imp_WindowsDeleteString
0x18004404f  mov     [rsp+0B8h+string], r14
0x180044054  lea     rcx, [rsp+0B8h+var_80]
0x180044059  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004405e  nop
0x18004405f  lea     rcx, [rsp+0B8h+var_88]
0x180044064  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044069  mov     eax, ebx
0x18004406b  jmp     loc_1800442DE
0x180044070  mov     [rsp+0B8h+length], r14d
0x180044075  lea     rdx, [rsp+0B8h+length]; length
0x18004407a  mov     rcx, [rsp+0B8h+string]; string
0x18004407f  call    cs:__imp_WindowsGetStringRawBuffer
0x180044085  mov     rbx, rax
0x180044088  xorps   xmm0, xmm0
0x18004408b  movups  [rsp+0B8h+var_68], xmm0
0x180044090  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180044098  movdqu  [rsp+0B8h+var_58], xmm1
0x18004409e  mov     word ptr [rsp+0B8h+var_68], r14w
0x1800440a4  lea     rdx, aInbox; "Inbox"
0x1800440ab  mov     rcx, rax; String1
0x1800440ae  call    wcscmp_0
0x1800440b3  test    eax, eax
0x1800440b5  jnz     loc_18004416C
0x1800440bb  mov     rax, [rdi]
0x1800440be  mov     rbx, [rax+30h]
0x1800440c2  mov     rcx, [rsp+0B8h+string]; string
0x1800440c7  call    cs:__imp_WindowsDeleteString
0x1800440cd  mov     [rsp+0B8h+string], r14; int
0x1800440d2  lea     rdx, [rsp+0B8h+string]
0x1800440d7  mov     rcx, rdi
0x1800440da  mov     rax, rbx
0x1800440dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800440e2  mov     ebx, eax
0x1800440e4  test    eax, eax
0x1800440e6  jns     short loc_18004413C
0x1800440e8  mov     rcx, [rsp+0B8h]; this
0x1800440f0  mov     r9d, eax; char *
0x1800440f3  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x1800440fa  mov     edx, 0AF1h; void *
0x1800440ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044104  nop
0x180044105  lea     rcx, [rsp+0B8h+var_68]
0x18004410a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004410f  nop
0x180044110  mov     rcx, [rsp+0B8h+string]; string
0x180044115  call    cs:__imp_WindowsDeleteString
0x18004411b  mov     [rsp+0B8h+string], r14
0x180044120  lea     rcx, [rsp+0B8h+var_80]
0x180044125  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004412a  nop
0x18004412b  lea     rcx, [rsp+0B8h+var_88]
0x180044130  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044135  mov     eax, ebx
0x180044137  jmp     loc_1800442DE
0x18004413c  lea     rdx, [rsp+0B8h+length]; length
0x180044141  mov     rcx, [rsp+0B8h+string]; string
0x180044146  call    cs:__imp_WindowsGetStringRawBuffer
0x18004414c  or      r8, 0FFFFFFFFFFFFFFFFh
0x180044150  inc     r8
0x180044153  cmp     [rax+r8*2], r14w
0x180044158  jnz     short loc_180044150
0x18004415a  mov     rdx, rax
0x18004415d  lea     rcx, [rsp+0B8h+var_68]
0x180044162  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x180044167  jmp     loc_180044229
0x18004416c  lea     rcx, [rsp+0B8h+var_88]
0x180044171  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044176  mov     rdx, rbx
0x180044179  lea     rcx, [rsp+0B8h+var_48]
0x18004417e  call    ?GetPackageFamilyNameFromPackageFullName@BatteryUsageHandlers@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(ushort const *)
0x180044183  nop
0x180044184  mov     rcx, rax
0x180044187  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004418c  lea     r8, [rsp+0B8h+var_88]
0x180044191  mov     rdx, rax
0x180044194  mov     rcx, rsi
0x180044197  call    ?GetPackageFromFamilyName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@QEAAJPEBGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)
0x18004419c  mov     ebx, eax
0x18004419e  lea     rcx, [rsp+0B8h+var_48]
0x1800441a3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800441a8  test    ebx, ebx
0x1800441aa  jns     short loc_180044200
0x1800441ac  mov     rcx, [rsp+0B8h]; this
0x1800441b4  mov     r9d, ebx; char *
0x1800441b7  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x1800441be  mov     edx, 0AF8h; void *
0x1800441c3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800441c8  nop
0x1800441c9  lea     rcx, [rsp+0B8h+var_68]
0x1800441ce  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800441d3  nop
0x1800441d4  mov     rcx, [rsp+0B8h+string]; string
0x1800441d9  call    cs:__imp_WindowsDeleteString
0x1800441df  mov     [rsp+0B8h+string], r14
0x1800441e4  lea     rcx, [rsp+0B8h+var_80]
0x1800441e9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800441ee  nop
0x1800441ef  lea     rcx, [rsp+0B8h+var_88]
0x1800441f4  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800441f9  mov     eax, ebx
0x1800441fb  jmp     loc_1800442DE
0x180044200  mov     r8, [rsp+0B8h+var_88]
0x180044205  lea     rdx, [rsp+0B8h+var_48]
0x18004420a  mov     rcx, rsi
0x18004420d  call    ?GetPackageDisplayName@UsageDataSingleton2@BatteryUsageHandlers@SystemSettings@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIPackage@StateRepository@Internal@Windows@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton2::GetPackageDisplayName(Windows::Internal::StateRepository::IPackage *)
0x180044212  mov     rdx, rax
0x180044215  lea     rcx, [rsp+0B8h+var_68]
0x18004421a  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18004421f  lea     rcx, [rsp+0B8h+var_48]
0x180044224  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044229  lea     rcx, [rsp+0B8h+var_68]
0x18004422e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044233  mov     rdx, rax
0x180044236  lea     rcx, [rsp+0B8h+var_48]
0x18004423b  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x180044240  lea     r8, [rsp+0B8h+var_48]
0x180044245  lea     rdx, [rsp+0B8h+var_78]
0x18004424a  lea     rcx, [rsi+110h]
0x180044251  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x180044256  mov     rdi, [rsi+110h]
0x18004425d  mov     rbx, [rax]
0x180044260  lea     rcx, [rsp+0B8h+var_48]
0x180044265  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004426a  cmp     rbx, rdi
0x18004426d  jnz     short loc_1800442A6
0x18004426f  lea     r8, [rsp+0B8h+var_80]
0x180044274  lea     rdx, [rsp+0B8h+var_68]
0x180044279  lea     rcx, [rsp+0B8h+var_48]
0x18004427e  call    ??$?0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@std@@QEAA@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAV?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@Z; std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>(std::wstring &,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo> &)
0x180044283  nop
0x180044284  lea     r8, [rsp+0B8h+var_48]
0x180044289  lea     rdx, [rsp+0B8h+var_78]
0x18004428e  lea     rcx, [rsi+110h]
0x180044295  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>>,0>>::insert<0,0>(std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>> &&)
0x18004429a  nop
0x18004429b  lea     rcx, [rsp+0B8h+var_48]
0x1800442a0  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>(void)
0x1800442a5  nop
0x1800442a6  lea     rcx, [rsp+0B8h+var_68]
0x1800442ab  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800442b0  nop
0x1800442b1  mov     rcx, [rsp+0B8h+string]; string
0x1800442b6  call    cs:__imp_WindowsDeleteString
0x1800442bc  mov     [rsp+0B8h+string], r14
0x1800442c1  lea     rcx, [rsp+0B8h+var_80]
0x1800442c6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800442cb  nop
0x1800442cc  lea     rcx, [rsp+0B8h+var_88]
0x1800442d1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800442d6  xor     eax, eax
0x1800442d8  jmp     short loc_1800442DE
0x1800442da  mov     eax, [rsp+0B8h+length]
0x1800442de  mov     rcx, [rsp+0B8h+var_20]
0x1800442e6  xor     rcx, rsp; StackCookie
0x1800442e9  call    __security_check_cookie
0x1800442ee  mov     rbx, [rsp+0B8h+arg_10]
0x1800442f6  add     rsp, 0A0h
0x1800442fd  pop     r14
0x1800442ff  pop     rdi
0x180044300  pop     rsi
0x180044301  retn
```
