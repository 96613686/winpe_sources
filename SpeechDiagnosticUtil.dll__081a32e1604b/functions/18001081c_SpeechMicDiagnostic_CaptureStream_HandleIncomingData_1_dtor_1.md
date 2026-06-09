# _SpeechMicDiagnostic::CaptureStream::HandleIncomingData_::_1_::dtor$1

- ea: `0x18001081c`
- end: `0x180010828`
- name: `_SpeechMicDiagnostic::CaptureStream::HandleIncomingData_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18000dd50`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::CaptureStream::HandleIncomingData_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)(a2 + 104));
}

```

## disassembly

```asm
0x18001081c  lea     rcx, [rdx+68h]; this
0x180010823  jmp     ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
```
