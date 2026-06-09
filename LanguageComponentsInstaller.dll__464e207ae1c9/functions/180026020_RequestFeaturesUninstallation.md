# RequestFeaturesUninstallation

- ea: `0x180026020`
- end: `0x180026215`
- name: `RequestFeaturesUninstallation`
- size: `501`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `13`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014788`

## callees

- `0x180003520`
- `0x180004118`
- `0x1800092a4`
- `0x180021590`
- `0x1800248c0`
- `0x180024a10`
- `0x180024b28`
- `0x1800253c8`
- `0x180025550`
- `0x180026020`
- `0x180026c2c`
- `0x180026f3c`
- `0x180027b54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002616c`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002616c`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002615e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18002615e`

## string_xrefs

- `0x180026157`: `UpdateAPI.dll`
- `0x180026084`: `UninstallationRequest`
- `0x1800261a5`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagefeaturesprovider.cpp`

## pseudocode

```c
__int64 __fastcall RequestFeaturesUninstallation(__int64 a1, __int64 a2)
{
  __int64 v2; // rcx
  HMODULE LibraryW; // rax
  unsigned int v4; // ebx
  int v5; // eax
  int v7; // [rsp+20h] [rbp-188h]
  _QWORD v8[3]; // [rsp+28h] [rbp-180h] BYREF
  void **v9; // [rsp+40h] [rbp-168h] BYREF
  int v10; // [rsp+48h] [rbp-160h] BYREF
  char v11; // [rsp+4Ch] [rbp-15Ch]
  int v12; // [rsp+70h] [rbp-138h] BYREF
  const char *v13; // [rsp+78h] [rbp-130h]
  __int64 v14; // [rsp+80h] [rbp-128h]
  char v15; // [rsp+88h] [rbp-120h]
  int v16; // [rsp+90h] [rbp-118h]
  _BYTE v17[152]; // [rsp+98h] [rbp-110h] BYREF
  __int128 v18; // [rsp+130h] [rbp-78h]
  int v19; // [rsp+140h] [rbp-68h]
  __int64 v20; // [rsp+148h] [rbp-60h]
  int *v21; // [rsp+150h] [rbp-58h]
  __int64 v22; // [rsp+158h] [rbp-50h]
  __int64 v23; // [rsp+160h] [rbp-48h]
  void ***v24; // [rsp+168h] [rbp-40h]
  __int64 v25; // [rsp+170h] [rbp-38h]
  int v26; // [rsp+178h] [rbp-30h]
  int *v27; // [rsp+180h] [rbp-28h]
  char v28; // [rsp+188h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+1A8h] [rbp+0h]

  GetCbsLanguageFeatures(v8, a1, a1 + 24 * a2);
  if ( v8[0] == v8[1] )
    MicrosoftTelemetryAssertTriggeredNoArgs(v2);
  v10 = 0;
  v11 = 0;
  v15 = 0;
  v12 = 0;
  v13 = "UninstallationRequest";
  v14 = 0;
  v16 = 0;
  v18 = 0;
  memset_0(v17, 0, sizeof(v17));
  v19 = 1;
  v20 = 0;
  v21 = &v10;
  v22 = 0;
  v23 = 0;
  v24 = &v9;
  v25 = 0;
  v26 = 0;
  v27 = &v12;
  v28 = 0;
  v9 = &LanguageComponentsInstallerTelemetry::UninstallationRequest::`vftable';
  LanguageComponentsInstallerTelemetry::UninstallationRequest::StartActivity(&v9, v8);
  LibraryW = LoadLibraryW(L"UpdateAPI.dll");
  if ( LibraryW )
  {
    FreeLibrary(LibraryW);
    v4 = OptionalityFeaturesProvider::UninstallFeatures(v8);
  }
  else
  {
    v5 = CbsFeaturesProvider::SendRequest(v8, 2, 0, 0);
    v4 = v5;
    if ( v5 >= 0 )
      v4 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagefeaturesprovider.cpp",
        (const char *)(unsigned int)v5,
        v7);
  }
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    &v9,
    v4);
  v9 = &LanguageComponentsInstallerTelemetry::UninstallationRequest::`vftable';
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v9);
  wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v9);
  std::vector<CbsLanguageFeature>::_Tidy(v8);
  return v4;
}

```

## disassembly

