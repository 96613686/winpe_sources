# FSMVirtualCamera::InternalInitialize(FSMVCamCreationInfo const &,IFSMSessionIdentity *,utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &,ushort const *)

- ea: `0x18001fb2c`
- end: `0x180020a04`
- name: `?InternalInitialize@FSMVirtualCamera@@IEAAJAEBUFSMVCamCreationInfo@@PEAUIFSMSessionIdentity@@AEAV?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@PEBG@Z`
- size: `3800`
- prototype: `__int64 __usercall@<rax>(FSMVirtualCamera *this@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `34`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x18001eeb0`

## callees

- `0x180001dc0`
- `0x180002f90`
- `0x180003274`
- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x180006ae8`
- `0x180007020`
- `0x18000723c`
- `0x18000c684`
- `0x18000cffc`
- `0x18000d060`
- `0x18000d088`
- `0x18000d62c`
- `0x18000d7c4`
- `0x180011438`
- `0x180018174`
- `0x180018418`
- `0x18001e7dc`
- `0x18001ec2c`
- `0x18001fb2c`
- `0x180021c8c`
- `0x180022b18`
- `0x18002544c`
- `0x180025474`
- `0x180025b3c`
- `0x18002d084`
- `0x18002fa3c`
- `0x18002fa70`
- `0x18002fd04`
- `0x180044ce8`
- `0x180045db4`
- `0x18004633c`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020763`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020688`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020763`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020651`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180020651`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180020748`
- `api-ms-win-security-base-l1-1-0!GetSecurityDescriptorControl` at `0x180020748`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002067a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18002067a`
- `MFPlat!MFCreateAttributes` at `0x180020025`
- `MFPlat!MFCreateAttributes` at `0x180020025`

## pseudocode

