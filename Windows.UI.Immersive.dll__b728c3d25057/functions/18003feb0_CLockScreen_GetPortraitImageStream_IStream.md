# CLockScreen::GetPortraitImageStream(IStream * *)

- ea: `0x18003feb0`
- end: `0x1800405c0`
- name: `?GetPortraitImageStream@CLockScreen@@UEAAJPEAPEAUIStream@@@Z`
- size: `1808`
- prototype: `__int64 __fastcall(CLockScreen *__hidden this, struct IStream **)`
- caller_count: `0`
- callee_count: `32`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x180009f0c`
- `0x18000a910`
- `0x18000b0d4`
- `0x18000bb20`
- `0x18000bd60`
- `0x180013244`
- `0x180023fb0`
- `0x180032a8c`
- `0x18003395c`
- `0x180034db4`
- `0x180039c30`
- `0x18003a5bc`
- `0x18003d6a4`
- `0x18003d858`
- `0x18003fe54`
- `0x18003feb0`
- `0x1800405c8`
- `0x1800405f4`
- `0x180040628`
- `0x1800406ec`
- `0x1800436a8`
- `0x180044054`
- `0x180045dc4`
- `0x180046c24`
- `0x180049de8`
- `0x180050ba0`
- `0x180051524`
- `0x1800ac428`
- `0x1800b2440`
- `0x1800b5e8c`
- `0x1800d4f30`
- `0x1800e5010`

## import_xrefs

- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180040003`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800401da`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800403df`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x180040003`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800401da`
- `api-ms-win-shcore-stream-l1-1-0!SHCreateStreamOnFileEx` at `0x1800403df`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x1800400ac`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x18004028e`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x180040485`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x1800400ac`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x18004028e`
- `SHCORE!__imp_SHCreateReadOnlySharedMemoryStream` at `0x180040485`

## string_xrefs

- `0x180040370`: `PortraitAssetPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall CLockScreen::GetPortraitImageStream(void **this, struct IStream **a2)
{
  bool v4; // dl
  unsigned int v5; // ebx
  int v6; // eax
  const WCHAR *v7; // rbx
  __int64 v8; // r9
  __int64 v9; // rdx
  HRESULT OnlySharedMemoryStream; // eax
  __int64 v11; // rdx
  wil::details::in1diag3 *v12; // rcx
  int v13; // eax
  int Stream; // eax
  __int64 v15; // rdx
  const WCHAR *v16; // rbx
  HRESULT v17; // eax
  __int64 v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  char v20; // r14
  int v21; // r9d
  int v22; // eax
  HRESULT v23; // eax
  __int64 v24; // rdx
  wil::details::in1diag3 *v25; // rcx
  int v26; // eax
  unsigned __int16 HistoryEntryAt; // ax
  int v28; // eax
  unsigned int v29; // eax
  __int64 v30; // rdx
  int pstmTemplate; // [rsp+20h] [rbp-E0h]
  int pstmTemplatea; // [rsp+20h] [rbp-E0h]
  int pstmTemplateb; // [rsp+20h] [rbp-E0h]
  int pstmTemplatec; // [rsp+20h] [rbp-E0h]
  int pstmTemplated; // [rsp+20h] [rbp-E0h]
  unsigned int *ppstm; // [rsp+28h] [rbp-D8h]
  LPCWSTR pszFile; // [rsp+30h] [rbp-D0h] BYREF
  _BYTE v39[16]; // [rsp+38h] [rbp-C8h] BYREF
  LPCWSTR v40; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v41; // [rsp+50h] [rbp-B0h]
  __int64 v42; // [rsp+58h] [rbp-A8h]
  IStream *v43; // [rsp+60h] [rbp-A0h] BYREF
  IStream *v44; // [rsp+68h] [rbp-98h] BYREF
  IStream *v45[2]; // [rsp+70h] [rbp-90h] BYREF
  _BYTE v46[16]; // [rsp+80h] [rbp-80h] BYREF
  unsigned int v47; // [rsp+90h] [rbp-70h]
  int v48; // [rsp+94h] [rbp-6Ch]
  _BYTE v49[16]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v50; // [rsp+E0h] [rbp-20h]
  int v51; // [rsp+E4h] [rbp-1Ch]
  _BYTE v52[16]; // [rsp+120h] [rbp+20h] BYREF
  unsigned int v53; // [rsp+130h] [rbp+30h]
  int v54; // [rsp+134h] [rbp+34h]
  _QWORD v55[42]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v56[1664]; // [rsp+2C0h] [rbp+1C0h] BYREF
  _WORD v57[832]; // [rsp+940h] [rbp+840h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+FF8h] [rbp+EF8h]

  wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v55);
  v55[0] = &LockScreenTelemetry::GetPortraitImageStreamActivity::`vftable';
  LockScreenTelemetry::GetPortraitImageStreamActivity::StartActivity((LockScreenTelemetry::GetPortraitImageStreamActivity *)v55);
  if ( !CLockScreen::s_IsSystemProcess() )
  {
    CLockScreenHistory::CSynchronizedOperation::CSynchronizedOperation(
      (CLockScreenHistory::CSynchronizedOperation *)v39,
      v4);
    *a2 = 0;
    if ( CLockScreen::_s_IsAppContainerProcess() )
    {
      v6 = CheckCallerCapabilityAndReportError(WinCapabilityPicturesLibrarySid, 0x9805u);
      v5 = v6;
      if ( v6 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x15F5,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v6,
          pstmTemplate);
LABEL_75:
        CLockScreenHistory::CSynchronizedOperation::~CSynchronizedOperation((CLockScreenHistory::CSynchronizedOperation *)v39);
        goto LABEL_76;
      }
    }
    pszFile = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &pszFile,
      0);
    if ( CLockScreen::_s_IsSpecificLockScreenLogonImageForced((unsigned __int16 **)&pszFile) )
    {
      v7 = pszFile;
      if ( !pszFile )
      {
        v5 = -2147467261;
        v8 = 2147500035LL;
        v9 = 5633;
LABEL_9:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)v8,
          pstmTemplate);
LABEL_74:
        wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::~unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>(&pszFile);
        goto LABEL_75;
      }
      v43 = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
      OnlySharedMemoryStream = SHCreateStreamOnFileEx(v7, 0, 0x80u, 0, 0, &v43);
      v5 = OnlySharedMemoryStream;
      if ( OnlySharedMemoryStream < 0 )
      {
        v11 = 5635;
LABEL_12:
        v12 = retaddr;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          v12,
          (void *)v11,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)OnlySharedMemoryStream,
          pstmTemplatea);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
        goto LABEL_74;
      }
      memset_0(v46, 0, 0x50u);
      OnlySharedMemoryStream = (*(__int64 (__fastcall **)(IStream *, _BYTE *, __int64))(*(_QWORD *)v43 + 96LL))(
                                 v43,
                                 v46,
                                 1);
      v5 = OnlySharedMemoryStream;
      v12 = retaddr;
      if ( OnlySharedMemoryStream < 0 )
      {
        v11 = 5638;
        goto LABEL_13;
      }
      if ( v48 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1607,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)0x8000FFFFLL,
          pstmTemplatea);
      OnlySharedMemoryStream = SHCreateReadOnlySharedMemoryStream(
                                 v43,
                                 v47,
                                 &GUID_0000000c_0000_0000_c000_000000000046,
                                 a2);
      v5 = OnlySharedMemoryStream;
      if ( OnlySharedMemoryStream < 0 )
      {
        v11 = 5641;
        goto LABEL_12;
      }
      wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v55, 0);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v43);
LABEL_47:
      v5 = 0;
      goto LABEL_74;
    }
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(`wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl'::`2'::impl);
    if ( CLockScreen::_s_IsSpotlightEnabled(0) )
    {
      v40 = 0;
      v41 = 0;
      v42 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
      v41 = -1;
      v42 = -1;
      v13 = CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(
              0,
              0,
              0,
              (unsigned __int16 **)&v40,
              0);
      if ( v13 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x160F,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v13,
          pstmTemplateb);
LABEL_24:
        CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v56);
        Stream = CLockScreenHistory::_EnsureCurrentUserSid((CLockScreenHistory *)(this + 13));
        v5 = Stream;
        if ( Stream < 0 )
        {
          v15 = 5668;
LABEL_26:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v15,
            (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
            (const char *)(unsigned int)Stream,
            pstmTemplateb);
          CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v56);
