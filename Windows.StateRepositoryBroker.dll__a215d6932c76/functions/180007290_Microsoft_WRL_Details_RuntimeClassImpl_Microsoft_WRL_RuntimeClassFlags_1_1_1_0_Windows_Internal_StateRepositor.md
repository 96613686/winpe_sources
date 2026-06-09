# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IApplicationResourceResolver,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x180007290`
- end: `0x18000730b`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIApplicationResourceResolver@StateRepository@Internal@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `123`
- prototype: `__int64 __fastcall(__int64, volatile int *)`
- caller_count: `4`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180006d10`
- `0x180007320`
- `0x180007330`
- `0x180007340`

## callees

- `0x180006248`
- `0x180007290`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::StateRepository::IApplicationResourceResolver,Microsoft::WRL::FtmBase>::Release(
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
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 264LL))(v3, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v4;
}

```

## disassembly

```asm
0x180007290  push    rbx
0x180007292  sub     rsp, 20h
0x180007296  mov     rax, [rcx+38h]
0x18000729a  mov     r10, rcx
0x18000729d  test    rax, rax
0x1800072a0  js      short loc_1800072BE
0x1800072a2  cmp     eax, 7FFFFFFFh
0x1800072a7  jz      short loc_1800072B7
0x1800072a9  lea     rbx, [rax-1]
0x1800072ad  lock cmpxchg [rcx+38h], rbx
0x1800072b3  jnz     short loc_18000729D
0x1800072b5  jmp     short loc_1800072CD
0x1800072b7  mov     ebx, 7FFFFFFEh
0x1800072bc  jmp     short loc_180007303
0x1800072be  lea     rcx, ds:10h[rax*2]; this
0x1800072c6  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x1800072cb  mov     ebx, eax
0x1800072cd  test    ebx, ebx
0x1800072cf  jnz     short loc_180007303
0x1800072d1  test    r10, r10
0x1800072d4  jz      short loc_1800072EB
0x1800072d6  mov     rcx, [r10]
0x1800072d9  lea     edx, [rbx+1]
0x1800072dc  mov     rax, [rcx+108h]
0x1800072e3  mov     rcx, r10
0x1800072e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072eb  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800072f2  test    rcx, rcx
0x1800072f5  jz      short loc_180007303
0x1800072f7  mov     rax, [rcx]
0x1800072fa  mov     rax, [rax+10h]
0x1800072fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007303  mov     eax, ebx
0x180007305  add     rsp, 20h
0x180007309  pop     rbx
0x18000730a  retn
```
