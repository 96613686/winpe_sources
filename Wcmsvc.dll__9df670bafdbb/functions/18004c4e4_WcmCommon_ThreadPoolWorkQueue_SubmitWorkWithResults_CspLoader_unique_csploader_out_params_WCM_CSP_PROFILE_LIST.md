# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults<CspLoader::unique_csploader_out_params<_WCM_CSP_PROFILE_LIST>,`CspLoader::GetProfileList(_GUID *,std::shared_ptr<_WCM_CSP_PROFILE_LIST> &)'::`6'::_lambda_1_>(`CspLoader::GetProfileList(_GUID *,std::shared_ptr<_WCM_CSP_PROFILE_LIST> &)'::`6'::_lambda_1_ &&)

- ea: `0x18004c4e4`
- end: `0x18004c62f`
- name: `??$SubmitWorkWithResults@U?$unique_csploader_out_params@U_WCM_CSP_PROFILE_LIST@@@CspLoader@@V_lambda_1_@?5??GetProfileList@2@QEAAKPEAU_GUID@@AEAV?$shared_ptr@U_WCM_CSP_PROFILE_LIST@@@std@@@Z@@ThreadPoolWorkQueue@WcmCommon@@QEAA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@U_WCM_CSP_PROFILE_LIST@@@CspLoader@@@WcmCommon@@@std@@$$QEAV_lambda_1_@?5??GetProfileList@CspLoader@@QEAAKPEAU_GUID@@AEAV?$shared_ptr@U_WCM_CSP_PROFILE_LIST@@@3@@Z@@Z`
- size: `331`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18006df54`

## callees

- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x18004c4e4`
- `0x18006de30`
- `0x180071838`
- `0x180098260`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c518`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18004c518`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c5f3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c546`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18004c5f3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004c608`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18004c608`

## pseudocode

```c
_QWORD *__fastcall Z::SubmitWorkWithResults<CspLoader::unique_csploader_out_params<_WCM_CSP_PROFILE_LIST>,`CspLoader::GetProfileList'::`6'::_lambda_1_,AKPEAU_GUID * const,std::shared_ptr<_WCM_CSP_PROFILE_LIST> &>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  struct _RTL_CRITICAL_SECTION *v6; // rsi
  __int64 *ProfileList_CspLoader__QEAAKPEAU_GUID__AEAV__shared_ptr_U_WCM_CSP_PROFILE_LIST___0__Z__Z; // rax
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
    ProfileList_CspLoader__QEAAKPEAU_GUID__AEAV__shared_ptr_U_WCM_CSP_PROFILE_LIST___0__Z__Z = (__int64 *)___make_shared_V__ThreadPoolWaitableResult_U__unique_csploader_out_params_U_WCM_CSP_PROFILE_LIST___CspLoader___WcmCommon__V_lambda_1___5__GetProfileList_CspLoader__QEAAKPEAU_GUID__AEAV__shared_ptr_U_WCM_CSP_PROFILE_LIST___std___Z__std__YA_AV__shared_ptr_V__ThreadPoolWaitableResult_U__unique_csploader_out_params_U_WCM_CSP_PROFILE_LIST___CspLoader___WcmCommon___0___QEAV_lambda_1___5__GetProfileList_CspLoader__QEAAKPEAU_GUID__AEAV__shared_ptr_U_WCM_CSP_PROFILE_LIST___0__Z__Z(v12, a3);
    v8 = *ProfileList_CspLoader__QEAAKPEAU_GUID__AEAV__shared_ptr_U_WCM_CSP_PROFILE_LIST___0__Z__Z;
    v9 = ProfileList_CspLoader__QEAAKPEAU_GUID__AEAV__shared_ptr_U_WCM_CSP_PROFILE_LIST___0__Z__Z[1];
    *ProfileList_CspLoader__QEAAKPEAU_GUID__AEAV__shared_ptr_U_WCM_CSP_PROFILE_LIST___0__Z__Z = 0;
    ProfileList_CspLoader__QEAAKPEAU_GUID__AEAV__shared_ptr_U_WCM_CSP_PROFILE_LIST___0__Z__Z[1] = 0;
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
0x18004c4e4  mov     [rsp-8+arg_18], rbx
0x18004c4e9  push    rbp
0x18004c4ea  push    rsi
0x18004c4eb  push    rdi
0x18004c4ec  push    r14
0x18004c4ee  push    r15
0x18004c4f0  lea     rbp, [rsp-37h]
0x18004c4f5  sub     rsp, 0A0h
0x18004c4fc  mov     r14, r8
0x18004c4ff  mov     rbx, rdx
0x18004c502  mov     rdi, rcx
0x18004c505  mov     [rbp+57h+var_78], rdx
0x18004c509  xorps   xmm1, xmm1
0x18004c50c  movdqa  [rbp+57h+var_A0], xmm1
0x18004c511  lea     rsi, [rcx+8]
0x18004c515  mov     rcx, rsi; lpCriticalSection
0x18004c518  call    cs:__imp_EnterCriticalSection
0x18004c51e  mov     [rbp+57h+var_78], rsi
0x18004c522  cmp     byte ptr [rdi+110h], 0
0x18004c529  jz      short loc_18004C551
0x18004c52b  mov     qword ptr [rbx], 0
0x18004c532  mov     qword ptr [rbx+8], 0
0x18004c53a  test    rsi, rsi
0x18004c53d  jz      loc_18004C615
0x18004c543  mov     rcx, rsi; lpCriticalSection
0x18004c546  call    cs:__imp_LeaveCriticalSection
0x18004c54c  jmp     loc_18004C615
0x18004c551  mov     rdx, r14
0x18004c554  lea     rcx, [rbp+57h+var_90]
0x18004c558  call    ??$make_shared@V?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@U_WCM_CSP_PROFILE_LIST@@@CspLoader@@@WcmCommon@@V_lambda_1_@?5??GetProfileList@CspLoader@@QEAAKPEAU_GUID@@AEAV?$shared_ptr@U_WCM_CSP_PROFILE_LIST@@@std@@@Z@@std@@YA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@U_WCM_CSP_PROFILE_LIST@@@CspLoader@@@WcmCommon@@@0@$$QEAV_lambda_1_@?5??GetProfileList@CspLoader@@QEAAKPEAU_GUID@@AEAV?$shared_ptr@U_WCM_CSP_PROFILE_LIST@@@0@@Z@@Z; std::make_shared<WcmCommon::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<_WCM_CSP_PROFILE_LIST>>,`CspLoader::GetProfileList(_GUID *,std::shared_ptr<_WCM_CSP_PROFILE_LIST> &)'::`6'::_lambda_1_>(`CspLoader::GetProfileList(_GUID *,std::shared_ptr<_WCM_CSP_PROFILE_LIST> &)'::`6'::_lambda_1_ &&)
0x18004c55d  mov     r15, [rax]
0x18004c560  mov     r14, [rax+8]
0x18004c564  mov     qword ptr [rax], 0
0x18004c56b  mov     qword ptr [rax+8], 0
0x18004c573  mov     qword ptr [rbp+57h+var_A0], r15
0x18004c577  mov     qword ptr [rbp+57h+var_A0+8], r14
0x18004c57b  mov     rcx, [rbp+57h+var_90+8]; this
0x18004c57f  test    rcx, rcx
0x18004c582  jz      short loc_18004C589
0x18004c584  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c589  cmp     dword ptr [rdi], 1
0x18004c58c  jnz     short loc_18004C5C2
0x18004c58e  lea     rcx, [rdi+0C0h]
0x18004c595  test    r14, r14
0x18004c598  jz      short loc_18004C59F
0x18004c59a  lock inc dword ptr [r14+8]
0x18004c59f  movaps  xmm0, [rbp+57h+var_A0]
0x18004c5a3  movdqa  xmmword ptr [rbp+57h+var_90], xmm0
0x18004c5a8  lea     rdx, [rbp+57h+var_90]
0x18004c5ac  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x18004c5b1  nop
0x18004c5b2  mov     rcx, [rbp+57h+var_90+8]; this
0x18004c5b6  test    rcx, rcx
0x18004c5b9  jz      short loc_18004C5EB
0x18004c5bb  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x18004c5c0  jmp     short loc_18004C5EB
0x18004c5c2  lea     rdx, [rbp+57h+var_A0]
0x18004c5c6  lea     rcx, [rbp+57h+var_70]
0x18004c5ca  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x18004c5cf  nop
0x18004c5d0  lea     rdx, [rbp+57h+var_70]
0x18004c5d4  lea     rcx, [rdi+0E8h]
0x18004c5db  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x18004c5e0  nop
0x18004c5e1  lea     rcx, [rbp+57h+var_70]
0x18004c5e5  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x18004c5ea  nop
0x18004c5eb  test    rsi, rsi
0x18004c5ee  jz      short loc_18004C5F9
0x18004c5f0  mov     rcx, rsi; lpCriticalSection
0x18004c5f3  call    cs:__imp_LeaveCriticalSection
0x18004c5f9  lock inc qword ptr [rdi+88h]
0x18004c601  mov     rcx, [rdi+80h]; pwk
0x18004c608  call    cs:__imp_SubmitThreadpoolWork
0x18004c60e  mov     [rbx], r15
0x18004c611  mov     [rbx+8], r14
0x18004c615  mov     rax, rbx
0x18004c618  mov     rbx, [rsp+0C0h+arg_18]
0x18004c620  add     rsp, 0A0h
0x18004c627  pop     r15
0x18004c629  pop     r14
0x18004c62b  pop     rdi
0x18004c62c  pop     rsi
0x18004c62d  pop     rbp
0x18004c62e  retn
```
