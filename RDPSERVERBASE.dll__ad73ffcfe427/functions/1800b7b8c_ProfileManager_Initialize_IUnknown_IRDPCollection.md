# ProfileManager::Initialize(IUnknown *,IRDPCollection *)

- ea: `0x1800b7b8c`
- end: `0x1800b84f1`
- name: `?Initialize@ProfileManager@@AEAAJPEAUIUnknown@@PEAUIRDPCollection@@@Z`
- size: `2405`
- prototype: `__int64 __fastcall(ProfileManager *__hidden this, struct IUnknown *, struct IRDPCollection *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b67e4`

## callees

- `0x1800012dc`
- `0x180001f84`
- `0x1800023e4`
- `0x180002568`
- `0x18000305c`
- `0x18000ce04`
- `0x180076090`
- `0x180079770`
- `0x18007e9e0`
- `0x18007f42c`
- `0x180089e40`
- `0x180089ef0`
- `0x1800b7b8c`
- `0x1800c06b8`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800b7e2c`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800b7e2c`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800b7c04`
- `RDPBASE!RDPAPI_GetGenericCounter` at `0x1800b7c04`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7ef8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800b7ef8`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7dc7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800b7dc7`

## string_xrefs

- `0x1800b832f`: `ReadRegistryUINT failed!`
- `0x1800b7db9`: `SOFTWARE\WOW6432Node\Google\Chrome\NativeMessagingHosts\com.microsoft.msrdcmmrnativehost`
- `0x1800b7eac`: `MMR host is installed`
- `0x1800b813e`: `ReadRegistryBOOL failed!`
- `0x1800b81d6`: `CacheEnabled`

## pseudocode

```c
__int64 __fastcall ProfileManager::Initialize(ProfileManager *this, struct IUnknown *a2, struct IRDPCollection *a3)
{
  int GenericCounter; // ebx
  signed int v7; // eax
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v9; // edx
  const char *v10; // rcx
  int v11; // r15d
  int *v12; // rsi
  __int64 v13; // r8
  __int64 v14; // r9
  int v15; // ebx
  int v16; // ecx
  int v17; // eax
  int v18; // eax
  int v19; // ecx
  int v20; // r8d
  int v21; // r9d
  int *v22; // rbx
  int v23; // ecx
  int v24; // r8d
  int v25; // r9d
  signed int v26; // eax
  __m128i si128; // xmm0
  signed int GfxPipeSettingBOOL; // eax
  signed int v29; // eax
  signed int v30; // eax
  signed int v31; // eax
  signed int GfxPipeSettingUINT; // eax
  signed int v33; // eax
  __int64 v34; // rax
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  int v38; // ecx
  int v39; // r8d
  int v40; // r9d
  int v41; // ecx
  int phkResult; // [rsp+20h] [rbp-E0h]
  int phkResulta; // [rsp+20h] [rbp-E0h]
  int v45[2]; // [rsp+50h] [rbp-B0h] BYREF
  int v46; // [rsp+58h] [rbp-A8h] BYREF
  struct IRDPCollection *v47; // [rsp+60h] [rbp-A0h] BYREF
  int v48; // [rsp+68h] [rbp-98h] BYREF
  int v49; // [rsp+6Ch] [rbp-94h] BYREF
  int v50[2]; // [rsp+70h] [rbp-90h] BYREF
  int v51; // [rsp+78h] [rbp-88h] BYREF
  const char *v52; // [rsp+80h] [rbp-80h] BYREF
  const char *v53; // [rsp+88h] [rbp-78h] BYREF
  const char *v54; // [rsp+90h] [rbp-70h] BYREF
  HKEY hKey; // [rsp+98h] [rbp-68h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+A0h] [rbp-60h] BYREF

  v47 = 0;
  v51 = 0;
  hKey = 0;
  v49 = 0;
  v48 = 0;
  GenericCounter = RDPAPI_GetGenericCounter(
                     L"RDV::RDP::GraphicsPipeline::PipelineProfile",
                     0xFFFFFFFFLL,
                     0xFFFFFFFFLL,
                     0xFFFFFFFFLL,
                     4,
                     (char *)this + 352);
  if ( GenericCounter < 0 )
    goto LABEL_94;
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IRDPCollection **))a2->lpVtbl->QueryInterface)(
         a2,
         &IID_IRDPCollection,
         &v47);
  GenericCounter = v7;
  if ( v7 >= 0 )
  {
    v11 = 0;
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, char *))(*(_QWORD *)v47 + 32LL))(
           v47,
           L"GfxPipeline::ForceRemoteFXProfile",
           (char *)this + 236) < 0 )
      *((_DWORD *)this + 59) = 0;
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, int *))(*(_QWORD *)v47 + 32LL))(
           v47,
           L"GfxPipeline::EnableFBR",
           &v51) >= 0 )
      *((_DWORD *)this + 35) = v51;
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, char *))(*(_QWORD *)v47 + 32LL))(
           v47,
           L"GfxPipeline::ForceLyncMCUProfile",
           (char *)this + 240) < 0 )
      *((_DWORD *)this + 60) = 0;
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, char *))(*(_QWORD *)v47 + 32LL))(
           v47,
           L"GfxPipeline::ForceLyncProfile",
           (char *)this + 244) < 0 )
      *((_DWORD *)this + 61) = 0;
    v12 = (int *)((char *)this + 256);
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, char *))(*(_QWORD *)v47 + 32LL))(
           v47,
           L"WVD::EnableAVCMMProfile",
           (char *)this + 256) < 0
      && (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, char *))(*(_QWORD *)a3 + 32LL))(
           a3,
           L"GfxPipeline::AVCMixedModePreferred",
           (char *)this + 256) < 0 )
    {
      *v12 = 0;
    }
    if ( !RegOpenKeyExW(
            HKEY_LOCAL_MACHINE,
            L"SOFTWARE\\WOW6432Node\\Google\\Chrome\\NativeMessagingHosts\\com.microsoft.msrdcmmrnativehost",
            0,
            0x20019u,
            &hKey) )
    {
      v11 = 1;
      if ( *v12 )
      {
        v15 = 0;
        if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, int *))(*(_QWORD *)v47 + 32LL))(
               v47,
               L"WVD::EnableMMRHint",
               &v49) < 0 )
          v49 = 0;
        memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
        VersionInformation.dwOSVersionInfoSize = 284;
        if ( GetVersionExW(&VersionInformation) && VersionInformation.dwBuildNumber >= 0x55F0 )
          v15 = 1;
        if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, int *))(*(_QWORD *)v47 + 32LL))(
               v47,
               L"WVD::RDRStackVersionWithMMRHint",
               &v48) >= 0 )
        {
          v17 = v48;
        }
        else
        {
          v17 = 0;
          v48 = 0;
        }
        if ( !v49 || !v17 || (v18 = 1, !v15) )
          v18 = 0;
        *v12 = v18;
        if ( (unsigned int)CallbackContext > 4 )
        {
          LODWORD(v53) = v48;
          LODWORD(v52) = v49;
          v46 = *v12;
          v54 = "MMR host is installed";
          v45[0] = v15;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
            v16,
            (unsigned int)byte_18027EF93,
            v13,
            v14,
            (__int64)&v54,
            (__int64)&v46,
            (__int64)&v52,
            (__int64)&v53,
            (__int64)v45);
        }
      }
    }
    if ( hKey )
      RegCloseKey(hKey);
    if ( (unsigned int)CallbackContext > 4
      && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v13, v14) )
    {
      v46 = v11;
      v54 = (char *)this + 328;
      *(_QWORD *)v45 = 0x1000000;
      v52 = "ProfileMgr";
      v53 = "Stack";
      *(_QWORD *)v50 = "Checkpoint";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
        v19,
        (unsigned int)&unk_18027EF20,
        v20,
        v21,
        (__int64)v50,
        (__int64)v45,
        (__int64)&v53,
        (__int64)&v52,
        (__int64)&v54,
        (__int64)&v46);
    }
    v22 = (int *)((char *)this + 304);
    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, char *))(*(_QWORD *)v47 + 32LL))(
           v47,
           L"WVD::EnableAVCMMRail",
           (char *)this + 304) < 0 )
      *v22 = 0;
    if ( (unsigned int)CallbackContext > 4 )
    {
      v46 = *v22;
      LODWORD(v52) = *v12;
      *(_QWORD *)v50 = "AVC Mixed Mode settings:";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v23,
        (unsigned int)&unk_18027EED0,
        v24,
        v25,
        (__int64)v50,
        (__int64)&v52,
        (__int64)&v46);
    }
    v26 = ProfileManager::SetConnectionProperties(this, a3, v47);
    GenericCounter = v26;
    if ( v26 >= 0 )
    {
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      *(__m128i *)((char *)this + 136) = si128;
      *(__m128i *)((char *)this + 152) = si128;
      v45[0] = 0;
      *((_QWORD *)this + 21) = si128.m128i_i64[0];
      *((__m128i *)this + 11) = si128;
      *((__m128i *)this + 12) = si128;
      *((__m128i *)this + 13) = si128;
      *((_DWORD *)this + 56) = _mm_cvtsi128_si32(si128);
      GfxPipeSettingBOOL = GetGfxPipeSettingBOOL(L"VideoDetectionEnabled", 1, v45);
      GenericCounter = GfxPipeSettingBOOL;
      if ( GfxPipeSettingBOOL >= 0 )
      {
        *((_DWORD *)this + 37) = v45[0];
        v29 = GetGfxPipeSettingBOOL(L"MotionDetectionEnabled", 1, v45);
        GenericCounter = v29;
        if ( v29 >= 0 )
        {
          *((_DWORD *)this + 39) = v45[0];
          v30 = GetGfxPipeSettingBOOL(L"CacheEnabled", 1, v45);
          GenericCounter = v30;
          if ( v30 >= 0 )
          {
            *((_DWORD *)this + 40) = v45[0];
            v31 = GetGfxPipeSettingBOOL(L"ClassifierEnabled", 1, v45);
            GenericCounter = v31;
            if ( v31 >= 0 )
            {
              *((_DWORD *)this + 41) = v45[0];
              GfxPipeSettingUINT = GetGfxPipeSettingUINT(L"AvcPipelineVideo", 1u, (unsigned int *)this + 74);
              GenericCounter = GfxPipeSettingUINT;
              if ( GfxPipeSettingUINT >= 0 )
              {
                v33 = GetGfxPipeSettingUINT(L"Downsampling", 1u, (unsigned int *)this + 75);
                GenericCounter = v33;
                if ( v33 >= 0 )
                {
                  if ( a3 )
                  {
                    v34 = *(_QWORD *)a3;
                    v45[0] = 0;
                    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, int *))(v34 + 40))(
                           a3,
                           L"GfxPipeline::DefaultCodec",
                           v45) >= 0 )
                    {
                      if ( v45[0] )
                      {
                        *((_DWORD *)this + 80) = v45[0];
                        if ( (unsigned int)CallbackContext > 4 )
                        {
                          v46 = v45[0];
                          *(_QWORD *)v50 = "Initialize: Default codec is";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                            v35,
                            (unsigned int)&word_18027EE9E,
                            v36,
                            v37,
                            (__int64)v50,
                            (__int64)&v46);
                        }
                      }
                    }
                    if ( (*(int (__fastcall **)(struct IRDPCollection *, const wchar_t *, int *))(*(_QWORD *)a3 + 40LL))(
                           a3,
                           L"GfxPipeline::ImageCodec",
                           v45) >= 0 )
                    {
                      if ( v45[0] )
                      {
                        *((_DWORD *)this + 81) = v45[0];
                        if ( (unsigned int)CallbackContext > 4 )
                        {
                          v46 = v45[0];
                          *(_QWORD *)v50 = "Initialize: Image codec is";
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                            v38,
                            (unsigned int)&dword_18027EE6C,
                            v39,
                            v40,
                            (__int64)v50,
                            (__int64)&v46);
                        }
                      }
                    }
                  }
                  if ( *((_DWORD *)this + 77) == 1 )
                  {
                    v41 = *((_DWORD *)this + 71);
                    if ( ((v41 - 512) & 0xFFFFF9FF) != 0 || v41 == 1536 )
                      *((_DWORD *)this + 77) = 0;
                  }
                  goto LABEL_94;
                }
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_InitializeGetGfxPipeSettingFail",
                  (char *)0x15A,
                  v33,
                  phkResulta);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_94;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v9 = 22;
              }
              else
              {
                RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
                  (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
                  "ProfileManagerError_InitializeGetGfxPipeSettingFail",
                  (char *)0x152,
                  GfxPipeSettingUINT,
                  phkResulta);
                if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
                  || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
                  || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
                {
                  goto LABEL_94;
                }
                CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
                v9 = 21;
              }
              v10 = "ReadRegistryUINT failed!";
              goto LABEL_7;
            }
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
              "ProfileManagerError_InitializeGetGfxPipeSettingFail",
              (char *)0x149,
              v31,
              phkResulta);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_94;
            }
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v9 = 20;
          }
          else
          {
            RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
              (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
              "ProfileManagerError_InitializeGetGfxPipeSettingFail",
              (char *)0x13F,
              v30,
              phkResulta);
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
            {
              goto LABEL_94;
            }
            CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
            v9 = 19;
          }
        }
        else
        {
          RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
            (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
            "ProfileManagerError_InitializeGetGfxPipeSettingFail",
            (char *)0x136,
            v29,
            phkResulta);
          if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
            || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
            || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
          {
            goto LABEL_94;
          }
          CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
          v9 = 18;
        }
      }
      else
      {
        RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
          (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
          "ProfileManagerError_InitializeGetGfxPipeSettingFail",
          (char *)0x12D,
          GfxPipeSettingBOOL,
          phkResulta);
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_94;
        }
        CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
        v9 = 17;
      }
      v10 = "ReadRegistryBOOL failed!";
      goto LABEL_7;
    }
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
      "ProfileManagerError_InitializeSetConnectionPropertiesFail",
      (char *)0x11B,
      v26,
      phkResulta);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 16;
      v10 = "Failed to set the connection properties";
      goto LABEL_7;
    }
  }
  else
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpProfileManager",
      "ProfileManagerError_InitializeQueryInterfaceFail",
      (char *)0xB1,
      v7,
      phkResult);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
      v9 = 15;
      v10 = "Failed to QI for the context properties";
