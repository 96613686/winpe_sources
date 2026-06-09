# SharingPlatform::Session::AddChannel(HSTRING__ *,uchar,SharingPlatform::IDeviceSessionChannelCallback *,SharingPlatform::IDeviceSessionChannel * *)

- ea: `0x180011de0`
- end: `0x180012373`
- name: `?AddChannel@Session@SharingPlatform@@UEAAJPEAUHSTRING__@@EPEAUIDeviceSessionChannelCallback@2@PEAPEAUIDeviceSessionChannel@2@@Z`
- size: `1427`
- prototype: `int(SharingPlatform::Session *__hidden this, HSTRING, unsigned __int8, struct SharingPlatform::IDeviceSessionChannelCallback *, struct SharingPlatform::IDeviceSessionChannel **)`
- caller_count: `0`
- callee_count: `17`
- tags: `broker_com_uri`

## callees

- `0x180004490`
- `0x180007410`
- `0x180010f00`
- `0x180011de0`
- `0x1800130ec`
- `0x180013168`
- `0x1800161d4`
- `0x18001f5ec`
- `0x1800225a0`
- `0x180046ad8`
- `0x18004729c`
- `0x180048e48`
- `0x18004c390`
- `0x18004d1c4`
- `0x18004fac8`
- `0x180055f04`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ffa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012087`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012112`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001215d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180011ffa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012087`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180012112`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001215d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fa2`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180011fa2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011eaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180011eaf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012022`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800120af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001213a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800121f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800122db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012333`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180011f80`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012022`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800120af`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001213a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800121f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800122db`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180012333`

## pseudocode

```c
// Hidden C++ exception states: #wind=8 #try_helpers=1
__int64 __fastcall SharingPlatform::Session::AddChannel(
        SharingPlatform::Session *this,
        HSTRING a2,
        unsigned __int8 a3,
        struct SharingPlatform::IDeviceSessionChannelCallback *a4,
        struct SharingPlatform::IDeviceSessionChannel **a5)
{
  const unsigned __int16 *StringRawBuffer; // rbx
  __int64 v11; // rax
  int v12; // eax
  unsigned int v13; // ebx
  _QWORD *v14; // rcx
  __int64 v15; // r8
  _QWORD *v16; // rcx
  int v17; // eax
  int CanCastTo; // edi
  _QWORD *v19; // rcx
  _QWORD *v20; // rcx
  int v21; // eax
  unsigned int v22; // r14d
  _QWORD *v23; // rcx
  struct SharingPlatform::IDeviceSessionChannel *v24; // rbx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // r9
  __int64 v28; // rdx
  _QWORD *v29; // rcx
  _QWORD *v30; // rcx
  int v31; // [rsp+20h] [rbp-1F8h]
  int v32; // [rsp+20h] [rbp-1F8h]
  _QWORD *v33; // [rsp+30h] [rbp-1E8h] BYREF
  int v34; // [rsp+38h] [rbp-1E0h] BYREF
  HSTRING string; // [rsp+40h] [rbp-1D8h] BYREF
  struct SharingPlatform::IDeviceSessionChannel *v36; // [rsp+48h] [rbp-1D0h] BYREF
  struct _GUID v37; // [rsp+50h] [rbp-1C8h] BYREF
  HSTRING v38; // [rsp+60h] [rbp-1B8h] BYREF
  __int64 v39; // [rsp+68h] [rbp-1B0h] BYREF
  char v40; // [rsp+70h] [rbp-1A8h]
  _QWORD v41[42]; // [rsp+80h] [rbp-198h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+0h]

  v38 = a2;
  LOBYTE(v34) = a3;
  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12B,
      (unsigned int)".\\session.cpp",
      (const char *)0x80070057LL,
      v31);
    return 2147942487LL;
  }
  if ( !a4 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12C,
      (unsigned int)".\\session.cpp",
      (const char *)0x80070057LL,
      v31);
    return 2147942487LL;
  }
  if ( !a5 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12D,
      (unsigned int)".\\session.cpp",
      (const char *)0x80004003LL,
      v31);
    return 2147500035LL;
  }
  StringRawBuffer = WindowsGetStringRawBuffer(a2, 0);
  wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(
    v41,
    "SessionAddChannel");
  v41[0] = &RemoteSessionTraceProvider::SessionAddChannel::`vftable';
  v37 = *(struct _GUID *)((char *)this + 56);
  RemoteSessionTraceProvider::SessionAddChannel::StartActivity(
    (RemoteSessionTraceProvider::SessionAddChannel *)v41,
    &v37,
    StringRawBuffer,
    a3);
  SharingPlatform::Internal::MakeChannelLocator(&string, (char *)this + 56, a2);
  v33 = 0;
  v36 = (struct SharingPlatform::IDeviceSessionChannel *)&v33;
  v11 = Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(&v36);
  v12 = Microsoft::WRL::AsWeak<SharingPlatform::IDeviceSessionChannelCallback>(a4, v11);
  v13 = v12;
  if ( v12 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x134,
      (unsigned int)".\\session.cpp",
      (const char *)(unsigned int)v12,
      v31);
    v14 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v14 + 16LL))(v14);
    }
    WindowsDeleteString(string);
    RemoteSessionTraceProvider::SessionAddChannel::~SessionAddChannel((RemoteSessionTraceProvider::SessionAddChannel *)v41);
    return v13;
  }
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  *(_QWORD *)&v37.Data1 = (char *)this + 104;
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::find(
    (char *)this + 184,
    &v36,
    &string);
  if ( v36 != *((struct SharingPlatform::IDeviceSessionChannel **)this + 23) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13A,
      (unsigned int)".\\session.cpp",
      (const char *)0x800700B7LL,
      v31);
    if ( this != (SharingPlatform::Session *)-104LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    v16 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v16 + 16LL))(v16);
    }
