# LegacyGenerateAndPublishCameraTelemetry

- ea: `0x1800553d8`
- end: `0x180056215`
- name: `LegacyGenerateAndPublishCameraTelemetry`
- size: `3645`
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
- `0x1800553d8`
- `0x1800586cc`
- `0x1800588d4`
- `0x180058d24`
- `0x180076274`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180055608`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180055608`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056102`
- `api-ms-win-core-registry-l1-1-0!RegSetValueExW` at `0x180056102`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055d4c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055d4c`
- `MFPlat!MFGetSystemTime` at `0x180055423`
- `MFPlat!MFGetSystemTime` at `0x180055423`

## string_xrefs

- `0x180055aa8`: `CacheUVCControl`
- `0x180055dad`: `EnableImageReplacement`

## pseudocode

```c
__int64 __fastcall LegacyGenerateAndPublishCameraTelemetry(int a1)
{
  int v1; // edi
  int v2; // eax
  unsigned int v3; // r15d
  __int64 v4; // rdx
  unsigned int ValueW; // eax
  __int64 v6; // rdx
  unsigned int *v7; // r9
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
  unsigned __int16 *v33; // rdi
  unsigned __int16 *v34; // rdi
  unsigned __int64 v35; // rax
  unsigned __int16 *v36; // r13
  struct IMFMediaType *v37; // rdi
  struct IMFMediaType *v38; // rdi
  __int64 v39; // r14
  __int64 (__fastcall *v40)(__int64, unsigned __int64 *); // rdi
  int v41; // eax
  int v42; // edi
  __int64 v43; // rax
  int (__fastcall *v44)(unsigned __int64, __int64 *, __int64 *, int *); // rax
  bool v45; // r14
  _DWORD *v46; // rcx
  int v47; // r8d
  double v48; // xmm2_8
  double v49; // xmm1_8
  int v50; // edi
  GuidTrace *v51; // rcx
  int v52; // r8d
  const char *String; // rax
  __int64 v54; // rcx
  void *v55; // rbx
  _QWORD *v56; // rdx
  char *v57; // rcx
  __int64 v58; // rax
  void *v59; // rbx
  _QWORD *v60; // rdx
  char *v61; // rcx
  __int64 v62; // rax
  unsigned int *pvData; // [rsp+28h] [rbp-E8h]
  unsigned int *pvDatac; // [rsp+28h] [rbp-E8h]
  unsigned int *pvDataa; // [rsp+28h] [rbp-E8h]
  unsigned int *pvDatab; // [rsp+28h] [rbp-E8h]
  DWORD pcbData; // [rsp+94h] [rbp-7Ch] BYREF
  unsigned int v70; // [rsp+98h] [rbp-78h]
  unsigned __int64 v71; // [rsp+A0h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-68h] BYREF
  int v73; // [rsp+B0h] [rbp-60h] BYREF
  unsigned __int8 v74[4]; // [rsp+B4h] [rbp-5Ch] BYREF
  BYTE v75[4]; // [rsp+B8h] [rbp-58h] BYREF
  int v76; // [rsp+BCh] [rbp-54h] BYREF
  struct IMFSensorGroup *v77; // [rsp+C0h] [rbp-50h] BYREF
  unsigned __int8 v78[8]; // [rsp+C8h] [rbp-48h] BYREF
  struct IMFMediaType *v79; // [rsp+D0h] [rbp-40h] BYREF
  struct IMFMediaType *v80; // [rsp+D8h] [rbp-38h] BYREF
  struct IMFMediaType *v81; // [rsp+E0h] [rbp-30h] BYREF
  HKEY hkey; // [rsp+E8h] [rbp-28h] BYREF
  int *v83; // [rsp+F0h] [rbp-20h] BYREF
  int v84; // [rsp+F8h] [rbp-18h]
  unsigned __int16 *v85; // [rsp+100h] [rbp-10h] BYREF
  __int64 v86; // [rsp+108h] [rbp-8h]
  void *v87[2]; // [rsp+110h] [rbp+0h] BYREF
  __int64 v88; // [rsp+120h] [rbp+10h]
  DWORD pdwType; // [rsp+128h] [rbp+18h] BYREF
  void *Block[2]; // [rsp+130h] [rbp+20h] BYREF
  __int64 v91; // [rsp+140h] [rbp+30h]
  unsigned int *v92; // [rsp+148h] [rbp+38h] BYREF
  struct _FILETIME v93; // [rsp+150h] [rbp+40h] BYREF
  BYTE Data[8]; // [rsp+158h] [rbp+48h] BYREF
  unsigned __int64 v95; // [rsp+160h] [rbp+50h]
  int v96; // [rsp+168h] [rbp+58h]
  LPVOID *p_pv; // [rsp+170h] [rbp+60h] BYREF
  __int64 v98; // [rsp+178h] [rbp+68h] BYREF
  char v99; // [rsp+180h] [rbp+70h]
  _BYTE v100[40]; // [rsp+188h] [rbp+78h] BYREF
  unsigned __int16 *v101; // [rsp+1B0h] [rbp+A0h]
  __int64 v102[11]; // [rsp+1B8h] [rbp+A8h] BYREF
  __int64 v103; // [rsp+210h] [rbp+100h]
  DEVPROPKEY Buf1[7]; // [rsp+220h] [rbp+110h] BYREF
  __int128 v105; // [rsp+2ACh] [rbp+19Ch]
  int v106; // [rsp+2BCh] [rbp+1ACh]
  __int128 v107; // [rsp+2C0h] [rbp+1B0h]
  int v108; // [rsp+2D0h] [rbp+1C0h]
  __int128 v109; // [rsp+2D4h] [rbp+1C4h]
  int v110; // [rsp+2E4h] [rbp+1D4h]
  char v111; // [rsp+2E8h] [rbp+1D8h] BYREF

  v70 = 0;
  v1 = a1;
  v76 = 0;
  pcbData = 0;
  v93 = 0;
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
  v106 = 8195;
  v108 = 8194;
  v110 = 12289;
  v87[0] = v87;
  v87[1] = v87;
  Block[0] = Block;
  v92 = 0;
  v85 = 0;
  *(_DWORD *)v75 = 0;
  *(_DWORD *)v78 = 0;
  v81 = 0;
  v80 = 0;
  v79 = 0;
  v105 = DEVPKEY_PNPX_ModelNumber;
  v77 = 0;
  v88 = 0;
  Block[1] = Block;
  v107 = DEVPKEY_PNPX_ModelName;
  v91 = 0;
  v109 = DEVPKEY_PNPX_FirmwareVersion;
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
    &hkey,
    0);
  v2 = OpenSensorGroupRegistryKey(0, 131359, 0, &hkey);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_110;
    v4 = 188;
    goto LABEL_4;
  }
  pcbData = 8;
  ValueW = RegGetValueW(hkey, 0, L"LastCensusReportTime", 0x48u, &pdwType, &v92, &pcbData);
  v7 = v92;
  if ( !ValueW && *(_QWORD *)Data >= (unsigned __int64)v92 && !v1 )
  {
    v6 = 864000000000LL;
    if ( *(_QWORD *)Data - (_QWORD)v92 < 0xC92A69C000uLL )
    {
      v3 = 0;
      goto LABEL_110;
    }
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_DII(*((_QWORD *)WPP_GLOBAL_Control + 27), 189, *(_QWORD *)Data, ValueW, *(_QWORD *)Data, v92);
  LOBYTE(v6) = 1;
  v2 = FSEnumDeviceInterfaces(&GUID_e5323777_f976_4f5b_9b55_b94699c46e44, v6, v87, v7);
  v3 = v2;
  if ( v2 < 0 )
  {
    if ( g_wppLevels )
    {
      v4 = 190;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v4, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v2);
      goto LABEL_110;
    }
    goto LABEL_110;
  }
  LOBYTE(v8) = 1;
  v2 = FSEnumDeviceInterfaces(&GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca, v8, Block, v9);
  v3 = v2;
  if ( v2 >= 0 )
  {
    for ( i = (void **)Block[0]; i != Block; i = (void **)*i )
    {
      v11 = (const unsigned __int16 *)i[2];
      *(_DWORD *)v74 = 0;
      if ( FSGetAliasDeviceName2(1, v11, &GUID_e5323777_f976_4f5b_9b55_b94699c46e44, 0, 0, (unsigned int *)v74) == -1072875819 )
        utl::list<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::allocator<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>::push_back(
          v87,
          i + 2);
    }
    v76 = v88;
    if ( !(_DWORD)v88 )
    {
      v3 = 0;
      goto LABEL_110;
    }
    v12 = 6848LL * (unsigned int)v88;
    unique = (void **)wil::make_unique_nothrow<unsigned char [0]>(&v83, v12);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::operator=((void **)&v85, unique);
    wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v83);
    v14 = v85;
    if ( !v85 )
    {
      v3 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          192,
          &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids,
          0,
          -2147024882);
      goto LABEL_110;
    }
    memset_0(v85, 0, v12);
    v16 = (void **)v87[0];
    v17 = v14;
LABEL_29:
    if ( v16 == v87 )
    {
      if ( (unsigned int)dword_18008B170 > 5 && (unsigned __int8)tlgKeywordOn(v15, 0x800000000000LL) )
      {
        v95 = __PAIR64__(HIDWORD(v85), (unsigned int)v14);
        v83 = &v76;
        v96 = (_DWORD)v17 - (_DWORD)v14;
        v84 = 2;
        v86 = 50333696;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperPtrSize,_tlgWrapperPtrSize>(
          v54,
          (__int64)byte_180083623);
      }
      RegSetValueExW(hkey, L"LastCensusReportTime", 0, 0xBu, Data, 8u);
      goto LABEL_109;
    }
    memset_0(v102, 0, 0x60u);
    v18 = (const unsigned __int16 *)v16[2];
    v19 = (_BYTE *)v16[3] - (_BYTE *)v18;
    *(_DWORD *)v74 = 0;
    v101 = v17;
    v20 = StringCchCopyW(v17, (v19 >> 1) + 1, v18);
    v3 = v20;
    if ( v20 < 0 )
    {
      if ( g_wppLevels )
      {
        v28 = 193;
        goto LABEL_38;
      }
LABEL_109:
      v1 = a1;
      goto LABEL_110;
    }
    LODWORD(v21) = 1;
    v22 = &v17[(((_BYTE *)v16[3] - (_BYTE *)v16[2]) >> 1) + 1];
    v23 = v22;
    v83 = (int *)v22;
    v24 = Buf1;
    while ( 1 )
    {
      v25 = v24->pid == 2;
      LODWORD(pv) = 0;
      v71 = 0;
      v102[(unsigned int)v21 - 1] = (__int64)v22;
      if ( v25 && !memcmp_0(v24, &DEVPKEY_Device_DriverDate, 0x10u) )
      {
        if ( (int)FSGetDeviceNodeProperty(
                    (LPCWSTR)v16[2],
                    (DEVPROPKEY *)&DEVPKEY_Device_DriverDate,
                    (PBYTE)&v93,
                    8u,
                    &pcbData) < 0 )
          goto LABEL_42;
        GetSystemDate(&v93, v22, v26);
        v20 = StringCchLengthW(v22, 0x40u, &v71);
        v3 = v20;
        if ( v20 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_109;
          v28 = 195;
          goto LABEL_38;
        }
      }
      else
      {
        if ( (int)FSGetDeviceNodeProperty((LPCWSTR)v16[2], v24, (PBYTE)v22, 0x206u, (unsigned int *)&pv) < 0 )
          goto LABEL_42;
        v29 = (unsigned int)pv >> 1;
        v23[v29] = 0;
        v20 = StringCchLengthW(v22, (unsigned int)(v29 + 1), &v71);
        v3 = v20;
        if ( v20 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_109;
          v28 = 194;
          goto LABEL_38;
        }
      }
      v30 = v71 + 1;
      if ( v71 == -1 || v71 == 0 )
      {
LABEL_42:
        v20 = StringCchCopyW(v22, 5u, L"N.A.");
        v3 = v20;
        if ( v20 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_109;
          v28 = 196;
          goto LABEL_38;
        }
        v30 = 5;
      }
      v21 = (unsigned int)(v21 + 1);
      ++v24;
      v22 = (unsigned __int16 *)v83 + v30;
      v83 = (int *)v22;
      v23 = v22;
      if ( v24 == (DEVPROPKEY *)&v111 )
      {
        v31 = (const WCHAR *)v16[2];
        v102[v21 - 1] = (__int64)v22;
        v71 = 0;
        GrabPanelInformation(v31, v22, v27);
        v20 = StringCchLengthW(v22, 0x40u, &v71);
        v3 = v20;
        if ( v20 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_109;
          v28 = 197;
        }
        else
        {
          v32 = (const unsigned __int16 *)v16[2];
          LODWORD(pv) = 0;
          v73 = 0;
          v33 = &v22[v71];
          v71 = 260;
          v34 = v33 + 1;
          v102[(unsigned int)(v21 + 1) - 1] = (__int64)v34;
          GetDMFTCLSIds(v32, v34, &v71, (int *)&pv, &v73);
          v35 = v71;
          if ( v71 <= 1 )
          {
            v20 = StringCchCopyW(v34, 5u, L"N.A.");
            v3 = v20;
            if ( v20 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_109;
              v28 = 198;
              goto LABEL_38;
            }
            v35 = 4;
          }
          v36 = &v34[v35 + 1];
          v86 = (__int64)v36;
          memset_0(v36, 0, 0x58u);
          v17 = v36 + 44;
          v95 = (unsigned __int64)(v36 + 44);
          *((_DWORD *)v36 + 3) = ((_DWORD)pv != 0) | (v73 != 0 ? 2 : 0);
          *(_DWORD *)v75 = 0;
          FSGetDeviceNodeRegistryEntry((LPCWSTR)v16[2], L"EnableDshowRedirection", v75, 4u, &pcbData);
          *((_DWORD *)v36 + 3) |= 4 * *(_DWORD *)v75;
          FSGetDeviceNodeRegistryEntry((LPCWSTR)v16[2], L"CacheUVCControl", (LPBYTE)v36, 4u, &pcbData);
          FSGetDeviceInterfaceRegistryEntry2(
            (const unsigned __int16 *)v16[2],
            L"CPV2FaceAuth",
            (unsigned __int8 *)v36 + 4,
            4u,
            &pcbData,
            pvData);
          FSGetDeviceInterfaceRegistryEntry2(
            (const unsigned __int16 *)v16[2],
            L"FSSensorOrientation",
            (unsigned __int8 *)v36 + 8,
            4u,
            &pcbData,
            pvDatac);
          wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v77);
          wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v81);
          wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v80);
          wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v79);
          wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v77);
          v20 = MFCreateSensorGroup(v16[2], &v77);
          v3 = v20;
          if ( v20 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_109;
            v28 = 199;
          }
          else
          {
            wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v79);
            wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v80);
            wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v81);
            v20 = PopulateMFDeviceStreamInfo(v77, &v81, &v80, &v79);
            v3 = v20;
            if ( v20 >= 0 )
            {
              v37 = v81;
              if ( v81 )
              {
                MFGetAttribute2UINT32asUINT64(v81, &MF_MT_FRAME_RATE, v36 + 24, v36 + 26);
                MFGetAttribute2UINT32asUINT64(v37, &MF_MT_FRAME_SIZE, v36 + 20, v36 + 22);
              }
              v38 = v80;
              if ( v80 )
              {
                MFGetAttribute2UINT32asUINT64(v80, &MF_MT_FRAME_RATE, v36 + 16, v36 + 18);
                MFGetAttribute2UINT32asUINT64(v38, &MF_MT_FRAME_SIZE, v36 + 12, v36 + 14);
              }
              if ( v79 )
                MFGetAttribute2UINT32asUINT64(v79, &MF_MT_FRAME_SIZE, v36 + 28, v36 + 30);
              if ( (int)FSGetDeviceInterfaceProperty2(
                          (LPCWSTR)v16[2],
                          (DEVPROPKEY *)&DEVPKEY_DeviceInterface_FSM_VirtualCamera_EffectsClsid,
                          0xDu,
                          (unsigned __int8 *)v36 + 64,
                          0x10u,
                          &pcbData) < 0 )
                *((GUID *)v36 + 4) = GUID_00000000_0000_0000_0000_000000000000;
              if ( v77 )
              {
                v83 = 0;
                if ( (*(int (__fastcall **)(struct IMFSensorGroup *, _QWORD, int **))(*(_QWORD *)v77 + 56LL))(
                       v77,
                       0,
                       &v83) >= 0 )
                {
                  v39 = (__int64)v83;
                  v71 = 0;
                  v73 = 0;
                  pv = 0;
                  v40 = *(__int64 (__fastcall **)(__int64, unsigned __int64 *))(*(_QWORD *)v83 + 56LL);
                  wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&v71);
                  v41 = v40(v39, &v71);
                  v42 = v70;
                  v45 = 0;
                  if ( v41 >= 0 )
                  {
                    if ( v71 )
                    {
                      v43 = *(_QWORD *)v71;
                      p_pv = &pv;
                      v42 = v70 | 1;
                      v98 = 0;
                      v70 |= 1u;
                      v44 = *(int (__fastcall **)(unsigned __int64, __int64 *, __int64 *, int *))(v43 + 128);
                      v99 = 1;
                      if ( v44(v71, FSSensorGroupCameraCapabiltiesBlob, &v98, &v73) >= 0 )
                        v45 = 1;
                    }
                  }
                  if ( (v42 & 1) != 0 )
                  {
                    v70 = v42 & 0xFFFFFFFE;
                    wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&p_pv);
                  }
                  v46 = pv;
                  if ( v45 )
                  {
                    *((_DWORD *)v36 + 4) = *((unsigned __int8 *)pv + 4)
                                         | (2 * (*((unsigned __int8 *)pv + 5) | (2 * *((unsigned __int8 *)pv + 6))));
                    *((_DWORD *)v36 + 5) = v46[2];
                  }
                  pv = 0;
                  if ( v46 )
                    CoTaskMemFree(v46);
                  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v71);
                  v17 = (unsigned __int16 *)v95;
                }
                wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v83);
              }
              if ( (int)FSGetDeviceInterfaceRegistryEntry2(
                          (const unsigned __int16 *)v16[2],
                          L"FSColorInfoOverride",
                          v74,
                          4u,
                          &pcbData,
                          pvDataa) >= 0 )
                *((_DWORD *)v36 + 20) = *(_DWORD *)v74;
              if ( (int)FSGetDeviceInterfaceRegistryEntry2(
                          (const unsigned __int16 *)v16[2],
                          L"EnableImageReplacement",
                          v78,
                          4u,
                          &pcbData,
                          pvDatab) >= 0 )
                *((_DWORD *)v36 + 21) = *(_DWORD *)v78;
              if ( (unsigned __int8)byte_18008D62D >= 8u )
              {
                WPP_SF_SSSSSSSSSSSS(
                  *((_QWORD *)WPP_GLOBAL_Control + 27),
                  201,
                  v47,
                  (_DWORD)v101,
                  v102[0],
                  v102[1],
                  v102[2],
                  v102[3],
                  v102[4],
                  v102[5],
                  v102[6],
                  v102[7],
                  v102[8],
                  v102[9],
                  v102[10]);
                if ( (unsigned __int8)byte_18008D62D >= 8u )
                {
                  LOBYTE(v48) = 0;
                  if ( *((_DWORD *)v36 + 13) )
                    v48 = (double)*((int *)v36 + 12) / (double)*((int *)v36 + 13);
                  LOBYTE(v49) = 0;
                  if ( *((_DWORD *)v36 + 9) )
                    v49 = (double)*((int *)v36 + 8) / (double)*((int *)v36 + 9);
                  WPP_SF_DDgDDgDDdDdddd(
                    *((_QWORD *)WPP_GLOBAL_Control + 27),
                    202,
                    *((_DWORD *)v36 + 10),
                    *((_DWORD *)v36 + 6),
                    *((_DWORD *)v36 + 7),
                    SLOBYTE(v49),
                    *((_DWORD *)v36 + 10),
                    *((_DWORD *)v36 + 11),
                    SLOBYTE(v48),
                    *((_DWORD *)v36 + 14),
                    *((_DWORD *)v36 + 15),
                    *(_DWORD *)v36,
                    *((_DWORD *)v36 + 1),
                    *((_DWORD *)v36 + 2),
                    *((_DWORD *)v36 + 4),
                    *((_DWORD *)v36 + 5),
                    *((_DWORD *)v36 + 21));
                  if ( (unsigned __int8)byte_18008D62D >= 8u )
                  {
                    v50 = *((_DWORD *)v36 + 20);
                    v70 |= 2u;
                    v51 = GuidTrace::GuidTrace((GuidTrace *)v100, (const struct _GUID *)v36 + 4);
                    String = (const char *)*((_QWORD *)v51 + 3);
                    if ( !String )
                      String = FSString::GetString(v51);
                    WPP_SF_SdsD(
                      *((_QWORD *)WPP_GLOBAL_Control + 27),
                      203,
                      v52,
                      v103,
                      *((_DWORD *)v36 + 3),
                      (__int64)String,
                      v50);
                  }
                }
              }
              if ( (v70 & 2) != 0 )
              {
                v70 &= ~2u;
                FSString::~FSString((FSString *)v100);
              }
              v16 = (void **)*v16;
              goto LABEL_29;
            }
            if ( !g_wppLevels )
              goto LABEL_109;
            v28 = 200;
          }
        }
LABEL_38:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, 0, v20);
        goto LABEL_109;
      }
    }
  }
  if ( g_wppLevels )
  {
    v4 = 191;
    goto LABEL_4;
  }
LABEL_110:
  if ( (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_Ddd(*((_QWORD *)WPP_GLOBAL_Control + 27), 204, &WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids, v3, v76, v1);
  while ( 1 )
  {
    v55 = Block[0];
    if ( Block[0] == Block )
      break;
    v56 = (_QWORD *)*((_QWORD *)Block[0] + 1);
    v57 = (char *)Block[0] + 16;
    v58 = *(_QWORD *)Block[0];
    *v56 = *(_QWORD *)Block[0];
    *(_QWORD *)(v58 + 8) = v56;
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v57);
    operator delete(v55);
  }
  v91 = 0;
  while ( 1 )
  {
    v59 = v87[0];
    if ( v87[0] == v87 )
      break;
    v60 = (_QWORD *)*((_QWORD *)v87[0] + 1);
    v61 = (char *)v87[0] + 16;
    v62 = *(_QWORD *)v87[0];
    *v60 = *(_QWORD *)v87[0];
    *(_QWORD *)(v62 + 8) = v60;
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v61);
    operator delete(v59);
  }
  v88 = 0;
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v77);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v79);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v80);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v81);
  wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::reset(&v85);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hkey);
  return v3;
}

```

