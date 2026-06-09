# SensorTransform::InitializeSensorTransform(void)

- ea: `0x1800bed40`
- end: `0x1800bfb37`
- name: `?InitializeSensorTransform@SensorTransform@@MEAAJXZ`
- size: `3575`
- prototype: `__int64 __fastcall(SensorTransform *__hidden this)`
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callees

- `0x180003e20`
- `0x1800041f0`
- `0x18000478c`
- `0x180004f20`
- `0x180008cf0`
- `0x180009608`
- `0x1800096f4`
- `0x18000ad10`
- `0x1800180c8`
- `0x1800766d0`
- `0x1800bed40`
- `0x1800c2bd4`
- `0x1800c2e4c`
- `0x1800c349c`
- `0x1800c407c`
- `0x1800c5750`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf54f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf9c0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf54f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800bf9c0`
- `MFPlat!MFCreateAttributes` at `0x1800bf2f8`
- `MFPlat!MFCreateAttributes` at `0x1800bf7f9`
- `MFPlat!MFCreateAttributes` at `0x1800bf867`
- `MFPlat!MFCreateAttributes` at `0x1800bf2f8`
- `MFPlat!MFCreateAttributes` at `0x1800bf7f9`
- `MFPlat!MFCreateAttributes` at `0x1800bf867`
- `MFPlat!MFCreateEventQueue` at `0x1800bfa3d`
- `MFPlat!MFCreateEventQueue` at `0x1800bfa3d`

## pseudocode

```c
__int64 __fastcall SensorTransform::InitializeSensorTransform(SensorTransform *this)
{
  unsigned int v1; // r15d
  __int64 v3; // rcx
  HRESULT v4; // eax
  unsigned int v5; // ebx
  __int64 v6; // rdx
  unsigned int v7; // r13d
  unsigned int v8; // ebx
  __int64 v9; // rax
  unsigned int v10; // r12d
  __int64 *v11; // rcx
  __int64 v12; // rax
  int v13; // eax
  __int64 v14; // rdx
  __int64 v15; // r8
  int v16; // eax
  __int64 v17; // rdx
  __int64 v18; // rdx
  struct IMFAttributes *v19; // rdx
  unsigned int *v20; // r12
  unsigned int *v21; // r15
  struct SensorTransformContextStream *v22; // rax
  struct SensorTransformContextStream *v23; // rbx
  _DWORD *v24; // rax
  const struct std::nothrow_t *v25; // rdx
  _DWORD *v26; // r13
  struct IFSSource *v27; // r15
  HRESULT v28; // eax
  __int64 v29; // rdx
  const struct std::nothrow_t *v30; // rdx
  char v32; // al
  __int64 v33; // rbx
  struct SensorTransformContextStream *v34; // r12
  __int64 i; // rbx
  __int64 j; // r15
  struct IMFDeviceTransform *v37; // r8
  unsigned int v38; // edx
  int Instance; // eax
  __int64 v40; // rdx
  __int64 v41; // rcx
  _QWORD *v42; // r15
  UINT32 v43; // edx
  UINT32 k; // r12d
  __int64 v45; // rcx
  IMFMediaEventQueue *v46; // rcx
  struct IFSSource *v47; // rax
  __int64 v48; // rcx
  __int64 v49; // rcx
  __int64 v50; // rcx
  __int64 v51; // rcx
  struct IFSSource *v52; // [rsp+40h] [rbp-89h] BYREF
  UINT32 v53; // [rsp+48h] [rbp-81h] BYREF
  __int64 v54; // [rsp+50h] [rbp-79h] BYREF
  __int64 v55; // [rsp+58h] [rbp-71h] BYREF
  __int64 v56; // [rsp+60h] [rbp-69h] BYREF
  struct SensorTransformContextStream *v57; // [rsp+68h] [rbp-61h] BYREF
  unsigned int v58; // [rsp+70h] [rbp-59h] BYREF
  __int64 v59; // [rsp+78h] [rbp-51h] BYREF
  IMFMediaEventQueue *ppMediaEventQueue; // [rsp+80h] [rbp-49h] BYREF
  __int64 v61; // [rsp+88h] [rbp-41h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+90h] [rbp-39h] BYREF
  __int64 v63; // [rsp+98h] [rbp-31h] BYREF
  struct IMFTransform *v64; // [rsp+A0h] [rbp-29h] BYREF
  __int64 v65; // [rsp+A8h] [rbp-21h] BYREF
  PROPVARIANT pvar[2]; // [rsp+B0h] [rbp-19h] BYREF
  __int64 v67; // [rsp+C0h] [rbp-9h]
  struct SensorTransformStream *v68[2]; // [rsp+C8h] [rbp-1h] BYREF

  v1 = 0;
  v65 = 0;
  v3 = *((_QWORD *)this + 90);
  v58 = 0;
  ppMFAttributes = 0;
  v61 = 0;
  ppMediaEventQueue = 0;
  v64 = 0;
  v63 = 0;
  v59 = 0;
  v67 = 0;
  *(_OWORD *)pvar = 0;
  if ( v3 )
  {
    if ( !*((_QWORD *)this + 81) )
    {
      v4 = -1072875845;
      v5 = -1072875845;
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 162;
      goto LABEL_4;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v3 + 168LL))(v3, &v63);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 163;
      goto LABEL_4;
    }
    v4 = FSClientContextInfo::CloneFSClientContextInfo(
           v63,
           *((unsigned int *)this + 196),
           0,
           0,
           1,
           &GUID_487ba10d_7ad6_44ca_a059_4d920d522f0e,
           &v59);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 164;
      goto LABEL_4;
    }
    v4 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(**((_QWORD **)this + 90) + 152LL))(
           *((_QWORD *)this + 90),
           &v58);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 165;
      goto LABEL_4;
    }
    v7 = 0;
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
    {
      v8 = v58;
      v9 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v59 + 128LL))(v59);
      WPP_SF_qqD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        166,
        &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
        this,
        v9,
        v8);
    }
    v10 = 0;
