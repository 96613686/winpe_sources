# CLanguagePackInstallerSingleton::s_LanguagePackInstallThread(void *)

- ea: `0x140040c30`
- end: `0x140040eb6`
- name: `?s_LanguagePackInstallThread@CLanguagePackInstallerSingleton@@SAKPEAX@Z`
- size: `646`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `18`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x140005f30`
- `0x14000e624`
- `0x14002996c`
- `0x14002ddcc`
- `0x14002de74`
- `0x14003e10c`
- `0x14003e328`
- `0x14003e3cc`
- `0x14003e680`
- `0x14003e9e8`
- `0x14003f3f8`
- `0x14003fb48`
- `0x14003fc8c`
- `0x140040304`
- `0x140040c30`
- `0x140041b08`
- `0x14004255c`
- `0x140042a40`

## import_xrefs

- `KERNEL32!TlsGetValue` at `0x140040c77`
- `KERNEL32!TlsGetValue` at `0x140040c77`
- `KERNEL32!TlsSetValue` at `0x140040caa`
- `KERNEL32!TlsSetValue` at `0x140040caa`
- `ntdll!NtGetMUIRegistryInfo` at `0x140040dca`
- `ntdll!NtGetMUIRegistryInfo` at `0x140040dca`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140040d4a`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x140040d4a`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140040e0c`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x140040e0c`
- `Bcp47Langs!ClearUserDisplayLanguageOverride` at `0x140040dd9`
- `Bcp47Langs!ClearUserDisplayLanguageOverride` at `0x140040dd9`

## string_xrefs

- `0x140040ded`: `pcshell\shell\systemsettings\adminflows\languagepackinstaller\lib\languagepackinstallersingleton.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CLanguagePackInstallerSingleton::s_LanguagePackInstallThread(_DWORD *Parameter)
{
  CLPInstallHandler **v1; // r15
  const unsigned __int16 *v2; // r14
  unsigned int v3; // edi
  char v4; // r12
  __int64 *Value; // rax
  __int64 *p_TlsValue; // rbx
  unsigned int v7; // ecx
  __int64 v8; // rcx
  __int64 v9; // rdx
  int v10; // edi
  unsigned int v11; // edx
  int v12; // eax
  unsigned int v13; // edx
  __int64 v14; // rsi
  int v16; // [rsp+20h] [rbp-E0h]
  DWORD v17; // [rsp+30h] [rbp-D0h] BYREF
  struct wil::Variant *v18; // [rsp+38h] [rbp-C8h] BYREF
  __int64 TlsValue; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v20; // [rsp+48h] [rbp-B8h]
  _DWORD *v21; // [rsp+50h] [rbp-B0h] BYREF
  _QWORD v22[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1F8h] [rbp+F8h]

  v1 = (CLPInstallHandler **)CLanguagePackInstallerSingleton::s_pInstance;
  v21 = Parameter;
  v2 = *(const unsigned __int16 **)Parameter;
  v3 = Parameter[6];
  v4 = *((_BYTE *)Parameter + 28);
  Value = (__int64 *)TlsGetValue(__g_tracingTlsSlot);
  p_TlsValue = Value;
  v17 = -1;
  TlsValue = 0;
  if ( Value )
  {
    v20 = Value;
  }
  else
  {
    p_TlsValue = &TlsValue;
    v17 = __g_tracingTlsSlot;
    TlsSetValue(__g_tracingTlsSlot, &TlsValue);
    v20 = &TlsValue;
  }
  ++*(_DWORD *)p_TlsValue;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v7 = 5 * *(_DWORD *)p_TlsValue;
    if ( v7 > 0x1E1 )
      v8 = 0;
    else
      v8 = 479LL - v7;
    WPP_SF_sS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      24,
      (unsigned int)&WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids,
      (unsigned int)&asc_140089BC0[v8],
      (__int64)v2);
  }
  wil::ActivityBase<LanguagePackSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguagePackSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v22);
  v22[0] = &LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest::`vftable';
  LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest::StartActivity(
    (LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest *)v22,
    v2,
    v3,
    0);
  v10 = RoInitialize(1, v9);
  if ( v10 >= 0 )
  {
    CLanguagePackInstallerSingleton::RaiseProgressEvent((CLanguagePackInstallerSingleton *)v1, v2, 0);
    v10 = CLPInstallHandler::PrepareForInstall(v1[3]);
    if ( v10 >= 0 )
    {
      v18 = 0;
      v10 = CLPInstallHandler::SearchForPackage(v1[3], v2, &v18);
      if ( v10 >= 0 )
      {
        v10 = CLPInstallHandler::DownloadAndInstallPackage(v1[3], v2, v18);
        LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest::DownloadAndInstallPackageRequest(
          (LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest *)v22,
          v11,
          v10);
      }
      CAutoMemPtr<wil::Variant>::~CAutoMemPtr<wil::Variant>(&v18);
    }
    NtGetMUIRegistryInfo(10, 0, 0);
    if ( v10 >= 0 )
    {
      if ( v4 )
      {
        v12 = ClearUserDisplayLanguageOverride();
        if ( v12 < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0xF8,
            (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagepackinstaller\\lib\\languagepackinstallersingleton.cpp",
            (const char *)(unsigned int)v12,
            v16);
      }
    }
    CLanguagePackInstallerSingleton::_CompleteInstallation((CLanguagePackInstallerSingleton *)v1, v2, v10);
    RoUninitialize();
  }
  wil::ActivityBase<LanguagePackSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v22,
    (unsigned int)v10);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && *((char *)WPP_GLOBAL_Control + 28) < 0 )
  {
    v13 = 5 * *(_DWORD *)p_TlsValue;
    if ( v13 > 0x1E1 )
      v14 = 0;
    else
      v14 = 479LL - v13;
    WPP_SF_sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      25,
      (unsigned int)&WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids,
      (unsigned int)&asc_140089BC0[v14],
      v10);
  }
  LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest::~LanguagePackInstallationRequest((LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest *)v22);
  --*(_DWORD *)p_TlsValue;
  TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(&v17);
  std::unique_ptr<LANGUAGE_PACK_INSTALL_PARAMETERS>::~unique_ptr<LANGUAGE_PACK_INSTALL_PARAMETERS>(&v21);
  return 0;
}

```

