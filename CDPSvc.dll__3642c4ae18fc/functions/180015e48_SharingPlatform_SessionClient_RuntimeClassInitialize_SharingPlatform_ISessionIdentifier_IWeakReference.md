# SharingPlatform::SessionClient::RuntimeClassInitialize(SharingPlatform::ISessionIdentifier *,IWeakReference *)

- ea: `0x180015e48`
- end: `0x18001602f`
- name: `?RuntimeClassInitialize@SessionClient@SharingPlatform@@QEAAJPEAUISessionIdentifier@2@PEAUIWeakReference@@@Z`
- size: `487`
- prototype: `__int64 __fastcall(SharingPlatform::SessionClient *__hidden this, struct SharingPlatform::ISessionIdentifier *, struct IWeakReference *)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x18004666c`

## callees

- `0x180004928`
- `0x180010d04`
- `0x1800130ec`
- `0x180015e48`
- `0x18001620c`
- `0x180016248`
- `0x180016334`
- `0x1800225a0`
- `0x18003f9c8`
- `0x180048218`
- `0x1800506bc`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180015fa5`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180015fa5`

## string_xrefs

- `0x180015e89`: `Windows.Storage.Streams.DataReader`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SharingPlatform::SessionClient::RuntimeClassInitialize(
        SharingPlatform::SessionClient *this,
        struct SharingPlatform::ISessionIdentifier *a2,
        struct IWeakReference *a3)
{
  int v6; // edi
  __int64 v7; // rdx
  HANDLE Event; // rax
  __int64 v10; // rcx
  unsigned int v11; // ebx
  int v12; // [rsp+20h] [rbp-59h]
  __int16 v13; // [rsp+60h] [rbp-19h] BYREF
  __int16 v14; // [rsp+62h] [rbp-17h] BYREF
  __int16 v15; // [rsp+64h] [rbp-15h] BYREF
  __int16 v16; // [rsp+66h] [rbp-13h] BYREF
  __int16 v17; // [rsp+68h] [rbp-11h] BYREF
  __int16 v18; // [rsp+6Ah] [rbp-Fh] BYREF
  __int16 v19; // [rsp+6Ch] [rbp-Dh] BYREF
  __int16 v20; // [rsp+6Eh] [rbp-Bh] BYREF
  struct IInspectable *v21; // [rsp+70h] [rbp-9h] BYREF
  struct IWeakReference *v22; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  __int64 v24; // [rsp+98h] [rbp+1Fh]
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v24 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Storage.Streams.DataReader",
    0x23u,
    0x22u);
  v6 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IDataReaderStatics>>(
         v24,
         (__int64)this + 120);
  if ( v6 < 0 )
  {
    v7 = 55;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)".\\sessionclient.cpp",
      (const char *)(unsigned int)v6,
      v12);
    return (unsigned int)v6;
  }
  Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>::operator=((char *)this + 112);
  v6 = (*(__int64 (__fastcall **)(struct SharingPlatform::ISessionIdentifier *, char *))(*(_QWORD *)a2 + 48LL))(
         a2,
         (char *)this + 96);
  if ( v6 < 0 )
  {
    v7 = 58;
    goto LABEL_3;
  }
  v13 = *((unsigned __int8 *)this + 111);
  v14 = *((unsigned __int8 *)this + 110);
  v15 = *((unsigned __int8 *)this + 109);
  v16 = *((unsigned __int8 *)this + 108);
  v17 = *((unsigned __int8 *)this + 107);
  v18 = *((unsigned __int8 *)this + 106);
  v19 = *((unsigned __int8 *)this + 105);
  v20 = *((unsigned __int8 *)this + 104);
  RemoteSessionTraceProvider::LogInfo<unsigned short const (&)[112],unsigned long &,unsigned short &,unsigned short &,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short,unsigned short>(
    L"SessionClient::RuntimeClassInitialize sessionGUID={%08lX-%04hX-%04hX-%02hX%02hX-%02hX%02hX%02hX%02hX%02hX%02hX}",
    (__int64)&v20,
    (__int64)&v19,
    (__int64)&v18,
    (__int64)&v17,
    (__int64)&v16,
    (__int64)&v15,
    (__int64)&v14,
    (__int64)&v13);
  Event = CreateEventExW(0, 0, 1u, 0x1F0003u);
  Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(
    (char *)this + 496,
    Event);
  v22 = a3;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(&v22);
  v10 = *((_QWORD *)this + 71);
  *((_QWORD *)this + 71) = a3;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v21 = 0;
  v11 = Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(
          (SharingPlatform::SessionClient *)((char *)this + 568),
          &v21);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v21);
  return v11;
}

