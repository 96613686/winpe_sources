# CSystemAudioDeviceExclusive::Initialize(AUDIO_DEVICE_PIPE_DESCRIPTOR *,IUnknown *,IAudioGraphCallback *,ulong)

- ea: `0x14007f400`
- end: `0x14007f59e`
- name: `?Initialize@CSystemAudioDeviceExclusive@@UEAAJPEAUAUDIO_DEVICE_PIPE_DESCRIPTOR@@PEAUIUnknown@@PEAUIAudioGraphCallback@@K@Z`
- size: `414`
- prototype: `__int64 __usercall@<rax>(CSystemAudioDeviceExclusive *__hidden this@<rcx>, struct AUDIO_DEVICE_PIPE_DESCRIPTOR *@<rdx>, struct IUnknown *@<r8>, struct IAudioGraphCallback *@<r9>, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `loader_planting`

## callees

- `0x140009448`
- `0x1400208d0`
- `0x140055904`
- `0x140055de0`
- `0x14005d0e0`
- `0x14007e5e4`
- `0x14007e764`
- `0x14007f400`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007f552`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x14007f552`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007f45d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x14007f45d`
- `ntdll!EtwEventActivityIdControl` at `0x14007f450`
- `ntdll!EtwEventActivityIdControl` at `0x14007f562`
- `ntdll!EtwEventActivityIdControl` at `0x14007f450`
- `ntdll!EtwEventActivityIdControl` at `0x14007f562`

## pseudocode

```c

```
