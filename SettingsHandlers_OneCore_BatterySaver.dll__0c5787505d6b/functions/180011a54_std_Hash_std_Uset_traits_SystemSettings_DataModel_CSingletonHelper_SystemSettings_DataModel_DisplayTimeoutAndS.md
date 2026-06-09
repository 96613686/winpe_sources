# std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &)

- ea: `0x180011a54`
- end: `0x180011bb1`
- name: `??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@Z`
- size: `349`
- prototype: `__int64 __fastcall(float *, __int64, unsigned __int8 *)`
- caller_count: `10`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180011980`
- `0x180017998`
- `0x180017a6c`
- `0x1800260a4`
- `0x180026274`
- `0x1800265fc`
- `0x1800267c0`
- `0x180026984`
- `0x18003cc80`
- `0x18003dfac`

## callees

- `0x18001146c`
- `0x1800117b8`
- `0x180011a54`
- `0x180011f30`
- `0x180012288`
- `0x18001386c`
- `0x18001394c`
- `0x180013b88`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011ab9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011ab9`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback * const &>(
        float *a1,
        __int64 a2,
        unsigned __int8 *a3)
{
  __int64 v6; // r14
  _QWORD *v7; // rbp
  __int64 v8; // rdx
  float v9; // xmm0_4
  __int64 v10; // rcx
  float v11; // xmm1_4
  __int64 v12; // rax
  __int64 v13; // rax
  _QWORD v15[2]; // [rsp+20h] [rbp-58h] BYREF
  _OWORD v16[4]; // [rsp+30h] [rbp-48h] BYREF

  v6 = std::_Conditionally_enabled_hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *,1>::operator()(a3);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,0>>::_Find_last<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>(
    a1,
    v16,
    a3,
    v6);
  if ( *((_QWORD *)&v16[0] + 1) )
  {
    *(_QWORD *)a2 = *((_QWORD *)&v16[0] + 1);
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( *((_QWORD *)a1 + 2) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v15[0] = a1 + 2;
    v7 = std::_Allocate<16,std::_Default_allocate_traits>(0x18u);
    v15[1] = v7;
    v7[2] = *(_QWORD *)a3;
    v8 = *((_QWORD *)a1 + 2) + 1LL;
    if ( v8 < 0 )
      v9 = (float)(v8 & 1 | (unsigned int)((unsigned __int64)v8 >> 1))
         + (float)(v8 & 1 | (unsigned int)((unsigned __int64)v8 >> 1));
    else
      v9 = (float)(int)v8;
    v10 = *((_QWORD *)a1 + 7);
    if ( v10 < 0 )
    {
      v12 = *((_QWORD *)a1 + 7) & 1LL | ((unsigned __int64)v10 >> 1);
      v11 = (float)(int)v12 + (float)(int)v12;
    }
    else
    {
      v11 = (float)(int)v10;
    }
    if ( (float)(v9 / v11) > *a1 )
    {
      v13 = std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::_Desired_grow_bucket_count(a1);
      std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *>,0>>::_Forced_rehash(
        a1,
        v13);
      v16[0] = *(_OWORD *)std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,0>>::_Find_last<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>(
                            a1,
                            v16,
                            v7 + 2,
                            v6);
    }
    *(_QWORD *)a2 = std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *>,0>>::_Insert_new_node_before(
                      a1,
                      v6,
                      *(_QWORD *)&v16[0],
                      v7,
                      v15[0],
                      0);
    *(_BYTE *)(a2 + 8) = 1;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,void *>>>(v15);
  }
  return a2;
}

```

## disassembly

```asm
0x180011a54  push    rbx
0x180011a56  push    rbp
0x180011a57  push    rsi
0x180011a58  push    rdi
0x180011a59  push    r14
0x180011a5b  push    r15
0x180011a5d  sub     rsp, 48h
0x180011a61  mov     rsi, r8
0x180011a64  mov     rbx, rdx
0x180011a67  mov     rdi, rcx
0x180011a6a  mov     rcx, r8; unsigned __int8 *
0x180011a6d  call    ??R?$_Conditionally_enabled_hash@PEAVCCallback@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@$00@std@@SA_KAEBQEAVCCallback@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@Z; std::_Conditionally_enabled_hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *,1>::operator()(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback * const &)
0x180011a72  mov     r14, rax
0x180011a75  mov     r9, rax
0x180011a78  mov     r8, rsi
0x180011a7b  lea     rdx, [rsp+78h+var_48]
0x180011a80  mov     rcx, rdi
0x180011a83  call    ??$_Find_last@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@PEAX@std@@@1@AEBQEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@_K@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,0>>::_Find_last<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback * const &,unsigned __int64)
0x180011a88  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x180011a8d  test    rdx, rdx
0x180011a90  jz      short loc_180011A9E
0x180011a92  mov     [rbx], rdx
0x180011a95  mov     byte ptr [rbx+8], 0
0x180011a99  jmp     loc_180011BA1
0x180011a9e  lea     rax, [rdi+8]
0x180011aa2  mov     rcx, 0AAAAAAAAAAAAAAAh
0x180011aac  cmp     [rax+8], rcx
0x180011ab0  jnz     short loc_180011AC0
0x180011ab2  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180011ab9  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180011ac0  mov     [rsp+78h+var_58], rax
0x180011ac5  mov     [rsp+78h+var_50], 0
0x180011ace  mov     ecx, 18h
0x180011ad3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180011ad8  mov     rbp, rax
0x180011adb  mov     [rsp+78h+var_50], rax
0x180011ae0  mov     rcx, [rsi]
0x180011ae3  mov     [rax+10h], rcx
0x180011ae7  mov     rdx, [rdi+10h]
0x180011aeb  add     rdx, 1
0x180011aef  xorps   xmm0, xmm0
0x180011af2  js      short loc_180011AFB
0x180011af4  cvtsi2ss xmm0, rdx
0x180011af9  jmp     short loc_180011B13
0x180011afb  mov     rcx, rdx
0x180011afe  shr     rcx, 1
0x180011b01  mov     rax, rdx
0x180011b04  and     eax, 1
0x180011b07  or      rcx, rax
0x180011b0a  cvtsi2ss xmm0, rcx
0x180011b0f  addss   xmm0, xmm0
0x180011b13  mov     rcx, [rdi+38h]
0x180011b17  xorps   xmm1, xmm1
0x180011b1a  test    rcx, rcx
0x180011b1d  js      short loc_180011B26
0x180011b1f  cvtsi2ss xmm1, rcx
0x180011b24  jmp     short loc_180011B3B
0x180011b26  mov     rax, rcx
0x180011b29  shr     rax, 1
0x180011b2c  and     ecx, 1
0x180011b2f  or      rax, rcx
0x180011b32  cvtsi2ss xmm1, rax
0x180011b37  addss   xmm1, xmm1
0x180011b3b  divss   xmm0, xmm1
0x180011b3f  comiss  xmm0, dword ptr [rdi]
0x180011b42  jbe     short loc_180011B74
0x180011b44  mov     rcx, rdi
0x180011b47  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180011b4c  mov     rdx, rax
0x180011b4f  mov     rcx, rdi
0x180011b52  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@U_POWER_MODE_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@U_POWER_MODE_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@U_POWER_MODE_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@U_POWER_MODE_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@U_POWER_MODE_STATE@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::_POWER_MODE_STATE>::CCallback *>,0>>::_Forced_rehash(unsigned __int64)
0x180011b57  mov     r9, r14
0x180011b5a  lea     r8, [rbp+10h]
0x180011b5e  lea     rdx, [rsp+78h+var_48]
0x180011b63  mov     rcx, rdi
0x180011b66  call    ??$_Find_last@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@PEAX@std@@@1@AEBQEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@_K@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,0>>::_Find_last<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback * const &,unsigned __int64)
0x180011b6b  movups  xmm0, xmmword ptr [rax]
0x180011b6e  movdqu  [rsp+78h+var_48], xmm0
0x180011b74  mov     [rsp+78h+var_50], 0
0x180011b7d  mov     r9, rbp
0x180011b80  mov     r8, qword ptr [rsp+78h+var_48]
0x180011b85  mov     rdx, r14
0x180011b88  mov     rcx, rdi
0x180011b8b  call    ?_Insert_new_node_before@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEAAPEAU?$_List_node@PEAVCCallback@?$CSingletonHelper@W4BatterySaverCallbackSetting@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@PEAX@2@_KQEAU32@1@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *>,0>>::_Insert_new_node_before(unsigned __int64,std::_List_node<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *,void *> * const,std::_List_node<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::BatterySaverCallbackSetting>::CCallback *,void *> * const)
0x180011b90  mov     [rbx], rax
0x180011b93  mov     byte ptr [rbx+8], 1
0x180011b97  lea     rcx, [rsp+78h+var_58]
0x180011b9c  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,void *>>>(void)
0x180011ba1  mov     rax, rbx
0x180011ba4  add     rsp, 48h
0x180011ba8  pop     r15
0x180011baa  pop     r14
0x180011bac  pop     rdi
0x180011bad  pop     rsi
0x180011bae  pop     rbp
0x180011baf  pop     rbx
0x180011bb0  retn
```
