# LegacyDescriptionsPlugin::OnPreCommit

- ea: `0x1800274f0`
- end: `0x1800279f3`
- name: `LegacyDescriptionsPlugin::OnPreCommit`
- size: `1283`
- prototype: ``
- caller_count: `0`
- callee_count: `36`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x180005580`
- `0x180005660`
- `0x18000a430`
- `0x18000e4c8`
- `0x18000e970`
- `0x18000ec20`
- `0x18000ecc8`
- `0x18000fd70`
- `0x180010200`
- `0x1800109f0`
- `0x18001368c`
- `0x180013994`
- `0x180015f50`
- `0x180017320`
- `0x180025c18`
- `0x1800261ac`
- `0x1800274f0`
- `0x180027a78`
- `0x180027ac0`
- `0x180027b38`
- `0x180027fc0`
- `0x1800284f4`
- `0x1800285fc`
- `0x180028a18`
- `0x180028a90`
- `0x180028bf4`
- `0x1800400bc`
- `0x18004c9cc`
- `0x18005593c`
- `0x180055aa4`
- `0x180055d20`
- `0x180056500`
- `0x180057b50`
- `0x180058188`
- `0x180064704`
- `0x1800810d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002795b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002796b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002795b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18002796b`

## string_xrefs

- `0x180027533`: `LegacyDescriptionsPlugin`

## pseudocode

```c
// Hidden C++ exception states: #wind=19
__int64 __fastcall LegacyDescriptionsPlugin::OnPreCommit(__int64 a1, _QWORD *a2, __int64 *a3)
{
  __int64 v4; // rbx
  HKEY CurrentControlSetRegistryHandle; // rax
  __int64 v6; // r8
  __int64 v7; // rcx
  void ****v8; // rbx
  void ****v9; // rdi
  _QWORD *v10; // rsi
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  void *v14; // rdi
  __int64 v15; // rbx
  const wchar_t *v16; // rsi
  __int64 v17; // r8
  __int64 v18; // rdx
  const struct MultiSz *v19; // rax
  __int64 i; // rax
  __m256i v22; // [rsp+48h] [rbp-C0h] BYREF
  void **v23; // [rsp+68h] [rbp-A0h]
  __int128 v24; // [rsp+70h] [rbp-98h]
  HKEY hKey; // [rsp+88h] [rbp-80h] BYREF
  void **v26; // [rsp+90h] [rbp-78h] BYREF
  void *Block[3]; // [rsp+98h] [rbp-70h] BYREF
  unsigned __int64 v28; // [rsp+B0h] [rbp-58h]
  void *v29[3]; // [rsp+B8h] [rbp-50h] BYREF
  unsigned __int64 v30; // [rsp+D0h] [rbp-38h]
  __int64 v31; // [rsp+D8h] [rbp-30h]
  HKEY v32; // [rsp+E0h] [rbp-28h] BYREF
  void *v33[2]; // [rsp+E8h] [rbp-20h] BYREF
  void *v34[2]; // [rsp+F8h] [rbp-10h] BYREF
  __int64 v35; // [rsp+108h] [rbp+0h]
  void *v36[2]; // [rsp+110h] [rbp+8h] BYREF
  __int64 v37; // [rsp+120h] [rbp+18h]
  unsigned __int64 v38; // [rsp+128h] [rbp+20h]
  void *v39; // [rsp+130h] [rbp+28h] BYREF
  __int64 v40; // [rsp+138h] [rbp+30h] BYREF
  _BYTE v41[20]; // [rsp+140h] [rbp+38h]
  void *v42[4]; // [rsp+158h] [rbp+50h] BYREF
  void **v43; // [rsp+178h] [rbp+70h] BYREF
  _BYTE v44[272]; // [rsp+180h] [rbp+78h] BYREF
  _BYTE v45[8]; // [rsp+290h] [rbp+188h] BYREF
  _BYTE v46[48]; // [rsp+298h] [rbp+190h] BYREF
  int v47; // [rsp+2C8h] [rbp+1C0h] BYREF
  __int64 v48; // [rsp+2CCh] [rbp+1C4h]
  __int128 v49; // [rsp+2D4h] [rbp+1CCh]
  __int64 v50; // [rsp+2E4h] [rbp+1DCh]
  int v51; // [rsp+2ECh] [rbp+1E4h]
  __int64 v52; // [rsp+2F0h] [rbp+1E8h]
  __int64 v53; // [rsp+2F8h] [rbp+1F0h]
  int v54; // [rsp+300h] [rbp+1F8h]
  __int64 v55; // [rsp+304h] [rbp+1FCh]
  __int128 v56; // [rsp+30Ch] [rbp+204h]
  __int64 v57; // [rsp+31Ch] [rbp+214h]
  int v58; // [rsp+324h] [rbp+21Ch]
  __int64 v59; // [rsp+328h] [rbp+220h]
  __int64 v60; // [rsp+330h] [rbp+228h]

  v31 = -2;
  v4 = *a3;
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>(
    &v43,
    "LegacyDescriptionsPlugin");
  v43 = &NetSetupTraceLogging::LegacyDescriptionsPlugin::`vftable';
  NetSetupTraceLogging::LegacyDescriptionsPlugin::StartActivity(
    (NetSetupTraceLogging::LegacyDescriptionsPlugin *)&v43,
    (const struct _GUID *)(v4 + 632));
  v33[1] = 0;
  v33[0] = (void *)std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::vector<unsigned int>>>>::_Buyheadnode();
  v39 = a2;
  v40 = 0;
  *(_DWORD *)v41 = 9;
  *(_OWORD *)&v41[4] = 0;
  CurrentControlSetRegistryHandle = NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle((NetSetup2::TransactionObject *)&v39);
  RegistryKey::DuplicateFrom(&v32, CurrentControlSetRegistryHandle);
  std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(&v40);
  RegistryKey::DeleteSubKey(
    (RegistryKey *)&v32,
    L"Control\\Network\\{4d36e972-e325-11ce-bfc1-08002be10318}\\Descriptions");
  RegistryKey::CreateSubKey(
    &v32,
    (HKEY)&hKey,
    L"Control\\Network\\{4d36e972-e325-11ce-bfc1-08002be10318}\\Descriptions",
    2u,
    0,
    0);
  v22.m256i_i32[1] = 0;
  *(_OWORD *)&v22.m256i_u64[1] = *(_OWORD *)&NETSETUPPKEY_Interface_OriginalDeviceDescrAndUniquifier;
  v22.m256i_i32[6] = 260;
  v47 = 1;
  v48 = *(__int64 *)((char *)v22.m256i_i64 + 4);
  v49 = *(_OWORD *)((char *)&v22.m256i_u64[1] + 4);
  v50 = 0;
  v51 = 0;
  v52 = 0;
  v53 = 0;
  v22.m256i_i32[1] = 0;
  *(_OWORD *)&v22.m256i_u64[1] = NETSETUPPKEY_Interface_PnpInstance;
  v22.m256i_i32[6] = 50;
  v24 = 0;
  v54 = 1;
  v55 = *(__int64 *)((char *)v22.m256i_i64 + 4);
  v56 = *(_OWORD *)((char *)&v22.m256i_u64[1] + 4);
  v57 = 0;
  v58 = 0;
  v59 = 0;
  v60 = 0;
  NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(
    a2,
    v34,
    v6,
    0,
    0,
    (__int64)&v47,
    2);
  v8 = (void ****)v34[0];
  v9 = (void ****)v34[1];
  while ( v8 != v9 )
  {
    if ( !NetSetup2::NetworkInterface::get_PnpDeviceInterfaceNumber((NetSetup2::NetworkInterface *)*v8) )
    {
      NetSetup2::ActiveObject::GetProperty(*v8, (GUID *)&v22, &NETSETUPPKEY_Interface_PnpInstance, 0);
      NetSetup2::Property::GetString(&v22, v42);
      std::vector<_NETSETUPPROPKEY>::_Tidy(&v22.m256i_u64[3]);
      NetSetup2::NetworkInterface::get_OriginalDeviceDescrAndUniquifier(*v8, &v39);
      v10 = std::wstring::wstring(v29, L"Control\\Network\\{4d36e972-e325-11ce-bfc1-08002be10318}\\");
      v11 = StringFromGuid(Block, (char *)*v8 + 20);
      v12 = std::wstring::append(v10, v11, 0, -1);
      v13 = std::wstring::append(v12, L"\\Connection");
      v38 = 7;
      v37 = 0;
      LOWORD(v36[0]) = 0;
      std::wstring::assign(v36, v13, 0, -1);
      if ( v28 >= 8 )
        operator delete(Block[0]);
      v28 = 7;
      Block[2] = 0;
      LOWORD(Block[0]) = 0;
      if ( v30 >= 8 )
        operator delete(v29[0]);
      v30 = 7;
      v29[2] = 0;
      LOWORD(v29[0]) = 0;
      v22.m256i_i64[0] = (__int64)v42;
      v22.m256i_i64[1] = (__int64)a2;
      v22.m256i_i64[2] = (__int64)&v39;
      v22.m256i_i64[3] = (__int64)&v32;
      v23 = v36;
      *(_QWORD *)&v24 = v33;
      NetSetupExecuteInFrame__lambda_4b982fc3cc7a4c08b5268975496311d4_(&v22);
      if ( v38 >= 8 )
        operator delete(v36[0]);
      v38 = 7;
      v37 = 0;
      LOWORD(v36[0]) = 0;
      if ( *(_QWORD *)&v41[8] >= 8u )
        operator delete(v39);
      *(_QWORD *)&v41[8] = 7;
      *(_QWORD *)v41 = 0;
      LOWORD(v39) = 0;
      if ( v42[3] >= (void *)8 )
        operator delete(v42[0]);
    }
    ++v8;
  }
  if ( v34[0] )
  {
    std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy(v7, v34[0], v34[1]);
    operator delete(v34[0]);
  }
  v14 = v33[0];
  v15 = *(_QWORD *)v33[0];
  while ( (void *)v15 != v14 )
  {
    v16 = (const wchar_t *)(v15 + 32);
    std::_Sort<unsigned int *,__int64>(
      *(_QWORD *)(v15 + 64),
      *(_QWORD *)(v15 + 72),
      (__int64)(*(_QWORD *)(v15 + 72) - *(_QWORD *)(v15 + 64)) >> 2);
    *(_OWORD *)v34 = 0;
    v35 = 0;
    v17 = *(_QWORD *)(v15 + 72);
    v18 = *(_QWORD *)(v15 + 64);
    if ( v18 == v17 )
      v26 = v34;
    else
      std::_Transform_unsigned_int___std::back_insert_iterator_std::vector_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t____std::allocator_std::basic_string_wchar_t_std::char_traits_wchar_t__std::allocator_wchar_t___________lambda_263f15600fbf0795fb7bd8e9a17bcf54___(
        &v26,
        v18,
        v17,
        v34);
    if ( *(_QWORD *)(v15 + 56) >= 8u )
      v16 = *(const wchar_t **)v16;
    v19 = (const struct MultiSz *)RegistryKey::ConvertMultiSzToBinary(v36, v34);
    RegistryKey::SetValue((RegistryKey *)&hKey, v16, v19);
    std::vector<_NETSETUPPROPKEY>::_Tidy(v36);
    std::vector<std::wstring>::_Tidy(v34);
    if ( !*(_BYTE *)(v15 + 25) )
    {
      if ( *(_BYTE *)(*(_QWORD *)(v15 + 16) + 25LL) )
      {
        for ( i = *(_QWORD *)(v15 + 8); !*(_BYTE *)(i + 25) && v15 == *(_QWORD *)(i + 16); i = *(_QWORD *)(i + 8) )
          v15 = i;
      }
      else
      {
        i = std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,int>>>::_Min();
      }
      v15 = i;
    }
  }
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(&v43);
  if ( hKey )
    RegCloseKey(hKey);
  if ( v32 )
    RegCloseKey(v32);
  std::_Tree<std::_Tmap_traits<std::wstring,std::vector<unsigned int>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<unsigned int>>>,0>>::erase(
    v33,
    &v26,
    *(_QWORD *)v33[0],
    v33[0]);
  operator delete(v33[0]);
  v43 = &NetSetupTraceLogging::LegacyDescriptionsPlugin::`vftable';
  wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(&v43);
  wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder((wil::details::ThreadFailureCallbackHolder *)v46);
  wil::details::shared_object<wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(v45);
  return wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>(v44);
}

