# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)

- ea: `0x18000f850`
- end: `0x18000f89f`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `6`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008578`
- `0x180009c68`
- `0x18000ae28`
- `0x1800141a0`
- `0x180015758`
- `0x18001a2bc`

## callees

- `0x18000f850`
- `0x180010bc4`
- `0x180027010`

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
0x18000f850  push    rbx
0x18000f852  sub     rsp, 20h
0x18000f856  mov     r10, rcx
0x18000f859  add     rcx, 0Ch; this
0x18000f85d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x18000f862  mov     ebx, eax
0x18000f864  test    eax, eax
0x18000f866  jnz     short loc_18000F897
0x18000f868  test    r10, r10
0x18000f86b  jz      short loc_18000F87F
0x18000f86d  mov     rdx, [r10]
0x18000f870  mov     rcx, r10
0x18000f873  mov     rax, [rdx+20h]
0x18000f877  lea     edx, [rbx+1]
0x18000f87a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f87f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000f886  test    rcx, rcx
0x18000f889  jz      short loc_18000F897
0x18000f88b  mov     rax, [rcx]
0x18000f88e  mov     rax, [rax+10h]
0x18000f892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f897  mov     eax, ebx
0x18000f899  add     rsp, 20h
0x18000f89d  pop     rbx
0x18000f89e  retn
```
