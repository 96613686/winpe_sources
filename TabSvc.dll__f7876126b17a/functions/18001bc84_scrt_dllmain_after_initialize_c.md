# __scrt_dllmain_after_initialize_c

- ea: `0x18001bc84`
- end: `0x18001bcb8`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18001b8c8`

## callees

- `0x18001bc84`
- `0x18001c248`
- `0x18001c4d4`
- `0x18001c5de`
- `0x18001c602`
- `0x180023250`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  COobeTabTipProcessInfo *v0; // rcx
  _crt_argv_mode IsOobe; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    IsOobe = (unsigned int)COobeTabTipProcessInfo::IsOobe(v0);
    if ( o__configure_narrow_argv_0(IsOobe) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x18001bc84  sub     rsp, 28h
0x18001bc88  call    __scrt_is_ucrt_dll_in_use
0x18001bc8d  test    eax, eax
0x18001bc8f  jz      short loc_18001BC98
0x18001bc91  call    __isa_available_init
0x18001bc96  jmp     short loc_18001BCB1
0x18001bc98  call    ?IsOobe@COobeTabTipProcessInfo@@UEBAHXZ; COobeTabTipProcessInfo::IsOobe(void)
0x18001bc9d  mov     ecx, eax; mode
0x18001bc9f  call    _o__configure_narrow_argv_0
0x18001bca4  test    eax, eax
0x18001bca6  jz      short loc_18001BCAC
0x18001bca8  xor     al, al
0x18001bcaa  jmp     short loc_18001BCB3
0x18001bcac  call    _initialize_narrow_environment
0x18001bcb1  mov     al, 1
0x18001bcb3  add     rsp, 28h
0x18001bcb7  retn
```
