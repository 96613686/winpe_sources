# __scrt_dllmain_after_initialize_c

- ea: `0x180003014`
- end: `0x180003048`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180002b48`

## callees

- `0x180003014`
- `0x180003470`
- `0x1800038d0`
- `0x18000396a`
- `0x18000398e`
- `0x180005240`

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
0x180003014  sub     rsp, 28h
0x180003018  call    __scrt_is_ucrt_dll_in_use
0x18000301d  test    eax, eax
0x18000301f  jz      short loc_180003028
0x180003021  call    __isa_available_init
0x180003026  jmp     short loc_180003041
0x180003028  call    ?AddRef@CRegObject@ATL@@UEAAKXZ; ATL::CRegObject::AddRef(void)
0x18000302d  mov     ecx, eax; mode
0x18000302f  call    _o__configure_narrow_argv_0
0x180003034  test    eax, eax
0x180003036  jz      short loc_18000303C
0x180003038  xor     al, al
0x18000303a  jmp     short loc_180003043
0x18000303c  call    _initialize_narrow_environment
0x180003041  mov     al, 1
0x180003043  add     rsp, 28h
0x180003047  retn
```