LABEL_33:
          Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
          goto LABEL_74;
        }
        Stream = CLockScreenHistory::_InitAndEnsureGPEntry(
                   (CLockScreenHistory *)(this + 13),
                   (struct CLockScreenHistory::CLockScreenHistoryEntry *)v56,
                   0x5Au);
        v5 = Stream;
        if ( Stream < 0 )
        {
          v15 = 5669;
          goto LABEL_26;
        }
        Stream = CLockScreenHistory::CLockScreenHistoryEntry::GetStream(
                   (CLockScreenHistory::CLockScreenHistoryEntry *)v56,
                   1,
                   a2);
        v5 = Stream;
        if ( Stream < 0 )
        {
          v15 = 5670;
          goto LABEL_26;
        }
        CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v56);
LABEL_46:
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
        goto LABEL_47;
      }
      v16 = v40;
      if ( !v40 || !*v40 )
        goto LABEL_24;
      v44 = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
      v17 = SHCreateStreamOnFileEx(v16, 0, 0x80u, 0, 0, &v44);
      v5 = v17;
      if ( v17 >= 0 )
      {
        memset_0(v49, 0, 0x50u);
        v17 = (*(__int64 (__fastcall **)(IStream *, _BYTE *, __int64))(*(_QWORD *)v44 + 96LL))(v44, v49, 1);
        v5 = v17;
        v19 = retaddr;
        if ( v17 < 0 )
        {
          v18 = 5658;
          goto LABEL_32;
        }
        if ( v51 )
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x161B,
            (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
            (const char *)0x8000FFFFLL,
            pstmTemplatec);
        v17 = SHCreateReadOnlySharedMemoryStream(v44, v50, &GUID_0000000c_0000_0000_c000_000000000046, a2);
        v5 = v17;
        if ( v17 >= 0 )
        {
          wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v55, 0);
          Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
          goto LABEL_46;
        }
        v18 = 5661;
      }
      else
      {
        v18 = 5651;
      }
      v19 = retaddr;
