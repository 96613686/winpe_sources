# SystemSettings::Prov::CProvisioningPackageInstalledSetting::DoGetValueAsyncWork(void)

- ea: `0x180014640`
- end: `0x18001485b`
- name: `?DoGetValueAsyncWork@CProvisioningPackageInstalledSetting@Prov@SystemSettings@@UEAAXXZ`
- size: `539`
- prototype: `void __fastcall(SystemSettings::Prov::CProvisioningPackageInstalledSetting *__hidden this)`
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800067fc`
- `0x18000b638`
- `0x180012740`
- `0x18001314c`
- `0x180014640`
- `0x1800198cc`
- `0x18001a7a4`
- `0x18001ecc0`
- `0x18001f74c`
- `0x1800232d8`
- `0x1800235dc`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18001470c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014752`
- `msvcrt!??3@YAXPEAX@Z` at `0x18001470c`
- `msvcrt!??3@YAXPEAX@Z` at `0x180014752`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180014651`
- `api-ms-win-core-winrt-l1-1-0!RoInitialize` at `0x180014651`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180014719`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180014845`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180014719`
- `api-ms-win-core-winrt-l1-1-0!RoUninitialize` at `0x180014845`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
void __fastcall SystemSettings::Prov::CProvisioningPackageInstalledSetting::DoGetValueAsyncWork(
        SystemSettings::Prov::CProvisioningPackageInstalledSetting *this)
{
  int v2; // eax
  int v3; // ebx
  CProvisioningSingleton *v4; // rcx
  int v5; // eax
  int InstalledPackageList; // eax
  wil::details::in1diag3 *v7; // rcx
  __int64 v8; // rcx
  void *v9; // rbx
  const struct ProvPackageInfo **i; // rdi
  int v11; // eax
  int v12; // eax
  wil::details::in1diag3 *v13; // rcx
  __int64 v14; // rdx
  int v15[2]; // [rsp+20h] [rbp-38h] BYREF
  __int128 v16; // [rsp+28h] [rbp-30h] BYREF
  __int64 v17; // [rsp+38h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int16 v19; // [rsp+70h] [rbp+18h] BYREF
  char v20; // [rsp+72h] [rbp+1Ah]
  __int64 v21; // [rsp+78h] [rbp+20h] BYREF

  v2 = RoInitialize(1);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x573,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      (const char *)(unsigned int)v2,
      v15[0]);
    goto LABEL_13;
  }
  Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(*((_QWORD *)this + 26));
  v5 = CProvisioningSingleton::InitializeInstalledPackageList(v4);
  if ( v5 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x576,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      (const char *)(unsigned int)v5,
      v15[0]);
    goto LABEL_24;
  }
  v16 = 0;
  v17 = 0;
  InstalledPackageList = CProvisioningSingleton::GetInstalledPackageList(retaddr, &v16);
  v7 = retaddr;
  if ( InstalledPackageList < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x57F,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      (const char *)(unsigned int)InstalledPackageList,
      v15[0]);
    v9 = (void *)v16;
    if ( (_QWORD)v16 )
    {
      std::vector<std::unique_ptr<ProvPackageInfo>>::_Destroy(v8, v16, *((_QWORD *)&v16 + 1));
      operator delete(v9);
    }
    RoUninitialize();
    return;
  }
  for ( i = (const struct ProvPackageInfo **)v16; i != *((const struct ProvPackageInfo ***)&v16 + 1); ++i )
  {
    v21 = 0;
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v21);
    v19 = 257;
    v20 = 0;
    v11 = SystemSettings::Prov::CProvisioningPackageItemSetting::CreateInstance(*i, (char *)&v19, &v21);
    if ( v11 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x588,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v11,
        v15[0]);
      goto LABEL_23;
    }
    *(_QWORD *)v15 = 0;
    v12 = Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningPackageItemSetting>::As<SystemSettings::DataModel::ISettingItem>(
            &v21,
            v15);
    v13 = retaddr;
    if ( v12 < 0 )
    {
      v14 = 1420;
LABEL_21:
      wil::details::in1diag3::_Log_Hr(
        v13,
        (void *)v14,
        (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
        (const char *)(unsigned int)v12,
        v15[0]);
      goto LABEL_22;
    }
    v12 = Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(
            *((_QWORD *)this + 26),
            0,
            *(__int64 *)v15,
            1);
    v13 = retaddr;
    if ( v12 < 0 )
    {
      v14 = 1423;
      goto LABEL_21;
    }
LABEL_22:
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease((__int64 *)v15);
LABEL_23:
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v21);
  }
  if ( (_QWORD)v16 )
  {
    std::vector<std::unique_ptr<ProvPackageInfo>>::_Destroy(v7, v16, *((_QWORD *)&v16 + 1));
    operator delete((void *)v16);
  }