LABEL_16:
    WindowsDeleteString(string);
    RemoteSessionTraceProvider::SessionAddChannel::~SessionAddChannel((RemoteSessionTraceProvider::SessionAddChannel *)v41);
    return 2147942583LL;
  }
  LOBYTE(v15) = a3 != 0;
  v17 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, __int64))(**((_QWORD **)this + 25) + 80LL))(
          *((_QWORD *)this + 25),
          string,
          v15);
  CanCastTo = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13C,
      (unsigned int)".\\session.cpp",
      (const char *)(unsigned int)v17,
      v31);
    if ( this != (SharingPlatform::Session *)-104LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    v19 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v19 + 16LL))(v19);
    }
LABEL_22:
    WindowsDeleteString(string);
    RemoteSessionTraceProvider::SessionAddChannel::~SessionAddChannel((RemoteSessionTraceProvider::SessionAddChannel *)v41);
    return (unsigned int)CanCastTo;
  }
  std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::_Emplace<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef &>(
    (char *)this + 184,
    &v39,
    &string,
    &v33);
  if ( !v40 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x13F,
      (unsigned int)".\\session.cpp",
      (const char *)0x800700B7LL,
      v31);
    if ( this != (SharingPlatform::Session *)-104LL )
      LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
    v20 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v20 + 16LL))(v20);
    }
    goto LABEL_16;
  }
  if ( this != (SharingPlatform::Session *)-104LL )
    LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  v36 = 0;
  v39 = *((_QWORD *)this + 20);
  *(_QWORD *)&v37.Data1 = this;
  v21 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::DeviceSessionChannel,SharingPlatform::DeviceSessionChannel,SharingPlatform::Session *,HSTRING__ *,HSTRING__ * &,unsigned char &>(
          (unsigned int)&v36,
          (unsigned int)&v37,
          (unsigned int)&v39,
          (unsigned int)&v38,
          (__int64)&v34);
  v22 = v21;
  if ( v21 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x146,
      (unsigned int)".\\session.cpp",
      (const char *)(unsigned int)v21,
      v32);
    if ( v36 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionChannel>::Release(v36);
    v23 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
    }
    WindowsDeleteString(string);
    RemoteSessionTraceProvider::SessionAddChannel::~SessionAddChannel((RemoteSessionTraceProvider::SessionAddChannel *)v41);
    return v22;
  }
  v24 = v36;
  *a5 = 0;
  if ( (unsigned int)InlineIsEqualGUID(
                       &GUID_9fda45aa_73c9_404b_bc95_1108ea66e487,
                       &GUID_00000000_0000_0000_c000_000000000046)
    || (unsigned int)InlineIsEqualGUID(v25, &GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90) )
  {
    *a5 = v24;
    (*(void (__fastcall **)(struct SharingPlatform::IDeviceSessionChannel *))(*(_QWORD *)v24 + 8LL))(v24);
    CanCastTo = 0;
    goto LABEL_44;
  }
  if ( (unsigned int)InlineIsEqualGUID(v26, v27) )
  {
    *a5 = v24;
    CanCastTo = 0;
LABEL_42:
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*a5 + 8LL))(*a5);
    goto LABEL_44;
  }
  CanCastTo = Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<9>,1,IWeakReferenceSource>::CanCastTo(
                (char *)v24 + 8,
                v28,
                a5);
  if ( CanCastTo >= 0 )
    goto LABEL_42;
