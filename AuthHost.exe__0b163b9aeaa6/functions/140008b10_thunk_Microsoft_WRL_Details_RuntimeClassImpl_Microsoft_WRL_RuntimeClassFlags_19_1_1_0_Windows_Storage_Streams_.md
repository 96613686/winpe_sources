# [thunk]:Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::AddRef`adjustor{24}' (void)

- ea: `0x140008b10`
- end: `0x140008b19`
- name: `?AddRef@?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@WBI@EAAKXZ`
- size: `9`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x140008aa0`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::AddRef(
        __int64 a1)
{
  return Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::AddRef(a1 - 24);
}

```

## disassembly

```asm
0x140008b10  sub     rcx, 18h
0x140008b14  jmp     ?AddRef@?$CBuffer@V_lambda_8fcabb03306c9f8765c03020018d7da6_@@UDefaultMarshaler@Streams@Storage@Windows@@@Streams@Storage@Windows@@UEAAKXZ; Windows::Storage::Streams::CBuffer<_lambda_8fcabb03306c9f8765c03020018d7da6_,Windows::Storage::Streams::DefaultMarshaler>::AddRef(void)
```
