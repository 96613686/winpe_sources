# Microsoft::WRL::Details::CreateActivationFactory<CSoftwareGamepadStatics>(uint *,Microsoft::WRL::Details::CreatorMap const *,_GUID const &,IUnknown * *)

- ea: `0x180002ea0`
- end: `0x180003048`
- name: `??$CreateActivationFactory@VCSoftwareGamepadStatics@@@Details@WRL@Microsoft@@YAJPEAIPEBUCreatorMap@012@AEBU_GUID@@PEAPEAUIUnknown@@@Z`
- size: `424`
- prototype: `__int64 __fastcall(_BYTE *, __int64, __int64, __int64)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x1800021ac`
- `0x180002b48`
- `0x180002ea0`
- `0x1800042f4`
- `0x180004e10`
- `0x1800060e0`
- `0x18000c01c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::CreateActivationFactory<CSoftwareGamepadStatics>(
        _BYTE *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  char *v8; // rax
  char *v9; // rbx
  _QWORD *v11; // rdi
  __int64 v12; // rdx
  signed __int32 v13; // edx
  __int64 v14; // rdx
  __int64 v15; // rdx
  int CanCastTo; // edi
  signed __int32 v17; // eax

  v8 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  if ( !v8 )
    return 2147942414LL;
  v11 = v8 + 8;
  Microsoft::WRL::FtmBase::FtmBase((Microsoft::WRL::FtmBase *)(v8 + 8));
  *((_DWORD *)v9 + 17) = 1;
  *(_QWORD *)v9 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable';
  *v11 = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::ISWDDeviceStatics>>'};
  *((_QWORD *)v9 + 5) = &Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::ISWDDeviceStatics>>'};
  *((_QWORD *)v9 + 10) = 0;
  *((_DWORD *)v9 + 22) = 4;
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)v9 = &CSoftwareGamepadStatics::`vftable';
  *v11 = &CSoftwareGamepadStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::ISWDDeviceStatics>>'};
  *((_QWORD *)v9 + 5) = &CSoftwareGamepadStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::ISWDDeviceStatics>>'};
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_0dff6f38adfd39e199de348a1fa5a8cf_Traceguids);
  }
  if ( SWDSingleton::GetInstance() )
  {
    do
    {
      v13 = *((_DWORD *)v9 + 17);
      if ( v13 == 0x7FFFFFFF )
      {
        v14 = 0x7FFFFFFF;
        goto LABEL_15;
      }
    }
    while ( v13 != _InterlockedCompareExchange((volatile signed __int32 *)v9 + 17, v13 + 1, v13) );
    v14 = (unsigned int)(v13 + 1);
LABEL_15:
    if ( (v9[88] & 4) == 0 && (_DWORD)v14 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
      v9,
      v14);
    CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(
                  v9,
                  a3,
                  a4);
    if ( CanCastTo >= 0 )
    {
      if ( (*a1 & 4) == 0 )
      {
        do
          v17 = *((_DWORD *)v9 + 17);
        while ( v17 != 0x7FFFFFFF
             && v17 != _InterlockedCompareExchange((volatile signed __int32 *)v9 + 17, v17 + 1, v17) );
      }
      *((_DWORD *)v9 + 22) = *(_DWORD *)a1;
      *((_QWORD *)v9 + 10) = a2;
      return 0;
    }
    else
    {
      Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
        v9,
        v15);
      return (unsigned int)CanCastTo;
    }
  }
  else
  {
    Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
      v9,
      v12);
    return 2147549183LL;
  }
}

