# CRemoteTextAppIntegration::OnCompositionUpdating(uint,uint,uint,uint,Windows::UI::Internal::Text::Remote::RemoteTextCompositionAction,Windows::Foundation::Collections::IVectorView<Windows::UI::Internal::Text::Remote::RemoteTextCompositionClause> *)

- ea: `0x18001e500`
- end: `0x18001e73d`
- name: `?OnCompositionUpdating@CRemoteTextAppIntegration@@UEAAJIIIIW4RemoteTextCompositionAction@Remote@Text@Internal@UI@Windows@@PEAU?$IVectorView@URemoteTextCompositionClause@Remote@Text@Internal@UI@Windows@@@Collections@Foundation@7@@Z`
- size: `573`
- prototype: ``
- caller_count: `0`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180002270`
- `0x180003e44`
- `0x180006a14`
- `0x180018cd0`
- `0x18001e500`
- `0x180024b70`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e55b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e6df`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e55b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001e6df`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e535`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e6ac`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e535`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001e6ac`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CRemoteTextAppIntegration::OnCompositionUpdating(
        RTL_SRWLOCK *a1,
        int a2,
        int a3,
        int a4,
        int a5,
        int a6,
        __int64 a7)
{
  RTL_SRWLOCK *v11; // r14
  __int64 v12; // rbx
  char *v13; // rax
  char *v14; // rdi
  _QWORD *v16; // rbx
  __int64 v17; // rbx
  __int64 v18; // rcx
  __int64 v19; // rbx
  _DWORD *Ptr; // rdx
  signed __int32 v21; // eax
  char *v22; // [rsp+20h] [rbp-68h] BYREF
  _QWORD v23[11]; // [rsp+30h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  RTL_SRWLOCK *v25; // [rsp+90h] [rbp+8h] BYREF

  v11 = a1 + 36;
  if ( a1[36].Ptr )
  {
    AcquireSRWLockExclusive(a1 + 37);
    if ( v11->Ptr )
      v12 = (__int64)(*((_QWORD *)v11->Ptr + 3) - *((_QWORD *)v11->Ptr + 2)) >> 3;
    else
      v12 = 0;
    if ( v11 != (RTL_SRWLOCK *)-8LL )
      ReleaseSRWLockExclusive(v11 + 1);
    if ( v12 )
    {
      v13 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
      v14 = v13;
      if ( !v13 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x55E,
          (unsigned int)"mincore\\textinput\\dev\\virtualization\\remotetextappintegration\\lib\\remotetextappintegration.cpp",
          (const char *)0x8007000ELL,
          (int)v22);
        return 2147942414LL;
      }
      v16 = v13 + 16;
      Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v13 + 16));
      *((_QWORD *)v14 + 7) = 1;
      *(_QWORD *)v14 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable';
      *((_QWORD *)v14 + 1) = &CRemoteTextCompositionUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'};
      *v16 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *(_QWORD *)v14 = &CRemoteTextCompositionUpdatingEventArgs::`vftable';
      *((_QWORD *)v14 + 1) = &CRemoteTextCompositionUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'};
      *v16 = &Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'};
      *((_QWORD *)v14 + 11) = 0;
      *((_DWORD *)v14 + 16) = a2;
      *((_DWORD *)v14 + 17) = a3;
      *((_DWORD *)v14 + 18) = a4;
      *((_DWORD *)v14 + 19) = a5;
      *((_DWORD *)v14 + 20) = a6;
      v17 = a7;
      if ( a7 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)a7 + 8LL))(a7);
        v18 = *((_QWORD *)v14 + 11);
        *((_QWORD *)v14 + 11) = v17;
        if ( v18 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 8LL))(v14);
      (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))(v14);
      v22 = v14;
      v25 = a1 - 2;
      v19 = 0;
      AcquireSRWLockExclusive(v11 + 1);
      Ptr = v11->Ptr;
      if ( v11->Ptr )
      {
        v19 = (__int64)v11->Ptr;
        do
          v21 = Ptr[3];
        while ( v21 != 0x7FFFFFFF && v21 != _InterlockedCompareExchange(Ptr + 3, v21 + 1, v21) );
      }
      if ( v11 != (RTL_SRWLOCK *)-8LL )
        ReleaseSRWLockExclusive(v11 + 1);
      if ( v19 )
      {
        v23[0] = &v25;
        v23[1] = &v22;
        Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(
          v23,
          v19,
          v11);
        Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(v19);
      }
      (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 16LL))(v14);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001e500  push    rbx