```asm
0x180026020  mov     [rsp+arg_8], rbx
0x180026025  push    rsi
0x180026026  sub     rsp, 1A0h
0x18002602d  mov     rax, cs:__security_cookie
0x180026034  xor     rax, rsp
0x180026037  mov     [rsp+1A8h+var_18], rax
0x18002603f  lea     rax, [rdx+rdx*2]
0x180026043  lea     r8, [rcx+rax*8]
0x180026047  mov     rdx, rcx
0x18002604a  lea     rcx, [rsp+1A8h+var_180]
0x18002604f  call    ?GetCbsLanguageFeatures@@YA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@PEBUCbsLanguageFeatureId@@0@Z; GetCbsLanguageFeatures(CbsLanguageFeatureId const *,CbsLanguageFeatureId const *)
0x180026054  nop
0x180026055  mov     rax, [rsp+1A8h+var_178]
0x18002605a  cmp     [rsp+1A8h+var_180], rax
0x18002605f  jnz     short loc_180026067
0x180026061  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180026066  nop
0x180026067  mov     [rsp+1A8h+var_160], 0
0x18002606f  mov     [rsp+1A8h+var_15C], 0
0x180026074  mov     [rsp+1A8h+var_120], 0
0x18002607c  mov     [rsp+1A8h+var_138], 0
0x180026084  lea     rax, aUninstallation; "UninstallationRequest"
0x18002608b  mov     [rsp+1A8h+var_130], rax
0x180026090  mov     [rsp+1A8h+var_128], 0
0x18002609c  mov     [rsp+1A8h+var_118], 0
0x1800260a7  xorps   xmm0, xmm0
0x1800260aa  movdqa  [rsp+1A8h+var_78], xmm0
0x1800260b3  xor     edx, edx; Val
0x1800260b5  mov     r8d, 98h; Size
0x1800260bb  lea     rcx, [rsp+1A8h+var_110]; void *
0x1800260c3  call    memset_0
0x1800260c8  mov     [rsp+1A8h+var_68], 1
0x1800260d3  xor     eax, eax
0x1800260d5  mov     [rsp+1A8h+var_60], rax
0x1800260dd  lea     rax, [rsp+1A8h+var_160]
0x1800260e2  mov     [rsp+1A8h+var_58], rax
0x1800260ea  mov     [rsp+1A8h+var_50], 0
0x1800260f6  mov     [rsp+1A8h+var_48], 0
0x180026102  lea     rax, [rsp+1A8h+var_168]
0x180026107  mov     [rsp+1A8h+var_40], rax
0x18002610f  mov     [rsp+1A8h+var_38], 0
0x18002611b  mov     [rsp+1A8h+var_30], 0
0x180026126  lea     rax, [rsp+1A8h+var_138]
0x18002612b  mov     [rsp+1A8h+var_28], rax
0x180026133  mov     [rsp+1A8h+var_20], 0
0x18002613b  lea     rsi, ??_7UninstallationRequest@LanguageComponentsInstallerTelemetry@@6B@; const LanguageComponentsInstallerTelemetry::UninstallationRequest::`vftable'
0x180026142  mov     [rsp+1A8h+var_168], rsi
0x180026147  lea     rdx, [rsp+1A8h+var_180]
0x18002614c  lea     rcx, [rsp+1A8h+var_168]
0x180026151  call    ?StartActivity@UninstallationRequest@LanguageComponentsInstallerTelemetry@@QEAAXAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z; LanguageComponentsInstallerTelemetry::UninstallationRequest::StartActivity(std::vector<CbsLanguageFeature> const &)
0x180026156  nop
0x180026157  lea     rcx, LibFileName; "UpdateAPI.dll"
0x18002615e  call    cs:__imp_LoadLibraryW
0x180026164  test    rax, rax
0x180026167  jz      short loc_180026180
0x180026169  mov     rcx, rax; hLibModule
0x18002616c  call    cs:__imp_FreeLibrary
0x180026172  lea     rcx, [rsp+1A8h+var_180]
0x180026177  call    ?UninstallFeatures@OptionalityFeaturesProvider@@YAJAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z; OptionalityFeaturesProvider::UninstallFeatures(std::vector<CbsLanguageFeature> const &)
0x18002617c  mov     ebx, eax
0x18002617e  jmp     short loc_1800261BA
0x180026180  xor     r9d, r9d
0x180026183  xor     r8d, r8d
0x180026186  lea     edx, [r9+2]
0x18002618a  lea     rcx, [rsp+1A8h+var_180]
0x18002618f  call    ?SendRequest@CbsFeaturesProvider@@YAJAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@W4RequestType@@PEAUICbsUIHandler@@K@Z; CbsFeaturesProvider::SendRequest(std::vector<CbsLanguageFeature> const &,RequestType,ICbsUIHandler *,ulong)
0x180026194  mov     ebx, eax
0x180026196  test    eax, eax
0x180026198  jns     short loc_1800261B8
0x18002619a  mov     rcx, [rsp+1A8h]; this
0x1800261a2  mov     r9d, eax; char *
0x1800261a5  lea     r8, aOnecoreShellCp_3; "onecore\\shell\\cpls\\internationalsett"...
0x1800261ac  mov     edx, 59h ; 'Y'; void *
0x1800261b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800261b6  jmp     short loc_1800261BA
0x1800261b8  xor     ebx, ebx
0x1800261ba  mov     edx, ebx
0x1800261bc  lea     rcx, [rsp+1A8h+var_168]
0x1800261c1  call    ?Stop@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800261c6  nop
0x1800261c7  mov     [rsp+1A8h+var_168], rsi
0x1800261cc  lea     rcx, [rsp+1A8h+var_168]
0x1800261d1  call    ?Destroy@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800261d6  lea     rcx, [rsp+1A8h+var_168]
0x1800261db  call    ??1?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800261e0  nop
0x1800261e1  lea     rcx, [rsp+1A8h+var_180]
0x1800261e6  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x1800261eb  mov     eax, ebx
0x1800261ed  jmp     short loc_1800261F3
0x1800261ef  mov     eax, [rsp+1A8h+var_188]
0x1800261f3  mov     rcx, [rsp+1A8h+var_18]
0x1800261fb  xor     rcx, rsp; StackCookie
0x1800261fe  call    __security_check_cookie
0x180026203  mov     rbx, [rsp+1A8h+arg_8]
0x18002620b  add     rsp, 1A0h
0x180026212  pop     rsi
0x180026213  retn
```
