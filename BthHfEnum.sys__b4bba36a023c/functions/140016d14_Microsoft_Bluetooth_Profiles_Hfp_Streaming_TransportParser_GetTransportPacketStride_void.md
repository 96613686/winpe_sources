# Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser::GetTransportPacketStride(void)

- ea: `0x140016d14`
- end: `0x140016d19`
- name: `?GetTransportPacketStride@TransportParser@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@QEBA_KXZ`
- size: `5`
- prototype: `unsigned __int64 __fastcall(Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser *__hidden this)`
- caller_count: `4`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x14002db70`
- `0x14002de78`
- `0x14002e440`
- `0x14002eeb0`

## pseudocode

```c
unsigned __int64 __fastcall Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser::GetTransportPacketStride(
        Microsoft::Bluetooth::Profiles::Hfp::Streaming::TransportParser *this)
{
  return *((_QWORD *)this + 3);
}

```

## disassembly

```asm
0x140016d14  mov     rax, [rcx+18h]
0x140016d18  retn
```
