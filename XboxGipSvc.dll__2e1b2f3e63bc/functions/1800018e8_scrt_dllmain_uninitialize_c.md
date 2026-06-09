# __scrt_dllmain_uninitialize_c

- ea: `0x1800018e8`
- end: `0x180001918`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800014a8`

## callees

- `0x1800018e8`
- `0x180001fe8`
- `0x180002082`
- `0x1800020a6`
- `0x180005520`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::GetObjectCount();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800018e8  sub     rsp, 28h
0x1800018ec  call    __scrt_is_ucrt_dll_in_use
0x1800018f1  test    eax, eax
0x1800018f3  jz      short loc_180001905
0x1800018f5  lea     rcx, Table; Table
0x1800018fc  add     rsp, 28h
0x180001900  jmp     _execute_onexit_table
0x180001905  call    ?GetObjectCount@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@EEBAKXZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::GetObjectCount(void)
0x18000190a  test    eax, eax
0x18000190c  jnz     short loc_180001913
0x18000190e  call    _o__cexit_0
0x180001913  add     rsp, 28h
0x180001917  retn
```
