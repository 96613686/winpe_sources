# __scrt_dllmain_uninitialize_c

- ea: `0x180004de0`
- end: `0x180004e10`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x180004a58`

## callees

- `0x180004de0`
- `0x18000554c`
- `0x180005622`
- `0x180005646`
- `0x18000a2b0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = HidDeviceCapabilityHandler::AccessCheckResult();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180004de0  sub     rsp, 28h
0x180004de4  call    __scrt_is_ucrt_dll_in_use
0x180004de9  test    eax, eax
0x180004deb  jz      short loc_180004DFD
0x180004ded  lea     rcx, Table; Table
0x180004df4  add     rsp, 28h
0x180004df8  jmp     _execute_onexit_table
0x180004dfd  call    ?AccessCheckResult@HidDeviceCapabilityHandler@@UEAAJW4CapabilityHandlerAccessStatus@@@Z; HidDeviceCapabilityHandler::AccessCheckResult(CapabilityHandlerAccessStatus)
0x180004e02  test    eax, eax
0x180004e04  jnz     short loc_180004E0B
0x180004e06  call    _o__cexit_0
0x180004e0b  add     rsp, 28h
0x180004e0f  retn
```
