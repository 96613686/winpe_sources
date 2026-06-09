# __scrt_dllmain_after_initialize_c

- ea: `0x180021ba8`
- end: `0x180021bdc`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180021718`

## callees

- `0x180014ad0`
- `0x180021ba8`
- `0x180021fd0`
- `0x18002225c`
- `0x1800222be`
- `0x1800222e2`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  CMetadataHandler *v0; // rcx
  _crt_argv_mode v1; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v1 = (unsigned int)CMetadataHandler::AllowFmeWhenShallowDirty(v0);
    if ( o__configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180021ba8  sub     rsp, 28h
0x180021bac  call    __scrt_is_ucrt_dll_in_use
0x180021bb1  test    eax, eax
0x180021bb3  jz      short loc_180021BBC
0x180021bb5  call    __isa_available_init
0x180021bba  jmp     short loc_180021BD5
0x180021bbc  call    ?AllowFmeWhenShallowDirty@CMetadataHandler@@MEAAHXZ; CMetadataHandler::AllowFmeWhenShallowDirty(void)
0x180021bc1  mov     ecx, eax; mode
0x180021bc3  call    _o__configure_narrow_argv_0
0x180021bc8  test    eax, eax
0x180021bca  jz      short loc_180021BD0
0x180021bcc  xor     al, al
0x180021bce  jmp     short loc_180021BD7
0x180021bd0  call    _initialize_narrow_environment
0x180021bd5  mov     al, 1
0x180021bd7  add     rsp, 28h
0x180021bdb  retn
```
