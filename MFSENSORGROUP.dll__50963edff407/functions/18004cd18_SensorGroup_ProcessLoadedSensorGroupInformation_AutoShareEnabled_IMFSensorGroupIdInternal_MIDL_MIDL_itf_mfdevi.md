# SensorGroup::ProcessLoadedSensorGroupInformation_AutoShareEnabled(IMFSensorGroupIdInternal *,__MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 const &,__MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0011 const &)

- ea: `0x18004cd18`
- end: `0x18004d885`
- name: `?ProcessLoadedSensorGroupInformation_AutoShareEnabled@SensorGroup@@IEAAJPEAUIMFSensorGroupIdInternal@@AEBT__MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010@@AEBU__MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0011@@@Z`
- size: `2925`
- prototype: `int(SensorGroup *__hidden this, struct IMFSensorGroupIdInternal *, const union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *, const struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0011 *)`
- caller_count: `1`
- callee_count: `36`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180011a94`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x1800099b4`
- `0x18001ba24`
- `0x18001bce0`
- `0x18001c854`
- `0x18001c96c`
- `0x1800231c8`
- `0x180023f48`
- `0x1800243b0`
- `0x18002464c`
- `0x180026320`
- `0x180026e70`
- `0x180028d34`
- `0x18002c008`
- `0x18002f3cc`
- `0x1800313f8`
- `0x18003369c`
- `0x1800432a4`
- `0x180044adc`
- `0x180044b1c`
- `0x180044b28`
- `0x180044f30`
- `0x180045900`
- `0x180048ad0`
- `0x18004ac48`
- `0x18004ad30`
- `0x18004cd18`
- `0x18004e08c`
- `0x18006dff0`
- `0x18006e01c`
- `0x18006e7b0`
- `0x18006eea4`
- `0x18006f538`
- `0x180076274`
- `0x180077010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x18004d6ca`
- `MFPlat!MFCreateAttributes` at `0x18004d6ca`
- `MFPlat!MFInitAttributesFromBlob` at `0x18004d702`
- `MFPlat!MFInitAttributesFromBlob` at `0x18004d702`

## pseudocode

