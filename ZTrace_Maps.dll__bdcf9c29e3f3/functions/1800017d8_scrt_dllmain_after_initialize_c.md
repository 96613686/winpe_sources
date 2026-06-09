# __scrt_dllmain_after_initialize_c

- ea: `0x1800017d8`
- end: `0x18000180c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001408`

## callees

- `0x1800017d8`
- `0x180001ef8`
- `0x180002184`
- `0x180002190`
- `0x180002252`
- `0x180002276`

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
0x1800017d8  sub     rsp, 28h
0x1800017dc  call    __scrt_is_ucrt_dll_in_use
0x1800017e1  test    eax, eax
0x1800017e3  jz      short loc_1800017EC
0x1800017e5  call    __isa_available_init
0x1800017ea  jmp     short loc_180001805
0x1800017ec  call    _get_startup_argv_mode
0x1800017f1  mov     ecx, eax; mode
0x1800017f3  call    _o__configure_narrow_argv_0
0x1800017f8  test    eax, eax
0x1800017fa  jz      short loc_180001800
0x1800017fc  xor     al, al
0x1800017fe  jmp     short loc_180001807
0x180001800  call    _initialize_narrow_environment
0x180001805  mov     al, 1
0x180001807  add     rsp, 28h
0x18000180b  retn
```
