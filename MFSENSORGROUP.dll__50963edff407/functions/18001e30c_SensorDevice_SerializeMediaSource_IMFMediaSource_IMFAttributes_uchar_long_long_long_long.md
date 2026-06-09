# SensorDevice::SerializeMediaSource(IMFMediaSource *,IMFAttributes *,uchar *,long,long *,long,long *)

- ea: `0x18001e30c`
- end: `0x18001ee84`
- name: `?SerializeMediaSource@SensorDevice@@IEAAJPEAUIMFMediaSource@@PEAUIMFAttributes@@PEAEJPEAJJ3@Z`
- size: `2936`
- prototype: `__int64 __usercall@<rax>(SensorDevice *__hidden this@<rcx>, struct IMFMediaSource *@<rdx>, IMFAttributes *pAttributes@<r8>, unsigned __int8 *@<r9>, int, int *, int, int *)`
- caller_count: `1`
- callee_count: `23`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001ce24`

## callees

- `0x180005fa0`
- `0x180008f9c`
- `0x18000d1f0`
- `0x18000f518`
- `0x180015e80`
- `0x180019a4c`
- `0x18001b3d8`
- `0x18001e30c`
- `0x180022fa0`
- `0x180028d34`
- `0x18002dcf4`
- `0x180031d34`
- `0x1800338b0`
- `0x180036258`
- `0x180039900`
- `0x18003a648`
- `0x18003f100`
- `0x180044f30`
- `0x180045900`
- `0x18004abb8`
- `0x180076274`
- `0x180076280`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eaf4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eae1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eaf4`
- `MFPlat!MFGetAttributesAsBlob` at `0x18001e477`
- `MFPlat!MFGetAttributesAsBlob` at `0x18001e477`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18001e434`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x18001e434`

## pseudocode

