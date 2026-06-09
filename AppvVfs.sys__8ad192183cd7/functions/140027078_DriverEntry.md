# DriverEntry

- ea: `0x140027078`
- end: `0x140027095`
- name: `DriverEntry`
- size: `29`
- prototype: `NTSTATUS __stdcall(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140027010`

## callees

- `0x140008100`
- `0x140027044`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(_DRIVER_OBJECT *DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  return DriverInitialize(DriverObject);
}

```

## disassembly

```asm
0x140027078  push    rbx
0x14002707a  sub     rsp, 20h
0x14002707e  mov     rbx, rcx
0x140027081  call    __security_init_cookie
0x140027086  mov     rcx, rbx; DriverObject
0x140027089  call    DriverInitialize
0x14002708e  add     rsp, 20h
0x140027092  pop     rbx
0x140027093  retn
```
