# UWAInstallWork::_TryInvalidateCachedLicense(void)

- ea: `0x1800fc048`
- end: `0x1800fc498`
- name: `?_TryInvalidateCachedLicense@UWAInstallWork@@AEAAJXZ`
- size: `1104`
- prototype: `__int64 __fastcall(UWAInstallWork *__hidden this)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1800f5abc`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x180010b74`
- `0x18001cce0`
- `0x18002ec2c`
- `0x18002f214`
- `0x180056d64`
- `0x1800b2d60`
- `0x1800b4410`
- `0x1800b50a8`
- `0x1800b63c0`
- `0x1800d1d30`
- `0x1800fc048`
- `0x1801023b8`
- `0x180133d6c`
- `0x180215010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc2f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc33c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc2f5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc33c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800fc407`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc0c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc3a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc3c0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc0c9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc3a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800fc3c0`

## string_xrefs

- `0x1800fc2b7`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`
- `0x1800fc122`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800fc17b`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800fc1c0`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800fc1fd`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800fc325`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`
- `0x1800fc3f0`: `onecoreuap\enduser\winstore\installservice\lib\uwainstallwork.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9 #try_helpers=1
__int64 __fastcall UWAInstallWork::_TryInvalidateCachedLicense(UWAInstallWork *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  int Size; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  __int64 v7; // r14
  __int64 i; // rsi
  __int64 v9; // rdi
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rbx
  int View; // eax
  int InstalledContentIdsNoCV; // eax
  int v15; // eax
  const WCHAR *v17; // rdi
  __int64 (__fastcall *v18)(const WCHAR *, _QWORD, const WCHAR **); // rbx
  int v19; // eax
  const WCHAR *v20; // rbx
  __int64 (__fastcall *v21)(const WCHAR *, HSTRING *); // rdi
  int v22; // eax
  unsigned int v23; // ebx
  const char *v24; // rsi
  struct IApplicationLicenseManager *v25; // rdi
  __int64 (__fastcall *v26)(struct IApplicationLicenseManager *, PCWSTR); // rbx
  PCWSTR v27; // rax
  unsigned int v28; // eax
  int j; // eax
  int v30; // [rsp+20h] [rbp-A8h]
  char v31[8]; // [rsp+30h] [rbp-98h] BYREF
  __int64 v32; // [rsp+38h] [rbp-90h] BYREF
  __int64 v33; // [rsp+40h] [rbp-88h] BYREF
  HSTRING string; // [rsp+48h] [rbp-80h] BYREF
  const WCHAR *v35; // [rsp+50h] [rbp-78h] BYREF
  struct IApplicationLicenseManager *v36; // [rsp+58h] [rbp-70h] BYREF
  PCWSTR StringRawBuffer; // [rsp+60h] [rbp-68h] BYREF
  const WCHAR *v38; // [rsp+68h] [rbp-60h]
  unsigned int v39; // [rsp+70h] [rbp-58h]
  const WCHAR *v40; // [rsp+78h] [rbp-50h] BYREF
  char v41[8]; // [rsp+80h] [rbp-48h] BYREF
  int v42; // [rsp+88h] [rbp-40h]
  _BYTE v43[16]; // [rsp+90h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v33 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>::InternalRelease(&v33);
  Size = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(
           v3,
           v2,
           &v33);
  v5 = Size;
  if ( Size < 0 )
  {
    v6 = 2726;
LABEL_8:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
      (const char *)(unsigned int)Size,
      v30);
LABEL_18:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>::InternalRelease(&v33);
    return v5;
  }
  v7 = *((_QWORD *)this + 147);
  for ( i = *((_QWORD *)this + 146); i != v7; i += 8 )
  {
    v31[0] = 0;
    v9 = v33;
    v10 = qword_1802CB048;
    StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)(*(_QWORD *)i + 112LL), 0);
    v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v41, &StringRawBuffer);
    Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
      v9,
      *(_QWORD *)(v11 + 24),
      v10,
      v31);
  }
  LODWORD(v32) = 0;
  Size = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<unsigned char>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,unsigned char,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::get_Size(
           v33,
           &v32);
  v5 = Size;
  if ( Size < 0 )
  {
    v6 = 2734;
    goto LABEL_8;
  }
  if ( (_DWORD)v32 )
  {
    v32 = 0;
    v12 = v33;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
    View = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetView(
             v12,
             &v32);
    v5 = View;
    if ( View < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB2,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        (const char *)(unsigned int)View,
        v30);
LABEL_17:
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
      goto LABEL_18;
    }
    v35 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
    InstalledContentIdsNoCV = GetInstalledContentIdsNoCV(v32, &v35);
    v5 = InstalledContentIdsNoCV;
    if ( InstalledContentIdsNoCV < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB5,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        (const char *)(unsigned int)InstalledContentIdsNoCV,
        v30);
LABEL_16:
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
      goto LABEL_17;
    }
    v36 = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
    v15 = CoCreateLicenseManager(&v36);
    v5 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xAB8,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        (const char *)(unsigned int)v15,
        v30);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
      goto LABEL_16;
    }
    StringRawBuffer = v35;
    v38 = v35;
    v39 = 0;
    v40 = 0;
    wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(
      &StringRawBuffer,
      v41);
    for ( j = v39; j != v42; j = ++v39 )
    {
      v17 = v38;
      v18 = *(__int64 (__fastcall **)(const WCHAR *, _QWORD, const WCHAR **))(*(_QWORD *)v38 + 48LL);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v40);
      v19 = v18(v17, v39, &v40);
      if ( v19 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x1CBE,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
          (const char *)(unsigned int)v19,
          v30);
      v20 = v40;
      StringRawBuffer = v40;
      if ( v40 )
        (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)v40 + 8LL))(v40);
      string = 0;
      v21 = *(__int64 (__fastcall **)(const WCHAR *, HSTRING *))(*(_QWORD *)v20 + 48LL);
      WindowsDeleteString(0);
      string = 0;
      v22 = v21(v20, &string);
      v23 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xABE,
          (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
          (const char *)(unsigned int)v22,
          v30);
        WindowsDeleteString(string);
        string = 0;
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&StringRawBuffer);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v43);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v40);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
        Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>::InternalRelease(&v33);
        return v23;
      }
      v24 = (const char *)WindowsGetStringRawBuffer(string, 0);
      v25 = v36;
      v26 = *(__int64 (__fastcall **)(struct IApplicationLicenseManager *, PCWSTR))(*(_QWORD *)v36 + 112LL);
      v27 = WindowsGetStringRawBuffer(string, 0);
      v28 = v26(v25, v27);
      wil::details::in1diag3::Log_IfFailedMsg(
        retaddr,
        (void *)0xAC0,
        (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\uwainstallwork.cpp",
        (const char *)v28,
        (int)"Unable to invalidate license for %s",
        v24);
      WindowsDeleteString(string);
      Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&StringRawBuffer);
    }
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(v43);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v40);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v36);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v35);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v32);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>::InternalRelease(&v33);
  return 0;
}

```

