# SharingPlatform::Session::Session(void)

- ea: `0x18004766c`
- end: `0x18004781b`
- name: `??0Session@SharingPlatform@@QEAA@XZ`
- size: `431`
- prototype: `__int64 __fastcall(SharingPlatform::Session *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800464b4`
- `0x180046590`

## callees

- `0x180047450`
- `0x18004766c`
- `0x18004f538`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180047806`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x180047806`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004777e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004778b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004779f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800477ac`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800477c0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800477cd`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800477e1`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800477ee`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004777e`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004778b`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x18004779f`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800477ac`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800477c0`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800477cd`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800477e1`
- `api-ms-win-core-synch-l1-1-0!InitializeSRWLock` at `0x1800477ee`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004772b`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18004772b`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
SharingPlatform::Session *__fastcall SharingPlatform::Session::Session(SharingPlatform::Session *this)
{
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>();
  *(_QWORD *)this = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<11>,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::`vftable';
  *((_QWORD *)this + 1) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<11>,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<11>,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'};
  *((_QWORD *)this + 3) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<11>,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,SharingPlatform::ISessionMessageChannelCallback>'};
  *((_QWORD *)this + 4) = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<11>,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'};
  if ( Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  *(_QWORD *)this = &SharingPlatform::Session::`vftable';
  *((_QWORD *)this + 1) = &SharingPlatform::Session::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'};
  *((_QWORD *)this + 3) = &SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,SharingPlatform::ISessionMessageChannelCallback>'};
  *((_QWORD *)this + 4) = &SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'};
  *(GUID *)((char *)this + 56) = GUID_NULL;
  *(GUID *)((char *)this + 88) = GUID_NULL;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)this + 104), 0, 0);
  *((_DWORD *)this + 36) = 0;
  *((_QWORD *)this + 19) = 0;
  *((_QWORD *)this + 20) = 0;
  *((_WORD *)this + 84) = 256;
  *((_QWORD *)this + 22) = 0;
  *((_QWORD *)this + 23) = 0;
  *((_QWORD *)this + 24) = 0;
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::_Alloc_sentinel_and_proxy();
  *((_QWORD *)this + 25) = 0;
  *((_QWORD *)this + 26) = 0;
  InitializeSRWLock((PSRWLOCK)this + 27);
  InitializeSRWLock((PSRWLOCK)this + 28);
  *((_QWORD *)this + 29) = 0;
  InitializeSRWLock((PSRWLOCK)this + 30);
  InitializeSRWLock((PSRWLOCK)this + 31);
  *((_QWORD *)this + 32) = 0;
  InitializeSRWLock((PSRWLOCK)this + 33);
  InitializeSRWLock((PSRWLOCK)this + 34);
  *((_QWORD *)this + 35) = 0;
  InitializeSRWLock((PSRWLOCK)this + 36);
  InitializeSRWLock((PSRWLOCK)this + 37);
  *((_QWORD *)this + 38) = 0;
  *((_QWORD *)this + 39) = 0;
  CoCreateGuid((GUID *)((char *)this + 72));
  return this;
}

```

## disassembly

```asm
0x18004766c  mov     [rsp+arg_10], rbx
0x180047671  mov     [rsp+arg_0], rcx
0x180047676  push    rdi
0x180047677  sub     rsp, 20h
0x18004767b  mov     rbx, rcx
0x18004767e  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00$00$0A@UISession@SharingPlatform@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>(void)
0x180047683  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@UISession@SharingPlatform@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<11>,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::`vftable'
0x18004768a  mov     [rbx], rcx
0x18004768d  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@UISession@SharingPlatform@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@WRL@Microsoft@@6BIWeakReferenceSource@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<11>,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::`vftable'{for `IWeakReferenceSource'}
0x180047694  mov     [rbx+8], rax
0x180047698  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@UISession@SharingPlatform@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<11>,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'}
0x18004769f  mov     [rbx+10h], rax
0x1800476a3  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@UISession@SharingPlatform@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00UISessionMessageChannelCallback@SharingPlatform@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<11>,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,SharingPlatform::ISessionMessageChannelCallback>'}
0x1800476aa  mov     [rbx+18h], rax
0x1800476ae  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@UISession@SharingPlatform@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<11>,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'}
0x1800476b5  mov     [rbx+20h], rax
0x1800476b9  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x1800476c0  xor     edi, edi
0x1800476c2  test    rcx, rcx
0x1800476c5  jz      short loc_1800476D4
0x1800476c7  mov     rax, [rcx]
0x1800476ca  mov     rax, [rax+8]
0x1800476ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476d3  nop
0x1800476d4  lea     rax, ??_7Session@SharingPlatform@@6B@; const SharingPlatform::Session::`vftable'
0x1800476db  mov     [rbx], rax
0x1800476de  lea     rax, ??_7Session@SharingPlatform@@6BIWeakReferenceSource@@@; const SharingPlatform::Session::`vftable'{for `IWeakReferenceSource'}
0x1800476e5  mov     [rbx+8], rax
0x1800476e9  lea     rax, ??_7Session@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@Details@WRL@Microsoft@@@; const SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'}
0x1800476f0  mov     [rbx+10h], rax
0x1800476f4  lea     rax, ??_7Session@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00UISessionMessageChannelCallback@SharingPlatform@@@Details@WRL@Microsoft@@@; const SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,SharingPlatform::ISessionMessageChannelCallback>'}
0x1800476fb  mov     [rbx+18h], rax
0x1800476ff  lea     rax, ??_7Session@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@Details@WRL@Microsoft@@@; const SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'}
0x180047706  mov     [rbx+20h], rax
0x18004770a  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180047711  movdqu  xmmword ptr [rbx+38h], xmm0
0x180047716  movups  xmm1, xmmword ptr cs:GUID_NULL.Data1
0x18004771d  movdqu  xmmword ptr [rbx+58h], xmm1
0x180047722  lea     rcx, [rbx+68h]; lpCriticalSection
0x180047726  xor     r8d, r8d; Flags
0x180047729  xor     edx, edx; dwSpinCount
0x18004772b  call    cs:__imp_InitializeCriticalSectionEx
0x180047731  nop
0x180047732  mov     [rbx+90h], edi
0x180047738  mov     [rbx+98h], rdi
0x18004773f  mov     [rbx+0A0h], rdi
0x180047746  mov     word ptr [rbx+0A8h], 100h
0x18004774f  mov     [rbx+0B0h], rdi
0x180047756  lea     rcx, [rbx+0B8h]
0x18004775d  mov     [rcx], rdi
0x180047760  mov     [rcx+8], rdi
0x180047764  call    ?_Alloc_sentinel_and_proxy@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@VWeakRef@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@$0A@@std@@@std@@IEAAXXZ; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::_Alloc_sentinel_and_proxy(void)
0x180047769  mov     [rbx+0C8h], rdi
0x180047770  mov     [rbx+0D0h], rdi
0x180047777  lea     rcx, [rbx+0D8h]; SRWLock
0x18004777e  call    cs:__imp_InitializeSRWLock
0x180047784  lea     rcx, [rbx+0E0h]; SRWLock
0x18004778b  call    cs:__imp_InitializeSRWLock
0x180047791  mov     [rbx+0E8h], rdi
0x180047798  lea     rcx, [rbx+0F0h]; SRWLock
0x18004779f  call    cs:__imp_InitializeSRWLock
0x1800477a5  lea     rcx, [rbx+0F8h]; SRWLock
0x1800477ac  call    cs:__imp_InitializeSRWLock
0x1800477b2  mov     [rbx+100h], rdi
0x1800477b9  lea     rcx, [rbx+108h]; SRWLock
0x1800477c0  call    cs:__imp_InitializeSRWLock
0x1800477c6  lea     rcx, [rbx+110h]; SRWLock
0x1800477cd  call    cs:__imp_InitializeSRWLock
0x1800477d3  mov     [rbx+118h], rdi
0x1800477da  lea     rcx, [rbx+120h]; SRWLock
0x1800477e1  call    cs:__imp_InitializeSRWLock
0x1800477e7  lea     rcx, [rbx+128h]; SRWLock
0x1800477ee  call    cs:__imp_InitializeSRWLock
0x1800477f4  mov     [rbx+130h], rdi
0x1800477fb  mov     [rbx+138h], rdi
0x180047802  lea     rcx, [rbx+48h]; pguid
0x180047806  call    cs:__imp_CoCreateGuid
0x18004780c  nop
0x18004780d  mov     rax, rbx
0x180047810  mov     rbx, [rsp+28h+arg_10]
0x180047815  add     rsp, 20h
0x180047819  pop     rdi
0x18004781a  retn
```
