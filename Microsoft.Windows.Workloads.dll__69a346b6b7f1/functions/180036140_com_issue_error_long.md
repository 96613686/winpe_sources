# _com_issue_error(long)

- ea: `0x180036140`
- end: `0x180036150`
- name: `?_com_issue_error@@YAXJ@Z`
- size: `16`
- prototype: `void __fastcall(__int64)`
- caller_count: `5`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1800229c0`
- `0x180022dd0`
- `0x180023860`
- `0x180023c50`
- `0x180024120`

## callees

- `0x18003bed0`

## pseudocode

```c
void __fastcall _com_issue_error(__int64 a1)
{
  ((void (__fastcall *)(__int64, _QWORD))__errorPfn)(a1, 0);
}

```

## disassembly

```asm
0x180036140  mov     rax, cs:?__errorPfn@@3P6AXJPEAUIErrorInfo@@@ZEA; void (*__errorPfn)(long,IErrorInfo *)
0x180036147  xor     edx, edx
0x180036149  jmp     cs:__guard_dispatch_icall_fptr
```