LABEL_32:
      wil::details::in1diag3::Return_Hr(
        v19,
        (void *)v18,
        (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
        (const char *)(unsigned int)v17,
        pstmTemplatec);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(&v44);
      goto LABEL_33;
    }
    v20 = 0;
    if ( CLockScreen::_s_IsSpotlight() && !CLockScreen::_s_IsSpotlightExpired() )
    {
      v40 = 0;
      v41 = 0;
      v42 = 0;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
      v41 = -1;
      v42 = -1;
      v22 = SHRegAllocData(
              HKEY_CURRENT_USER,
              L"Software\\Microsoft\\Windows\\CurrentVersion\\Lock Screen\\Creative",
              L"PortraitAssetPath",
              v21,
              (void **)&v40,
              ppstm);
      v5 = v22;
      if ( v22 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x162E,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v22,
          pstmTemplated);
        goto LABEL_33;
      }
      v45[0] = 0;
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v45);
      v23 = SHCreateStreamOnFileEx(v40, 0, 0x80u, 0, 0, v45);
      v5 = v23;
      if ( v23 < 0 )
      {
        v24 = 5681;
LABEL_54:
        v25 = retaddr;
LABEL_55:
        wil::details::in1diag3::Return_Hr(
          v25,
          (void *)v24,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v23,
          pstmTemplate);
        Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v45);
        goto LABEL_33;
      }
      memset_0(v52, 0, 0x50u);
      v23 = (*(__int64 (__fastcall **)(IStream *, _BYTE *, __int64))(*(_QWORD *)v45[0] + 96LL))(v45[0], v52, 1);
      v5 = v23;
      v25 = retaddr;
      if ( v23 < 0 )
      {
        v24 = 5688;
        goto LABEL_55;
      }
      if ( v54 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x1639,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)0x8000FFFFLL,
          pstmTemplate);
      v23 = SHCreateReadOnlySharedMemoryStream(v45[0], v53, &GUID_0000000c_0000_0000_c000_000000000046, a2);
      v5 = v23;
      if ( v23 < 0 )
      {
        v24 = 5691;
        goto LABEL_54;
      }
      v20 = 1;
      wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v55, 0);
      Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(v45);
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v40);
    }
    v5 = 0;
    if ( v20 )
      goto LABEL_74;
    v26 = CLockScreenHistory::_EnsureCurrentUserSid((CLockScreenHistory *)(this + 13));
    v5 = v26;
    if ( v26 >= 0 )
    {
      CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v57);
      HistoryEntryAt = CLockScreenHistory::s_GetHistoryEntryAt(0, this[13]);
      v28 = CLockScreenHistory::_InitAndEnsureGPEntry(
              (CLockScreenHistory *)(this + 13),
              (struct CLockScreenHistory::CLockScreenHistoryEntry *)v57,
              HistoryEntryAt);
      v5 = v28;
      if ( v28 >= 0 )
      {
        v29 = CLockScreenHistory::CLockScreenHistoryEntry::GetStream(
                (CLockScreenHistory::CLockScreenHistoryEntry *)v57,
                1,
                a2);
        v5 = v29;
        if ( v29 != -2147024894 || v57[0] == 79 )
          v30 = v29;
        else
          v30 = 0;
        wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v55, v30);
      }
      else
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x1644,
          (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
          (const char *)(unsigned int)v28,
          pstmTemplate);
      }
      CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry((CLockScreenHistory::CLockScreenHistoryEntry *)v57);
      goto LABEL_74;
    }
    v8 = (unsigned int)v26;
    v9 = 5697;
    goto LABEL_9;
  }
  v5 = -2147418113;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x15ED,
    (unsigned int)"shell\\windowsuiimmersive\\userinfo\\lockscreen.cpp",
    (const char *)0x8000FFFFLL,
    pstmTemplate);