LABEL_44:
  if ( CanCastTo < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x148,
      (unsigned int)".\\session.cpp",
      (const char *)(unsigned int)CanCastTo,
      v32);
    if ( v24 )
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionChannel>::Release(v24);
    v29 = v33;
    if ( v33 )
    {
      v33 = 0;
      (*(void (__fastcall **)(_QWORD *, _QWORD))(*v29 + 16LL))(v29, *v29);
    }
    goto LABEL_22;
  }
  wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(
    v41,
    v22);
  if ( v24 )
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionChannel>::Release(v24);
  v30 = v33;
  if ( v33 )
  {
    v33 = 0;
    (*(void (__fastcall **)(_QWORD *))(*v30 + 16LL))(v30);
  }
  WindowsDeleteString(string);
  RemoteSessionTraceProvider::SessionAddChannel::~SessionAddChannel((RemoteSessionTraceProvider::SessionAddChannel *)v41);
  return 0;
}

```

## disassembly

```asm
0x180011de0  push    rbx
0x180011de2  push    rsi
0x180011de3  push    rdi
0x180011de4  push    r12
0x180011de6  push    r13
0x180011de8  push    r14
0x180011dea  push    r15
0x180011dec  sub     rsp, 1E0h
0x180011df3  mov     rax, cs:__security_cookie
0x180011dfa  xor     rax, rsp
0x180011dfd  mov     [rsp+218h+var_48], rax
0x180011e05  mov     r13, r9
0x180011e08  mov     r12b, r8b
0x180011e0b  mov     r15, rdx
0x180011e0e  mov     r14, rcx
0x180011e11  mov     [rsp+218h+var_1B8], rdx
0x180011e16  mov     byte ptr [rsp+218h+var_1E0], r8b
0x180011e1b  mov     rsi, [rsp+218h+arg_20]
0x180011e23  test    rdx, rdx
0x180011e26  jnz     short loc_180011E50
0x180011e28  mov     rcx, [rsp+218h]; this
0x180011e30  mov     ebx, 80070057h
0x180011e35  mov     r9d, ebx; char *
0x180011e38  lea     r8, aSessionCpp; ".\\session.cpp"
0x180011e3f  mov     edx, 12Bh; void *
0x180011e44  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e49  mov     eax, ebx
0x180011e4b  jmp     loc_18001234F
0x180011e50  test    r13, r13
0x180011e53  jnz     short loc_180011E7D
0x180011e55  mov     rcx, [rsp+218h]; this
0x180011e5d  mov     ebx, 80070057h
0x180011e62  mov     r9d, ebx; char *
0x180011e65  lea     r8, aSessionCpp; ".\\session.cpp"
0x180011e6c  mov     edx, 12Ch; void *
0x180011e71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011e76  mov     eax, ebx
0x180011e78  jmp     loc_18001234F
0x180011e7d  test    rsi, rsi
0x180011e80  jnz     short loc_180011EAA
0x180011e82  mov     rcx, [rsp+218h]; this
0x180011e8a  mov     ebx, 80004003h
0x180011e8f  mov     r9d, ebx; char *
0x180011e92  lea     r8, aSessionCpp; ".\\session.cpp"
0x180011e99  mov     edx, 12Dh; void *
0x180011e9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ea3  mov     eax, ebx
0x180011ea5  jmp     loc_18001234F
0x180011eaa  xor     edx, edx; length
0x180011eac  mov     rcx, r15; string
0x180011eaf  call    cs:__imp_WindowsGetStringRawBuffer
0x180011eb5  mov     rbx, rax
0x180011eb8  lea     rdx, aSessionaddchan; "SessionAddChannel"
0x180011ebf  lea     rcx, [rsp+218h+var_198]
0x180011ec7  call    ??0?$ActivityBase@VRemoteSessionTraceProvider@@$00$0EAAAAAAAAAAA@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<RemoteSessionTraceProvider,1,70368744177664,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180011ecc  lea     rax, ??_7SessionAddChannel@RemoteSessionTraceProvider@@6B@; const RemoteSessionTraceProvider::SessionAddChannel::`vftable'
0x180011ed3  mov     [rsp+218h+var_198], rax
0x180011edb  movups  xmm0, xmmword ptr [r14+38h]
0x180011ee0  movdqu  xmmword ptr [rsp+218h+var_1C8.Data1], xmm0
0x180011ee6  mov     r9b, r12b; unsigned __int8
0x180011ee9  mov     r8, rbx; unsigned __int16 *
0x180011eec  lea     rdx, [rsp+218h+var_1C8]; struct _GUID
0x180011ef1  lea     rcx, [rsp+218h+var_198]; this
0x180011ef9  call    ?StartActivity@SessionAddChannel@RemoteSessionTraceProvider@@QEAAXU_GUID@@PEBGE@Z; RemoteSessionTraceProvider::SessionAddChannel::StartActivity(_GUID,ushort const *,uchar)
0x180011efe  nop
0x180011eff  mov     r8, r15
0x180011f02  lea     rdx, [r14+38h]
0x180011f06  lea     rcx, [rsp+218h+string]
0x180011f0b  call    ?MakeChannelLocator@Internal@SharingPlatform@@YA?AVHString@Wrappers@WRL@Microsoft@@AEBU_GUID@@PEAUHSTRING__@@@Z; SharingPlatform::Internal::MakeChannelLocator(_GUID const &,HSTRING__ *)
0x180011f10  nop
0x180011f11  mov     [rsp+218h+var_1E8], 0
0x180011f1a  lea     rax, [rsp+218h+var_1E8]
0x180011f1f  mov     [rsp+218h+var_1D0], rax
0x180011f24  lea     rcx, [rsp+218h+var_1D0]
0x180011f29  call    ??B?$ComPtrRef@VWeakRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVWeakRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::WeakRef>::operator Microsoft::WRL::WeakRef *(void)
0x180011f2e  mov     rdx, rax
0x180011f31  mov     rcx, r13
0x180011f34  call    ??$AsWeak@UIDeviceSessionChannelCallback@SharingPlatform@@@WRL@Microsoft@@YAJPEAUIDeviceSessionChannelCallback@SharingPlatform@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<SharingPlatform::IDeviceSessionChannelCallback>(SharingPlatform::IDeviceSessionChannelCallback *,Microsoft::WRL::WeakRef *)
0x180011f39  mov     ebx, eax
0x180011f3b  xor     r13d, r13d
0x180011f3e  test    eax, eax
0x180011f40  jns     short loc_180011F9B
0x180011f42  mov     rcx, [rsp+218h]; this
0x180011f4a  mov     r9d, eax; char *
0x180011f4d  lea     r8, aSessionCpp; ".\\session.cpp"
0x180011f54  mov     edx, 134h; void *
0x180011f59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011f5e  nop
0x180011f5f  mov     rcx, [rsp+218h+var_1E8]
0x180011f64  test    rcx, rcx
0x180011f67  jz      short loc_180011F7B
0x180011f69  mov     [rsp+218h+var_1E8], r13
0x180011f6e  mov     rax, [rcx]
0x180011f71  mov     rax, [rax+10h]
0x180011f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f7a  nop
0x180011f7b  mov     rcx, [rsp+218h+string]; string
0x180011f80  call    cs:__imp_WindowsDeleteString
0x180011f86  nop
0x180011f87  lea     rcx, [rsp+218h+var_198]; this
0x180011f8f  call    ??1SessionAddChannel@RemoteSessionTraceProvider@@QEAA@XZ; RemoteSessionTraceProvider::SessionAddChannel::~SessionAddChannel(void)
0x180011f94  mov     eax, ebx
0x180011f96  jmp     loc_18001234F
0x180011f9b  lea     rbx, [r14+68h]
0x180011f9f  mov     rcx, rbx; lpCriticalSection
0x180011fa2  call    cs:__imp_EnterCriticalSection
0x180011fa8  mov     qword ptr [rsp+218h+var_1C8.Data1], rbx
0x180011fad  lea     r15, [r14+0B8h]
0x180011fb4  lea     r8, [rsp+218h+string]
0x180011fb9  lea     rdx, [rsp+218h+var_1D0]
0x180011fbe  mov     rcx, r15
0x180011fc1  call    ?find@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@VWeakRef@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@@std@@@2@AEBVHString@Wrappers@WRL@Microsoft@@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::find(Microsoft::WRL::Wrappers::HString const &)
0x180011fc6  mov     rax, [r15]
0x180011fc9  cmp     [rsp+218h+var_1D0], rax
0x180011fce  jz      short loc_18001203D
0x180011fd0  mov     rcx, [rsp+218h]; this
0x180011fd8  mov     edi, 800700B7h
0x180011fdd  mov     r9d, edi; char *
0x180011fe0  lea     r8, aSessionCpp; ".\\session.cpp"
0x180011fe7  mov     edx, 13Ah; void *
0x180011fec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011ff1  nop
0x180011ff2  test    rbx, rbx
0x180011ff5  jz      short loc_180012001
0x180011ff7  mov     rcx, rbx; lpCriticalSection
0x180011ffa  call    cs:__imp_LeaveCriticalSection
0x180012000  nop
0x180012001  mov     rcx, [rsp+218h+var_1E8]
0x180012006  test    rcx, rcx
0x180012009  jz      short loc_18001201D
0x18001200b  mov     [rsp+218h+var_1E8], r13
0x180012010  mov     rdx, [rcx]
0x180012013  mov     rax, [rdx+10h]
0x180012017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001201c  nop
0x18001201d  mov     rcx, [rsp+218h+string]; string
0x180012022  call    cs:__imp_WindowsDeleteString
0x180012028  nop
0x180012029  lea     rcx, [rsp+218h+var_198]; this
0x180012031  call    ??1SessionAddChannel@RemoteSessionTraceProvider@@QEAA@XZ; RemoteSessionTraceProvider::SessionAddChannel::~SessionAddChannel(void)
0x180012036  mov     eax, edi
0x180012038  jmp     loc_18001234F
0x18001203d  mov     rcx, [r14+0C8h]
0x180012044  mov     rax, [rcx]
0x180012047  test    r12b, r12b
0x18001204a  setnz   r8b
0x18001204e  mov     rdx, [rsp+218h+string]
0x180012053  mov     rax, [rax+50h]
0x180012057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001205c  mov     edi, eax
0x18001205e  test    eax, eax
0x180012060  jns     short loc_1800120CA
0x180012062  mov     rcx, [rsp+218h]; this
0x18001206a  mov     r9d, eax; char *
0x18001206d  lea     r8, aSessionCpp; ".\\session.cpp"
0x180012074  mov     edx, 13Ch; void *
0x180012079  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001207e  nop
0x18001207f  test    rbx, rbx
0x180012082  jz      short loc_18001208E
0x180012084  mov     rcx, rbx; lpCriticalSection
0x180012087  call    cs:__imp_LeaveCriticalSection
0x18001208d  nop
0x18001208e  mov     rcx, [rsp+218h+var_1E8]
0x180012093  test    rcx, rcx
0x180012096  jz      short loc_1800120AA
0x180012098  mov     [rsp+218h+var_1E8], r13
0x18001209d  mov     rax, [rcx]
0x1800120a0  mov     rax, [rax+10h]
0x1800120a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120a9  nop
0x1800120aa  mov     rcx, [rsp+218h+string]; string
0x1800120af  call    cs:__imp_WindowsDeleteString
0x1800120b5  nop
0x1800120b6  lea     rcx, [rsp+218h+var_198]; this
0x1800120be  call    ??1SessionAddChannel@RemoteSessionTraceProvider@@QEAA@XZ; RemoteSessionTraceProvider::SessionAddChannel::~SessionAddChannel(void)
0x1800120c3  mov     eax, edi
0x1800120c5  jmp     loc_18001234F
0x1800120ca  lea     r9, [rsp+218h+var_1E8]
0x1800120cf  lea     r8, [rsp+218h+string]
0x1800120d4  lea     rdx, [rsp+218h+var_1B0]
0x1800120d9  mov     rcx, r15
0x1800120dc  call    ??$_Emplace@VHString@Wrappers@WRL@Microsoft@@AEAVWeakRef@34@@?$_Tree@V?$_Tmap_traits@VHString@Wrappers@WRL@Microsoft@@VWeakRef@34@Uhstring_insensitive_less@wil@@V?$allocator@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVHString@Wrappers@WRL@Microsoft@@VWeakRef@34@@std@@PEAX@std@@_N@1@$$QEAVHString@Wrappers@WRL@Microsoft@@AEAVWeakRef@56@@Z; std::_Tree<std::_Tmap_traits<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef,wil::hstring_insensitive_less,std::allocator<std::pair<Microsoft::WRL::Wrappers::HString const,Microsoft::WRL::WeakRef>>,0>>::_Emplace<Microsoft::WRL::Wrappers::HString,Microsoft::WRL::WeakRef &>(Microsoft::WRL::Wrappers::HString &&,Microsoft::WRL::WeakRef &)
0x1800120e1  cmp     [rsp+218h+var_1A8], r13b
0x1800120e6  jnz     short loc_180012155
0x1800120e8  mov     rcx, [rsp+218h]; this
0x1800120f0  mov     edi, 800700B7h
0x1800120f5  mov     r9d, edi; char *
0x1800120f8  lea     r8, aSessionCpp; ".\\session.cpp"
0x1800120ff  mov     edx, 13Fh; void *
0x180012104  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180012109  nop
0x18001210a  test    rbx, rbx
0x18001210d  jz      short loc_180012119
0x18001210f  mov     rcx, rbx; lpCriticalSection
0x180012112  call    cs:__imp_LeaveCriticalSection
0x180012118  nop
0x180012119  mov     rcx, [rsp+218h+var_1E8]
0x18001211e  test    rcx, rcx
0x180012121  jz      short loc_180012135
0x180012123  mov     [rsp+218h+var_1E8], r13
0x180012128  mov     rax, [rcx]
0x18001212b  mov     rax, [rax+10h]
0x18001212f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012134  nop
0x180012135  mov     rcx, [rsp+218h+string]; string
0x18001213a  call    cs:__imp_WindowsDeleteString
0x180012140  nop
0x180012141  lea     rcx, [rsp+218h+var_198]; this
0x180012149  call    ??1SessionAddChannel@RemoteSessionTraceProvider@@QEAA@XZ; RemoteSessionTraceProvider::SessionAddChannel::~SessionAddChannel(void)
0x18001214e  mov     eax, edi
0x180012150  jmp     loc_18001234F
0x180012155  test    rbx, rbx
0x180012158  jz      short loc_180012163
0x18001215a  mov     rcx, rbx; lpCriticalSection
0x18001215d  call    cs:__imp_LeaveCriticalSection
0x180012163  mov     [rsp+218h+var_1D0], r13
0x180012168  mov     rax, [r14+0A0h]
0x18001216f  mov     [rsp+218h+var_1B0], rax
0x180012174  mov     qword ptr [rsp+218h+var_1C8.Data1], r14
0x180012179  lea     rax, [rsp+218h+var_1E0]
0x18001217e  mov     qword ptr [rsp+218h+var_1F8], rax; int
0x180012183  lea     r9, [rsp+218h+var_1B8]
0x180012188  lea     r8, [rsp+218h+var_1B0]
0x18001218d  lea     rdx, [rsp+218h+var_1C8]
0x180012192  lea     rcx, [rsp+218h+var_1D0]
0x180012197  call    ??$MakeAndInitialize@VDeviceSessionChannel@SharingPlatform@@V12@PEAVSession@2@PEAUHSTRING__@@AEAPEAU4@AEAE@Details@WRL@Microsoft@@YAJPEAPEAVDeviceSessionChannel@SharingPlatform@@$$QEAPEAVSession@4@$$QEAPEAUHSTRING__@@AEAPEAU6@AEAE@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::DeviceSessionChannel,SharingPlatform::DeviceSessionChannel,SharingPlatform::Session *,HSTRING__ *,HSTRING__ * &,uchar &>(SharingPlatform::DeviceSessionChannel * *,SharingPlatform::Session * &&,HSTRING__ * &&,HSTRING__ * &,uchar &)
0x18001219c  mov     r14d, eax
0x18001219f  test    eax, eax
0x1800121a1  jns     short loc_18001220D
0x1800121a3  mov     rcx, [rsp+218h]; this
0x1800121ab  mov     r9d, eax; char *
0x1800121ae  lea     r8, aSessionCpp; ".\\session.cpp"
0x1800121b5  mov     edx, 146h; void *
0x1800121ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800121bf  nop
0x1800121c0  mov     rcx, [rsp+218h+var_1D0]
0x1800121c5  test    rcx, rcx
0x1800121c8  jz      short loc_1800121D0
0x1800121ca  call    ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00$00$0A@UIDeviceSessionChannel@SharingPlatform@@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<9>,1,1,0,SharingPlatform::IDeviceSessionChannel>::Release(void)
0x1800121cf  nop
0x1800121d0  mov     rcx, [rsp+218h+var_1E8]
0x1800121d5  test    rcx, rcx
0x1800121d8  jz      short loc_1800121EC
0x1800121da  mov     [rsp+218h+var_1E8], r13
0x1800121df  mov     rax, [rcx]
0x1800121e2  mov     rax, [rax+10h]
0x1800121e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121eb  nop
0x1800121ec  mov     rcx, [rsp+218h+string]; string
0x1800121f1  call    cs:__imp_WindowsDeleteString
0x1800121f7  nop
0x1800121f8  lea     rcx, [rsp+218h+var_198]; this
0x180012200  call    ??1SessionAddChannel@RemoteSessionTraceProvider@@QEAA@XZ; RemoteSessionTraceProvider::SessionAddChannel::~SessionAddChannel(void)
0x180012205  mov     eax, r14d
0x180012208  jmp     loc_18001234F
0x18001220d  mov     rbx, [rsp+218h+var_1D0]
0x180012212  mov     [rsi], r13
0x180012215  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18001221c  lea     r9, _GUID_9fda45aa_73c9_404b_bc95_1108ea66e487
0x180012223  mov     rcx, r9
0x180012226  call    InlineIsEqualGUID
0x18001222b  test    eax, eax
0x18001222d  jnz     short loc_180012276
0x18001222f  lea     rdx, _GUID_af86e2e0_b12d_4c6a_9c5a_d7aa65101e90
0x180012236  call    InlineIsEqualGUID
0x18001223b  test    eax, eax
0x18001223d  jnz     short loc_180012276
0x18001223f  mov     rdx, r9
0x180012242  call    InlineIsEqualGUID
0x180012247  test    eax, eax
0x180012249  jz      short loc_180012253
0x18001224b  mov     [rsi], rbx
0x18001224e  mov     edi, r13d
0x180012251  jmp     short loc_180012265
0x180012253  lea     rcx, [rbx+8]
0x180012257  mov     r8, rsi
0x18001225a  call    ?CanCastTo@?$ImplementsHelper@U?$RuntimeClassFlags@$08@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@WRL@Microsoft@@IEAAJAEBU_GUID@@PEAPEAXPEA_N@Z; Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<9>,1,IWeakReferenceSource>::CanCastTo(_GUID const &,void * *,bool *)
0x18001225f  mov     edi, eax
0x180012261  test    eax, eax
0x180012263  js      short loc_18001228B
0x180012265  mov     rcx, [rsi]
0x180012268  mov     rax, [rcx]
0x18001226b  mov     rax, [rax+8]
0x18001226f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012274  jmp     short loc_18001228B
0x180012276  mov     [rsi], rbx
0x180012279  mov     rax, [rbx]
0x18001227c  mov     rcx, rbx
0x18001227f  mov     rax, [rax+8]
0x180012283  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012288  mov     edi, r13d
0x18001228b  test    edi, edi
0x18001228d  jns     short loc_1800122F3
0x18001228f  mov     rcx, [rsp+218h]; this
0x180012297  mov     r9d, edi; char *
0x18001229a  lea     r8, aSessionCpp; ".\\session.cpp"
0x1800122a1  mov     edx, 148h; void *
0x1800122a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800122ab  nop
  ... truncated ...
```
