# FxDriverEntry

- ea: `0x140015790`
- end: `0x1400157bc`
- name: `FxDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x1400157c4`
- `0x140030008`

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
0x140015790  mov     [rsp+arg_0], rbx
0x140015795  push    rdi
0x140015796  sub     rsp, 20h
0x14001579a  mov     rbx, rdx
0x14001579d  mov     rdi, rcx
0x1400157a0  call    __security_init_cookie
0x1400157a5  mov     rdx, rbx; RegistryPath
0x1400157a8  mov     rcx, rdi; DriverObject
0x1400157ab  call    FxDriverEntryWorker
0x1400157b0  mov     rbx, [rsp+28h+arg_0]
0x1400157b5  add     rsp, 20h
0x1400157b9  pop     rdi
0x1400157ba  retn
```
