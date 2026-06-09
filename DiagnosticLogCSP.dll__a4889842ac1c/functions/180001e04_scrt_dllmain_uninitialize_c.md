# __scrt_dllmain_uninitialize_c

- ea: `0x180001e04`
- end: `0x180001e34`
- name: `__scrt_dllmain_uninitialize_c`
- size: `48`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, installer_update`

## callers

- `0x180001948`

## callees

- `0x180001e04`
- `0x180002454`
- `0x18000253a`
- `0x18000255e`
- `0x1800075e0`

## pseudocode

```c
int _scrt_dllmain_uninitialize_c()
{
  void *v0; // rdx
  WMIDPREQUESTCODE v1; // ecx
  ULONG *v2; // r8
  void *v3; // r9
  int result; // eax

  if ( (unsigned int)_scrt_is_ucrt_dll_in_use() )
    return execute_onexit_table(&Table);
  result = CArchiveDefinitionNode::PersistRollbackMoveState(v1, v0, v2, v3);
  if ( !result )
    return o__cexit_0();
  return result;
}

```

## disassembly

```asm
0x180001e04  sub     rsp, 28h
0x180001e08  call    __scrt_is_ucrt_dll_in_use
0x180001e0d  test    eax, eax
0x180001e0f  jz      short loc_180001E21
0x180001e11  lea     rcx, Table; Table
0x180001e18  add     rsp, 28h
0x180001e1c  jmp     _execute_onexit_table
0x180001e21  call    ?PersistRollbackMoveState@CArchiveDefinitionNode@@UEAAJPEAUIConfigManager2URI@@PEAUISequentialStream@@1@Z; CArchiveDefinitionNode::PersistRollbackMoveState(IConfigManager2URI *,ISequentialStream *,ISequentialStream *)
0x180001e26  test    eax, eax
0x180001e28  jnz     short loc_180001E2F
0x180001e2a  call    _o__cexit_0
0x180001e2f  add     rsp, 28h
0x180001e33  retn
```