LABEL_20:
    if ( v10 < v58 )
    {
      v11 = (__int64 *)*((_QWORD *)this + 90);
      v52 = 0;
      v54 = 0;
      v53 = 0;
      v12 = *v11;
      v56 = 0;
      v55 = 0;
      v13 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct IFSSource **))(v12 + 160))(v11, v10, &v52);
      v5 = v13;
      if ( v13 < 0 )
      {
        if ( g_wppLevels )
        {
          v18 = 167;
          goto LABEL_52;
        }
      }
      else
      {
        v13 = SensorTransformContextSource::CreateInstance(this, v52, v59, *((unsigned int *)this + 196), &v55);
        v5 = v13;
        if ( v13 < 0 )
        {
          if ( g_wppLevels )
          {
            v18 = 168;
            goto LABEL_52;
          }
        }
        else if ( (unsigned int)CTUnkArray<IMFMediaType>::Add((char *)this + 760, v55) )
        {
          v13 = (*(__int64 (__fastcall **)(struct IFSSource *, GUID *, GUID *, __int64 *))(*(_QWORD *)v52 + 224LL))(
                  v52,
                  &GUID_00000000_0000_0000_0000_000000000000,
                  &GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8,
                  &v54);
          v5 = v13;
          if ( v13 < 0 )
          {
            if ( g_wppLevels )
            {
              v18 = 170;
              goto LABEL_52;
            }
          }
          else
          {
            v13 = (*(__int64 (__fastcall **)(struct IFSSource *, UINT32 *))(*(_QWORD *)v52 + 64LL))(v52, &v53);
            v5 = v13;
            if ( v13 >= 0 )
            {
              if ( (unsigned __int8)byte_18010EC4D >= 8u )
                WPP_SF_qqDD(*((_QWORD *)WPP_GLOBAL_Control + 27), v14, v15, this, v52, v53, v7);
              while ( 1 )
              {
                if ( v1 >= v53 )
                {
                  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v55);
                  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v56);
                  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v54);
                  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v52);
                  ++v10;
                  v1 = 0;
                  goto LABEL_20;
                }
                v68[0] = 0;
                v57 = 0;
                v16 = (*(__int64 (__fastcall **)(struct IFSSource *, _QWORD, struct SensorTransformStream **))(*(_QWORD *)v52 + 72LL))(
                        v52,
                        v1,
                        v68);
                v5 = v16;
                if ( v16 < 0 )
                  break;
                v16 = SensorTransformContextStream::CreateInstance(this, v52, v1, v7, &v57);
                v5 = v16;
                if ( v16 < 0 )
                {
                  if ( !g_wppLevels )
                    goto LABEL_41;
                  v17 = 174;
                  goto LABEL_40;
                }
                if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add((char *)this + 736, v57) )
                {
                  v16 = -2147024882;
                  v5 = -2147024882;
                  if ( !g_wppLevels )
                    goto LABEL_41;
                  v17 = 175;
                  goto LABEL_40;
                }
                ++v7;
                wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v57);
                wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v68);
                ++v1;
              }
              if ( !g_wppLevels )
                goto LABEL_41;
              v17 = 173;
LABEL_40:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v17,
                &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
                this,
                v16);
LABEL_41:
              wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v57);
              wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v68);
              goto LABEL_53;
            }
            if ( g_wppLevels )
            {
              v18 = 171;
LABEL_52:
              WPP_SF_qD(
                *((_QWORD *)WPP_GLOBAL_Control + 2),
                v18,
                &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
                this,
                v13);
            }
          }
        }
        else
        {
          v13 = -2147024882;
          v5 = -2147024882;
          if ( g_wppLevels )
          {
            v18 = 169;
            goto LABEL_52;
          }
        }
      }