LABEL_7:
      WPP_SF_DsD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v9,
        (unsigned int)WPP_8c9510a349ee3b6327c0d183301c85a7_Traceguids,
        CurrentThreadActivityIdPrefix,
        (__int64)v10,
        GenericCounter);
    }
  }
LABEL_94:
  TCntPtr<IRdpVCMgr>::SafeRelease(&v47);
  return (unsigned int)GenericCounter;
}

```

## disassembly

```asm
0x1800b7b8c  mov     [rsp-8+arg_18], rbx
0x1800b7b91  push    rbp
0x1800b7b92  push    rsi
0x1800b7b93  push    rdi
0x1800b7b94  push    r12
0x1800b7b96  push    r13
0x1800b7b98  push    r14
0x1800b7b9a  push    r15
0x1800b7b9c  lea     rbp, [rsp-0D0h]
0x1800b7ba4  sub     rsp, 1D0h
0x1800b7bab  mov     rax, cs:__security_cookie
0x1800b7bb2  xor     rax, rsp
0x1800b7bb5  mov     [rbp+100h+var_40], rax
0x1800b7bbc  xor     r12d, r12d
0x1800b7bbf  lea     rax, [rcx+160h]
0x1800b7bc6  mov     rsi, rdx
0x1800b7bc9  mov     [rsp+200h+var_1D8], rax
0x1800b7bce  or      edx, 0FFFFFFFFh
0x1800b7bd1  mov     [rsp+200h+var_1A0], r12
0x1800b7bd6  mov     r14, r8
0x1800b7bd9  mov     [rsp+200h+var_188], r12d
0x1800b7bde  mov     rdi, rcx
0x1800b7be1  mov     [rbp+100h+hKey], r12
0x1800b7be5  mov     r9d, edx
0x1800b7be8  mov     [rsp+200h+var_194], r12d
0x1800b7bed  mov     r8d, edx
0x1800b7bf0  mov     [rsp+200h+var_198], r12d
0x1800b7bf5  lea     rcx, aRdvRdpGraphics_44; "RDV::RDP::GraphicsPipeline::PipelinePro"...
0x1800b7bfc  mov     dword ptr [rsp+200h+phkResult], 4; int
0x1800b7c04  call    cs:__imp_RDPAPI_GetGenericCounter
0x1800b7c0a  mov     ebx, eax
0x1800b7c0c  test    eax, eax
0x1800b7c0e  js      loc_1800B84BB
0x1800b7c14  mov     rax, [rsi]
0x1800b7c17  lea     r8, [rsp+200h+var_1A0]
0x1800b7c1c  lea     rdx, IID_IRDPCollection
0x1800b7c23  mov     rcx, rsi
0x1800b7c26  mov     rax, [rax]
0x1800b7c29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7c2e  mov     ebx, eax
0x1800b7c30  test    eax, eax
0x1800b7c32  jns     loc_1800B7CB8
0x1800b7c38  mov     r9d, eax; unsigned int
0x1800b7c3b  lea     rdx, aProfilemanager_19; "ProfileManagerError_InitializeQueryInte"...
0x1800b7c42  mov     r8d, 0B1h; char *
0x1800b7c48  lea     rcx, aIidIrdpprofile; "IID_IRdpProfileManager"
0x1800b7c4f  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b7c54  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7c5b  lea     rax, WPP_GLOBAL_Control
0x1800b7c62  cmp     rcx, rax
0x1800b7c65  jz      loc_1800B84BB
0x1800b7c6b  test    byte ptr [rcx+1Ch], 8
0x1800b7c6f  jz      loc_1800B84BB
0x1800b7c75  cmp     byte ptr [rcx+19h], 2
0x1800b7c79  jb      loc_1800B84BB
0x1800b7c7f  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b7c84  lea     edx, [r12+0Fh]
0x1800b7c89  lea     rcx, aFailedToQiForT_3; "Failed to QI for the context properties"
0x1800b7c90  mov     dword ptr [rsp+200h+var_1D8], ebx
0x1800b7c94  lea     r8, WPP_8c9510a349ee3b6327c0d183301c85a7_Traceguids
0x1800b7c9b  mov     [rsp+200h+phkResult], rcx
0x1800b7ca0  mov     r9d, eax
0x1800b7ca3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b7caa  mov     rcx, [rcx+10h]
0x1800b7cae  call    WPP_SF_DsD
0x1800b7cb3  jmp     loc_1800B84BB
0x1800b7cb8  mov     rcx, [rsp+200h+var_1A0]
0x1800b7cbd  lea     rbx, [rdi+0ECh]
0x1800b7cc4  mov     r8, rbx
0x1800b7cc7  lea     rdx, aGfxpipelineFor_0; "GfxPipeline::ForceRemoteFXProfile"
0x1800b7cce  mov     r15d, r12d
0x1800b7cd1  mov     rax, [rcx]
0x1800b7cd4  mov     rax, [rax+20h]
0x1800b7cd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7cdd  test    eax, eax
0x1800b7cdf  jns     short loc_1800B7CE4
0x1800b7ce1  mov     [rbx], r12d
0x1800b7ce4  mov     rcx, [rsp+200h+var_1A0]
0x1800b7ce9  lea     r8, [rsp+200h+var_188]
0x1800b7cee  lea     rdx, aGfxpipelineEna; "GfxPipeline::EnableFBR"
0x1800b7cf5  mov     rax, [rcx]
0x1800b7cf8  mov     rax, [rax+20h]
0x1800b7cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d01  test    eax, eax
0x1800b7d03  js      short loc_1800B7D0F
0x1800b7d05  mov     eax, [rsp+200h+var_188]
0x1800b7d09  mov     [rdi+8Ch], eax
0x1800b7d0f  mov     rcx, [rsp+200h+var_1A0]
0x1800b7d14  lea     rbx, [rdi+0F0h]
0x1800b7d1b  mov     r8, rbx
0x1800b7d1e  lea     rdx, aGfxpipelineFor_1; "GfxPipeline::ForceLyncMCUProfile"
0x1800b7d25  mov     rax, [rcx]
0x1800b7d28  mov     rax, [rax+20h]
0x1800b7d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d31  test    eax, eax
0x1800b7d33  jns     short loc_1800B7D38
0x1800b7d35  mov     [rbx], r12d
0x1800b7d38  mov     rcx, [rsp+200h+var_1A0]
0x1800b7d3d  lea     rbx, [rdi+0F4h]
0x1800b7d44  mov     r8, rbx
0x1800b7d47  lea     rdx, aGfxpipelineFor; "GfxPipeline::ForceLyncProfile"
0x1800b7d4e  mov     rax, [rcx]
0x1800b7d51  mov     rax, [rax+20h]
0x1800b7d55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d5a  test    eax, eax
0x1800b7d5c  jns     short loc_1800B7D61
0x1800b7d5e  mov     [rbx], r12d
0x1800b7d61  mov     rcx, [rsp+200h+var_1A0]
0x1800b7d66  lea     rsi, [rdi+100h]
0x1800b7d6d  mov     r8, rsi
0x1800b7d70  lea     rdx, aWvdEnableavcmm_0; "WVD::EnableAVCMMProfile"
0x1800b7d77  mov     rax, [rcx]
0x1800b7d7a  mov     rax, [rax+20h]
0x1800b7d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7d83  test    eax, eax
0x1800b7d85  jns     short loc_1800B7DA7
0x1800b7d87  mov     rax, [r14]
0x1800b7d8a  lea     rdx, aGfxpipelineAvc_0; "GfxPipeline::AVCMixedModePreferred"
0x1800b7d91  mov     r8, rsi
0x1800b7d94  mov     rcx, r14
0x1800b7d97  mov     rax, [rax+20h]
0x1800b7d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7da0  test    eax, eax
0x1800b7da2  jns     short loc_1800B7DA7
0x1800b7da4  mov     [rsi], r12d
0x1800b7da7  lea     rax, [rbp+100h+hKey]
0x1800b7dab  mov     r9d, 20019h; samDesired
0x1800b7db1  xor     r8d, r8d; ulOptions
0x1800b7db4  mov     [rsp+200h+phkResult], rax; phkResult
0x1800b7db9  lea     rdx, aSoftwareWow643; "SOFTWARE\\WOW6432Node\\Google\\Chrome\\"...
0x1800b7dc0  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800b7dc7  call    cs:__imp_RegOpenKeyExW
0x1800b7dcd  mov     r13d, 1
0x1800b7dd3  test    eax, eax
0x1800b7dd5  jnz     loc_1800B7EEF
0x1800b7ddb  mov     r15d, r13d
0x1800b7dde  cmp     [rsi], r12d
0x1800b7de1  jz      loc_1800B7EEF
0x1800b7de7  mov     rcx, [rsp+200h+var_1A0]
0x1800b7dec  lea     r8, [rsp+200h+var_194]
0x1800b7df1  lea     rdx, aWvdEnablemmrhi; "WVD::EnableMMRHint"
0x1800b7df8  mov     ebx, r12d
0x1800b7dfb  mov     rax, [rcx]
0x1800b7dfe  mov     rax, [rax+20h]
0x1800b7e02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7e07  test    eax, eax
0x1800b7e09  jns     short loc_1800B7E10
0x1800b7e0b  mov     [rsp+200h+var_194], r12d
0x1800b7e10  xor     edx, edx; Val
0x1800b7e12  lea     rcx, [rbp+100h+VersionInformation.dwMajorVersion]; void *
0x1800b7e16  mov     r8d, 118h; Size
0x1800b7e1c  call    memset_0
0x1800b7e21  lea     rcx, [rbp+100h+VersionInformation]; lpVersionInformation
0x1800b7e25  mov     [rbp+100h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800b7e2c  call    cs:__imp_GetVersionExW
0x1800b7e32  test    eax, eax
0x1800b7e34  jz      short loc_1800B7E41
0x1800b7e36  cmp     [rbp+100h+VersionInformation.dwBuildNumber], 55F0h
0x1800b7e3d  cmovnb  ebx, r13d
0x1800b7e41  mov     rcx, [rsp+200h+var_1A0]
0x1800b7e46  lea     r8, [rsp+200h+var_198]
0x1800b7e4b  lea     rdx, aWvdRdrstackver; "WVD::RDRStackVersionWithMMRHint"
0x1800b7e52  mov     rax, [rcx]
0x1800b7e55  mov     rax, [rax+20h]
0x1800b7e59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7e5e  test    eax, eax
0x1800b7e60  jns     short loc_1800B7E6B
0x1800b7e62  mov     eax, r12d
0x1800b7e65  mov     [rsp+200h+var_198], eax
0x1800b7e69  jmp     short loc_1800B7E6F
0x1800b7e6b  mov     eax, [rsp+200h+var_198]
0x1800b7e6f  cmp     [rsp+200h+var_194], r12d
0x1800b7e74  jz      short loc_1800B7E81
0x1800b7e76  test    eax, eax
0x1800b7e78  jz      short loc_1800B7E81
0x1800b7e7a  mov     eax, r13d
0x1800b7e7d  test    ebx, ebx
0x1800b7e7f  jnz     short loc_1800B7E84
0x1800b7e81  mov     eax, r12d
0x1800b7e84  mov     [rsi], eax
0x1800b7e86  mov     eax, cs:CallbackContext
0x1800b7e8c  cmp     eax, 4
0x1800b7e8f  jbe     short loc_1800B7EEF
0x1800b7e91  mov     eax, [rsp+200h+var_198]
0x1800b7e95  lea     rdx, byte_18027EF93
0x1800b7e9c  mov     dword ptr [rbp+100h+var_178], eax
0x1800b7e9f  mov     eax, [rsp+200h+var_194]
0x1800b7ea3  mov     dword ptr [rbp+100h+var_180], eax
0x1800b7ea6  mov     eax, [rsi]
0x1800b7ea8  mov     [rsp+200h+var_1A8], eax
0x1800b7eac  lea     rax, aMmrHostIsInsta; "MMR host is installed"
0x1800b7eb3  mov     [rbp+100h+var_170], rax
0x1800b7eb7  lea     rax, [rsp+200h+var_1B0]
0x1800b7ebc  mov     [rsp+200h+var_1C0], rax
0x1800b7ec1  lea     rax, [rbp+100h+var_178]
0x1800b7ec5  mov     [rsp+200h+var_1C8], rax
0x1800b7eca  lea     rax, [rbp+100h+var_180]
0x1800b7ece  mov     [rsp+200h+var_1D0], rax
0x1800b7ed3  lea     rax, [rsp+200h+var_1A8]
0x1800b7ed8  mov     [rsp+200h+var_1D8], rax
0x1800b7edd  lea     rax, [rbp+100h+var_170]
0x1800b7ee1  mov     [rsp+200h+phkResult], rax
0x1800b7ee6  mov     [rsp+200h+var_1B0], ebx
0x1800b7eea  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U2@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@444@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b7eef  mov     rcx, [rbp+100h+hKey]; hKey
0x1800b7ef3  test    rcx, rcx
0x1800b7ef6  jz      short loc_1800B7EFE
0x1800b7ef8  call    cs:__imp_RegCloseKey
0x1800b7efe  mov     eax, cs:CallbackContext
0x1800b7f04  cmp     eax, 4
0x1800b7f07  jbe     loc_1800B7FAB
0x1800b7f0d  mov     rdx, 470000000000h
0x1800b7f17  lea     rcx, CallbackContext
0x1800b7f1e  call    _tlgKeywordOn
0x1800b7f23  test    al, al
0x1800b7f25  jz      loc_1800B7FAB
0x1800b7f2b  lea     rax, [rdi+148h]
0x1800b7f32  mov     [rsp+200h+var_1A8], r15d
0x1800b7f37  mov     [rbp+100h+var_170], rax
0x1800b7f3b  lea     rdx, unk_18027EF20
0x1800b7f42  lea     rax, aProfilemgr; "ProfileMgr"
0x1800b7f49  mov     qword ptr [rsp+200h+var_1B0], 1000000h
0x1800b7f52  mov     [rbp+100h+var_180], rax
0x1800b7f56  lea     rax, aStack; "Stack"
0x1800b7f5d  mov     [rbp+100h+var_178], rax
0x1800b7f61  lea     rax, aCheckpoint; "Checkpoint"
0x1800b7f68  mov     qword ptr [rsp+200h+var_190], rax
0x1800b7f6d  lea     rax, [rsp+200h+var_1A8]
0x1800b7f72  mov     [rsp+200h+var_1B8], rax
0x1800b7f77  lea     rax, [rbp+100h+var_170]
0x1800b7f7b  mov     [rsp+200h+var_1C0], rax
0x1800b7f80  lea     rax, [rbp+100h+var_180]
0x1800b7f84  mov     [rsp+200h+var_1C8], rax
0x1800b7f89  lea     rax, [rbp+100h+var_178]
0x1800b7f8d  mov     [rsp+200h+var_1D0], rax
0x1800b7f92  lea     rax, [rsp+200h+var_1B0]
0x1800b7f97  mov     [rsp+200h+var_1D8], rax
0x1800b7f9c  lea     rax, [rsp+200h+var_190]
0x1800b7fa1  mov     [rsp+200h+phkResult], rax
0x1800b7fa6  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$07@@U1@U1@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$07@@33AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<8> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<4> const &)
0x1800b7fab  mov     rcx, [rsp+200h+var_1A0]
0x1800b7fb0  lea     rbx, [rdi+130h]
0x1800b7fb7  mov     r8, rbx
0x1800b7fba  lea     rdx, aWvdEnableavcmm_1; "WVD::EnableAVCMMRail"
0x1800b7fc1  mov     rax, [rcx]
0x1800b7fc4  mov     rax, [rax+20h]
0x1800b7fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b7fcd  test    eax, eax
0x1800b7fcf  jns     short loc_1800B7FD4
0x1800b7fd1  mov     [rbx], r12d
0x1800b7fd4  mov     eax, cs:CallbackContext
0x1800b7fda  cmp     eax, 4
0x1800b7fdd  jbe     short loc_1800B801F
0x1800b7fdf  mov     eax, [rbx]
0x1800b7fe1  lea     rdx, unk_18027EED0
0x1800b7fe8  mov     [rsp+200h+var_1A8], eax
0x1800b7fec  mov     eax, [rsi]
0x1800b7fee  mov     dword ptr [rbp+100h+var_180], eax
0x1800b7ff1  lea     rax, aAvcMixedModeSe; "AVC Mixed Mode settings:"
0x1800b7ff8  mov     qword ptr [rsp+200h+var_190], rax
0x1800b7ffd  lea     rax, [rsp+200h+var_1A8]
0x1800b8002  mov     [rsp+200h+var_1D0], rax
0x1800b8007  lea     rax, [rbp+100h+var_180]
0x1800b800b  mov     [rsp+200h+var_1D8], rax
0x1800b8010  lea     rax, [rsp+200h+var_190]
0x1800b8015  mov     [rsp+200h+phkResult], rax; int
0x1800b801a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x1800b801f  mov     r8, [rsp+200h+var_1A0]; struct IRDPCollection *
0x1800b8024  mov     rdx, r14; struct IRDPCollection *
0x1800b8027  mov     rcx, rdi; this
0x1800b802a  call    ?SetConnectionProperties@ProfileManager@@AEAAJPEAUIRDPCollection@@0@Z; ProfileManager::SetConnectionProperties(IRDPCollection *,IRDPCollection *)
0x1800b802f  mov     ebx, eax
0x1800b8031  test    eax, eax
0x1800b8033  jns     short loc_1800B8092
0x1800b8035  mov     r9d, eax; unsigned int
0x1800b8038  lea     rdx, aProfilemanager_20; "ProfileManagerError_InitializeSetConnec"...
0x1800b803f  mov     r8d, 11Bh; char *
0x1800b8045  lea     rcx, aIidIrdpprofile; "IID_IRdpProfileManager"
0x1800b804c  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800b8051  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b8058  lea     rax, WPP_GLOBAL_Control
0x1800b805f  cmp     rcx, rax
0x1800b8062  jz      loc_1800B84BB
0x1800b8068  test    byte ptr [rcx+1Ch], 8
0x1800b806c  jz      loc_1800B84BB
0x1800b8072  cmp     byte ptr [rcx+19h], 2
0x1800b8076  jb      loc_1800B84BB
0x1800b807c  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x1800b8081  mov     edx, 10h
0x1800b8086  lea     rcx, aFailedToSetThe_1; "Failed to set the connection properties"
0x1800b808d  jmp     loc_1800B7C90
0x1800b8092  movdqa  xmm0, cs:__xmm@00000001000000010000000100000001
0x1800b809a  lea     r8, [rsp+200h+var_1B0]; int *
0x1800b809f  movups  xmmword ptr [rdi+88h], xmm0
0x1800b80a6  mov     edx, r13d; int
0x1800b80a9  lea     rcx, aVideodetection; "VideoDetectionEnabled"
0x1800b80b0  movups  xmmword ptr [rdi+98h], xmm0
0x1800b80b7  mov     [rsp+200h+var_1B0], r12d
0x1800b80bc  movq    qword ptr [rdi+0A8h], xmm0
0x1800b80c5  movups  xmmword ptr [rdi+0B0h], xmm0
  ... truncated ...
```
