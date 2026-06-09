# WorkerThread<Unit>::WorkerThread<Unit>(void)

- ea: `0x180007404`
- end: `0x1800075ab`
- name: `??0?$WorkerThread@UUnit@@@@QEAA@XZ`
- size: `423`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800072c8`
- `0x180007390`

## callees

- `0x180004ecc`
- `0x180007404`
- `0x1800075b4`
- `0x18001607c`
- `0x18002a514`
- `0x180043a8c`
- `0x180091010`

## import_xrefs

- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000758e`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000758e`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180007555`
- `api-ms-win-crt-private-l1-1-0!_o_terminate` at `0x180007555`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000753d`
- `api-ms-win-crt-private-l1-1-0!_o__beginthreadex` at `0x18000753d`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000744a`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x18000744a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000745c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000745c`

## string_xrefs

- `0x180007599`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall WorkerThread<Unit>::WorkerThread<Unit>(__int64 a1)
{
  __int64 v2; // rbx
  HANDLE Event; // rsi
  const char *v4; // r9
  _QWORD *v5; // rax
  _QWORD *v6; // rax
  __int64 v7; // rdx
  __int64 v8; // rcx
  int v9; // ecx
  int v10; // eax
  _DWORD v12[2]; // [rsp+38h] [rbp-48h] BYREF
  _BYTE v13[56]; // [rsp+40h] [rbp-40h] BYREF
  _BYTE *v14; // [rsp+78h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+28h]
  _QWORD *v16; // [rsp+B8h] [rbp+38h] BYREF
  _BYTE *v17; // [rsp+C0h] [rbp+40h]
  __int64 v18; // [rsp+C8h] [rbp+48h]

  v14 = 0;
  v17 = v13;
  *(_OWORD *)a1 = 0;
  v2 = a1 + 16;
  v16 = (_QWORD *)(a1 + 16);
  *(_QWORD *)(a1 + 16) = 0;
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  if ( !Event )
LABEL_11:
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x1CC8,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      v4);
  GetLastError();
  _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
    v2,
    Event);
  v18 = a1 + 24;
  LODWORD(v16) = 0;
  ____0W4EventOptions_wil_____shared_any_t_V__event_t_V__shared_storage_V__unique_any_t_V__event_t_V__unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__Uerr_exception_policy_3__wil___wil___details_wil__Uerr_exception_policy_3__wil___wil__QEAA___QEAW4EventOptions_1__Z(
    a1 + 24,
    &v16);
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
  v5 = operator new(0x50u);
  *v5 = v5;
  v5[1] = v5;
  *(_QWORD *)(a1 + 120) = v5;
  *(_QWORD *)(a1 + 192) = 0;
  if ( v14 )
  {
    if ( v14 == v13 )
    {
      *(_QWORD *)(a1 + 192) = (*(__int64 (__fastcall **)(_BYTE *, __int64))(*(_QWORD *)v14 + 8LL))(v14, a1 + 136);
      std::_Func_class<void,GetCompositionInputSinkViewInstanceIdFromPointRequestPayload,RequestCompleter<HrResponse<GetCompositionInputSinkViewInstanceIdFromPointService::ResponsePayload>>>::_Tidy(v13);
    }
    else
    {
      *(_QWORD *)(a1 + 192) = v14;
      v14 = 0;
    }
  }
  v6 = operator new(8u);
  *v6 = a1;
  v16 = v6;
  v7 = _o__beginthreadex(
         0,
         0,
         std::thread::_Invoke<std::tuple<_lambda_8a8ac1eece88354f66237a83e3edaffe_>,0>,
         v6,
         0,
         v12);
  if ( !v7 )
  {
    v12[0] = 0;
    std::_Throw_Cpp_error(6);
    goto LABEL_11;
  }
  if ( *(_DWORD *)(a1 + 8) )
  {
    _o_terminate(v8, v7);
    __debugbreak();
  }
  v9 = v12[0];
  v10 = v12[1];
  *(_QWORD *)a1 = v7;
  *(_DWORD *)(a1 + 8) = v9;
  *(_DWORD *)(a1 + 12) = v10;
  std::_Func_class<void,GetCompositionInputSinkViewInstanceIdFromPointRequestPayload,RequestCompleter<HrResponse<GetCompositionInputSinkViewInstanceIdFromPointService::ResponsePayload>>>::_Tidy(v13);
  return a1;
}

```

## disassembly

