# SbcWbsCodec::GetInputBuffer(void)

- ea: `0x14002ebd0`
- end: `0x14002ebd5`
- name: `?GetInputBuffer@SbcWbsCodec@@UEAAAEAVByteWriter@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@XZ`
- size: `5`
- prototype: `struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *__fastcall(SbcWbsCodec *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteWriter *__fastcall SbcWbsCodec::GetInputBuffer(
        SbcWbsCodec *this)
{
  return (SbcWbsCodec *)((char *)this + 32);
}

```

## disassembly

```asm
0x14002ebd0  lea     rax, [rcx+20h]
0x14002ebd4  retn
```
