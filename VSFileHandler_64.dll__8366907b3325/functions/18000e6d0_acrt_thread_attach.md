# __acrt_thread_attach

- ea: `0x18000e6d0`
- end: `0x18000e6e4`
- name: `__acrt_thread_attach`
- size: `20`
- prototype: `__crt_bool __cdecl()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800077a8`

## callees

- `0x180010420`

## pseudocode

```c
__crt_bool __cdecl _acrt_thread_attach()
{
  return _acrt_getptd_noexit() != 0;
}

```

## disassembly

```asm
0x18000e6d0  sub     rsp, 28h
0x18000e6d4  call    __acrt_getptd_noexit
0x18000e6d9  test    rax, rax
0x18000e6dc  setnz   al
0x18000e6df  add     rsp, 28h
0x18000e6e3  retn
```
