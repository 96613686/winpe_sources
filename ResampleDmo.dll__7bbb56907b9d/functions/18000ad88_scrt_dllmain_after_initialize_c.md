# __scrt_dllmain_after_initialize_c

- ea: `0x18000ad88`
- end: `0x18000adbc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a878`

## callees

- `0x18000ad88`
- `0x18000b344`
- `0x18000b5d0`
- `0x18000b692`
- `0x18000b6b6`
- `0x1800818f0`

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
0x18000ad88  sub     rsp, 28h
0x18000ad8c  call    __scrt_is_ucrt_dll_in_use
0x18000ad91  test    eax, eax
0x18000ad93  jz      short loc_18000AD9C
0x18000ad95  call    __isa_available_init
0x18000ad9a  jmp     short loc_18000ADB5
0x18000ad9c  call    _get_startup_argv_mode
0x18000ada1  mov     ecx, eax; mode
0x18000ada3  call    _o__configure_narrow_argv_0
0x18000ada8  test    eax, eax
0x18000adaa  jz      short loc_18000ADB0
0x18000adac  xor     al, al
0x18000adae  jmp     short loc_18000ADB7
0x18000adb0  call    _initialize_narrow_environment
0x18000adb5  mov     al, 1
0x18000adb7  add     rsp, 28h
0x18000adbb  retn
```
