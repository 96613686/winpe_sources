# SensorDevice::InitializeByBlob(_GUID const &,uchar const *,long,long *)

- ea: `0x18001a100`
- end: `0x18001abdc`
- name: `?InitializeByBlob@SensorDevice@@UEAAJAEBU_GUID@@PEBEJPEAJ@Z`
- size: `2780`
- prototype: `__int64 __usercall@<rax>(SensorDevice *__hidden this@<rcx>, const struct _GUID *@<rdx>, const unsigned __int8 *@<r8>, int@<r9d>, int *)`
- caller_count: `0`
- callee_count: `27`
- tags: `file_ops, reparse_path, registry_config, service_task, broker_com_uri`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x180009a20`
- `0x18000d1f0`
- `0x180015e58`
- `0x180015e80`
- `0x18001a100`
- `0x18001abe4`
- `0x18001ad90`
- `0x18001b144`
- `0x18001b258`
- `0x18001bd24`
- `0x18001c854`
- `0x18001c96c`
- `0x18003fadc`
- `0x18003fe70`
- `0x180044b28`
- `0x180044f30`
- `0x180045300`
- `0x180045900`
- `0x1800477e4`
- `0x18004a270`
- `0x18004a560`
- `0x180056220`
- `0x180076274`
- `0x180076280`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a4ec`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001a4ec`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a152`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001a152`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a8e6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a8e6`
- `MFPlat!MFCreateAttributes` at `0x18001a208`
- `MFPlat!MFCreateAttributes` at `0x18001a208`
- `MFPlat!MFInitAttributesFromBlob` at `0x18001a225`
- `MFPlat!MFInitAttributesFromBlob` at `0x18001a225`

## pseudocode