LABEL_13:
  SystemSettings::DataModel::CSettingBase::OnValueChanged(this, (const unsigned __int16 *)&stru_180035948);
  if ( v3 >= 0 )
LABEL_24:
    RoUninitialize();
}

```

## disassembly

```asm
0x180014640  push    rbx
0x180014642  push    rdi
0x180014643  push    r14
0x180014645  sub     rsp, 40h
0x180014649  mov     r14, rcx
0x18001464c  mov     ecx, 1
0x180014651  call    cs:__imp_RoInitialize
0x180014658  nop     dword ptr [rax+rax+00h]
0x18001465d  mov     ebx, eax
0x18001465f  mov     [rsp+58h+arg_8], eax
0x180014663  mov     rcx, [rsp+58h]; this
0x180014668  test    eax, eax
0x18001466a  jns     short loc_180014685
0x18001466c  mov     r9d, eax; char *
0x18001466f  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180014676  mov     edx, 573h; void *
0x18001467b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014680  jmp     loc_18001475F
0x180014685  mov     rcx, [r14+0D0h]
0x18001468c  call    ?Clear@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@UEAAJXZ; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::Clear(void)
0x180014691  call    ?InitializeInstalledPackageList@CProvisioningSingleton@@QEAAJXZ; CProvisioningSingleton::InitializeInstalledPackageList(void)
0x180014696  mov     rcx, [rsp+58h]; this
0x18001469b  test    eax, eax
0x18001469d  jns     short loc_1800146B8
0x18001469f  mov     r9d, eax; char *
0x1800146a2  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800146a9  mov     edx, 576h; void *
0x1800146ae  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800146b3  jmp     loc_180014845
0x1800146b8  xorps   xmm0, xmm0
0x1800146bb  movdqu  [rsp+58h+var_30], xmm0
0x1800146c1  mov     [rsp+58h+var_20], 0
0x1800146ca  lea     rdx, [rsp+58h+var_30]
0x1800146cf  call    ?GetInstalledPackageList@CProvisioningSingleton@@QEAAJAEAV?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@@Z; CProvisioningSingleton::GetInstalledPackageList(std::vector<std::unique_ptr<ProvPackageInfo>> &)
0x1800146d4  mov     rcx, [rsp+58h]; this
0x1800146d9  test    eax, eax
0x1800146db  jns     short loc_18001472A
0x1800146dd  mov     r9d, eax; char *
0x1800146e0  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800146e7  mov     edx, 57Fh; void *
0x1800146ec  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800146f1  nop
0x1800146f2  mov     rbx, qword ptr [rsp+58h+var_30]
0x1800146f7  test    rbx, rbx
0x1800146fa  jz      short loc_180014719
0x1800146fc  mov     r8, qword ptr [rsp+58h+var_30+8]
0x180014701  mov     rdx, rbx
0x180014704  call    ?_Destroy@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@2@0@Z; std::vector<std::unique_ptr<ProvPackageInfo>>::_Destroy(std::unique_ptr<ProvPackageInfo> *,std::unique_ptr<ProvPackageInfo> *)
0x180014709  mov     rcx, rbx
0x18001470c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014713  nop     dword ptr [rax+rax+00h]
0x180014718  nop
0x180014719  call    cs:__imp_RoUninitialize
0x180014720  nop     dword ptr [rax+rax+00h]
0x180014725  jmp     loc_180014851
0x18001472a  mov     rdi, qword ptr [rsp+58h+var_30]
0x18001472f  cmp     rdi, qword ptr [rsp+58h+var_30+8]
0x180014734  jnz     short loc_18001477C
0x180014736  cmp     qword ptr [rsp+58h+var_30], 0
0x18001473c  jz      short loc_18001475F
0x18001473e  mov     r8, qword ptr [rsp+58h+var_30+8]
0x180014743  mov     rdx, qword ptr [rsp+58h+var_30]
0x180014748  call    ?_Destroy@?$vector@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@2@0@Z; std::vector<std::unique_ptr<ProvPackageInfo>>::_Destroy(std::unique_ptr<ProvPackageInfo> *,std::unique_ptr<ProvPackageInfo> *)
0x18001474d  mov     rcx, qword ptr [rsp+58h+var_30]
0x180014752  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180014759  nop     dword ptr [rax+rax+00h]
0x18001475e  nop
0x18001475f  lea     rdx, stru_180035948; unsigned __int16 *
0x180014766  mov     rcx, r14; this
0x180014769  call    ?OnValueChanged@CSettingBase@DataModel@SystemSettings@@QEAAXPEBG@Z; SystemSettings::DataModel::CSettingBase::OnValueChanged(ushort const *)
0x18001476e  nop
0x18001476f  test    ebx, ebx
0x180014771  js      loc_180014851
0x180014777  jmp     loc_180014845
0x18001477c  mov     [rsp+58h+arg_18], 0
0x180014785  lea     rcx, [rsp+58h+arg_18]
0x18001478a  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18001478f  mov     [rsp+58h+arg_10], 101h
0x180014796  mov     [rsp+58h+arg_12], 0
0x18001479b  lea     r8, [rsp+58h+arg_18]
0x1800147a0  lea     rdx, [rsp+58h+arg_10]
0x1800147a5  mov     rcx, [rdi]
0x1800147a8  call    ?CreateInstance@CProvisioningPackageItemSetting@Prov@SystemSettings@@SAJPEAVProvPackageInfo@@UActionButtonType@23@PEAPEAV123@@Z; SystemSettings::Prov::CProvisioningPackageItemSetting::CreateInstance(ProvPackageInfo *,SystemSettings::Prov::ActionButtonType,SystemSettings::Prov::CProvisioningPackageItemSetting * *)
0x1800147ad  mov     rcx, [rsp+58h]; this
0x1800147b2  test    eax, eax
0x1800147b4  jns     short loc_1800147CC
0x1800147b6  mov     r9d, eax; char *
0x1800147b9  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800147c0  mov     edx, 588h; void *
0x1800147c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800147ca  jmp     short loc_180014832
0x1800147cc  mov     qword ptr [rsp+58h+var_38], 0; int
0x1800147d5  lea     rdx, [rsp+58h+var_38]
0x1800147da  lea     rcx, [rsp+58h+arg_18]
0x1800147df  call    ??$As@UISettingItem@DataModel@SystemSettings@@@?$ComPtr@VCProvisioningPackageItemSetting@Prov@SystemSettings@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISettingItem@DataModel@SystemSettings@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningPackageItemSetting>::As<SystemSettings::DataModel::ISettingItem>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SystemSettings::DataModel::ISettingItem>>)
0x1800147e4  mov     rcx, [rsp+58h]
0x1800147e9  test    eax, eax
0x1800147eb  jns     short loc_1800147F4
0x1800147ed  mov     edx, 58Ch
0x1800147f2  jmp     short loc_180014818
0x1800147f4  mov     r9b, 1
0x1800147f7  mov     r8, qword ptr [rsp+58h+var_38]
0x1800147fc  xor     edx, edx
0x1800147fe  mov     rcx, [r14+0D0h]
0x180014805  call    ?InsertAtInternal@?$Vector@PEAUISettingItem@DataModel@SystemSettings@@U?$DefaultEqualityPredicate@PEAUISettingItem@DataModel@SystemSettings@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@PEAUISettingItem@DataModel@SystemSettings@@@5678@U?$VectorOptions@PEAUISettingItem@DataModel@SystemSettings@@$00$00$0A@@5678@@Internal@Collections@Foundation@Windows@@AEAAJIPEAUISettingItem@DataModel@SystemSettings@@_N@Z; Windows::Foundation::Collections::Internal::Vector<SystemSettings::DataModel::ISettingItem *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<SystemSettings::DataModel::ISettingItem *>,Windows::Foundation::Collections::Internal::VectorOptions<SystemSettings::DataModel::ISettingItem *,1,1,0>>::InsertAtInternal(uint,SystemSettings::DataModel::ISettingItem *,bool)
0x18001480a  mov     rcx, [rsp+58h]; this
0x18001480f  test    eax, eax
0x180014811  jns     short loc_180014827
0x180014813  mov     edx, 58Fh; void *
0x180014818  mov     r9d, eax; char *
0x18001481b  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180014822  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180014827  lea     rcx, [rsp+58h+var_38]
0x18001482c  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180014831  nop
0x180014832  lea     rcx, [rsp+58h+arg_18]
0x180014837  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x18001483c  add     rdi, 8
0x180014840  jmp     loc_18001472F
0x180014845  call    cs:__imp_RoUninitialize
0x18001484c  nop     dword ptr [rax+rax+00h]
0x180014851  add     rsp, 40h
0x180014855  pop     r14
0x180014857  pop     rdi
0x180014858  pop     rbx
0x180014859  retn
```