```c
__int64 __fastcall SensorGroup::ProcessLoadedSensorGroupInformation_AutoShareEnabled(
        SensorGroup *this,
        struct IMFSensorGroupIdInternal *a2,
        const union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *a3,
        const struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0011 *a4)
{
  unsigned int v4; // r15d
  char v9; // r14
  int v10; // ebx
  __int64 v11; // rdx
  HRESULT v12; // eax
  __int64 v13; // rdx
  int v14; // r8d
  const char *v15; // rdx
  FSString *v16; // rax
  const char *String; // rbx
  FSString *v18; // rax
  const char *v19; // rax
  struct SensorDevice **v20; // rdi
  struct SensorDevice *v21; // rdi
  __int64 (__fastcall *v22)(char *, __int64, _QWORD, __int64 (__fastcall ****)(__int64, GUID *, __int64 *)); // rbx
  int v23; // eax
  __int64 (__fastcall **v24)(__int64, GUID *, __int64 *); // rax
  int v25; // eax
  __int64 v26; // rdx
  _QWORD *v27; // rax
  _QWORD *v28; // rdi
  __int64 i; // r15
  int v30; // eax
  unsigned int v31; // eax
  __int64 j; // r14
  __int64 v33; // rcx
  unsigned int v34; // eax
  unsigned int m; // r14d
  __int64 v36; // rcx
  int v37; // eax
  unsigned int v38; // eax
  unsigned int k; // r14d
  __int64 v40; // rcx
  __int64 v41; // rbx
  MediaTypeTracer *v42; // rax
  const char *v43; // rax
  unsigned int v44; // eax
  unsigned int n; // ebx
  __int64 v46; // rcx
  struct SensorDevice *v47; // rdi
  int v48; // edi
  SensorDevice *v49; // rbx
  SensorDevice *v50; // rax
  SensorDevice *v51; // rax
  int v52; // eax
  _QWORD **v53; // rdi
  __int64 (__fastcall ***v54)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v55; // rcx
  __int64 (__fastcall **v56)(_QWORD, GUID *, __int64 *); // rax
  __int64 (__fastcall *v57)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v58; // rdx
  unsigned int v60; // [rsp+50h] [rbp-B0h] BYREF
  struct IMFMediaType *v61; // [rsp+58h] [rbp-A8h] BYREF
  __int64 (__fastcall ***v62)(__int64, GUID *, __int64 *); // [rsp+60h] [rbp-A0h] BYREF
  SensorDevice *v63; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v64; // [rsp+70h] [rbp-90h] BYREF
  __int64 v65; // [rsp+78h] [rbp-88h] BYREF
  int v66; // [rsp+80h] [rbp-80h] BYREF
  UINT cbBufSize; // [rsp+84h] [rbp-7Ch] BYREF
  unsigned int v68; // [rsp+88h] [rbp-78h] BYREF
  __int64 v69; // [rsp+90h] [rbp-70h] BYREF
  __int64 v70; // [rsp+98h] [rbp-68h] BYREF
  __int64 v71; // [rsp+A0h] [rbp-60h] BYREF
  const char *v72; // [rsp+A8h] [rbp-58h] BYREF
  UINT8 *pBuf; // [rsp+B0h] [rbp-50h] BYREF
  SensorDevice *v74; // [rsp+B8h] [rbp-48h] BYREF
  struct SensorDevice **v75; // [rsp+C0h] [rbp-40h] BYREF
  int v76; // [rsp+C8h] [rbp-38h]
  __int64 v77; // [rsp+CCh] [rbp-34h]
  __int64 v78; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v79; // [rsp+E0h] [rbp-20h] BYREF
  int v80; // [rsp+E8h] [rbp-18h]
  _BYTE v81[24]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v82[56]; // [rsp+118h] [rbp+18h] BYREF
  GUID Buf1; // [rsp+150h] [rbp+50h] BYREF

  v4 = 0;
  v75 = 0;
  v77 = 0;
  v76 = 0;
  v74 = 0;
  v71 = 0;
  v70 = 0;
  v9 = 0;
  v66 = 0;
  v72 = 0;
  pBuf = 0;
  cbBufSize = 0;
  v69 = 0;
  v64 = 0;
  v68 = 0;
  `vector constructor iterator'(&v78, 0x28u, 1u, (void *(*)(void *))SensorStreamCloneInfo::SensorStreamCloneInfo);
  if ( !a2 )
  {
    v10 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_139;
    v11 = 220;
LABEL_138:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v10);
    goto LABEL_139;
  }
  v12 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, __int64 *, _QWORD))(*(_QWORD *)a2 + 192LL))(
          a2,
          3,
          0,
          &v71,
          0);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_139;
    v13 = 221;
    goto LABEL_7;
  }
  v12 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, const char **, _QWORD))(*(_QWORD *)a2 + 192LL))(
          a2,
          14,
          0,
          &v72,
          0);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_139;
    v13 = 222;
    goto LABEL_7;
  }
  v12 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, __int64 *, int *))(*(_QWORD *)a2 + 192LL))(
          a2,
          6,
          0,
          &v70,
          &v66);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_139;
    v13 = 223;
    goto LABEL_7;
  }
  v12 = (*(__int64 (__fastcall **)(struct IMFSensorGroupIdInternal *, __int64, _QWORD, UINT8 **, UINT *))(*(_QWORD *)a2 + 192LL))(
          a2,
          5,
          0,
          &pBuf,
          &cbBufSize);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_139;
    v13 = 224;
    goto LABEL_7;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v15 = L"<null>";
    if ( v72 )
      v15 = v72;
    WPP_SF_qqSqDqD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_DWORD)v15,
      v14,
      (_DWORD)this,
      v71,
      (__int64)v15,
      v70,
      v66,
      (char)pBuf,
      cbBufSize);
    if ( (unsigned __int8)byte_18008D62D >= 8u )
    {
      v16 = ManagedModeTrace::ManagedModeTrace((ManagedModeTrace *)v81, a4);
      String = FSString::GetString(v16);
      v18 = ManagedModeTrace::ManagedModeTrace((ManagedModeTrace *)&Buf1, a3);
      v19 = FSString::GetString(v18);
      WPP_SF_qss(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)v19, (__int64)String);
      v9 = 3;
    }
  }
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    FSString::~FSString((FSString *)&Buf1);
  }
  if ( (v9 & 1) != 0 )
  {
    v9 &= ~1u;
    FSString::~FSString((FSString *)v81);
  }
  v12 = SensorGroup::BuildSensorDeviceListFromBlob(this, a2, v72);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_139;
    v13 = 227;
    goto LABEL_7;
  }
  if ( v76 != 1 )
  {
    v10 = -1072875845;
    if ( !g_wppLevels )
      goto LABEL_139;
    v11 = 228;
    goto LABEL_138;
  }
  v20 = v75;
  v12 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned int *))(*((_QWORD *)*v75 + 1) + 64LL))(
          (__int64)*v75 + 8,
          2,
          &v68);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_139;
    v13 = 229;
    goto LABEL_7;
  }
  while ( 1 )
  {
    if ( v4 >= v68 )
      goto LABEL_96;
    v62 = 0;
    Buf1 = GUID_00000000_0000_0000_0000_000000000000;
    v21 = *v20;
    v22 = *(__int64 (__fastcall **)(char *, __int64, _QWORD, __int64 (__fastcall ****)(__int64, GUID *, __int64 *)))(*((_QWORD *)v21 + 1) + 72LL);
    wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&v62);
    v23 = v22((char *)v21 + 8, 2, v4, &v62);
    v10 = v23;
    if ( v23 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 230, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v23);
      goto LABEL_51;
    }
    if ( (int)(*v62)[10]((__int64)v62, (GUID *)&MF_DEVICESTREAM_STREAM_CATEGORY, (__int64 *)&Buf1) >= 0
      && !memcmp_0(&Buf1, &GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba, 0x10u) )
    {
      break;
    }
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v62);
    v20 = v75;
    ++v4;
  }
  v65 = 0;
  v60 = 0;
  v61 = 0;
  v24 = *v62;
  v64 = 0;
  v63 = 0;
  v25 = (*v24)((__int64)v62, &GUID_e9a42171_c56e_498a_8b39_eda5a070b7fc, &v65);
  v10 = v25;
  if ( v25 < 0 )
  {
    if ( g_wppLevels )
    {
      v26 = 231;
      goto LABEL_43;
    }
    goto LABEL_50;
  }
  v25 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v65 + 264LL))(v65, &v60);
  v10 = v25;
  if ( v25 < 0 )
  {
    if ( g_wppLevels )
    {
      v26 = 232;
LABEL_43:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v26, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v25);
    }
