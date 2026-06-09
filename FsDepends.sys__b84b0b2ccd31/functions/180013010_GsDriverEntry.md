# GsDriverEntry

- ea: `0x180013010`
- end: `0x18001303c`
- name: `GsDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180013044`
- `0x180013078`

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
0x180013010  mov     [rsp+arg_0], rbx
0x180013015  push    rdi
0x180013016  sub     rsp, 20h
0x18001301a  mov     rbx, rdx
0x18001301d  mov     rdi, rcx
0x180013020  call    __security_init_cookie
0x180013025  mov     rdx, rbx; RegistryPath
0x180013028  mov     rcx, rdi; DriverObject
0x18001302b  call    DriverEntry
0x180013030  mov     rbx, [rsp+28h+arg_0]
0x180013035  add     rsp, 20h
0x180013039  pop     rdi
0x18001303a  retn
```
