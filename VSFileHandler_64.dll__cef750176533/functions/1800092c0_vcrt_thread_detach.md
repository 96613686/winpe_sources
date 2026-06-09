# __vcrt_thread_detach

- ea: `0x1800092c0`
- end: `0x1800092d0`
- name: `__vcrt_thread_detach`
- size: `16`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800077a8`
- `0x1800077d0`

## callees

- `0x1800094d0`

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
0x1800092c0  sub     rsp, 28h
0x1800092c4  call    __vcrt_freeptd_for_this_thread
0x1800092c9  mov     al, 1
0x1800092cb  add     rsp, 28h
0x1800092cf  retn
```
