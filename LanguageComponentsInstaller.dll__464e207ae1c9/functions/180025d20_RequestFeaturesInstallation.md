# RequestFeaturesInstallation

- ea: `0x180025d20`
- end: `0x180026015`
- name: `RequestFeaturesInstallation`
- size: `757`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, unsigned __int8, int)`
- caller_count: `1`
- callee_count: `17`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001b3c0`

## callees

- `0x180003520`
- `0x180004118`
- `0x1800092a4`
- `0x18000a7fc`
- `0x180021590`
- `0x18002354c`
- `0x1800248c0`
- `0x180024a10`
- `0x180024b28`
- `0x180025240`
- `0x180025550`
- `0x180025b58`
- `0x180025d20`
- `0x1800269c0`
- `0x180026c2c`
- `0x180027434`
- `0x180027b54`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025e71`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x180025e71`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180025e5e`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x180025e5e`
- `ntdll!RtlPublishWnfStateData` at `0x180025e8d`
- `ntdll!RtlPublishWnfStateData` at `0x180025f74`
- `ntdll!RtlPublishWnfStateData` at `0x180025e8d`
- `ntdll!RtlPublishWnfStateData` at `0x180025f74`

## string_xrefs

- `0x180025e57`: `UpdateAPI.dll`
- `0x180025d94`: `InstallationRequest`
- `0x180025f1e`: `onecore\shell\cpls\internationalsettings\languagecomponentsinstaller\dll\languagefeaturesprovider.cpp`

## pseudocode

