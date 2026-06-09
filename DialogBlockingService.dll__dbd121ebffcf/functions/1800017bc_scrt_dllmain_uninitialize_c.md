# __scrt_dllmain_uninitialize_c

- ea: `0x1800017bc`
- end: `0x1800017ec`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180001408`

## callees

- `0x1800017bc`
- `0x180001f78`
- `0x180002012`
- `0x180002036`
- `0x1800057e0`

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
0x1800017bc  sub     rsp, 28h
0x1800017c0  call    __scrt_is_ucrt_dll_in_use
0x1800017c5  test    eax, eax
0x1800017c7  jz      short loc_1800017D9
0x1800017c9  lea     rcx, Table; Table
0x1800017d0  add     rsp, 28h
0x1800017d4  jmp     _execute_onexit_table
0x1800017d9  call    ?GetObjectCount@?$OutOfProcModuleBase@VServiceModule@Internal@Windows@@@Details@WRL@Microsoft@@EEBAKXZ; Microsoft::WRL::Details::OutOfProcModuleBase<Windows::Internal::ServiceModule>::GetObjectCount(void)
0x1800017de  test    eax, eax
0x1800017e0  jnz     short loc_1800017E7
0x1800017e2  call    _o__cexit_0
0x1800017e7  add     rsp, 28h
0x1800017eb  retn
```
