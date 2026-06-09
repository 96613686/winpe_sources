# __scrt_dllmain_after_initialize_c

- ea: `0x180001674`
- end: `0x1800016a8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800012f8`

## callees

- `0x180001674`
- `0x180001c10`
- `0x180001e9c`
- `0x180001ea8`
- `0x180001fde`
- `0x180002002`

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
0x180001674  sub     rsp, 28h
0x180001678  call    __scrt_is_ucrt_dll_in_use
0x18000167d  test    eax, eax
0x18000167f  jz      short loc_180001688
0x180001681  call    __isa_available_init
0x180001686  jmp     short loc_1800016A1
0x180001688  call    _get_startup_argv_mode
0x18000168d  mov     ecx, eax; mode
0x18000168f  call    _o__configure_narrow_argv_0
0x180001694  test    eax, eax
0x180001696  jz      short loc_18000169C
0x180001698  xor     al, al
0x18000169a  jmp     short loc_1800016A3
0x18000169c  call    _initialize_narrow_environment
0x1800016a1  mov     al, 1
0x1800016a3  add     rsp, 28h
0x1800016a7  retn
```
