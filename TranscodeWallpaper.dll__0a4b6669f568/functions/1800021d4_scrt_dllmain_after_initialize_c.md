# __scrt_dllmain_after_initialize_c

- ea: `0x1800021d4`
- end: `0x180002208`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001e58`

## callees

- `0x1800021d4`
- `0x1800027d0`
- `0x180002a5c`
- `0x180002a68`
- `0x180002c0e`
- `0x180002c32`

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
0x1800021d4  sub     rsp, 28h
0x1800021d8  call    __scrt_is_ucrt_dll_in_use
0x1800021dd  test    eax, eax
0x1800021df  jz      short loc_1800021E8
0x1800021e1  call    __isa_available_init
0x1800021e6  jmp     short loc_180002201
0x1800021e8  call    _get_startup_argv_mode
0x1800021ed  mov     ecx, eax; mode
0x1800021ef  call    _o__configure_narrow_argv_0
0x1800021f4  test    eax, eax
0x1800021f6  jz      short loc_1800021FC
0x1800021f8  xor     al, al
0x1800021fa  jmp     short loc_180002203
0x1800021fc  call    _initialize_narrow_environment
0x180002201  mov     al, 1
0x180002203  add     rsp, 28h
0x180002207  retn
```
