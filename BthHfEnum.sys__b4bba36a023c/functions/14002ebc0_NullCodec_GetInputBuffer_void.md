# NullCodec::GetInputBuffer(void)

- ea: `0x14002ebc0`
- end: `0x14002ebc5`
- name: `?GetInputBuffer@NullCodec@@UEAAAEAVByteWriter@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@XZ`
- size: `5`
- prototype: `struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *__fastcall(NullCodec *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *__fastcall NullCodec::GetInputBuffer(
        NullCodec *this)
{
  return (NullCodec *)((char *)this + 16);
}

```

## disassembly

```asm
0x14002ebc0  lea     rax, [rcx+10h]
0x14002ebc4  retn
```
