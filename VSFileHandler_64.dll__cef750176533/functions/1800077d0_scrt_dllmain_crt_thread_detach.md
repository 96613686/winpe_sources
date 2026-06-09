# __scrt_dllmain_crt_thread_detach

- ea: `0x1800077d0`
- end: `0x1800077e5`
- name: `__scrt_dllmain_crt_thread_detach`
- size: `21`
- prototype: `char()`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x180007390`

## callees

- `0x1800092c0`
- `0x18000e6e4`

## pseudocode

```c
char _scrt_dllmain_crt_thread_detach()
{
  _acrt_thread_detach();
  _vcrt_thread_detach();
  return 1;
}

```

## disassembly

```asm
0x1800077d0  sub     rsp, 28h
0x1800077d4  call    __acrt_thread_detach
0x1800077d9  call    __vcrt_thread_detach
0x1800077de  mov     al, 1
0x1800077e0  add     rsp, 28h
0x1800077e4  retn
```
