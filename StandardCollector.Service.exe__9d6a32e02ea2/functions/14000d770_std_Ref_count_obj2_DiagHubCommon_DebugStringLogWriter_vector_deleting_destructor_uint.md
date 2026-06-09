# std::_Ref_count_obj2<DiagHubCommon::DebugStringLogWriter>::`vector deleting destructor'(uint)

- ea: `0x14000d770`
- end: `0x14000d79b`
- name: `??_E?$_Ref_count_obj2@VDebugStringLogWriter@DiagHubCommon@@@std@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000d770`
- `0x14001382c`

## pseudocode

```c
_QWORD *__fastcall std::_Ref_count_obj2<DiagHubCommon::DebugStringLogWriter>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &std::_Ref_count_obj2<DiagHubCommon::DebugStringLogWriter>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x14000d770  push    rbx
0x14000d772  sub     rsp, 20h
0x14000d776  lea     rax, ??_7?$_Ref_count_obj2@VDebugStringLogWriter@DiagHubCommon@@@std@@6B@; const std::_Ref_count_obj2<DiagHubCommon::DebugStringLogWriter>::`vftable'
0x14000d77d  mov     rbx, rcx
0x14000d780  mov     [rcx], rax
0x14000d783  test    dl, 1
0x14000d786  jz      short loc_14000D792
0x14000d788  mov     edx, 18h
0x14000d78d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d792  mov     rax, rbx
0x14000d795  add     rsp, 20h
0x14000d799  pop     rbx
0x14000d79a  retn
```
