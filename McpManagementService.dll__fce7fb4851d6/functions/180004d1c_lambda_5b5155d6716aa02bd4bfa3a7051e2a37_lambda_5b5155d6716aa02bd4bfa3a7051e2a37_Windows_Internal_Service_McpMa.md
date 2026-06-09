# _lambda_5b5155d6716aa02bd4bfa3a7051e2a37_::_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_(Windows::Internal::Service<McpManagementService,2,Windows::Internal::ServiceModuleBase::SecurityPolicyEveryoneLocal,2,Windows::Internal::DefaultServerDescriptor> *)

- ea: `0x180004d1c`
- end: `0x180004d23`
- name: `??0_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_@@QEAA@PEAV?$Service@VMcpManagementService@@$01USecurityPolicyEveryoneLocal@ServiceModuleBase@Internal@Windows@@$01UDefaultServerDescriptor@45@@Internal@Windows@@@Z`
- size: `7`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64)`
- caller_count: `6`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800050e4`
- `0x180007980`
- `0x18000a914`
- `0x18000aa78`
- `0x1800234cc`
- `0x180024ca0`

## pseudocode

```c
_QWORD *__fastcall _lambda_5b5155d6716aa02bd4bfa3a7051e2a37_::_lambda_5b5155d6716aa02bd4bfa3a7051e2a37_(
        _QWORD *a1,
        __int64 a2)
{
  *a1 = a2;
  return a1;
}

```

## disassembly

```asm
0x180004d1c  mov     [rcx], rdx
0x180004d1f  mov     rax, rcx
0x180004d22  retn
```
