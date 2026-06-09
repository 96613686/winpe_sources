# SharingPlatform::SharingPlatformStatics::InitializeInternal(void)

- ea: `0x180009538`
- end: `0x180009774`
- name: `?InitializeInternal@SharingPlatformStatics@SharingPlatform@@SAJXZ`
- size: `572`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `13`
- tags: `broker_com_uri`

## callers

- `0x18001b820`
- `0x180052300`

## callees

- `0x180004628`
- `0x180004928`
- `0x180006668`
- `0x180009538`
- `0x18000a580`
- `0x18000a988`
- `0x18000aa2c`
- `0x180010d64`
- `0x180010ee8`
- `0x18001177c`
- `0x1800130ec`
- `0x1800177d0`
- `0x1800225a0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000974b`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000974b`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009567`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009567`
- `cdp!CDPCreateAppId` at `0x1800095a2`
- `cdp!CDPCreateAppId` at `0x1800095e6`
- `cdp!CDPCreateAppId` at `0x1800095a2`
- `cdp!CDPCreateAppId` at `0x1800095e6`

## string_xrefs

- `0x180009599`: `com.microsoft.analog.snp.platform`
- `0x1800095dd`: `com.microsoft.analog.platform.spatialsharing.sessions`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 SharingPlatform::SharingPlatformStatics::InitializeInternal(void)
{
  int v0; // eax
  unsigned int v1; // ebx
  __int64 v2; // rdx
  __int64 v3; // r8
  char *v4; // r9
  char *v5; // rdx
  __int64 v6; // rcx
  __int128 *v7; // rbx
  _DWORD *v8; // rax
  __int64 v9; // rcx
  RemoteSessionTraceProvider *v10; // rax
  __int128 *v11; // rax
  int v12; // eax
  int v14; // [rsp+20h] [rbp-19h]
  __int64 v15[2]; // [rsp+30h] [rbp-9h] BYREF
  __int128 v16; // [rsp+40h] [rbp+7h] BYREF
  __int128 v17; // [rsp+50h] [rbp+17h]
  __int128 v18; // [rsp+60h] [rbp+27h] BYREF
  __int128 v19; // [rsp+70h] [rbp+37h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+5Fh]

  EnterCriticalSection(&SharingPlatform::SharingPlatformStatics::sm_cs);
  v15[1] = (__int64)&SharingPlatform::SharingPlatformStatics::sm_cs;
  if ( SharingPlatform::SharingPlatformStatics::sm_spAppId
    || (Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&SharingPlatform::SharingPlatformStatics::sm_spAppId),
        v0 = CDPCreateAppId(
               0,
               "com.microsoft.analog.snp.platform",
               0,
               "sharingplatform",
               &SharingPlatform::SharingPlatformStatics::sm_spAppId),
        v1 = v0,
        v0 >= 0) )
  {
    if ( *(_QWORD *)&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId
      || (Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(&SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId),
          v0 = CDPCreateAppId(
                 0,
                 "com.microsoft.analog.platform.spatialsharing.sessions",
                 0,
                 "spatialsharing.sessions",
                 &SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId),
          v1 = v0,
          v0 >= 0) )
    {
      if ( !SharingPlatform::SharingPlatformStatics::sm_spMainListener )
      {
        v16 = 0;
        v17 = 0;
        std::string::_Construct<1,char const *>(&v16, "SharingBinaryHost", 17);
        if ( *((_QWORD *)&v17 + 1) > 0xFu )
        {
          v5 = (char *)v16;
          v4 = (char *)(v16 + v17);
        }
        else
        {
          v4 = (char *)&v16 + v17;
          v5 = (char *)&v16;
        }
        v18 = 0;
        v19 = 0;
        if ( v5 == v4 )
          std::wstring::_Construct_empty(&v18);
        else
          std::wstring::_Construct_from_iter<char const *,char const *,unsigned __int64>(&v18, v5, v3, v4 - v5);
        v7 = &v18;
        if ( *((_QWORD *)&v19 + 1) > 7u )
          v7 = (__int128 *)v18;
        v8 = *(_DWORD **)(wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                            v6,
                            _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_)
                        + 8);
        if ( v8 && *v8 )
        {
          v10 = (RemoteSessionTraceProvider *)wil::details::static_lazy<RemoteSessionTraceProvider>::get(
                                                v9,
                                                _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_);
          RemoteSessionTraceProvider::LogInfo_(v10, L"SharingPlatformStatics::Initialize InstanceId:%s", v7);
        }
        v11 = &v16;
        if ( *((_QWORD *)&v17 + 1) > 0xFu )
          v11 = (__int128 *)v16;
        v15[0] = (__int64)v11;
        Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPListener>::InternalRelease(&SharingPlatform::SharingPlatformStatics::sm_spMainListener);
        v12 = Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPListener,SharingPlatform::Internal::CDPListener,char const *>(
                &SharingPlatform::SharingPlatformStatics::sm_spMainListener,
                v15);
        v1 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x54,
            (unsigned int)".\\sharingplatformstatic.cpp",
            (const char *)(unsigned int)v12,
            v14);
          std::wstring::_Tidy_deallocate(&v18);
          std::string::~string(&v16);
          goto LABEL_26;
        }
        std::wstring::_Tidy_deallocate(&v18);
        std::string::~string(&v16);
      }
      v1 = 0;
      goto LABEL_26;
    }
    v2 = 75;
  }
  else
  {
    v2 = 68;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v2,
    (unsigned int)".\\sharingplatformstatic.cpp",
    (const char *)(unsigned int)v0,
    v14);
LABEL_26:
  LeaveCriticalSection(&SharingPlatform::SharingPlatformStatics::sm_cs);
  return v1;
}

```