LABEL_50:
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v63);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v61);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v65);
LABEL_51:
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v62);
    goto LABEL_139;
  }
  v27 = operator new[](saturated_mul(v60, 8u));
  v28 = v27;
  if ( !v27 )
  {
    v10 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        233,
        &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
        this,
        -2147024882);
    goto LABEL_50;
  }
  memset_0(v27, 0, 8LL * v60);
  for ( i = 0; (unsigned int)i < v60; i = (unsigned int)(i + 1) )
  {
    v30 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD *))(*(_QWORD *)v65 + 272LL))(v65, (unsigned int)i, &v28[i]);
    v10 = v30;
    if ( v30 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 234, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v30);
      v31 = v60;
      for ( j = 0; (unsigned int)j < v31; j = (unsigned int)(j + 1) )
      {
        v33 = v28[j];
        if ( v33 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v33 + 16LL))(v33);
          v28[j] = 0;
          v31 = v60;
        }
      }
LABEL_72:
      operator delete(v28);
      goto LABEL_50;
    }
  }
  if ( !FSIsSelectedMediaInfoValid(a4)
    || (wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v61),
        FSFindMatchingMediaType((struct IMFMediaType **)v28, v60, a4, &v64, &v61) < 0) )
  {
    wil::com_ptr_t<Windows::Internal::System::IRelativePanelDirectionTracker,wil::err_returncode_policy>::reset(&v61);
    v37 = FSGetSelectedMediaForAutoShare((struct IMFMediaType **)v28, v60, &v64, &v61);
    v10 = v37;
    if ( v37 < 0 )
    {
      if ( g_wppLevels )
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 235, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v37);
      v38 = v60;
      for ( k = 0; k < v38; ++k )
      {
        v40 = v28[k];
        if ( v40 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
          v28[k] = 0;
          v38 = v60;
        }
      }
      goto LABEL_72;
    }
  }
  if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add(&v79, (__int64)v61) )
  {
    v10 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        236,
        &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
        this,
        -2147024882);
    v34 = v60;
    for ( m = 0; m < v34; ++m )
    {
      v36 = v28[m];
      if ( v36 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v36 + 16LL))(v36);
        v28[m] = 0;
        v34 = v60;
      }
    }
    goto LABEL_72;
  }
  v41 = v78;
  v78 = v65;
  if ( v65 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v65 + 8LL))(v65);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v9 |= 4u;
    v42 = MediaTypeTracer::MediaTypeTracer((MediaTypeTracer *)v82, v61);
    v43 = FSString::GetString((MediaTypeTracer *)((char *)v42 + 32));
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      237,
      (unsigned int)&WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
      (_DWORD)this,
      (__int64)v43);
  }
  if ( (v9 & 4) != 0 )
    MediaTypeTracer::~MediaTypeTracer((MediaTypeTracer *)v82);
  v44 = v60;
  for ( n = 0; n < v44; ++n )
  {
    v46 = v28[n];
    if ( v46 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
      v28[n] = 0;
      v44 = v60;
    }
  }
  operator delete(v28);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v63);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v61);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v65);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v62);
  v20 = v75;
