# SharingPlatform::SessionClient::OnData(CDPTarget const &,uchar const *,unsigned __int64,unsigned __int64,unsigned __int64,char const *)

- ea: `0x180059340`
- end: `0x180059a1a`
- name: `?OnData@SessionClient@SharingPlatform@@UEAAJAEBUCDPTarget@@PEBE_K22PEBD@Z`
- size: `1754`
- prototype: `__int64 __fastcall(SharingPlatform::SessionClient *this, struct SharingPlatform::IParticipantIdentifier **, const unsigned __int8 *, __int64)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x180004928`
- `0x18000a580`
- `0x18000a988`
- `0x1800130ec`
- `0x18001620c`
- `0x180018490`
- `0x18001a5b4`
- `0x1800225a0`
- `0x18004513c`
- `0x180056874`
- `0x1800575e8`
- `0x1800582b0`
- `0x18005885c`
- `0x180059340`
- `0x180061c48`
- `0x180062014`
- `0x1800620c0`
- `0x180062230`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005953b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800595bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059844`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059935`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18005953b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800595bd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059844`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180059935`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800594fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005957c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059803`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005991d`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800594fa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005957c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180059803`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18005991d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800595f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800596bb`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800595f9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180059668`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800596bb`

## string_xrefs

- `0x1800596e8`: `SessionClient OnData Message received: PARTICIPANT_REMOVED`
- `0x1800597ed`: `SessionClient OnData Message received: REMOVED`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SharingPlatform::SessionClient::OnData(
        SharingPlatform::SessionClient *this,
        struct SharingPlatform::IParticipantIdentifier **a2,
        const unsigned __int8 *a3,
        __int64 a4)
{
  unsigned int v6; // edi
  unsigned int v7; // r14d
  int v8; // eax
  unsigned int v9; // ebx
  int OverCallerManagedBuffer; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, _QWORD, struct Windows::Storage::Streams::IDataReader **); // rbx
  int v13; // eax
  unsigned __int64 v14; // r9
  __int64 v15; // rdx
  int v16; // eax
  __int64 v17; // rcx
  struct SharingPlatform::IParticipantIdentifier *v18; // rax
  int v19; // ebx
  unsigned __int64 v20; // rdx
  __int64 v21; // rcx
  void (*GetRuntimeClassName)(void); // rax
  __int64 v23; // rcx
  RemoteSessionTraceProvider *v24; // rax
  __int64 v25; // rcx
  int v26; // eax
  __int64 v27; // rcx
  RemoteSessionTraceProvider *v28; // rax
  int v29; // eax
  __int64 v30; // rcx
  RemoteSessionTraceProvider *v31; // rax
  int v32; // eax
  struct SharingPlatform::IParticipantIdentifier **v33; // rcx
  struct SharingPlatform::IParticipantIdentifier **v34; // rcx
  __int64 v35; // rcx
  RemoteSessionTraceProvider *v36; // rax
  __int64 v37; // rcx
  int started; // eax
  unsigned __int64 v39; // rdx
  unsigned __int8 v40; // cl
  __int64 v41; // rdx
  __int64 v42; // rbx
  __int64 v43; // rcx
  RemoteSessionTraceProvider *v44; // rax
  struct Windows::Storage::Streams::IBuffer **v46; // [rsp+20h] [rbp-A1h]
  int v47; // [rsp+20h] [rbp-A1h]
  int v48; // [rsp+20h] [rbp-A1h]
  struct Windows::Storage::Streams::IDataReader *v49; // [rsp+30h] [rbp-91h] BYREF
  unsigned __int8 v50; // [rsp+38h] [rbp-89h] BYREF
  unsigned __int8 v51; // [rsp+39h] [rbp-88h] BYREF
  unsigned __int8 v52[6]; // [rsp+3Ah] [rbp-87h] BYREF
  unsigned __int8 v53[8]; // [rsp+40h] [rbp-81h] BYREF
  struct IInspectable *v54; // [rsp+48h] [rbp-79h] BYREF
  HSTRING string; // [rsp+50h] [rbp-71h] BYREF
  unsigned __int16 v56; // [rsp+58h] [rbp-69h] BYREF
  struct SharingPlatform::IParticipantIdentifier *v57; // [rsp+60h] [rbp-61h] BYREF
  __int128 v58; // [rsp+68h] [rbp-59h] BYREF
  __int64 v59; // [rsp+78h] [rbp-49h]
  __int64 v60; // [rsp+80h] [rbp-41h] BYREF
  __int64 v61; // [rsp+88h] [rbp-39h] BYREF
  __int64 v62; // [rsp+90h] [rbp-31h] BYREF
  int v63[2]; // [rsp+98h] [rbp-29h] BYREF
  _BYTE v64[16]; // [rsp+A0h] [rbp-21h] BYREF
  _BYTE v65[16]; // [rsp+B0h] [rbp-11h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+47h]

  v61 = a4;
  v54 = 0;
  v6 = a4;
  v7 = (unsigned int)a3;
  v8 = Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(
         (SharingPlatform::SessionClient *)((char *)this + 544),
         &v54);
  v9 = v8;
  if ( v8 >= 0 )
  {
    if ( !v54 )
    {
      v9 = -2147467260;
      goto LABEL_75;
    }
    *(_QWORD *)v53 = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v53);
    OverCallerManagedBuffer = Windows::Storage::Streams::CBuffer_CreateOverCallerManagedBuffer(
                                (Windows::Storage::Streams *)v6,
                                v6,
                                v7,
                                v53,
                                v46);
    v9 = OverCallerManagedBuffer;
    if ( OverCallerManagedBuffer < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA0,
        (unsigned int)".\\sessionclient.cpp",
        (const char *)(unsigned int)OverCallerManagedBuffer,
        v47);
