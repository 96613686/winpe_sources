# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)

- ea: `0x180005d70`
- end: `0x180005dbf`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003184`
- `0x180003f30`
- `0x180004658`
- `0x180006e90`

## callees

- `0x180005d70`
- `0x180006248`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(
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
0x180005d70  push    rbx
0x180005d72  sub     rsp, 20h
0x180005d76  mov     r10, rcx
0x180005d79  add     rcx, 0Ch; this
0x180005d7d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180005d82  mov     ebx, eax
0x180005d84  test    eax, eax
0x180005d86  jnz     short loc_180005DB7
0x180005d88  test    r10, r10
0x180005d8b  jz      short loc_180005D9F
0x180005d8d  mov     rdx, [r10]
0x180005d90  mov     rcx, r10
0x180005d93  mov     rax, [rdx+20h]
0x180005d97  lea     edx, [rbx+1]
0x180005d9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d9f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005da6  test    rcx, rcx
0x180005da9  jz      short loc_180005DB7
0x180005dab  mov     rax, [rcx]
0x180005dae  mov     rax, [rax+10h]
0x180005db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005db7  mov     eax, ebx
0x180005db9  add     rsp, 20h
0x180005dbd  pop     rbx
0x180005dbe  retn
```
