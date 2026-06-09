# NgcIsoContainer::ReadProtectorProperties(void)

- ea: `0x180030bdc`
- end: `0x180031157`
- name: `?ReadProtectorProperties@NgcIsoContainer@@AEAAJXZ`
- size: `1403`
- prototype: `__int64 __fastcall(NgcIsoContainer *__hidden this)`
- caller_count: `1`
- callee_count: `33`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180019bf0`

## callees

- `0x180007670`
- `0x18000d62c`
- `0x1800108c8`
- `0x18001cb98`
- `0x18001cbe8`
- `0x18001d5bc`
- `0x18002c250`
- `0x18002c2bc`
- `0x18002c990`
- `0x18002ca48`
- `0x18002cac8`
- `0x18002cb6c`
- `0x18002d1e4`
- `0x18002d3f0`
- `0x18002daf0`
- `0x18002db80`
- `0x18002dbac`
- `0x18002df38`
- `0x18002dfd4`
- `0x18002e1e0`
- `0x18002e2e4`
- `0x18002ff34`
- `0x180030138`
- `0x180030bdc`
- `0x180034878`
- `0x180034fd0`
- `0x18003500c`
- `0x1800351ec`
- `0x18003cd1c`
- `0x1800752b4`
- `0x1800758fc`
- `0x180075bc4`
- `0x18008b010`

## import_xrefs

- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180030da4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSidToSidW` at `0x180030da4`

## string_xrefs

