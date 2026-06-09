# SharingPlatform::SendInvitationHelper::SendInvitationToDevice(ICDPDevice *,SharingPlatform::ISessionIdentifier *,HSTRING__ *)

- ea: `0x180053a80`
- end: `0x180053ea2`
- name: `?SendInvitationToDevice@SendInvitationHelper@SharingPlatform@@UEAAJPEAVICDPDevice@@PEAUISessionIdentifier@2@PEAUHSTRING__@@@Z`
- size: `1058`
- prototype: `int(SharingPlatform::SendInvitationHelper *__hidden this, struct ICDPDevice *, struct SharingPlatform::ISessionIdentifier *, HSTRING)`
- caller_count: `1`
- callee_count: `14`
- tags: `broker_com_uri`

## callers

- `0x180053a00`

## callees

- `0x180004928`
- `0x18000a580`
- `0x18000af58`
- `0x180010d04`
- `0x1800130ec`
- `0x180018490`
- `0x1800225a0`
- `0x18004a640`
- `0x1800524bc`
- `0x18005283c`
- `0x1800528fc`
- `0x180053a80`
- `0x180055364`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180053b5c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180053b5c`
- `cdp!CDPCreateBinaryClientInternal` at `0x180053d3a`
- `cdp!CDPCreateBinaryClientInternal` at `0x180053d3a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall SharingPlatform::SendInvitationHelper::SendInvitationToDevice(
        HANDLE *this,
        struct ICDPDevice *a2,
        struct SharingPlatform::ISessionIdentifier *a3,
        HSTRING a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r8
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  unsigned __int8 v22; // cl
  __int64 v23; // rcx
  RemoteSessionTraceProvider *v24; // rax
  int v26; // [rsp+20h] [rbp-E0h]
  struct Windows::Storage::Streams::IBuffer *v27; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v28; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v29; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v30; // [rsp+68h] [rbp-98h] BYREF
  __int64 v31; // [rsp+70h] [rbp-90h] BYREF
  __int64 v32; // [rsp+78h] [rbp-88h] BYREF
  HANDLE *v33; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v34; // [rsp+88h] [rbp-78h] BYREF
  struct ICDPDevice *v35; // [rsp+90h] [rbp-70h] BYREF
  HANDLE *v36; // [rsp+98h] [rbp-68h] BYREF
  _QWORD v37[2]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v38[256]; // [rsp+B0h] [rbp-50h] BYREF
  _BYTE v39[48]; // [rsp+1B0h] [rbp+B0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+228h] [rbp+128h]

  v35 = a2;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(&v35);
  v32 = 0;
  v33 = this;
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v32);
  v8 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPDeviceCallback,ICDPDeviceCallback,SharingPlatform::SendInvitationHelper *>(
         &v32,
         &v33);
  v9 = v8;
  if ( v8 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(struct ICDPDevice *, __int64))(*(_QWORD *)a2 + 48LL))(a2, v32);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 97;
      goto LABEL_5;
    }
    LOBYTE(v11) = 1;
    v8 = (*(__int64 (__fastcall **)(struct ICDPDevice *, __int64, __int64))(*(_QWORD *)a2 + 56LL))(a2, 18, v11);
    v9 = v8;
    if ( v8 < 0 )
    {
      v10 = 100;
      goto LABEL_5;
    }
    if ( WaitForSingleObject(this[6], 0x2710u) )
    {
      v9 = -2147023436;
      v12 = 2147943860LL;
      v10 = 103;
      goto LABEL_6;
    }
    if ( !*((_BYTE *)this + 56) )
    {
      v9 = -2147467259;
      v12 = 2147500037LL;
      v10 = 104;
      goto LABEL_6;
    }
    v37[0] = 0;
    v37[1] = 0;
    v38[0] = 0;
    v39[0] = 0;
    v31 = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
    v13 = SharingPlatform::SharingPlatformStatics::sm_spAppId;
    if ( SharingPlatform::SharingPlatformStatics::sm_spAppId )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)SharingPlatform::SharingPlatformStatics::sm_spAppId + 8LL))(SharingPlatform::SharingPlatformStatics::sm_spAppId);
      v13 = SharingPlatform::SharingPlatformStatics::sm_spAppId;
    }
    v31 = v13;
    v14 = (*(__int64 (__fastcall **)(struct ICDPDevice *, __int64, const char *, _QWORD *))(*(_QWORD *)a2 + 40LL))(
            a2,
            v13,
            "SharingBinaryHost",
            v37);
    v9 = v14;
    if ( v14 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x6F,
        (unsigned int)".\\invitationmanager.cpp",
        (const char *)(unsigned int)v14,
        v26);
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
LABEL_17:
      CDPTarget::~CDPTarget((CDPTarget *)v37);
      goto LABEL_42;
    }
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v31);
    v27 = 0;
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v27);
    v15 = SharingPlatform::Internal::MessageBuilder::WriteInvitation(a3, a4, &v27);
    v9 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x74,
        (unsigned int)".\\invitationmanager.cpp",
        (const char *)(unsigned int)v15,
        v26);
