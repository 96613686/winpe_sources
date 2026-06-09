# ImpGenerateAndPublishCameraTelemetry

- ea: `0x1800544c4`
- end: `0x1800553d0`
- name: `ImpGenerateAndPublishCameraTelemetry`
- size: `3852`
- prototype: ``
- caller_count: `1`
- callee_count: `43`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003bde0`

## callees

- `0x18000136c`
- `0x180003740`
- `0x180003ac0`
- `0x180005fa0`
- `0x180008f9c`
- `0x18000d1f0`
- `0x18000ec30`
- `0x18000f5a0`
- `0x1800133fc`
- `0x1800158b8`
- `0x180015d60`
- `0x180015e80`
- `0x1800176c0`
- `0x18001bd24`
- `0x18001c854`
- `0x18001c96c`
- `0x180024070`
- `0x180025ed0`
- `0x1800261a8`
- `0x180028d34`
- `0x180028d5c`
- `0x180028e5c`
- `0x180028eb4`
- `0x18002c008`
- `0x1800329bc`
- `0x180035004`
- `0x180036258`
- `0x180036284`
- `0x180038e74`
- `0x18003b370`
- `0x18003ba1c`
- `0x18003ba48`
- `0x18003f6b8`
- `0x18003f950`
- `0x180044b28`
- `0x180044f30`
- `0x180045900`
- `0x1800544c4`
- `0x1800586cc`
- `0x1800588d4`
- `0x180058d24`
- `0x180076274`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800546f4`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1800546f4`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800552bd`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x1800552bd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054ed9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180054ed9`
- `MFPlat!MFGetSystemTime` at `0x18005450f`
- `MFPlat!MFGetSystemTime` at `0x18005450f`

## string_xrefs

- `0x180054c35`: `CacheUVCControl`
- `0x180054f3a`: `EnableImageReplacement`

## pseudocode

```c
__int64 __fastcall ImpGenerateAndPublishCameraTelemetry(int a1)
{
  int v1; // edi
  int v2; // eax
  unsigned int v3; // r15d
  __int64 v4; // rdx
  unsigned int ValueW; // eax
  __int64 v6; // rdx
  unsigned __int64 v7; // r9
  __int64 v8; // rdx
  __int64 v9; // r9
  void **i; // rbx
  const unsigned __int16 *v11; // rdx
  unsigned __int64 v12; // rbx
  void **unique; // rax
  unsigned __int16 *v14; // rsi
  __int64 v15; // rcx
  void **v16; // rbx
  unsigned __int16 *v17; // r14
  const unsigned __int16 *v18; // r8
  __int64 v19; // rdx
  int v20; // eax
  __int64 v21; // r13
  unsigned __int16 *v22; // rdi
  unsigned __int16 *v23; // r15
  DEVPROPKEY *v24; // r14
  bool v25; // zf
  unsigned int v26; // r8d
  unsigned int v27; // r8d
  __int64 v28; // rdx
  __int64 v29; // rcx
  unsigned __int64 v30; // rax
  const WCHAR *v31; // rcx
  const unsigned __int16 *v32; // rcx
  __int64 v33; // r13
  char *v34; // rdi
  unsigned __int16 *v35; // rdi
  unsigned __int64 v36; // rax
  const WCHAR *v37; // rcx
  unsigned __int16 *v38; // rdi
  unsigned __int64 v39; // rax
  unsigned __int16 *v40; // r13
  struct IMFMediaType *v41; // rdi
  struct IMFMediaType *v42; // rdi
  __int64 v43; // r14
  __int64 (__fastcall *v44)(__int64, unsigned __int64 *); // rdi
  int v45; // eax
  int v46; // edi
  __int64 v47; // rax
  int (__fastcall *v48)(unsigned __int64, __int64 *, __int64 *, int *); // rax
  bool v49; // r14
  _DWORD *v50; // rcx
  int v51; // r8d
  double v52; // xmm2_8
  double v53; // xmm1_8
  int v54; // edi
  GuidTrace *v55; // rcx
  int v56; // r8d
  const char *String; // rax
  __int64 v58; // rcx
  void *v59; // rbx
  _QWORD *v60; // rdx
  char *v61; // rcx
  __int64 v62; // rax
  void *v63; // rbx
  _QWORD *v64; // rdx
  char *v65; // rcx
  __int64 v66; // rax
  unsigned int *pvData; // [rsp+28h] [rbp-E8h]
  unsigned int *pvDatac; // [rsp+28h] [rbp-E8h]
  unsigned int *pvDataa; // [rsp+28h] [rbp-E8h]
  unsigned int *pvDatab; // [rsp+28h] [rbp-E8h]
  DWORD pcbData; // [rsp+94h] [rbp-7Ch] BYREF
  unsigned int v74; // [rsp+98h] [rbp-78h]
  unsigned __int64 v75; // [rsp+A0h] [rbp-70h] BYREF
  int v76; // [rsp+A8h] [rbp-68h]
  unsigned int v77[2]; // [rsp+B0h] [rbp-60h] BYREF
  int v78; // [rsp+B8h] [rbp-58h] BYREF
  unsigned __int8 v79[4]; // [rsp+BCh] [rbp-54h] BYREF
  BYTE v80[4]; // [rsp+C0h] [rbp-50h] BYREF
  int v81; // [rsp+C4h] [rbp-4Ch] BYREF
  LPVOID pv; // [rsp+C8h] [rbp-48h] BYREF
  struct IMFSensorGroup *v83; // [rsp+D0h] [rbp-40h] BYREF
  unsigned __int8 v84[8]; // [rsp+D8h] [rbp-38h] BYREF
  struct IMFMediaType *v85; // [rsp+E0h] [rbp-30h] BYREF
  struct IMFMediaType *v86; // [rsp+E8h] [rbp-28h] BYREF
  struct IMFMediaType *v87; // [rsp+F0h] [rbp-20h] BYREF
  HKEY hkey; // [rsp+F8h] [rbp-18h] BYREF
  unsigned __int16 *v89; // [rsp+100h] [rbp-10h] BYREF
  __int64 v90; // [rsp+108h] [rbp-8h]
  void *v91[2]; // [rsp+110h] [rbp+0h] BYREF
  __int64 v92; // [rsp+120h] [rbp+10h]
  DWORD pdwType; // [rsp+128h] [rbp+18h] BYREF
  void *Block[2]; // [rsp+130h] [rbp+20h] BYREF
  __int64 v95; // [rsp+140h] [rbp+30h]
  unsigned __int64 v96; // [rsp+148h] [rbp+38h] BYREF
  struct _FILETIME v97; // [rsp+150h] [rbp+40h] BYREF
  BYTE Data[8]; // [rsp+158h] [rbp+48h] BYREF
  unsigned __int64 v99; // [rsp+160h] [rbp+50h]
  int v100; // [rsp+168h] [rbp+58h]
  LPVOID *p_pv; // [rsp+170h] [rbp+60h] BYREF
  __int64 v102; // [rsp+178h] [rbp+68h] BYREF
  char v103; // [rsp+180h] [rbp+70h]
  _BYTE v104[32]; // [rsp+188h] [rbp+78h] BYREF
  DEVPROPKEY PropertyKey; // [rsp+1A8h] [rbp+98h] BYREF
  unsigned __int16 *v106; // [rsp+1C0h] [rbp+B0h]
  __int64 v107[12]; // [rsp+1C8h] [rbp+B8h] BYREF
  __int64 v108; // [rsp+228h] [rbp+118h]
  DEVPROPKEY Buf1[7]; // [rsp+230h] [rbp+120h] BYREF
  __int128 v110; // [rsp+2BCh] [rbp+1ACh]
  int v111; // [rsp+2CCh] [rbp+1BCh]
  __int128 v112; // [rsp+2D0h] [rbp+1C0h]
  int v113; // [rsp+2E0h] [rbp+1D0h]
  __int128 v114; // [rsp+2E4h] [rbp+1D4h]
  int v115; // [rsp+2F4h] [rbp+1E4h]
  char v116; // [rsp+2F8h] [rbp+1E8h] BYREF

  v74 = 0;
  v1 = a1;
  v81 = 0;
  pcbData = 0;
  v97 = 0;
  hkey = 0;
  pdwType = 0;
  *(_QWORD *)Data = MFGetSystemTime();
  Buf1[0] = DEVPKEY_Device_Service;
  Buf1[1] = DEVPKEY_Device_DriverVersion;
  Buf1[2] = DEVPKEY_Device_DriverDate;
  Buf1[3] = DEVPKEY_Device_DriverDesc;
  Buf1[4] = DEVPKEY_Device_Manufacturer;
  Buf1[5] = DEVPKEY_Device_HardwareIds;
  Buf1[6] = DEVPKEY_Device_EnumeratorName;
  v111 = 8195;
  v113 = 8194;
  v115 = 12289;
  v91[0] = v91;
  v91[1] = v91;
  Block[0] = Block;
  v96 = 0;
  v89 = 0;
  *(_DWORD *)v80 = 0;
  *(_DWORD *)v84 = 0;
  v87 = 0;
  v86 = 0;
  v85 = 0;
  v110 = DEVPKEY_PNPX_ModelNumber;
  v83 = 0;
  v92 = 0;
  Block[1] = Block;
  v112 = DEVPKEY_PNPX_ModelName;
  v95 = 0;
  v114 = DEVPKEY_PNPX_FirmwareVersion;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v2 = OpenSensorGroupRegistryKey(0, 131359, 0, &hkey);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_119;
    v4 = 169;
    goto LABEL_4;
  }
  pcbData = 8;
  ValueW = RegGetValueW(hkey, 0, L"LastCensusReportTime", 0x48u, &pdwType, &v96, &pcbData);
  v7 = v96;
  if ( !ValueW && *(_QWORD *)Data >= v96 && !v1 )
  {
    v6 = 864000000000LL;
    if ( *(_QWORD *)Data - v96 < 0xC92A69C000LL )
    {
      v3 = 0;
      goto LABEL_119;
    }
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_DII(*((_QWORD *)WPP_GLOBAL_Control + 27), 170, *(_QWORD *)Data, ValueW, *(_QWORD *)Data, v96);
  LOBYTE(v6) = 1;
  v2 = FSEnumDeviceInterfaces(&GUID_e5323777_f976_4f5b_9b55_b94699c46e44, v6, v91, v7);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( g_wppLevels )
    {
      v4 = 171;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v2);
      goto LABEL_119;
    }
    goto LABEL_119;
  }
  LOBYTE(v8) = 1;
  v2 = FSEnumDeviceInterfaces(&GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca, v8, Block, v9);
  v3 = v2;
  if ( v2 >= 0 )
  {
    for ( i = (void **)Block[0]; i != Block; i = (void **)*i )
    {
      v11 = (const unsigned __int16 *)i[2];
      *(_DWORD *)v79 = 0;
      if ( FSGetAliasDeviceName2(1, v11, &GUID_e5323777_f976_4f5b_9b55_b94699c46e44, 0, 0, (unsigned int *)v79) == -1072875819 )
        utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::push_back(
          v91,
          i + 2);
    }
    v81 = v92;
    if ( !(_DWORD)v92 )
    {
      v3 = 0;
      goto LABEL_119;
    }
    v12 = 8408LL * (unsigned int)v92;
    unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v75, v12);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=((void **)&v89, unique);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v75);
    v14 = v89;
    if ( !v89 )
    {
      v3 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          173,
          &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
          0,
          -2147024882);
      goto LABEL_119;
    }
    memset_0(v89, 0, v12);
    v16 = (void **)v91[0];
    v17 = v14;
