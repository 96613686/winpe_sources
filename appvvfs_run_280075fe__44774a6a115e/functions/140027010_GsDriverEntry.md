# GsDriverEntry

- ea: `0x140027010`
- end: `0x14002703c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140027044`
- `0x140027078`

## pseudocode

```c
NTSTATUS __stdcall GsDriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  return DriverEntry(DriverObject, RegistryPath);
}

```

## disassembly

```asm
0x140027010  mov     [rsp+arg_0], rbx
0x140027015  push    rdi
0x140027016  sub     rsp, 20h
0x14002701a  mov     rbx, rdx
0x14002701d  mov     rdi, rcx
0x140027020  call    __security_init_cookie
0x140027025  mov     rdx, rbx; RegistryPath
0x140027028  mov     rcx, rdi; DriverObject
0x14002702b  call    DriverEntry
0x140027030  mov     rbx, [rsp+28h+arg_0]
0x140027035  add     rsp, 20h
0x140027039  pop     rdi
0x14002703a  retn
```
