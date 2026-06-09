# Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::VectorChangedEventArgs,Windows::Foundation::Collections::CollectionChange &,uint &>(Windows::Foundation::Collections::CollectionChange &,uint &)

- ea: `0x18000f888`
- end: `0x18000f92c`
- name: `??$Make@VVectorChangedEventArgs@Internal@Collections@Foundation@Windows@@AEAW4CollectionChange@345@AEAI@Details@WRL@Microsoft@@YA?AV?$ComPtr@VVectorChangedEventArgs@Internal@Collections@Foundation@Windows@@@12@AEAW4CollectionChange@Collections@Foundation@Windows@@AEAI@Z`
- size: `164`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001d5d0`

## callees

- `0x180002380`
- `0x18000f888`
- `0x18001dc00`
- `0x18002b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall Microsoft::WRL::Details::Make<Windows::Foundation::Collections::Internal::VectorChangedEventArgs,enum Windows::Foundation::Collections::CollectionChange &,unsigned int &>(
        _QWORD *a1,
        int *a2,
        int *a3)
{
  _QWORD *v6; // rax
  _QWORD *v7; // rbx
  int v8; // esi
  int v9; // ebp

  *a1 = 0;
  v6 = operator new(0x28u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    v8 = *a3;
    v9 = *a2;
    v6[3] = 1;
    *v6 = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IVectorChangedEventArgs>::`vftable'{for `Windows::Foundation::Collections::IVectorChangedEventArgs'};
    v6[1] = &Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IVectorChangedEventArgs>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *v7 = &Windows::Foundation::Collections::Internal::VectorChangedEventArgs::`vftable'{for `Windows::Foundation::Collections::IVectorChangedEventArgs'};
    v7[1] = &Windows::Foundation::Collections::Internal::VectorChangedEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'};
    *((_DWORD *)v7 + 8) = v9;
    *((_DWORD *)v7 + 9) = v8;
    if ( *a1 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorChangedEventArgs>::Release();
    *a1 = v7;
  }
  return a1;
}

```

## disassembly

```asm
0x18000f888  push    rbx
0x18000f88a  push    rbp
0x18000f88b  push    rsi
0x18000f88c  push    rdi
0x18000f88d  sub     rsp, 28h
0x18000f891  mov     rsi, r8
0x18000f894  mov     rbp, rdx
0x18000f897  mov     rdi, rcx
0x18000f89a  mov     qword ptr [rcx], 0
0x18000f8a1  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f8a8  mov     ecx, 28h ; '('; unsigned __int64
0x18000f8ad  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f8b2  mov     rbx, rax
0x18000f8b5  test    rax, rax
0x18000f8b8  jz      short loc_18000F920
0x18000f8ba  mov     esi, [rsi]
0x18000f8bc  mov     ebp, [rbp+0]
0x18000f8bf  mov     qword ptr [rax+18h], 1
0x18000f8c7  lea     rax, ??_7?$RuntimeClass@UIVectorChangedEventArgs@Collections@Foundation@Windows@@@WRL@Microsoft@@6BIVectorChangedEventArgs@Collections@Foundation@Windows@@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IVectorChangedEventArgs>::`vftable'{for `Windows::Foundation::Collections::IVectorChangedEventArgs'}
0x18000f8ce  mov     [rbx], rax
0x18000f8d1  lea     rax, ??_7?$RuntimeClass@UIVectorChangedEventArgs@Collections@Foundation@Windows@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::Foundation::Collections::IVectorChangedEventArgs>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x18000f8d8  mov     [rbx+8], rax
0x18000f8dc  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000f8e3  test    rcx, rcx
0x18000f8e6  jz      short loc_18000F8F5
0x18000f8e8  mov     rax, [rcx]
0x18000f8eb  mov     rax, [rax+8]
0x18000f8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f8f4  nop
0x18000f8f5  lea     rax, ??_7VectorChangedEventArgs@Internal@Collections@Foundation@Windows@@6BIVectorChangedEventArgs@234@@; const Windows::Foundation::Collections::Internal::VectorChangedEventArgs::`vftable'{for `Windows::Foundation::Collections::IVectorChangedEventArgs'}
0x18000f8fc  mov     [rbx], rax
0x18000f8ff  lea     rax, ??_7VectorChangedEventArgs@Internal@Collections@Foundation@Windows@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@@; const Windows::Foundation::Collections::Internal::VectorChangedEventArgs::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,IWeakReferenceSource>'}
0x18000f906  mov     [rbx+8], rax
0x18000f90a  mov     [rbx+20h], ebp
0x18000f90d  mov     [rbx+24h], esi
0x18000f910  mov     rcx, [rdi]
0x18000f913  test    rcx, rcx
0x18000f916  jz      short loc_18000F91D
0x18000f918  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIVectorChangedEventArgs@Collections@Foundation@Windows@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Foundation::Collections::IVectorChangedEventArgs>::Release(void)
0x18000f91d  mov     [rdi], rbx
0x18000f920  mov     rax, rdi
0x18000f923  add     rsp, 28h
0x18000f927  pop     rdi
0x18000f928  pop     rsi
0x18000f929  pop     rbp
0x18000f92a  pop     rbx
0x18000f92b  retn
```
