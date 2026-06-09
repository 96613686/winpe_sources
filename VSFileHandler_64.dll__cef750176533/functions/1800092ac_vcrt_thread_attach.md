# __vcrt_thread_attach

- ea: `0x1800092ac`
- end: `0x1800092c0`
- name: `__vcrt_thread_attach`
- size: `20`
- prototype: `__vcrt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800077a8`

## callees

- `0x180009534`

## pseudocode

```c
__vcrt_bool __cdecl _vcrt_thread_attach()
{
  return _vcrt_getptd_noexit() != 0;
}

```

## disassembly

```asm
0x1800092ac  sub     rsp, 28h
0x1800092b0  call    __vcrt_getptd_noexit
0x1800092b5  test    rax, rax
0x1800092b8  setnz   al
0x1800092bb  add     rsp, 28h
0x1800092bf  retn
```
