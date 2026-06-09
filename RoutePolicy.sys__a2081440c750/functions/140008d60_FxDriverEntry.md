# FxDriverEntry

- ea: `0x140008d60`
- end: `0x140008d8c`
- name: `FxDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140008d94`
- `0x140019008`

## pseudocode

```c
NTSTATUS __stdcall FxDriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  _security_init_cookie();
  return FxDriverEntryWorker(DriverObject, RegistryPath);
}

```

## disassembly

```asm
0x140008d60  mov     [rsp+arg_0], rbx
0x140008d65  push    rdi
0x140008d66  sub     rsp, 20h
0x140008d6a  mov     rbx, rdx
0x140008d6d  mov     rdi, rcx
0x140008d70  call    __security_init_cookie
0x140008d75  mov     rdx, rbx; RegistryPath
0x140008d78  mov     rcx, rdi; DriverObject
0x140008d7b  call    FxDriverEntryWorker
0x140008d80  mov     rbx, [rsp+28h+arg_0]
0x140008d85  add     rsp, 20h
0x140008d89  pop     rdi
0x140008d8a  retn
```
