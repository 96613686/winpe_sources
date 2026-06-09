# Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::Invoke(void)

- ea: `0x1800059d0`
- end: `0x1800059e7`
- name: `?Invoke@?$MethodReleaseNotifier@V?$Service@VGipMgmtSvc@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@?$OutOfProcModuleBase@VSvcHostModule@Internal@Windows@@@Details@WRL@Microsoft@@UEAAXXZ`
- size: `23`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::SvcHostModule>::MethodReleaseNotifier<Windows::Internal::Service<GipMgmtSvc,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor>>::Invoke(
        __int64 a1)
{
  return (*(__int64 (__fastcall **)(_QWORD))(a1 + 24))(*(_QWORD *)(a1 + 16));
}

```

## disassembly

```asm
0x1800059d0  sub     rsp, 28h
0x1800059d4  mov     rax, [rcx+18h]
0x1800059d8  mov     rcx, [rcx+10h]
0x1800059dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059e1  nop
0x1800059e2  add     rsp, 28h
0x1800059e6  retn
```
