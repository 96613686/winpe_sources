# CapsManager::Initialize(IRdpGfxCapsSet *,IRdpPipeProtocol *,IRdpPipeExtensionFactory *,IRDPCollection *,ComPlainSmartPtr<IRDPENCPlatformContext> const &)

- ea: `0x1800a5fb4`
- end: `0x1800a7158`
- name: `?Initialize@CapsManager@@QEAAJPEAUIRdpGfxCapsSet@@PEAVIRdpPipeProtocol@@PEAVIRdpPipeExtensionFactory@@PEAUIRDPCollection@@AEBV?$ComPlainSmartPtr@UIRDPENCPlatformContext@@@@@Z`
- size: `4516`
- prototype: `__int64 __fastcall(CapsManager *this, __int64, struct IRdpPipeProtocol *, struct IRdpPipeExtensionFactory *, struct IRDPCollection *, HKEY *)`
- caller_count: `1`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180098aa0`

## callees

- `0x1800012dc`
- `0x180001308`
- `0x180001f84`
- `0x18000202c`
- `0x18000305c`
- `0x180003970`
- `0x18000ce04`
- `0x18000ce34`
- `0x18004d52c`
- `0x18007e9e0`
- `0x18007f42c`
- `0x1800a3608`
- `0x1800a5fb4`
- `0x1800a71ec`
- `0x1800a730c`
- `0x1800a81e0`
- `0x1800a87e0`
- `0x1800a8bd4`
- `0x180158180`
- `0x18019c010`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800a6030`
- `api-ms-win-core-sysinfo-l1-1-0!GetVersionExW` at `0x1800a6030`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a62c8`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x1800a62c8`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a62ea`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800a62ea`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a628d`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800a628d`

## string_xrefs

- `0x1800a60f7`: `Unable to GetProtocolSettings`
- `0x1800a60d3`: `CapsManagerError_InitializeGetProtocolSettingsFail`
- `0x1800a67a3`: `Capability: client side HEVC capability`
- `0x1800a6966`: `Capability: client side HEVC 444 capability`
- `0x1800a6aac`: `Capability: No client side HEVC 444 capability`
- `0x1800a6e22`: `Capability: client side AVC capability is`
- `0x1800a70e5`: `Unable to update client mode in caps`

## pseudocode

