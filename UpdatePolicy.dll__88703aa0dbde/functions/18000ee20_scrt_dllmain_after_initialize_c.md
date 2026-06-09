# __scrt_dllmain_after_initialize_c

- ea: `0x18000ee20`
- end: `0x18000ee54`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000f238`

## callees

- `0x18000ec61`
- `0x18000ec9d`
- `0x18000ee20`
- `0x18000f738`
- `0x18000f9d4`
- `0x18000f9e0`

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
0x18000ee20  sub     rsp, 28h
0x18000ee24  call    __scrt_is_ucrt_dll_in_use
0x18000ee29  test    eax, eax
0x18000ee2b  jz      short loc_18000EE34
0x18000ee2d  call    __isa_available_init
0x18000ee32  jmp     short loc_18000EE4D
0x18000ee34  call    _get_startup_argv_mode
0x18000ee39  mov     ecx, eax; mode
0x18000ee3b  call    _o__configure_narrow_argv_0
0x18000ee40  test    eax, eax
0x18000ee42  jz      short loc_18000EE48
0x18000ee44  xor     al, al
0x18000ee46  jmp     short loc_18000EE4F
0x18000ee48  call    _initialize_narrow_environment
0x18000ee4d  mov     al, 1
0x18000ee4f  add     rsp, 28h
0x18000ee53  retn
```