- `0x180030cdf`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_protectoroperations.cpp`
- `0x180030e13`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_protectoroperations.cpp`
- `0x180030ef9`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_protectoroperations.cpp`
- `0x180030fe1`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_protectoroperations.cpp`
- `0x180031067`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_protectoroperations.cpp`
- `0x180031109`: `onecore\ds\security\ngc\ctnrsvc\iso\container\dll\isocontainer_protectoroperations.cpp`
- `0x180030c0c`: `NgcIsoReadProtectorProperties`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall NgcIsoContainer::ReadProtectorProperties(NgcIsoContainer *this)
{
  FileSystem *v2; // rax
  struct Properties::Protectors *v3; // r8
  int ProtectorProperties; // r14d
  unsigned __int8 v5; // r13
  char v6; // r15
  char v7; // si
  char v8; // r12
  __int64 *v9; // rax
  int v10; // eax
  NgcUtils *v11; // rcx
  const WCHAR *v12; // rax
  BOOL v13; // ebx
  NgcUtils *v14; // rcx
  int updated; // eax
  __int64 *v16; // rax
  int v17; // eax
  bool IsEmpty; // al
  char v19; // cl
  __int64 *v20; // rax
  int v21; // eax
  __int64 *v22; // rax
  int v23; // eax
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  int v27; // [rsp+40h] [rbp-C0h] BYREF
  char v28[4]; // [rsp+44h] [rbp-BCh] BYREF
  int v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v31; // [rsp+58h] [rbp-A8h] BYREF
  int v32[4]; // [rsp+60h] [rbp-A0h] BYREF
  PSID Sid[2]; // [rsp+70h] [rbp-90h] BYREF
  char v34; // [rsp+80h] [rbp-80h]
  _BYTE v35[80]; // [rsp+90h] [rbp-70h] BYREF
  _BYTE v36[368]; // [rsp+E0h] [rbp-20h] BYREF
  unsigned __int16 v37[44]; // [rsp+250h] [rbp+150h] BYREF
  _BYTE v38[368]; // [rsp+2A8h] [rbp+1A8h] BYREF
  _QWORD v39[3]; // [rsp+418h] [rbp+318h] BYREF
  _BYTE v40[368]; // [rsp+430h] [rbp+330h] BYREF
  _BYTE v41[368]; // [rsp+5A0h] [rbp+4A0h] BYREF
  _BYTE v42[32]; // [rsp+710h] [rbp+610h] BYREF
  _BYTE v43[368]; // [rsp+730h] [rbp+630h] BYREF
  _BYTE v44[368]; // [rsp+8A0h] [rbp+7A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A68h] [rbp+968h]

  LogProvider::WatchCurrentThread(v35, "NgcIsoReadProtectorProperties");
  Properties::Protectors::Protectors((Properties::Protectors *)v37);
  v2 = (FileSystem *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 32);
  ProtectorProperties = FileSystem::ReadProtectorProperties(v2, v37, v3);
  v32[0] = ProtectorProperties;
  v5 = 0;
  v28[0] = 0;
  v6 = 0;
  v7 = 0;
  v27 = 0;
  v8 = 0;
  if ( !Properties::SecretStore::IsEmpty((Properties::SecretStore *)v38) )
  {
    v9 = std::make_unique<Protector::Pin,_GUID &,Properties::PinProtector,std::vector<unsigned char> &,0>(
           &v31,
           (__int64)this + 136,
           (__int64)v37,
           (__int64)this + 184);
    std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(
      (__int64 *)this + 64,
      v9);
    std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v31);
    v10 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 64) + 72LL))(*((_QWORD *)this + 64));
    if ( v10 >= 0 )
    {
      v5 = 1;
      v28[0] = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1B5,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_protectoroperations.cpp",
        (const char *)(unsigned int)v10,
        v25);
      if ( !*((_DWORD *)this + 6) )
        *((_DWORD *)this + 6) = 3;
    }
  }
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl'::`2'::impl) )
  {
    if ( NgcUtils::IsNormalBioProtectorEnabled(v11) )
      goto LABEL_17;
LABEL_16:
    Properties::SecretStore::SecretStore((Properties::SecretStore *)v36);
    Properties::SecretStore::operator=(v40, v36);
    Properties::SecretStore::~SecretStore((Properties::SecretStore *)v36);
    *(_OWORD *)Sid = 0;
    std::vector<unsigned char>::operator=(v39, Sid);
    LogProvider::NgcIsoContainerDidNotReadNormalBioProtector();
    goto LABEL_17;
  }
  if ( !NgcUtils::IsNormalBioProtectorEnabled(v11) )
    goto LABEL_16;
  if ( Properties::SecretStore::IsEmpty((Properties::SecretStore *)v40) || v39[0] == v39[1] )
  {
    v31 = 0;
    Sid[0] = &v31;
    Sid[1] = 0;
    v34 = 1;
    v12 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 152);
    v13 = ConvertStringSidToSidW(v12, &Sid[1]);
    wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(Sid);
    if ( v13 )
    {
      v30 = v31;
      v29 = 0;
      Sid[0] = &v30;
      Sid[1] = &v29;
      lambda_dcc46b57e3b17782259cf4b8e691dc4d_::operator()(Sid);
      if ( (v29 & 0x1A) != 0 )
      {
        LogProvider::NgcIsoContainerNormalBioProtectorHealingTriggered<unsigned int &>(&v29);
        updated = NgcUtils::SetBioProtectorUpdateNeeded(v14);
        if ( updated < 0 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x1D5,
            (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_protectoroperations.cpp",
            (const char *)(unsigned int)updated,
            v25);
      }
    }
    wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&void * FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v31);
  }
