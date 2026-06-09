# DriverEntry

- ea: `0x140024010`
- end: `0x14002403c`
- name: `DriverEntry`
- size: `44`
- prototype: `NTSTATUS __stdcall(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)`
- caller_count: `0`
- callee_count: `2`
- tags: `registry_config`

## callees

- `0x140005118`
- `0x140024044`

## pseudocode

```c
NTSTATUS __stdcall DriverEntry(PDRIVER_OBJECT DriverObject, PUNICODE_STRING RegistryPath)
{
  sub_140024044();
  return sub_140005118(DriverObject, &RegistryPath->Length);
}

```

## disassembly

```asm
0x140024010  mov     [rsp+arg_0], rbx
0x140024015  push    rdi
0x140024016  sub     rsp, 20h
0x14002401a  mov     rbx, rdx
0x14002401d  mov     rdi, rcx
0x140024020  call    sub_140024044
0x140024025  mov     rdx, rbx
0x140024028  mov     rcx, rdi; DriverObject
0x14002402b  call    sub_140005118
0x140024030  mov     rbx, [rsp+28h+arg_0]
0x140024035  add     rsp, 20h
0x140024039  pop     rdi
0x14002403a  retn
```
