# _SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor$2

- ea: `0x1800106de`
- end: `0x1800106ee`
- name: `_SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor$2`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800076cc`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  std::unique_ptr<SpeechMicDiagnostic::CaptureStream>::~unique_ptr<SpeechMicDiagnostic::CaptureStream>((SpeechMicDiagnostic::CaptureStream **)(*(_QWORD *)(a2 + 48) + 8LL));
}

```

## disassembly

```asm
0x1800106de  mov     rcx, [rdx+30h]
0x1800106e5  add     rcx, 8
0x1800106e9  jmp     ??1?$unique_ptr@VCaptureStream@SpeechMicDiagnostic@@U?$default_delete@VCaptureStream@SpeechMicDiagnostic@@@std@@@std@@QEAA@XZ; std::unique_ptr<SpeechMicDiagnostic::CaptureStream>::~unique_ptr<SpeechMicDiagnostic::CaptureStream>(void)
```