LABEL_29:
    if ( v16 == v91 )
    {
      if ( (unsigned int)dword_18008B170 > 5 && (unsigned __int8)tlgKeywordOn(v15, 0x800000000000LL) )
      {
        v99 = __PAIR64__(HIDWORD(v89), (unsigned int)v14);
        v75 = (unsigned __int64)&v81;
        v100 = (_DWORD)v17 - (_DWORD)v14;
        v76 = 2;
        v90 = 50333696;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
          v58,
          (__int64)&byte_180083837);
      }
      RegSetValueExW(hkey, L"LastCensusReportTime", 0, 0xBu, Data, 8u);
      goto LABEL_118;
    }
    memset_0(v107, 0, 0x68u);
    v18 = (const unsigned __int16 *)v16[2];
    v19 = (_BYTE *)v16[3] - (_BYTE *)v18;
    *(_DWORD *)v79 = 0;
    v106 = v17;
    v20 = StringCchCopyW(v17, (v19 >> 1) + 1, v18);
    v3 = v20;
    if ( v20 < 0 )
    {
      if ( g_wppLevels )
      {
        v28 = 174;
        goto LABEL_38;
      }
LABEL_118:
      v1 = a1;
      goto LABEL_119;
    }
    LODWORD(v21) = 1;
    v22 = &v17[(((_BYTE *)v16[3] - (_BYTE *)v16[2]) >> 1) + 1];
    v23 = v22;
    pv = v22;
    v24 = Buf1;
    while ( 1 )
    {
      v25 = v24->pid == 2;
      v77[0] = 0;
      v75 = 0;
      v107[(unsigned int)v21 - 1] = (__int64)v22;
      if ( v25 && !memcmp_0(v24, &DEVPKEY_Device_DriverDate, 0x10u) )
      {
        if ( (int)FSGetDeviceNodeProperty(
                    (LPCWSTR)v16[2],
                    (DEVPROPKEY *)&DEVPKEY_Device_DriverDate,
                    (PBYTE)&v97,
                    8u,
                    &pcbData) < 0 )
          goto LABEL_42;
        GetSystemDate(&v97, v22, v26);
        v20 = StringCchLengthW(v22, 0x40u, &v75);
        v3 = v20;
        if ( v20 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_118;
          v28 = 176;
          goto LABEL_38;
        }
      }
      else
      {
        if ( (int)FSGetDeviceNodeProperty((LPCWSTR)v16[2], v24, (PBYTE)v22, 0x206u, v77) < 0 )
          goto LABEL_42;
        v29 = v77[0] >> 1;
        v23[v29] = 0;
        v20 = StringCchLengthW(v22, (unsigned int)(v29 + 1), &v75);
        v3 = v20;
        if ( v20 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_118;
          v28 = 175;
          goto LABEL_38;
        }
      }
      v30 = v75 + 1;
      if ( v75 == -1 || v75 == 0 )
      {
LABEL_42:
        v20 = StringCchCopyW(v22, 5u, L"N.A.");
        v3 = v20;
        if ( v20 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_118;
          v28 = 177;
          goto LABEL_38;
        }
        v30 = 5;
      }
      v21 = (unsigned int)(v21 + 1);
      ++v24;
      v22 = (unsigned __int16 *)((char *)pv + 2 * v30);
      pv = v22;
      v23 = v22;
      if ( v24 == (DEVPROPKEY *)&v116 )
      {
        v31 = (const WCHAR *)v16[2];
        v107[v21 - 1] = (__int64)v22;
        v75 = 0;
        GrabPanelInformation(v31, v22, v27);
        v20 = StringCchLengthW(v22, 0x40u, &v75);
        v3 = v20;
        if ( v20 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_118;
          v28 = 178;
        }
        else
        {
          v32 = (const unsigned __int16 *)v16[2];
          v33 = (unsigned int)(v21 + 1);
          v77[0] = 0;
          v78 = 0;
          v34 = (char *)&v22[v75];
          v75 = 260;
          v35 = (unsigned __int16 *)(v34 + 2);
          v107[v33 - 1] = (__int64)v35;
          GetDMFTCLSIds(v32, v35, &v75, (int *)v77, &v78);
          v36 = v75;
          if ( v75 <= 1 )
          {
            v20 = StringCchCopyW(v35, 5u, L"N.A.");
            v3 = v20;
            if ( v20 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_118;
              v28 = 179;
              goto LABEL_38;
            }
            v36 = 4;
            v75 = 4;
          }
          v37 = (const WCHAR *)v16[2];
          v38 = &v35[v36 + 1];
          PropertyKey.pid = 25;
          v107[(unsigned int)(v33 + 1) - 1] = (__int64)v38;
          PropertyKey.fmtid = (DEVPROPGUID)SensorGroupFMTGUID;
          if ( (int)FSGetDeviceInterfaceProperty2(
                      v37,
                      &PropertyKey,
                      0x12u,
                      (unsigned __int8 *)v38,
                      0x618u,
                      (unsigned int *)&pv) >= 0 )
          {
            v20 = StringCchLengthW(v38, 0x30Cu, &v75);
            v3 = v20;
            if ( v20 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_118;
              v28 = 181;
              goto LABEL_38;
            }
            v39 = v75;
          }
          else
          {
            v20 = StringCchCopyW(v38, 5u, L"N.A.");
            v3 = v20;
            if ( v20 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_118;
              v28 = 180;
              goto LABEL_38;
            }
            v39 = 4;
          }
          v40 = &v38[v39 + 1];
          v90 = (__int64)v40;
          memset_0(v40, 0, 0x58u);
          v17 = v40 + 44;
          v99 = (unsigned __int64)(v40 + 44);
          *((_DWORD *)v40 + 3) = (v77[0] != 0) | (v78 != 0 ? 2 : 0);
          *(_DWORD *)v80 = 0;
          FSGetDeviceNodeRegistryEntry((LPCWSTR)v16[2], L"EnableDshowRedirection", v80, 4u, &pcbData);
          *((_DWORD *)v40 + 3) |= 4 * *(_DWORD *)v80;
          FSGetDeviceNodeRegistryEntry((LPCWSTR)v16[2], L"CacheUVCControl", (LPBYTE)v40, 4u, &pcbData);
          FSGetDeviceInterfaceRegistryEntry2(
            (const unsigned __int16 *)v16[2],
            L"CPV2FaceAuth",
            (unsigned __int8 *)v40 + 4,
            4u,
            &pcbData,
            pvData);
          FSGetDeviceInterfaceRegistryEntry2(
            (const unsigned __int16 *)v16[2],
            L"FSSensorOrientation",
            (unsigned __int8 *)v40 + 8,
            4u,
            &pcbData,
            pvDatac);
          wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v83);
          wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v87);
          wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v86);
          wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v85);
          wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v83);
          v20 = MFCreateSensorGroup(v16[2], &v83);
          v3 = v20;
          if ( v20 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_118;
            v28 = 182;
          }
          else
          {
            wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v85);
            wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v86);
            wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v87);
            v20 = PopulateMFDeviceStreamInfo(v83, &v87, &v86, &v85);
            v3 = v20;
            if ( v20 >= 0 )
            {
              v41 = v87;
              if ( v87 )
              {
                MFGetAttribute2UINT32asUINT64(v87, &MF_MT_FRAME_RATE, v40 + 24, v40 + 26);
                MFGetAttribute2UINT32asUINT64(v41, &MF_MT_FRAME_SIZE, v40 + 20, v40 + 22);
              }
              v42 = v86;
              if ( v86 )
              {
                MFGetAttribute2UINT32asUINT64(v86, &MF_MT_FRAME_RATE, v40 + 16, v40 + 18);
                MFGetAttribute2UINT32asUINT64(v42, &MF_MT_FRAME_SIZE, v40 + 12, v40 + 14);
              }
              if ( v85 )
                MFGetAttribute2UINT32asUINT64(v85, &MF_MT_FRAME_SIZE, v40 + 28, v40 + 30);
              if ( (int)FSGetDeviceInterfaceProperty2(
                          (LPCWSTR)v16[2],
                          (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_EffectsClsid,
                          0xDu,
                          (unsigned __int8 *)v40 + 64,
                          0x10u,
                          &pcbData) < 0 )
                *((GUID *)v40 + 4) = GUID_00000000_0000_0000_0000_000000000000;
              if ( v83 )
              {
                *(_QWORD *)v77 = 0;
                if ( (*(int (__fastcall **)(struct IMFSensorGroup *, _QWORD, unsigned int *))(*(_QWORD *)v83 + 56LL))(
                       v83,
                       0,
                       v77) >= 0 )
                {
                  v43 = *(_QWORD *)v77;
                  v75 = 0;
                  v78 = 0;
                  pv = 0;
                  v44 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *))(**(_QWORD **)v77 + 56LL);
                  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&v75);
                  v45 = v44(v43, &v75);
                  v46 = v74;
                  v49 = 0;
                  if ( v45 >= 0 )
                  {
                    if ( v75 )
                    {
                      v47 = *(_QWORD *)v75;
                      p_pv = &pv;
                      v46 = v74 | 1;
                      v102 = 0;
                      v74 |= 1u;
                      v48 = *(int (__fastcall **)(unsigned __int64, __int64 *, __int64 *, int *))(v47 + 128);
                      v103 = 1;
                      if ( v48(v75, FSSensorGroupCameraCapabiltiesBlob, &v102, &v78) >= 0 )
                        v49 = 1;
                    }
                  }
                  if ( (v46 & 1) != 0 )
                  {
                    v74 = v46 & 0xFFFFFFFE;
                    wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
                  }
                  v50 = pv;
                  if ( v49 )
                  {
                    *((_DWORD *)v40 + 4) = *((unsigned __int8 *)pv + 4)
                                         | (2 * (*((unsigned __int8 *)pv + 5) | (2 * *((unsigned __int8 *)pv + 6))));
                    *((_DWORD *)v40 + 5) = v50[2];
                  }
                  pv = 0;
                  if ( v50 )
                    CoTaskMemFree(v50);
                  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v75);
                  v17 = (unsigned __int16 *)v99;
                }
                wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)v77);
              }
              if ( (int)FSGetDeviceInterfaceRegistryEntry2(
                          (const unsigned __int16 *)v16[2],
                          L"FSColorInfoOverride",
                          v79,
                          4u,
                          &pcbData,
                          pvDataa) >= 0 )
                *((_DWORD *)v40 + 20) = *(_DWORD *)v79;
              if ( (int)FSGetDeviceInterfaceRegistryEntry2(
                          (const unsigned __int16 *)v16[2],
                          L"EnableImageReplacement",
                          v84,
                          4u,
                          &pcbData,
                          pvDatab) >= 0 )
                *((_DWORD *)v40 + 21) = *(_DWORD *)v84;
              if ( (unsigned __int8)byte_18008D62D >= 8u )
              {
                WPP_SF_SSSSSSSSSSSS(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  184,
                  v51,
                  (_DWORD)v106,
                  v107[0],
                  v107[1],
                  v107[2],
                  v107[3],
                  v107[4],
                  v107[5],
                  v107[6],
                  v107[7],
                  v107[8],
                  v107[9],
                  v107[10]);
                if ( (unsigned __int8)byte_18008D62D >= 8u )
                {
                  LOBYTE(v52) = 0;
                  if ( *((_DWORD *)v40 + 13) )
                    v52 = (double)*((int *)v40 + 12) / (double)*((int *)v40 + 13);
                  LOBYTE(v53) = 0;
                  if ( *((_DWORD *)v40 + 9) )
                    v53 = (double)*((int *)v40 + 8) / (double)*((int *)v40 + 9);
                  WPP_SF_DDgDDgDDdDdddd(
                    *((_QWORD *)WPP_GLOBAL_Control + 27),
                    185,
                    *((_DWORD *)v40 + 10),
                    *((_DWORD *)v40 + 6),
                    *((_DWORD *)v40 + 7),
                    SLOBYTE(v53),
                    *((_DWORD *)v40 + 10),
                    *((_DWORD *)v40 + 11),
                    SLOBYTE(v52),
                    *((_DWORD *)v40 + 14),
                    *((_DWORD *)v40 + 15),
                    *(_DWORD *)v40,
                    *((_DWORD *)v40 + 1),
                    *((_DWORD *)v40 + 2),
                    *((_DWORD *)v40 + 4),
                    *((_DWORD *)v40 + 5),
                    *((_DWORD *)v40 + 21));
                  if ( (unsigned __int8)byte_18008D62D >= 8u )
                  {
                    v54 = *((_DWORD *)v40 + 20);
                    v74 |= 2u;
                    v55 = GuidTrace::GuidTrace((GuidTrace *)v104, (const struct _GUID *)v40 + 4);
                    String = (const char *)*((_QWORD *)v55 + 3);
                    if ( !String )
                      String = FSString::GetString(v55);
                    WPP_SF_SdsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 27),
                      186,
                      v56,
                      v108,
                      *((_DWORD *)v40 + 3),
                      (__int64)String,
                      v54);
                  }
                }
              }
              if ( (v74 & 2) != 0 )
              {
                v74 &= ~2u;
                FSString::~FSString((FSString *)v104);
              }
              v16 = (void **)*v16;
              goto LABEL_29;
            }
            if ( !g_wppLevels )
              goto LABEL_118;
            v28 = 183;
          }
        }
