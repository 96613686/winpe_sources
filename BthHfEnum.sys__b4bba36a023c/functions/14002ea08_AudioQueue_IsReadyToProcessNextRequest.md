# AudioQueue_IsReadyToProcessNextRequest

- ea: `0x14002ea08`
- end: `0x14002ea27`
- name: `AudioQueue_IsReadyToProcessNextRequest`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140010eb0`

## callees

- `0x140016118`
- `0x14001ae00`

## pseudocode

```c
__int64 __fastcall AudioQueue_IsReadyToProcessNextRequest(struct WDFQUEUE__ *a1)
{
  struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy *ContextFromObject; // rax

  ContextFromObject = Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy::GetContextFromObject(a1);
  return (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)ContextFromObject + 1) + 8LL))(*((_QWORD *)ContextFromObject
                                                                                          + 1));
}

```

## disassembly

```asm
0x14002ea08  sub     rsp, 28h
0x14002ea0c  call    ?GetContextFromObject@AudioQueueProxy@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@SAPEAV123456@PEAUWDFQUEUE__@@@Z; Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy::GetContextFromObject(WDFQUEUE__ *)
0x14002ea11  mov     rcx, [rax+8]
0x14002ea15  mov     rax, [rcx]
0x14002ea18  mov     rax, [rax+8]
0x14002ea1c  call    _guard_dispatch_icall
0x14002ea21  add     rsp, 28h
0x14002ea25  retn
```
