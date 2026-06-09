# FileProvReleaseReadCbReadParameters

- ea: `0x140007878`
- end: `0x14000788b`
- name: `FileProvReleaseReadCbReadParameters`
- size: `19`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140039750`

## callees

- `0x1400078a0`

## pseudocode

```c
__int64 __fastcall FileProvReleaseReadCbReadParameters(__int64 a1)
{
  return FileProvReleaseReadCompletionContext((PVOID)(a1 - 24));
}

```

## disassembly

```asm
0x140007878  sub     rsp, 28h
0x14000787c  add     rcx, 0FFFFFFFFFFFFFFE8h; Entry
0x140007880  call    FileProvReleaseReadCompletionContext
0x140007885  add     rsp, 28h
0x140007889  retn
```