```c
__int64 __fastcall SensorDevice::InitializeByBlob(
        SensorDevice *this,
        struct _GUID *a2,
        const unsigned __int8 *a3,
        int a4,
        int *a5)
{
  char v6; // bl
  int v9; // r13d
  signed int v10; // r15d
  HRESULT v11; // eax
  int ContainerSymbolicNameFromHostSymbolicName_Helper; // ebx
  HRESULT v13; // eax
  __int64 v14; // rax
  int v15; // r13d
  __int64 v16; // rcx
  IMFAttributes *v17; // rcx
  struct IMFAttributesVtbl *lpVtbl; // rax
  unsigned int v19; // eax
  struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *v20; // rdx
  int i; // eax
  unsigned int v22; // eax
  int v23; // eax
  int v24; // eax
  unsigned int v25; // r13d
  char v27; // r13
  struct IMFSensorStreamInternal *v28; // rbx
  __int64 v29; // rdx
  void *v30; // rax
  void *v31; // r15
  void *v32; // rcx
  void *v33; // rcx
  void *v35; // rcx
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdx
  __int64 v39; // rdx
  __int64 v40; // rdx
  __int64 v41; // rdx
  GuidTrace *v42; // rax
  const char *String; // rcx
  int v44; // r15d
  void **j; // rbx
  char v46; // cl
  char *v47; // rbx
  _QWORD *v48; // rcx
  __int64 v49; // rax
  __int64 v50; // r15
  unsigned int v51; // [rsp+60h] [rbp-A0h] BYREF
  struct IMFSensorStreamInternal *v52; // [rsp+68h] [rbp-98h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+70h] [rbp-90h] BYREF
  LPVOID pv; // [rsp+78h] [rbp-88h] BYREF
  char v55[4]; // [rsp+80h] [rbp-80h] BYREF
  char v56[4]; // [rsp+84h] [rbp-7Ch]
  struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *v57; // [rsp+88h] [rbp-78h]
  int v58; // [rsp+90h] [rbp-70h]
  signed int v59; // [rsp+94h] [rbp-6Ch]
  void *Block[3]; // [rsp+98h] [rbp-68h] BYREF
  int *v61; // [rsp+B0h] [rbp-50h]
  _OWORD Buf1[2]; // [rsp+B8h] [rbp-48h] BYREF
  unsigned __int16 v63[264]; // [rsp+E0h] [rbp-20h] BYREF

  v6 = 0;
  v61 = a5;
  v59 = 0;
  pv = a2;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  if ( !a5 )
  {
    ContainerSymbolicNameFromHostSymbolicName_Helper = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_63;
    v41 = 40;
    goto LABEL_91;
  }
  *a5 = 0;
  if ( *((_QWORD *)this + 10) )
  {
    ContainerSymbolicNameFromHostSymbolicName_Helper = -1072871856;
    if ( !g_wppLevels )
      goto LABEL_63;
    v41 = 41;
    goto LABEL_91;
  }
  if ( !a3
    || (v58 = 584, (unsigned int)a4 < 0x248)
    || (v9 = *((_DWORD *)a3 + 6)) == 0
    || (*(_DWORD *)v55 = *((_DWORD *)a3 + 4), a4 < *(int *)v55) )
  {
    v37 = -2147024809;
    ContainerSymbolicNameFromHostSymbolicName_Helper = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_63;
    v38 = 42;
    goto LABEL_143;
  }
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v6 = 1;
    *(_DWORD *)v56 = *((_DWORD *)a3 + 5);
    v57 = (struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *)*((_QWORD *)a3 + 1);
    ppMFAttributes = *(IMFAttributes **)a3;
    v42 = GuidTrace::GuidTrace((GuidTrace *)Buf1, (const struct _GUID *)pv);
    String = (const char *)*((_QWORD *)v42 + 3);
    if ( !String )
      String = FSString::GetString(v42);
    WPP_SF_qsiidddS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (__int64)String,
      (char)ppMFAttributes,
      (char)v57,
      v55[0],
      v56[0],
      v9,
      (__int64)(a3 + 32));
  }
  if ( (v6 & 1) != 0 )
    FSString::~FSString((FSString *)Buf1);
  v10 = a4 - 584;
  *(_OWORD *)((char *)this + 136) = *(_OWORD *)pv;
  if ( *((int *)a3 + 5) <= 0 )
  {
    v20 = (struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *)(a3 + 584);
    ContainerSymbolicNameFromHostSymbolicName_Helper = 0;
    v57 = (struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *)(a3 + 584);
    v15 = 584;
    goto LABEL_24;
  }
  ppMFAttributes = 0;
  if ( v10 < *((_DWORD *)a3 + 5) )
  {
    v11 = -2147024809;
    ContainerSymbolicNameFromHostSymbolicName_Helper = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_63;
    v40 = 44;
    goto LABEL_95;
  }
  v11 = MFCreateAttributes(&ppMFAttributes, 1u);
  ContainerSymbolicNameFromHostSymbolicName_Helper = v11;
  if ( v11 < 0 )
  {
    if ( !g_wppLevels )
    {
LABEL_74:
      v35 = ppMFAttributes;
      goto LABEL_61;
    }
    v40 = 45;
LABEL_95:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v40, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v11);
    goto LABEL_74;
  }
  v13 = MFInitAttributesFromBlob(ppMFAttributes, a3 + 584, *((_DWORD *)a3 + 5));
  ContainerSymbolicNameFromHostSymbolicName_Helper = v13;
  if ( v13 < 0 )
  {
    if ( g_wppLevels )
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 46, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v13);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
    goto LABEL_63;
  }
  v14 = *((int *)a3 + 5);
  v10 -= v14;
  v57 = (struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *)&a3[v14 + 584];
  v15 = v14 + 584;
  v58 = v14 + 584;
  if ( ppMFAttributes )
  {
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->AddRef)(ppMFAttributes);
    v16 = *((_QWORD *)this + 12);
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v17 = ppMFAttributes;
    *((_QWORD *)this + 12) = ppMFAttributes;
  }
  else
  {
    v17 = (IMFAttributes *)*((_QWORD *)this + 12);
    if ( v17 )
    {
      ((void (__fastcall *)(IMFAttributes *))v17->lpVtbl->Release)(v17);
      v17 = 0;
      *((_QWORD *)this + 12) = 0;
    }
  }
  lpVtbl = v17->lpVtbl;
  v51 = 0;
  if ( ((int (__fastcall *)(IMFAttributes *, __int64 *, unsigned int *))lpVtbl->GetUINT32)(
         v17,
         MF_SENSORDEVICE_SENSOR_ORIENTATION,
         &v51) >= 0 )
    v19 = v51;
  else
    v19 = 0;
  *((_DWORD *)this + 52) = v19;
  if ( v19 && v19 != 90 && v19 != 180 && v19 != 270 )
    *((_DWORD *)this + 52) = 0;
  if ( ppMFAttributes )
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
  v20 = v57;
LABEL_24:
  if ( v10 )
  {
    for ( i = 0; ; i = *(_DWORD *)v56 + 1 )
    {
      *(_DWORD *)v56 = i;
      if ( i >= *((_DWORD *)a3 + 6) )
        break;
      v22 = *(_DWORD *)v20;
      v59 = *(_DWORD *)v20;
      v52 = 0;
      v51 = 1;
      if ( (unsigned int)v10 < 0x10 )
      {
        v24 = -2147024809;
        ContainerSymbolicNameFromHostSymbolicName_Helper = -2147024809;
        if ( !g_wppLevels )
          goto LABEL_117;
        v29 = 47;
        goto LABEL_116;
      }
      if ( v10 < *((_DWORD *)v20 + 2) )
      {
        v24 = -2147024809;
        ContainerSymbolicNameFromHostSymbolicName_Helper = -2147024809;
        if ( !g_wppLevels )
          goto LABEL_117;
        v29 = 48;
        goto LABEL_116;
      }
      v23 = SensorDevice::CreateSensorStreamFromBlob(this, v20, (const unsigned __int8 *)v20 + 16, v22, &v52);
      ContainerSymbolicNameFromHostSymbolicName_Helper = v23;
      if ( v23 < 0 )
      {
        if ( g_wppLevels )
        {
          v39 = 49;
          goto LABEL_72;
        }
LABEL_60:
        v35 = v52;
LABEL_61:
        if ( v35 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v35 + 16LL))(v35);
        goto LABEL_63;
      }
      v24 = MFIsStreamAvailableToAppPackage(v52, *((_QWORD *)this + 19), &v51);
      ContainerSymbolicNameFromHostSymbolicName_Helper = v24;
      if ( v24 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_117;
        v29 = 50;
LABEL_116:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v24);
        goto LABEL_117;
      }
      v25 = v51;
      if ( v51 )
      {
        pv = 0;
        *(_DWORD *)v55 = 0;
        if ( (*(int (__fastcall **)(struct IMFSensorStreamInternal *, __int64 *, LPVOID *, char *))(*(_QWORD *)v52
                                                                                                  + 104LL))(
               v52,
               MF_DEVICESTREAM_REQUIRED_CAPABILITIES,
               &pv,
               v55) >= 0 )
        {
          ContainerSymbolicNameFromHostSymbolicName_Helper = MFCheckProcessCapabilities(
                                                               0,
                                                               pv,
                                                               (unsigned int)(*(_DWORD *)v55 + 1),
                                                               &v51);
          CoTaskMemFree(pv);
          pv = 0;
          if ( ContainerSymbolicNameFromHostSymbolicName_Helper < 0 )
          {
            if ( g_wppLevels )
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                51,
                &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
                this,
                ContainerSymbolicNameFromHostSymbolicName_Helper);
            goto LABEL_117;
          }
          v25 = v51;
        }
        if ( v25 )
        {
          v51 = 0;
          if ( !((*(int (__fastcall **)(struct IMFSensorStreamInternal *, __int64 *, unsigned int *))(*(_QWORD *)v52 + 56LL))(
                   v52,
                   MF_DEVICESTREAM_FRAMESERVER_HIDDEN,
                   &v51) >= 0
               ? v51
               : 0) )
          {
            v51 = 0;
            v27 = 1;
            if ( (*(int (__fastcall **)(struct IMFSensorStreamInternal *, __int128 *, unsigned int *))(*(_QWORD *)v52 + 56LL))(
                   v52,
                   &MF_DEVICESTREAM_ATTRIBUTE_FRAMESOURCE_TYPES,
                   &v51) >= 0 )
              v27 = v51;
            v28 = v52;
            v51 = *((_DWORD *)this + 30);
            Buf1[0] = GUID_00000000_0000_0000_0000_000000000000;
            if ( !(unsigned int)CTEntryArray<SensorDeviceId *>::SetSize((char *)this + 112, v51 + 1) )
            {
              v24 = -2147024882;
              ContainerSymbolicNameFromHostSymbolicName_Helper = -2147024882;
              if ( g_wppLevels )
              {
                v29 = 52;
                goto LABEL_116;
              }
LABEL_117:
              wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v52);
LABEL_63:
              if ( byte_18008D62D )
              {
                v36 = 60;
                goto LABEL_65;
              }
              goto LABEL_53;
            }
            *(_QWORD *)(*((_QWORD *)this + 14) + 8LL * v51) = v28;
            if ( v28 )
              (*(void (__fastcall **)(struct IMFSensorStreamInternal *))(*(_QWORD *)v28 + 8LL))(v28);
            v23 = (*(__int64 (__fastcall **)(struct IMFSensorStreamInternal *, const IID *, _OWORD *))(*(_QWORD *)v52 + 80LL))(
                    v52,
                    &MF_DEVICESTREAM_STREAM_CATEGORY,
                    Buf1);
            ContainerSymbolicNameFromHostSymbolicName_Helper = v23;
            if ( v23 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_60;
              v39 = 53;
LABEL_72:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v39,
                &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
                this,
                v23);
              goto LABEL_60;
            }
            if ( (v27 & 1) != 0 )
              *((_QWORD *)this + 20) |= 0x2000000000000uLL;
            if ( !memcmp_0(Buf1, &GUID_fb6c428a_0353_11d1_905f_0000c0cc16ba, 0x10u)
              || !memcmp_0(Buf1, &GUID_38a0cd98_d49b_4ce8_b48a_344667a17830, 0x10u) )
            {
              *((_QWORD *)this + 20) |= 0x1000000000000uLL;
            }
          }
        }
      }
      v10 -= v59;
      v20 = (struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *)((char *)v57 + v59);
      v15 = v59 + v58;
      v57 = v20;
      v58 += v59;
      if ( v52 )
      {
        (*(void (__fastcall **)(struct IMFSensorStreamInternal *))(*(_QWORD *)v52 + 16LL))(v52);
        v20 = v57;
      }
    }
    if ( !*((_DWORD *)this + 30) )
      *((_QWORD *)this + 20) = 0x4000000000000LL;
    *((_DWORD *)this + 22) = v15;
    v30 = operator new[](v15, (const struct std::nothrow_t *)&std::nothrow);
    v31 = v30;
    if ( v30 )
      memset_0(v30, 0, v15);
    else
      v31 = 0;
    v32 = (void *)*((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = v31;
    if ( v32 )
      operator delete(v32);
    v33 = (void *)*((_QWORD *)this + 10);
    if ( v33 )
    {
      memcpy_0(v33, a3, *((int *)this + 22));
      if ( !SGIsProcessInContainer() )
      {
LABEL_50:
        *v61 = *((_DWORD *)this + 22);
        goto LABEL_51;
      }
      memset_0(v63, 0, 0x208u);
      pv = 0;
      if ( (unsigned __int8)byte_18008D62D >= 0x10u )
      {
        utl::list<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>>::list<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>,utl::allocator<utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>>>(Block);
        v44 = 0;
        GatherContainerNamePairs(&GUID_e5323777_f976_4f5b_9b55_b94699c46e44, Block);
        GatherContainerNamePairs(&GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca, Block);
        for ( j = (void **)Block[0]; j != Block; j = (void **)*j )
        {
          if ( (unsigned __int8)byte_18008D62D >= 8u )
          {
            v46 = v44++;
            WPP_SF_qDSS(*((_QWORD *)WPP_GLOBAL_Control + 27), v46, (__int64)j[2], (__int64)j[6]);
          }
        }
        while ( 1 )
        {
          v47 = (char *)Block[0];
          if ( Block[0] == Block )
            break;
          v48 = (_QWORD *)*((_QWORD *)Block[0] + 1);
          v49 = *(_QWORD *)Block[0];
          *v48 = *(_QWORD *)Block[0];
          *(_QWORD *)(v49 + 8) = v48;
          utl::pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>::~pair<utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>,utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>>(v47 + 16);
          operator delete(v47);
        }
      }
      v50 = *((_QWORD *)this + 10);
      ContainerSymbolicNameFromHostSymbolicName_Helper = FindContainerSymbolicNameFromHostSymbolicName_Helper(
                                                           &GUID_e5323777_f976_4f5b_9b55_b94699c46e44,
                                                           (const unsigned __int16 *)(v50 + 32),
                                                           v63);
      if ( ContainerSymbolicNameFromHostSymbolicName_Helper == -1072875819 )
        ContainerSymbolicNameFromHostSymbolicName_Helper = FindContainerSymbolicNameFromHostSymbolicName_Helper(
                                                             &GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca,
                                                             (const unsigned __int16 *)(v50 + 32),
                                                             v63);
      if ( ContainerSymbolicNameFromHostSymbolicName_Helper < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_63;
        v41 = 56;
LABEL_91:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v41,
          &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
          this,
          ContainerSymbolicNameFromHostSymbolicName_Helper);
        goto LABEL_63;
      }
      if ( (unsigned __int8)byte_18008D62D >= 8u )
        WPP_SF_qSS(*((_QWORD *)WPP_GLOBAL_Control + 27), *((_QWORD *)this + 10) + 32LL, (__int64)v63);
      v37 = StringCchCopyW((unsigned __int16 *)(*((_QWORD *)this + 10) + 32LL), 0x104u, v63);
      ContainerSymbolicNameFromHostSymbolicName_Helper = v37;
      if ( v37 >= 0 )
      {
        v37 = StringCchLengthW(v63, 0x104u, (unsigned __int64 *)&pv);
        ContainerSymbolicNameFromHostSymbolicName_Helper = v37;
        if ( v37 >= 0 )
        {
          *(_DWORD *)(*((_QWORD *)this + 10) + 28LL) = (_DWORD)pv;
          goto LABEL_50;
        }
        if ( !g_wppLevels )
          goto LABEL_63;
        v38 = 59;
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_63;
        v38 = 58;
      }
    }
    else
    {
      v37 = -2147024882;
      ContainerSymbolicNameFromHostSymbolicName_Helper = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_63;
      v38 = 54;
    }
LABEL_143:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v38, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v37);
    goto LABEL_63;
  }
LABEL_51:
  if ( ContainerSymbolicNameFromHostSymbolicName_Helper < 0 )
    goto LABEL_63;
  if ( (unsigned __int8)byte_18008D62D >= 8u )
  {
    v36 = 61;
LABEL_65:
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v36,
      &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
      this,
      ContainerSymbolicNameFromHostSymbolicName_Helper);
  }
LABEL_53:
  LeaveCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  return (unsigned int)ContainerSymbolicNameFromHostSymbolicName_Helper;
}

```

