# GsDriverEntry

- ea: `0x140008010`
- end: `0x14000803c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140008044`
- `0x140008078`

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
0x140008010  mov     [rsp+arg_0], rbx
0x140008015  push    rdi
0x140008016  sub     rsp, 20h
0x14000801a  mov     rbx, rdx
0x14000801d  mov     rdi, rcx
0x140008020  call    __security_init_cookie
0x140008025  mov     rdx, rbx; RegistryPath
0x140008028  mov     rcx, rdi; DriverObject
0x14000802b  call    DriverEntry
0x140008030  mov     rbx, [rsp+28h+arg_0]
0x140008035  add     rsp, 20h
0x140008039  pop     rdi
0x14000803a  retn
```