```c
__int64 __fastcall FSMVirtualCamera::InternalInitialize(
        FSMVirtualCamera *this,
        __int64 a2,
        struct IFSMSessionIdentity *a3,
        __int64 a4,
        __int64 a5)
{
  __int64 v5; // r13
  int v6; // ebx
  const char *v11; // r15
  const char *v12; // rax
  FSString *v13; // rax
  const char *String; // rax
  unsigned int i; // r15d
  GuidTrace *v16; // rax
  const char *v17; // rax
  bool v18; // zf
  HRESULT FSMDeviceProperties; // eax
  signed int v20; // ebx
  __int64 v21; // rdx
  char **v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // r8
  __int64 v25; // rax
  __int64 v26; // rcx
  char *v27; // rcx
  __int128 v28; // xmm1
  __int64 v29; // rax
  __int64 v30; // rax
  char *v31; // r8
  char *v32; // r10
  __int64 v33; // rdx
  __int64 j; // r9
  __int64 v35; // rcx
  __int64 v36; // rdx
  char v37; // al
  struct IFSMCameraDeviceProperties **v38; // r15
  const struct _GUID *v39; // rcx
  const struct _GUID *v40; // rcx
  struct IFSMCameraDeviceProperties *v41; // rcx
  int v42; // eax
  __int64 v43; // rdx
  const unsigned __int8 **v44; // rsi
  const unsigned __int8 **v45; // r12
  const unsigned __int8 *v46; // rcx
  struct IFSMCameraDeviceProperties **v47; // r13
  __int64 v48; // rcx
  const unsigned __int8 **v49; // rsi
  const struct std::nothrow_t *v50; // rax
  const struct std::nothrow_t *v51; // rdx
  void *v52; // rcx
  unsigned int m; // edx
  __int64 v54; // rcx
  unsigned int v55; // r9d
  unsigned int v56; // edx
  unsigned int v57; // edx
  const struct std::nothrow_t *unique; // rax
  const struct std::nothrow_t *v59; // rdx
  void *v60; // rcx
  unsigned int v61; // eax
  unsigned int k; // edx
  __int64 v63; // rcx
  PSECURITY_DESCRIPTOR *v64; // rbx
  void *v65; // r14
  const WCHAR *v66; // rcx
  signed int LastError; // eax
  __int64 v68; // rdx
  LPCWSTR v70; // rbx
  char v71; // al
  const unsigned __int8 *v72; // rax
  struct IFSMCameraDeviceProperties *v73; // rcx
  struct IFSMCameraDeviceProperties *v74; // rcx
  struct IFSMCameraDeviceProperties *v75; // rcx
  WORD pControl; // [rsp+40h] [rbp-41h] BYREF
  DWORD dwRevision[2]; // [rsp+48h] [rbp-39h] BYREF
  LPCWSTR StringSecurityDescriptor[2]; // [rsp+50h] [rbp-31h] BYREF
  _WORD v79[8]; // [rsp+60h] [rbp-21h] BYREF
  char v80[8]; // [rsp+70h] [rbp-11h] BYREF
  __int64 v81; // [rsp+78h] [rbp-9h] BYREF
  __int64 v82[10]; // [rsp+80h] [rbp-1h] BYREF
  int v83; // [rsp+F0h] [rbp+6Fh] BYREF

  v5 = a5;
  v6 = 0;
  v83 = 255;
  v82[0] = 0;
  v81 = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 0x10u )
  {
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    {
      WPP_SF_qddS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        103,
        (_DWORD)a3,
        (_DWORD)this,
        *((_DWORD *)this + 36),
        *((_DWORD *)this + 37),
        *(_QWORD *)(a2 + 16));
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          104,
          (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          (_DWORD)this,
          *(_QWORD *)(a2 + 24));
        if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        {
          v11 = L"<nullptr>";
          v12 = L"<nullptr>";
          if ( v5 )
            v12 = (const char *)v5;
          WPP_SF_qS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            105,
            (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
            (_DWORD)this,
            (__int64)v12);
          if ( (unsigned __int8)byte_18005E5A5 >= 8u )
          {
            if ( *(_QWORD *)a4 != *(_QWORD *)(a4 + 8) )
              v11 = *(const char **)a4;
            WPP_SF_qS(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              106,
              (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
              (_DWORD)this,
              (__int64)v11);
            if ( (unsigned __int8)byte_18005E5A5 >= 8u )
            {
              v13 = FSMSessionIdentityTrace::FSMSessionIdentityTrace(
                      (FSMSessionIdentityTrace *)StringSecurityDescriptor,
                      a3);
              String = FSString::GetString(v13);
              WPP_SF_qs(
                *((_QWORD *)WPP_GLOBAL_Control + 27),
                107,
                (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
                (_DWORD)this,
                (__int64)String);
              v6 = 1;
            }
          }
        }
      }
    }
    if ( (v6 & 1) != 0 )
    {
      v6 &= ~1u;
      FSString::~FSString((FSString *)StringSecurityDescriptor, (const struct std::nothrow_t *)a2);
    }
    for ( i = 0; i < *(_DWORD *)(a2 + 40); ++i )
    {
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      {
        v6 |= 2u;
        v16 = GuidTrace::GuidTrace(
                (GuidTrace *)StringSecurityDescriptor,
                (const struct _GUID *)(*(_QWORD *)(a2 + 32) + 16LL * i));
        v17 = GuidTrace::GetString(v16);
        WPP_SF_qs(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          108,
          (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          (_DWORD)this,
          (__int64)v17);
      }
      if ( (v6 & 2) != 0 )
      {
        v6 &= ~2u;
        FSString::~FSString((FSString *)StringSecurityDescriptor, (const struct std::nothrow_t *)a2);
      }
    }
    if ( (unsigned __int8)byte_18005E5A5 >= 8u )
      WPP_SF_qqD(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        109,
        &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
        this,
        *(_QWORD *)(a2 + 48),
        *(_DWORD *)(a2 + 56));
  }
  if ( (*(unsigned __int8 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a3 + 288LL))(a3)
    || (*(unsigned __int8 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a3 + 296LL))(a3)
    || (*(unsigned __int8 (__fastcall **)(struct IFSMSessionIdentity *))(*(_QWORD *)a3 + 312LL))(a3) )
  {
    LOBYTE(pControl) = 1;
  }
  else
  {
    v18 = *((_DWORD *)this + 38) == 1;
    LOBYTE(pControl) = 0;
    if ( v18 )
    {
      FSMDeviceProperties = -2147024891;
      v20 = -2147024891;
      if ( g_wppLevels )
      {
        v21 = 110;
LABEL_186:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v21,
          &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          this,
          FSMDeviceProperties);
        goto LABEL_187;
      }
      goto LABEL_187;
    }
  }
  FSMDeviceProperties = FSMValidateVirtualCameraCreationInfo(a2);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 111;
      goto LABEL_186;
    }
LABEL_187:
    if ( !byte_18005E5A5 )
      goto LABEL_156;
    v68 = 144;
    goto LABEL_155;
  }
  v22 = (char **)((char *)this + 496);
  v23 = *((_QWORD *)this + 62);
  v24 = a4 + 16;
  *((_QWORD *)this + 62) = *(_QWORD *)a4;
  v25 = *(_QWORD *)(a4 + 8);
  *(_QWORD *)a4 = v23;
  v26 = *((_QWORD *)this + 63);
  *((_QWORD *)this + 63) = v25;
  *(_QWORD *)(a4 + 8) = v26;
  v27 = (char *)this + 512;
  v28 = *((_OWORD *)this + 32);
  *((_OWORD *)this + 32) = *(_OWORD *)(a4 + 16);
  *(_OWORD *)(a4 + 16) = v28;
  if ( *((_QWORD *)this + 62) == a4 + 16 )
  {
    v29 = *((_QWORD *)this + 63) - a4;
    *v22 = v27;
    *((_QWORD *)this + 63) = &v27[2 * ((v29 - 16) >> 1)];
  }
  if ( *(char **)a4 == v27 )
  {
    v30 = *(_QWORD *)(a4 + 8) - (_QWORD)v22;
    *(_QWORD *)a4 = v24;
    *(_QWORD *)(a4 + 8) = v24 + 2 * ((v30 - 16) >> 1);
  }
  FSMDeviceProperties = AutoSecurityAttributes::Set(
                          (FSMVirtualCamera *)((char *)this + 592),
                          L"O:SYG:SYD:(A;;GA;;;BA)(A;;GA;;;OW)(A;;GRGX;;;WD)(A;;GRGX;;;S-1-15-3-3845273463-1331427702-1186"
                           "551195-1148109977)");
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 112;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  FSMDeviceProperties = FSMCreateVirtualCameraHash(a2, v5, (char *)this + 160, 32);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 113;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  v31 = (char *)this + 160;
  if ( this == (FSMVirtualCamera *)-160LL )
  {
    FSMDeviceProperties = -2147024809;
    v20 = -2147024809;
    if ( g_wppLevels )
    {
      v21 = (unsigned int)((_DWORD)this + 274);
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  v32 = (char *)this + 192;
  LODWORD(v33) = 0;
  for ( j = 0; j != 32; ++j )
  {
    v35 = (unsigned int)v33;
    v36 = (unsigned int)(v33 + 1);
    *(_WORD *)&v32[2 * v35] = a0123456789abcd_0[(unsigned __int64)(unsigned __int8)v31[j] >> 4];
    v37 = v31[j];
    *(_WORD *)&v32[2 * v36] = a0123456789abcd_0[v37 & 0xF];
    v33 = (unsigned int)(v36 + 1);
  }
  *(_WORD *)&v32[2 * v33] = 0;
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      115,
      (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
      (_DWORD)this,
      (__int64)this + 192);
  v38 = (struct IFSMCameraDeviceProperties **)((char *)this + 536);
  v39 = (const struct _GUID *)*((_QWORD *)this + 67);
  *((_QWORD *)this + 67) = 0;
  if ( v39 )
    (*(void (__fastcall **)(const struct _GUID *))(*(_QWORD *)&v39->Data1 + 16LL))(v39);
  FSMDeviceProperties = FSMCameraDeviceProperties::CreateFSMDeviceProperties(v39, (void **)this + 67);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 116;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  v40 = (const struct _GUID *)*((_QWORD *)this + 66);
  *((_QWORD *)this + 66) = 0;
  if ( v40 )
    (*(void (__fastcall **)(const struct _GUID *))(*(_QWORD *)&v40->Data1 + 16LL))(v40);
  FSMDeviceProperties = FSMCameraDeviceProperties::CreateFSMDeviceProperties(v40, (void **)this + 66);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 117;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset((char *)this + 576);
  FSMDeviceProperties = MFCreateAttributes((IMFAttributes **)this + 72, 0);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 118;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  if ( *(_QWORD *)(a2 + 48) && *(_DWORD *)(a2 + 56) )
  {
    v41 = *v38;
    *(_QWORD *)dwRevision = 0;
    v42 = (*(__int64 (__fastcall **)(struct IFSMCameraDeviceProperties *))(*(_QWORD *)v41 + 88LL))(v41);
    v20 = v42;
    if ( v42 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_68:
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)dwRevision);
        goto LABEL_187;
      }
      v43 = 119;
LABEL_67:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v43, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v42);
      goto LABEL_68;
    }
    v42 = FSMVirtualCamera::InternalValidatePropertyCollection(this, a3, *v38);
    v20 = v42;
    if ( v42 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_68;
      v43 = 120;
      goto LABEL_67;
    }
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)dwRevision);
  }
  v44 = (const unsigned __int8 **)((char *)this + 336);
  FSMDeviceProperties = FSMVirtualCamera::InternalUpdateFriendlyName(this, a2, (char *)this + 336);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 121;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           (char *)this + 368,
                           *(_QWORD *)(a2 + 24)) )
  {
    FSMDeviceProperties = -2147024882;
    v20 = -2147024882;
    if ( g_wppLevels )
    {
      v21 = 122;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  v45 = (const unsigned __int8 **)((char *)this + 400);
  if ( v5 )
  {
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             (char *)this + 400,
                             v5) )
    {
      FSMDeviceProperties = -2147024882;
      v20 = -2147024882;
      if ( g_wppLevels )
      {
        v21 = 123;
        goto LABEL_186;
      }
      goto LABEL_187;
    }
  }
  else
  {
    v46 = *v45;
    *((_QWORD *)this + 51) = *((_QWORD *)this + 50);
    *(_WORD *)v46 = 0;
  }
  v47 = (struct IFSMCameraDeviceProperties **)((char *)this + 528);
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *((struct IFSMCameraDeviceProperties **)this + 66),
                          &DEVPKEY_DeviceInterface_IsVirtualCamera,
                          0x11u,
                          (const unsigned __int8 *)&v83,
                          1u);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 124;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *v38,
                          &DEVPKEY_DeviceInterface_IsVirtualCamera,
                          0x11u,
                          (const unsigned __int8 *)&v83,
                          1u);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 125;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *v47,
                          &DEVPKEY_DeviceInterface_FriendlyName,
                          0x12u,
                          *v44,
                          2 * ((__int64)(*((_QWORD *)this + 43) - *((_QWORD *)this + 42)) >> 1) + 2);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 126;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *v38,
                          &DEVPKEY_DeviceInterface_FriendlyName,
                          0x12u,
                          *v44,
                          2 * ((__int64)(*((_QWORD *)this + 43) - *((_QWORD *)this + 42)) >> 1) + 2);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 127;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *v47,
                          &DEVPKEY_DeviceInterface_FrameServerUniqueID,
                          0x1003u,
                          (const unsigned __int8 *)this + 160,
                          0x20u);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 128;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *v38,
                          &DEVPKEY_DeviceInterface_FrameServerUniqueID,
                          0x1003u,
                          (const unsigned __int8 *)this + 160,
                          0x20u);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 129;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  v48 = *(_QWORD *)(a2 + 32);
  if ( v48 )
  {
    v55 = *(_DWORD *)(a2 + 40);
    v56 = 0;
    if ( v55 )
    {
      while ( *(_QWORD *)(v48 + 16LL * v56) != *(_QWORD *)&GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8.Data1
           || *(_QWORD *)(v48 + 16LL * v56 + 8) != *(_QWORD *)GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8.Data4 )
      {
        if ( ++v56 >= v55 )
          goto LABEL_115;
      }
      FSMDeviceProperties = -2147024809;
      v20 = -2147024809;
      if ( !g_wppLevels )
        goto LABEL_187;
      v21 = 131;
      goto LABEL_186;
    }
LABEL_115:
    if ( !(_BYTE)pControl )
    {
      v57 = 0;
      if ( v55 )
      {
        while ( 1 )
        {
          v45 = (const unsigned __int8 **)((char *)this + 400);
          if ( (*(_QWORD *)(v48 + 16LL * v57) != *(_QWORD *)&GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data1
             || *(_QWORD *)(v48 + 16LL * v57 + 8) != *(_QWORD *)GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data4)
            && (*(_QWORD *)(v48 + 16LL * v57) != *(_QWORD *)&GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca.Data1
             || *(_QWORD *)(v48 + 16LL * v57 + 8) != *(_QWORD *)GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca.Data4)
            && (*(_QWORD *)(v48 + 16LL * v57) != *(_QWORD *)&GUID_6994ad05_93ef_11d0_a3cc_00a0c9223196.Data1
             || *(_QWORD *)(v48 + 16LL * v57 + 8) != *(_QWORD *)GUID_6994ad05_93ef_11d0_a3cc_00a0c9223196.Data4) )
          {
            v38 = (struct IFSMCameraDeviceProperties **)((char *)this + 536);
            if ( *(_QWORD *)(v48 + 16LL * v57) != *(_QWORD *)&GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196.Data1
              || (v45 = (const unsigned __int8 **)((char *)this + 400),
                  *(_QWORD *)(v48 + 16LL * v57 + 8) != *(_QWORD *)GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196.Data4) )
            {
              v55 = *(_DWORD *)(a2 + 40);
              if ( *(_QWORD *)(v48 + 16LL * v57) != KSCATEGORY_DSHOWREVERSE_MFBRIDGE
                || *(_QWORD *)(v48 + 16LL * v57 + 8) != 0x3728D0F7397ACCB6LL )
              {
                break;
              }
            }
          }
          if ( ++v57 >= v55 )
          {
            v47 = (struct IFSMCameraDeviceProperties **)((char *)this + 528);
            goto LABEL_129;
          }
        }
        FSMDeviceProperties = -2147024891;
        v20 = -2147024891;
        if ( !g_wppLevels )
          goto LABEL_187;
        v21 = 132;
        goto LABEL_186;
      }
    }
LABEL_129:
    *((_DWORD *)this + 110) = v55 + 1;
    v49 = (const unsigned __int8 **)((char *)this + 432);
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<_GUID [0]>(dwRevision, v55 + 1);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=(
      (void **)this + 54,
      unique);
    v60 = *(void **)dwRevision;
    *(_QWORD *)dwRevision = 0;
    if ( v60 )
      operator delete(v60, v59);
    if ( !*v49 )
    {
      FSMDeviceProperties = -2147024882;
      v20 = -2147024882;
      if ( g_wppLevels )
      {
        v21 = 133;
        goto LABEL_186;
      }
      goto LABEL_187;
    }
    v61 = *(_DWORD *)(a2 + 40);
    for ( k = 0; k < v61; v61 = *(_DWORD *)(a2 + 40) )
    {
      v63 = k++;
      *(_OWORD *)&(*v49)[16 * v63] = *(_OWORD *)(*(_QWORD *)(a2 + 32) + 16 * v63);
    }
    *(GUID *)&(*v49)[16 * v61] = GUID_588c8d20_c0e3_4fd3_b511_8f2f692156f8;
  }
  else
  {
    *((_DWORD *)this + 110) = 4;
    v49 = (const unsigned __int8 **)((char *)this + 432);
    v50 = (const struct std::nothrow_t *)wil::make_unique_nothrow<_GUID [0]>(dwRevision, 4u);
    wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::operator=((void **)this + 54, v50);
    v52 = *(void **)dwRevision;
    *(_QWORD *)dwRevision = 0;
    if ( v52 )
      operator delete(v52, v51);
    if ( !*v49 )
    {
      FSMDeviceProperties = -2147024882;
      v20 = -2147024882;
      if ( g_wppLevels )
      {
        v21 = 130;
        goto LABEL_186;
      }
      goto LABEL_187;
    }
    for ( m = 0; m < *((_DWORD *)this + 110); *(_OWORD *)&(*v49)[16 * v54] = xmmword_180053B20[v54] )
      v54 = m++;
  }
  if ( *v45 != v45[1] )
  {
    StringSecurityDescriptor[0] = v79;
    StringSecurityDescriptor[1] = v79;
    v79[0] = 0;
    pControl = 0;
    dwRevision[0] = 0;
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                             StringSecurityDescriptor,
                             L"O:SYG:SYD:(A;;0x00010001;;;SY)(A;;0x00000001;;;S-1-15-2-1)(A;;0x00010001;;;S-1-5-80-3915894"
                              "004-2104103821-3047269622-1811662266-774708259)(A;;0x00010001;;;",
                             155)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             StringSecurityDescriptor,
                             *v45)
      || !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::append(
                             StringSecurityDescriptor,
                             L")",
                             1) )
    {
      v20 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          134,
          &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          this,
          -2147024882);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)StringSecurityDescriptor);
      goto LABEL_187;
    }
    v64 = (PSECURITY_DESCRIPTOR *)((char *)this + 448);
    v65 = (void *)*((_QWORD *)this + 56);
    if ( v65 )
    {
      wil::last_error_context::last_error_context((wil::last_error_context *)v80);
      LocalFree(v65);
      wil::last_error_context::~last_error_context((wil::last_error_context *)v80);
    }
    v66 = StringSecurityDescriptor[0];
    *v64 = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            v66,
            1u,
            (PSECURITY_DESCRIPTOR *)this + 56,
            (PULONG)this + 114) )
    {
      LastError = GetLastError();
      v20 = LastError;
      if ( LastError > 0 )
        v20 = (unsigned __int16)LastError | 0x80070000;
      if ( byte_18005E5A5 )
        WPP_SF_qDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          135,
          (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          (_DWORD)this,
          v20,
          (__int64)StringSecurityDescriptor[0]);
      utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)StringSecurityDescriptor);
      if ( v20 < 0 )
        goto LABEL_187;
      goto LABEL_153;
    }
    if ( GetSecurityDescriptorControl(*v64, &pControl, dwRevision) )
    {
      if ( (unsigned __int8)byte_18005E5A5 >= 8u )
        WPP_SF_qDDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          137,
          (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
          (_DWORD)this,
          pControl,
          dwRevision[0],
          (__int64)StringSecurityDescriptor[0]);
    }
    else if ( byte_18005E5A5 )
    {
      v70 = StringSecurityDescriptor[0];
      v71 = GetLastError();
      WPP_SF_qDS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        136,
        (unsigned int)&WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids,
        (_DWORD)this,
        v71,
        (__int64)v70);
    }
    utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::_Uninit((void **)StringSecurityDescriptor);
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *v38,
                          &DEVPKEY_DeviceInterface_FSM_VirtualCamera_Categories,
                          0x1003u,
                          *v49,
                          16LL * *((unsigned int *)this + 110));
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 138;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          *v38,
                          &DEVPKEY_DeviceInterface_FSM_VirtualCamera_SourceId,
                          0x12u,
                          *((const unsigned __int8 **)this + 46),
                          2 * ((__int64)(*((_QWORD *)this + 47) - *((_QWORD *)this + 46)) >> 1) + 2);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 139;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  v72 = v45[1];
  v73 = *v38;
  if ( *v45 == v72 )
  {
    (*(void (__fastcall **)(struct IFSMCameraDeviceProperties *, const DEVPROPKEY *))(*(_QWORD *)v73 + 72LL))(
      v73,
      &DEVPKEY_DeviceInterface_FSM_VirtualCamera_UserSidString);
  }
  else
  {
    FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                            v73,
                            &DEVPKEY_DeviceInterface_FSM_VirtualCamera_UserSidString,
                            0x12u,
                            *v45,
                            2 * ((v72 - *v45) >> 1) + 2);
    v20 = FSMDeviceProperties;
    if ( FSMDeviceProperties < 0 )
    {
      if ( g_wppLevels )
      {
        v21 = 140;
        goto LABEL_186;
      }
      goto LABEL_187;
    }
  }
  v74 = *v38;
  LOBYTE(pControl) = -1;
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          v74,
                          &DEVPKEY_DeviceInterface_CameraSettings_Configured,
                          0x11u,
                          (const unsigned __int8 *)&pControl,
                          1u);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 141;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  v75 = *v47;
  LOBYTE(pControl) = -1;
  FSMDeviceProperties = FSMVirtualCamera::AddPropertyToCollection(
                          v75,
                          &DEVPKEY_DeviceInterface_CameraSettings_Configured,
                          0x11u,
                          (const unsigned __int8 *)&pControl,
                          1u);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 142;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
  FSMDeviceProperties = (*(__int64 (__fastcall **)(FSMVirtualCamera *, char *, _QWORD))(*(_QWORD *)this + 8LL))(
                          this,
                          (char *)this + 192,
                          0);
  v20 = FSMDeviceProperties;
  if ( FSMDeviceProperties < 0 )
  {
    if ( g_wppLevels )
    {
      v21 = 143;
      goto LABEL_186;
    }
    goto LABEL_187;
  }
LABEL_153:
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v68 = 145;
LABEL_155:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v68, &WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids, this, v20);
  }
LABEL_156:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v81);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v82);
  return (unsigned int)v20;
}

```

