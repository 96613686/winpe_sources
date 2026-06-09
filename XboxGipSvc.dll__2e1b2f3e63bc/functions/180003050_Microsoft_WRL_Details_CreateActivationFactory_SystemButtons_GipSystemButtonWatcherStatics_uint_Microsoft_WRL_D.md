# Microsoft::WRL::Details::CreateActivationFactory<SystemButtons::GipSystemButtonWatcherStatics>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180003050`
- end: `0x1800031f5`
- name: `??$CreateActivationFactory@VGipSystemButtonWatcherStatics@SystemButtons@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `421`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `7`
- tags: `broker_com_uri`

## callees

- `0x1800021ac`
- `0x180003050`
- `0x1800042f4`
- `0x180004d40`
- `0x1800060e0`
- `0x18000dd6c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<SystemButtons::GipSystemButtonWatcherStatics>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char *v7; // rax
  char *v8; // rdi
  int v9; // esi
  _QWORD *v10; // rbx
  volatile signed __int32 *v11; // r14
  __int64 v12; // rdx
  char *v13; // rbx
  signed __int32 v14; // edx
  __int64 v15; // rdx
  __int64 v17; // rdx
  int CanCastTo; // edi
  signed __int32 v19; // eax

  v7 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  v8 = v7;
  if ( !v7 )
    return (unsigned int)-2147024882;
  v10 = v7 + 8;
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v7 + 8));
  v11 = (volatile signed __int32 *)(v8 + 68);
  *((_DWORD *)v8 + 17) = 1;
  *(_QWORD *)v8 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
  *v10 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::IGipControllerWatcherStatics>>'};
  *((_QWORD *)v8 + 5) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::IGipControllerWatcherStatics>>'};
  *((_QWORD *)v8 + 10) = 0;
  *((_DWORD *)v8 + 22) = 4;
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v8 = &SystemButtons::GipSystemButtonWatcherStatics::`vftable';
  *v10 = &SystemButtons::GipSystemButtonWatcherStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::IGipControllerWatcherStatics>>'};
  *((_QWORD *)v8 + 5) = &SystemButtons::GipSystemButtonWatcherStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::IGipControllerWatcherStatics>>'};
  *((_QWORD *)v8 + 12) = 0;
  v9 = SystemButtons::GipSystemButtonWatcherStatics::RuntimeClassInitialize((SystemButtons::GipSystemButtonWatcherStatics *)v8);
  if ( v9 >= 0 )
  {
    v13 = v8;
    do
    {
      v14 = *v11;
      if ( *v11 == 0x7FFFFFFF )
      {
        v12 = 0x7FFFFFFF;
        goto LABEL_11;
      }
    }
    while ( v14 != _InterlockedCompareExchange(v11, v14 + 1, v14) );
    v12 = (unsigned int)(v14 + 1);
LABEL_11:
    if ( (v8[88] & 4) == 0 && (_DWORD)v12 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                          + 8LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        v12,
        0x7FFFFFFF);
    v9 = 0;
  }
  else
  {
    v13 = 0;
  }
  Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
    v8,
    v12);
  if ( v9 < 0 )
  {
    if ( v13 )
      Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
        v13,
        v15);
    return (unsigned int)v9;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                v13,
                a3,
                a4);
  if ( CanCastTo >= 0 )
  {
    if ( (*a1 & 4) == 0 )
    {
      do
        v19 = *((_DWORD *)v13 + 17);
      while ( v19 != 0x7FFFFFFF && v19 != _InterlockedCompareExchange((volatile signed __int32 *)v13 + 17, v19 + 1, v19) );
    }
    *((_DWORD *)v13 + 22) = *(_DWORD *)a1;
    *((_QWORD *)v13 + 10) = a2;
    return 0;
  }
  else
  {
    if ( v13 )
      Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
        v13,
        v17);
    return (unsigned int)CanCastTo;
  }
}

```

## disassembly