LABEL_74:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v53);
      goto LABEL_75;
    }
    v11 = *((_QWORD *)this + 12);
    v49 = 0;
    v12 = *(__int64 (__fastcall **)(__int64, _QWORD, struct Windows::Storage::Streams::IDataReader **))(*(_QWORD *)v11 + 48LL);
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v49);
    v13 = v12(v11, *(_QWORD *)v53, &v49);
    v9 = v13;
    if ( v13 < 0 )
    {
      v14 = (unsigned int)v13;
      v15 = 164;
LABEL_72:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)".\\sessionclient.cpp",
        (const char *)v14,
        v47);
      goto LABEL_73;
    }
    v16 = SharingPlatform::Internal::SpecificMessageParser::ParseSessionMessageHeader(v49, &v56, &v50, &v51);
    v9 = v16;
    if ( v16 < 0 )
    {
      v14 = (unsigned int)v16;
      v15 = 172;
      goto LABEL_72;
    }
    if ( v56 != 2 || v50 != 1 )
    {
      v9 = -2147483637;
      v15 = 174;
      goto LABEL_71;
    }
    v18 = *a2;
    v19 = v51;
    v52[0] = v51;
    v57 = v18;
    RemoteSessionTraceProvider::LogVerbose<unsigned short const (&)[66],unsigned __int64,unsigned __int64 &,unsigned char>(
      v17,
      &v57,
      &v61,
      v52);
    if ( v19 != 4 )
    {
      if ( v19 == 5 )
      {
        if ( RemoteSessionTraceProvider::IsEnabled(0, v20) )
        {
          v36 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                                v35,
                                                _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
          RemoteSessionTraceProvider::LogInfo_(v36, L"SessionClient OnData Message received: REMOVED");
        }
        EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        *((_DWORD *)this + 138) = 0;
        v37 = *((_QWORD *)this + 58);
        if ( v37 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 72LL))(v37);
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 464);
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 104);
        if ( this != (SharingPlatform::SessionClient *)-32LL )
          LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
        GetRuntimeClassName = (void (*)(void))v54->lpVtbl[1].GetRuntimeClassName;
        goto LABEL_53;
      }
      if ( v19 != 6 )
      {
        if ( v19 != 7 )
        {
          if ( v19 != 8 )
          {
            if ( v19 == 9 )
            {
              if ( RemoteSessionTraceProvider::IsEnabled(0, v20) )
              {
                v24 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                                      v23,
                                                      _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
                RemoteSessionTraceProvider::LogInfo_(
                  v24,
                  L"SessionClient OnData Message received: SESSION_JOIN_REQUEST_REJECTED");
              }
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
              *((_DWORD *)this + 138) = 0;
              v25 = *((_QWORD *)this + 58);
              if ( v25 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 72LL))(v25);
              Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 464);
              Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 104);
              if ( this != (SharingPlatform::SessionClient *)-32LL )
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
              GetRuntimeClassName = (void (*)(void))v54->lpVtbl[1].GetTrustLevel;
              goto LABEL_53;
            }
            if ( v19 == 11 )
            {
              RemoteSessionTraceProvider::LogInfo<unsigned short const (&)[58]>(L"SessionClient OnData Message received: S"
                                                                                 "ESSION_TERMINATED");
              EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
              *((_DWORD *)this + 138) = 0;
              v21 = *((_QWORD *)this + 58);
              if ( v21 )
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 72LL))(v21);
              Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 464);
              Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease((char *)this + 104);
              if ( this != (SharingPlatform::SessionClient *)-32LL )
                LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
              GetRuntimeClassName = (void (*)(void))v54->lpVtbl[1].GetIids;
