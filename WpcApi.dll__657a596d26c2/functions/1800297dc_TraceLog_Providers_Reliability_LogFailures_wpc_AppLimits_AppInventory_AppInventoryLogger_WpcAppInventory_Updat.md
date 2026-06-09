# _TraceLog::Providers::Reliability::LogFailures_wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser__::_1_::catch$1

- ea: `0x1800297dc`
- end: `0x18002981f`
- name: `_TraceLog::Providers::Reliability::LogFailures_wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser__::_1_::catch$1`
- size: `67`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `installer_update`

## callees

- `0x180003d20`
- `0x1800128a0`
- `0x18001312c`
- `0x1800196b4`
- `0x18002c010`

## pseudocode

```c
void __fastcall __noreturn TraceLog::Providers::Reliability::LogFailures_wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser__::_1_::catch_1(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax
  int v4; // eax

  v3 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a2 + 32) + 8LL))(*(_QWORD *)(a2 + 32));
  wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::SetMessage(
    *(_QWORD *)(a2 + 64),
    v3);
  v4 = ErrorCodeFromCaughtException();
  wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::Stop(
    *(_QWORD **)(a2 + 64),
    v4);
  throw;
}

```

## disassembly

```asm
0x1800297dc  mov     [rsp+arg_8], rdx
0x1800297e1  push    rbp
0x1800297e2  sub     rsp, 20h
0x1800297e6  mov     rbp, rdx
0x1800297e9  mov     rcx, [rbp+20h]
0x1800297ed  mov     rax, [rcx]
0x1800297f0  mov     rax, [rax+8]
0x1800297f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297f9  mov     rdx, rax
0x1800297fc  mov     rcx, [rbp+40h]
0x180029800  call    ?SetMessage@?$ActivityBase@VWpcBaseLogger@Logging@wpc@@$00$0A@$03$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXPEBDZZ; wil::ActivityBase<wpc::Logging::WpcBaseLogger,1,0,4,16777216,_TlgReflectorTag_Param0IsProviderType>::SetMessage(char const *,...)
0x180029805  call    ?ErrorCodeFromCaughtException@@YAJXZ; ErrorCodeFromCaughtException(void)
0x18002980a  mov     edx, eax; int
0x18002980c  mov     rcx, [rbp+40h]; this
0x180029810  call    ?Stop@WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser@AppInventoryLogger@AppInventory@AppLimits@wpc@@QEAAXJ@Z; wpc::AppLimits::AppInventory::AppInventoryLogger::WpcAppInventory_UpdateLastUsedTimeIfKnownAppForUser::Stop(long)
0x180029815  xor     edx, edx; pThrowInfo
0x180029817  xor     ecx, ecx; pExceptionObject
0x180029819  call    _CxxThrowException_0
```
