# __scrt_dllmain_after_initialize_c

- ea: `0x180001f34`
- end: `0x180001f68`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180001b38`

## callees

- `0x180001f34`
- `0x180002508`
- `0x180002794`
- `0x18000282a`
- `0x18000284e`
- `0x180003fd0`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  ATL::CRegObject *v0; // rcx
  _crt_argv_mode v1; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v1 = ATL::CRegObject::AddRef(v0);
    if ( o__configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180001f34  sub     rsp, 28h
0x180001f38  call    __scrt_is_ucrt_dll_in_use
0x180001f3d  test    eax, eax
0x180001f3f  jz      short loc_180001F48
0x180001f41  call    __isa_available_init
0x180001f46  jmp     short loc_180001F61
0x180001f48  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x180001f4d  mov     ecx, eax; mode
0x180001f4f  call    _o__configure_narrow_argv_0
0x180001f54  test    eax, eax
0x180001f56  jz      short loc_180001F5C
0x180001f58  xor     al, al
0x180001f5a  jmp     short loc_180001F63
0x180001f5c  call    _initialize_narrow_environment
0x180001f61  mov     al, 1
0x180001f63  add     rsp, 28h
0x180001f67  retn
```
