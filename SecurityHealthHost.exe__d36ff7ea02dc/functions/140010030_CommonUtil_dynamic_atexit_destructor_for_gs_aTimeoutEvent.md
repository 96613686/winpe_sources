# CommonUtil::_dynamic_atexit_destructor_for__gs_aTimeoutEvent__

- ea: `0x140010030`
- end: `0x140010052`
- name: `CommonUtil::_dynamic_atexit_destructor_for__gs_aTimeoutEvent__`
- size: `34`
- prototype: `int()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140010030`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140010047`
- `KERNEL32!CloseHandle` at `0x140010047`

## pseudocode

```c
int CommonUtil::_dynamic_atexit_destructor_for__gs_aTimeoutEvent__()
{
  int result; // eax

  result = (int)qword_1400191A0;
  if ( qword_1400191A0 )
    return CloseHandle(qword_1400191A0);
  return result;
}

```

## disassembly

```asm
0x140010030  sub     rsp, 28h
0x140010034  mov     rax, cs:qword_1400191A0
0x14001003b  test    rax, rax
0x14001003e  jz      short loc_14001004D
0x140010040  mov     rcx, cs:qword_1400191A0; hObject
0x140010047  call    cs:__imp_CloseHandle
0x14001004d  add     rsp, 28h
0x140010051  retn
```
