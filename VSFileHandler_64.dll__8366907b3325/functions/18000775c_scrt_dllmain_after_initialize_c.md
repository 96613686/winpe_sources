# __scrt_dllmain_after_initialize_c

- ea: `0x18000775c`
- end: `0x180007790`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800073e0`

## callees

- `0x180002470`
- `0x18000775c`
- `0x180008078`
- `0x180008344`
- `0x18000dda0`
- `0x18000e150`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  CVsShellExtHandler *v0; // rcx
  _crt_argv_mode IsDirty; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    IsDirty = (unsigned int)CVsShellExtHandler::IsDirty(v0);
    if ( configure_narrow_argv(IsDirty) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x18000775c  sub     rsp, 28h
0x180007760  call    __scrt_is_ucrt_dll_in_use
0x180007765  test    eax, eax
0x180007767  jz      short loc_180007770
0x180007769  call    __isa_available_init
0x18000776e  jmp     short loc_180007789
0x180007770  call    ?IsDirty@CVsShellExtHandler@@UEAAJXZ; CVsShellExtHandler::IsDirty(void)
0x180007775  mov     ecx, eax; mode
0x180007777  call    _configure_narrow_argv
0x18000777c  test    eax, eax
0x18000777e  jz      short loc_180007784
0x180007780  xor     al, al
0x180007782  jmp     short loc_18000778B
0x180007784  call    _initialize_narrow_environment
0x180007789  mov     al, 1
0x18000778b  add     rsp, 28h
0x18000778f  retn
```