LABEL_20:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v27);
      goto LABEL_17;
    }
    v28 = 0;
    v33 = 0;
    v16 = (*(__int64 (__fastcall **)(struct Windows::Storage::Streams::IBuffer *, unsigned int *))(*(_QWORD *)v27 + 56LL))(
            v27,
            &v34);
    v9 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7D,
        (unsigned int)".\\invitationmanager.cpp",
        (const char *)(unsigned int)v16,
        v26);
LABEL_23:
      Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v28);
      goto LABEL_20;
    }
    v29 = 0;
    v17 = Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(
            (__int64 (__fastcall ****)(_QWORD, GUID *, __int64))&v27,
            (__int64)&v29);
    v9 = v17;
    if ( v17 >= 0 )
    {
      v17 = (*(__int64 (__fastcall **)(__int64, HANDLE **))(*(_QWORD *)v29 + 24LL))(v29, &v33);
      v9 = v17;
      if ( v17 >= 0 )
      {
        Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v28);
        v17 = CDPCreateBinaryClientInternal(&v28);
        v9 = v17;
        if ( v17 >= 0 )
        {
          v30 = 0;
          v36 = this;
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v30);
          v19 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPBinaryClientCallback,ICDPBinaryClientCallback,SharingPlatform::SendInvitationHelper *>(
                  &v30,
                  &v36);
          v9 = v19;
          if ( v19 >= 0 )
          {
            v19 = (*(__int64 (__fastcall **)(__int64, _QWORD *, __int64))(*(_QWORD *)v28 + 24LL))(v28, v37, v30);
            v9 = v19;
            if ( v19 >= 0 )
            {
              if ( RemoteSessionTraceProvider::IsEnabled(v22, v21) )
              {
                v24 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                                      v23,
                                                      _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
                RemoteSessionTraceProvider::LogVerbose_(
                  v24,
                  L"DeviceSessionInvitationManager::SendData deviceId=%hs targetName=%hs",
                  v39,
                  v38);
              }
              v26 = 0;
              v19 = (*(__int64 (__fastcall **)(__int64, _QWORD *, HANDLE *, _QWORD))(*(_QWORD *)v28 + 32LL))(
                      v28,
                      v37,
                      v33,
                      v34);
              v9 = v19;
              if ( v19 >= 0 )
              {
                Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v30);
                Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
                Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v28);
                Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v27);
                CDPTarget::~CDPTarget((CDPTarget *)v37);
                v9 = 0;
                goto LABEL_42;
              }
              v20 = 139;
            }
            else
            {
              v20 = 135;
            }
          }
          else
          {
            v20 = 133;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)".\\invitationmanager.cpp",
            (const char *)(unsigned int)v19,
            v26);
          Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v30);
          goto LABEL_27;
        }
        v18 = 130;
      }
      else
      {
        v18 = 128;
      }
    }
    else
    {
      v18 = 127;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v18,
      (unsigned int)".\\invitationmanager.cpp",
      (const char *)(unsigned int)v17,
      v26);
LABEL_27:
    Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v29);
    goto LABEL_23;
  }
  v10 = 96;
