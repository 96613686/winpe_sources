# __scrt_dllmain_after_initialize_c

- ea: `0x18000d0f4`
- end: `0x18000d128`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d780`

## callees

- `0x180003360`
- `0x18000d0f4`
- `0x18000da90`
- `0x18000dc34`
- `0x18000e0fc`
- `0x18000e102`

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
    if ( configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment_0();
  }
  return 1;
}

```

## disassembly

```asm
0x18000d0f4  sub     rsp, 28h
0x18000d0f8  call    __scrt_is_ucrt_dll_in_use
0x18000d0fd  test    eax, eax
0x18000d0ff  jz      short loc_18000D108
0x18000d101  call    __isa_available_init
0x18000d106  jmp     short loc_18000D121
0x18000d108  call    ?AddRef@CRegObject@ATL@@UEAAKXZ
0x18000d10d  mov     ecx, eax; mode
0x18000d10f  call    _configure_narrow_argv_0
0x18000d114  test    eax, eax
0x18000d116  jz      short loc_18000D11C
0x18000d118  xor     al, al
0x18000d11a  jmp     short loc_18000D123
0x18000d11c  call    _initialize_narrow_environment_0
0x18000d121  mov     al, 1
0x18000d123  add     rsp, 28h
0x18000d127  retn
```
