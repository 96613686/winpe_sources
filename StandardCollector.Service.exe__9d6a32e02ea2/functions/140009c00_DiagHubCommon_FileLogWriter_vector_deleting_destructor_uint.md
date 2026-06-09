# DiagHubCommon::FileLogWriter::`vector deleting destructor'(uint)

- ea: `0x140009c00`
- end: `0x140009c34`
- name: `??_EFileLogWriter@DiagHubCommon@@UEAAPEAXI@Z`
- size: `52`
- prototype: `DiagHubCommon::FileLogWriter *__fastcall(DiagHubCommon::FileLogWriter *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140009b50`
- `0x140009c00`
- `0x14001382c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
DiagHubCommon::FileLogWriter *__fastcall DiagHubCommon::FileLogWriter::`vector deleting destructor'(
        DiagHubCommon::FileLogWriter *this,
        char a2)
{
  DiagHubCommon::FileLogWriter::~FileLogWriter(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x140009c00  mov     [rsp+arg_0], rbx
0x140009c05  push    rdi
0x140009c06  sub     rsp, 20h
0x140009c0a  mov     ebx, edx
0x140009c0c  mov     rdi, rcx
0x140009c0f  call    ??1FileLogWriter@DiagHubCommon@@UEAA@XZ; DiagHubCommon::FileLogWriter::~FileLogWriter(void)
0x140009c14  test    bl, 1
0x140009c17  jz      short loc_140009C26
0x140009c19  mov     edx, 138h
0x140009c1e  mov     rcx, rdi; Block
0x140009c21  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140009c26  mov     rbx, [rsp+28h+arg_0]
0x140009c2b  mov     rax, rdi
0x140009c2e  add     rsp, 20h
0x140009c32  pop     rdi
0x140009c33  retn
```
