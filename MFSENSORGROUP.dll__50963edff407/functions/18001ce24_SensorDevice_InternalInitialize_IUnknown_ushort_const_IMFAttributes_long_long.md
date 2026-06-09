# SensorDevice::InternalInitialize(IUnknown *,ushort const *,IMFAttributes *,long,long *)

- ea: `0x18001ce24`
- end: `0x18001e304`
- name: `?InternalInitialize@SensorDevice@@IEAAJPEAUIUnknown@@PEBGPEAUIMFAttributes@@JPEAJ@Z`
- size: `5344`
- prototype: `__int64 __usercall@<rax>(SensorDevice *__hidden this@<rcx>, struct IUnknown *@<rdx>, const unsigned __int16 *@<r8>, struct IMFAttributes *@<r9>, int, int *)`
- caller_count: `2`
- callee_count: `34`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180006230`
- `0x180048270`

## callees

- `0x180002474`
- `0x180005fa0`
- `0x180008f9c`
- `0x1800099b4`
- `0x18000a450`
- `0x18000aa08`
- `0x180015e80`
- `0x180016328`
- `0x18001635c`
- `0x180019a4c`
- `0x180019d8c`
- `0x18001b3d8`
- `0x18001bd24`
- `0x18001c854`
- `0x18001c96c`
- `0x18001cd8c`
- `0x18001ce24`
- `0x18001e30c`
- `0x18001ee8c`
- `0x18001eefc`
- `0x18001f09c`
- `0x1800261a8`
- `0x180031920`
- `0x18003491c`
- `0x180036d7c`
- `0x18003ccec`
- `0x180044b28`
- `0x180044f30`
- `0x180045300`
- `0x180045900`
- `0x18004a734`
- `0x18004a854`
- `0x180050c3c`
- `0x180077010`

## import_xrefs

- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18001d99c`
- `api-ms-win-devices-config-l1-1-1!CM_Open_Device_Interface_KeyW` at `0x18001d99c`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d9d6`
- `api-ms-win-core-registry-l1-1-0!RegQueryValueExW` at `0x18001d9d6`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d2c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d96b`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d2c5`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18001d96b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d30c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001d30c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001de13`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18001de13`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001d3c4`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001d905`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001d3c4`
- `api-ms-win-core-com-l1-1-0!IIDFromString` at `0x18001d905`
- `MFPlat!MFCreateAttributes` at `0x18001dad0`
- `MFPlat!MFCreateAttributes` at `0x18001dba3`
- `MFPlat!MFCreateAttributes` at `0x18001dad0`
- `MFPlat!MFCreateAttributes` at `0x18001dba3`

## pseudocode