```

## disassembly

```asm
0x1800274f0  mov     rax, rsp
0x1800274f3  push    rbp
0x1800274f4  push    rdi
0x1800274f5  push    r12
0x1800274f7  push    r14
0x1800274f9  push    r15
0x1800274fb  lea     rbp, [rax-268h]
0x180027502  sub     rsp, 340h
0x180027509  mov     [rbp+260h+var_290], 0FFFFFFFFFFFFFFFEh
0x180027511  mov     [rax+8], rbx
0x180027515  mov     [rax+20h], rsi
0x180027519  mov     rax, cs:__security_cookie
0x180027520  xor     rax, rsp
0x180027523  mov     [rbp+260h+var_30], rax
0x18002752a  mov     r14, rdx
0x18002752d  xor     r15d, r15d
0x180027530  mov     rbx, [r8]
0x180027533  lea     rdx, aLegacydescript_0; "LegacyDescriptionsPlugin"
0x18002753a  lea     rcx, [rbp+260h+var_1F0]
0x18002753e  call    ??0?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180027543  lea     rsi, ??_7LegacyDescriptionsPlugin@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::LegacyDescriptionsPlugin::`vftable'
0x18002754a  mov     [rbp+260h+var_1F0], rsi
0x18002754e  lea     rdx, [rbx+278h]; struct _GUID *
0x180027555  lea     rcx, [rbp+260h+var_1F0]; this
0x180027559  call    ?StartActivity@LegacyDescriptionsPlugin@NetSetupTraceLogging@@QEAAXAEBU_GUID@@@Z; NetSetupTraceLogging::LegacyDescriptionsPlugin::StartActivity(_GUID const &)
0x18002755e  nop
0x18002755f  mov     [rbp+260h+var_280], r15
0x180027563  mov     [rbp+260h+var_278], r15
0x180027567  call    ?_Buyheadnode@?$_Tree_alloc@$0A@U?$_Tree_base_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@IV?$allocator@I@std@@@2@@std@@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@IV?$allocator@I@std@@@2@@std@@@2@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@IV?$allocator@I@std@@@2@@std@@PEAX@2@XZ; std::_Tree_alloc<0,std::_Tree_base_types<std::pair<std::wstring const,std::vector<uint>>>>::_Buyheadnode(void)
0x18002756c  mov     [rbp+260h+var_280], rax
0x180027570  xorps   xmm0, xmm0
0x180027573  mov     [rbp+260h+var_238], r14
0x180027577  mov     [rbp+260h+var_230], r15
0x18002757b  mov     dword ptr [rbp+260h+var_228], 9
0x180027582  movdqu  xmmword ptr [rbp+260h+var_228+4], xmm0
0x180027587  lea     rcx, [rbp+260h+var_238]; this
0x18002758b  call    ?get_CurrentControlSetRegistryHandle@TransactionObject@NetSetup2@@QEBAPEAUHKEY__@@XZ; NetSetup2::TransactionObject::get_CurrentControlSetRegistryHandle(void)
0x180027590  mov     rdx, rax
0x180027593  lea     rcx, [rbp+260h+var_288]
0x180027597  call    ?DuplicateFrom@RegistryKey@@SA?AV1@PEAUHKEY__@@@Z; RegistryKey::DuplicateFrom(HKEY__ *)
0x18002759c  nop
0x18002759d  lea     rcx, [rbp+260h+var_230]
0x1800275a1  call    ?_Delete@?$unique_ptr@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@U?$default_delete@V?$vector@VProperty@NetSetup2@@V?$allocator@VProperty@NetSetup2@@@std@@@std@@@2@@std@@AEAAXXZ; std::unique_ptr<std::vector<NetSetup2::Property>>::_Delete(void)
0x1800275a6  lea     rdx, aControlNetwork_4; "Control\\Network\\{4d36e972-e325-11ce-b"...
0x1800275ad  lea     rcx, [rbp+260h+var_288]; this
0x1800275b1  call    ?DeleteSubKey@RegistryKey@@QEBAXPEB_W@Z; RegistryKey::DeleteSubKey(wchar_t const *)
0x1800275b6  mov     qword ptr [rsp+360h+var_338], r15
0x1800275bb  mov     [rsp+360h+var_340], r15
0x1800275c0  lea     ebx, [r15+2]
0x1800275c4  mov     r9d, ebx
0x1800275c7  lea     r8, aControlNetwork_4; "Control\\Network\\{4d36e972-e325-11ce-b"...
0x1800275ce  lea     rdx, [rbp+260h+hKey]
0x1800275d2  lea     rcx, [rbp+260h+var_288]
0x1800275d6  call    ?CreateSubKey@RegistryKey@@QEBA?AV1@PEB_WKPEAXPEAKK@Z; RegistryKey::CreateSubKey(wchar_t const *,ulong,void *,ulong *,ulong)
0x1800275db  nop
0x1800275dc  movups  xmm0, cs:NETSETUPPKEY_Interface_OriginalDeviceDescrAndUniquifier
0x1800275e3  mov     eax, cs:dword_18009AD28
0x1800275e9  lea     edx, [rbx-1]
0x1800275ec  xor     ecx, ecx
0x1800275ee  mov     dword ptr [rsp+360h+var_320+4], ecx
0x1800275f2  movups  [rsp+360h+var_318], xmm0
0x1800275f7  mov     dword ptr [rsp+360h+var_308], eax
0x1800275fb  xorps   xmm1, xmm1
0x1800275fe  movups  [rsp+360h+var_300+8], xmm1
0x180027603  mov     [rbp+260h+var_A0], edx
0x180027609  mov     rax, [rsp+360h+var_320+4]
0x18002760e  mov     [rbp+260h+var_9C], rax
0x180027615  movups  xmm0, [rsp+360h+var_318+4]
0x18002761a  movdqu  [rbp+260h+var_94], xmm0
0x180027622  mov     [rbp+260h+var_84], rcx
0x180027629  mov     [rbp+260h+var_7C], ecx
0x18002762f  movsd   [rbp+260h+var_78], xmm1
0x180027637  mov     rax, [rsp+360h+var_2F0]
0x18002763c  mov     [rbp+260h+var_70], rax
0x180027643  movups  xmm0, cs:NETSETUPPKEY_Interface_PnpInstance
0x18002764a  mov     eax, cs:dword_180099CB8
0x180027650  mov     dword ptr [rsp+360h+var_320+4], ecx
0x180027654  movups  [rsp+360h+var_318], xmm0
0x180027659  mov     dword ptr [rsp+360h+var_308], eax
0x18002765d  movups  [rsp+360h+var_300+8], xmm1
0x180027662  mov     [rbp+260h+var_68], edx
0x180027668  mov     rax, [rsp+360h+var_320+4]
0x18002766d  mov     [rbp+260h+var_64], rax
0x180027674  movups  xmm0, [rsp+360h+var_318+4]
0x180027679  movdqu  [rbp+260h+var_5C], xmm0
0x180027681  mov     [rbp+260h+var_4C], rcx
0x180027688  mov     [rbp+260h+var_44], ecx
0x18002768e  movsd   [rbp+260h+var_40], xmm1
0x180027696  mov     rax, [rsp+360h+var_2F0]
0x18002769b  mov     [rbp+260h+var_38], rax
0x1800276a2  mov     [rsp+360h+var_330], ebx
0x1800276a6  lea     rax, [rbp+260h+var_A0]
0x1800276ad  mov     qword ptr [rsp+360h+var_338], rax
0x1800276b2  mov     dword ptr [rsp+360h+var_340], r15d
0x1800276b7  xor     r9d, r9d
0x1800276ba  lea     rdx, [rbp+260h+var_270]
0x1800276be  mov     rcx, r14
0x1800276c1  call    ??$GetAllObjectsInner@VNetworkInterface@NetSetup2@@@TransactionBase@details@NetSetup2@@AEBA?AV?$vector@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VNetworkInterface@NetSetup2@@U?$default_delete@VNetworkInterface@NetSetup2@@@std@@@std@@@2@@std@@W4_NETSETUP_OBJECT_TYPE@@PEBU_NETSETUPPROPCOMPKEY@@KPEBU_NETSETUPPROP_FILTER_EXPRESSION@@K@Z; NetSetup2::details::TransactionBase::GetAllObjectsInner<NetSetup2::NetworkInterface>(_NETSETUP_OBJECT_TYPE,_NETSETUPPROPCOMPKEY const *,ulong,_NETSETUPPROP_FILTER_EXPRESSION const *,ulong)
0x1800276c6  nop
0x1800276c7  mov     rbx, [rbp+260h+var_270]
0x1800276cb  mov     rdi, [rbp+260h+var_270+8]
0x1800276cf  lea     r12d, [r15+7]
0x1800276d3  cmp     rbx, rdi
0x1800276d6  jz      loc_18002785B
0x1800276dc  mov     rcx, [rbx]; this
0x1800276df  call    ?get_PnpDeviceInterfaceNumber@NetworkInterface@NetSetup2@@QEBAKXZ; NetSetup2::NetworkInterface::get_PnpDeviceInterfaceNumber(void)
0x1800276e4  test    eax, eax
0x1800276e6  jnz     loc_180027852
0x1800276ec  xor     r9d, r9d
0x1800276ef  lea     r8, NETSETUPPKEY_Interface_PnpInstance; unsigned int
0x1800276f6  lea     rdx, [rsp+360h+var_320]; struct _NETSETUPPROPKEY *
0x1800276fb  mov     rcx, [rbx]; this
0x1800276fe  call    ?GetProperty@ActiveObject@NetSetup2@@QEBA?AVProperty@2@AEBU_NETSETUPPROPKEY@@K@Z; NetSetup2::ActiveObject::GetProperty(_NETSETUPPROPKEY const &,ulong)
0x180027703  nop
0x180027704  lea     rdx, [rbp+260h+var_210]
0x180027708  lea     rcx, [rsp+360h+var_320]
0x18002770d  call    ?GetString@Property@NetSetup2@@QEBA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@XZ; NetSetup2::Property::GetString(void)
0x180027712  nop
0x180027713  lea     rcx, [rsp+360h+var_308]
0x180027718  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x18002771d  nop
0x18002771e  lea     rdx, [rbp+260h+var_238]
0x180027722  mov     rcx, [rbx]
0x180027725  call    ?get_OriginalDeviceDescrAndUniquifier@NetworkInterface@NetSetup2@@QEBA?AUOriginalDeviceDescrAndUniquifier_Value@Aggregate@2@XZ; NetSetup2::NetworkInterface::get_OriginalDeviceDescrAndUniquifier(void)
0x18002772a  nop
0x18002772b  lea     rdx, aControlNetwork_9; "Control\\Network\\{4d36e972-e325-11ce-b"...
0x180027732  lea     rcx, [rbp+260h+var_2B0]
0x180027736  call    ??0?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@PEB_W@Z; std::wstring::wstring(wchar_t const *)
0x18002773b  mov     rsi, rax
0x18002773e  mov     rdx, [rbx]
0x180027741  add     rdx, 14h
0x180027745  lea     rcx, [rbp+260h+Block]
0x180027749  call    ?StringFromGuid@@YA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEBU_GUID@@W4GuidConvertOptions@@@Z; StringFromGuid(_GUID const &,GuidConvertOptions)
0x18002774e  nop
0x18002774f  or      r9, 0FFFFFFFFFFFFFFFFh
0x180027753  xor     r8d, r8d
0x180027756  mov     rdx, rax
0x180027759  mov     rcx, rsi
0x18002775c  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x180027761  lea     rdx, aConnection_0; "\\Connection"
0x180027768  mov     rcx, rax
0x18002776b  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@PEB_W@Z; std::wstring::append(wchar_t const *)
0x180027770  mov     [rbp+260h+var_240], r12
0x180027774  mov     [rbp+260h+var_248], r15
0x180027778  mov     word ptr [rbp+260h+var_258], r15w
0x18002777d  or      r9, 0FFFFFFFFFFFFFFFFh
0x180027781  xor     r8d, r8d
0x180027784  mov     rdx, rax
0x180027787  lea     rcx, [rbp+260h+var_258]
0x18002778b  call    ?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x180027790  nop
0x180027791  cmp     [rbp+260h+var_2B8], 8
0x180027796  jb      short loc_1800277A1
0x180027798  mov     rcx, [rbp+260h+Block]; Block
0x18002779c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800277a1  mov     [rbp+260h+var_2B8], r12
0x1800277a5  mov     [rbp+260h+var_2C0], r15
0x1800277a9  mov     word ptr [rbp+260h+Block], r15w
0x1800277ae  cmp     [rbp+260h+var_298], 8
0x1800277b3  jb      short loc_1800277BE
0x1800277b5  mov     rcx, [rbp+260h+var_2B0]; Block
0x1800277b9  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800277be  mov     [rbp+260h+var_298], r12
0x1800277c2  mov     [rbp+260h+var_2A0], r15
0x1800277c6  mov     word ptr [rbp+260h+var_2B0], r15w
0x1800277cb  lea     rax, [rbp+260h+var_210]
0x1800277cf  mov     [rsp+360h+var_320], rax
0x1800277d4  mov     qword ptr [rsp+360h+var_318], r14
0x1800277d9  lea     rax, [rbp+260h+var_238]
0x1800277dd  mov     qword ptr [rsp+360h+var_318+8], rax
0x1800277e2  lea     rax, [rbp+260h+var_288]
0x1800277e6  mov     [rsp+360h+var_308], rax
0x1800277eb  lea     rax, [rbp+260h+var_258]
0x1800277ef  mov     qword ptr [rsp+360h+var_300], rax
0x1800277f4  lea     rax, [rbp+260h+var_280]
0x1800277f8  mov     qword ptr [rsp+360h+var_300+8], rax
0x1800277fd  lea     rcx, [rsp+360h+var_320]
0x180027802  call    NetSetupExecuteInFrame__lambda_4b982fc3cc7a4c08b5268975496311d4___; NetSetupExecuteInFrame__lambda_4b982fc3cc7a4c08b5268975496311d4_
0x180027807  nop
0x180027808  cmp     [rbp+260h+var_240], 8
0x18002780d  jb      short loc_180027818
0x18002780f  mov     rcx, [rbp+260h+var_258]; Block
0x180027813  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027818  mov     [rbp+260h+var_240], r12
0x18002781c  mov     [rbp+260h+var_248], r15
0x180027820  mov     word ptr [rbp+260h+var_258], r15w
0x180027825  cmp     [rbp+260h+var_220], 8
0x18002782a  jb      short loc_180027835
0x18002782c  mov     rcx, [rbp+260h+var_238]; Block
0x180027830  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027835  mov     [rbp+260h+var_220], r12
0x180027839  mov     [rbp+260h+var_228], r15
0x18002783d  mov     word ptr [rbp+260h+var_238], r15w
0x180027842  cmp     [rbp+260h+var_1F8], 8
0x180027847  jb      short loc_180027852
0x180027849  mov     rcx, [rbp+260h+var_210]; Block
0x18002784d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027852  add     rbx, 8
0x180027856  jmp     loc_1800276D3
0x18002785b  mov     rdx, [rbp+260h+var_270]
0x18002785f  test    rdx, rdx
0x180027862  jz      short loc_180027876
0x180027864  mov     r8, [rbp+260h+var_270+8]
0x180027868  call    ?_Destroy@?$vector@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@V?$allocator@V?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@std@@@2@@std@@IEAAXPEAV?$unique_ptr@VMux@NetSetup2@@U?$default_delete@VMux@NetSetup2@@@std@@@2@0@Z; std::vector<std::unique_ptr<NetSetup2::Mux>>::_Destroy(std::unique_ptr<NetSetup2::Mux> *,std::unique_ptr<NetSetup2::Mux> *)
0x18002786d  mov     rcx, [rbp+260h+var_270]; Block
0x180027871  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027876  mov     rdi, [rbp+260h+var_280]
0x18002787a  mov     rbx, [rdi]
0x18002787d  cmp     rbx, rdi
0x180027880  jz      loc_180027948
0x180027886  lea     rsi, [rbx+20h]
0x18002788a  mov     rdx, [rbx+48h]
0x18002788e  mov     rcx, [rbx+40h]
0x180027892  mov     r8, rdx
0x180027895  sub     r8, rcx
0x180027898  sar     r8, 2
0x18002789c  call    ??$_Sort@PEAI_J@std@@YAXPEAI0_J@Z; std::_Sort<uint *,__int64>(uint *,uint *,__int64)
0x1800278a1  xorps   xmm0, xmm0
0x1800278a4  movdqu  xmmword ptr [rbp+260h+var_270], xmm0
0x1800278a9  mov     [rbp+260h+var_260], r15
0x1800278ad  mov     r8, [rbx+48h]
0x1800278b1  mov     rdx, [rbx+40h]
0x1800278b5  cmp     rdx, r8
0x1800278b8  jz      short loc_1800278C9
0x1800278ba  lea     r9, [rbp+260h+var_270]
0x1800278be  lea     rcx, [rbp+260h+var_2D8]
0x1800278c2  call    std___Transform_unsigned_int___std__back_insert_iterator_std__vector_std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t____std__allocator_std__basic_string_wchar_t_std__char_traits_wchar_t__std__allocator_wchar_t___________lambda_263f15600fbf0795fb7bd8e9a17bcf54___
0x1800278c7  jmp     short loc_1800278D1
0x1800278c9  lea     rax, [rbp+260h+var_270]
0x1800278cd  mov     [rbp+260h+var_2D8], rax
0x1800278d1  cmp     qword ptr [rsi+18h], 8
0x1800278d6  jb      short loc_1800278DB
0x1800278d8  mov     rsi, [rsi]
0x1800278db  lea     rdx, [rbp+260h+var_270]
0x1800278df  lea     rcx, [rbp+260h+var_258]
0x1800278e3  call    ?ConvertMultiSzToBinary@RegistryKey@@SA?AVMultiSz@@AEBV?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@@Z; RegistryKey::ConvertMultiSzToBinary(std::vector<std::wstring> const &)
0x1800278e8  nop
0x1800278e9  mov     r8, rax; struct MultiSz *
0x1800278ec  mov     rdx, rsi; wchar_t *
0x1800278ef  lea     rcx, [rbp+260h+hKey]; this
0x1800278f3  call    ?SetValue@RegistryKey@@QEBAXPEB_WAEBVMultiSz@@@Z; RegistryKey::SetValue(wchar_t const *,MultiSz const &)
0x1800278f8  nop
0x1800278f9  lea     rcx, [rbp+260h+var_258]
0x1800278fd  call    ?_Tidy@?$vector@U_NETSETUPPROPKEY@@V?$allocator@U_NETSETUPPROPKEY@@@std@@@std@@IEAAXXZ; std::vector<_NETSETUPPROPKEY>::_Tidy(void)
0x180027902  nop
0x180027903  lea     rcx, [rbp+260h+var_270]
0x180027907  call    ?_Tidy@?$vector@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$allocator@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@@std@@IEAAXXZ; std::vector<std::wstring>::_Tidy(void)
0x18002790c  cmp     [rbx+19h], r15b
0x180027910  jnz     loc_18002787D
0x180027916  mov     rcx, [rbx+10h]
0x18002791a  cmp     [rcx+19h], r15b
0x18002791e  jnz     short loc_180027927
0x180027920  call    ?_Min@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@std@@@std@@@std@@SAPEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@H@std@@PEAX@2@PEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,int>>>::_Min(std::_Tree_node<std::pair<std::wstring const,int>,void *> *)
0x180027925  jmp     short loc_180027940
0x180027927  mov     rax, [rbx+8]
0x18002792b  jmp     short loc_18002793A
0x18002792d  cmp     rbx, [rax+10h]
0x180027931  jnz     short loc_180027940
0x180027933  mov     rbx, rax
0x180027936  mov     rax, [rax+8]
0x18002793a  cmp     [rax+19h], r15b
0x18002793e  jz      short loc_18002792D
0x180027940  mov     rbx, rax
0x180027943  jmp     loc_18002787D
0x180027948  lea     rcx, [rbp+260h+var_1F0]
0x18002794c  call    ?Stop@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x180027951  nop
0x180027952  mov     rcx, [rbp+260h+hKey]; hKey
0x180027956  test    rcx, rcx
0x180027959  jz      short loc_180027962
0x18002795b  call    cs:__imp_RegCloseKey
0x180027961  nop
0x180027962  mov     rcx, [rbp+260h+var_288]; hKey
0x180027966  test    rcx, rcx
0x180027969  jz      short loc_180027972
0x18002796b  call    cs:__imp_RegCloseKey
0x180027971  nop
0x180027972  mov     r8, [rbp+260h+var_280]
0x180027976  mov     r9, r8
0x180027979  mov     r8, [r8]
0x18002797c  lea     rdx, [rbp+260h+var_2D8]
0x180027980  lea     rcx, [rbp+260h+var_280]
0x180027984  call    ?erase@?$_Tree@V?$_Tmap_traits@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@IV?$allocator@I@std@@@2@U?$less@V?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@IV?$allocator@I@std@@@2@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@IV?$allocator@I@std@@@2@@std@@@std@@@std@@@2@V?$_Tree_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@V?$vector@IV?$allocator@I@std@@@2@@std@@@std@@@std@@@2@0@Z; std::_Tree<std::_Tmap_traits<std::wstring,std::vector<uint>,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::vector<uint>>>,0>>::erase(std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<uint>>>>>,std::_Tree_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<std::wstring const,std::vector<uint>>>>>)
0x180027989  mov     rcx, [rbp+260h+var_280]; Block
0x18002798d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180027992  nop
0x180027993  lea     rax, ??_7LegacyDescriptionsPlugin@NetSetupTraceLogging@@6B@; const NetSetupTraceLogging::LegacyDescriptionsPlugin::`vftable'
0x18002799a  mov     [rbp+260h+var_1F0], rax
0x18002799e  lea     rcx, [rbp+260h+var_1F0]
0x1800279a2  call    ?Destroy@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x1800279a7  lea     rcx, [rbp+260h+var_D0]; this
0x1800279ae  call    ??1ThreadFailureCallbackHolder@details@wil@@QEAA@XZ; wil::details::ThreadFailureCallbackHolder::~ThreadFailureCallbackHolder(void)
0x1800279b3  lea     rcx, [rbp+260h+var_D8]
0x1800279ba  call    ?reset@?$shared_object@V?$ActivityData@VNetSetupTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@@details@wil@@QEAAXXZ; wil::details::shared_object<wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>>::reset(void)
0x1800279bf  lea     rcx, [rbp+260h+var_1E8]
0x1800279c3  call    ??1?$ActivityData@VNetSetupTraceLogging@@U_TlgReflectorTag_Param0IsProviderType@@@?$ActivityBase@VNetSetupTraceLogging@@$0A@$00$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<NetSetupTraceLogging,0,1,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>::~ActivityData<NetSetupTraceLogging,_TlgReflectorTag_Param0IsProviderType>(void)
0x1800279c8  mov     rcx, [rbp+260h+var_30]
0x1800279cf  xor     rcx, rsp; StackCookie
0x1800279d2  call    __security_check_cookie
0x1800279d7  lea     r11, [rsp+360h+var_20]
  ... truncated ...
```
