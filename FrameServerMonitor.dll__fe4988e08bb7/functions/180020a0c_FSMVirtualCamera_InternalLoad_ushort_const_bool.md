# FSMVirtualCamera::InternalLoad(ushort const *,bool)

- ea: `0x180020a0c`
- end: `0x180021c85`
- name: `?InternalLoad@FSMVirtualCamera@@IEAAJPEBG_N@Z`
- size: `4729`
- prototype: `int(FSMVirtualCamera *__hidden this, const unsigned __int16 *, bool)`
- caller_count: `1`
- callee_count: `31`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180023978`

## callees

- `0x1800019f0`
- `0x180001dc0`
- `0x180002f90`
- `0x180003274`
- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x180006ae8`
- `0x180006cc0`
- `0x18000723c`
- `0x18000c684`
- `0x18000cffc`
- `0x18000d060`
- `0x18000d088`
- `0x18000d1e0`
- `0x18000d594`
- `0x18000d62c`
- `0x18001e7dc`
- `0x18001e848`
- `0x18001e86c`
- `0x18001ec2c`
- `0x180020a0c`
- `0x180023350`
- `0x18002544c`
- `0x180025474`
- `0x180025578`
- `0x18002fa3c`
- `0x18002fa70`
- `0x180040914`
- `0x18004633c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800212b5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021287`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180021287`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800212ab`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x1800212ab`
- `MFPlat!MFCreateAttributes` at `0x180020b2a`
- `MFPlat!MFCreateAttributes` at `0x180020b2a`
- `MFPlat!MFInitAttributesFromBlob` at `0x18002154c`
- `MFPlat!MFInitAttributesFromBlob` at `0x18002154c`

## pseudocode

```c
__int64 __fastcall FSMVirtualCamera::InternalLoad(FSMVirtualCamera *this, const unsigned __int16 *a2, char a3)
{
  unsigned __int8 *v5; // rsi
  signed int v6; // edi
  __int64 v7; // rdx
  HRESULT FSMDeviceProperties; // eax
  __int64 v9; // rdx
  const struct _GUID *v10; // rcx
  struct IFSMCameraDeviceProperties **v11; // r15
  const struct _GUID *v12; // rcx
  unsigned __int8 *v13; // r15
  unsigned __int8 *v14; // r14
  unsigned __int8 *v15; // rbx
  __int64 v16; // rdi
  const char *v17; // rax
  __int64 v18; // rdx
  void *v19; // rdi
  const WCHAR *v20; // rcx
  signed int LastError; // eax
  const WCHAR *v22; // rsi
  PBYTE *v23; // rbx
  unsigned __int64 v24; // rdx
  const struct std::nothrow_t *unique; // rax
  const struct std::nothrow_t *v26; // rdx
  WCHAR *v27; // rcx
  struct IFSMCameraDeviceProperties **v28; // r14
  UINT8 *v29; // rbx
  signed int v30; // eax
  __int64 v31; // rdx
  UINT8 *v32; // rbx
  UINT8 *v33; // rbx
  UINT8 *v34; // rbx
  int (__fastcall ***v35)(_QWORD, GUID *, LPCWSTR *); // rcx
  int (__fastcall **v36)(_QWORD, GUID *, LPCWSTR *); // rax
  const struct std::nothrow_t *v37; // rdx
  UINT v38; // ebx
  int i; // esi
  FSString *v40; // rax
  const char *String; // rax
  __int64 v42; // rcx
  struct IFSMCameraDeviceProperties *v43; // rbx
  int (__fastcall **v44)(struct IFSMCameraDeviceProperties *, GUID *, __int64 *); // rax
  int (__fastcall *v45)(struct IFSMCameraDeviceProperties *, GUID *, __int64 *); // rdi
  const struct std::nothrow_t *v46; // rdx
  UINT j; // ebx
  FSString *v48; // rax
  const char *v49; // rax
  __int64 v50; // rdx
  UINT cbBufSize; // [rsp+30h] [rbp-79h] BYREF
  UINT8 *pBuf; // [rsp+38h] [rbp-71h] BYREF
  BYTE PropertyBuffer; // [rsp+40h] [rbp-69h] BYREF
  char v55; // [rsp+41h] [rbp-68h]
  __int64 v56; // [rsp+48h] [rbp-61h] BYREF
  int v57; // [rsp+50h] [rbp-59h]
  void *v58; // [rsp+58h] [rbp-51h] BYREF
  unsigned int v59; // [rsp+60h] [rbp-49h]
  unsigned int v60; // [rsp+64h] [rbp-45h]
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+68h] [rbp-41h] BYREF
  _WORD v62[8]; // [rsp+78h] [rbp-31h] BYREF
  unsigned __int8 *v63; // [rsp+88h] [rbp-21h] BYREF
  unsigned __int8 *v64; // [rsp+90h] [rbp-19h] BYREF
  unsigned __int8 *v65; // [rsp+98h] [rbp-11h] BYREF
  unsigned __int8 *v66; // [rsp+A0h] [rbp-9h] BYREF
  __int64 v67; // [rsp+A8h] [rbp-1h] BYREF
  LPCWSTR pszDeviceInterface[2]; // [rsp+B0h] [rbp+7h] BYREF

  v55 = a3;
  pszDeviceInterface[0] = a2;
  v57 = 0;
  cbBufSize = 0;
  v5 = 0;
  PropertyBuffer = 0;
  v67 = 0;
  LODWORD(pBuf) = 0;
  v66 = 0;
  LODWORD(v58) = 0;
  v65 = 0;
  LODWORD(v56) = 0;
  v64 = 0;
  v59 = 0;
  v63 = 0;
  v60 = 0;
  if ( !a2 )
  {
    v6 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_222;
    v7 = 146;
    goto LABEL_4;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      147,
      (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      (_DWORD)this,
      (__int64)a2);
  FSMDeviceProperties = AutoSecurityAttributes::Set(
                          (FSMVirtualCamera *)((char *)this + 592),
                          L"O:SYG:SYD:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GRGX;;;WD)(A;;GRGX;;;S-1-15-3-3845273463-1331427702-1186"
                           "551195-1148109977)");
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 148;
LABEL_221:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      this,
      FSMDeviceProperties);
    goto LABEL_222;
  }
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((char *)this + 576);
  FSMDeviceProperties = MFCreateAttributes((IMFAttributes **)this + 72, 1u);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 149;
    goto LABEL_221;
  }
  v10 = (const struct _GUID *)*((_QWORD *)this + 66);
  *((_QWORD *)this + 66) = 0;
  if ( v10 )
    (*(void (__fastcall **)(const struct _GUID *))(*(_QWORD *)&v10->Data1 + 16LL))(v10);
  FSMDeviceProperties = FSMCameraDeviceProperties::CreateFSMDeviceProperties(v10, (void **)this + 66);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 150;
    goto LABEL_221;
  }
  v11 = (struct IFSMCameraDeviceProperties **)((char *)this + 536);
  v12 = (const struct _GUID *)*((_QWORD *)this + 67);
  *((_QWORD *)this + 67) = 0;
  if ( v12 )
    (*(void (__fastcall **)(const struct _GUID *))(*(_QWORD *)&v12->Data1 + 16LL))(v12);
  FSMDeviceProperties = FSMCameraDeviceProperties::CreateFSMDeviceProperties(v12, (void **)this + 67);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 151;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSGetDeviceInterfaceProperty(
                          a2,
                          (DEVPROPKEY *)&DEVPKEY_DeviceInterface_CameraSettings_Configured,
                          &PropertyBuffer,
                          1u,
                          &cbBufSize);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 152;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *v11,
                          &DEVPKEY_DeviceInterface_CameraSettings_Configured,
                          0x11u,
                          &PropertyBuffer,
                          1u);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 153;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSGetDeviceInterfaceProperty(
                          a2,
                          (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_Data,
                          (PBYTE)this + 136,
                          0xC8u,
                          &cbBufSize);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 154;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *v11,
                          &DEVPKEY_DeviceInterface_FSM_VirtualCamera_Data,
                          0x1003u,
                          (const unsigned __int8 *)this + 136,
                          0xC8u);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 155;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *v11,
                          &DEVPKEY_DeviceInterface_FrameServerUniqueID,
                          0x1003u,
                          (const unsigned __int8 *)this + 160,
                          0x20u);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 156;
    goto LABEL_221;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      157,
      &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      this,
      *((_DWORD *)this + 36));
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        158,
        &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
        this,
        *((_DWORD *)this + 37));
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          159,
          &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          this,
          *((_DWORD *)this + 38));
    }
  }
  FSMDeviceProperties = FSMVirtualCamera::LoadStringDevProperty(
                          a2,
                          (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_SymbolicName);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 160;
    goto LABEL_221;
  }
  v13 = v64;
  if ( !v64 )
  {
    FSMDeviceProperties = -1072873843;
    v6 = -1072873843;
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 161;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *((struct IFSMCameraDeviceProperties **)this + 67),
                          &DEVPKEY_DeviceInterface_FSM_VirtualCamera_SymbolicName,
                          0x12u,
                          v64,
                          2LL * v59);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 162;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSMVirtualCamera::LoadStringDevProperty(
                          a2,
                          (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_InternalAlias);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 163;
    goto LABEL_221;
  }
  v14 = v63;
  if ( !v63 )
  {
    FSMDeviceProperties = -1072873843;
    v6 = -1072873843;
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 164;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *((struct IFSMCameraDeviceProperties **)this + 67),
                          &DEVPKEY_DeviceInterface_FSM_VirtualCamera_InternalAlias,
                          0x12u,
                          v63,
                          2LL * v60);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 165;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSMVirtualCamera::LoadStringDevProperty(
                          a2,
                          (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceId);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 166;
    goto LABEL_221;
  }
  v15 = v66;
  if ( !v66 )
  {
    FSMDeviceProperties = -1072873843;
    v6 = -1072873843;
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 167;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *((struct IFSMCameraDeviceProperties **)this + 67),
                          &DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceId,
                          0x12u,
                          v66,
                          2LL * (unsigned int)v58);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 168;
    goto LABEL_221;
  }
  FSMDeviceProperties = FSMVirtualCamera::LoadStringDevProperty(
                          pszDeviceInterface[0],
                          (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FriendlyName);
  v6 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 169;
    goto LABEL_221;
  }
  if ( !*((_DWORD *)this + 38) )
  {
    FSMDeviceProperties = FSMVirtualCamera::LoadStringDevProperty(
                            pszDeviceInterface[0],
                            (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_UserSidString);
    v6 = FSMDeviceProperties;
    if ( FSMDeviceProperties < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_222;
      v9 = 170;
      goto LABEL_221;
    }
    v5 = v65;
    FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                            *((struct IFSMCameraDeviceProperties **)this + 67),
                            &DEVPKEY_DeviceInterface_FSM_VirtualCamera_UserSidString,
                            0x12u,
                            v65,
                            2LL * (unsigned int)v56);
    v6 = FSMDeviceProperties;
    if ( FSMDeviceProperties < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_222;
      v9 = 171;
      goto LABEL_221;
    }
  }
  v16 = v67;
  if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
  {
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      172,
      (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      (_DWORD)this,
      v67);
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        173,
        (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
        (_DWORD)this,
        (__int64)v15);
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        v17 = L"<nullptr>";
        if ( v5 )
          v17 = (const char *)v5;
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          174,
          (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          (_DWORD)this,
          (__int64)v17);
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            175,
            (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
            (_DWORD)this,
            (__int64)this + 192);
      }
    }
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 336,
                           v16)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 368,
                           v15)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 464,
                           v13)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 496,
                           v14) )
  {
    FSMDeviceProperties = -2147024882;
    v6 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_222;
    v9 = 176;
    goto LABEL_221;
  }
  if ( !v5 )
  {
LABEL_109:
    v22 = pszDeviceInterface[0];
    FSMDeviceProperties = FSGetDeviceInterfaceProperty(
                            pszDeviceInterface[0],
                            (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_Categories,
                            0,
                            0,
                            &cbBufSize);
    v6 = FSMDeviceProperties;
    if ( FSMDeviceProperties < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_222;
      v9 = 180;
      goto LABEL_221;
    }
    if ( cbBufSize < 0x10 || (cbBufSize & 0xF) != 0 )
    {
      v6 = -1072875845;
      if ( g_wppLevels )
      {
        v7 = 181;
LABEL_4:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v7, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v6);
      }
LABEL_222:
      if ( byte_18005E5A5 )
      {
        v50 = 206;
        goto LABEL_224;
      }
      goto LABEL_225;
    }
    v23 = (PBYTE *)((char *)this + 432);
    v24 = cbBufSize >> 4;
    *((_DWORD *)this + 110) = v24;
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<_GUID [0]>(pszDeviceInterface, v24);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
      (void **)this + 54,
      unique);
    v27 = (WCHAR *)pszDeviceInterface[0];
    pszDeviceInterface[0] = 0;
    if ( v27 )
      operator delete(v27, v26);
    if ( !*v23 )
    {
      FSMDeviceProperties = -2147024882;
      v6 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_222;
      v9 = 182;
      goto LABEL_221;
    }
    FSMDeviceProperties = FSGetDeviceInterfaceProperty(
                            v22,
                            (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_Categories,
                            *v23,
                            16 * *((_DWORD *)this + 110),
                            &cbBufSize);
    v6 = FSMDeviceProperties;
    if ( FSMDeviceProperties < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_222;
      v9 = 183;
      goto LABEL_221;
    }
    v28 = (struct IFSMCameraDeviceProperties **)((char *)this + 536);
    FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                            *((struct IFSMCameraDeviceProperties **)this + 67),
                            &DEVPKEY_DeviceInterface_FSM_VirtualCamera_Categories,
                            0x1003u,
                            *v23,
                            16LL * *((unsigned int *)this + 110));
    v6 = FSMDeviceProperties;
    if ( FSMDeviceProperties < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_222;
      v9 = 184;
      goto LABEL_221;
    }
    if ( FSGetDeviceInterfaceProperty(
           v22,
           (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes,
           0,
           0,
           &cbBufSize) >= 0 )
    {
      wil::make_unique_nothrow<unsigned char [0]>(&pBuf, cbBufSize);
      v29 = pBuf;
      if ( !pBuf )
      {
        v30 = -2147024882;
        v6 = -2147024882;
        if ( !g_wppLevels )
        {
LABEL_132:
          wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pBuf);
          goto LABEL_222;
        }
        v31 = 185;
LABEL_131:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v30);
        goto LABEL_132;
      }
      v30 = FSGetDeviceInterfaceProperty(
              v22,
              (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes,
              pBuf,
              cbBufSize,
              &cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 186;
        goto LABEL_131;
      }
      v30 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 72), v29, cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 187;
        goto LABEL_131;
      }
      v30 = FSMVirtualCamera::AddPropertyToCollection(
              *v28,
              &DEVPKEY_DeviceInterface_FSM_VirtualCamera_Attributes,
              0x1003u,
              v29,
              cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 188;
        goto LABEL_131;
      }
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pBuf);
    }
    if ( FSGetDeviceInterfaceProperty(
           v22,
           (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_Properties,
           0,
           0,
           &cbBufSize) >= 0 )
    {
      wil::make_unique_nothrow<unsigned char [0]>(&pBuf, cbBufSize);
      v32 = pBuf;
      if ( !pBuf )
      {
        v30 = -2147024882;
        v6 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 189;
        goto LABEL_131;
      }
      v30 = FSGetDeviceInterfaceProperty(
              v22,
              (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_Properties,
              pBuf,
              cbBufSize,
              &cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 190;
        goto LABEL_131;
      }
      v30 = (*(__int64 (__fastcall **)(_QWORD, UINT8 *, _QWORD))(**((_QWORD **)this + 66) + 88LL))(
              *((_QWORD *)this + 66),
              v32,
              cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 191;
        goto LABEL_131;
      }
      v30 = FSMVirtualCamera::AddPropertyToCollection(
              *v28,
              &DEVPKEY_DeviceInterface_FSM_VirtualCamera_Properties,
              0x1003u,
              v32,
              cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 192;
        goto LABEL_131;
      }
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pBuf);
    }
    if ( FSGetDeviceInterfaceProperty(
           v22,
           (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceInfo,
           0,
           0,
           &cbBufSize) >= 0 )
    {
      wil::make_unique_nothrow<unsigned char [0]>(&pBuf, cbBufSize);
      v33 = pBuf;
      if ( !pBuf )
      {
        v30 = -2147024882;
        v6 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 193;
        goto LABEL_131;
      }
      v30 = FSGetDeviceInterfaceProperty(
              v22,
              (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceInfo,
              pBuf,
              cbBufSize,
              &cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 194;
        goto LABEL_131;
      }
      v30 = FSMVirtualCamera::AddPropertyToCollection(
              *v28,
              &DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceInfo,
              0x1003u,
              v33,
              cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 195;
        goto LABEL_131;
      }
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pBuf);
    }
    if ( FSGetDeviceInterfaceProperty(
           v22,
           (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_DllLoadModuleName,
           0,
           0,
           &cbBufSize) >= 0 )
    {
      wil::make_unique_nothrow<unsigned char [0]>(&pBuf, cbBufSize);
      v34 = pBuf;
      *(GUID *)pszDeviceInterface = GUID_00000000_0000_0000_0000_000000000000;
      if ( !pBuf )
      {
        v30 = -2147024882;
        v6 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 196;
        goto LABEL_131;
      }
      v30 = FSGetDeviceInterfaceProperty(
              v22,
              (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_DllLoadModuleName,
              pBuf,
              cbBufSize,
              &cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 197;
        goto LABEL_131;
      }
      v30 = FSMVirtualCamera::AddPropertyToCollection(
              *v28,
              &DEVPKEY_DeviceInterface_FSM_VirtualCamera_DllLoadModuleName,
              0x12u,
              v34,
              cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 198;
        goto LABEL_131;
      }
      v30 = FSGetDeviceInterfaceProperty(
              v22,
              (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_DllLoadModuleCLSID,
              (PBYTE)pszDeviceInterface,
              0x10u,
              &cbBufSize);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 199;
        goto LABEL_131;
      }
      v30 = FSMVirtualCamera::AddPropertyToCollection(
              *v28,
              &DEVPKEY_DeviceInterface_FSM_VirtualCamera_DllLoadModuleCLSID,
              0xDu,
              (const unsigned __int8 *)pszDeviceInterface,
              0x10u);
      v6 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_132;
        v31 = 200;
        goto LABEL_131;
      }
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pBuf);
    }
    if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
    {
      v35 = (int (__fastcall ***)(_QWORD, GUID *, LPCWSTR *))*((_QWORD *)this + 66);
      pszDeviceInterface[0] = 0;
      v56 = 0;
      pBuf = 0;
      cbBufSize = 0;
      v36 = *v35;
      v58 = 0;
      if ( (*v36)(v35, &GUID_9257d918_c95f_42d2_8bc7_a722fad119b2, pszDeviceInterface) < 0
        || (*(int (__fastcall **)(LPCWSTR, UINT8 **, UINT *))(*(_QWORD *)pszDeviceInterface[0] + 96LL))(
             pszDeviceInterface[0],
             &pBuf,
             &cbBufSize) < 0 )
      {
        i = 0;
      }
      else
      {
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            201,
            &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
            this,
            cbBufSize);
        wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset<_DEVPROPERTY *>(
          &v58,
          pBuf);
        v38 = 0;
        for ( i = 0; v38 < cbBufSize; ++v38 )
        {
          if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          {
            i |= 1u;
            v40 = DevPropTrace::DevPropTrace(
                    (DevPropTrace *)StringSecurityDescriptor,
                    (const struct _DEVPROPERTY *)&pBuf[48 * v38]);
            String = FSString::GetString(v40);
            WPP_SF_qDs(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              202,
              (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
              (_DWORD)this,
              v38,
              (__int64)String);
          }
          if ( (i & 1) != 0 )
          {
            i &= ~1u;
            FSString::~FSString((FSString *)StringSecurityDescriptor, v37);
          }
        }
      }
      wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v58);
      v42 = v56;
      v43 = *v28;
      v44 = *(int (__fastcall ***)(struct IFSMCameraDeviceProperties *, GUID *, __int64 *))*v28;
      v56 = 0;
      v45 = *v44;
      if ( v42 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
      if ( v45(v43, &GUID_9257d918_c95f_42d2_8bc7_a722fad119b2, &v56) >= 0
        && (*(int (__fastcall **)(__int64, UINT8 **, UINT *))(*(_QWORD *)v56 + 96LL))(v56, &pBuf, &cbBufSize) >= 0 )
      {
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            203,
            &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
            this,
            cbBufSize);
        wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset<_DEVPROPERTY *>(
          &v58,
          pBuf);
        for ( j = 0; j < cbBufSize; ++j )
        {
          if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          {
            i |= 2u;
            v48 = DevPropTrace::DevPropTrace(
                    (DevPropTrace *)StringSecurityDescriptor,
                    (const struct _DEVPROPERTY *)&pBuf[48 * j]);
            v49 = FSString::GetString(v48);
            WPP_SF_qDs(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              204,
              (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
              (_DWORD)this,
              j,
              (__int64)v49);
          }
          if ( (i & 2) != 0 )
          {
            i &= ~2u;
            FSString::~FSString((FSString *)StringSecurityDescriptor, v46);
          }
        }
      }
      wistd::unique_ptr<_DEVPROPERTY [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(&v58);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v56);
      wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)pszDeviceInterface);
    }
    FSMDeviceProperties = (*(__int64 (__fastcall **)(FSMVirtualCamera *, char *, _QWORD))(*(_QWORD *)this + 8LL))(
                            this,
                            (char *)this + 192,
                            0);
    v6 = FSMDeviceProperties;
    if ( FSMDeviceProperties < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_222;
      v9 = 205;
      goto LABEL_221;
    }
    *((_BYTE *)this + 644) = v55;
    goto LABEL_215;
  }
  v62[0] = 0;
  StringSecurityDescriptor[0] = v62;
  pBuf = 0;
  StringSecurityDescriptor[1] = v62;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 400,
                           v5) )
  {
    v6 = -2147024882;
    if ( !g_wppLevels )
    {
LABEL_95:
      wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pBuf);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)StringSecurityDescriptor);
      goto LABEL_222;
    }
    v18 = 177;
