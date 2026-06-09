# __scrt_dllmain_after_initialize_c

- ea: `0x180012e78`
- end: `0x180012eac`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180012ab8`

## callees

- `0x180012e78`
- `0x180013580`
- `0x18001380c`
- `0x180013818`
- `0x1800138be`
- `0x1800138e2`

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
0x180012e78  sub     rsp, 28h
0x180012e7c  call    __scrt_is_ucrt_dll_in_use
0x180012e81  test    eax, eax
0x180012e83  jz      short loc_180012E8C
0x180012e85  call    __isa_available_init
0x180012e8a  jmp     short loc_180012EA5
0x180012e8c  call    _get_startup_argv_mode
0x180012e91  mov     ecx, eax; mode
0x180012e93  call    _o__configure_narrow_argv_0
0x180012e98  test    eax, eax
0x180012e9a  jz      short loc_180012EA0
0x180012e9c  xor     al, al
0x180012e9e  jmp     short loc_180012EA7
0x180012ea0  call    _initialize_narrow_environment
0x180012ea5  mov     al, 1
0x180012ea7  add     rsp, 28h
0x180012eab  retn
```
