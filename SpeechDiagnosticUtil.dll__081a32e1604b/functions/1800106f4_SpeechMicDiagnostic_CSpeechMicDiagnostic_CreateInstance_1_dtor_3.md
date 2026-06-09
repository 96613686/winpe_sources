# _SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor$3

- ea: `0x1800106f4`
- end: `0x180010704`
- name: `_SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor$3`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007654`

## pseudocode

```c
__int64 __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor_3(__int64 a1, __int64 a2)
{
  return std::shared_ptr<SpeechMicDiagnostic::DiagnosticStatus>::~shared_ptr<SpeechMicDiagnostic::DiagnosticStatus>(*(_QWORD *)(a2 + 48) + 16LL);
}

```

## disassembly

```asm
0x1800106f4  mov     rcx, [rdx+30h]
0x1800106fb  add     rcx, 10h
0x1800106ff  jmp     ??1?$shared_ptr@VDiagnosticStatus@SpeechMicDiagnostic@@@std@@QEAA@XZ; std::shared_ptr<SpeechMicDiagnostic::DiagnosticStatus>::~shared_ptr<SpeechMicDiagnostic::DiagnosticStatus>(void)
```
