# _SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor$1

- ea: `0x1800106cc`
- end: `0x1800106d8`
- name: `_SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007904`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  SpeechMicDiagnostic::ISpeechMicDiagnostic::~ISpeechMicDiagnostic(*(SpeechMicDiagnostic::ISpeechMicDiagnostic **)(a2 + 48));
}

```

## disassembly

```asm
0x1800106cc  mov     rcx, [rdx+30h]; this
0x1800106d3  jmp     ??1ISpeechMicDiagnostic@SpeechMicDiagnostic@@UEAA@XZ; SpeechMicDiagnostic::ISpeechMicDiagnostic::~ISpeechMicDiagnostic(void)
```
