# SharingPlatform::Internal::CDPListener::OnData(unsigned __int64,uchar const *,unsigned __int64,unsigned __int64,unsigned __int64,char const *)

- ea: `0x180020ff0`
- end: `0x1800218ac`
- name: `?OnData@CDPListener@Internal@SharingPlatform@@UEAAJ_KPEBE000PEBD@Z`
- size: `2236`
- prototype: `__int64 __fastcall(SharingPlatform::Internal::CDPListener *this, unsigned __int64, const unsigned __int8 *, unsigned int)`
- caller_count: `0`
- callee_count: `24`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x18000a580`
- `0x18000a988`
- `0x1800130ec`
- `0x180018490`
- `0x18001a394`
- `0x18001a5b4`
- `0x18001b404`
- `0x180020ff0`
- `0x180021990`
- `0x180026850`
- `0x18002da20`
- `0x180043388`
- `0x180044964`
- `0x18004fff0`
- `0x1800524bc`
- `0x180053320`
- `0x180055580`
- `0x180056290`
- `0x180056874`
- `0x180056ea8`
- `0x180061b0c`
- `0x180062014`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021458`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800215d1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180021458`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800215d1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800213fd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800213fd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x180021354`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002115a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800213a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002146d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002158d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002115a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800213a4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002146d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18002158d`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall SharingPlatform::Internal::CDPListener::OnData(
        SharingPlatform::Internal::CDPListener *this,
        unsigned __int64 a2,
        const unsigned __int8 *a3,
        unsigned int a4)
{
  int v8; // eax
  int v9; // eax
  unsigned __int64 v10; // rdx
  bool v11; // al
  unsigned int v12; // ebx
  __int64 v13; // rcx
  RemoteSessionTraceProvider *v14; // rax
  unsigned __int64 v15; // rdx
  unsigned __int8 v16; // cl
  __int64 v17; // rcx
  RemoteSessionTraceProvider *v18; // rax
  SharingPlatform::Internal *v19; // rsi
  int HString; // eax
  HSTRING *v21; // r8
  int v22; // ebx
  __int64 v23; // rdx
  int v24; // eax
  int v25; // eax
  int v26; // eax
  int v27; // eax
  int v28; // eax
  __int64 v29; // rbx
  PCWSTR StringRawBuffer; // rsi
  unsigned __int64 v31; // rdx
  unsigned __int8 v32; // cl
  __int64 v33; // rcx
  RemoteSessionTraceProvider *v34; // rax
  __int64 v35; // rcx
  RemoteSessionTraceProvider *v36; // rax
  unsigned __int8 v37; // cl
  int v38; // eax
  int v39; // eax
  int v40; // eax
  __int64 v41; // rcx
  RemoteSessionTraceProvider *v42; // rax
  __int64 v43; // rcx
  RemoteSessionTraceProvider *v44; // rax
  int v45; // eax
  int v46; // ebx
  int v47; // eax
  int v48; // eax
  int v49; // eax
  int v50; // eax
  int v51; // eax
  unsigned __int64 v52; // rdx
  __int64 v53; // rbx
  __int64 v54; // rcx
  RemoteSessionTraceProvider *v55; // rax
  const char *v56; // r9
  __int64 result; // rax
  int v58; // [rsp+20h] [rbp-A8h]
  unsigned __int8 v59[8]; // [rsp+50h] [rbp-78h] BYREF
  HSTRING v60; // [rsp+58h] [rbp-70h] BYREF
  unsigned __int8 v61[8]; // [rsp+60h] [rbp-68h] BYREF
  unsigned __int16 v62[4]; // [rsp+68h] [rbp-60h] BYREF
  HSTRING string; // [rsp+70h] [rbp-58h] BYREF
  __int64 v64; // [rsp+78h] [rbp-50h] BYREF
  __int64 v65; // [rsp+80h] [rbp-48h] BYREF
  SharingPlatform::Internal *v66; // [rsp+88h] [rbp-40h] BYREF
  struct SharingPlatform::ISessionIdentifier *v67; // [rsp+90h] [rbp-38h] BYREF
  __int64 v68; // [rsp+98h] [rbp-30h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-28h]
  unsigned __int64 v70; // [rsp+A8h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]
  unsigned __int64 v72; // [rsp+D8h] [rbp+10h] BYREF

  v72 = a2;
  v66 = 0;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v66);
  try
  {
    v8 = SharingPlatform::Internal::SpecificMessageParser::CreateFromBorrowedCBuffer(a3, a4, &v66);
    if ( v8 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x3E,
        (unsigned int)".\\cdplistener.cpp",
        (const char *)(unsigned int)v8,
        v58);
    v9 = SharingPlatform::Internal::SpecificMessageParser::ParseSessionMessageHeader(v66, v62, v61, v59);
    if ( v9 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x45,
        (unsigned int)".\\cdplistener.cpp",
        (const char *)(unsigned int)v9,
        v58);
    v11 = 1;
    if ( v62[0] == 2 )
      v11 = v61[0] != 1;
    if ( v11 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x49,
        (unsigned int)".\\cdplistener.cpp",
        (const char *)0x80070032LL,
        v58);
    v12 = v59[0];
    if ( !v59[0] )
    {
      if ( RemoteSessionTraceProvider::IsEnabled((unsigned __int8)retaddr, v10) )
      {
        v44 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                              v43,
                                              _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
        RemoteSessionTraceProvider::LogInfo_(v44, L"CDPListener::OnData Discovery request received from %llx", a2);
      }
      v45 = (*(__int64 (__fastcall **)(SharingPlatform::Internal *, unsigned __int8 *))(*(_QWORD *)v66 + 128LL))(
              v66,
              v59);
      v46 = v45;
      if ( v45 >= 0 )
        v46 = 0;
      else
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x5B,
          (unsigned int)".\\specificmessageparser.cpp",
          (const char *)(unsigned int)v45,
          v58);
      if ( v46 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x79,
          (unsigned int)".\\cdplistener.cpp",
          (const char *)(unsigned int)v46,
          v58);
      std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(&v68);
      SharingPlatform::Internal::SessionsList::GetCopy(&v68, 0);
      v60 = 0;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v60);
      v47 = SharingPlatform::Internal::MessageBuilder::WriteSessionDiscoveryResponse(&v68, &v60);
      if ( v47 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x81,
          (unsigned int)".\\cdplistener.cpp",
          (const char *)(unsigned int)v47,
          v58);
      v67 = 0;
      v48 = (*(__int64 (__fastcall **)(HSTRING, unsigned __int16 *))(*(_QWORD *)v60 + 56LL))(v60, v62);
      if ( v48 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x86,
          (unsigned int)".\\cdplistener.cpp",
          (const char *)(unsigned int)v48,
          v58);
      v64 = 0;
      v49 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
              &v60,
              &v64);
      if ( v49 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x88,
          (unsigned int)".\\cdplistener.cpp",
          (const char *)(unsigned int)v49,
          v58);
      v50 = (*(__int64 (__fastcall **)(__int64, struct SharingPlatform::ISessionIdentifier **))(*(_QWORD *)v64 + 24LL))(
              v64,
              &v67);
      if ( v50 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x89,
          (unsigned int)".\\cdplistener.cpp",
          (const char *)(unsigned int)v50,
          v58);
      v51 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, struct SharingPlatform::ISessionIdentifier *, _QWORD))(**((_QWORD **)this + 12) + 40LL))(
              *((_QWORD *)this + 12),
              a2,
              v67,
              *(unsigned int *)v62);
      if ( v51 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x8C,
          (unsigned int)".\\cdplistener.cpp",
          (const char *)(unsigned int)v51,
          0);
      v53 = v69 - v68;
      if ( RemoteSessionTraceProvider::IsEnabled((unsigned __int8)retaddr, v52) )
      {
        v55 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                              v54,
                                              _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
        RemoteSessionTraceProvider::LogInfo_(
          v55,
          L"CDPListener::OnData Discovery response sent to %llx session_count=%Iu",
          a2,
          v53 >> 3);
      }
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v64);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v60);
      goto LABEL_80;
    }
    if ( v59[0] == 2 )
    {
      if ( RemoteSessionTraceProvider::IsEnabled((unsigned __int8)retaddr, v10) )
      {
        v36 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                              v35,
                                              _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
        RemoteSessionTraceProvider::LogInfo_(v36, L"CDPListener::OnData Invitation received from %llx", a2);
      }
      SharingPlatform::InvitationManagerStatics::GetDefaultInternal(&v64);
      *(_QWORD *)v62 = 0;
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
      std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<ICDPDevice>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<ICDPDevice>>>,0>>::_Find_lower_bound<unsigned __int64>(
        (char *)this + 104,
        &v68,
        &v72);
      if ( *(_BYTE *)(v70 + 25) || a2 < *(_QWORD *)(v70 + 32) || v70 == *((_QWORD *)this + 13) )
      {
        if ( RemoteSessionTraceProvider::IsEnabled(v37, v70) )
        {
          v42 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                                v41,
                                                _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
          RemoteSessionTraceProvider::LogWarning_(
            v42,
            L"CDPListener::OnData sender disconnected while we were processing this message, ignore the message");
        }
        if ( this != (SharingPlatform::Internal::CDPListener *)-48LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v62);
      }
      else
      {
        Microsoft::WRL::ComPtr<ICDPDevice>::operator=(v62, v70 + 40);
        if ( this != (SharingPlatform::Internal::CDPListener *)-48LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
        v60 = 0;
        v67 = 0;
        WindowsDeleteString(0);
        v60 = 0;
        v38 = SharingPlatform::Internal::SpecificMessageParser::ParseInvitation(v66, &v67, &v60);
        if ( v38 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xAB,
            (unsigned int)".\\cdplistener.cpp",
            (const char *)(unsigned int)v38,
            v58);
        string = 0;
        v65 = *(_QWORD *)v62;
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&string);
        v39 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::DeviceIdentifier,SharingPlatform::IDeviceIdentifier,ICDPDevice *>(
                &string,
                &v65);
        if ( v39 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xB2,
            (unsigned int)".\\cdplistener.cpp",
            (const char *)(unsigned int)v39,
            v58);
        v65 = 0;
        v40 = Microsoft::WRL::ComPtr<SharingPlatform::IInvitationManager>::As<SharingPlatform::Internal::IInvitationManagerInternal>(
                &v64,
                &v65);
        if ( v40 < 0 )
          wil::details::in1diag3::_Throw_Hr(
            retaddr,
            (void *)0xB7,
            (unsigned int)".\\cdplistener.cpp",
            (const char *)(unsigned int)v40,
            v58);
        (*(void (__fastcall **)(__int64, HSTRING, struct SharingPlatform::ISessionIdentifier *, HSTRING))(*(_QWORD *)v65 + 56LL))(
          v65,
          string,
          v67,
          v60);
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v65);
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&string);
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v67);
        WindowsDeleteString(v60);
        v60 = 0;
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v62);
      }
      if ( v64 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
      goto LABEL_82;
    }
    if ( v59[0] != 10 )
    {
      if ( RemoteSessionTraceProvider::IsEnabled((unsigned __int8)retaddr, v10) )
      {
        v14 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                              v13,
                                              _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
        RemoteSessionTraceProvider::LogWarning_(v14, L"CDPListener::OnData invalid messageType=%hhu", v12);
      }
LABEL_82:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v66);
      return 0;
    }
    std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(&v68);
    v60 = 0;
    string = 0;
    if ( RemoteSessionTraceProvider::IsEnabled(v16, v15) )
    {
      v18 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                            v17,
                                            _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
      RemoteSessionTraceProvider::LogInfo_(v18, L"CDPListener::OnData DiscoveryByApp request received from %llx", a2);
    }
    WindowsDeleteString(string);
    string = 0;
    v19 = v66;
    HString = (*(__int64 (__fastcall **)(SharingPlatform::Internal *, unsigned __int8 *))(*(_QWORD *)v66 + 128LL))(
                v66,
                v59);
    v22 = HString;
    if ( HString >= 0 )
    {
      HString = SharingPlatform::Internal::ReadHString(
                  v19,
                  (struct Windows::Storage::Streams::IDataReader *)&string,
                  v21);
      v22 = HString;
      if ( HString >= 0 )
      {
        v22 = 0;
        goto LABEL_23;
      }
      v23 = 77;
    }
    else
    {
      v23 = 74;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v23,
      (unsigned int)".\\specificmessageparser.cpp",
      (const char *)(unsigned int)HString,
      v58);
LABEL_23:
    if ( v22 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x59,
        (unsigned int)".\\cdplistener.cpp",
        (const char *)(unsigned int)v22,
        v58);
    SharingPlatform::Internal::SessionsList::GetCopy(&v68, string);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v60);
    v24 = SharingPlatform::Internal::MessageBuilder::WriteSessionDiscoveryResponse(&v68, &v60);
    if ( v24 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x5F,
        (unsigned int)".\\cdplistener.cpp",
        (const char *)(unsigned int)v24,
        v58);
    v64 = 0;
    v25 = (*(__int64 (__fastcall **)(HSTRING, unsigned __int16 *))(*(_QWORD *)v60 + 56LL))(v60, v62);
    if ( v25 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x64,
        (unsigned int)".\\cdplistener.cpp",
        (const char *)(unsigned int)v25,
        v58);
    v65 = 0;
    v26 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
            &v60,
            &v65);
    if ( v26 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x66,
        (unsigned int)".\\cdplistener.cpp",
        (const char *)(unsigned int)v26,
        v58);
    v27 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v65 + 24LL))(v65, &v64);
    if ( v27 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)".\\cdplistener.cpp",
        (const char *)(unsigned int)v27,
        v58);
    v28 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int64, __int64, _QWORD))(**((_QWORD **)this + 12) + 40LL))(
            *((_QWORD *)this + 12),
            a2,
            v64,
            *(unsigned int *)v62);
    if ( v28 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x6A,
        (unsigned int)".\\cdplistener.cpp",
        (const char *)(unsigned int)v28,
        0);
    v29 = v69 - v68;
    StringRawBuffer = WindowsGetStringRawBuffer(string, 0);
    if ( RemoteSessionTraceProvider::IsEnabled(v32, v31) )
    {
      v34 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                            v33,
                                            _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
      RemoteSessionTraceProvider::LogInfo_(
        v34,
        L"CDPListener::OnData DiscoveryByApp response sent to %llx for app %ls session_count=%Iu",
        a2,
        StringRawBuffer,
        v29 >> 3);
    }
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v65);
    WindowsDeleteString(string);
    string = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v60);
LABEL_80:
    if ( v68 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SharingPlatform::ISession>>>(v68, v69);
      std::_Deallocate<16>(v68, (v70 - v68) & 0xFFFFFFFFFFFFFFF8uLL);
    }
    goto LABEL_82;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xC5,
                           (unsigned int)".\\cdplistener.cpp",
                           v56);
  }
  return result;
}

```

