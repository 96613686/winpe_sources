# CLockScreen::GetHistoryEntryAt(uint,IShellItem * *,IShellItem * *,ushort * *)

- ea: `0x1800358d0`
- end: `0x180035dba`
- name: `?GetHistoryEntryAt@CLockScreen@@UEAAJIPEAPEAUIShellItem@@0PEAPEAG@Z`
- size: `1258`
- prototype: `int(CLockScreen *__hidden this, unsigned int, struct IShellItem **, struct IShellItem **, unsigned __int16 **)`
- caller_count: `0`
- callee_count: `22`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180009f0c`
- `0x18000a910`
- `0x18000ada8`
- `0x18000b0d4`
- `0x18000bb20`
- `0x18000bd60`
- `0x180023fb0`
- `0x18003217c`
- `0x18003395c`
- `0x180034db4`
- `0x1800358d0`
- `0x180035f0c`
- `0x180039c30`
- `0x18003d858`
- `0x1800405f4`
- `0x1800436a8`
- `0x180046c24`
- `0x180049de8`
- `0x1800ae6ac`
- `0x1800b0fa0`
- `0x1800b1c40`
- `0x1800e5010`

## import_xrefs

- `SHELL32!SHCreateItemFromParsingName` at `0x18003598f`
- `SHELL32!SHCreateItemFromParsingName` at `0x180035ac8`
- `SHELL32!SHCreateItemFromParsingName` at `0x180035b95`
- `SHELL32!SHCreateItemFromParsingName` at `0x180035c75`
- `SHELL32!SHCreateItemFromParsingName` at `0x180035d0e`
- `SHELL32!SHCreateItemFromParsingName` at `0x18003598f`
- `SHELL32!SHCreateItemFromParsingName` at `0x180035ac8`
- `SHELL32!SHCreateItemFromParsingName` at `0x180035b95`
- `SHELL32!SHCreateItemFromParsingName` at `0x180035c75`
- `SHELL32!SHCreateItemFromParsingName` at `0x180035d0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035d8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180035d8c`

## string_xrefs

- `0x180035cd0`: `LandscapeAssetPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CLockScreen::GetHistoryEntryAt(
        CLockScreen *this,
        int a2,
        struct IShellItem **a3,
        struct IShellItem **a4,
        const WCHAR *ppv)
{
  CLockScreen *v8; // r12
  unsigned __int16 **v9; // r15
  bool IsSpecificLockScreenLogonImageForced; // al
  bool v11; // dl
  bool v12; // r13
  HRESULT LockScreenHistoryOrderInternal; // edi
  const WCHAR *v14; // rbx
  int Entry; // ebx
  HRESULT v16; // eax
  struct IShellItem *v17; // rcx
  int v18; // eax
  const WCHAR *v19; // rbx
  HRESULT v20; // eax
  struct IShellItem *v21; // rcx
  char v22; // r12
  CLockScreenHistory::CLockScreenHistoryEntry *v23; // rbx
  unsigned int v24; // edx
  void **v25; // rbx
  unsigned __int16 **v26; // r12
  unsigned int v27; // edx
  CLockScreenHistory::CLockScreenHistoryEntry *v28; // rbx
  int v29; // r9d
  struct IShellItem *v30; // rcx
  int v32; // [rsp+20h] [rbp-38h]
  int v33; // [rsp+20h] [rbp-38h]
  unsigned int *v34; // [rsp+28h] [rbp-30h]
  CLockScreenHistory::CLockScreenHistoryEntry *v35; // [rsp+30h] [rbp-28h] BYREF
  PCWSTR v36; // [rsp+38h] [rbp-20h] BYREF
  __int64 v37; // [rsp+40h] [rbp-18h]
  __int64 v38; // [rsp+48h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  void *v42; // [rsp+B0h] [rbp+58h] BYREF
  PCWSTR pszPath; // [rsp+B8h] [rbp+60h] BYREF

  v8 = this;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  v9 = (unsigned __int16 **)ppv;
  if ( ppv )
    *(_QWORD *)ppv = 0;
  pszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pszPath,
    0);
  IsSpecificLockScreenLogonImageForced = CLockScreen::_s_IsSpecificLockScreenLogonImageForced((unsigned __int16 **)&pszPath);
  v12 = IsSpecificLockScreenLogonImageForced;
  if ( a2 )
    goto LABEL_45;
  LockScreenHistoryOrderInternal = 0;
  if ( !IsSpecificLockScreenLogonImageForced )
  {
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
    if ( !CLockScreen::_s_IsSpotlightEnabled(0) )
    {
      if ( CLockScreen::_s_IsSpotlight() )
      {
        if ( a3 )
        {
          v36 = 0;
          v37 = 0;
          v38 = 0;
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
          v37 = -1;
          v38 = -1;
          LockScreenHistoryOrderInternal = SHRegAllocData(
                                             HKEY_CURRENT_USER,
                                             L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen\\Creative",
                                             L"LandscapeAssetPath",
                                             v29,
                                             (void **)&v36,
                                             v34);
          if ( LockScreenHistoryOrderInternal >= 0 )
          {
            ppv = 0;
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
            LockScreenHistoryOrderInternal = SHCreateItemFromParsingName(
                                               v36,
                                               0,
                                               &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                               (void **)&ppv);
            if ( LockScreenHistoryOrderInternal >= 0 )
            {
              v30 = (struct IShellItem *)ppv;
              if ( ppv )
              {
                (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)ppv + 8LL))(ppv);
                v30 = (struct IShellItem *)ppv;
              }
              *a3 = v30;
              LockScreenHistoryOrderInternal = 0;
              if ( a4 )
              {
                ppv = 0;
                *a4 = v30;
              }
            }
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
          }
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
        }
        else
        {
          LockScreenHistoryOrderInternal = -2147024809;
        }
        goto LABEL_71;
      }
      goto LABEL_45;
    }
    if ( !a3 )
    {
      LockScreenHistoryOrderInternal = -2147024809;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9F5,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)0x80070057LL,
        v32);
      goto LABEL_71;
    }
    v36 = 0;
    v37 = 0;
    v38 = 0;
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
    v37 = -1;
    v38 = -1;
    v18 = CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(0, 0, (DWORD *)&v36, 0, 0);
    if ( v18 >= 0 )
    {
      v19 = v36;
      if ( v36 && *v36 )
      {
        v42 = 0;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
        v20 = SHCreateItemFromParsingName(v19, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v42);
        Entry = v20;
        if ( v20 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x9FA,
            (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
            (const char *)(unsigned int)v20,
            v33);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
LABEL_27:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
          goto LABEL_72;
        }
        v21 = (struct IShellItem *)v42;
        if ( v42 )
        {
          (*(void (__fastcall **)(void *))(*(_QWORD *)v42 + 8LL))(v42);
          v21 = (struct IShellItem *)v42;
        }
        *a3 = v21;
        if ( a4 )
        {
          v42 = 0;
          *a4 = v21;
        }
        v22 = 1;
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v42);
        goto LABEL_43;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x9F7,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v18,
        v33);
    }
    ppv = 0;
    Entry = CLockScreenHistory::_GetEntry(
              (CLockScreen *)((char *)v8 + 88),
              0x5Au,
              (struct CLockScreenHistory::CLockScreenHistoryEntry **)&ppv);
    if ( Entry < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA06,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)Entry,
        v33);
      goto LABEL_27;
    }
    v22 = 0;
    v23 = (CLockScreenHistory::CLockScreenHistoryEntry *)ppv;
    LockScreenHistoryOrderInternal = SHCreateItemFromParsingName(
                                       ppv + 289,
                                       0,
                                       &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                       (void **)a3);
    if ( LockScreenHistoryOrderInternal >= 0 )
    {
      if ( a4 )
        CLockScreenHistory::CLockScreenHistoryEntry::GetOriginalFile(v23, a4);
      if ( v9 )
        CLockScreenHistory::CLockScreenHistoryEntry::GetDetails(v23, v9);
      v22 = 1;
    }
    if ( v23 )
      CLockScreenHistory::CLockScreenHistoryEntry::`scalar deleting destructor'(v23, v24);
LABEL_43:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v36);
    if ( v22 )
      goto LABEL_71;
    v8 = this;
LABEL_45:
    CLockScreenHistory::CSynchronizedOperation::CSynchronizedOperation(
      (CLockScreenHistory::CSynchronizedOperation *)&v36,
      v11);
    v25 = (void **)((char *)v8 + 88);
    LockScreenHistoryOrderInternal = CLockScreenHistory::_EnsureCurrentUserSid((CLockScreen *)((char *)v8 + 88));
    if ( LockScreenHistoryOrderInternal < 0 )
      goto LABEL_70;
    ppv = 0;
    LockScreenHistoryOrderInternal = CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(
                                       *v25,
                                       !v12,
                                       (unsigned __int16 **)&ppv);
    if ( LockScreenHistoryOrderInternal < 0 )
      goto LABEL_70;
    v35 = 0;
    v26 = (unsigned __int16 **)ppv;
    LockScreenHistoryOrderInternal = CLockScreenHistory::_GetEntry((CLockScreenHistory *)v25, ppv[a2], &v35);
    if ( LockScreenHistoryOrderInternal < 0 )
    {
LABEL_69:
      CoTaskMemFree(v26);
LABEL_70:
      CLockScreenHistory::CSynchronizedOperation::~CSynchronizedOperation((CLockScreenHistory::CSynchronizedOperation *)&v36);
      goto LABEL_71;
    }
    v28 = v35;
    if ( a3 )
    {
      LockScreenHistoryOrderInternal = SHCreateItemFromParsingName(
                                         (PCWSTR)v35 + 289,
                                         0,
                                         &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe,
                                         (void **)a3);
      if ( LockScreenHistoryOrderInternal < 0 )
      {
LABEL_67:
        if ( v28 )
          CLockScreenHistory::CLockScreenHistoryEntry::`scalar deleting destructor'(v28, v27);
        goto LABEL_69;
      }
    }
    else
    {
      LockScreenHistoryOrderInternal = 0;
    }
    if ( a4 )
      CLockScreenHistory::CLockScreenHistoryEntry::GetOriginalFile(v28, a4);
    if ( v9 )
      CLockScreenHistory::CLockScreenHistoryEntry::GetDetails(v28, v9);
    goto LABEL_67;
  }
  v14 = pszPath;
  if ( pszPath )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
    v16 = SHCreateItemFromParsingName(v14, 0, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&ppv);
    Entry = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x9EB,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v16,
        v32);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
      goto LABEL_72;
    }
    v17 = (struct IShellItem *)ppv;
    if ( ppv )
    {
      (*(void (__fastcall **)(const WCHAR *))(*(_QWORD *)ppv + 8LL))(ppv);
      v17 = (struct IShellItem *)ppv;
    }
    *a3 = v17;
    if ( a4 )
    {
      ppv = 0;
      *a4 = v17;
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppv);
LABEL_71:
    Entry = LockScreenHistoryOrderInternal;
    goto LABEL_72;
  }
  Entry = -2147467261;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9E9,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
    (const char *)0x80004003LL,
    v32);
