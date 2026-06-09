# GetCatalogCacheItemDeleteThresholdFromOneSettings(void)

- ea: `0x18003b300`
- end: `0x18003b551`
- name: `?GetCatalogCacheItemDeleteThresholdFromOneSettings@@YA_JXZ`
- size: `593`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801b0548`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001af10`
- `0x1800252e8`
- `0x180034328`
- `0x18003b300`
- `0x180044cb8`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003b47a`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003b47a`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003b340`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003b340`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b412`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b48b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b4bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b50a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b412`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b48b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b4bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b50a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b46b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b46b`

## string_xrefs

- `0x18003b4f3`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003b3d1`: `SCCINSTALLSVC`
- `0x18003b434`: `CATALOGCACHEITEMDELETETHRESHOLDINHOURS`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 GetCatalogCacheItemDeleteThresholdFromOneSettings(void)
{
  int v1; // eax
  __int64 v2; // rdi
  __int64 (__fastcall *v3)(__int64, __int64, __int64 *); // rbx
  __int64 v4; // rdi
  __int64 (__fastcall *v5)(__int64, __int64, HSTRING *); // rbx
  const wchar_t *StringRawBuffer; // rax
  unsigned int v7; // eax
  __int64 v8; // rbx
  int v9; // [rsp+20h] [rbp-68h]
  HSTRING string; // [rsp+40h] [rbp-48h] BYREF
  __int64 v11; // [rsp+48h] [rbp-40h] BYREF
  __int64 v12; // [rsp+50h] [rbp-38h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+58h] [rbp-30h] BYREF
  __int64 v14; // [rsp+70h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_CatalogCacheImprovements>::GetImpl'::`2'::impl) )
  {
    InitOnceExecuteOnce(&stru_1802E4F70, InitializeOneSettingsConfiguration, 0, 0);
    return qword_1802CA648;
  }
  v12 = 0;
  v11 = 0;
  string = 0;
  v14 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Flighting.OneSettings.OneSettingsPayload",
    0x3Au,
    0x39u);
  v1 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(
         v14,
         &v12);
  if ( v1 < 0 )
    goto LABEL_9;
  v2 = v12;
  v3 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v12 + 48LL);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v11);
  v14 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"SCCINSTALLSVC", 0xEu, 0xDu);
  v1 = v3(v2, v14, &v11);
  if ( v1 < 0
    || (v4 = v11,
        v5 = *(__int64 (__fastcall **)(__int64, __int64, HSTRING *))(*(_QWORD *)v11 + 72LL),
        WindowsDeleteString(string),
        string = 0,
        v14 = 0,
        Microsoft::WRL::Wrappers::HStringReference::CreateReference(
          &hstringHeader,
          L"CATALOGCACHEITEMDELETETHRESHOLDINHOURS",
          0x27u,
          0x26u),
        v1 = v5(v4, v14, &string),
        v1 < 0) )
  {
LABEL_9:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2F3,
      (unsigned int)"onecoreuap\\enduser\\winstore\\installservice\\lib\\settings.cpp",
      (const char *)(unsigned int)v1,
      v9);
    goto LABEL_7;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
  v7 = wcstoul(StringRawBuffer, 0, 10);
  v8 = v7;
  if ( !v7 )
  {
LABEL_7:
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v11);
    Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v12);
    return 720;
  }
  WindowsDeleteString(string);
  string = 0;
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v11);
  Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(&v12);
  return v8;
}

