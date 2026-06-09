# __scrt_dllmain_after_initialize_c

- ea: `0x18000ebd4`
- end: `0x18000ec08`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e858`

## callees

- `0x18000ebd4`
- `0x18000f160`
- `0x18000f3ec`
- `0x18000f3f8`
- `0x18000f452`
- `0x18000f476`

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
0x18000ebd4  sub     rsp, 28h
0x18000ebd8  call    __scrt_is_ucrt_dll_in_use
0x18000ebdd  test    eax, eax
0x18000ebdf  jz      short loc_18000EBE8
0x18000ebe1  call    __isa_available_init
0x18000ebe6  jmp     short loc_18000EC01
0x18000ebe8  call    _get_startup_argv_mode
0x18000ebed  mov     ecx, eax; mode
0x18000ebef  call    _o__configure_narrow_argv_0
0x18000ebf4  test    eax, eax
0x18000ebf6  jz      short loc_18000EBFC
0x18000ebf8  xor     al, al
0x18000ebfa  jmp     short loc_18000EC03
0x18000ebfc  call    _initialize_narrow_environment
0x18000ec01  mov     al, 1
0x18000ec03  add     rsp, 28h
0x18000ec07  retn
```
