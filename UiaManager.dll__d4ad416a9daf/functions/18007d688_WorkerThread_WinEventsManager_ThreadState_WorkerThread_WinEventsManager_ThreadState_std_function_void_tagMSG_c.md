# WorkerThread<WinEventsManager::ThreadState>::WorkerThread<WinEventsManager::ThreadState>(std::function<void (tagMSG const &,WinEventsManager::ThreadState &)>)

- ea: `0x18007d688`
- end: `0x18007d7e5`
- name: `??0?$WorkerThread@UThreadState@WinEventsManager@@@@QEAA@V?$function@$$A6AXAEBUtagMSG@@AEAUThreadState@WinEventsManager@@@Z@std@@@Z`
- size: `349`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180036350`

## callees

- `0x180004ecc`
- `0x180007250`
- `0x1800125c0`
- `0x18001607c`
- `0x180016250`
- `0x18002cd38`
- `0x180043a8c`
- `0x18007d688`
- `0x180091010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18007d7de`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18007d7de`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18007d78d`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18007d78d`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall WorkerThread<WinEventsManager::ThreadState>::WorkerThread<WinEventsManager::ThreadState>(
        __int64 a1,
        __int64 a2)
{
  _QWORD *v4; // rax
  __int64 v5; // rcx
  _QWORD *v6; // rax
  __int64 v8; // [rsp+30h] [rbp-10h] BYREF
  int v9; // [rsp+38h] [rbp-8h] BYREF
  _QWORD *v10; // [rsp+80h] [rbp+40h] BYREF
  __int64 v11; // [rsp+88h] [rbp+48h]

  *(_OWORD *)a1 = 0;
  LODWORD(v10) = 1;
  ____0W4EventOptions_wil____V___unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    (_QWORD *)(a1 + 16),
    (int *)&v10);
  v11 = a1 + 24;
  LODWORD(v10) = 0;
  ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    (_QWORD *)(a1 + 24),
    (int *)&v10);
  *(_QWORD *)(a1 + 40) = 2;
  *(_OWORD *)(a1 + 64) = 0;
  *(_OWORD *)(a1 + 80) = 0;
  *(_OWORD *)(a1 + 96) = 0;
  *(_QWORD *)(a1 + 48) = 0;
  *(_QWORD *)(a1 + 56) = 0;
  *(_DWORD *)(a1 + 112) = -1;
  *(_DWORD *)(a1 + 116) = 0;
  *(_QWORD *)(a1 + 120) = 0;
  *(_QWORD *)(a1 + 128) = 0;
  v4 = operator new(0x50u);
  *v4 = v4;
  v4[1] = v4;
  *(_QWORD *)(a1 + 120) = v4;
  *(_QWORD *)(a1 + 192) = 0;
  v5 = *(_QWORD *)(a2 + 56);
  if ( v5 )
  {
    if ( v5 == a2 )
    {
      *(_QWORD *)(a1 + 192) = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v5 + 8LL))(v5, a1 + 136);
      std::_Func_class<void,GetCompositionInputSinkViewInstanceIdFromPointRequestPayload,RequestCompleter<HrResponse<GetCompositionInputSinkViewInstanceIdFromPointService::ResponsePayload>>>::_Tidy(a2);
    }
    else
    {
      *(_QWORD *)(a1 + 192) = v5;
      *(_QWORD *)(a2 + 56) = 0;
    }
  }
  v6 = operator new(8u);
  *v6 = a1;
  v10 = v6;
  v8 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke<std::tuple<_lambda_d869f02c39f35682526e1a41b8686bac_>,0>,
         v6,
         0,
         &v9);
  if ( !v8 )
  {
    v9 = 0;
    std::_Throw_Cpp_error(6);
    JUMPOUT(0x18007D7E4LL);
  }
  v10 = 0;
  std::unique_ptr<std::tuple<_lambda_8a8ac1eece88354f66237a83e3edaffe_>>::~unique_ptr<std::tuple<_lambda_8a8ac1eece88354f66237a83e3edaffe_>>(&v10);
  std::thread::operator=(a1, &v8);
  std::thread::~thread((std::thread *)&v8);
  std::_Func_class<void,GetCompositionInputSinkViewInstanceIdFromPointRequestPayload,RequestCompleter<HrResponse<GetCompositionInputSinkViewInstanceIdFromPointService::ResponsePayload>>>::_Tidy(a2);
  return a1;
}