```c
__int64 __fastcall CapsManager::Initialize(
        CapsManager *this,
        __int64 a2,
        struct IRdpPipeProtocol *a3,
        struct IRdpPipeExtensionFactory *a4,
        struct IRDPCollection *a5,
        HKEY *a6)
{
  int v8; // r8d
  int v9; // r9d
  int v10; // esi
  DWORD *v11; // r14
  signed int v12; // eax
  int v13; // ecx
  int v14; // r8d
  int v15; // r9d
  signed int updated; // edi
  int v17; // r8d
  int v18; // r9d
  __int64 v20; // rcx
  __int64 v21; // rcx
  int v22; // ecx
  int v23; // r8d
  int v24; // r9d
  int v25; // ecx
  int v26; // r8d
  int v27; // r9d
  char *v28; // rax
  char *v29; // rdx
  char *v30; // rax
  struct IRdpPipeExtensionFactory **v31; // rax
  unsigned int v32; // edx
  _DWORD *v33; // rax
  __int64 v34; // rcx
  struct IRDPCollection *v35; // r8
  const char *v36; // r9
  int v37; // ecx
  HKEY v38; // r14
  __int64 v39; // rcx
  BOOL v40; // eax
  __int64 v41; // rcx
  BOOL v42; // eax
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  __int64 v46; // rcx
  int v47; // ecx
  int v48; // r8d
  int v49; // r9d
  int v50; // ecx
  int v51; // eax
  signed int v52; // eax
  int v53; // ecx
  int v54; // r8d
  int v55; // r9d
  int v56; // ecx
  int v57; // r8d
  int v58; // r9d
  __int64 v59; // rcx
  int v60; // ecx
  int v61; // r8d
  int v62; // r9d
  DWORD v63; // ecx
  int v64; // eax
  signed int v65; // eax
  int v66; // ecx
  int v67; // r8d
  int v68; // r9d
  signed int v69; // eax
  int v70; // ecx
  int v71; // r8d
  int v72; // r9d
  __int64 v73; // rcx
  int v74; // ecx
  int v75; // r8d
  int v76; // r9d
  int v77; // eax
  __int64 v78; // rcx
  __int64 v79; // rcx
  signed int v80; // eax
  int v81; // ecx
  int v82; // r8d
  int v83; // r9d
  __int64 v84; // rcx
  __int64 v85; // r8
  __int64 v86; // r9
  __int64 v87; // rcx
  int v88; // ecx
  int v89; // ecx
  int v90; // r8d
  int v91; // r9d
  int v92; // ecx
  int v93; // r8d
  int v94; // r9d
  int phkResult; // [rsp+20h] [rbp-E0h]
  struct IRDPCollection **v96; // [rsp+30h] [rbp-D0h]
  HKEY *v97; // [rsp+40h] [rbp-C0h]
  void *p_hKey; // [rsp+48h] [rbp-B8h]
  DWORD cbData; // [rsp+80h] [rbp-80h] BYREF
  HKEY hKey; // [rsp+88h] [rbp-78h] BYREF
  BYTE Data[8]; // [rsp+90h] [rbp-70h] BYREF
  DWORD Type[2]; // [rsp+98h] [rbp-68h] BYREF
  struct IRDPCollection *v103; // [rsp+A0h] [rbp-60h] BYREF
  const char *v104; // [rsp+A8h] [rbp-58h] BYREF
  struct IRdpPipeExtensionFactory *v105; // [rsp+B0h] [rbp-50h] BYREF
  int v106[2]; // [rsp+B8h] [rbp-48h] BYREF
  int v107[2]; // [rsp+C0h] [rbp-40h] BYREF
  const char *v108; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v109; // [rsp+D0h] [rbp-30h] BYREF
  GUID ActivityId; // [rsp+D8h] [rbp-28h] BYREF
  struct _OSVERSIONINFOW VersionInformation; // [rsp+F0h] [rbp-10h] BYREF

  v103 = a5;
  v105 = a4;
  *(struct _GUID *)((char *)this + 136) = *RdpActivityId::GetCurrentActivityId(&ActivityId);
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x118u);
  VersionInformation.dwOSVersionInfoSize = 284;
  v10 = 1;
  if ( GetVersionExW(&VersionInformation) )
  {
    if ( VersionInformation.dwMajorVersion < 0xA )
    {
      *((_DWORD *)this + 44) = 1;
      if ( (unsigned int)CallbackContext > 4 )
      {
        cbData = VersionInformation.dwMajorVersion;
        hKey = (HKEY)"SxS stack deployed on OS major version";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
          0,
          (unsigned int)qword_18027DE68,
          v8,
          v9,
          (__int64)&hKey,
          (__int64)&cbData);
      }
    }
  }
  v11 = (DWORD *)((char *)this + 108);
  v12 = (*(__int64 (__fastcall **)(struct IRdpPipeProtocol *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)a3 + 152LL))(
          a3,
          0,
          0,
          0);
  updated = v12;
  if ( v12 < 0 )
  {
    RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
      (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
      "CapsManagerError_InitializeGetProtocolSettingsFail",
      (char *)0x105,
      v12,
      0);
    if ( (unsigned int)CallbackContext > 2 )
    {
      cbData = 262;
      hKey = (HKEY)"Unable to GetProtocolSettings";
      Type[0] = updated;
      v104 = "Initialize";
      v103 = (struct IRDPCollection *)"onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\capsmanager.cpp";
      v105 = (struct IRdpPipeExtensionFactory *)"Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        (_DWORD)CallbackContext,
        (unsigned int)word_18027DE1A,
        v17,
        v18,
        (__int64)&v105,
        (__int64)Type,
        (__int64)&v103,
        (__int64)&cbData,
        (__int64)&v104,
        (__int64)&hKey);
    }
    goto LABEL_8;
  }
  if ( (unsigned int)CallbackContext > 4 )
  {
    cbData = *v11;
    hKey = (HKEY)"Capability: Rail connection state";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
      v13,
      (unsigned int)&word_18027DDEE,
      v14,
      v15,
      (__int64)&hKey,
      (__int64)&cbData);
  }
  hKey = *a6;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&hKey);
  *((_DWORD *)this + 41) = (unsigned __int8)CapsManager::IsDisplayProtectionEnforced(v20, &hKey);
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_ReverseConnectGraphicsCapsVersionBlock>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_ReverseConnectGraphicsCapsVersionBlock>::GetImpl'::`2'::impl) )
  {
    hKey = *a6;
    TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&hKey);
    *((_DWORD *)this + 42) = (unsigned __int8)CapsManager::IsReverseConnectMode(v21, &hKey);
    hKey = 0;
    if ( !RegOpenKeyExW(HKEY_LOCAL_MACHINE, L"System\\CurrentControlSet\\Control\\Terminal Server", 0, 0x20019u, &hKey) )
    {
      Type[0] = 0;
      *(_DWORD *)Data = 0;
      cbData = 4;
      if ( !RegQueryValueExW(hKey, L"AllowReverseConnectGraphicsCaps", 0, Type, Data, &cbData) && Type[0] == 4 )
        *((_DWORD *)this + 43) = *(_DWORD *)Data != 0;
      RegCloseKey(hKey);
    }
    if ( (unsigned int)CallbackContext > 5 )
    {
      cbData = *((_DWORD *)this + 43);
      v104 = "Capability: AllowReverseConnectGraphicsCaps";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v22,
        (unsigned int)byte_18027DDAB,
        v23,
        v24,
        (__int64)&v104,
        (__int64)&cbData);
    }
  }
  hKey = *a6;
  TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(&hKey);
  updated = CapsManager::SelectCapsVersion(this);
  if ( updated < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v28 = "Unable to select valid caps";
      cbData = 308;
      v29 = byte_18027DD5D;
LABEL_25:
      hKey = (HKEY)v28;
      v104 = "Initialize";
      v103 = (struct IRDPCollection *)"onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\capsmanager.cpp";
      v30 = "Error HResult failed";
LABEL_26:
      v105 = (struct IRdpPipeExtensionFactory *)v30;
      p_hKey = &hKey;
      v97 = (HKEY *)&v104;
      v96 = &v103;
      v31 = &v105;
LABEL_27:
      Type[0] = updated;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v25,
        (_DWORD)v29,
        v26,
        v27,
        (__int64)v31,
        (__int64)Type,
        (__int64)v96,
        (__int64)&cbData,
        (__int64)v97,
        (__int64)p_hKey);
      goto LABEL_8;
    }
    goto LABEL_8;
  }
  v26 = *((_DWORD *)this + 22);
  v32 = 0;
  while ( 1 )
  {
    v25 = 3 * v32;
    v33 = (_DWORD *)qword_1801B9A40 + 3 * v32;
    if ( v26 == *v33 )
      break;
    if ( (int)++v32 >= 15 )
      goto LABEL_34;
  }
  *((_QWORD *)this + 23) = v33;
LABEL_34:
  if ( !*((_QWORD *)this + 23) )
  {
    updated = -2147467261;
    if ( (unsigned int)CallbackContext > 2 )
    {
      cbData = 319;
      hKey = (HKEY)"Unexpected NULL pointer";
      v29 = &byte_18027DD0F;
      v104 = "Initialize";
      v103 = (struct IRDPCollection *)"onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\capsmanager.cpp";
      v30 = "Error condition failed";
      goto LABEL_26;
    }
    goto LABEL_8;
  }
  updated = CapsManager::CheckCodecSupport(this, a3, v105, v103, (struct IUnknown *)*a6);
  if ( updated < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      v28 = "Unable to check codec support";
      cbData = 324;
      v29 = byte_18027DCC1;
      goto LABEL_25;
    }
