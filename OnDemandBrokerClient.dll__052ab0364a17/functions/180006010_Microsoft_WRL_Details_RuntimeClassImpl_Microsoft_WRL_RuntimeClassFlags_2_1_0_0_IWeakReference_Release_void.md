# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)

- ea: `0x180006010`
- end: `0x18000605f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180003110`
- `0x180004120`
- `0x180004f98`
- `0x180005820`

## callees

- `0x180004350`
- `0x180006010`
- `0x180007010`

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
0x180006010  push    rbx
0x180006012  sub     rsp, 20h
0x180006016  mov     r9, rcx
0x180006019  add     rcx, 0Ch; this
0x18000601d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180006022  mov     ebx, eax
0x180006024  test    eax, eax
0x180006026  jnz     short loc_180006057
0x180006028  test    r9, r9
0x18000602b  jz      short loc_18000603F
0x18000602d  mov     rdx, [r9]
0x180006030  mov     rcx, r9
0x180006033  mov     rax, [rdx+20h]
0x180006037  lea     edx, [rbx+1]
0x18000603a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000603f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180006046  test    rcx, rcx
0x180006049  jz      short loc_180006057
0x18000604b  mov     rax, [rcx]
0x18000604e  mov     rax, [rax+10h]
0x180006052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006057  mov     eax, ebx
0x180006059  add     rsp, 20h
0x18000605d  pop     rbx
0x18000605e  retn
```
