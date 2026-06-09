# __scrt_dllmain_after_initialize_c

- ea: `0x180008ae4`
- end: `0x180008b18`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180008768`

## callees

- `0x180008ae4`
- `0x180009050`
- `0x1800092dc`
- `0x1800092e8`
- `0x18000938e`
- `0x1800093b2`

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
0x180008ae4  sub     rsp, 28h
0x180008ae8  call    __scrt_is_ucrt_dll_in_use
0x180008aed  test    eax, eax
0x180008aef  jz      short loc_180008AF8
0x180008af1  call    __isa_available_init
0x180008af6  jmp     short loc_180008B11
0x180008af8  call    _get_startup_argv_mode
0x180008afd  mov     ecx, eax; mode
0x180008aff  call    _o__configure_narrow_argv_0
0x180008b04  test    eax, eax
0x180008b06  jz      short loc_180008B0C
0x180008b08  xor     al, al
0x180008b0a  jmp     short loc_180008B13
0x180008b0c  call    _initialize_narrow_environment
0x180008b11  mov     al, 1
0x180008b13  add     rsp, 28h
0x180008b17  retn
```
