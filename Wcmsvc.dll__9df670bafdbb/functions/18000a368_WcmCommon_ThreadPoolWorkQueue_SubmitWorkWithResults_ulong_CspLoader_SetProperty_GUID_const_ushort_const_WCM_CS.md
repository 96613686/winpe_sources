# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults<ulong,`CspLoader::SetProperty(_GUID const *,ushort const *,WCM_CSP_PROPERTY,ulong,uchar const *,ulong,bool)'::`6'::_lambda_1_>(`CspLoader::SetProperty(_GUID const *,ushort const *,WCM_CSP_PROPERTY,ulong,uchar const *,ulong,bool)'::`6'::_lambda_1_ &&)

- ea: `0x18000a368`
- end: `0x18000a4b3`
- name: `??$SubmitWorkWithResults@KV_lambda_1_@?5??SetProperty@CspLoader@@QEAAKPEBU_GUID@@PEBGW4WCM_CSP_PROPERTY@@KPEBEK_N@Z@@ThreadPoolWorkQueue@WcmCommon@@QEAA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@K@WcmCommon@@@std@@$$QEAV_lambda_1_@?5??SetProperty@CspLoader@@QEAAKPEBU_GUID@@PEBGW4WCM_CSP_PROPERTY@@KPEBEK_N@Z@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000a028`

## callees

- `0x180009340`
- `0x18000a368`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x18006de30`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a39c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a39c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a3ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a477`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a3ca`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a477`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000a48c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000a48c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Z::SubmitWorkWithResults<unsigned long,`CspLoader::SetProperty'::`6'::_lambda_1_,AKPEBU_GUID * const,unsigned short const *,enum WCM_CSP_PROPERTY,unsigned long,unsigned char const *,unsigned long,bool>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int64 *shared_V__ThreadPoolWaitableResult_K_WcmCommon__V_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__std__YA_AV__shared_ptr_V__ThreadPoolWaitableResult_K_WcmCommon___0___QEAV_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__Z; // rax
  __int64 v8; // r15
  __int64 v9; // r14
  __int128 v11; // [rsp+20h] [rbp-49h] BYREF
  std::_Ref_count_base *v12[2]; // [rsp+30h] [rbp-39h] BYREF
  struct _RTL_CRITICAL_SECTION *v13; // [rsp+48h] [rbp-21h]
  _BYTE v14[112]; // [rsp+50h] [rbp-19h] BYREF

  v11 = 0;
  v6 = (struct _RTL_CRITICAL_SECTION *)(a1 + 8);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  v13 = v6;
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( v6 )
      LeaveCriticalSection(v6);
  }
  else
  {
    shared_V__ThreadPoolWaitableResult_K_WcmCommon__V_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__std__YA_AV__shared_ptr_V__ThreadPoolWaitableResult_K_WcmCommon___0___QEAV_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__Z = (__int64 *)___make_shared_V__ThreadPoolWaitableResult_K_WcmCommon__V_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__std__YA_AV__shared_ptr_V__ThreadPoolWaitableResult_K_WcmCommon___0___QEAV_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__Z(v12, a3);
    v8 = *shared_V__ThreadPoolWaitableResult_K_WcmCommon__V_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__std__YA_AV__shared_ptr_V__ThreadPoolWaitableResult_K_WcmCommon___0___QEAV_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__Z;
    v9 = shared_V__ThreadPoolWaitableResult_K_WcmCommon__V_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__std__YA_AV__shared_ptr_V__ThreadPoolWaitableResult_K_WcmCommon___0___QEAV_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__Z[1];
    *shared_V__ThreadPoolWaitableResult_K_WcmCommon__V_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__std__YA_AV__shared_ptr_V__ThreadPoolWaitableResult_K_WcmCommon___0___QEAV_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__Z = 0;
    shared_V__ThreadPoolWaitableResult_K_WcmCommon__V_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__std__YA_AV__shared_ptr_V__ThreadPoolWaitableResult_K_WcmCommon___0___QEAV_lambda_1___5__SetProperty_CspLoader__QEAAKPEBU_GUID__PEBGW4WCM_CSP_PROPERTY__KPEBEK_N_Z__Z[1] = 0;
    *(_QWORD *)&v11 = v8;
    *((_QWORD *)&v11 + 1) = v9;
    if ( v12[1] )
      std::_Ref_count_base::_Decref(v12[1]);
    if ( *(_DWORD *)a1 == 1 )
    {
      if ( v9 )
        _InterlockedIncrement((volatile signed __int32 *)(v9 + 8));
      *(_OWORD *)v12 = v11;
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(a1 + 192, v12);
      if ( v12[1] )
        std::_Ref_count_base::_Decref(v12[1]);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
        v14,
        &v11);
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(
        a1 + 232,
        v14);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v14);
    }
    if ( v6 )
      LeaveCriticalSection(v6);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *a2 = v8;
    a2[1] = v9;
  }
  return a2;
}

