# __scrt_dllmain_after_initialize_c

- ea: `0x180001b24`
- end: `0x180001b58`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800017a8`

## callees

- `0x180001b24`
- `0x1800020e0`
- `0x18000236c`
- `0x180002378`
- `0x180002616`
- `0x18000263a`

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
0x180001b24  sub     rsp, 28h
0x180001b28  call    __scrt_is_ucrt_dll_in_use
0x180001b2d  test    eax, eax
0x180001b2f  jz      short loc_180001B38
0x180001b31  call    __isa_available_init
0x180001b36  jmp     short loc_180001B51
0x180001b38  call    _get_startup_argv_mode
0x180001b3d  mov     ecx, eax; mode
0x180001b3f  call    _o__configure_narrow_argv_0
0x180001b44  test    eax, eax
0x180001b46  jz      short loc_180001B4C
0x180001b48  xor     al, al
0x180001b4a  jmp     short loc_180001B53
0x180001b4c  call    _initialize_narrow_environment
0x180001b51  mov     al, 1
0x180001b53  add     rsp, 28h
0x180001b57  retn
```
