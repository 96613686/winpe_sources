# __scrt_initialize_thread_safe_statics(void)

- ea: `0x40d0a0`
- end: `0x40d0c7`
- name: `?__scrt_initialize_thread_safe_statics@@YAHXZ`
- size: `39`
- prototype: `int __cdecl()`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x40d0a0`
- `0x40d0c7`
- `0x40d33b`
- `0x40d4c8`
- `0x40d86c`

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
0x40d0a0  call    ?__scrt_initialize_thread_safe_statics_platform_specific@@YAXXZ
0x40d0a5  push    0
0x40d0a7  call    ___scrt_initialize_onexit_tables
0x40d0ac  pop     ecx
0x40d0ad  test    al, al
0x40d0af  jz      short loc_40D0BF
0x40d0b1  push    offset ?__scrt_uninitialize_thread_safe_statics@@YAXXZ; void (__cdecl *)()
0x40d0b6  call    _atexit
0x40d0bb  pop     ecx
0x40d0bc  xor     eax, eax
0x40d0be  retn
0x40d0bf  push    7
0x40d0c1  call    ___scrt_fastfail
0x40d0c6  int     3; Trap to Debugger
```
