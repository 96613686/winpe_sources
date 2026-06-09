# CPipeManager::LogGraphicsSettings(void)

- ea: `0x180097a08`
- end: `0x18009818a`
- name: `?LogGraphicsSettings@CPipeManager@@IEAAJXZ`
- size: `1922`
- prototype: `__int64 __fastcall(CPipeManager *__hidden this)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180094a60`

## callees

- `0x180001308`
- `0x18000202c`
- `0x18000ce04`
- `0x18002aafc`
- `0x18004f5bc`
- `0x180076090`
- `0x180077aa0`
- `0x180079770`
- `0x18007e9e0`
- `0x18007f348`
- `0x18007f42c`
- `0x180097a08`
- `0x1800b7520`
- `0x180158d34`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180097fe1`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x180097fe1`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180097eee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180097f7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180098049`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180097eee`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180097f7d`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x180098049`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098156`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180098156`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097eb1`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180097eb1`
- `OLEAUT32!__imp_VariantInit` at `0x180097a7a`
- `OLEAUT32!__imp_VariantInit` at `0x180097a84`
- `OLEAUT32!__imp_VariantInit` at `0x180097a7a`
- `OLEAUT32!__imp_VariantInit` at `0x180097a84`
- `OLEAUT32!__imp_VariantClear` at `0x18009813d`
- `OLEAUT32!__imp_VariantClear` at `0x180098147`
- `OLEAUT32!__imp_VariantClear` at `0x18009813d`
- `OLEAUT32!__imp_VariantClear` at `0x180098147`

## string_xrefs

- `0x180097ea3`: `Software\Policies\Microsoft\Windows NT\Terminal Services`
- `0x180097bb8`: `GetProperty RDP_PROPERTY_PROTOCOL_NAME failed`
- `0x180097e65`: `MaxCompressionLevel`
- `0x18009809e`: `MonitorConfig`

## pseudocode