```

## disassembly

```asm
0x18000a368  mov     [rsp-8+arg_18], rbx
0x18000a36d  push    rbp
0x18000a36e  push    rsi
0x18000a36f  push    rdi
0x18000a370  push    r14
0x18000a372  push    r15
0x18000a374  lea     rbp, [rsp-37h]
0x18000a379  sub     rsp, 0A0h
0x18000a380  mov     r14, r8
0x18000a383  mov     rbx, rdx
0x18000a386  mov     rdi, rcx
0x18000a389  mov     [rbp+57h+var_78], rdx
0x18000a38d  xorps   xmm1, xmm1
0x18000a390  movdqa  [rbp+57h+var_A0], xmm1
0x18000a395  lea     rsi, [rcx+8]
0x18000a399  mov     rcx, rsi; lpCriticalSection
0x18000a39c  call    cs:__imp_EnterCriticalSection
0x18000a3a2  mov     [rbp+57h+var_78], rsi
0x18000a3a6  cmp     byte ptr [rdi+110h], 0
0x18000a3ad  jz      short loc_18000A3D5
0x18000a3af  mov     qword ptr [rbx], 0
0x18000a3b6  mov     qword ptr [rbx+8], 0
0x18000a3be  test    rsi, rsi
0x18000a3c1  jz      loc_18000A499
0x18000a3c7  mov     rcx, rsi; lpCriticalSection
0x18000a3ca  call    cs:__imp_LeaveCriticalSection
0x18000a3d0  jmp     loc_18000A499
0x18000a3d5  mov     rdx, r14
0x18000a3d8  lea     rcx, [rbp+57h+var_90]
0x18000a3dc  call    ??$make_shared@V?$ThreadPoolWaitableResult@K@WcmCommon@@V_lambda_1_@?5??SetProperty@CspLoader@@QEAAKPEBU_GUID@@PEBGW4WCM_CSP_PROPERTY@@KPEBEK_N@Z@@std@@YA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@K@WcmCommon@@@0@$$QEAV_lambda_1_@?5??SetProperty@CspLoader@@QEAAKPEBU_GUID@@PEBGW4WCM_CSP_PROPERTY@@KPEBEK_N@Z@@Z; std::make_shared<WcmCommon::ThreadPoolWaitableResult<ulong>,`CspLoader::SetProperty(_GUID const *,ushort const *,WCM_CSP_PROPERTY,ulong,uchar const *,ulong,bool)'::`6'::_lambda_1_>(`CspLoader::SetProperty(_GUID const *,ushort const *,WCM_CSP_PROPERTY,ulong,uchar const *,ulong,bool)'::`6'::_lambda_1_ &&)
0x18000a3e1  mov     r15, [rax]
0x18000a3e4  mov     r14, [rax+8]
0x18000a3e8  mov     qword ptr [rax], 0
0x18000a3ef  mov     qword ptr [rax+8], 0
0x18000a3f7  mov     qword ptr [rbp+57h+var_A0], r15
0x18000a3fb  mov     qword ptr [rbp+57h+var_A0+8], r14
0x18000a3ff  mov     rcx, [rbp+57h+var_90+8]; this
0x18000a403  test    rcx, rcx
0x18000a406  jz      short loc_18000A40D
0x18000a408  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a40d  cmp     dword ptr [rdi], 1
0x18000a410  jnz     short loc_18000A446
0x18000a412  lea     rcx, [rdi+0C0h]
0x18000a419  test    r14, r14
0x18000a41c  jz      short loc_18000A423
0x18000a41e  lock inc dword ptr [r14+8]
0x18000a423  movaps  xmm0, [rbp+57h+var_A0]
0x18000a427  movdqa  xmmword ptr [rbp+57h+var_90], xmm0
0x18000a42c  lea     rdx, [rbp+57h+var_90]
0x18000a430  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18000a435  nop
0x18000a436  mov     rcx, [rbp+57h+var_90+8]; this
0x18000a43a  test    rcx, rcx
0x18000a43d  jz      short loc_18000A46F
0x18000a43f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18000a444  jmp     short loc_18000A46F
0x18000a446  lea     rdx, [rbp+57h+var_A0]
0x18000a44a  lea     rcx, [rbp+57h+var_70]
0x18000a44e  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x18000a453  nop
0x18000a454  lea     rdx, [rbp+57h+var_70]
0x18000a458  lea     rcx, [rdi+0E8h]
0x18000a45f  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18000a464  nop
0x18000a465  lea     rcx, [rbp+57h+var_70]
0x18000a469  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x18000a46e  nop
0x18000a46f  test    rsi, rsi
0x18000a472  jz      short loc_18000A47D
0x18000a474  mov     rcx, rsi; lpCriticalSection
0x18000a477  call    cs:__imp_LeaveCriticalSection
0x18000a47d  lock inc qword ptr [rdi+88h]
0x18000a485  mov     rcx, [rdi+80h]; pwk
0x18000a48c  call    cs:__imp_SubmitThreadpoolWork
0x18000a492  mov     [rbx], r15
0x18000a495  mov     [rbx+8], r14
0x18000a499  mov     rax, rbx
0x18000a49c  mov     rbx, [rsp+0C0h+arg_18]
0x18000a4a4  add     rsp, 0A0h
0x18000a4ab  pop     r15
0x18000a4ad  pop     r14
0x18000a4af  pop     rdi
0x18000a4b0  pop     rsi
0x18000a4b1  pop     rbp
0x18000a4b2  retn
```
