# NullCodec::GetOutputBuffer(void)

- ea: `0x14002ec10`
- end: `0x14002ec15`
- name: `?GetOutputBuffer@NullCodec@@UEAAAEAVByteReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@XZ`
- size: `5`
- prototype: `struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *__fastcall(NullCodec *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *__fastcall NullCodec::GetOutputBuffer(
        NullCodec *this)
{
  return (NullCodec *)((char *)this + 24);
}

```

## disassembly

```asm
0x14002ec10  lea     rax, [rcx+18h]
0x14002ec14  retn
```
