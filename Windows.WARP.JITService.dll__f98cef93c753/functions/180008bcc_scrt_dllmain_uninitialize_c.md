# __scrt_dllmain_uninitialize_c

- ea: `0x180008bcc`
- end: `0x180008bfc`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: `int()`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008868`

## callees

- `0x180008bcc`
- `0x1800092e8`
- `0x180009382`
- `0x1800093a6`
- `0x180009718`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = _scrt_stub_for_is_c_termination_complete();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180008bcc  sub     rsp, 28h
0x180008bd0  call    __scrt_is_ucrt_dll_in_use
0x180008bd5  test    eax, eax
0x180008bd7  jz      short loc_180008BE9
0x180008bd9  lea     rcx, Table; Table
0x180008be0  add     rsp, 28h
0x180008be4  jmp     _execute_onexit_table
0x180008be9  call    __scrt_stub_for_is_c_termination_complete
0x180008bee  test    eax, eax
0x180008bf0  jnz     short loc_180008BF7
0x180008bf2  call    _o__cexit_0
0x180008bf7  add     rsp, 28h
0x180008bfb  retn
```
