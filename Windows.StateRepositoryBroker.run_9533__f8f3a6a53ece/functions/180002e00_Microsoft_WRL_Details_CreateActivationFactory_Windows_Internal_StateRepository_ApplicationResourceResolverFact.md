# Microsoft::WRL::Details::CreateActivationFactory<Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002e00`
- end: `0x180002ea1`
- name: `??$CreateActivationFactory@VApplicationResourceResolverFactoryServer@StateRepository@Internal@Windows@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `161`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180002e00`
- `0x180003400`
- `0x1800044a8`
- `0x180006270`
- `0x18000b010`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer>(
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
  v8 = Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer,Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer,>(v13);
  if ( v8 >= 0 )
  {
    v10 = v13[0];
    CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IApplicationResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
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
0x180002e00  push    rbx
0x180002e02  push    rbp
0x180002e03  push    rsi
0x180002e04  push    rdi
0x180002e05  push    r14
0x180002e07  sub     rsp, 30h
0x180002e0b  mov     rsi, r9
0x180002e0e  mov     r14, r8
0x180002e11  mov     rbp, rdx
0x180002e14  mov     rdi, rcx
0x180002e17  mov     [rsp+58h+var_38], 0
0x180002e20  lea     rcx, [rsp+58h+var_38]
0x180002e25  call    ??$MakeAndInitialize@VApplicationResourceResolverFactoryServer@StateRepository@Internal@Windows@@V1234@$$V@Details@WRL@Microsoft@@YAJPEAPEAVApplicationResourceResolverFactoryServer@StateRepository@Internal@Windows@@@Z; Microsoft::WRL::Details::MakeAndInitialize<Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer,Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer,>(Windows::Internal::StateRepository::ApplicationResourceResolverFactoryServer * *)
0x180002e2a  mov     ebx, eax
0x180002e2c  test    eax, eax
0x180002e2e  jns     short loc_180002E4B
0x180002e30  mov     rcx, [rsp+58h+var_38]
0x180002e35  test    rcx, rcx
0x180002e38  jz      short loc_180002E47
0x180002e3a  mov     rdx, [rcx]
0x180002e3d  mov     rax, [rdx+10h]
0x180002e41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e46  nop
0x180002e47  mov     eax, ebx
0x180002e49  jmp     short loc_180002E96
0x180002e4b  mov     r8, rsi
0x180002e4e  mov     rdx, r14
0x180002e51  mov     rbx, [rsp+58h+var_38]
0x180002e56  mov     rcx, rbx
0x180002e59  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIApplicationResourceResolverStatics@StateRepository@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::StateRepository::IApplicationResourceResolverStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180002e5e  mov     esi, eax
0x180002e60  test    eax, eax
0x180002e62  jns     short loc_180002E7D
0x180002e64  test    rbx, rbx
0x180002e67  jz      short loc_180002E79
0x180002e69  mov     rdx, [rbx]
0x180002e6c  mov     rcx, rbx
0x180002e6f  mov     rax, [rdx+10h]
0x180002e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e78  nop
0x180002e79  mov     eax, esi
0x180002e7b  jmp     short loc_180002E96
0x180002e7d  test    byte ptr [rdi], 4
0x180002e80  jnz     short loc_180002E8B
0x180002e82  lea     rcx, [rbx+44h]; this
0x180002e86  call    ?SafeUnknownIncrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownIncrementReference(long volatile &)
0x180002e8b  mov     eax, [rdi]
0x180002e8d  mov     [rbx+58h], eax
0x180002e90  mov     [rbx+50h], rbp
0x180002e94  xor     eax, eax
0x180002e96  add     rsp, 30h
0x180002e9a  pop     r14
0x180002e9c  pop     rdi
0x180002e9d  pop     rsi
0x180002e9e  pop     rbp
0x180002e9f  pop     rbx
0x180002ea0  retn
```
