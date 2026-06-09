# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)

- ea: `0x180020b20`
- end: `0x180020b6f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64(void)`
- caller_count: `8`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000cb90`
- `0x18000cc28`
- `0x18000cdbc`
- `0x18001af0c`
- `0x18001b004`
- `0x1800200e0`
- `0x180026b50`
- `0x180026be8`

## callees

- `0x180008ea4`
- `0x180020b20`
- `0x180031010`

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
0x180020b20  push    rbx
0x180020b22  sub     rsp, 20h
0x180020b26  mov     r10, rcx
0x180020b29  add     rcx, 0Ch; this
0x180020b2d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180020b32  mov     ebx, eax
0x180020b34  test    eax, eax
0x180020b36  jnz     short loc_180020B67
0x180020b38  test    r10, r10
0x180020b3b  jz      short loc_180020B4F
0x180020b3d  mov     rdx, [r10]
0x180020b40  mov     rcx, r10
0x180020b43  mov     rax, [rdx+20h]
0x180020b47  lea     edx, [rbx+1]
0x180020b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b4f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180020b56  test    rcx, rcx
0x180020b59  jz      short loc_180020B67
0x180020b5b  mov     rax, [rcx]
0x180020b5e  mov     rax, [rax+10h]
0x180020b62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b67  mov     eax, ebx
0x180020b69  add     rsp, 20h
0x180020b6d  pop     rbx
0x180020b6e  retn
```
