# SbcWbsCodec::GetOutputBuffer(void)

- ea: `0x14002ec20`
- end: `0x14002ec25`
- name: `?GetOutputBuffer@SbcWbsCodec@@UEAAAEAVByteReader@Streaming@Hfp@Profiles@Bluetooth@Microsoft@@XZ`
- size: `5`
- prototype: `struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *__fastcall(SbcWbsCodec *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
struct Microsoft::Bluetooth::Profiles::Hfp::Streaming::ByteReader *__fastcall SbcWbsCodec::GetOutputBuffer(
        SbcWbsCodec *this)
{
  return (SbcWbsCodec *)((char *)this + 104);
}

```

## disassembly

```asm
0x14002ec20  lea     rax, [rcx+68h]
0x14002ec24  retn
```
