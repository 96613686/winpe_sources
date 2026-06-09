# _lambda_bbe3fba25f2dd4d7642083cd447b5ef3_::_lambda_invoker_cdecl_

- ea: `0x18005a130`
- end: `0x18005a1b7`
- name: `_lambda_bbe3fba25f2dd4d7642083cd447b5ef3_::_lambda_invoker_cdecl_`
- size: `135`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_TIMER Timer)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1800439cc`
- `0x1800575c4`
- `0x18005a130`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005a194`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18005a194`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a147`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005a147`

## pseudocode

```c
void __fastcall lambda_bbe3fba25f2dd4d7642083cd447b5ef3_::_lambda_invoker_cdecl_(
        PTP_CALLBACK_INSTANCE Instance,
        PVOID Context,
        PTP_TIMER Timer)
{
  __int64 i; // rbx
  RTL_SRWLOCK *v5; // [rsp+38h] [rbp+10h] BYREF

  AcquireSRWLockExclusive(&gBfeTimerTracking);
  v5 = &gBfeTimerTracking;
  for ( i = qword_1800EF2A8; i != qword_1800EF2B0 && *(PVOID *)i != Context; i += 8 )
    ;
  if ( i != qword_1800EF2B0 )
  {
    if ( *(_DWORD *)(*(_QWORD *)i + 16LL) == 1 )
      MicrosoftTelemetryAssertTriggeredNoArgs();
    *(_DWORD *)(*(_QWORD *)i + 16LL) = 1;
    SubmitThreadpoolWork(pwk);
    *(_QWORD *)&xmmword_1800EF330 = xmmword_1800EF330 + 1;
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
}

```

## disassembly

```asm
0x18005a130  mov     [rsp+arg_0], rbx
0x18005a135  push    rdi
0x18005a136  sub     rsp, 20h
0x18005a13a  mov     rdi, rdx
0x18005a13d  lea     rbx, ?gBfeTimerTracking@@3VBfeTimerTracking@@A; BfeTimerTracking gBfeTimerTracking
0x18005a144  mov     rcx, rbx; SRWLock
0x18005a147  call    cs:__imp_AcquireSRWLockExclusive
0x18005a14d  mov     [rsp+28h+arg_8], rbx
0x18005a152  mov     rbx, cs:qword_1800EF2A8
0x18005a159  mov     rax, cs:qword_1800EF2B0
0x18005a160  jmp     short loc_18005A16B
0x18005a162  cmp     [rbx], rdi
0x18005a165  jz      short loc_18005A170
0x18005a167  add     rbx, 8
0x18005a16b  cmp     rbx, rax
0x18005a16e  jnz     short loc_18005A162
0x18005a170  cmp     rbx, rax
0x18005a173  jz      short loc_18005A1A1
0x18005a175  mov     rax, [rbx]
0x18005a178  cmp     dword ptr [rax+10h], 1
0x18005a17c  jnz     short loc_18005A183
0x18005a17e  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18005a183  mov     rax, [rbx]
0x18005a186  mov     dword ptr [rax+10h], 1
0x18005a18d  mov     rcx, cs:pwk; pwk
0x18005a194  call    cs:__imp_SubmitThreadpoolWork
0x18005a19a  inc     qword ptr cs:xmmword_1800EF330
0x18005a1a1  lea     rcx, [rsp+28h+arg_8]
0x18005a1a6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18005a1ab  nop
0x18005a1ac  mov     rbx, [rsp+28h+arg_0]
0x18005a1b1  add     rsp, 20h
0x18005a1b5  pop     rdi
0x18005a1b6  retn
```
