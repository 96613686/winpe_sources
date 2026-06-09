# __scrt_dllmain_after_initialize_c

- ea: `0x18000170c`
- end: `0x180001740`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: `char()`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001348`

## callees

- `0x18000170c`
- `0x180001c68`
- `0x180001ef4`
- `0x180001f00`
- `0x180001f8e`
- `0x180001fb2`

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
0x18000170c  sub     rsp, 28h
0x180001710  call    __scrt_is_ucrt_dll_in_use
0x180001715  test    eax, eax
0x180001717  jz      short loc_180001720
0x180001719  call    __isa_available_init
0x18000171e  jmp     short loc_180001739
0x180001720  call    _get_startup_argv_mode
0x180001725  mov     ecx, eax; mode
0x180001727  call    _o__configure_narrow_argv_0
0x18000172c  test    eax, eax
0x18000172e  jz      short loc_180001734
0x180001730  xor     al, al
0x180001732  jmp     short loc_18000173B
0x180001734  call    _initialize_narrow_environment
0x180001739  mov     al, 1
0x18000173b  add     rsp, 28h
0x18000173f  retn
```
