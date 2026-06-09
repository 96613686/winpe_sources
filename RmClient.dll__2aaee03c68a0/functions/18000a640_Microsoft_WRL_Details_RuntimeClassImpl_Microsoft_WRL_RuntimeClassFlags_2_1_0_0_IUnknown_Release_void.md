# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)

- ea: `0x18000a640`
- end: `0x18000a68f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `17`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180001500`
- `0x1800018f0`
- `0x18000a2d4`
- `0x18000a318`
- `0x18000a474`
- `0x18000a4b4`
- `0x18000a5b0`
- `0x18000a5e0`
- `0x18000a610`
- `0x18000f684`
- `0x180010918`
- `0x180013594`
- `0x180017b94`
- `0x180017c34`
- `0x180017d78`
- `0x180018ca0`
- `0x180018e18`

## callees

- `0x18000a640`
- `0x18000a6a0`
- `0x18001c010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r9

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 12), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 24LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18000a640  push    rbx
0x18000a642  sub     rsp, 20h
0x18000a646  mov     r9, rcx
0x18000a649  add     rcx, 0Ch; this
0x18000a64d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x18000a652  mov     ebx, eax
0x18000a654  test    eax, eax
0x18000a656  jnz     short loc_18000A687
0x18000a658  test    r9, r9
0x18000a65b  jz      short loc_18000A66F
0x18000a65d  mov     rdx, [r9]
0x18000a660  mov     rcx, r9
0x18000a663  mov     rax, [rdx+18h]
0x18000a667  lea     edx, [rbx+1]
0x18000a66a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a66f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a676  test    rcx, rcx
0x18000a679  jz      short loc_18000A687
0x18000a67b  mov     rax, [rcx]
0x18000a67e  mov     rax, [rax+10h]
0x18000a682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a687  mov     eax, ebx
0x18000a689  add     rsp, 20h
0x18000a68d  pop     rbx
0x18000a68e  retn
```