LABEL_8:
    if ( *((_QWORD *)this + 6) )
    {
      TCntPtr<IRdpVCMgr>::SafeRelease((char *)this + 48);
      *((_QWORD *)this + 6) = 0;
      TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef((char *)this + 48);
    }
    *((_QWORD *)this + 11) = 0;
    *((_QWORD *)this + 16) = 0;
    *(_QWORD *)((char *)this + 100) = 0;
    *((_DWORD *)this + 38) = 0;
    return (unsigned int)updated;
  }
  if ( *v11
    && (*((_DWORD *)this + 22) == 524292 || *((_DWORD *)this + 22) == 524549 || *((_DWORD *)this + 22) == 655362) )
  {
    *((_DWORD *)this + 23) = 0;
  }
  if ( *((_DWORD *)this + 22) >= 0xA0502u )
  {
    v34 = *((_QWORD *)this + 6);
    Type[0] = 0;
    cbData = 4;
    *((_DWORD *)this + 28) = (*(int (__fastcall **)(__int64, __int64, DWORD *, DWORD *))(*(_QWORD *)v34 + 24LL))(
                               v34,
                               10,
                               Type,
                               &cbData) < 0
                          || Type[0] == 0;
  }
  if ( *((_DWORD *)this + 22) >= 0xA0600u && *((_DWORD *)this + 28) )
    *((_DWORD *)this + 29) = 1;
  if ( *((_DWORD *)this + 22) == 657153 )
    *((_DWORD *)this + 30) = 1;
  v35 = (struct IRDPCollection *)"Stack";
  v36 = "Checkpoint";
  if ( (unsigned int)CallbackContext > 4
    && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, "Stack", "Checkpoint") )
  {
    v38 = (HKEY)((char *)this + 136);
    cbData = *((_DWORD *)this + 30);
    hKey = (HKEY)((char *)this + 136);
    v104 = "CapsMgr";
    v103 = v35;
    v105 = (struct IRdpPipeExtensionFactory *)0x1000000;
    *(_QWORD *)Type = v36;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v37,
      (unsigned int)&dword_18027DC4C,
      (_DWORD)v35,
      (_DWORD)v36,
      (__int64)Type,
      (__int64)&v105,
      (__int64)&v103,
      (__int64)&v104,
      (__int64)&hKey,
      (__int64)&cbData);
  }
  else
  {
    v38 = (HKEY)((char *)this + 136);
  }
  if ( *((_DWORD *)this + 22) >= 0xB0101u )
  {
    v39 = *((_QWORD *)this + 6);
    Type[0] = 0;
    *(_DWORD *)Data = 4;
    v40 = (*(int (__fastcall **)(__int64, __int64, DWORD *, BYTE *))(*(_QWORD *)v39 + 24LL))(v39, 11, Type, Data) < 0
       || Type[0] == 0;
    *((_DWORD *)this + 30) = v40;
    if ( *((_DWORD *)this + 22) <= 0xB0101u )
    {
      *((_DWORD *)this + 31) = 1;
    }
    else
    {
      v41 = *((_QWORD *)this + 6);
      cbData = 0;
      *(_DWORD *)Data = 4;
      v42 = (*(int (__fastcall **)(__int64, __int64, DWORD *, BYTE *))(*(_QWORD *)v41 + 24LL))(v41, 12, &cbData, Data) < 0
         || cbData == 0;
      *((_DWORD *)this + 31) = v42;
    }
  }
  if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v35, v36) )
  {
    cbData = *((_DWORD *)this + 31);
    v103 = (struct IRDPCollection *)"Stack";
    *(_QWORD *)Type = "Checkpoint";
    hKey = v38;
    v104 = "CapsMgr";
    v105 = (struct IRdpPipeExtensionFactory *)0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>>(
      v43,
      (unsigned int)word_18027DBE2,
      v44,
      v45,
      (__int64)Type,
      (__int64)&v105,
      (__int64)&v103,
      (__int64)&v104,
      (__int64)&hKey,
      (__int64)&cbData);
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6), 13) )
  {
    v46 = *((_QWORD *)this + 6);
    *(_DWORD *)Data = 0;
    cbData = 4;
    if ( (*(int (__fastcall **)(__int64, __int64, BYTE *, DWORD *))(*(_QWORD *)v46 + 24LL))(v46, 13, Data, &cbData) < 0 )
    {
      *(_DWORD *)Data = 0;
      if ( (unsigned int)CallbackContext > 3 )
      {
        hKey = (HKEY)"Cannot get RDPGFX_CAPS_FLAG_HEVC_ENABLE caps, so assume no HEVC.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v47,
          (unsigned int)qword_18027DBC0,
          v48,
          v49,
          (__int64)&hKey);
      }
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      Type[0] = *(_DWORD *)Data;
      hKey = (HKEY)"Capability: client side HEVC capability";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v47,
        (unsigned int)byte_18027DB91,
        v48,
        v49,
        (__int64)&hKey,
        (__int64)Type);
    }
    v50 = *(_DWORD *)Data;
    if ( !*(_DWORD *)Data || (v51 = 1, *((_DWORD *)this + 44)) )
      v51 = 0;
    *((_DWORD *)this + 32) &= v51;
    if ( v50 && !*((_DWORD *)this + 32) && (unsigned int)CallbackContext > 3 )
    {
      hKey = (HKEY)"Capability: HEVC is not supported on OS version less than 10, so disabling HEVC.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v50,
        (unsigned int)&byte_18027DB6F,
        v48,
        v49,
        (__int64)&hKey);
    }
    v52 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, __int64))(**((_QWORD **)this + 6) + 48LL))(
            *((_QWORD *)this + 6),
            13,
            (char *)this + 128,
            4);
    updated = v52;
    if ( v52 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "CapsManagerError_InitializeVer11_2EnableHevcFail",
        (char *)0x1AE,
        v52,
        phkResult);
      if ( (unsigned int)CallbackContext > 2 )
      {
        Type[0] = 431;
        hKey = (HKEY)"Cannot set RDPGFX_CAPS_FLAG_HEVC_ENABLE caps";
        LODWORD(v105) = updated;
        v104 = "Initialize";
        v103 = (struct IRDPCollection *)"onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\capsmanager.cpp";
        *(_QWORD *)v106 = "Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v53,
          (unsigned int)byte_18027DB21,
          v54,
          v55,
          (__int64)v106,
          (__int64)&v105,
          (__int64)&v103,
          (__int64)Type,
          (__int64)&v104,
          (__int64)&hKey);
      }
      goto LABEL_8;
    }
  }
  if ( (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6), 15) )
  {
    v59 = *((_QWORD *)this + 6);
    *(_DWORD *)Data = 0;
    LODWORD(v105) = 4;
    if ( (*(int (__fastcall **)(__int64, __int64, BYTE *, struct IRdpPipeExtensionFactory **))(*(_QWORD *)v59 + 24LL))(
           v59,
           15,
           Data,
           &v105) < 0 )
    {
      *(_DWORD *)Data = 0;
      if ( (unsigned int)CallbackContext > 3 )
      {
        *(_QWORD *)v106 = "Cannot get RDPGFX_CAPS_FLAG_HEVC444_ENABLE caps, so assume no HEVC 444 capability.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v60,
          (unsigned int)&byte_18027DAFF,
          v61,
          v62,
          (__int64)v106);
      }
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      cbData = *(_DWORD *)Data;
      *(_QWORD *)v106 = "Capability: client side HEVC 444 capability";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v60,
        (unsigned int)byte_18027DACD,
        v61,
        v62,
        (__int64)v106,
        (__int64)&cbData);
    }
    v63 = *(_DWORD *)Data;
    if ( !*(_DWORD *)Data || (v64 = 1, *((_DWORD *)this + 44)) )
      v64 = 0;
    *((_DWORD *)this + 33) &= v64;
    if ( v63 && !*((_DWORD *)this + 33) && (unsigned int)CallbackContext > 3 )
    {
      *(_QWORD *)v106 = "Capability: HEVC is not supported on OS version less than 10, so disabling HEVC.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v63,
        (unsigned int)byte_18027DAAB,
        v61,
        v62,
        (__int64)v106);
    }
    v65 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, __int64))(**((_QWORD **)this + 6) + 48LL))(
            *((_QWORD *)this + 6),
            15,
            (char *)this + 132,
            4);
    updated = v65;
    if ( v65 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "CapsManagerError_InitializeVer11_2EnableHevcFail",
        (char *)0x1CB,
        v65,
        phkResult);
      if ( (unsigned int)CallbackContext > 2 )
      {
        cbData = 460;
        *(_QWORD *)v106 = "Cannot set RDPGFX_CAPS_FLAG_HEVC444_ENABLE caps";
        v29 = byte_18027DA5D;
        hKey = (HKEY)"Initialize";
        v104 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\capsmanager.cpp";
        v103 = (struct IRDPCollection *)"Error HResult failed";
        p_hKey = v106;
        v97 = &hKey;
        v96 = (struct IRDPCollection **)&v104;
        v31 = &v103;
        goto LABEL_27;
      }
      goto LABEL_8;
    }
  }
  else
  {
    *((_DWORD *)this + 33) = 0;
    if ( (unsigned int)CallbackContext > 4 )
    {
      *(_QWORD *)v106 = "Capability: No client side HEVC 444 capability";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v56,
        (unsigned int)byte_18027DA3B,
        v57,
        v58,
        (__int64)v106);
    }
  }
  if ( *((_DWORD *)this + 22) == 655616 )
  {
    updated = -2147467259;
    if ( !*((_DWORD *)this + 23) )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "CapsManagerError_InitializeVer10_1GeneralFail",
        (char *)0x1D8,
        0x80004005,
        phkResult);
      if ( !*((_DWORD *)this + 23) )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v105) = 473;
          *(_QWORD *)v106 = "No fallback in RDP 10.1 with large monitor size";
          cbData = -2147467259;
          hKey = (HKEY)"Initialize";
          v104 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\capsmanager.cpp";
          v103 = (struct IRDPCollection *)"Error condition failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v66,
            (unsigned int)byte_18027D9ED,
            v67,
            v68,
            (__int64)&v103,
            (__int64)&cbData,
            (__int64)&v104,
            (__int64)&v105,
            (__int64)&hKey,
            (__int64)v106);
        }
        goto LABEL_8;
      }
    }
  }
  else if ( *((_DWORD *)this + 22) == 524549 )
  {
    *((_DWORD *)this + 23) = 0;
    if ( (unsigned int)CallbackContext > 3 )
    {
      *(_QWORD *)v106 = "Capability: AVC in RDP8.1 is no longer supported.";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
        v56,
        (unsigned int)byte_18027D9CB,
        v57,
        v58,
        (__int64)v106);
    }
    v69 = (*(__int64 (__fastcall **)(_QWORD, __int64, char *, __int64))(**((_QWORD **)this + 6) + 48LL))(
            *((_QWORD *)this + 6),
            3,
            (char *)this + 92,
            4);
    updated = v69;
    if ( v69 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "CapsManagerError_InitializeVer8_1DisableAvcFail",
        (char *)0x1E2,
        v69,
        phkResult);
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v105) = 483;
        *(_QWORD *)v106 = "Cannot set RDPGFX_CAPS_FLAG_H264ENABLED caps";
        cbData = updated;
        hKey = (HKEY)"Initialize";
        v104 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\capsmanager.cpp";
        v103 = (struct IRDPCollection *)"Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v70,
          (unsigned int)byte_18027D97D,
          v71,
          v72,
          (__int64)&v103,
          (__int64)&cbData,
          (__int64)&v104,
          (__int64)&v105,
          (__int64)&hKey,
          (__int64)v106);
      }
      goto LABEL_8;
    }
  }
  else if ( (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6), 4) )
  {
    v73 = *((_QWORD *)this + 6);
    *(_DWORD *)Data = 0;
    Type[0] = 4;
    if ( (*(int (__fastcall **)(__int64, __int64, BYTE *, DWORD *))(*(_QWORD *)v73 + 24LL))(v73, 4, Data, Type) < 0 )
    {
      *(_DWORD *)Data = 1;
      if ( (unsigned int)CallbackContext > 3 )
      {
        *(_QWORD *)v106 = "Cannot get RDPGFX_CAPS_FLAG_AVC_DISABLE caps, so assume no AVC.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v74,
          (unsigned int)byte_18027D95B,
          v75,
          v76,
          (__int64)v106);
      }
    }
    if ( *(_DWORD *)Data || (v77 = 1, *((_DWORD *)this + 44)) )
      v77 = 0;
    *((_DWORD *)this + 23) &= v77;
    if ( !*((_DWORD *)this + 25)
      && *((_DWORD *)this + 23)
      && (*(unsigned int (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 6) + 64LL))(*((_QWORD *)this + 6), 9) )
    {
      v78 = *((_QWORD *)this + 6);
      cbData = 0;
      Type[0] = 4;
      updated = (*(__int64 (__fastcall **)(__int64, __int64, DWORD *, DWORD *))(*(_QWORD *)v78 + 24LL))(
                  v78,
                  9,
                  &cbData,
                  Type);
      if ( updated < 0 )
      {
        if ( (unsigned int)CallbackContext > 2 )
        {
          LODWORD(v105) = 508;
          *(_QWORD *)v106 = "Cannot get RdpgfxCapsAvcThinClientMode value";
          LODWORD(v103) = updated;
          hKey = (HKEY)"Initialize";
          v108 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\capsmanager.cpp";
          *(_QWORD *)v107 = "Error HResult failed";
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
            v74,
            (unsigned int)byte_18027D90D,
            v75,
            v76,
            (__int64)v107,
            (__int64)&v103,
            (__int64)&v108,
            (__int64)&v105,
            (__int64)&hKey,
            (__int64)v106);
        }
        goto LABEL_8;
      }
      *((_DWORD *)this + 25) = cbData != 0;
    }
    if ( (unsigned int)CallbackContext > 4 )
    {
      LODWORD(v103) = *(_DWORD *)Data == 0;
      *(_QWORD *)v107 = "Capability: client side AVC capability is";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        v74,
        (unsigned int)word_18027D8E2,
        v75,
        v76,
        (__int64)v107,
        (__int64)&v103);
    }
    v79 = *((_QWORD *)this + 6);
    LODWORD(v104) = *((_DWORD *)this + 23) == 0;
    v80 = (*(__int64 (__fastcall **)(__int64, __int64, const char **, __int64))(*(_QWORD *)v79 + 48LL))(
            v79,
            4,
            &v104,
            4);
    updated = v80;
    if ( v80 < 0 )
    {
      RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(
        (RDPGraphicsTraceLogging *)"IID_IRdpPipeManager",
        "CapsManagerError_InitializeVer10DisableAvcFail",
        (char *)0x205,
        v80,
        phkResult);
      if ( (unsigned int)CallbackContext > 2 )
      {
        LODWORD(v103) = 518;
        *(_QWORD *)v107 = "Cannot set RDPGFX_CAPS_FLAG_AVC_DISABLE caps";
        LODWORD(v105) = updated;
        v108 = "Initialize";
        *(_QWORD *)v106 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\capsmanager.cpp";
        hKey = (HKEY)"Error HResult failed";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
          v81,
          (unsigned int)&dword_18027D894,
          v82,
          v83,
          (__int64)&hKey,
          (__int64)&v105,
          (__int64)v106,
          (__int64)&v103,
          (__int64)&v108,
          (__int64)v107);
      }
      goto LABEL_8;
    }
  }
  if ( *((_DWORD *)this + 22) >= 0xB0300u )
    *((_DWORD *)this + 39) = 1;
  v84 = *((_QWORD *)this + 6);
  *((_DWORD *)this + 40) = *((_DWORD *)this + 22) == 721920;
  if ( (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v84 + 64LL))(v84, 14) )
  {
    v87 = *((_QWORD *)this + 6);
    Type[0] = 0;
    LODWORD(v104) = 4;
    if ( (*(int (__fastcall **)(__int64, __int64, DWORD *, const char **))(*(_QWORD *)v87 + 24LL))(v87, 14, Type, &v104) < 0 )
    {
      Type[0] = 0;
      if ( (unsigned int)CallbackContext > 3 )
      {
        *(_QWORD *)v107 = "Cannot get RDPGFX_CAPS_FLAG_AVCMM_ENABLE caps, so assume no AVCMM.";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>>(
          v88,
          (unsigned int)word_18027D872,
          v85,
          v86,
          (__int64)v107);
      }
    }
    if ( Type[0] != 1 || !*((_DWORD *)this + 23) )
      v10 = 0;
    *((_DWORD *)this + 38) = v10;
  }
  if ( (unsigned int)CallbackContext > 4 && (unsigned __int8)tlgKeywordOn(&CallbackContext, 0x470000000000LL, v85, v86) )
  {
    LODWORD(v104) = *((_DWORD *)this + 41);
    LODWORD(v103) = *((_DWORD *)this + 40);
    LODWORD(v105) = *((_DWORD *)this + 38);
    cbData = *((_DWORD *)this + 25);
    Type[0] = *((_DWORD *)this + 33);
    *(_DWORD *)Data = *((_DWORD *)this + 32);
    LODWORD(hKey) = *((_DWORD *)this + 23);
    v108 = "CapsMgr";
    *(_QWORD *)v106 = "Stack";
    *(_QWORD *)&ActivityId.Data1 = "Checkpoint";
    *(_QWORD *)v107 = v38;
    v109 = 0x1000000;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<8>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByRef<16>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      v89,
      (unsigned int)word_18027D762,
      v90,
      v91,
      (__int64)&ActivityId,
      (__int64)&v109,
      (__int64)v106,
      (__int64)&v108,
      (__int64)v107,
      (__int64)&hKey,
      (__int64)Data,
      (__int64)Type,
      (__int64)&cbData,
      (__int64)&v105,
      (__int64)&v103,
      (__int64)&v104);
  }
  updated = CapsManager::UpdateClientMode(this);
  if ( updated < 0 )
  {
    if ( (unsigned int)CallbackContext > 2 )
    {
      LODWORD(hKey) = 559;
      *(_QWORD *)&ActivityId.Data1 = "Unable to update client mode in caps";
      LODWORD(v104) = updated;
      v109 = (__int64)"Initialize";
      *(_QWORD *)v107 = "onecore\\termsrv\\rdpplatform\\gfxpipe\\server\\capsmanager.cpp";
      v108 = "Error HResult failed";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(
        v92,
        (unsigned int)&dword_18027D714,
        v93,
        v94,
        (__int64)&v108,
        (__int64)&v104,
        (__int64)v107,
        (__int64)&hKey,
        (__int64)&v109,
        (__int64)&ActivityId);
    }
    goto LABEL_8;
  }
  return (unsigned int)updated;
}

