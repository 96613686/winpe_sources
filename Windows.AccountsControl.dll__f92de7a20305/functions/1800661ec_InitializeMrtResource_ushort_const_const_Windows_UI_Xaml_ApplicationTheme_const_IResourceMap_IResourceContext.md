# InitializeMrtResource(ushort const * const,Windows::UI::Xaml::ApplicationTheme const *,IResourceMap * *,IResourceContext * *)

- ea: `0x1800661ec`
- end: `0x180066656`
- name: `?InitializeMrtResource@@YAXQEBGPEBW4ApplicationTheme@Xaml@UI@Windows@@PEAPEAUIResourceMap@@PEAPEAUIResourceContext@@@Z`
- size: `1130`
- prototype: `void __fastcall(const unsigned __int16 *const, const enum Windows::UI::Xaml::ApplicationTheme *, struct IResourceMap **, struct IResourceContext **)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180065d64`

## callees

- `0x180011ffc`
- `0x180018f90`
- `0x1800658a8`
- `0x1800661ec`
- `0x18006665c`
- `0x18006851c`
- `0x18006c010`

## import_xrefs

- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800664be`
- `ntdll!RtlGetDeviceFamilyInfoEnum` at `0x1800664be`
- `ntdll!RtlIsMultiSessionSku` at `0x1800664d6`
- `ntdll!RtlIsMultiSessionSku` at `0x1800664d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006628d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800663a1`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18006628d`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1800663a1`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006652d`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18006652d`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall InitializeMrtResource(
        const unsigned __int16 *a1,
        const enum Windows::UI::Xaml::ApplicationTheme *a2,
        struct IResourceMap **a3,
        struct IResourceContext **a4)
{
  CallerIdentity *v8; // rcx
  unsigned __int16 **v9; // r8
  int SinglePackageFullNameFromPackageFamilyName; // eax
  HRESULT v11; // eax
  int v12; // eax
  LPVOID v13; // rdi
  __int64 (__fastcall *v14)(LPVOID, GUID *, struct IResourceContext **); // rbx
  int v15; // eax
  const WCHAR *v16; // r8
  HRESULT v17; // eax
  int v18; // eax
  LPVOID v19; // rdi
  __int64 (__fastcall *v20)(LPVOID, GUID *, __int64 *); // rbx
  int v21; // eax
  __int64 v22; // rdi
  void (__fastcall *v23)(__int64, const wchar_t *, unsigned __int16 **); // rbx
  int v24; // ecx
  LSTATUS ValueW; // eax
  const unsigned __int16 *v26; // rcx
  LPVOID v27; // rdi
  __int64 (__fastcall *v28)(LPVOID, const wchar_t *, GUID *, __int64 *); // rbx
  int v29; // eax
  __int64 v30; // rdi
  __int64 (__fastcall *v31)(__int64, const wchar_t *, struct IResourceMap **); // rbx
  int v32; // eax
  struct IResourceMap *v33; // rax
  struct IResourceContext *v34; // rax
  int ppv; // [rsp+20h] [rbp-59h]
  int ppva; // [rsp+20h] [rbp-59h]
  struct IResourceContext *v37; // [rsp+40h] [rbp-39h] BYREF
  LPVOID v38; // [rsp+48h] [rbp-31h] BYREF
  struct IResourceMap *v39; // [rsp+50h] [rbp-29h] BYREF
  __int64 v40; // [rsp+58h] [rbp-21h] BYREF
  DWORD pdwType; // [rsp+60h] [rbp-19h] BYREF
  unsigned __int16 *v42; // [rsp+68h] [rbp-11h] BYREF
  __int64 v43; // [rsp+70h] [rbp-9h]
  __int64 v44; // [rsp+78h] [rbp-1h]
  unsigned __int16 v45[4]; // [rsp+80h] [rbp+7h] BYREF
  __int64 v46; // [rsp+88h] [rbp+Fh]
  __int64 v47; // [rsp+90h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  LPVOID pvData; // [rsp+F0h] [rbp+77h] BYREF
  __int64 pcbData; // [rsp+F8h] [rbp+7Fh] BYREF

  *a3 = 0;
  *a4 = 0;
  *(_QWORD *)v45 = 0;
  v46 = 0;
  v47 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v45);
  v46 = -1;
  v47 = -1;
  SinglePackageFullNameFromPackageFamilyName = CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(
                                                 v8,
                                                 v45,
                                                 v9);
  if ( SinglePackageFullNameFromPackageFamilyName < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x79,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\resourcehelperlib\\mrticonhelpers.cpp",
      (const char *)(unsigned int)SinglePackageFullNameFromPackageFamilyName,
      ppv);
  v38 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  v11 = CoCreateInstance(
          &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
          0,
          1u,
          &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
          &v38);
  if ( v11 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7C,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\resourcehelperlib\\mrticonhelpers.cpp",
      (const char *)(unsigned int)v11,
      ppva);
  v12 = (*(__int64 (__fastcall **)(LPVOID, _QWORD))(*(_QWORD *)v38 + 40LL))(v38, *(_QWORD *)v45);
  if ( v12 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\resourcehelperlib\\mrticonhelpers.cpp",
      (const char *)(unsigned int)v12,
      ppva);
  v37 = 0;
  v13 = v38;
  v14 = *(__int64 (__fastcall **)(LPVOID, GUID *, struct IResourceContext **))(*(_QWORD *)v38 + 72LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  v15 = v14(v13, &GUID_e3c22b30_8502_4b2f_9133_559674587e51, &v37);
  if ( v15 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x80,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\resourcehelperlib\\mrticonhelpers.cpp",
      (const char *)(unsigned int)v15,
      ppva);
  if ( a2 )
  {
    v16 = L"Dark";
    if ( *(_DWORD *)a2 != 1 )
      v16 = L"Light";
    (*(void (__fastcall **)(struct IResourceContext *, const wchar_t *, const WCHAR *))(*(_QWORD *)v37 + 144LL))(
      v37,
      L"Theme",
      v16);
    goto LABEL_31;
  }
  if ( a1 && *a1 )
  {
    pvData = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pvData);
    v17 = CoCreateInstance(
            &GUID_dbce7e40_7345_439d_b12c_114a11819a09,
            0,
            1u,
            &GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c,
            &pvData);
    if ( v17 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x9B,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\resourcehelperlib\\mrticonhelpers.cpp",
        (const char *)(unsigned int)v17,
        ppva);
    v18 = (*(__int64 (__fastcall **)(LPVOID, const unsigned __int16 *))(*(_QWORD *)pvData + 40LL))(pvData, a1);
    if ( v18 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x9C,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\resourcehelperlib\\mrticonhelpers.cpp",
        (const char *)(unsigned int)v18,
        ppva);
    pcbData = 0;
    v19 = pvData;
    v20 = *(__int64 (__fastcall **)(LPVOID, GUID *, __int64 *))(*(_QWORD *)pvData + 72LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pcbData);
    v21 = v20(v19, &GUID_e3c22b30_8502_4b2f_9133_559674587e51, &pcbData);
    if ( v21 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x9F,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\resourcehelperlib\\mrticonhelpers.cpp",
        (const char *)(unsigned int)v21,
        ppva);
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v22 = pcbData;
    v23 = *(void (__fastcall **)(__int64, const wchar_t *, unsigned __int16 **))(*(_QWORD *)pcbData + 80LL);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
    v43 = -1;
    v44 = -1;
    v23(v22, L"Theme", &v42);
    OverrideThemeConsideringContrast(v42, v37);
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pcbData);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&pvData);
    goto LABEL_31;
  }
  LODWORD(pvData) = 0;
  RtlGetDeviceFamilyInfoEnum(0, &pvData, 0);
  v24 = (int)pvData;
  if ( (((_DWORD)pvData - 1) & 0xFFFFFFFD) != 0 )
  {
    if ( (_DWORD)pvData != 6 )
      goto LABEL_26;
    if ( !(unsigned __int8)RtlIsMultiSessionSku() )
    {
      v24 = (int)pvData;
LABEL_26:
      if ( v24 != 9 )
        goto LABEL_31;
    }
  }
  LODWORD(pvData) = 0;
  LODWORD(pcbData) = 4;
  pdwType = 0;
  ValueW = RegGetValueW(
             HKEY_CURRENT_USER,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Themes\\Personalize",
             L"AppsUseLightTheme",
             0x10u,
             &pdwType,
             &pvData,
             (LPDWORD)&pcbData);
  v26 = L"Light";
  if ( !ValueW && !(_DWORD)pvData )
    v26 = L"Dark";
  OverrideThemeConsideringContrast(v26, v37);
LABEL_31:
  v40 = 0;
  v27 = v38;
  v28 = *(__int64 (__fastcall **)(LPVOID, const wchar_t *, GUID *, __int64 *))(*(_QWORD *)v38 + 64LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  v29 = v28(v27, L"Windows.UI.AccountsControl", &GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd, &v40);
  if ( v29 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC4,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\resourcehelperlib\\mrticonhelpers.cpp",
      (const char *)(unsigned int)v29,
      ppva);
  v39 = 0;
  v30 = v40;
  v31 = *(__int64 (__fastcall **)(__int64, const wchar_t *, struct IResourceMap **))(*(_QWORD *)v40 + 32LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  v32 = v31(v30, L"Files", &v39);
  if ( v32 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0xC7,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\resourcehelperlib\\mrticonhelpers.cpp",
      (const char *)(unsigned int)v32,
      ppva);
  v33 = v39;
  v39 = 0;
  *a3 = v33;
  v34 = v37;
  v37 = 0;
  *a4 = v34;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v39);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v40);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v37);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v38);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v45);
}

```

