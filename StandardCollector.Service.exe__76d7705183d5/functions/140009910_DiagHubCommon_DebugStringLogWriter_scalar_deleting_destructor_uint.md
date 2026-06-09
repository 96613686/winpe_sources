# DiagHubCommon::DebugStringLogWriter::`scalar deleting destructor'(uint)

- ea: `0x140009910`
- end: `0x14000993b`
- name: `??_GDebugStringLogWriter@DiagHubCommon@@UEAAPEAXI@Z`
- size: `43`
- prototype: `void *__fastcall(DiagHubCommon::DebugStringLogWriter *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140009910`
- `0x14001382c`

## pseudocode

```c
DiagHubCommon::DebugStringLogWriter *__fastcall DiagHubCommon::DebugStringLogWriter::`scalar deleting destructor'(
        DiagHubCommon::DebugStringLogWriter *this,
        char a2)
{
  *(_QWORD *)this = &DiagHubCommon::DebugStringLogWriter::`vftable';
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140009910  push    rbx
0x140009912  sub     rsp, 20h
0x140009916  lea     rax, ??_7DebugStringLogWriter@DiagHubCommon@@6B@; const DiagHubCommon::DebugStringLogWriter::`vftable'
0x14000991d  mov     rbx, rcx
0x140009920  mov     [rcx], rax
0x140009923  test    dl, 1
0x140009926  jz      short loc_140009932
0x140009928  mov     edx, 8
0x14000992d  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009932  mov     rax, rbx
0x140009935  add     rsp, 20h
0x140009939  pop     rbx
0x14000993a  retn
```