LABEL_53:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v55);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v56);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v54);
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v52);
      goto LABEL_98;
    }
    v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 81))(
           *((_QWORD *)this + 81),
           &GUID_2cd0bd52_bcd5_4b89_b62c_eadc0c031e7d,
           (char *)this + 696);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 176;
      goto LABEL_4;
    }
    v4 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 81))(
           *((_QWORD *)this + 81),
           &GUID_03910848_ab16_4611_b100_17b88ae2f248,
           &v65);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 177;
      goto LABEL_4;
    }
    v4 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v65 + 40LL))(
           v65,
           *((unsigned int *)this + 13),
           0);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 178;
      goto LABEL_4;
    }
    v4 = (*(__int64 (__fastcall **)(_QWORD, char *, _QWORD))(**((_QWORD **)this + 87) + 32LL))(
           *((_QWORD *)this + 87),
           (char *)this + 32,
           0);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 179;
      goto LABEL_4;
    }
    v4 = SensorTransformFSSourceDMFT::CreateInstance(*((struct IFSClientContext **)this + 90), v19, &v64);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 180;
      goto LABEL_4;
    }
    v4 = MFCreateAttributes(&ppMFAttributes, 1u);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 181;
      goto LABEL_4;
    }
    v4 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, struct IMFTransform *))ppMFAttributes->lpVtbl->SetUnknown)(
           ppMFAttributes,
           &MF_DEVICEMFT_CONNECTED_FILTER_KSCONTROL,
           v64);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 182;
      goto LABEL_4;
    }
    v4 = (*(__int64 (__fastcall **)(_QWORD, IMFAttributes *))(**((_QWORD **)this + 81) + 24LL))(
           *((_QWORD *)this + 81),
           ppMFAttributes);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 183;
      goto LABEL_4;
    }
    v20 = (unsigned int *)((char *)this + 704);
    v21 = (unsigned int *)((char *)this + 708);
    v4 = (*(__int64 (__fastcall **)(_QWORD, char *, char *))(**((_QWORD **)this + 81) + 80LL))(
           *((_QWORD *)this + 81),
           (char *)this + 708,
           (char *)this + 704);
    v5 = v4;
    if ( v4 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 184;
      goto LABEL_4;
    }
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_qDD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        185,
        &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
        this,
        *v21,
        *v20);
    v22 = (struct SensorTransformContextStream *)operator new[](saturated_mul(*v21, 4u));
    v57 = v22;
    v23 = v22;
    if ( !v22 )
    {
      v4 = -2147024882;
      v5 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_98;
      v6 = 186;
      goto LABEL_4;
    }
    memset_0(v22, 0, 4LL * *v21);
    v24 = operator new[](saturated_mul(*v20, 4u));
    v26 = v24;
    if ( !v24 )
    {
      v27 = 0;
      v5 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          187,
          &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
          this,
          -2147024882);
      goto LABEL_94;
    }
    memset_0(v24, 0, 4LL * *v20);
    v52 = (struct IFSSource *)operator new[](saturated_mul(*v20, 0x20u));
    if ( v52 )
    {
      v28 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, struct SensorTransformContextStream *, _QWORD, _DWORD *))(**((_QWORD **)this + 81) + 88LL))(
              *((_QWORD *)this + 81),
              *v21,
              v23,
              *v20,
              v26);
      v5 = v28;
      if ( v28 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_93;
        v29 = 189;
        goto LABEL_92;
      }
      v32 = byte_18010EC4D;
      if ( (unsigned __int8)byte_18010EC4D >= 8u )
      {
        v33 = 0;
        if ( *v21 )
        {
          v34 = v57;
          do
          {
            if ( (unsigned __int8)v32 >= 8u )
            {
              WPP_SF_qDD(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                190,
                &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
                this,
                v33,
                *((_DWORD *)v34 + v33));
              v32 = byte_18010EC4D;
            }
            v33 = (unsigned int)(v33 + 1);
          }
          while ( (unsigned int)v33 < *v21 );
          v20 = (unsigned int *)((char *)this + 704);
        }
        for ( i = 0; (unsigned int)i < *v20; i = (unsigned int)(i + 1) )
        {
          if ( (unsigned __int8)v32 >= 8u )
          {
            WPP_SF_qDD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              191,
              &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
              this,
              i,
              v26[i]);
            v32 = byte_18010EC4D;
          }
        }
      }
      for ( j = 0; (unsigned int)j < *v20; j = (unsigned int)(j + 1) )
      {
        v37 = (struct IMFDeviceTransform *)*((_QWORD *)this + 81);
        v38 = v26[j];
        v68[0] = 0;
        Instance = SensorTransformStream::CreateInstance(j, v38, v37, this, v68);
        v5 = Instance;
        if ( Instance < 0 )
        {
          if ( g_wppLevels )
          {
            v40 = 192;
LABEL_120:
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v40,
              &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids,
              this,
              Instance);
          }
LABEL_121:
          wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v68);
          goto LABEL_93;
        }
        if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add((char *)this + 808, v68[0]) )
        {
          Instance = -2147024882;
          v5 = -2147024882;
          if ( g_wppLevels )
          {
            v40 = 193;
            goto LABEL_120;
          }
          goto LABEL_121;
        }
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(v68);
      }
      v41 = *((_QWORD *)this + 7);
      v53 = 0;
      LODWORD(v55) = 0;
      if ( v41 )
      {
        v28 = (*(__int64 (__fastcall **)(__int64, UINT32 *))(*(_QWORD *)v41 + 240LL))(v41, &v53);
        v5 = v28;
        if ( v28 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_93;
          v29 = 194;
          goto LABEL_92;
        }
      }
      if ( (***((int (__fastcall ****)(_QWORD, GUID *, __int64 *))this + 81))(
             *((_QWORD *)this + 81),
             &GUID_2cd2d921_c447_44a7_a13c_4adabfc247e3,
             &v61) < 0 )
      {
        v43 = v53;
        v42 = (_QWORD *)((char *)this + 680);
        if ( !v53 )
          v43 = 2;
        v28 = MFCreateAttributes((IMFAttributes **)this + 85, v43);
        v5 = v28;
        if ( v28 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_93;
          v29 = 198;
          goto LABEL_92;
        }
      }
      else
      {
        LODWORD(v54) = 0;
        v28 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v61 + 240LL))(v61, &v54);
        v5 = v28;
        if ( v28 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_93;
          v29 = 195;
          goto LABEL_92;
        }
        v42 = (_QWORD *)((char *)this + 680);
        v28 = MFCreateAttributes((IMFAttributes **)this + 85, v53 + v54);
        v5 = v28;
        if ( v28 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_93;
          v29 = 196;
          goto LABEL_92;
        }
        v28 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v61 + 256LL))(v61, *v42);
        v5 = v28;
        if ( v28 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_93;
          v29 = 197;
          goto LABEL_92;
        }
      }
      if ( (*(int (__fastcall **)(_QWORD, const IID *, __int64 *))(*(_QWORD *)*v42 + 32LL))(
             *v42,
             &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
             &v55) >= 0
        || (v28 = (*(__int64 (__fastcall **)(_QWORD, const IID *, char *))(*(_QWORD *)*v42 + 200LL))(
                    *v42,
                    &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
                    (char *)this + 64),
            v5 = v28,
            v28 >= 0) )
      {
        if ( (*(int (__fastcall **)(_QWORD, void *, __int64 *))(*(_QWORD *)*v42 + 32LL))(
               *v42,
               &MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE,
               &v55) >= 0
          || (v28 = (*(__int64 (__fastcall **)(_QWORD, void *, __int64))(*(_QWORD *)*v42 + 168LL))(
                      *v42,
                      &MF_DEVSOURCE_ATTRIBUTE_DEVICETYPE,
                      4),
              v5 = v28,
              v28 >= 0) )
        {
          for ( k = 0; k < v53; ++k )
          {
            v45 = *((_QWORD *)this + 7);
            *(GUID *)v68 = GUID_00000000_0000_0000_0000_000000000000;
            LODWORD(v54) = 0;
            v28 = (*(__int64 (__fastcall **)(__int64, _QWORD, struct SensorTransformStream **, PROPVARIANT *))(*(_QWORD *)v45 + 248LL))(
                    v45,
                    k,
                    v68,
                    pvar);
            v5 = v28;
            if ( v28 < 0 )
            {
              if ( !g_wppLevels )
                goto LABEL_93;
              v29 = 201;
              goto LABEL_92;
            }
            if ( (*(int (__fastcall **)(_QWORD, struct SensorTransformStream **, __int64 *))(*(_QWORD *)*v42 + 32LL))(
                   *v42,
                   v68,
                   &v54) < 0 )
            {
              v28 = (*(__int64 (__fastcall **)(_QWORD, struct SensorTransformStream **, PROPVARIANT *))(*(_QWORD *)*v42 + 144LL))(
                      *v42,
                      v68,
                      pvar);
              v5 = v28;
              if ( v28 < 0 )
              {
                if ( !g_wppLevels )
                  goto LABEL_93;
                v29 = 202;
                goto LABEL_92;
              }
            }
            PropVariantClear(pvar);
          }
          v28 = (***((__int64 (__fastcall ****)(_QWORD, GUID *, char *))this + 81))(
                  *((_QWORD *)this + 81),
                  &GUID_28f54685_06fd_11d2_b27a_00a0c9223196,
                  (char *)this + 656);
          v5 = v28;
          if ( v28 >= 0 )
          {
            v28 = MFCreateEventQueue(&ppMediaEventQueue);
            v5 = v28;
            if ( v28 >= 0 )
            {
              v46 = ppMediaEventQueue;
              v27 = 0;
              v47 = v52;
              *((_QWORD *)this + 89) = v26;
              v26 = 0;
              *((_QWORD *)this + 86) = v47;
              if ( v46 )
              {
                ((void (__fastcall *)(IMFMediaEventQueue *))v46->lpVtbl->AddRef)(v46);
                v49 = *((_QWORD *)this + 99);
                if ( v49 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v49 + 16LL))(v49);
                *((_QWORD *)this + 99) = ppMediaEventQueue;
              }
              else
              {
                v48 = *((_QWORD *)this + 99);
                if ( v48 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v48 + 16LL))(v48);
                  *((_QWORD *)this + 99) = 0;
                }
              }
              if ( v59 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 8LL))(v59);
                v51 = *((_QWORD *)this + 91);
                if ( v51 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
                *((_QWORD *)this + 91) = v59;
              }
              else
              {
                v50 = *((_QWORD *)this + 91);
                if ( v50 )
                {
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                  *((_QWORD *)this + 91) = 0;
                }
              }
              goto LABEL_94;
            }
            if ( !g_wppLevels )
              goto LABEL_93;
            v29 = 204;
          }
          else
          {
            if ( !g_wppLevels )
              goto LABEL_93;
            v29 = 203;
          }
        }
        else
        {
          if ( !g_wppLevels )
            goto LABEL_93;
          v29 = 200;
        }
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_93;
        v29 = 199;
      }
    }
    else
    {
      v28 = -2147024882;
      v5 = -2147024882;
      if ( !g_wppLevels )
      {
LABEL_93:
        v27 = v52;
LABEL_94:
        operator delete(v57, v25);
        if ( v26 )
          operator delete(v26, v30);
        if ( v27 )
          operator delete(v27, v30);
        goto LABEL_98;
      }
      v29 = 188;
    }