```c
__int64 __fastcall CPipeManager::LogGraphicsSettings(CPipeManager *this)
{
  unsigned int v1; // r13d
  __int64 v3; // rbx
  unsigned int CurrentThreadActivityIdPrefix; // eax
  int v5; // edx
  const char *v6; // rcx
  DWORD v7; // edi
  int v8; // eax
  int v9; // ecx
  int v10; // r8d
  int v11; // r9d
  BOOL v12; // r14d
  int v13; // r15d
  __int64 v14; // rcx
  __int64 v15; // rcx
  int v16; // eax
  char v17; // r12
  unsigned int v18; // eax
  __int64 v19; // rcx
  int v20; // eax
  char v21; // r12
  unsigned int v22; // eax
  __int64 v23; // rcx
  int v24; // eax
  char v25; // r12
  unsigned int v26; // eax
  BOOL v27; // r12d
  int v28; // ecx
  int v29; // r8d
  int v30; // r9d
  BOOL v31; // edi
  int v32; // ecx
  int v33; // r8d
  int v34; // r9d
  int v35; // ecx
  int v36; // r8d
  int v37; // r9d
  LONG v38; // edx
  int v39; // ecx
  int v40; // r8d
  void (__fastcall *v41)(__int64, const unsigned __int16 *, _QWORD); // rdi
  const unsigned __int16 *ImageQualityName; // rax
  DWORD Type; // [rsp+60h] [rbp-A0h] BYREF
  DWORD cbData; // [rsp+64h] [rbp-9Ch] BYREF
  unsigned int v46; // [rsp+68h] [rbp-98h] BYREF
  BYTE Data[4]; // [rsp+6Ch] [rbp-94h] BYREF
  int v48; // [rsp+70h] [rbp-90h] BYREF
  unsigned int v49; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD lpcbData[2]; // [rsp+78h] [rbp-88h] BYREF
  HKEY hKey; // [rsp+80h] [rbp-80h] BYREF
  const char *v52; // [rsp+88h] [rbp-78h] BYREF
  int v53; // [rsp+90h] [rbp-70h] BYREF
  __int64 v54; // [rsp+98h] [rbp-68h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-60h] BYREF
  const char *v56; // [rsp+B8h] [rbp-48h] BYREF
  const char *v57; // [rsp+C0h] [rbp-40h] BYREF
  VARIANTARG v58; // [rsp+C8h] [rbp-38h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v60; // [rsp+1F8h] [rbp+F8h]

  v1 = 0;
  v49 = 0;
  v46 = 0;
  *(_DWORD *)Data = 0;
  v3 = 0;
  v48 = 0;
  v54 = 0;
  memset(&pvarg, 0, sizeof(pvarg));
  memset(&v58, 0, sizeof(v58));
  hKey = 0;
  v53 = 0;
  VariantInit(&pvarg);
  VariantInit(&v58);
  if ( !*((_QWORD *)this + 6114) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 256;
    v6 = "m_spGfxConnProperties";
LABEL_6:
    WPP_SF_Ds(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v5,
      (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
      CurrentThreadActivityIdPrefix,
      (__int64)v6);
LABEL_7:
    v7 = -2147467261;
    goto LABEL_73;
  }
  if ( !*((_QWORD *)this + 1627) )
  {
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_7;
    }
    CurrentThreadActivityIdPrefix = RdpWppGetCurrentThreadActivityIdPrefix();
    v5 = 257;
    v6 = "m_spRDPENCPlatform";
    goto LABEL_6;
  }
  *(_QWORD *)lpcbData = (char *)this + 48896;
  CTSCriticalSection::Lock((CPipeManager *)((char *)this + 48896));
  if ( *((_QWORD *)this + 1638) )
  {
    TCntPtr<IRdpVCMgr>::SafeRelease(&v54);
    v3 = *((_QWORD *)this + 1638);
    v54 = v3;
    if ( v3 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 8LL))(v3);
  }
  CTSAutoLock::~CTSAutoLock((CTSAutoLock *)lpcbData);
  v8 = (*(__int64 (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 1627) + 24LL))(
         *((_QWORD *)this + 1627),
         L"RDP::TerminalName",
         &pvarg);
  v7 = v8;
  if ( pvarg.vt != 8 )
  {
    v7 = -2147467259;
    goto LABEL_19;
  }
  if ( v8 < 0 )
  {
LABEL_19:
    if ( (unsigned int)CallbackContext > 2 )
    {
      cbData = 9939;
      *(_QWORD *)lpcbData = "GetProperty RDP_PROPERTY_PROTOCOL_NAME failed";
      Type = v7;
      v56 = "LogGraphicsSettings";
      v57 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\pipemanager.cpp";
      v52 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v9,
        (unsigned int)word_1802751A2,
        v10,
        v11,
        (__int64)&v52,
        (__int64)&Type,
        (__int64)&v57,
        (__int64)&cbData,
        (__int64)&v56,
        (__int64)lpcbData);
    }
    goto LABEL_73;
  }
  v12 = 1;
  if ( wcsicmp(pvarg.bstrVal, L"RDP-Tcp") )
  {
    if ( wcsicmp(pvarg.bstrVal, L"RDP-Cdv") )
    {
      if ( wcsicmp(pvarg.bstrVal, L"31C5CE94259D4006A9E4") && wcsicmp(pvarg.bstrVal, L"41C5CE94259D4006A9E4") )
      {
        v14 = *((_QWORD *)this + 1627);
        Type = 0;
        v13 = 0;
        if ( (*(int (__fastcall **)(__int64, const wchar_t *, DWORD *))(*(_QWORD *)v14 + 32LL))(
               v14,
               L"GfxPipeline::ForceRemoteFXProfile",
               &Type) >= 0
          && Type )
        {
          v13 = 4;
        }
      }
      else
      {
        v13 = 3;
      }
    }
    else
    {
      v13 = 2;
    }
  }
  else
  {
    v13 = 1;
  }
  v15 = *((_QWORD *)this + 6114);
  v48 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, int *))(*(_QWORD *)v15 + 40LL))(
          v15,
          L"GfxPipeline::ProfilePolicy",
          &v48);
  v17 = v16;
  if ( v16 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v18 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      259,
      (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
      v18,
      (__int64)"GetPropertyUnsignedLong GFX_PIPELINE_PROFILE_POLICY failed. Not critical. ",
      v17);
  }
  v19 = *((_QWORD *)this + 6114);
  v46 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *))(*(_QWORD *)v19 + 40LL))(
          v19,
          L"GfxPipeline::ImageQualityPolicy",
          &v46);
  v21 = v20;
  if ( v20 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v22 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      260,
      (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
      v22,
      (__int64)"GetPropertyUnsignedLong GFX_PIPELINE_IMAGE_QUALITY_POLICY failed. Not critical.",
      v21);
  }
  v23 = *((_QWORD *)this + 6114);
  v49 = 0;
  LOBYTE(v1) = v46 == 2;
  v24 = (*(__int64 (__fastcall **)(__int64, const wchar_t *, unsigned int *))(*(_QWORD *)v23 + 32LL))(
          v23,
          L"GfxPipeline::AVC444ModePreferred",
          &v49);
  v25 = v24;
  if ( v24 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v26 = RdpWppGetCurrentThreadActivityIdPrefix();
    WPP_SF_DsD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      261,
      (unsigned int)WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids,
      v26,
      (__int64)"GetPropertyBool GFX_PIPELINE_AVC444_MODE_PREFERRED failed. Not critical.",
      v25);
  }
  v27 = 1;
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, int *))(**((_QWORD **)this + 6114) + 40LL))(
         *((_QWORD *)this + 6114),
         L"MaxCompressionLevel",
         &v53) >= 0 )
    v27 = v53 != 0;
  *(_DWORD *)Data = 0;
  if ( !RegOpenKeyExW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Policies\\Microsoft\\Windows NT\\Terminal Services",
          0,
          0x20019u,
          &hKey) )
  {
    Type = 0;
    cbData = 4;
    if ( RegQueryValueExW(hKey, L"AVCHardwareEncodePreferred", 0, &Type, Data, &cbData) || Type != 4 )
    {
      *(_DWORD *)Data = 0;
      if ( (unsigned int)CallbackContext > 3 )
      {
        v52 = "AVC hardware encode policy not set. Not critical.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v28,
          (unsigned int)qword_180275180,
          v29,
          v30,
          (__int64)&v52);
      }
    }
  }
  v31 = 1;
  if ( hKey )
  {
    cbData = 0;
    lpcbData[0] = 4;
    Type = 0;
    if ( RegQueryValueExW(hKey, L"bEnumerateHWBeforeSW", 0, &Type, (LPBYTE)&cbData, lpcbData) || Type != 4 )
    {
      if ( (unsigned int)CallbackContext > 3 )
      {
        v52 = "GPU enabled in remote sessions policy not set. Not critical.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v32,
          (unsigned int)&word_18027515E,
          v33,
          v34,
          (__int64)&v52);
      }
      memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
      VersionInformation.dwOSVersionInfoSize = 284;
      if ( GetVersionExW(&VersionInformation) )
        v31 = (v60 & 0x100) != 0;
    }
    else
    {
      v31 = cbData != 0;
    }
    if ( hKey )
    {
      Type = 0;
      lpcbData[0] = 4;
      cbData = 0;
      if ( RegQueryValueExW(hKey, L"fEnableRemoteFXAdvancedRemoteApp", 0, &cbData, (LPBYTE)&Type, lpcbData)
        || cbData != 4 )
      {
        if ( (unsigned int)CallbackContext > 3 )
        {
          v52 = "Hidef RAIL mode policy not set. Not critical.";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
            v35,
            (unsigned int)&dword_18027513C,
            v36,
            v37,
            (__int64)&v52);
        }
      }
      else
      {
        v12 = Type != 0;
      }
    }
  }
  if ( (*(int (__fastcall **)(_QWORD, const wchar_t *, VARIANTARG *))(**((_QWORD **)this + 6114) + 24LL))(
         *((_QWORD *)this + 6114),
         L"MonitorConfig",
         &v58) < 0 )
  {
    v39 = 0x2000;
    v38 = 16;
    v40 = 0x2000;
  }
  else
  {
    v38 = *v58.plVal;
    v39 = *(_DWORD *)(v58.llVal + 4);
    v40 = *(_DWORD *)(v58.llVal + 8);
  }
  RDPGraphicsTraceLogging::LogRDPGraphicsSystemSettings(
    v49,
    v46,
    v31,
    *(unsigned int *)Data,
    v38,
    v39,
    v40,
    v12,
    v27,
    v48,
    v13);
  if ( v3 )
  {
    v41 = *(void (__fastcall **)(__int64, const unsigned __int16 *, _QWORD))(*(_QWORD *)v3 + 128LL);
    ImageQualityName = GetImageQualityName(v46);
    v41(v3, ImageQualityName, v1);
  }
  v7 = 0;
LABEL_73:
  VariantClear(&pvarg);
  VariantClear(&v58);
  if ( hKey )
    RegCloseKey(hKey);
  TCntPtr<IRdpVCMgr>::SafeRelease(&v54);
  return v7;
}

```