## disassembly

```asm
0x140040c30  push    rbp
0x140040c32  push    rbx
0x140040c33  push    rsi
0x140040c34  push    rdi
0x140040c35  push    r12
0x140040c37  push    r14
0x140040c39  push    r15
0x140040c3b  lea     rbp, [rsp-0C0h]
0x140040c43  sub     rsp, 1C0h
0x140040c4a  mov     rax, cs:__security_cookie
0x140040c51  xor     rax, rsp
0x140040c54  mov     [rbp+0F0h+var_40], rax
0x140040c5b  mov     r15, cs:?s_pInstance@CLanguagePackInstallerSingleton@@0PEAV1@EA; CLanguagePackInstallerSingleton * CLanguagePackInstallerSingleton::s_pInstance
0x140040c62  mov     [rsp+1F0h+var_1A0], rcx
0x140040c67  mov     r14, [rcx]
0x140040c6a  mov     edi, [rcx+18h]
0x140040c6d  mov     r12b, [rcx+1Ch]
0x140040c71  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x140040c77  call    cs:__imp_TlsGetValue
0x140040c7d  mov     rbx, rax
0x140040c80  mov     [rsp+1F0h+var_1C0], 0FFFFFFFFh
0x140040c88  mov     [rsp+1F0h+TlsValue], 0
0x140040c91  test    rax, rax
0x140040c94  jnz     short loc_140040CB7
0x140040c96  lea     rbx, [rsp+1F0h+TlsValue]
0x140040c9b  mov     ecx, cs:?__g_tracingTlsSlot@@3KA; dwTlsIndex
0x140040ca1  mov     [rsp+1F0h+var_1C0], ecx
0x140040ca5  lea     rdx, [rsp+1F0h+TlsValue]; lpTlsValue
0x140040caa  call    cs:__imp_TlsSetValue
0x140040cb0  mov     [rsp+1F0h+var_1A8], rbx
0x140040cb5  jmp     short loc_140040CBC
0x140040cb7  mov     [rsp+1F0h+var_1A8], rax
0x140040cbc  inc     dword ptr [rbx]
0x140040cbe  lea     rax, WPP_GLOBAL_Control
0x140040cc5  mov     esi, 1DFh
0x140040cca  lea     rdx, asc_140089BC0; "                                       "...
0x140040cd1  mov     r10, cs:WPP_GLOBAL_Control
0x140040cd8  cmp     r10, rax
0x140040cdb  jz      short loc_140040D1B
0x140040cdd  test    byte ptr [r10+1Ch], 80h
0x140040ce2  jz      short loc_140040D1B
0x140040ce4  mov     eax, [rbx]
0x140040ce6  lea     ecx, [rax+rax*4]
0x140040ce9  cmp     ecx, 1E1h
0x140040cef  ja      short loc_140040CFA
0x140040cf1  mov     eax, ecx
0x140040cf3  mov     ecx, esi
0x140040cf5  sub     rcx, rax
0x140040cf8  jmp     short loc_140040CFC
0x140040cfa  xor     ecx, ecx
0x140040cfc  lea     r9, [rcx+rdx]
0x140040d00  mov     edx, 18h
0x140040d05  mov     qword ptr [rsp+1F0h+var_1D0], r14; int
0x140040d0a  lea     r8, WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids
0x140040d11  mov     rcx, [r10+10h]
0x140040d15  call    WPP_SF_sS
0x140040d1a  nop
0x140040d1b  lea     rcx, [rsp+1F0h+var_190]; struct wil::details::IFailureCallback *
0x140040d20  call    ??0?$ActivityBase@VLanguagePackSettingsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LanguagePackSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LanguagePackSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x140040d25  lea     rax, ??_7LanguagePackInstallationRequest@LanguagePackInstallSettingsTelemetryProvider@@6B@; const LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest::`vftable'
0x140040d2c  mov     [rsp+1F0h+var_190], rax
0x140040d31  xor     r9d, r9d; bool
0x140040d34  mov     r8d, edi; unsigned int
0x140040d37  mov     rdx, r14; unsigned __int16 *
0x140040d3a  lea     rcx, [rsp+1F0h+var_190]; this
0x140040d3f  call    ?StartActivity@LanguagePackInstallationRequest@LanguagePackInstallSettingsTelemetryProvider@@QEAAXPEBGI_N@Z; LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest::StartActivity(ushort const *,uint,bool)
0x140040d44  nop
0x140040d45  mov     ecx, 1
0x140040d4a  call    cs:__imp_RoInitialize
0x140040d50  mov     edi, eax
0x140040d52  test    eax, eax
0x140040d54  js      loc_140040E12
0x140040d5a  xor     r8d, r8d; unsigned int
0x140040d5d  mov     rdx, r14; unsigned __int16 *
0x140040d60  mov     rcx, r15; this
0x140040d63  call    ?RaiseProgressEvent@CLanguagePackInstallerSingleton@@QEAAXPEBGI@Z; CLanguagePackInstallerSingleton::RaiseProgressEvent(ushort const *,uint)
0x140040d68  mov     rcx, [r15+18h]; this
0x140040d6c  call    ?PrepareForInstall@CLPInstallHandler@@QEAAJXZ; CLPInstallHandler::PrepareForInstall(void)
0x140040d71  mov     edi, eax
0x140040d73  test    eax, eax
0x140040d75  js      short loc_140040DC2
0x140040d77  mov     [rsp+1F0h+var_1B8], 0
0x140040d80  lea     r8, [rsp+1F0h+var_1B8]; struct wil::Variant **
0x140040d85  mov     rdx, r14; unsigned __int16 *
0x140040d88  mov     rcx, [r15+18h]; this
0x140040d8c  call    ?SearchForPackage@CLPInstallHandler@@QEAAJPEBGPEAPEAVVariant@wil@@@Z; CLPInstallHandler::SearchForPackage(ushort const *,wil::Variant * *)
0x140040d91  mov     edi, eax
0x140040d93  test    eax, eax
0x140040d95  js      short loc_140040DB8
0x140040d97  mov     r8, [rsp+1F0h+var_1B8]; struct wil::Variant *
0x140040d9c  mov     rdx, r14; unsigned __int16 *
0x140040d9f  mov     rcx, [r15+18h]; this
0x140040da3  call    ?DownloadAndInstallPackage@CLPInstallHandler@@QEAAJPEBGPEBVVariant@wil@@@Z; CLPInstallHandler::DownloadAndInstallPackage(ushort const *,wil::Variant const *)
0x140040da8  mov     edi, eax
0x140040daa  mov     r8d, eax; int
0x140040dad  lea     rcx, [rsp+1F0h+var_190]; this
0x140040db2  call    ?DownloadAndInstallPackageRequest@LanguagePackInstallationRequest@LanguagePackInstallSettingsTelemetryProvider@@QEAAXIJ@Z; LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest::DownloadAndInstallPackageRequest(uint,long)
0x140040db7  nop
0x140040db8  lea     rcx, [rsp+1F0h+var_1B8]
0x140040dbd  call    ??1?$CAutoMemPtr@VVariant@wil@@@@QEAA@XZ; CAutoMemPtr<wil::Variant>::~CAutoMemPtr<wil::Variant>(void)
0x140040dc2  xor     r8d, r8d
0x140040dc5  xor     edx, edx
0x140040dc7  lea     ecx, [rdx+0Ah]
0x140040dca  call    cs:__imp_NtGetMUIRegistryInfo
0x140040dd0  test    edi, edi
0x140040dd2  js      short loc_140040DFE
0x140040dd4  test    r12b, r12b
0x140040dd7  jz      short loc_140040DFE
0x140040dd9  call    cs:__imp_ClearUserDisplayLanguageOverride
0x140040ddf  mov     rcx, [rbp+0F8h]; this
0x140040de6  test    eax, eax
0x140040de8  jns     short loc_140040DFE
0x140040dea  mov     r9d, eax; char *
0x140040ded  lea     r8, aPcshellShellSy_30; "pcshell\\shell\\systemsettings\\adminfl"...
0x140040df4  mov     edx, 0F8h; void *
0x140040df9  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x140040dfe  mov     r8d, edi; int
0x140040e01  mov     rdx, r14; unsigned __int16 *
0x140040e04  mov     rcx, r15; this
0x140040e07  call    ?_CompleteInstallation@CLanguagePackInstallerSingleton@@AEAAXPEBGJ@Z; CLanguagePackInstallerSingleton::_CompleteInstallation(ushort const *,long)
0x140040e0c  call    cs:__imp_RoUninitialize
0x140040e12  mov     edx, edi
0x140040e14  lea     rcx, [rsp+1F0h+var_190]
0x140040e19  call    ?Stop@?$ActivityBase@VLanguagePackSettingsLogging@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LanguagePackSettingsLogging,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140040e1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140040e25  lea     rax, WPP_GLOBAL_Control
0x140040e2c  cmp     rcx, rax
0x140040e2f  jz      short loc_140040E71
0x140040e31  test    byte ptr [rcx+1Ch], 80h
0x140040e35  jz      short loc_140040E71
0x140040e37  mov     eax, [rbx]
0x140040e39  lea     edx, [rax+rax*4]
0x140040e3c  cmp     edx, 1E1h
0x140040e42  ja      short loc_140040E4B
0x140040e44  mov     eax, edx
0x140040e46  sub     rsi, rax
0x140040e49  jmp     short loc_140040E4D
0x140040e4b  xor     esi, esi
0x140040e4d  lea     r9, asc_140089BC0; "                                       "...
0x140040e54  add     r9, rsi
0x140040e57  mov     edx, 19h
0x140040e5c  mov     [rsp+1F0h+var_1D0], edi
0x140040e60  lea     r8, WPP_f36bffa08b0b30fbbd1fad32a50cf4e7_Traceguids
0x140040e67  mov     rcx, [rcx+10h]
0x140040e6b  call    WPP_SF_sd
0x140040e70  nop
0x140040e71  lea     rcx, [rsp+1F0h+var_190]; this
0x140040e76  call    ??1LanguagePackInstallationRequest@LanguagePackInstallSettingsTelemetryProvider@@QEAA@XZ; LanguagePackInstallSettingsTelemetryProvider::LanguagePackInstallationRequest::~LanguagePackInstallationRequest(void)
0x140040e7b  nop
0x140040e7c  dec     dword ptr [rbx]
0x140040e7e  lea     rcx, [rsp+1F0h+var_1C0]
0x140040e83  call    ??1?$AutoTlsPtr@UTracingContext@TracingInternal@@@TracingInternal@@QEAA@XZ; TracingInternal::AutoTlsPtr<TracingInternal::TracingContext>::~AutoTlsPtr<TracingInternal::TracingContext>(void)
0x140040e88  nop
0x140040e89  lea     rcx, [rsp+1F0h+var_1A0]
0x140040e8e  call    ??1?$unique_ptr@ULANGUAGE_PACK_INSTALL_PARAMETERS@@U?$default_delete@ULANGUAGE_PACK_INSTALL_PARAMETERS@@@std@@@std@@QEAA@XZ; std::unique_ptr<LANGUAGE_PACK_INSTALL_PARAMETERS>::~unique_ptr<LANGUAGE_PACK_INSTALL_PARAMETERS>(void)
0x140040e93  xor     eax, eax
0x140040e95  mov     rcx, [rbp+0F0h+var_40]
0x140040e9c  xor     rcx, rsp; StackCookie
0x140040e9f  call    __security_check_cookie
0x140040ea4  add     rsp, 1C0h
0x140040eab  pop     r15
0x140040ead  pop     r14
0x140040eaf  pop     r12
0x140040eb1  pop     rdi
0x140040eb2  pop     rsi
0x140040eb3  pop     rbx
0x140040eb4  pop     rbp
0x140040eb5  retn
```
