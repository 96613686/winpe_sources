# __scrt_dllmain_after_initialize_c

- ea: `0x180003704`
- end: `0x180003738`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180003388`

## callees

- `0x180003704`
- `0x180003c70`
- `0x180003efc`
- `0x180003f08`
- `0x180003fae`
- `0x180003fd2`

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
0x180003704  sub     rsp, 28h
0x180003708  call    __scrt_is_ucrt_dll_in_use
0x18000370d  test    eax, eax
0x18000370f  jz      short loc_180003718
0x180003711  call    __isa_available_init
0x180003716  jmp     short loc_180003731
0x180003718  call    _get_startup_argv_mode
0x18000371d  mov     ecx, eax; mode
0x18000371f  call    _o__configure_narrow_argv_0
0x180003724  test    eax, eax
0x180003726  jz      short loc_18000372C
0x180003728  xor     al, al
0x18000372a  jmp     short loc_180003733
0x18000372c  call    _initialize_narrow_environment
0x180003731  mov     al, 1
0x180003733  add     rsp, 28h
0x180003737  retn
```
