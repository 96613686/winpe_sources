# __vcrt_thread_detach

- ea: `0x180008c00`
- end: `0x180008c10`
- name: `__vcrt_thread_detach`
- size: `16`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x180007378`
- `0x1800073a0`

## callees

- `0x180008f80`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_detach()
{
  _vcrt_freeptd_for_this_thread();
  return 1;
}

```

## disassembly

```asm
0x180008c00  sub     rsp, 28h
0x180008c04  call    __vcrt_freeptd_for_this_thread
0x180008c09  mov     al, 1
0x180008c0b  add     rsp, 28h
0x180008c0f  retn
```
