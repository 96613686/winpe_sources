# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x180005cd0`
- end: `0x180005d48`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIAppInfoFactoryBroker@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `120`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180005d50`
- `0x180005d60`
- `0x180005e30`

## callees

- `0x180005cd0`
- `0x180006248`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IAppInfoFactoryBroker,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  __int64 v3; // r10
  unsigned int v4; // ebx
  signed __int64 v5; // rtt

  v2 = *(_QWORD *)(a1 + 56);
  v3 = a1;
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v4 = v2 - 1;
    v5 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 56), v2 - 1, v2);
    if ( v5 == v2 )
      goto LABEL_8;
  }
  v4 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
LABEL_8:
  if ( !v4 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 56LL))(v3, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v4;
}

```

## disassembly

```asm
0x180005cd0  push    rbx
0x180005cd2  sub     rsp, 20h
0x180005cd6  mov     rax, [rcx+38h]
0x180005cda  mov     r10, rcx
0x180005cdd  test    rax, rax
0x180005ce0  js      short loc_180005CFE
0x180005ce2  cmp     eax, 7FFFFFFFh
0x180005ce7  jz      short loc_180005CF7
0x180005ce9  lea     rbx, [rax-1]
0x180005ced  lock cmpxchg [rcx+38h], rbx
0x180005cf3  jnz     short loc_180005CDD
0x180005cf5  jmp     short loc_180005D0D
0x180005cf7  mov     ebx, 7FFFFFFEh
0x180005cfc  jmp     short loc_180005D40
0x180005cfe  lea     rcx, ds:10h[rax*2]; this
0x180005d06  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180005d0b  mov     ebx, eax
0x180005d0d  test    ebx, ebx
0x180005d0f  jnz     short loc_180005D40
0x180005d11  test    r10, r10
0x180005d14  jz      short loc_180005D28
0x180005d16  mov     rcx, [r10]
0x180005d19  lea     edx, [rbx+1]
0x180005d1c  mov     rax, [rcx+38h]
0x180005d20  mov     rcx, r10
0x180005d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d28  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005d2f  test    rcx, rcx
0x180005d32  jz      short loc_180005D40
0x180005d34  mov     rax, [rcx]
0x180005d37  mov     rax, [rax+10h]
0x180005d3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d40  mov     eax, ebx
0x180005d42  add     rsp, 20h
0x180005d46  pop     rbx
0x180005d47  retn
```