```

## disassembly

```asm
0x180015e48  mov     [rsp-8+arg_10], rbx
0x180015e4d  push    rbp
0x180015e4e  push    rsi
0x180015e4f  push    rdi
0x180015e50  push    r14
0x180015e52  push    r15
0x180015e54  lea     rbp, [rsp-37h]
0x180015e59  sub     rsp, 0B0h
0x180015e60  mov     rax, cs:__security_cookie
0x180015e67  xor     rax, rsp
0x180015e6a  mov     [rbp+57h+var_30], rax
0x180015e6e  mov     r15, r8
0x180015e71  mov     rsi, rdx
0x180015e74  mov     rbx, rcx
0x180015e77  mov     [rbp+57h+var_38], 0
0x180015e7f  mov     r9d, 22h ; '"'; unsigned int
0x180015e85  lea     r8d, [r9+1]; unsigned int
0x180015e89  lea     rdx, ?RuntimeClass_Windows_Storage_Streams_DataReader@@3QBGB; "Windows.Storage.Streams.DataReader"
0x180015e90  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180015e94  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180015e99  lea     rdx, [rbx+78h]
0x180015e9d  mov     rcx, [rbp+57h+var_38]
0x180015ea1  call    ??$GetActivationFactory@V?$ComPtr@UIDataReaderStatics@Streams@Storage@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIDataReaderStatics@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IDataReaderStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IDataReaderStatics>>)
0x180015ea6  mov     edi, eax
0x180015ea8  test    eax, eax
0x180015eaa  jns     short loc_180015ECB
0x180015eac  mov     edx, 37h ; '7'; void *
0x180015eb1  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x180015eb8  mov     r9d, edi; char *
0x180015ebb  mov     rcx, [rbp+5Fh]; this
0x180015ebf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180015ec4  mov     eax, edi
0x180015ec6  jmp     loc_18001600C
0x180015ecb  lea     rcx, [rbx+70h]
0x180015ecf  mov     rdx, rsi
0x180015ed2  call    ??4?$ComPtr@UIParticipantIdentifier@SharingPlatform@@@WRL@Microsoft@@QEAAAEAV012@PEAUIParticipantIdentifier@SharingPlatform@@@Z; Microsoft::WRL::ComPtr<SharingPlatform::IParticipantIdentifier>::operator=(SharingPlatform::IParticipantIdentifier *)
0x180015ed7  mov     rax, [rsi]
0x180015eda  lea     rdx, [rbx+60h]
0x180015ede  mov     rcx, rsi
0x180015ee1  mov     rax, [rax+30h]
0x180015ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015eea  mov     edi, eax
0x180015eec  test    eax, eax
0x180015eee  jns     short loc_180015EF7
0x180015ef0  mov     edx, 3Ah ; ':'
0x180015ef5  jmp     short loc_180015EB1
0x180015ef7  movzx   eax, byte ptr [rbx+6Fh]
0x180015efb  mov     word ptr [rbp+57h+var_70], ax
0x180015eff  movzx   eax, byte ptr [rbx+6Eh]
0x180015f03  mov     word ptr [rbp+57h+var_70+2], ax
0x180015f07  movzx   eax, byte ptr [rbx+6Dh]
0x180015f0b  mov     word ptr [rbp+57h+var_70+4], ax
0x180015f0f  movzx   eax, byte ptr [rbx+6Ch]
0x180015f13  mov     word ptr [rbp+57h+var_70+6], ax
0x180015f17  movzx   eax, byte ptr [rbx+6Bh]
0x180015f1b  mov     word ptr [rbp+57h+var_68], ax
0x180015f1f  movzx   eax, byte ptr [rbx+6Ah]
0x180015f23  mov     word ptr [rbp+57h+var_68+2], ax
0x180015f27  movzx   eax, byte ptr [rbx+69h]
0x180015f2b  mov     word ptr [rbp+57h+var_68+4], ax
0x180015f2f  movzx   eax, byte ptr [rbx+68h]
0x180015f33  mov     word ptr [rbp+57h+var_68+6], ax
0x180015f37  lea     r9, [rbx+66h]
0x180015f3b  lea     r8, [rbx+64h]
0x180015f3f  lea     rax, [rbp+57h+var_70]
0x180015f43  mov     [rsp+0D0h+var_78], rax; __int64
0x180015f48  lea     rax, [rbp+57h+var_70+2]
0x180015f4c  mov     [rsp+0D0h+var_80], rax; __int64
0x180015f51  lea     rax, [rbp+57h+var_70+4]
0x180015f55  mov     [rsp+0D0h+var_88], rax; __int64
0x180015f5a  lea     rax, [rbp+57h+var_70+6]
0x180015f5e  mov     [rsp+0D0h+var_90], rax; __int64
0x180015f63  lea     rax, [rbp+57h+var_68]
0x180015f67  mov     [rsp+0D0h+var_98], rax; __int64
0x180015f6c  lea     rax, [rbp+57h+var_68+2]
0x180015f70  mov     [rsp+0D0h+var_A0], rax; __int64
0x180015f75  lea     rax, [rbp+57h+var_68+4]
0x180015f79  mov     [rsp+0D0h+var_A8], rax; __int64
0x180015f7e  lea     rax, [rbp+57h+var_68+6]
0x180015f82  mov     [rsp+0D0h+var_B0], rax; __int64
0x180015f87  lea     rdx, [rbx+60h]
0x180015f8b  lea     rcx, aSessionclientR; "SessionClient::RuntimeClassInitialize s"...
0x180015f92  call    ??$LogInfo@AEAY0HA@$$CBGAEAKAEAGAEAGGGGGGGGG@RemoteSessionTraceProvider@@SAXAEAY0HA@$$CBGAEAKAEAG2$$QEAG3333333@Z; RemoteSessionTraceProvider::LogInfo<ushort const (&)[112],ulong &,ushort &,ushort &,ushort,ushort,ushort,ushort,ushort,ushort,ushort,ushort>(ushort const (&)[112],ulong &,ushort &,ushort &,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&,ushort &&)
0x180015f97  xor     edx, edx; lpName
0x180015f99  xor     ecx, ecx; lpEventAttributes
0x180015f9b  mov     r9d, 1F0003h; dwDesiredAccess
0x180015fa1  lea     r8d, [rdx+1]; dwFlags
0x180015fa5  call    cs:__imp_CreateEventExW
0x180015fab  mov     rdx, rax
0x180015fae  lea     rcx, [rbx+1F0h]
0x180015fb5  call    ?Attach@?$HandleT@UEventTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXPEAX@Z; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::EventTraits>::Attach(void *)
0x180015fba  mov     [rbp+57h+var_58], r15
0x180015fbe  lea     rcx, [rbp+57h+var_58]
0x180015fc2  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x180015fc7  mov     rcx, [rbx+238h]
0x180015fce  mov     [rbx+238h], r15
0x180015fd5  test    rcx, rcx
0x180015fd8  jz      short loc_180015FE7
0x180015fda  mov     rax, [rcx]
0x180015fdd  mov     rax, [rax+10h]
0x180015fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fe6  nop
0x180015fe7  mov     [rbp+57h+var_60], 0
0x180015fef  lea     rdx, [rbp+57h+var_60]; struct IInspectable **
0x180015ff3  lea     rcx, [rbx+238h]; this
0x180015ffa  call    ??$As@UISessionMessageChannelCallback@SharingPlatform@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>>)
0x180015fff  mov     ebx, eax
0x180016001  lea     rcx, [rbp+57h+var_60]
0x180016005  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18001600a  mov     eax, ebx
0x18001600c  mov     rcx, [rbp+57h+var_30]
0x180016010  xor     rcx, rsp; StackCookie
0x180016013  call    __security_check_cookie
0x180016018  mov     rbx, [rsp+0D0h+arg_10]
0x180016020  add     rsp, 0B0h
0x180016027  pop     r15
0x180016029  pop     r14
0x18001602b  pop     rdi
0x18001602c  pop     rsi
0x18001602d  pop     rbp
0x18001602e  retn
```
