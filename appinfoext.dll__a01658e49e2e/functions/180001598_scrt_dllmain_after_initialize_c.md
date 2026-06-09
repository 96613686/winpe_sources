# __scrt_dllmain_after_initialize_c

- ea: `0x180001598`
- end: `0x1800015cc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800010e8`

## callees

- `0x180001598`
- `0x180001960`
- `0x180001bec`
- `0x180001bf8`
- `0x180001c56`
- `0x180001c6e`

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
0x180001598  sub     rsp, 28h
0x18000159c  call    __scrt_is_ucrt_dll_in_use
0x1800015a1  test    eax, eax
0x1800015a3  jz      short loc_1800015AC
0x1800015a5  call    __isa_available_init
0x1800015aa  jmp     short loc_1800015C5
0x1800015ac  call    _get_startup_argv_mode
0x1800015b1  mov     ecx, eax; mode
0x1800015b3  call    _o__configure_narrow_argv_0
0x1800015b8  test    eax, eax
0x1800015ba  jz      short loc_1800015C0
0x1800015bc  xor     al, al
0x1800015be  jmp     short loc_1800015C7
0x1800015c0  call    _initialize_narrow_environment
0x1800015c5  mov     al, 1
0x1800015c7  add     rsp, 28h
0x1800015cb  retn
```
