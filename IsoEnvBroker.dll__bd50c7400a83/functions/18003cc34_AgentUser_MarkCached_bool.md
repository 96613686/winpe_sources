# AgentUser::MarkCached(bool)

- ea: `0x18003cc34`
- end: `0x18003cd17`
- name: `?MarkCached@AgentUser@@QEAAX_N@Z`
- size: `227`
- prototype: `void __fastcall(AgentUser *__hidden this, bool)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180037064`
- `0x180037470`
- `0x18003c4a4`

## callees

- `0x1800075e4`
- `0x180011e18`
- `0x18003cc34`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003cc89`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003cccb`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003cc89`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x18003cccb`

## string_xrefs

- `0x18003cd05`: `onecoreuap\windows\core\isoenvbroker\lib\isoenvbrokersvc\agentuser.cpp`
- `0x18003cca6`: `AU %s is no longer keeping the service alive.`
- `0x18003cc64`: `AU %s is keeping the service alive.`

## pseudocode

```c
void __fastcall AgentUser::MarkCached(AgentUser *this, char a2, __int64 a3, const char *a4)
{
  _QWORD *v6; // r8
  void (__fastcall *v7)(void *); // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_BYTE *)this + 244) == a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xEF,
      (int)"onecoreuap\\windows\\core\\isoenvbroker\\lib\\isoenvbrokersvc\\agentuser.cpp",
      a4);
  v6 = (_QWORD *)((char *)this + 144);
  if ( a2 )
  {
    if ( *((_QWORD *)this + 21) > 7u )
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
    if ( *((_QWORD *)this + 21) > 7u )
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
  *((_BYTE *)this + 244) = a2;
}

```

## disassembly

```asm
0x18003cc34  mov     [rsp+arg_0], rbx
0x18003cc39  push    rdi
0x18003cc3a  sub     rsp, 20h
0x18003cc3e  mov     bl, dl
0x18003cc40  mov     rdi, rcx
0x18003cc43  cmp     [rcx+0F4h], dl
0x18003cc49  jz      loc_18003CD00
0x18003cc4f  lea     r8, [rcx+90h]
0x18003cc56  test    dl, dl
0x18003cc58  jz      short loc_18003CC9C
0x18003cc5a  cmp     qword ptr [r8+18h], 7
0x18003cc5f  jbe     short loc_18003CC64
0x18003cc61  mov     r8, [r8]
0x18003cc64  lea     rdx, aAuSIsKeepingTh; "AU %s is keeping the service alive."
0x18003cc6b  mov     ecx, 4; unsigned __int8
0x18003cc70  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003cc75  xor     r9d, r9d; Context
0x18003cc78  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18003cc7f  xor     r8d, r8d; Parameter
0x18003cc82  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18003cc89  call    cs:__imp_InitOnceExecuteOnce
0x18003cc8f  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x18003cc96  mov     rax, [rax+10h]
0x18003cc9a  jmp     short loc_18003CCDC
0x18003cc9c  cmp     qword ptr [r8+18h], 7
0x18003cca1  jbe     short loc_18003CCA6
0x18003cca3  mov     r8, [r8]
0x18003cca6  lea     rdx, aAuSIsNoLongerK; "AU %s is no longer keeping the service "...
0x18003ccad  mov     ecx, 4; unsigned __int8
0x18003ccb2  call    ?Log@@YAXEPEB_WZZ; Log(uchar,wchar_t const *,...)
0x18003ccb7  xor     r9d, r9d; Context
0x18003ccba  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_1_@?1??Create@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@SAAEAVSvcHostModule@Internal@Windows@@XZ@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x18003ccc1  xor     r8d, r8d; Parameter
0x18003ccc4  lea     rcx, ?initOnceOutOfProc_@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@1T_RTL_RUN_ONCE@@A; InitOnce
0x18003cccb  call    cs:__imp_InitOnceExecuteOnce
0x18003ccd1  mov     rax, cs:?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x18003ccd8  mov     rax, [rax+18h]
0x18003ccdc  lea     rcx, ?instance_@?$StaticStorage@VSvcHostModule@Internal@Windows@@$00H@Details@WRL@Microsoft@@0V1234@A; Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int> Microsoft::WRL::Details::StaticStorage<Windows::Internal::SvcHostModule,1,int>::instance_
0x18003cce3  mov     cs:byte_1800B92C0, 1
0x18003ccea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccef  mov     [rdi+0F4h], bl
0x18003ccf5  mov     rbx, [rsp+28h+arg_0]
0x18003ccfa  add     rsp, 20h
0x18003ccfe  pop     rdi
0x18003ccff  retn
0x18003cd00  mov     rcx, [rsp+28h]; this
0x18003cd05  lea     r8, aOnecoreuapWind_22; "onecoreuap\\windows\\core\\isoenvbroker"...
0x18003cd0c  mov     edx, 0EFh; void *
0x18003cd11  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