## disassembly

```asm
0x18001a100  mov     [rsp-8+arg_18], rbx
0x18001a105  push    rbp
0x18001a106  push    rsi
0x18001a107  push    rdi
0x18001a108  push    r12
0x18001a10a  push    r13
0x18001a10c  push    r14
0x18001a10e  push    r15
0x18001a110  lea     rbp, [rsp-200h]
0x18001a118  sub     rsp, 300h
0x18001a11f  mov     rax, cs:__security_cookie
0x18001a126  xor     rax, rsp
0x18001a129  mov     [rbp+230h+var_40], rax
0x18001a130  mov     r14, [rbp+230h+arg_20]
0x18001a137  mov     rsi, rcx
0x18001a13a  xor     ebx, ebx
0x18001a13c  mov     [rbp+230h+var_280], r14
0x18001a140  add     rcx, 20h ; ' '; lpCriticalSection
0x18001a144  mov     [rbp+230h+var_29C], ebx
0x18001a147  mov     r15d, r9d
0x18001a14a  mov     [rsp+330h+pv], rdx
0x18001a14f  mov     r12, r8
0x18001a152  call    cs:__imp_EnterCriticalSection
0x18001a158  test    r14, r14
0x18001a15b  jz      loc_18001A68C
0x18001a161  mov     [r14], ebx
0x18001a164  cmp     [rsi+50h], rbx
0x18001a168  jnz     loc_18001A7F1
0x18001a16e  test    r12, r12
0x18001a171  jz      loc_18001AB9B
0x18001a177  mov     eax, 248h
0x18001a17c  mov     [rbp+230h+var_2A0], eax
0x18001a17f  cmp     r15d, eax
0x18001a182  jb      loc_18001AB9B
0x18001a188  mov     r13d, [r12+18h]
0x18001a18d  test    r13d, r13d
0x18001a190  jz      loc_18001AB9B
0x18001a196  mov     eax, [r12+10h]
0x18001a19b  mov     dword ptr [rbp+230h+var_2B0], eax
0x18001a19e  cmp     r15d, eax
0x18001a1a1  jl      loc_18001AB9B
0x18001a1a7  cmp     cs:byte_18008D62D, 8
0x18001a1ae  lea     r14d, [rbx+1]
0x18001a1b2  jnb     loc_18001A75F
0x18001a1b8  test    r14b, bl
0x18001a1bb  jnz     loc_18001A81F
0x18001a1c1  mov     rax, [rsp+330h+pv]
0x18001a1c6  lea     r13, [r12+248h]
0x18001a1ce  add     r15d, 0FFFFFDB8h
0x18001a1d5  movups  xmm0, xmmword ptr [rax]
0x18001a1d8  movdqu  xmmword ptr [rsi+88h], xmm0
0x18001a1e0  cmp     dword ptr [r12+14h], 0
0x18001a1e6  jle     loc_18001A571
0x18001a1ec  mov     [rsp+330h+ppMFAttributes], 0
0x18001a1f5  cmp     r15d, [r12+14h]
0x18001a1fa  jl      loc_18001A66E
0x18001a200  mov     edx, r14d; cInitialSize
0x18001a203  lea     rcx, [rsp+330h+ppMFAttributes]; ppMFAttributes
0x18001a208  call    cs:__imp_MFCreateAttributes
0x18001a20e  mov     ebx, eax
0x18001a210  test    eax, eax
0x18001a212  js      loc_18001A657
0x18001a218  mov     r8d, [r12+14h]; cbBufSize
0x18001a21d  mov     rdx, r13; pBuf
0x18001a220  mov     rcx, [rsp+330h+ppMFAttributes]; pAttributes
0x18001a225  call    cs:__imp_MFInitAttributesFromBlob
0x18001a22b  mov     ebx, eax
0x18001a22d  test    eax, eax
0x18001a22f  js      loc_18001A855
0x18001a235  movsxd  rax, dword ptr [r12+14h]
0x18001a23a  sub     r15d, eax
0x18001a23d  lea     rcx, [rax+r13]
0x18001a241  mov     [rbp+230h+var_2A8], rcx
0x18001a245  lea     r13d, [rax+248h]
0x18001a24c  mov     rcx, [rsp+330h+ppMFAttributes]
0x18001a251  mov     [rbp+230h+var_2A0], r13d
0x18001a255  test    rcx, rcx
0x18001a258  jz      loc_18001A5FA
0x18001a25e  mov     rax, [rcx]
0x18001a261  mov     rax, [rax+8]
0x18001a265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a26a  mov     rcx, [rsi+60h]
0x18001a26e  test    rcx, rcx
0x18001a271  jz      short loc_18001A27F
0x18001a273  mov     rax, [rcx]
0x18001a276  mov     rax, [rax+10h]
0x18001a27a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a27f  mov     rcx, [rsp+330h+ppMFAttributes]
0x18001a284  mov     [rsi+60h], rcx
0x18001a288  mov     rax, [rcx]
0x18001a28b  lea     r8, [rsp+330h+var_2D0]
0x18001a290  lea     rdx, MF_SENSORDEVICE_SENSOR_ORIENTATION
0x18001a297  mov     [rsp+330h+var_2D0], 0
0x18001a29f  mov     rax, [rax+38h]
0x18001a2a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2a8  test    eax, eax
0x18001a2aa  jns     loc_18001A890
0x18001a2b0  xor     eax, eax
0x18001a2b2  mov     [rsi+0D0h], eax
0x18001a2b8  test    eax, eax
0x18001a2ba  jnz     loc_18001A899
0x18001a2c0  mov     rcx, [rsp+330h+ppMFAttributes]
0x18001a2c5  test    rcx, rcx
0x18001a2c8  jz      short loc_18001A2D6
0x18001a2ca  mov     rax, [rcx]
0x18001a2cd  mov     rax, [rax+10h]
0x18001a2d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a2d6  mov     rdx, [rbp+230h+var_2A8]; struct __MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *
0x18001a2da  test    r15d, r15d
0x18001a2dd  jz      loc_18001A4D3
0x18001a2e3  xor     eax, eax
0x18001a2e5  mov     dword ptr [rbp+230h+var_2AC], eax
0x18001a2e8  cmp     eax, [r12+18h]
0x18001a2ed  jge     loc_18001A45A
0x18001a2f3  mov     eax, [rdx]
0x18001a2f5  mov     [rbp+230h+var_29C], eax
0x18001a2f8  mov     [rsp+330h+var_2C8], 0
0x18001a301  mov     [rsp+330h+var_2D0], r14d
0x18001a306  cmp     r15d, 10h
0x18001a30a  jb      loc_18001A95B
0x18001a310  cmp     r15d, [rdx+8]
0x18001a314  jl      loc_18001A944
0x18001a31a  lea     rcx, [rsp+330h+var_2C8]
0x18001a31f  mov     r9d, eax; int
0x18001a322  mov     [rsp+330h+var_310], rcx; struct IMFSensorStreamInternal **
0x18001a327  lea     r8, [rdx+10h]; unsigned __int8 *
0x18001a32b  mov     rcx, rsi; this
0x18001a32e  call    ?CreateSensorStreamFromBlob@SensorDevice@@IEAAJPEAU__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005@@PEBEJPEAPEAUIMFSensorStreamInternal@@@Z; SensorDevice::CreateSensorStreamFromBlob(__MIDL___MIDL_itf_mfdeviceinternal_0000_0026_0005 *,uchar const *,long,IMFSensorStreamInternal * *)
0x18001a333  mov     ebx, eax
0x18001a335  test    eax, eax
0x18001a337  js      loc_18001A622
0x18001a33d  mov     rdx, [rsi+98h]
0x18001a344  lea     r8, [rsp+330h+var_2D0]
0x18001a349  mov     rcx, [rsp+330h+var_2C8]
0x18001a34e  call    MFIsStreamAvailableToAppPackage
0x18001a353  mov     ebx, eax
0x18001a355  test    eax, eax
0x18001a357  js      loc_18001A934
0x18001a35d  mov     r13d, [rsp+330h+var_2D0]
0x18001a362  test    r13d, r13d
0x18001a365  jz      loc_18001A52F
0x18001a36b  mov     rcx, [rsp+330h+var_2C8]
0x18001a370  lea     r9, [rbp+230h+var_2B0]
0x18001a374  mov     [rsp+330h+pv], 0
0x18001a37d  lea     r8, [rsp+330h+pv]
0x18001a382  mov     dword ptr [rbp+230h+var_2B0], 0
0x18001a389  lea     rdx, MF_DEVICESTREAM_REQUIRED_CAPABILITIES
0x18001a390  mov     rax, [rcx]
0x18001a393  mov     rax, [rax+68h]
0x18001a397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a39c  test    eax, eax
0x18001a39e  jns     loc_18001A8C7
0x18001a3a4  test    r13d, r13d
0x18001a3a7  jz      loc_18001A52F
0x18001a3ad  mov     rcx, [rsp+330h+var_2C8]
0x18001a3b2  lea     r8, [rsp+330h+var_2D0]
0x18001a3b7  lea     rdx, MF_DEVICESTREAM_FRAMESERVER_HIDDEN
0x18001a3be  mov     [rsp+330h+var_2D0], 0
0x18001a3c6  mov     rax, [rcx]
0x18001a3c9  mov     rax, [rax+38h]
0x18001a3cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3d2  test    eax, eax
0x18001a3d4  jns     loc_18001A903
0x18001a3da  xor     eax, eax
0x18001a3dc  test    eax, eax
0x18001a3de  jnz     loc_18001A52F
0x18001a3e4  mov     rcx, [rsp+330h+var_2C8]
0x18001a3e9  lea     r8, [rsp+330h+var_2D0]
0x18001a3ee  mov     [rsp+330h+var_2D0], eax
0x18001a3f2  lea     rdx, MF_DEVICESTREAM_ATTRIBUTE_FRAMESOURCE_TYPES
0x18001a3f9  mov     rax, [rcx]
0x18001a3fc  mov     rax, [rax+38h]
0x18001a400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a405  mov     r13d, r14d
0x18001a408  test    eax, eax
0x18001a40a  jns     loc_18001A90C
0x18001a410  mov     ecx, [rsi+78h]
0x18001a413  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18001a41a  mov     rbx, [rsp+330h+var_2C8]
0x18001a41f  mov     [rsp+330h+var_2D0], ecx
0x18001a423  lea     edx, [rcx+1]
0x18001a426  lea     rcx, [rsi+70h]
0x18001a42a  movdqu  [rbp+230h+Buf1], xmm0
0x18001a42f  call    ?SetSize@?$CTEntryArray@PEAVSensorDeviceId@@@@QEAAHKK@Z; CTEntryArray<SensorDeviceId *>::SetSize(ulong,ulong)
0x18001a434  test    eax, eax
0x18001a436  jnz     loc_18001A6BF
0x18001a43c  mov     eax, 8007000Eh
0x18001a441  mov     ebx, eax
0x18001a443  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18001a44a  jb      loc_18001A98E
0x18001a450  mov     edx, 34h ; '4'
0x18001a455  jmp     loc_18001A970
0x18001a45a  cmp     dword ptr [rsi+78h], 0
0x18001a45e  jz      loc_18001A99D
0x18001a464  mov     [rsi+58h], r13d
0x18001a468  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001a46f  movsxd  r13, r13d
0x18001a472  mov     rcx, r13; unsigned __int64
0x18001a475  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18001a47a  mov     r15, rax
0x18001a47d  test    rax, rax
0x18001a480  jz      loc_18001A6AD
0x18001a486  mov     r8, r13; Size
0x18001a489  xor     edx, edx; Val
0x18001a48b  mov     rcx, rax; void *
0x18001a48e  call    memset_0
0x18001a493  mov     rcx, [rsi+50h]; Block
0x18001a497  mov     [rsi+50h], r15
0x18001a49b  test    rcx, rcx
0x18001a49e  jnz     loc_18001A6B5
0x18001a4a4  mov     rcx, [rsi+50h]; void *
0x18001a4a8  test    rcx, rcx
0x18001a4ab  jz      loc_18001A5E0
0x18001a4b1  movsxd  r8, dword ptr [rsi+58h]; Size
0x18001a4b5  mov     rdx, r12; Src
0x18001a4b8  call    memcpy_0
0x18001a4bd  call    ?SGIsProcessInContainer@@YA_NXZ; SGIsProcessInContainer(void)
0x18001a4c2  test    al, al
0x18001a4c4  jnz     loc_18001A9B3
0x18001a4ca  mov     rcx, [rbp+230h+var_280]
0x18001a4ce  mov     eax, [rsi+58h]
0x18001a4d1  mov     [rcx], eax
0x18001a4d3  test    ebx, ebx
0x18001a4d5  js      loc_18001A5A8
0x18001a4db  cmp     cs:byte_18008D62D, 8
0x18001a4e2  jnb     loc_18001AB91
0x18001a4e8  lea     rcx, [rsi+20h]; lpCriticalSection
0x18001a4ec  call    cs:__imp_LeaveCriticalSection
0x18001a4f2  mov     eax, ebx
0x18001a4f4  mov     rcx, [rbp+230h+var_40]
0x18001a4fb  xor     rcx, rsp; StackCookie
0x18001a4fe  call    __security_check_cookie
0x18001a503  mov     rbx, [rsp+330h+arg_18]
0x18001a50b  add     rsp, 300h
0x18001a512  pop     r15
0x18001a514  pop     r14
0x18001a516  pop     r13
0x18001a518  pop     r12
0x18001a51a  pop     rdi
0x18001a51b  pop     rsi
0x18001a51c  pop     rbp
0x18001a51d  retn
0x18001a51e  mov     rax, 1000000000000h
0x18001a528  or      [rsi+0A0h], rax
0x18001a52f  movsxd  rcx, [rbp+230h+var_29C]
0x18001a533  mov     rdx, [rbp+230h+var_2A8]
0x18001a537  sub     r15d, ecx
0x18001a53a  mov     r13d, [rbp+230h+var_2A0]
0x18001a53e  add     rdx, rcx
0x18001a541  add     r13d, ecx
0x18001a544  mov     [rbp+230h+var_2A8], rdx
0x18001a548  mov     rcx, [rsp+330h+var_2C8]
0x18001a54d  mov     [rbp+230h+var_2A0], r13d
0x18001a551  test    rcx, rcx
0x18001a554  jz      short loc_18001A566
0x18001a556  mov     rax, [rcx]
0x18001a559  mov     rax, [rax+10h]
0x18001a55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a562  mov     rdx, [rbp+230h+var_2A8]
0x18001a566  mov     eax, dword ptr [rbp+230h+var_2AC]
0x18001a569  add     eax, r14d
0x18001a56c  jmp     loc_18001A2E5
0x18001a571  mov     rdx, r13
0x18001a574  xor     ebx, ebx
0x18001a576  mov     [rbp+230h+var_2A8], rdx
0x18001a57a  mov     r13d, 248h
0x18001a580  jmp     loc_18001A2DA
0x18001a585  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18001a58c  jnb     loc_18001A92A
0x18001a592  mov     rcx, [rsp+330h+var_2C8]
0x18001a597  test    rcx, rcx
0x18001a59a  jz      short loc_18001A5A8
0x18001a59c  mov     rax, [rcx]
0x18001a59f  mov     rax, [rax+10h]
0x18001a5a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a5a8  cmp     cs:byte_18008D62D, r14b
0x18001a5af  jb      loc_18001A4E8
0x18001a5b5  mov     edx, 3Ch ; '<'
0x18001a5ba  mov     rcx, cs:WPP_GLOBAL_Control
0x18001a5c1  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x18001a5c8  mov     r9, rsi
0x18001a5cb  mov     dword ptr [rsp+330h+var_310], ebx
0x18001a5cf  mov     rcx, [rcx+0D8h]
0x18001a5d6  call    WPP_SF_qD
0x18001a5db  jmp     loc_18001A4E8
0x18001a5e0  mov     eax, 8007000Eh
0x18001a5e5  mov     ebx, eax
0x18001a5e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18001a5ee  jb      short loc_18001A5A8
0x18001a5f0  mov     edx, 36h ; '6'
0x18001a5f5  jmp     loc_18001ABB9
0x18001a5fa  mov     rcx, [rsi+60h]
0x18001a5fe  test    rcx, rcx
0x18001a601  jz      loc_18001A288
0x18001a607  mov     rax, [rcx]
0x18001a60a  mov     rax, [rax+10h]
0x18001a60e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a613  xor     ecx, ecx
0x18001a615  mov     qword ptr [rsi+60h], 0
0x18001a61d  jmp     loc_18001A288
  ... truncated ...
```