```

## disassembly

```asm
0x1800a5fb4  push    rbp
0x1800a5fb6  push    rbx
0x1800a5fb7  push    rsi
0x1800a5fb8  push    rdi
0x1800a5fb9  push    r12
0x1800a5fbb  push    r13
0x1800a5fbd  push    r14
0x1800a5fbf  push    r15
0x1800a5fc1  lea     rbp, [rsp-128h]
0x1800a5fc9  sub     rsp, 228h
0x1800a5fd0  mov     rax, cs:__security_cookie
0x1800a5fd7  xor     rax, rsp
0x1800a5fda  mov     [rbp+160h+var_50], rax
0x1800a5fe1  mov     rax, [rbp+160h+arg_20]
0x1800a5fe8  mov     rbx, rcx
0x1800a5feb  mov     r15, [rbp+160h+arg_28]
0x1800a5ff2  lea     rcx, [rbp+160h+ActivityId]; ActivityId
0x1800a5ff6  mov     [rbp+160h+var_1C0], rax
0x1800a5ffa  mov     r12, r8
0x1800a5ffd  mov     [rbp+160h+var_1B0], r9
0x1800a6001  mov     r13, rdx
0x1800a6004  call    ?GetCurrentActivityId@RdpActivityId@@SA?AU_GUID@@XZ; RdpActivityId::GetCurrentActivityId(void)
0x1800a6009  xor     edx, edx; Val
0x1800a600b  lea     rcx, [rbp+160h+VersionInformation.dwMajorVersion]; void *
0x1800a600f  mov     r8d, 118h; Size
0x1800a6015  movups  xmm0, xmmword ptr [rax]
0x1800a6018  movdqu  xmmword ptr [rbx+88h], xmm0
0x1800a6020  call    memset_0
0x1800a6025  lea     rcx, [rbp+160h+VersionInformation]; lpVersionInformation
0x1800a6029  mov     [rbp+160h+VersionInformation.dwOSVersionInfoSize], 11Ch
0x1800a6030  call    cs:__imp_GetVersionExW
0x1800a6036  xor     ecx, ecx
0x1800a6038  mov     esi, 1
0x1800a603d  test    eax, eax
0x1800a603f  jz      short loc_1800A6089
0x1800a6041  cmp     [rbp+160h+VersionInformation.dwMajorVersion], 0Ah
0x1800a6045  jnb     short loc_1800A6089
0x1800a6047  mov     [rbx+0B0h], esi
0x1800a604d  mov     eax, cs:CallbackContext
0x1800a6053  cmp     eax, 4
0x1800a6056  jbe     short loc_1800A6089
0x1800a6058  mov     eax, [rbp+160h+VersionInformation.dwMajorVersion]
0x1800a605b  lea     rdx, qword_18027DE68
0x1800a6062  mov     [rbp+160h+cbData], eax
0x1800a6065  lea     rax, aSxsStackDeploy; "SxS stack deployed on OS major version"
0x1800a606c  mov     [rbp+160h+hKey], rax
0x1800a6070  lea     rax, [rbp+160h+cbData]
0x1800a6074  mov     [rsp+260h+lpcbData], rax
0x1800a6079  lea     rax, [rbp+160h+hKey]
0x1800a607d  mov     [rsp+260h+phkResult], rax
0x1800a6082  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a6087  xor     ecx, ecx
0x1800a6089  mov     rax, [r12]
0x1800a608d  lea     r14, [rbx+6Ch]
0x1800a6091  mov     [rsp+260h+var_218], rcx
0x1800a6096  xor     r9d, r9d
0x1800a6099  mov     [rsp+260h+var_220], r14
0x1800a609e  xor     r8d, r8d
0x1800a60a1  mov     [rsp+260h+var_228], rcx
0x1800a60a6  xor     edx, edx
0x1800a60a8  mov     rax, [rax+98h]
0x1800a60af  mov     [rsp+260h+var_230], rcx
0x1800a60b4  mov     [rsp+260h+lpcbData], rcx
0x1800a60b9  mov     [rsp+260h+phkResult], rcx; int
0x1800a60be  mov     rcx, r12
0x1800a60c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a60c6  mov     edi, eax
0x1800a60c8  test    eax, eax
0x1800a60ca  jns     loc_1800A61D5
0x1800a60d0  mov     r9d, eax; unsigned int
0x1800a60d3  lea     rdx, aCapsmanagererr_7; "CapsManagerError_InitializeGetProtocolS"...
0x1800a60da  mov     r8d, 105h; char *
0x1800a60e0  lea     rcx, aIidIrdppipeman; "IID_IRdpPipeManager"
0x1800a60e7  call    ?LogRDPGraphicsErrorStrings@RDPGraphicsTraceLogging@@YAXPEAD0IJ@Z; RDPGraphicsTraceLogging::LogRDPGraphicsErrorStrings(char *,char *,uint,long)
0x1800a60ec  mov     ecx, cs:CallbackContext
0x1800a60f2  cmp     ecx, 2
0x1800a60f5  jbe     short loc_1800A616F
0x1800a60f7  lea     rax, aUnableToGetpro; "Unable to GetProtocolSettings"
0x1800a60fe  mov     [rbp+160h+cbData], 106h
0x1800a6105  mov     [rbp+160h+hKey], rax
0x1800a6109  lea     rdx, word_18027DE1A
0x1800a6110  lea     rax, aInitialize; "Initialize"
0x1800a6117  mov     [rbp+160h+Type], edi
0x1800a611a  mov     [rbp+160h+var_1B8], rax
0x1800a611e  lea     rax, aOnecoreTermsrv_12; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800a6125  mov     [rbp+160h+var_1C0], rax
0x1800a6129  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800a6130  mov     [rbp+160h+var_1B0], rax
0x1800a6134  lea     rax, [rbp+160h+hKey]
0x1800a6138  mov     [rsp+260h+var_218], rax
0x1800a613d  lea     rax, [rbp+160h+var_1B8]
0x1800a6141  mov     [rsp+260h+var_220], rax
0x1800a6146  lea     rax, [rbp+160h+cbData]
0x1800a614a  mov     [rsp+260h+var_228], rax
0x1800a614f  lea     rax, [rbp+160h+var_1C0]
0x1800a6153  mov     [rsp+260h+var_230], rax
0x1800a6158  lea     rax, [rbp+160h+Type]
0x1800a615c  mov     [rsp+260h+lpcbData], rax
0x1800a6161  lea     rax, [rbp+160h+var_1B0]
0x1800a6165  mov     [rsp+260h+phkResult], rax
0x1800a616a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800a616f  xor     r13d, r13d
0x1800a6172  lea     rsi, [rbx+30h]
0x1800a6176  cmp     [rsi], r13
0x1800a6179  jz      short loc_1800A618E
0x1800a617b  mov     rcx, rsi
0x1800a617e  call    ?SafeRelease@?$TCntPtr@UIRdpVCMgr@@@@AEAAXXZ; TCntPtr<IRdpVCMgr>::SafeRelease(void)
0x1800a6183  mov     rcx, rsi
0x1800a6186  mov     [rsi], r13
0x1800a6189  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800a618e  mov     qword ptr [rbx+58h], 0
0x1800a6196  mov     qword ptr [rbx+80h], 0
0x1800a61a1  mov     qword ptr [rbx+64h], 0
0x1800a61a9  mov     [rbx+98h], r13d
0x1800a61b0  mov     eax, edi
0x1800a61b2  mov     rcx, [rbp+160h+var_50]
0x1800a61b9  xor     rcx, rsp; StackCookie
0x1800a61bc  call    __security_check_cookie
0x1800a61c1  add     rsp, 228h
0x1800a61c8  pop     r15
0x1800a61ca  pop     r14
0x1800a61cc  pop     r13
0x1800a61ce  pop     r12
0x1800a61d0  pop     rdi
0x1800a61d1  pop     rsi
0x1800a61d2  pop     rbx
0x1800a61d3  pop     rbp
0x1800a61d4  retn
0x1800a61d5  mov     eax, cs:CallbackContext
0x1800a61db  cmp     eax, 4
0x1800a61de  jbe     short loc_1800A620F
0x1800a61e0  mov     eax, [r14]
0x1800a61e3  lea     rdx, word_18027DDEE
0x1800a61ea  mov     [rbp+160h+cbData], eax
0x1800a61ed  lea     rax, aCapabilityRail; "Capability: Rail connection state"
0x1800a61f4  mov     [rbp+160h+hKey], rax
0x1800a61f8  lea     rax, [rbp+160h+cbData]
0x1800a61fc  mov     [rsp+260h+lpcbData], rax
0x1800a6201  lea     rax, [rbp+160h+hKey]
0x1800a6205  mov     [rsp+260h+phkResult], rax
0x1800a620a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a620f  mov     rax, [r15]
0x1800a6212  lea     rcx, [rbp+160h+hKey]
0x1800a6216  mov     [rbp+160h+hKey], rax
0x1800a621a  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800a621f  lea     rdx, [rbp+160h+hKey]
0x1800a6223  call    ?IsDisplayProtectionEnforced@CapsManager@@AEBA_NV?$ComPlainSmartPtr@UIRDPENCPlatformContext@@@@@Z; CapsManager::IsDisplayProtectionEnforced(ComPlainSmartPtr<IRDPENCPlatformContext>)
0x1800a6228  movzx   eax, al
0x1800a622b  mov     [rbx+0A4h], eax
0x1800a6231  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_ReverseConnectGraphicsCapsVersionBlock@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_ReverseConnectGraphicsCapsVersionBlock@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ReverseConnectGraphicsCapsVersionBlock> `wil::Feature<__WilFeatureTraits_Feature_ReverseConnectGraphicsCapsVersionBlock>::GetImpl(void)'::`2'::impl
0x1800a6238  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_ReverseConnectGraphicsCapsVersionBlock@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ReverseConnectGraphicsCapsVersionBlock>::__private_IsEnabled(void)
0x1800a623d  xor     edi, edi
0x1800a623f  test    al, al
0x1800a6241  jz      loc_1800A632D
0x1800a6247  mov     rax, [r15]
0x1800a624a  lea     rcx, [rbp+160h+hKey]
0x1800a624e  mov     [rbp+160h+hKey], rax
0x1800a6252  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800a6257  lea     rdx, [rbp+160h+hKey]
0x1800a625b  call    ?IsReverseConnectMode@CapsManager@@AEBA_NV?$ComPlainSmartPtr@UIRDPENCPlatformContext@@@@@Z; CapsManager::IsReverseConnectMode(ComPlainSmartPtr<IRDPENCPlatformContext>)
0x1800a6260  movzx   eax, al
0x1800a6263  lea     rdx, SubKey; "System\\CurrentControlSet\\Control\\Ter"...
0x1800a626a  mov     [rbx+0A8h], eax
0x1800a6270  mov     r9d, 20019h; samDesired
0x1800a6276  lea     rax, [rbp+160h+hKey]
0x1800a627a  mov     [rbp+160h+hKey], rdi
0x1800a627e  xor     r8d, r8d; ulOptions
0x1800a6281  mov     [rsp+260h+phkResult], rax; phkResult
0x1800a6286  mov     rcx, 0FFFFFFFF80000002h; hKey
0x1800a628d  call    cs:__imp_RegOpenKeyExW
0x1800a6293  test    eax, eax
0x1800a6295  jnz     short loc_1800A62F0
0x1800a6297  mov     rcx, [rbp+160h+hKey]; hKey
0x1800a629b  lea     rax, [rbp+160h+cbData]
0x1800a629f  mov     [rsp+260h+lpcbData], rax; lpcbData
0x1800a62a4  lea     r9, [rbp+160h+Type]; lpType
0x1800a62a8  lea     rax, [rbp+160h+Data]
0x1800a62ac  mov     [rbp+160h+Type], edi
0x1800a62af  xor     r8d, r8d; lpReserved
0x1800a62b2  mov     [rsp+260h+phkResult], rax; lpData
0x1800a62b7  lea     rdx, aAllowreverseco; "AllowReverseConnectGraphicsCaps"
0x1800a62be  mov     dword ptr [rbp+160h+Data], edi
0x1800a62c1  mov     [rbp+160h+cbData], 4
0x1800a62c8  call    cs:__imp_RegQueryValueExW
0x1800a62ce  test    eax, eax
0x1800a62d0  jnz     short loc_1800A62E6
0x1800a62d2  cmp     [rbp+160h+Type], 4
0x1800a62d6  jnz     short loc_1800A62E6
0x1800a62d8  cmp     dword ptr [rbp+160h+Data], edi
0x1800a62db  mov     eax, edi
0x1800a62dd  setnz   al
0x1800a62e0  mov     [rbx+0ACh], eax
0x1800a62e6  mov     rcx, [rbp+160h+hKey]; hKey
0x1800a62ea  call    cs:__imp_RegCloseKey
0x1800a62f0  mov     eax, cs:CallbackContext
0x1800a62f6  cmp     eax, 5
0x1800a62f9  jbe     short loc_1800A632D
0x1800a62fb  mov     eax, [rbx+0ACh]
0x1800a6301  lea     rdx, byte_18027DDAB
0x1800a6308  mov     [rbp+160h+cbData], eax
0x1800a630b  lea     rax, aCapabilityAllo; "Capability: AllowReverseConnectGraphics"...
0x1800a6312  mov     [rbp+160h+var_1B8], rax
0x1800a6316  lea     rax, [rbp+160h+cbData]
0x1800a631a  mov     [rsp+260h+lpcbData], rax
0x1800a631f  lea     rax, [rbp+160h+var_1B8]
0x1800a6323  mov     [rsp+260h+phkResult], rax
0x1800a6328  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800a632d  mov     rax, [r15]
0x1800a6330  lea     rcx, [rbp+160h+hKey]
0x1800a6334  mov     [rbp+160h+hKey], rax
0x1800a6338  call    ?SafeAddRef@?$TCntPtr@UIRDPWDUMX_StackEx@@@@AEAAXXZ; TCntPtr<IRDPWDUMX_StackEx>::SafeAddRef(void)
0x1800a633d  lea     r8, [rbp+160h+hKey]
0x1800a6341  mov     rdx, r13
0x1800a6344  mov     rcx, rbx; this
0x1800a6347  call    ?SelectCapsVersion@CapsManager@@AEAAJPEAUIRdpGfxCapsSet@@V?$ComPlainSmartPtr@UIRDPENCPlatformContext@@@@@Z; CapsManager::SelectCapsVersion(IRdpGfxCapsSet *,ComPlainSmartPtr<IRDPENCPlatformContext>)
0x1800a634c  xor     r13d, r13d
0x1800a634f  mov     edi, eax
0x1800a6351  test    eax, eax
0x1800a6353  jns     loc_1800A63E5
0x1800a6359  mov     eax, cs:CallbackContext
0x1800a635f  cmp     eax, 2
0x1800a6362  jbe     loc_1800A6172
0x1800a6368  lea     rax, aUnableToSelect; "Unable to select valid caps"
0x1800a636f  mov     [rbp+160h+cbData], 134h
0x1800a6376  lea     rdx, byte_18027DD5D
0x1800a637d  mov     [rbp+160h+hKey], rax
0x1800a6381  lea     rax, aInitialize; "Initialize"
0x1800a6388  mov     [rbp+160h+var_1B8], rax
0x1800a638c  lea     rax, aOnecoreTermsrv_12; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800a6393  mov     [rbp+160h+var_1C0], rax
0x1800a6397  lea     rax, aErrorHresultFa; "Error HResult failed"
0x1800a639e  mov     [rbp+160h+var_1B0], rax
0x1800a63a2  lea     rax, [rbp+160h+hKey]
0x1800a63a6  mov     [rsp+260h+var_218], rax
0x1800a63ab  lea     rax, [rbp+160h+var_1B8]
0x1800a63af  mov     [rsp+260h+var_220], rax
0x1800a63b4  lea     rax, [rbp+160h+cbData]
0x1800a63b8  mov     [rsp+260h+var_228], rax
0x1800a63bd  lea     rax, [rbp+160h+var_1C0]
0x1800a63c1  mov     [rsp+260h+var_230], rax
0x1800a63c6  lea     rax, [rbp+160h+Type]
0x1800a63ca  mov     [rsp+260h+lpcbData], rax
0x1800a63cf  lea     rax, [rbp+160h+var_1B0]
0x1800a63d3  mov     [rbp+160h+Type], edi
0x1800a63d6  mov     [rsp+260h+phkResult], rax
0x1800a63db  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U2@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@3433@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &)
0x1800a63e0  jmp     loc_1800A6172
0x1800a63e5  mov     r8d, [rbx+58h]
0x1800a63e9  mov     edx, r13d
0x1800a63ec  mov     eax, edx
0x1800a63ee  lea     rcx, [rax+rax*2]
0x1800a63f2  lea     rax, qword_1801B9A40
0x1800a63f9  lea     rax, [rax+rcx*4]
0x1800a63fd  cmp     r8d, [rax]
0x1800a6400  jz      short loc_1800A640B
0x1800a6402  add     edx, esi
0x1800a6404  cmp     edx, 0Fh
0x1800a6407  jl      short loc_1800A63EC
0x1800a6409  jmp     short loc_1800A6412
0x1800a640b  mov     [rbx+0B8h], rax
0x1800a6412  cmp     [rbx+0B8h], r13
0x1800a6419  jnz     short loc_1800A646A
0x1800a641b  mov     eax, cs:CallbackContext
0x1800a6421  mov     edi, 80004003h
0x1800a6426  cmp     eax, 2
0x1800a6429  jbe     loc_1800A6172
0x1800a642f  lea     rax, aUnexpectedNull; "Unexpected NULL pointer"
0x1800a6436  mov     [rbp+160h+cbData], 13Fh
0x1800a643d  mov     [rbp+160h+hKey], rax
0x1800a6441  lea     rdx, byte_18027DD0F
0x1800a6448  lea     rax, aInitialize; "Initialize"
0x1800a644f  mov     [rbp+160h+var_1B8], rax
0x1800a6453  lea     rax, aOnecoreTermsrv_12; "onecore\\termsrv\\rdpplatform\\gfxpipe"...
0x1800a645a  mov     [rbp+160h+var_1C0], rax
0x1800a645e  lea     rax, aErrorCondition; "Error condition failed"
0x1800a6465  jmp     loc_1800A639E
0x1800a646a  mov     rax, [r15]
0x1800a646d  mov     rdx, r12; struct IRdpPipeProtocol *
0x1800a6470  mov     r9, [rbp+160h+var_1C0]; struct IRDPCollection *
0x1800a6474  mov     rcx, rbx; this
0x1800a6477  mov     r8, [rbp+160h+var_1B0]; struct IRdpPipeExtensionFactory *
0x1800a647b  mov     [rsp+260h+phkResult], rax; struct IUnknown *
0x1800a6480  call    ?CheckCodecSupport@CapsManager@@AEAAJPEAVIRdpPipeProtocol@@PEAVIRdpPipeExtensionFactory@@PEAUIRDPCollection@@PEAUIUnknown@@@Z; CapsManager::CheckCodecSupport(IRdpPipeProtocol *,IRdpPipeExtensionFactory *,IRDPCollection *,IUnknown *)
0x1800a6485  mov     edi, eax
0x1800a6487  test    eax, eax
0x1800a6489  jns     short loc_1800A64B4
0x1800a648b  mov     eax, cs:CallbackContext
0x1800a6491  cmp     eax, 2
0x1800a6494  jbe     loc_1800A6172
0x1800a649a  lea     rax, aUnableToCheckC; "Unable to check codec support"
0x1800a64a1  mov     [rbp+160h+cbData], 144h
0x1800a64a8  lea     rdx, byte_18027DCC1
0x1800a64af  jmp     loc_1800A637D
0x1800a64b4  cmp     [r14], r13d
0x1800a64b7  jz      short loc_1800A64D8
0x1800a64b9  cmp     dword ptr [rbx+58h], 80004h
0x1800a64c0  jz      short loc_1800A64D4
0x1800a64c2  cmp     dword ptr [rbx+58h], 80105h
0x1800a64c9  jz      short loc_1800A64D4
0x1800a64cb  cmp     dword ptr [rbx+58h], 0A0002h
  ... truncated ...
```
