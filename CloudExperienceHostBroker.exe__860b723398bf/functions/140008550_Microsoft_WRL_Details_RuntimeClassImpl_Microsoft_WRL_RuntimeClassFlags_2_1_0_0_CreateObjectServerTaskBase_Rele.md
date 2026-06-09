# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>::Release(void)

- ea: `0x140008550`
- end: `0x14000859f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@VCreateObjectServerTaskBase@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x140006788`
- `0x1400085b0`
- `0x1400085c0`

## callees

- `0x140008550`
- `0x140008960`
- `0x14000a010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,CreateObjectServerTaskBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r10

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 108), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 56LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x140008550  push    rbx
0x140008552  sub     rsp, 20h
0x140008556  mov     r10, rcx
0x140008559  add     rcx, 6Ch ; 'l'; this
0x14000855d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x140008562  mov     ebx, eax
0x140008564  test    eax, eax
0x140008566  jnz     short loc_140008597
0x140008568  test    r10, r10
0x14000856b  jz      short loc_14000857F
0x14000856d  mov     rdx, [r10]
0x140008570  mov     rcx, r10
0x140008573  mov     rax, [rdx+38h]
0x140008577  lea     edx, [rbx+1]
0x14000857a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000857f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x140008586  test    rcx, rcx
0x140008589  jz      short loc_140008597
0x14000858b  mov     rax, [rcx]
0x14000858e  mov     rax, [rax+10h]
0x140008592  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008597  mov     eax, ebx
0x140008599  add     rsp, 20h
0x14000859d  pop     rbx
0x14000859e  retn
```