LABEL_94:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v18,
      &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      this,
      -2147024882);
    goto LABEL_95;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           StringSecurityDescriptor,
                           L"O:SYG:SYD:(A;;0x00010001;;;SY)(A;;0x00000001;;;S-1-15-2-1)(A;;0x00010001;;;S-1-5-80-391589400"
                            "4-2104103821-3047269622-1811662266-774708259)(A;;0x00010001;;;",
                           155)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           StringSecurityDescriptor,
                           v5)
    || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                           StringSecurityDescriptor,
                           L")",
                           1) )
  {
    v6 = -2147024882;
    if ( !g_wppLevels )
      goto LABEL_95;
    v18 = 178;
    goto LABEL_94;
  }
  v19 = (void *)*((_QWORD *)this + 56);
  if ( v19 )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v56);
    LocalFree(v19);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v56);
  }
  v20 = StringSecurityDescriptor[0];
  *((_QWORD *)this + 56) = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         v20,
         1u,
         (PSECURITY_DESCRIPTOR *)this + 56,
         (PULONG)this + 114) )
  {
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pBuf);
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)StringSecurityDescriptor);
    goto LABEL_109;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( byte_18005E5A5 )
    WPP_SF_qDS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      179,
      (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      (_DWORD)this,
      v6,
      0);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&pBuf);
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)StringSecurityDescriptor);
  if ( v6 < 0 )
    goto LABEL_222;
