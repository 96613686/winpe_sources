# EvtTraceScope::~EvtTraceScope(void)

- ea: `0x1400094e4`
- end: `0x140009510`
- name: `??1EvtTraceScope@@QEAA@XZ`
- size: `44`
- prototype: `void __fastcall(EvtTraceScope *__hidden this)`
- caller_count: `9`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000a51c`
- `0x14000ddd8`
- `0x14000e3a4`
- `0x14000e934`
- `0x14000ee48`
- `0x14000f220`
- `0x14000f69c`
- `0x14000fd3c`
- `0x140010818`

## callees

- `0x1400094e4`
- `0x140012210`

## pseudocode

```c
void __fastcall EvtTraceScope::~EvtTraceScope(EvtTraceScope *this, __int64 a2)
{
  int *v2; // rax

  v2 = (int *)*((_QWORD *)this + 1);
  if ( v2 && *v2 < 0 && (Microsoft_Windows_DM_Enrollment_ProviderEnableBits & 8) != 0 )
    McTemplateU0sq_EventWriteTransfer((__int64)this, a2, *(const char **)this, *v2);
}

```

## disassembly

```asm
0x1400094e4  sub     rsp, 28h
0x1400094e8  mov     rax, [rcx+8]
0x1400094ec  test    rax, rax
0x1400094ef  jz      short loc_14000950A
0x1400094f1  mov     r9d, [rax]
0x1400094f4  test    r9d, r9d
0x1400094f7  jns     short loc_14000950A
0x1400094f9  test    cs:Microsoft_Windows_DM_Enrollment_ProviderEnableBits, 8
0x140009500  jz      short loc_14000950A
0x140009502  mov     r8, [rcx]
0x140009505  call    McTemplateU0sq_EventWriteTransfer
0x14000950a  add     rsp, 28h
0x14000950e  retn
```
