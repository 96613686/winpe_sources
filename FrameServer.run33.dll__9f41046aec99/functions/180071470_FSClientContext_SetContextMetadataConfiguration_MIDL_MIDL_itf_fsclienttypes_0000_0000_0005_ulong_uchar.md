# FSClientContext::SetContextMetadataConfiguration(__MIDL___MIDL_itf_fsclienttypes_0000_0000_0005,ulong,uchar *)

- ea: `0x180071470`
- end: `0x180071c3e`
- name: `?SetContextMetadataConfiguration@FSClientContext@@UEAAJW4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0005@@KPEAE@Z`
- size: `1998`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180003e20`
- `0x1800041f0`
- `0x18000478c`
- `0x180008cf0`
- `0x180009494`
- `0x180009608`
- `0x180009b5c`
- `0x18000a648`
- `0x18000a880`
- `0x18000a91c`
- `0x180017ab8`
- `0x180024200`
- `0x180027e80`
- `0x18002a6fc`
- `0x18004d714`
- `0x18004da70`
- `0x18006745c`
- `0x18006b09c`
- `0x180071470`
- `0x180073984`
- `0x180073f20`
- `0x1800ea010`

## import_xrefs

- `MFPlat!MFCreateAttributes` at `0x180071521`
- `MFPlat!MFCreateAttributes` at `0x1800716b8`
- `MFPlat!MFCreateAttributes` at `0x180071521`
- `MFPlat!MFCreateAttributes` at `0x1800716b8`
- `MFPlat!MFInitAttributesFromBlob` at `0x18007154f`
- `MFPlat!MFInitAttributesFromBlob` at `0x1800716e6`
- `MFPlat!MFInitAttributesFromBlob` at `0x18007154f`
- `MFPlat!MFInitAttributesFromBlob` at `0x1800716e6`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x1800715ba`
- `MFPlat!MFGetAttributesAsBlobSize` at `0x1800715ba`

## pseudocode