LABEL_96:
  if ( !v78 || !v80 )
  {
    v10 = -1072875854;
    if ( !g_wppLevels )
      goto LABEL_139;
    v11 = 238;
    goto LABEL_138;
  }
  v47 = *v20;
  v63 = 0;
  v74 = 0;
  if ( !v47 )
  {
    v48 = -2147024809;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        111,
        &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
        0,
        -2147024809);
LABEL_101:
    v49 = 0;
    goto LABEL_112;
  }
  v50 = (SensorDevice *)operator new(0xE8u);
  if ( v50 )
    v51 = SensorDevice::SensorDevice(v50, a2, 0);
  else
    v51 = 0;
  wil::com_ptr_t<FSConfiguration,wil::err_returncode_policy>::attach((__int64 *)&v63, (__int64)v51);
  v49 = v63;
  if ( !v63 )
  {
    v48 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)((_DWORD)v63 + 112),
        &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
        0,
        -2147024882);
    goto LABEL_101;
  }
  v52 = SensorDevice::InternalInitializeClone(v63, v47, (struct SensorStreamCloneInfo *)&v78, 1u);
  v48 = v52;
  if ( v52 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 113, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, 0, v52);
    goto LABEL_101;
  }
  v63 = 0;
  v74 = v49;
LABEL_112:
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v63);
  if ( v48 < 0 )
  {
    v10 = v48;
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 239, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v48);
    goto LABEL_139;
  }
  if ( !(unsigned int)CTUnkArray<IMFSensorDevice>::Add(
                        (char *)this + 96,
                        ((unsigned __int64)v49 + 8) & -(__int64)(v49 != 0)) )
  {
    v10 = -2147024882;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        240,
        &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids,
        this,
        -2147024882);
LABEL_139:
    if ( byte_18008D62D )
    {
      v58 = 245;
      goto LABEL_141;
    }
    goto LABEL_142;
  }
  ComSmartPtr<IMFCameraProfileValidation>::operator=((_QWORD *)this + 9, 0);
  v12 = MFCreateAttributes((IMFAttributes **)this + 9, 1u);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_139;
    v13 = 241;
    goto LABEL_7;
  }
  if ( pBuf )
  {
    if ( cbBufSize )
    {
      v12 = MFInitAttributesFromBlob(*((IMFAttributes **)this + 9), pBuf, cbBufSize);
      v10 = v12;
      if ( v12 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_139;
        v13 = 242;
        goto LABEL_7;
      }
    }
  }
  v53 = (_QWORD **)((char *)this + 384);
  ComSmartPtr<IMFSensorProfileCollection>::operator=((__int64 *)this + 48);
  v12 = MFCreateSensorProfileCollection((char *)this + 384);
  v10 = v12;
  if ( v12 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_139;
    v13 = 243;
LABEL_7:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v13, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v12);
    goto LABEL_139;
  }
  v54 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))*v53;
  v55 = v69;
  v56 = (__int64 (__fastcall **)(_QWORD, GUID *, __int64 *))**v53;
  v69 = 0;
  v57 = *v56;
  if ( v55 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v55 + 16LL))(v55);
  v10 = v57(v54, &GUID_9a9daaaa_9774_4732_848e_8739655f2ba3, &v69);
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_139;
    v11 = 244;
    goto LABEL_138;
  }
  (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v69 + 160LL))(v69, 0x40000000);
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v58 = 246;
LABEL_141:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v58, &WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids, this, v10);
  }
