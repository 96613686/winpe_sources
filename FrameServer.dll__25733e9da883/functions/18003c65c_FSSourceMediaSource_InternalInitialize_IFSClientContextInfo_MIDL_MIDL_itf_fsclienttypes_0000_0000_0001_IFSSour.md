# FSSourceMediaSource::InternalInitialize(IFSClientContextInfo *,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001,IFSSource *,IFSSource *,FSSourceActivate *)

- ea: `0x18003c65c`
- end: `0x18003d187`
- name: `?InternalInitialize@FSSourceMediaSource@@IEAAJPEAUIFSClientContextInfo@@W4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@PEAUIFSSource@@2PEAVFSSourceActivate@@@Z`
- size: `2859`
- prototype: ``
- caller_count: `1`
- callee_count: `21`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18003bac8`

## callees

- `0x1800041f0`
- `0x18000478c`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x18000a880`
- `0x18000a91c`
- `0x18000ad10`
- `0x180017f60`
- `0x18001807c`
- `0x180018998`
- `0x180024200`
- `0x18003b578`
- `0x18003c65c`
- `0x180040bcc`
- `0x1800416dc`
- `0x18004d714`
- `0x18004d748`
- `0x18004f37c`
- `0x18007bc34`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d145`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18003d145`
- `MFPlat!MFCreateAttributes` at `0x18003c8c5`
- `MFPlat!MFCreateAttributes` at `0x18003c8c5`
- `MFPlat!MFCreateEventQueue` at `0x18003cc92`
- `MFPlat!MFCreateEventQueue` at `0x18003cc92`
- `MFPlat!MFCreatePresentationDescriptor` at `0x18003cf9f`
- `MFPlat!MFCreatePresentationDescriptor` at `0x18003cf9f`

## pseudocode