## disassembly

```asm
0x1800553d8  push    rbp
0x1800553da  push    rbx
0x1800553db  push    rsi
0x1800553dc  push    rdi
0x1800553dd  push    r13
0x1800553df  push    r14
0x1800553e1  push    r15
0x1800553e3  lea     rbp, [rsp-1F0h]
0x1800553eb  sub     rsp, 300h
0x1800553f2  mov     rax, cs:__security_cookie
0x1800553f9  xor     rax, rsp
0x1800553fc  mov     [rbp+220h+var_40], rax
0x180055403  xor     r13d, r13d
0x180055406  mov     [rbp+220h+var_2A0], ecx
0x180055409  mov     [rbp+220h+var_298], r13d
0x18005540d  mov     edi, ecx
0x18005540f  mov     [rbp+220h+var_274], r13d
0x180055413  mov     [rbp+220h+var_29C], r13d
0x180055417  mov     qword ptr [rbp+220h+var_1E0.dwLowDateTime], r13
0x18005541b  mov     [rbp+220h+hkey], r13
0x18005541f  mov     [rbp+220h+var_208], r13d
0x180055423  call    cs:__imp_MFGetSystemTime
0x180055429  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_Service.fmtid.Data1
0x180055430  mov     qword ptr [rbp+220h+Data], rax
0x180055434  lea     rcx, [rbp+220h+hkey]
0x180055438  mov     eax, cs:DEVPKEY_Device_Service.pid
0x18005543e  xor     edx, edx
0x180055440  mov     [rbp+220h+var_100], eax
0x180055446  mov     eax, cs:DEVPKEY_Device_DriverVersion.pid
0x18005544c  mov     [rbp+220h+var_EC], eax
0x180055452  mov     eax, cs:DEVPKEY_Device_DriverDate.pid
0x180055458  mov     [rbp+220h+var_D8], eax
0x18005545e  mov     eax, cs:DEVPKEY_Device_DriverDesc.pid
0x180055464  mov     [rbp+220h+var_C4], eax
0x18005546a  mov     eax, cs:DEVPKEY_Device_Manufacturer.pid
0x180055470  movaps  [rbp+220h+Buf1], xmm0
0x180055477  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverVersion.fmtid.Data1
0x18005547e  mov     [rbp+220h+var_B0], eax
0x180055484  mov     eax, cs:DEVPKEY_Device_HardwareIds.pid
0x18005548a  movups  [rbp+220h+var_FC], xmm0
0x180055491  mov     [rbp+220h+var_9C], eax
0x180055497  mov     eax, cs:DEVPKEY_Device_EnumeratorName.pid
0x18005549d  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverDate.fmtid.Data1
0x1800554a4  mov     [rbp+220h+var_88], eax
0x1800554aa  mov     eax, cs:dword_18007E310
0x1800554b0  movups  [rbp+220h+var_E8], xmm0
0x1800554b7  mov     [rbp+220h+var_74], eax
0x1800554bd  mov     eax, cs:dword_18007E450
0x1800554c3  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_DriverDesc.fmtid.Data1
0x1800554ca  mov     [rbp+220h+var_60], eax
0x1800554d0  mov     eax, cs:dword_18007E410
0x1800554d6  movups  [rbp+220h+var_D4], xmm0
0x1800554dd  mov     [rbp+220h+var_4C], eax
0x1800554e3  lea     rax, [rbp+220h+var_220]
0x1800554e7  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_Manufacturer.fmtid.Data1
0x1800554ee  mov     [rbp+220h+var_220], rax
0x1800554f2  lea     rax, [rbp+220h+var_220]
0x1800554f6  mov     [rbp+220h+var_218], rax
0x1800554fa  lea     rax, [rbp+220h+Block]
0x1800554fe  movaps  [rbp+220h+var_C0], xmm0
0x180055505  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_HardwareIds.fmtid.Data1
0x18005550c  mov     [rbp+220h+Block], rax
0x180055510  lea     rax, [rbp+220h+Block]
0x180055514  mov     [rbp+220h+var_1E8], r13
0x180055518  movups  [rbp+220h+var_AC], xmm0
0x18005551f  mov     [rbp+220h+var_230], r13
0x180055523  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_EnumeratorName.fmtid.Data1
0x18005552a  mov     dword ptr [rbp+220h+var_278], r13d
0x18005552e  mov     dword ptr [rbp+220h+var_268], r13d
0x180055532  movups  [rbp+220h+var_98], xmm0
0x180055539  mov     [rbp+220h+var_250], r13
0x18005553d  movups  xmm0, cs:DEVPKEY_PNPX_ModelNumber
0x180055544  mov     [rbp+220h+var_258], r13
0x180055548  mov     [rbp+220h+var_260], r13
0x18005554c  movups  [rbp+220h+var_84], xmm0
0x180055553  mov     [rbp+220h+var_270], r13
0x180055557  movups  xmm0, cs:DEVPKEY_PNPX_ModelName
0x18005555e  mov     [rbp+220h+var_210], r13
0x180055562  mov     [rbp+220h+var_1F8], rax
0x180055566  movaps  [rbp+220h+var_70], xmm0
0x18005556d  movups  xmm0, cs:DEVPKEY_PNPX_FirmwareVersion
0x180055574  mov     [rbp+220h+var_1F0], r13
0x180055578  movups  [rbp+220h+var_5C], xmm0
0x18005557f  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180055584  lea     r9, [rbp+220h+hkey]; HKEY *
0x180055588  xor     r8d, r8d; bool *
0x18005558b  mov     edx, 2011Fh; unsigned int
0x180055590  xor     ecx, ecx; unsigned __int16 *
0x180055592  call    ?OpenSensorGroupRegistryKey@@YAJPEBGKPEA_NPEAPEAUHKEY__@@@Z; OpenSensorGroupRegistryKey(ushort const *,ulong,bool *,HKEY__ * *)
0x180055597  mov     r15d, eax
0x18005559a  test    eax, eax
0x18005559c  jns     short loc_1800555D3
0x18005559e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800555a5  jb      loc_18005610B
0x1800555ab  mov     edx, 0BCh
0x1800555b0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800555b7  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x1800555be  xor     r9d, r9d
0x1800555c1  mov     dword ptr [rsp+330h+pdwType], eax
0x1800555c5  mov     rcx, [rcx+10h]
0x1800555c9  call    WPP_SF_qD
0x1800555ce  jmp     loc_18005610B
0x1800555d3  mov     rcx, [rbp+220h+hkey]; hkey
0x1800555d7  lea     rax, [rbp+220h+var_29C]
0x1800555db  mov     [rsp+330h+pcbData], rax; pcbData
0x1800555e0  lea     r8, aLastcensusrepo; "LastCensusReportTime"
0x1800555e7  lea     rax, [rbp+220h+var_1E8]
0x1800555eb  mov     [rbp+220h+var_29C], 8
0x1800555f2  mov     [rsp+330h+pvData], rax; pvData
0x1800555f7  mov     r9d, 48h ; 'H'; dwFlags
0x1800555fd  lea     rax, [rbp+220h+var_208]
0x180055601  xor     edx, edx; lpSubKey
0x180055603  mov     [rsp+330h+pdwType], rax; pdwType
0x180055608  call    cs:__imp_RegGetValueW
0x18005560e  mov     r8, qword ptr [rbp+220h+Data]
0x180055612  mov     r9, [rbp+220h+var_1E8]
0x180055616  test    eax, eax
0x180055618  jnz     short loc_180055640
0x18005561a  cmp     r8, r9
0x18005561d  jb      short loc_180055640
0x18005561f  test    edi, edi
0x180055621  jnz     short loc_180055640
0x180055623  mov     rcx, r8
0x180055626  mov     rdx, 0C92A69C000h
0x180055630  sub     rcx, r9
0x180055633  cmp     rcx, rdx
0x180055636  jnb     short loc_180055640
0x180055638  xor     r15d, r15d
0x18005563b  jmp     loc_18005610B
0x180055640  cmp     cs:byte_18008D62D, 8
0x180055647  jb      short loc_18005566E
0x180055649  mov     rcx, cs:WPP_GLOBAL_Control
0x180055650  mov     edx, 0BDh
0x180055655  mov     [rsp+330h+pvData], r9; unsigned int *
0x18005565a  mov     r9d, eax
0x18005565d  mov     [rsp+330h+pdwType], r8
0x180055662  mov     rcx, [rcx+0D8h]
0x180055669  call    WPP_SF_DII
0x18005566e  lea     r8, [rbp+220h+var_220]
0x180055672  mov     dl, 1
0x180055674  lea     rcx, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44
0x18005567b  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x180055680  mov     r15d, eax
0x180055683  test    eax, eax
0x180055685  jns     short loc_18005569E
0x180055687  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005568e  jb      loc_18005610B
0x180055694  mov     edx, 0BEh
0x180055699  jmp     loc_1800555B0
0x18005569e  lea     r8, [rbp+220h+Block]
0x1800556a2  mov     dl, 1
0x1800556a4  lea     rcx, _GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca
0x1800556ab  call    ?FSEnumDeviceInterfaces@@YAJAEBU_GUID@@_NAEAV?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@@Z; FSEnumDeviceInterfaces(_GUID const &,bool,utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>> &)
0x1800556b0  mov     r15d, eax
0x1800556b3  test    eax, eax
0x1800556b5  jns     short loc_1800556CE
0x1800556b7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800556be  jb      loc_18005610B
0x1800556c4  mov     edx, 0BFh
0x1800556c9  jmp     loc_1800555B0
0x1800556ce  mov     rbx, [rbp+220h+Block]
0x1800556d2  lea     rax, [rbp+220h+Block]
0x1800556d6  cmp     rbx, rax
0x1800556d9  jz      short loc_18005571B
0x1800556db  mov     rdx, [rbx+10h]; unsigned __int16 *
0x1800556df  lea     rax, [rbp+220h+var_27C]
0x1800556e3  mov     [rsp+330h+pvData], rax; unsigned int *
0x1800556e8  lea     r8, _GUID_e5323777_f976_4f5b_9b55_b94699c46e44; struct _GUID *
0x1800556ef  xor     r9d, r9d; unsigned __int16 *
0x1800556f2  mov     dword ptr [rsp+330h+pdwType], r13d; unsigned int
0x1800556f7  mov     cl, 1; bool
0x1800556f9  mov     dword ptr [rbp+220h+var_27C], r13d
0x1800556fd  call    ?FSGetAliasDeviceName2@@YAJ_NPEBGAEBU_GUID@@PEAGKPEAK@Z; FSGetAliasDeviceName2(bool,ushort const *,_GUID const &,ushort *,ulong,ulong *)
0x180055702  cmp     eax, 0C00D36D5h
0x180055707  jnz     short loc_180055716
0x180055709  lea     rdx, [rbx+10h]
0x18005570d  lea     rcx, [rbp+220h+var_220]
0x180055711  call    ?push_back@?$list@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@V?$allocator@V?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@@2@@utl@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@2@@Z; utl::list<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>,utl::allocator<utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>>>::push_back(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> const &)
0x180055716  mov     rbx, [rbx]
0x180055719  jmp     short loc_1800556D2
0x18005571b  mov     rax, [rbp+220h+var_210]
0x18005571f  mov     [rbp+220h+var_274], eax
0x180055722  test    eax, eax
0x180055724  jnz     short loc_18005572E
0x180055726  xor     r15d, r15d
0x180055729  jmp     loc_18005610B
0x18005572e  mov     eax, eax
0x180055730  lea     rcx, [rbp+220h+var_240]
0x180055734  imul    rbx, rax, 1AC0h
0x18005573b  mov     rdx, rbx
0x18005573e  call    ??$make_unique_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<uchar [0]>(unsigned __int64)
0x180055743  mov     rdx, rax
0x180055746  lea     rcx, [rbp+220h+var_230]
0x18005574a  call    ??4?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::operator=(wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>> &&)
0x18005574f  lea     rcx, [rbp+220h+var_240]
0x180055753  call    ?reset@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<uchar [0],wistd::default_delete<uchar [0]>>::reset(std::nullptr_t)
0x180055758  mov     rsi, [rbp+220h+var_230]
0x18005575c  test    rsi, rsi
0x18005575f  jnz     short loc_18005579D
0x180055761  mov     r15d, 8007000Eh
0x180055767  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18005576e  jb      loc_18005610B
0x180055774  mov     rcx, cs:WPP_GLOBAL_Control
0x18005577b  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x180055782  mov     edx, 0C0h
0x180055787  mov     dword ptr [rsp+330h+pdwType], r15d
0x18005578c  xor     r9d, r9d
0x18005578f  mov     rcx, [rcx+10h]
0x180055793  call    WPP_SF_qD
0x180055798  jmp     loc_18005610B
0x18005579d  mov     r8, rbx; Size
0x1800557a0  xor     edx, edx; Val
0x1800557a2  mov     rcx, rsi; void *
0x1800557a5  call    memset_0
0x1800557aa  mov     rbx, [rbp+220h+var_220]
0x1800557ae  mov     r14, rsi
0x1800557b1  lea     rax, [rbp+220h+var_220]
0x1800557b5  cmp     rbx, rax
0x1800557b8  jz      loc_180056071
0x1800557be  xor     edx, edx; Val
0x1800557c0  lea     rcx, [rbp+220h+var_178]; void *
0x1800557c7  lea     r8d, [rdx+60h]; Size
0x1800557cb  call    memset_0
0x1800557d0  mov     r8, [rbx+10h]; unsigned __int16 *
0x1800557d4  mov     rcx, r14; unsigned __int16 *
0x1800557d7  mov     rdx, [rbx+18h]
0x1800557db  sub     rdx, r8
0x1800557de  mov     dword ptr [rbp+220h+var_27C], 0
0x1800557e5  sar     rdx, 1
0x1800557e8  inc     rdx; unsigned __int64
0x1800557eb  mov     [rbp+220h+var_180], r14
0x1800557f2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800557f7  mov     r15d, eax
0x1800557fa  test    eax, eax
0x1800557fc  js      loc_18005605A
0x180055802  mov     rdi, [rbx+18h]
0x180055806  mov     r13d, 1
0x18005580c  sub     rdi, [rbx+10h]
0x180055810  sar     rdi, 1
0x180055813  add     r14, 2
0x180055817  lea     rdi, [r14+rdi*2]
0x18005581b  mov     r15, rdi
0x18005581e  mov     [rbp+220h+var_240], rdi
0x180055822  lea     r14, [rbp+220h+Buf1]
0x180055829  cmp     dword ptr [r14+10h], 2
0x18005582e  mov     eax, r13d
0x180055831  mov     dword ptr [rbp+220h+pv], 0
0x180055838  mov     [rbp+220h+var_290], 0
0x180055840  mov     [rbp+rax*8+220h+var_180], rdi
0x180055848  jnz     loc_1800558EF
0x18005584e  mov     r8d, 10h; Size
0x180055854  lea     rdx, DEVPKEY_Device_DriverDate; Buf2
0x18005585b  mov     rcx, r14; Buf1
0x18005585e  call    memcmp_0
0x180055863  test    eax, eax
0x180055865  jnz     loc_1800558EF
0x18005586b  mov     rcx, [rbx+10h]; pszDeviceInterface
0x18005586f  lea     rax, [rbp+220h+var_29C]
0x180055873  mov     r9d, 8; unsigned int
0x180055879  mov     [rsp+330h+pdwType], rax; unsigned int *
0x18005587e  lea     r8, [rbp+220h+var_1E0]; PropertyBuffer
0x180055882  lea     rdx, DEVPKEY_Device_DriverDate; PropertyKey
0x180055889  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x18005588e  test    eax, eax
0x180055890  js      loc_180055944
0x180055896  mov     rdx, rdi; unsigned __int16 *
0x180055899  lea     rcx, [rbp+220h+var_1E0]; struct _FILETIME *
0x18005589d  call    ?GetSystemDate@@YAXAEAU_FILETIME@@PEAGI@Z; GetSystemDate(_FILETIME &,ushort *,uint)
0x1800558a2  lea     r8, [rbp+220h+var_290]; unsigned __int64 *
0x1800558a6  mov     edx, 40h ; '@'; unsigned __int64
0x1800558ab  mov     rcx, rdi; unsigned __int16 *
0x1800558ae  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800558b3  mov     r15d, eax
0x1800558b6  test    eax, eax
0x1800558b8  jns     short loc_180055937
0x1800558ba  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800558c1  jb      loc_180056108
0x1800558c7  mov     edx, 0C3h
0x1800558cc  mov     rcx, cs:WPP_GLOBAL_Control
0x1800558d3  lea     r8, WPP_26240e33afde38acfb2c6165a2db6f60_Traceguids
0x1800558da  xor     r9d, r9d
0x1800558dd  mov     dword ptr [rsp+330h+pdwType], eax
0x1800558e1  mov     rcx, [rcx+10h]
0x1800558e5  call    WPP_SF_qD
0x1800558ea  jmp     loc_180056108
0x1800558ef  mov     rcx, [rbx+10h]; pszDeviceInterface
0x1800558f3  lea     rax, [rbp+220h+pv]
0x1800558f7  mov     r9d, 206h; unsigned int
0x1800558fd  mov     [rsp+330h+pdwType], rax; unsigned int *
0x180055902  mov     r8, rdi; PropertyBuffer
0x180055905  mov     rdx, r14; PropertyKey
0x180055908  call    ?FSGetDeviceNodeProperty@@YAJPEBGPEBU_DEVPROPKEY@@PEAEKPEAK@Z; FSGetDeviceNodeProperty(ushort const *,_DEVPROPKEY const *,uchar *,ulong,ulong *)
0x18005590d  test    eax, eax
0x18005590f  js      short loc_180055944
0x180055911  mov     ecx, dword ptr [rbp+220h+pv]
0x180055914  lea     r8, [rbp+220h+var_290]; unsigned __int64 *
0x180055918  shr     ecx, 1
0x18005591a  xor     eax, eax
0x18005591c  mov     [r15+rcx*2], ax
0x180055921  lea     edx, [rcx+1]; unsigned __int64
  ... truncated ...
```
