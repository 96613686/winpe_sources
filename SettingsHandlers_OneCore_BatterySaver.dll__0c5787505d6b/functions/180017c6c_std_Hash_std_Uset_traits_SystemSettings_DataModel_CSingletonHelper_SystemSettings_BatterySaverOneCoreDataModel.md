# std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &>(SystemSettings::DataModel::CSingletonHelper<SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &)

- ea: `0x180017c6c`
- end: `0x180017e10`
- name: `??$emplace@AEBQEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@QEAA?AU?$pair@V?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@PEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@@std@@@std@@_N@1@AEBQEAVCCallback@?$CSingletonHelper@W4AdaptiveModeState@BatterySaverOneCoreDataModel@SystemSettings@@@DataModel@SystemSettings@@@Z`
- size: `420`
- prototype: `__int64 __fastcall(float *, __int64, unsigned __int8 *)`
- caller_count: `8`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180026438`
- `0x180030400`
- `0x180030f7c`
- `0x1800323f8`
- `0x1800324a0`
- `0x180036ad0`
- `0x180036c94`
- `0x180045c84`

## callees

- `0x18000967c`
- `0x1800117b8`
- `0x180011f30`
- `0x18001386c`
- `0x180013910`
- `0x180017c6c`
- `0x18002aa44`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017cd9`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180017cd9`

## pseudocode

```c
__int64 __fastcall std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback *>,0>>::emplace<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::BatterySaverOneCoreDataModel::AdaptiveModeState>::CCallback * const &>(
        float *a1,
        __int64 a2,
        unsigned __int8 *a3)
{
  __int64 appended; // r15
  _QWORD *v7; // rbx
  __int64 v8; // rdx
  float v9; // xmm0_4
  __int64 v10; // rcx
  float v11; // xmm1_4
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rdx
  _QWORD *v15; // r8
  __int64 v16; // rax
  __int64 v17; // rcx
  __int64 v18; // r9
  _QWORD *v20; // [rsp+20h] [rbp-58h] BYREF
  _QWORD *v21; // [rsp+28h] [rbp-50h]
  _OWORD v22[4]; // [rsp+30h] [rbp-48h] BYREF

  appended = std::_Fnv1a_append_bytes((unsigned __int64)a1, a3, 8u);
  std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,0>>::_Find_last<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>(
    a1,
    v22,
    a3,
    appended);
  if ( !*((_QWORD *)&v22[0] + 1) )
  {
    if ( *((_QWORD *)a1 + 2) == 0xAAAAAAAAAAAAAAALL )
      std::_Xlength_error("unordered_map/set too long");
    v20 = a1 + 2;
    v7 = operator new(0x18u);
    v21 = v7;
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
      std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,0>>::_Forced_rehash(
        a1,
        v13);
      v22[0] = *(_OWORD *)std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,0>>::_Find_last<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>(
                            a1,
                            v22,
                            v7 + 2,
                            appended);
    }
    v21 = 0;
    v14 = *(_QWORD *)&v22[0];
    v15 = *(_QWORD **)(*(_QWORD *)&v22[0] + 8LL);
    ++*((_QWORD *)a1 + 2);
    *v7 = v14;
    v7[1] = v15;
    *v15 = v7;
    *(_QWORD *)(v14 + 8) = v7;
    v16 = 2 * (appended & *((_QWORD *)a1 + 6));
    v17 = *((_QWORD *)a1 + 3);
    v18 = *(_QWORD *)(v17 + 16 * (appended & *((_QWORD *)a1 + 6)));
    if ( v18 == *((_QWORD *)a1 + 1) )
    {
      *(_QWORD *)(v17 + 16 * (appended & *((_QWORD *)a1 + 6))) = v7;
LABEL_18:
      *(_QWORD *)(v17 + 8 * v16 + 8) = v7;
      goto LABEL_19;
    }
    if ( v18 == v14 )
    {
      *(_QWORD *)(v17 + 16 * (appended & *((_QWORD *)a1 + 6))) = v7;
    }
    else if ( *(_QWORD **)(v17 + 16 * (appended & *((_QWORD *)a1 + 6)) + 8) == v15 )
    {
      goto LABEL_18;
    }
LABEL_19:
    *(_QWORD *)a2 = v7;
    *(_BYTE *)(a2 + 8) = 1;
    std::_Alloc_construct_ptr<std::allocator<std::_List_node<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<SystemSettings::DataModel::CSingletonHelper<enum SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,void *>>>(&v20);
    return a2;
  }
  *(_QWORD *)a2 = *((_QWORD *)&v22[0] + 1);
  *(_BYTE *)(a2 + 8) = 0;
  return a2;
}