```c
__int64 __fastcall FSSourceMediaSource::InternalInitialize(
        struct FSSourceMediaSource *a1,
        struct IFSClientContextInfo *a2,
        int a3,
        struct IFSSource *a4,
        __int64 a5,
        _QWORD *a6)
{
  char v9; // r14
  IMFStreamDescriptor **v10; // r13
  FSString *v11; // rax
  const char *String; // rax
  const char *v13; // rax
  __int64 v14; // r12
  __int64 v15; // rax
  int (__fastcall *v16)(struct IFSSource *, void **); // rbx
  const wchar_t *v17; // rdi
  const wchar_t *v18; // rax
  int (__fastcall *v19)(__int64, void **); // rbx
  int FSSourceExtendedCameraController; // eax
  int v21; // edi
  __int64 v22; // rdx
  _QWORD *v23; // r13
  HRESULT v24; // eax
  __int64 v25; // rdx
  __int64 v26; // rdx
  _QWORD *v27; // rbx
  __int64 v28; // rax
  __int64 (__fastcall *v29)(struct IFSSource *, __int64 *); // rbx
  int v30; // eax
  __int64 v31; // rax
  __int64 (__fastcall *v32)(struct IFSSource *, void **); // rbx
  int v33; // eax
  __int64 v34; // rdx
  __int64 v35; // rdi
  __int64 (__fastcall *v36)(__int64, const IID *, __int64); // rbx
  __int64 v37; // rax
  int v38; // edi
  int v39; // eax
  struct IFSClientContextInfo **v40; // r13
  int v41; // ebx
  int v42; // r9d
  struct IFSClientContextInfo *v43; // rdx
  const struct std::nothrow_t *v44; // rdx
  FSString *v45; // rax
  const char *v46; // rax
  FSString *v47; // rax
  const char *v48; // rax
  const struct std::nothrow_t *unique; // rax
  const struct std::nothrow_t *v50; // rdx
  void *v51; // rcx
  void (__fastcall *v52)(__int64, struct IFSSourceIdentity **); // rbx
  __int64 v53; // rax
  __int64 (__fastcall *v54)(struct IFSSource *, IMFStreamDescriptor ***); // rbx
  int v55; // eax
  __int64 v56; // rdx
  __int64 v57; // r14
  struct IFSClientContextInfo *v58; // r8
  int FSSourceMediaStream; // eax
  IMFStreamDescriptor **v60; // rbx
  HRESULT v61; // eax
  __int64 v62; // rdx
  __int64 v63; // rdx
  __int64 (__fastcall *v64)(struct FSSourceMediaSource *, GUID *, __int64 *); // rbx
  DWORD v65; // eax
  __int64 i; // rbx
  IMFStreamDescriptor *v67; // rcx
  const struct std::nothrow_t *v68; // rdx
  int v70; // [rsp+28h] [rbp-59h]
  IMFStreamDescriptor **apStreamDescriptors; // [rsp+38h] [rbp-49h] BYREF
  void *v72; // [rsp+40h] [rbp-41h] BYREF
  struct IFSSourceIdentity *v73; // [rsp+48h] [rbp-39h] BYREF
  __int64 v74; // [rsp+50h] [rbp-31h] BYREF
  __int64 v75; // [rsp+58h] [rbp-29h] BYREF
  _BYTE v76[24]; // [rsp+60h] [rbp-21h] BYREF
  PROPVARIANT pvar[2]; // [rsp+78h] [rbp-9h] BYREF
  __int64 v78; // [rsp+88h] [rbp+7h]
  DWORD cStreamDescriptors; // [rsp+D8h] [rbp+57h] BYREF
  struct IFSClientContextInfo *v80; // [rsp+E0h] [rbp+5Fh]
  int v81; // [rsp+E8h] [rbp+67h]

  v81 = a3;
  v80 = a2;
  v78 = 0;
  cStreamDescriptors = 0;
  apStreamDescriptors = 0;
  v9 = 0;
  v75 = 0;
  v10 = 0;
  v74 = 0;
  *(_OWORD *)pvar = 0;
  v73 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v11 = ClientContextInfoTrace::ClientContextInfoTrace((ClientContextInfoTrace *)v76, a2);
    String = FSString::GetString(v11);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      183,
      (unsigned int)&WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
      (_DWORD)a1,
      (__int64)String);
    v9 = 1;
  }
  if ( (v9 & 1) != 0 )
  {
    v9 &= ~1u;
    FSString::~FSString((FSString *)v76, a2);
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v13 = "shared";
    if ( a3 != 1 )
      v13 = "controlling";
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      184,
      (unsigned int)&WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
      (_DWORD)a1,
      (__int64)v13);
  }
  v14 = a5;
  if ( (unsigned __int8)byte_18010EC4D >= 0x10u )
  {
    v15 = *(_QWORD *)a4;
    v72 = 0;
    v16 = *(int (__fastcall **)(struct IFSSource *, void **))(v15 + 48);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v72);
    v17 = L"<nullptr";
    if ( v16(a4, &v72) >= 0 && (unsigned __int8)byte_18010EC4D >= 8u )
    {
      if ( (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v72 + 40LL))(v72) )
        v18 = (const wchar_t *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v72 + 40LL))(v72);
      else
        v18 = L"<nullptr";
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        185,
        (unsigned int)&WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
        (_DWORD)a1,
        (__int64)v18);
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v72);
    if ( v14 )
    {
      v19 = *(int (__fastcall **)(__int64, void **))(*(_QWORD *)v14 + 48LL);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v72);
      if ( v19(v14, &v72) >= 0 && (unsigned __int8)byte_18010EC4D >= 8u )
      {
        if ( (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v72 + 40LL))(v72) )
          v17 = (const wchar_t *)(*(__int64 (__fastcall **)(void *))(*(_QWORD *)v72 + 40LL))(v72);
        WPP_SF_qS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          186,
          (unsigned int)&WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
          (_DWORD)a1,
          (__int64)v17);
      }
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v72);
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)a1 + 232);
  FSSourceExtendedCameraController = FSSourceExtendedCameraController::CreateFSSourceExtendedCameraController(
                                       a4,
                                       (struct FSSourceExtendedCameraController **)a1 + 29);
  v21 = FSSourceExtendedCameraController;
  if ( FSSourceExtendedCameraController < 0 )
  {
    if ( g_wppLevels )
    {
      v22 = 187;
LABEL_90:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v22,
        &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
        a1,
        FSSourceExtendedCameraController);
      goto LABEL_31;
    }
    goto LABEL_31;
  }
  v23 = (_QWORD *)((char *)a1 + 136);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)a1 + 136);
  v24 = MFCreateAttributes((IMFAttributes **)a1 + 17, 0);
  v21 = v24;
  if ( v24 < 0 )
  {
    if ( !g_wppLevels )
    {
LABEL_30:
      v10 = apStreamDescriptors;
      goto LABEL_31;
    }
    v25 = 188;
LABEL_29:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v25, &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids, a1, v24);
    goto LABEL_30;
  }
  v27 = a6;
  if ( !a6 )
  {
    v31 = *(_QWORD *)a4;
    v72 = 0;
    v32 = *(__int64 (__fastcall **)(struct IFSSource *, void **))(v31 + 48);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v72);
    v33 = v32(a4, &v72);
    v21 = v33;
    if ( v33 >= 0 )
    {
      v33 = (*(__int64 (__fastcall **)(_QWORD, const IID *, const IID *))(*(_QWORD *)*v23 + 192LL))(
              *v23,
              &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE,
              &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID);
      v21 = v33;
      if ( v33 < 0 )
      {
        if ( !g_wppLevels )
          goto LABEL_51;
        v34 = 194;
        goto LABEL_50;
      }
      v35 = *v23;
      v36 = *(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)*v23 + 200LL);
      v37 = (*(__int64 (__fastcall **)(void *))(*(_QWORD *)v72 + 40LL))(v72);
      v33 = v36(v35, &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK, v37);
      v21 = v33;
      if ( v33 >= 0 )
      {
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v72);
        goto LABEL_59;
      }
      if ( g_wppLevels )
      {
        v34 = 195;
        goto LABEL_50;
      }
    }
    else if ( g_wppLevels )
    {
      v34 = 193;
LABEL_50:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v34, &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids, a1, v33);
    }
LABEL_51:
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v72);
    goto LABEL_30;
  }
  v28 = *a6;
  LODWORD(v72) = 0;
  if ( (*(int (__fastcall **)(_QWORD *, __int64 *, void **))(v28 + 56))(a6, MF_SA_D3D12_AWARE, &v72) >= 0
    && (unsigned __int8)byte_18010EC4D >= 8u )
  {
    WPP_SF_qD(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      189,
      &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
      a1,
      (_DWORD)v72);
  }
  v24 = (*(__int64 (__fastcall **)(_QWORD *, _QWORD))(*v27 + 256LL))(v27, *v23);
  v21 = v24;
  if ( v24 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v25 = 190;
    goto LABEL_29;
  }
  if ( (_DWORD)v72 )
  {
    v29 = *(__int64 (__fastcall **)(struct IFSSource *, __int64 *))(*(_QWORD *)a4 + 288LL);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v74);
    v24 = v29(a4, &v74);
    v21 = v24;
    if ( v24 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_30;
      v25 = 191;
      goto LABEL_29;
    }
    v30 = MFGetAttributeUINT32(v74, MF_SA_D3D12_AWARE, 0);
    v24 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, _QWORD))(*(_QWORD *)*v23 + 168LL))(
            *v23,
            MF_SA_D3D12_AWARE,
            (unsigned int)v72 & v30);
    v21 = v24;
    if ( v24 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_30;
      v25 = 192;
      goto LABEL_29;
    }
  }
LABEL_59:
  v38 = (int)v80;
  v39 = (*(__int64 (__fastcall **)(struct IFSClientContextInfo *))(*(_QWORD *)v80 + 32LL))(v80);
  v40 = (struct IFSClientContextInfo **)((char *)a1 + 264);
  v41 = v39 != 0 ? v81 : 0;
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)a1 + 264);
  LOBYTE(v42) = 1;
  v24 = FSCloneClientContextInfo(v38, v41, 0, v42, v70, (__int64)a1 + 264);
  v21 = v24;
  if ( v24 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v25 = 196;
    goto LABEL_29;
  }
  if ( v81 == 1 )
    v43 = *v40;
  else
    v43 = v80;
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((__int64 *)a1 + 25, (__int64)v43);
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v9 |= 2u;
    v45 = ClientContextInfoTrace::ClientContextInfoTrace(
            (ClientContextInfoTrace *)v76,
            *((struct IFSClientContextInfo **)a1 + 25));
    v46 = FSString::GetString(v45);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      197,
      (unsigned int)&WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
      (_DWORD)a1,
      (__int64)v46);
  }
  if ( (v9 & 2) != 0 )
  {
    v9 &= ~2u;
    FSString::~FSString((FSString *)v76, v44);
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v9 |= 4u;
    v47 = ClientContextInfoTrace::ClientContextInfoTrace((ClientContextInfoTrace *)v76, *v40);
    v48 = FSString::GetString(v47);
    WPP_SF_qs(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      198,
      (unsigned int)&WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
      (_DWORD)a1,
      (__int64)v48);
  }
  if ( (v9 & 4) != 0 )
    FSString::~FSString((FSString *)v76, v44);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)a1 + 128);
  v24 = MFCreateEventQueue((IMFMediaEventQueue **)a1 + 16);
  v21 = v24;
  if ( v24 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v25 = 199;
    goto LABEL_29;
  }
  v24 = (*(__int64 (__fastcall **)(struct IFSSource *, unsigned __int64, _QWORD, _QWORD, __int64))(*(_QWORD *)a4 + 120LL))(
          a4,
          ((unsigned __int64)a1 + 40) & -(__int64)(a1 != 0),
          *((_QWORD *)a1 + 25),
          0,
          (__int64)a1 + 168);
  v21 = v24;
  if ( v24 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v25 = 200;
    goto LABEL_29;
  }
  v24 = (*(__int64 (__fastcall **)(struct IFSSource *, DWORD *))(*(_QWORD *)a4 + 64LL))(a4, &cStreamDescriptors);
  v21 = v24;
  if ( v24 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_30;
    v25 = 201;
    goto LABEL_29;
  }
  if ( !cStreamDescriptors )
  {
    v21 = -1072875845;
    if ( g_wppLevels )
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        202,
        &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
        a1,
        -1072875845);
    goto LABEL_30;
  }
  unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<IMFStreamDescriptor * [0]>(&v72, cStreamDescriptors);
  wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(
    (void **)&apStreamDescriptors,
    unique);
  v51 = v72;
  v72 = 0;
  if ( v51 )
    operator delete(v51, v50);
  v10 = apStreamDescriptors;
  if ( !apStreamDescriptors )
  {
    FSSourceExtendedCameraController = -2147024882;
    v21 = -2147024882;
    if ( g_wppLevels )
    {
      v22 = 203;
      goto LABEL_90;
    }
LABEL_31:
    if ( !byte_18010EC4D )
      goto LABEL_136;
    v26 = 213;
    goto LABEL_135;
  }
  memset_0(apStreamDescriptors, 0, 8LL * cStreamDescriptors);
  if ( v14 )
  {
    v52 = *(void (__fastcall **)(__int64, struct IFSSourceIdentity **))(*(_QWORD *)v14 + 48LL);
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v73);
    v52(v14, &v73);
    if ( (*(unsigned int (__fastcall **)(struct IFSSourceIdentity *))(*(_QWORD *)v73 + 24LL))(v73) == 4 )
    {
      v53 = *(_QWORD *)a4;
      apStreamDescriptors = 0;
      v54 = *(__int64 (__fastcall **)(struct IFSSource *, IMFStreamDescriptor ***))(v53 + 520);
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&apStreamDescriptors);
      v55 = v54(a4, &apStreamDescriptors);
      if ( v55 < 0 )
      {
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          v56 = 206;
          goto LABEL_101;
        }
      }
      else
      {
        v55 = (*(__int64 (__fastcall **)(__int64, IMFStreamDescriptor **))(*(_QWORD *)v14 + 512LL))(
                v14,
                apStreamDescriptors);
        if ( v55 >= 0 )
        {
          if ( (unsigned __int8)byte_18010EC4D >= 8u )
            WPP_SF_qq(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              204,
              &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
              a1,
              apStreamDescriptors);
          goto LABEL_102;
        }
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          v56 = 205;
LABEL_101:
          WPP_SF_qD(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            v56,
            &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
            a1,
            v55);
        }
      }
LABEL_102:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&apStreamDescriptors);
    }
  }
  v57 = 0;
  if ( !cStreamDescriptors )
  {
LABEL_108:
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)a1 + 144);
    v61 = MFCreatePresentationDescriptor(cStreamDescriptors, v10, (IMFPresentationDescriptor **)a1 + 18);
    v21 = v61;
    if ( v61 >= 0 )
    {
      v64 = **(__int64 (__fastcall ***)(struct FSSourceMediaSource *, GUID *, __int64 *))a1;
      wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v75);
      v61 = v64(a1, &GUID_00000000_0000_0000_c000_000000000046, &v75);
      v21 = v61;
      if ( v61 >= 0 )
      {
        if ( !v14
          || (v61 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v14 + 464LL))(v14, v75), v21 = v61, v61 >= 0) )
        {
          wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((__int64 *)a1 + 15, v14);
          wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((__int64 *)a1 + 14, (__int64)a4);
          goto LABEL_128;
        }
        if ( !g_wppLevels )
          goto LABEL_128;
        v62 = 212;
      }
      else
      {
        if ( !g_wppLevels )
          goto LABEL_128;
        v62 = 211;
      }
    }
    else
    {
      if ( !g_wppLevels )
        goto LABEL_128;
      v62 = 210;
    }
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v62, &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids, a1, v61);
    goto LABEL_128;
  }
  while ( 1 )
  {
    v58 = (struct IFSClientContextInfo *)*((_QWORD *)a1 + 25);
    apStreamDescriptors = 0;
    FSSourceMediaStream = FSSourceMediaStream::CreateFSSourceMediaStream(
                            a4,
                            v57,
                            v58,
                            a1,
                            v73,
                            (struct FSSourceMediaStream **)&apStreamDescriptors);
    v21 = FSSourceMediaStream;
    if ( FSSourceMediaStream < 0 )
      break;
    v60 = apStreamDescriptors;
    FSSourceMediaStream = ((__int64 (__fastcall *)(IMFStreamDescriptor **, IMFStreamDescriptor **))(*apStreamDescriptors)[8].lpVtbl)(
                            apStreamDescriptors,
                            &v10[v57]);
    v21 = FSSourceMediaStream;
    if ( FSSourceMediaStream < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_119;
      v63 = 208;
      goto LABEL_118;
    }
    if ( !(unsigned int)CTUnkArray<IMFMediaType>::Add((__int64)a1 + 176, (__int64)v60) )
    {
      FSSourceMediaStream = -2147024882;
      v21 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_119;
      v63 = 209;
      goto LABEL_118;
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&apStreamDescriptors);
    v57 = (unsigned int)(v57 + 1);
    if ( (unsigned int)v57 >= cStreamDescriptors )
      goto LABEL_108;
  }
  if ( !g_wppLevels )
    goto LABEL_119;
  v63 = 207;
LABEL_118:
  WPP_SF_qD(
    *((_QWORD *)WPP_GLOBAL_Control + 2),
    v63,
    &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids,
    a1,
    FSSourceMediaStream);
LABEL_119:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&apStreamDescriptors);
LABEL_128:
  v65 = cStreamDescriptors;
  for ( i = 0; (unsigned int)i < v65; i = (unsigned int)(i + 1) )
  {
    v67 = v10[i];
    if ( v67 )
    {
      ((void (__fastcall *)(IMFStreamDescriptor *))v67->lpVtbl->Release)(v67);
      v10[i] = 0;
      v65 = cStreamDescriptors;
    }
  }
  if ( v21 < 0 )
    goto LABEL_31;
  if ( (unsigned __int8)byte_18010EC4D < 8u )
    goto LABEL_136;
  v26 = 214;
LABEL_135:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v26, &WPP_c86f311039f236b6866f123fc8c117c6_Traceguids, a1, v21);
LABEL_136:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v73);
  PropVariantClear(pvar);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v74);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v75);
  if ( v10 )
    operator delete(v10, v68);
  return (unsigned int)v21;
}

```

