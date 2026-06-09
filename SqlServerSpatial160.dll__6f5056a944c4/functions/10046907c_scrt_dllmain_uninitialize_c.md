# __scrt_dllmain_uninitialize_c

- ea: `0x10046907c`
- end: `0x1004690ac`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x100468d28`

## callees

- `0x1004020d0`
- `0x10046907c`
- `0x1004697f8`
- `0x1004698ca`
- `0x1004698e2`

## pseudocode

```c
void _scrt_dllmain_uninitialize_c()
{
  bool v0; // dl
  CDummySink *v1; // rcx

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
  {
    execute_onexit_table_0(&Table);
  }
  else if ( !(unsigned int)CDummySink::EndGeometry(v1, v0) )
  {
    cexit_0();
  }
}

```

## disassembly

```asm
0x10046907c  sub     rsp, 28h
0x100469080  call    __scrt_is_ucrt_dll_in_use
0x100469085  test    eax, eax
0x100469087  jz      short loc_100469099
0x100469089  lea     rcx, Table; Table
0x100469090  add     rsp, 28h
0x100469094  jmp     _execute_onexit_table_0
0x100469099  call    ?EndGeometry@CDummySink@@UEAAJ_N@Z
0x10046909e  test    eax, eax
0x1004690a0  jnz     short loc_1004690A7
0x1004690a2  call    _cexit_0
0x1004690a7  add     rsp, 28h
0x1004690ab  retn
```