```c
__int64 __fastcall SensorDevice::InternalInitialize(
        SensorDevice *this,
        struct IUnknown *a2,
        unsigned __int16 *a3,
        struct IMFAttributes *a4,
        int a5,
        int *a6)
{
  bool v6; // r15
  __int64 v8; // rcx
  struct IUnknown *v12; // rsi
  wchar_t *v13; // r12
  signed int v14; // ebx
  __int64 v15; // rdx
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  const char *String; // rax
  char v20; // r8
  UINT32 i; // r15d
  int v22; // eax
  __int64 v23; // rdx
  char *v24; // r15
  __int64 v25; // rax
  int DeviceInterfacePropertySz; // eax
  __int64 v27; // rdx
  const unsigned __int16 *SensorGroupPropertyName; // rax
  HRESULT v30; // eax
  __int64 v31; // rdx
  const char *v32; // rax
  const wchar_t *v33; // r8
  LPVOID v34; // r9
  const WCHAR *v35; // r15
  struct IMFAttributesVtbl *v36; // rax
  int v37; // eax
  __int64 v38; // rdx
  void **v39; // rax
  void *v40; // rcx
  int v41; // eax
  __int64 v42; // rdx
  __int64 *v43; // rcx
  const char *v44; // rax
  const wchar_t *v45; // r8
  bool *v46; // rbx
  const char *v47; // rax
  void **unique; // rax
  void *v49; // rcx
  const unsigned __int16 *v50; // rax
  HKEY v51; // rbx
  CONFIGRET v52; // eax
  int v53; // eax
  HRESULT v54; // eax
  __int64 v55; // rdx
  char v56; // bl
  struct IMFAttributesVtbl *lpVtbl; // rax
  struct IMFAttributesVtbl *v58; // rax
  UINT32 j; // ebx
  struct IMFAttributesVtbl *v60; // rax
  HRESULT (__stdcall *GetItemByIndex)(IMFAttributes *, UINT32, GUID *, PROPVARIANT *); // rax
  int v62; // eax
  char v63; // r15
  const char *v64; // rax
  int v65; // eax
  __int64 v66; // rdx
  struct IMFMediaSource *v67; // rcx
  int v68; // eax
  __int64 v69; // rdx
  __int64 ROISupportedConfig; // rax
  size_t v71; // rbx
  char *v72; // rax
  int v73; // r14d
  unsigned __int16 *v74; // r8
  __int64 v75; // rdx
  unsigned __int16 *v76; // rax
  unsigned int v77; // eax
  __int64 v78; // rdx
  __int64 v79; // rcx
  _WORD *v80; // rax
  unsigned int *lpcbData; // [rsp+28h] [rbp-D8h]
  struct IUnknown *v82; // [rsp+40h] [rbp-C0h]
  UINT32 v83; // [rsp+48h] [rbp-B8h] BYREF
  struct IUnknown *v84; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbData[2]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v86; // [rsp+60h] [rbp-A0h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+68h] [rbp-98h] BYREF
  struct IMFMediaSource *v88; // [rsp+70h] [rbp-90h] BYREF
  int v89; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v90; // [rsp+7Ch] [rbp-84h] BYREF
  unsigned int v91; // [rsp+80h] [rbp-80h] BYREF
  int v92; // [rsp+84h] [rbp-7Ch] BYREF
  LPVOID pv; // [rsp+88h] [rbp-78h] BYREF
  HKEY hKey; // [rsp+90h] [rbp-70h] BYREF
  __int64 v95; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v96; // [rsp+A0h] [rbp-60h] BYREF
  PROPVARIANT pvar[2]; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v98; // [rsp+B8h] [rbp-48h]
  __int64 v99; // [rsp+C0h] [rbp-40h]
  BYTE Data[4]; // [rsp+C8h] [rbp-38h] BYREF
  DWORD Type; // [rsp+CCh] [rbp-34h] BYREF
  unsigned __int16 *v102; // [rsp+D0h] [rbp-30h]
  int *v103; // [rsp+D8h] [rbp-28h]
  _BYTE v104[24]; // [rsp+E0h] [rbp-20h] BYREF
  const char *v105; // [rsp+F8h] [rbp-8h]
  void *Block[2]; // [rsp+100h] [rbp+0h] BYREF
  char v107; // [rsp+110h] [rbp+10h]
  OLECHAR sz[264]; // [rsp+120h] [rbp+20h] BYREF

  v6 = 0;
  v102 = a3;
  v103 = a6;
  v8 = 0;
  v95 = 0;
  v82 = 0;
  v89 = 0;
  v91 = 0;
  v12 = 0;
  v96 = 0;
  v13 = 0;
  v88 = 0;
  pv = 0;
  v90 = 0;
  v92 = 0;
  ppMFAttributes = 0;
  *(_QWORD *)cbData = 0;
  *(_DWORD *)Data = 0;
  hKey = 0;
  Type = 0;
  if ( !a2 )
  {
    v14 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_63;
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      118,
      &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
      this,
      -2147024809);
    goto LABEL_60;
  }
  if ( !*((_QWORD *)this + 10) )
  {
    if ( !*((_QWORD *)this + 21) )
    {
      v14 = -1072875810;
      if ( !g_wppLevels )
        goto LABEL_63;
      v15 = 120;
      goto LABEL_7;
    }
    if ( a4 )
    {
      v6 = (unsigned int)MFGetAttributeUINT32(a4, MF_FSM_CLIENT_ACTIVATED_MEDIASOURCE, 0) != 0;
      *((_BYTE *)this + 224) = (unsigned int)MFGetAttributeUINT32(a4, MF_FSM_BLOCK_FACEAUTH_CONTROL, 0) != 0;
    }
    if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_5bc8a76b_869a_46a3_9b03_fa218a66aebe,
           &v95) >= 0 )
    {
      v83 = 0;
      if ( !a4 )
      {
        v14 = -2147024809;
        if ( !g_wppLevels )
        {
LABEL_18:
          v12 = 0;
          goto LABEL_60;
        }
        v16 = 121;
LABEL_17:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v16,
          &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
          this,
          -2147024809);
        goto LABEL_18;
      }
      v17 = ((__int64 (__fastcall *)(struct IMFAttributes *, __int64 *, char *))a4->lpVtbl->GetGUID)(
              a4,
              MF_SENSORTRANSFORM_FACTORYCLSID,
              (char *)this + 136);
      v14 = v17;
      if ( v17 >= 0 )
      {
        v17 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v95 + 24LL))(v95, &v83);
        v14 = v17;
        if ( v17 >= 0 )
        {
          if ( (unsigned __int8)byte_18008D62D >= 0x10u )
          {
            GuidTrace::GuidTrace((GuidTrace *)pvar, (const struct _GUID *)((char *)this + 136));
            if ( (unsigned __int8)byte_18008D62D >= 8u )
            {
              String = (const char *)v99;
              v20 = v83;
              if ( !v99 )
                String = FSString::GetString((FSString *)pvar);
              WPP_SF_qsD(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                124,
                (unsigned int)&WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
                (_DWORD)this,
                (__int64)String,
                v20);
            }
            FSString::~FSString((FSString *)pvar);
          }
          for ( i = 0; ; ++i )
          {
            if ( i >= v83 )
              goto LABEL_93;
            v86 = 0;
            v84 = 0;
            v22 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v95 + 32LL))(v95, i, &v86);
            v14 = v22;
            if ( v22 < 0 )
              break;
            v22 = (**(__int64 (__fastcall ***)(__int64, GUID *, struct IUnknown **))v86)(
                    v86,
                    &GUID_30acfa70_af94_4ad4_be36_14e23900c104,
                    &v84);
            v14 = v22;
            if ( v22 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_45;
              v23 = 126;
LABEL_44:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v23,
                &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
                this,
                v22);
              goto LABEL_45;
            }
            if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add((__int64 *)this + 14, (__int64)v84) )
            {
              v22 = -2147024882;
              v14 = -2147024882;
              if ( g_wppLevels )
              {
                v23 = 127;
                goto LABEL_44;
              }
LABEL_45:
              wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v84);
              wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v86);
              goto LABEL_18;
            }
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v84);
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v86);
          }
          if ( !g_wppLevels )
            goto LABEL_45;
          v23 = 125;
          goto LABEL_44;
        }
        if ( !g_wppLevels )
          goto LABEL_18;
        v18 = 123;
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_18;
        v18 = 122;
      }
LABEL_22:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v18, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v17);
      goto LABEL_18;
    }
    if ( !v6
      && ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 **))a2->lpVtbl->QueryInterface)(
           a2,
           &GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67,
           &v96) >= 0 )
    {
      memset_0(sz, 0, 0x208u);
      v24 = 0;
      v25 = *v96;
      Block[0] = &pv;
      Block[1] = 0;
      v107 = 1;
      v14 = (*(__int64 (__fastcall **)(__int64 *, const IID *, void **, unsigned int *))(v25 + 104))(
              v96,
              &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
              &Block[1],
              &v90);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)Block);
      if ( v14 < 0 )
      {
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            128,
            &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
            this,
            v14);
        goto LABEL_18;
      }
      v17 = (*(__int64 (__fastcall **)(__int64 *, GUID *, struct IMFMediaSource **))(*v96 + 264))(
              v96,
              &GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66,
              &v88);
      v14 = v17;
      if ( v17 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_18;
        v18 = 129;
        goto LABEL_22;
      }
      DeviceInterfacePropertySz = GetDeviceInterfacePropertySz(a3);
      v14 = DeviceInterfacePropertySz;
      if ( DeviceInterfacePropertySz < 0 )
      {
        if ( !g_wppLevels )
        {
LABEL_58:
          v13 = *(wchar_t **)cbData;
LABEL_59:
          v12 = (struct IUnknown *)v24;
          goto LABEL_60;
        }
        v27 = 130;
LABEL_57:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v27,
          &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
          this,
          DeviceInterfacePropertySz);
        goto LABEL_58;
      }
      v13 = *(wchar_t **)cbData;
      if ( !*(_QWORD *)cbData )
      {
        GetDevicePropertySz(a3);
        v13 = 0;
      }
      SensorGroupPropertyName = GetSensorGroupPropertyName(0xAu);
      if ( (int)FSGetDeviceInterfaceRegistryEntry2(
                  (const unsigned __int16 *)pv,
                  SensorGroupPropertyName,
                  (unsigned __int8 *)sz,
                  0x208u,
                  cbData,
                  lpcbData) >= 0 )
      {
        v30 = IIDFromString(sz, (LPIID)((char *)this + 136));
        v14 = v30;
        if ( v30 < 0 )
        {
          if ( g_wppLevels )
          {
            v31 = 131;
LABEL_84:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v31,
              &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
              this,
              v30);
            goto LABEL_59;
          }
          goto LABEL_226;
        }
      }
      if ( (unsigned __int8)byte_18008D62D >= 0x10u )
      {
        GuidTrace::GuidTrace((GuidTrace *)pvar, (const struct _GUID *)((char *)this + 136));
        if ( (unsigned __int8)byte_18008D62D >= 8u )
        {
          v32 = (const char *)v99;
          v33 = L"NoFriendlyName";
          v34 = pv;
          if ( v13 )
            v33 = v13;
          if ( !v99 )
            v32 = FSString::GetString((FSString *)pvar);
          WPP_SF_qdsSS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            *((_DWORD *)this + 52),
            (__int64)v32,
            (__int64)v33,
            (__int64)v34);
        }
        FSString::~FSString((FSString *)pvar);
      }
LABEL_93:
      if ( !a3 )
      {
        v35 = (const WCHAR *)pv;
        goto LABEL_135;
      }
LABEL_134:
      v35 = a3;
LABEL_135:
      v46 = (bool *)this + 225;
      if ( v35 )
      {
        memset_0(sz, 0, 0x208u);
        *v46 = v46 == 0;
        if ( (unsigned __int8)byte_18008D62D >= 8u )
        {
          v47 = "true";
          if ( this != (SensorDevice *)-225LL )
            v47 = "false";
          WPP_SF_qSsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)sz, (__int64)v47, (__int64)v35);
        }
      }
      else
      {
        *v46 = 1;
        if ( (unsigned __int8)byte_18008D62D >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 146, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this);
      }
      v51 = hKey;
      if ( hKey )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)Block);
        RegCloseKey(v51);
        wil::last_error_context::~last_error_context((wil::last_error_context *)Block);
      }
      hKey = 0;
      v52 = CM_Open_Device_Interface_KeyW(v35, 0x20019u, 1u, &hKey, 0);
      v24 = 0;
      if ( !v52 )
      {
        cbData[0] = 4;
        RegQueryValueExW(hKey, L"FSColorInfoOverride", 0, &Type, Data, cbData);
      }
      if ( v88 )
      {
        v86 = 0;
        v84 = 0;
        v53 = ((__int64 (__fastcall *)(struct IMFMediaSource *, GUID *, __int64 *))v88->lpVtbl->QueryInterface)(
                v88,
                &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8,
                &v86);
        v14 = v53;
        if ( v53 < 0 )
        {
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              147,
              &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
              this,
              v53);
          if ( v84 )
            ((void (__fastcall *)(struct IUnknown *))v84->lpVtbl->Release)(v84);
          if ( v86 )
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
          goto LABEL_59;
        }
        v54 = (*(__int64 (__fastcall **)(__int64, struct IUnknown **))(*(_QWORD *)v86 + 104LL))(v86, &v84);
        v14 = v54;
        if ( v54 < 0 )
        {
          if ( !g_wppLevels )
          {
LABEL_175:
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v84);
            v43 = &v86;
            goto LABEL_121;
          }
          v55 = 148;
LABEL_174:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v55,
            &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
            this,
            v54);
          goto LABEL_175;
        }
        v54 = MFCreateAttributes(&ppMFAttributes, 1u);
        v14 = v54;
        if ( v54 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_175;
          v55 = 149;
          goto LABEL_174;
        }
        v54 = ((__int64 (__fastcall *)(struct IUnknown *, IMFAttributes *))v84->lpVtbl[10].Release)(v84, ppMFAttributes);
        v14 = v54;
        if ( v54 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_175;
          v55 = 150;
          goto LABEL_174;
        }
        v56 = 1;
        if ( v84 )
          ((void (__fastcall *)(struct IUnknown *))v84->lpVtbl->Release)(v84);
        if ( v86 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v86 + 16LL))(v86);
      }
      else
      {
        lpVtbl = a4->lpVtbl;
        v83 = 0;
        cbData[0] = 0;
        v30 = ((__int64 (__fastcall *)(struct IMFAttributes *, UINT32 *))lpVtbl->GetCount)(a4, &v83);
        v14 = v30;
        if ( v30 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_59;
          v31 = 151;
          goto LABEL_84;
        }
        v83 += 2;
        v30 = MFCreateAttributes(&ppMFAttributes, v83);
        v14 = v30;
        if ( v30 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_59;
          v31 = 152;
          goto LABEL_84;
        }
        v30 = ((__int64 (__fastcall *)(struct IMFAttributes *, IMFAttributes *))a4->lpVtbl->CopyAllItems)(
                a4,
                ppMFAttributes);
        v14 = v30;
        if ( v30 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_59;
          v31 = 153;
          goto LABEL_84;
        }
        if ( ((int (__fastcall *)(IMFAttributes *, const IID *, DWORD *))ppMFAttributes->lpVtbl->GetStringLength)(
               ppMFAttributes,
               &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
               cbData) < 0 )
        {
          v30 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, unsigned __int16 *))ppMFAttributes->lpVtbl->SetString)(
                  ppMFAttributes,
                  &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
                  a3);
          v14 = v30;
          if ( v30 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_59;
            v31 = 154;
            goto LABEL_84;
          }
        }
        if ( ((int (__fastcall *)(IMFAttributes *, const IID *, DWORD *))ppMFAttributes->lpVtbl->GetStringLength)(
               ppMFAttributes,
               &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
               cbData) < 0 )
        {
          if ( v13 )
          {
            v30 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, wchar_t *))ppMFAttributes->lpVtbl->SetString)(
                    ppMFAttributes,
                    &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
                    v13);
            v14 = v30;
            if ( v30 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_59;
              v31 = 155;
              goto LABEL_84;
            }
          }
        }
        v56 = 0;
      }
      if ( *((_DWORD *)this + 52) )
      {
        ((void (__fastcall *)(IMFAttributes *, __int64 *))ppMFAttributes->lpVtbl->SetUINT32)(
          ppMFAttributes,
          MF_SENSORDEVICE_SENSOR_ORIENTATION);
        ((void (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
          ppMFAttributes,
          MF_DEVSOURCE_ATTRIBUTE_USE_DSHOWBRIDGE,
          1);
      }
      if ( v56 )
      {
        if ( a4 )
        {
          v58 = a4->lpVtbl;
          v83 = 0;
          cbData[0] = 0;
          if ( ((int (__fastcall *)(struct IMFAttributes *, UINT32 *))v58->GetCount)(a4, &v83) >= 0 )
          {
            for ( j = 0; j < v83; ++j )
            {
              v98 = 0;
              v60 = a4->lpVtbl;
              *(GUID *)Block = GUID_00000000_0000_0000_0000_000000000000;
              GetItemByIndex = v60->GetItemByIndex;
              *(_OWORD *)pvar = 0;
              if ( ((int (__fastcall *)(struct IMFAttributes *, _QWORD, void **, PROPVARIANT *))GetItemByIndex)(
                     a4,
                     j,
                     Block,
                     pvar) >= 0 )
              {
                v62 = ((__int64 (__fastcall *)(IMFAttributes *, void **, PROPVARIANT *))ppMFAttributes->lpVtbl->SetItem)(
                        ppMFAttributes,
                        Block,
                        pvar);
                v63 = v62;
                if ( v62 < 0 && (unsigned __int8)byte_18008D62D >= 0x10u )
                {
                  GuidTrace::GuidTrace((GuidTrace *)v104, (const struct _GUID *)Block);
                  if ( byte_18008D62D )
                  {
                    v64 = v105;
                    if ( !v105 )
                      v64 = FSString::GetString((FSString *)v104);
                    WPP_SF_qDs(
                      *((_QWORD *)WPP_GLOBAL_Control + 27),
                      156,
                      (unsigned int)&WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
                      (_DWORD)this,
                      v63,
                      (__int64)v64);
                  }
                  FSString::~FSString((FSString *)v104);
                }
              }
              PropVariantClear(pvar);
            }
            if ( v13 )
            {
              if ( ((int (__fastcall *)(struct IMFAttributes *, const IID *, DWORD *))a4->lpVtbl->GetItemType)(
                     a4,
                     &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
                     cbData) < 0 )
              {
                v65 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, wchar_t *))ppMFAttributes->lpVtbl->SetString)(
                        ppMFAttributes,
                        &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
                        v13);
                v14 = v65;
                if ( v65 < 0 )
                {
                  if ( !g_wppLevels )
                    goto LABEL_226;
                  v66 = 157;
LABEL_225:
                  WPP_SF_qD(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    v66,
                    &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
                    this,
                    v65);
                  goto LABEL_226;
                }
              }
            }
          }
        }
        else if ( v13 )
        {
          v30 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, wchar_t *))ppMFAttributes->lpVtbl->SetString)(
                  ppMFAttributes,
                  &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
                  v13);
          v14 = v30;
          if ( v30 < 0 )
          {
            if ( !g_wppLevels )
              goto LABEL_59;
            v31 = 158;
            goto LABEL_84;
          }
        }
      }
      v67 = v88;
      if ( v88 )
      {
        v84 = 0;
        LODWORD(Block[0]) = 0;
        *(void **)((char *)Block + 4) = 0;
        v68 = ((__int64 (__fastcall *)(struct IMFMediaSource *, GUID *, struct IUnknown **))v88->lpVtbl->QueryInterface)(
                v88,
                &GUID_00000000_0000_0000_c000_000000000046,
                &v84);
        v14 = v68;
        if ( v68 < 0 )
        {
          if ( !g_wppLevels )
          {
LABEL_236:
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v84);
            goto LABEL_226;
          }
          v69 = 159;
LABEL_235:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v69,
            &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
            this,
            v68);
          goto LABEL_236;
        }
        LODWORD(Block[0]) = 12;
        ROISupportedConfig = GetROISupportedConfig(&v83, v88);
        WORD2(Block[0]) = *(_WORD *)ROISupportedConfig;
        BYTE6(Block[0]) = *(_BYTE *)(ROISupportedConfig + 2);
        LODWORD(Block[1]) = GetPrivacyShutterSupportFlags(v84);
        v68 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, void **, __int64))ppMFAttributes->lpVtbl->SetBlob)(
                ppMFAttributes,
                FSSensorGroupCameraCapabiltiesBlob,
                Block,
                12);
        v14 = v68;
        if ( v68 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_236;
          v69 = 160;
          goto LABEL_235;
        }
        if ( v84 )
          ((void (__fastcall *)(struct IUnknown *))v84->lpVtbl->Release)(v84);
        v67 = v88;
      }
      v14 = SensorDevice::SerializeMediaSource(this, v67, ppMFAttributes, 0, 0, &v89, a5, &v92);
      if ( v14 < 0 )
        goto LABEL_226;
      v71 = v89;
      v72 = (char *)operator new[](v89, (const struct std::nothrow_t *)&std::nothrow);
      v24 = v72;
      if ( !v72 )
      {
        v65 = -2147024882;
        v14 = -2147024882;
        if ( !g_wppLevels )
          goto LABEL_226;
        v66 = 161;
        goto LABEL_225;
      }
      memset_0(v72, 0, v71);
      v82 = (struct IUnknown *)v24;
      v84 = (struct IUnknown *)v24;
      v14 = SensorDevice::SerializeMediaSource(
              this,
              v88,
              ppMFAttributes,
              (unsigned __int8 *)v24,
              v89,
              (int *)&v91,
              a5,
              &v92);
      if ( v14 < 0 )
        goto LABEL_59;
      v73 = -2147024809;
      if ( !pv )
      {
        v74 = v102;
        if ( v102 )
        {
          v75 = 0x7FFFFFFF;
          v76 = v102;
          do
          {
            if ( !*v76 )
              break;
            ++v76;
            --v75;
          }
          while ( v75 );
          v14 = v75 == 0 ? 0x80070057 : 0;
          v102 = (unsigned __int16 *)((0x7FFFFFFF - v75) & -(__int64)(v75 != 0));
          if ( v75 )
          {
            if ( ((0x7FFFFFFF - v75) & (unsigned __int64)-(__int64)(v75 != 0)) >= 0x104 )
              goto LABEL_266;
            v30 = StringCchCopyW((unsigned __int16 *)v24 + 16, 0x104u, v74);
            v14 = v30;
            if ( v30 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_59;
              v31 = 163;
              goto LABEL_84;
            }
            v77 = (unsigned int)v102;
            goto LABEL_265;
          }
        }
        else
        {
          v14 = -2147024809;
        }
        if ( g_wppLevels )
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            162,
            &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
            this,
            v14);
        goto LABEL_59;
      }
      if ( v90 >= 0x104 )
        goto LABEL_266;
      v30 = StringCchCopyW((unsigned __int16 *)v24 + 16, 0x104u, (const unsigned __int16 *)pv);
      v14 = v30;
      if ( v30 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_59;
        v31 = 164;
        goto LABEL_84;
      }
      v77 = v90;
LABEL_265:
      *((_DWORD *)v24 + 7) = v77;
LABEL_266:
      if ( v24 == (char *)-32LL )
      {
        if ( !g_wppLevels )
        {
LABEL_270:
          v14 = v73;
          goto LABEL_281;
        }
        v78 = (unsigned int)((_DWORD)v24 + 129);
      }
      else
      {
        v79 = 0x7FFFFFFF;
        v91 = 32;
        v80 = v24 + 32;
        do
        {
          if ( !*v80 )
            break;
          ++v80;
          --v79;
        }
        while ( v79 );
        v14 = v79 == 0 ? 0x80070057 : 0;
        if ( !v79 )
        {
          v73 = -2147024809;
          if ( !g_wppLevels )
            goto LABEL_226;
          WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), 99, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v14);
LABEL_281:
          if ( g_wppLevels )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              165,
              &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
              this,
              v73);
          goto LABEL_226;
        }
        v73 = GenerateSignatureFromBlob(
                (LPCWSTR)v24 + 16,
                2 * ((0x7FFFFFFF - v79) & ((unsigned __int128)-(__int128)(unsigned __int64)v79 >> 64)) + 2,
                (unsigned __int8 *)v24 + 552,
                0x20u,
                &v91);
        if ( v73 >= 0 || !g_wppLevels )
        {
          v14 = v73;
          if ( v73 >= 0 )
          {
            ComSmartPtr<IMFAttributes>::operator=((_QWORD *)this + 12, &ppMFAttributes);
            wistd::unique_ptr<unsigned char [0],wistd::default_delete<unsigned char [0]>>::swap((char *)this + 80, &v84);
            v12 = v84;
            *((_DWORD *)this + 22) = v89;
            if ( v103 )
              *v103 = v92;
            goto LABEL_60;
          }
          goto LABEL_281;
        }
        v78 = 100;
      }
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v78, &WPP_cc6378c746ea368f019c0ec88e4d78a0_Traceguids, 0, v73);
      goto LABEL_270;
    }
    memset_0(sz, 0, 0x208u);
    if ( !a3 )
    {
      v14 = -2147024809;
      if ( g_wppLevels )
      {
        v16 = 133;
        goto LABEL_17;
      }
      goto LABEL_226;
    }
    v17 = ((__int64 (__fastcall *)(struct IUnknown *, GUID *, struct IMFMediaSource **))a2->lpVtbl->QueryInterface)(
            a2,
            &GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66,
            &v88);
    v14 = v17;
    if ( v17 < 0 )
    {
      if ( g_wppLevels )
      {
        v18 = 134;
        goto LABEL_22;
      }
      goto LABEL_226;
    }
    if ( v6 )
    {
      v36 = a4->lpVtbl;
      v24 = 0;
      v83 = 0;
      if ( ((int (__fastcall *)(struct IMFAttributes *, const IID *, UINT32 *))v36->GetStringLength)(
             a4,
             &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
             &v83) >= 0 )
      {
        unique = (void **)wil::make_unique_nothrow<unsigned short [0]>(Block, ++v83);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
          (void **)cbData,
          unique);
        v49 = Block[0];
        Block[0] = 0;
        if ( v49 )
          operator delete(v49);
        v13 = *(wchar_t **)cbData;
        if ( !*(_QWORD *)cbData )
        {
          v30 = -2147024882;
          v14 = -2147024882;
          if ( g_wppLevels )
          {
            v31 = 140;
            goto LABEL_84;
          }
LABEL_226:
          v12 = v82;
          goto LABEL_60;
        }
        v30 = ((__int64 (__fastcall *)(struct IMFAttributes *, const IID *, _QWORD, _QWORD, UINT32 *))a4->lpVtbl->GetString)(
                a4,
                &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
                *(_QWORD *)cbData,
                v83,
                &v83);
        v14 = v30;
        if ( v30 < 0 )
        {
          if ( g_wppLevels )
          {
            v31 = 141;
            goto LABEL_84;
          }
          goto LABEL_226;
        }
      }
      else
      {
        v84 = 0;
        v86 = 0;
        v37 = ((__int64 (__fastcall *)(struct IMFMediaSource *, GUID *, struct IUnknown **))v88->lpVtbl->QueryInterface)(
                v88,
                &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8,
                &v84);
        v14 = v37;
        if ( v37 < 0 )
        {
          if ( !g_wppLevels )
          {
LABEL_107:
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v86);
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v84);
            goto LABEL_18;
          }
          v38 = 135;
LABEL_106:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v38,
            &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
            this,
            v37);
          goto LABEL_107;
        }
        v37 = ((__int64 (__fastcall *)(struct IUnknown *, __int64 *))v84->lpVtbl[4].AddRef)(v84, &v86);
        v14 = v37;
        if ( v37 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_107;
          v38 = 136;
          goto LABEL_106;
        }
        v37 = (*(__int64 (__fastcall **)(__int64, const IID *, UINT32 *))(*(_QWORD *)v86 + 88LL))(
                v86,
                &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
                &v83);
        v14 = v37;
        if ( v37 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_107;
          v38 = 137;
          goto LABEL_106;
        }
        v39 = (void **)wil::make_unique_nothrow<unsigned short [0]>(Block, ++v83);
        wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)cbData, v39);
        v40 = Block[0];
        Block[0] = 0;
        if ( v40 )
          operator delete(v40);
        v13 = *(wchar_t **)cbData;
        if ( !*(_QWORD *)cbData )
        {
          v41 = -2147024882;
          v14 = -2147024882;
          if ( !g_wppLevels )
          {
LABEL_120:
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v86);
            v43 = (__int64 *)&v84;
LABEL_121:
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(v43);
            goto LABEL_59;
          }
          v42 = 138;
LABEL_119:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v42,
            &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
            this,
            v41);
          goto LABEL_120;
        }
        v41 = (*(__int64 (__fastcall **)(__int64, const IID *, _QWORD, _QWORD, UINT32 *))(*(_QWORD *)v86 + 96LL))(
                v86,
                &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
                *(_QWORD *)cbData,
                v83,
                &v83);
        v14 = v41;
        if ( v41 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_120;
          v42 = 139;
          goto LABEL_119;
        }
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v86);
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v84);
      }
    }
    else
    {
      DeviceInterfacePropertySz = GetDeviceInterfacePropertySz(a3);
      v24 = 0;
      v14 = DeviceInterfacePropertySz;
      if ( DeviceInterfacePropertySz < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_58;
        v27 = 142;
        goto LABEL_57;
      }
      v13 = *(wchar_t **)cbData;
      if ( !*(_QWORD *)cbData )
      {
        GetDevicePropertySz(a3);
        v13 = 0;
      }
      v50 = GetSensorGroupPropertyName(0xAu);
      if ( (int)FSGetDeviceInterfaceRegistryEntry2(a3, v50, (unsigned __int8 *)sz, 0x208u, cbData, lpcbData) >= 0 )
      {
        v30 = IIDFromString(sz, (LPIID)((char *)this + 136));
        v14 = v30;
        if ( v30 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_59;
          v31 = 143;
          goto LABEL_84;
        }
      }
    }
    if ( (unsigned __int8)byte_18008D62D >= 0x10u )
    {
      GuidTrace::GuidTrace((GuidTrace *)pvar, (const struct _GUID *)((char *)this + 136));
      if ( (unsigned __int8)byte_18008D62D >= 8u )
      {
        v44 = (const char *)v99;
        v45 = L"NoFriendlyName";
        if ( v13 )
          v45 = v13;
        if ( !v99 )
          v44 = FSString::GetString((FSString *)pvar);
        WPP_SF_qdsSS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          *((_DWORD *)this + 52),
          (__int64)v44,
          (__int64)v45,
          (__int64)a3);
      }
      FSString::~FSString((FSString *)pvar);
    }
    goto LABEL_134;
  }
  v14 = -1072871856;
  if ( !g_wppLevels )
    goto LABEL_63;
  v15 = 119;
LABEL_7:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v15, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v14);
LABEL_60:
  if ( hKey )
    RegCloseKey(hKey);
  v8 = v95;
LABEL_63:
  if ( v8 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
  if ( v13 )
    operator delete(v13);
  if ( ppMFAttributes )
    ((void (__fastcall *)(IMFAttributes *))ppMFAttributes->lpVtbl->Release)(ppMFAttributes);
  if ( pv )
    CoTaskMemFree(pv);
  if ( v88 )
    ((void (__fastcall *)(struct IMFMediaSource *))v88->lpVtbl->Release)(v88);
  if ( v96 )
    (*(void (__fastcall **)(__int64 *))(*v96 + 16))(v96);
  if ( v12 )
    operator delete(v12);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x18001ce24  push    rbp
0x18001ce26  push    rbx
0x18001ce27  push    rsi
0x18001ce28  push    rdi
0x18001ce29  push    r12
0x18001ce2b  push    r13
0x18001ce2d  push    r14
0x18001ce2f  push    r15
0x18001ce31  lea     rbp, [rsp-248h]
0x18001ce39  sub     rsp, 348h
0x18001ce40  mov     rax, cs:__security_cookie
0x18001ce47  xor     rax, rsp
0x18001ce4a  mov     [rbp+280h+var_50], rax
0x18001ce51  mov     rax, [rbp+280h+arg_28]
0x18001ce58  xor     r15d, r15d
0x18001ce5b  mov     [rbp+280h+var_2B0], r8
0x18001ce5f  mov     rdi, rcx
0x18001ce62  mov     [rbp+280h+var_2A8], rax
0x18001ce66  mov     ecx, r15d
0x18001ce69  mov     [rbp+280h+var_2E8], rcx
0x18001ce6d  mov     r14, r9
0x18001ce70  mov     [rsp+380h+var_340], r15
0x18001ce75  mov     r13, r8
0x18001ce78  mov     [rsp+380h+var_308], r15d
0x18001ce7d  mov     rbx, rdx
0x18001ce80  mov     [rbp+280h+var_300], r15d
0x18001ce84  mov     esi, r15d
0x18001ce87  mov     [rbp+280h+var_2E0], r15
0x18001ce8b  mov     r12d, r15d
0x18001ce8e  mov     [rsp+380h+var_310], r15
0x18001ce93  mov     [rbp+280h+pv], r15
0x18001ce97  mov     [rsp+380h+var_304], r15d
0x18001ce9c  mov     [rbp+280h+var_2FC], r15d
0x18001cea0  mov     [rsp+380h+ppMFAttributes], r15
0x18001cea5  mov     qword ptr [rsp+380h+cbData], r15
0x18001ceaa  mov     dword ptr [rbp+280h+Data], r15d
0x18001ceae  mov     [rbp+280h+hKey], r15
0x18001ceb2  mov     [rbp+280h+Type], r15d
0x18001ceb6  test    rdx, rdx
0x18001ceb9  jnz     short loc_18001CEF9
0x18001cebb  mov     r14d, 80070057h
0x18001cec1  mov     ebx, r14d
0x18001cec4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001cecb  jb      loc_18001D2CF
0x18001ced1  lea     edx, [r15+76h]
0x18001ced5  mov     [rsp+380h+ulFlags], r14d
0x18001ceda  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cee1  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x18001cee8  mov     r9, rdi
0x18001ceeb  mov     rcx, [rcx+10h]
0x18001ceef  call    WPP_SF_qD
0x18001cef4  jmp     loc_18001D2BC
0x18001cef9  cmp     [rdi+50h], r15
0x18001cefd  jz      short loc_18001CF1C
0x18001ceff  mov     ebx, 0C00D4650h
0x18001cf04  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001cf0b  jb      loc_18001D2CF
0x18001cf11  mov     edx, 77h ; 'w'
0x18001cf16  mov     [rsp+380h+ulFlags], ebx
0x18001cf1a  jmp     short loc_18001CEDA
0x18001cf1c  cmp     [rdi+0A8h], r15
0x18001cf23  jnz     short loc_18001CF3E
0x18001cf25  mov     ebx, 0C00D36DEh
0x18001cf2a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001cf31  jb      loc_18001D2CF
0x18001cf37  mov     edx, 78h ; 'x'
0x18001cf3c  jmp     short loc_18001CF16
0x18001cf3e  test    r14, r14
0x18001cf41  jz      short loc_18001CF78
0x18001cf43  xor     r8d, r8d
0x18001cf46  lea     rdx, MF_FSM_CLIENT_ACTIVATED_MEDIASOURCE
0x18001cf4d  mov     rcx, r14
0x18001cf50  call    MFGetAttributeUINT32
0x18001cf55  test    eax, eax
0x18001cf57  lea     rdx, MF_FSM_BLOCK_FACEAUTH_CONTROL
0x18001cf5e  mov     rcx, r14
0x18001cf61  setnz   r15b
0x18001cf65  xor     r8d, r8d
0x18001cf68  call    MFGetAttributeUINT32
0x18001cf6d  test    eax, eax
0x18001cf6f  setnz   al
0x18001cf72  mov     [rdi+0E0h], al
0x18001cf78  mov     rax, [rbx]
0x18001cf7b  lea     r8, [rbp+280h+var_2E8]
0x18001cf7f  lea     rdx, _GUID_5bc8a76b_869a_46a3_9b03_fa218a66aebe
0x18001cf86  mov     rcx, rbx
0x18001cf89  mov     rax, [rax]
0x18001cf8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cf91  lea     rsi, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x18001cf98  test    eax, eax
0x18001cf9a  js      loc_18001D19C
0x18001cfa0  xor     r15d, r15d
0x18001cfa3  mov     [rsp+380h+var_338], r15d
0x18001cfa8  test    r14, r14
0x18001cfab  jnz     short loc_18001CFE6
0x18001cfad  mov     r14d, 80070057h
0x18001cfb3  mov     ebx, r14d
0x18001cfb6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001cfbd  jb      short loc_18001CFDE
0x18001cfbf  lea     edx, [r15+79h]
0x18001cfc3  mov     [rsp+380h+ulFlags], r14d
0x18001cfc8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfcf  mov     r9, rdi
0x18001cfd2  mov     r8, rsi
0x18001cfd5  mov     rcx, [rcx+10h]
0x18001cfd9  call    WPP_SF_qD
0x18001cfde  mov     rsi, r12
0x18001cfe1  jmp     loc_18001D2BC
0x18001cfe6  mov     rax, [r14]
0x18001cfe9  lea     r15, [rdi+88h]
0x18001cff0  mov     r8, r15
0x18001cff3  lea     rdx, MF_SENSORTRANSFORM_FACTORYCLSID
0x18001cffa  mov     rcx, r14
0x18001cffd  mov     rax, [rax+50h]
0x18001d001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d006  mov     ebx, eax
0x18001d008  test    eax, eax
0x18001d00a  jns     short loc_18001D020
0x18001d00c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d013  jb      short loc_18001CFDE
0x18001d015  mov     edx, 7Ah ; 'z'
0x18001d01a  mov     [rsp+380h+ulFlags], eax
0x18001d01e  jmp     short loc_18001CFC8
0x18001d020  mov     rcx, [rbp+280h+var_2E8]
0x18001d024  lea     rdx, [rsp+380h+var_338]
0x18001d029  mov     rax, [rcx]
0x18001d02c  mov     rax, [rax+18h]
0x18001d030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d035  mov     ebx, eax
0x18001d037  test    eax, eax
0x18001d039  jns     short loc_18001D04B
0x18001d03b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d042  jb      short loc_18001CFDE
0x18001d044  mov     edx, 7Bh ; '{'
0x18001d049  jmp     short loc_18001D01A
0x18001d04b  cmp     cs:byte_18008D62D, 10h
0x18001d052  jb      short loc_18001D0B1
0x18001d054  mov     rdx, r15; struct _GUID *
0x18001d057  lea     rcx, [rbp+280h+pvar]; this
0x18001d05b  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18001d060  cmp     cs:byte_18008D62D, 8
0x18001d067  jb      short loc_18001D0A8
0x18001d069  mov     rax, [rbp+280h+var_2C0]
0x18001d06d  mov     r8d, [rsp+380h+var_338]
0x18001d072  test    rax, rax
0x18001d075  jnz     short loc_18001D080
0x18001d077  lea     rcx, [rbp+280h+pvar]; this
0x18001d07b  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18001d080  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d087  mov     edx, 7Ch ; '|'
0x18001d08c  mov     dword ptr [rsp+380h+lpcbData], r8d
0x18001d091  mov     r9, rdi
0x18001d094  mov     r8, rsi
0x18001d097  mov     qword ptr [rsp+380h+ulFlags], rax
0x18001d09c  mov     rcx, [rcx+0D8h]
0x18001d0a3  call    WPP_SF_qsD
0x18001d0a8  lea     rcx, [rbp+280h+pvar]; this
0x18001d0ac  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18001d0b1  xor     r15d, r15d
0x18001d0b4  cmp     r15d, [rsp+380h+var_338]
0x18001d0b9  jnb     loc_18001D484
0x18001d0bf  mov     rcx, [rbp+280h+var_2E8]
0x18001d0c3  lea     r8, [rsp+380h+var_320]
0x18001d0c8  mov     [rsp+380h+var_320], r12
0x18001d0cd  mov     edx, r15d
0x18001d0d0  mov     [rsp+380h+var_330], r12
0x18001d0d5  mov     rax, [rcx]
0x18001d0d8  mov     rax, [rax+20h]
0x18001d0dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d0e1  mov     ebx, eax
0x18001d0e3  test    eax, eax
0x18001d0e5  js      short loc_18001D15B
0x18001d0e7  mov     rcx, [rsp+380h+var_320]
0x18001d0ec  lea     r8, [rsp+380h+var_330]
0x18001d0f1  lea     rdx, _GUID_30acfa70_af94_4ad4_be36_14e23900c104
0x18001d0f8  mov     rax, [rcx]
0x18001d0fb  mov     rax, [rax]
0x18001d0fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d103  mov     ebx, eax
0x18001d105  test    eax, eax
0x18001d107  js      short loc_18001D14B
0x18001d109  mov     rdx, [rsp+380h+var_330]
0x18001d10e  lea     rcx, [rdi+70h]
0x18001d112  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x18001d117  test    eax, eax
0x18001d119  jz      short loc_18001D134
0x18001d11b  lea     rcx, [rsp+380h+var_330]
0x18001d120  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18001d125  lea     rcx, [rsp+380h+var_320]
0x18001d12a  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18001d12f  inc     r15d
0x18001d132  jmp     short loc_18001D0B4
0x18001d134  mov     eax, 8007000Eh
0x18001d139  mov     ebx, eax
0x18001d13b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d142  jb      short loc_18001D183
0x18001d144  mov     edx, 7Fh
0x18001d149  jmp     short loc_18001D169
0x18001d14b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d152  jb      short loc_18001D183
0x18001d154  mov     edx, 7Eh ; '~'
0x18001d159  jmp     short loc_18001D169
0x18001d15b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d162  jb      short loc_18001D183
0x18001d164  mov     edx, 7Dh ; '}'
0x18001d169  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d170  mov     r9, rdi
0x18001d173  mov     r8, rsi
0x18001d176  mov     [rsp+380h+ulFlags], eax
0x18001d17a  mov     rcx, [rcx+10h]
0x18001d17e  call    WPP_SF_qD
0x18001d183  lea     rcx, [rsp+380h+var_330]
0x18001d188  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18001d18d  lea     rcx, [rsp+380h+var_320]
0x18001d192  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18001d197  jmp     loc_18001CFDE
0x18001d19c  test    r15b, r15b
0x18001d19f  jnz     loc_18001D496
0x18001d1a5  mov     rax, [rbx]
0x18001d1a8  lea     r8, [rbp+280h+var_2E0]
0x18001d1ac  lea     rdx, _GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67
0x18001d1b3  mov     rcx, rbx
0x18001d1b6  mov     rax, [rax]
0x18001d1b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d1be  test    eax, eax
0x18001d1c0  js      loc_18001D496
0x18001d1c6  xor     edx, edx; Val
0x18001d1c8  lea     rcx, [rbp+280h+sz]; void *
0x18001d1cc  mov     r8d, 208h; Size
0x18001d1d2  call    memset_0
0x18001d1d7  mov     rcx, [rbp+280h+var_2E0]
0x18001d1db  lea     rdx, [rbp+280h+pv]
0x18001d1df  xor     r15d, r15d
0x18001d1e2  lea     r9, [rsp+380h+var_304]
0x18001d1e7  lea     r8, [rbp+280h+Block+8]
0x18001d1eb  mov     rax, [rcx]
0x18001d1ee  mov     [rbp+280h+Block], rdx
0x18001d1f2  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x18001d1f9  mov     [rbp+280h+Block+8], r15
0x18001d1fd  mov     [rbp+280h+var_270], 1
0x18001d201  mov     rax, [rax+68h]
0x18001d205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d20a  lea     rcx, [rbp+280h+Block]
0x18001d20e  mov     ebx, eax
0x18001d210  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(void)
0x18001d215  mov     eax, ebx
0x18001d217  shr     eax, 1Fh
0x18001d21a  test    al, al
0x18001d21c  jz      short loc_18001D239
0x18001d21e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d225  jb      loc_18001CFDE
0x18001d22b  mov     edx, 80h
0x18001d230  mov     [rsp+380h+ulFlags], ebx
0x18001d234  jmp     loc_18001CFC8
0x18001d239  mov     rcx, [rbp+280h+var_2E0]
0x18001d23d  lea     r8, [rsp+380h+var_310]
0x18001d242  lea     rdx, _GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66
0x18001d249  mov     rax, [rcx]
0x18001d24c  mov     rax, [rax+108h]
0x18001d253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d258  mov     ebx, eax
0x18001d25a  test    eax, eax
0x18001d25c  jns     short loc_18001D275
0x18001d25e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d265  jb      loc_18001CFDE
0x18001d26b  mov     edx, 81h
0x18001d270  jmp     loc_18001D01A
0x18001d275  lea     r8, [rsp+380h+cbData]
0x18001d27a  mov     rcx, r13; pszDeviceInterface
0x18001d27d  call    ?GetDeviceInterfacePropertySz@@YAJPEBGPEBU_DEVPROPKEY@@AEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@@Z; GetDeviceInterfacePropertySz(ushort const *,_DEVPROPKEY const *,wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>> &)
0x18001d282  mov     ebx, eax
0x18001d284  test    eax, eax
0x18001d286  jns     loc_18001D36F
0x18001d28c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001d293  jb      short loc_18001D2B4
0x18001d295  mov     edx, 82h
0x18001d29a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d2a1  mov     r9, rdi
0x18001d2a4  mov     r8, rsi
0x18001d2a7  mov     [rsp+380h+ulFlags], eax
0x18001d2ab  mov     rcx, [rcx+10h]
0x18001d2af  call    WPP_SF_qD
0x18001d2b4  mov     r12, qword ptr [rsp+380h+cbData]
0x18001d2b9  mov     rsi, r15
0x18001d2bc  mov     rcx, [rbp+280h+hKey]; hKey
0x18001d2c0  test    rcx, rcx
0x18001d2c3  jz      short loc_18001D2CB
0x18001d2c5  call    cs:__imp_RegCloseKey
0x18001d2cb  mov     rcx, [rbp+280h+var_2E8]
0x18001d2cf  test    rcx, rcx
0x18001d2d2  jz      short loc_18001D2E0
0x18001d2d4  mov     rax, [rcx]
0x18001d2d7  mov     rax, [rax+10h]
0x18001d2db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d2e0  test    r12, r12
0x18001d2e3  jz      short loc_18001D2ED
0x18001d2e5  mov     rcx, r12; Block
0x18001d2e8  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001d2ed  mov     rcx, [rsp+380h+ppMFAttributes]
0x18001d2f2  test    rcx, rcx
  ... truncated ...
```