LABEL_72:
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszPath);
  return (unsigned int)Entry;
}

```

## disassembly

```asm
0x1800358d0  mov     [rsp-40h+arg_8], edx
0x1800358d4  mov     [rsp-40h+arg_0], rcx
0x1800358d9  push    rbp
0x1800358da  push    rbx
0x1800358db  push    rsi
0x1800358dc  push    rdi
0x1800358dd  push    r12
0x1800358df  push    r13
0x1800358e1  push    r14
0x1800358e3  push    r15
0x1800358e5  mov     rbp, rsp
0x1800358e8  sub     rsp, 58h
0x1800358ec  mov     rsi, r9
0x1800358ef  mov     r14, r8
0x1800358f2  mov     ebx, edx
0x1800358f4  mov     r12, rcx
0x1800358f7  xor     edi, edi
0x1800358f9  test    r8, r8
0x1800358fc  jz      short loc_180035901
0x1800358fe  mov     [r8], rdi
0x180035901  test    rsi, rsi
0x180035904  jz      short loc_180035909
0x180035906  mov     [r9], rdi
0x180035909  mov     r15, [rbp+ppv]
0x18003590d  test    r15, r15
0x180035910  jz      short loc_180035915
0x180035912  mov     [r15], rdi
0x180035915  mov     [rbp+pszPath], rdi
0x180035919  xor     edx, edx
0x18003591b  lea     rcx, [rbp+pszPath]
0x18003591f  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180035924  lea     rcx, [rbp+pszPath]; unsigned __int16 **
0x180035928  call    ?_s_IsSpecificLockScreenLogonImageForced@CLockScreen@@KA_NPEAPEAG@Z; CLockScreen::_s_IsSpecificLockScreenLogonImageForced(ushort * *)
0x18003592d  mov     r13b, al
0x180035930  test    ebx, ebx
0x180035932  jnz     loc_180035BE8
0x180035938  xor     ebx, ebx
0x18003593a  mov     edi, ebx
0x18003593c  test    al, al
0x18003593e  jz      loc_1800359F7
0x180035944  mov     rbx, [rbp+pszPath]
0x180035948  xor     r15d, r15d
0x18003594b  test    rbx, rbx
0x18003594e  jnz     short loc_180035972
0x180035950  mov     rcx, [rbp+40h]; this
0x180035954  mov     ebx, 80004003h
0x180035959  mov     r9d, ebx; char *
0x18003595c  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180035963  mov     edx, 9E9h; void *
0x180035968  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003596d  jmp     loc_180035D9E
0x180035972  mov     [rbp+ppv], r15
0x180035976  lea     rcx, [rbp+ppv]
0x18003597a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18003597f  lea     r9, [rbp+ppv]; ppv
0x180035983  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003598a  xor     edx, edx; pbc
0x18003598c  mov     rcx, rbx; pszPath
0x18003598f  call    cs:__imp_SHCreateItemFromParsingName
0x180035995  mov     ebx, eax
0x180035997  test    eax, eax
0x180035999  jns     short loc_1800359C1
0x18003599b  mov     rcx, [rbp+40h]; this
0x18003599f  mov     r9d, eax; char *
0x1800359a2  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x1800359a9  mov     edx, 9EBh; void *
0x1800359ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800359b3  lea     rcx, [rbp+ppv]
0x1800359b7  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800359bc  jmp     loc_180035D9E
0x1800359c1  mov     rcx, [rbp+ppv]
0x1800359c5  test    rcx, rcx
0x1800359c8  jz      short loc_1800359DA
0x1800359ca  mov     rax, [rcx]
0x1800359cd  mov     rax, [rax+8]
0x1800359d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800359d6  mov     rcx, [rbp+ppv]
0x1800359da  mov     [r14], rcx
0x1800359dd  test    rsi, rsi
0x1800359e0  jz      short loc_1800359E9
0x1800359e2  mov     [rbp+ppv], r15
0x1800359e6  mov     [rsi], rcx
0x1800359e9  lea     rcx, [rbp+ppv]
0x1800359ed  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800359f2  jmp     loc_180035D9C
0x1800359f7  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x1800359fe  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x180035a03  xor     ecx, ecx; this
0x180035a05  call    ?_s_IsSpotlightEnabled@CLockScreen@@KA_NPEBG@Z; CLockScreen::_s_IsSpotlightEnabled(ushort const *)
0x180035a0a  test    al, al
0x180035a0c  jz      loc_180035C8A
0x180035a12  test    r14, r14
0x180035a15  jnz     short loc_180035A39
0x180035a17  mov     rcx, [rbp+40h]; this
0x180035a1b  mov     edi, 80070057h
0x180035a20  mov     r9d, edi; char *
0x180035a23  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180035a2a  mov     edx, 9F5h; void *
0x180035a2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035a34  jmp     loc_180035D9C
0x180035a39  mov     [rbp+var_20], rbx
0x180035a3d  mov     [rbp+var_18], rbx
0x180035a41  mov     [rbp+var_10], rbx
0x180035a45  lea     rcx, [rbp+var_20]
0x180035a49  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180035a4e  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035a52  mov     [rbp+var_18], rax
0x180035a56  mov     [rbp+var_10], rax
0x180035a5a  mov     [rsp+58h+var_38], rbx; int
0x180035a5f  xor     r9d, r9d; unsigned __int16 **
0x180035a62  lea     r8, [rbp+var_20]; unsigned __int16 **
0x180035a66  xor     edx, edx; unsigned __int16 *
0x180035a68  xor     ecx, ecx; this
0x180035a6a  call    ?PeekLockScreenRegistryKeys@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEAPEAG11PEA_N@Z; CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(ushort const *,ushort * *,ushort * *,ushort * *,bool *)
0x180035a6f  mov     rcx, [rbp+40h]; this
0x180035a73  test    eax, eax
0x180035a75  jns     short loc_180035A90
0x180035a77  mov     r9d, eax; char *
0x180035a7a  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180035a81  mov     edx, 9F7h; void *
0x180035a86  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180035a8b  jmp     loc_180035B3F
0x180035a90  mov     rbx, [rbp+var_20]
0x180035a94  xor     eax, eax
0x180035a96  test    rbx, rbx
0x180035a99  jz      loc_180035B3D
0x180035a9f  cmp     [rbx], ax
0x180035aa2  jz      loc_180035B3D
0x180035aa8  xor     r12d, r12d
0x180035aab  mov     [rbp+arg_10], r12
0x180035aaf  lea     rcx, [rbp+arg_10]
0x180035ab3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035ab8  lea     r9, [rbp+arg_10]; ppv
0x180035abc  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180035ac3  xor     edx, edx; pbc
0x180035ac5  mov     rcx, rbx; pszPath
0x180035ac8  call    cs:__imp_SHCreateItemFromParsingName
0x180035ace  mov     ebx, eax
0x180035ad0  test    eax, eax
0x180035ad2  jns     short loc_180035B04
0x180035ad4  mov     rcx, [rbp+40h]; this
0x180035ad8  mov     r9d, eax; char *
0x180035adb  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180035ae2  mov     edx, 9FAh; void *
0x180035ae7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035aec  lea     rcx, [rbp+arg_10]
0x180035af0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035af5  nop
0x180035af6  lea     rcx, [rbp+var_20]
0x180035afa  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180035aff  jmp     loc_180035D9E
0x180035b04  mov     rcx, [rbp+arg_10]
0x180035b08  test    rcx, rcx
0x180035b0b  jz      short loc_180035B1D
0x180035b0d  mov     rax, [rcx]
0x180035b10  mov     rax, [rax+8]
0x180035b14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035b19  mov     rcx, [rbp+arg_10]
0x180035b1d  mov     [r14], rcx
0x180035b20  test    rsi, rsi
0x180035b23  jz      short loc_180035B2C
0x180035b25  mov     [rbp+arg_10], r12
0x180035b29  mov     [rsi], rcx
0x180035b2c  mov     r12b, 1
0x180035b2f  lea     rcx, [rbp+arg_10]
0x180035b33  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035b38  jmp     loc_180035BD2
0x180035b3d  xor     ebx, ebx
0x180035b3f  mov     [rbp+ppv], rbx
0x180035b43  mov     edx, 5Ah ; 'Z'; unsigned __int16
0x180035b48  lea     rcx, [r12+58h]; this
0x180035b4d  lea     r8, [rbp+ppv]; struct CLockScreenHistory::CLockScreenHistoryEntry **
0x180035b51  call    ?_GetEntry@CLockScreenHistory@@IEAAJGPEAPEAVCLockScreenHistoryEntry@1@@Z; CLockScreenHistory::_GetEntry(ushort,CLockScreenHistory::CLockScreenHistoryEntry * *)
0x180035b56  mov     ebx, eax
0x180035b58  xor     eax, eax
0x180035b5a  test    ebx, ebx
0x180035b5c  jns     short loc_180035B7B
0x180035b5e  mov     rcx, [rbp+40h]; this
0x180035b62  mov     r9d, ebx; char *
0x180035b65  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180035b6c  mov     edx, 0A06h; void *
0x180035b71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180035b76  jmp     loc_180035AF6
0x180035b7b  mov     r12b, al
0x180035b7e  mov     rbx, [rbp+ppv]
0x180035b82  lea     rcx, [rbx+242h]; pszPath
0x180035b89  mov     r9, r14; ppv
0x180035b8c  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180035b93  xor     edx, edx; pbc
0x180035b95  call    cs:__imp_SHCreateItemFromParsingName
0x180035b9b  mov     edi, eax
0x180035b9d  test    eax, eax
0x180035b9f  js      short loc_180035BC4
0x180035ba1  test    rsi, rsi
0x180035ba4  jz      short loc_180035BB1
0x180035ba6  mov     rdx, rsi; struct IShellItem **
0x180035ba9  mov     rcx, rbx; this
0x180035bac  call    ?GetOriginalFile@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJPEAPEAUIShellItem@@@Z; CLockScreenHistory::CLockScreenHistoryEntry::GetOriginalFile(IShellItem * *)
0x180035bb1  test    r15, r15
0x180035bb4  jz      short loc_180035BC1
0x180035bb6  mov     rdx, r15; unsigned __int16 **
0x180035bb9  mov     rcx, rbx; this
0x180035bbc  call    ?GetDetails@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJPEAPEAG@Z; CLockScreenHistory::CLockScreenHistoryEntry::GetDetails(ushort * *)
0x180035bc1  mov     r12b, 1
0x180035bc4  test    rbx, rbx
0x180035bc7  jz      short loc_180035BD2
0x180035bc9  mov     rcx, rbx; this
0x180035bcc  call    ??_GCLockScreenHistoryEntry@CLockScreenHistory@@QEAAPEAXI@Z; CLockScreenHistory::CLockScreenHistoryEntry::`scalar deleting destructor'(uint)
0x180035bd1  nop
0x180035bd2  lea     rcx, [rbp+var_20]
0x180035bd6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180035bdb  test    r12b, r12b
0x180035bde  jnz     loc_180035D9C
0x180035be4  mov     r12, [rbp+arg_0]
0x180035be8  lea     rcx, [rbp+var_20]; this
0x180035bec  call    ??0CSynchronizedOperation@CLockScreenHistory@@QEAA@_N@Z; CLockScreenHistory::CSynchronizedOperation::CSynchronizedOperation(bool)
0x180035bf1  nop
0x180035bf2  lea     rbx, [r12+58h]
0x180035bf7  mov     rcx, rbx; this
0x180035bfa  call    ?_EnsureCurrentUserSid@CLockScreenHistory@@IEAAJXZ; CLockScreenHistory::_EnsureCurrentUserSid(void)
0x180035bff  mov     edi, eax
0x180035c01  xor     eax, eax
0x180035c03  test    edi, edi
0x180035c05  js      loc_180035D93
0x180035c0b  mov     [rbp+ppv], rax
0x180035c0f  xor     r13b, 1
0x180035c13  lea     r8, [rbp+ppv]; unsigned __int16 **
0x180035c17  mov     dl, r13b; bool
0x180035c1a  mov     rcx, [rbx]; void *
0x180035c1d  call    ?_s_GetLockScreenHistoryOrderInternal@CLockScreenHistory@@KAJPEAX_NPEAPEAG@Z; CLockScreenHistory::_s_GetLockScreenHistoryOrderInternal(void *,bool,ushort * *)
0x180035c22  mov     edi, eax
0x180035c24  xor     r13d, r13d
0x180035c27  test    eax, eax
0x180035c29  js      loc_180035D93
0x180035c2f  mov     [rbp+var_28], r13
0x180035c33  mov     edx, [rbp+arg_8]
0x180035c36  lea     r8, [rbp+var_28]; struct CLockScreenHistory::CLockScreenHistoryEntry **
0x180035c3a  mov     r12, [rbp+ppv]
0x180035c3e  movzx   edx, word ptr [r12+rdx*2]; unsigned __int16
0x180035c43  mov     rcx, rbx; this
0x180035c46  call    ?_GetEntry@CLockScreenHistory@@IEAAJGPEAPEAVCLockScreenHistoryEntry@1@@Z; CLockScreenHistory::_GetEntry(ushort,CLockScreenHistory::CLockScreenHistoryEntry * *)
0x180035c4b  mov     edi, eax
0x180035c4d  test    eax, eax
0x180035c4f  js      loc_180035D89
0x180035c55  mov     rbx, [rbp+var_28]
0x180035c59  test    r14, r14
0x180035c5c  jz      loc_180035D59
0x180035c62  lea     rcx, [rbx+242h]; pszPath
0x180035c69  mov     r9, r14; ppv
0x180035c6c  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180035c73  xor     edx, edx; pbc
0x180035c75  call    cs:__imp_SHCreateItemFromParsingName
0x180035c7b  mov     edi, eax
0x180035c7d  test    eax, eax
0x180035c7f  js      loc_180035D7C
0x180035c85  jmp     loc_180035D5C
0x180035c8a  call    ?_s_IsSpotlight@CLockScreen@@KA_NXZ; CLockScreen::_s_IsSpotlight(void)
0x180035c8f  test    al, al
0x180035c91  jz      loc_180035BE8
0x180035c97  test    r14, r14
0x180035c9a  jnz     short loc_180035CA6
0x180035c9c  mov     edi, 80070057h
0x180035ca1  jmp     loc_180035D9C
0x180035ca6  mov     [rbp+var_20], rbx
0x180035caa  mov     [rbp+var_18], rbx
0x180035cae  mov     [rbp+var_10], rbx
0x180035cb2  lea     rcx, [rbp+var_20]
0x180035cb6  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180035cbb  or      rax, 0FFFFFFFFFFFFFFFFh
0x180035cbf  mov     [rbp+var_18], rax
0x180035cc3  mov     [rbp+var_10], rax
0x180035cc7  lea     rax, [rbp+var_20]
0x180035ccb  mov     [rsp+58h+var_38], rax; void **
0x180035cd0  lea     r8, ?c_landscapeAssetPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "LandscapeAssetPath"
0x180035cd7  lea     rdx, ?c_lockScreenCreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180035cde  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180035ce5  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x180035cea  mov     edi, eax
0x180035cec  test    eax, eax
0x180035cee  js      short loc_180035D4E
0x180035cf0  mov     [rbp+ppv], rbx
0x180035cf4  lea     rcx, [rbp+ppv]
0x180035cf8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180035cfd  lea     r9, [rbp+ppv]; ppv
0x180035d01  lea     r8, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180035d08  xor     edx, edx; pbc
0x180035d0a  mov     rcx, [rbp+var_20]; pszPath
0x180035d0e  call    cs:__imp_SHCreateItemFromParsingName
0x180035d14  mov     edi, eax
0x180035d16  test    eax, eax
0x180035d18  js      short loc_180035D44
0x180035d1a  mov     rcx, [rbp+ppv]
0x180035d1e  test    rcx, rcx
0x180035d21  jz      short loc_180035D33
0x180035d23  mov     rax, [rcx]
0x180035d26  mov     rax, [rax+8]
0x180035d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035d2f  mov     rcx, [rbp+ppv]
0x180035d33  mov     [r14], rcx
0x180035d36  mov     edi, ebx
  ... truncated ...
```
