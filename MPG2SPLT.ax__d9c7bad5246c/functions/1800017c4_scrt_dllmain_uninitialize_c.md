# __scrt_dllmain_uninitialize_c

- ea: `0x1800017c4`
- end: `0x1800017f4`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180001248`

## callees

- `0x1800017c4`
- `0x180001d9c`
- `0x180001dfe`
- `0x180001e22`
- `0x180005d10`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  CPersistStream *v0; // rcx
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CPersistStream::GetSoftwareVersion(v0);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x1800017c4  sub     rsp, 28h
0x1800017c8  call    __scrt_is_ucrt_dll_in_use
0x1800017cd  test    eax, eax
0x1800017cf  jz      short loc_1800017E1
0x1800017d1  lea     rcx, Table; Table
0x1800017d8  add     rsp, 28h
0x1800017dc  jmp     _execute_onexit_table
0x1800017e1  call    ?GetSoftwareVersion@CPersistStream@@UEAAKXZ; CPersistStream::GetSoftwareVersion(void)
0x1800017e6  test    eax, eax
0x1800017e8  jnz     short loc_1800017EF
0x1800017ea  call    _o__cexit_0
0x1800017ef  add     rsp, 28h
0x1800017f3  retn
```