## disassembly

```asm
0x180020ff0  mov     rax, rsp
0x180020ff3  mov     [rax+8], rbx
0x180020ff7  mov     [rax+18h], rsi
0x180020ffb  mov     [rax+10h], rdx
0x180020fff  push    rdi
0x180021000  push    r14
0x180021002  push    r15
0x180021004  sub     rsp, 0B0h
0x18002100b  mov     rbx, r9
0x18002100e  mov     rsi, r8
0x180021011  mov     rdi, rdx
0x180021014  mov     r14, rcx
0x180021017  xor     r15d, r15d
0x18002101a  mov     [rax-40h], r15
0x18002101e  lea     rcx, [rax-40h]
0x180021022  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180021027  lea     r8, [rsp+0C8h+var_40]; struct Windows::Storage::Streams::IDataReader **
0x18002102f  mov     rdx, rbx; unsigned int
0x180021032  mov     rcx, rsi; unsigned __int8 *
0x180021035  call    ?CreateFromBorrowedCBuffer@SpecificMessageParser@Internal@SharingPlatform@@SAJPEBE_KPEAPEAUIDataReader@Streams@Storage@Windows@@@Z; SharingPlatform::Internal::SpecificMessageParser::CreateFromBorrowedCBuffer(uchar const *,unsigned __int64,Windows::Storage::Streams::IDataReader * *)
0x18002103a  mov     rcx, [rsp+0C8h]; this
0x180021042  test    eax, eax
0x180021044  jns     short loc_180021059
0x180021046  mov     r9d, eax; char *
0x180021049  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x180021050  lea     edx, [r15+3Eh]; void *
0x180021054  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021059  lea     r9, [rsp+0C8h+var_78]; unsigned __int8 *
0x18002105e  lea     r8, [rsp+0C8h+var_68]; unsigned __int8 *
0x180021063  lea     rdx, [rsp+0C8h+var_60]; unsigned __int16 *
0x180021068  mov     rcx, [rsp+0C8h+var_40]; struct Windows::Storage::Streams::IDataReader *
0x180021070  call    ?ParseSessionMessageHeader@SpecificMessageParser@Internal@SharingPlatform@@SAJPEAUIDataReader@Streams@Storage@Windows@@PEAGPEAE2@Z; SharingPlatform::Internal::SpecificMessageParser::ParseSessionMessageHeader(Windows::Storage::Streams::IDataReader *,ushort *,uchar *,uchar *)
0x180021075  mov     rcx, [rsp+0C8h]; this
0x18002107d  test    eax, eax
0x18002107f  jns     short loc_180021095
0x180021081  mov     r9d, eax; char *
0x180021084  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x18002108b  mov     edx, 45h ; 'E'; void *
0x180021090  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021095  mov     al, 1
0x180021097  cmp     [rsp+0C8h+var_60], 2
0x18002109d  jnz     short loc_1800210A8
0x18002109f  cmp     [rsp+0C8h+var_68], al
0x1800210a3  jnz     short loc_1800210A8
0x1800210a5  mov     al, r15b
0x1800210a8  mov     rcx, [rsp+0C8h]; unsigned __int8
0x1800210b0  test    al, al
0x1800210b2  jz      short loc_1800210CB
0x1800210b4  mov     r9d, 80070032h; char *
0x1800210ba  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x1800210c1  mov     edx, 49h ; 'I'; void *
0x1800210c6  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800210cb  movzx   ebx, [rsp+0C8h+var_78]
0x1800210d0  test    bl, bl
0x1800210d2  jz      loc_1800215FF
0x1800210d8  cmp     bl, 2
0x1800210db  jz      loc_1800213BF
0x1800210e1  cmp     bl, 0Ah
0x1800210e4  jz      short loc_180021116
0x1800210e6  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x1800210eb  test    al, al
0x1800210ed  jz      loc_18002187D
0x1800210f3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x1800210fa  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x1800210ff  mov     r8d, ebx
0x180021102  lea     rdx, aCdplistenerOnd_0; "CDPListener::OnData invalid messageType"...
0x180021109  mov     rcx, rax; this
0x18002110c  call    ?LogWarning_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogWarning_(ushort const *,...)
0x180021111  jmp     loc_18002187D
0x180021116  lea     rcx, [rsp+0C8h+var_30]
0x18002111e  call    ??0?$vector@UStackFrame@Exception@ConnectedDevices@@V?$allocator@UStackFrame@Exception@ConnectedDevices@@@std@@@std@@QEAA@XZ; std::vector<ConnectedDevices::Exception::StackFrame>::vector<ConnectedDevices::Exception::StackFrame>(void)
0x180021123  nop
0x180021124  mov     [rsp+0C8h+var_70], r15
0x180021129  mov     [rsp+0C8h+string], r15
0x18002112e  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x180021133  test    al, al
0x180021135  jz      short loc_180021155
0x180021137  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x18002113e  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x180021143  mov     r8, rdi
0x180021146  lea     rdx, aCdplistenerOnd_4; "CDPListener::OnData DiscoveryByApp requ"...
0x18002114d  mov     rcx, rax; this
0x180021150  call    ?LogInfo_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogInfo_(ushort const *,...)
0x180021155  mov     rcx, [rsp+0C8h+string]; string
0x18002115a  call    cs:__imp_WindowsDeleteString
0x180021160  mov     [rsp+0C8h+string], r15
0x180021165  mov     rsi, [rsp+0C8h+var_40]
0x18002116d  mov     rax, [rsi]
0x180021170  lea     rdx, [rsp+0C8h+var_78]
0x180021175  mov     rcx, rsi
0x180021178  mov     rax, [rax+80h]
0x18002117f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021184  mov     ebx, eax
0x180021186  test    eax, eax
0x180021188  jns     short loc_1800211A8
0x18002118a  mov     edx, 4Ah ; 'J'; void *
0x18002118f  lea     r8, aSpecificmessag; ".\\specificmessageparser.cpp"
0x180021196  mov     r9d, eax; char *
0x180021199  mov     rcx, [rsp+0C8h]; this
0x1800211a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800211a6  jmp     short loc_1800211C5
0x1800211a8  lea     rdx, [rsp+0C8h+string]; struct Windows::Storage::Streams::IDataReader *
0x1800211ad  mov     rcx, rsi; this
0x1800211b0  call    ?ReadHString@Internal@SharingPlatform@@YAJPEAUIDataReader@Streams@Storage@Windows@@PEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::ReadHString(Windows::Storage::Streams::IDataReader *,HSTRING__ * *)
0x1800211b5  mov     ebx, eax
0x1800211b7  test    eax, eax
0x1800211b9  jns     short loc_1800211C2
0x1800211bb  mov     edx, 4Dh ; 'M'
0x1800211c0  jmp     short loc_18002118F
0x1800211c2  mov     ebx, r15d
0x1800211c5  mov     rcx, [rsp+0C8h]; this
0x1800211cd  test    ebx, ebx
0x1800211cf  jns     short loc_1800211E5
0x1800211d1  mov     r9d, ebx; char *
0x1800211d4  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x1800211db  mov     edx, 59h ; 'Y'; void *
0x1800211e0  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800211e5  mov     rdx, [rsp+0C8h+string]
0x1800211ea  lea     rcx, [rsp+0C8h+var_30]
0x1800211f2  call    ?GetCopy@SessionsList@Internal@SharingPlatform@@SAJAEAV?$vector@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@@std@@@std@@PEAUHSTRING__@@@Z; SharingPlatform::Internal::SessionsList::GetCopy(std::vector<Microsoft::WRL::ComPtr<SharingPlatform::ISession>> &,HSTRING__ *)
0x1800211f7  lea     rcx, [rsp+0C8h+var_70]
0x1800211fc  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180021201  lea     rdx, [rsp+0C8h+var_70]
0x180021206  lea     rcx, [rsp+0C8h+var_30]
0x18002120e  call    ?WriteSessionDiscoveryResponse@MessageBuilder@Internal@SharingPlatform@@SAJAEBV?$vector@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@V?$allocator@V?$ComPtr@UISession@SharingPlatform@@@WRL@Microsoft@@@std@@@std@@PEAPEAUIBuffer@Streams@Storage@Windows@@@Z; SharingPlatform::Internal::MessageBuilder::WriteSessionDiscoveryResponse(std::vector<Microsoft::WRL::ComPtr<SharingPlatform::ISession>> const &,Windows::Storage::Streams::IBuffer * *)
0x180021213  mov     rcx, [rsp+0C8h]; this
0x18002121b  test    eax, eax
0x18002121d  jns     short loc_180021233
0x18002121f  mov     r9d, eax; char *
0x180021222  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x180021229  mov     edx, 5Fh ; '_'; void *
0x18002122e  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021233  mov     [rsp+0C8h+var_50], r15
0x180021238  mov     rcx, [rsp+0C8h+var_70]
0x18002123d  mov     rax, [rcx]
0x180021240  lea     rdx, [rsp+0C8h+var_60]
0x180021245  mov     rax, [rax+38h]
0x180021249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002124e  mov     rcx, [rsp+0C8h]; this
0x180021256  test    eax, eax
0x180021258  jns     short loc_18002126E
0x18002125a  mov     r9d, eax; char *
0x18002125d  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x180021264  mov     edx, 64h ; 'd'; void *
0x180021269  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002126e  mov     [rsp+0C8h+var_48], r15
0x180021276  lea     rdx, [rsp+0C8h+var_48]
0x18002127e  lea     rcx, [rsp+0C8h+var_70]
0x180021283  call    ??$As@UIBufferByteAccess@Streams@Storage@Windows@@@?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBufferByteAccess@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBufferByteAccess>>)
0x180021288  mov     rcx, [rsp+0C8h]; this
0x180021290  test    eax, eax
0x180021292  jns     short loc_1800212A8
0x180021294  mov     r9d, eax; char *
0x180021297  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x18002129e  mov     edx, 66h ; 'f'; void *
0x1800212a3  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800212a8  mov     rcx, [rsp+0C8h+var_48]
0x1800212b0  mov     rax, [rcx]
0x1800212b3  lea     rdx, [rsp+0C8h+var_50]
0x1800212b8  mov     rax, [rax+18h]
0x1800212bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212c1  mov     rcx, [rsp+0C8h]; this
0x1800212c9  test    eax, eax
0x1800212cb  jns     short loc_1800212E1
0x1800212cd  mov     r9d, eax; char *
0x1800212d0  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x1800212d7  mov     edx, 67h ; 'g'; void *
0x1800212dc  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800212e1  mov     rcx, [r14+60h]
0x1800212e5  mov     rax, [rcx]
0x1800212e8  mov     r9d, dword ptr [rsp+0C8h+var_60]
0x1800212ed  mov     [rsp+0C8h+var_90], 0EA60h
0x1800212f5  mov     [rsp+0C8h+var_98], r15
0x1800212fa  mov     rdx, [rsp+0C8h+arg_28]
0x180021302  mov     [rsp+0C8h+var_A0], rdx
0x180021307  mov     qword ptr [rsp+0C8h+var_A8], r15; int
0x18002130c  mov     r8, [rsp+0C8h+var_50]
0x180021311  mov     rdx, rdi
0x180021314  mov     rax, [rax+28h]
0x180021318  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002131d  mov     rcx, [rsp+0C8h]; this
0x180021325  test    eax, eax
0x180021327  jns     short loc_18002133D
0x180021329  mov     r9d, eax; char *
0x18002132c  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x180021333  mov     edx, 6Ah ; 'j'; void *
0x180021338  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002133d  mov     rbx, [rsp+0C8h+var_28]
0x180021345  sub     rbx, [rsp+0C8h+var_30]
0x18002134d  xor     edx, edx; length
0x18002134f  mov     rcx, [rsp+0C8h+string]; string
0x180021354  call    cs:__imp_WindowsGetStringRawBuffer
0x18002135a  mov     rsi, rax
0x18002135d  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x180021362  test    al, al
0x180021364  jz      short loc_180021391
0x180021366  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x18002136d  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x180021372  sar     rbx, 3
0x180021376  mov     qword ptr [rsp+0C8h+var_A8], rbx
0x18002137b  mov     r9, rsi
0x18002137e  mov     r8, rdi
0x180021381  lea     rdx, aCdplistenerOnd; "CDPListener::OnData DiscoveryByApp resp"...
0x180021388  mov     rcx, rax; this
0x18002138b  call    ?LogInfo_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogInfo_(ushort const *,...)
0x180021390  nop
0x180021391  lea     rcx, [rsp+0C8h+var_48]
0x180021399  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18002139e  nop
0x18002139f  mov     rcx, [rsp+0C8h+string]; string
0x1800213a4  call    cs:__imp_WindowsDeleteString
0x1800213aa  mov     [rsp+0C8h+string], r15
0x1800213af  lea     rcx, [rsp+0C8h+var_70]
0x1800213b4  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800213b9  nop
0x1800213ba  jmp     loc_180021846
0x1800213bf  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x1800213c4  test    al, al
0x1800213c6  jz      short loc_1800213E6
0x1800213c8  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x1800213cf  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x1800213d4  mov     r8, rdi
0x1800213d7  lea     rdx, aCdplistenerOnd_3; "CDPListener::OnData Invitation received"...
0x1800213de  mov     rcx, rax; this
0x1800213e1  call    ?LogInfo_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogInfo_(ushort const *,...)
0x1800213e6  lea     rcx, [rsp+0C8h+var_50]
0x1800213eb  call    ?GetDefaultInternal@InvitationManagerStatics@SharingPlatform@@SA?AV?$ComPtr@UIInvitationManager@SharingPlatform@@@WRL@Microsoft@@XZ; SharingPlatform::InvitationManagerStatics::GetDefaultInternal(void)
0x1800213f0  nop
0x1800213f1  mov     qword ptr [rsp+0C8h+var_60], r15
0x1800213f6  lea     rbx, [r14+30h]
0x1800213fa  mov     rcx, rbx; lpCriticalSection
0x1800213fd  call    cs:__imp_EnterCriticalSection
0x180021403  lea     r8, [rsp+0C8h+arg_8]
0x18002140b  lea     rdx, [rsp+0C8h+var_30]
0x180021413  lea     rcx, [r14+68h]
0x180021417  call    ??$_Find_lower_bound@_K@?$_Tree@V?$_Tmap_traits@_KV?$ComPtr@VICDPDevice@@@WRL@Microsoft@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KV?$ComPtr@VICDPDevice@@@WRL@Microsoft@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CB_KV?$ComPtr@VICDPDevice@@@WRL@Microsoft@@@std@@PEAX@std@@@1@AEB_K@Z; std::_Tree<std::_Tmap_traits<unsigned __int64,Microsoft::WRL::ComPtr<ICDPDevice>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,Microsoft::WRL::ComPtr<ICDPDevice>>>,0>>::_Find_lower_bound<unsigned __int64>(unsigned __int64 const &)
0x18002141c  mov     rdx, [rsp+0C8h+var_20]; unsigned __int64
0x180021424  cmp     [rdx+19h], r15b
0x180021428  jnz     loc_1800215A5
0x18002142e  cmp     rdi, [rdx+20h]
0x180021432  jb      loc_1800215A5
0x180021438  cmp     rdx, [r14+68h]
0x18002143c  jz      loc_1800215A5
0x180021442  add     rdx, 28h ; '('
0x180021446  lea     rcx, [rsp+0C8h+var_60]
0x18002144b  call    ??4?$ComPtr@VICDPDevice@@@WRL@Microsoft@@QEAAAEAV012@AEBV012@@Z; Microsoft::WRL::ComPtr<ICDPDevice>::operator=(Microsoft::WRL::ComPtr<ICDPDevice> const &)
0x180021450  test    rbx, rbx
0x180021453  jz      short loc_18002145E
0x180021455  mov     rcx, rbx; lpCriticalSection
0x180021458  call    cs:__imp_LeaveCriticalSection
0x18002145e  mov     [rsp+0C8h+var_70], r15
0x180021463  mov     [rsp+0C8h+var_38], r15
0x18002146b  xor     ecx, ecx; string
0x18002146d  call    cs:__imp_WindowsDeleteString
0x180021473  mov     [rsp+0C8h+var_70], r15
0x180021478  lea     r8, [rsp+0C8h+var_70]; HSTRING *
0x18002147d  lea     rdx, [rsp+0C8h+var_38]; struct SharingPlatform::ISessionIdentifier **
0x180021485  mov     rcx, [rsp+0C8h+var_40]; this
0x18002148d  call    ?ParseInvitation@SpecificMessageParser@Internal@SharingPlatform@@SAJPEAUIDataReader@Streams@Storage@Windows@@PEAPEAUISessionIdentifier@3@PEAPEAUHSTRING__@@@Z; SharingPlatform::Internal::SpecificMessageParser::ParseInvitation(Windows::Storage::Streams::IDataReader *,SharingPlatform::ISessionIdentifier * *,HSTRING__ * *)
0x180021492  mov     rcx, [rsp+0C8h]; this
0x18002149a  test    eax, eax
0x18002149c  jns     short loc_1800214B2
0x18002149e  mov     r9d, eax; char *
0x1800214a1  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x1800214a8  mov     edx, 0ABh; void *
0x1800214ad  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x1800214b2  mov     [rsp+0C8h+string], r15
0x1800214b7  mov     rax, qword ptr [rsp+0C8h+var_60]
0x1800214bc  mov     [rsp+0C8h+var_48], rax
0x1800214c4  lea     rcx, [rsp+0C8h+string]
0x1800214c9  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800214ce  lea     rdx, [rsp+0C8h+var_48]
0x1800214d6  lea     rcx, [rsp+0C8h+string]
0x1800214db  call    ??$MakeAndInitialize@VDeviceIdentifier@SharingPlatform@@UIDeviceIdentifier@2@PEAVICDPDevice@@@Details@WRL@Microsoft@@YAJPEAPEAUIDeviceIdentifier@SharingPlatform@@$$QEAPEAVICDPDevice@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::DeviceIdentifier,SharingPlatform::IDeviceIdentifier,ICDPDevice *>(SharingPlatform::IDeviceIdentifier * *,ICDPDevice * &&)
0x1800214e0  mov     rcx, [rsp+0C8h]; this
0x1800214e8  test    eax, eax
0x1800214ea  jns     short loc_180021500
0x1800214ec  mov     r9d, eax; char *
0x1800214ef  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x1800214f6  mov     edx, 0B2h; void *
0x1800214fb  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180021500  mov     [rsp+0C8h+var_48], r15
0x180021508  lea     rdx, [rsp+0C8h+var_48]
0x180021510  lea     rcx, [rsp+0C8h+var_50]
0x180021515  call    ??$As@UIInvitationManagerInternal@Internal@SharingPlatform@@@?$ComPtr@UIInvitationManager@SharingPlatform@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIInvitationManagerInternal@Internal@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<SharingPlatform::IInvitationManager>::As<SharingPlatform::Internal::IInvitationManagerInternal>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::Internal::IInvitationManagerInternal>>)
0x18002151a  mov     rcx, [rsp+0C8h]; this
0x180021522  test    eax, eax
0x180021524  jns     short loc_18002153A
0x180021526  mov     r9d, eax; char *
0x180021529  lea     r8, aCdplistenerCpp; ".\\cdplistener.cpp"
0x180021530  mov     edx, 0B7h; void *
0x180021535  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18002153a  mov     rcx, [rsp+0C8h+var_48]
0x180021542  mov     rax, [rcx]
0x180021545  mov     r9, [rsp+0C8h+var_70]
0x18002154a  mov     r8, [rsp+0C8h+var_38]
0x180021552  mov     rdx, [rsp+0C8h+string]
0x180021557  mov     rax, [rax+38h]
0x18002155b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021560  nop
  ... truncated ...
```