LABEL_142:
  `vector destructor iterator'(&v78, 0x28u, 1u, (void (*)(void *))SensorStreamCloneInfo::~SensorStreamCloneInfo);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v69);
  wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v74);
  CTUnkArray<SensorDevice>::~CTUnkArray<SensorDevice>(&v75);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18004cd18  push    rbp
0x18004cd1a  push    rbx
0x18004cd1b  push    rsi
0x18004cd1c  push    rdi
0x18004cd1d  push    r12
0x18004cd1f  push    r13
0x18004cd21  push    r14
0x18004cd23  push    r15
0x18004cd25  lea     rbp, [rsp-78h]
0x18004cd2a  sub     rsp, 178h
0x18004cd31  mov     rax, cs:__security_cookie
0x18004cd38  xor     rax, rsp
0x18004cd3b  mov     [rbp+0B0h+var_48], rax
0x18004cd3f  xor     r15d, r15d
0x18004cd42  mov     r13, r9
0x18004cd45  mov     [rsp+1B0h+var_140], r15d
0x18004cd4a  lea     r9, ??0SensorStreamCloneInfo@@QEAA@XZ; void *(*)(void *)
0x18004cd51  mov     rdi, r8
0x18004cd54  mov     [rbp+0B0h+var_F0], r15
0x18004cd58  mov     r12, rdx
0x18004cd5b  mov     [rbp+0B0h+var_E4], r15
0x18004cd5f  mov     rsi, rcx
0x18004cd62  mov     [rbp+0B0h+var_E8], r15d
0x18004cd66  lea     edx, [r15+28h]; unsigned __int64
0x18004cd6a  mov     [rbp+0B0h+var_F8], r15
0x18004cd6e  lea     r8d, [r15+1]; unsigned __int64
0x18004cd72  mov     [rbp+0B0h+var_110], r15
0x18004cd76  lea     rcx, [rbp+0B0h+var_D8]; void *
0x18004cd7a  mov     [rbp+0B0h+var_118], r15
0x18004cd7e  mov     r14d, r15d
0x18004cd81  mov     [rbp+0B0h+var_130], r15d
0x18004cd85  mov     [rbp+0B0h+var_108], r15
0x18004cd89  mov     [rbp+0B0h+pBuf], r15
0x18004cd8d  mov     [rbp+0B0h+cbBufSize], r15d
0x18004cd91  mov     [rbp+0B0h+var_120], r15
0x18004cd95  mov     [rsp+1B0h+var_140], r15d
0x18004cd9a  mov     [rbp+0B0h+var_128], r15d
0x18004cd9e  call    ??_H@YAXPEAX_K1P6APEAX0@Z@Z; `vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void * (*)(void *))
0x18004cda3  test    r12, r12
0x18004cda6  jnz     short loc_18004CDC4
0x18004cda8  mov     ebx, 80070057h
0x18004cdad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cdb4  jb      loc_18004D800
0x18004cdba  mov     edx, 0DCh
0x18004cdbf  jmp     loc_18004D7E2
0x18004cdc4  mov     rax, [r12]
0x18004cdc8  lea     r9, [rbp+0B0h+var_110]
0x18004cdcc  xor     r8d, r8d
0x18004cdcf  mov     [rsp+1B0h+var_190], r15
0x18004cdd4  mov     rcx, r12
0x18004cdd7  mov     rax, [rax+0C0h]
0x18004cdde  lea     edx, [r8+3]
0x18004cde2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004cde7  mov     ebx, eax
0x18004cde9  test    eax, eax
0x18004cdeb  jns     short loc_18004CE08
0x18004cded  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cdf4  jb      loc_18004D800
0x18004cdfa  mov     edx, 0DDh
0x18004cdff  mov     dword ptr [rsp+1B0h+var_190], eax
0x18004ce03  jmp     loc_18004D7E6
0x18004ce08  mov     rax, [r12]
0x18004ce0c  lea     r9, [rbp+0B0h+var_108]
0x18004ce10  xor     r8d, r8d
0x18004ce13  mov     [rsp+1B0h+var_190], r15
0x18004ce18  mov     rcx, r12
0x18004ce1b  mov     rax, [rax+0C0h]
0x18004ce22  lea     edx, [r8+0Eh]
0x18004ce26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce2b  mov     ebx, eax
0x18004ce2d  test    eax, eax
0x18004ce2f  jns     short loc_18004CE45
0x18004ce31  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004ce38  jb      loc_18004D800
0x18004ce3e  mov     edx, 0DEh
0x18004ce43  jmp     short loc_18004CDFF
0x18004ce45  mov     rax, [r12]
0x18004ce49  lea     rcx, [rbp+0B0h+var_130]
0x18004ce4d  xor     r8d, r8d
0x18004ce50  mov     [rsp+1B0h+var_190], rcx
0x18004ce55  lea     r9, [rbp+0B0h+var_118]
0x18004ce59  mov     rcx, r12
0x18004ce5c  mov     rax, [rax+0C0h]
0x18004ce63  lea     edx, [r8+6]
0x18004ce67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ce6c  mov     ebx, eax
0x18004ce6e  test    eax, eax
0x18004ce70  jns     short loc_18004CE89
0x18004ce72  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004ce79  jb      loc_18004D800
0x18004ce7f  mov     edx, 0DFh
0x18004ce84  jmp     loc_18004CDFF
0x18004ce89  mov     rax, [r12]
0x18004ce8d  lea     rcx, [rbp+0B0h+cbBufSize]
0x18004ce91  xor     r8d, r8d
0x18004ce94  mov     [rsp+1B0h+var_190], rcx
0x18004ce99  lea     r9, [rbp+0B0h+pBuf]
0x18004ce9d  mov     rcx, r12
0x18004cea0  mov     rax, [rax+0C0h]
0x18004cea7  lea     edx, [r8+5]
0x18004ceab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ceb0  mov     ebx, eax
0x18004ceb2  test    eax, eax
0x18004ceb4  jns     short loc_18004CECD
0x18004ceb6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004cebd  jb      loc_18004D800
0x18004cec3  mov     edx, 0E0h
0x18004cec8  jmp     loc_18004CDFF
0x18004cecd  cmp     cs:byte_18008D62D, 8
0x18004ced4  jb      loc_18004CF96
0x18004ceda  mov     rax, [rbp+0B0h+var_108]
0x18004cede  lea     rdx, aNull_0; "<null>"
0x18004cee5  mov     rcx, [rbp+0B0h+var_118]
0x18004cee9  test    rax, rax
0x18004ceec  mov     r9, rsi
0x18004ceef  cmovnz  rdx, rax
0x18004cef3  mov     eax, [rbp+0B0h+cbBufSize]
0x18004cef6  mov     [rsp+1B0h+var_168], eax
0x18004cefa  mov     rax, [rbp+0B0h+pBuf]
0x18004cefe  mov     [rsp+1B0h+var_170], rax
0x18004cf03  mov     eax, [rbp+0B0h+var_130]
0x18004cf06  mov     dword ptr [rsp+1B0h+var_178], eax
0x18004cf0a  mov     rax, [rbp+0B0h+var_110]
0x18004cf0e  mov     [rsp+1B0h+var_180], rcx
0x18004cf13  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cf1a  mov     [rsp+1B0h+var_188], rdx
0x18004cf1f  mov     [rsp+1B0h+var_190], rax
0x18004cf24  mov     rcx, [rcx+0D8h]
0x18004cf2b  call    WPP_SF_qqSqDqD
0x18004cf30  cmp     cs:byte_18008D62D, 8
0x18004cf37  jb      short loc_18004CF96
0x18004cf39  mov     rdx, r13; struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0011 *
0x18004cf3c  lea     rcx, [rbp+0B0h+var_B0]; this
0x18004cf40  call    ??0ManagedModeTrace@@QEAA@AEBU__MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0011@@@Z; ManagedModeTrace::ManagedModeTrace(__MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0011 const &)
0x18004cf45  mov     rcx, rax; this
0x18004cf48  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18004cf4d  lea     rcx, [rbp+0B0h+Buf1]; this
0x18004cf51  mov     rdx, rdi; union __MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 *
0x18004cf54  mov     rbx, rax
0x18004cf57  call    ??0ManagedModeTrace@@QEAA@AEBT__MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010@@@Z; ManagedModeTrace::ManagedModeTrace(__MIDL___MIDL_itf_mfdeviceinternal_0000_0066_0010 const &)
0x18004cf5c  mov     rcx, rax; this
0x18004cf5f  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18004cf64  mov     rcx, cs:WPP_GLOBAL_Control
0x18004cf6b  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18004cf72  mov     edx, 0E2h
0x18004cf77  mov     [rsp+1B0h+var_188], rbx; __int64
0x18004cf7c  mov     r9, rsi
0x18004cf7f  mov     [rsp+1B0h+var_190], rax; __int64
0x18004cf84  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18004cf8b  call    WPP_SF_qss
0x18004cf90  mov     r14d, 3
0x18004cf96  test    r14b, 2
0x18004cf9a  jz      short loc_18004CFA9
0x18004cf9c  and     r14d, 0FFFFFFFDh
0x18004cfa0  lea     rcx, [rbp+0B0h+Buf1]; this
0x18004cfa4  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18004cfa9  test    r14b, 1
0x18004cfad  jz      short loc_18004CFBC
0x18004cfaf  and     r14d, 0FFFFFFFEh
0x18004cfb3  lea     rcx, [rbp+0B0h+var_B0]; this
0x18004cfb7  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18004cfbc  mov     r8, [rbp+0B0h+var_108]
0x18004cfc0  lea     rax, [rbp+0B0h+var_F0]
0x18004cfc4  mov     [rsp+1B0h+var_170], rax
0x18004cfc9  mov     rdx, r12
0x18004cfcc  lea     rax, [rsp+1B0h+var_140]
0x18004cfd1  mov     [rsp+1B0h+var_178], rax
0x18004cfd6  mov     eax, [rbp+0B0h+var_130]
0x18004cfd9  mov     dword ptr [rsp+1B0h+var_180], eax
0x18004cfdd  mov     rax, [rbp+0B0h+var_118]
0x18004cfe1  mov     [rsp+1B0h+var_188], rax
0x18004cfe6  mov     rax, [rbp+0B0h+var_110]
0x18004cfea  mov     ecx, [rax+54h]
0x18004cfed  mov     dword ptr [rsp+1B0h+var_190], ecx
0x18004cff1  mov     rcx, rsi
0x18004cff4  call    ?BuildSensorDeviceListFromBlob@SensorGroup@@IEAAJPEAUIMFSensorGroupIdInternal@@PEBGAEBU_GUID@@JPEBEJPEAKAEAV?$CTUnkArray@VSensorDevice@@@@@Z; SensorGroup::BuildSensorDeviceListFromBlob(IMFSensorGroupIdInternal *,ushort const *,_GUID const &,long,uchar const *,long,ulong *,CTUnkArray<SensorDevice> &)
0x18004cff9  mov     ebx, eax
0x18004cffb  test    eax, eax
0x18004cffd  jns     short loc_18004D016
0x18004cfff  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d006  jb      loc_18004D800
0x18004d00c  mov     edx, 0E3h
0x18004d011  jmp     loc_18004CDFF
0x18004d016  cmp     [rbp+0B0h+var_E8], 1
0x18004d01a  jz      short loc_18004D038
0x18004d01c  mov     ebx, 0C00D36BBh
0x18004d021  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d028  jb      loc_18004D800
0x18004d02e  mov     edx, 0E4h
0x18004d033  jmp     loc_18004D7E2
0x18004d038  mov     rdi, [rbp+0B0h+var_F0]
0x18004d03c  lea     r8, [rbp+0B0h+var_128]
0x18004d040  mov     edx, 2
0x18004d045  mov     rcx, [rdi]
0x18004d048  add     rcx, 8
0x18004d04c  mov     rax, [rcx]
0x18004d04f  mov     rax, [rax+40h]
0x18004d053  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d058  mov     ebx, eax
0x18004d05a  test    eax, eax
0x18004d05c  jns     short loc_18004D075
0x18004d05e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d065  jb      loc_18004D800
0x18004d06b  mov     edx, 0E5h
0x18004d070  jmp     loc_18004CDFF
0x18004d075  cmp     r15d, [rbp+0B0h+var_128]
0x18004d079  jnb     loc_18004D55E
0x18004d07f  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18004d086  mov     [rsp+1B0h+var_150], 0
0x18004d08f  lea     rcx, [rsp+1B0h+var_150]
0x18004d094  movdqu  xmmword ptr [rbp+0B0h+Buf1.Data1], xmm0
0x18004d099  mov     rdi, [rdi]
0x18004d09c  mov     rax, [rdi+8]
0x18004d0a0  mov     rbx, [rax+48h]
0x18004d0a4  call    ?reset@?$com_ptr_t@UIMFAttributes@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(void)
0x18004d0a9  lea     r9, [rsp+1B0h+var_150]
0x18004d0ae  mov     r8d, r15d
0x18004d0b1  mov     edx, 2
0x18004d0b6  lea     rcx, [rdi+8]
0x18004d0ba  mov     rax, rbx
0x18004d0bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0c2  xor     edi, edi
0x18004d0c4  mov     ebx, eax
0x18004d0c6  test    eax, eax
0x18004d0c8  js      loc_18004D529
0x18004d0ce  mov     rcx, [rsp+1B0h+var_150]
0x18004d0d3  lea     r8, [rbp+0B0h+Buf1]
0x18004d0d7  lea     rdx, MF_DEVICESTREAM_STREAM_CATEGORY
0x18004d0de  mov     rax, [rcx]
0x18004d0e1  mov     rax, [rax+50h]
0x18004d0e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d0ea  test    eax, eax
0x18004d0ec  js      short loc_18004D106
0x18004d0ee  lea     r8d, [rdi+10h]; Size
0x18004d0f2  lea     rdx, _GUID_fb6c4281_0353_11d1_905f_0000c0cc16ba; Buf2
0x18004d0f9  lea     rcx, [rbp+0B0h+Buf1]; Buf1
0x18004d0fd  call    memcmp_0
0x18004d102  test    eax, eax
0x18004d104  jz      short loc_18004D11C
0x18004d106  lea     rcx, [rsp+1B0h+var_150]
0x18004d10b  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004d110  mov     rdi, [rbp+0B0h+var_F0]
0x18004d114  inc     r15d
0x18004d117  jmp     loc_18004D075
0x18004d11c  mov     rcx, [rsp+1B0h+var_150]
0x18004d121  lea     r8, [rsp+1B0h+var_138]
0x18004d126  mov     [rsp+1B0h+var_138], rdi
0x18004d12b  lea     rdx, _GUID_e9a42171_c56e_498a_8b39_eda5a070b7fc
0x18004d132  mov     [rsp+1B0h+var_160], edi
0x18004d136  mov     [rsp+1B0h+var_158], rdi
0x18004d13b  mov     rax, [rcx]
0x18004d13e  mov     [rsp+1B0h+var_140], edi
0x18004d142  mov     [rsp+1B0h+var_148], rdi
0x18004d147  mov     rax, [rax]
0x18004d14a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d14f  mov     ebx, eax
0x18004d151  test    eax, eax
0x18004d153  jns     short loc_18004D16D
0x18004d155  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d15c  jb      loc_18004D1F9
0x18004d162  mov     edx, 0E7h
0x18004d167  mov     dword ptr [rsp+1B0h+var_190], eax
0x18004d16b  jmp     short loc_18004D1DF
0x18004d16d  mov     rcx, [rsp+1B0h+var_138]
0x18004d172  lea     rdx, [rsp+1B0h+var_160]
0x18004d177  mov     rax, [rcx]
0x18004d17a  mov     rax, [rax+108h]
0x18004d181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d186  mov     ebx, eax
0x18004d188  test    eax, eax
0x18004d18a  jns     short loc_18004D19C
0x18004d18c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d193  jb      short loc_18004D1F9
0x18004d195  mov     edx, 0E8h
0x18004d19a  jmp     short loc_18004D167
0x18004d19c  mov     ecx, [rsp+1B0h+var_160]
0x18004d1a0  mov     eax, 8
0x18004d1a5  mul     rcx
0x18004d1a8  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x18004d1af  cmovb   rax, rcx
0x18004d1b3  mov     rcx, rax; unsigned __int64
0x18004d1b6  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18004d1bb  mov     rdi, rax
0x18004d1be  test    rax, rax
0x18004d1c1  jnz     short loc_18004D226
0x18004d1c3  mov     r14d, 8007000Eh
0x18004d1c9  mov     ebx, r14d
0x18004d1cc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18004d1d3  jb      short loc_18004D1F9
0x18004d1d5  mov     edx, 0E9h
0x18004d1da  mov     dword ptr [rsp+1B0h+var_190], r14d
0x18004d1df  mov     rcx, cs:WPP_GLOBAL_Control
0x18004d1e6  lea     r8, WPP_3682f06399713e6eb6d5e127ede867b4_Traceguids
0x18004d1ed  mov     r9, rsi
0x18004d1f0  mov     rcx, [rcx+10h]
0x18004d1f4  call    WPP_SF_qD
0x18004d1f9  lea     rcx, [rsp+1B0h+var_148]
0x18004d1fe  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18004d203  lea     rcx, [rsp+1B0h+var_158]
0x18004d208  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
  ... truncated ...
```
