# EvtTraceScope::~EvtTraceScope(void)

- ea: `0x1400090fc`
- end: `0x140009127`
- name: `??1EvtTraceScope@@QEAA@XZ`
- size: `43`
- prototype: `void __fastcall(EvtTraceScope *this, __int64)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a0b8`
- `0x14000d70c`
- `0x14000dca0`
- `0x14000e200`
- `0x14000e6e8`
- `0x14000eaa8`
- `0x14000ef04`
- `0x14000f56c`
- `0x140010000`

## callees

- `0x1400090fc`
- `0x140011a04`

## pseudocode

```c
void __fastcall EvtTraceScope::~EvtTraceScope(EvtTraceScope *this, __int64 a2)
{
  int *v2; // rax

  v2 = (int *)*((_QWORD *)this + 1);
  if ( v2 && *v2 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
    McTemplateU0sq_EventWriteTransfer(this, a2, *(_QWORD *)this);
}

```

## disassembly

```asm
0x1400090fc  sub     rsp, 28h
0x140009100  mov     rax, [rcx+8]
0x140009104  test    rax, rax
0x140009107  jz      short loc_140009122
0x140009109  mov     r9d, [rax]
0x14000910c  test    r9d, r9d
0x14000910f  jns     short loc_140009122
0x140009111  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 8
0x140009118  jz      short loc_140009122
0x14000911a  mov     r8, [rcx]
0x14000911d  call    McTemplateU0sq_EventWriteTransfer
0x140009122  add     rsp, 28h
0x140009126  retn
```
