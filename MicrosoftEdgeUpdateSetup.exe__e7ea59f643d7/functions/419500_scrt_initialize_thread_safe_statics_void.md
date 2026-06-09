# __scrt_initialize_thread_safe_statics(void)

- ea: `0x419500`
- end: `0x419527`
- name: `?__scrt_initialize_thread_safe_statics@@YAHXZ`
- size: `39`
- prototype: `int __cdecl()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x4084b9`
- `0x408646`
- `0x40877f`
- `0x419500`
- `0x419527`

## pseudocode

```c
int __cdecl __scrt_initialize_thread_safe_statics()
{
  __scrt_initialize_thread_safe_statics_platform_specific();
  if ( !(unsigned __int8)__scrt_initialize_onexit_tables(0) )
  {
    __scrt_fastfail(7);
    __debugbreak();
  }
  atexit(__scrt_uninitialize_thread_safe_statics);
  return 0;
}

```

## disassembly

```asm
0x419500  call    ?__scrt_initialize_thread_safe_statics_platform_specific@@YAXXZ
0x419505  push    0
0x419507  call    ___scrt_initialize_onexit_tables
0x41950c  pop     ecx
0x41950d  test    al, al
0x41950f  jz      short loc_41951F
0x419511  push    offset ?__scrt_uninitialize_thread_safe_statics@@YAXXZ; void (__cdecl *)()
0x419516  call    _atexit
0x41951b  pop     ecx
0x41951c  xor     eax, eax
0x41951e  retn
0x41951f  push    7
0x419521  call    ___scrt_fastfail
0x419526  int     3; Trap to Debugger
```
