# SharingPlatform::SessionHost::~SessionHost(void)

- ea: `0x1800150c0`
- end: `0x180015260`
- name: `??1SessionHost@SharingPlatform@@UEAA@XZ`
- size: `416`
- prototype: `void __fastcall(SharingPlatform::SessionHost *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180048710`

## callees

- `0x180004928`
- `0x18001336c`
- `0x1800150c0`
- `0x180015268`
- `0x1800155c8`
- `0x180015824`
- `0x180015844`
- `0x180016248`
- `0x18005c4d0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015208`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001524c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180015208`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001524c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SharingPlatform::SessionHost::~SessionHost(SharingPlatform::SessionHost *this)
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

  *(_QWORD *)this = &SharingPlatform::SessionHost::`vftable'{for `SharingPlatform::ISessionMessageChannel'};
  *((_QWORD *)this + 1) = &SharingPlatform::SessionHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,IWeakReferenceSource,SharingPlatform::ISessionHostMessageChannel,Microsoft::WRL::CloakedIid<ICDPBinaryHostCallback>,Microsoft::WRL::CloakedIid<ICDPParticipantHandler>,Microsoft::WRL::CloakedIid<ICDPHostAuthorizationProvider>>'};
  *((_QWORD *)this + 2) = &SharingPlatform::SessionHost::`vftable'{for `SharingPlatform::ISessionHostMessageChannel'};
  *((_QWORD *)this + 3) = &SharingPlatform::SessionHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<ICDPBinaryHostCallback>,Microsoft::WRL::CloakedIid<ICDPParticipantHandler>,Microsoft::WRL::CloakedIid<ICDPHostAuthorizationProvider>>'};
  *((_QWORD *)this + 4) = &SharingPlatform::SessionHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,ICDPParticipantHandler>'};
  *((_QWORD *)this + 5) = &SharingPlatform::SessionHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<ICDPHostAuthorizationProvider>>'};
  v7 = *((unsigned __int8 *)this + 127);
  v8 = *((unsigned __int8 *)this + 126);
  v9 = *((unsigned __int8 *)this + 125);
  v10 = *((unsigned __int8 *)this + 124);
  v3 = *((unsigned __int8 *)this + 123);
  v4 = *((unsigned __int8 *)this + 122);
  v5 = *((unsigned __int8 *)this + 121);
  v6[0] = *((unsigned __int8 *)this + 120);
  RemoteSessionTraceProvider::LogInfo<unsigned short const (&)[112],unsigned long &,unsigned short &,unsigned short &,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
    L"SessionHost::~SessionHost sessionId={%08lX-%04hX-%04hX-%02hX%02hX-%02hX%02hX%02hX%02hX%02hX%02hX}",
    (__int64)v6,
    (__int64)&v5,
    (__int64)&v4,
    (__int64)&v3,
    (__int64)&v10,
    (__int64)&v9,
    (__int64)&v8,
    (__int64)&v7);
  if ( *((_BYTE *)this + 144) )
    SharingPlatform::SessionHost::Disconnect(this);
  std::_Tree<std::_Tmap_traits<_GUID,unsigned __int64,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<_GUID,unsigned __int64,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned __int64>>,0>>((char *)this + 296);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 288);
  std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>>,0>>((char *)this + 272);
  std::_Tree<std::_Tmap_traits<_GUID,unsigned __int64,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<_GUID,unsigned __int64,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned __int64>>,0>>((char *)this + 256);
  std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>>,0>>((char *)this + 240);
  std::_Tree<std::_Tmap_traits<std::wstring,SharingPlatform::CDPBinaryHostContainer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,SharingPlatform::CDPBinaryHostContainer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,SharingPlatform::CDPBinaryHostContainer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,SharingPlatform::CDPBinaryHostContainer>>,0>>((char *)this + 224);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 184));
  SharingPlatform::CDPBinaryHostContainer::~CDPBinaryHostContainer((SharingPlatform::SessionHost *)((char *)this + 160));
  v2 = *((_QWORD *)this + 19);
  if ( v2 )
  {
    *((_QWORD *)this + 19) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISessionMessageChannel,SharingPlatform::ISessionHostMessageChannel,Microsoft::WRL::CloakedIid<ICDPBinaryHostCallback>,Microsoft::WRL::CloakedIid<ICDPParticipantHandler>,Microsoft::WRL::CloakedIid<ICDPHostAuthorizationProvider>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISessionMessageChannel,SharingPlatform::ISessionHostMessageChannel,Microsoft::WRL::CloakedIid<ICDPBinaryHostCallback>,Microsoft::WRL::CloakedIid<ICDPParticipantHandler>,Microsoft::WRL::CloakedIid<ICDPHostAuthorizationProvider>>(this);
}