LABEL_5:
  v12 = (unsigned int)v8;
LABEL_6:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v10,
    (unsigned int)".\\invitationmanager.cpp",
    (const char *)v12,
    v26);
LABEL_42:
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v32);
  Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&v35);
  return v9;
}

```

## disassembly

```asm
0x180053a80  push    rbp
0x180053a82  push    rbx
0x180053a83  push    rsi
0x180053a84  push    rdi
0x180053a85  push    r12
0x180053a87  push    r14
0x180053a89  push    r15
0x180053a8b  lea     rbp, [rsp-0F0h]
0x180053a93  sub     rsp, 1F0h
0x180053a9a  mov     rax, cs:__security_cookie
0x180053aa1  xor     rax, rsp
0x180053aa4  mov     [rbp+120h+var_40], rax
0x180053aab  mov     r15, r9
0x180053aae  mov     r14, r8
0x180053ab1  mov     rdi, rdx
0x180053ab4  mov     rsi, rcx
0x180053ab7  mov     [rbp+120h+var_190], rdx
0x180053abb  lea     rcx, [rbp+120h+var_190]
0x180053abf  call    ?InternalAddRef@?$ComPtr@UISessionIdentifier@SharingPlatform@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionIdentifier>::InternalAddRef(void)
0x180053ac4  xor     r12d, r12d
0x180053ac7  mov     [rsp+220h+var_1A8], r12
0x180053acc  mov     [rbp+120h+var_1A0], rsi
0x180053ad0  lea     rcx, [rsp+220h+var_1A8]
0x180053ad5  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053ada  lea     rdx, [rbp+120h+var_1A0]
0x180053ade  lea     rcx, [rsp+220h+var_1A8]
0x180053ae3  call    ??$MakeAndInitialize@VCDPDeviceCallback@Internal@SharingPlatform@@VICDPDeviceCallback@@PEAVSendInvitationHelper@3@@Details@WRL@Microsoft@@YAJPEAPEAVICDPDeviceCallback@@$$QEAPEAVSendInvitationHelper@SharingPlatform@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPDeviceCallback,ICDPDeviceCallback,SharingPlatform::SendInvitationHelper *>(ICDPDeviceCallback * *,SharingPlatform::SendInvitationHelper * &&)
0x180053ae8  mov     ebx, eax
0x180053aea  test    eax, eax
0x180053aec  jns     short loc_180053AF5
0x180053aee  lea     edx, [r12+60h]
0x180053af3  jmp     short loc_180053B14
0x180053af5  mov     rax, [rdi]
0x180053af8  mov     rdx, [rsp+220h+var_1A8]
0x180053afd  mov     rcx, rdi
0x180053b00  mov     rax, [rax+30h]
0x180053b04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b09  mov     ebx, eax
0x180053b0b  test    eax, eax
0x180053b0d  jns     short loc_180053B2F
0x180053b0f  mov     edx, 61h ; 'a'; void *
0x180053b14  mov     r9d, eax; char *
0x180053b17  mov     rcx, [rbp+128h]; this
0x180053b1e  lea     r8, aInvitationmana; ".\\invitationmanager.cpp"
0x180053b25  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053b2a  jmp     loc_180053E6C
0x180053b2f  mov     rax, [rdi]
0x180053b32  mov     r8b, 1
0x180053b35  mov     edx, 12h
0x180053b3a  mov     rcx, rdi
0x180053b3d  mov     rax, [rax+38h]
0x180053b41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053b46  mov     ebx, eax
0x180053b48  test    eax, eax
0x180053b4a  jns     short loc_180053B53
0x180053b4c  mov     edx, 64h ; 'd'
0x180053b51  jmp     short loc_180053B14
0x180053b53  mov     edx, 2710h; dwMilliseconds
0x180053b58  mov     rcx, [rsi+30h]; hHandle
0x180053b5c  call    cs:__imp_WaitForSingleObject
0x180053b62  test    eax, eax
0x180053b64  jz      short loc_180053B75
0x180053b66  mov     ebx, 800705B4h
0x180053b6b  mov     r9d, ebx
0x180053b6e  mov     edx, 67h ; 'g'
0x180053b73  jmp     short loc_180053B17
0x180053b75  cmp     [rsi+38h], r12b
0x180053b79  jnz     short loc_180053B8A
0x180053b7b  mov     ebx, 80004005h
0x180053b80  mov     r9d, ebx
0x180053b83  mov     edx, 68h ; 'h'
0x180053b88  jmp     short loc_180053B17
0x180053b8a  mov     [rbp+120h+var_180], r12
0x180053b8e  mov     [rbp+120h+var_178], r12
0x180053b92  mov     [rbp+120h+var_170], r12b
0x180053b96  mov     [rbp+120h+var_70], r12b
0x180053b9d  mov     [rsp+220h+var_1B0], r12
0x180053ba2  lea     rcx, [rsp+220h+var_1B0]
0x180053ba7  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053bac  nop
0x180053bad  mov     rdx, cs:?sm_spAppId@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VICDPAppId@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ICDPAppId> SharingPlatform::SharingPlatformStatics::sm_spAppId
0x180053bb4  test    rdx, rdx
0x180053bb7  jz      short loc_180053BCF
0x180053bb9  mov     rax, [rdx]
0x180053bbc  mov     rcx, rdx
0x180053bbf  mov     rax, [rax+8]
0x180053bc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bc8  mov     rdx, cs:?sm_spAppId@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VICDPAppId@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ICDPAppId> SharingPlatform::SharingPlatformStatics::sm_spAppId
0x180053bcf  mov     [rsp+220h+var_1B0], rdx
0x180053bd4  mov     rax, [rdi]
0x180053bd7  lea     r9, [rbp+120h+var_180]
0x180053bdb  lea     r8, ?SharingBinaryHostName@SharingPlatformStatics@SharingPlatform@@2QBDB; "SharingBinaryHost"
0x180053be2  mov     rcx, rdi
0x180053be5  mov     rax, [rax+28h]
0x180053be9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053bee  mov     ebx, eax
0x180053bf0  test    eax, eax
0x180053bf2  jns     short loc_180053C27
0x180053bf4  mov     rcx, [rbp+128h]; this
0x180053bfb  mov     r9d, eax; char *
0x180053bfe  lea     r8, aInvitationmana; ".\\invitationmanager.cpp"
0x180053c05  mov     edx, 6Fh ; 'o'; void *
0x180053c0a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053c0f  lea     rcx, [rsp+220h+var_1B0]
0x180053c14  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053c19  lea     rcx, [rbp+120h+var_180]; this
0x180053c1d  call    ??1CDPTarget@@QEAA@XZ; CDPTarget::~CDPTarget(void)
0x180053c22  jmp     loc_180053E6C
0x180053c27  lea     rcx, [rsp+220h+var_1B0]
0x180053c2c  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053c31  mov     [rsp+220h+var_1D0], r12
0x180053c36  lea     rcx, [rsp+220h+var_1D0]
0x180053c3b  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053c40  lea     r8, [rsp+220h+var_1D0]; struct Windows::Storage::Streams::IBuffer **
0x180053c45  mov     rdx, r15; HSTRING
0x180053c48  mov     rcx, r14; struct SharingPlatform::ISessionIdentifier *
0x180053c4b  call    ?WriteInvitation@MessageBuilder@Internal@SharingPlatform@@SAJPEAUISessionIdentifier@3@PEAUHSTRING__@@PEAPEAUIBuffer@Streams@Storage@Windows@@@Z; SharingPlatform::Internal::MessageBuilder::WriteInvitation(SharingPlatform::ISessionIdentifier *,HSTRING__ *,Windows::Storage::Streams::IBuffer * *)
0x180053c50  mov     ebx, eax
0x180053c52  test    eax, eax
0x180053c54  jns     short loc_180053C7D
0x180053c56  mov     rcx, [rbp+128h]; this
0x180053c5d  mov     r9d, eax; char *
0x180053c60  lea     r8, aInvitationmana; ".\\invitationmanager.cpp"
0x180053c67  mov     edx, 74h ; 't'; void *
0x180053c6c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053c71  lea     rcx, [rsp+220h+var_1D0]
0x180053c76  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053c7b  jmp     short loc_180053C19
0x180053c7d  mov     [rsp+220h+var_1C8], r12
0x180053c82  mov     [rbp+120h+var_1A0], r12
0x180053c86  mov     rcx, [rsp+220h+var_1D0]
0x180053c8b  mov     rax, [rcx]
0x180053c8e  lea     rdx, [rbp+120h+var_198]
0x180053c92  mov     rax, [rax+38h]
0x180053c96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053c9b  mov     ebx, eax
0x180053c9d  test    eax, eax
0x180053c9f  jns     short loc_180053CC8
0x180053ca1  mov     rcx, [rbp+128h]; this
0x180053ca8  mov     r9d, eax; char *
0x180053cab  lea     r8, aInvitationmana; ".\\invitationmanager.cpp"
0x180053cb2  mov     edx, 7Dh ; '}'; void *
0x180053cb7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053cbc  lea     rcx, [rsp+220h+var_1C8]
0x180053cc1  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053cc6  jmp     short loc_180053C71
0x180053cc8  mov     [rsp+220h+var_1C0], r12
0x180053ccd  lea     rdx, [rsp+220h+var_1C0]
0x180053cd2  lea     rcx, [rsp+220h+var_1D0]
0x180053cd7  call    ??$As@UIBufferByteAccess@Streams@Storage@Windows@@@?$ComPtr@UIBuffer@Streams@Storage@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIBufferByteAccess@Streams@Storage@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBuffer>::As<Windows::Storage::Streams::IBufferByteAccess>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Storage::Streams::IBufferByteAccess>>)
0x180053cdc  mov     ebx, eax
0x180053cde  test    eax, eax
0x180053ce0  jns     short loc_180053D09
0x180053ce2  mov     edx, 7Fh; void *
0x180053ce7  mov     rcx, [rbp+128h]; this
0x180053cee  mov     r9d, eax; char *
0x180053cf1  lea     r8, aInvitationmana; ".\\invitationmanager.cpp"
0x180053cf8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053cfd  lea     rcx, [rsp+220h+var_1C0]
0x180053d02  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053d07  jmp     short loc_180053CBC
0x180053d09  mov     rcx, [rsp+220h+var_1C0]
0x180053d0e  mov     rax, [rcx]
0x180053d11  lea     rdx, [rbp+120h+var_1A0]
0x180053d15  mov     rax, [rax+18h]
0x180053d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053d1e  mov     ebx, eax
0x180053d20  test    eax, eax
0x180053d22  jns     short loc_180053D2B
0x180053d24  mov     edx, 80h
0x180053d29  jmp     short loc_180053CE7
0x180053d2b  lea     rcx, [rsp+220h+var_1C8]
0x180053d30  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053d35  lea     rcx, [rsp+220h+var_1C8]
0x180053d3a  call    cs:__imp_CDPCreateBinaryClientInternal
0x180053d40  mov     ebx, eax
0x180053d42  test    eax, eax
0x180053d44  jns     short loc_180053D4D
0x180053d46  mov     edx, 82h
0x180053d4b  jmp     short loc_180053CE7
0x180053d4d  mov     [rsp+220h+var_1B8], r12
0x180053d52  mov     [rbp+120h+var_188], rsi
0x180053d56  lea     rcx, [rsp+220h+var_1B8]
0x180053d5b  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053d60  lea     rdx, [rbp+120h+var_188]
0x180053d64  lea     rcx, [rsp+220h+var_1B8]
0x180053d69  call    ??$MakeAndInitialize@VCDPBinaryClientCallback@Internal@SharingPlatform@@VICDPBinaryClientCallback@@PEAVSendInvitationHelper@3@@Details@WRL@Microsoft@@YAJPEAPEAVICDPBinaryClientCallback@@$$QEAPEAVSendInvitationHelper@SharingPlatform@@@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPBinaryClientCallback,ICDPBinaryClientCallback,SharingPlatform::SendInvitationHelper *>(ICDPBinaryClientCallback * *,SharingPlatform::SendInvitationHelper * &&)
0x180053d6e  mov     ebx, eax
0x180053d70  test    eax, eax
0x180053d72  jns     short loc_180053D9E
0x180053d74  mov     edx, 85h; void *
0x180053d79  mov     rcx, [rbp+128h]; this
0x180053d80  mov     r9d, eax; char *
0x180053d83  lea     r8, aInvitationmana; ".\\invitationmanager.cpp"
0x180053d8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180053d8f  lea     rcx, [rsp+220h+var_1B8]
0x180053d94  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053d99  jmp     loc_180053CFD
0x180053d9e  mov     rcx, [rsp+220h+var_1C8]
0x180053da3  mov     rax, [rcx]
0x180053da6  mov     r8, [rsp+220h+var_1B8]
0x180053dab  lea     rdx, [rbp+120h+var_180]
0x180053daf  mov     rax, [rax+18h]
0x180053db3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053db8  mov     ebx, eax
0x180053dba  test    eax, eax
0x180053dbc  jns     short loc_180053DC5
0x180053dbe  mov     edx, 87h
0x180053dc3  jmp     short loc_180053D79
0x180053dc5  call    ?IsEnabled@RemoteSessionTraceProvider@@SA_NE_K@Z; RemoteSessionTraceProvider::IsEnabled(uchar,unsigned __int64)
0x180053dca  test    al, al
0x180053dcc  jz      short loc_180053DF4
0x180053dce  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x180053dd5  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x180053dda  lea     r9, [rbp+120h+var_170]
0x180053dde  lea     r8, [rbp+120h+var_70]
0x180053de5  lea     rdx, aDevicesessioni; "DeviceSessionInvitationManager::SendDat"...
0x180053dec  mov     rcx, rax; this
0x180053def  call    ?LogVerbose_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogVerbose_(ushort const *,...)
0x180053df4  mov     rcx, [rsp+220h+var_1C8]
0x180053df9  mov     rax, [rcx]
0x180053dfc  mov     r9d, [rbp+120h+var_198]
0x180053e00  mov     [rsp+220h+var_1E8], 0EA60h
0x180053e08  mov     [rsp+220h+var_1F0], r12
0x180053e0d  mov     [rsp+220h+var_1F8], r12
0x180053e12  mov     [rsp+220h+var_200], r12
0x180053e17  mov     r8, [rbp+120h+var_1A0]
0x180053e1b  lea     rdx, [rbp+120h+var_180]
0x180053e1f  mov     rax, [rax+20h]
0x180053e23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053e28  mov     ebx, eax
0x180053e2a  test    eax, eax
0x180053e2c  jns     short loc_180053E38
0x180053e2e  mov     edx, 8Bh
0x180053e33  jmp     loc_180053D79
0x180053e38  lea     rcx, [rsp+220h+var_1B8]
0x180053e3d  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053e42  lea     rcx, [rsp+220h+var_1C0]
0x180053e47  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053e4c  lea     rcx, [rsp+220h+var_1C8]
0x180053e51  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053e56  lea     rcx, [rsp+220h+var_1D0]
0x180053e5b  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053e60  lea     rcx, [rbp+120h+var_180]; this
0x180053e64  call    ??1CDPTarget@@QEAA@XZ; CDPTarget::~CDPTarget(void)
0x180053e69  mov     ebx, r12d
0x180053e6c  lea     rcx, [rsp+220h+var_1A8]
0x180053e71  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053e76  lea     rcx, [rbp+120h+var_190]
0x180053e7a  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x180053e7f  mov     eax, ebx
0x180053e81  mov     rcx, [rbp+120h+var_40]
0x180053e88  xor     rcx, rsp; StackCookie
0x180053e8b  call    __security_check_cookie
0x180053e90  add     rsp, 1F0h
0x180053e97  pop     r15
0x180053e99  pop     r14
0x180053e9b  pop     r12
0x180053e9d  pop     rdi
0x180053e9e  pop     rsi
0x180053e9f  pop     rbx
0x180053ea0  pop     rbp
0x180053ea1  retn
```
