# __scrt_dllmain_after_initialize_c

- ea: `0x18002ac38`
- end: `0x18002ac6c`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18002a7a8`

## callees

- `0x18002ac38`
- `0x18002b000`
- `0x18002b28c`
- `0x18002b298`
- `0x18002b2fe`
- `0x18002b316`

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
0x18002ac38  sub     rsp, 28h
0x18002ac3c  call    __scrt_is_ucrt_dll_in_use
0x18002ac41  test    eax, eax
0x18002ac43  jz      short loc_18002AC4C
0x18002ac45  call    __isa_available_init
0x18002ac4a  jmp     short loc_18002AC65
0x18002ac4c  call    _get_startup_argv_mode
0x18002ac51  mov     ecx, eax; mode
0x18002ac53  call    _o__configure_narrow_argv_0
0x18002ac58  test    eax, eax
0x18002ac5a  jz      short loc_18002AC60
0x18002ac5c  xor     al, al
0x18002ac5e  jmp     short loc_18002AC67
0x18002ac60  call    _initialize_narrow_environment
0x18002ac65  mov     al, 1
0x18002ac67  add     rsp, 28h
0x18002ac6b  retn
```