LABEL_53:
              GetRuntimeClassName();
            }
LABEL_69:
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v49);
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v53);
            v9 = 0;
            goto LABEL_75;
          }
          v61 = 0;
          string = 0;
          *(_QWORD *)v63 = 0;
          v62 = 0;
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v62);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v63);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v61);
          v26 = SharingPlatform::Internal::SpecificMessageParser::ParseSessionStreamMessage(
                  (_DWORD)v49,
                  (unsigned int)v64,
                  (unsigned int)&v61,
                  (unsigned int)&string,
                  (__int64)v63,
                  (__int64)&v62);
          v9 = v26;
          if ( v26 >= 0 )
          {
            ((void (__fastcall *)(struct IInspectable *, _BYTE *, HSTRING, _QWORD, __int64))v54->lpVtbl[2].QueryInterface)(
              v54,
              v64,
              string,
              *(_QWORD *)v63,
              v62);
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v62);
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v63);
            WindowsDeleteString(string);
            string = 0;
            Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v61);
            goto LABEL_69;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x111,
            (unsigned int)".\\sessionclient.cpp",
            (const char *)(unsigned int)v26,
            v48);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v62);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v63);
          WindowsDeleteString(string);
          string = 0;
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v61);
LABEL_73:
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v49);
          goto LABEL_74;
        }
        if ( RemoteSessionTraceProvider::IsEnabled(0, v20) )
        {
          v28 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                                v27,
                                                _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
          RemoteSessionTraceProvider::LogInfo_(v28, L"SessionClient OnData Message received: PARTICIPANT_REMOVED");
        }
        v29 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IDataReader *, _BYTE *))(*(_QWORD *)v49
                                                                                                  + 136LL))(
                v49,
                v65);
        v9 = v29;
        if ( v29 >= 0 )
        {
          ((void (__fastcall *)(struct IInspectable *, _BYTE *))v54->lpVtbl[1].AddRef)(v54, v65);
          goto LABEL_69;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x9B,
          (unsigned int)".\\specificmessageparser.cpp",
          (const char *)(unsigned int)v29,
          v47);
        v15 = 258;
LABEL_71:
        v14 = v9;
        goto LABEL_72;
      }
      if ( RemoteSessionTraceProvider::IsEnabled(0, v20) )
      {
        v31 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                              v30,
                                              _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
        RemoteSessionTraceProvider::LogInfo_(v31, L"SessionClient OnData Message received: PARTICIPANT_ADDED");
      }
      v57 = 0;
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v57);
      v32 = SharingPlatform::Internal::SpecificMessageParser::ParseSessionParticipantJoined(v49, &v57);
      v9 = v32;
      if ( v32 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xF7,
          (unsigned int)".\\sessionclient.cpp",
          (const char *)(unsigned int)v32,
          v47);
        v33 = &v57;
LABEL_44:
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v33);
        goto LABEL_73;
      }
      ((void (__fastcall *)(struct IInspectable *, struct SharingPlatform::IParticipantIdentifier *))v54->lpVtbl[1].QueryInterface)(
        v54,
        v57);
      v34 = &v57;
