# _SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor$4

- ea: `0x18001070a`
- end: `0x18001071a`
- name: `_SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor$4`
- size: `16`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800076fc`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor_4(__int64 a1, __int64 a2)
{
  CSpDynamicString::~CSpDynamicString((CSpDynamicString *)(*(_QWORD *)(a2 + 48) + 32LL));
}

```

## disassembly

```asm
0x18001070a  mov     rcx, [rdx+30h]
0x180010711  add     rcx, 20h ; ' '; this
0x180010715  jmp     ??1CSpDynamicString@@QEAA@XZ; CSpDynamicString::~CSpDynamicString(void)
```
