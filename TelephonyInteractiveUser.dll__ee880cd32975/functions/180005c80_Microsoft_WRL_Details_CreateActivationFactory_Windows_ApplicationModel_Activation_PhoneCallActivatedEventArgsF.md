# Microsoft::WRL::Details::CreateActivationFactory<Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsFactory>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180005c80`
- end: `0x180005db5`
- name: `??$CreateActivationFactory@VPhoneCallActivatedEventArgsFactory@Activation@ApplicationModel@Windows@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `309`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: `broker_com_uri`

## callees

- `0x180001de4`
- `0x180005c80`
- `0x180006f80`
- `0x18000891c`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsFactory>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char *v8; // rax
  char *v9; // rbx
  __int64 result; // rax
  _QWORD *v11; // rsi
  struct Microsoft::WRL::Details::ModuleBase *v12; // rcx
  int CanCastTo; // esi
  signed __int32 v14; // eax

  v8 = (char *)operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v11 = v8 + 8;
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v8 + 8));
  v12 = Microsoft::WRL::Details::ModuleBase::module_;
  *(_QWORD *)v9 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
  *v11 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>>'};
  *((_QWORD *)v9 + 5) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>>'};
  *((_DWORD *)v9 + 17) = 1;
  *((_QWORD *)v9 + 10) = 0;
  *((_DWORD *)v9 + 22) = 4;
  if ( v12 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v12 + 8LL))(v12);
  *(_QWORD *)v9 = &Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsFactory::`vftable';
  *v11 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>>'};
  *((_QWORD *)v9 + 5) = &Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsFactory::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>>'};
  ((void (__fastcall *)(char *))Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef)(v9);
  (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                v9,
                a3,
                a4);
  if ( CanCastTo >= 0 )
  {
    if ( (*a1 & 4) == 0 )
    {
      do
        v14 = *((_DWORD *)v9 + 17);
      while ( v14 != 0x7FFFFFFF && v14 != _InterlockedCompareExchange((volatile signed __int32 *)v9 + 17, v14 + 1, v14) );
    }
    *((_DWORD *)v9 + 22) = *(_DWORD *)a1;
    result = 0;
    *((_QWORD *)v9 + 10) = a2;
  }
  else
  {
    (*(void (__fastcall **)(char *))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)CanCastTo;
  }
  return result;
}

```

## disassembly

```asm
0x180005c80  mov     [rsp+arg_8], rbx
0x180005c85  push    rbp
0x180005c86  push    rsi
0x180005c87  push    rdi
0x180005c88  push    r14
0x180005c8a  push    r15
0x180005c8c  sub     rsp, 20h
0x180005c90  mov     rbp, rdx
0x180005c93  mov     rdi, rcx
0x180005c96  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180005c9d  mov     ecx, 60h ; '`'; unsigned __int64
0x180005ca2  mov     r15, r9
0x180005ca5  mov     r14, r8
0x180005ca8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180005cad  mov     rbx, rax
0x180005cb0  test    rax, rax
0x180005cb3  jnz     short loc_180005CBF
0x180005cb5  mov     eax, 8007000Eh
0x180005cba  jmp     loc_180005DA4
0x180005cbf  lea     rsi, [rax+8]
0x180005cc3  mov     rcx, rsi; this
0x180005cc6  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180005ccb  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180005cd2  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x180005cd9  mov     [rbx], rax
0x180005cdc  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>>'}
0x180005ce3  mov     [rsi], rax
0x180005ce6  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@234@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>>'}
0x180005ced  mov     [rbx+28h], rax
0x180005cf1  mov     dword ptr [rbx+44h], 1
0x180005cf8  mov     qword ptr [rbx+50h], 0
0x180005d00  mov     dword ptr [rbx+58h], 4
0x180005d07  test    rcx, rcx
0x180005d0a  jz      short loc_180005D18
0x180005d0c  mov     rax, [rcx]
0x180005d0f  mov     rax, [rax+8]
0x180005d13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d18  lea     rax, ??_7PhoneCallActivatedEventArgsFactory@Activation@ApplicationModel@Windows@@6B@; const Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsFactory::`vftable'
0x180005d1f  mov     rcx, rbx
0x180005d22  mov     [rbx], rax
0x180005d25  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>>'}
0x180005d2c  mov     [rsi], rax
0x180005d2f  lea     rax, ??_7PhoneCallActivatedEventArgsFactory@Activation@ApplicationModel@Windows@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@234@@Details@WRL@Microsoft@@@; const Windows::ApplicationModel::Activation::PhoneCallActivatedEventArgsFactory::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>>'}
0x180005d36  mov     [rbx+28h], rax
0x180005d3a  mov     rax, cs:off_18001ACD8
0x180005d41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d46  mov     rax, [rbx]
0x180005d49  mov     rcx, rbx
0x180005d4c  mov     rax, [rax+10h]
0x180005d50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d55  mov     r8, r15
0x180005d58  mov     rdx, r14
0x180005d5b  mov     rcx, rbx
0x180005d5e  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@U?$CloakedIid@UIValueUnmarshalByPropertySet@Internal@Marshaling@Foundation@Windows@@@23@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Foundation::Marshaling::Internal::IValueUnmarshalByPropertySet>>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180005d63  mov     esi, eax
0x180005d65  test    eax, eax
0x180005d67  jns     short loc_180005D7C
0x180005d69  mov     rcx, [rbx]
0x180005d6c  mov     rax, [rcx+10h]
0x180005d70  mov     rcx, rbx
0x180005d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d78  mov     eax, esi
0x180005d7a  jmp     short loc_180005DA4
0x180005d7c  test    byte ptr [rdi], 4
0x180005d7f  jnz     short loc_180005D99
0x180005d81  mov     edx, 7FFFFFFFh
0x180005d86  jmp     short loc_180005D92
0x180005d88  lea     ecx, [rax+1]
0x180005d8b  lock cmpxchg [rbx+44h], ecx
0x180005d90  jz      short loc_180005D99
0x180005d92  mov     eax, [rbx+44h]
0x180005d95  cmp     eax, edx
0x180005d97  jnz     short loc_180005D88
0x180005d99  mov     eax, [rdi]
0x180005d9b  mov     [rbx+58h], eax
0x180005d9e  xor     eax, eax
0x180005da0  mov     [rbx+50h], rbp
0x180005da4  mov     rbx, [rsp+48h+arg_8]
0x180005da9  add     rsp, 20h
0x180005dad  pop     r15
0x180005daf  pop     r14
0x180005db1  pop     rdi
0x180005db2  pop     rsi
0x180005db3  pop     rbp
0x180005db4  retn
```
