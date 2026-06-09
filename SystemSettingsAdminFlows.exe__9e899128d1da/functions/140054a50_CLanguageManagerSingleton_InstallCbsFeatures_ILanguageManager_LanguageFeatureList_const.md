# CLanguageManagerSingleton::_InstallCbsFeatures(ILanguageManager *,LanguageFeatureList const *)

- ea: `0x140054a50`
- end: `0x140054ede`
- name: `?_InstallCbsFeatures@CLanguageManagerSingleton@@AEAAJPEAUILanguageManager@@PEBULanguageFeatureList@@@Z`
- size: `1166`
- prototype: `__int64 __fastcall(CLanguageManagerSingleton *__hidden this, struct ILanguageManager *, const struct LanguageFeatureList *)`
- caller_count: `1`
- callee_count: `25`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14004d1d0`

## callees

- `0x140005f30`
- `0x14000c3c8`
- `0x14001f3d4`
- `0x140029eb8`
- `0x14002a3e8`
- `0x1400337b0`
- `0x14003f000`
- `0x140045a88`
- `0x140045f1c`
- `0x140046bf4`
- `0x140047834`
- `0x140049b84`
- `0x140049fc8`
- `0x14004bc48`
- `0x14004c188`
- `0x14004c3d0`
- `0x14004cfb8`
- `0x14004d180`
- `0x14004d2a0`
- `0x14004e1e8`
- `0x140051b60`
- `0x14005390c`
- `0x140054a50`
- `0x140055af4`
- `0x140055d84`

## import_xrefs

- `KERNEL32!EnterCriticalSection` at `0x140054b43`
- `KERNEL32!EnterCriticalSection` at `0x140054b43`
- `LanguageComponentsInstaller!RequestFeaturesInstallation` at `0x140054cb9`
- `LanguageComponentsInstaller!RequestFeaturesInstallation` at `0x140054cb9`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall CLanguageManagerSingleton::_InstallCbsFeatures(
        CLanguageManagerSingleton *this,
        struct ILanguageManager *a2,
        const struct LanguageFeatureList *a3)
{
  __int64 SerializedLanguageFeatures; // rax
  signed __int32 v7; // ebx
  __int64 v8; // r9
  __int64 v9; // rax
  int v10; // r14d
  CLanguageManagerSingleton *v11; // r15
  __int64 v12; // rbx
  _DWORD *v13; // rdi
  int v14; // eax
  unsigned int v15; // ebx
  __int64 v16; // r9
  int v17; // eax
  int v18; // eax
  int v19; // [rsp+20h] [rbp-218h]
  PVOID Parameter; // [rsp+30h] [rbp-208h] BYREF
  int v21[2]; // [rsp+38h] [rbp-200h] BYREF
  _QWORD v22[2]; // [rsp+40h] [rbp-1F8h] BYREF
  _DWORD v23[2]; // [rsp+50h] [rbp-1E8h] BYREF
  CLanguageManagerSingleton *v24; // [rsp+58h] [rbp-1E0h]
  char v25; // [rsp+60h] [rbp-1D8h]
  __int64 v26; // [rsp+70h] [rbp-1C8h] BYREF
  std::_Ref_count_base *v27; // [rsp+78h] [rbp-1C0h]
  __int128 v28; // [rsp+80h] [rbp-1B8h] BYREF
  __int64 v29; // [rsp+90h] [rbp-1A8h]
  _QWORD v30[3]; // [rsp+98h] [rbp-1A0h] BYREF
  _BYTE v31[336]; // [rsp+B0h] [rbp-188h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+238h] [rbp+0h]

  CLanguageManagerSingleton::_GetLanguageFeatures(v30, a3);
  if ( v30[1] == v30[0] )
  {
    std::vector<CbsLanguageFeature>::_Tidy(v30);
    return 0;
  }
  SerializedLanguageFeatures = CLanguageManagerSingleton::_GetSerializedLanguageFeatures(v23, v30);
  *(_QWORD *)v21 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(SerializedLanguageFeatures);
  LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest::Start<unsigned short const *>(
    (LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest *)v31,
    (const unsigned __int16 **)v21);
  std::wstring::_Tidy_deallocate(v23);
  std::make_shared<LANGUAGE_FEATURES_INSTALLATION,>(&v26);
  v7 = _InterlockedIncrement((volatile signed __int32 *)this + 22);
  v21[0] = v7;
  Microsoft::WRL::ComPtr<ILanguageManager>::operator=(v26, a2);
  *(_DWORD *)(v26 + 40) = 1;
  std::vector<CbsLanguageFeature>::operator=(v26 + 16, v30);
  *(_DWORD *)(v26 + 8) = v7;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 96));
  v22[0] = (char *)this + 96;
  if ( *((_QWORD *)this + 18) == *((_QWORD *)this + 19) )
  {
    std::vector<std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>>::_Emplace_reallocate<std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> const &>(
      (__int64 *)this + 17,
      *((void **)this + 18),
      (__int64)&v26);
  }
  else
  {
    std::_Construct_in_place<std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>,std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> const &>();
    *(_QWORD *)(v8 + 8) += 16LL;
  }
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)v22);
  v9 = lambda_10f371a7cd363efdae7abed437b57372_::_lambda_10f371a7cd363efdae7abed437b57372_(v22, v21, this);
  v10 = *(_DWORD *)v9;
  v23[0] = *(_DWORD *)v9;
  v23[1] = *(_DWORD *)(v9 + 4);
  v11 = *(CLanguageManagerSingleton **)(v9 + 8);
  v24 = v11;
  v25 = 1;
  Parameter = 0;
  v12 = v26 + 16;
  v13 = (_DWORD *)(v26 + 8);
  v22[0] = this;
  Microsoft::WRL::ComPtr<CbsInstallProgressHandler>::InternalRelease(&Parameter);
  v14 = Microsoft::WRL::Details::MakeAndInitialize<CbsInstallProgressHandler,CbsInstallProgressHandler,LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest &,CLanguageManagerSingleton *,long &,std::vector<CbsLanguageFeature> &>(
          &Parameter,
          (int)v31,
          v22,
          v13,
          v12);
  v15 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A2,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v14,
      v19);
    Microsoft::WRL::ComPtr<CbsInstallProgressHandler>::InternalRelease(&Parameter);
    CLanguageManagerSingleton::_RemoveInstallation(v11, v10);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
LABEL_21:
    LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest::~InstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest *)v31);
    std::vector<CbsLanguageFeature>::_Tidy(v30);
    return v15;
  }
  GetCbsLanguageFeatureIds(&v28, *(_QWORD *)(v26 + 16), *(_QWORD *)(v26 + 24));
  LOBYTE(v16) = 1;
  v17 = RequestFeaturesInstallation(
          v28,
          0xAAAAAAAAAAAAAAABuLL * ((__int64)(*((_QWORD *)&v28 + 1) - v28) >> 3),
          Parameter,
          v16);
  v15 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AA,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v17,
      1);
    if ( (_QWORD)v28 )
    {
      std::_Deallocate<16>((void *)v28, (struct std::nothrow_t *)(8 * ((v29 - (__int64)v28) >> 3)));
      v28 = 0;
      v29 = 0;
    }
    Microsoft::WRL::ComPtr<CbsInstallProgressHandler>::InternalRelease(&Parameter);
    CLanguageManagerSingleton::_RemoveInstallation(v11, v10);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    goto LABEL_21;
  }
  v18 = CbsInstallProgressHandler::Initiate(Parameter, 0, v21);
  v15 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B1,
      (unsigned int)"pcshell\\shell\\systemsettings\\adminflows\\languagemanager\\lib\\languagemanagersingleton.cpp",
      (const char *)(unsigned int)v18,
      1);
    if ( (_QWORD)v28 )
    {
      std::_Deallocate<16>((void *)v28, (struct std::nothrow_t *)(8 * ((v29 - (__int64)v28) >> 3)));
      v28 = 0;
      v29 = 0;
    }
    Microsoft::WRL::ComPtr<CbsInstallProgressHandler>::InternalRelease(&Parameter);
    if ( v27 )
      std::_Ref_count_base::_Decref(v27);
    goto LABEL_21;
  }
  wil::ActivityBase<LanguageFeaturesOnDemandSettings,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v31,
    0);
  if ( (_QWORD)v28 )
  {
    std::_Deallocate<16>((void *)v28, (struct std::nothrow_t *)(8 * ((v29 - (__int64)v28) >> 3)));
    v28 = 0;
    v29 = 0;
  }
  Microsoft::WRL::ComPtr<CbsInstallProgressHandler>::InternalRelease(&Parameter);
  if ( v27 )
    std::_Ref_count_base::_Decref(v27);
  LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest::~InstallRequest((LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest *)v31);
  std::vector<CbsLanguageFeature>::_Tidy(v30);
  return 0;
}

```

