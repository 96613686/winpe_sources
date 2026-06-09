# __scrt_dllmain_after_initialize_c

- ea: `0x180002784`
- end: `0x1800027b8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002338`

## callees

- `0x180002784`
- `0x180002ca4`
- `0x180003100`
- `0x18000310c`
- `0x1800031fe`
- `0x180003222`

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
0x180002784  sub     rsp, 28h
0x180002788  call    __scrt_is_ucrt_dll_in_use
0x18000278d  test    eax, eax
0x18000278f  jz      short loc_180002798
0x180002791  call    __isa_available_init
0x180002796  jmp     short loc_1800027B1
0x180002798  call    _get_startup_argv_mode
0x18000279d  mov     ecx, eax; mode
0x18000279f  call    _o__configure_narrow_argv_0
0x1800027a4  test    eax, eax
0x1800027a6  jz      short loc_1800027AC
0x1800027a8  xor     al, al
0x1800027aa  jmp     short loc_1800027B3
0x1800027ac  call    _initialize_narrow_environment
0x1800027b1  mov     al, 1
0x1800027b3  add     rsp, 28h
0x1800027b7  retn
```
