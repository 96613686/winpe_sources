# _SpeechMicDiagnostic::CreateSpeechMicDiagnostic_::_1_::dtor$0

- ea: `0x180010720`
- end: `0x18001072c`
- name: `_SpeechMicDiagnostic::CreateSpeechMicDiagnostic_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180007828`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::CreateSpeechMicDiagnostic_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::~CreateInstance((SpeechMicDiagnostic::SmdTraceProvider::CreateInstance *)(a2 + 48));
}

```

## disassembly

```asm
0x180010720  lea     rcx, [rdx+30h]; this
0x180010727  jmp     ??1CreateInstance@SmdTraceProvider@SpeechMicDiagnostic@@QEAA@XZ; SpeechMicDiagnostic::SmdTraceProvider::CreateInstance::~CreateInstance(void)
```
