# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWICRawMetadataBlockReaderBase,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x18009d220`
- end: `0x18009d273`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCWICRawMetadataBlockReaderBase@@UIWICMetadataBlockReader@@U?$ChainInterfaces@UIWICBitmapFrameDecode@@UIWICBitmapSource@@VNil@Details@WRL@Microsoft@@V3456@V3456@V3456@V3456@V3456@V3456@V3456@@23@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `83`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18009d280`
- `0x18009d290`
- `0x18009d2a0`

## callees

- `0x180096d20`
- `0x18009d220`
- `0x1800b4010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CWICRawMetadataBlockReaderBase,IWICMetadataBlockReader,Microsoft::WRL::ChainInterfaces<IWICBitmapFrameDecode,IWICBitmapSource,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 156), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 56LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18009d220  push    rbx
0x18009d222  sub     rsp, 20h
0x18009d226  mov     r10, rcx
0x18009d229  add     rcx, 9Ch; this
0x18009d230  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x18009d235  mov     ebx, eax
0x18009d237  test    eax, eax
0x18009d239  jnz     short loc_18009D26A
0x18009d23b  test    r10, r10
0x18009d23e  jz      short loc_18009D252
0x18009d240  mov     rdx, [r10]
0x18009d243  mov     rcx, r10
0x18009d246  mov     rax, [rdx+38h]
0x18009d24a  lea     edx, [rbx+1]
0x18009d24d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d252  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18009d259  test    rcx, rcx
0x18009d25c  jz      short loc_18009D26A
0x18009d25e  mov     rax, [rcx]
0x18009d261  mov     rax, [rax+10h]
0x18009d265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009d26a  mov     eax, ebx
0x18009d26c  add     rsp, 20h
0x18009d270  pop     rbx
0x18009d271  retn
```
