# Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)

- ea: `0x140009194`
- end: `0x1400091b2`
- name: `?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$0A@UIBuffer@Streams@Storage@Windows@@UIWeakReferenceSource@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z`
- size: `30`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140009310`

## callees

- `0x140009174`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,0,Windows::Storage::Streams::IBuffer,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(
        __int64 a1,
        unsigned int *a2,
        __int64 a3)
{
  int v3; // ecx

  v3 = *a2;
  *(GUID *)(a3 + 16LL * *a2) = GUID_905a0fe0_bc53_11df_8c49_001e4fc686da;
  *a2 = v3 + 1;
  return Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid();
}

```

## disassembly

```asm
0x140009194  mov     ecx, [rdx]
0x140009196  movups  xmm0, xmmword ptr cs:_GUID_905a0fe0_bc53_11df_8c49_001e4fc686da.Data1
0x14000919d  mov     eax, ecx
0x14000919f  add     rax, rax
0x1400091a2  movdqu  xmmword ptr [r8+rax*8], xmm0
0x1400091a8  lea     eax, [rcx+1]
0x1400091ab  mov     [rdx], eax
0x1400091ad  jmp     ?FillArrayWithIid@?$ImplementsHelper@U?$RuntimeClassFlags@$0BD@@WRL@Microsoft@@$00UIWeakReferenceSource@@U?$CloakedIid@UIBufferByteAccess@Streams@Storage@Windows@@@23@U?$CloakedIid@UIMarshal@@@23@VFtmBase@23@@Details@WRL@Microsoft@@IEAAXPEAKPEAU_GUID@@@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<19>,1,IWeakReferenceSource,Microsoft::WRL::CloakedIid<Windows::Storage::Streams::IBufferByteAccess>,Microsoft::WRL::CloakedIid<IMarshal>,Microsoft::WRL::FtmBase>::FillArrayWithIid(ulong *,_GUID *)
```
