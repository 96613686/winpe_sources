# Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(tagComCallData *)

- ea: `0x180004ad0`
- end: `0x180004adb`
- name: `?ConnectCallbackThunk@ServiceModuleBase@Internal@Windows@@SAJPEAUtagComCallData@@@Z`
- size: `11`
- prototype: `__int64 __fastcall(struct tagComCallData *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000e010`

## pseudocode

```c
__int64 __fastcall Windows::Internal::ServiceModuleBase::ConnectCallbackThunk(struct tagComCallData *a1)
{
  return (**(__int64 (__fastcall ***)(struct tagComCallData *))&a1->dwDispid)(a1);
}

```

## disassembly

```asm
0x180004ad0  mov     rax, [rcx]
0x180004ad3  mov     rax, [rax]
0x180004ad6  jmp     _guard_dispatch_icall$thunk$10345483385596137414
```
