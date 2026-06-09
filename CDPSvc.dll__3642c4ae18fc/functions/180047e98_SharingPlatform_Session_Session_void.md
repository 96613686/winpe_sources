# SharingPlatform::Session::~Session(void)

- ea: `0x180047e98`
- end: `0x180048083`
- name: `??1Session@SharingPlatform@@UEAA@XZ`
- size: `491`
- prototype: `void __fastcall(SharingPlatform::Session *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800486d0`

## callees

- `0x180004928`
- `0x180010c38`
- `0x18001b150`
- `0x1800411b0`
- `0x180045174`
- `0x180047b0c`
- `0x180047c38`
- `0x180047e98`
- `0x1800493fc`
- `0x18004a4a0`
- `0x18004fa00`
- `0x180056f24`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004806a`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18004806a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048049`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180048049`

## pseudocode

```c
void __fastcall SharingPlatform::Session::~Session(SharingPlatform::Session *this)
{
  void *v2; // rcx
  SharingPlatform::SessionStatics *v3; // rbx
  __int16 v4; // [rsp+68h] [rbp+17h] BYREF
  __int16 v5; // [rsp+6Ah] [rbp+19h] BYREF
  __int16 v6; // [rsp+6Ch] [rbp+1Bh] BYREF
  _WORD v7[5]; // [rsp+6Eh] [rbp+1Dh] BYREF
  _OWORD v8[3]; // [rsp+78h] [rbp+27h] BYREF
  __int16 v9; // [rsp+B8h] [rbp+67h] BYREF
  __int16 v10; // [rsp+C0h] [rbp+6Fh] BYREF
  __int16 v11; // [rsp+C8h] [rbp+77h] BYREF
  __int16 v12; // [rsp+D0h] [rbp+7Fh] BYREF

  *(_QWORD *)this = &SharingPlatform::Session::`vftable';
  *((_QWORD *)this + 1) = &SharingPlatform::Session::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'};
  *((_QWORD *)this + 3) = &SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,SharingPlatform::ISessionMessageChannelCallback>'};
  *((_QWORD *)this + 4) = &SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'};
  v9 = *((unsigned __int8 *)this + 71);
  v10 = *((unsigned __int8 *)this + 70);
  v11 = *((unsigned __int8 *)this + 69);
  v12 = *((unsigned __int8 *)this + 68);
  v4 = *((unsigned __int8 *)this + 67);
  v5 = *((unsigned __int8 *)this + 66);
  v6 = *((unsigned __int8 *)this + 65);
  v7[0] = *((unsigned __int8 *)this + 64);
  RemoteSessionTraceProvider::LogInfo<unsigned short const (&)[90],unsigned long &,unsigned short &,unsigned short &,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
    (_DWORD)this,
    (_DWORD)this + 56,
    (_DWORD)this + 60,
    (_DWORD)this + 62,
    (__int64)v7,
    (__int64)&v6,
    (__int64)&v5,
    (__int64)&v4,
    (__int64)&v12,
    (__int64)&v11,
    (__int64)&v10,
    (__int64)&v9);
  v2 = (void *)*((_QWORD *)this + 38);
  if ( v2 )
  {
    Sharing::OperationQueue::Shutdown(v2);
    Microsoft::WRL::ComPtr<Sharing::OperationQueue>::InternalRelease((char *)this + 304);
  }
  if ( *((_BYTE *)this + 168) )
    SharingPlatform::Internal::SessionsList::Remove(this);
  v3 = (SharingPlatform::SessionStatics *)*((_QWORD *)this + 39);
  v8[0] = *(_OWORD *)((char *)this + 72);
  SharingPlatform::SessionStatics::DecrementNumberOfHostedSessions(v3, this);
  std::_Tree<std::_Tmap_traits<_GUID,Microsoft::WRL::WeakRef,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,Microsoft::WRL::WeakRef>>,0>>::erase(
    (char *)v3 + 88,
    v8);
  if ( *((_QWORD *)this + 39) )
  {
    *((_QWORD *)this + 39) = 0;
    Microsoft::WRL::ActivationFactory<SharingPlatform::IDeviceSessionQueryStatic,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release();
  }
  Microsoft::WRL::ComPtr<Sharing::OperationQueue>::InternalRelease((char *)this + 304);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 280);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 256);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 232);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 208);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 200);
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>((char *)this + 184);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 176);
  WindowsDeleteString(*((HSTRING *)this + 20));
  *((_QWORD *)this + 20) = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 152);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>(this);
}

```

## disassembly

```asm
0x180047e98  mov     r11, rsp
0x180047e9b  push    rbp
0x180047e9c  push    rbx
0x180047e9d  push    rsi
0x180047e9e  push    rdi
0x180047e9f  lea     rbp, [r11-5Fh]
0x180047ea3  sub     rsp, 88h
0x180047eaa  mov     rdi, rcx
0x180047ead  lea     rax, ??_7Session@SharingPlatform@@6B@; const SharingPlatform::Session::`vftable'
0x180047eb4  mov     [rcx], rax
0x180047eb7  lea     rax, ??_7Session@SharingPlatform@@6BIWeakReferenceSource@@@; const SharingPlatform::Session::`vftable'{for `IWeakReferenceSource'}
0x180047ebe  mov     [rcx+8], rax
0x180047ec2  lea     rax, ??_7Session@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@Details@WRL@Microsoft@@@; const SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'}
0x180047ec9  mov     [rcx+10h], rax
0x180047ecd  lea     rax, ??_7Session@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00UISessionMessageChannelCallback@SharingPlatform@@@Details@WRL@Microsoft@@@; const SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,SharingPlatform::ISessionMessageChannelCallback>'}
0x180047ed4  mov     [rcx+18h], rax
0x180047ed8  lea     rax, ??_7Session@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@Details@WRL@Microsoft@@@; const SharingPlatform::Session::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<11>,1,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>'}
0x180047edf  mov     [rcx+20h], rax
0x180047ee3  movzx   eax, byte ptr [rcx+47h]
0x180047ee7  mov     [rbp+57h+arg_0], ax
0x180047eeb  movzx   eax, byte ptr [rcx+46h]
0x180047eef  mov     [rbp+57h+arg_8], ax
0x180047ef3  movzx   eax, byte ptr [rcx+45h]
0x180047ef7  mov     [rbp+57h+arg_10], ax
0x180047efb  movzx   eax, byte ptr [rcx+44h]
0x180047eff  mov     [rbp+57h+arg_18], ax
0x180047f03  movzx   eax, byte ptr [rcx+43h]
0x180047f07  mov     [rbp+57h+var_40], ax
0x180047f0b  movzx   eax, byte ptr [rcx+42h]
0x180047f0f  mov     [rbp+57h+var_3E], ax
0x180047f13  movzx   eax, byte ptr [rcx+41h]
0x180047f17  mov     [rbp+57h+var_3C], ax
0x180047f1b  movzx   eax, byte ptr [rcx+40h]
0x180047f1f  mov     [rbp+57h+var_3A], ax
0x180047f23  lea     rdx, [rcx+38h]
0x180047f27  lea     r9, [rdx+6]
0x180047f2b  lea     r8, [rdx+4]
0x180047f2f  lea     rax, [rbp+57h+arg_0]
0x180047f33  mov     [r11-50h], rax
0x180047f37  lea     rax, [rbp+57h+arg_8]
0x180047f3b  mov     [r11-58h], rax
0x180047f3f  lea     rax, [rbp+57h+arg_10]
0x180047f43  mov     [r11-60h], rax
0x180047f47  lea     rax, [rbp+57h+arg_18]
0x180047f4b  mov     [r11-68h], rax
0x180047f4f  lea     rax, [rbp+57h+var_40]
0x180047f53  mov     [r11-70h], rax
0x180047f57  lea     rax, [rbp+57h+var_3E]
0x180047f5b  mov     [r11-78h], rax
0x180047f5f  lea     rax, [rbp+57h+var_3C]
0x180047f63  mov     [r11-80h], rax
0x180047f67  lea     rax, [rbp+57h+var_3A]
0x180047f6b  mov     [rsp+20h], rax
0x180047f70  call    ??$LogInfo@AEAY0FK@$$CBGAEAKAEAGAEAGGGGGGGGG@RemoteSessionTraceProvider@@SAXAEAY0FK@$$CBGAEAKAEAG2$$QEAG3333333@Z; RemoteSessionTraceProvider::LogInfo<ushort const (&)[90],ulong &,ushort &,ushort &,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort>(ushort const (&)[90],ulong &,ushort &,ushort &,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&)
0x180047f75  lea     rsi, [rdi+130h]
0x180047f7c  mov     rcx, [rsi]; pv
0x180047f7f  test    rcx, rcx
0x180047f82  jz      short loc_180047F91
0x180047f84  call    ?Shutdown@OperationQueue@Sharing@@QEAAJXZ; Sharing::OperationQueue::Shutdown(void)
0x180047f89  mov     rcx, rsi
0x180047f8c  call    ?InternalRelease@?$ComPtr@VOperationQueue@Sharing@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Sharing::OperationQueue>::InternalRelease(void)
0x180047f91  cmp     byte ptr [rdi+0A8h], 0
0x180047f98  jz      short loc_180047FA2
0x180047f9a  mov     rcx, rdi; struct SharingPlatform::ISession *
0x180047f9d  call    ?Remove@SessionsList@Internal@SharingPlatform@@SAXPEAUISession@3@@Z; SharingPlatform::Internal::SessionsList::Remove(SharingPlatform::ISession *)
0x180047fa2  mov     rbx, [rdi+138h]
0x180047fa9  movups  xmm0, xmmword ptr [rdi+48h]
0x180047fad  movdqu  [rbp+57h+var_30], xmm0
0x180047fb2  mov     rdx, rdi; struct SharingPlatform::ISession *
0x180047fb5  mov     rcx, rbx; this
0x180047fb8  call    ?DecrementNumberOfHostedSessions@SessionStatics@SharingPlatform@@AEAAJPEAUISession@2@@Z; SharingPlatform::SessionStatics::DecrementNumberOfHostedSessions(SharingPlatform::ISession *)
0x180047fbd  lea     rcx, [rbx+58h]
0x180047fc1  lea     rdx, [rbp+57h+var_30]
0x180047fc5  call    ?erase@?$_Tree@V?$_Tmap_traits@U_GUID@@VWeakRef@WRL@Microsoft@@UGUIDComparer@Internal@SharingPlatform@@V?$allocator@U?$pair@$$CBU_GUID@@VWeakRef@WRL@Microsoft@@@std@@@std@@$0A@@std@@@std@@QEAA_KAEBU_GUID@@@Z; std::_Tree<std::_Tmap_traits<_GUID,Microsoft::WRL::WeakRef,SharingPlatform::Internal::GUIDComparer,std::allocator<std::pair<_GUID const,Microsoft::WRL::WeakRef>>,0>>::erase(_GUID const &)
0x180047fca  mov     rcx, [rdi+138h]
0x180047fd1  test    rcx, rcx
0x180047fd4  jz      short loc_180047FE6
0x180047fd6  mov     qword ptr [rdi+138h], 0
0x180047fe1  call    ?Release@?$ActivationFactory@UIDeviceSessionQueryStatic@SharingPlatform@@VNil@Details@WRL@Microsoft@@V3456@$0A@@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::ActivationFactory<SharingPlatform::IDeviceSessionQueryStatic,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)
0x180047fe6  mov     rcx, rsi
0x180047fe9  call    ?InternalRelease@?$ComPtr@VOperationQueue@Sharing@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Sharing::OperationQueue>::InternalRelease(void)
0x180047fee  lea     rcx, [rdi+118h]
0x180047ff5  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUISession@SharingPlatform@@PEAUISessionStateChangedEventArgs@2@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x180047ffa  lea     rcx, [rdi+100h]
0x180048001  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUISession@SharingPlatform@@PEAUISessionStateChangedEventArgs@2@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x180048006  lea     rcx, [rdi+0E8h]
0x18004800d  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUISession@SharingPlatform@@PEAUISessionStateChangedEventArgs@2@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x180048012  lea     rcx, [rdi+0D0h]
0x180048019  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUISession@SharingPlatform@@PEAUISessionStateChangedEventArgs@2@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x18004801e  lea     rcx, [rdi+0C8h]
0x180048025  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18004802a  lea     rcx, [rdi+0B8h]
0x180048031  call    ??1?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@VWeakRef@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::~_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>(void)
0x180048036  lea     rcx, [rdi+0B0h]
0x18004803d  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180048042  mov     rcx, [rdi+0A0h]; string
0x180048049  call    cs:__imp_WindowsDeleteString
0x18004804f  mov     qword ptr [rdi+0A0h], 0
0x18004805a  lea     rcx, [rdi+98h]
0x180048061  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180048066  lea     rcx, [rdi+68h]; lpCriticalSection
0x18004806a  call    cs:__imp_DeleteCriticalSection
0x180048070  mov     rcx, rdi
0x180048073  add     rsp, 88h
0x18004807a  pop     rdi
0x18004807b  pop     rsi
0x18004807c  pop     rbx
0x18004807d  pop     rbp
0x18004807e  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$0L@@WRL@Microsoft@@$00$00$0A@UISession@SharingPlatform@@UIClosable@Foundation@Windows@@U?$CloakedIid@UISessionMessageChannelCallback@SharingPlatform@@@23@U?$CloakedIid@UISessionInternal@SharingPlatform@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<11>,1,1,0,SharingPlatform::ISession,Windows::Foundation::IClosable,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionMessageChannelCallback>,Microsoft::WRL::CloakedIid<SharingPlatform::ISessionInternal>>(void)
```
