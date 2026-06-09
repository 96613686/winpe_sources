# SpeechMicDiagnostic::DiagnosticStatus::CompleteDiagnostic(ulong,double,long)

- ea: `0x180007c38`
- end: `0x180007c80`
- name: `?CompleteDiagnostic@DiagnosticStatus@SpeechMicDiagnostic@@QEAAXKNJ@Z`
- size: `72`
- prototype: `void __fastcall(SpeechMicDiagnostic::DiagnosticStatus *__hidden this, unsigned int, double, int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180008fe0`
- `0x18000df50`
- `0x18000f4b0`

## callees

- `0x18000713c`

## import_xrefs

- `KERNEL32!SetEvent` at `0x180007c5a`
- `KERNEL32!SetEvent` at `0x180007c5a`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::DiagnosticStatus::CompleteDiagnostic(
        SpeechMicDiagnostic::DiagnosticStatus *this,
        int a2,
        double a3,
        int a4)
{
  int v4; // [rsp+38h] [rbp+10h] BYREF
  double v5; // [rsp+40h] [rbp+18h] BYREF
  int v6; // [rsp+48h] [rbp+20h] BYREF

  v6 = a4;
  v5 = a3;
  v4 = a2;
  *(double *)this = a3;
  *((_DWORD *)this + 2) = a2;
  *((_DWORD *)this + 3) = a4;
  SetEvent(*((HANDLE *)this + 2));
  SpeechMicDiagnostic::SmdTraceProvider::DignosticCompletion<unsigned long &,double &,long &>(&v4, (__int64 *)&v5, &v6);
}

```

## disassembly

```asm
0x180007c38  mov     [rsp+arg_18], r9d
0x180007c3d  movsd   [rsp+arg_10], xmm2
0x180007c43  mov     [rsp+arg_8], edx
0x180007c47  sub     rsp, 28h
0x180007c4b  movsd   qword ptr [rcx], xmm2
0x180007c4f  mov     [rcx+8], edx
0x180007c52  mov     [rcx+0Ch], r9d
0x180007c56  mov     rcx, [rcx+10h]; hEvent
0x180007c5a  call    cs:__imp_SetEvent
0x180007c61  nop     dword ptr [rax+rax+00h]
0x180007c66  lea     r8, [rsp+28h+arg_18]
0x180007c6b  lea     rdx, [rsp+28h+arg_10]
0x180007c70  lea     rcx, [rsp+28h+arg_8]
0x180007c75  call    ??$DignosticCompletion@AEAKAEANAEAJ@SmdTraceProvider@SpeechMicDiagnostic@@SAXAEAKAEANAEAJ@Z; SpeechMicDiagnostic::SmdTraceProvider::DignosticCompletion<ulong &,double &,long &>(ulong &,double &,long &)
0x180007c7a  add     rsp, 28h
0x180007c7e  retn
```