```

## disassembly

```asm
0x180002ea0  push    rbx
0x180002ea2  push    rbp
0x180002ea3  push    rsi
0x180002ea4  push    rdi
0x180002ea5  push    r12
0x180002ea7  push    r14
0x180002ea9  push    r15
0x180002eab  sub     rsp, 20h
0x180002eaf  mov     r14, r9
0x180002eb2  mov     r15, r8
0x180002eb5  mov     rbp, rdx
0x180002eb8  mov     rsi, rcx
0x180002ebb  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002ec2  mov     ecx, 60h ; '`'; unsigned __int64
0x180002ec7  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180002ecc  mov     rbx, rax
0x180002ecf  test    rax, rax
0x180002ed2  jnz     short loc_180002EDE
0x180002ed4  mov     eax, 8007000Eh
0x180002ed9  jmp     loc_180003039
0x180002ede  lea     rdi, [rax+8]
0x180002ee2  mov     rcx, rdi; this
0x180002ee5  call    ??0FtmBase@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::FtmBase::FtmBase(void)
0x180002eea  mov     dword ptr [rbx+44h], 1
0x180002ef1  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UISWDDeviceStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'
0x180002ef8  mov     [rbx], rax
0x180002efb  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UISWDDeviceStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UISWDDeviceStatics@Gaming@Internal@Windows@@@Details@23@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::ISWDDeviceStatics>>'}
0x180002f02  mov     [rdi], rax
0x180002f05  lea     rax, ??_7?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UISWDDeviceStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISWDDeviceStatics@Gaming@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UISWDDeviceStatics@Gaming@Internal@Windows@@@234@@Details@12@@; const Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::ISWDDeviceStatics>>'}
0x180002f0c  mov     [rbx+28h], rax
0x180002f10  mov     qword ptr [rbx+50h], 0
0x180002f18  mov     dword ptr [rbx+58h], 4
0x180002f1f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002f26  test    rcx, rcx
0x180002f29  jz      short loc_180002F38
0x180002f2b  mov     rax, [rcx]
0x180002f2e  mov     rax, [rax+8]
0x180002f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f37  nop
0x180002f38  lea     rax, ??_7CSoftwareGamepadStatics@@6B@; const CSoftwareGamepadStatics::`vftable'
0x180002f3f  mov     [rbx], rax
0x180002f42  lea     rax, ??_7CSoftwareGamepadStatics@@6B?$Selector@VFtmBase@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UISWDDeviceStatics@Gaming@Internal@Windows@@@Details@23@@Details@WRL@Microsoft@@@; const CSoftwareGamepadStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::FtmBase,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::ISWDDeviceStatics>>'}
0x180002f49  mov     [rdi], rax
0x180002f4c  lea     rax, ??_7CSoftwareGamepadStatics@@6B?$Selector@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00UISWDDeviceStatics@Gaming@Internal@Windows@@@Details@WRL@Microsoft@@U?$ImplementsHelper@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00U?$ImplementsMarker@VFtmBase@WRL@Microsoft@@@Details@23@UISWDDeviceStatics@Gaming@Internal@Windows@@@234@@Details@WRL@Microsoft@@@; const CSoftwareGamepadStatics::`vftable'{for `Microsoft::WRL::Details::Selector<Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<1>,1,Microsoft::WRL::Details::ImplementsMarker<Microsoft::WRL::FtmBase>,Windows::Internal::Gaming::ISWDDeviceStatics>>'}
0x180002f53  mov     [rbx+28h], rax
0x180002f57  lea     rax, WPP_GLOBAL_Control
0x180002f5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180002f65  cmp     rcx, rax
0x180002f68  jz      short loc_180002F8B
0x180002f6a  test    byte ptr [rcx+1Ch], 8
0x180002f6e  jz      short loc_180002F8B
0x180002f70  cmp     byte ptr [rcx+19h], 4
0x180002f74  jb      short loc_180002F8B
0x180002f76  mov     edx, 0Dh
0x180002f7b  lea     r8, WPP_0dff6f38adfd39e199de348a1fa5a8cf_Traceguids
0x180002f82  mov     rcx, [rcx+10h]
0x180002f86  call    WPP_SF_
0x180002f8b  call    ?GetInstance@SWDSingleton@@SAPEAV1@XZ; SWDSingleton::GetInstance(void)
0x180002f90  test    rax, rax
0x180002f93  jnz     short loc_180002FA7
0x180002f95  mov     rcx, rbx
0x180002f98  call    ?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180002f9d  mov     eax, 8000FFFFh
0x180002fa2  jmp     loc_180003039
0x180002fa7  mov     r12d, 7FFFFFFFh
0x180002fad  jmp     short loc_180002FBB
0x180002faf  lea     ecx, [rdx+1]
0x180002fb2  mov     eax, edx
0x180002fb4  lock cmpxchg [rbx+44h], ecx
0x180002fb9  jz      short loc_180003011
0x180002fbb  mov     edx, [rbx+44h]
0x180002fbe  cmp     edx, r12d
0x180002fc1  jnz     short loc_180002FAF
0x180002fc3  mov     edx, r12d
0x180002fc6  test    byte ptr [rbx+58h], 4
0x180002fca  jnz     short loc_180002FE9
0x180002fcc  cmp     edx, 2
0x180002fcf  jnz     short loc_180002FE9
0x180002fd1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180002fd8  test    rcx, rcx
0x180002fdb  jz      short loc_180002FE9
0x180002fdd  mov     rax, [rcx]
0x180002fe0  mov     rax, [rax+8]
0x180002fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fe9  mov     rcx, rbx
0x180002fec  call    ?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180002ff1  mov     r8, r14
0x180002ff4  mov     rdx, r15
0x180002ff7  mov     rcx, rbx
0x180002ffa  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$0N@@WRL@Microsoft@@$0A@UIActivationFactory@@U?$Implements@VFtmBase@WRL@Microsoft@@UISWDDeviceStatics@Gaming@Internal@Windows@@@23@VNil@Details@23@V6723@V6723@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<13>,0,IActivationFactory,Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::ISWDDeviceStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil>::CanCastTo(_GUID const &,void * *,bool *)
0x180002fff  mov     edi, eax
0x180003001  test    eax, eax
0x180003003  jns     short loc_180003015
0x180003005  mov     rcx, rbx
0x180003008  call    ?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIGipControllerWatcherStatics@Gaming@Internal@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::Internal::Gaming::IGipControllerWatcherStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x18000300d  mov     eax, edi
0x18000300f  jmp     short loc_180003039
0x180003011  inc     edx
0x180003013  jmp     short loc_180002FC6
0x180003015  test    byte ptr [rsi], 4
0x180003018  jnz     short loc_18000302E
0x18000301a  jmp     short loc_180003026
0x18000301c  lea     ecx, [rax+1]
0x18000301f  lock cmpxchg [rbx+44h], ecx
0x180003024  jz      short loc_18000302E
0x180003026  mov     eax, [rbx+44h]
0x180003029  cmp     eax, r12d
0x18000302c  jnz     short loc_18000301C
0x18000302e  mov     eax, [rsi]
0x180003030  mov     [rbx+58h], eax
0x180003033  mov     [rbx+50h], rbp
0x180003037  xor     eax, eax
0x180003039  add     rsp, 20h
0x18000303d  pop     r15
0x18000303f  pop     r14
0x180003041  pop     r12
0x180003043  pop     rdi
0x180003044  pop     rsi
0x180003045  pop     rbp
0x180003046  pop     rbx
0x180003047  retn
```
