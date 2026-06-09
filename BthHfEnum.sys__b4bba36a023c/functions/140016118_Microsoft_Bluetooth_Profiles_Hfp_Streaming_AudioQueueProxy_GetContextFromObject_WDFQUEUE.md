# Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy::GetContextFromObject(WDFQUEUE__ *)

- ea: `0x140016118`
- end: `0x140016146`
- name: `?GetContextFromObject@AudioQueueProxy@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@SAPEAV123456@PEAUWDFQUEUE__@@@Z`
- size: `46`
- prototype: `struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy *__fastcall(struct WDFQUEUE__ *)`
- caller_count: `9`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14002d280`
- `0x14002d320`
- `0x14002e9d8`
- `0x14002ea08`
- `0x14002ea48`
- `0x14002ea78`
- `0x14002eaa4`
- `0x14002eacc`
- `0x14002eaf4`

## callees

- `0x14001ae00`

## pseudocode

```c
struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy *__fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy::GetContextFromObject(
        struct WDFQUEUE__ *a1)
{
  return (struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::AudioQueueProxy *)(*(__int64 (__fastcall **)(PWDF_DRIVER_GLOBALS, struct WDFQUEUE__ *, __int64 *))(WdfFunctions_01015 + 1616))(
                                                                                     WdfDriverGlobals,
                                                                                     a1,
                                                                                     off_1400224B0);
}

```

## disassembly

```asm
0x140016118  sub     rsp, 28h
0x14001611c  mov     rax, cs:WdfFunctions_01015
0x140016123  mov     rdx, rcx
0x140016126  mov     r8, cs:off_1400224B0
0x14001612d  mov     rcx, cs:WdfDriverGlobals
0x140016134  mov     rax, [rax+650h]
0x14001613b  call    _guard_dispatch_icall
0x140016140  add     rsp, 28h
0x140016144  retn
```
