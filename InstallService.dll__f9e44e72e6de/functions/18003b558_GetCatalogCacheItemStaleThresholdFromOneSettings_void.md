# GetCatalogCacheItemStaleThresholdFromOneSettings(void)

- ea: `0x18003b558`
- end: `0x18003b7a9`
- name: `?GetCatalogCacheItemStaleThresholdFromOneSettings@@YA_JXZ`
- size: `593`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x1801ae18c`

## callees

- `0x180009ea0`
- `0x1800101f4`
- `0x18001af10`
- `0x1800252e8`
- `0x180034328`
- `0x18003b558`
- `0x180044cb8`
- `0x180215010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003b6d2`
- `api-ms-win-crt-private-l1-1-0!_o_wcstoul` at `0x18003b6d2`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003b598`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003b598`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b66a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b6e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b66a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b6e3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b713`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18003b762`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b6c3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18003b6c3`

## string_xrefs

- `0x18003b74b`: `onecoreuap\enduser\winstore\installservice\lib\settings.cpp`
- `0x18003b629`: `SCCINSTALLSVC`
- `0x18003b68c`: `CATALOGCACHEITEMSTALETHRESHOLDINHOURS`

## pseudocode

```c
// Hidden C++ exception states: #wind=4 #try_helpers=1
__int64 GetCatalogCacheItemStaleThresholdFromOneSettings(void)
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
    return qword_1802CA650;
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
          L"CATALOGCACHEITEMSTALETHRESHOLDINHOURS",
          0x26u,
          0x25u),
        v1 = v5(v4, v14, &string),
        v1 < 0) )
  {
LABEL_9:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x2C5,
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
    return 24;
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
0x18003b558  mov     [rsp+arg_0], rbx
0x18003b55d  push    rdi
0x18003b55e  sub     rsp, 80h
0x18003b565  mov     rax, cs:__security_cookie
0x18003b56c  xor     rax, rsp
0x18003b56f  mov     [rsp+88h+var_10], rax
0x18003b574  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements> `wil::Feature<__WilFeatureTraits_Feature_CatalogCacheImprovements>::GetImpl(void)'::`2'::impl
0x18003b57b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_CatalogCacheImprovements@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CatalogCacheImprovements>::__private_IsEnabled(void)
0x18003b580  test    al, al
0x18003b582  jz      short loc_18003B5AA
0x18003b584  xor     r9d, r9d; Context
0x18003b587  xor     r8d, r8d; Parameter
0x18003b58a  lea     rdx, InitializeOneSettingsConfiguration; InitFn
0x18003b591  lea     rcx, stru_1802E4F70; InitOnce
0x18003b598  call    cs:__imp_InitOnceExecuteOnce
0x18003b59e  mov     rax, cs:qword_1802CA650
0x18003b5a5  jmp     loc_18003B78B
0x18003b5aa  mov     [rsp+88h+var_38], 0
0x18003b5b3  mov     [rsp+88h+var_40], 0
0x18003b5bc  mov     [rsp+88h+string], 0
0x18003b5c5  mov     [rsp+88h+var_18], 0
0x18003b5ce  mov     r9d, 39h ; '9'; unsigned int
0x18003b5d4  lea     r8d, [r9+1]; unsigned int
0x18003b5d8  lea     rdx, ?RuntimeClass_Windows_Internal_Flighting_OneSettings_OneSettingsPayload@@3QBGB; "Windows.Internal.Flighting.OneSettings."...
0x18003b5df  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x18003b5e4  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003b5e9  lea     rdx, [rsp+88h+var_38]
0x18003b5ee  mov     rcx, [rsp+88h+var_18]
0x18003b5f3  call    ??$GetActivationFactory@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIOneSettingsPayloadStatics@OneSettings@Flighting@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Flighting::OneSettings::IOneSettingsPayloadStatics>>)
0x18003b5f8  test    eax, eax
0x18003b5fa  js      loc_18003B73C
0x18003b600  mov     rdi, [rsp+88h+var_38]
0x18003b605  mov     rax, [rdi]
0x18003b608  mov     rbx, [rax+30h]
0x18003b60c  lea     rcx, [rsp+88h+var_40]
0x18003b611  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b616  mov     [rsp+88h+var_18], 0
0x18003b61f  mov     r9d, 0Dh; unsigned int
0x18003b625  lea     r8d, [r9+1]; unsigned int
0x18003b629  lea     rdx, aSccinstallsvc; "SCCINSTALLSVC"
0x18003b630  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x18003b635  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003b63a  nop
0x18003b63b  lea     r8, [rsp+88h+var_40]
0x18003b640  mov     rdx, [rsp+88h+var_18]
0x18003b645  mov     rcx, rdi
0x18003b648  mov     rax, rbx
0x18003b64b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b650  nop
0x18003b651  test    eax, eax
0x18003b653  js      loc_18003B73C
0x18003b659  mov     rdi, [rsp+88h+var_40]
0x18003b65e  mov     rax, [rdi]
0x18003b661  mov     rbx, [rax+48h]
0x18003b665  mov     rcx, [rsp+88h+string]; string
0x18003b66a  call    cs:__imp_WindowsDeleteString
0x18003b670  mov     [rsp+88h+string], 0
0x18003b679  mov     [rsp+88h+var_18], 0
0x18003b682  mov     r9d, 25h ; '%'; unsigned int
0x18003b688  lea     r8d, [r9+1]; unsigned int
0x18003b68c  lea     rdx, aCatalogcacheit_0; "CATALOGCACHEITEMSTALETHRESHOLDINHOURS"
0x18003b693  lea     rcx, [rsp+88h+hstringHeader]; hstringHeader
0x18003b698  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18003b69d  nop
0x18003b69e  lea     r8, [rsp+88h+string]
0x18003b6a3  mov     rdx, [rsp+88h+var_18]
0x18003b6a8  mov     rcx, rdi
0x18003b6ab  mov     rax, rbx
0x18003b6ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b6b3  nop
0x18003b6b4  test    eax, eax
0x18003b6b6  js      loc_18003B73C
0x18003b6bc  xor     edx, edx; length
0x18003b6be  mov     rcx, [rsp+88h+string]; string
0x18003b6c3  call    cs:__imp_WindowsGetStringRawBuffer
0x18003b6c9  xor     edx, edx; EndPtr
0x18003b6cb  lea     r8d, [rdx+0Ah]; Radix
0x18003b6cf  mov     rcx, rax; String
0x18003b6d2  call    cs:__imp_wcstoul
0x18003b6d8  mov     ebx, eax
0x18003b6da  test    eax, eax
0x18003b6dc  jnz     short loc_18003B70E
0x18003b6de  mov     rcx, [rsp+88h+string]; string
0x18003b6e3  call    cs:__imp_WindowsDeleteString
0x18003b6e9  mov     [rsp+88h+string], 0
0x18003b6f2  lea     rcx, [rsp+88h+var_40]
0x18003b6f7  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b6fc  nop
0x18003b6fd  lea     rcx, [rsp+88h+var_38]
0x18003b702  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b707  mov     eax, 18h
0x18003b70c  jmp     short loc_18003B78B
0x18003b70e  mov     rcx, [rsp+88h+string]; string
0x18003b713  call    cs:__imp_WindowsDeleteString
0x18003b719  mov     [rsp+88h+string], 0
0x18003b722  lea     rcx, [rsp+88h+var_40]
0x18003b727  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b72c  nop
0x18003b72d  lea     rcx, [rsp+88h+var_38]
0x18003b732  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b737  mov     rax, rbx
0x18003b73a  jmp     short loc_18003B78B
0x18003b73c  mov     rcx, [rsp+88h]; this
0x18003b744  test    eax, eax
0x18003b746  jns     short loc_18003B75D
0x18003b748  mov     r9d, eax; char *
0x18003b74b  lea     r8, aOnecoreuapEndu_6; "onecoreuap\\enduser\\winstore\\installs"...
0x18003b752  mov     edx, 2C5h; void *
0x18003b757  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b75c  nop
0x18003b75d  mov     rcx, [rsp+88h+string]; string
0x18003b762  call    cs:__imp_WindowsDeleteString
0x18003b768  mov     [rsp+88h+string], 0
0x18003b771  lea     rcx, [rsp+88h+var_40]
0x18003b776  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b77b  nop
0x18003b77c  lea     rcx, [rsp+88h+var_38]
0x18003b781  call    ?InternalRelease@?$ComPtr@UIInstallationCompletedCallbackArgs@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IInstallationCompletedCallbackArgs>::InternalRelease(void)
0x18003b786  mov     eax, 18h
0x18003b78b  mov     rcx, [rsp+88h+var_10]
0x18003b790  xor     rcx, rsp; StackCookie
0x18003b793  call    __security_check_cookie
0x18003b798  mov     rbx, [rsp+88h+arg_0]
0x18003b7a0  add     rsp, 80h
0x18003b7a7  pop     rdi
0x18003b7a8  retn
```
