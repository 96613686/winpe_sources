# SystemSettings::StorageSenseHandlers::CAppPackageList::_IsSystemComponent(Windows::Internal::StateRepository::IPackage *,uchar &)

- ea: `0x1800aeacc`
- end: `0x1800aee8d`
- name: `?_IsSystemComponent@CAppPackageList@StorageSenseHandlers@SystemSettings@@IEAAJPEAUIPackage@StateRepository@Internal@Windows@@AEAE@Z`
- size: `961`
- prototype: `__int64 __fastcall(SystemSettings::StorageSenseHandlers::CAppPackageList *__hidden this, struct Windows::Internal::StateRepository::IPackage *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `12`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ad684`

## callees

- `0x180006e50`
- `0x180007a00`
- `0x18000c964`
- `0x18000e6cc`
- `0x18003b450`
- `0x18005abf0`
- `0x18005d26c`
- `0x1800a1234`
- `0x1800a2ec8`
- `0x1800aeacc`
- `0x1800afdd8`
- `0x1800e3010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aeb90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aee0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aee4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aeb90`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aee0c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800aee4b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aebe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aec0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aecb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aedd6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aebe5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aec0a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aecb1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800aedd6`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800aec9c`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800aedc5`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800aec9c`
- `api-ms-win-appmodel-runtime-l1-1-1!ParseApplicationUserModelId` at `0x1800aedc5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800aebf5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800aec1a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800aecbf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800aecf4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800aede4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800aebf5`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800aec1a`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800aecbf`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800aecf4`
- `api-ms-win-core-shlwapi-obsolete-l1-1-0!StrCmpIW` at `0x1800aede4`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SystemSettings::StorageSenseHandlers::CAppPackageList::_IsSystemComponent(
        SystemSettings::StorageSenseHandlers::CAppPackageList *this,
        struct Windows::Internal::StateRepository::IPackage *a2,
        bool *a3)
{
  int v6; // eax
  unsigned int v7; // ebx
  __int64 (__fastcall *v8)(struct Windows::Internal::StateRepository::IPackage *, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdx
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, HSTRING *); // rbx
  const WCHAR *v13; // rax
  const WCHAR *v14; // rax
  const struct ShellLists::SystemCategorizationOverrideEntry near *const *v15; // rbx
  unsigned int v16; // eax
  const WCHAR *v17; // rax
  unsigned int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  __int64 v21; // rdx
  const struct ShellLists::SystemCategorizationOverrideEntry near *const *v22; // rbx
  const WCHAR *StringRawBuffer; // rax
  int packageRelativeApplicationId; // [rsp+20h] [rbp-E0h]
  wil::reg::reg_view_details *packageRelativeApplicationIda; // [rsp+20h] [rbp-E0h]
  HSTRING string; // [rsp+30h] [rbp-D0h] BYREF
  UINT32 packageRelativeApplicationIdLength; // [rsp+38h] [rbp-C8h] BYREF
  UINT32 packageFamilyNameLength; // [rsp+3Ch] [rbp-C4h] BYREF
  __int64 v30; // [rsp+40h] [rbp-C0h] BYREF
  HKEY v31; // [rsp+48h] [rbp-B8h] BYREF
  int v32; // [rsp+50h] [rbp-B0h] BYREF
  char v33; // [rsp+54h] [rbp-ACh]
  int v34[2]; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR packageFamilyName[72]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR v36[72]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+A8h]

  *a3 = 0;
  v6 = (*(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, bool *))(*(_QWORD *)a2 + 120LL))(
         a2,
         a3);
  v7 = v6;
  if ( v6 >= 0 )
  {
    v30 = 0;
    string = 0;
    v8 = *(__int64 (__fastcall **)(struct Windows::Internal::StateRepository::IPackage *, __int64 *))(*(_QWORD *)a2 + 72LL);
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
    v9 = v8(a2, &v30);
    v7 = v9;
    if ( v9 < 0 )
    {
      v10 = 452;
LABEL_7:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
        (const char *)(unsigned int)v9,
        packageRelativeApplicationId);
LABEL_31:
      WindowsDeleteString(string);
      string = 0;
      Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
      return v7;
    }
    v11 = v30;
    v12 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 88LL);
    WindowsDeleteString(string);
    string = 0;
    v9 = v12(v11, &string);
    v7 = v9;
    if ( v9 < 0 )
    {
      v10 = 453;
      goto LABEL_7;
    }
    if ( !*a3 )
    {
      v22 = &ShellLists::s_packagedAppSystemCategorizationOverrides;
      while ( 1 )
      {
        memset_0(packageFamilyName, 0, 0x82u);
        packageRelativeApplicationIdLength = 65;
        memset_0(v36, 0, 0x84u);
        packageFamilyNameLength = 66;
        v16 = ParseApplicationUserModelId(
                *(PCWSTR *)v22,
                &packageRelativeApplicationIdLength,
                packageFamilyName,
                &packageFamilyNameLength,
                v36);
        if ( v16 )
          break;
        StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
        if ( !StrCmpIW(packageFamilyName, StringRawBuffer) )
          *a3 = *((_BYTE *)v22 + 8);
        v22 += 2;
        if ( v22 == (const struct ShellLists::SystemCategorizationOverrideEntry near *const *)&off_1800FDE30 )
          goto LABEL_28;
      }
      v21 = 528;
LABEL_30:
      v7 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)v21,
             (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
             (const char *)v16,
             (unsigned int)packageRelativeApplicationIda);
      goto LABEL_31;
    }
    v13 = WindowsGetStringRawBuffer(string, 0);
    if ( StrCmpIW(v13, L"Microsoft.MicrosoftEdge_8wekyb3d8bbwe") )
    {
      v14 = WindowsGetStringRawBuffer(string, 0);
      if ( !StrCmpIW(v14, L"Microsoft.MicrosoftEdge_8wekyb3d8bbwe") || (*((_BYTE *)this + 32) & 8) == 0 )
        goto LABEL_28;
      if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemComponentsWindowsFeatureExperiencePack>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SystemComponentsWindowsFeatureExperiencePack>::GetImpl'::`2'::impl) )
      {
        v15 = &ShellLists::s_packagedInboxAppSystemCategorizationOverrides;
        while ( 1 )
        {
          memset_0(packageFamilyName, 0, 0x82u);
          packageFamilyNameLength = 65;
          memset_0(v36, 0, 0x84u);
          packageRelativeApplicationIdLength = 66;
          v16 = ParseApplicationUserModelId(
                  *(PCWSTR *)v15,
                  &packageFamilyNameLength,
                  packageFamilyName,
                  &packageRelativeApplicationIdLength,
                  v36);
          if ( v16 )
          {
            v21 = 479;
            goto LABEL_30;
          }
          v17 = WindowsGetStringRawBuffer(string, 0);
          if ( !StrCmpIW(packageFamilyName, v17) )
            break;
          v15 += 2;
          if ( v15 == (const struct ShellLists::SystemCategorizationOverrideEntry near *const *)&WINRT_version )
            goto LABEL_17;
        }
        *a3 = *((_BYTE *)v15 + 8);
        if ( !StrCmpIW(*(PCWSTR *)v15, L"MicrosoftWindows.Client.CoreAI_cw5n1h2txyewy!ClickToDoApp") )
        {
          v31 = 0;
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
            &v31,
            0);
          if ( CreateShellSessionKey(v18, &v31) >= 0 )
          {
            *(_QWORD *)v34 = v31;
            LODWORD(packageRelativeApplicationIda) = 16;
            wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<unsigned int>(
              (int)v34,
              (int)&v32,
              v19,
              v20,
              packageRelativeApplicationIda);
            *a3 = (v33 != 0 ? v32 : 0) == 0;
          }
          wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
        }
        goto LABEL_28;
      }
    }