## disassembly

```asm
0x180009538  mov     [rsp-8+arg_0], rbx
0x18000953d  mov     [rsp-8+arg_8], rsi
0x180009542  push    rbp
0x180009543  lea     rbp, [rsp-57h]
0x180009548  sub     rsp, 90h
0x18000954f  mov     rax, cs:__security_cookie
0x180009556  xor     rax, rsp
0x180009559  mov     [rbp+57h+var_10], rax
0x18000955d  lea     rsi, ?sm_cs@SharingPlatformStatics@SharingPlatform@@0VCriticalSection@Wrappers@WRL@Microsoft@@A; Microsoft::WRL::Wrappers::CriticalSection SharingPlatform::SharingPlatformStatics::sm_cs
0x180009564  mov     rcx, rsi; lpCriticalSection
0x180009567  call    cs:__imp_EnterCriticalSection
0x18000956d  mov     [rbp+57h+var_58], rsi
0x180009571  cmp     cs:?sm_spAppId@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VICDPAppId@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<ICDPAppId> SharingPlatform::SharingPlatformStatics::sm_spAppId
0x180009579  jnz     short loc_1800095B5
0x18000957b  lea     rbx, ?sm_spAppId@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VICDPAppId@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ICDPAppId> SharingPlatform::SharingPlatformStatics::sm_spAppId
0x180009582  mov     rcx, rbx
0x180009585  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x18000958a  xor     r8d, r8d
0x18000958d  mov     qword ptr [rsp+90h+var_70], rbx
0x180009592  lea     r9, aSharingplatfor_0; "sharingplatform"
0x180009599  lea     rdx, aComMicrosoftAn_0; "com.microsoft.analog.snp.platform"
0x1800095a0  xor     ecx, ecx
0x1800095a2  call    cs:__imp_CDPCreateAppId
0x1800095a8  mov     ebx, eax
0x1800095aa  test    eax, eax
0x1800095ac  jns     short loc_1800095B5
0x1800095ae  mov     edx, 44h ; 'D'
0x1800095b3  jmp     short loc_1800095F7
0x1800095b5  cmp     cs:?sm_spSessionsAppId@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VICDPAppId@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<ICDPAppId> SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId
0x1800095bd  jnz     short loc_18000960F
0x1800095bf  lea     rbx, ?sm_spSessionsAppId@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VICDPAppId@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<ICDPAppId> SharingPlatform::SharingPlatformStatics::sm_spSessionsAppId
0x1800095c6  mov     rcx, rbx
0x1800095c9  call    ?InternalRelease@?$ComPtr@UISessionMessageChannelCallback@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::ISessionMessageChannelCallback>::InternalRelease(void)
0x1800095ce  xor     r8d, r8d
0x1800095d1  mov     qword ptr [rsp+90h+var_70], rbx; int
0x1800095d6  lea     r9, aSpatialsharing; "spatialsharing.sessions"
0x1800095dd  lea     rdx, aComMicrosoftAn; "com.microsoft.analog.platform.spatialsh"...
0x1800095e4  xor     ecx, ecx
0x1800095e6  call    cs:__imp_CDPCreateAppId
0x1800095ec  mov     ebx, eax
0x1800095ee  test    eax, eax
0x1800095f0  jns     short loc_18000960F
0x1800095f2  mov     edx, 4Bh ; 'K'; void *
0x1800095f7  lea     r8, aSharingplatfor; ".\\sharingplatformstatic.cpp"
0x1800095fe  mov     r9d, eax; char *
0x180009601  mov     rcx, [rbp+5Fh]; this
0x180009605  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000960a  jmp     loc_180009748
0x18000960f  cmp     cs:?sm_spMainListener@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VCDPListener@Internal@SharingPlatform@@@WRL@Microsoft@@A, 0; Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPListener> SharingPlatform::SharingPlatformStatics::sm_spMainListener
0x180009617  jnz     loc_180009746
0x18000961d  xorps   xmm0, xmm0
0x180009620  movups  [rbp+57h+var_50], xmm0
0x180009624  xorps   xmm1, xmm1
0x180009627  movdqu  [rbp+57h+var_40], xmm1
0x18000962c  mov     r8d, 11h
0x180009632  lea     rdx, ?SharingBinaryHostName@SharingPlatformStatics@SharingPlatform@@2QBDB; "SharingBinaryHost"
0x180009639  lea     rcx, [rbp+57h+var_50]
0x18000963d  call    ??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z; std::string::_Construct<1,char const *>(char const * const,unsigned __int64)
0x180009642  nop
0x180009643  mov     r9, qword ptr [rbp+57h+var_40]
0x180009647  cmp     qword ptr [rbp+57h+var_40+8], 0Fh
0x18000964c  ja      short loc_18000965B
0x18000964e  lea     rcx, [rbp+57h+var_50]
0x180009652  add     r9, rcx
0x180009655  lea     rdx, [rbp+57h+var_50]
0x180009659  jmp     short loc_180009662
0x18000965b  mov     rdx, qword ptr [rbp+57h+var_50]
0x18000965f  add     r9, rdx
0x180009662  xorps   xmm0, xmm0
0x180009665  movups  [rbp+57h+var_30], xmm0
0x180009669  xorps   xmm1, xmm1
0x18000966c  movdqu  [rbp+57h+var_20], xmm1
0x180009671  lea     rcx, [rbp+57h+var_30]
0x180009675  cmp     rdx, r9
0x180009678  jnz     short loc_180009681
0x18000967a  call    ?_Construct_empty@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Construct_empty(void)
0x18000967f  jmp     short loc_18000968A
0x180009681  sub     r9, rdx
0x180009684  call    ??$_Construct_from_iter@PEBDPEBD_K@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXPEBDQEBD_K@Z; std::wstring::_Construct_from_iter<char const *,char const *,unsigned __int64>(char const *,char const * const,unsigned __int64)
0x180009689  nop
0x18000968a  lea     rbx, [rbp+57h+var_30]
0x18000968e  cmp     qword ptr [rbp+57h+var_20+8], 7
0x180009693  cmova   rbx, qword ptr [rbp+57h+var_30]
0x180009698  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x18000969f  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x1800096a4  mov     rax, [rax+8]
0x1800096a8  test    rax, rax
0x1800096ab  jz      short loc_1800096D1
0x1800096ad  mov     eax, [rax]
0x1800096af  test    eax, eax
0x1800096b1  jz      short loc_1800096D1
0x1800096b3  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_d16ede8d5b83737b43ecc5e6e08d1063_@@CA@XZ; _lambda_d16ede8d5b83737b43ecc5e6e08d1063_::_lambda_invoker_cdecl_(void)
0x1800096ba  call    ?get@?$static_lazy@VRemoteSessionTraceProvider@@@details@wil@@QEAAPEAVRemoteSessionTraceProvider@@P6AXXZ@Z; wil::details::static_lazy<RemoteSessionTraceProvider>::get(void (*)(void))
0x1800096bf  mov     r8, rbx
0x1800096c2  lea     rdx, aSharingplatfor_1; "SharingPlatformStatics::Initialize Inst"...
0x1800096c9  mov     rcx, rax; this
0x1800096cc  call    ?LogInfo_@RemoteSessionTraceProvider@@QEAAXPEBGZZ; RemoteSessionTraceProvider::LogInfo_(ushort const *,...)
0x1800096d1  lea     rax, [rbp+57h+var_50]
0x1800096d5  cmp     qword ptr [rbp+57h+var_40+8], 0Fh
0x1800096da  cmova   rax, qword ptr [rbp+57h+var_50]
0x1800096df  mov     [rbp+57h+var_60], rax
0x1800096e3  lea     rcx, ?sm_spMainListener@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VCDPListener@Internal@SharingPlatform@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPListener> SharingPlatform::SharingPlatformStatics::sm_spMainListener
0x1800096ea  call    ?InternalRelease@?$ComPtr@VCDPListener@Internal@SharingPlatform@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPListener>::InternalRelease(void)
0x1800096ef  lea     rdx, [rbp+57h+var_60]
0x1800096f3  lea     rcx, ?sm_spMainListener@SharingPlatformStatics@SharingPlatform@@0V?$ComPtr@VCDPListener@Internal@SharingPlatform@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<SharingPlatform::Internal::CDPListener> SharingPlatform::SharingPlatformStatics::sm_spMainListener
0x1800096fa  call    ??$MakeAndInitialize@VCDPListener@Internal@SharingPlatform@@V123@PEBD@Details@WRL@Microsoft@@YAJPEAPEAVCDPListener@Internal@SharingPlatform@@$$QEAPEBD@Z; Microsoft::WRL::Details::MakeAndInitialize<SharingPlatform::Internal::CDPListener,SharingPlatform::Internal::CDPListener,char const *>(SharingPlatform::Internal::CDPListener * *,char const * &&)
0x1800096ff  mov     ebx, eax
0x180009701  test    eax, eax
0x180009703  jns     short loc_180009733
0x180009705  mov     rcx, [rbp+5Fh]; this
0x180009709  mov     r9d, eax; char *
0x18000970c  lea     r8, aSharingplatfor; ".\\sharingplatformstatic.cpp"
0x180009713  mov     edx, 54h ; 'T'; void *
0x180009718  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000971d  nop
0x18000971e  lea     rcx, [rbp+57h+var_30]
0x180009722  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x180009727  nop
0x180009728  lea     rcx, [rbp+57h+var_50]
0x18000972c  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180009731  jmp     short loc_180009748
0x180009733  lea     rcx, [rbp+57h+var_30]
0x180009737  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18000973c  nop
0x18000973d  lea     rcx, [rbp+57h+var_50]
0x180009741  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x180009746  xor     ebx, ebx
0x180009748  mov     rcx, rsi; lpCriticalSection
0x18000974b  call    cs:__imp_LeaveCriticalSection
0x180009751  mov     eax, ebx
0x180009753  mov     rcx, [rbp+57h+var_10]
0x180009757  xor     rcx, rsp; StackCookie
0x18000975a  call    __security_check_cookie
0x18000975f  lea     r11, [rsp+90h+var_s0]
0x180009767  mov     rbx, [r11+10h]
0x18000976b  mov     rsi, [r11+18h]
0x18000976f  mov     rsp, r11
0x180009772  pop     rbp
0x180009773  retn
```