```asm
0x180003050  mov     [rsp+arg_10], r8
0x180003055  push    rbx
0x180003056  push    rbp
0x180003057  push    rsi
0x180003058  push    rdi
0x180003059  push    r12
0x18000305b  push    r13
0x18000305d  push    r14
0x18000305f  push    r15
0x180003061  sub     rsp, 28h
0x180003065  mov     r13, r9
0x180003068  mov     r12, rdx
0x18000306b  mov     r15, rcx
0x18000306e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003075  mov     ecx, 68h ; 'h'; unsigned __int64
0x18000307a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000307f  mov     rdi, rax
0x180003082  test    rax, rax
0x180003085  jnz     short loc_180003091
0x180003087  mov     esi, 8007000Eh
0x18000308c  jmp     loc_180003188
0x180003091  lea     rbx, [rax+8]
0x180003095  mov     rcx, rbx; this
0x180003098  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x18000309d  lea     r14, [rdi+44h]
0x1800030a1  mov     dword ptr [r14], 1
0x1800030a8  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x1800030af  mov     [rdi], rax
0x1800030b2  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::IGipControllerWatcherStatics>>'}
0x1800030b9  mov     [rbx], rax
0x1800030bc  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@234@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::IGipControllerWatcherStatics>>'}
0x1800030c3  mov     [rdi+28h], rax
0x1800030c7  mov     qword ptr [rdi+50h], 0
0x1800030cf  mov     dword ptr [rdi+58h], 4
0x1800030d6  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800030dd  test    rcx, rcx
0x1800030e0  jz      short loc_1800030EF
0x1800030e2  mov     rax, [rcx]
0x1800030e5  mov     rax, [rax+8]
0x1800030e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030ee  nop
0x1800030ef  lea     rax, ??_7GipSystemButtonWatcherStatics@SystemButtons@@6B@; const SystemButtons::GipSystemButtonWatcherStatics::`vftable'
0x1800030f6  mov     [rdi], rax
0x1800030f9  lea     rax, ??_7GipSystemButtonWatcherStatics@SystemButtons@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const SystemButtons::GipSystemButtonWatcherStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::IGipControllerWatcherStatics>>'}
0x180003100  mov     [rbx], rax
0x180003103  lea     rax, ??_7GipSystemButtonWatcherStatics@SystemButtons@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@234@@Details@WRL@Microsoft@@@; const SystemButtons::GipSystemButtonWatcherStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::IGipControllerWatcherStatics>>'}
0x18000310a  mov     [rdi+28h], rax
0x18000310e  mov     qword ptr [rdi+60h], 0
0x180003116  mov     rcx, rdi; this
0x180003119  call    ?RuntimeClassInitialize@GipSystemButtonWatcherStatics@SystemButtons@@QEAAJXZ; SystemButtons::GipSystemButtonWatcherStatics::RuntimeClassInitialize(void)
0x18000311e  mov     esi, eax
0x180003120  mov     r8d, 7FFFFFFFh
0x180003126  test    eax, eax
0x180003128  jns     short loc_18000312E
0x18000312a  xor     ebx, ebx
0x18000312c  jmp     short loc_18000316F
0x18000312e  mov     rbx, rdi
0x180003131  jmp     short loc_18000313F
0x180003133  lea     ecx, [rdx+1]
0x180003136  mov     eax, edx
0x180003138  lock cmpxchg [r14], ecx
0x18000313d  jz      short loc_18000318C
0x18000313f  mov     edx, [r14]
0x180003142  cmp     edx, r8d
0x180003145  jnz     short loc_180003133
0x180003147  mov     edx, r8d
0x18000314a  test    byte ptr [rdi+58h], 4
0x18000314e  jnz     short loc_18000316D
0x180003150  cmp     edx, 2
0x180003153  jnz     short loc_18000316D
0x180003155  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000315c  test    rcx, rcx
0x18000315f  jz      short loc_18000316D
0x180003161  mov     rax, [rcx]
0x180003164  mov     rax, [rax+8]
0x180003168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000316d  xor     esi, esi
0x18000316f  mov     rcx, rdi
0x180003172  call    ?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180003177  test    esi, esi
0x180003179  jns     short loc_180003190
0x18000317b  test    rbx, rbx
0x18000317e  jz      short loc_180003188
0x180003180  mov     rcx, rbx
0x180003183  call    ?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180003188  mov     eax, esi
0x18000318a  jmp     short loc_1800031E4
0x18000318c  inc     edx
0x18000318e  jmp     short loc_18000314A
0x180003190  mov     r8, r13
0x180003193  mov     rdx, [rsp+68h+arg_10]
0x18000319b  mov     rcx, rbx
0x18000319e  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x1800031a3  mov     edi, eax
0x1800031a5  test    eax, eax
0x1800031a7  jns     short loc_1800031BA
0x1800031a9  test    rbx, rbx
0x1800031ac  jz      short loc_1800031B6
0x1800031ae  mov     rcx, rbx
0x1800031b1  call    ?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x1800031b6  mov     eax, edi
0x1800031b8  jmp     short loc_1800031E4
0x1800031ba  test    byte ptr [r15], 4
0x1800031be  jnz     short loc_1800031D8
0x1800031c0  mov     edx, 7FFFFFFFh
0x1800031c5  jmp     short loc_1800031D1
0x1800031c7  lea     ecx, [rax+1]
0x1800031ca  lock cmpxchg [rbx+44h], ecx
0x1800031cf  jz      short loc_1800031D8
0x1800031d1  mov     eax, [rbx+44h]
0x1800031d4  cmp     eax, edx
0x1800031d6  jnz     short loc_1800031C7
0x1800031d8  mov     eax, [r15]
0x1800031db  mov     [rbx+58h], eax
0x1800031de  mov     [rbx+50h], r12
0x1800031e2  xor     eax, eax
0x1800031e4  add     rsp, 28h
0x1800031e8  pop     r15
0x1800031ea  pop     r14
0x1800031ec  pop     r13
0x1800031ee  pop     r12
0x1800031f0  pop     rdi
0x1800031f1  pop     rsi
0x1800031f2  pop     rbp
0x1800031f3  pop     rbx
0x1800031f4  retn
```
