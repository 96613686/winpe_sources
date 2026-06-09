# Microsoft::WRL::Details::CreateActivationFactory<Windows::Internal::StateRepository::PackageResourceResolverFactoryServer>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002eb0`
- end: `0x180002f51`
- name: `??$CreateActivationFactory@VPackageResourceResolverFactoryServer@StateRepository@Internal@Windows@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002eb0`
- `0x180003498`
- `0x180004528`
- `0x180006270`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Windows::Internal::StateRepository::PackageResourceResolverFactoryServer>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  int v8; // ebx
  __int64 v10; // rbx
  volatile int *v11; // rdx
  int CanCastTo; // esi
  _QWORD v13[7]; // [rsp+20h] [rbp-38h] BYREF

  v13[0] = 0;
  v8 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::PackageResourceResolverFactoryServer,Windows::Internal::StateRepository::PackageResourceResolverFactoryServer,>(v13);
  if ( v8 >= 0 )
  {
    v10 = v13[0];
    CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IPackageResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                  v13[0],
                  a3,
                  a4);
    if ( CanCastTo >= 0 )
    {
      if ( (*a1 & 4) == 0 )
        Microsoft::WRL::Details::SafeUnknownIncrementReference((Microsoft::WRL::Details *)(v10 + 68), v11);
      *(_DWORD *)(v10 + 88) = *(_DWORD *)a1;
      *(_QWORD *)(v10 + 80) = a2;
      return 0;
    }
    else
    {
      if ( v10 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
      return (unsigned int)CanCastTo;
    }
  }
  else
  {
    if ( v13[0] )
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v13[0] + 16LL))(v13[0]);
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x180002eb0  push    rbx
0x180002eb2  push    rbp
0x180002eb3  push    rsi
0x180002eb4  push    rdi
0x180002eb5  push    r14
0x180002eb7  sub     rsp, 30h
0x180002ebb  mov     rsi, r9
0x180002ebe  mov     r14, r8
0x180002ec1  mov     rbp, rdx
0x180002ec4  mov     rdi, rcx
0x180002ec7  mov     [rsp+58h+var_38], 0
0x180002ed0  lea     rcx, [rsp+58h+var_38]
0x180002ed5  call    ??$MakeAndInitialize@VPackageResourceResolverFactoryServer@StateRepository@Internal@Windows@@V1234@$$V@Details@WRL@Microsoft@@YAJPEAPEAVPackageResourceResolverFactoryServer@StateRepository@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::PackageResourceResolverFactoryServer,Windows::Internal::StateRepository::PackageResourceResolverFactoryServer,>(Windows::Internal::StateRepository::PackageResourceResolverFactoryServer * *)
0x180002eda  mov     ebx, eax
0x180002edc  test    eax, eax
0x180002ede  jns     short loc_180002EFB
0x180002ee0  mov     rcx, [rsp+58h+var_38]
0x180002ee5  test    rcx, rcx
0x180002ee8  jz      short loc_180002EF7
0x180002eea  mov     rdx, [rcx]
0x180002eed  mov     rax, [rdx+10h]
0x180002ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ef6  nop
0x180002ef7  mov     eax, ebx
0x180002ef9  jmp     short loc_180002F46
0x180002efb  mov     r8, rsi
0x180002efe  mov     rdx, r14
0x180002f01  mov     rbx, [rsp+58h+var_38]
0x180002f06  mov     rcx, rbx
0x180002f09  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIPackageResourceResolverStatics@StateRepository@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IPackageResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180002f0e  mov     esi, eax
0x180002f10  test    eax, eax
0x180002f12  jns     short loc_180002F2D
0x180002f14  test    rbx, rbx
0x180002f17  jz      short loc_180002F29
0x180002f19  mov     rdx, [rbx]
0x180002f1c  mov     rcx, rbx
0x180002f1f  mov     rax, [rdx+10h]
0x180002f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f28  nop
0x180002f29  mov     eax, esi
0x180002f2b  jmp     short loc_180002F46
0x180002f2d  test    byte ptr [rdi], 4
0x180002f30  jnz     short loc_180002F3B
0x180002f32  lea     rcx, [rbx+44h]; this
0x180002f36  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180002f3b  mov     eax, [rdi]
0x180002f3d  mov     [rbx+58h], eax
0x180002f40  mov     [rbx+50h], rbp
0x180002f44  xor     eax, eax
0x180002f46  add     rsp, 30h
0x180002f4a  pop     r14
0x180002f4c  pop     rdi
0x180002f4d  pop     rsi
0x180002f4e  pop     rbp
0x180002f4f  pop     rbx
0x180002f50  retn
```