## disassembly

```asm
0x140054a50  push    rbx
0x140054a52  push    rsi
0x140054a53  push    rdi
0x140054a54  push    r14
0x140054a56  push    r15
0x140054a58  sub     rsp, 210h
0x140054a5f  mov     rax, cs:__security_cookie
0x140054a66  xor     rax, rsp
0x140054a69  mov     [rsp+238h+var_38], rax
0x140054a71  mov     rdi, rdx
0x140054a74  mov     rsi, rcx
0x140054a77  mov     rdx, r8
0x140054a7a  lea     rcx, [rsp+238h+var_1A0]
0x140054a82  call    ?_GetLanguageFeatures@CLanguageManagerSingleton@@CA?AV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@PEBULanguageFeatureList@@@Z; CLanguageManagerSingleton::_GetLanguageFeatures(LanguageFeatureList const *)
0x140054a87  nop
0x140054a88  mov     rax, [rsp+238h+var_198]
0x140054a90  cmp     rax, [rsp+238h+var_1A0]
0x140054a98  jnz     short loc_140054AAE
0x140054a9a  lea     rcx, [rsp+238h+var_1A0]
0x140054aa2  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x140054aa7  xor     eax, eax
0x140054aa9  jmp     loc_140054EBE
0x140054aae  lea     rdx, [rsp+238h+var_1A0]
0x140054ab6  lea     rcx, [rsp+238h+var_1E8]
0x140054abb  call    ?_GetSerializedLanguageFeatures@CLanguageManagerSingleton@@CA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@3@@Z; CLanguageManagerSingleton::_GetSerializedLanguageFeatures(std::vector<CbsLanguageFeature> const &)
0x140054ac0  mov     rcx, rax
0x140054ac3  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x140054ac8  mov     qword ptr [rsp+238h+var_200], rax
0x140054acd  lea     rdx, [rsp+238h+var_200]
0x140054ad2  lea     rcx, [rsp+238h+var_188]; this
0x140054ada  call    ??$Start@PEBG@InstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@SA?AV01@$$QEAPEBG@Z; LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest::Start<ushort const *>(ushort const * &&)
0x140054adf  nop
0x140054ae0  lea     rcx, [rsp+238h+var_1E8]
0x140054ae5  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x140054aea  lea     rcx, [rsp+238h+var_1C8]
0x140054aef  call    ??$make_shared@ULANGUAGE_FEATURES_INSTALLATION@@$$V@std@@YA?AV?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@0@XZ; std::make_shared<LANGUAGE_FEATURES_INSTALLATION,>(void)
0x140054af4  nop
0x140054af5  mov     ebx, 1
0x140054afa  lock xadd [rsi+58h], ebx
0x140054aff  inc     ebx
0x140054b01  mov     [rsp+238h+var_200], ebx
0x140054b05  mov     rdx, rdi
0x140054b08  mov     rcx, [rsp+238h+var_1C8]
0x140054b0d  call    ??4?$ComPtr@UILanguageManager@@@WRL@Microsoft@@QEAAAEAV012@PEAUILanguageManager@@@Z; Microsoft::WRL::ComPtr<ILanguageManager>::operator=(ILanguageManager *)
0x140054b12  mov     rax, [rsp+238h+var_1C8]
0x140054b17  mov     dword ptr [rax+28h], 1
0x140054b1e  mov     rcx, [rsp+238h+var_1C8]
0x140054b23  add     rcx, 10h
0x140054b27  lea     rdx, [rsp+238h+var_1A0]
0x140054b2f  call    ??4?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<CbsLanguageFeature>::operator=(std::vector<CbsLanguageFeature> const &)
0x140054b34  mov     rax, [rsp+238h+var_1C8]
0x140054b39  mov     [rax+8], ebx
0x140054b3c  lea     rbx, [rsi+60h]
0x140054b40  mov     rcx, rbx; lpCriticalSection
0x140054b43  call    cs:__imp_EnterCriticalSection
0x140054b49  mov     [rsp+238h+var_1F8], rbx
0x140054b4e  lea     r9, [rsi+88h]
0x140054b55  mov     rcx, [r9+8]
0x140054b59  cmp     rcx, [r9+10h]
0x140054b5d  jz      short loc_140054B70
0x140054b5f  lea     rdx, [rsp+238h+var_1C8]
0x140054b64  call    ??$_Construct_in_place@V?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@std@@AEBV12@@std@@YAXAEAV?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@0@AEBV10@@Z; std::_Construct_in_place<std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>,std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> const &>(std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> &,std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> const &)
0x140054b69  add     qword ptr [r9+8], 10h
0x140054b6e  jmp     short loc_140054B81
0x140054b70  lea     r8, [rsp+238h+var_1C8]
0x140054b75  mov     rdx, rcx
0x140054b78  mov     rcx, r9
0x140054b7b  call    ??$_Emplace_reallocate@AEBV?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@std@@@?$vector@V?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@std@@V?$allocator@V?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@std@@@2@@std@@AEAAPEAV?$shared_ptr@ULANGUAGE_FEATURES_INSTALLATION@@@1@QEAV21@AEBV21@@Z; std::vector<std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION>>::_Emplace_reallocate<std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> const &>(std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> * const,std::shared_ptr<LANGUAGE_FEATURES_INSTALLATION> const &)
0x140054b80  nop
0x140054b81  lea     rcx, [rsp+238h+var_1F8]; this
0x140054b86  call    ?InternalUnlock@SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@AEAAXXZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::InternalUnlock(void)
0x140054b8b  mov     r8, rsi
0x140054b8e  lea     rdx, [rsp+238h+var_200]
0x140054b93  lea     rcx, [rsp+238h+var_1F8]
0x140054b98  call    _lambda_10f371a7cd363efdae7abed437b57372____lambda_10f371a7cd363efdae7abed437b57372_
0x140054b9d  mov     r14d, [rax]
0x140054ba0  mov     [rsp+238h+var_1E8], r14d
0x140054ba5  mov     ecx, [rax+4]
0x140054ba8  mov     [rsp+238h+var_1E4], ecx
0x140054bac  mov     r15, [rax+8]
0x140054bb0  mov     [rsp+238h+var_1E0], r15
0x140054bb5  mov     [rsp+238h+var_1D8], 1
0x140054bba  mov     [rsp+238h+Parameter], 0
0x140054bc3  mov     rax, [rsp+238h+var_1C8]
0x140054bc8  lea     rbx, [rax+10h]
0x140054bcc  lea     rdi, [rax+8]
0x140054bd0  mov     [rsp+238h+var_1F8], rsi
0x140054bd5  lea     rcx, [rsp+238h+Parameter]
0x140054bda  call    ?InternalRelease@?$ComPtr@VCbsInstallProgressHandler@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CbsInstallProgressHandler>::InternalRelease(void)
0x140054bdf  mov     qword ptr [rsp+238h+var_218], rbx; int
0x140054be4  mov     r9, rdi
0x140054be7  lea     r8, [rsp+238h+var_1F8]
0x140054bec  lea     rdx, [rsp+238h+var_188]
0x140054bf4  lea     rcx, [rsp+238h+Parameter]
0x140054bf9  call    ??$MakeAndInitialize@VCbsInstallProgressHandler@@V1@AEAVInstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@PEAVCLanguageManagerSingleton@@AEAJAEAV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Details@WRL@Microsoft@@YAJPEAPEAVCbsInstallProgressHandler@@AEAVInstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@$$QEAPEAVCLanguageManagerSingleton@@AEAJAEAV?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@@Z; Microsoft::WRL::Details::MakeAndInitialize<CbsInstallProgressHandler,CbsInstallProgressHandler,LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest &,CLanguageManagerSingleton *,long &,std::vector<CbsLanguageFeature> &>(CbsInstallProgressHandler * *,LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest &,CLanguageManagerSingleton * &&,long &,std::vector<CbsLanguageFeature> &)
0x140054bfe  mov     ebx, eax
0x140054c00  test    eax, eax
0x140054c02  jns     short loc_140054C6A
0x140054c04  mov     rcx, [rsp+238h]; this
0x140054c0c  mov     r9d, eax; char *
0x140054c0f  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x140054c16  mov     edx, 1A2h; void *
0x140054c1b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054c20  nop
0x140054c21  lea     rcx, [rsp+238h+Parameter]
0x140054c26  call    ?InternalRelease@?$ComPtr@VCbsInstallProgressHandler@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CbsInstallProgressHandler>::InternalRelease(void)
0x140054c2b  nop
0x140054c2c  mov     edx, r14d; int
0x140054c2f  mov     rcx, r15; this
0x140054c32  call    ?_RemoveInstallation@CLanguageManagerSingleton@@AEAAXJ@Z; CLanguageManagerSingleton::_RemoveInstallation(long)
0x140054c37  nop
0x140054c38  mov     rcx, [rsp+238h+var_1C0]; this
0x140054c3d  test    rcx, rcx
0x140054c40  jz      short loc_140054C48
0x140054c42  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140054c47  nop
0x140054c48  lea     rcx, [rsp+238h+var_188]; this
0x140054c50  call    ??1InstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@QEAA@XZ; LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest::~InstallRequest(void)
0x140054c55  nop
0x140054c56  lea     rcx, [rsp+238h+var_1A0]
0x140054c5e  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x140054c63  mov     eax, ebx
0x140054c65  jmp     loc_140054EBE
0x140054c6a  mov     rdx, [rsp+238h+var_1C8]
0x140054c6f  mov     r8, [rdx+18h]
0x140054c73  mov     rdx, [rdx+10h]
0x140054c77  lea     rcx, [rsp+238h+var_1B8]
0x140054c7f  call    ?GetCbsLanguageFeatureIds@@YA?AV?$vector@UCbsLanguageFeatureId@@V?$allocator@UCbsLanguageFeatureId@@@std@@@std@@V?$_Vector_const_iterator@V?$_Vector_val@U?$_Simple_types@VCbsLanguageFeature@@@std@@@std@@@2@0@Z; GetCbsLanguageFeatureIds(std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>,std::_Vector_const_iterator<std::_Vector_val<std::_Simple_types<CbsLanguageFeature>>>)
0x140054c84  mov     rcx, qword ptr [rsp+238h+var_1B8]
0x140054c8c  mov     rdx, qword ptr [rsp+238h+var_1B8+8]
0x140054c94  sub     rdx, rcx
0x140054c97  sar     rdx, 3
0x140054c9b  mov     rdi, 0AAAAAAAAAAAAAAABh
0x140054ca5  imul    rdx, rdi
0x140054ca9  mov     [rsp+238h+var_218], 1; int
0x140054cb1  mov     r9b, 1
0x140054cb4  mov     r8, [rsp+238h+Parameter]
0x140054cb9  call    cs:__imp_RequestFeaturesInstallation
0x140054cbf  mov     ebx, eax
0x140054cc1  test    eax, eax
0x140054cc3  jns     loc_140054D73
0x140054cc9  mov     rcx, [rsp+238h]; this
0x140054cd1  mov     r9d, eax; char *
0x140054cd4  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x140054cdb  mov     edx, 1AAh; void *
0x140054ce0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054ce5  mov     rcx, qword ptr [rsp+238h+var_1B8]
0x140054ced  test    rcx, rcx
0x140054cf0  jz      short loc_140054D2A
0x140054cf2  mov     rdx, [rsp+238h+var_1A8]
0x140054cfa  sub     rdx, rcx
0x140054cfd  sar     rdx, 3
0x140054d01  imul    rdx, rdi
0x140054d05  lea     rdx, [rdx+rdx*2]
0x140054d09  shl     rdx, 3
0x140054d0d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140054d12  xorps   xmm0, xmm0
0x140054d15  movdqu  [rsp+238h+var_1B8], xmm0
0x140054d1e  mov     [rsp+238h+var_1A8], 0
0x140054d2a  lea     rcx, [rsp+238h+Parameter]
0x140054d2f  call    ?InternalRelease@?$ComPtr@VCbsInstallProgressHandler@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CbsInstallProgressHandler>::InternalRelease(void)
0x140054d34  nop
0x140054d35  mov     edx, r14d; int
0x140054d38  mov     rcx, r15; this
0x140054d3b  call    ?_RemoveInstallation@CLanguageManagerSingleton@@AEAAXJ@Z; CLanguageManagerSingleton::_RemoveInstallation(long)
0x140054d40  nop
0x140054d41  mov     rcx, [rsp+238h+var_1C0]; this
0x140054d46  test    rcx, rcx
0x140054d49  jz      short loc_140054D51
0x140054d4b  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140054d50  nop
0x140054d51  lea     rcx, [rsp+238h+var_188]; this
0x140054d59  call    ??1InstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@QEAA@XZ; LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest::~InstallRequest(void)
0x140054d5e  nop
0x140054d5f  lea     rcx, [rsp+238h+var_1A0]
0x140054d67  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x140054d6c  mov     eax, ebx
0x140054d6e  jmp     loc_140054EBE
0x140054d73  lea     r8, [rsp+238h+var_200]; int *
0x140054d78  xor     edx, edx; struct IEnumCbsUpdate *
0x140054d7a  mov     rcx, [rsp+238h+Parameter]; Parameter
0x140054d7f  call    ?Initiate@CbsInstallProgressHandler@@UEAAJPEAUIEnumCbsUpdate@@PEAH@Z; CbsInstallProgressHandler::Initiate(IEnumCbsUpdate *,int *)
0x140054d84  mov     ebx, eax
0x140054d86  test    eax, eax
0x140054d88  jns     loc_140054E2C
0x140054d8e  mov     rcx, [rsp+238h]; this
0x140054d96  mov     r9d, eax; char *
0x140054d99  lea     r8, aPcshellShellSy_0; "pcshell\\shell\\systemsettings\\adminfl"...
0x140054da0  mov     edx, 1B1h; void *
0x140054da5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x140054daa  mov     rcx, qword ptr [rsp+238h+var_1B8]
0x140054db2  test    rcx, rcx
0x140054db5  jz      short loc_140054DEF
0x140054db7  mov     rdx, [rsp+238h+var_1A8]
0x140054dbf  sub     rdx, rcx
0x140054dc2  sar     rdx, 3
0x140054dc6  imul    rdx, rdi
0x140054dca  lea     rdx, [rdx+rdx*2]
0x140054dce  shl     rdx, 3
0x140054dd2  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140054dd7  xorps   xmm0, xmm0
0x140054dda  movdqu  [rsp+238h+var_1B8], xmm0
0x140054de3  mov     [rsp+238h+var_1A8], 0
0x140054def  lea     rcx, [rsp+238h+Parameter]
0x140054df4  call    ?InternalRelease@?$ComPtr@VCbsInstallProgressHandler@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CbsInstallProgressHandler>::InternalRelease(void)
0x140054df9  nop
0x140054dfa  mov     rcx, [rsp+238h+var_1C0]; this
0x140054dff  test    rcx, rcx
0x140054e02  jz      short loc_140054E0A
0x140054e04  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140054e09  nop
0x140054e0a  lea     rcx, [rsp+238h+var_188]; this
0x140054e12  call    ??1InstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@QEAA@XZ; LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest::~InstallRequest(void)
0x140054e17  nop
0x140054e18  lea     rcx, [rsp+238h+var_1A0]
0x140054e20  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x140054e25  mov     eax, ebx
0x140054e27  jmp     loc_140054EBE
0x140054e2c  xor     edx, edx
0x140054e2e  lea     rcx, [rsp+238h+var_188]
0x140054e36  call    ?Stop@?$ActivityBase@VLanguageFeaturesOnDemandSettings@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LanguageFeaturesOnDemandSettings,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x140054e3b  mov     rcx, qword ptr [rsp+238h+var_1B8]
0x140054e43  test    rcx, rcx
0x140054e46  jz      short loc_140054E80
0x140054e48  mov     rax, [rsp+238h+var_1A8]
0x140054e50  sub     rax, rcx
0x140054e53  sar     rax, 3
0x140054e57  imul    rax, rdi
0x140054e5b  lea     rdx, [rax+rax*2]
0x140054e5f  shl     rdx, 3
0x140054e63  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x140054e68  xorps   xmm0, xmm0
0x140054e6b  movdqu  [rsp+238h+var_1B8], xmm0
0x140054e74  mov     [rsp+238h+var_1A8], 0
0x140054e80  lea     rcx, [rsp+238h+Parameter]
0x140054e85  call    ?InternalRelease@?$ComPtr@VCbsInstallProgressHandler@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<CbsInstallProgressHandler>::InternalRelease(void)
0x140054e8a  nop
0x140054e8b  mov     rcx, [rsp+238h+var_1C0]; this
0x140054e90  test    rcx, rcx
0x140054e93  jz      short loc_140054E9B
0x140054e95  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x140054e9a  nop
0x140054e9b  lea     rcx, [rsp+238h+var_188]; this
0x140054ea3  call    ??1InstallRequest@LanguageFeaturesOnDemandSettingsTelemetryProvider@@QEAA@XZ; LanguageFeaturesOnDemandSettingsTelemetryProvider::InstallRequest::~InstallRequest(void)
0x140054ea8  nop
0x140054ea9  lea     rcx, [rsp+238h+var_1A0]
0x140054eb1  call    ?_Tidy@?$vector@VCbsLanguageFeature@@V?$allocator@VCbsLanguageFeature@@@std@@@std@@AEAAXXZ; std::vector<CbsLanguageFeature>::_Tidy(void)
0x140054eb6  xor     eax, eax
0x140054eb8  jmp     short loc_140054EBE
0x140054eba  mov     eax, [rsp+238h+var_200]
0x140054ebe  mov     rcx, [rsp+238h+var_38]
0x140054ec6  xor     rcx, rsp; StackCookie
0x140054ec9  call    __security_check_cookie
0x140054ece  add     rsp, 210h
0x140054ed5  pop     r15
0x140054ed7  pop     r14
0x140054ed9  pop     rdi
0x140054eda  pop     rsi
0x140054edb  pop     rbx
0x140054edc  retn
```