## disassembly

```asm
0x180097a08  push    rbp
0x180097a0a  push    rbx
0x180097a0b  push    rsi
0x180097a0c  push    rdi
0x180097a0d  push    r12
0x180097a0f  push    r13
0x180097a11  push    r14
0x180097a13  push    r15
0x180097a15  lea     rbp, [rsp-118h]
0x180097a1d  sub     rsp, 218h
0x180097a24  mov     rax, cs:__security_cookie
0x180097a2b  xor     rax, rsp
0x180097a2e  mov     [rbp+150h+var_50], rax
0x180097a35  xor     r13d, r13d
0x180097a38  xor     eax, eax
0x180097a3a  mov     rsi, rcx
0x180097a3d  mov     [rsp+250h+var_1DC], r13d
0x180097a42  xorps   xmm0, xmm0
0x180097a45  mov     [rsp+250h+var_1E8], r13d
0x180097a4a  xorps   xmm1, xmm1
0x180097a4d  mov     dword ptr [rsp+250h+Data], r13d
0x180097a52  mov     ebx, r13d
0x180097a55  mov     [rsp+250h+var_1E0], r13d
0x180097a5a  lea     rcx, [rbp+150h+pvarg]; pvarg
0x180097a5e  mov     [rbp+150h+var_1B8], rbx
0x180097a62  movups  xmmword ptr [rbp+150h+pvarg], xmm0
0x180097a66  mov     qword ptr [rbp+150h+pvarg+10h], rax
0x180097a6a  movups  xmmword ptr [rbp+150h+var_188], xmm1
0x180097a6e  mov     qword ptr [rbp+150h+var_188+10h], rax
0x180097a72  mov     [rbp+150h+hKey], r13
0x180097a76  mov     [rbp+150h+var_1C0], r13d
0x180097a7a  call    cs:__imp_VariantInit
0x180097a80  lea     rcx, [rbp+150h+var_188]; pvarg
0x180097a84  call    cs:__imp_VariantInit
0x180097a8a  cmp     [rsi+0BF10h], r13
0x180097a91  jnz     short loc_180097AEC
0x180097a93  mov     rax, cs:WPP_GLOBAL_Control
0x180097a9a  lea     rdi, WPP_GLOBAL_Control
0x180097aa1  cmp     rax, rdi
0x180097aa4  jz      short loc_180097AE2
0x180097aa6  test    byte ptr [rax+1Ch], 8
0x180097aaa  jz      short loc_180097AE2
0x180097aac  cmp     byte ptr [rax+19h], 2
0x180097ab0  jb      short loc_180097AE2
0x180097ab2  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180097ab7  mov     edx, 100h
0x180097abc  lea     rcx, aMSpgfxconnprop; "m_spGfxConnProperties"
0x180097ac3  mov     [rsp+250h+phkResult], rcx
0x180097ac8  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x180097acf  mov     rcx, cs:WPP_GLOBAL_Control
0x180097ad6  mov     r9d, eax
0x180097ad9  mov     rcx, [rcx+10h]
0x180097add  call    WPP_SF_Ds
0x180097ae2  mov     edi, 80004003h
0x180097ae7  jmp     loc_180098139
0x180097aec  cmp     [rsi+32D8h], r13
0x180097af3  jnz     short loc_180097B27
0x180097af5  mov     rax, cs:WPP_GLOBAL_Control
0x180097afc  lea     rdi, WPP_GLOBAL_Control
0x180097b03  cmp     rax, rdi
0x180097b06  jz      short loc_180097AE2
0x180097b08  test    byte ptr [rax+1Ch], 8
0x180097b0c  jz      short loc_180097AE2
0x180097b0e  cmp     byte ptr [rax+19h], 2
0x180097b12  jb      short loc_180097AE2
0x180097b14  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180097b19  mov     edx, 101h
0x180097b1e  lea     rcx, aMSprdpencplatf; "m_spRDPENCPlatform"
0x180097b25  jmp     short loc_180097AC3
0x180097b27  lea     rcx, [rsi+0BF00h]; this
0x180097b2e  mov     qword ptr [rsp+250h+var_1D8], rcx
0x180097b33  call    ?Lock@CTSCriticalSection@@QEAAXXZ; CTSCriticalSection::Lock(void)
0x180097b38  cmp     [rsi+3330h], r13
0x180097b3f  jz      short loc_180097B69
0x180097b41  lea     rcx, [rbp+150h+var_1B8]
0x180097b45  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x180097b4a  mov     rbx, [rsi+3330h]
0x180097b51  mov     [rbp+150h+var_1B8], rbx
0x180097b55  test    rbx, rbx
0x180097b58  jz      short loc_180097B69
0x180097b5a  mov     rax, [rbx]
0x180097b5d  mov     rcx, rbx
0x180097b60  mov     rax, [rax+8]
0x180097b64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b69  lea     rcx, [rsp+250h+var_1D8]; this
0x180097b6e  call    ??1CTSAutoLock@@QEAA@XZ; CTSAutoLock::~CTSAutoLock(void)
0x180097b73  mov     rcx, [rsi+32D8h]
0x180097b7a  lea     r8, [rbp+150h+pvarg]
0x180097b7e  lea     rdx, aRdpTerminalnam; "RDP::TerminalName"
0x180097b85  mov     rax, [rcx]
0x180097b88  mov     rax, [rax+18h]
0x180097b8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097b91  cmp     word ptr [rbp+150h+pvarg], 8
0x180097b96  mov     edi, eax
0x180097b98  jz      short loc_180097BA1
0x180097b9a  mov     edi, 80004005h
0x180097b9f  jmp     short loc_180097BA9
0x180097ba1  test    eax, eax
0x180097ba3  jns     loc_180097C3B
0x180097ba9  mov     eax, cs:CallbackContext
0x180097baf  cmp     eax, 2
0x180097bb2  jbe     loc_180098139
0x180097bb8  lea     rax, aGetpropertyRdp; "GetProperty RDP_PROPERTY_PROTOCOL_NAME "...
0x180097bbf  mov     [rsp+250h+cbData], 26D3h
0x180097bc7  mov     qword ptr [rsp+250h+var_1D8], rax
0x180097bcc  lea     rdx, word_1802751A2
0x180097bd3  lea     rax, aLoggraphicsset_0; "LogGraphicsSettings"
0x180097bda  mov     [rsp+250h+Type], edi
0x180097bde  mov     [rbp+150h+var_198], rax
0x180097be2  lea     rax, aOnecoreTermsrv_23; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x180097be9  mov     [rbp+150h+var_190], rax
0x180097bed  lea     rax, aErrorHresultFa; "Error HResult failed"
0x180097bf4  mov     [rbp+150h+var_1C8], rax
0x180097bf8  lea     rax, [rsp+250h+var_1D8]
0x180097bfd  mov     [rsp+250h+var_208], rax
0x180097c02  lea     rax, [rbp+150h+var_198]
0x180097c06  mov     [rsp+250h+var_210], rax
0x180097c0b  lea     rax, [rsp+250h+cbData]
0x180097c10  mov     [rsp+250h+var_218], rax
0x180097c15  lea     rax, [rbp+150h+var_190]
0x180097c19  mov     [rsp+250h+var_220], rax
0x180097c1e  lea     rax, [rsp+250h+Type]
0x180097c23  mov     [rsp+250h+lpcbData], rax
0x180097c28  lea     rax, [rbp+150h+var_1C8]
0x180097c2c  mov     [rsp+250h+phkResult], rax
0x180097c31  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x180097c36  jmp     loc_180098139
0x180097c3b  mov     rcx, qword ptr [rbp+150h+pvarg+8]; String1
0x180097c3f  lea     rdx, aRdpTcp_0; "RDP-Tcp"
0x180097c46  call    _wcsicmp
0x180097c4b  mov     r14d, 1
0x180097c51  test    eax, eax
0x180097c53  jnz     short loc_180097C5D
0x180097c55  mov     r15d, r14d
0x180097c58  jmp     loc_180097CDF
0x180097c5d  mov     rcx, qword ptr [rbp+150h+pvarg+8]; String1
0x180097c61  lea     rdx, aRdpCdv; "RDP-Cdv"
0x180097c68  call    _wcsicmp
0x180097c6d  test    eax, eax
0x180097c6f  jnz     short loc_180097C77
0x180097c71  lea     r15d, [rax+2]
0x180097c75  jmp     short loc_180097CDF
0x180097c77  mov     rcx, qword ptr [rbp+150h+pvarg+8]; String1
0x180097c7b  lea     rdx, a31c5ce94259d40; "31C5CE94259D4006A9E4"
0x180097c82  call    _wcsicmp
0x180097c87  test    eax, eax
0x180097c89  jz      short loc_180097CD9
0x180097c8b  mov     rcx, qword ptr [rbp+150h+pvarg+8]; String1
0x180097c8f  lea     rdx, a41c5ce94259d40; "41C5CE94259D4006A9E4"
0x180097c96  call    _wcsicmp
0x180097c9b  test    eax, eax
0x180097c9d  jz      short loc_180097CD9
0x180097c9f  mov     rcx, [rsi+32D8h]
0x180097ca6  lea     r8, [rsp+250h+Type]
0x180097cab  mov     [rsp+250h+Type], r13d
0x180097cb0  lea     rdx, aGfxpipelineFor_0; "GfxPipeline::ForceRemoteFXProfile"
0x180097cb7  mov     r15d, r13d
0x180097cba  mov     rax, [rcx]
0x180097cbd  mov     rax, [rax+20h]
0x180097cc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097cc6  test    eax, eax
0x180097cc8  js      short loc_180097CDF
0x180097cca  cmp     [rsp+250h+Type], r13d
0x180097ccf  jz      short loc_180097CDF
0x180097cd1  mov     r15d, 4
0x180097cd7  jmp     short loc_180097CDF
0x180097cd9  mov     r15d, 3
0x180097cdf  mov     rcx, [rsi+0BF10h]
0x180097ce6  lea     r8, [rsp+250h+var_1E0]
0x180097ceb  mov     [rsp+250h+var_1E0], r13d
0x180097cf0  lea     rdx, aGfxpipelinePro_0; "GfxPipeline::ProfilePolicy"
0x180097cf7  mov     rax, [rcx]
0x180097cfa  mov     rax, [rax+28h]
0x180097cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097d03  lea     rdi, WPP_GLOBAL_Control
0x180097d0a  mov     r12d, eax
0x180097d0d  test    eax, eax
0x180097d0f  jns     short loc_180097D5E
0x180097d11  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d18  cmp     rcx, rdi
0x180097d1b  jz      short loc_180097D5E
0x180097d1d  test    byte ptr [rcx+1Ch], 8
0x180097d21  jz      short loc_180097D5E
0x180097d23  cmp     byte ptr [rcx+19h], 2
0x180097d27  jb      short loc_180097D5E
0x180097d29  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180097d2e  lea     rcx, aGetpropertyuns; "GetPropertyUnsignedLong GFX_PIPELINE_PR"...
0x180097d35  mov     dword ptr [rsp+250h+lpcbData], r12d
0x180097d3a  mov     [rsp+250h+phkResult], rcx
0x180097d3f  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x180097d46  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d4d  mov     edx, 103h
0x180097d52  mov     r9d, eax
0x180097d55  mov     rcx, [rcx+10h]
0x180097d59  call    WPP_SF_DsD
0x180097d5e  mov     rcx, [rsi+0BF10h]
0x180097d65  lea     r8, [rsp+250h+var_1E8]
0x180097d6a  mov     [rsp+250h+var_1E8], r13d
0x180097d6f  lea     rdx, aGfxpipelineIma; "GfxPipeline::ImageQualityPolicy"
0x180097d76  mov     rax, [rcx]
0x180097d79  mov     rax, [rax+28h]
0x180097d7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097d82  mov     r12d, eax
0x180097d85  test    eax, eax
0x180097d87  jns     short loc_180097DD6
0x180097d89  mov     rcx, cs:WPP_GLOBAL_Control
0x180097d90  cmp     rcx, rdi
0x180097d93  jz      short loc_180097DD6
0x180097d95  test    byte ptr [rcx+1Ch], 8
0x180097d99  jz      short loc_180097DD6
0x180097d9b  cmp     byte ptr [rcx+19h], 2
0x180097d9f  jb      short loc_180097DD6
0x180097da1  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180097da6  lea     rcx, aGetpropertyuns_0; "GetPropertyUnsignedLong GFX_PIPELINE_IM"...
0x180097dad  mov     dword ptr [rsp+250h+lpcbData], r12d
0x180097db2  mov     [rsp+250h+phkResult], rcx
0x180097db7  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x180097dbe  mov     rcx, cs:WPP_GLOBAL_Control
0x180097dc5  mov     edx, 104h
0x180097dca  mov     r9d, eax
0x180097dcd  mov     rcx, [rcx+10h]
0x180097dd1  call    WPP_SF_DsD
0x180097dd6  mov     rcx, [rsi+0BF10h]
0x180097ddd  lea     r8, [rsp+250h+var_1DC]
0x180097de2  cmp     [rsp+250h+var_1E8], 2
0x180097de7  lea     rdx, aGfxpipelineAvc_2; "GfxPipeline::AVC444ModePreferred"
0x180097dee  mov     [rsp+250h+var_1DC], 0
0x180097df6  setz    r13b
0x180097dfa  mov     rax, [rcx]
0x180097dfd  mov     rax, [rax+20h]
0x180097e01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e06  mov     r12d, eax
0x180097e09  test    eax, eax
0x180097e0b  jns     short loc_180097E5A
0x180097e0d  mov     rcx, cs:WPP_GLOBAL_Control
0x180097e14  cmp     rcx, rdi
0x180097e17  jz      short loc_180097E5A
0x180097e19  test    byte ptr [rcx+1Ch], 8
0x180097e1d  jz      short loc_180097E5A
0x180097e1f  cmp     byte ptr [rcx+19h], 2
0x180097e23  jb      short loc_180097E5A
0x180097e25  call    ?RdpWppGetCurrentThreadActivityIdPrefix@@YAIXZ; RdpWppGetCurrentThreadActivityIdPrefix(void)
0x180097e2a  lea     rcx, aGetpropertyboo_0; "GetPropertyBool GFX_PIPELINE_AVC444_MOD"...
0x180097e31  mov     dword ptr [rsp+250h+lpcbData], r12d
0x180097e36  mov     [rsp+250h+phkResult], rcx
0x180097e3b  lea     r8, WPP_6a304ed0a30f3e677431555ea8dad46d_Traceguids
0x180097e42  mov     rcx, cs:WPP_GLOBAL_Control
0x180097e49  mov     edx, 105h
0x180097e4e  mov     r9d, eax
0x180097e51  mov     rcx, [rcx+10h]
0x180097e55  call    WPP_SF_DsD
0x180097e5a  mov     rcx, [rsi+0BF10h]
0x180097e61  lea     r8, [rbp+150h+var_1C0]
0x180097e65  lea     rdx, aMaxcompression_0; "MaxCompressionLevel"
0x180097e6c  mov     r12d, r14d
0x180097e6f  mov     rax, [rcx]
0x180097e72  mov     rax, [rax+28h]
0x180097e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e7b  test    eax, eax
0x180097e7d  js      short loc_180097E89
0x180097e7f  mov     eax, [rbp+150h+var_1C0]
0x180097e82  neg     eax
0x180097e84  sbb     ecx, ecx
0x180097e86  and     r12d, ecx
0x180097e89  lea     rax, [rbp+150h+hKey]
0x180097e8d  mov     dword ptr [rsp+250h+Data], 0
0x180097e95  mov     r9d, 20019h; samDesired
0x180097e9b  mov     [rsp+250h+phkResult], rax; phkResult
0x180097ea0  xor     r8d, r8d; ulOptions
0x180097ea3  lea     rdx, aSoftwarePolici_3; "Software\\Policies\\Microsoft\\Windows "...
0x180097eaa  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180097eb1  call    cs:__imp_RegOpenKeyExW
0x180097eb7  test    eax, eax
0x180097eb9  jnz     short loc_180097F32
0x180097ebb  mov     rcx, [rbp+150h+hKey]; hKey
0x180097ebf  lea     r9, [rsp+250h+Type]; lpType
0x180097ec4  mov     [rsp+250h+Type], eax
0x180097ec8  lea     rdx, aAvchardwareenc; "AVCHardwareEncodePreferred"
0x180097ecf  lea     rax, [rsp+250h+cbData]
0x180097ed4  mov     [rsp+250h+cbData], 4
0x180097edc  mov     [rsp+250h+lpcbData], rax; lpcbData
0x180097ee1  xor     r8d, r8d; lpReserved
0x180097ee4  lea     rax, [rsp+250h+Data]
0x180097ee9  mov     [rsp+250h+phkResult], rax; lpData
0x180097eee  call    cs:__imp_RegQueryValueExW
0x180097ef4  test    eax, eax
0x180097ef6  jnz     short loc_180097EFF
0x180097ef8  cmp     [rsp+250h+Type], 4
0x180097efd  jz      short loc_180097F32
0x180097eff  mov     eax, cs:CallbackContext
0x180097f05  mov     dword ptr [rsp+250h+Data], 0
0x180097f0d  cmp     eax, 3
0x180097f10  jbe     short loc_180097F32
0x180097f12  lea     rax, aAvcHardwareEnc; "AVC hardware encode policy not set. Not"...
0x180097f19  mov     [rbp+150h+var_1C8], rax
0x180097f1d  lea     rdx, qword_180275180
0x180097f24  lea     rax, [rbp+150h+var_1C8]
0x180097f28  mov     [rsp+250h+phkResult], rax
0x180097f2d  call    ??$Write@U?$_tlgWrapSz@D@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &)
0x180097f32  mov     rcx, [rbp+150h+hKey]; hKey
  ... truncated ...
```