LABEL_38:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v20);
        goto LABEL_118;
      }
    }
  }
  if ( g_wppLevels )
  {
    v4 = 172;
    goto LABEL_4;
  }
LABEL_119:
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 27), 187, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, v3, v81, v1);
  while ( 1 )
  {
    v59 = Block[0];
    if ( Block[0] == Block )
      break;
    v60 = (_QWORD *)*((_QWORD *)Block[0] + 1);
    v61 = (char *)Block[0] + 16;
    v62 = *(_QWORD *)Block[0];
    *v60 = *(_QWORD *)Block[0];
    *(_QWORD *)(v62 + 8) = v60;
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v61);
    operator delete(v59);
  }
  v95 = 0;
  while ( 1 )
  {
    v63 = v91[0];
    if ( v91[0] == v91 )
      break;
    v64 = (_QWORD *)*((_QWORD *)v91[0] + 1);
    v65 = (char *)v91[0] + 16;
    v66 = *(_QWORD *)v91[0];
    *v64 = *(_QWORD *)v91[0];
    *(_QWORD *)(v66 + 8) = v64;
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v65);
    operator delete(v63);
  }
  v92 = 0;
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v83);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v85);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v86);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v87);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v89);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v3;
}

```

## disassembly

```asm
0x1800544c4  push    rbp
0x1800544c6  push    rbx
0x1800544c7  push    rsi
0x1800544c8  push    rdi
0x1800544c9  push    r13
0x1800544cb  push    r14
0x1800544cd  push    r15
0x1800544cf  lea     rbp, [rsp-200h]
0x1800544d7  sub     rsp, 310h
0x1800544de  mov     rax, cs:__security_cookie
0x1800544e5  xor     rax, rsp
0x1800544e8  mov     [rbp+230h+var_40], rax
0x1800544ef  xor     r13d, r13d
0x1800544f2  mov     [rbp+230h+var_2B0], ecx
0x1800544f5  mov     [rbp+230h+var_2A8], r13d
0x1800544f9  mov     edi, ecx
0x1800544fb  mov     [rbp+230h+var_27C], r13d
0x1800544ff  mov     [rbp+230h+var_2AC], r13d
0x180054503  mov     qword ptr [rbp+230h+var_1F0.dwLowDateTime], r13
0x180054507  mov     [rbp+230h+hkey], r13
0x18005450b  mov     [rbp+230h+var_218], r13d
0x18005450f  call    cs:__imp_MFGetSystemTime
0x180054515  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_Service.fmtid.Data1
0x18005451c  mov     qword ptr [rbp+230h+Data], rax
0x180054520  lea     rcx, [rbp+230h+hkey]
0x180054524  mov     eax, cs:DEVPKEY_Device_Service.pid
0x18005452a  xor     edx, edx
0x18005452c  mov     [rbp+230h+var_100], eax
0x180054532  mov     eax, cs:DEVPKEY_Device_DriverVersion.pid
0x180054538  mov     [rbp+230h+var_EC], eax
0x18005453e  mov     eax, cs:DEVPKEY_Device_DriverDate.pid
0x180054544  mov     [rbp+230h+var_D8], eax
0x18005454a  mov     eax, cs:DEVPKEY_Device_DriverDesc.pid
0x180054550  mov     [rbp+230h+var_C4], eax
0x180054556  mov     eax, cs:DEVPKEY_Device_Manufacturer.pid
0x18005455c  movaps  [rbp+230h+Buf1], xmm0
0x180054563  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverVersion.fmtid.Data1
0x18005456a  mov     [rbp+230h+var_B0], eax
0x180054570  mov     eax, cs:DEVPKEY_Device_HardwareIds.pid
0x180054576  movups  [rbp+230h+var_FC], xmm0
0x18005457d  mov     [rbp+230h+var_9C], eax
0x180054583  mov     eax, cs:DEVPKEY_Device_EnumeratorName.pid
0x180054589  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverDate.fmtid.Data1
0x180054590  mov     [rbp+230h+var_88], eax
0x180054596  mov     eax, cs:dword_18007E310
0x18005459c  movups  [rbp+230h+var_E8], xmm0
0x1800545a3  mov     [rbp+230h+var_74], eax
0x1800545a9  mov     eax, cs:dword_18007E450
0x1800545af  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverDesc.fmtid.Data1
0x1800545b6  mov     [rbp+230h+var_60], eax
0x1800545bc  mov     eax, cs:dword_18007E410
0x1800545c2  movups  [rbp+230h+var_D4], xmm0
0x1800545c9  mov     [rbp+230h+var_4C], eax
0x1800545cf  lea     rax, [rbp+230h+var_230]
0x1800545d3  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_Manufacturer.fmtid.Data1
0x1800545da  mov     [rbp+230h+var_230], rax
0x1800545de  lea     rax, [rbp+230h+var_230]
0x1800545e2  mov     [rbp+230h+var_228], rax
0x1800545e6  lea     rax, [rbp+230h+Block]
0x1800545ea  movaps  [rbp+230h+var_C0], xmm0
0x1800545f1  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_HardwareIds.fmtid.Data1
0x1800545f8  mov     [rbp+230h+Block], rax
0x1800545fc  lea     rax, [rbp+230h+Block]
0x180054600  mov     [rbp+230h+var_1F8], r13
0x180054604  movups  [rbp+230h+var_AC], xmm0
0x18005460b  mov     [rbp+230h+var_240], r13
0x18005460f  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_EnumeratorName.fmtid.Data1
0x180054616  mov     dword ptr [rbp+230h+var_280], r13d
0x18005461a  mov     dword ptr [rbp+230h+var_268], r13d
0x18005461e  movups  [rbp+230h+var_98], xmm0
0x180054625  mov     [rbp+230h+var_250], r13
0x180054629  movups  xmm0, cs:DEVPKEY_PNPX_ModelNumber
0x180054630  mov     [rbp+230h+var_258], r13
0x180054634  mov     [rbp+230h+var_260], r13
0x180054638  movups  [rbp+230h+var_84], xmm0
0x18005463f  mov     [rbp+230h+var_270], r13
0x180054643  movups  xmm0, cs:DEVPKEY_PNPX_ModelName
0x18005464a  mov     [rbp+230h+var_220], r13
0x18005464e  mov     [rbp+230h+var_208], rax
0x180054652  movaps  [rbp+230h+var_70], xmm0
0x180054659  movups  xmm0, cs:DEVPKEY_PNPX_FirmwareVersion
0x180054660  mov     [rbp+230h+var_200], r13
0x180054664  movups  [rbp+230h+var_5C], xmm0
0x18005466b  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180054670  lea     r9, [rbp+230h+hkey]; HKEY *
0x180054674  xor     r8d, r8d; bool *
0x180054677  mov     edx, 2011Fh; unsigned int
0x18005467c  xor     ecx, ecx; unsigned __int16 *
0x18005467e  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x180054683  mov     r15d, eax
0x180054686  test    eax, eax
0x180054688  jns     short loc_1800546BF
0x18005468a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180054691  jb      loc_1800552C6
0x180054697  mov     edx, 0A9h
0x18005469c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800546a3  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x1800546aa  xor     r9d, r9d
0x1800546ad  mov     dword ptr [rsp+340h+pdwType], eax
0x1800546b1  mov     rcx, [rcx+10h]
0x1800546b5  call    WPP_SF_qD
0x1800546ba  jmp     loc_1800552C6
0x1800546bf  mov     rcx, [rbp+230h+hkey]; hkey
0x1800546c3  lea     rax, [rbp+230h+var_2AC]
0x1800546c7  mov     [rsp+340h+pcbData], rax; pcbData
0x1800546cc  lea     r8, aLastcensusrepo; "LastCensusReportTime"
0x1800546d3  lea     rax, [rbp+230h+var_1F8]
0x1800546d7  mov     [rbp+230h+var_2AC], 8
0x1800546de  mov     [rsp+340h+pvData], rax; pvData
0x1800546e3  mov     r9d, 48h ; 'H'; dwFlags
0x1800546e9  lea     rax, [rbp+230h+var_218]
0x1800546ed  xor     edx, edx; lpSubKey
0x1800546ef  mov     [rsp+340h+pdwType], rax; pdwType
0x1800546f4  call    cs:__imp_RegGetValueW
0x1800546fa  mov     r8, qword ptr [rbp+230h+Data]
0x1800546fe  mov     r9, [rbp+230h+var_1F8]
0x180054702  test    eax, eax
0x180054704  jnz     short loc_18005472C
0x180054706  cmp     r8, r9
0x180054709  jb      short loc_18005472C
0x18005470b  test    edi, edi
0x18005470d  jnz     short loc_18005472C
0x18005470f  mov     rcx, r8
0x180054712  mov     rdx, 0C92A69C000h
0x18005471c  sub     rcx, r9
0x18005471f  cmp     rcx, rdx
0x180054722  jnb     short loc_18005472C
0x180054724  xor     r15d, r15d
0x180054727  jmp     loc_1800552C6
0x18005472c  cmp     cs:byte_18008D62D, 8
0x180054733  jb      short loc_18005475A
0x180054735  mov     rcx, cs:WPP_GLOBAL_Control
0x18005473c  mov     edx, 0AAh
0x180054741  mov     [rsp+340h+pvData], r9
0x180054746  mov     r9d, eax
0x180054749  mov     [rsp+340h+pdwType], r8
0x18005474e  mov     rcx, [rcx+0D8h]
0x180054755  call    WPP_SF_DII
0x18005475a  lea     r8, [rbp+230h+var_230]
0x18005475e  mov     dl, 1
0x180054760  lea     rcx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x180054767  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x18005476c  mov     r15d, eax
0x18005476f  test    eax, eax
0x180054771  jns     short loc_18005478A
0x180054773  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005477a  jb      loc_1800552C6
0x180054780  mov     edx, 0ABh
0x180054785  jmp     loc_18005469C
0x18005478a  lea     r8, [rbp+230h+Block]
0x18005478e  mov     dl, 1
0x180054790  lea     rcx, _GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca
0x180054797  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x18005479c  mov     r15d, eax
0x18005479f  test    eax, eax
0x1800547a1  jns     short loc_1800547BA
0x1800547a3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800547aa  jb      loc_1800552C6
0x1800547b0  mov     edx, 0ACh
0x1800547b5  jmp     loc_18005469C
0x1800547ba  mov     rbx, [rbp+230h+Block]
0x1800547be  lea     rax, [rbp+230h+Block]
0x1800547c2  cmp     rbx, rax
0x1800547c5  jz      short loc_180054807
0x1800547c7  mov     rdx, [rbx+10h]; unsigned __int16 *
0x1800547cb  lea     rax, [rbp+230h+var_284]
0x1800547cf  mov     [rsp+340h+pvData], rax; unsigned int *
0x1800547d4  lea     r8, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44; struct _GUID *
0x1800547db  xor     r9d, r9d; unsigned __int16 *
0x1800547de  mov     dword ptr [rsp+340h+pdwType], r13d; unsigned int
0x1800547e3  mov     cl, 1; bool
0x1800547e5  mov     dword ptr [rbp+230h+var_284], r13d
0x1800547e9  call    ?FSGetAliasDeviceName2@@YAJ_NPEBGAEBU_GUID@@PEAGKPEAK@Z; FSGetAliasDeviceName2(bool,ushort const *,_GUID const &,ushort *,ulong,ulong *)
0x1800547ee  cmp     eax, 0C00D36D5h
0x1800547f3  jnz     short loc_180054802
0x1800547f5  lea     rdx, [rbx+10h]
0x1800547f9  lea     rcx, [rbp+230h+var_230]
0x1800547fd  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::push_back(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180054802  mov     rbx, [rbx]
0x180054805  jmp     short loc_1800547BE
0x180054807  mov     rax, [rbp+230h+var_220]
0x18005480b  mov     [rbp+230h+var_27C], eax
0x18005480e  test    eax, eax
0x180054810  jnz     short loc_18005481A
0x180054812  xor     r15d, r15d
0x180054815  jmp     loc_1800552C6
0x18005481a  mov     eax, eax
0x18005481c  lea     rcx, [rbp+230h+var_2A0]
0x180054820  imul    rbx, rax, 20D8h
0x180054827  mov     rdx, rbx
0x18005482a  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x18005482f  mov     rdx, rax
0x180054832  lea     rcx, [rbp+230h+var_240]
0x180054836  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x18005483b  lea     rcx, [rbp+230h+var_2A0]
0x18005483f  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180054844  mov     rsi, [rbp+230h+var_240]
0x180054848  test    rsi, rsi
0x18005484b  jnz     short loc_180054889
0x18005484d  mov     r15d, 8007000Eh
0x180054853  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005485a  jb      loc_1800552C6
0x180054860  mov     rcx, cs:WPP_GLOBAL_Control
0x180054867  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x18005486e  mov     edx, 0ADh
0x180054873  mov     dword ptr [rsp+340h+pdwType], r15d
0x180054878  xor     r9d, r9d
0x18005487b  mov     rcx, [rcx+10h]
0x18005487f  call    WPP_SF_qD
0x180054884  jmp     loc_1800552C6
0x180054889  mov     r8, rbx; Size
0x18005488c  xor     edx, edx; Val
0x18005488e  mov     rcx, rsi; void *
0x180054891  call    memset_0
0x180054896  mov     rbx, [rbp+230h+var_230]
0x18005489a  mov     r14, rsi
0x18005489d  lea     rax, [rbp+230h+var_230]
0x1800548a1  cmp     rbx, rax
0x1800548a4  jz      loc_18005522C
0x1800548aa  xor     edx, edx; Val
0x1800548ac  lea     rcx, [rbp+230h+var_178]; void *
0x1800548b3  lea     r8d, [rdx+68h]; Size
0x1800548b7  call    memset_0
0x1800548bc  mov     r8, [rbx+10h]; unsigned __int16 *
0x1800548c0  mov     rcx, r14; unsigned __int16 *
0x1800548c3  mov     rdx, [rbx+18h]
0x1800548c7  sub     rdx, r8
0x1800548ca  mov     dword ptr [rbp+230h+var_284], 0
0x1800548d1  sar     rdx, 1
0x1800548d4  inc     rdx; unsigned __int64
0x1800548d7  mov     [rbp+230h+var_180], r14
0x1800548de  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800548e3  mov     r15d, eax
0x1800548e6  test    eax, eax
0x1800548e8  js      loc_180055215
0x1800548ee  mov     rdi, [rbx+18h]
0x1800548f2  mov     r13d, 1
0x1800548f8  sub     rdi, [rbx+10h]
0x1800548fc  sar     rdi, 1
0x1800548ff  add     r14, 2
0x180054903  lea     rdi, [r14+rdi*2]
0x180054907  mov     r15, rdi
0x18005490a  mov     [rbp+230h+pv], rdi
0x18005490e  lea     r14, [rbp+230h+Buf1]
0x180054915  cmp     dword ptr [r14+10h], 2
0x18005491a  mov     eax, r13d
0x18005491d  mov     [rbp+230h+var_290], 0
0x180054924  mov     [rbp+230h+var_2A0], 0
0x18005492c  mov     [rbp+rax*8+230h+var_180], rdi
0x180054934  jnz     loc_1800549DB
0x18005493a  mov     r8d, 10h; Size
0x180054940  lea     rdx, DEVPKEY_Device_DriverDate; Buf2
0x180054947  mov     rcx, r14; Buf1
0x18005494a  call    memcmp_0
0x18005494f  test    eax, eax
0x180054951  jnz     loc_1800549DB
0x180054957  mov     rcx, [rbx+10h]; pszDeviceInterface
0x18005495b  lea     rax, [rbp+230h+var_2AC]
0x18005495f  mov     r9d, 8; unsigned int
0x180054965  mov     [rsp+340h+pdwType], rax; unsigned int *
0x18005496a  lea     r8, [rbp+230h+var_1F0]; PropertyBuffer
0x18005496e  lea     rdx, DEVPKEY_Device_DriverDate; PropertyKey
0x180054975  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x18005497a  test    eax, eax
0x18005497c  js      loc_180054A30
0x180054982  mov     rdx, rdi; unsigned __int16 *
0x180054985  lea     rcx, [rbp+230h+var_1F0]; struct _FILETIME *
0x180054989  call    ?GetSystemDate@@YAXAEAU_FILETIME@@PEAGI@Z; GetSystemDate(_FILETIME &,ushort *,uint)
0x18005498e  lea     r8, [rbp+230h+var_2A0]; unsigned __int64 *
0x180054992  mov     edx, 40h ; '@'; unsigned __int64
0x180054997  mov     rcx, rdi; unsigned __int16 *
0x18005499a  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18005499f  mov     r15d, eax
0x1800549a2  test    eax, eax
0x1800549a4  jns     short loc_180054A23
0x1800549a6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800549ad  jb      loc_1800552C3
0x1800549b3  mov     edx, 0B0h
0x1800549b8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800549bf  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x1800549c6  xor     r9d, r9d
0x1800549c9  mov     dword ptr [rsp+340h+pdwType], eax
0x1800549cd  mov     rcx, [rcx+10h]
0x1800549d1  call    WPP_SF_qD
0x1800549d6  jmp     loc_1800552C3
0x1800549db  mov     rcx, [rbx+10h]; pszDeviceInterface
0x1800549df  lea     rax, [rbp+230h+var_290]
0x1800549e3  mov     r9d, 206h; unsigned int
0x1800549e9  mov     [rsp+340h+pdwType], rax; unsigned int *
0x1800549ee  mov     r8, rdi; PropertyBuffer
0x1800549f1  mov     rdx, r14; PropertyKey
0x1800549f4  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x1800549f9  test    eax, eax
0x1800549fb  js      short loc_180054A30
0x1800549fd  mov     ecx, [rbp+230h+var_290]
0x180054a00  lea     r8, [rbp+230h+var_2A0]; unsigned __int64 *
0x180054a04  shr     ecx, 1
0x180054a06  xor     eax, eax
0x180054a08  mov     [r15+rcx*2], ax
0x180054a0d  lea     edx, [rcx+1]; unsigned __int64
  ... truncated ...
```
