# __scrt_dllmain_uninitialize_c

- ea: `0x1800017ec`
- end: `0x18000181c`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001488`

## callees

- `0x1800017ec`
- `0x180001f78`
- `0x180002032`
- `0x180002056`
- `0x18000a1d0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = winrt::implements<XpsToTiffConverter::XpsToTiffConverter,IPDLConverter>::find_inspectable();
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800017ec  sub     rsp, 28h
0x1800017f0  call    __scrt_is_ucrt_dll_in_use
0x1800017f5  test    eax, eax
0x1800017f7  jz      short loc_180001809
0x1800017f9  lea     rcx, Table; Table
0x180001800  add     rsp, 28h
0x180001804  jmp     _execute_onexit_table
0x180001809  call    ?find_inspectable@?$implements@UXpsToTiffConverter@1@UIPDLConverter@@@winrt@@UEBAPEAUtype@?$abi@UIInspectable@Foundation@Windows@winrt@@X@impl@2@XZ; winrt::implements<XpsToTiffConverter::XpsToTiffConverter,IPDLConverter>::find_inspectable(void)
0x18000180e  test    eax, eax
0x180001810  jnz     short loc_180001817
0x180001812  call    _o__cexit_0
0x180001817  add     rsp, 28h
0x18000181b  retn
```