LABEL_17:
  if ( !Properties::SecretStore::IsEmpty((Properties::SecretStore *)v40)
    || !Properties::SecretStore::IsEmpty((Properties::SecretStore *)v41) )
  {
    v16 = std::make_unique<Protector::Bio,_GUID &,std::wstring &,Properties::BioProtector,0>(
            &v30,
            (NgcIsoContainer *)((char *)this + 136),
            (__int64)this + 152,
            (__int64)v39);
    std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(
      (__int64 *)this + 65,
      v16);
    std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v30);
    v17 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 65) + 72LL))(*((_QWORD *)this + 65));
    if ( v17 >= 0 )
    {
      v6 = !Properties::SecretStore::IsEmpty((Properties::SecretStore *)v40);
      HIBYTE(v27) = v6;
      v7 = !Properties::SecretStore::IsEmpty((Properties::SecretStore *)v41);
      BYTE1(v27) = v7;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x1EB,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_protectoroperations.cpp",
        (const char *)(unsigned int)v17,
        v25);
      if ( !*((_DWORD *)this + 6) )
        *((_DWORD *)this + 6) = 3;
    }
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureBioSekFix>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_SecureBioSekFix>::GetImpl'::`2'::impl) )
    {
      IsEmpty = Properties::SecretStore::IsEmpty((Properties::SecretStore *)v41);
      v19 = v7;
      if ( !IsEmpty )
        v19 = 1;
      v7 = v19;
      BYTE1(v27) = v19;
    }
  }
  if ( !Properties::SecretStore::IsEmpty((Properties::SecretStore *)v43) )
  {
    v20 = std::make_unique<Protector::Recovery,_GUID &,Properties::RecoveryProtector,0>(
            &v30,
            (NgcIsoContainer *)((char *)this + 136),
            (__int64)v42);
    std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(
      (__int64 *)this + 66,
      v20);
    std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v30);
    v21 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 66) + 72LL))(*((_QWORD *)this + 66));
    if ( v21 >= 0 )
    {
      LOBYTE(v27) = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x204,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_protectoroperations.cpp",
        (const char *)(unsigned int)v21,
        v25);
      if ( !*((_DWORD *)this + 6) )
        *((_DWORD *)this + 6) = 3;
    }
  }
  if ( !Properties::SecretStore::IsEmpty((Properties::SecretStore *)v44) )
  {
    v22 = std::make_unique<Protector::Preboot,_GUID &,Properties::PrebootProtector,0>(
            &v30,
            (NgcIsoContainer *)((char *)this + 136),
            (__int64)v44);
    std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(
      (__int64 *)this + 67,
      v22);
    std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(&v30);
    v23 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 67) + 72LL))(*((_QWORD *)this + 67));
    if ( v23 >= 0 )
    {
      v8 = 1;
      BYTE2(v27) = 1;
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x214,
        (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_protectoroperations.cpp",
        (const char *)(unsigned int)v23,
        v25);
      if ( !*((_DWORD *)this + 6) )
        *((_DWORD *)this + 6) = 3;
    }
  }
  if ( (Microsoft_Windows_HelloForBusinessEnableBits & 1) != 0 )
    McTemplateU0dttttt_EventWriteTransfer(
      (unsigned __int8)v27,
      (unsigned int)EVENT_HFB_PROTECTORPROPERTIESREAD,
      ProtectorProperties,
      v5,
      v6,
      v7,
      v27,
      v8);
  LogProvider::NgcIsoReadProtectorProperties<long &,bool &,bool &,bool &,bool &,bool &>(
    v32,
    v28,
    (char *)&v27 + 3,
    (char *)&v27 + 1,
    (char *)&v27,
    (char *)&v27 + 2);
  if ( ProtectorProperties < 0 )
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x222,
      (unsigned int)"onecore\\ds\\security\\ngc\\ctnrsvc\\iso\\container\\dll\\isocontainer_protectoroperations.cpp",
      (const char *)(unsigned int)ProtectorProperties,
      v26);
  Properties::Protectors::~Protectors((Properties::Protectors *)v37);
  wil::ActivityThreadWatcher::~ActivityThreadWatcher((wil::ActivityThreadWatcher *)v35);
  return (unsigned int)ProtectorProperties;
}

