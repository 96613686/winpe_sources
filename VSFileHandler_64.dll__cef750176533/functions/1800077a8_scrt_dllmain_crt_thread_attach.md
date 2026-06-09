# __scrt_dllmain_crt_thread_attach

- ea: `0x1800077a8`
- end: `0x1800077d0`
- name: `__scrt_dllmain_crt_thread_attach`
- size: `40`
- prototype: `char()`
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x180007390`

## callees

- `0x1800077a8`
- `0x1800092ac`
- `0x1800092c0`
- `0x18000e6d0`

## pseudocode

```c
char _scrt_dllmain_crt_thread_attach()
{
  if ( !_vcrt_thread_attach() )
    return 0;
  if ( !_acrt_thread_attach() )
  {
    _vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x1800077a8  sub     rsp, 28h
0x1800077ac  call    __vcrt_thread_attach
0x1800077b1  test    al, al
0x1800077b3  jnz     short loc_1800077B9
0x1800077b5  xor     al, al
0x1800077b7  jmp     short loc_1800077CB
0x1800077b9  call    __acrt_thread_attach
0x1800077be  test    al, al
0x1800077c0  jnz     short loc_1800077C9
0x1800077c2  call    __vcrt_thread_detach
0x1800077c7  jmp     short loc_1800077B5
0x1800077c9  mov     al, 1
0x1800077cb  add     rsp, 28h
0x1800077cf  retn
```
