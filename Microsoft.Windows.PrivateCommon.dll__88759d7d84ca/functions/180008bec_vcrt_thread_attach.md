# __vcrt_thread_attach

- ea: `0x180008bec`
- end: `0x180008c00`
- name: `__vcrt_thread_attach`
- size: `20`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x180007378`

## callees

- `0x180008fe4`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_attach()
{
  return _vcrt_getptd_noexit() != 0;
}

```

## disassembly

```asm
0x180008bec  sub     rsp, 28h
0x180008bf0  call    __vcrt_getptd_noexit
0x180008bf5  test    rax, rax
0x180008bf8  setnz   al
0x180008bfb  add     rsp, 28h
0x180008bff  retn
```