```

## disassembly

```asm
0x18003b300  mov     [rsp+arg_0], rbx
0x18003b305  push    rdi
0x18003b306  sub     rsp, 80h
0x18003b30d  mov     rax, cs:__security_cookie
0x18003b314  xor     rax, rsp
0x18003b317  mov     [rsp+88h+var_10], rax
0x18003b31c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements> `wil::Feature<__WilFeatureTraits_Feature_CatalogCacheImprovements>::GetImpl(void)'::`2'::impl
0x18003b323  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements>::__private_IsEnabled(void)
0x18003b328  test    al, al
0x18003b32a  jz      short loc_18003B352
0x18003b32c  xor     r9d, r9d; Context
0x18003b32f  xor     r8d, r8d; Parameter
0x18003b332  lea     rdx, InitializeOneSettingsConfiguration; InitFn
0x18003b339  lea     rcx, stru_1802E4F70; InitOnce
0x18003b340  call    cs:__imp_InitOnceExecuteOnce
0x18003b346  mov     rax, cs:qword_1802CA648
0x18003b34d  jmp     loc_18003B533
0x18003b352  mov     [rsp+88h+var_38], 0
0x18003b35b  mov     [rsp+88h+var_40], 0
0x18003b364  mov     [rsp+88h+string], 0
0x18003b36d  mov     [rsp+88h+var_18], 0
0x18003b376  mov     r9d, 39h ; '9'; unsigned int
0x18003b37c  lea     r8d, [r9+1]; unsigned int
0x18003b380  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18003b387  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x18003b38c  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003b391  lea     rdx, [rsp+88h+var_38]
0x18003b396  mov     rcx, [rsp+88h+var_18]
0x18003b39b  call    ??$GetActivationFactory@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>)
0x18003b3a0  test    eax, eax
0x18003b3a2  js      loc_18003B4E4
0x18003b3a8  mov     rdi, [rsp+88h+var_38]
0x18003b3ad  mov     rax, [rdi]
0x18003b3b0  mov     rbx, [rax+30h]
0x18003b3b4  lea     rcx, [rsp+88h+var_40]
0x18003b3b9  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b3be  mov     [rsp+88h+var_18], 0
0x18003b3c7  mov     r9d, 0Dh; unsigned int
0x18003b3cd  lea     r8d, [r9+1]; unsigned int
0x18003b3d1  lea     rdx, aSccinstallsvc; "SCCINSTALLSVC"
0x18003b3d8  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x18003b3dd  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003b3e2  nop
0x18003b3e3  lea     r8, [rsp+88h+var_40]
0x18003b3e8  mov     rdx, [rsp+88h+var_18]
0x18003b3ed  mov     rcx, rdi
0x18003b3f0  mov     rax, rbx
0x18003b3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b3f8  nop
0x18003b3f9  test    eax, eax
0x18003b3fb  js      loc_18003B4E4
0x18003b401  mov     rdi, [rsp+88h+var_40]
0x18003b406  mov     rax, [rdi]
0x18003b409  mov     rbx, [rax+48h]
0x18003b40d  mov     rcx, [rsp+88h+string]; string
0x18003b412  call    cs:__imp_WindowsDeleteString
0x18003b418  mov     [rsp+88h+string], 0
0x18003b421  mov     [rsp+88h+var_18], 0
0x18003b42a  mov     r9d, 26h ; '&'; unsigned int
0x18003b430  lea     r8d, [r9+1]; unsigned int
0x18003b434  lea     rdx, aCatalogcacheit; "CATALOGCACHEITEMDELETETHRESHOLDINHOURS"
0x18003b43b  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x18003b440  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003b445  nop
0x18003b446  lea     r8, [rsp+88h+string]
0x18003b44b  mov     rdx, [rsp+88h+var_18]
0x18003b450  mov     rcx, rdi
0x18003b453  mov     rax, rbx
0x18003b456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b45b  nop
0x18003b45c  test    eax, eax
0x18003b45e  js      loc_18003B4E4
0x18003b464  xor     edx, edx; length
0x18003b466  mov     rcx, [rsp+88h+string]; string
0x18003b46b  call    cs:__imp_WindowsGetStringRawBuffer
0x18003b471  xor     edx, edx; EndPtr
0x18003b473  lea     r8d, [rdx+0Ah]; Radix
0x18003b477  mov     rcx, rax; String
0x18003b47a  call    cs:__imp_wcstoul
0x18003b480  mov     ebx, eax
0x18003b482  test    eax, eax
0x18003b484  jnz     short loc_18003B4B6
0x18003b486  mov     rcx, [rsp+88h+string]; string
0x18003b48b  call    cs:__imp_WindowsDeleteString
0x18003b491  mov     [rsp+88h+string], 0
0x18003b49a  lea     rcx, [rsp+88h+var_40]
0x18003b49f  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b4a4  nop
0x18003b4a5  lea     rcx, [rsp+88h+var_38]
0x18003b4aa  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b4af  mov     eax, 2D0h
0x18003b4b4  jmp     short loc_18003B533
0x18003b4b6  mov     rcx, [rsp+88h+string]; string
0x18003b4bb  call    cs:__imp_WindowsDeleteString
0x18003b4c1  mov     [rsp+88h+string], 0
0x18003b4ca  lea     rcx, [rsp+88h+var_40]
0x18003b4cf  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b4d4  nop
0x18003b4d5  lea     rcx, [rsp+88h+var_38]
0x18003b4da  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b4df  mov     rax, rbx
0x18003b4e2  jmp     short loc_18003B533
0x18003b4e4  mov     rcx, [rsp+88h]; this
0x18003b4ec  test    eax, eax
0x18003b4ee  jns     short loc_18003B505
0x18003b4f0  mov     r9d, eax; char *
0x18003b4f3  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003b4fa  mov     edx, 2F3h; void *
0x18003b4ff  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b504  nop
0x18003b505  mov     rcx, [rsp+88h+string]; string
0x18003b50a  call    cs:__imp_WindowsDeleteString
0x18003b510  mov     [rsp+88h+string], 0
0x18003b519  lea     rcx, [rsp+88h+var_40]
0x18003b51e  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b523  nop
0x18003b524  lea     rcx, [rsp+88h+var_38]
0x18003b529  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b52e  mov     eax, 2D0h
0x18003b533  mov     rcx, [rsp+88h+var_10]
0x18003b538  xor     rcx, rsp; StackCookie
0x18003b53b  call    __security_check_cookie
0x18003b540  mov     rbx, [rsp+88h+arg_0]
0x18003b548  add     rsp, 80h
0x18003b54f  pop     rdi
0x18003b550  retn
```
