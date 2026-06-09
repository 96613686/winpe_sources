# CommonUtil::_dynamic_atexit_destructor_for__gs_aTimeoutEvent__

- ea: `0x140012760`
- end: `0x140012782`
- name: `CommonUtil::_dynamic_atexit_destructor_for__gs_aTimeoutEvent__`
- size: `34`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140012760`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140012777`
- `KERNEL32!CloseHandle` at `0x140012777`

## pseudocode

```c
int CommonUtil::_dynamic_atexit_destructor_for__gs_aTimeoutEvent__()
{
  int result; // eax

  result = (int)qword_14001BD48;
  if ( qword_14001BD48 )
    return CloseHandle(qword_14001BD48);
  return result;
}

```

## disassembly

```asm
0x140012760  sub     rsp, 28h
0x140012764  mov     rax, cs:qword_14001BD48
0x14001276b  test    rax, rax
0x14001276e  jz      short loc_14001277D
0x140012770  mov     rcx, cs:qword_14001BD48; hObject
0x140012777  call    cs:__imp_CloseHandle
0x14001277d  add     rsp, 28h
0x140012781  retn
```
