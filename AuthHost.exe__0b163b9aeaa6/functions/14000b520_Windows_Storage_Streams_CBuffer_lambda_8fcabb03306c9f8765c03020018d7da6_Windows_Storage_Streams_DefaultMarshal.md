# Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::Release(void)

- ea: `0x14000b520`
- end: `0x14000b525`
- name: `?Release@?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@UEAAKXZ`
- size: `5`
- prototype: ``
- caller_count: `4`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x14000b530`
- `0x14000b540`
- `0x14000b550`
- `0x14000b560`

## callees

- `0x14000b570`

## pseudocode

```c
// attributes: thunk
__int64 __fastcall Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::Release(
        __int64 a1,
        volatile int *a2)
{
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::Release(
           a1,
           a2);
}

```

## disassembly

```asm
0x14000b520  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::Release(void)
```