0x18001e502  push    rbp
0x18001e503  push    rsi
0x18001e504  push    rdi
0x18001e505  push    r12
0x18001e507  push    r13
0x18001e509  push    r14
0x18001e50b  push    r15
0x18001e50d  sub     rsp, 48h
0x18001e511  mov     r15d, r9d
0x18001e514  mov     r12d, r8d
0x18001e517  mov     r13d, edx
0x18001e51a  mov     rbp, rcx
0x18001e51d  lea     r14, [rcx+120h]
0x18001e524  cmp     qword ptr [r14], 0
0x18001e528  jz      loc_18001E72A
0x18001e52e  lea     rsi, [r14+8]
0x18001e532  mov     rcx, rsi; SRWLock
0x18001e535  call    cs:__imp_AcquireSRWLockExclusive
0x18001e53b  mov     rax, [r14]
0x18001e53e  test    rax, rax
0x18001e541  jnz     short loc_18001E547
0x18001e543  xor     ebx, ebx
0x18001e545  jmp     short loc_18001E553
0x18001e547  mov     rbx, [rax+18h]
0x18001e54b  sub     rbx, [rax+10h]
0x18001e54f  sar     rbx, 3
0x18001e553  test    rsi, rsi
0x18001e556  jz      short loc_18001E561
0x18001e558  mov     rcx, rsi; SRWLock
0x18001e55b  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e561  test    rbx, rbx
0x18001e564  jz      loc_18001E72A
0x18001e56a  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e571  mov     ecx, 60h ; '`'; unsigned __int64
0x18001e576  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e57b  mov     rdi, rax
0x18001e57e  test    rax, rax
0x18001e581  jnz     short loc_18001E5AC
0x18001e583  mov     rcx, [rsp+88h]; this
0x18001e58b  mov     ebx, 8007000Eh
0x18001e590  mov     r9d, ebx; char *
0x18001e593  lea     r8, aMincoreTextinp_14; "mincore\\textinput\\dev\\virtualization"...
0x18001e59a  mov     edx, 55Eh; void *
0x18001e59f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e5a4  nop
0x18001e5a5  mov     eax, ebx
0x18001e5a7  jmp     loc_18001E72C
0x18001e5ac  lea     rbx, [rax+10h]
0x18001e5b0  mov     rcx, rbx; this
0x18001e5b3  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18001e5b8  mov     qword ptr [rdi+38h], 1
0x18001e5c0  lea     rax, ??_7?$RuntimeClass@UIRemoteTextCompositionUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'
0x18001e5c7  mov     [rdi], rax
0x18001e5ca  lea     rax, ??_7CRemoteTextCompositionUpdatingEventArgs@@6BIWeakReferenceSource@@@; const CRemoteTextCompositionUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'}
0x18001e5d1  mov     [rdi+8], rax
0x18001e5d5  lea     rax, ??_7?$RuntimeClass@UIRemoteTextCompositionUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001e5dc  mov     [rbx], rax
0x18001e5df  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001e5e6  test    rcx, rcx
0x18001e5e9  jz      short loc_18001E5F8
0x18001e5eb  mov     rax, [rcx]
0x18001e5ee  mov     rax, [rax+8]
0x18001e5f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e5f7  nop
0x18001e5f8  lea     rax, ??_7CRemoteTextCompositionUpdatingEventArgs@@6B@; const CRemoteTextCompositionUpdatingEventArgs::`vftable'
0x18001e5ff  mov     [rdi], rax
0x18001e602  lea     rax, ??_7CRemoteTextCompositionUpdatingEventArgs@@6BIWeakReferenceSource@@@; const CRemoteTextCompositionUpdatingEventArgs::`vftable'{for `IWeakReferenceSource'}
0x18001e609  mov     [rdi+8], rax
0x18001e60d  lea     rax, ??_7?$RuntimeClass@UIRemoteTextCompositionUpdatingEventArgs@Remote@Text@Internal@UI@Windows@@VFtmBase@WRL@Microsoft@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Windows::UI::Internal::Text::Remote::IRemoteTextCompositionUpdatingEventArgs,Microsoft::WRL::FtmBase>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>>'}
0x18001e614  mov     [rbx], rax
0x18001e617  mov     qword ptr [rdi+58h], 0
0x18001e61f  mov     [rdi+40h], r13d
0x18001e623  mov     [rdi+44h], r12d
0x18001e627  mov     [rdi+48h], r15d
0x18001e62b  mov     eax, [rsp+88h+arg_20]
0x18001e632  mov     [rdi+4Ch], eax
0x18001e635  mov     eax, [rsp+88h+arg_28]
0x18001e63c  mov     [rdi+50h], eax
0x18001e63f  mov     rbx, [rsp+88h+arg_30]
0x18001e647  test    rbx, rbx
0x18001e64a  jz      short loc_18001E676
0x18001e64c  mov     rax, [rbx]
0x18001e64f  mov     rcx, rbx
0x18001e652  mov     rax, [rax+8]
0x18001e656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e65b  nop
0x18001e65c  mov     rcx, [rdi+58h]
0x18001e660  mov     [rdi+58h], rbx
0x18001e664  test    rcx, rcx
0x18001e667  jz      short loc_18001E676
0x18001e669  mov     rax, [rcx]
0x18001e66c  mov     rax, [rax+10h]
0x18001e670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e675  nop
0x18001e676  mov     rax, [rdi]
0x18001e679  mov     rcx, rdi
0x18001e67c  mov     rax, [rax+8]
0x18001e680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e685  nop
0x18001e686  mov     rax, [rdi]
0x18001e689  mov     rcx, rdi
0x18001e68c  mov     rax, [rax+10h]
0x18001e690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e695  nop
0x18001e696  mov     [rsp+88h+var_68], rdi
0x18001e69b  lea     rax, [rbp-10h]
0x18001e69f  mov     [rsp+88h+arg_0], rax
0x18001e6a7  xor     ebx, ebx
0x18001e6a9  mov     rcx, rsi; SRWLock
0x18001e6ac  call    cs:__imp_AcquireSRWLockExclusive
0x18001e6b2  mov     rdx, [r14]
0x18001e6b5  test    rdx, rdx
0x18001e6b8  jz      short loc_18001E6D7
0x18001e6ba  mov     rbx, rdx
0x18001e6bd  mov     r8d, 7FFFFFFFh
0x18001e6c3  jmp     short loc_18001E6CF
0x18001e6c5  lea     ecx, [rax+1]
0x18001e6c8  lock cmpxchg [rdx+0Ch], ecx
0x18001e6cd  jz      short loc_18001E6D7
0x18001e6cf  mov     eax, [rdx+0Ch]
0x18001e6d2  cmp     eax, r8d
0x18001e6d5  jnz     short loc_18001E6C5
0x18001e6d7  test    rsi, rsi
0x18001e6da  jz      short loc_18001E6E5
0x18001e6dc  mov     rcx, rsi; SRWLock
0x18001e6df  call    cs:__imp_ReleaseSRWLockExclusive
0x18001e6e5  test    rbx, rbx
0x18001e6e8  jz      short loc_18001E71A
0x18001e6ea  lea     rax, [rsp+88h+arg_0]
0x18001e6f2  mov     [rsp+88h+var_58], rax
0x18001e6f7  lea     rax, [rsp+88h+var_68]
0x18001e6fc  mov     [rsp+88h+var_50], rax
0x18001e701  mov     r8, r14
0x18001e704  mov     rdx, rbx
0x18001e707  lea     rcx, [rsp+88h+var_58]
0x18001e70c  call    ??$InvokeDelegates@V_lambda_63f70fd3a6236e7362d86e89a2498b35_@@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@?$InvokeTraits@$0?1@WRL@Microsoft@@SAJV_lambda_63f70fd3a6236e7362d86e89a2498b35_@@PEAVEventTargetArray@Details@12@PEAV?$EventSource@U?$ITypedEventHandler@PEAVRemoteTextAppIntegration@Remote@Text@Internal@UI@Windows@@PEAVRemoteTextNonComponentUIHostDetectedEventArgs@23456@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@12@@Z; Microsoft::WRL::InvokeTraits<-2>::InvokeDelegates<_lambda_63f70fd3a6236e7362d86e89a2498b35_,Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(_lambda_63f70fd3a6236e7362d86e89a2498b35_,Microsoft::WRL::Details::EventTargetArray *,Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<Windows::UI::Internal::Text::Remote::RemoteTextAppIntegration *,Windows::UI::Internal::Text::Remote::RemoteTextNonComponentUIHostDetectedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>> *)
0x18001e711  mov     rcx, rbx
0x18001e714  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)
0x18001e719  nop
0x18001e71a  mov     rax, [rdi]
0x18001e71d  mov     rcx, rdi
0x18001e720  mov     rax, [rax+10h]
0x18001e724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e729  nop
0x18001e72a  xor     eax, eax
0x18001e72c  add     rsp, 48h
0x18001e730  pop     r15
0x18001e732  pop     r14
0x18001e734  pop     r13
0x18001e736  pop     r12
0x18001e738  pop     rdi
0x18001e739  pop     rsi
0x18001e73a  pop     rbp
0x18001e73b  pop     rbx
0x18001e73c  retn
```
