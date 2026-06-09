# FxDriverEntry

- ea: `0x140042040`
- end: `0x14004206c`
- name: `FxDriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callees

- `0x140042074`
- `0x140067008`

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
0x140042040  mov     [rsp+arg_0], rbx
0x140042045  push    rdi
0x140042046  sub     rsp, 20h
0x14004204a  mov     rbx, rdx
0x14004204d  mov     rdi, rcx
0x140042050  call    __security_init_cookie
0x140042055  mov     rdx, rbx; RegistryPath
0x140042058  mov     rcx, rdi; DriverObject
0x14004205b  call    FxDriverEntryWorker
0x140042060  mov     rbx, [rsp+28h+arg_0]
0x140042065  add     rsp, 20h
0x140042069  pop     rdi
0x14004206a  retn
```
