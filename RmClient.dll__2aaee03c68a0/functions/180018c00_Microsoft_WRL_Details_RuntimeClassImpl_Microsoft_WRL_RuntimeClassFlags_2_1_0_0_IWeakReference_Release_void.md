# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)

- ea: `0x180018c00`
- end: `0x180018c4f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `6`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000ad38`
- `0x18000dcc0`
- `0x1800100e4`
- `0x1800108f8`
- `0x180017ecc`
- `0x180018230`

## callees

- `0x18000a6a0`
- `0x180018c00`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r9

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
0x180018c00  push    rbx
0x180018c02  sub     rsp, 20h
0x180018c06  mov     r9, rcx
0x180018c09  add     rcx, 0Ch; this
0x180018c0d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180018c12  mov     ebx, eax
0x180018c14  test    eax, eax
0x180018c16  jnz     short loc_180018C47
0x180018c18  test    r9, r9
0x180018c1b  jz      short loc_180018C2F
0x180018c1d  mov     rdx, [r9]
0x180018c20  mov     rcx, r9
0x180018c23  mov     rax, [rdx+20h]
0x180018c27  lea     edx, [rbx+1]
0x180018c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c2f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180018c36  test    rcx, rcx
0x180018c39  jz      short loc_180018C47
0x180018c3b  mov     rax, [rcx]
0x180018c3e  mov     rax, [rax+10h]
0x180018c42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018c47  mov     eax, ebx
0x180018c49  add     rsp, 20h
0x180018c4d  pop     rbx
0x180018c4e  retn
```
