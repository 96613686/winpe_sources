# _DiagHubCommon::Logger::GetLogger_::_2_::_dynamic_atexit_destructor_for__loggerInstance__

- ea: `0x140015c10`
- end: `0x140015c3d`
- name: `_DiagHubCommon::Logger::GetLogger_::_2_::_dynamic_atexit_destructor_for__loggerInstance__`
- size: `45`
- prototype: `void __cdecl()`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x14000d7fc`
- `0x14001382c`
- `0x140015c10`

## pseudocode

```c
void __fastcall DiagHubCommon::Logger::GetLogger_::_2_::_dynamic_atexit_destructor_for__loggerInstance__()
{
  DiagHubCommon::Logger *v0; // rbx

  v0 = Block;
  if ( Block )
  {
    DiagHubCommon::Logger::~Logger(Block);
    operator delete(v0);
  }
}

```

## disassembly

```asm
0x140015c10  push    rbx
0x140015c12  sub     rsp, 20h
0x140015c16  mov     rbx, cs:Block
0x140015c1d  test    rbx, rbx
0x140015c20  jz      short loc_140015C37
0x140015c22  mov     rcx, rbx; this
0x140015c25  call    ??1Logger@DiagHubCommon@@QEAA@XZ; DiagHubCommon::Logger::~Logger(void)
0x140015c2a  mov     edx, 118h
0x140015c2f  mov     rcx, rbx; Block
0x140015c32  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140015c37  add     rsp, 20h
0x140015c3b  pop     rbx
0x140015c3c  retn
```
