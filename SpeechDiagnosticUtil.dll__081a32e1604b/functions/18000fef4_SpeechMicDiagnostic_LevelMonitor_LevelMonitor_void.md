# SpeechMicDiagnostic::LevelMonitor::~LevelMonitor(void)

- ea: `0x18000fef4`
- end: `0x18000ff24`
- name: `??1LevelMonitor@SpeechMicDiagnostic@@QEAA@XZ`
- size: `48`
- prototype: `void __fastcall(SpeechMicDiagnostic::LevelMonitor *__hidden this)`
- caller_count: `3`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000dc0c`
- `0x18000dd84`
- `0x18000eb3c`

## callees

- `0x180002ce0`
- `0x18000fef4`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::LevelMonitor::~LevelMonitor(SpeechMicDiagnostic::LevelMonitor *this)
{
  void *v2; // rcx

  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    operator delete(v2);
  if ( *(_QWORD *)this )
    operator delete(*(void **)this);
}

```

## disassembly

```asm
0x18000fef4  push    rbx
0x18000fef6  sub     rsp, 20h
0x18000fefa  mov     rbx, rcx
0x18000fefd  mov     rcx, [rcx+8]; void *
0x18000ff01  test    rcx, rcx
0x18000ff04  jz      short loc_18000FF0B
0x18000ff06  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ff0b  mov     rcx, [rbx]; void *
0x18000ff0e  test    rcx, rcx
0x18000ff11  jz      short loc_18000FF1D
0x18000ff13  mov     edx, 10h; unsigned __int64
0x18000ff18  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ff1d  add     rsp, 20h
0x18000ff21  pop     rbx
0x18000ff22  retn
```
