# WcmCommon::ThreadPoolWorkQueue::SubmitWorkWithResults<CspLoader::unique_csploader_out_params<_WCM_PROFILE_INFO_LIST>,`CspLoader::GetProfileListByPurpose(_GUID const *,_GUID const *,_WCM_PROFILE_INFO_LIST * *)'::`6'::_lambda_1_>(`CspLoader::GetProfileListByPurpose(_GUID const *,_GUID const *,_WCM_PROFILE_INFO_LIST * *)'::`6'::_lambda_1_ &&)

- ea: `0x1800b6888`
- end: `0x1800b69e0`
- name: `??$SubmitWorkWithResults@U?$unique_csploader_out_params@U_WCM_PROFILE_INFO_LIST@@@CspLoader@@V_lambda_1_@?5??GetProfileListByPurpose@2@QEAAKPEBU_GUID@@0PEAPEAU_WCM_PROFILE_INFO_LIST@@@Z@@ThreadPoolWorkQueue@WcmCommon@@QEAA?AV?$shared_ptr@V?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@U_WCM_PROFILE_INFO_LIST@@@CspLoader@@@WcmCommon@@@std@@$$QEAV_lambda_1_@?5??GetProfileListByPurpose@CspLoader@@QEAAKPEBU_GUID@@0PEAPEAU_WCM_PROFILE_INFO_LIST@@@Z@@Z`
- size: `344`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x1800b78bc`

## callees

- `0x180008394`
- `0x180010080`
- `0x180010560`
- `0x18001d53c`
- `0x180027630`
- `0x18006de30`
- `0x18008534c`
- `0x180098260`
- `0x1800b6710`
- `0x1800b6888`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b68f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b69a4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b68f0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800b69a4`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800b69b9`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x1800b69b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall Z::SubmitWorkWithResults<CspLoader::unique_csploader_out_params<_WCM_PROFILE_INFO_LIST>,`CspLoader::GetProfileListByPurpose'::`6'::_lambda_1_,AKPEBU_GUID * const,CspLoader::unique_csploader_out_params<_WCM_PROFILE_INFO_LIST>,_WCM_PROFILE_INFO_LIST * *>(
        __int64 a1,
        _QWORD *a2,
        __int64 a3)
{
  _DWORD *v6; // rsi
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-49h] BYREF
  __int128 v9; // [rsp+28h] [rbp-41h] BYREF
  _DWORD *v10; // [rsp+40h] [rbp-29h] BYREF
  std::_Ref_count_base *v11; // [rsp+48h] [rbp-21h]
  _BYTE v12[112]; // [rsp+50h] [rbp-19h] BYREF

  v9 = 0;
  lpCriticalSection = 0;
  wil::EnterCriticalSection(&lpCriticalSection, a1 + 8);
  if ( *(_BYTE *)(a1 + 272) )
  {
    *a2 = 0;
    a2[1] = 0;
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
  }
  else
  {
    v6 = operator new(0x88u);
    v10 = v6;
    *(_OWORD *)v6 = 0;
    v6[2] = 1;
    v6[3] = 1;
    *(_QWORD *)v6 = &std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<_WCM_CSP_PROFILE_LIST>>>::`vftable';
    ____0V_lambda_1___5__GetProfileListByPurpose_CspLoader__QEAAKPEBU_GUID__0PEAPEAU_WCM_PROFILE_INFO_LIST___Z____ThreadPoolWaitableResult_U__unique_csploader_out_params_U_WCM_PROFILE_INFO_LIST___CspLoader___WcmCommon__QEAA___QEAV_lambda_1___5__GetProfileListByPurpose_CspLoader__QEAAKPEBU_GUID__0PEAPEAU_WCM_PROFILE_INFO_LIST___Z__Z(
      v6 + 4,
      a3);
    *(_QWORD *)&v9 = v6 + 4;
    *((_QWORD *)&v9 + 1) = v6;
    if ( *(_DWORD *)a1 == 1 )
    {
      std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(&v10);
      std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(a1 + 192, &v10);
      if ( v11 )
        std::_Ref_count_base::_Decref(v11);
    }
    else
    {
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(
        v12,
        &v9);
      std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(
        a1 + 232,
        v12);
      std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(v12);
    }
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    _InterlockedIncrement64((volatile signed __int64 *)(a1 + 136));
    SubmitThreadpoolWork(*(PTP_WORK *)(a1 + 128));
    *a2 = v6 + 4;
    a2[1] = v6;
  }
  return a2;
}

```

## disassembly

```asm
0x1800b6888  mov     [rsp-8+arg_10], rbx
0x1800b688d  push    rbp
0x1800b688e  push    rsi
0x1800b688f  push    rdi
0x1800b6890  push    r14
0x1800b6892  push    r15
0x1800b6894  lea     rbp, [rsp-37h]
0x1800b6899  sub     rsp, 0A0h
0x1800b68a0  mov     r15, r8
0x1800b68a3  mov     rbx, rdx
0x1800b68a6  mov     rdi, rcx
0x1800b68a9  mov     [rbp+57h+lpCriticalSection], rdx
0x1800b68ad  xorps   xmm1, xmm1
0x1800b68b0  movdqu  [rbp+57h+var_98], xmm1
0x1800b68b5  mov     [rbp+57h+lpCriticalSection], 0
0x1800b68bd  lea     rdx, [rcx+8]
0x1800b68c1  lea     rcx, [rbp+57h+lpCriticalSection]
0x1800b68c5  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x1800b68ca  nop
0x1800b68cb  cmp     byte ptr [rdi+110h], 0
0x1800b68d2  jz      short loc_1800B68FB
0x1800b68d4  mov     qword ptr [rbx], 0
0x1800b68db  mov     qword ptr [rbx+8], 0
0x1800b68e3  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800b68e7  test    rcx, rcx
0x1800b68ea  jz      loc_1800B69C6
0x1800b68f0  call    cs:__imp_LeaveCriticalSection
0x1800b68f6  jmp     loc_1800B69C6
0x1800b68fb  mov     ecx, 88h; Size
0x1800b6900  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b6905  mov     rsi, rax
0x1800b6908  mov     [rbp+57h+var_80], rax
0x1800b690c  xorps   xmm0, xmm0
0x1800b690f  movups  xmmword ptr [rax], xmm0
0x1800b6912  mov     dword ptr [rax+8], 1
0x1800b6919  mov     dword ptr [rax+0Ch], 1
0x1800b6920  lea     rax, ??_7?$_Ref_count_obj2@V?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@U_WCM_CSP_PROFILE_LIST@@@CspLoader@@@WcmCommon@@@std@@6B@; const std::_Ref_count_obj2<WcmCommon::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<_WCM_CSP_PROFILE_LIST>>>::`vftable'
0x1800b6927  mov     [rsi], rax
0x1800b692a  lea     r14, [rsi+10h]
0x1800b692e  mov     rdx, r15
0x1800b6931  mov     rcx, r14
0x1800b6934  call    ??$?0V_lambda_1_@?5??GetProfileListByPurpose@CspLoader@@QEAAKPEBU_GUID@@0PEAPEAU_WCM_PROFILE_INFO_LIST@@@Z@@?$ThreadPoolWaitableResult@U?$unique_csploader_out_params@U_WCM_PROFILE_INFO_LIST@@@CspLoader@@@WcmCommon@@QEAA@$$QEAV_lambda_1_@?5??GetProfileListByPurpose@CspLoader@@QEAAKPEBU_GUID@@0PEAPEAU_WCM_PROFILE_INFO_LIST@@@Z@@Z; WcmCommon::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<_WCM_PROFILE_INFO_LIST>>::ThreadPoolWaitableResult<CspLoader::unique_csploader_out_params<_WCM_PROFILE_INFO_LIST>>(`CspLoader::GetProfileListByPurpose(_GUID const *,_GUID const *,_WCM_PROFILE_INFO_LIST * *)'::`6'::_lambda_1_ &&)
0x1800b6939  nop
0x1800b693a  mov     qword ptr [rbp+57h+var_98], r14
0x1800b693e  mov     qword ptr [rbp+57h+var_98+8], rsi
0x1800b6942  lea     rdx, [rbp+57h+var_98]
0x1800b6946  cmp     dword ptr [rdi], 1
0x1800b6949  jnz     short loc_1800B6976
0x1800b694b  lea     rcx, [rbp+57h+var_80]
0x1800b694f  call    ??$?0V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@$0A@@?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@QEAA@AEBV?$shared_ptr@V?$ThreadPoolWaitableResult@V?$tuple@JV?$unique_ptr@U_WCM_ONDEMAND_STATE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?WcmFree@@YAX0@Z@wil@@@std@@@std@@@WcmCommon@@@1@@Z; std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<std::tuple<long,std::unique_ptr<_WCM_ONDEMAND_STATE_INFO,wil::function_deleter<void (*)(void *),&WcmFree(void *)>>>>> const &)
0x1800b6954  nop
0x1800b6955  lea     rdx, [rbp+57h+var_80]
0x1800b6959  lea     rcx, [rdi+0C0h]
0x1800b6960  call    ?push_back@?$deque@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@V?$allocator@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@std@@@2@@std@@QEAAX$$QEAV?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@Z; std::deque<std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::push_back(std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult> &&)
0x1800b6965  nop
0x1800b6966  mov     rcx, [rbp+57h+var_78]; this
0x1800b696a  test    rcx, rcx
0x1800b696d  jz      short loc_1800B699B
0x1800b696f  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1800b6974  jmp     short loc_1800B699B
0x1800b6976  lea     rcx, [rbp+57h+var_70]
0x1800b697a  call    ??$?0AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@std@@$0A@$0A@@?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@AEAV?$shared_ptr@V?$ThreadPoolWaitableResult@_N@WcmCommon@@@1@@Z; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(std::shared_ptr<WcmCommon::ThreadPoolWaitableResult<bool>> &)
0x1800b697f  nop
0x1800b6980  lea     rdx, [rbp+57h+var_70]
0x1800b6984  lea     rcx, [rdi+0E8h]
0x1800b698b  call    ??$_Emplace_back_internal@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@?$deque@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@V?$allocator@V?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@@2@@std@@AEAAX$$QEAV?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@1@@Z; std::deque<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>::_Emplace_back_internal<std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>>(std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>> &&)
0x1800b6990  nop
0x1800b6991  lea     rcx, [rbp+57h+var_70]
0x1800b6995  call    ??1?$variant@V?$function@$$A6AXXZ@std@@V?$shared_ptr@VBaseThreadPoolWaitableResult@WcmCommon@@@2@@std@@QEAA@XZ; std::variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>::~variant<std::function<void (void)>,std::shared_ptr<WcmCommon::BaseThreadPoolWaitableResult>>(void)
0x1800b699a  nop
0x1800b699b  mov     rcx, [rbp+57h+lpCriticalSection]; lpCriticalSection
0x1800b699f  test    rcx, rcx
0x1800b69a2  jz      short loc_1800B69AA
0x1800b69a4  call    cs:__imp_LeaveCriticalSection
0x1800b69aa  lock inc qword ptr [rdi+88h]
0x1800b69b2  mov     rcx, [rdi+80h]; pwk
0x1800b69b9  call    cs:__imp_SubmitThreadpoolWork
0x1800b69bf  mov     [rbx], r14
0x1800b69c2  mov     [rbx+8], rsi
0x1800b69c6  mov     rax, rbx
0x1800b69c9  mov     rbx, [rsp+0C0h+arg_10]
0x1800b69d1  add     rsp, 0A0h
0x1800b69d8  pop     r15
0x1800b69da  pop     r14
0x1800b69dc  pop     rdi
0x1800b69dd  pop     rsi
0x1800b69de  pop     rbp
0x1800b69df  retn
```
