# _SpeechMicDiagnostic::CaptureStream::UpdateVolumeLevel_::_1_::dtor$0

- ea: `0x1800108be`
- end: `0x1800108ca`
- name: `_SpeechMicDiagnostic::CaptureStream::UpdateVolumeLevel_::_1_::dtor$0`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update, broker_com_uri`

## callees

- `0x18000dd50`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::CaptureStream::UpdateVolumeLevel_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection((Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection *)(a2 + 72));
}

```

## disassembly

```asm
0x1800108be  lea     rcx, [rdx+48h]; this
0x1800108c5  jmp     ??1SyncLockCriticalSection@Details@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::Details::SyncLockCriticalSection::~SyncLockCriticalSection(void)
```
