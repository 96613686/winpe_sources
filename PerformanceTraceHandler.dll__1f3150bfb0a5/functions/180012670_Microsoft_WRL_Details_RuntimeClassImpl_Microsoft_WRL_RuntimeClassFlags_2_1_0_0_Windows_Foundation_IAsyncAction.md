# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x180012670`
- end: `0x1800126bf`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIAsyncActionCompletedHandler@Foundation@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800126d0`

## callees

- `0x18000ce58`
- `0x180012670`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Foundation::IAsyncActionCompletedHandler,Microsoft::WRL::FtmBase>::Release(
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
0x180012670  push    rbx
0x180012672  sub     rsp, 20h
0x180012676  mov     r10, rcx
0x180012679  add     rcx, 2Ch ; ','; this
0x18001267d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180012682  mov     ebx, eax
0x180012684  test    eax, eax
0x180012686  jnz     short loc_1800126B7
0x180012688  test    r10, r10
0x18001268b  jz      short loc_18001269F
0x18001268d  mov     rdx, [r10]
0x180012690  mov     rcx, r10
0x180012693  mov     rax, [rdx+20h]
0x180012697  lea     edx, [rbx+1]
0x18001269a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001269f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800126a6  test    rcx, rcx
0x1800126a9  jz      short loc_1800126B7
0x1800126ab  mov     rax, [rcx]
0x1800126ae  mov     rax, [rax+10h]
0x1800126b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126b7  mov     eax, ebx
0x1800126b9  add     rsp, 20h
0x1800126bd  pop     rbx
0x1800126be  retn
```
