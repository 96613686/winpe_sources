# SharingPlatform::BinarySessionStream::~BinarySessionStream(void)

- ea: `0x180050d7c`
- end: `0x180050ecc`
- name: `??1BinarySessionStream@SharingPlatform@@UEAA@XZ`
- size: `336`
- prototype: `void __fastcall(SharingPlatform::BinarySessionStream *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180050f00`

## callees

- `0x180004928`
- `0x18001b150`
- `0x18001bcfc`
- `0x180047b0c`
- `0x18004a4a0`
- `0x1800506f8`
- `0x180050d7c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050db6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180050db6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050e88`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180050e88`

## pseudocode

```c
void __fastcall SharingPlatform::BinarySessionStream::~BinarySessionStream(SharingPlatform::BinarySessionStream *this)
{
  int v2; // ecx
  char *v3; // rcx
  __int16 v4; // [rsp+70h] [rbp+27h] BYREF
  __int16 v5; // [rsp+72h] [rbp+29h] BYREF
  __int16 v6; // [rsp+74h] [rbp+2Bh] BYREF
  __int16 v7; // [rsp+76h] [rbp+2Dh] BYREF
  PCWSTR v8[5]; // [rsp+78h] [rbp+2Fh] BYREF
  __int16 v9; // [rsp+B0h] [rbp+67h] BYREF
  __int16 v10; // [rsp+B8h] [rbp+6Fh] BYREF
  __int16 v11; // [rsp+C0h] [rbp+77h] BYREF
  __int16 v12; // [rsp+C8h] [rbp+7Fh] BYREF

  *(_QWORD *)this = &SharingPlatform::BinarySessionStream::`vftable';
  *((_QWORD *)this + 1) = &SharingPlatform::BinarySessionStream::`vftable'{for `IWeakReferenceSource'};
  *((_QWORD *)this + 2) = &SharingPlatform::BinarySessionStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<9>,1,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceSessionChannelCallback>>'};
  v8[0] = WindowsGetStringRawBuffer(*((HSTRING *)this + 13), 0);
  v9 = *((unsigned __int8 *)this + 95);
  v10 = *((unsigned __int8 *)this + 94);
  v11 = *((unsigned __int8 *)this + 93);
  v12 = *((unsigned __int8 *)this + 92);
  v4 = *((unsigned __int8 *)this + 91);
  v5 = *((unsigned __int8 *)this + 90);
  v6 = *((unsigned __int8 *)this + 89);
  v7 = *((unsigned __int8 *)this + 88);
  RemoteSessionTraceProvider::LogVerbose<unsigned short const (&)[126],unsigned long &,unsigned short &,unsigned short &,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short const *>(
    v2,
    (_DWORD)this + 80,
    (_DWORD)this + 84,
    (_DWORD)this + 86,
    (__int64)&v7,
    (__int64)&v6,
    (__int64)&v5,
    (__int64)&v4,
    (__int64)&v12,
    (__int64)&v11,
    (__int64)&v10,
    (__int64)&v9,
    (__int64)v8);
  v3 = (char *)*((_QWORD *)this + 9);
  if ( v3 )
  {
    Sharing::OperationQueue::Shutdown(v3);
    Microsoft::WRL::ComPtr<Sharing::OperationQueue>::InternalRelease((char *)this + 72);
  }
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 96);
  WindowsDeleteString(*((HSTRING *)this + 13));
  *((_QWORD *)this + 13) = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 96);
  Microsoft::WRL::ComPtr<Sharing::OperationQueue>::InternalRelease((char *)this + 72);
  Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>((char *)this + 48);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 40);
  Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionBinaryChannel,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceSessionChannelCallback>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionBinaryChannel,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceSessionChannelCallback>>(this);
}