LABEL_17:
    *a3 = 0;
LABEL_28:
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(&v30);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x1C0,
    (unsigned int)"onecoreuap\\shell\\coresettinghandlers\\storagesense\\lib\\applisthelper.cpp",
    (const char *)(unsigned int)v6,
    packageRelativeApplicationId);
  return v7;
}

```

## disassembly

```asm
0x1800aeacc  mov     [rsp-8+arg_0], rbx
0x1800aead1  mov     [rsp-8+arg_18], rsi
0x1800aead6  push    rbp
0x1800aead7  push    rdi
0x1800aead8  push    r14
0x1800aeada  lea     rbp, [rsp-90h]
0x1800aeae2  sub     rsp, 190h
0x1800aeae9  mov     rax, cs:__security_cookie
0x1800aeaf0  xor     rax, rsp
0x1800aeaf3  mov     [rbp+0A0h+var_20], rax
0x1800aeafa  mov     rsi, r8
0x1800aeafd  mov     rdi, rdx
0x1800aeb00  mov     r14, rcx
0x1800aeb03  mov     byte ptr [r8], 0
0x1800aeb07  mov     rax, [rdx]
0x1800aeb0a  mov     rdx, r8
0x1800aeb0d  mov     rcx, rdi
0x1800aeb10  mov     rax, [rax+78h]
0x1800aeb14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb19  mov     ebx, eax
0x1800aeb1b  test    eax, eax
0x1800aeb1d  jns     short loc_1800AEB3F
0x1800aeb1f  mov     rcx, [rbp+0A8h]; this
0x1800aeb26  mov     r9d, eax; char *
0x1800aeb29  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800aeb30  mov     edx, 1C0h; void *
0x1800aeb35  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aeb3a  jmp     loc_1800AEE64
0x1800aeb3f  mov     [rsp+1A0h+var_160], 0
0x1800aeb48  mov     [rsp+1A0h+string], 0
0x1800aeb51  mov     rax, [rdi]
0x1800aeb54  mov     rbx, [rax+48h]
0x1800aeb58  lea     rcx, [rsp+1A0h+var_160]
0x1800aeb5d  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aeb62  lea     rdx, [rsp+1A0h+var_160]
0x1800aeb67  mov     rcx, rdi
0x1800aeb6a  mov     rax, rbx
0x1800aeb6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aeb72  mov     ebx, eax
0x1800aeb74  test    eax, eax
0x1800aeb76  jns     short loc_1800AEB7F
0x1800aeb78  mov     edx, 1C4h
0x1800aeb7d  jmp     short loc_1800AEBBA
0x1800aeb7f  mov     rdi, [rsp+1A0h+var_160]
0x1800aeb84  mov     rax, [rdi]
0x1800aeb87  mov     rbx, [rax+58h]
0x1800aeb8b  mov     rcx, [rsp+1A0h+string]; string
0x1800aeb90  call    cs:__imp_WindowsDeleteString
0x1800aeb96  mov     [rsp+1A0h+string], 0
0x1800aeb9f  lea     rdx, [rsp+1A0h+string]
0x1800aeba4  mov     rcx, rdi
0x1800aeba7  mov     rax, rbx
0x1800aebaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aebaf  mov     ebx, eax
0x1800aebb1  test    eax, eax
0x1800aebb3  jns     short loc_1800AEBD5
0x1800aebb5  mov     edx, 1C5h; void *
0x1800aebba  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800aebc1  mov     r9d, eax; char *
0x1800aebc4  mov     rcx, [rbp+0A8h]; this
0x1800aebcb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aebd0  jmp     loc_1800AEE46
0x1800aebd5  cmp     byte ptr [rsi], 0
0x1800aebd8  jz      loc_1800AED70
0x1800aebde  xor     edx, edx; length
0x1800aebe0  mov     rcx, [rsp+1A0h+string]; string
0x1800aebe5  call    cs:__imp_WindowsGetStringRawBuffer
0x1800aebeb  lea     rdx, aMicrosoftMicro_0; "Microsoft.MicrosoftEdge_8wekyb3d8bbwe"
0x1800aebf2  mov     rcx, rax; psz1
0x1800aebf5  call    cs:__imp_StrCmpIW
0x1800aebfb  test    eax, eax
0x1800aebfd  jz      loc_1800AECDD
0x1800aec03  xor     edx, edx; length
0x1800aec05  mov     rcx, [rsp+1A0h+string]; string
0x1800aec0a  call    cs:__imp_WindowsGetStringRawBuffer
0x1800aec10  lea     rdx, aMicrosoftMicro_0; "Microsoft.MicrosoftEdge_8wekyb3d8bbwe"
0x1800aec17  mov     rcx, rax; psz1
0x1800aec1a  call    cs:__imp_StrCmpIW
0x1800aec20  test    eax, eax
0x1800aec22  jz      loc_1800AEE07
0x1800aec28  test    byte ptr [r14+20h], 8
0x1800aec2d  jz      loc_1800AEE07
0x1800aec33  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SystemComponentsWindowsFeatureExperiencePack@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SystemComponentsWindowsFeatureExperiencePack@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemComponentsWindowsFeatureExperiencePack> `wil::Feature<__WilFeatureTraits_Feature_SystemComponentsWindowsFeatureExperiencePack>::GetImpl(void)'::`2'::impl
0x1800aec3a  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SystemComponentsWindowsFeatureExperiencePack@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SystemComponentsWindowsFeatureExperiencePack>::__private_IsEnabled(void)
0x1800aec3f  test    al, al
0x1800aec41  jz      loc_1800AECDD
0x1800aec47  lea     rbx, ?s_packagedInboxAppSystemCategorizationOverrides@ShellLists@@3QBUSystemCategorizationOverrideEntry@1@B; ShellLists::SystemCategorizationOverrideEntry const near * const ShellLists::s_packagedInboxAppSystemCategorizationOverrides
0x1800aec4e  xor     edx, edx; Val
0x1800aec50  mov     r8d, 82h; Size
0x1800aec56  lea     rcx, [rsp+1A0h+packageFamilyName]; void *
0x1800aec5b  call    memset_0
0x1800aec60  mov     [rsp+1A0h+packageFamilyNameLength], 41h ; 'A'
0x1800aec68  xor     edx, edx; Val
0x1800aec6a  mov     r8d, 84h; Size
0x1800aec70  lea     rcx, [rbp+0A0h+var_B0]; void *
0x1800aec74  call    memset_0
0x1800aec79  mov     [rsp+1A0h+packageRelativeApplicationIdLength], 42h ; 'B'
0x1800aec81  lea     rax, [rbp+0A0h+var_B0]
0x1800aec85  mov     [rsp+1A0h+packageRelativeApplicationId], rax; packageRelativeApplicationId
0x1800aec8a  lea     r9, [rsp+1A0h+packageRelativeApplicationIdLength]; packageRelativeApplicationIdLength
0x1800aec8f  lea     r8, [rsp+1A0h+packageFamilyName]; packageFamilyName
0x1800aec94  lea     rdx, [rsp+1A0h+packageFamilyNameLength]; packageFamilyNameLength
0x1800aec99  mov     rcx, [rbx]; applicationUserModelId
0x1800aec9c  call    cs:__imp_ParseApplicationUserModelId
0x1800aeca2  test    eax, eax
0x1800aeca4  jnz     loc_1800AED66
0x1800aecaa  xor     edx, edx; length
0x1800aecac  mov     rcx, [rsp+1A0h+string]; string
0x1800aecb1  call    cs:__imp_WindowsGetStringRawBuffer
0x1800aecb7  mov     rdx, rax; psz2
0x1800aecba  lea     rcx, [rsp+1A0h+packageFamilyName]; psz1
0x1800aecbf  call    cs:__imp_StrCmpIW
0x1800aecc5  test    eax, eax
0x1800aecc7  jz      short loc_1800AECE5
0x1800aecc9  add     rbx, 10h
0x1800aeccd  lea     rax, WINRT_version
0x1800aecd4  cmp     rbx, rax
0x1800aecd7  jnz     loc_1800AEC4E
0x1800aecdd  mov     byte ptr [rsi], 0
0x1800aece0  jmp     loc_1800AEE07
0x1800aece5  mov     al, [rbx+8]
0x1800aece8  mov     [rsi], al
0x1800aecea  lea     rdx, aMicrosoftwindo_2; "MicrosoftWindows.Client.CoreAI_cw5n1h2t"...
0x1800aecf1  mov     rcx, [rbx]; psz1
0x1800aecf4  call    cs:__imp_StrCmpIW
0x1800aecfa  test    eax, eax
0x1800aecfc  jnz     loc_1800AEE07
0x1800aed02  mov     [rsp+1A0h+var_158], 0
0x1800aed0b  xor     edx, edx
0x1800aed0d  lea     rcx, [rsp+1A0h+var_158]
0x1800aed12  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x1800aed17  lea     rdx, [rsp+1A0h+var_158]; HKEY *
0x1800aed1c  call    ?CreateShellSessionKey@@YAJKPEAPEAUHKEY__@@@Z; CreateShellSessionKey(ulong,HKEY__ * *)
0x1800aed21  test    eax, eax
0x1800aed23  js      short loc_1800AED57
0x1800aed25  mov     rax, [rsp+1A0h+var_158]
0x1800aed2a  mov     qword ptr [rsp+1A0h+var_148], rax
0x1800aed2f  mov     dword ptr [rsp+1A0h+packageRelativeApplicationId], 10h; wil::reg::reg_view_details *
0x1800aed37  lea     rdx, [rsp+1A0h+var_150]; int
0x1800aed3c  lea     rcx, [rsp+1A0h+var_148]; int
0x1800aed41  call    ??$try_get_value@I@?$reg_view_t@Uerr_exception_policy@wil@@@reg_view_details@reg@wil@@QEBA?AV?$optional@I@std@@PEBG0K@Z; wil::reg::reg_view_details::reg_view_t<wil::err_exception_policy>::try_get_value<uint>(ushort const *,ushort const *,ulong)
0x1800aed46  mov     al, [rsp+1A0h+var_14C]
0x1800aed4a  neg     al
0x1800aed4c  sbb     ecx, ecx
0x1800aed4e  and     ecx, [rsp+1A0h+var_150]
0x1800aed52  setz    al
0x1800aed55  mov     [rsi], al
0x1800aed57  lea     rcx, [rsp+1A0h+var_158]
0x1800aed5c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800aed61  jmp     loc_1800AEE07
0x1800aed66  mov     edx, 1DFh
0x1800aed6b  jmp     loc_1800AEE2E
0x1800aed70  lea     rbx, ?s_packagedAppSystemCategorizationOverrides@ShellLists@@3QBUSystemCategorizationOverrideEntry@1@B; ShellLists::SystemCategorizationOverrideEntry const near * const ShellLists::s_packagedAppSystemCategorizationOverrides
0x1800aed77  xor     edx, edx; Val
0x1800aed79  mov     r8d, 82h; Size
0x1800aed7f  lea     rcx, [rsp+1A0h+packageFamilyName]; void *
0x1800aed84  call    memset_0
0x1800aed89  mov     [rsp+1A0h+packageRelativeApplicationIdLength], 41h ; 'A'
0x1800aed91  xor     edx, edx; Val
0x1800aed93  mov     r8d, 84h; Size
0x1800aed99  lea     rcx, [rbp+0A0h+var_B0]; void *
0x1800aed9d  call    memset_0
0x1800aeda2  mov     [rsp+1A0h+packageFamilyNameLength], 42h ; 'B'
0x1800aedaa  lea     rax, [rbp+0A0h+var_B0]
0x1800aedae  mov     [rsp+1A0h+packageRelativeApplicationId], rax; unsigned int
0x1800aedb3  lea     r9, [rsp+1A0h+packageFamilyNameLength]; packageRelativeApplicationIdLength
0x1800aedb8  lea     r8, [rsp+1A0h+packageFamilyName]; packageFamilyName
0x1800aedbd  lea     rdx, [rsp+1A0h+packageRelativeApplicationIdLength]; packageFamilyNameLength
0x1800aedc2  mov     rcx, [rbx]; applicationUserModelId
0x1800aedc5  call    cs:__imp_ParseApplicationUserModelId
0x1800aedcb  test    eax, eax
0x1800aedcd  jnz     short loc_1800AEE29
0x1800aedcf  xor     edx, edx; length
0x1800aedd1  mov     rcx, [rsp+1A0h+string]; string
0x1800aedd6  call    cs:__imp_WindowsGetStringRawBuffer
0x1800aeddc  mov     rdx, rax; psz2
0x1800aeddf  lea     rcx, [rsp+1A0h+packageFamilyName]; psz1
0x1800aede4  call    cs:__imp_StrCmpIW
0x1800aedea  test    eax, eax
0x1800aedec  jnz     short loc_1800AEDF3
0x1800aedee  mov     al, [rbx+8]
0x1800aedf1  mov     [rsi], al
0x1800aedf3  add     rbx, 10h
0x1800aedf7  lea     rax, off_1800FDE30; "SystemSettings_StorageSense_SystemCompo"...
0x1800aedfe  cmp     rbx, rax
0x1800aee01  jnz     loc_1800AED77
0x1800aee07  mov     rcx, [rsp+1A0h+string]; string
0x1800aee0c  call    cs:__imp_WindowsDeleteString
0x1800aee12  mov     [rsp+1A0h+string], 0
0x1800aee1b  lea     rcx, [rsp+1A0h+var_160]
0x1800aee20  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aee25  xor     eax, eax
0x1800aee27  jmp     short loc_1800AEE66
0x1800aee29  mov     edx, 210h; void *
0x1800aee2e  mov     r9d, eax; char *
0x1800aee31  lea     r8, aOnecoreuapShel_14; "onecoreuap\\shell\\coresettinghandlers"...
0x1800aee38  mov     rcx, [rbp+0A8h]; this
0x1800aee3f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800aee44  mov     ebx, eax
0x1800aee46  mov     rcx, [rsp+1A0h+string]; string
0x1800aee4b  call    cs:__imp_WindowsDeleteString
0x1800aee51  mov     [rsp+1A0h+string], 0
0x1800aee5a  lea     rcx, [rsp+1A0h+var_160]
0x1800aee5f  call    ?InternalRelease@?$ComPtr@UIConfigurePopupProperty@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IConfigurePopupProperty>::InternalRelease(void)
0x1800aee64  mov     eax, ebx
0x1800aee66  mov     rcx, [rbp+0A0h+var_20]
0x1800aee6d  xor     rcx, rsp; StackCookie
0x1800aee70  call    __security_check_cookie
0x1800aee75  lea     r11, [rsp+1A0h+var_10]
0x1800aee7d  mov     rbx, [r11+20h]
0x1800aee81  mov     rsi, [r11+38h]
0x1800aee85  mov     rsp, r11
0x1800aee88  pop     r14
0x1800aee8a  pop     rdi
0x1800aee8b  pop     rbp
0x1800aee8c  retn
```
