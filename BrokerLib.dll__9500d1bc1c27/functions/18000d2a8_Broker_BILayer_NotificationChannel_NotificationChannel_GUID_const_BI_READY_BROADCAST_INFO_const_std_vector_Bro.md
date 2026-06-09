# Broker::BILayer::NotificationChannel::NotificationChannel(_GUID const &,_BI_READY_BROADCAST_INFO const *,std::vector<Broker::BILayer::NotificationChannel::TCallback,std::allocator<Broker::BILayer::NotificationChannel::TCallback>>)

- ea: `0x18000d2a8`
- end: `0x18000d5c3`
- name: `??0NotificationChannel@BILayer@Broker@@QEAA@AEBU_GUID@@PEBU_BI_READY_BROADCAST_INFO@@V?$vector@UTCallback@NotificationChannel@BILayer@Broker@@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@@Z`
- size: `795`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: `broker_com_uri`

## callers

- `0x18000c4c0`

## callees

- `0x180004ae0`
- `0x18000cdac`
- `0x18000d2a8`
- `0x18000d5cc`
- `0x18000dc30`
- `0x18000dcd4`
- `0x18000dd78`
- `0x18000e000`
- `0x18000e0a4`
- `0x18000e148`
- `0x18000e188`
- `0x18000e22c`
- `0x18000e360`
- `0x1800137e4`
- `0x180013888`
- `0x18001402c`
- `0x180014174`
- `0x180014e54`
- `0x1800165da`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 *__fastcall Broker::BILayer::NotificationChannel::NotificationChannel(
        __int64 *a1,
        _OWORD *a2,
        __int64 a3,
        __int64 a4)
{
  __int64 v8; // r8
  unsigned __int64 v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rax
  __int64 v12; // rax
  __int64 v13; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 v20; // rax
  _BYTE v22[8]; // [rsp+20h] [rbp-40h] BYREF
  std::_Ref_count_base *v23; // [rsp+28h] [rbp-38h]
  void **pExceptionObject; // [rsp+30h] [rbp-30h] BYREF
  __int128 v25; // [rsp+38h] [rbp-28h]
  int v26; // [rsp+48h] [rbp-18h]
  int v27; // [rsp+50h] [rbp-10h]
  int v28; // [rsp+98h] [rbp+38h] BYREF
  __int64 *v29; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v30; // [rsp+A8h] [rbp+48h]

  v30 = a4;
  *a1 = 0;
  a1[1] = 0;
  a1[2] = 0;
  std::vector<Broker::BILayer::NotificationChannel::TCallback>::vector<Broker::BILayer::NotificationChannel::TCallback>(
    a1 + 3,
    a4);
  *((_OWORD *)a1 + 3) = *a2;
  v28 = 0;
  if ( !a3 )
  {
    v25 = 0;
    v26 = 1;
    pExceptionObject = &Broker::Win32Error::`vftable';
    v27 = 87;
    throw (Broker::Win32Error *)&pExceptionObject;
  }
  v8 = *a1;
  v9 = (a1[1] - *a1) >> 4;
  if ( v9 <= 0xC )
  {
    if ( v9 < 0xC )
    {
      if ( (unsigned __int64)((a1[2] - v8) >> 4) >= 0xC )
        a1[1] = std::_Uninitialized_value_construct_n<std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>(
                  a1[1],
                  12 - v9);
      else
        std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Resize_reallocate<std::_Value_init_tag>(a1);
    }
  }
  else
  {
    v10 = v8 + 192;
    std::_Destroy_range<std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>(v8 + 192, a1[1]);
    a1[1] = v10;
  }
  v29 = a1;
  v11 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_86892d1650ab55be7a4c4976be615a04___(
          v22,
          a3 + 36,
          &v28,
          &v29);
  std::shared_ptr<Broker::BrokerEvent>::operator=(*a1 + 64, v11);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v29 = a1;
  v12 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_00e69972730096af00ca8c298f9f4a9e___(
          v22,
          a3 + 4,
          &v28,
          &v29);
  std::shared_ptr<Broker::BrokerEvent>::operator=(*a1, v12);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v29 = a1;
  v13 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_6bfd76c01525acb47ab5bcaa8ea8042e___(
          v22,
          a3 + 12,
          &v28,
          &v29);
  std::shared_ptr<Broker::BrokerEvent>::operator=(*a1 + 16, v13);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v29 = a1;
  v14 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_ed25073690fe97cfe2ed26a37220a83f___(
          v22,
          a3 + 44,
          &v28,
          &v29);
  std::shared_ptr<Broker::BrokerEvent>::operator=(*a1 + 80, v14);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v29 = a1;
  v15 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_9d24c723111f0c973d4021d51a62e01e___(
          v22,
          a3 + 52,
          &v28,
          &v29);
  std::shared_ptr<Broker::BrokerEvent>::operator=(*a1 + 96, v15);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v29 = a1;
  v16 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_1c32acd994d3000f15957eeb4748b2f8___(
          v22,
          a3 + 20,
          &v28,
          &v29);
  std::shared_ptr<Broker::BrokerEvent>::operator=(*a1 + 32, v16);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v29 = a1;
  v17 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_29d90547a1146d9dafb960207b00aa6e___(
          v22,
          a3 + 28,
          &v28,
          &v29);
  std::shared_ptr<Broker::BrokerEvent>::operator=(*a1 + 48, v17);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v29 = a1;
  v18 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_67a15ee0df3935e87e13224f0fa153b5___(
          v22,
          a3 + 60,
          &v28,
          &v29);
  std::shared_ptr<Broker::BrokerEvent>::operator=(*a1 + 112, v18);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v29 = a1;
  v19 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_5d7b7f460b8d2e2d49dbd32e66ff681c___(
          v22,
          a3 + 68,
          &v28,
          &v29);
  std::shared_ptr<Broker::BrokerEvent>::operator=(*a1 + 128, v19);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  v29 = a1;
  v20 = std::make_shared_Broker::BILayer::WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_a90fc444ce5b75418fe9bacc436dfeb6___(
          v22,
          a3 + 76,
          &v28,
          &v29);
  std::shared_ptr<Broker::BrokerEvent>::operator=(*a1 + 144, v20);
  if ( v23 )
    std::_Ref_count_base::_Decref(v23);
  std::vector<Broker::BILayer::NotificationChannel::TCallback>::_Tidy(a4);
  return a1;
}

```

## disassembly

```asm
0x18000d2a8  mov     [rsp-28h+arg_18], r9
0x18000d2ad  mov     [rsp-28h+arg_0], rcx
0x18000d2b2  push    rbp
0x18000d2b3  push    rbx
0x18000d2b4  push    rsi
0x18000d2b5  push    rdi
0x18000d2b6  push    r14
0x18000d2b8  mov     rbp, rsp
0x18000d2bb  sub     rsp, 60h
0x18000d2bf  mov     r14, r9
0x18000d2c2  mov     rsi, r8
0x18000d2c5  mov     rbx, rdx
0x18000d2c8  mov     rdi, rcx
0x18000d2cb  mov     qword ptr [rcx], 0
0x18000d2d2  mov     qword ptr [rcx+8], 0
0x18000d2da  mov     qword ptr [rcx+10h], 0
0x18000d2e2  add     rcx, 18h
0x18000d2e6  mov     rdx, r9
0x18000d2e9  call    ??0?$vector@UTCallback@NotificationChannel@BILayer@Broker@@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@QEAA@AEBV01@@Z; std::vector<Broker::BILayer::NotificationChannel::TCallback>::vector<Broker::BILayer::NotificationChannel::TCallback>(std::vector<Broker::BILayer::NotificationChannel::TCallback> const &)
0x18000d2ee  nop
0x18000d2ef  movups  xmm0, xmmword ptr [rbx]
0x18000d2f2  movdqu  xmmword ptr [rdi+30h], xmm0
0x18000d2f7  mov     [rbp+arg_8], 0
0x18000d2fe  test    rsi, rsi
0x18000d301  jnz     short loc_18000D334
0x18000d303  xorps   xmm0, xmm0
0x18000d306  movups  [rbp+var_28], xmm0
0x18000d30a  mov     [rbp+var_18], 1
0x18000d311  lea     rax, ??_7Win32Error@Broker@@6B@; const Broker::Win32Error::`vftable'
0x18000d318  mov     [rbp+pExceptionObject], rax
0x18000d31c  mov     [rbp+var_10], 57h ; 'W'
0x18000d323  lea     rdx, _TI3?AUWin32Error@Broker@@; pThrowInfo
0x18000d32a  lea     rcx, [rbp+pExceptionObject]; pExceptionObject
0x18000d32e  call    _CxxThrowException_0
0x18000d334  mov     r8, [rdi]
0x18000d337  mov     rcx, [rdi+8]
0x18000d33b  sub     rcx, r8
0x18000d33e  sar     rcx, 4
0x18000d342  mov     edx, 0Ch
0x18000d347  cmp     rcx, rdx
0x18000d34a  jbe     short loc_18000D365
0x18000d34c  lea     rbx, [r8+0C0h]
0x18000d353  mov     rdx, [rdi+8]
0x18000d357  mov     rcx, rbx
0x18000d35a  call    ??$_Destroy_range@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@std@@@std@@YAXPEAV?$shared_ptr@VWnfNotification@BILayer@Broker@@@0@QEAV10@AEAV?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>(std::shared_ptr<Broker::BILayer::WnfNotification> *,std::shared_ptr<Broker::BILayer::WnfNotification> * const,std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>> &)
0x18000d35f  mov     [rdi+8], rbx
0x18000d363  jmp     short loc_18000D391
0x18000d365  jnb     short loc_18000D391
0x18000d367  mov     rax, [rdi+10h]
0x18000d36b  sub     rax, r8
0x18000d36e  sar     rax, 4
0x18000d372  cmp     rax, rdx
0x18000d375  jnb     short loc_18000D381
0x18000d377  mov     rcx, rdi
0x18000d37a  call    ??$_Resize_reallocate@U_Value_init_tag@std@@@?$vector@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@2@@std@@AEAAX_KAEBU_Value_init_tag@1@@Z; std::vector<std::shared_ptr<Broker::BILayer::WnfNotification>>::_Resize_reallocate<std::_Value_init_tag>(unsigned __int64,std::_Value_init_tag const &)
0x18000d37f  jmp     short loc_18000D391
0x18000d381  sub     rdx, rcx
0x18000d384  mov     rcx, [rdi+8]
0x18000d388  call    ??$_Uninitialized_value_construct_n@V?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@std@@@std@@YAPEAV?$shared_ptr@VWnfNotification@BILayer@Broker@@@0@PEAV10@_KAEAV?$allocator@V?$shared_ptr@VWnfNotification@BILayer@Broker@@@std@@@0@@Z; std::_Uninitialized_value_construct_n<std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>>>(std::shared_ptr<Broker::BILayer::WnfNotification> *,unsigned __int64,std::allocator<std::shared_ptr<Broker::BILayer::WnfNotification>> &)
0x18000d38d  mov     [rdi+8], rax
0x18000d391  mov     [rbp+arg_10], rdi
0x18000d395  lea     rdx, [rsi+24h]
0x18000d399  lea     r9, [rbp+arg_10]
0x18000d39d  lea     r8, [rbp+arg_8]
0x18000d3a1  lea     rcx, [rbp+var_40]
0x18000d3a5  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_86892d1650ab55be7a4c4976be615a04___
0x18000d3aa  mov     rcx, [rdi]
0x18000d3ad  add     rcx, 40h ; '@'
0x18000d3b1  mov     rdx, rax
0x18000d3b4  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000d3b9  mov     rcx, [rbp+var_38]; this
0x18000d3bd  test    rcx, rcx
0x18000d3c0  jz      short loc_18000D3C7
0x18000d3c2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d3c7  mov     [rbp+arg_10], rdi
0x18000d3cb  lea     rdx, [rsi+4]
0x18000d3cf  lea     r9, [rbp+arg_10]
0x18000d3d3  lea     r8, [rbp+arg_8]
0x18000d3d7  lea     rcx, [rbp+var_40]
0x18000d3db  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_00e69972730096af00ca8c298f9f4a9e___
0x18000d3e0  mov     rdx, rax
0x18000d3e3  mov     rcx, [rdi]
0x18000d3e6  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000d3eb  mov     rcx, [rbp+var_38]; this
0x18000d3ef  test    rcx, rcx
0x18000d3f2  jz      short loc_18000D3F9
0x18000d3f4  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d3f9  mov     [rbp+arg_10], rdi
0x18000d3fd  lea     rdx, [rsi+0Ch]
0x18000d401  lea     r9, [rbp+arg_10]
0x18000d405  lea     r8, [rbp+arg_8]
0x18000d409  lea     rcx, [rbp+var_40]
0x18000d40d  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_6bfd76c01525acb47ab5bcaa8ea8042e___
0x18000d412  mov     rcx, [rdi]
0x18000d415  add     rcx, 10h
0x18000d419  mov     rdx, rax
0x18000d41c  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000d421  mov     rcx, [rbp+var_38]; this
0x18000d425  test    rcx, rcx
0x18000d428  jz      short loc_18000D42F
0x18000d42a  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d42f  mov     [rbp+arg_10], rdi
0x18000d433  lea     rdx, [rsi+2Ch]
0x18000d437  lea     r9, [rbp+arg_10]
0x18000d43b  lea     r8, [rbp+arg_8]
0x18000d43f  lea     rcx, [rbp+var_40]
0x18000d443  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_ed25073690fe97cfe2ed26a37220a83f___
0x18000d448  mov     rcx, [rdi]
0x18000d44b  add     rcx, 50h ; 'P'
0x18000d44f  mov     rdx, rax
0x18000d452  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000d457  mov     rcx, [rbp+var_38]; this
0x18000d45b  test    rcx, rcx
0x18000d45e  jz      short loc_18000D465
0x18000d460  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d465  mov     [rbp+arg_10], rdi
0x18000d469  lea     rdx, [rsi+34h]
0x18000d46d  lea     r9, [rbp+arg_10]
0x18000d471  lea     r8, [rbp+arg_8]
0x18000d475  lea     rcx, [rbp+var_40]
0x18000d479  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_9d24c723111f0c973d4021d51a62e01e___
0x18000d47e  mov     rcx, [rdi]
0x18000d481  add     rcx, 60h ; '`'
0x18000d485  mov     rdx, rax
0x18000d488  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000d48d  mov     rcx, [rbp+var_38]; this
0x18000d491  test    rcx, rcx
0x18000d494  jz      short loc_18000D49B
0x18000d496  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d49b  mov     [rbp+arg_10], rdi
0x18000d49f  lea     rdx, [rsi+14h]
0x18000d4a3  lea     r9, [rbp+arg_10]
0x18000d4a7  lea     r8, [rbp+arg_8]
0x18000d4ab  lea     rcx, [rbp+var_40]
0x18000d4af  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_1c32acd994d3000f15957eeb4748b2f8___
0x18000d4b4  mov     rcx, [rdi]
0x18000d4b7  add     rcx, 20h ; ' '
0x18000d4bb  mov     rdx, rax
0x18000d4be  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000d4c3  mov     rcx, [rbp+var_38]; this
0x18000d4c7  test    rcx, rcx
0x18000d4ca  jz      short loc_18000D4D1
0x18000d4cc  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d4d1  mov     [rbp+arg_10], rdi
0x18000d4d5  lea     rdx, [rsi+1Ch]
0x18000d4d9  lea     r9, [rbp+arg_10]
0x18000d4dd  lea     r8, [rbp+arg_8]
0x18000d4e1  lea     rcx, [rbp+var_40]
0x18000d4e5  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_29d90547a1146d9dafb960207b00aa6e___
0x18000d4ea  mov     rcx, [rdi]
0x18000d4ed  add     rcx, 30h ; '0'
0x18000d4f1  mov     rdx, rax
0x18000d4f4  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000d4f9  mov     rcx, [rbp+var_38]; this
0x18000d4fd  test    rcx, rcx
0x18000d500  jz      short loc_18000D507
0x18000d502  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d507  mov     [rbp+arg_10], rdi
0x18000d50b  lea     rdx, [rsi+3Ch]
0x18000d50f  lea     r9, [rbp+arg_10]
0x18000d513  lea     r8, [rbp+arg_8]
0x18000d517  lea     rcx, [rbp+var_40]
0x18000d51b  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_67a15ee0df3935e87e13224f0fa153b5___
0x18000d520  mov     rcx, [rdi]
0x18000d523  add     rcx, 70h ; 'p'
0x18000d527  mov     rdx, rax
0x18000d52a  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000d52f  mov     rcx, [rbp+var_38]; this
0x18000d533  test    rcx, rcx
0x18000d536  jz      short loc_18000D53D
0x18000d538  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d53d  mov     [rbp+arg_10], rdi
0x18000d541  lea     rdx, [rsi+44h]
0x18000d545  lea     r9, [rbp+arg_10]
0x18000d549  lea     r8, [rbp+arg_8]
0x18000d54d  lea     rcx, [rbp+var_40]
0x18000d551  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_5d7b7f460b8d2e2d49dbd32e66ff681c___
0x18000d556  mov     rcx, [rdi]
0x18000d559  sub     rcx, 0FFFFFFFFFFFFFF80h
0x18000d55d  mov     rdx, rax
0x18000d560  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000d565  mov     rcx, [rbp+var_38]; this
0x18000d569  test    rcx, rcx
0x18000d56c  jz      short loc_18000D573
0x18000d56e  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d573  mov     [rbp+arg_10], rdi
0x18000d577  lea     rdx, [rsi+4Ch]
0x18000d57b  lea     r9, [rbp+arg_10]
0x18000d57f  lea     r8, [rbp+arg_8]
0x18000d583  lea     rcx, [rbp+var_40]
0x18000d587  call    std__make_shared_Broker__BILayer__WnfNotification__WNF_STATE_NAME_const___unsigned_long____lambda_a90fc444ce5b75418fe9bacc436dfeb6___
0x18000d58c  mov     rcx, [rdi]
0x18000d58f  add     rcx, 90h
0x18000d596  mov     rdx, rax
0x18000d599  call    ??4?$shared_ptr@VBrokerEvent@Broker@@@std@@QEAAAEAV01@$$QEAV01@@Z; std::shared_ptr<Broker::BrokerEvent>::operator=(std::shared_ptr<Broker::BrokerEvent> &&)
0x18000d59e  mov     rcx, [rbp+var_38]; this
0x18000d5a2  test    rcx, rcx
0x18000d5a5  jz      short loc_18000D5AD
0x18000d5a7  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000d5ac  nop
0x18000d5ad  mov     rcx, r14
0x18000d5b0  call    ?_Tidy@?$vector@UTCallback@NotificationChannel@BILayer@Broker@@V?$allocator@UTCallback@NotificationChannel@BILayer@Broker@@@std@@@std@@AEAAXXZ; std::vector<Broker::BILayer::NotificationChannel::TCallback>::_Tidy(void)
0x18000d5b5  mov     rax, rdi
0x18000d5b8  add     rsp, 60h
0x18000d5bc  pop     r14
0x18000d5be  pop     rdi
0x18000d5bf  pop     rsi
0x18000d5c0  pop     rbx
0x18000d5c1  pop     rbp
0x18000d5c2  retn
```
