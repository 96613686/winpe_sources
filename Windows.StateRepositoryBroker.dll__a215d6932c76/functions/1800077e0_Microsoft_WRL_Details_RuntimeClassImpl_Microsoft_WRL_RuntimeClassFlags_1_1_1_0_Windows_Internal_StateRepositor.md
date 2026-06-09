# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IPackageResourceResolver,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x1800077e0`
- end: `0x180007858`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIPackageResourceResolver@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `120`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180007370`
- `0x180007860`
- `0x180007870`
- `0x180007880`

## callees

- `0x180006248`
- `0x1800077e0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IPackageResourceResolver,Microsoft::WRL::FtmBase>::Release(
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
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 96LL))(v3, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v4;
}

```

## disassembly

```asm
0x1800077e0  push    rbx
0x1800077e2  sub     rsp, 20h
0x1800077e6  mov     rax, [rcx+38h]
0x1800077ea  mov     r10, rcx
0x1800077ed  test    rax, rax
0x1800077f0  js      short loc_18000780E
0x1800077f2  cmp     eax, 7FFFFFFFh
0x1800077f7  jz      short loc_180007807
0x1800077f9  lea     rbx, [rax-1]
0x1800077fd  lock cmpxchg [rcx+38h], rbx
0x180007803  jnz     short loc_1800077ED
0x180007805  jmp     short loc_18000781D
0x180007807  mov     ebx, 7FFFFFFEh
0x18000780c  jmp     short loc_180007850
0x18000780e  lea     rcx, ds:10h[rax*2]; this
0x180007816  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x18000781b  mov     ebx, eax
0x18000781d  test    ebx, ebx
0x18000781f  jnz     short loc_180007850
0x180007821  test    r10, r10
0x180007824  jz      short loc_180007838
0x180007826  mov     rcx, [r10]
0x180007829  lea     edx, [rbx+1]
0x18000782c  mov     rax, [rcx+60h]
0x180007830  mov     rcx, r10
0x180007833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007838  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000783f  test    rcx, rcx
0x180007842  jz      short loc_180007850
0x180007844  mov     rax, [rcx]
0x180007847  mov     rax, [rax+10h]
0x18000784b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007850  mov     eax, ebx
0x180007852  add     rsp, 20h
0x180007856  pop     rbx
0x180007857  retn
```
