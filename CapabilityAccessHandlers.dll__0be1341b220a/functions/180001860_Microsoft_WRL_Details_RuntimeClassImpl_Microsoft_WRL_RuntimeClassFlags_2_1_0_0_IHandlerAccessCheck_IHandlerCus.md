# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent>::Release(void)

- ea: `0x180001860`
- end: `0x1800018af`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIHandlerAccessCheck@@UIHandlerCustomConsent@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `79`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `5`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180002920`
- `0x180006150`
- `0x18000624c`
- `0x180006364`
- `0x180008fd0`

## callees

- `0x180001860`
- `0x1800018c0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IHandlerAccessCheck,IHandlerCustomConsent>::Release(
        __int64 a1,
        volatile int *a2)
{
  unsigned int v2; // ebx
  __int64 v3; // r9

  v2 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(a1 + 20), a2);
  if ( !v2 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v3 + 48LL))(v3, v2 + 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x180001860  push    rbx
0x180001862  sub     rsp, 20h
0x180001866  mov     r9, rcx
0x180001869  add     rcx, 14h; this
0x18000186d  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180001872  mov     ebx, eax
0x180001874  test    eax, eax
0x180001876  jnz     short loc_1800018A7
0x180001878  test    r9, r9
0x18000187b  jz      short loc_18000188F
0x18000187d  mov     rdx, [r9]
0x180001880  mov     rcx, r9
0x180001883  mov     rax, [rdx+30h]
0x180001887  lea     edx, [rbx+1]
0x18000188a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000188f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180001896  test    rcx, rcx
0x180001899  jz      short loc_1800018A7
0x18000189b  mov     rax, [rcx]
0x18000189e  mov     rax, [rax+10h]
0x1800018a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800018a7  mov     eax, ebx
0x1800018a9  add     rsp, 20h
0x1800018ad  pop     rbx
0x1800018ae  retn
```
