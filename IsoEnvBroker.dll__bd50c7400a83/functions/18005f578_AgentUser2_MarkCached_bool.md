# AgentUser2::MarkCached(bool)

- ea: `0x18005f578`
- end: `0x18005f658`
- name: `?MarkCached@AgentUser2@@QEAAX_N@Z`
- size: `224`
- prototype: `void __fastcall(AgentUser2 *__hidden this, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x18005b2a4`
- `0x18005b660`
- `0x18005f33c`

## callees

- `0x1800075e4`
- `0x180011e18`
- `0x18005f578`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005f5ca`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005f60c`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005f5ca`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18005f60c`

## string_xrefs

- `0x18005f5e7`: `AU %s is no longer keeping the service alive.`
- `0x18005f5a5`: `AU %s is keeping the service alive.`
- `0x18005f646`: `onecoreuap\windows\core\isoenvbroker\lib\v2\agentuser.cpp`

## pseudocode

```c
void __fastcall AgentUser2::MarkCached(AgentUser2 *this, char a2, __int64 a3, const char *a4)
{
  _QWORD *v6; // r8
  void (__fastcall *v7)(void *); // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_BYTE *)this + 236) == a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x92,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\v2\\agentuser.cpp",
      a4);
  v6 = (_QWORD *)((char *)this + 72);
  if ( a2 )
  {
    if ( *((_QWORD *)this + 12) > 7u )
      v6 = (_QWORD *)*v6;
    Log(4u, L"AU %s is keeping the service alive.", v6);
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::initOnceOutOfProc_,
      (PINIT_ONCE_FN)`Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    v7 = *(void (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
                                       + 16LL);
  }
  else
  {
    if ( *((_QWORD *)this + 12) > 7u )
      v6 = (_QWORD *)*v6;
    Log(4u, L"AU %s is no longer keeping the service alive.", v6);
    InitOnceExecuteOnce(
      &Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::initOnceOutOfProc_,
      (PINIT_ONCE_FN)`Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::Create'::`2'::_lambda_1_::_lambda_invoker_cdecl_,
      0,
      0);
    v7 = *(void (__fastcall **)(void *))(Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
                                       + 24LL);
  }
  byte_1800B92C0 = 1;
  v7(&Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_);
  *((_BYTE *)this + 236) = a2;
}

```

## disassembly

```asm
0x18005f578  mov     [rsp+arg_0], rbx
0x18005f57d  push    rdi
0x18005f57e  sub     rsp, 20h
0x18005f582  mov     bl, dl
0x18005f584  mov     rdi, rcx
0x18005f587  cmp     [rcx+0ECh], dl
0x18005f58d  jz      loc_18005F641
0x18005f593  lea     r8, [rcx+48h]
0x18005f597  test    dl, dl
0x18005f599  jz      short loc_18005F5DD
0x18005f59b  cmp     qword ptr [r8+18h], 7
0x18005f5a0  jbe     short loc_18005F5A5
0x18005f5a2  mov     r8, [r8]
0x18005f5a5  lea     rdx, aAuSIsKeepingTh; "AU %s is keeping the service alive."
0x18005f5ac  mov     ecx, 4; unsigned __int8
0x18005f5b1  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18005f5b6  xor     r9d, r9d; Context
0x18005f5b9  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18005f5c0  xor     r8d, r8d; Parameter
0x18005f5c3  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18005f5ca  call    cs:__imp_InitOnceExecuteOnce
0x18005f5d0  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x18005f5d7  mov     rax, [rax+10h]
0x18005f5db  jmp     short loc_18005F61D
0x18005f5dd  cmp     qword ptr [r8+18h], 7
0x18005f5e2  jbe     short loc_18005F5E7
0x18005f5e4  mov     r8, [r8]
0x18005f5e7  lea     rdx, aAuSIsNoLongerK; "AU %s is no longer keeping the service "...
0x18005f5ee  mov     ecx, 4; unsigned __int8
0x18005f5f3  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18005f5f8  xor     r9d, r9d; Context
0x18005f5fb  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18005f602  xor     r8d, r8d; Parameter
0x18005f605  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18005f60c  call    cs:__imp_InitOnceExecuteOnce
0x18005f612  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x18005f619  mov     rax, [rax+18h]
0x18005f61d  lea     rcx, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x18005f624  mov     cs:byte_1800B92C0, 1
0x18005f62b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f630  mov     [rdi+0ECh], bl
0x18005f636  mov     rbx, [rsp+28h+arg_0]
0x18005f63b  add     rsp, 20h
0x18005f63f  pop     rdi
0x18005f640  retn
0x18005f641  mov     rcx, [rsp+28h]; this
0x18005f646  lea     r8, aOnecoreuapWind_24; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18005f64d  mov     edx, 92h; void *
0x18005f652  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
