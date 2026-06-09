# __scrt_dllmain_after_initialize_c

- ea: `0x180002124`
- end: `0x180002158`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001da8`

## callees

- `0x180002124`
- `0x1800026e0`
- `0x18000296c`
- `0x180002978`
- `0x180002a8e`
- `0x180002ab2`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode startup_argv_mode; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    startup_argv_mode = get_startup_argv_mode();
    if ( o__configure_narrow_argv_0(startup_argv_mode) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180002124  sub     rsp, 28h
0x180002128  call    __scrt_is_ucrt_dll_in_use
0x18000212d  test    eax, eax
0x18000212f  jz      short loc_180002138
0x180002131  call    __isa_available_init
0x180002136  jmp     short loc_180002151
0x180002138  call    _get_startup_argv_mode
0x18000213d  mov     ecx, eax; mode
0x18000213f  call    _o__configure_narrow_argv_0
0x180002144  test    eax, eax
0x180002146  jz      short loc_18000214C
0x180002148  xor     al, al
0x18000214a  jmp     short loc_180002153
0x18000214c  call    _initialize_narrow_environment
0x180002151  mov     al, 1
0x180002153  add     rsp, 28h
0x180002157  retn
```