```c
__int64 __fastcall RequestFeaturesInstallation(__int64 a1, __int64 a2, __int64 a3, unsigned __int8 a4, int a5)
{
  int v5; // edi
  HMODULE LibraryW; // rax
  char v8; // bl
  int v9; // eax
  int v10; // ebx
  int IsOSSilentElevationOn; // eax
  int v12; // eax
  unsigned int v13; // ebx
  __int64 v14; // r9
  __int64 v15; // rdx
  bool v16; // zf
  int v17; // eax
  const char *v18; // r9
  __int64 result; // rax
  int v20; // [rsp+30h] [rbp-198h] BYREF
  _QWORD v21[3]; // [rsp+38h] [rbp-190h] BYREF
  void **v22; // [rsp+50h] [rbp-178h] BYREF
  int v23; // [rsp+58h] [rbp-170h] BYREF
  char v24; // [rsp+5Ch] [rbp-16Ch]
  int v25; // [rsp+80h] [rbp-148h] BYREF
  const char *v26; // [rsp+88h] [rbp-140h]
  __int64 v27; // [rsp+90h] [rbp-138h]
  char v28; // [rsp+98h] [rbp-130h]
  int v29; // [rsp+A0h] [rbp-128h]
  _BYTE v30[152]; // [rsp+A8h] [rbp-120h] BYREF
  __int128 v31; // [rsp+140h] [rbp-88h]
  int v32; // [rsp+150h] [rbp-78h]
  __int64 v33; // [rsp+158h] [rbp-70h]
  int *v34; // [rsp+160h] [rbp-68h]
  __int64 v35; // [rsp+168h] [rbp-60h]
  __int64 v36; // [rsp+170h] [rbp-58h]
  void ***v37; // [rsp+178h] [rbp-50h]
  __int64 v38; // [rsp+180h] [rbp-48h]
  int v39; // [rsp+188h] [rbp-40h]
  int *v40; // [rsp+190h] [rbp-38h]
  char v41; // [rsp+198h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+1C8h] [rbp+0h]

  v5 = a4;
  try
  {
    GetCbsLanguageFeatures();
    if ( v21[0] == v21[1] )
      ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
    v23 = 0;
    v24 = 0;
    v28 = 0;
    v25 = 0;
    v26 = "InstallationRequest";
    v27 = 0;
    v29 = 0;
    v31 = 0;
    memset_0(v30, 0, sizeof(v30));
    v32 = 1;
    v33 = 0;
    v34 = &v23;
    v35 = 0;
    v36 = 0;
    v37 = &v22;
    v38 = 0;
    v39 = 0;
    v40 = &v25;
    v41 = 0;
    v22 = &LanguageComponentsInstallerTelemetry::InstallationRequest::`vftable';
    LanguageComponentsInstallerTelemetry::InstallationRequest::StartActivity(&v22, v21);
    LibraryW = LoadLibraryW(L"UpdateAPI.dll");
    if ( LibraryW )
    {
      FreeLibrary(LibraryW);
      v8 = 1;
    }
    else
    {
      v8 = 0;
    }
    v9 = RtlPublishWnfStateData(WNF_LANG_FOD_INSTALLATION_STARTED, 0, 0, 0) | 0x10000000;
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x35A,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
        (const char *)(unsigned int)v9,
        0);
    if ( v8 )
    {
      v13 = OptionalityFeaturesProvider::InstallFeatures(v21);
      goto LABEL_22;
    }
    v20 = 0;
    v10 = LUAIsUserUACAdmin(&v20);
    IsOSSilentElevationOn = LUAIsAdminAndIsOSSilentElevationOn();
    if ( a5 )
    {
      if ( a5 != 1 )
      {
        if ( a5 == 2 )
        {
LABEL_12:
          v12 = CbsFeaturesProvider::SendRequest(v21, 1, a3, (unsigned int)(v5 << 9));
          v13 = v12;
          if ( v12 < 0 )
          {
            v14 = (unsigned int)v12;
            v15 = 78;
LABEL_19:
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)v15,
              (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\languagefeaturesprovider.cpp",
              (const char *)v14,
              0);
            goto LABEL_22;
          }
          v13 = 0;
LABEL_22:
          if ( !(_BYTE)v5 )
          {
            StoreInstallResultInRegistry(v13, v21);
            v17 = RtlPublishWnfStateData(WNF_LANG_FOD_INSTALLATION_COMPLETED, 0, 0, 0) | 0x10000000;
            if ( v17 < 0 )
              wil::details::in1diag3::_Throw_Hr(
                retaddr,
                (void *)0x35A,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\resource.h",
                (const char *)(unsigned int)v17,
                0);
          }
          wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
            &v22,
            v13);
          v22 = &LanguageComponentsInstallerTelemetry::InstallationRequest::`vftable';
          wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v22);
          wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(&v22);
          std::vector<CbsLanguageFeature>::_Tidy(v21);
          return v13;
        }
LABEL_18:
        v13 = -2147024891;
        v14 = 2147942405LL;
        v15 = 71;
        goto LABEL_19;
      }
      if ( v10 < 0 )
        goto LABEL_18;
      v16 = v20 == 0;
    }
    else
    {
      v16 = IsOSSilentElevationOn == 0;
    }
    if ( !v16 )
      goto LABEL_12;
    goto LABEL_18;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x3A,
                           (unsigned int)"onecore\\shell\\cpls\\internationalsettings\\languagecomponentsinstaller\\dll\\"
                                         "installerrequests.cpp",
                           v18);
  }
  return result;
}

```

## disassembly

```asm
0x180025d20  mov     [rsp+arg_8], rbx
0x180025d25  mov     [rsp+arg_18], rsi
0x180025d2a  push    rdi
0x180025d2b  push    r13
0x180025d2d  push    r14
0x180025d2f  sub     rsp, 1B0h
0x180025d36  mov     rax, cs:__security_cookie
0x180025d3d  xor     rax, rsp
0x180025d40  mov     [rsp+1C8h+var_28], rax
0x180025d48  movzx   edi, r9b
0x180025d4c  mov     rsi, r8
0x180025d4f  lea     rax, [rdx+rdx*2]
0x180025d53  lea     r8, [rcx+rax*8]
0x180025d57  mov     rdx, rcx
0x180025d5a  lea     rcx, [rsp+1C8h+var_190]
0x180025d5f  call    ?GetCbsLanguageFeatures@@YA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@PEBUCbsLanguageFeatureId@@0@Z; GetCbsLanguageFeatures(CbsLanguageFeatureId const *,CbsLanguageFeatureId const *)
0x180025d64  nop
0x180025d65  mov     rax, [rsp+1C8h+var_188]
0x180025d6a  cmp     [rsp+1C8h+var_190], rax
0x180025d6f  jnz     short loc_180025D77
0x180025d71  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025d76  nop
0x180025d77  xor     r14d, r14d
0x180025d7a  mov     [rsp+1C8h+var_170], r14d
0x180025d7f  mov     [rsp+1C8h+var_16C], r14b
0x180025d84  mov     [rsp+1C8h+var_130], r14b
0x180025d8c  mov     [rsp+1C8h+var_148], r14d
0x180025d94  lea     rax, aInstallationre; "InstallationRequest"
0x180025d9b  mov     [rsp+1C8h+var_140], rax
0x180025da3  mov     [rsp+1C8h+var_138], r14
0x180025dab  mov     [rsp+1C8h+var_128], r14d
0x180025db3  xorps   xmm0, xmm0
0x180025db6  movdqa  [rsp+1C8h+var_88], xmm0
0x180025dbf  xor     edx, edx; Val
0x180025dc1  mov     r8d, 98h; Size
0x180025dc7  lea     rcx, [rsp+1C8h+var_120]; void *
0x180025dcf  call    memset_0
0x180025dd4  mov     [rsp+1C8h+var_78], 1
0x180025ddf  xor     eax, eax
0x180025de1  mov     [rsp+1C8h+var_70], rax
0x180025de9  lea     rax, [rsp+1C8h+var_170]
0x180025dee  mov     [rsp+1C8h+var_68], rax
0x180025df6  mov     [rsp+1C8h+var_60], r14
0x180025dfe  mov     [rsp+1C8h+var_58], r14
0x180025e06  lea     rax, [rsp+1C8h+var_178]
0x180025e0b  mov     [rsp+1C8h+var_50], rax
0x180025e13  mov     [rsp+1C8h+var_48], r14
0x180025e1b  mov     [rsp+1C8h+var_40], r14d
0x180025e23  lea     rax, [rsp+1C8h+var_148]
0x180025e2b  mov     [rsp+1C8h+var_38], rax
0x180025e33  mov     [rsp+1C8h+var_30], r14b
0x180025e3b  lea     r13, ??_7InstallationRequest@LanguageComponentsInstallerTelemetry@@6B@; const LanguageComponentsInstallerTelemetry::InstallationRequest::`vftable'
0x180025e42  mov     [rsp+1C8h+var_178], r13
0x180025e47  lea     rdx, [rsp+1C8h+var_190]
0x180025e4c  lea     rcx, [rsp+1C8h+var_178]
0x180025e51  call    ?StartActivity@InstallationRequest@LanguageComponentsInstallerTelemetry@@QEAAXAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z; LanguageComponentsInstallerTelemetry::InstallationRequest::StartActivity(std::vector<CbsLanguageFeature> const &)
0x180025e56  nop
0x180025e57  lea     rcx, LibFileName; "UpdateAPI.dll"
0x180025e5e  call    cs:__imp_LoadLibraryW
0x180025e64  test    rax, rax
0x180025e67  jnz     short loc_180025E6E
0x180025e69  mov     bl, r14b
0x180025e6c  jmp     short loc_180025E79
0x180025e6e  mov     rcx, rax; hLibModule
0x180025e71  call    cs:__imp_FreeLibrary
0x180025e77  mov     bl, 1
0x180025e79  mov     qword ptr [rsp+1C8h+var_1A8], r14; int
0x180025e7e  xor     r9d, r9d
0x180025e81  xor     r8d, r8d
0x180025e84  xor     edx, edx
0x180025e86  mov     rcx, cs:WNF_LANG_FOD_INSTALLATION_STARTED
0x180025e8d  call    cs:__imp_RtlPublishWnfStateData
0x180025e93  or      eax, 10000000h
0x180025e98  mov     rcx, [rsp+1C8h]; this
0x180025ea0  jl      loc_180025FEB
0x180025ea6  test    bl, bl
0x180025ea8  jnz     loc_180025F39
0x180025eae  mov     [rsp+1C8h+var_198], r14d
0x180025eb3  lea     rcx, [rsp+1C8h+var_198]
0x180025eb8  call    LUAIsUserUACAdmin
0x180025ebd  mov     ebx, eax
0x180025ebf  call    LUAIsAdminAndIsOSSilentElevationOn
0x180025ec4  mov     edx, [rsp+1C8h+arg_20]
0x180025ecb  test    edx, edx
0x180025ecd  jz      short loc_180025F0D
0x180025ecf  sub     edx, 1
0x180025ed2  jz      short loc_180025F02
0x180025ed4  cmp     edx, 1
0x180025ed7  jnz     short loc_180025F11
0x180025ed9  mov     r9d, edi
0x180025edc  shl     r9d, 9
0x180025ee0  mov     r8, rsi
0x180025ee3  mov     edx, 1
0x180025ee8  lea     rcx, [rsp+1C8h+var_190]
0x180025eed  call    ?SendRequest@CbsFeaturesProvider@@YAJAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@W4RequestType@@PEAUICbsUIHandler@@K@Z; CbsFeaturesProvider::SendRequest(std::vector<CbsLanguageFeature> const &,RequestType,ICbsUIHandler *,ulong)
0x180025ef2  mov     ebx, eax
0x180025ef4  test    eax, eax
0x180025ef6  jns     short loc_180025F34
0x180025ef8  mov     r9d, eax
0x180025efb  mov     edx, 4Eh ; 'N'
0x180025f00  jmp     short loc_180025F1E
0x180025f02  test    ebx, ebx
0x180025f04  js      short loc_180025F11
0x180025f06  cmp     [rsp+1C8h+var_198], r14d
0x180025f0b  jmp     short loc_180025F0F
0x180025f0d  test    eax, eax
0x180025f0f  jnz     short loc_180025ED9
0x180025f11  mov     ebx, 80070005h
0x180025f16  mov     r9d, ebx; char *
0x180025f19  mov     edx, 47h ; 'G'; void *
0x180025f1e  lea     r8, aOnecoreShellCp_3; "onecore\\shell\\cpls\\internationalsett"...
0x180025f25  mov     rcx, [rsp+1C8h]; this
0x180025f2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025f32  jmp     short loc_180025F4F
0x180025f34  mov     ebx, r14d
0x180025f37  jmp     short loc_180025F4F
0x180025f39  cmp     bl, 1
0x180025f3c  jz      short loc_180025F43
0x180025f3e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180025f43  lea     rcx, [rsp+1C8h+var_190]
0x180025f48  call    ?InstallFeatures@OptionalityFeaturesProvider@@YAJAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z; OptionalityFeaturesProvider::InstallFeatures(std::vector<CbsLanguageFeature> const &)
0x180025f4d  mov     ebx, eax
0x180025f4f  test    dil, dil
0x180025f52  jnz     short loc_180025F89
0x180025f54  lea     rdx, [rsp+1C8h+var_190]
0x180025f59  mov     ecx, ebx
0x180025f5b  call    ?StoreInstallResultInRegistry@@YAXJAEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z; StoreInstallResultInRegistry(long,std::vector<CbsLanguageFeature> const &)
0x180025f60  mov     qword ptr [rsp+1C8h+var_1A8], r14; int
0x180025f65  xor     r9d, r9d
0x180025f68  xor     r8d, r8d
0x180025f6b  xor     edx, edx
0x180025f6d  mov     rcx, cs:WNF_LANG_FOD_INSTALLATION_COMPLETED
0x180025f74  call    cs:__imp_RtlPublishWnfStateData
0x180025f7a  or      eax, 10000000h
0x180025f7f  mov     rcx, [rsp+1C8h]; this
0x180025f87  jl      short loc_180025FFF
0x180025f89  mov     edx, ebx
0x180025f8b  lea     rcx, [rsp+1C8h+var_178]
0x180025f90  call    ?Stop@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180025f95  nop
0x180025f96  mov     [rsp+1C8h+var_178], r13
0x180025f9b  lea     rcx, [rsp+1C8h+var_178]
0x180025fa0  call    ?Destroy@?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180025fa5  lea     rcx, [rsp+1C8h+var_178]
0x180025faa  call    ??1?$ActivityBase@VLanguageComponentsInstallerTelemetryProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<LanguageComponentsInstallerTelemetryProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(void)
0x180025faf  nop
0x180025fb0  lea     rcx, [rsp+1C8h+var_190]
0x180025fb5  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x180025fba  mov     eax, ebx
0x180025fbc  jmp     short loc_180025FC2
0x180025fbe  mov     eax, [rsp+1C8h+var_198]
0x180025fc2  mov     rcx, [rsp+1C8h+var_28]
0x180025fca  xor     rcx, rsp; StackCookie
0x180025fcd  call    __security_check_cookie
0x180025fd2  lea     r11, [rsp+1C8h+var_18]
0x180025fda  mov     rbx, [r11+28h]
0x180025fde  mov     rsi, [r11+38h]
0x180025fe2  mov     rsp, r11
0x180025fe5  pop     r14
0x180025fe7  pop     r13
0x180025fe9  pop     rdi
0x180025fea  retn
0x180025feb  mov     r9d, eax; char *
0x180025fee  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x180025ff5  mov     edx, 35Ah; void *
0x180025ffa  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180025fff  mov     r9d, eax; char *
0x180026002  lea     r8, aOnecoreInterna_2; "onecore\\internal\\sdk\\inc\\wil\\resou"...
0x180026009  mov     edx, 35Ah; void *
0x18002600e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
```
