# __scrt_dllmain_after_initialize_c

- ea: `0x18000467c`
- end: `0x1800046b0`
- name: `__scrt_dllmain_after_initialize_c`
- size: `52`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180004298`

## callees

- `0x18000467c`
- `0x180004f18`
- `0x1800051a4`
- `0x1800052ca`
- `0x1800052ee`
- `0x180027350`

## pseudocode

```c
char _scrt_dllmain_after_initialize_c()
{
  _crt_argv_mode IsLocalProfileAvailable; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    _isa_available_init();
  }
  else
  {
    IsLocalProfileAvailable = (unsigned int)Microsoft::Windows::Autopilot::RegistryPolicyManager::IsLocalProfileAvailable();
    if ( o__configure_narrow_argv_0(IsLocalProfileAvailable) )
      return 0;
    initialize_narrow_environment();
  }
  return 1;
}

```

## disassembly

```asm
0x18000467c  sub     rsp, 28h
0x180004680  call    __scrt_is_ucrt_dll_in_use
0x180004685  test    eax, eax
0x180004687  jz      short loc_180004690
0x180004689  call    __isa_available_init
0x18000468e  jmp     short loc_1800046A9
0x180004690  call    ?IsLocalProfileAvailable@RegistryPolicyManager@Autopilot@Windows@Microsoft@@UEBA?AW4ProfileDataState@234@XZ; Microsoft::Windows::Autopilot::RegistryPolicyManager::IsLocalProfileAvailable(void)
0x180004695  mov     ecx, eax; mode
0x180004697  call    _o__configure_narrow_argv_0
0x18000469c  test    eax, eax
0x18000469e  jz      short loc_1800046A4
0x1800046a0  xor     al, al
0x1800046a2  jmp     short loc_1800046AB
0x1800046a4  call    _initialize_narrow_environment
0x1800046a9  mov     al, 1
0x1800046ab  add     rsp, 28h
0x1800046af  retn
```
