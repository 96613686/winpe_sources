# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x18000a4a0`
- end: `0x18000a4ef`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@U?$IAsyncOperationCompletedHandler@PEAVStorageFile@Storage@Windows@@@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000a500`

## callees

- `0x180006248`
- `0x18000a4a0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncOperationCompletedHandler<Windows::Storage::StorageFile *>,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 44), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 32LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18000a4a0  push    rbx
0x18000a4a2  sub     rsp, 20h
0x18000a4a6  mov     r10, rcx
0x18000a4a9  add     rcx, 2Ch ; ','; this
0x18000a4ad  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x18000a4b2  mov     ebx, eax
0x18000a4b4  test    eax, eax
0x18000a4b6  jnz     short loc_18000A4E7
0x18000a4b8  test    r10, r10
0x18000a4bb  jz      short loc_18000A4CF
0x18000a4bd  mov     rdx, [r10]
0x18000a4c0  mov     rcx, r10
0x18000a4c3  mov     rax, [rdx+20h]
0x18000a4c7  lea     edx, [rbx+1]
0x18000a4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4cf  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a4d6  test    rcx, rcx
0x18000a4d9  jz      short loc_18000A4E7
0x18000a4db  mov     rax, [rcx]
0x18000a4de  mov     rax, [rax+10h]
0x18000a4e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a4e7  mov     eax, ebx
0x18000a4e9  add     rsp, 20h
0x18000a4ed  pop     rbx
0x18000a4ee  retn
```