```

## disassembly

```asm
0x180030bdc  push    rbp
0x180030bde  push    rbx
0x180030bdf  push    rsi
0x180030be0  push    rdi
0x180030be1  push    r12
0x180030be3  push    r13
0x180030be5  push    r14
0x180030be7  push    r15
0x180030be9  lea     rbp, [rsp-928h]
0x180030bf1  sub     rsp, 0A28h
0x180030bf8  mov     rax, cs:__security_cookie
0x180030bff  xor     rax, rsp
0x180030c02  mov     [rbp+960h+var_50], rax
0x180030c09  mov     rdi, rcx
0x180030c0c  lea     rdx, aNgcisoreadprot; "NgcIsoReadProtectorProperties"
0x180030c13  lea     rcx, [rbp+960h+var_9D0]
0x180030c17  call    ?WatchCurrentThread@LogProvider@@SA?AVActivityThreadWatcher@wil@@PEBD@Z; LogProvider::WatchCurrentThread(char const *)
0x180030c1c  nop
0x180030c1d  lea     rcx, [rbp+960h+var_810]; this
0x180030c24  call    ??0Protectors@Properties@@QEAA@XZ; Properties::Protectors::Protectors(void)
0x180030c29  nop
0x180030c2a  lea     rcx, [rdi+20h]
0x180030c2e  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030c33  lea     rdx, [rbp+960h+var_810]; unsigned __int16 *
0x180030c3a  mov     rcx, rax; this
0x180030c3d  call    ?ReadProtectorProperties@FileSystem@@YAJPEBGPEAUProtectors@Properties@@@Z; FileSystem::ReadProtectorProperties(ushort const *,Properties::Protectors *)
0x180030c42  mov     r14d, eax
0x180030c45  mov     [rsp+0A60h+var_A00], eax
0x180030c49  xor     r13b, r13b
0x180030c4c  mov     [rsp+0A60h+var_A1C], r13b
0x180030c51  xor     r15b, r15b
0x180030c54  mov     byte ptr [rsp+0A60h+var_A20+3], r15b
0x180030c59  xor     sil, sil
0x180030c5c  mov     byte ptr [rsp+0A60h+var_A20+1], sil
0x180030c61  mov     byte ptr [rsp+0A60h+var_A20], sil
0x180030c66  xor     r12b, r12b
0x180030c69  mov     byte ptr [rsp+0A60h+var_A20+2], r12b
0x180030c6e  lea     rcx, [rbp+960h+var_7B8]; this
0x180030c75  call    ?IsEmpty@SecretStore@Properties@@QEBA_NXZ; Properties::SecretStore::IsEmpty(void)
0x180030c7a  mov     ebx, 1
0x180030c7f  test    al, al
0x180030c81  jnz     loc_180030D10
0x180030c87  lea     r9, [rdi+0B8h]
0x180030c8e  lea     rdx, [rdi+88h]
0x180030c95  lea     r8, [rbp+960h+var_810]
0x180030c9c  lea     rcx, [rsp+0A60h+var_A08]
0x180030ca1  call    ??$make_unique@VPin@Protector@@AEAU_GUID@@UPinProtector@Properties@@AEAV?$vector@EV?$allocator@E@std@@@std@@$0A@@std@@YA?AV?$unique_ptr@VPin@Protector@@U?$default_delete@VPin@Protector@@@std@@@0@AEAU_GUID@@$$QEAUPinProtector@Properties@@AEAV?$vector@EV?$allocator@E@std@@@0@@Z; std::make_unique<Protector::Pin,_GUID &,Properties::PinProtector,std::vector<uchar> &,0>(_GUID &,Properties::PinProtector &&,std::vector<uchar> &)
0x180030ca6  lea     rbx, [rdi+200h]
0x180030cad  mov     rdx, rax
0x180030cb0  mov     rcx, rbx
0x180030cb3  call    ??$?4U?$default_delete@UKeyMaterial@Properties@@@std@@$0A@@?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(std::unique_ptr<Properties::KeyMaterial> &&)
0x180030cb8  lea     rcx, [rsp+0A60h+var_A08]
0x180030cbd  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x180030cc2  mov     rcx, [rbx]
0x180030cc5  mov     rax, [rcx]
0x180030cc8  mov     rax, [rax+48h]
0x180030ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030cd1  mov     rcx, [rbp+968h]; this
0x180030cd8  test    eax, eax
0x180030cda  jns     short loc_180030D04
0x180030cdc  mov     r9d, eax; char *
0x180030cdf  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180030ce6  mov     edx, 1B5h; void *
0x180030ceb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030cf0  mov     ebx, 1
0x180030cf5  cmp     dword ptr [rdi+18h], 0
0x180030cf9  jnz     short loc_180030D10
0x180030cfb  mov     dword ptr [rdi+18h], 3
0x180030d02  jmp     short loc_180030D10
0x180030d04  mov     ebx, 1
0x180030d09  mov     r13b, bl
0x180030d0c  mov     [rsp+0A60h+var_A1C], bl
0x180030d10  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_EssFprPeripherals@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals> `wil::Feature<__WilFeatureTraits_Feature_EssFprPeripherals>::GetImpl(void)'::`2'::impl
0x180030d17  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_EssFprPeripherals@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_EssFprPeripherals>::__private_IsEnabled(void)
0x180030d1c  test    al, al
0x180030d1e  jz      loc_180030E31
0x180030d24  call    ?IsNormalBioProtectorEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsNormalBioProtectorEnabled(void)
0x180030d29  test    al, al
0x180030d2b  jnz     short loc_180030D4D
0x180030d2d  lea     rcx, [rbp+960h+var_980]; this
0x180030d31  call    ??0SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::SecretStore(void)
0x180030d36  nop
0x180030d37  lea     rdx, [rbp+960h+var_980]
0x180030d3b  lea     rcx, [rbp+960h+var_630]
0x180030d42  call    ??4SecretStore@Properties@@QEAAAEAU01@$$QEAU01@@Z; Properties::SecretStore::operator=(Properties::SecretStore &&)
0x180030d47  nop
0x180030d48  jmp     loc_180030E55
0x180030d4d  lea     rcx, [rbp+960h+var_630]; this
0x180030d54  call    ?IsEmpty@SecretStore@Properties@@QEBA_NXZ; Properties::SecretStore::IsEmpty(void)
0x180030d59  test    al, al
0x180030d5b  jnz     short loc_180030D71
0x180030d5d  mov     rax, [rbp+960h+var_640]
0x180030d64  cmp     [rbp+960h+var_648], rax
0x180030d6b  jnz     loc_180030E7D
0x180030d71  mov     [rsp+0A60h+var_A08], 0
0x180030d7a  lea     rax, [rsp+0A60h+var_A08]
0x180030d7f  mov     [rsp+0A60h+Sid], rax
0x180030d84  mov     [rsp+0A60h+Sid+8], 0
0x180030d8d  mov     [rbp+960h+var_9E0], bl
0x180030d90  lea     rcx, [rdi+98h]
0x180030d97  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180030d9c  lea     rdx, [rsp+0A60h+Sid+8]; Sid
0x180030da1  mov     rcx, rax; StringSid
0x180030da4  call    cs:__imp_ConvertStringSidToSidW
0x180030daa  mov     ebx, eax
0x180030dac  lea     rcx, [rsp+0A60h+Sid]
0x180030db1  call    ??1?$out_param_ptr_t@PEAPEAXV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>::~out_param_ptr_t<void * *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>>>(void)
0x180030db6  test    ebx, ebx
0x180030db8  jz      short loc_180030E25
0x180030dba  mov     rax, [rsp+0A60h+var_A08]
0x180030dbf  mov     [rsp+0A60h+var_A10], rax
0x180030dc4  mov     [rsp+0A60h+var_A18], 0
0x180030dcc  lea     rax, [rsp+0A60h+var_A10]
0x180030dd1  mov     [rsp+0A60h+Sid], rax
0x180030dd6  lea     rax, [rsp+0A60h+var_A18]
0x180030ddb  mov     [rsp+0A60h+Sid+8], rax
0x180030de0  lea     rcx, [rsp+0A60h+Sid]
0x180030de5  call    _lambda_dcc46b57e3b17782259cf4b8e691dc4d___operator__
0x180030dea  mov     eax, [rsp+0A60h+var_A18]
0x180030dee  mov     [rsp+0A60h+var_A18], eax
0x180030df2  test    al, 1Ah
0x180030df4  jz      short loc_180030E25
0x180030df6  lea     rcx, [rsp+0A60h+var_A18]
0x180030dfb  call    ??$NgcIsoContainerNormalBioProtectorHealingTriggered@AEAI@LogProvider@@SAXAEAI@Z; LogProvider::NgcIsoContainerNormalBioProtectorHealingTriggered<uint &>(uint &)
0x180030e00  call    ?SetBioProtectorUpdateNeeded@NgcUtils@@YAJXZ; NgcUtils::SetBioProtectorUpdateNeeded(void)
0x180030e05  mov     rcx, [rbp+968h]; this
0x180030e0c  test    eax, eax
0x180030e0e  jns     short loc_180030E25
0x180030e10  mov     r9d, eax; char *
0x180030e13  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180030e1a  mov     edx, 1D5h; void *
0x180030e1f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030e24  nop
0x180030e25  lea     rcx, [rsp+0A60h+var_A08]
0x180030e2a  call    ??1?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?FreeSid@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&FreeSid(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x180030e2f  jmp     short loc_180030E7D
0x180030e31  call    ?IsNormalBioProtectorEnabled@NgcUtils@@YA_NXZ; NgcUtils::IsNormalBioProtectorEnabled(void)
0x180030e36  test    al, al
0x180030e38  jnz     short loc_180030E7D
0x180030e3a  lea     rcx, [rbp+960h+var_980]; this
0x180030e3e  call    ??0SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::SecretStore(void)
0x180030e43  nop
0x180030e44  lea     rdx, [rbp+960h+var_980]
0x180030e48  lea     rcx, [rbp+960h+var_630]
0x180030e4f  call    ??4SecretStore@Properties@@QEAAAEAU01@$$QEAU01@@Z; Properties::SecretStore::operator=(Properties::SecretStore &&)
0x180030e54  nop
0x180030e55  lea     rcx, [rbp+960h+var_980]; this
0x180030e59  call    ??1SecretStore@Properties@@QEAA@XZ; Properties::SecretStore::~SecretStore(void)
0x180030e5e  xorps   xmm0, xmm0
0x180030e61  movdqa  xmmword ptr [rsp+0A60h+Sid], xmm0
0x180030e67  lea     rdx, [rsp+0A60h+Sid]
0x180030e6c  lea     rcx, [rbp+960h+var_648]
0x180030e73  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@V?$initializer_list@E@1@@Z; std::vector<uchar>::operator=(std::initializer_list<uchar>)
0x180030e78  call    ?NgcIsoContainerDidNotReadNormalBioProtector@LogProvider@@SAXXZ; LogProvider::NgcIsoContainerDidNotReadNormalBioProtector(void)
0x180030e7d  lea     rcx, [rbp+960h+var_630]; this
0x180030e84  call    ?IsEmpty@SecretStore@Properties@@QEBA_NXZ; Properties::SecretStore::IsEmpty(void)
0x180030e89  test    al, al
0x180030e8b  jz      short loc_180030EA1
0x180030e8d  lea     rcx, [rbp+960h+var_4C0]; this
0x180030e94  call    ?IsEmpty@SecretStore@Properties@@QEBA_NXZ; Properties::SecretStore::IsEmpty(void)
0x180030e99  test    al, al
0x180030e9b  jnz     loc_180030F80
0x180030ea1  lea     r8, [rdi+98h]
0x180030ea8  lea     rdx, [rdi+88h]
0x180030eaf  lea     r9, [rbp+960h+var_648]
0x180030eb6  lea     rcx, [rsp+0A60h+var_A10]
0x180030ebb  call    ??$make_unique@VBio@Protector@@AEAU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@UBioProtector@Properties@@$0A@@std@@YA?AV?$unique_ptr@VBio@Protector@@U?$default_delete@VBio@Protector@@@std@@@0@AEAU_GUID@@AEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@0@$$QEAUBioProtector@Properties@@@Z; std::make_unique<Protector::Bio,_GUID &,std::wstring &,Properties::BioProtector,0>(_GUID &,std::wstring &,Properties::BioProtector &&)
0x180030ec0  lea     rbx, [rdi+208h]
0x180030ec7  mov     rdx, rax
0x180030eca  mov     rcx, rbx
0x180030ecd  call    ??$?4U?$default_delete@UKeyMaterial@Properties@@@std@@$0A@@?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(std::unique_ptr<Properties::KeyMaterial> &&)
0x180030ed2  lea     rcx, [rsp+0A60h+var_A10]
0x180030ed7  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x180030edc  mov     rcx, [rbx]
0x180030edf  mov     rax, [rcx]
0x180030ee2  mov     rax, [rax+48h]
0x180030ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030eeb  mov     rcx, [rbp+968h]; this
0x180030ef2  test    eax, eax
0x180030ef4  jns     short loc_180030F1E
0x180030ef6  mov     r9d, eax; char *
0x180030ef9  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180030f00  mov     edx, 1EBh; void *
0x180030f05  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030f0a  mov     ebx, 1
0x180030f0f  cmp     dword ptr [rdi+18h], 0
0x180030f13  jnz     short loc_180030F54
0x180030f15  mov     dword ptr [rdi+18h], 3
0x180030f1c  jmp     short loc_180030F54
0x180030f1e  lea     rcx, [rbp+960h+var_630]; this
0x180030f25  call    ?IsEmpty@SecretStore@Properties@@QEBA_NXZ; Properties::SecretStore::IsEmpty(void)
0x180030f2a  mov     r15b, al
0x180030f2d  mov     ebx, 1
0x180030f32  xor     r15b, bl
0x180030f35  mov     byte ptr [rsp+0A60h+var_A20+3], r15b
0x180030f3a  lea     rcx, [rbp+960h+var_4C0]; this
0x180030f41  call    ?IsEmpty@SecretStore@Properties@@QEBA_NXZ; Properties::SecretStore::IsEmpty(void)
0x180030f46  movzx   esi, sil
0x180030f4a  test    al, al
0x180030f4c  cmovz   esi, ebx
0x180030f4f  mov     byte ptr [rsp+0A60h+var_A20+1], sil
0x180030f54  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_SecureBioSekFix@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_SecureBioSekFix@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureBioSekFix> `wil::Feature<__WilFeatureTraits_Feature_SecureBioSekFix>::GetImpl(void)'::`2'::impl
0x180030f5b  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_SecureBioSekFix@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_SecureBioSekFix>::__private_IsEnabled(void)
0x180030f60  test    al, al
0x180030f62  jz      short loc_180030F80
0x180030f64  lea     rcx, [rbp+960h+var_4C0]; this
0x180030f6b  call    ?IsEmpty@SecretStore@Properties@@QEBA_NXZ; Properties::SecretStore::IsEmpty(void)
0x180030f70  movzx   ecx, sil
0x180030f74  test    al, al
0x180030f76  cmovz   ecx, ebx
0x180030f79  mov     sil, cl
0x180030f7c  mov     byte ptr [rsp+0A60h+var_A20+1], cl
0x180030f80  lea     rcx, [rbp+960h+var_330]; this
0x180030f87  call    ?IsEmpty@SecretStore@Properties@@QEBA_NXZ; Properties::SecretStore::IsEmpty(void)
0x180030f8c  test    al, al
0x180030f8e  jnz     short loc_180031006
0x180030f90  lea     rdx, [rdi+88h]
0x180030f97  lea     r8, [rbp+960h+var_350]
0x180030f9e  lea     rcx, [rsp+0A60h+var_A10]
0x180030fa3  call    ??$make_unique@VRecovery@Protector@@AEAU_GUID@@URecoveryProtector@Properties@@$0A@@std@@YA?AV?$unique_ptr@VRecovery@Protector@@U?$default_delete@VRecovery@Protector@@@std@@@0@AEAU_GUID@@$$QEAURecoveryProtector@Properties@@@Z; std::make_unique<Protector::Recovery,_GUID &,Properties::RecoveryProtector,0>(_GUID &,Properties::RecoveryProtector &&)
0x180030fa8  lea     rbx, [rdi+210h]
0x180030faf  mov     rdx, rax
0x180030fb2  mov     rcx, rbx
0x180030fb5  call    ??$?4U?$default_delete@UKeyMaterial@Properties@@@std@@$0A@@?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(std::unique_ptr<Properties::KeyMaterial> &&)
0x180030fba  lea     rcx, [rsp+0A60h+var_A10]
0x180030fbf  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x180030fc4  mov     rcx, [rbx]
0x180030fc7  mov     rax, [rcx]
0x180030fca  mov     rax, [rax+48h]
0x180030fce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180030fd3  mov     rcx, [rbp+968h]; this
0x180030fda  test    eax, eax
0x180030fdc  jns     short loc_180031001
0x180030fde  mov     r9d, eax; char *
0x180030fe1  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x180030fe8  mov     edx, 204h; void *
0x180030fed  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180030ff2  cmp     dword ptr [rdi+18h], 0
0x180030ff6  jnz     short loc_180031006
0x180030ff8  mov     dword ptr [rdi+18h], 3
0x180030fff  jmp     short loc_180031006
0x180031001  mov     byte ptr [rsp+0A60h+var_A20], 1
0x180031006  lea     rcx, [rbp+960h+var_1C0]; this
0x18003100d  call    ?IsEmpty@SecretStore@Properties@@QEBA_NXZ; Properties::SecretStore::IsEmpty(void)
0x180031012  test    al, al
0x180031014  jnz     short loc_18003108F
0x180031016  lea     rdx, [rdi+88h]
0x18003101d  lea     r8, [rbp+960h+var_1C0]
0x180031024  lea     rcx, [rsp+0A60h+var_A10]
0x180031029  call    ??$make_unique@VPreboot@Protector@@AEAU_GUID@@UPrebootProtector@Properties@@$0A@@std@@YA?AV?$unique_ptr@VPreboot@Protector@@U?$default_delete@VPreboot@Protector@@@std@@@0@AEAU_GUID@@$$QEAUPrebootProtector@Properties@@@Z; std::make_unique<Protector::Preboot,_GUID &,Properties::PrebootProtector,0>(_GUID &,Properties::PrebootProtector &&)
0x18003102e  lea     rbx, [rdi+218h]
0x180031035  mov     rdx, rax
0x180031038  mov     rcx, rbx
0x18003103b  call    ??$?4U?$default_delete@UKeyMaterial@Properties@@@std@@$0A@@?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::unique_ptr<Properties::KeyMaterial>::operator=<std::default_delete<Properties::KeyMaterial>,0>(std::unique_ptr<Properties::KeyMaterial> &&)
0x180031040  lea     rcx, [rsp+0A60h+var_A10]
0x180031045  call    ??1?$unique_ptr@UKeyMaterial@Properties@@U?$default_delete@UKeyMaterial@Properties@@@std@@@std@@QEAA@XZ; std::unique_ptr<Properties::KeyMaterial>::~unique_ptr<Properties::KeyMaterial>(void)
0x18003104a  mov     rcx, [rbx]
0x18003104d  mov     rax, [rcx]
0x180031050  mov     rax, [rax+48h]
0x180031054  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031059  mov     rcx, [rbp+968h]; this
0x180031060  test    eax, eax
0x180031062  jns     short loc_180031087
0x180031064  mov     r9d, eax; char *
0x180031067  lea     r8, aOnecoreDsSecur_26; "onecore\\ds\\security\\ngc\\ctnrsvc\\is"...
0x18003106e  mov     edx, 214h; void *
0x180031073  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180031078  cmp     dword ptr [rdi+18h], 0
0x18003107c  jnz     short loc_18003108F
0x18003107e  mov     dword ptr [rdi+18h], 3
0x180031085  jmp     short loc_18003108F
0x180031087  mov     r12b, 1
0x18003108a  mov     byte ptr [rsp+0A60h+var_A20+2], r12b
0x18003108f  test    cs:Microsoft_Windows_HelloForBusinessEnableBits, 1
0x180031096  jz      short loc_1800310CD
0x180031098  movzx   eax, r12b
0x18003109c  movzx   ecx, byte ptr [rsp+0A60h+var_A20]
0x1800310a1  movzx   edx, sil
0x1800310a5  movzx   r8d, r15b
0x1800310a9  movzx   r9d, r13b
0x1800310ad  mov     [rsp+0A60h+var_A28], eax
0x1800310b1  mov     [rsp+0A60h+var_A30], ecx
0x1800310b5  mov     dword ptr [rsp+0A60h+var_A38], edx
0x1800310b9  mov     [rsp+0A60h+var_A40], r8d
0x1800310be  mov     r8d, r14d
0x1800310c1  lea     rdx, EVENT_HFB_PROTECTORPROPERTIESREAD
0x1800310c8  call    McTemplateU0dttttt_EventWriteTransfer
0x1800310cd  lea     rax, [rsp+0A60h+var_A20+2]
0x1800310d2  mov     [rsp+0A60h+var_A38], rax
0x1800310d7  lea     rax, [rsp+0A60h+var_A20]
0x1800310dc  mov     qword ptr [rsp+0A60h+var_A40], rax; int
0x1800310e1  lea     r9, [rsp+0A60h+var_A20+1]
0x1800310e6  lea     r8, [rsp+0A60h+var_A20+3]
0x1800310eb  lea     rdx, [rsp+0A60h+var_A1C]
0x1800310f0  lea     rcx, [rsp+0A60h+var_A00]
0x1800310f5  call    ??$NgcIsoReadProtectorProperties@AEAJAEA_NAEA_NAEA_NAEA_NAEA_N@LogProvider@@SAXAEAJAEA_N1111@Z; LogProvider::NgcIsoReadProtectorProperties<long &,bool &,bool &,bool &,bool &,bool &>(long &,bool &,bool &,bool &,bool &,bool &)
0x1800310fa  test    r14d, r14d
0x1800310fd  jns     short loc_18003111B
0x1800310ff  mov     rcx, [rbp+968h]; this
0x180031106  mov     r9d, r14d; char *
  ... truncated ...
```