## disassembly

```asm
0x18003c65c  mov     rax, rsp
0x18003c65f  mov     [rax+20h], rbx
0x18003c663  mov     [rax+18h], r8d
0x18003c667  mov     [rax+10h], rdx
0x18003c66b  push    rbp
0x18003c66c  push    rsi
0x18003c66d  push    rdi
0x18003c66e  push    r12
0x18003c670  push    r13
0x18003c672  push    r14
0x18003c674  push    r15
0x18003c676  lea     rbp, [rax-4Fh]
0x18003c67a  sub     rsp, 90h
0x18003c681  xor     edi, edi
0x18003c683  mov     rsi, rcx
0x18003c686  mov     [rbp+47h+cStreamDescriptors], edi
0x18003c689  xor     ecx, ecx
0x18003c68b  xorps   xmm0, xmm0
0x18003c68e  mov     [rbp+47h+var_40], rcx
0x18003c692  mov     r15, r9
0x18003c695  mov     [rbp+47h+cStreamDescriptors], edi
0x18003c698  mov     ebx, r8d
0x18003c69b  mov     [rbp+47h+apStreamDescriptors], rdi
0x18003c69f  mov     r14d, edi
0x18003c6a2  mov     [rbp+47h+var_70], rdi
0x18003c6a6  mov     r13d, edi
0x18003c6a9  mov     [rbp+47h+var_78], rdi
0x18003c6ad  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x18003c6b1  mov     [rbp+47h+var_80], rdi
0x18003c6b5  cmp     cs:byte_18010EC4D, 8
0x18003c6bc  jb      short loc_18003C6FA
0x18003c6be  lea     rcx, [rbp+47h+var_68]; this
0x18003c6c2  call    ??0ClientContextInfoTrace@@QEAA@PEAUIFSClientContextInfo@@@Z; ClientContextInfoTrace::ClientContextInfoTrace(IFSClientContextInfo *)
0x18003c6c7  mov     rcx, rax; this
0x18003c6ca  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18003c6cf  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c6d6  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003c6dd  mov     edx, 0B7h
0x18003c6e2  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18003c6e7  mov     r9, rsi
0x18003c6ea  mov     rcx, [rcx+0D8h]
0x18003c6f1  call    WPP_SF_qs
0x18003c6f6  lea     r14d, [rdi+1]
0x18003c6fa  test    r14b, 1
0x18003c6fe  jz      short loc_18003C70D
0x18003c700  and     r14d, 0FFFFFFFEh
0x18003c704  lea     rcx, [rbp+47h+var_68]; this
0x18003c708  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18003c70d  cmp     cs:byte_18010EC4D, 8
0x18003c714  jb      short loc_18003C752
0x18003c716  cmp     ebx, 1
0x18003c719  lea     rcx, aControlling; "controlling"
0x18003c720  lea     rax, aShared; "shared"
0x18003c727  mov     edx, 0B8h
0x18003c72c  cmovnz  rax, rcx
0x18003c730  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003c737  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c73e  mov     r9, rsi
0x18003c741  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18003c746  mov     rcx, [rcx+0D8h]
0x18003c74d  call    WPP_SF_qs
0x18003c752  cmp     cs:byte_18010EC4D, 10h
0x18003c759  mov     r12, [rbp+47h+arg_20]
0x18003c75d  jb      loc_18003C87E
0x18003c763  mov     rax, [r15]
0x18003c766  lea     rcx, [rbp+47h+var_88]
0x18003c76a  mov     [rbp+47h+var_88], rdi
0x18003c76e  mov     rbx, [rax+30h]
0x18003c772  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003c777  lea     rdx, [rbp+47h+var_88]
0x18003c77b  mov     rcx, r15
0x18003c77e  mov     rax, rbx
0x18003c781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c786  lea     rdi, aNullptr_2; "<nullptr"
0x18003c78d  test    eax, eax
0x18003c78f  js      short loc_18003C7EB
0x18003c791  cmp     cs:byte_18010EC4D, 8
0x18003c798  jb      short loc_18003C7EB
0x18003c79a  mov     rcx, [rbp+47h+var_88]
0x18003c79e  mov     rax, [rcx]
0x18003c7a1  mov     rax, [rax+28h]
0x18003c7a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7aa  test    rax, rax
0x18003c7ad  jnz     short loc_18003C7B4
0x18003c7af  mov     rax, rdi
0x18003c7b2  jmp     short loc_18003C7C4
0x18003c7b4  mov     rcx, [rbp+47h+var_88]
0x18003c7b8  mov     rax, [rcx]
0x18003c7bb  mov     rax, [rax+28h]
0x18003c7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c7c4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c7cb  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003c7d2  mov     edx, 0B9h
0x18003c7d7  mov     qword ptr [rsp+0C0h+var_A0], rax
0x18003c7dc  mov     r9, rsi
0x18003c7df  mov     rcx, [rcx+0D8h]
0x18003c7e6  call    WPP_SF_qS
0x18003c7eb  lea     rcx, [rbp+47h+var_88]
0x18003c7ef  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003c7f4  test    r12, r12
0x18003c7f7  jz      short loc_18003C875
0x18003c7f9  mov     rax, [r12]
0x18003c7fd  lea     rcx, [rbp+47h+var_88]
0x18003c801  mov     rbx, [rax+30h]
0x18003c805  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003c80a  lea     rdx, [rbp+47h+var_88]
0x18003c80e  mov     rcx, r12
0x18003c811  mov     rax, rbx
0x18003c814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c819  test    eax, eax
0x18003c81b  js      short loc_18003C875
0x18003c81d  cmp     cs:byte_18010EC4D, 8
0x18003c824  jb      short loc_18003C875
0x18003c826  mov     rcx, [rbp+47h+var_88]
0x18003c82a  mov     rax, [rcx]
0x18003c82d  mov     rax, [rax+28h]
0x18003c831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c836  test    rax, rax
0x18003c839  jz      short loc_18003C84E
0x18003c83b  mov     rcx, [rbp+47h+var_88]
0x18003c83f  mov     rax, [rcx]
0x18003c842  mov     rax, [rax+28h]
0x18003c846  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c84b  mov     rdi, rax
0x18003c84e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c855  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003c85c  mov     edx, 0BAh
0x18003c861  mov     qword ptr [rsp+0C0h+var_A0], rdi
0x18003c866  mov     r9, rsi
0x18003c869  mov     rcx, [rcx+0D8h]
0x18003c870  call    WPP_SF_qS
0x18003c875  lea     rcx, [rbp+47h+var_88]; void *
0x18003c879  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003c87e  lea     rbx, [rsi+0E8h]
0x18003c885  mov     rcx, rbx
0x18003c888  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003c88d  mov     rdx, rbx; struct FSSourceExtendedCameraController **
0x18003c890  mov     rcx, r15; struct IFSSource *
0x18003c893  call    ?CreateFSSourceExtendedCameraController@FSSourceExtendedCameraController@@SAJPEAUIFSSource@@PEAPEAV1@@Z; FSSourceExtendedCameraController::CreateFSSourceExtendedCameraController(IFSSource *,FSSourceExtendedCameraController * *)
0x18003c898  mov     edi, eax
0x18003c89a  test    eax, eax
0x18003c89c  jns     short loc_18003C8B1
0x18003c89e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c8a5  jb      short loc_18003C901
0x18003c8a7  mov     edx, 0BBh
0x18003c8ac  jmp     loc_18003CDB2
0x18003c8b1  lea     r13, [rsi+88h]
0x18003c8b8  mov     rcx, r13
0x18003c8bb  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003c8c0  xor     edx, edx; cInitialSize
0x18003c8c2  mov     rcx, r13; ppMFAttributes
0x18003c8c5  call    cs:__imp_MFCreateAttributes
0x18003c8cb  mov     edi, eax
0x18003c8cd  test    eax, eax
0x18003c8cf  jns     short loc_18003C918
0x18003c8d1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c8d8  jb      short loc_18003C8FD
0x18003c8da  mov     edx, 0BCh
0x18003c8df  mov     [rsp+0C0h+var_A0], eax
0x18003c8e3  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003c8ea  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c8f1  mov     r9, rsi
0x18003c8f4  mov     rcx, [rcx+10h]
0x18003c8f8  call    WPP_SF_qD
0x18003c8fd  mov     r13, [rbp+47h+apStreamDescriptors]
0x18003c901  cmp     cs:byte_18010EC4D, 1
0x18003c908  jb      loc_18003D138
0x18003c90e  mov     edx, 0D5h
0x18003c913  jmp     loc_18003D117
0x18003c918  mov     rbx, [rbp+47h+arg_28]
0x18003c91c  test    rbx, rbx
0x18003c91f  jz      loc_18003CA50
0x18003c925  mov     rax, [rbx]
0x18003c928  lea     r8, [rbp+47h+var_88]
0x18003c92c  lea     rdx, MF_SA_D3D12_AWARE
0x18003c933  mov     dword ptr [rbp+47h+var_88], 0
0x18003c93a  mov     rcx, rbx
0x18003c93d  mov     rax, [rax+38h]
0x18003c941  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c946  test    eax, eax
0x18003c948  js      short loc_18003C97C
0x18003c94a  cmp     cs:byte_18010EC4D, 8
0x18003c951  jb      short loc_18003C97C
0x18003c953  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c95a  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003c961  mov     eax, dword ptr [rbp+47h+var_88]
0x18003c964  mov     edx, 0BDh
0x18003c969  mov     r9, rsi
0x18003c96c  mov     [rsp+0C0h+var_A0], eax
0x18003c970  mov     rcx, [rcx+0D8h]
0x18003c977  call    WPP_SF_qD
0x18003c97c  mov     rax, [rbx]
0x18003c97f  mov     rcx, rbx
0x18003c982  mov     rdx, [r13+0]
0x18003c986  mov     rax, [rax+100h]
0x18003c98d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c992  mov     edi, eax
0x18003c994  test    eax, eax
0x18003c996  jns     short loc_18003C9AF
0x18003c998  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c99f  jb      loc_18003C8FD
0x18003c9a5  mov     edx, 0BEh
0x18003c9aa  jmp     loc_18003C8DF
0x18003c9af  cmp     dword ptr [rbp+47h+var_88], 0
0x18003c9b3  jz      loc_18003CB47
0x18003c9b9  mov     rax, [r15]
0x18003c9bc  lea     rcx, [rbp+47h+var_78]
0x18003c9c0  mov     rbx, [rax+120h]
0x18003c9c7  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003c9cc  lea     rdx, [rbp+47h+var_78]
0x18003c9d0  mov     rcx, r15
0x18003c9d3  mov     rax, rbx
0x18003c9d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9db  mov     edi, eax
0x18003c9dd  test    eax, eax
0x18003c9df  jns     short loc_18003C9F8
0x18003c9e1  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003c9e8  jb      loc_18003C8FD
0x18003c9ee  mov     edx, 0BFh
0x18003c9f3  jmp     loc_18003C8DF
0x18003c9f8  mov     rcx, [rbp+47h+var_78]
0x18003c9fc  lea     rdx, MF_SA_D3D12_AWARE
0x18003ca03  xor     r8d, r8d
0x18003ca06  call    MFGetAttributeUINT32
0x18003ca0b  mov     rcx, [r13+0]
0x18003ca0f  lea     rdx, MF_SA_D3D12_AWARE
0x18003ca16  mov     r9d, eax
0x18003ca19  and     r9d, dword ptr [rbp+47h+var_88]
0x18003ca1d  mov     r8, [rcx]
0x18003ca20  mov     rax, [r8+0A8h]
0x18003ca27  mov     r8d, r9d
0x18003ca2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca2f  mov     edi, eax
0x18003ca31  test    eax, eax
0x18003ca33  jns     loc_18003CB47
0x18003ca39  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ca40  jb      loc_18003C8FD
0x18003ca46  mov     edx, 0C0h
0x18003ca4b  jmp     loc_18003C8DF
0x18003ca50  mov     rax, [r15]
0x18003ca53  lea     rcx, [rbp+47h+var_88]
0x18003ca57  mov     [rbp+47h+var_88], 0
0x18003ca5f  mov     rbx, [rax+30h]
0x18003ca63  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003ca68  lea     rdx, [rbp+47h+var_88]
0x18003ca6c  mov     rcx, r15
0x18003ca6f  mov     rax, rbx
0x18003ca72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca77  mov     edi, eax
0x18003ca79  test    eax, eax
0x18003ca7b  jns     short loc_18003CAB7
0x18003ca7d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ca84  jb      short loc_18003CAA9
0x18003ca86  mov     edx, 0C1h
0x18003ca8b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ca92  lea     r8, WPP_c86f311039f236b6866f123fc8c117c6_Traceguids
0x18003ca99  mov     r9, rsi
0x18003ca9c  mov     [rsp+0C0h+var_A0], eax
0x18003caa0  mov     rcx, [rcx+10h]
0x18003caa4  call    WPP_SF_qD
0x18003caa9  lea     rcx, [rbp+47h+var_88]; void *
0x18003caad  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003cab2  jmp     loc_18003C8FD
0x18003cab7  mov     rcx, [r13+0]
0x18003cabb  lea     r8, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID
0x18003cac2  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE
0x18003cac9  mov     rax, [rcx]
0x18003cacc  mov     rax, [rax+0C0h]
0x18003cad3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cad8  mov     edi, eax
0x18003cada  test    eax, eax
0x18003cadc  jns     short loc_18003CAEE
0x18003cade  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cae5  jb      short loc_18003CAA9
0x18003cae7  mov     edx, 0C2h
0x18003caec  jmp     short loc_18003CA8B
0x18003caee  mov     rdi, [r13+0]
0x18003caf2  mov     rcx, [rbp+47h+var_88]
0x18003caf6  mov     rax, [rdi]
0x18003caf9  mov     rdx, [rcx]
0x18003cafc  mov     rbx, [rax+0C8h]
0x18003cb03  mov     rax, [rdx+28h]
0x18003cb07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb0c  mov     r8, rax
0x18003cb0f  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x18003cb16  mov     rax, rbx
0x18003cb19  mov     rcx, rdi
0x18003cb1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cb21  mov     edi, eax
0x18003cb23  test    eax, eax
0x18003cb25  jns     short loc_18003CB3E
0x18003cb27  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003cb2e  jb      loc_18003CAA9
0x18003cb34  mov     edx, 0C3h
0x18003cb39  jmp     loc_18003CA8B
0x18003cb3e  lea     rcx, [rbp+47h+var_88]; void *
0x18003cb42  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003cb47  mov     rdi, [rbp+47h+arg_8]
0x18003cb4b  mov     rcx, rdi
0x18003cb4e  mov     rax, [rdi]
  ... truncated ...
```