LABEL_68:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(v34);
      goto LABEL_69;
    }
    v60 = 0;
    v59 = 0;
    v58 = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v60);
    started = SharingPlatform::Internal::SpecificMessageParser::ParseJoiningMessage(v49, &v60, &v58);
    v9 = started;
    if ( started >= 0 )
    {
      v42 = *((_QWORD *)&v58 + 1) - v58;
      if ( RemoteSessionTraceProvider::IsEnabled(v40, v39) )
      {
        v44 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                              v43,
                                              _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
        RemoteSessionTraceProvider::LogInfo_(
          v44,
          L"SessionClient OnData Message received: JOINING got %u participants info",
          (unsigned int)(v42 >> 3));
      }
      EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
      *((_DWORD *)this + 138) = 4;
      if ( this != (SharingPlatform::SessionClient *)-32LL )
        LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
      started = SharingPlatform::SessionClient::CreateAndStartAllSessionStreams((SharingPlatform::SessionClient *)((char *)this - 24));
      v9 = started;
      if ( started >= 0 )
      {
        ((void (__fastcall *)(struct IInspectable *, __int64, __int128 *))v54->lpVtbl[2].Release)(v54, v60, &v58);
        if ( (_QWORD)v58 )
        {
          std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SharingPlatform::ISession>>>(
            v58,
            *((_QWORD *)&v58 + 1));
          std::_Deallocate<16>(v58, (v59 - v58) & 0xFFFFFFFFFFFFFFF8uLL);
          v59 = 0;
          v58 = 0;
        }
        v34 = (struct SharingPlatform::IParticipantIdentifier **)&v60;
        goto LABEL_68;
      }
      v41 = 198;
    }
    else
    {
      v41 = 188;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v41,
      (unsigned int)".\\sessionclient.cpp",
      (const char *)(unsigned int)started,
      v47);
    if ( (_QWORD)v58 )
    {
      std::_Destroy_range<std::allocator<Microsoft::WRL::ComPtr<SharingPlatform::ISession>>>(v58, *((_QWORD *)&v58 + 1));
      std::_Deallocate<16>(v58, (v59 - v58) & 0xFFFFFFFFFFFFFFF8uLL);
      v59 = 0;
      v58 = 0;
    }
    v33 = (struct SharingPlatform::IParticipantIdentifier **)&v60;
    goto LABEL_44;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x9B,
    (unsigned int)".\\sessionclient.cpp",
    (const char *)(unsigned int)v8,
    (int)v46);
LABEL_75:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v54);
  return v9;
}

