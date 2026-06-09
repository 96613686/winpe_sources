# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::Invoke(void)

- ea: `0x180005d90`
- end: `0x180005da7`
- name: `?Invoke@?$MethodReleaseNotifier@V?$Service@VDialogBlockingService@@$00USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAXXZ`
- size: `23`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::MethodReleaseNotifier<Windows::Internal::Service<DialogBlockingService,1,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::Invoke(
        __int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(a1 + 24))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x180005d90  sub     rsp, 28h
0x180005d94  mov     rax, [rcx+18h]
0x180005d98  mov     rcx, [rcx+10h]
0x180005d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005da1  nop
0x180005da2  add     rsp, 28h
0x180005da6  retn
```