```c
__int64 __fastcall SensorDevice::SerializeMediaSource(
        SensorDevice *this,
        struct IMFMediaSource *a2,
        IMFAttributes *pAttributes,
        unsigned __int8 *a4,
        int a5,
        int *a6,
        int a7,
        int *a8)
{
  HRESULT v12; // eax
  int v13; // ebx
  __int64 v14; // rdx
  int v15; // r15d
  UINT32 v16; // ecx
  unsigned int v17; // r15d
  unsigned int v18; // r13d
  __int64 i; // rdi
  __int64 v20; // r9
  unsigned __int64 v21; // rdi
  bool v22; // di
  unsigned int j; // edi
  __int64 v24; // rcx
  int v25; // eax
  __int64 v26; // rdx
  unsigned int v27; // r13d
  __int64 k; // r15
  unsigned int v29; // eax
  struct IMFMediaSourceVtbl *lpVtbl; // rax
  HRESULT (__stdcall *QueryInterface)(IMFMediaSource *, const IID *const, void **); // rax
  unsigned __int64 v32; // rdi
  int (__fastcall *v33)(unsigned __int64, __int64 **); // rbx
  __int64 v34; // rax
  char v35; // bl
  __int64 v36; // rcx
  __int64 v37; // rax
  char v38; // bl
  __int64 v39; // rcx
  void *v40; // rcx
  int v41; // edx
  int v42; // r8d
  unsigned int m; // edi
  __int64 v44; // rcx
  __int64 v45; // rax
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rcx
  int v49; // r13d
  int v50; // eax
  unsigned __int8 *v51; // r9
  int *v52; // r13
  int *v53; // rax
  int v54; // ecx
  int v56[2]; // [rsp+20h] [rbp-E0h]
  int *v57; // [rsp+28h] [rbp-D8h]
  __int64 v58; // [rsp+30h] [rbp-D0h]
  __int64 v59; // [rsp+70h] [rbp-90h] BYREF
  unsigned int Size; // [rsp+78h] [rbp-88h] BYREF
  int Size_4; // [rsp+7Ch] [rbp-84h]
  unsigned int v62; // [rsp+80h] [rbp-80h]
  UINT32 pcbBufSize; // [rsp+84h] [rbp-7Ch] BYREF
  int v64; // [rsp+88h] [rbp-78h] BYREF
  void *pv; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int64 v66; // [rsp+98h] [rbp-68h] BYREF
  __int64 *v67; // [rsp+A0h] [rbp-60h] BYREF
  void *v68; // [rsp+A8h] [rbp-58h] BYREF
  void *Src; // [rsp+B0h] [rbp-50h] BYREF
  int *v70; // [rsp+B8h] [rbp-48h]
  int *v71; // [rsp+C0h] [rbp-40h]
  __int128 Buf1; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v73; // [rsp+D8h] [rbp-28h]
  unsigned __int16 v74[264]; // [rsp+E0h] [rbp-20h] BYREF

  v71 = a6;
  v70 = a8;
  v64 = 0;
  pcbBufSize = 0;
  if ( !a6 )
  {
    v12 = -2147467261;
    v13 = -2147467261;
    if ( !g_wppLevels )
      goto LABEL_145;
    v14 = 184;
    goto LABEL_4;
  }
  if ( !a8 )
  {
    v12 = -2147467261;
    v13 = -2147467261;
    if ( g_wppLevels )
    {
      v14 = 185;
LABEL_4:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids, this, v12);
      goto LABEL_145;
    }
    goto LABEL_145;
  }
  *a6 = 0;
  *a8 = 0;
  if ( a4 )
  {
    v15 = a5;
    if ( (unsigned __int8)byte_18008D62D >= 8u )
      WPP_SF_qqqqdd(*((_QWORD *)WPP_GLOBAL_Control + 27), a2, pAttributes, this, a2, pAttributes, a4, a5, a7);
  }
  else
  {
    v15 = a5;
  }
  Size_4 = 584;
  if ( pAttributes )
  {
    v12 = MFGetAttributesAsBlobSize(pAttributes, &pcbBufSize);
    v13 = v12;
    if ( v12 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 187;
        goto LABEL_4;
      }
LABEL_145:
      if ( byte_18008D62D )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          208,
          &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
          this,
          v13);
      return (unsigned int)v13;
    }
    if ( a4 )
    {
      v16 = pcbBufSize;
      if ( v15 - 584 < (int)pcbBufSize )
      {
LABEL_22:
        Size_4 = v16 + 584;
        goto LABEL_23;
      }
      v12 = MFGetAttributesAsBlob(pAttributes, a4 + 584, pcbBufSize);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( g_wppLevels )
        {
          v14 = 188;
          goto LABEL_4;
        }
        goto LABEL_145;
      }
    }
    v16 = pcbBufSize;
    goto LABEL_22;
  }
LABEL_23:
  v17 = *((_DWORD *)this + 30);
  v62 = v17;
  if ( !*((_BYTE *)this + 200) )
  {
    v18 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 24LL))(*((_QWORD *)this + 21));
    if ( !*((_BYTE *)this + 224) )
    {
      for ( i = 0; (unsigned int)i < v17 && a2; i = (unsigned int)(i + 1) )
      {
        v13 = SensorDevice::SetFaceAuthDDICapabilityOnStream(
                this,
                a2,
                *(struct IMFAttributes **)(*((_QWORD *)this + 14) + 8 * i),
                i);
        if ( v13 < 0 )
          goto LABEL_145;
        if ( !*((_BYTE *)this + 225) )
        {
          v13 = SensorDevice::SetSecureModeDDICapabilityOnStream(
                  this,
                  a2,
                  *(struct IMFAttributes **)(*((_QWORD *)this + 14) + 8 * i),
                  i);
          if ( v13 < 0 )
            goto LABEL_145;
        }
        v17 = v62;
      }
    }
    if ( *((_QWORD *)this + 27) )
    {
      memset_0(v74, 0, 0x208u);
      v20 = *((unsigned int *)this + 45);
      v58 = *((_QWORD *)this + 24);
      LODWORD(v57) = *((_DWORD *)this + 44);
      *(_QWORD *)v56 = *((_QWORD *)this + 23);
      v66 = 0;
      pv = 0;
      v12 = StringCchPrintfW(
              v74,
              0x104u,
              L"face_auth_streamid=%d,face_auth_caps=0x%llX,secure_mode_streamid=%d,secure_mode_caps=0x%llX",
              v20,
              *(_QWORD *)v56,
              v57,
              v58);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( g_wppLevels )
        {
          v14 = 189;
          goto LABEL_4;
        }
        goto LABEL_145;
      }
      v12 = StringCchLengthW(v74, 0x104u, &v66);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( g_wppLevels )
        {
          v14 = 190;
          goto LABEL_4;
        }
        goto LABEL_145;
      }
      v21 = v66 + 1;
      v12 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, void **, _QWORD))(**((_QWORD **)this + 27) + 192LL))(
              *((_QWORD *)this + 27),
              16,
              (unsigned int)(2 * (v66 + 1)),
              &pv,
              0);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( g_wppLevels )
        {
          v14 = 191;
          goto LABEL_4;
        }
        goto LABEL_145;
      }
      v12 = StringCchCopyW((unsigned __int16 *)pv, v21, v74);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( g_wppLevels )
        {
          v14 = 192;
          goto LABEL_4;
        }
        goto LABEL_145;
      }
    }
    v22 = 0;
    if ( *((_DWORD *)this + 45) != -1 && v18 )
    {
      for ( j = 0; j < v18; ++j )
      {
        v24 = *((_QWORD *)this + 21);
        v59 = 0;
        v73 = 0;
        Buf1 = 0;
        v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v24 + 32LL))(v24, j, &v59);
        v13 = v25;
        if ( v25 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_62;
          v26 = 193;
LABEL_61:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v26,
            &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
            this,
            v25);
          goto LABEL_62;
        }
        v25 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v59 + 24LL))(v59, &Buf1);
        v13 = v25;
        if ( v25 < 0 )
        {
          if ( g_wppLevels )
          {
            v26 = 194;
            goto LABEL_61;
          }
LABEL_62:
          wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v59);
          goto LABEL_145;
        }
        if ( !memcmp_0(&Buf1, &GUID_81361b22_700b_4546_a2d4_c52e907bfc27, 0x10u) )
        {
          wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v59);
          *((_DWORD *)this + 51) = -1;
          v22 = 1;
          goto LABEL_54;
        }
        wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v59);
      }
      v22 = *((_DWORD *)this + 51) != -1;
      if ( *((_DWORD *)this + 51) == -1 )
      {
        v59 = 0;
        v25 = MFCreateSensorProfile(&GUID_81361b22_700b_4546_a2d4_c52e907bfc27, 0, 0, &v59);
        v13 = v25;
        if ( v25 >= 0 )
        {
          v27 = v62;
          for ( k = 0; (unsigned int)k < v27; k = (unsigned int)(k + 1) )
          {
            v29 = MFGetAttributeUINT32(
                    *(_QWORD *)(*((_QWORD *)this + 14) + 8 * k),
                    &MF_DEVICESTREAM_STREAM_ID,
                    0xFFFFFFFFLL);
            if ( v29 == *((_DWORD *)this + 45) )
            {
              v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v59 + 32LL))(
                      v59,
                      v29,
                      L"(*)");
              v13 = v25;
              if ( v25 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_62;
                v26 = 196;
                goto LABEL_61;
              }
            }
            else
            {
              v25 = (*(__int64 (__fastcall **)(__int64, _QWORD, const unsigned __int16 *))(*(_QWORD *)v59 + 32LL))(
                      v59,
                      v29,
                      L"(!)");
              v13 = v25;
              if ( v25 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_62;
                v26 = 197;
                goto LABEL_61;
              }
            }
          }
          v25 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**((_QWORD **)this + 21) + 40LL))(
                  *((_QWORD *)this + 21),
                  v59);
          v13 = v25;
          if ( v25 >= 0 )
          {
            wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(&v59);
            v17 = v62;
            goto LABEL_54;
          }
          if ( !g_wppLevels )
            goto LABEL_62;
          v26 = 198;
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_62;
          v26 = 195;
        }
        goto LABEL_61;
      }
    }
LABEL_54:
    v12 = SensorDevice::SynthesizeCPV2FaceAuthProfile(this);
    v13 = v12;
    if ( v12 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 199;
        goto LABEL_4;
      }
      goto LABEL_145;
    }
    *((_BYTE *)this + 200) = 1;
    *((_BYTE *)this + 201) = v22;
  }
  if ( a2 && *((_QWORD *)this + 27) )
  {
    lpVtbl = a2->lpVtbl;
    v67 = 0;
    Src = 0;
    Size = 0;
    QueryInterface = lpVtbl->QueryInterface;
    pv = 0;
    LODWORD(v59) = 0;
    v66 = 0;
    if ( ((int (__fastcall *)(struct IMFMediaSource *, GUID *, unsigned __int64 *))QueryInterface)(
           a2,
           &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8,
           &v66) >= 0 )
    {
      v32 = v66;
      v33 = *(int (__fastcall **)(unsigned __int64, __int64 **))(*(_QWORD *)v66 + 104LL);
      wil::com_ptr_t<IMFAttributes,wil::err_returncode_policy>::reset(&v67);
      if ( v33(v32, &v67) >= 0 )
      {
        v34 = *v67;
        *(_QWORD *)&Buf1 = &Src;
        *((_QWORD *)&Buf1 + 1) = 0;
        LOBYTE(v73) = 1;
        if ( (*(int (__fastcall **)(__int64 *, __int64 *, char *, unsigned int *))(v34 + 128))(
               v67,
               MF_DEVICESOURCE_DMFT_FIXED_FILEDINFO,
               (char *)&Buf1 + 8,
               &Size) < 0
          || (v35 = 1, !Size) )
        {
          v35 = 0;
        }
        wil::details::out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned char [0],wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>((__int64)&Buf1);
        if ( v35 )
        {
          v36 = *((_QWORD *)this + 27);
          v68 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, void **, _QWORD))(*(_QWORD *)v36 + 192LL))(
                 v36,
                 24,
                 Size,
                 &v68,
                 0) < 0 )
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 27) + 192LL))(
              *((_QWORD *)this + 27),
              24,
              0,
              0,
              0);
          else
            memcpy_0(v68, Src, Size);
        }
        v37 = *v67;
        *(_QWORD *)&Buf1 = &pv;
        *((_QWORD *)&Buf1 + 1) = 0;
        LOBYTE(v73) = 1;
        if ( (*(int (__fastcall **)(__int64 *, __int64 *, char *, __int64 *))(v37 + 104))(
               v67,
               MF_DEVICESOURCE_DMFT_FIXED_FILEDINFO_STRING,
               (char *)&Buf1 + 8,
               &v59) < 0
          || (v38 = 1, !(_DWORD)v59) )
        {
          v38 = 0;
        }
        wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>((__int64)&Buf1);
        if ( v38 )
        {
          v39 = *((_QWORD *)this + 27);
          v68 = 0;
          if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, void **, _QWORD))(*(_QWORD *)v39 + 192LL))(
                 v39,
                 25,
                 (unsigned int)(2 * v59 + 2),
                 &v68,
                 0) < 0 )
            (*(void (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 27) + 192LL))(
              *((_QWORD *)this + 27),
              25,
              0,
              0,
              0);
          else
            memcpy_0(v68, pv, 2LL * (unsigned int)v59);
        }
      }
    }
    if ( pv )
      CoTaskMemFree(pv);
    v40 = Src;
    Src = 0;
    if ( v40 )
      CoTaskMemFree(v40);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v67);
    wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>((__int64 *)&v66);
  }
  v12 = SensorDevice::SetShareStream(this);
  v13 = v12;
  if ( v12 < 0 )
  {
    if ( g_wppLevels )
    {
      v14 = 200;
      goto LABEL_4;
    }
    goto LABEL_145;
  }
  for ( m = 0; m < v17; ++m )
  {
    v44 = *((_QWORD *)this + 14);
    Size = 0;
    if ( (unsigned int)MFGetAttributeUINT32(
                         *(_QWORD *)(v44 + 8LL * m),
                         MF_DEVICESTREAM_SENSORSTREAM_FSSTREAM_ID,
                         0xFFFFFFFFLL) == -1 )
    {
      v45 = *((_QWORD *)this + 14);
      LODWORD(v59) = -1;
      v12 = (*(__int64 (__fastcall **)(_QWORD, const IID *, __int64 *))(**(_QWORD **)(v45 + 8LL * m) + 56LL))(
              *(_QWORD *)(v45 + 8LL * m),
              &MF_DEVICESTREAM_STREAM_ID,
              &v59);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v14 = 201;
        goto LABEL_4;
      }
      v46 = *(_QWORD *)(*((_QWORD *)this + 14) + 8LL * m);
      v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, _QWORD))(*(_QWORD *)v46 + 168LL))(
              v46,
              MF_DEVICESTREAM_SENSORSTREAM_FSSTREAM_ID,
              (unsigned int)v59);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v14 = 202;
        goto LABEL_4;
      }
      if ( ((*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 21) + 152LL))(*((_QWORD *)this + 21)) & 0x40000000) == 0 )
      {
        v12 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(**((_QWORD **)this + 21) + 144LL))(
                *((_QWORD *)this + 21),
                (unsigned int)v59,
                m + a7);
        v13 = v12;
        if ( v12 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_145;
          v14 = 203;
          goto LABEL_4;
        }
      }
    }
    v47 = *(_QWORD *)(*((_QWORD *)this + 14) + 8LL * m);
    v12 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v47 + 288LL))(v47, m + a7);
    v13 = v12;
    if ( v12 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_145;
      v14 = 204;
      goto LABEL_4;
    }
    v48 = *(_QWORD *)(*((_QWORD *)this + 14) + 8LL * m);
    v12 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v48 + 240LL))(v48, &Size);
    v13 = v12;
    if ( v12 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_145;
      v14 = 205;
      goto LABEL_4;
    }
    if ( Size )
    {
      if ( a5 <= 0 )
      {
        v50 = 0;
        v49 = Size_4;
      }
      else
      {
        v49 = Size_4;
        v50 = a5 - Size_4;
      }
      if ( a4 )
        v51 = &a4[v49];
      else
        v51 = 0;
      v12 = SensorDevice::SerializeStreamAttributes(
              this,
              *(struct IMFAttributes **)(*((_QWORD *)this + 14) + 8LL * m),
              m + a7,
              v51,
              v50,
              &v64);
      v13 = v12;
      if ( v12 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_145;
        v14 = 206;
        goto LABEL_4;
      }
      Size_4 = v64 + v49;
    }
    v17 = v62;
  }
  v52 = v70;
  v53 = v71;
  v54 = Size_4;
  *v70 = v17;
  *v53 = v54;
  if ( a4 )
  {
    if ( a5 < v54 )
    {
      v13 = -2147024774;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          207,
          &WPP_0eec4797894634749f1184d2686a5cfc_Traceguids,
          this,
          -2147024774);
      goto LABEL_145;
    }
    *((_DWORD *)a4 + 5) = pcbBufSize;
    *(_QWORD *)a4 = 0;
    *((_QWORD *)a4 + 1) = 0;
    *((_DWORD *)a4 + 4) = v54;
    *((_DWORD *)a4 + 6) = *((_DWORD *)this + 30);
  }
  if ( v13 < 0 )
    goto LABEL_145;
  if ( a4 && (unsigned __int8)byte_18008D62D >= 8u )
    WPP_SF_qDddddiiddd(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      v41,
      v42,
      (_DWORD)this,
      v13,
      *v52,
      *((_BYTE *)this + 201),
      *((_DWORD *)this + 45),
      *((_DWORD *)this + 44),
      *(_QWORD *)a4,
      *((_QWORD *)a4 + 1),
      *((_DWORD *)a4 + 4),
      *((_DWORD *)a4 + 5),
      *((_DWORD *)a4 + 6));
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18001e30c  push    rbp
0x18001e30e  push    rbx
0x18001e30f  push    rsi
0x18001e310  push    rdi
0x18001e311  push    r12
0x18001e313  push    r13
0x18001e315  push    r14
0x18001e317  push    r15
0x18001e319  lea     rbp, [rsp-208h]
0x18001e321  sub     rsp, 308h
0x18001e328  mov     rax, cs:__security_cookie
0x18001e32f  xor     rax, rsp
0x18001e332  mov     [rbp+240h+var_50], rax
0x18001e339  mov     rax, [rbp+240h+arg_28]
0x18001e340  mov     rsi, rcx
0x18001e343  mov     r13, [rbp+240h+arg_38]
0x18001e34a  xor     ecx, ecx
0x18001e34c  mov     [rbp+240h+var_280], rax
0x18001e350  mov     r14, r9
0x18001e353  mov     [rbp+240h+var_288], r13
0x18001e357  mov     rdi, r8
0x18001e35a  mov     [rbp+240h+var_2B8], ecx
0x18001e35d  mov     r12, rdx
0x18001e360  mov     [rbp+240h+pcbBufSize], ecx
0x18001e363  test    rax, rax
0x18001e366  jnz     short loc_18001E3A4
0x18001e368  mov     eax, 80004003h
0x18001e36d  mov     ebx, eax
0x18001e36f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e376  jb      loc_18001EDB2
0x18001e37c  mov     edx, 0B8h
0x18001e381  mov     [rsp+340h+var_320], eax
0x18001e385  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e38c  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x18001e393  mov     r9, rsi
0x18001e396  mov     rcx, [rcx+10h]
0x18001e39a  call    WPP_SF_qD
0x18001e39f  jmp     loc_18001EDB2
0x18001e3a4  test    r13, r13
0x18001e3a7  jnz     short loc_18001E3C4
0x18001e3a9  mov     eax, 80004003h
0x18001e3ae  mov     ebx, eax
0x18001e3b0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e3b7  jb      loc_18001EDB2
0x18001e3bd  mov     edx, 0B9h
0x18001e3c2  jmp     short loc_18001E381
0x18001e3c4  mov     [rax], ecx
0x18001e3c6  mov     [r13+0], ecx
0x18001e3ca  xor     r13d, r13d
0x18001e3cd  test    r14, r14
0x18001e3d0  jz      short loc_18001E418
0x18001e3d2  cmp     cs:byte_18008D62D, 8
0x18001e3d9  mov     r15d, [rbp+240h+arg_20]
0x18001e3e0  jb      short loc_18001E41F
0x18001e3e2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e3e9  mov     r9, rsi
0x18001e3ec  mov     eax, [rbp+240h+arg_30]
0x18001e3f2  mov     [rsp+340h+var_300], eax
0x18001e3f6  mov     [rsp+340h+var_308], r15d
0x18001e3fb  mov     rcx, [rcx+0D8h]
0x18001e402  mov     [rsp+340h+var_310], r14
0x18001e407  mov     [rsp+340h+var_318], rdi
0x18001e40c  mov     qword ptr [rsp+340h+var_320], r12
0x18001e411  call    WPP_SF_qqqqdd
0x18001e416  jmp     short loc_18001E41F
0x18001e418  mov     r15d, [rbp+240h+arg_20]
0x18001e41f  mov     ecx, 248h
0x18001e424  mov     dword ptr [rsp+340h+Size+4], ecx
0x18001e428  test    rdi, rdi
0x18001e42b  jz      short loc_18001E4A7
0x18001e42d  lea     rdx, [rbp+240h+pcbBufSize]; pcbBufSize
0x18001e431  mov     rcx, rdi; pAttributes
0x18001e434  call    cs:__imp_MFGetAttributesAsBlobSize
0x18001e43a  mov     ebx, eax
0x18001e43c  test    eax, eax
0x18001e43e  jns     short loc_18001E457
0x18001e440  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e447  jb      loc_18001EDB2
0x18001e44d  mov     edx, 0BBh
0x18001e452  jmp     loc_18001E381
0x18001e457  test    r14, r14
0x18001e45a  jz      short loc_18001E49A
0x18001e45c  mov     ecx, [rbp+240h+pcbBufSize]
0x18001e45f  lea     eax, [r15-248h]
0x18001e466  cmp     eax, ecx
0x18001e468  jl      short loc_18001E49D
0x18001e46a  mov     r8d, ecx; cbBufSize
0x18001e46d  lea     rdx, [r14+248h]; pBuf
0x18001e474  mov     rcx, rdi; pAttributes
0x18001e477  call    cs:__imp_MFGetAttributesAsBlob
0x18001e47d  mov     ebx, eax
0x18001e47f  test    eax, eax
0x18001e481  jns     short loc_18001E49A
0x18001e483  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e48a  jb      loc_18001EDB2
0x18001e490  mov     edx, 0BCh
0x18001e495  jmp     loc_18001E381
0x18001e49a  mov     ecx, [rbp+240h+pcbBufSize]
0x18001e49d  add     ecx, 248h
0x18001e4a3  mov     dword ptr [rsp+340h+Size+4], ecx
0x18001e4a7  mov     r15d, [rsi+78h]
0x18001e4ab  mov     [rbp+240h+var_2C0], r15d
0x18001e4af  cmp     [rsi+0C8h], r13b
0x18001e4b6  jnz     loc_18001E8DF
0x18001e4bc  mov     rcx, [rsi+0A8h]
0x18001e4c3  mov     rax, [rcx]
0x18001e4c6  mov     rax, [rax+18h]
0x18001e4ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4cf  cmp     byte ptr [rsi+0E0h], 0
0x18001e4d6  mov     r13d, eax
0x18001e4d9  jnz     short loc_18001E538
0x18001e4db  xor     edi, edi
0x18001e4dd  cmp     edi, r15d
0x18001e4e0  jnb     short loc_18001E538
0x18001e4e2  test    r12, r12
0x18001e4e5  jz      short loc_18001E538
0x18001e4e7  mov     r8, [rsi+70h]
0x18001e4eb  mov     r9d, edi; unsigned int
0x18001e4ee  mov     rdx, r12; struct IMFMediaSource *
0x18001e4f1  mov     rcx, rsi; this
0x18001e4f4  mov     r8, [r8+rdi*8]; struct IMFAttributes *
0x18001e4f8  call    ?SetFaceAuthDDICapabilityOnStream@SensorDevice@@IEAAJPEAUIMFMediaSource@@PEAUIMFAttributes@@K@Z; SensorDevice::SetFaceAuthDDICapabilityOnStream(IMFMediaSource *,IMFAttributes *,ulong)
0x18001e4fd  mov     ebx, eax
0x18001e4ff  test    eax, eax
0x18001e501  js      loc_18001EDB2
0x18001e507  cmp     byte ptr [rsi+0E1h], 0
0x18001e50e  jnz     short loc_18001E530
0x18001e510  mov     r8, [rsi+70h]
0x18001e514  mov     r9d, edi; unsigned int
0x18001e517  mov     rdx, r12; struct IMFMediaSource *
0x18001e51a  mov     rcx, rsi; this
0x18001e51d  mov     r8, [r8+rdi*8]; struct IMFAttributes *
0x18001e521  call    ?SetSecureModeDDICapabilityOnStream@SensorDevice@@IEAAJPEAUIMFMediaSource@@PEAUIMFAttributes@@K@Z; SensorDevice::SetSecureModeDDICapabilityOnStream(IMFMediaSource *,IMFAttributes *,ulong)
0x18001e526  mov     ebx, eax
0x18001e528  test    eax, eax
0x18001e52a  js      loc_18001EDB2
0x18001e530  mov     r15d, [rbp+240h+var_2C0]
0x18001e534  inc     edi
0x18001e536  jmp     short loc_18001E4DD
0x18001e538  cmp     qword ptr [rsi+0D8h], 0
0x18001e540  jz      loc_18001E66C
0x18001e546  xor     edx, edx; Val
0x18001e548  lea     rcx, [rbp+240h+var_260]; void *
0x18001e54c  mov     r8d, 208h; Size
0x18001e552  call    memset_0
0x18001e557  mov     rax, [rsi+0C0h]
0x18001e55e  lea     r8, aFaceAuthStream; "face_auth_streamid=%d,face_auth_caps=0x"...
0x18001e565  mov     r9d, [rsi+0B4h]
0x18001e56c  lea     rcx, [rbp+240h+var_260]; unsigned __int16 *
0x18001e570  mov     [rsp+340h+var_310], rax
0x18001e575  mov     edi, 104h
0x18001e57a  mov     eax, [rsi+0B0h]
0x18001e580  mov     edx, edi; unsigned __int64
0x18001e582  mov     dword ptr [rsp+340h+var_318], eax
0x18001e586  mov     rax, [rsi+0B8h]
0x18001e58d  mov     qword ptr [rsp+340h+var_320], rax
0x18001e592  mov     [rbp+240h+var_2A8], 0
0x18001e59a  mov     [rbp+240h+pv], 0
0x18001e5a2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001e5a7  mov     ebx, eax
0x18001e5a9  test    eax, eax
0x18001e5ab  jns     short loc_18001E5C2
0x18001e5ad  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e5b4  jb      loc_18001EDB2
0x18001e5ba  lea     edx, [rdi-47h]
0x18001e5bd  jmp     loc_18001E381
0x18001e5c2  lea     r8, [rbp+240h+var_2A8]; unsigned __int64 *
0x18001e5c6  mov     rdx, rdi; unsigned __int64
0x18001e5c9  lea     rcx, [rbp+240h+var_260]; unsigned __int16 *
0x18001e5cd  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18001e5d2  mov     ebx, eax
0x18001e5d4  test    eax, eax
0x18001e5d6  jns     short loc_18001E5EF
0x18001e5d8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e5df  jb      loc_18001EDB2
0x18001e5e5  mov     edx, 0BEh
0x18001e5ea  jmp     loc_18001E381
0x18001e5ef  mov     rcx, [rsi+0D8h]
0x18001e5f6  lea     r9, [rbp+240h+pv]
0x18001e5fa  mov     rdi, [rbp+240h+var_2A8]
0x18001e5fe  mov     edx, 10h
0x18001e603  inc     rdi
0x18001e606  mov     qword ptr [rsp+340h+var_320], 0
0x18001e60f  mov     rax, [rcx]
0x18001e612  lea     r8d, [rdi+rdi]
0x18001e616  mov     rax, [rax+0C0h]
0x18001e61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e622  mov     ebx, eax
0x18001e624  test    eax, eax
0x18001e626  jns     short loc_18001E63F
0x18001e628  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e62f  jb      loc_18001EDB2
0x18001e635  mov     edx, 0BFh
0x18001e63a  jmp     loc_18001E381
0x18001e63f  mov     rcx, [rbp+240h+pv]; unsigned __int16 *
0x18001e643  lea     r8, [rbp+240h+var_260]; unsigned __int16 *
0x18001e647  mov     rdx, rdi; unsigned __int64
0x18001e64a  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18001e64f  mov     ebx, eax
0x18001e651  test    eax, eax
0x18001e653  jns     short loc_18001E66C
0x18001e655  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e65c  jb      loc_18001EDB2
0x18001e662  mov     edx, 0C0h
0x18001e667  jmp     loc_18001E381
0x18001e66c  xor     dil, dil
0x18001e66f  cmp     dword ptr [rsi+0B4h], 0FFFFFFFFh
0x18001e676  jz      loc_18001E722
0x18001e67c  test    r13d, r13d
0x18001e67f  jz      loc_18001E722
0x18001e685  xor     edi, edi
0x18001e687  cmp     edi, r13d
0x18001e68a  jnb     loc_18001E799
0x18001e690  mov     rcx, [rsi+0A8h]
0x18001e697  lea     r8, [rsp+340h+var_2D0]
0x18001e69c  xor     eax, eax
0x18001e69e  mov     [rsp+340h+var_2D0], 0
0x18001e6a7  mov     [rbp+240h+var_268], rax
0x18001e6ab  xorps   xmm0, xmm0
0x18001e6ae  movups  [rbp+240h+Buf1], xmm0
0x18001e6b2  mov     rax, [rcx]
0x18001e6b5  mov     edx, edi
0x18001e6b7  mov     rax, [rax+20h]
0x18001e6bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6c0  mov     ebx, eax
0x18001e6c2  test    eax, eax
0x18001e6c4  js      loc_18001E75E
0x18001e6ca  mov     rcx, [rsp+340h+var_2D0]
0x18001e6cf  lea     rdx, [rbp+240h+Buf1]
0x18001e6d3  mov     rax, [rcx]
0x18001e6d6  mov     rax, [rax+18h]
0x18001e6da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6df  mov     ebx, eax
0x18001e6e1  test    eax, eax
0x18001e6e3  js      short loc_18001E74E
0x18001e6e5  mov     r8d, 10h; Size
0x18001e6eb  lea     rdx, _GUID_81361b22_700b_4546_a2d4_c52e907bfc27; Buf2
0x18001e6f2  lea     rcx, [rbp+240h+Buf1]; Buf1
0x18001e6f6  call    memcmp_0
0x18001e6fb  lea     rcx, [rsp+340h+var_2D0]
0x18001e700  test    eax, eax
0x18001e702  jz      short loc_18001E710
0x18001e704  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18001e709  inc     edi
0x18001e70b  jmp     loc_18001E687
0x18001e710  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18001e715  mov     dword ptr [rsi+0CCh], 0FFFFFFFFh
0x18001e71f  mov     dil, 1
0x18001e722  xor     r13d, r13d
0x18001e725  mov     rcx, rsi; this
0x18001e728  call    ?SynthesizeCPV2FaceAuthProfile@SensorDevice@@IEAAJXZ; SensorDevice::SynthesizeCPV2FaceAuthProfile(void)
0x18001e72d  mov     ebx, eax
0x18001e72f  test    eax, eax
0x18001e731  jns     loc_18001E8D1
0x18001e737  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e73e  jb      loc_18001EDB2
0x18001e744  mov     edx, 0C7h
0x18001e749  jmp     loc_18001E381
0x18001e74e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e755  jb      short loc_18001E78A
0x18001e757  mov     edx, 0C2h
0x18001e75c  jmp     short loc_18001E76C
0x18001e75e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e765  jb      short loc_18001E78A
0x18001e767  mov     edx, 0C1h
0x18001e76c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001e773  lea     r8, WPP_0eec4797894634749f1184d2686a5cfc_Traceguids
0x18001e77a  mov     r9, rsi
0x18001e77d  mov     [rsp+340h+var_320], eax
0x18001e781  mov     rcx, [rcx+10h]
0x18001e785  call    WPP_SF_qD
0x18001e78a  lea     rcx, [rsp+340h+var_2D0]
0x18001e78f  call    ??1?$com_ptr_t@UIMFSensorProfileInternal@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>::~com_ptr_t<IMFSensorProfileInternal,wil::err_returncode_policy>(void)
0x18001e794  jmp     loc_18001EDB2
0x18001e799  cmp     dword ptr [rsi+0CCh], 0FFFFFFFFh
0x18001e7a0  setnz   dil
0x18001e7a4  jnz     loc_18001E722
0x18001e7aa  lea     r9, [rsp+340h+var_2D0]
0x18001e7af  mov     [rsp+340h+var_2D0], 0
0x18001e7b8  xor     r8d, r8d
0x18001e7bb  lea     rcx, _GUID_81361b22_700b_4546_a2d4_c52e907bfc27
0x18001e7c2  xor     edx, edx
0x18001e7c4  call    MFCreateSensorProfile
0x18001e7c9  mov     ebx, eax
0x18001e7cb  test    eax, eax
0x18001e7cd  jns     short loc_18001E7DF
0x18001e7cf  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001e7d6  jb      short loc_18001E78A
0x18001e7d8  mov     edx, 0C3h
0x18001e7dd  jmp     short loc_18001E76C
0x18001e7df  mov     r13d, [rbp+240h+var_2C0]
0x18001e7e3  xor     r15d, r15d
0x18001e7e6  cmp     r15d, r13d
0x18001e7e9  jnb     loc_18001E886
0x18001e7ef  mov     rcx, [rsi+70h]
0x18001e7f3  lea     rdx, MF_DEVICESTREAM_STREAM_ID
0x18001e7fa  or      r8d, 0FFFFFFFFh
0x18001e7fe  mov     rcx, [rcx+r15*8]
0x18001e802  call    MFGetAttributeUINT32
0x18001e807  mov     edx, eax
  ... truncated ...
```