LABEL_76:
  LockScreenTelemetry::GetPortraitImageStreamActivity::~GetPortraitImageStreamActivity((LockScreenTelemetry::GetPortraitImageStreamActivity *)v55);
  return v5;
}

```

## disassembly

```asm
0x18003feb0  mov     [rsp-8+arg_10], rbx
0x18003feb5  push    rbp
0x18003feb6  push    rsi
0x18003feb7  push    r12
0x18003feb9  push    r14
0x18003febb  push    r15
0x18003febd  lea     rbp, [rsp-0ED0h]
0x18003fec5  sub     rsp, 0FD0h
0x18003fecc  mov     rax, cs:__security_cookie
0x18003fed3  xor     rax, rsp
0x18003fed6  mov     [rbp+0EF0h+var_30], rax
0x18003fedd  mov     rsi, rdx
0x18003fee0  mov     r15, rcx
0x18003fee3  lea     rdx, aGetportraitima; "GetPortraitImageStreamActivity"
0x18003feea  lea     rcx, [rbp+0EF0h+var_E80]; struct wil::details::IFailureCallback *
0x18003feee  call    ??0?$ActivityBase@VLockScreenLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003fef3  lea     rax, ??_7GetPortraitImageStreamActivity@LockScreenTelemetry@@6B@; const LockScreenTelemetry::GetPortraitImageStreamActivity::`vftable'
0x18003fefa  mov     [rbp+0EF0h+var_E80], rax
0x18003fefe  lea     rcx, [rbp+0EF0h+var_E80]; this
0x18003ff02  call    ?StartActivity@GetPortraitImageStreamActivity@LockScreenTelemetry@@QEAAXXZ; LockScreenTelemetry::GetPortraitImageStreamActivity::StartActivity(void)
0x18003ff07  nop
0x18003ff08  call    ?s_IsSystemProcess@CLockScreen@@SA_NXZ; CLockScreen::s_IsSystemProcess(void)
0x18003ff0d  xor     r12d, r12d
0x18003ff10  test    al, al
0x18003ff12  jz      short loc_18003FF39
0x18003ff14  mov     rcx, [rbp+0EF8h]; this
0x18003ff1b  mov     ebx, 8000FFFFh
0x18003ff20  mov     r9d, ebx; char *
0x18003ff23  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18003ff2a  mov     edx, 15EDh; void *
0x18003ff2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ff34  jmp     loc_18004058E
0x18003ff39  lea     rcx, [rsp+0FF0h+var_FB8]; this
0x18003ff3e  call    ??0CSynchronizedOperation@CLockScreenHistory@@QEAA@_N@Z; CLockScreenHistory::CSynchronizedOperation::CSynchronizedOperation(bool)
0x18003ff43  nop
0x18003ff44  mov     [rsi], r12
0x18003ff47  call    ?_s_IsAppContainerProcess@CLockScreen@@KA_NXZ; CLockScreen::_s_IsAppContainerProcess(void)
0x18003ff4c  test    al, al
0x18003ff4e  jz      short loc_18003FF85
0x18003ff50  mov     edx, 9805h; unsigned int
0x18003ff55  mov     ecx, 58h ; 'X'; enum WELL_KNOWN_SID_TYPE
0x18003ff5a  call    ?CheckCallerCapabilityAndReportError@@YAJW4WELL_KNOWN_SID_TYPE@@IZZ; CheckCallerCapabilityAndReportError(WELL_KNOWN_SID_TYPE,uint,...)
0x18003ff5f  mov     ebx, eax
0x18003ff61  test    eax, eax
0x18003ff63  jns     short loc_18003FF85
0x18003ff65  mov     rcx, [rbp+0EF8h]; this
0x18003ff6c  mov     r9d, eax; char *
0x18003ff6f  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18003ff76  mov     edx, 15F5h; void *
0x18003ff7b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ff80  jmp     loc_180040583
0x18003ff85  mov     [rsp+0FF0h+pszFile], r12
0x18003ff8a  xor     edx, edx
0x18003ff8c  lea     rcx, [rsp+0FF0h+pszFile]
0x18003ff91  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003ff96  lea     rcx, [rsp+0FF0h+pszFile]; unsigned __int16 **
0x18003ff9b  call    ?_s_IsSpecificLockScreenLogonImageForced@CLockScreen@@KA_NPEAPEAG@Z; CLockScreen::_s_IsSpecificLockScreenLogonImageForced(ushort * *)
0x18003ffa0  test    al, al
0x18003ffa2  jz      loc_1800400DD
0x18003ffa8  mov     rbx, [rsp+0FF0h+pszFile]
0x18003ffad  test    rbx, rbx
0x18003ffb0  jnz     short loc_18003FFD7
0x18003ffb2  mov     ebx, 80004003h
0x18003ffb7  mov     r9d, ebx; char *
0x18003ffba  mov     edx, 1601h; void *
0x18003ffbf  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18003ffc6  mov     rcx, [rbp+0EF8h]; this
0x18003ffcd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ffd2  jmp     loc_180040578
0x18003ffd7  mov     [rsp+0FF0h+var_F90], r12
0x18003ffdc  lea     rcx, [rsp+0FF0h+var_F90]
0x18003ffe1  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18003ffe6  lea     rax, [rsp+0FF0h+var_F90]
0x18003ffeb  mov     [rsp+0FF0h+ppstm], rax; ppstm
0x18003fff0  mov     [rsp+0FF0h+pstmTemplate], r12; int
0x18003fff5  xor     r9d, r9d; fCreate
0x18003fff8  xor     edx, edx; grfMode
0x18003fffa  mov     r8d, 80h; dwAttributes
0x180040000  mov     rcx, rbx; pszFile
0x180040003  call    cs:__imp_SHCreateStreamOnFileEx
0x180040009  mov     ebx, eax
0x18004000b  test    eax, eax
0x18004000d  jns     short loc_18004003A
0x18004000f  mov     edx, 1603h; void *
0x180040014  mov     rcx, [rbp+0EF8h]; this
0x18004001b  mov     r9d, eax; char *
0x18004001e  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180040025  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004002a  nop
0x18004002b  lea     rcx, [rsp+0FF0h+var_F90]
0x180040030  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x180040035  jmp     loc_180040578
0x18004003a  xor     edx, edx; Val
0x18004003c  lea     r8d, [rdx+50h]; Size
0x180040040  lea     rcx, [rbp+0EF0h+var_F70]; void *
0x180040044  call    memset_0
0x180040049  mov     rcx, [rsp+0FF0h+var_F90]
0x18004004e  mov     rax, [rcx]
0x180040051  mov     r8d, 1
0x180040057  lea     rdx, [rbp+0EF0h+var_F70]
0x18004005b  mov     rax, [rax+60h]
0x18004005f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040064  mov     ebx, eax
0x180040066  mov     rcx, [rbp+0EF8h]; this
0x18004006d  test    eax, eax
0x18004006f  jns     short loc_180040078
0x180040071  mov     edx, 1606h
0x180040076  jmp     short loc_18004001B
0x180040078  cmp     [rbp+0EF0h+var_F5C], r12d
0x18004007c  setz    al
0x18004007f  test    al, al
0x180040081  jnz     short loc_18004009A
0x180040083  mov     r9d, 8000FFFFh; char *
0x180040089  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180040090  mov     edx, 1607h; void *
0x180040095  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004009a  mov     r9, rsi
0x18004009d  lea     r8, _GUID_0000000c_0000_0000_c000_000000000046
0x1800400a4  mov     edx, [rbp+0EF0h+var_F60]
0x1800400a7  mov     rcx, [rsp+0FF0h+var_F90]
0x1800400ac  call    cs:__imp_SHCreateReadOnlySharedMemoryStream
0x1800400b2  mov     ebx, eax
0x1800400b4  test    eax, eax
0x1800400b6  jns     short loc_1800400C2
0x1800400b8  mov     edx, 1609h
0x1800400bd  jmp     loc_180040014
0x1800400c2  xor     edx, edx
0x1800400c4  lea     rcx, [rbp+0EF0h+var_E80]
0x1800400c8  call    ?Stop@?$ActivityBase@VLockScreenLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800400cd  nop
0x1800400ce  lea     rcx, [rsp+0FF0h+var_F90]
0x1800400d3  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800400d8  jmp     loc_18004031A
0x1800400dd  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3> `wil::Feature<__WilFeatureTraits_Feature_WindowsSpotlightV3>::GetImpl(void)'::`2'::impl
0x1800400e4  call    ?__private_IsEnabledPreCheck@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsSpotlightV3@@@details@wil@@QEAA_NW4ReportingKind@3@@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsSpotlightV3>::__private_IsEnabledPreCheck(wil::ReportingKind)
0x1800400e9  xor     ecx, ecx; this
0x1800400eb  call    ?_s_IsSpotlightEnabled@CLockScreen@@KA_NPEBG@Z; CLockScreen::_s_IsSpotlightEnabled(ushort const *)
0x1800400f0  test    al, al
0x1800400f2  jz      loc_180040322
0x1800400f8  mov     [rsp+0FF0h+var_FA8], r12
0x1800400fd  mov     [rsp+0FF0h+var_FA0], r12
0x180040102  mov     [rsp+0FF0h+var_F98], r12
0x180040107  lea     rcx, [rsp+0FF0h+var_FA8]
0x18004010c  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180040111  or      rax, 0FFFFFFFFFFFFFFFFh
0x180040115  mov     [rsp+0FF0h+var_FA0], rax
0x18004011a  mov     [rsp+0FF0h+var_F98], rax
0x18004011f  mov     [rsp+0FF0h+pstmTemplate], r12; int
0x180040124  lea     r9, [rsp+0FF0h+var_FA8]; unsigned __int16 **
0x180040129  xor     r8d, r8d; unsigned __int16 **
0x18004012c  xor     edx, edx; unsigned __int16 *
0x18004012e  xor     ecx, ecx; this
0x180040130  call    ?PeekLockScreenRegistryKeys@LockScreenCreativeConfigHelpers@CreativeFramework@@YAJPEBGPEAPEAG11PEA_N@Z; CreativeFramework::LockScreenCreativeConfigHelpers::PeekLockScreenRegistryKeys(ushort const *,ushort * *,ushort * *,ushort * *,bool *)
0x180040135  mov     rcx, [rbp+0EF8h]; this
0x18004013c  test    eax, eax
0x18004013e  jns     short loc_18004019E
0x180040140  mov     r9d, eax; char *
0x180040143  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18004014a  mov     edx, 160Fh; void *
0x18004014f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180040154  lea     rcx, [rbp+0EF0h+var_D30]; this
0x18004015b  call    ??0CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::CLockScreenHistoryEntry(void)
0x180040160  nop
0x180040161  lea     rcx, [r15+68h]; this
0x180040165  call    ?_EnsureCurrentUserSid@CLockScreenHistory@@IEAAJXZ; CLockScreenHistory::_EnsureCurrentUserSid(void)
0x18004016a  mov     ebx, eax
0x18004016c  test    eax, eax
0x18004016e  jns     loc_1800402BC
0x180040174  mov     edx, 1624h; void *
0x180040179  mov     rcx, [rbp+0EF8h]; this
0x180040180  mov     r9d, eax; char *
0x180040183  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x18004018a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004018f  nop
0x180040190  lea     rcx, [rbp+0EF0h+var_D30]; this
0x180040197  call    ??1CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry(void)
0x18004019c  jmp     short loc_18004020D
0x18004019e  mov     rbx, [rsp+0FF0h+var_FA8]
0x1800401a3  test    rbx, rbx
0x1800401a6  jz      short loc_180040154
0x1800401a8  cmp     [rbx], r12w
0x1800401ac  jz      short loc_180040154
0x1800401ae  mov     [rsp+0FF0h+var_F88], r12
0x1800401b3  lea     rcx, [rsp+0FF0h+var_F88]
0x1800401b8  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800401bd  lea     rax, [rsp+0FF0h+var_F88]
0x1800401c2  mov     [rsp+0FF0h+ppstm], rax; ppstm
0x1800401c7  mov     [rsp+0FF0h+pstmTemplate], r12; int
0x1800401cc  xor     r9d, r9d; fCreate
0x1800401cf  xor     edx, edx; grfMode
0x1800401d1  mov     r8d, 80h; dwAttributes
0x1800401d7  mov     rcx, rbx; pszFile
0x1800401da  call    cs:__imp_SHCreateStreamOnFileEx
0x1800401e0  mov     ebx, eax
0x1800401e2  test    eax, eax
0x1800401e4  jns     short loc_18004021C
0x1800401e6  mov     edx, 1613h; void *
0x1800401eb  mov     rcx, [rbp+0EF8h]; this
0x1800401f2  mov     r9d, eax; char *
0x1800401f5  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x1800401fc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040201  nop
0x180040202  lea     rcx, [rsp+0FF0h+var_F88]
0x180040207  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x18004020c  nop
0x18004020d  lea     rcx, [rsp+0FF0h+var_FA8]
0x180040212  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180040217  jmp     loc_180040578
0x18004021c  xor     edx, edx; Val
0x18004021e  lea     r8d, [rdx+50h]; Size
0x180040222  lea     rcx, [rbp+0EF0h+var_F20]; void *
0x180040226  call    memset_0
0x18004022b  mov     rcx, [rsp+0FF0h+var_F88]
0x180040230  mov     rax, [rcx]
0x180040233  mov     r8d, 1
0x180040239  lea     rdx, [rbp+0EF0h+var_F20]
0x18004023d  mov     rax, [rax+60h]
0x180040241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180040246  mov     ebx, eax
0x180040248  mov     rcx, [rbp+0EF8h]; this
0x18004024f  test    eax, eax
0x180040251  jns     short loc_18004025A
0x180040253  mov     edx, 161Ah
0x180040258  jmp     short loc_1800401F2
0x18004025a  cmp     [rbp+0EF0h+var_F0C], r12d
0x18004025e  setz    al
0x180040261  test    al, al
0x180040263  jnz     short loc_18004027C
0x180040265  mov     r9d, 8000FFFFh; char *
0x18004026b  lea     r8, aShellWindowsui_13; "shell\\windowsuiimmersive\\userinfo\\lo"...
0x180040272  mov     edx, 161Bh; void *
0x180040277  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004027c  mov     r9, rsi
0x18004027f  lea     r8, _GUID_0000000c_0000_0000_c000_000000000046
0x180040286  mov     edx, [rbp+0EF0h+var_F10]
0x180040289  mov     rcx, [rsp+0FF0h+var_F88]
0x18004028e  call    cs:__imp_SHCreateReadOnlySharedMemoryStream
0x180040294  mov     ebx, eax
0x180040296  test    eax, eax
0x180040298  jns     short loc_1800402A4
0x18004029a  mov     edx, 161Dh
0x18004029f  jmp     loc_1800401EB
0x1800402a4  xor     edx, edx
0x1800402a6  lea     rcx, [rbp+0EF0h+var_E80]
0x1800402aa  call    ?Stop@?$ActivityBase@VLockScreenLogging@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<LockScreenLogging,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800402af  nop
0x1800402b0  lea     rcx, [rsp+0FF0h+var_F88]
0x1800402b5  call    ?InternalRelease@?$ComPtr@UIFrameTaskManager@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IFrameTaskManager>::InternalRelease(void)
0x1800402ba  jmp     short loc_180040310
0x1800402bc  mov     r8d, 5Ah ; 'Z'; unsigned __int16
0x1800402c2  lea     rdx, [rbp+0EF0h+var_D30]; struct CLockScreenHistory::CLockScreenHistoryEntry *
0x1800402c9  lea     rcx, [r15+68h]; this
0x1800402cd  call    ?_InitAndEnsureGPEntry@CLockScreenHistory@@IEAAJPEAVCLockScreenHistoryEntry@1@G@Z; CLockScreenHistory::_InitAndEnsureGPEntry(CLockScreenHistory::CLockScreenHistoryEntry *,ushort)
0x1800402d2  mov     ebx, eax
0x1800402d4  test    eax, eax
0x1800402d6  jns     short loc_1800402E2
0x1800402d8  mov     edx, 1625h
0x1800402dd  jmp     loc_180040179
0x1800402e2  mov     r8, rsi; struct IStream **
0x1800402e5  mov     dl, 1; bool
0x1800402e7  lea     rcx, [rbp+0EF0h+var_D30]; this
0x1800402ee  call    ?GetStream@CLockScreenHistoryEntry@CLockScreenHistory@@QEAAJ_NPEAPEAUIStream@@@Z; CLockScreenHistory::CLockScreenHistoryEntry::GetStream(bool,IStream * *)
0x1800402f3  mov     ebx, eax
0x1800402f5  test    eax, eax
0x1800402f7  jns     short loc_180040303
0x1800402f9  mov     edx, 1626h
0x1800402fe  jmp     loc_180040179
0x180040303  lea     rcx, [rbp+0EF0h+var_D30]; this
0x18004030a  call    ??1CLockScreenHistoryEntry@CLockScreenHistory@@QEAA@XZ; CLockScreenHistory::CLockScreenHistoryEntry::~CLockScreenHistoryEntry(void)
0x18004030f  nop
0x180040310  lea     rcx, [rsp+0FF0h+var_FA8]
0x180040315  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18004031a  mov     ebx, r12d
0x18004031d  jmp     loc_180040578
0x180040322  mov     r14b, r12b
0x180040325  call    ?_s_IsSpotlight@CLockScreen@@KA_NXZ; CLockScreen::_s_IsSpotlight(void)
0x18004032a  test    al, al
0x18004032c  jz      loc_1800404BF
0x180040332  call    ?_s_IsSpotlightExpired@CLockScreen@@KA_NXZ; CLockScreen::_s_IsSpotlightExpired(void)
0x180040337  test    al, al
0x180040339  jnz     loc_1800404BF
0x18004033f  mov     [rsp+0FF0h+var_FA8], r12
0x180040344  mov     [rsp+0FF0h+var_FA0], r12
0x180040349  mov     [rsp+0FF0h+var_F98], r12
0x18004034e  lea     rcx, [rsp+0FF0h+var_FA8]
0x180040353  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x180040358  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004035c  mov     [rsp+0FF0h+var_FA0], rax
0x180040361  mov     [rsp+0FF0h+var_F98], rax
0x180040366  lea     rax, [rsp+0FF0h+var_FA8]
0x18004036b  mov     [rsp+0FF0h+pstmTemplate], rax; int
0x180040370  lea     r8, ?c_portraitAssetPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "PortraitAssetPath"
0x180040377  lea     rdx, ?c_lockScreenCreativeKeyPath@LockScreenCreativeConfigHelpers@CreativeFramework@@3QBGB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18004037e  mov     rcx, 0FFFFFFFF80000001h; HKEY
0x180040385  call    ?SHRegAllocData@@YAJPEAUHKEY__@@PEBG1HPEAPEAXPEAK@Z; SHRegAllocData(HKEY__ *,ushort const *,ushort const *,int,void * *,ulong *)
0x18004038a  mov     ebx, eax
0x18004038c  test    eax, eax
0x18004038e  jns     short loc_1800403B1
0x180040390  mov     rcx, [rbp+0EF8h]; this
0x180040397  mov     r9d, eax; char *
  ... truncated ...
```