LABEL_92:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v29, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, this, v28);
    goto LABEL_93;
  }
  v4 = -1072875845;
  v5 = -1072875845;
  if ( g_wppLevels )
  {
    v6 = 161;
LABEL_4:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v6, &WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids, this, v4);
  }
LABEL_98:
  PropVariantClear(pvar);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v59);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v63);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v64);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMediaEventQueue);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v61);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v65);
  return v5;
}

```

## disassembly

```asm
0x1800bed40  push    rbp
0x1800bed42  push    rbx
0x1800bed43  push    rsi
0x1800bed44  push    rdi
0x1800bed45  push    r12
0x1800bed47  push    r13
0x1800bed49  push    r14
0x1800bed4b  push    r15
0x1800bed4d  lea     rbp, [rsp-1Fh]
0x1800bed52  sub     rsp, 0E8h
0x1800bed59  mov     rax, cs:__security_cookie
0x1800bed60  xor     rax, rsp
0x1800bed63  mov     [rbp+57h+var_48], rax
0x1800bed67  xor     r15d, r15d
0x1800bed6a  xor     eax, eax
0x1800bed6c  mov     rdi, rcx
0x1800bed6f  mov     [rbp+57h+var_78], r15
0x1800bed73  mov     rcx, [rcx+2D0h]
0x1800bed7a  xorps   xmm0, xmm0
0x1800bed7d  mov     [rbp+57h+var_B0], r15d
0x1800bed81  mov     [rbp+57h+ppMFAttributes], r15
0x1800bed85  mov     [rbp+57h+var_98], r15
0x1800bed89  mov     [rbp+57h+ppMediaEventQueue], r15
0x1800bed8d  mov     [rbp+57h+var_80], r15
0x1800bed91  mov     [rbp+57h+var_88], r15
0x1800bed95  mov     [rbp+57h+var_A8], r15
0x1800bed99  mov     [rbp+57h+var_60], rax
0x1800bed9d  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x1800beda1  test    rcx, rcx
0x1800beda4  jnz     short loc_1800BEDE5
0x1800beda6  mov     eax, 0C00D36BBh
0x1800bedab  mov     ebx, eax
0x1800bedad  lea     esi, [rcx+1]
0x1800bedb0  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bedb7  jb      loc_1800BF54B
0x1800bedbd  mov     edx, 0A1h
0x1800bedc2  lea     r8, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x1800bedc9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bedd0  mov     r9, rdi
0x1800bedd3  mov     dword ptr [rsp+120h+var_100], eax
0x1800bedd7  mov     rcx, [rcx+10h]
0x1800beddb  call    WPP_SF_qD
0x1800bede0  jmp     loc_1800BF54B
0x1800bede5  cmp     [rdi+288h], r15
0x1800bedec  jnz     short loc_1800BEE0E
0x1800bedee  mov     eax, 0C00D36BBh
0x1800bedf3  mov     ebx, eax
0x1800bedf5  mov     esi, 1
0x1800bedfa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bee01  jb      loc_1800BF54B
0x1800bee07  mov     edx, 0A2h
0x1800bee0c  jmp     short loc_1800BEDC2
0x1800bee0e  mov     rax, [rcx]
0x1800bee11  lea     rdx, [rbp+57h+var_88]
0x1800bee15  mov     rax, [rax+0A8h]
0x1800bee1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bee21  mov     ebx, eax
0x1800bee23  test    eax, eax
0x1800bee25  jns     short loc_1800BEE40
0x1800bee27  mov     esi, 1
0x1800bee2c  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bee33  jb      loc_1800BF54B
0x1800bee39  mov     edx, 0A3h
0x1800bee3e  jmp     short loc_1800BEDC2
0x1800bee40  mov     edx, [rdi+310h]
0x1800bee46  lea     rax, [rbp+57h+var_A8]
0x1800bee4a  mov     rcx, [rbp+57h+var_88]
0x1800bee4e  mov     esi, 1
0x1800bee53  mov     [rsp+120h+var_F0], rax
0x1800bee58  xor     r9d, r9d
0x1800bee5b  lea     rax, _GUID_487ba10d_7ad6_44ca_a059_4d920d522f0e
0x1800bee62  xor     r8d, r8d
0x1800bee65  mov     [rsp+120h+var_F8], rax
0x1800bee6a  mov     byte ptr [rsp+120h+var_100], sil
0x1800bee6f  call    ?CloneFSClientContextInfo@FSClientContextInfo@@SAJPEAUIFSClientContextInfo@@W4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@W4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0018@@_N3AEBU_GUID@@PEAPEAX@Z; FSClientContextInfo::CloneFSClientContextInfo(IFSClientContextInfo *,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0018,bool,bool,_GUID const &,void * *)
0x1800bee74  mov     ebx, eax
0x1800bee76  test    eax, eax
0x1800bee78  jns     short loc_1800BEE91
0x1800bee7a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bee81  jb      loc_1800BF54B
0x1800bee87  mov     edx, 0A4h
0x1800bee8c  jmp     loc_1800BEDC2
0x1800bee91  mov     rcx, [rdi+2D0h]
0x1800bee98  lea     rdx, [rbp+57h+var_B0]
0x1800bee9c  mov     rax, [rcx]
0x1800bee9f  mov     rax, [rax+98h]
0x1800beea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beeab  mov     ebx, eax
0x1800beead  test    eax, eax
0x1800beeaf  jns     short loc_1800BEEC8
0x1800beeb1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800beeb8  jb      loc_1800BF54B
0x1800beebe  mov     edx, 0A5h
0x1800beec3  jmp     loc_1800BEDC2
0x1800beec8  cmp     cs:byte_18010EC4D, 8
0x1800beecf  lea     r14, WPP_d1d2e7bb2c893df46f1284d21fd62588_Traceguids
0x1800beed6  mov     r13d, r15d
0x1800beed9  jb      short loc_1800BEF18
0x1800beedb  mov     rcx, [rbp+57h+var_A8]
0x1800beedf  mov     ebx, [rbp+57h+var_B0]
0x1800beee2  mov     rax, [rcx]
0x1800beee5  mov     rax, [rax+80h]
0x1800beeec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800beef1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800beef8  mov     edx, 0A6h
0x1800beefd  mov     dword ptr [rsp+120h+var_F8], ebx
0x1800bef01  mov     r9, rdi
0x1800bef04  mov     r8, r14
0x1800bef07  mov     [rsp+120h+var_100], rax
0x1800bef0c  mov     rcx, [rcx+0D8h]
0x1800bef13  call    WPP_SF_qqD
0x1800bef18  mov     r12d, r15d
0x1800bef1b  cmp     r12d, [rbp+57h+var_B0]
0x1800bef1f  jnb     loc_1800BF1E8
0x1800bef25  mov     rcx, [rdi+2D0h]
0x1800bef2c  lea     r8, [rsp+120h+var_E0]
0x1800bef31  mov     [rsp+120h+var_E0], r15
0x1800bef36  mov     edx, r12d
0x1800bef39  mov     [rbp+57h+var_D0], r15
0x1800bef3d  mov     [rsp+120h+var_D8], r15d
0x1800bef42  mov     rax, [rcx]
0x1800bef45  mov     [rbp+57h+var_C0], r15
0x1800bef49  mov     [rbp+57h+var_C8], r15
0x1800bef4d  mov     rax, [rax+0A0h]
0x1800bef54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bef59  mov     ebx, eax
0x1800bef5b  test    eax, eax
0x1800bef5d  js      loc_1800BF196
0x1800bef63  mov     r9d, [rdi+310h]
0x1800bef6a  lea     rax, [rbp+57h+var_C8]
0x1800bef6e  mov     r8, [rbp+57h+var_A8]
0x1800bef72  mov     rcx, rdi
0x1800bef75  mov     rdx, [rsp+120h+var_E0]
0x1800bef7a  mov     [rsp+120h+var_100], rax
0x1800bef7f  call    ?CreateInstance@SensorTransformContextSource@@SAJPEAVSensorTransform@@PEAUIFSSource@@PEAUIFSClientContextInfo@@W4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@PEAPEAV1@@Z; SensorTransformContextSource::CreateInstance(SensorTransform *,IFSSource *,IFSClientContextInfo *,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001,SensorTransformContextSource * *)
0x1800bef84  mov     ebx, eax
0x1800bef86  test    eax, eax
0x1800bef88  js      loc_1800BF186
0x1800bef8e  mov     rdx, [rbp+57h+var_C8]
0x1800bef92  lea     rcx, [rdi+2F8h]
0x1800bef99  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x1800bef9e  test    eax, eax
0x1800befa0  jz      loc_1800BF16F
0x1800befa6  mov     rcx, [rsp+120h+var_E0]
0x1800befab  lea     r9, [rbp+57h+var_D0]
0x1800befaf  lea     r8, _GUID_3c9b2eb9_86d5_4514_a394_f56664f9f0d8
0x1800befb6  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x1800befbd  mov     rax, [rcx]
0x1800befc0  mov     rax, [rax+0E0h]
0x1800befc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800befcc  mov     ebx, eax
0x1800befce  test    eax, eax
0x1800befd0  js      loc_1800BF15F
0x1800befd6  mov     rcx, [rsp+120h+var_E0]
0x1800befdb  lea     rdx, [rsp+120h+var_D8]
0x1800befe0  mov     rax, [rcx]
0x1800befe3  mov     rax, [rax+40h]
0x1800befe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800befec  mov     ebx, eax
0x1800befee  test    eax, eax
0x1800beff0  js      loc_1800BF14F
0x1800beff6  cmp     cs:byte_18010EC4D, 8
0x1800beffd  jb      short loc_1800BF02C
0x1800befff  mov     eax, [rsp+120h+var_D8]
0x1800bf003  mov     r9, rdi
0x1800bf006  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf00d  mov     dword ptr [rsp+120h+var_F0], r13d
0x1800bf012  mov     dword ptr [rsp+120h+var_F8], eax
0x1800bf016  mov     rax, [rsp+120h+var_E0]
0x1800bf01b  mov     rcx, [rcx+0D8h]
0x1800bf022  mov     [rsp+120h+var_100], rax
0x1800bf027  call    WPP_SF_qqDD
0x1800bf02c  cmp     r15d, [rsp+120h+var_D8]
0x1800bf031  jnb     loc_1800BF0BC
0x1800bf037  mov     rcx, [rsp+120h+var_E0]
0x1800bf03c  lea     r8, [rbp+57h+var_58]
0x1800bf040  mov     [rbp+57h+var_58], 0
0x1800bf048  mov     edx, r15d
0x1800bf04b  mov     [rbp+57h+var_B8], 0
0x1800bf053  mov     rax, [rcx]
0x1800bf056  mov     rax, [rax+48h]
0x1800bf05a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf05f  mov     ebx, eax
0x1800bf061  test    eax, eax
0x1800bf063  js      loc_1800BF113
0x1800bf069  mov     rdx, [rsp+120h+var_E0]; struct IFSSource *
0x1800bf06e  lea     rax, [rbp+57h+var_B8]
0x1800bf072  mov     r9d, r13d; unsigned int
0x1800bf075  mov     [rsp+120h+var_100], rax; struct SensorTransformContextStream **
0x1800bf07a  mov     r8d, r15d; unsigned int
0x1800bf07d  mov     rcx, rdi; struct SensorTransform *
0x1800bf080  call    ?CreateInstance@SensorTransformContextStream@@SAJPEAVSensorTransform@@PEAUIFSSource@@KKPEAPEAV1@@Z; SensorTransformContextStream::CreateInstance(SensorTransform *,IFSSource *,ulong,ulong,SensorTransformContextStream * *)
0x1800bf085  mov     ebx, eax
0x1800bf087  test    eax, eax
0x1800bf089  js      short loc_1800BF103
0x1800bf08b  mov     rdx, [rbp+57h+var_B8]
0x1800bf08f  lea     rcx, [rdi+2E0h]
0x1800bf096  call    ?Add@?$CTUnkArray@UIMFMediaType@@@@QEAAHPEAUIMFMediaType@@@Z; CTUnkArray<IMFMediaType>::Add(IMFMediaType *)
0x1800bf09b  test    eax, eax
0x1800bf09d  jz      short loc_1800BF0EC
0x1800bf09f  lea     rcx, [rbp+57h+var_B8]; void *
0x1800bf0a3  add     r13d, esi
0x1800bf0a6  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf0ab  lea     rcx, [rbp+57h+var_58]; void *
0x1800bf0af  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf0b4  add     r15d, esi
0x1800bf0b7  jmp     loc_1800BF02C
0x1800bf0bc  lea     rcx, [rbp+57h+var_C8]; void *
0x1800bf0c0  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf0c5  lea     rcx, [rbp+57h+var_C0]; void *
0x1800bf0c9  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf0ce  lea     rcx, [rbp+57h+var_D0]; void *
0x1800bf0d2  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf0d7  lea     rcx, [rsp+120h+var_E0]; void *
0x1800bf0dc  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf0e1  add     r12d, esi
0x1800bf0e4  xor     r15d, r15d
0x1800bf0e7  jmp     loc_1800BEF1B
0x1800bf0ec  mov     eax, 8007000Eh
0x1800bf0f1  mov     ebx, eax
0x1800bf0f3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bf0fa  jb      short loc_1800BF13B
0x1800bf0fc  mov     edx, 0AFh
0x1800bf101  jmp     short loc_1800BF121
0x1800bf103  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bf10a  jb      short loc_1800BF13B
0x1800bf10c  mov     edx, 0AEh
0x1800bf111  jmp     short loc_1800BF121
0x1800bf113  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bf11a  jb      short loc_1800BF13B
0x1800bf11c  mov     edx, 0ADh
0x1800bf121  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf128  mov     r9, rdi
0x1800bf12b  mov     r8, r14
0x1800bf12e  mov     dword ptr [rsp+120h+var_100], eax
0x1800bf132  mov     rcx, [rcx+10h]
0x1800bf136  call    WPP_SF_qD
0x1800bf13b  lea     rcx, [rbp+57h+var_B8]; void *
0x1800bf13f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf144  lea     rcx, [rbp+57h+var_58]; void *
0x1800bf148  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf14d  jmp     short loc_1800BF1BE
0x1800bf14f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bf156  jb      short loc_1800BF1BE
0x1800bf158  mov     edx, 0ABh
0x1800bf15d  jmp     short loc_1800BF1A4
0x1800bf15f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bf166  jb      short loc_1800BF1BE
0x1800bf168  mov     edx, 0AAh
0x1800bf16d  jmp     short loc_1800BF1A4
0x1800bf16f  mov     eax, 8007000Eh
0x1800bf174  mov     ebx, eax
0x1800bf176  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bf17d  jb      short loc_1800BF1BE
0x1800bf17f  mov     edx, 0A9h
0x1800bf184  jmp     short loc_1800BF1A4
0x1800bf186  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bf18d  jb      short loc_1800BF1BE
0x1800bf18f  mov     edx, 0A8h
0x1800bf194  jmp     short loc_1800BF1A4
0x1800bf196  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bf19d  jb      short loc_1800BF1BE
0x1800bf19f  mov     edx, 0A7h
0x1800bf1a4  mov     rcx, cs:WPP_GLOBAL_Control
0x1800bf1ab  mov     r9, rdi
0x1800bf1ae  mov     r8, r14
0x1800bf1b1  mov     dword ptr [rsp+120h+var_100], eax
0x1800bf1b5  mov     rcx, [rcx+10h]
0x1800bf1b9  call    WPP_SF_qD
0x1800bf1be  lea     rcx, [rbp+57h+var_C8]; void *
0x1800bf1c2  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf1c7  lea     rcx, [rbp+57h+var_C0]; void *
0x1800bf1cb  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf1d0  lea     rcx, [rbp+57h+var_D0]; void *
0x1800bf1d4  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf1d9  lea     rcx, [rsp+120h+var_E0]; void *
0x1800bf1de  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800bf1e3  jmp     loc_1800BF54B
0x1800bf1e8  mov     rcx, [rdi+288h]
0x1800bf1ef  lea     r15, [rdi+2B8h]
0x1800bf1f6  mov     r8, r15
0x1800bf1f9  lea     rdx, _GUID_2cd0bd52_bcd5_4b89_b62c_eadc0c031e7d
0x1800bf200  mov     rax, [rcx]
0x1800bf203  mov     rax, [rax]
0x1800bf206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf20b  mov     ebx, eax
0x1800bf20d  test    eax, eax
0x1800bf20f  jns     short loc_1800BF22B
0x1800bf211  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, sil; MFWppLevels g_wppLevels
0x1800bf218  jb      loc_1800BF54B
0x1800bf21e  mov     edx, 0B0h
0x1800bf223  mov     r8, r14
0x1800bf226  jmp     loc_1800BEDC9
0x1800bf22b  mov     rcx, [rdi+288h]
0x1800bf232  lea     r8, [rbp+57h+var_78]
0x1800bf236  lea     rdx, _GUID_03910848_ab16_4611_b100_17b88ae2f248
0x1800bf23d  mov     rax, [rcx]
0x1800bf240  mov     rax, [rax]
0x1800bf243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bf248  mov     ebx, eax
  ... truncated ...
```