## disassembly

```asm
0x18001fb2c  push    rbp
0x18001fb2e  push    rbx
0x18001fb2f  push    rsi
0x18001fb30  push    rdi
0x18001fb31  push    r12
0x18001fb33  push    r13
0x18001fb35  push    r14
0x18001fb37  push    r15
0x18001fb39  lea     rbp, [rsp-17h]
0x18001fb3e  sub     rsp, 98h
0x18001fb45  mov     r13, [rbp+4Fh+arg_20]
0x18001fb49  lea     r15, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001fb50  xor     ebx, ebx
0x18001fb52  mov     rsi, r9
0x18001fb55  mov     [rbp+4Fh+arg_10], ebx
0x18001fb58  mov     r12, r8
0x18001fb5b  mov     al, cs:byte_18005E5A5
0x18001fb61  mov     r14, rdx
0x18001fb64  mov     [rbp+4Fh+var_50], rbx
0x18001fb68  mov     rdi, rcx
0x18001fb6b  mov     [rbp+4Fh+var_58], rbx
0x18001fb6f  mov     byte ptr [rbp+4Fh+arg_10], 0FFh
0x18001fb73  cmp     al, 10h
0x18001fb75  jb      loc_18001FD6F
0x18001fb7b  cmp     al, 8
0x18001fb7d  jb      loc_18001FCAD
0x18001fb83  mov     rax, [r14+10h]
0x18001fb87  lea     edx, [rbx+67h]
0x18001fb8a  mov     [rsp+0D0h+var_A0], rax
0x18001fb8f  mov     r9, rcx
0x18001fb92  mov     eax, [rcx+94h]
0x18001fb98  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18001fb9c  mov     eax, [rcx+90h]
0x18001fba2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fba9  mov     dword ptr [rsp+0D0h+var_B0], eax
0x18001fbad  mov     rcx, [rcx+0D8h]
0x18001fbb4  call    WPP_SF_qddS
0x18001fbb9  cmp     cs:byte_18005E5A5, 8
0x18001fbc0  jb      loc_18001FCAD
0x18001fbc6  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbcd  lea     edx, [rbx+68h]
0x18001fbd0  mov     rax, [r14+18h]
0x18001fbd4  mov     r9, rdi
0x18001fbd7  mov     r8, r15
0x18001fbda  mov     [rsp+0D0h+var_B0], rax
0x18001fbdf  mov     rcx, [rcx+0D8h]
0x18001fbe6  call    WPP_SF_qS
0x18001fbeb  cmp     cs:byte_18005E5A5, 8
0x18001fbf2  jb      loc_18001FCAD
0x18001fbf8  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fbff  lea     r15, aNullptr; "<nullptr>"
0x18001fc06  test    r13, r13
0x18001fc09  lea     edx, [rbx+69h]
0x18001fc0c  mov     rax, r15
0x18001fc0f  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001fc16  cmovnz  rax, r13
0x18001fc1a  mov     r9, rdi
0x18001fc1d  mov     rcx, [rcx+0D8h]
0x18001fc24  mov     [rsp+0D0h+var_B0], rax
0x18001fc29  call    WPP_SF_qS
0x18001fc2e  cmp     cs:byte_18005E5A5, 8
0x18001fc35  jb      short loc_18001FCAD
0x18001fc37  mov     rax, [rsi]
0x18001fc3a  lea     edx, [rbx+6Ah]
0x18001fc3d  cmp     rax, [rsi+8]
0x18001fc41  mov     r9, rdi
0x18001fc44  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc4b  cmovnz  r15, rax
0x18001fc4f  mov     [rsp+0D0h+var_B0], r15
0x18001fc54  lea     r15, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001fc5b  mov     r8, r15
0x18001fc5e  mov     rcx, [rcx+0D8h]
0x18001fc65  call    WPP_SF_qS
0x18001fc6a  cmp     cs:byte_18005E5A5, 8
0x18001fc71  jb      short loc_18001FCAD
0x18001fc73  mov     rdx, r12; struct IFSMSessionIdentity *
0x18001fc76  lea     rcx, [rbp+4Fh+StringSecurityDescriptor]; this
0x18001fc7a  call    ??0FSMSessionIdentityTrace@@QEAA@PEAUIFSMSessionIdentity@@@Z; FSMSessionIdentityTrace::FSMSessionIdentityTrace(IFSMSessionIdentity *)
0x18001fc7f  mov     rcx, rax; this
0x18001fc82  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18001fc87  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fc8e  lea     edx, [rbx+6Bh]
0x18001fc91  mov     r9, rdi
0x18001fc94  mov     [rsp+0D0h+var_B0], rax
0x18001fc99  mov     r8, r15
0x18001fc9c  mov     rcx, [rcx+0D8h]
0x18001fca3  call    WPP_SF_qs
0x18001fca8  mov     ebx, 1
0x18001fcad  test    bl, 1
0x18001fcb0  jz      short loc_18001FCBE
0x18001fcb2  and     ebx, 0FFFFFFFEh
0x18001fcb5  lea     rcx, [rbp+4Fh+StringSecurityDescriptor]; this
0x18001fcb9  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18001fcbe  xor     r15d, r15d
0x18001fcc1  cmp     [r14+28h], r15d
0x18001fcc5  jbe     short loc_18001FD30
0x18001fcc7  cmp     cs:byte_18005E5A5, 8
0x18001fcce  jb      short loc_18001FD16
0x18001fcd0  mov     edx, r15d
0x18001fcd3  lea     rcx, [rbp+4Fh+StringSecurityDescriptor]; this
0x18001fcd7  shl     rdx, 4
0x18001fcdb  or      ebx, 2
0x18001fcde  add     rdx, [r14+20h]; struct _GUID *
0x18001fce2  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x18001fce7  mov     rcx, rax; this
0x18001fcea  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x18001fcef  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fcf6  lea     r8, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001fcfd  mov     edx, 6Ch ; 'l'
0x18001fd02  mov     [rsp+0D0h+var_B0], rax
0x18001fd07  mov     r9, rdi
0x18001fd0a  mov     rcx, [rcx+0D8h]
0x18001fd11  call    WPP_SF_qs
0x18001fd16  test    bl, 2
0x18001fd19  jz      short loc_18001FD27
0x18001fd1b  and     ebx, 0FFFFFFFDh
0x18001fd1e  lea     rcx, [rbp+4Fh+StringSecurityDescriptor]; this
0x18001fd22  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18001fd27  inc     r15d
0x18001fd2a  cmp     r15d, [r14+28h]
0x18001fd2e  jb      short loc_18001FCC7
0x18001fd30  cmp     cs:byte_18005E5A5, 8
0x18001fd37  lea     r15, WPP_faa60a456d7f3bb042585fb2bc27ef15_Traceguids
0x18001fd3e  jb      short loc_18001FD6F
0x18001fd40  mov     eax, [r14+38h]
0x18001fd44  mov     edx, 6Dh ; 'm'
0x18001fd49  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd50  mov     r9, rdi
0x18001fd53  mov     dword ptr [rsp+0D0h+var_A8], eax
0x18001fd57  mov     r8, r15
0x18001fd5a  mov     rax, [r14+30h]
0x18001fd5e  mov     [rsp+0D0h+var_B0], rax
0x18001fd63  mov     rcx, [rcx+0D8h]
0x18001fd6a  call    WPP_SF_qqD
0x18001fd6f  mov     rax, [r12]
0x18001fd73  mov     rcx, r12
0x18001fd76  mov     rax, [rax+120h]
0x18001fd7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd82  test    al, al
0x18001fd84  jnz     short loc_18001FDE1
0x18001fd86  mov     rax, [r12]
0x18001fd8a  mov     rcx, r12
0x18001fd8d  mov     rax, [rax+128h]
0x18001fd94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fd99  test    al, al
0x18001fd9b  jnz     short loc_18001FDE1
0x18001fd9d  mov     rax, [r12]
0x18001fda1  mov     rcx, r12
0x18001fda4  mov     rax, [rax+138h]
0x18001fdab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001fdb0  test    al, al
0x18001fdb2  jnz     short loc_18001FDE1
0x18001fdb4  cmp     dword ptr [rdi+98h], 1
0x18001fdbb  mov     byte ptr [rbp+4Fh+pControl], al
0x18001fdbe  jnz     short loc_18001FDE5
0x18001fdc0  mov     eax, 80070005h
0x18001fdc5  mov     ebx, eax
0x18001fdc7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001fdce  jb      loc_1800209ED
0x18001fdd4  mov     edx, 6Eh ; 'n'
0x18001fdd9  mov     r8, r15
0x18001fddc  jmp     loc_1800209D6
0x18001fde1  mov     byte ptr [rbp+4Fh+pControl], 1
0x18001fde5  mov     rcx, r14
0x18001fde8  call    FSMValidateVirtualCameraCreationInfo
0x18001fded  mov     ebx, eax
0x18001fdef  test    eax, eax
0x18001fdf1  jns     short loc_18001FE07
0x18001fdf3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001fdfa  jb      loc_1800209ED
0x18001fe00  mov     edx, 6Fh ; 'o'
0x18001fe05  jmp     short loc_18001FDD9
0x18001fe07  mov     rax, [rsi]
0x18001fe0a  lea     rdx, [rdi+1F0h]
0x18001fe11  mov     rcx, [rdx]
0x18001fe14  lea     r8, [rsi+10h]
0x18001fe18  mov     [rdx], rax
0x18001fe1b  mov     rax, [rsi+8]
0x18001fe1f  mov     [rsi], rcx
0x18001fe22  mov     rcx, [rdx+8]
0x18001fe26  mov     [rdx+8], rax
0x18001fe2a  mov     [rsi+8], rcx
0x18001fe2e  lea     rcx, [rdx+10h]
0x18001fe32  movups  xmm0, xmmword ptr [r8]
0x18001fe36  movups  xmm1, xmmword ptr [rcx]
0x18001fe39  movdqu  xmmword ptr [rcx], xmm0
0x18001fe3d  movdqu  xmmword ptr [r8], xmm1
0x18001fe42  cmp     [rdx], r8
0x18001fe45  jnz     short loc_18001FE60
0x18001fe47  mov     rax, [rdx+8]
0x18001fe4b  sub     rax, rsi
0x18001fe4e  mov     [rdx], rcx
0x18001fe51  sub     rax, 10h
0x18001fe55  sar     rax, 1
0x18001fe58  lea     rax, [rcx+rax*2]
0x18001fe5c  mov     [rdx+8], rax
0x18001fe60  cmp     [rsi], rcx
0x18001fe63  jnz     short loc_18001FE7E
0x18001fe65  mov     rax, [rsi+8]
0x18001fe69  sub     rax, rdx
0x18001fe6c  mov     [rsi], r8
0x18001fe6f  sub     rax, 10h
0x18001fe73  sar     rax, 1
0x18001fe76  lea     rax, [r8+rax*2]
0x18001fe7a  mov     [rsi+8], rax
0x18001fe7e  lea     rcx, [rdi+250h]; this
0x18001fe85  lea     rdx, aOSygSydAGaBaAG; "O:SYG:SYD:(A;;GA;;;BA)(A;;GA;;;OW)(A;;G"...
0x18001fe8c  call    ?Set@AutoSecurityAttributes@@QEAAJPEBG@Z; AutoSecurityAttributes::Set(ushort const *)
0x18001fe91  xor     esi, esi
0x18001fe93  mov     ebx, eax
0x18001fe95  test    eax, eax
0x18001fe97  jns     short loc_18001FEAE
0x18001fe99  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001fea0  jb      loc_1800209ED
0x18001fea6  lea     edx, [rsi+70h]
0x18001fea9  jmp     loc_18001FDD9
0x18001feae  lea     r8, [rdi+0A0h]
0x18001feb5  mov     r9d, 20h ; ' '
0x18001febb  mov     rdx, r13
0x18001febe  mov     rcx, r14
0x18001fec1  call    FSMCreateVirtualCameraHash
0x18001fec6  mov     ebx, eax
0x18001fec8  test    eax, eax
0x18001feca  jns     short loc_18001FEE3
0x18001fecc  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001fed3  jb      loc_1800209ED
0x18001fed9  mov     edx, 71h ; 'q'
0x18001fede  jmp     loc_18001FDD9
0x18001fee3  lea     r8, [rdi+0A0h]
0x18001feea  test    r8, r8
0x18001feed  jnz     short loc_18001FF0C
0x18001feef  mov     eax, 80070057h
0x18001fef4  mov     ebx, eax
0x18001fef6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001fefd  jb      loc_1800209ED
0x18001ff03  lea     edx, [r8+72h]
0x18001ff07  jmp     loc_18001FDD9
0x18001ff0c  lea     r10, [rdi+0C0h]
0x18001ff13  mov     edx, esi
0x18001ff15  mov     r9, rsi
0x18001ff18  lea     r11, __ImageBase
0x18001ff1f  movzx   eax, byte ptr [r9+r8]
0x18001ff24  shr     rax, 4
0x18001ff28  mov     ecx, edx
0x18001ff2a  inc     edx
0x18001ff2c  movzx   eax, word ptr ds:rva a0123456789abcd_0[r11+rax*2]; "0123456789ABCDEF" ...
0x18001ff35  mov     [r10+rcx*2], ax
0x18001ff3a  movzx   eax, byte ptr [r9+r8]
0x18001ff3f  inc     r9
0x18001ff42  and     eax, 0Fh
0x18001ff45  movzx   eax, word ptr ds:rva a0123456789abcd_0[r11+rax*2]; "0123456789ABCDEF" ...
0x18001ff4e  mov     [r10+rdx*2], ax
0x18001ff53  inc     edx
0x18001ff55  cmp     r9, 20h ; ' '
0x18001ff59  jnz     short loc_18001FF1F
0x18001ff5b  mov     [r10+rdx*2], si
0x18001ff60  cmp     cs:byte_18005E5A5, 8
0x18001ff67  jb      short loc_18001FF8B
0x18001ff69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff70  lea     edx, [r9+53h]
0x18001ff74  mov     r9, rdi
0x18001ff77  mov     [rsp+0D0h+var_B0], r10
0x18001ff7c  mov     r8, r15
0x18001ff7f  mov     rcx, [rcx+0D8h]
0x18001ff86  call    WPP_SF_qS
0x18001ff8b  lea     r15, [rdi+218h]
0x18001ff92  mov     rcx, [r15]
0x18001ff95  mov     [r15], rsi
0x18001ff98  test    rcx, rcx
0x18001ff9b  jz      short loc_18001FFA9
0x18001ff9d  mov     rax, [rcx]
0x18001ffa0  mov     rax, [rax+10h]
0x18001ffa4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffa9  mov     rdx, r15; void **
0x18001ffac  call    ?CreateFSMDeviceProperties@FSMCameraDeviceProperties@@SAJAEBU_GUID@@PEAPEAX@Z; FSMCameraDeviceProperties::CreateFSMDeviceProperties(_GUID const &,void * *)
0x18001ffb1  mov     ebx, eax
0x18001ffb3  test    eax, eax
0x18001ffb5  jns     short loc_18001FFCE
0x18001ffb7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18001ffbe  jb      loc_1800209ED
0x18001ffc4  mov     edx, 74h ; 't'
0x18001ffc9  jmp     loc_1800209CF
0x18001ffce  lea     rbx, [rdi+210h]
0x18001ffd5  mov     rcx, [rbx]
0x18001ffd8  mov     [rbx], rsi
0x18001ffdb  test    rcx, rcx
0x18001ffde  jz      short loc_18001FFEC
0x18001ffe0  mov     rax, [rcx]
0x18001ffe3  mov     rax, [rax+10h]
0x18001ffe7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ffec  mov     rdx, rbx; void **
0x18001ffef  call    ?CreateFSMDeviceProperties@FSMCameraDeviceProperties@@SAJAEBU_GUID@@PEAPEAX@Z; FSMCameraDeviceProperties::CreateFSMDeviceProperties(_GUID const &,void * *)
0x18001fff4  mov     ebx, eax
0x18001fff6  test    eax, eax
0x18001fff8  jns     short loc_180020011
0x18001fffa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180020001  jb      loc_1800209ED
0x180020007  mov     edx, 75h ; 'u'
0x18002000c  jmp     loc_1800209CF
0x180020011  lea     rbx, [rdi+240h]
  ... truncated ...
```