```

## disassembly

```asm
0x180059340  push    rbp
0x180059342  push    rbx
0x180059343  push    rsi
0x180059344  push    rdi
0x180059345  push    r12
0x180059347  push    r14
0x180059349  push    r15
0x18005934b  lea     rbp, [rsp-0Fh]
0x180059350  sub     rsp, 0D0h
0x180059357  mov     rax, cs:__security_cookie
0x18005935e  xor     rax, rsp
0x180059361  mov     [rbp+3Fh+var_40], rax
0x180059365  mov     r15, rdx
0x180059368  mov     [rbp+3Fh+var_78], r9
0x18005936c  mov     rsi, rcx
0x18005936f  lea     rdx, [rbp+3Fh+var_B8]; struct IInspectable **
0x180059373  xor     r12d, r12d
0x180059376  add     rcx, 220h; this
0x18005937d  mov     [rbp+3Fh+var_B8], r12
0x180059381  mov     rdi, r9
0x180059384  mov     r14, r8
0x180059387  call    ??$As@UISessionMessageChannelCallback@SharingPlatform@@@WeakRef@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::WeakRef::As<SharingPlatform::ISessionMessageChannelCallback>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>>)
0x18005938c  mov     ebx, eax
0x18005938e  test    eax, eax
0x180059390  jns     short loc_1800593AF
0x180059392  mov     rcx, [rbp+47h]; this
0x180059396  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x18005939d  mov     r9d, eax; char *
0x1800593a0  mov     edx, 9Bh; void *
0x1800593a5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800593aa  jmp     loc_1800599F1
0x1800593af  cmp     [rbp+3Fh+var_B8], r12
0x1800593b3  jnz     short loc_1800593BF
0x1800593b5  mov     ebx, 80004004h
0x1800593ba  jmp     loc_1800599F1
0x1800593bf  lea     rcx, [rsp+100h+var_C0]
0x1800593c4  mov     qword ptr [rsp+100h+var_C0], r12
0x1800593c9  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800593ce  lea     r9, [rsp+100h+var_C0]; unsigned __int8 *
0x1800593d3  mov     r8, r14; unsigned int
0x1800593d6  mov     edx, edi; unsigned int
0x1800593d8  mov     ecx, edi; this
0x1800593da  call    ?CBuffer_CreateOverCallerManagedBuffer@Streams@Storage@Windows@@YAJIIPEAEPEAPEAUIBuffer@123@@Z; Windows::Storage::Streams::CBuffer_CreateOverCallerManagedBuffer(uint,uint,uchar *,Windows::Storage::Streams::IBuffer * *)
0x1800593df  mov     ebx, eax
0x1800593e1  test    eax, eax
0x1800593e3  jns     short loc_180059402
0x1800593e5  mov     rcx, [rbp+47h]; this
0x1800593e9  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x1800593f0  mov     r9d, eax; char *
0x1800593f3  mov     edx, 0A0h; void *
0x1800593f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800593fd  jmp     loc_1800599E7
0x180059402  mov     rdi, [rsi+60h]
0x180059406  lea     rcx, [rsp+100h+var_D0]
0x18005940b  mov     [rsp+100h+var_D0], r12
0x180059410  mov     rax, [rdi]
0x180059413  mov     rbx, [rax+30h]
0x180059417  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005941c  mov     rdx, qword ptr [rsp+100h+var_C0]
0x180059421  lea     r8, [rsp+100h+var_D0]
0x180059426  mov     rcx, rdi
0x180059429  mov     rax, rbx
0x18005942c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059431  mov     ebx, eax
0x180059433  test    eax, eax
0x180059435  jns     short loc_180059444
0x180059437  mov     r9d, eax
0x18005943a  mov     edx, 0A4h
0x18005943f  jmp     loc_1800599CD
0x180059444  mov     rcx, [rsp+100h+var_D0]; struct Windows::Storage::Streams::IDataReader *
0x180059449  lea     r9, [rsp+100h+var_C7]; unsigned __int8 *
0x18005944e  lea     r8, [rsp+100h+var_C8]; unsigned __int8 *
0x180059453  lea     rdx, [rbp+3Fh+var_A8]; unsigned __int16 *
0x180059457  call    ?ParseSessionMessageHeader@SpecificMessageParser@Internal@SharingPlatform@@SAJPEAUIDataReader@Streams@Storage@Windows@@PEAGPEAE2@Z; SharingPlatform::Internal::SpecificMessageParser::ParseSessionMessageHeader(Windows::Storage::Streams::IDataReader *,ushort *,uchar *,uchar *)
0x18005945c  mov     ebx, eax
0x18005945e  test    eax, eax
0x180059460  jns     short loc_18005946F
0x180059462  mov     r9d, eax
0x180059465  mov     edx, 0ACh
0x18005946a  jmp     loc_1800599CD
0x18005946f  mov     edi, 2
0x180059474  cmp     [rbp+3Fh+var_A8], di
0x180059478  jnz     loc_1800599C0
0x18005947e  cmp     [rsp+100h+var_C8], 1
0x180059483  jnz     loc_1800599C0
0x180059489  mov     rax, [r15]
0x18005948c  lea     r9, [rsp+100h+var_C6]
0x180059491  movzx   ebx, [rsp+100h+var_C7]
0x180059496  lea     r8, [rbp+3Fh+var_78]
0x18005949a  lea     rdx, [rbp+3Fh+var_A0]
0x18005949e  mov     [rsp+100h+var_C6], bl
0x1800594a2  mov     [rbp+3Fh+var_A0], rax
0x1800594a6  call    ??$LogVerbose@AEAY0EC@$$CBG_KAEA_KE@RemoteSessionTraceProvider@@SAXAEAY0EC@$$CBG$$QEA_KAEA_K$$QEAE@Z; RemoteSessionTraceProvider::LogVerbose<ushort const (&)[66],unsigned __int64,unsigned __int64 &,uchar>(ushort const (&)[66],unsigned __int64 &&,unsigned __int64 &,uchar &&)
0x1800594ab  mov     ecx, ebx
0x1800594ad  sub     ecx, 4
0x1800594b0  jz      loc_18005985F
0x1800594b6  sub     ecx, 1; unsigned __int8
0x1800594b9  jz      loc_1800597D8
0x1800594bf  sub     ecx, 1; unsigned __int8
0x1800594c2  jz      loc_180059750
0x1800594c8  sub     ecx, 1; unsigned __int8
0x1800594cb  jz      loc_1800596D3
0x1800594d1  sub     ecx, 1
0x1800594d4  jz      loc_1800595D3
0x1800594da  sub     ecx, 1; unsigned __int8
0x1800594dd  jz      short loc_180059551
0x1800594df  cmp     ecx, edi
0x1800594e1  jnz     loc_1800599A7
0x1800594e7  lea     rcx, aSessionclientO_7; "SessionClient OnData Message received: "...
0x1800594ee  call    ??$LogInfo@AEAY0DK@$$CBG@RemoteSessionTraceProvider@@SAXAEAY0DK@$$CBG@Z; RemoteSessionTraceProvider::LogInfo<ushort const (&)[58]>(ushort const (&)[58])
0x1800594f3  lea     rbx, [rsi+20h]
0x1800594f7  mov     rcx, rbx; lpCriticalSection
0x1800594fa  call    cs:__imp_EnterCriticalSection
0x180059500  lea     rdi, [rsi+1D0h]
0x180059507  mov     [rsi+228h], r12d
0x18005950e  mov     rcx, [rdi]
0x180059511  test    rcx, rcx
0x180059514  jz      short loc_180059522
0x180059516  mov     rax, [rcx]
0x180059519  mov     rax, [rax+48h]
0x18005951d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059522  mov     rcx, rdi
0x180059525  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005952a  lea     rcx, [rsi+68h]
0x18005952e  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180059533  test    rbx, rbx
0x180059536  jz      short loc_180059541
0x180059538  mov     rcx, rbx; lpCriticalSection
0x18005953b  call    cs:__imp_LeaveCriticalSection
0x180059541  mov     rcx, [rbp+3Fh+var_B8]
0x180059545  mov     rax, [rcx]
0x180059548  mov     rax, [rax+48h]
0x18005954c  jmp     loc_180059855
0x180059551  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x180059556  test    al, al
0x180059558  jz      short loc_180059575
0x18005955a  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x180059561  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x180059566  lea     rdx, aSessionclientO; "SessionClient OnData Message received: "...
0x18005956d  mov     rcx, rax; this
0x180059570  call    ?LogInfo_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogInfo_(ushort const *,...)
0x180059575  lea     rbx, [rsi+20h]
0x180059579  mov     rcx, rbx; lpCriticalSection
0x18005957c  call    cs:__imp_EnterCriticalSection
0x180059582  lea     rdi, [rsi+1D0h]
0x180059589  mov     [rsi+228h], r12d
0x180059590  mov     rcx, [rdi]
0x180059593  test    rcx, rcx
0x180059596  jz      short loc_1800595A4
0x180059598  mov     rax, [rcx]
0x18005959b  mov     rax, [rax+48h]
0x18005959f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800595a4  mov     rcx, rdi
0x1800595a7  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800595ac  lea     rcx, [rsi+68h]
0x1800595b0  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800595b5  test    rbx, rbx
0x1800595b8  jz      short loc_1800595C3
0x1800595ba  mov     rcx, rbx; lpCriticalSection
0x1800595bd  call    cs:__imp_LeaveCriticalSection
0x1800595c3  mov     rcx, [rbp+3Fh+var_B8]
0x1800595c7  mov     rax, [rcx]
0x1800595ca  mov     rax, [rax+58h]
0x1800595ce  jmp     loc_180059855
0x1800595d3  lea     rcx, [rbp+3Fh+var_70]
0x1800595d7  mov     [rbp+3Fh+var_78], r12
0x1800595db  mov     [rbp+3Fh+string], r12
0x1800595df  mov     qword ptr [rbp+3Fh+var_68], r12
0x1800595e3  mov     [rbp+3Fh+var_70], r12
0x1800595e7  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800595ec  lea     rcx, [rbp+3Fh+var_68]
0x1800595f0  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800595f5  mov     rcx, [rbp+3Fh+string]; string
0x1800595f9  call    cs:__imp_WindowsDeleteString
0x1800595ff  lea     rcx, [rbp+3Fh+var_78]
0x180059603  mov     [rbp+3Fh+string], r12
0x180059607  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005960c  mov     rcx, [rsp+100h+var_D0]
0x180059611  lea     rax, [rbp+3Fh+var_70]
0x180059615  mov     [rsp+100h+var_D8], rax
0x18005961a  lea     r9, [rbp+3Fh+string]
0x18005961e  lea     rax, [rbp+3Fh+var_68]
0x180059622  lea     r8, [rbp+3Fh+var_78]
0x180059626  mov     qword ptr [rsp+100h+var_E0], rax; int
0x18005962b  lea     rdx, [rbp+3Fh+var_60]
0x18005962f  call    ?ParseSessionStreamMessage@SpecificMessageParser@Internal@SharingPlatform@@SAJPEAUIDataReader@Streams@Storage@Windows@@PEAU_GUID@@PEAPEAU?$IVector@U_GUID@@@Collections@Foundation@7@PEAPEAUHSTRING__@@PEAPEAUIBuffer@567@4@Z; SharingPlatform::Internal::SpecificMessageParser::ParseSessionStreamMessage(Windows::Storage::Streams::IDataReader *,_GUID *,Windows::Foundation::Collections::IVector<_GUID> * *,HSTRING__ * *,Windows::Storage::Streams::IBuffer * *,Windows::Storage::Streams::IBuffer * *)
0x180059634  mov     ebx, eax
0x180059636  test    eax, eax
0x180059638  jns     short loc_180059680
0x18005963a  mov     rcx, [rbp+47h]; this
0x18005963e  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x180059645  mov     r9d, eax; char *
0x180059648  mov     edx, 111h; void *
0x18005964d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180059652  lea     rcx, [rbp+3Fh+var_70]
0x180059656  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005965b  lea     rcx, [rbp+3Fh+var_68]
0x18005965f  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180059664  mov     rcx, [rbp+3Fh+string]; string
0x180059668  call    cs:__imp_WindowsDeleteString
0x18005966e  lea     rcx, [rbp+3Fh+var_78]
0x180059672  mov     [rbp+3Fh+string], r12
0x180059676  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18005967b  jmp     loc_1800599DD
0x180059680  mov     rdx, [rbp+3Fh+var_70]
0x180059684  mov     rcx, [rbp+3Fh+var_B8]
0x180059688  mov     r9, qword ptr [rbp+3Fh+var_68]
0x18005968c  mov     r8, [rbp+3Fh+string]
0x180059690  mov     qword ptr [rsp+100h+var_E0], rdx
0x180059695  lea     rdx, [rbp+3Fh+var_60]
0x180059699  mov     rax, [rcx]
0x18005969c  mov     rax, [rax+60h]
0x1800596a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800596a5  lea     rcx, [rbp+3Fh+var_70]
0x1800596a9  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800596ae  lea     rcx, [rbp+3Fh+var_68]
0x1800596b2  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800596b7  mov     rcx, [rbp+3Fh+string]; string
0x1800596bb  call    cs:__imp_WindowsDeleteString
0x1800596c1  lea     rcx, [rbp+3Fh+var_78]
0x1800596c5  mov     [rbp+3Fh+string], r12
0x1800596c9  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800596ce  jmp     loc_1800599A7
0x1800596d3  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x1800596d8  test    al, al
0x1800596da  jz      short loc_1800596F7
0x1800596dc  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x1800596e3  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x1800596e8  lea     rdx, aSessionclientO_3; "SessionClient OnData Message received: "...
0x1800596ef  mov     rcx, rax; this
0x1800596f2  call    ?LogInfo_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogInfo_(ushort const *,...)
0x1800596f7  mov     rcx, [rsp+100h+var_D0]
0x1800596fc  lea     rdx, [rbp+3Fh+var_50]
0x180059700  mov     rax, [rcx]
0x180059703  mov     rax, [rax+88h]
0x18005970a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005970f  mov     ebx, eax
0x180059711  test    eax, eax
0x180059713  jns     short loc_180059737
0x180059715  mov     rcx, [rbp+47h]; this
0x180059719  lea     r8, aSpecificmessag; ".\\specificmessageparser.cpp"
0x180059720  mov     r9d, eax; char *
0x180059723  mov     edx, 9Bh; void *
0x180059728  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18005972d  mov     edx, 102h
0x180059732  jmp     loc_1800599CA
0x180059737  mov     rcx, [rbp+3Fh+var_B8]
0x18005973b  lea     rdx, [rbp+3Fh+var_50]
0x18005973f  mov     rax, [rcx]
0x180059742  mov     rax, [rax+38h]
0x180059746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005974b  jmp     loc_1800599A7
0x180059750  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x180059755  test    al, al
0x180059757  jz      short loc_180059774
0x180059759  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x180059760  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x180059765  lea     rdx, aSessionclientO_1; "SessionClient OnData Message received: "...
0x18005976c  mov     rcx, rax; this
0x18005976f  call    ?LogInfo_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogInfo_(ushort const *,...)
0x180059774  lea     rcx, [rbp+3Fh+var_A0]
0x180059778  mov     [rbp+3Fh+var_A0], r12
0x18005977c  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180059781  mov     rcx, [rsp+100h+var_D0]; struct Windows::Storage::Streams::IDataReader *
0x180059786  lea     rdx, [rbp+3Fh+var_A0]; struct SharingPlatform::IParticipantIdentifier **
0x18005978a  call    ?ParseSessionParticipantJoined@SpecificMessageParser@Internal@SharingPlatform@@SAJPEAUIDataReader@Streams@Storage@Windows@@PEAPEAUIParticipantIdentifier@3@@Z; SharingPlatform::Internal::SpecificMessageParser::ParseSessionParticipantJoined(Windows::Storage::Streams::IDataReader *,SharingPlatform::IParticipantIdentifier * *)
0x18005978f  mov     ebx, eax
0x180059791  test    eax, eax
0x180059793  jns     short loc_1800597BB
0x180059795  mov     rcx, [rbp+47h]; this
0x180059799  lea     r8, aSessionclientC_0; ".\\sessionclient.cpp"
0x1800597a0  mov     r9d, eax; char *
0x1800597a3  mov     edx, 0F7h; void *
0x1800597a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800597ad  lea     rcx, [rbp+3Fh+var_A0]
0x1800597b1  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800597b6  jmp     loc_1800599DD
0x1800597bb  mov     rcx, [rbp+3Fh+var_B8]
0x1800597bf  mov     rdx, [rbp+3Fh+var_A0]
0x1800597c3  mov     rax, [rcx]
0x1800597c6  mov     rax, [rax+30h]
0x1800597ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800597cf  lea     rcx, [rbp+3Fh+var_A0]
0x1800597d3  jmp     loc_1800599A2
0x1800597d8  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x1800597dd  test    al, al
0x1800597df  jz      short loc_1800597FC
0x1800597e1  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x1800597e8  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x1800597ed  lea     rdx, aSessionclientO_5; "SessionClient OnData Message received: "...
0x1800597f4  mov     rcx, rax; this
0x1800597f7  call    ?LogInfo_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogInfo_(ushort const *,...)
0x1800597fc  lea     rbx, [rsi+20h]
0x180059800  mov     rcx, rbx; lpCriticalSection
0x180059803  call    cs:__imp_EnterCriticalSection
0x180059809  lea     rdi, [rsi+1D0h]
0x180059810  mov     [rsi+228h], r12d
0x180059817  mov     rcx, [rdi]
0x18005981a  test    rcx, rcx
0x18005981d  jz      short loc_18005982B
  ... truncated ...
```