```

## disassembly

```asm
0x180050d7c  push    rbp
0x180050d7e  push    rbx
0x180050d7f  push    rsi
0x180050d80  push    rdi
0x180050d81  lea     rbp, [rsp-3Fh]
0x180050d86  sub     rsp, 88h
0x180050d8d  mov     rdi, rcx
0x180050d90  lea     rax, ??_7BinarySessionStream@SharingPlatform@@6B@; const SharingPlatform::BinarySessionStream::`vftable'
0x180050d97  mov     [rcx], rax
0x180050d9a  lea     rax, ??_7BinarySessionStream@SharingPlatform@@6BIWeakReferenceSource@@@; const SharingPlatform::BinarySessionStream::`vftable'{for `IWeakReferenceSource'}
0x180050da1  mov     [rcx+8], rax
0x180050da5  lea     rax, ??_7BinarySessionStream@SharingPlatform@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00U?$CloakedIid@UIDeviceSessionChannelCallback@SharingPlatform@@@23@@Details@WRL@Microsoft@@@; const SharingPlatform::BinarySessionStream::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<9>,1,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceSessionChannelCallback>>'}
0x180050dac  mov     [rcx+10h], rax
0x180050db0  xor     edx, edx; length
0x180050db2  mov     rcx, [rcx+68h]; string
0x180050db6  call    cs:__imp_WindowsGetStringRawBuffer
0x180050dbc  mov     [rbp+57h+var_28], rax
0x180050dc0  movzx   eax, byte ptr [rdi+5Fh]
0x180050dc4  mov     [rbp+57h+arg_0], ax
0x180050dc8  movzx   eax, byte ptr [rdi+5Eh]
0x180050dcc  mov     [rbp+57h+arg_8], ax
0x180050dd0  movzx   eax, byte ptr [rdi+5Dh]
0x180050dd4  mov     [rbp+57h+arg_10], ax
0x180050dd8  movzx   eax, byte ptr [rdi+5Ch]
0x180050ddc  mov     [rbp+57h+arg_18], ax
0x180050de0  movzx   eax, byte ptr [rdi+5Bh]
0x180050de4  mov     [rbp+57h+var_30], ax
0x180050de8  movzx   eax, byte ptr [rdi+5Ah]
0x180050dec  mov     [rbp+57h+var_2E], ax
0x180050df0  movzx   eax, byte ptr [rdi+59h]
0x180050df4  mov     [rbp+57h+var_2C], ax
0x180050df8  movzx   eax, byte ptr [rdi+58h]
0x180050dfc  mov     [rbp+57h+var_2A], ax
0x180050e00  lea     rdx, [rdi+50h]
0x180050e04  lea     r9, [rdx+6]
0x180050e08  lea     r8, [rdx+4]
0x180050e0c  lea     rax, [rbp+57h+var_28]
0x180050e10  mov     [rsp+0A0h+var_40], rax
0x180050e15  lea     rax, [rbp+57h+arg_0]
0x180050e19  mov     [rsp+0A0h+var_48], rax
0x180050e1e  lea     rax, [rbp+57h+arg_8]
0x180050e22  mov     [rsp+0A0h+var_50], rax
0x180050e27  lea     rax, [rbp+57h+arg_10]
0x180050e2b  mov     [rsp+0A0h+var_58], rax
0x180050e30  lea     rax, [rbp+57h+arg_18]
0x180050e34  mov     [rsp+0A0h+var_60], rax
0x180050e39  lea     rax, [rbp+57h+var_30]
0x180050e3d  mov     [rsp+0A0h+var_68], rax
0x180050e42  lea     rax, [rbp+57h+var_2E]
0x180050e46  mov     [rsp+0A0h+var_70], rax
0x180050e4b  lea     rax, [rbp+57h+var_2C]
0x180050e4f  mov     [rsp+0A0h+var_78], rax
0x180050e54  lea     rax, [rbp+57h+var_2A]
0x180050e58  mov     [rsp+0A0h+var_80], rax
0x180050e5d  call    ??$LogVerbose@AEAY0HO@$$CBGAEAKAEAGAEAGGGGGGGGGPEBG@RemoteSessionTraceProvider@@SAXAEAY0HO@$$CBGAEAKAEAG2$$QEAG3333333$$QEAPEBG@Z; RemoteSessionTraceProvider::LogVerbose<ushort const (&)[126],ulong &,ushort &,ushort &,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort const *>(ushort const (&)[126],ulong &,ushort &,ushort &,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort const * &&)
0x180050e62  lea     rsi, [rdi+48h]
0x180050e66  mov     rcx, [rsi]; pv
0x180050e69  test    rcx, rcx
0x180050e6c  jz      short loc_180050E7B
0x180050e6e  call    ?Shutdown@OperationQueue@Sharing@@QEAAJXZ; Sharing::OperationQueue::Shutdown(void)
0x180050e73  mov     rcx, rsi
0x180050e76  call    ?InternalRelease@?$ComPtr@VOperationQueue@Sharing@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Sharing::OperationQueue>::InternalRelease(void)
0x180050e7b  lea     rcx, [rdi+60h]
0x180050e7f  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180050e84  mov     rcx, [rdi+68h]; string
0x180050e88  call    cs:__imp_WindowsDeleteString
0x180050e8e  mov     qword ptr [rdi+68h], 0
0x180050e96  lea     rcx, [rdi+60h]
0x180050e9a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180050e9f  mov     rcx, rsi
0x180050ea2  call    ?InternalRelease@?$ComPtr@VOperationQueue@Sharing@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Sharing::OperationQueue>::InternalRelease(void)
0x180050ea7  lea     rcx, [rdi+30h]
0x180050eab  call    ??1?$EventSource@U?$ITypedEventHandler@PEAUISession@SharingPlatform@@PEAUISessionStateChangedEventArgs@2@@Foundation@Windows@@U?$InvokeModeOptions@$0?1@WRL@Microsoft@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>::~EventSource<Windows::Foundation::ITypedEventHandler<SharingPlatform::ISession *,SharingPlatform::ISessionStateChangedEventArgs *>,Microsoft::WRL::InvokeModeOptions<-2>>(void)
0x180050eb0  lea     rcx, [rdi+28h]
0x180050eb4  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180050eb9  mov     rcx, rdi
0x180050ebc  add     rsp, 88h
0x180050ec3  pop     rdi
0x180050ec4  pop     rsi
0x180050ec5  pop     rbx
0x180050ec6  pop     rbp
0x180050ec7  jmp     ??1?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UIDeviceSessionBinaryChannel@SharingPlatform@@U?$CloakedIid@UIDeviceSessionChannelCallback@SharingPlatform@@@23@@Details@WRL@Microsoft@@UEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionBinaryChannel,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceSessionChannelCallback>>::~RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionBinaryChannel,Microsoft::WRL::CloakedIid<SharingPlatform::IDeviceSessionChannelCallback>>(void)
```
