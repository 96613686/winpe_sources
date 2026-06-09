# std::_Ref_count_obj2<DiagHubCommon::FileLogWriter>::`vector deleting destructor'(uint)

- ea: `0x14000d7d0`
- end: `0x14000d7fb`
- name: `??_E?$_Ref_count_obj2@VFileLogWriter@DiagHubCommon@@@std@@UEAAPEAXI@Z`
- size: `43`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000d7d0`
- `0x14001382c`

## pseudocode

```c
_QWORD *__fastcall std::_Ref_count_obj2<DiagHubCommon::FileLogWriter>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  *a1 = &std::_Ref_count_obj2<DiagHubCommon::FileLogWriter>::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x14000d7d0  push    rbx
0x14000d7d2  sub     rsp, 20h
0x14000d7d6  lea     rax, ??_7?$_Ref_count_obj2@VFileLogWriter@DiagHubCommon@@@std@@6B@; const std::_Ref_count_obj2<DiagHubCommon::FileLogWriter>::`vftable'
0x14000d7dd  mov     rbx, rcx
0x14000d7e0  mov     [rcx], rax
0x14000d7e3  test    dl, 1
0x14000d7e6  jz      short loc_14000D7F2
0x14000d7e8  mov     edx, 148h
0x14000d7ed  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000d7f2  mov     rax, rbx
0x14000d7f5  add     rsp, 20h
0x14000d7f9  pop     rbx
0x14000d7fa  retn
```