## disassembly

```asm
0x1800fc048  mov     [rsp+arg_8], rbx
0x1800fc04d  mov     [rsp+arg_10], rsi
0x1800fc052  push    rdi
0x1800fc053  push    r14
0x1800fc055  push    r15
0x1800fc057  sub     rsp, 0B0h
0x1800fc05e  mov     rax, cs:__security_cookie
0x1800fc065  xor     rax, rsp
0x1800fc068  mov     [rsp+0C8h+var_28], rax
0x1800fc070  mov     rsi, rcx
0x1800fc073  xor     r15d, r15d
0x1800fc076  mov     [rsp+0C8h+var_88], r15
0x1800fc07b  lea     rcx, [rsp+0C8h+var_88]
0x1800fc080  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@7@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@9Collections@Foundation@7@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>::InternalRelease(void)
0x1800fc085  lea     r8, [rsp+0C8h+var_88]
0x1800fc08a  call    ?Make@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>> * *)
0x1800fc08f  mov     ebx, eax
0x1800fc091  test    eax, eax
0x1800fc093  jns     short loc_1800FC09F
0x1800fc095  mov     edx, 0AA6h
0x1800fc09a  jmp     loc_1800FC122
0x1800fc09f  mov     r14, [rsi+498h]
0x1800fc0a6  mov     rsi, [rsi+490h]
0x1800fc0ad  jmp     short loc_1800FC0FE
0x1800fc0af  mov     [rsp+0C8h+var_98], r15b
0x1800fc0b4  mov     rdi, [rsp+0C8h+var_88]
0x1800fc0b9  mov     rbx, cs:qword_1802CB048
0x1800fc0c0  mov     rcx, [rsi]
0x1800fc0c3  xor     edx, edx; length
0x1800fc0c5  mov     rcx, [rcx+70h]; string
0x1800fc0c9  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fc0cf  mov     [rsp+0C8h+var_68], rax
0x1800fc0d4  lea     rdx, [rsp+0C8h+var_68]
0x1800fc0d9  lea     rcx, [rsp+0C8h+var_48]
0x1800fc0e1  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x1800fc0e6  lea     r9, [rsp+0C8h+var_98]
0x1800fc0eb  mov     r8, rbx
0x1800fc0ee  mov     rdx, [rax+18h]
0x1800fc0f2  mov     rcx, rdi
0x1800fc0f5  call    ?Insert@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@0PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,HSTRING__ *,uchar *)
0x1800fc0fa  add     rsi, 8
0x1800fc0fe  cmp     rsi, r14
0x1800fc101  jnz     short loc_1800FC0AF
0x1800fc103  mov     dword ptr [rsp+0C8h+var_90], r15d
0x1800fc108  lea     rdx, [rsp+0C8h+var_90]
0x1800fc10d  mov     rcx, [rsp+0C8h+var_88]
0x1800fc112  call    ?get_Size@?$HashMap@PEAUHSTRING__@@EU?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@E@3456@U?$HashMapOptions@PEAUHSTRING__@@EU?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAI@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<uchar>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,uchar,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::get_Size(uint *)
0x1800fc117  mov     ebx, eax
0x1800fc119  test    eax, eax
0x1800fc11b  jns     short loc_1800FC13E
0x1800fc11d  mov     edx, 0AAEh; void *
0x1800fc122  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800fc129  mov     r9d, eax; char *
0x1800fc12c  mov     rcx, [rsp+0C8h]; this
0x1800fc134  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc139  jmp     loc_1800FC230
0x1800fc13e  cmp     dword ptr [rsp+0C8h+var_90], r15d
0x1800fc143  jbe     loc_1800FC463
0x1800fc149  mov     [rsp+0C8h+var_90], r15
0x1800fc14e  mov     rbx, [rsp+0C8h+var_88]
0x1800fc153  lea     rcx, [rsp+0C8h+var_90]
0x1800fc158  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc15d  lea     rdx, [rsp+0C8h+var_90]
0x1800fc162  mov     rcx, rbx
0x1800fc165  call    ?GetView@?$HashMap@PEAUHSTRING__@@PEAU1@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@3456@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@3456@U83456@U?$HashMapOptions@PEAUHSTRING__@@PEAU1@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@Windows@@$0A@$00$0A@@3456@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,HSTRING__ *,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetView(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> * *)
0x1800fc16a  mov     ebx, eax
0x1800fc16c  test    eax, eax
0x1800fc16e  jns     short loc_1800FC191
0x1800fc170  mov     rcx, [rsp+0C8h]; this
0x1800fc178  mov     r9d, eax; char *
0x1800fc17b  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800fc182  mov     edx, 0AB2h; void *
0x1800fc187  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc18c  jmp     loc_1800FC225
0x1800fc191  mov     [rsp+0C8h+var_78], r15
0x1800fc196  lea     rcx, [rsp+0C8h+var_78]
0x1800fc19b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc1a0  lea     rdx, [rsp+0C8h+var_78]
0x1800fc1a5  mov     rcx, [rsp+0C8h+var_90]
0x1800fc1aa  call    ?GetInstalledContentIdsNoCV@@YAJPEAU?$IMapView@PEAUHSTRING__@@PEAU1@@Collections@Foundation@Windows@@PEAPEAU?$IVectorView@PEAVContentIdInfo@Internal@WindowsUpdate@@@234@@Z; GetInstalledContentIdsNoCV(Windows::Foundation::Collections::IMapView<HSTRING__ *,HSTRING__ *> *,Windows::Foundation::Collections::IVectorView<WindowsUpdate::Internal::ContentIdInfo *> * *)
0x1800fc1af  mov     ebx, eax
0x1800fc1b1  test    eax, eax
0x1800fc1b3  jns     short loc_1800FC1D3
0x1800fc1b5  mov     rcx, [rsp+0C8h]; this
0x1800fc1bd  mov     r9d, eax; char *
0x1800fc1c0  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800fc1c7  mov     edx, 0AB5h; void *
0x1800fc1cc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc1d1  jmp     short loc_1800FC21A
0x1800fc1d3  mov     [rsp+0C8h+var_70], r15
0x1800fc1d8  lea     rcx, [rsp+0C8h+var_70]
0x1800fc1dd  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc1e2  lea     rcx, [rsp+0C8h+var_70]; struct IApplicationLicenseManager **
0x1800fc1e7  call    ?CoCreateLicenseManager@@YAJPEAPEAUIApplicationLicenseManager@@@Z; CoCreateLicenseManager(IApplicationLicenseManager * *)
0x1800fc1ec  mov     ebx, eax
0x1800fc1ee  test    eax, eax
0x1800fc1f0  jns     short loc_1800FC241
0x1800fc1f2  mov     rcx, [rsp+0C8h]; this
0x1800fc1fa  mov     r9d, eax; char *
0x1800fc1fd  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800fc204  mov     edx, 0AB8h; void *
0x1800fc209  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc20e  nop
0x1800fc20f  lea     rcx, [rsp+0C8h+var_70]
0x1800fc214  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc219  nop
0x1800fc21a  lea     rcx, [rsp+0C8h+var_78]
0x1800fc21f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc224  nop
0x1800fc225  lea     rcx, [rsp+0C8h+var_90]
0x1800fc22a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc22f  nop
0x1800fc230  lea     rcx, [rsp+0C8h+var_88]
0x1800fc235  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@7@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@9Collections@Foundation@7@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>::InternalRelease(void)
0x1800fc23a  mov     eax, ebx
0x1800fc23c  jmp     loc_1800FC46F
0x1800fc241  mov     rax, [rsp+0C8h+var_78]
0x1800fc246  mov     [rsp+0C8h+var_68], rax
0x1800fc24b  mov     [rsp+0C8h+var_60], rax
0x1800fc250  mov     [rsp+0C8h+var_58], r15d
0x1800fc255  mov     [rsp+0C8h+var_50], r15
0x1800fc25a  lea     rdx, [rsp+0C8h+var_48]
0x1800fc262  lea     rcx, [rsp+0C8h+var_68]
0x1800fc267  call    ?end@?$vector_range@U?$IVectorView@PEAVToastNotification@Notifications@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ; wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::Notifications::ToastNotification *>,wil::err_exception_policy>::end(void)
0x1800fc26c  nop
0x1800fc26d  mov     eax, [rsp+0C8h+var_58]
0x1800fc271  cmp     eax, [rsp+0C8h+var_40]
0x1800fc278  jz      loc_1800FC427
0x1800fc27e  mov     rdi, [rsp+0C8h+var_60]
0x1800fc283  mov     rax, [rdi]
0x1800fc286  mov     rbx, [rax+30h]
0x1800fc28a  lea     rcx, [rsp+0C8h+var_50]
0x1800fc28f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc294  lea     r8, [rsp+0C8h+var_50]
0x1800fc299  mov     edx, [rsp+0C8h+var_58]
0x1800fc29d  mov     rcx, rdi
0x1800fc2a0  mov     rax, rbx
0x1800fc2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc2a8  mov     rcx, [rsp+0C8h]; this
0x1800fc2b0  test    eax, eax
0x1800fc2b2  jns     short loc_1800FC2C8
0x1800fc2b4  mov     r9d, eax; char *
0x1800fc2b7  lea     r8, aOnecoreInterna_11; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800fc2be  mov     edx, 1CBEh; void *
0x1800fc2c3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800fc2c8  mov     rbx, [rsp+0C8h+var_50]
0x1800fc2cd  mov     [rsp+0C8h+var_68], rbx
0x1800fc2d2  test    rbx, rbx
0x1800fc2d5  jz      short loc_1800FC2E7
0x1800fc2d7  mov     rax, [rbx]
0x1800fc2da  mov     rcx, rbx
0x1800fc2dd  mov     rax, [rax+8]
0x1800fc2e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc2e6  nop
0x1800fc2e7  mov     [rsp+0C8h+string], r15
0x1800fc2ec  mov     rax, [rbx]
0x1800fc2ef  mov     rdi, [rax+30h]
0x1800fc2f3  xor     ecx, ecx; string
0x1800fc2f5  call    cs:__imp_WindowsDeleteString
0x1800fc2fb  mov     [rsp+0C8h+string], r15
0x1800fc300  lea     rdx, [rsp+0C8h+string]
0x1800fc305  mov     rcx, rbx
0x1800fc308  mov     rax, rdi
0x1800fc30b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc310  mov     ebx, eax
0x1800fc312  test    eax, eax
0x1800fc314  jns     loc_1800FC39D
0x1800fc31a  mov     rcx, [rsp+0C8h]; this
0x1800fc322  mov     r9d, eax; char *
0x1800fc325  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800fc32c  mov     edx, 0ABEh; void *
0x1800fc331  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800fc336  nop
0x1800fc337  mov     rcx, [rsp+0C8h+string]; string
0x1800fc33c  call    cs:__imp_WindowsDeleteString
0x1800fc342  mov     [rsp+0C8h+string], r15
0x1800fc347  lea     rcx, [rsp+0C8h+var_68]
0x1800fc34c  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc351  nop
0x1800fc352  lea     rcx, [rsp+0C8h+var_38]
0x1800fc35a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc35f  nop
0x1800fc360  lea     rcx, [rsp+0C8h+var_50]
0x1800fc365  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc36a  nop
0x1800fc36b  lea     rcx, [rsp+0C8h+var_70]
0x1800fc370  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc375  nop
0x1800fc376  lea     rcx, [rsp+0C8h+var_78]
0x1800fc37b  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc380  nop
0x1800fc381  lea     rcx, [rsp+0C8h+var_90]
0x1800fc386  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc38b  nop
0x1800fc38c  lea     rcx, [rsp+0C8h+var_88]
0x1800fc391  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@7@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@9Collections@Foundation@7@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>::InternalRelease(void)
0x1800fc396  mov     eax, ebx
0x1800fc398  jmp     loc_1800FC46F
0x1800fc39d  xor     edx, edx; length
0x1800fc39f  mov     rcx, [rsp+0C8h+string]; string
0x1800fc3a4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fc3aa  mov     rsi, rax
0x1800fc3ad  mov     rdi, [rsp+0C8h+var_70]
0x1800fc3b2  mov     rdx, [rdi]
0x1800fc3b5  mov     rbx, [rdx+70h]
0x1800fc3b9  xor     edx, edx; length
0x1800fc3bb  mov     rcx, [rsp+0C8h+string]; string
0x1800fc3c0  call    cs:__imp_WindowsGetStringRawBuffer
0x1800fc3c6  mov     rdx, rax
0x1800fc3c9  mov     rcx, rdi
0x1800fc3cc  mov     rax, rbx
0x1800fc3cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800fc3d4  mov     rcx, [rsp+0C8h]; this
0x1800fc3dc  mov     [rsp+0C8h+var_A0], rsi; char *
0x1800fc3e1  lea     rdx, aUnableToInvali; "Unable to invalidate license for %s"
0x1800fc3e8  mov     qword ptr [rsp+0C8h+var_A8], rdx; int
0x1800fc3ed  mov     r9d, eax; char *
0x1800fc3f0  lea     r8, aOnecoreuapEndu_12; "onecoreuap\\enduser\\winstore\\installs"...
0x1800fc3f7  mov     edx, 0AC0h; void *
0x1800fc3fc  call    ?Log_IfFailedMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_IfFailedMsg(void *,uint,char const *,long,char const *,...)
0x1800fc401  nop
0x1800fc402  mov     rcx, [rsp+0C8h+string]; string
0x1800fc407  call    cs:__imp_WindowsDeleteString
0x1800fc40d  nop
0x1800fc40e  lea     rcx, [rsp+0C8h+var_68]
0x1800fc413  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc418  mov     eax, [rsp+0C8h+var_58]
0x1800fc41c  inc     eax
0x1800fc41e  mov     [rsp+0C8h+var_58], eax
0x1800fc422  jmp     loc_1800FC271
0x1800fc427  lea     rcx, [rsp+0C8h+var_38]
0x1800fc42f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc434  nop
0x1800fc435  lea     rcx, [rsp+0C8h+var_50]
0x1800fc43a  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc43f  nop
0x1800fc440  jmp     short $+2
0x1800fc442  lea     rcx, [rsp+0C8h+var_70]
0x1800fc447  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc44c  nop
0x1800fc44d  lea     rcx, [rsp+0C8h+var_78]
0x1800fc452  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc457  nop
0x1800fc458  lea     rcx, [rsp+0C8h+var_90]
0x1800fc45d  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x1800fc462  nop
0x1800fc463  lea     rcx, [rsp+0C8h+var_88]
0x1800fc468  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@7@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@9Collections@Foundation@7@U?$DefaultLifetimeTraits@PEAVAppInstallItem@InstallControl@Preview@Store@ApplicationModel@Windows@@@9Collections@Foundation@7@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::ApplicationModel::Store::Preview::InstallControl::AppInstallItem *>,0>>::InternalRelease(void)
0x1800fc46d  xor     eax, eax
0x1800fc46f  mov     rcx, [rsp+0C8h+var_28]
0x1800fc477  xor     rcx, rsp; StackCookie
0x1800fc47a  call    __security_check_cookie
0x1800fc47f  lea     r11, [rsp+0C8h+var_18]
0x1800fc487  mov     rbx, [r11+28h]
0x1800fc48b  mov     rsi, [r11+30h]
0x1800fc48f  mov     rsp, r11
0x1800fc492  pop     r15
0x1800fc494  pop     r14
0x1800fc496  pop     rdi
0x1800fc497  retn
```