LABEL_215:
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v50 = 207;
LABEL_224:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v50, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v6);
  }
LABEL_225:
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v63);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v64);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v65);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v66);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset(&v67);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180020a0c  mov     [rsp-8+arg_10], rbx
0x180020a11  push    rbp
0x180020a12  push    rsi
0x180020a13  push    rdi
0x180020a14  push    r12
0x180020a16  push    r13
0x180020a18  push    r14
0x180020a1a  push    r15
0x180020a1c  lea     rbp, [rsp-27h]
0x180020a21  sub     rsp, 0D0h
0x180020a28  mov     rax, cs:__security_cookie
0x180020a2f  xor     rax, rsp
0x180020a32  mov     [rbp+57h+var_40], rax
0x180020a36  xor     r14d, r14d
0x180020a39  mov     [rbp+57h+var_BF], r8b
0x180020a3d  mov     [rbp+57h+pszDeviceInterface], rdx
0x180020a41  mov     rbx, rdx
0x180020a44  mov     [rbp+57h+var_B0], r14d
0x180020a48  mov     r12, rcx
0x180020a4b  mov     [rbp+57h+cbBufSize], r14d
0x180020a4f  mov     esi, r14d
0x180020a52  mov     [rbp+57h+PropertyBuffer], r14b
0x180020a56  mov     [rbp+57h+var_58], r14
0x180020a5a  mov     dword ptr [rbp+57h+pBuf], r14d
0x180020a5e  mov     [rbp+57h+var_60], r14
0x180020a62  mov     dword ptr [rbp+57h+var_A8], r14d
0x180020a66  mov     [rbp+57h+var_68], r14
0x180020a6a  mov     dword ptr [rbp+57h+var_B8], r14d
0x180020a6e  mov     [rbp+57h+var_70], r14
0x180020a72  mov     [rbp+57h+var_A0], r14d
0x180020a76  mov     [rbp+57h+var_78], r14
0x180020a7a  mov     [rbp+57h+var_9C], r14d
0x180020a7e  test    rdx, rdx
0x180020a81  jnz     short loc_180020AA7
0x180020a83  mov     edi, 80070057h
0x180020a88  lea     r13d, [rdx+1]
0x180020a8c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020a93  jb      loc_180021C00
0x180020a99  mov     edx, 92h
0x180020a9e  mov     dword ptr [rsp+100h+var_E0], edi
0x180020aa2  jmp     loc_180021BE6
0x180020aa7  cmp     cs:byte_18005E5A5, 8
0x180020aae  jb      short loc_180020AD7
0x180020ab0  mov     rcx, cs:WPP_GLOBAL_Control
0x180020ab7  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180020abe  mov     edx, 93h
0x180020ac3  mov     [rsp+100h+var_E0], rbx
0x180020ac8  mov     r9, r12
0x180020acb  mov     rcx, [rcx+0D8h]
0x180020ad2  call    WPP_SF_qS
0x180020ad7  lea     rcx, [r12+250h]; this
0x180020adf  lea     rdx, aOSygSydAGaBaAG; "O:SYG:SYD:(A;;GA;;;BA)(A;;GA;;;OW)(A;;G"...
0x180020ae6  call    ?Set@AutoSecurityAttributes@@QEAAJPEBG@Z; AutoSecurityAttributes::Set(ushort const *)
0x180020aeb  mov     edi, eax
0x180020aed  test    eax, eax
0x180020aef  jns     short loc_180020B0E
0x180020af1  mov     r13d, 1
0x180020af7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020afe  jb      loc_180021C00
0x180020b04  mov     edx, 94h
0x180020b09  jmp     loc_180021BE2
0x180020b0e  lea     rdi, [r12+240h]
0x180020b16  mov     rcx, rdi
0x180020b19  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x180020b1e  mov     r13d, 1
0x180020b24  mov     rcx, rdi; ppMFAttributes
0x180020b27  mov     edx, r13d; cInitialSize
0x180020b2a  call    cs:__imp_MFCreateAttributes
0x180020b30  mov     edi, eax
0x180020b32  test    eax, eax
0x180020b34  jns     short loc_180020B4D
0x180020b36  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020b3d  jb      loc_180021C00
0x180020b43  mov     edx, 95h
0x180020b48  jmp     loc_180021BE2
0x180020b4d  lea     rdi, [r12+210h]
0x180020b55  mov     rcx, [rdi]
0x180020b58  mov     [rdi], r14
0x180020b5b  test    rcx, rcx
0x180020b5e  jz      short loc_180020B6C
0x180020b60  mov     rax, [rcx]
0x180020b63  mov     rax, [rax+10h]
0x180020b67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b6c  mov     rdx, rdi; void **
0x180020b6f  call    ?CreateFSMDeviceProperties@FSMCameraDeviceProperties@@SAJAEBU_GUID@@PEAPEAX@Z; FSMCameraDeviceProperties::CreateFSMDeviceProperties(_GUID const &,void * *)
0x180020b74  mov     edi, eax
0x180020b76  test    eax, eax
0x180020b78  jns     short loc_180020B91
0x180020b7a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020b81  jb      loc_180021C00
0x180020b87  mov     edx, 96h
0x180020b8c  jmp     loc_180021BE2
0x180020b91  lea     r15, [r12+218h]
0x180020b99  mov     rcx, [r15]
0x180020b9c  mov     [r15], r14
0x180020b9f  test    rcx, rcx
0x180020ba2  jz      short loc_180020BB0
0x180020ba4  mov     rax, [rcx]
0x180020ba7  mov     rax, [rax+10h]
0x180020bab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bb0  mov     rdx, r15; void **
0x180020bb3  call    ?CreateFSMDeviceProperties@FSMCameraDeviceProperties@@SAJAEBU_GUID@@PEAPEAX@Z; FSMCameraDeviceProperties::CreateFSMDeviceProperties(_GUID const &,void * *)
0x180020bb8  mov     edi, eax
0x180020bba  test    eax, eax
0x180020bbc  jns     short loc_180020BD5
0x180020bbe  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020bc5  jb      loc_180021C00
0x180020bcb  mov     edx, 97h
0x180020bd0  jmp     loc_180021BE2
0x180020bd5  lea     rax, [rbp+57h+cbBufSize]
0x180020bd9  mov     r9d, r13d; unsigned int
0x180020bdc  lea     r8, [rbp+57h+PropertyBuffer]; PropertyBuffer
0x180020be0  mov     [rsp+100h+var_E0], rax; unsigned int *
0x180020be5  lea     rdx, DEVPKEY_DeviceInterface_CameraSettings_Configured; PropertyKey
0x180020bec  mov     rcx, rbx; pszDeviceInterface
0x180020bef  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180020bf4  mov     edi, eax
0x180020bf6  test    eax, eax
0x180020bf8  jns     short loc_180020C11
0x180020bfa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020c01  jb      loc_180021C00
0x180020c07  mov     edx, 98h
0x180020c0c  jmp     loc_180021BE2
0x180020c11  mov     rcx, [r15]; struct IFSMCameraDeviceProperties *
0x180020c14  lea     r9, [rbp+57h+PropertyBuffer]; unsigned __int8 *
0x180020c18  mov     r8d, 11h; unsigned int
0x180020c1e  mov     [rsp+100h+var_E0], r13; unsigned __int64
0x180020c23  lea     rdx, DEVPKEY_DeviceInterface_CameraSettings_Configured; struct _DEVPROPKEY *
0x180020c2a  call    ?AddPropertyToCollection@FSMVirtualCamera@@SAJPEAUIFSMCameraDeviceProperties@@AEBU_DEVPROPKEY@@KPEBE_K@Z; FSMVirtualCamera::AddPropertyToCollection(IFSMCameraDeviceProperties *,_DEVPROPKEY const &,ulong,uchar const *,unsigned __int64)
0x180020c2f  mov     edi, eax
0x180020c31  test    eax, eax
0x180020c33  jns     short loc_180020C4C
0x180020c35  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020c3c  jb      loc_180021C00
0x180020c42  mov     edx, 99h
0x180020c47  jmp     loc_180021BE2
0x180020c4c  lea     rax, [rbp+57h+cbBufSize]
0x180020c50  mov     r9d, 0C8h; unsigned int
0x180020c56  lea     r14, [r12+88h]
0x180020c5e  mov     [rsp+100h+var_E0], rax; unsigned int *
0x180020c63  mov     r8, r14; PropertyBuffer
0x180020c66  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_Data; PropertyKey
0x180020c6d  mov     rcx, rbx; pszDeviceInterface
0x180020c70  call    ?FSGetDeviceInterfaceProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceInterfaceProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x180020c75  mov     edi, eax
0x180020c77  test    eax, eax
0x180020c79  jns     short loc_180020C92
0x180020c7b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020c82  jb      loc_180021C00
0x180020c88  mov     edx, 9Ah
0x180020c8d  jmp     loc_180021BE2
0x180020c92  mov     rcx, [r15]; struct IFSMCameraDeviceProperties *
0x180020c95  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_Data; struct _DEVPROPKEY *
0x180020c9c  mov     r9, r14; unsigned __int8 *
0x180020c9f  mov     [rsp+100h+var_E0], 0C8h; unsigned __int64
0x180020ca8  mov     r14d, 1003h
0x180020cae  mov     r8d, r14d; unsigned int
0x180020cb1  call    ?AddPropertyToCollection@FSMVirtualCamera@@SAJPEAUIFSMCameraDeviceProperties@@AEBU_DEVPROPKEY@@KPEBE_K@Z; FSMVirtualCamera::AddPropertyToCollection(IFSMCameraDeviceProperties *,_DEVPROPKEY const &,ulong,uchar const *,unsigned __int64)
0x180020cb6  mov     edi, eax
0x180020cb8  test    eax, eax
0x180020cba  jns     short loc_180020CD3
0x180020cbc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020cc3  jb      loc_180021C00
0x180020cc9  mov     edx, 9Bh
0x180020cce  jmp     loc_180021BE2
0x180020cd3  mov     rcx, [r15]; struct IFSMCameraDeviceProperties *
0x180020cd6  lea     r9, [r12+0A0h]; unsigned __int8 *
0x180020cde  mov     r8d, r14d; unsigned int
0x180020ce1  mov     [rsp+100h+var_E0], 20h ; ' '; unsigned __int64
0x180020cea  lea     rdx, DEVPKEY_DeviceInterface_FrameServerUniqueID; struct _DEVPROPKEY *
0x180020cf1  call    ?AddPropertyToCollection@FSMVirtualCamera@@SAJPEAUIFSMCameraDeviceProperties@@AEBU_DEVPROPKEY@@KPEBE_K@Z; FSMVirtualCamera::AddPropertyToCollection(IFSMCameraDeviceProperties *,_DEVPROPKEY const &,ulong,uchar const *,unsigned __int64)
0x180020cf6  mov     edi, eax
0x180020cf8  test    eax, eax
0x180020cfa  jns     short loc_180020D13
0x180020cfc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020d03  jb      loc_180021C00
0x180020d09  mov     edx, 9Ch
0x180020d0e  jmp     loc_180021BE2
0x180020d13  cmp     cs:byte_18005E5A5, 10h
0x180020d1a  jb      loc_180020DBC
0x180020d20  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d27  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180020d2e  mov     eax, [r12+90h]
0x180020d36  mov     edx, 9Dh
0x180020d3b  mov     r9, r12
0x180020d3e  mov     dword ptr [rsp+100h+var_E0], eax
0x180020d42  mov     rcx, [rcx+0D8h]
0x180020d49  call    WPP_SF_qD
0x180020d4e  cmp     cs:byte_18005E5A5, 8
0x180020d55  jb      short loc_180020DBC
0x180020d57  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d5e  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180020d65  mov     eax, [r12+94h]
0x180020d6d  mov     edx, 9Eh
0x180020d72  mov     r9, r12
0x180020d75  mov     dword ptr [rsp+100h+var_E0], eax
0x180020d79  mov     rcx, [rcx+0D8h]
0x180020d80  call    WPP_SF_qD
0x180020d85  cmp     cs:byte_18005E5A5, 8
0x180020d8c  jb      short loc_180020DBC
0x180020d8e  mov     rcx, cs:WPP_GLOBAL_Control
0x180020d95  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x180020d9c  mov     eax, [r12+98h]
0x180020da4  mov     edx, 9Fh
0x180020da9  mov     r9, r12
0x180020dac  mov     dword ptr [rsp+100h+var_E0], eax
0x180020db0  mov     rcx, [rcx+0D8h]
0x180020db7  call    WPP_SF_qD
0x180020dbc  lea     r9, [rbp+57h+var_A0]
0x180020dc0  mov     rcx, rbx; pszDeviceInterface
0x180020dc3  lea     r8, [rbp+57h+var_70]
0x180020dc7  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_SymbolicName; PropertyKey
0x180020dce  call    ?LoadStringDevProperty@FSMVirtualCamera@@SAJPEBGAEBU_DEVPROPKEY@@AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@PEAK@Z; FSMVirtualCamera::LoadStringDevProperty(ushort const *,_DEVPROPKEY const &,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,ulong *)
0x180020dd3  mov     edi, eax
0x180020dd5  test    eax, eax
0x180020dd7  jns     short loc_180020DF0
0x180020dd9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020de0  jb      loc_180021C00
0x180020de6  mov     edx, 0A0h
0x180020deb  jmp     loc_180021BE2
0x180020df0  mov     r15, [rbp+57h+var_70]
0x180020df4  test    r15, r15
0x180020df7  jnz     short loc_180020E17
0x180020df9  mov     eax, 0C00D3E8Dh
0x180020dfe  mov     edi, eax
0x180020e00  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020e07  jb      loc_180021C00
0x180020e0d  mov     edx, 0A1h
0x180020e12  jmp     loc_180021BE2
0x180020e17  mov     eax, [rbp+57h+var_A0]
0x180020e1a  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_SymbolicName; struct _DEVPROPKEY *
0x180020e21  mov     rcx, [r12+218h]; struct IFSMCameraDeviceProperties *
0x180020e29  add     rax, rax
0x180020e2c  mov     r9, r15; unsigned __int8 *
0x180020e2f  mov     [rsp+100h+var_E0], rax; unsigned __int64
0x180020e34  mov     r8d, 12h; unsigned int
0x180020e3a  call    ?AddPropertyToCollection@FSMVirtualCamera@@SAJPEAUIFSMCameraDeviceProperties@@AEBU_DEVPROPKEY@@KPEBE_K@Z; FSMVirtualCamera::AddPropertyToCollection(IFSMCameraDeviceProperties *,_DEVPROPKEY const &,ulong,uchar const *,unsigned __int64)
0x180020e3f  mov     edi, eax
0x180020e41  test    eax, eax
0x180020e43  jns     short loc_180020E5C
0x180020e45  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020e4c  jb      loc_180021C00
0x180020e52  mov     edx, 0A2h
0x180020e57  jmp     loc_180021BE2
0x180020e5c  lea     r9, [rbp+57h+var_9C]
0x180020e60  mov     rcx, rbx; pszDeviceInterface
0x180020e63  lea     r8, [rbp+57h+var_78]
0x180020e67  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_InternalAlias; PropertyKey
0x180020e6e  call    ?LoadStringDevProperty@FSMVirtualCamera@@SAJPEBGAEBU_DEVPROPKEY@@AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@PEAK@Z; FSMVirtualCamera::LoadStringDevProperty(ushort const *,_DEVPROPKEY const &,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,ulong *)
0x180020e73  mov     edi, eax
0x180020e75  test    eax, eax
0x180020e77  jns     short loc_180020E90
0x180020e79  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020e80  jb      loc_180021C00
0x180020e86  mov     edx, 0A3h
0x180020e8b  jmp     loc_180021BE2
0x180020e90  mov     r14, [rbp+57h+var_78]
0x180020e94  test    r14, r14
0x180020e97  jnz     short loc_180020EB7
0x180020e99  mov     eax, 0C00D3E8Dh
0x180020e9e  mov     edi, eax
0x180020ea0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020ea7  jb      loc_180021C00
0x180020ead  mov     edx, 0A4h
0x180020eb2  jmp     loc_180021BE2
0x180020eb7  mov     eax, [rbp+57h+var_9C]
0x180020eba  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_InternalAlias; struct _DEVPROPKEY *
0x180020ec1  mov     rcx, [r12+218h]; struct IFSMCameraDeviceProperties *
0x180020ec9  add     rax, rax
0x180020ecc  mov     r9, r14; unsigned __int8 *
0x180020ecf  mov     [rsp+100h+var_E0], rax; unsigned __int64
0x180020ed4  mov     r8d, 12h; unsigned int
0x180020eda  call    ?AddPropertyToCollection@FSMVirtualCamera@@SAJPEAUIFSMCameraDeviceProperties@@AEBU_DEVPROPKEY@@KPEBE_K@Z; FSMVirtualCamera::AddPropertyToCollection(IFSMCameraDeviceProperties *,_DEVPROPKEY const &,ulong,uchar const *,unsigned __int64)
0x180020edf  mov     edi, eax
0x180020ee1  test    eax, eax
0x180020ee3  jns     short loc_180020EFC
0x180020ee5  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020eec  jb      loc_180021C00
0x180020ef2  mov     edx, 0A5h
0x180020ef7  jmp     loc_180021BE2
0x180020efc  lea     r9, [rbp+57h+var_A8]
0x180020f00  mov     rcx, rbx; pszDeviceInterface
0x180020f03  lea     r8, [rbp+57h+var_60]
0x180020f07  lea     rdx, DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceId; PropertyKey
0x180020f0e  call    ?LoadStringDevProperty@FSMVirtualCamera@@SAJPEBGAEBU_DEVPROPKEY@@AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@PEAK@Z; FSMVirtualCamera::LoadStringDevProperty(ushort const *,_DEVPROPKEY const &,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &,ulong *)
0x180020f13  mov     edi, eax
0x180020f15  test    eax, eax
0x180020f17  jns     short loc_180020F30
0x180020f19  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020f20  jb      loc_180021C00
0x180020f26  mov     edx, 0A6h
0x180020f2b  jmp     loc_180021BE2
0x180020f30  mov     rbx, [rbp+57h+var_60]
0x180020f34  test    rbx, rbx
0x180020f37  jnz     short loc_180020F57
0x180020f39  mov     eax, 0C00D3E8Dh
0x180020f3e  mov     edi, eax
0x180020f40  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r13b; MFWppLevels g_wppLevels
0x180020f47  jb      loc_180021C00
0x180020f4d  mov     edx, 0A7h
  ... truncated ...
```