```asm
0x180007404  mov     [rsp-28h+arg_0], rcx
0x180007409  push    rbp
0x18000740a  push    rbx
0x18000740b  push    rsi
0x18000740c  push    rdi
0x18000740d  push    r14
0x18000740f  mov     rbp, rsp
0x180007412  sub     rsp, 80h
0x180007419  mov     rdi, rcx
0x18000741c  xor     r14d, r14d
0x18000741f  mov     [rbp+var_8], r14
0x180007423  lea     rax, [rbp+var_40]
0x180007427  mov     [rbp+arg_10], rax
0x18000742b  xorps   xmm0, xmm0
0x18000742e  movups  xmmword ptr [rcx], xmm0
0x180007431  lea     rbx, [rcx+10h]
0x180007435  mov     [rbp+arg_8], rbx
0x180007439  mov     [rbx], r14
0x18000743c  xor     edx, edx; lpName
0x18000743e  xor     ecx, ecx; lpEventAttributes
0x180007440  mov     r9d, 1F0003h; dwDesiredAccess
0x180007446  lea     r8d, [r14+1]; dwFlags
0x18000744a  call    cs:__imp_CreateEventExW
0x180007450  mov     rsi, rax
0x180007453  test    rax, rax
0x180007456  jz      loc_180007595
0x18000745c  call    cs:__imp_GetLastError
0x180007462  mov     rdx, rsi
0x180007465  mov     rcx, rbx
0x180007468  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x18000746d  nop
0x18000746e  lea     rbx, [rdi+18h]
0x180007472  mov     [rbp+arg_18], rbx
0x180007476  mov     dword ptr [rbp+arg_8], r14d
0x18000747a  lea     rdx, [rbp+arg_8]
0x18000747e  mov     rcx, rbx
0x180007481  call    ??$?0W4EventOptions@wil@@@?$shared_any_t@V?$event_t@V?$shared_storage@V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@QEAA@$$QEAW4EventOptions@1@@Z
0x180007486  nop
0x180007487  mov     qword ptr [rbx+10h], 2
0x18000748f  xorps   xmm0, xmm0
0x180007492  movups  xmmword ptr [rbx+28h], xmm0
0x180007496  movups  xmmword ptr [rbx+38h], xmm0
0x18000749a  movups  xmmword ptr [rbx+48h], xmm0
0x18000749e  mov     [rbx+18h], r14
0x1800074a2  mov     [rbx+20h], r14
0x1800074a6  mov     dword ptr [rbx+58h], 0FFFFFFFFh
0x1800074ad  mov     [rbx+5Ch], r14d
0x1800074b1  mov     [rbx+60h], r14
0x1800074b5  mov     [rbx+68h], r14
0x1800074b9  lea     ecx, [r14+50h]; Size
0x1800074bd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800074c2  mov     [rax], rax
0x1800074c5  mov     [rax+8], rax
0x1800074c9  mov     [rbx+60h], rax
0x1800074cd  lea     rbx, [rdi+88h]
0x1800074d4  mov     [rbx+38h], r14
0x1800074d8  mov     rcx, [rbp+var_8]
0x1800074dc  test    rcx, rcx
0x1800074df  jz      short loc_180007510
0x1800074e1  lea     rax, [rbp+var_40]
0x1800074e5  cmp     rcx, rax
0x1800074e8  jnz     short loc_180007508
0x1800074ea  mov     rax, [rcx]
0x1800074ed  mov     rdx, rbx
0x1800074f0  mov     rax, [rax+8]
0x1800074f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074f9  mov     [rbx+38h], rax
0x1800074fd  lea     rcx, [rbp+var_40]
0x180007501  call    ?_Tidy@?$_Func_class@XUGetCompositionInputSinkViewInstanceIdFromPointRequestPayload@@V?$RequestCompleter@U?$HrResponse@UResponsePayload@GetCompositionInputSinkViewInstanceIdFromPointService@@@@@@@std@@IEAAXXZ; std::_Func_class<void,GetCompositionInputSinkViewInstanceIdFromPointRequestPayload,RequestCompleter<HrResponse<GetCompositionInputSinkViewInstanceIdFromPointService::ResponsePayload>>>::_Tidy(void)
0x180007506  jmp     short loc_180007510
0x180007508  mov     [rbx+38h], rcx
0x18000750c  mov     [rbp+var_8], r14
0x180007510  mov     ecx, 8; Size
0x180007515  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000751a  mov     [rax], rdi
0x18000751d  mov     [rbp+arg_8], rax
0x180007521  lea     rcx, [rbp+var_48]
0x180007525  mov     [rsp+80h+var_58], rcx
0x18000752a  mov     [rsp+80h+var_60], r14d
0x18000752f  mov     r9, rax
0x180007532  lea     r8, ??$_Invoke@V?$tuple@V_lambda_8a8ac1eece88354f66237a83e3edaffe_@@@std@@$0A@@thread@std@@CAIPEAX@Z; std::thread::_Invoke<std::tuple<_lambda_8a8ac1eece88354f66237a83e3edaffe_>,0>(void *)
0x180007539  xor     edx, edx
0x18000753b  xor     ecx, ecx
0x18000753d  call    cs:__imp__o__beginthreadex
0x180007543  mov     rdx, rax
0x180007546  mov     [rbp+var_50], rax
0x18000754a  test    rax, rax
0x18000754d  jz      short loc_180007585
0x18000754f  cmp     [rdi+8], r14d
0x180007553  jz      short loc_18000755C
0x180007555  call    cs:__imp__o_terminate
0x18000755b  int     3; Trap to Debugger
0x18000755c  mov     ecx, [rbp+var_48]
0x18000755f  mov     eax, [rbp+var_44]
0x180007562  mov     [rdi], rdx
0x180007565  mov     [rdi+8], ecx
0x180007568  mov     [rdi+0Ch], eax
0x18000756b  lea     rcx, [rbp+var_40]
0x18000756f  call    ?_Tidy@?$_Func_class@XUGetCompositionInputSinkViewInstanceIdFromPointRequestPayload@@V?$RequestCompleter@U?$HrResponse@UResponsePayload@GetCompositionInputSinkViewInstanceIdFromPointService@@@@@@@std@@IEAAXXZ; std::_Func_class<void,GetCompositionInputSinkViewInstanceIdFromPointRequestPayload,RequestCompleter<HrResponse<GetCompositionInputSinkViewInstanceIdFromPointService::ResponsePayload>>>::_Tidy(void)
0x180007574  mov     rax, rdi
0x180007577  add     rsp, 80h
0x18000757e  pop     r14
0x180007580  pop     rdi
0x180007581  pop     rsi
0x180007582  pop     rbx
0x180007583  pop     rbp
0x180007584  retn
0x180007585  mov     [rbp+var_48], r14d
0x180007589  mov     ecx, 6
0x18000758e  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180007594  nop
0x180007595  mov     rcx, [rbp+28h]; this
0x180007599  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800075a0  mov     edx, 1CC8h; void *
0x1800075a5  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
