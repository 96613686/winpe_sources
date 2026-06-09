# Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(uint)

- ea: `0x140008a20`
- end: `0x140008a4f`
- name: `??_G?$RuntimeClass@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@WRL@Microsoft@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(PVOID P)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x140008998`
- `0x140008a20`
- `0x140012d4c`

## pseudocode

```c
PVOID __fastcall Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<19>,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::`scalar deleting destructor'(
        PVOID P,
        char a2)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>((__int64)P);
  if ( (a2 & 1) != 0 )
    Common::GlobalHeap::Free(P);
  return P;
}

```

## disassembly

```asm
0x140008a20  mov     [rsp+arg_0], rbx
0x140008a25  push    rdi
0x140008a26  sub     rsp, 20h
0x140008a2a  mov     ebx, edx
0x140008a2c  mov     rdi, rcx
0x140008a2f  call    ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<19>,1,1,0,Windows::Storage::Streams::IBuffer,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>(void)
0x140008a34  test    bl, 1
0x140008a37  jz      short loc_140008A41
0x140008a39  mov     rcx, rdi; P
0x140008a3c  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x140008a41  mov     rax, rdi
0x140008a44  mov     rbx, [rsp+28h+arg_0]
0x140008a49  add     rsp, 20h
0x140008a4d  pop     rdi
0x140008a4e  retn
```
