# SystemSettings::BatteryUsageHandlers::UsageDataSingleton::InsertPackage(SystemSettings::BatteryUsageHandlers::IPackageInfo *)

- ea: `0x18004430c`
- end: `0x18004468f`
- name: `?InsertPackage@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@AEAAJPEAUIPackageInfo@23@@Z`
- size: `899`
- prototype: `__int64 __fastcall(SystemSettings::BatteryUsageHandlers::UsageDataSingleton *__hidden this, struct SystemSettings::BatteryUsageHandlers::IPackageInfo *)`
- caller_count: `1`
- callee_count: `19`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18003ed98`

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
- `0x180042d3c`
- `0x1800434e4`
- `0x18004430c`
- `0x18004719c`
- `0x1800512e0`
- `0x180055cf4`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044392`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800443d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800444a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044642`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044392`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800443d5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044453`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800444a1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044565`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180044642`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004440b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800444d2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18004440b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800444d2`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall SystemSettings::BatteryUsageHandlers::UsageDataSingleton::InsertPackage(
        SystemSettings::BatteryUsageHandlers::UsageDataSingleton *this,
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
      (void *)0x528,
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
      (void *)0x52C,
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
        (void *)0x534,
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
    PackageFromFamilyName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFromFamilyName(
                              this,
                              v19,
                              &v28);
    std::wstring::_Tidy_deallocate(v32);
    if ( PackageFromFamilyName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x53B,
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
    PackageDisplayName = SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageDisplayName(this, v32, v28);
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
0x18004430c  mov     [rsp+arg_10], rbx
0x180044311  push    rsi
0x180044312  push    rdi
0x180044313  push    r14
0x180044315  sub     rsp, 0A0h
0x18004431c  mov     rax, cs:__security_cookie
0x180044323  xor     rax, rsp
0x180044326  mov     [rsp+0B8h+var_20], rax
0x18004432e  mov     rdi, rdx
0x180044331  mov     rsi, rcx
0x180044334  xor     r14d, r14d
0x180044337  mov     [rsp+0B8h+var_88], r14
0x18004433c  test    rdx, rdx
0x18004433f  jnz     short loc_180044374
0x180044341  mov     rcx, [rsp+0B8h]; this
0x180044349  mov     ebx, 80004005h
0x18004434e  mov     r9d, ebx; char *
0x180044351  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180044358  mov     edx, 528h; void *
0x18004435d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044362  nop
0x180044363  lea     rcx, [rsp+0B8h+var_88]
0x180044368  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004436d  mov     eax, ebx
0x18004436f  jmp     loc_18004466A
0x180044374  mov     [rsp+0B8h+var_80], rdi
0x180044379  lea     rcx, [rsp+0B8h+var_80]
0x18004437e  call    ?InternalAddRef@?$ComPtr@UIInspectable@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IInspectable>::InternalAddRef(void)
0x180044383  nop
0x180044384  mov     [rsp+0B8h+string], r14
0x180044389  mov     rax, [rdi]
0x18004438c  mov     rbx, [rax+48h]
0x180044390  xor     ecx, ecx; string
0x180044392  call    cs:__imp_WindowsDeleteString
0x180044398  mov     [rsp+0B8h+string], r14; int
0x18004439d  lea     rdx, [rsp+0B8h+string]
0x1800443a2  mov     rcx, rdi
0x1800443a5  mov     rax, rbx
0x1800443a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800443ad  mov     ebx, eax
0x1800443af  test    eax, eax
0x1800443b1  jns     short loc_1800443FC
0x1800443b3  mov     rcx, [rsp+0B8h]; this
0x1800443bb  mov     r9d, eax; char *
0x1800443be  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x1800443c5  mov     edx, 52Ch; void *
0x1800443ca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800443cf  nop
0x1800443d0  mov     rcx, [rsp+0B8h+string]; string
0x1800443d5  call    cs:__imp_WindowsDeleteString
0x1800443db  mov     [rsp+0B8h+string], r14
0x1800443e0  lea     rcx, [rsp+0B8h+var_80]
0x1800443e5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800443ea  nop
0x1800443eb  lea     rcx, [rsp+0B8h+var_88]
0x1800443f0  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800443f5  mov     eax, ebx
0x1800443f7  jmp     loc_18004466A
0x1800443fc  mov     [rsp+0B8h+length], r14d
0x180044401  lea     rdx, [rsp+0B8h+length]; length
0x180044406  mov     rcx, [rsp+0B8h+string]; string
0x18004440b  call    cs:__imp_WindowsGetStringRawBuffer
0x180044411  mov     rbx, rax
0x180044414  xorps   xmm0, xmm0
0x180044417  movups  [rsp+0B8h+var_68], xmm0
0x18004441c  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180044424  movdqu  [rsp+0B8h+var_58], xmm1
0x18004442a  mov     word ptr [rsp+0B8h+var_68], r14w
0x180044430  lea     rdx, aInbox; "Inbox"
0x180044437  mov     rcx, rax; String1
0x18004443a  call    wcscmp_0
0x18004443f  test    eax, eax
0x180044441  jnz     loc_1800444F8
0x180044447  mov     rax, [rdi]
0x18004444a  mov     rbx, [rax+30h]
0x18004444e  mov     rcx, [rsp+0B8h+string]; string
0x180044453  call    cs:__imp_WindowsDeleteString
0x180044459  mov     [rsp+0B8h+string], r14; int
0x18004445e  lea     rdx, [rsp+0B8h+string]
0x180044463  mov     rcx, rdi
0x180044466  mov     rax, rbx
0x180044469  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004446e  mov     ebx, eax
0x180044470  test    eax, eax
0x180044472  jns     short loc_1800444C8
0x180044474  mov     rcx, [rsp+0B8h]; this
0x18004447c  mov     r9d, eax; char *
0x18004447f  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x180044486  mov     edx, 534h; void *
0x18004448b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044490  nop
0x180044491  lea     rcx, [rsp+0B8h+var_68]
0x180044496  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004449b  nop
0x18004449c  mov     rcx, [rsp+0B8h+string]; string
0x1800444a1  call    cs:__imp_WindowsDeleteString
0x1800444a7  mov     [rsp+0B8h+string], r14
0x1800444ac  lea     rcx, [rsp+0B8h+var_80]
0x1800444b1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800444b6  nop
0x1800444b7  lea     rcx, [rsp+0B8h+var_88]
0x1800444bc  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800444c1  mov     eax, ebx
0x1800444c3  jmp     loc_18004466A
0x1800444c8  lea     rdx, [rsp+0B8h+length]; length
0x1800444cd  mov     rcx, [rsp+0B8h+string]; string
0x1800444d2  call    cs:__imp_WindowsGetStringRawBuffer
0x1800444d8  or      r8, 0FFFFFFFFFFFFFFFFh
0x1800444dc  inc     r8
0x1800444df  cmp     [rax+r8*2], r14w
0x1800444e4  jnz     short loc_1800444DC
0x1800444e6  mov     rdx, rax
0x1800444e9  lea     rcx, [rsp+0B8h+var_68]
0x1800444ee  call    ??$_Assign@G@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@QEBG_K@Z; std::wstring::_Assign<ushort>(ushort const * const,unsigned __int64)
0x1800444f3  jmp     loc_1800445B5
0x1800444f8  lea     rcx, [rsp+0B8h+var_88]
0x1800444fd  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044502  mov     rdx, rbx
0x180044505  lea     rcx, [rsp+0B8h+var_48]
0x18004450a  call    ?GetPackageFamilyNameFromPackageFullName@BatteryUsageHandlers@SystemSettings@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEBG@Z; SystemSettings::BatteryUsageHandlers::GetPackageFamilyNameFromPackageFullName(ushort const *)
0x18004450f  nop
0x180044510  mov     rcx, rax
0x180044513  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180044518  lea     r8, [rsp+0B8h+var_88]
0x18004451d  mov     rdx, rax
0x180044520  mov     rcx, rsi
0x180044523  call    ?GetPackageFromFamilyName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@QEAAJPEBGPEAV?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageFromFamilyName(ushort const *,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage> *)
0x180044528  mov     ebx, eax
0x18004452a  lea     rcx, [rsp+0B8h+var_48]
0x18004452f  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180044534  test    ebx, ebx
0x180044536  jns     short loc_18004458C
0x180044538  mov     rcx, [rsp+0B8h]; this
0x180044540  mov     r9d, ebx; char *
0x180044543  lea     r8, aOnecoreuapShel_8; "onecoreuap\\shell\\coresettinghandlers"...
0x18004454a  mov     edx, 53Bh; void *
0x18004454f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180044554  nop
0x180044555  lea     rcx, [rsp+0B8h+var_68]
0x18004455a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004455f  nop
0x180044560  mov     rcx, [rsp+0B8h+string]; string
0x180044565  call    cs:__imp_WindowsDeleteString
0x18004456b  mov     [rsp+0B8h+string], r14
0x180044570  lea     rcx, [rsp+0B8h+var_80]
0x180044575  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18004457a  nop
0x18004457b  lea     rcx, [rsp+0B8h+var_88]
0x180044580  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044585  mov     eax, ebx
0x180044587  jmp     loc_18004466A
0x18004458c  mov     r8, [rsp+0B8h+var_88]
0x180044591  lea     rdx, [rsp+0B8h+var_48]
0x180044596  mov     rcx, rsi
0x180044599  call    ?GetPackageDisplayName@UsageDataSingleton@BatteryUsageHandlers@SystemSettings@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIPackage@StateRepository@Internal@Windows@@@Z; SystemSettings::BatteryUsageHandlers::UsageDataSingleton::GetPackageDisplayName(Windows::Internal::StateRepository::IPackage *)
0x18004459e  mov     rdx, rax
0x1800445a1  lea     rcx, [rsp+0B8h+var_68]
0x1800445a6  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x1800445ab  lea     rcx, [rsp+0B8h+var_48]
0x1800445b0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800445b5  lea     rcx, [rsp+0B8h+var_68]
0x1800445ba  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x1800445bf  mov     rdx, rax
0x1800445c2  lea     rcx, [rsp+0B8h+var_48]
0x1800445c7  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800445cc  lea     r8, [rsp+0B8h+var_48]
0x1800445d1  lea     rdx, [rsp+0B8h+var_78]
0x1800445d6  lea     rcx, [rsi+110h]
0x1800445dd  call    ?find@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,std::wstring,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::find(std::wstring const &)
0x1800445e2  mov     rdi, [rsi+110h]
0x1800445e9  mov     rbx, [rax]
0x1800445ec  lea     rcx, [rsp+0B8h+var_48]
0x1800445f1  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800445f6  cmp     rbx, rdi
0x1800445f9  jnz     short loc_180044632
0x1800445fb  lea     r8, [rsp+0B8h+var_80]
0x180044600  lea     rdx, [rsp+0B8h+var_68]
0x180044605  lea     rcx, [rsp+0B8h+var_48]
0x18004460a  call    ??$?0AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAV?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@$0A@@?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@std@@QEAA@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@1@AEAV?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@Z; std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>(std::wstring &,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo> &)
0x18004460f  nop
0x180044610  lea     r8, [rsp+0B8h+var_48]
0x180044615  lea     rdx, [rsp+0B8h+var_78]
0x18004461a  lea     rcx, [rsi+110h]
0x180044621  call    ??$insert@$0A@$0A@@?$_Tree@V?$_Tmap_traits@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@U?$less@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@2@$0A@@std@@@std@@QEAA?AU?$pair@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@std@@@std@@@std@@@std@@_N@1@$$QEAU?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackageInfo@BatteryUsageHandlers@SystemSettings@@@WRL@Microsoft@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>,std::less<std::wstring const>,std::allocator<std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>>>,0>>::insert<0,0>(std::pair<std::wstring const,Microsoft::WRL::ComPtr<SystemSettings::BatteryUsageHandlers::IPackageInfo>> &&)
0x180044626  nop
0x180044627  lea     rcx, [rsp+0B8h+var_48]
0x18004462c  call    ??1?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$ComPtr@UIPackage@StateRepository@Internal@Windows@@@WRL@Microsoft@@@std@@QEAA@XZ; std::pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>::~pair<std::wstring const,Microsoft::WRL::ComPtr<Windows::Internal::StateRepository::IPackage>>(void)
0x180044631  nop
0x180044632  lea     rcx, [rsp+0B8h+var_68]
0x180044637  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004463c  nop
0x18004463d  mov     rcx, [rsp+0B8h+string]; string
0x180044642  call    cs:__imp_WindowsDeleteString
0x180044648  mov     [rsp+0B8h+string], r14
0x18004464d  lea     rcx, [rsp+0B8h+var_80]
0x180044652  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044657  nop
0x180044658  lea     rcx, [rsp+0B8h+var_88]
0x18004465d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x180044662  xor     eax, eax
0x180044664  jmp     short loc_18004466A
0x180044666  mov     eax, [rsp+0B8h+length]
0x18004466a  mov     rcx, [rsp+0B8h+var_20]
0x180044672  xor     rcx, rsp; StackCookie
0x180044675  call    __security_check_cookie
0x18004467a  mov     rbx, [rsp+0B8h+arg_10]
0x180044682  add     rsp, 0A0h
0x180044689  pop     r14
0x18004468b  pop     rdi
0x18004468c  pop     rsi
0x18004468d  retn
```
