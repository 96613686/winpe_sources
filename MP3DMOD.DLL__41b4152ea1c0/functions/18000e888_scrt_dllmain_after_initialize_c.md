# __scrt_dllmain_after_initialize_c

- ea: `0x18000e888`
- end: `0x18000e8bc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e428`

## callees

- `0x18000e888`
- `0x18000ec38`
- `0x18000eec4`
- `0x18000eed0`
- `0x18000ef4e`
- `0x18000ef66`

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
0x18000e888  sub     rsp, 28h
0x18000e88c  call    __scrt_is_ucrt_dll_in_use
0x18000e891  test    eax, eax
0x18000e893  jz      short loc_18000E89C
0x18000e895  call    __isa_available_init
0x18000e89a  jmp     short loc_18000E8B5
0x18000e89c  call    _get_startup_argv_mode
0x18000e8a1  mov     ecx, eax; mode
0x18000e8a3  call    _o__configure_narrow_argv_0
0x18000e8a8  test    eax, eax
0x18000e8aa  jz      short loc_18000E8B0
0x18000e8ac  xor     al, al
0x18000e8ae  jmp     short loc_18000E8B7
0x18000e8b0  call    _initialize_narrow_environment
0x18000e8b5  mov     al, 1
0x18000e8b7  add     rsp, 28h
0x18000e8bb  retn
```