```

## disassembly

```asm
0x18007d688  mov     [rsp-28h+arg_8], rdx
0x18007d68d  mov     [rsp-28h+arg_0], rcx
0x18007d692  push    rbp
0x18007d693  push    rbx
0x18007d694  push    rsi
0x18007d695  push    rdi
0x18007d696  push    r14
0x18007d698  mov     rbp, rsp
0x18007d69b  sub     rsp, 40h
0x18007d69f  mov     rdi, rdx
0x18007d6a2  mov     rsi, rcx
0x18007d6a5  xor     r14d, r14d
0x18007d6a8  xorps   xmm0, xmm0
0x18007d6ab  movups  xmmword ptr [rcx], xmm0
0x18007d6ae  mov     dword ptr [rbp+arg_10], 1
0x18007d6b5  add     rcx, 10h
0x18007d6b9  lea     rdx, [rbp+arg_10]
0x18007d6bd  call    ??$?0W4EventOptions@wil@@$$V@?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18007d6c2  nop
0x18007d6c3  lea     rbx, [rsi+18h]
0x18007d6c7  mov     [rbp+arg_18], rbx
0x18007d6cb  mov     dword ptr [rbp+arg_10], r14d
0x18007d6cf  lea     rdx, [rbp+arg_10]
0x18007d6d3  mov     rcx, rbx
0x18007d6d6  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x18007d6db  nop
0x18007d6dc  mov     qword ptr [rbx+10h], 2
0x18007d6e4  xorps   xmm0, xmm0
0x18007d6e7  movups  xmmword ptr [rbx+28h], xmm0
0x18007d6eb  movups  xmmword ptr [rbx+38h], xmm0
0x18007d6ef  movups  xmmword ptr [rbx+48h], xmm0
0x18007d6f3  mov     [rbx+18h], r14
0x18007d6f7  mov     [rbx+20h], r14
0x18007d6fb  mov     dword ptr [rbx+58h], 0FFFFFFFFh
0x18007d702  mov     [rbx+5Ch], r14d
0x18007d706  mov     [rbx+60h], r14
0x18007d70a  mov     [rbx+68h], r14
0x18007d70e  lea     ecx, [r14+50h]; Size
0x18007d712  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007d717  mov     [rax], rax
0x18007d71a  mov     [rax+8], rax
0x18007d71e  mov     [rbx+60h], rax
0x18007d722  lea     rbx, [rsi+88h]
0x18007d729  mov     [rbx+38h], r14
0x18007d72d  mov     rcx, [rdi+38h]
0x18007d731  test    rcx, rcx
0x18007d734  jz      short loc_18007D760
0x18007d736  cmp     rcx, rdi
0x18007d739  jnz     short loc_18007D758
0x18007d73b  mov     rax, [rcx]
0x18007d73e  mov     rdx, rbx
0x18007d741  mov     rax, [rax+8]
0x18007d745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007d74a  mov     [rbx+38h], rax
0x18007d74e  mov     rcx, rdi
0x18007d751  call    ?_Tidy@?$_Func_class@XUGetCompositionInputSinkViewInstanceIdFromPointRequestPayload@@V?$RequestCompleter@U?$HrResponse@UResponsePayload@GetCompositionInputSinkViewInstanceIdFromPointService@@@@@@@std@@IEAAXXZ; std::_Func_class<void,GetCompositionInputSinkViewInstanceIdFromPointRequestPayload,RequestCompleter<HrResponse<GetCompositionInputSinkViewInstanceIdFromPointService::ResponsePayload>>>::_Tidy(void)
0x18007d756  jmp     short loc_18007D760
0x18007d758  mov     [rbx+38h], rcx
0x18007d75c  mov     [rdi+38h], r14
0x18007d760  mov     ecx, 8; Size
0x18007d765  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18007d76a  mov     [rax], rsi
0x18007d76d  mov     [rbp+arg_10], rax
0x18007d771  lea     rcx, [rbp+var_8]
0x18007d775  mov     [rsp+40h+var_18], rcx
0x18007d77a  mov     [rsp+40h+var_20], r14d
0x18007d77f  mov     r9, rax
0x18007d782  lea     r8, ??$_Invoke@V?$tuple@V_lambda_d869f02c39f35682526e1a41b8686bac_@@@std@@$0A@@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<_lambda_d869f02c39f35682526e1a41b8686bac_>,0>(void *)
0x18007d789  xor     edx, edx
0x18007d78b  xor     ecx, ecx
0x18007d78d  call    cs:__imp__o__beginthreadex
0x18007d793  mov     [rbp+var_10], rax
0x18007d797  test    rax, rax
0x18007d79a  jz      short loc_18007D7D5
0x18007d79c  mov     [rbp+arg_10], r14
0x18007d7a0  lea     rcx, [rbp+arg_10]
0x18007d7a4  call    ??1?$unique_ptr@V?$tuple@V_lambda_8a8ac1eece88354f66237a83e3edaffe_@@@std@@U?$default_delete@V?$tuple@V_lambda_8a8ac1eece88354f66237a83e3edaffe_@@@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::tuple<_lambda_8a8ac1eece88354f66237a83e3edaffe_>>::~unique_ptr<std::tuple<_lambda_8a8ac1eece88354f66237a83e3edaffe_>>(void)
0x18007d7a9  lea     rdx, [rbp+var_10]
0x18007d7ad  mov     rcx, rsi
0x18007d7b0  call    ??4thread@std@@QEAAAEAV01@$$QEAV01@@Z; std::thread::operator=(std::thread &&)
0x18007d7b5  lea     rcx, [rbp+var_10]; this
0x18007d7b9  call    ??1thread@std@@QEAA@XZ; std::thread::~thread(void)
0x18007d7be  nop
0x18007d7bf  mov     rcx, rdi
0x18007d7c2  call    ?_Tidy@?$_Func_class@XUGetCompositionInputSinkViewInstanceIdFromPointRequestPayload@@V?$RequestCompleter@U?$HrResponse@UResponsePayload@GetCompositionInputSinkViewInstanceIdFromPointService@@@@@@@std@@IEAAXXZ; std::_Func_class<void,GetCompositionInputSinkViewInstanceIdFromPointRequestPayload,RequestCompleter<HrResponse<GetCompositionInputSinkViewInstanceIdFromPointService::ResponsePayload>>>::_Tidy(void)
0x18007d7c7  mov     rax, rsi
0x18007d7ca  add     rsp, 40h
0x18007d7ce  pop     r14
0x18007d7d0  pop     rdi
0x18007d7d1  pop     rsi
0x18007d7d2  pop     rbx
0x18007d7d3  pop     rbp
0x18007d7d4  retn
0x18007d7d5  mov     [rbp+var_8], r14d
0x18007d7d9  mov     ecx, 6
0x18007d7de  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
```
