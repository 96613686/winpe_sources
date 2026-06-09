# FxDriverEntry

- ea: `0x14000be30`
- end: `0x14000be5c`
- name: `FxDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x14000be64`
- `0x14001d008`

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
0x14000be30  mov     [rsp+arg_0], rbx
0x14000be35  push    rdi
0x14000be36  sub     rsp, 20h
0x14000be3a  mov     rbx, rdx
0x14000be3d  mov     rdi, rcx
0x14000be40  call    __security_init_cookie
0x14000be45  mov     rdx, rbx; RegistryPath
0x14000be48  mov     rcx, rdi; DriverObject
0x14000be4b  call    FxDriverEntryWorker
0x14000be50  mov     rbx, [rsp+28h+arg_0]
0x14000be55  add     rsp, 20h
0x14000be59  pop     rdi
0x14000be5a  retn
```
