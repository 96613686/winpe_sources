# Microsoft::WRL::Details::CreateActivationFactory<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002ba0`
- end: `0x180002ccf`
- name: `??$CreateActivationFactory@VIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180001de4`
- `0x180002ba0`
- `0x1800035fc`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _DWORD *v8; // rax
  _DWORD *v9; // rbx
  __int64 result; // rax
  struct Microsoft::WRL::Details::ModuleBase *v11; // rcx
  int CanCastTo; // esi
  signed __int32 v13; // eax

  v8 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v11 = Microsoft::WRL::Details::ModuleBase::module_;
  v8[11] = 1;
  *(_QWORD *)v8 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
  *((_QWORD *)v8 + 1) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics'};
  *((_QWORD *)v8 + 2) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationActivationCallback>'};
  *((_QWORD *)v8 + 7) = 0;
  v8[16] = 4;
  if ( v11 )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)v11 + 8LL))(v11);
  *(_QWORD *)v9 = &WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable';
  *((_QWORD *)v9 + 1) = &WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'{for `WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics'};
  *((_QWORD *)v9 + 2) = &WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationActivationCallback>'};
  WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::AddRef((WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics *)v9);
  (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                v9,
                a3,
                a4);
  if ( CanCastTo >= 0 )
  {
    if ( (*a1 & 4) == 0 )
    {
      do
        v13 = v9[11];
      while ( v13 != 0x7FFFFFFF && v13 != _InterlockedCompareExchange(v9 + 11, v13 + 1, v13) );
    }
    v9[16] = *(_DWORD *)a1;
    result = 0;
    *((_QWORD *)v9 + 7) = a2;
  }
  else
  {
    (*(void (__fastcall **)(_DWORD *))(*(_QWORD *)v9 + 16LL))(v9);
    return (unsigned int)CanCastTo;
  }
  return result;
}

```

## disassembly

```asm
0x180002ba0  mov     [rsp+arg_8], rbx
0x180002ba5  mov     [rsp+arg_10], rbp
0x180002baa  push    rsi
0x180002bab  push    rdi
0x180002bac  push    r14
0x180002bae  sub     rsp, 20h
0x180002bb2  mov     rbp, rdx
0x180002bb5  mov     rdi, rcx
0x180002bb8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002bbf  mov     ecx, 48h ; 'H'; unsigned __int64
0x180002bc4  mov     r14, r9
0x180002bc7  mov     rsi, r8
0x180002bca  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002bcf  mov     rbx, rax
0x180002bd2  test    rax, rax
0x180002bd5  jnz     short loc_180002BE1
0x180002bd7  mov     eax, 8007000Eh
0x180002bdc  jmp     loc_180002CBC
0x180002be1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002be8  mov     dword ptr [rax+2Ch], 1
0x180002bef  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x180002bf6  mov     [rbx], rax
0x180002bf9  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6BIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics'}
0x180002c00  mov     [rbx+8], rax
0x180002c04  lea     rax, ??_7?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UINotificationActivationCallback@@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationActivationCallback>'}
0x180002c0b  mov     [rbx+10h], rax
0x180002c0f  mov     qword ptr [rbx+38h], 0
0x180002c17  mov     dword ptr [rbx+40h], 4
0x180002c1e  test    rcx, rcx
0x180002c21  jz      short loc_180002C2F
0x180002c23  mov     rax, [rcx]
0x180002c26  mov     rax, [rax+8]
0x180002c2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c2f  lea     rax, ??_7IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@6B@; const WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'
0x180002c36  mov     rcx, rbx
0x180002c39  mov     [rbx], rax
0x180002c3c  lea     rax, ??_7IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@6BIIncomingCallToastStatics@123@@; const WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'{for `WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics'}
0x180002c43  mov     [rbx+8], rax
0x180002c47  lea     rax, ??_7IncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UINotificationActivationCallback@@@Details@WRL@Microsoft@@@; const WindowsInternal::ApplicationModel::Calls::IncomingCallToastStatics::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,INotificationActivationCallback>'}
0x180002c4e  mov     [rbx+10h], rax
0x180002c52  mov     rax, cs:off_18001A0F0
0x180002c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c5e  mov     rax, [rbx]
0x180002c61  mov     rcx, rbx
0x180002c64  mov     rax, [rax+10h]
0x180002c68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c6d  mov     r8, r14
0x180002c70  mov     rdx, rsi
0x180002c73  mov     rcx, rbx
0x180002c76  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180002c7b  mov     esi, eax
0x180002c7d  test    eax, eax
0x180002c7f  jns     short loc_180002C94
0x180002c81  mov     rcx, [rbx]
0x180002c84  mov     rax, [rcx+10h]
0x180002c88  mov     rcx, rbx
0x180002c8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002c90  mov     eax, esi
0x180002c92  jmp     short loc_180002CBC
0x180002c94  test    byte ptr [rdi], 4
0x180002c97  jnz     short loc_180002CB1
0x180002c99  mov     edx, 7FFFFFFFh
0x180002c9e  jmp     short loc_180002CAA
0x180002ca0  lea     ecx, [rax+1]
0x180002ca3  lock cmpxchg [rbx+2Ch], ecx
0x180002ca8  jz      short loc_180002CB1
0x180002caa  mov     eax, [rbx+2Ch]
0x180002cad  cmp     eax, edx
0x180002caf  jnz     short loc_180002CA0
0x180002cb1  mov     eax, [rdi]
0x180002cb3  mov     [rbx+40h], eax
0x180002cb6  xor     eax, eax
0x180002cb8  mov     [rbx+38h], rbp
0x180002cbc  mov     rbx, [rsp+38h+arg_8]
0x180002cc1  mov     rbp, [rsp+38h+arg_10]
0x180002cc6  add     rsp, 20h
0x180002cca  pop     r14
0x180002ccc  pop     rdi
0x180002ccd  pop     rsi
0x180002cce  retn
```
