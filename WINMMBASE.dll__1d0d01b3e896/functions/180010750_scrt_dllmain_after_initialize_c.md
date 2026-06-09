# __scrt_dllmain_after_initialize_c

- ea: `0x180010750`
- end: `0x180010784`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x1800103a8`

## callees

- `0x180010750`
- `0x180010ca8`
- `0x180010f34`
- `0x180010f9a`
- `0x180010fbe`
- `0x18001ad90`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  CWinmmNotificationClient *v0; // rcx
  _crt_argv_mode v1; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    v1 = CWinmmNotificationClient::Release(v0);
    if ( o__configure_narrow_argv_0(v1) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x180010750  sub     rsp, 28h
0x180010754  call    __scrt_is_ucrt_dll_in_use
0x180010759  test    eax, eax
0x18001075b  jz      short loc_180010764
0x18001075d  call    __isa_available_init
0x180010762  jmp     short loc_18001077D
0x180010764  call    ?Release@CWinmmNotificationClient@@UEAAKXZ; CWinmmNotificationClient::Release(void)
0x180010769  mov     ecx, eax; mode
0x18001076b  call    _o__configure_narrow_argv_0
0x180010770  test    eax, eax
0x180010772  jz      short loc_180010778
0x180010774  xor     al, al
0x180010776  jmp     short loc_18001077F
0x180010778  call    _initialize_narrow_environment
0x18001077d  mov     al, 1
0x18001077f  add     rsp, 28h
0x180010783  retn
```