## disassembly

```asm
0x1800661ec  mov     [rsp-8+arg_0], rbx
0x1800661f1  push    rbp
0x1800661f2  push    rsi
0x1800661f3  push    rdi
0x1800661f4  push    r12
0x1800661f6  push    r13
0x1800661f8  push    r14
0x1800661fa  push    r15
0x1800661fc  lea     rbp, [rsp-27h]
0x180066201  sub     rsp, 0A0h
0x180066208  mov     r15, r9
0x18006620b  mov     r12, r8
0x18006620e  mov     r14, rdx
0x180066211  mov     rsi, rcx
0x180066214  xor     r13d, r13d
0x180066217  mov     [r8], r13
0x18006621a  mov     [r9], r13
0x18006621d  mov     qword ptr [rbp+57h+var_50], r13
0x180066221  mov     [rbp+57h+var_48], r13
0x180066225  mov     [rbp+57h+var_40], r13
0x180066229  lea     rcx, [rbp+57h+var_50]
0x18006622d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180066232  or      rax, 0FFFFFFFFFFFFFFFFh
0x180066236  mov     [rbp+57h+var_48], rax
0x18006623a  mov     [rbp+57h+var_40], rax
0x18006623e  lea     rdx, [rbp+57h+var_50]; unsigned __int16 *
0x180066242  call    ?GetSinglePackageFullNameFromPackageFamilyName@CallerIdentity@@YAJPEBGPEAPEAG@Z; CallerIdentity::GetSinglePackageFullNameFromPackageFamilyName(ushort const *,ushort * *)
0x180066247  mov     rcx, [rbp+5Fh]; this
0x18006624b  test    eax, eax
0x18006624d  jns     short loc_180066263
0x18006624f  mov     r9d, eax; char *
0x180066252  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\accountscontrol\\api"...
0x180066259  lea     edx, [r13+79h]; void *
0x18006625d  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180066263  mov     [rbp+57h+var_88], r13
0x180066267  lea     rcx, [rbp+57h+var_88]
0x18006626b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180066270  lea     rax, [rbp+57h+var_88]
0x180066274  mov     [rsp+0D0h+ppv], rax; int
0x180066279  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x180066280  xor     edx, edx; pUnkOuter
0x180066282  lea     r8d, [rdx+1]; dwClsContext
0x180066286  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x18006628d  call    cs:__imp_CoCreateInstance
0x180066293  mov     rcx, [rbp+5Fh]; this
0x180066297  test    eax, eax
0x180066299  jns     short loc_1800662B0
0x18006629b  mov     r9d, eax; char *
0x18006629e  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800662a5  mov     edx, 7Ch ; '|'; void *
0x1800662aa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800662b0  mov     rcx, [rbp+57h+var_88]
0x1800662b4  mov     rax, [rcx]
0x1800662b7  mov     rdx, qword ptr [rbp+57h+var_50]
0x1800662bb  mov     rax, [rax+28h]
0x1800662bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800662c4  mov     rcx, [rbp+5Fh]; this
0x1800662c8  test    eax, eax
0x1800662ca  jns     short loc_1800662E1
0x1800662cc  mov     r9d, eax; char *
0x1800662cf  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800662d6  mov     edx, 7Dh ; '}'; void *
0x1800662db  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800662e1  mov     [rbp+57h+var_90], r13
0x1800662e5  mov     rdi, [rbp+57h+var_88]
0x1800662e9  mov     rax, [rdi]
0x1800662ec  mov     rbx, [rax+48h]
0x1800662f0  lea     rcx, [rbp+57h+var_90]
0x1800662f4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800662f9  lea     r8, [rbp+57h+var_90]
0x1800662fd  lea     rdx, _GUID_e3c22b30_8502_4b2f_9133_559674587e51
0x180066304  mov     rcx, rdi
0x180066307  mov     rax, rbx
0x18006630a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006630f  mov     rcx, [rbp+5Fh]; this
0x180066313  test    eax, eax
0x180066315  jns     short loc_18006632C
0x180066317  mov     r9d, eax; char *
0x18006631a  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\accountscontrol\\api"...
0x180066321  mov     edx, 80h; void *
0x180066326  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006632c  test    r14, r14
0x18006632f  jz      short loc_180066364
0x180066331  mov     rcx, [rbp+57h+var_90]
0x180066335  lea     rdx, aTheme; "Theme"
0x18006633c  mov     rax, [rcx]
0x18006633f  mov     rax, [rax+90h]
0x180066346  cmp     dword ptr [r14], 1
0x18006634a  lea     r8, aDark; "Dark"
0x180066351  jz      short loc_18006635A
0x180066353  lea     r8, aLight; "Light"
0x18006635a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006635f  jmp     loc_180066556
0x180066364  test    rsi, rsi
0x180066367  jz      loc_1800664B1
0x18006636d  cmp     [rsi], r13w
0x180066371  jz      loc_1800664B1
0x180066377  mov     [rbp+57h+arg_10], r13
0x18006637b  lea     rcx, [rbp+57h+arg_10]
0x18006637f  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180066384  lea     rax, [rbp+57h+arg_10]
0x180066388  mov     [rsp+0D0h+ppv], rax; int
0x18006638d  lea     r9, _GUID_130a2f65_2be7_4309_9a58_a9052ff2b61c; riid
0x180066394  xor     edx, edx; pUnkOuter
0x180066396  lea     r8d, [rdx+1]; dwClsContext
0x18006639a  lea     rcx, _GUID_dbce7e40_7345_439d_b12c_114a11819a09; rclsid
0x1800663a1  call    cs:__imp_CoCreateInstance
0x1800663a7  mov     rcx, [rbp+5Fh]; this
0x1800663ab  test    eax, eax
0x1800663ad  jns     short loc_1800663C4
0x1800663af  mov     r9d, eax; char *
0x1800663b2  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800663b9  mov     edx, 9Bh; void *
0x1800663be  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800663c4  mov     rcx, [rbp+57h+arg_10]
0x1800663c8  mov     rax, [rcx]
0x1800663cb  mov     rdx, rsi
0x1800663ce  mov     rax, [rax+28h]
0x1800663d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800663d7  mov     rcx, [rbp+5Fh]; this
0x1800663db  test    eax, eax
0x1800663dd  jns     short loc_1800663F4
0x1800663df  mov     r9d, eax; char *
0x1800663e2  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800663e9  mov     edx, 9Ch; void *
0x1800663ee  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800663f4  mov     [rbp+57h+arg_18], r13
0x1800663f8  mov     rdi, [rbp+57h+arg_10]
0x1800663fc  mov     rax, [rdi]
0x1800663ff  mov     rbx, [rax+48h]
0x180066403  lea     rcx, [rbp+57h+arg_18]
0x180066407  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006640c  lea     r8, [rbp+57h+arg_18]
0x180066410  lea     rdx, _GUID_e3c22b30_8502_4b2f_9133_559674587e51
0x180066417  mov     rcx, rdi
0x18006641a  mov     rax, rbx
0x18006641d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066422  mov     rcx, [rbp+5Fh]; this
0x180066426  test    eax, eax
0x180066428  jns     short loc_18006643F
0x18006642a  mov     r9d, eax; char *
0x18006642d  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\accountscontrol\\api"...
0x180066434  mov     edx, 9Fh; void *
0x180066439  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18006643f  mov     [rbp+57h+var_68], r13
0x180066443  mov     [rbp+57h+var_60], r13
0x180066447  mov     [rbp+57h+var_58], r13
0x18006644b  mov     rdi, [rbp+57h+arg_18]
0x18006644f  mov     rax, [rdi]
0x180066452  mov     rbx, [rax+50h]
0x180066456  lea     rcx, [rbp+57h+var_68]
0x18006645a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006645f  or      rax, 0FFFFFFFFFFFFFFFFh
0x180066463  mov     [rbp+57h+var_60], rax
0x180066467  mov     [rbp+57h+var_58], rax
0x18006646b  lea     r8, [rbp+57h+var_68]
0x18006646f  lea     rdx, aTheme; "Theme"
0x180066476  mov     rcx, rdi
0x180066479  mov     rax, rbx
0x18006647c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066481  mov     rdx, [rbp+57h+var_90]; struct IResourceContext *
0x180066485  mov     rcx, [rbp+57h+var_68]; unsigned __int16 *
0x180066489  call    ?OverrideThemeConsideringContrast@@YAXPEBGPEAUIResourceContext@@@Z; OverrideThemeConsideringContrast(ushort const *,IResourceContext *)
0x18006648e  nop
0x18006648f  lea     rcx, [rbp+57h+var_68]
0x180066493  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180066498  nop
0x180066499  lea     rcx, [rbp+57h+arg_18]
0x18006649d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800664a2  nop
0x1800664a3  lea     rcx, [rbp+57h+arg_10]
0x1800664a7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800664ac  jmp     loc_180066556
0x1800664b1  mov     dword ptr [rbp+57h+arg_10], r13d
0x1800664b5  xor     r8d, r8d
0x1800664b8  lea     rdx, [rbp+57h+arg_10]
0x1800664bc  xor     ecx, ecx
0x1800664be  call    cs:__imp_RtlGetDeviceFamilyInfoEnum
0x1800664c4  mov     ecx, dword ptr [rbp+57h+arg_10]
0x1800664c7  lea     eax, [rcx-1]
0x1800664ca  test    eax, 0FFFFFFFDh
0x1800664cf  jz      short loc_1800664E8
0x1800664d1  cmp     ecx, 6
0x1800664d4  jnz     short loc_1800664E3
0x1800664d6  call    cs:__imp_RtlIsMultiSessionSku
0x1800664dc  test    al, al
0x1800664de  jnz     short loc_1800664E8
0x1800664e0  mov     ecx, dword ptr [rbp+57h+arg_10]
0x1800664e3  cmp     ecx, 9
0x1800664e6  jnz     short loc_180066556
0x1800664e8  mov     dword ptr [rbp+57h+arg_10], r13d
0x1800664ec  mov     dword ptr [rbp+57h+arg_18], 4
0x1800664f3  mov     [rbp+57h+pdwType], r13d
0x1800664f7  lea     rax, [rbp+57h+arg_18]
0x1800664fb  mov     [rsp+0D0h+pcbData], rax; pcbData
0x180066500  lea     rax, [rbp+57h+arg_10]
0x180066504  mov     [rsp+0D0h+pvData], rax; pvData
0x180066509  lea     rax, [rbp+57h+pdwType]
0x18006650d  mov     [rsp+0D0h+ppv], rax; int
0x180066512  mov     r9d, 10h; dwFlags
0x180066518  lea     r8, aAppsuselightth; "AppsUseLightTheme"
0x18006651f  lea     rdx, aSoftwareMicros_0; "SOFTWARE\\Microsoft\\Windows\\CurrentVe"...
0x180066526  mov     rcx, 0FFFFFFFF80000001h; hkey
0x18006652d  call    cs:__imp_RegGetValueW
0x180066533  lea     rcx, aLight; "Light"
0x18006653a  test    eax, eax
0x18006653c  jnz     short loc_18006654D
0x18006653e  lea     rdx, aDark; "Dark"
0x180066545  cmp     dword ptr [rbp+57h+arg_10], r13d
0x180066549  cmovz   rcx, rdx; unsigned __int16 *
0x18006654d  mov     rdx, [rbp+57h+var_90]; struct IResourceContext *
0x180066551  call    ?OverrideThemeConsideringContrast@@YAXPEBGPEAUIResourceContext@@@Z; OverrideThemeConsideringContrast(ushort const *,IResourceContext *)
0x180066556  mov     [rbp+57h+var_78], r13
0x18006655a  mov     rdi, [rbp+57h+var_88]
0x18006655e  mov     rax, [rdi]
0x180066561  mov     rbx, [rax+40h]
0x180066565  lea     rcx, [rbp+57h+var_78]
0x180066569  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006656e  lea     r9, [rbp+57h+var_78]
0x180066572  lea     r8, _GUID_6e21e72b_b9b0_42ae_a686_983cf784edcd
0x180066579  lea     rdx, aWindowsUiAccou; "Windows.UI.AccountsControl"
0x180066580  mov     rcx, rdi
0x180066583  mov     rax, rbx
0x180066586  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006658b  mov     rcx, [rbp+5Fh]; this
0x18006658f  test    eax, eax
0x180066591  jns     short loc_1800665A8
0x180066593  mov     r9d, eax; char *
0x180066596  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\accountscontrol\\api"...
0x18006659d  mov     edx, 0C4h; void *
0x1800665a2  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800665a8  mov     [rbp+57h+var_80], r13
0x1800665ac  mov     rdi, [rbp+57h+var_78]
0x1800665b0  mov     rax, [rdi]
0x1800665b3  mov     rbx, [rax+20h]
0x1800665b7  lea     rcx, [rbp+57h+var_80]
0x1800665bb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800665c0  lea     r8, [rbp+57h+var_80]
0x1800665c4  lea     rdx, aFiles; "Files"
0x1800665cb  mov     rcx, rdi
0x1800665ce  mov     rax, rbx
0x1800665d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800665d6  mov     rcx, [rbp+5Fh]; this
0x1800665da  test    eax, eax
0x1800665dc  jns     short loc_1800665F3
0x1800665de  mov     r9d, eax; char *
0x1800665e1  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800665e8  mov     edx, 0C7h; void *
0x1800665ed  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800665f3  mov     rax, [rbp+57h+var_80]
0x1800665f7  mov     [rbp+57h+var_80], r13
0x1800665fb  mov     [r12], rax
0x1800665ff  mov     rax, [rbp+57h+var_90]
0x180066603  mov     [rbp+57h+var_90], r13
0x180066607  mov     [r15], rax
0x18006660a  lea     rcx, [rbp+57h+var_80]
0x18006660e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180066613  nop
0x180066614  lea     rcx, [rbp+57h+var_78]
0x180066618  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18006661d  nop
0x18006661e  lea     rcx, [rbp+57h+var_90]
0x180066622  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180066627  nop
0x180066628  lea     rcx, [rbp+57h+var_88]
0x18006662c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180066631  nop
0x180066632  lea     rcx, [rbp+57h+var_50]
0x180066636  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006663b  mov     rbx, [rsp+0D0h+arg_0]
0x180066643  add     rsp, 0A0h
0x18006664a  pop     r15
0x18006664c  pop     r14
0x18006664e  pop     r13
0x180066650  pop     r12
0x180066652  pop     rdi
0x180066653  pop     rsi
0x180066654  pop     rbp
0x180066655  retn
```