```

## disassembly

```asm
0x1800150c0  mov     r11, rsp
0x1800150c3  push    rbp
0x1800150c4  push    rbx
0x1800150c5  mov     rbp, rsp
0x1800150c8  sub     rsp, 78h
0x1800150cc  mov     rbx, rcx
0x1800150cf  lea     rax, ??_7SessionHost@SharingPlatform@@6BISessionMessageChannel@1@@; const SharingPlatform::SessionHost::`vftable'{for `SharingPlatform::ISessionMessageChannel'}
0x1800150d6  mov     [rcx], rax
0x1800150d9  lea     rax, ??_7SessionHost@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00UIWeakReferenceSource@@UISessionHostMessageChannel@SharingPlatform@@U?$CloakedIid@VICDPBinaryHostCallback@@@23@U?$CloakedIid@VICDPParticipantHandler@@@23@U?$CloakedIid@VICDPHostAuthorizationProvider@@@23@@Details@WRL@Microsoft@@@; const SharingPlatform::SessionHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,IWeakReferenceSource,SharingPlatform::ISessionHostMessageChannel,Microsoft::WRL::CloakedIid<ICDPBinaryHostCallback>,Microsoft::WRL::CloakedIid<ICDPParticipantHandler>,Microsoft::WRL::CloakedIid<ICDPHostAuthorizationProvider>>'}
0x1800150e0  mov     [rcx+8], rax
0x1800150e4  lea     rax, ??_7SessionHost@SharingPlatform@@6BISessionHostMessageChannel@1@@; const SharingPlatform::SessionHost::`vftable'{for `SharingPlatform::ISessionHostMessageChannel'}
0x1800150eb  mov     [rcx+10h], rax
0x1800150ef  lea     rax, ??_7SessionHost@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00U?$CloakedIid@VICDPBinaryHostCallback@@@23@U?$CloakedIid@VICDPParticipantHandler@@@23@U?$CloakedIid@VICDPHostAuthorizationProvider@@@23@@Details@WRL@Microsoft@@@; const SharingPlatform::SessionHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<ICDPBinaryHostCallback>,Microsoft::WRL::CloakedIid<ICDPParticipantHandler>,Microsoft::WRL::CloakedIid<ICDPHostAuthorizationProvider>>'}
0x1800150f6  mov     [rcx+18h], rax
0x1800150fa  lea     rax, ??_7SessionHost@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00VICDPParticipantHandler@@@Details@WRL@Microsoft@@@; const SharingPlatform::SessionHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,ICDPParticipantHandler>'}
0x180015101  mov     [rcx+20h], rax
0x180015105  lea     rax, ??_7SessionHost@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00U?$CloakedIid@VICDPHostAuthorizationProvider@@@23@@Details@WRL@Microsoft@@@; const SharingPlatform::SessionHost::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<ICDPHostAuthorizationProvider>>'}
0x18001510c  mov     [rcx+28h], rax
0x180015110  movzx   eax, byte ptr [rcx+7Fh]
0x180015114  mov     [rbp+arg_0], ax
0x180015118  movzx   eax, byte ptr [rcx+7Eh]
0x18001511c  mov     [rbp+arg_8], ax
0x180015120  movzx   eax, byte ptr [rcx+7Dh]
0x180015124  mov     [rbp+arg_10], ax
0x180015128  movzx   eax, byte ptr [rcx+7Ch]
0x18001512c  mov     [rbp+arg_18], ax
0x180015130  movzx   eax, byte ptr [rcx+7Bh]
0x180015134  mov     [rbp+var_18], ax
0x180015138  movzx   eax, byte ptr [rcx+7Ah]
0x18001513c  mov     [rbp+var_16], ax
0x180015140  movzx   eax, byte ptr [rcx+79h]
0x180015144  mov     [rbp+var_14], ax
0x180015148  movzx   eax, byte ptr [rcx+78h]
0x18001514c  mov     [rbp+var_12], ax
0x180015150  lea     rdx, [rcx+70h]
0x180015154  lea     r9, [rdx+6]
0x180015158  lea     r8, [rdx+4]
0x18001515c  lea     rax, [rbp+arg_0]
0x180015160  mov     [r11-30h], rax
0x180015164  lea     rax, [rbp+arg_8]
0x180015168  mov     [r11-38h], rax
0x18001516c  lea     rax, [rbp+arg_10]
0x180015170  mov     [r11-40h], rax
0x180015174  lea     rax, [rbp+arg_18]
0x180015178  mov     [r11-48h], rax
0x18001517c  lea     rax, [rbp+var_18]
0x180015180  mov     [r11-50h], rax
0x180015184  lea     rax, [rbp+var_16]
0x180015188  mov     [r11-58h], rax
0x18001518c  lea     rax, [rbp+var_14]
0x180015190  mov     [r11-60h], rax
0x180015194  lea     rax, [rbp+var_12]
0x180015198  mov     [r11-68h], rax
0x18001519c  lea     rcx, aSessionhostSes; "SessionHost::~SessionHost sessionId={%0"...
0x1800151a3  call    ??$LogInfo@AEAY0HA@$$CBGAEAKAEAGAEAGGGGGGGGG@RemoteSessionTraceProvider@@SAXAEAY0HA@$$CBGAEAKAEAG2$$QEAG3333333@Z; RemoteSessionTraceProvider::LogInfo<ushort const (&)[112],ulong &,ushort &,ushort &,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort>(ushort const (&)[112],ulong &,ushort &,ushort &,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&)
0x1800151a8  cmp     byte ptr [rbx+90h], 0
0x1800151af  jz      short loc_1800151B9
0x1800151b1  mov     rcx, rbx; this
0x1800151b4  call    ?Disconnect@SessionHost@SharingPlatform@@UEAAJXZ; SharingPlatform::SessionHost::Disconnect(void)
0x1800151b9  lea     rcx, [rbx+128h]
0x1800151c0  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@_KUGUIDComparer@Internal@SharingPlatform@@V?$allocator@U?$pair@$$CBU_GUID@@_K@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,unsigned __int64,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<_GUID,unsigned __int64,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned __int64>>,0>>(void)
0x1800151c5  lea     rcx, [rbx+120h]
0x1800151cc  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800151d1  lea     rcx, [rbx+110h]
0x1800151d8  call    ??1?$_Tree@V?$_Tmap_traits@_KV?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KV?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>>,0>>(void)
0x1800151dd  lea     rcx, [rbx+100h]
0x1800151e4  call    ??1?$_Tree@V?$_Tmap_traits@U_GUID@@_KUGUIDComparer@Internal@SharingPlatform@@V?$allocator@U?$pair@$$CBU_GUID@@_K@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<_GUID,unsigned __int64,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned __int64>>,0>>::~_Tree<std::_Tmap_traits<_GUID,unsigned __int64,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,unsigned __int64>>,0>>(void)
0x1800151e9  lea     rcx, [rbx+0F0h]
0x1800151f0  call    ??1?$_Tree@V?$_Tmap_traits@_KV?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KV?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>>>,0>>(void)
0x1800151f5  lea     rcx, [rbx+0E0h]
0x1800151fc  call    ??1?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCDPBinaryHostContainer@SharingPlatform@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VCDPBinaryHostContainer@SharingPlatform@@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<std::wstring,SharingPlatform::CDPBinaryHostContainer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,SharingPlatform::CDPBinaryHostContainer>>,0>>::~_Tree<std::_Tmap_traits<std::wstring,SharingPlatform::CDPBinaryHostContainer,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,SharingPlatform::CDPBinaryHostContainer>>,0>>(void)
0x180015201  lea     rcx, [rbx+0B8h]; lpCriticalSection
0x180015208  call    cs:__imp_DeleteCriticalSection
0x18001520e  lea     rcx, [rbx+0A0h]; this
0x180015215  call    ??1CDPBinaryHostContainer@SharingPlatform@@QEAA@XZ; SharingPlatform::CDPBinaryHostContainer::~CDPBinaryHostContainer(void)
0x18001521a  nop
0x18001521b  mov     rcx, [rbx+98h]
0x180015222  test    rcx, rcx
0x180015225  jz      short loc_18001523F
0x180015227  mov     qword ptr [rbx+98h], 0
0x180015232  mov     rax, [rcx]
0x180015235  mov     rax, [rax+10h]
0x180015239  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001523e  nop
0x18001523f  lea     rcx, [rbx+68h]
0x180015243  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180015248  lea     rcx, [rbx+40h]; lpCriticalSection
0x18001524c  call    cs:__imp_DeleteCriticalSection
0x180015252  mov     rcx, rbx
0x180015255  add     rsp, 78h
0x180015259  pop     rbx
0x18001525a  pop     rbp
0x18001525b  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00$00$0A@UISessionMessageChannel@SharingPlatform@@UISessionHostMessageChannel@5@U?$CloakedIid@VICDPBinaryHostCallback@@@23@U?$CloakedIid@VICDPParticipantHandler@@@23@U?$CloakedIid@VICDPHostAuthorizationProvider@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISessionMessageChannel,SharingPlatform::ISessionHostMessageChannel,Microsoft::WRL::CloakedIid<ICDPBinaryHostCallback>,Microsoft::WRL::CloakedIid<ICDPParticipantHandler>,Microsoft::WRL::CloakedIid<ICDPHostAuthorizationProvider>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISessionMessageChannel,SharingPlatform::ISessionHostMessageChannel,Microsoft::WRL::CloakedIid<ICDPBinaryHostCallback>,Microsoft::WRL::CloakedIid<ICDPParticipantHandler>,Microsoft::WRL::CloakedIid<ICDPHostAuthorizationProvider>>(void)
```
