# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)

- ea: `0x18001b2d0`
- end: `0x18001b31f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800143ec`
- `0x18001e8dc`
- `0x18002748c`
- `0x180028c24`
- `0x18002ebf8`
- `0x1800306d0`

## callees

- `0x18001b2d0`
- `0x18001b5ac`
- `0x180041010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 12), a2);
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
0x18001b2d0  push    rbx
0x18001b2d2  sub     rsp, 20h
0x18001b2d6  mov     r10, rcx
0x18001b2d9  add     rcx, 0Ch; this
0x18001b2dd  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x18001b2e2  mov     ebx, eax
0x18001b2e4  test    eax, eax
0x18001b2e6  jnz     short loc_18001B317
0x18001b2e8  test    r10, r10
0x18001b2eb  jz      short loc_18001B2FF
0x18001b2ed  mov     rdx, [r10]
0x18001b2f0  mov     rcx, r10
0x18001b2f3  mov     rax, [rdx+20h]
0x18001b2f7  lea     edx, [rbx+1]
0x18001b2fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b2ff  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001b306  test    rcx, rcx
0x18001b309  jz      short loc_18001B317
0x18001b30b  mov     rax, [rcx]
0x18001b30e  mov     rax, [rax+10h]
0x18001b312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001b317  mov     eax, ebx
0x18001b319  add     rsp, 20h
0x18001b31d  pop     rbx
0x18001b31e  retn
```
