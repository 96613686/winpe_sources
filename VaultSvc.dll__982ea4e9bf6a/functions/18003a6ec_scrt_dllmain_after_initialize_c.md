# __scrt_dllmain_after_initialize_c

- ea: `0x18003a6ec`
- end: `0x18003a720`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18003a268`

## callees

- `0x18003a6ec`
- `0x18003ab20`
- `0x18003adac`
- `0x18003adb8`
- `0x18003ae66`
- `0x18003ae8a`

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
0x18003a6ec  sub     rsp, 28h
0x18003a6f0  call    __scrt_is_ucrt_dll_in_use
0x18003a6f5  test    eax, eax
0x18003a6f7  jz      short loc_18003A700
0x18003a6f9  call    __isa_available_init
0x18003a6fe  jmp     short loc_18003A719
0x18003a700  call    _get_startup_argv_mode
0x18003a705  mov     ecx, eax; mode
0x18003a707  call    _o__configure_narrow_argv_0
0x18003a70c  test    eax, eax
0x18003a70e  jz      short loc_18003A714
0x18003a710  xor     al, al
0x18003a712  jmp     short loc_18003A71B
0x18003a714  call    _initialize_narrow_environment
0x18003a719  mov     al, 1
0x18003a71b  add     rsp, 28h
0x18003a71f  retn
```
