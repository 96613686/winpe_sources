# ___scrt_dllmain_after_initialize_c

- ea: `0x10010d71`
- end: `0x10010d9c`
- name: `___scrt_dllmain_after_initialize_c`
- size: `43`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x10010784`

## callees

- `0x10010d71`
- `0x100111db`
- `0x10011372`
- `0x10011376`
- `0x100166d0`
- `0x100168c5`

## pseudocode

```c
char __scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode v0; // eax

  if ( __scrt_is_ucrt_dll_in_use() )
  {
    __isa_available_init();
  }
  else
  {
    v0 = sub_10011372();
    if ( _configure_narrow_argv(v0) )
      return 0;
    common_initialize_environment_nolock<char>();
  }
  return 1;
}

```

## disassembly

```asm
0x10010d71  call    ___scrt_is_ucrt_dll_in_use
0x10010d76  test    eax, eax
0x10010d78  jz      short loc_10010D81
0x10010d7a  call    ___isa_available_init
0x10010d7f  jmp     short loc_10010D99
0x10010d81  call    sub_10011372
0x10010d86  push    eax; mode
0x10010d87  call    __configure_narrow_argv
0x10010d8c  pop     ecx
0x10010d8d  test    eax, eax
0x10010d8f  jz      short loc_10010D94
0x10010d91  xor     al, al
0x10010d93  retn
0x10010d94  call    j_??$common_initialize_environment_nolock@D@@YAHXZ
0x10010d99  mov     al, 1
0x10010d9b  retn
```
