# __scrt_dllmain_after_initialize_c

- ea: `0x18000228c`
- end: `0x1800022c0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001ea8`

## callees

- `0x18000228c`
- `0x180002828`
- `0x180002ab4`
- `0x180002ac0`
- `0x180002b5e`
- `0x180002b82`

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
0x18000228c  sub     rsp, 28h
0x180002290  call    __scrt_is_ucrt_dll_in_use
0x180002295  test    eax, eax
0x180002297  jz      short loc_1800022A0
0x180002299  call    __isa_available_init
0x18000229e  jmp     short loc_1800022B9
0x1800022a0  call    _get_startup_argv_mode
0x1800022a5  mov     ecx, eax; mode
0x1800022a7  call    _o__configure_narrow_argv_0
0x1800022ac  test    eax, eax
0x1800022ae  jz      short loc_1800022B4
0x1800022b0  xor     al, al
0x1800022b2  jmp     short loc_1800022BB
0x1800022b4  call    _initialize_narrow_environment
0x1800022b9  mov     al, 1
0x1800022bb  add     rsp, 28h
0x1800022bf  retn
```