```

## disassembly

```asm
0x180017c6c  push    rbx
0x180017c6e  push    rbp
0x180017c6f  push    rsi
0x180017c70  push    rdi
0x180017c71  push    r12
0x180017c73  push    r14
0x180017c75  push    r15
0x180017c77  sub     rsp, 40h
0x180017c7b  mov     r14, r8
0x180017c7e  mov     rdi, rdx
0x180017c81  mov     rsi, rcx
0x180017c84  mov     r8d, 8; unsigned __int64
0x180017c8a  mov     rdx, r14; unsigned __int8 *
0x180017c8d  call    ?_Fnv1a_append_bytes@std@@YA_K_KQEBE_K@Z; std::_Fnv1a_append_bytes(unsigned __int64,uchar const * const,unsigned __int64)
0x180017c92  mov     r15, rax
0x180017c95  mov     r9, rax
0x180017c98  mov     r8, r14
0x180017c9b  lea     rdx, [rsp+78h+var_48]
0x180017ca0  mov     rcx, rsi
0x180017ca3  call    ??$_Find_last@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@PEAX@std@@@1@AEBQEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@_K@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,0>>::_Find_last<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback * const &,unsigned __int64)
0x180017ca8  mov     rdx, qword ptr [rsp+78h+var_48+8]
0x180017cad  test    rdx, rdx
0x180017cb0  jz      short loc_180017CBE
0x180017cb2  mov     [rdi], rdx
0x180017cb5  mov     byte ptr [rdi+8], 0
0x180017cb9  jmp     loc_180017DFE
0x180017cbe  lea     rbp, [rsi+8]
0x180017cc2  mov     rax, 0AAAAAAAAAAAAAAAh
0x180017ccc  cmp     [rbp+8], rax
0x180017cd0  jnz     short loc_180017CE0
0x180017cd2  lea     rcx, aUnorderedMapSe; "unordered_map/set too long"
0x180017cd9  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180017ce0  mov     [rsp+78h+var_58], rbp
0x180017ce5  mov     [rsp+78h+var_50], 0
0x180017cee  mov     ecx, 18h; Size
0x180017cf3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180017cf8  mov     rbx, rax
0x180017cfb  mov     [rsp+78h+var_50], rax
0x180017d00  mov     rcx, [r14]
0x180017d03  mov     [rax+10h], rcx
0x180017d07  mov     rdx, [rsi+10h]
0x180017d0b  add     rdx, 1
0x180017d0f  xorps   xmm0, xmm0
0x180017d12  js      short loc_180017D1B
0x180017d14  cvtsi2ss xmm0, rdx
0x180017d19  jmp     short loc_180017D33
0x180017d1b  mov     rcx, rdx
0x180017d1e  shr     rcx, 1
0x180017d21  mov     rax, rdx
0x180017d24  and     eax, 1
0x180017d27  or      rcx, rax
0x180017d2a  cvtsi2ss xmm0, rcx
0x180017d2f  addss   xmm0, xmm0
0x180017d33  mov     rcx, [rsi+38h]
0x180017d37  xorps   xmm1, xmm1
0x180017d3a  test    rcx, rcx
0x180017d3d  js      short loc_180017D46
0x180017d3f  cvtsi2ss xmm1, rcx
0x180017d44  jmp     short loc_180017D5B
0x180017d46  mov     rax, rcx
0x180017d49  shr     rax, 1
0x180017d4c  and     ecx, 1
0x180017d4f  or      rax, rcx
0x180017d52  cvtsi2ss xmm1, rax
0x180017d57  addss   xmm1, xmm1
0x180017d5b  divss   xmm0, xmm1
0x180017d5f  comiss  xmm0, dword ptr [rsi]
0x180017d62  jbe     short loc_180017D94
0x180017d64  mov     rcx, rsi
0x180017d67  call    ?_Desired_grow_bucket_count@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEBA_K_K@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *>,0>>::_Desired_grow_bucket_count(unsigned __int64)
0x180017d6c  mov     rdx, rax
0x180017d6f  mov     rcx, rsi
0x180017d72  call    ?_Forced_rehash@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEAAX_K@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,0>>::_Forced_rehash(unsigned __int64)
0x180017d77  mov     r9, r15
0x180017d7a  lea     r8, [rbx+10h]
0x180017d7e  lea     rdx, [rsp+78h+var_48]
0x180017d83  mov     rcx, rsi
0x180017d86  call    ??$_Find_last@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@?$_Hash@V?$_Uset_traits@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@V?$_Uhash_compare@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@U?$hash@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@std@@U?$equal_to@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@6@@std@@V?$allocator@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@@6@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@PEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@PEAX@std@@@1@AEBQEAVCCallback@?$CSingletonHelper@U_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD@@@DataModel@SystemSettings@@_K@Z; std::_Hash<std::_Uset_traits<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::_Uhash_compare<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *,std::hash<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,std::equal_to<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>>,std::allocator<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>,0>>::_Find_last<SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback *>(SystemSettings::DataModel::CSingletonHelper<_WNF_PO_POWER_ADAPTER_REC_STATUS_PAYLOAD>::CCallback * const &,unsigned __int64)
0x180017d8b  movups  xmm0, xmmword ptr [rax]
0x180017d8e  movdqu  [rsp+78h+var_48], xmm0
0x180017d94  mov     [rsp+78h+var_50], 0
0x180017d9d  mov     rdx, qword ptr [rsp+78h+var_48]
0x180017da2  mov     r8, [rdx+8]
0x180017da6  inc     qword ptr [rsi+10h]
0x180017daa  mov     [rbx], rdx
0x180017dad  mov     [rbx+8], r8
0x180017db1  mov     [r8], rbx
0x180017db4  mov     [rdx+8], rbx
0x180017db8  mov     rax, [rsi+30h]
0x180017dbc  and     rax, r15
0x180017dbf  add     rax, rax
0x180017dc2  mov     rcx, [rsi+18h]
0x180017dc6  mov     r9, [rcx+rax*8]
0x180017dca  cmp     r9, [rbp+0]
0x180017dce  jnz     short loc_180017DD6
0x180017dd0  mov     [rcx+rax*8], rbx
0x180017dd4  jmp     short loc_180017DE8
0x180017dd6  cmp     r9, rdx
0x180017dd9  jnz     short loc_180017DE1
0x180017ddb  mov     [rcx+rax*8], rbx
0x180017ddf  jmp     short loc_180017DED
0x180017de1  cmp     [rcx+rax*8+8], r8
0x180017de6  jnz     short loc_180017DED
0x180017de8  mov     [rcx+rax*8+8], rbx
0x180017ded  mov     [rdi], rbx
0x180017df0  mov     byte ptr [rdi+8], 1
0x180017df4  lea     rcx, [rsp+78h+var_58]
0x180017df9  call    ??1?$_Alloc_construct_ptr@V?$allocator@U?$_List_node@PEAVCCallback@?$CSingletonHelper@W4DisplayTimeoutAndSleepEvent@DataModel@SystemSettings@@@DataModel@SystemSettings@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Alloc_construct_ptr<std::allocator<std::_List_node<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,void *>>>::~_Alloc_construct_ptr<std::allocator<std::_List_node<SystemSettings::DataModel::CSingletonHelper<SystemSettings::DataModel::DisplayTimeoutAndSleepEvent>::CCallback *,void *>>>(void)
0x180017dfe  mov     rax, rdi
0x180017e01  add     rsp, 40h
0x180017e05  pop     r15
0x180017e07  pop     r14
0x180017e09  pop     r12
0x180017e0b  pop     rdi
0x180017e0c  pop     rsi
0x180017e0d  pop     rbp
0x180017e0e  pop     rbx
0x180017e0f  retn
```
