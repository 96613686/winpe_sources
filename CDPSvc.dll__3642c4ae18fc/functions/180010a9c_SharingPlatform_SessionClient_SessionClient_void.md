# SharingPlatform::SessionClient::~SessionClient(void)

- ea: `0x180010a9c`
- end: `0x180010c31`
- name: `??1SessionClient@SharingPlatform@@UEAA@XZ`
- size: `405`
- prototype: `void __fastcall(SharingPlatform::SessionClient *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800581d0`

## callees

- `0x180004928`
- `0x18001091c`
- `0x180010964`
- `0x180010a9c`
- `0x180010c38`
- `0x180010c58`
- `0x180011da4`
- `0x180014250`
- `0x1800573f8`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010bbb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010c1d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010bbb`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180010c1d`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SharingPlatform::SessionClient::~SessionClient(SharingPlatform::SessionClient *this)
{
  __int64 v2; // rcx
  __int16 v3; // [rsp+60h] [rbp-18h] BYREF
  __int16 v4; // [rsp+62h] [rbp-16h] BYREF
  __int16 v5; // [rsp+64h] [rbp-14h] BYREF
  _WORD v6[9]; // [rsp+66h] [rbp-12h] BYREF
  __int16 v7; // [rsp+90h] [rbp+18h] BYREF
  __int16 v8; // [rsp+98h] [rbp+20h] BYREF
  __int16 v9; // [rsp+A0h] [rbp+28h] BYREF
  __int16 v10; // [rsp+A8h] [rbp+30h] BYREF

  *(_QWORD *)this = &SharingPlatform::SessionClient::`vftable';
  *((_QWORD *)this + 1) = &SharingPlatform::SessionClient::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &SharingPlatform::SessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<SharingPlatform::Internal::IDeviceCallback>,Microsoft::WRL::CloakedIid<ICDPBinaryClientCallback>,Microsoft::WRL::CloakedIid<ICDPClientAuthorizationProvider>>'};
  *((_QWORD *)this + 3) = &SharingPlatform::SessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,ICDPBinaryClientCallback>'};
  *((_QWORD *)this + 4) = &SharingPlatform::SessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<ICDPClientAuthorizationProvider>>'};
  v7 = *((unsigned __int8 *)this + 111);
  v8 = *((unsigned __int8 *)this + 110);
  v9 = *((unsigned __int8 *)this + 109);
  v10 = *((unsigned __int8 *)this + 108);
  v3 = *((unsigned __int8 *)this + 107);
  v4 = *((unsigned __int8 *)this + 106);
  v5 = *((unsigned __int8 *)this + 105);
  v6[0] = *((unsigned __int8 *)this + 104);
  RemoteSessionTraceProvider::LogInfo<unsigned short const (&)[102],unsigned long &,unsigned short &,unsigned short &,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
    (_DWORD)this,
    (_DWORD)this + 96,
    (_DWORD)this + 100,
    (_DWORD)this + 102,
    (__int64)v6,
    (__int64)&v5,
    (__int64)&v4,
    (__int64)&v3,
    (__int64)&v10,
    (__int64)&v9,
    (__int64)&v8,
    (__int64)&v7);
  if ( *((_DWORD *)this + 144) )
    SharingPlatform::SessionClient::Disconnect(this);
  v2 = *((_QWORD *)this + 71);
  if ( v2 )
  {
    *((_QWORD *)this + 71) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  std::_Tree<std::_Tmap_traits<std::wstring,SharingPlatform::CDPBinaryClientContainer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,SharingPlatform::CDPBinaryClientContainer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,SharingPlatform::CDPBinaryClientContainer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,SharingPlatform::CDPBinaryClientContainer>>,0>>((char *)this + 552);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 512));
  *((_QWORD *)this + 62) = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable';
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close((char *)this + 496);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 488);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 480);
  Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPBinaryClientCallback>::InternalRelease((char *)this + 472);
  SharingPlatform::CDPBinaryClientContainer::~CDPBinaryClientContainer((SharingPlatform::SessionClient *)((char *)this + 128));
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 120);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 112);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>(this);
}

```

## disassembly

```asm
0x180010a9c  mov     r11, rsp
0x180010a9f  push    rbp
0x180010aa0  push    rbx
0x180010aa1  mov     rbp, rsp
0x180010aa4  sub     rsp, 78h
0x180010aa8  mov     rbx, rcx
0x180010aab  lea     rax, ??_7SessionClient@SharingPlatform@@6B@; const SharingPlatform::SessionClient::`vftable'
0x180010ab2  mov     [rcx], rax
0x180010ab5  lea     rax, ??_7SessionClient@SharingPlatform@@6BIWeakReferenceSource@@@; const SharingPlatform::SessionClient::`vftable'{for `IWeakReferenceSource'}
0x180010abc  mov     [rcx+8], rax
0x180010ac0  lea     rax, ??_7SessionClient@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00U?$CloakedIid@UIDeviceCallback@Internal@SharingPlatform@@@23@U?$CloakedIid@VICDPBinaryClientCallback@@@23@U?$CloakedIid@VICDPClientAuthorizationProvider@@@23@@Details@WRL@Microsoft@@@; const SharingPlatform::SessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<SharingPlatform::Internal::IDeviceCallback>,Microsoft::WRL::CloakedIid<ICDPBinaryClientCallback>,Microsoft::WRL::CloakedIid<ICDPClientAuthorizationProvider>>'}
0x180010ac7  mov     [rcx+10h], rax
0x180010acb  lea     rax, ??_7SessionClient@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00VICDPBinaryClientCallback@@@Details@WRL@Microsoft@@@; const SharingPlatform::SessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,ICDPBinaryClientCallback>'}
0x180010ad2  mov     [rcx+18h], rax
0x180010ad6  lea     rax, ??_7SessionClient@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00U?$CloakedIid@VICDPClientAuthorizationProvider@@@23@@Details@WRL@Microsoft@@@; const SharingPlatform::SessionClient::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<ICDPClientAuthorizationProvider>>'}
0x180010add  mov     [rcx+20h], rax
0x180010ae1  movzx   eax, byte ptr [rcx+6Fh]
0x180010ae5  mov     [rbp+arg_0], ax
0x180010ae9  movzx   eax, byte ptr [rcx+6Eh]
0x180010aed  mov     [rbp+arg_8], ax
0x180010af1  movzx   eax, byte ptr [rcx+6Dh]
0x180010af5  mov     [rbp+arg_10], ax
0x180010af9  movzx   eax, byte ptr [rcx+6Ch]
0x180010afd  mov     [rbp+arg_18], ax
0x180010b01  movzx   eax, byte ptr [rcx+6Bh]
0x180010b05  mov     [rbp+var_18], ax
0x180010b09  movzx   eax, byte ptr [rcx+6Ah]
0x180010b0d  mov     [rbp+var_16], ax
0x180010b11  movzx   eax, byte ptr [rcx+69h]
0x180010b15  mov     [rbp+var_14], ax
0x180010b19  movzx   eax, byte ptr [rcx+68h]
0x180010b1d  mov     [rbp+var_12], ax
0x180010b21  lea     rdx, [rcx+60h]
0x180010b25  lea     r9, [rdx+6]
0x180010b29  lea     r8, [rdx+4]
0x180010b2d  lea     rax, [rbp+arg_0]
0x180010b31  mov     [r11-30h], rax
0x180010b35  lea     rax, [rbp+arg_8]
0x180010b39  mov     [r11-38h], rax
0x180010b3d  lea     rax, [rbp+arg_10]
0x180010b41  mov     [r11-40h], rax
0x180010b45  lea     rax, [rbp+arg_18]
0x180010b49  mov     [r11-48h], rax
0x180010b4d  lea     rax, [rbp+var_18]
0x180010b51  mov     [r11-50h], rax
0x180010b55  lea     rax, [rbp+var_16]
0x180010b59  mov     [r11-58h], rax
0x180010b5d  lea     rax, [rbp+var_14]
0x180010b61  mov     [r11-60h], rax
0x180010b65  lea     rax, [rbp+var_12]
0x180010b69  mov     [r11-68h], rax
0x180010b6d  call    ??$LogInfo@AEAY0GG@$$CBGAEAKAEAGAEAGGGGGGGGG@RemoteSessionTraceProvider@@SAXAEAY0GG@$$CBGAEAKAEAG2$$QEAG3333333@Z; RemoteSessionTraceProvider::LogInfo<ushort const (&)[102],ulong &,ushort &,ushort &,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort>(ushort const (&)[102],ulong &,ushort &,ushort &,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&)
0x180010b72  cmp     dword ptr [rbx+240h], 0
0x180010b79  jz      short loc_180010B84
0x180010b7b  mov     rcx, rbx; this
0x180010b7e  call    ?Disconnect@SessionClient@SharingPlatform@@UEAAJXZ; SharingPlatform::SessionClient::Disconnect(void)
0x180010b83  nop
0x180010b84  mov     rcx, [rbx+238h]
0x180010b8b  test    rcx, rcx
0x180010b8e  jz      short loc_180010BA8
0x180010b90  mov     qword ptr [rbx+238h], 0
0x180010b9b  mov     rax, [rcx]
0x180010b9e  mov     rax, [rax+10h]
0x180010ba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ba7  nop
0x180010ba8  lea     rcx, [rbx+228h]
0x180010baf  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCDPBinaryClientContainer@SharingPlatform@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCDPBinaryClientContainer@SharingPlatform@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,SharingPlatform::CDPBinaryClientContainer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,SharingPlatform::CDPBinaryClientContainer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,SharingPlatform::CDPBinaryClientContainer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,SharingPlatform::CDPBinaryClientContainer>>,0>>(void)
0x180010bb4  lea     rcx, [rbx+200h]; lpCriticalSection
0x180010bbb  call    cs:__imp_DeleteCriticalSection
0x180010bc1  lea     rcx, [rbx+1F0h]
0x180010bc8  lea     rax, ??_7?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::`vftable'
0x180010bcf  mov     [rcx], rax
0x180010bd2  call    ?Close@?$HandleT@UCMNotificationTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::CMNotificationTraits>::Close(void)
0x180010bd7  lea     rcx, [rbx+1E8h]
0x180010bde  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180010be3  lea     rcx, [rbx+1E0h]
0x180010bea  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180010bef  lea     rcx, [rbx+1D8h]
0x180010bf6  call    ?InternalRelease@?$ComPtr@VCDPBinaryClientCallback@Internal@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPBinaryClientCallback>::InternalRelease(void)
0x180010bfb  lea     rcx, [rbx+80h]; this
0x180010c02  call    ??1CDPBinaryClientContainer@SharingPlatform@@QEAA@XZ; SharingPlatform::CDPBinaryClientContainer::~CDPBinaryClientContainer(void)
0x180010c07  lea     rcx, [rbx+78h]
0x180010c0b  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180010c10  lea     rcx, [rbx+70h]
0x180010c14  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180010c19  lea     rcx, [rbx+38h]; lpCriticalSection
0x180010c1d  call    cs:__imp_DeleteCriticalSection
0x180010c23  mov     rcx, rbx
0x180010c26  add     rsp, 78h
0x180010c2a  pop     rbx
0x180010c2b  pop     rbp
0x180010c2c  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00$00$0A@UISession@SharingPlatform@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>(void)
```