```c
__int64 __fastcall FSClientContext::SetContextMetadataConfiguration(
        FSClientContext *a1,
        unsigned int a2,
        __int64 a3,
        const UINT8 *a4)
{
  unsigned int v4; // r12d
  int v6; // r13d
  UINT v7; // ebx
  HRESULT NetworkCamAtribs; // eax
  int v11; // edi
  __int64 v12; // rdx
  HRESULT v13; // eax
  __int64 v14; // rdx
  IMFAttributes *v15; // rdi
  HRESULT (__stdcall *GetAllocatedString)(IMFAttributes *, const GUID *const, LPWSTR *, UINT32 *); // rbx
  IMFAttributes *v17; // rdi
  HRESULT (__stdcall *v18)(IMFAttributes *, const GUID *const, LPWSTR *, UINT32 *); // rbx
  unsigned int v19; // eax
  unsigned int v20; // r15d
  __int64 unique; // rax
  const struct std::nothrow_t *v22; // rdx
  void *v23; // rcx
  GUID *v24; // r14
  bool v25; // cl
  IMFAttributes *v26; // rbx
  GuidTrace *v27; // rax
  const char *String; // rax
  __int64 v29; // rax
  const struct std::nothrow_t *v30; // rdx
  void *v31; // rcx
  int v32; // eax
  __int64 v33; // rdx
  const struct std::nothrow_t *v34; // rdx
  bool v35; // cl
  int v36; // ebx
  bool v37; // cl
  int v38; // eax
  const struct std::nothrow_t *v39; // rdx
  __int64 v40; // rdx
  unsigned int v42; // [rsp+20h] [rbp-E0h]
  unsigned int v43; // [rsp+20h] [rbp-E0h]
  unsigned int *v44; // [rsp+28h] [rbp-D8h]
  unsigned int *v45; // [rsp+28h] [rbp-D8h]
  IMFAttributes *ppMFAttributes; // [rsp+40h] [rbp-C0h] BYREF
  IMFAttributes *pAttributes; // [rsp+48h] [rbp-B8h] BYREF
  char v48; // [rsp+50h] [rbp-B0h]
  IMFAttributes *v49; // [rsp+58h] [rbp-A8h] BYREF
  UINT32 pcbBufSize; // [rsp+60h] [rbp-A0h] BYREF
  void *v51; // [rsp+68h] [rbp-98h] BYREF
  void *v52; // [rsp+70h] [rbp-90h] BYREF
  int v53; // [rsp+78h] [rbp-88h] BYREF
  _BYTE v54[32]; // [rsp+80h] [rbp-80h] BYREF
  unsigned __int16 v55[264]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v56[264]; // [rsp+2B0h] [rbp+1B0h] BYREF

  v4 = 0;
  v6 = 0;
  LODWORD(v51) = 0;
  v7 = a3;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    LODWORD(v44) = a3;
    v42 = a2;
    WPP_SF_qdDq(*((_QWORD *)WPP_GLOBAL_Control + 27), 252, a3, a1);
  }
  if ( a2 != 1 )
  {
    if ( a2 != 4 )
    {
      v11 = -2147467263;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          270,
          &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids,
          a1,
          -2147467263);
LABEL_91:
      if ( byte_18010EC4D )
      {
        v40 = 271;
        goto LABEL_93;
      }
      return (unsigned int)v11;
    }
    ppMFAttributes = 0;
    v53 = 0;
    pAttributes = 0;
    pcbBufSize = 0;
    v51 = 0;
    v49 = 0;
    if ( !a4 || !v7 )
    {
      v13 = -2147024809;
      v11 = -2147024809;
      if ( g_wppLevels )
      {
        v14 = 258;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v49);
    v13 = MFCreateAttributes(&v49, 0);
    v11 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 259;
LABEL_86:
        WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, a1, v13);
        goto LABEL_87;
      }
      goto LABEL_87;
    }
    v13 = MFInitAttributesFromBlob(v49, a4, v7);
    v11 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 260;
        goto LABEL_86;
      }
LABEL_87:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v49);
LABEL_88:
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pAttributes);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppMFAttributes);
      goto LABEL_91;
    }
    v15 = v49;
    GetAllocatedString = v49->lpVtbl->GetAllocatedString;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &ppMFAttributes,
      0);
    v13 = ((__int64 (__fastcall *)(IMFAttributes *, void *, IMFAttributes **, int *))GetAllocatedString)(
            v15,
            &FSSERVICE_CONFIGURATION_DEVICE_SYMBOLICNAME,
            &ppMFAttributes,
            &v53);
    v11 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 261;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    v17 = v49;
    v18 = v49->lpVtbl->GetAllocatedString;
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
      &pAttributes,
      0);
    v13 = ((__int64 (__fastcall *)(IMFAttributes *, void *, IMFAttributes **, UINT32 *))v18)(
            v17,
            &FSSERVICE_CONFIGURATION_UPDATED_FRIENDLYNAME,
            &pAttributes,
            &pcbBufSize);
    v11 = v13;
    if ( v13 < 0 )
    {
      if ( g_wppLevels )
      {
        v14 = 262;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    v19 = MFGetAttributeUINT32(v49, &FSSERVICE_CONFIGURATION_UPDATED_INTERFACECATEGORY_COUNT, 0);
    v20 = v19;
    if ( !v19 )
    {
      v20 = 2;
      unique = wil::make_unique_nothrow<_GUID [0]>(&v52, 2);
      wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&v51, unique);
      v23 = v52;
      v52 = 0;
      if ( v23 )
        operator delete(v23, v22);
      v24 = (GUID *)v51;
      if ( v51 )
      {
        v48 = 1;
        *(GUID *)v51 = GUID_e5323777_f976_4f5b_9b55_b94699c46e44;
        v24[1] = GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca;
        goto LABEL_48;
      }
      v13 = -2147024882;
      v11 = -2147024882;
      if ( !g_wppLevels )
        goto LABEL_87;
      v14 = 263;
      goto LABEL_86;
    }
    v29 = wil::make_unique_nothrow<_GUID [0]>(&v52, v19);
    wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(&v51, v29);
    v31 = v52;
    v52 = 0;
    if ( v31 )
      operator delete(v31, v30);
    v24 = (GUID *)v51;
    if ( !v51 )
    {
      v13 = -2147024882;
      v11 = -2147024882;
      if ( g_wppLevels )
      {
        v14 = 264;
        goto LABEL_86;
      }
      goto LABEL_87;
    }
    v48 = 0;
    v42 = 0;
    v32 = ((__int64 (__fastcall *)(IMFAttributes *, void *, void *, _QWORD))v49->lpVtbl->GetBlob)(
            v49,
            &FSSERVICE_CONFIGURATION_UPDATED_INTERFACECATEGORY_LIST,
            v51,
            16 * v20);
    v11 = v32;
    if ( v32 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_64;
      v33 = 265;
LABEL_63:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v33, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, a1, v32);
LABEL_64:
      wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v49);
      if ( v24 )
        operator delete(v24, v34);
      goto LABEL_88;
    }
LABEL_48:
    while ( v4 < v20 )
    {
      memset_0(v55, 0, 0x208u);
      LODWORD(v51) = FSGetAliasDeviceName2(v25, (const unsigned __int16 *)ppMFAttributes, &v24[v4], v55, v42, v44);
      if ( (int)v51 >= 0 )
      {
        v32 = FSSetDeviceInterfaceProperty(
                v55,
                &DEVPKEY_DeviceInterface_FriendlyName,
                0x12u,
                (unsigned __int8 *const)pAttributes,
                2 * pcbBufSize + 2);
        v11 = v32;
        if ( v32 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_64;
          v33 = 267;
          goto LABEL_63;
        }
      }
      else
      {
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
        {
          v26 = ppMFAttributes;
          v6 |= 1u;
          v27 = GuidTrace::GuidTrace((GuidTrace *)v54, &v24[v4]);
          String = GuidTrace::GetString(v27);
          WPP_SF_qDsS(*((_QWORD *)WPP_GLOBAL_Control + 27), (char)v51, (__int64)String, (__int64)v26);
        }
        if ( (v6 & 1) != 0 )
        {
          v6 &= ~1u;
          FSString::~FSString((FSString *)v54);
        }
        v11 = 0;
      }
      ++v4;
    }
    if ( v48 )
    {
      memset_0(v55, 0, 0x208u);
      memset_0(v56, 0, 0x208u);
      v36 = FSGetAliasDeviceName2(
              v35,
              (const unsigned __int16 *)ppMFAttributes,
              &GUID_65e8773d_8f56_11d0_a3b9_00a0c9223196,
              v55,
              v42,
              v44);
      v38 = FSGetAliasDeviceName2(
              v37,
              (const unsigned __int16 *)ppMFAttributes,
              &GUID_6994ad05_93ef_11d0_a3cc_00a0c9223196,
              v56,
              v43,
              v45);
      if ( v36 >= 0 && v38 >= 0 )
      {
        v32 = FSSetDeviceInterfaceProperty(
                v55,
                &DEVPKEY_DeviceInterface_FriendlyName,
                0x12u,
                (unsigned __int8 *const)pAttributes,
                2 * pcbBufSize + 2);
        v11 = v32;
        if ( v32 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_64;
          v33 = 268;
          goto LABEL_63;
        }
        v32 = FSSetDeviceInterfaceProperty(
                v56,
                &DEVPKEY_DeviceInterface_FriendlyName,
                0x12u,
                (unsigned __int8 *const)pAttributes,
                2 * pcbBufSize + 2);
        v11 = v32;
        if ( v32 < 0 )
        {
          if ( !g_wppLevels )
            goto LABEL_64;
          v33 = 269;
          goto LABEL_63;
        }
      }
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v49);
    if ( v24 )
      operator delete(v24, v39);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&pAttributes);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&ppMFAttributes);
    if ( v11 < 0 )
      goto LABEL_91;
    goto LABEL_82;
  }
  ppMFAttributes = 0;
  pAttributes = 0;
  pcbBufSize = 0;
  if ( !a4 || !v7 )
  {
    NetworkCamAtribs = -2147024809;
    v11 = -2147024809;
    if ( g_wppLevels )
    {
      v12 = 253;
      goto LABEL_24;
    }
    goto LABEL_25;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&ppMFAttributes);
  NetworkCamAtribs = MFCreateAttributes(&ppMFAttributes, 0);
  v11 = NetworkCamAtribs;
  if ( NetworkCamAtribs < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 254;
LABEL_24:
      WPP_SF_qD(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v12,
        &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids,
        a1,
        NetworkCamAtribs);
      goto LABEL_25;
    }
    goto LABEL_25;
  }
  NetworkCamAtribs = MFInitAttributesFromBlob(ppMFAttributes, a4, v7);
  v11 = NetworkCamAtribs;
  if ( NetworkCamAtribs < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 255;
      goto LABEL_24;
    }
LABEL_25:
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&pAttributes);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
    goto LABEL_91;
  }
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&pAttributes);
  NetworkCamAtribs = FSClientContext::GetNetworkCamAtribs(a1, ppMFAttributes, &pAttributes);
  v11 = NetworkCamAtribs;
  if ( NetworkCamAtribs < 0 )
  {
    if ( g_wppLevels )
    {
      v12 = 256;
      goto LABEL_24;
    }
    goto LABEL_25;
  }
  if ( pAttributes )
  {
    NetworkCamAtribs = MFGetAttributesAsBlobSize(pAttributes, &pcbBufSize);
    v11 = NetworkCamAtribs;
    if ( NetworkCamAtribs < 0 )
    {
      if ( g_wppLevels )
      {
        v12 = 257;
        goto LABEL_24;
      }
      goto LABEL_25;
    }
    wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((char *)a1 + 800, pAttributes);
    *((_DWORD *)a1 + 202) = pcbBufSize;
  }
  else
  {
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset((char *)a1 + 800);
    *((_DWORD *)a1 + 202) = 0;
  }
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&pAttributes);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&ppMFAttributes);
LABEL_82:
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v40 = 272;
LABEL_93:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v40, &WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids, a1, v11);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180071470  mov     [rsp-8+arg_8], rbx
0x180071475  push    rbp
0x180071476  push    rsi
0x180071477  push    rdi
0x180071478  push    r12
0x18007147a  push    r13
0x18007147c  push    r14
0x18007147e  push    r15
0x180071480  lea     rbp, [rsp-3D0h]
0x180071488  sub     rsp, 4D0h
0x18007148f  mov     rax, cs:__security_cookie
0x180071496  xor     rax, rsp
0x180071499  mov     [rbp+400h+var_40], rax
0x1800714a0  xor     r12d, r12d
0x1800714a3  mov     r14, r9
0x1800714a6  mov     r13d, r12d
0x1800714a9  mov     dword ptr [rsp+500h+var_498], r12d
0x1800714ae  mov     ebx, r8d
0x1800714b1  mov     edi, edx
0x1800714b3  mov     rsi, rcx
0x1800714b6  cmp     cs:byte_18010EC4D, 8
0x1800714bd  jb      short loc_1800714E7
0x1800714bf  mov     [rsp+500h+var_4D0], r9
0x1800714c4  mov     edx, 0FCh
0x1800714c9  mov     r9, rcx
0x1800714cc  mov     dword ptr [rsp+500h+var_4D8], ebx; unsigned int *
0x1800714d0  mov     rcx, cs:WPP_GLOBAL_Control
0x1800714d7  mov     [rsp+500h+var_4E0], edi; unsigned int
0x1800714db  mov     rcx, [rcx+0D8h]
0x1800714e2  call    WPP_SF_qdDq
0x1800714e7  cmp     edi, 1
0x1800714ea  jnz     loc_18007166F
0x1800714f0  mov     [rsp+500h+ppMFAttributes], r12
0x1800714f5  mov     [rsp+500h+pAttributes], r12
0x1800714fa  mov     [rsp+500h+pcbBufSize], r12d
0x1800714ff  test    r14, r14
0x180071502  jz      loc_180071623
0x180071508  test    ebx, ebx
0x18007150a  jz      loc_180071623
0x180071510  lea     rcx, [rsp+500h+ppMFAttributes]
0x180071515  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007151a  xor     edx, edx; cInitialSize
0x18007151c  lea     rcx, [rsp+500h+ppMFAttributes]; ppMFAttributes
0x180071521  call    cs:__imp_MFCreateAttributes
0x180071527  mov     edi, eax
0x180071529  test    eax, eax
0x18007152b  jns     short loc_180071544
0x18007152d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071534  jb      loc_180071656
0x18007153a  mov     edx, 0FEh
0x18007153f  jmp     loc_180071638
0x180071544  mov     rcx, [rsp+500h+ppMFAttributes]; pAttributes
0x180071549  mov     r8d, ebx; cbBufSize
0x18007154c  mov     rdx, r14; pBuf
0x18007154f  call    cs:__imp_MFInitAttributesFromBlob
0x180071555  mov     edi, eax
0x180071557  test    eax, eax
0x180071559  jns     short loc_180071572
0x18007155b  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071562  jb      loc_180071656
0x180071568  mov     edx, 0FFh
0x18007156d  jmp     loc_180071638
0x180071572  lea     rcx, [rsp+500h+pAttributes]
0x180071577  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18007157c  mov     rdx, [rsp+500h+ppMFAttributes]; struct IMFAttributes *
0x180071581  lea     r8, [rsp+500h+pAttributes]; struct IMFAttributes **
0x180071586  mov     rcx, rsi; this
0x180071589  call    ?GetNetworkCamAtribs@FSClientContext@@IEAAJPEAUIMFAttributes@@PEAPEAU2@@Z; FSClientContext::GetNetworkCamAtribs(IMFAttributes *,IMFAttributes * *)
0x18007158e  mov     edi, eax
0x180071590  test    eax, eax
0x180071592  jns     short loc_1800715AB
0x180071594  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007159b  jb      loc_180071656
0x1800715a1  mov     edx, 100h
0x1800715a6  jmp     loc_180071638
0x1800715ab  mov     rcx, [rsp+500h+pAttributes]; pAttributes
0x1800715b0  test    rcx, rcx
0x1800715b3  jz      short loc_1800715F7
0x1800715b5  lea     rdx, [rsp+500h+pcbBufSize]; pcbBufSize
0x1800715ba  call    cs:__imp_MFGetAttributesAsBlobSize
0x1800715c0  mov     edi, eax
0x1800715c2  test    eax, eax
0x1800715c4  jns     short loc_1800715DA
0x1800715c6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800715cd  jb      loc_180071656
0x1800715d3  mov     edx, 101h
0x1800715d8  jmp     short loc_180071638
0x1800715da  mov     rdx, [rsp+500h+pAttributes]
0x1800715df  lea     rcx, [rsi+320h]
0x1800715e6  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x1800715eb  mov     eax, [rsp+500h+pcbBufSize]
0x1800715ef  mov     [rsi+328h], eax
0x1800715f5  jmp     short loc_18007160A
0x1800715f7  lea     rcx, [rsi+320h]
0x1800715fe  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x180071603  mov     [rsi+328h], r12d
0x18007160a  lea     rcx, [rsp+500h+pAttributes]; void *
0x18007160f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180071614  lea     rcx, [rsp+500h+ppMFAttributes]; void *
0x180071619  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18007161e  jmp     loc_180071B48
0x180071623  mov     eax, 80070057h
0x180071628  mov     edi, eax
0x18007162a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071631  jb      short loc_180071656
0x180071633  mov     edx, 0FDh
0x180071638  mov     rcx, cs:WPP_GLOBAL_Control
0x18007163f  lea     r8, WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids
0x180071646  mov     r9, rsi
0x180071649  mov     [rsp+500h+var_4E0], eax
0x18007164d  mov     rcx, [rcx+10h]
0x180071651  call    WPP_SF_qD
0x180071656  lea     rcx, [rsp+500h+pAttributes]; void *
0x18007165b  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x180071660  lea     rcx, [rsp+500h+ppMFAttributes]; void *
0x180071665  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18007166a  jmp     loc_180071BE3
0x18007166f  cmp     edi, 4
0x180071672  jnz     loc_180071BB2
0x180071678  mov     [rsp+500h+ppMFAttributes], r12
0x18007167d  mov     [rsp+500h+var_488], r12d
0x180071682  mov     [rsp+500h+pAttributes], r12
0x180071687  mov     [rsp+500h+pcbBufSize], r12d
0x18007168c  mov     [rsp+500h+var_498], r12
0x180071691  mov     [rsp+500h+var_4A8], r12
0x180071696  test    r14, r14
0x180071699  jz      loc_180071B5F
0x18007169f  test    ebx, ebx
0x1800716a1  jz      loc_180071B5F
0x1800716a7  lea     rcx, [rsp+500h+var_4A8]
0x1800716ac  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800716b1  xor     edx, edx; cInitialSize
0x1800716b3  lea     rcx, [rsp+500h+var_4A8]; ppMFAttributes
0x1800716b8  call    cs:__imp_MFCreateAttributes
0x1800716be  mov     edi, eax
0x1800716c0  test    eax, eax
0x1800716c2  jns     short loc_1800716DB
0x1800716c4  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800716cb  jb      loc_180071B92
0x1800716d1  mov     edx, 103h
0x1800716d6  jmp     loc_180071B74
0x1800716db  mov     rcx, [rsp+500h+var_4A8]; pAttributes
0x1800716e0  mov     r8d, ebx; cbBufSize
0x1800716e3  mov     rdx, r14; pBuf
0x1800716e6  call    cs:__imp_MFInitAttributesFromBlob
0x1800716ec  mov     edi, eax
0x1800716ee  test    eax, eax
0x1800716f0  jns     short loc_180071709
0x1800716f2  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800716f9  jb      loc_180071B92
0x1800716ff  mov     edx, 104h
0x180071704  jmp     loc_180071B74
0x180071709  mov     rdi, [rsp+500h+var_4A8]
0x18007170e  lea     rcx, [rsp+500h+ppMFAttributes]
0x180071713  xor     edx, edx
0x180071715  mov     rax, [rdi]
0x180071718  mov     rbx, [rax+68h]
0x18007171c  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180071721  lea     r9, [rsp+500h+var_488]
0x180071726  mov     rcx, rdi
0x180071729  lea     r8, [rsp+500h+ppMFAttributes]
0x18007172e  mov     rax, rbx
0x180071731  lea     rdx, FSSERVICE_CONFIGURATION_DEVICE_SYMBOLICNAME
0x180071738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007173d  mov     edi, eax
0x18007173f  test    eax, eax
0x180071741  jns     short loc_18007175A
0x180071743  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007174a  jb      loc_180071B92
0x180071750  mov     edx, 105h
0x180071755  jmp     loc_180071B74
0x18007175a  mov     rdi, [rsp+500h+var_4A8]
0x18007175f  lea     rcx, [rsp+500h+pAttributes]
0x180071764  xor     edx, edx
0x180071766  mov     rax, [rdi]
0x180071769  mov     rbx, [rax+68h]
0x18007176d  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x180071772  lea     r9, [rsp+500h+pcbBufSize]
0x180071777  mov     rcx, rdi
0x18007177a  lea     r8, [rsp+500h+pAttributes]
0x18007177f  mov     rax, rbx
0x180071782  lea     rdx, FSSERVICE_CONFIGURATION_UPDATED_FRIENDLYNAME
0x180071789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007178e  mov     edi, eax
0x180071790  test    eax, eax
0x180071792  jns     short loc_1800717AB
0x180071794  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007179b  jb      loc_180071B92
0x1800717a1  mov     edx, 106h
0x1800717a6  jmp     loc_180071B74
0x1800717ab  mov     rcx, [rsp+500h+var_4A8]
0x1800717b0  lea     rdx, FSSERVICE_CONFIGURATION_UPDATED_INTERFACECATEGORY_COUNT
0x1800717b7  xor     r8d, r8d
0x1800717ba  call    MFGetAttributeUINT32
0x1800717bf  mov     r15d, eax
0x1800717c2  lea     rcx, [rsp+500h+var_490]
0x1800717c7  test    eax, eax
0x1800717c9  jnz     loc_1800718FE
0x1800717cf  lea     r15d, [rax+2]
0x1800717d3  mov     edx, r15d
0x1800717d6  call    ??$make_unique_nothrow@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$default_delete@$$BY0A@U_GUID@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<_GUID [0]>(unsigned __int64)
0x1800717db  mov     rdx, rax
0x1800717de  lea     rcx, [rsp+500h+var_498]
0x1800717e3  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x1800717e8  mov     rcx, [rsp+500h+var_490]; void *
0x1800717ed  mov     [rsp+500h+var_490], r12
0x1800717f2  test    rcx, rcx
0x1800717f5  jz      short loc_1800717FC
0x1800717f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800717fc  mov     r14, [rsp+500h+var_498]
0x180071801  test    r14, r14
0x180071804  jnz     short loc_180071824
0x180071806  mov     eax, 8007000Eh
0x18007180b  mov     edi, eax
0x18007180d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180071814  jb      loc_180071B92
0x18007181a  mov     edx, 107h
0x18007181f  jmp     loc_180071B74
0x180071824  movups  xmm0, xmmword ptr cs:_GUID_e5323777_f976_4f5b_9b55_b94699c46e44.Data1
0x18007182b  mov     [rsp+500h+var_4B0], 1
0x180071830  movdqu  xmmword ptr [r14], xmm0
0x180071835  movups  xmm0, xmmword ptr cs:_GUID_24e552d7_6523_47f7_a647_d3465bf1f5ca.Data1
0x18007183c  movdqu  xmmword ptr [r14+10h], xmm0
0x180071842  mov     ebx, 208h
0x180071847  cmp     r12d, r15d
0x18007184a  jnb     loc_180071A1C
0x180071850  mov     r8, rbx; Size
0x180071853  lea     rcx, [rbp+400h+var_460]; void *
0x180071857  xor     edx, edx; Val
0x180071859  call    memset_0
0x18007185e  mov     rdx, [rsp+500h+ppMFAttributes]; unsigned __int16 *
0x180071863  lea     r9, [rbp+400h+var_460]; unsigned __int16 *
0x180071867  mov     edi, r12d
0x18007186a  shl     rdi, 4
0x18007186e  add     rdi, r14
0x180071871  mov     r8, rdi; struct _GUID *
0x180071874  call    ?FSGetAliasDeviceName2@@YAJ_NPEBGAEBU_GUID@@PEAGKPEAK@Z; FSGetAliasDeviceName2(bool,ushort const *,_GUID const &,ushort *,ulong,ulong *)
0x180071879  mov     dword ptr [rsp+500h+var_498], eax
0x18007187d  test    eax, eax
0x18007187f  jns     loc_1800719D1
0x180071885  cmp     cs:byte_18010EC4D, 8
0x18007188c  jb      short loc_1800718E4
0x18007188e  mov     rbx, [rsp+500h+ppMFAttributes]
0x180071893  lea     rcx, [rbp+400h+var_480]; this
0x180071897  mov     rdx, rdi; struct _GUID *
0x18007189a  or      r13d, 1
0x18007189e  call    ??0GuidTrace@@QEAA@AEBU_GUID@@@Z; GuidTrace::GuidTrace(_GUID const &)
0x1800718a3  mov     rcx, rax; this
0x1800718a6  call    ?GetString@GuidTrace@@QEBAPEBDXZ; GuidTrace::GetString(void)
0x1800718ab  mov     rcx, cs:WPP_GLOBAL_Control
0x1800718b2  lea     r8, WPP_b8e9c5bb41d83a1fe5a50aa5287d6a19_Traceguids
0x1800718b9  mov     [rsp+500h+var_4D0], rbx; __int64
0x1800718be  mov     edx, 10Ah
0x1800718c3  mov     [rsp+500h+var_4D8], rax; __int64
0x1800718c8  mov     r9, rsi
0x1800718cb  mov     eax, dword ptr [rsp+500h+var_498]
0x1800718cf  mov     rcx, [rcx+0D8h]; LoggerHandle
0x1800718d6  mov     [rsp+500h+var_4E0], eax; char
0x1800718da  call    WPP_SF_qDsS
0x1800718df  mov     ebx, 208h
0x1800718e4  test    r13b, 1
0x1800718e8  jz      short loc_1800718F7
0x1800718ea  and     r13d, 0FFFFFFFEh
0x1800718ee  lea     rcx, [rbp+400h+var_480]; this
0x1800718f2  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x1800718f7  xor     edi, edi
0x1800718f9  jmp     loc_180071A01
0x1800718fe  mov     rdx, r15
0x180071901  call    ??$make_unique_nothrow@$$BY0A@U_GUID@@@wil@@YA?AV?$unique_ptr@$$BY0A@U_GUID@@U?$default_delete@$$BY0A@U_GUID@@@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<_GUID [0]>(unsigned __int64)
0x180071906  mov     rdx, rax
0x180071909  lea     rcx, [rsp+500h+var_498]
0x18007190e  call    ??4?$unique_ptr@$$BY0A@KU?$default_delete@$$BY0A@K@wistd@@@wistd@@QEAAAEAV01@$$QEAV01@@Z; wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>>::operator=(wistd::unique_ptr<ulong [0],wistd::default_delete<ulong [0]>> &&)
0x180071913  mov     rcx, [rsp+500h+var_490]; void *
0x180071918  mov     [rsp+500h+var_490], r12
0x18007191d  test    rcx, rcx
0x180071920  jz      short loc_180071927
0x180071922  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180071927  mov     r14, [rsp+500h+var_498]
0x18007192c  test    r14, r14
0x18007192f  jnz     short loc_18007194F
0x180071931  mov     eax, 8007000Eh
0x180071936  mov     edi, eax
0x180071938  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18007193f  jb      loc_180071B92
0x180071945  mov     edx, 108h
0x18007194a  jmp     loc_180071B74
0x18007194f  mov     rcx, [rsp+500h+var_4A8]
0x180071954  lea     rdx, FSSERVICE_CONFIGURATION_UPDATED_INTERFACECATEGORY_LIST
0x18007195b  mov     r9d, r15d
0x18007195e  mov     [rsp+500h+var_4B0], r12b
0x180071963  shl     r9d, 4
0x180071967  mov     r8, r14
0x18007196a  mov     qword ptr [rsp+500h+var_4E0], r12
0x18007196f  mov     rax, [rcx]
0x180071972  mov     rax, [rax+78h]
0x180071976  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007197b  mov     edi, eax
0x18007197d  test    eax, eax
0x18007197f  jns     loc_180071842
0x180071985  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
  ... truncated ...
```
