# FSSourceActivate::InternalInitialize(IFSClientContextInfo *,IFSSource *,__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001,IFSSource *)

- ea: `0x18003a914`
- end: `0x18003aff2`
- name: `?InternalInitialize@FSSourceActivate@@IEAAJPEAUIFSClientContextInfo@@PEAUIFSSource@@W4__MIDL___MIDL_itf_fsclienttypes_0000_0000_0001@@1@Z`
- size: `1758`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, reparse_path, registry_config, broker_com_uri`

## callers

- `0x18003a3cc`

## callees

- `0x1800041f0`
- `0x18000478c`
- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x180009fac`
- `0x18000a880`
- `0x18000a91c`
- `0x180017f60`
- `0x180028208`
- `0x18003a914`
- `0x18003b49c`
- `0x180047510`
- `0x18004d714`
- `0x18004d748`
- `0x18004f37c`
- `0x1800ea010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x18003abc0`
- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x18003abc0`
- `MFPlat!MFCreateAttributes` at `0x18003aadf`
- `MFPlat!MFCreateAttributes` at `0x18003aadf`

## pseudocode

```c
__int64 __fastcall FSSourceActivate::InternalInitialize(
        __int64 a1,
        struct IFSClientContextInfo *a2,
        __int64 a3,
        int a4,
        __int64 a5)
{
  char v6; // al
  BYTE *v10; // r15
  FSString *v11; // rax
  const char *String; // rax
  const char *v13; // rcx
  HRESULT v14; // eax
  int v15; // ebx
  __int64 v16; // rdx
  __int64 (__fastcall *v17)(__int64, __int64 *); // rbx
  __int64 v18; // rax
  _QWORD *v19; // r14
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, const IID *, __int64); // rbx
  __int64 v22; // rax
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rcx
  __int64 v24; // rax
  __int64 (__fastcall ***v25)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v26)(_QWORD, GUID *, void **); // rbx
  int v27; // eax
  __int64 v28; // rdx
  struct IMFSensorProfileCollection *v29; // rcx
  void *v30; // rbx
  __int64 v31; // rax
  __int64 (__fastcall *v32)(void *, GUID *, GUID *, struct IMFSensorProfileCollection **); // rdi
  struct IMFSensorProfileCollection *v33; // rcx
  struct IMFSensorProfileCollection *v34; // rdi
  __int64 (__fastcall *v35)(struct IMFSensorProfileCollection *, GUID *, __int64 *); // rbx
  const WCHAR *v36; // rax
  __int64 v37; // rbx
  const struct std::nothrow_t *unique; // rax
  const struct std::nothrow_t *v39; // rdx
  void *v40; // rcx
  const WCHAR *v41; // rax
  __int64 v42; // rdx
  const struct std::nothrow_t *v43; // rdx
  void *v45; // [rsp+40h] [rbp-31h] BYREF
  struct IMFSensorProfileCollection *v46; // [rsp+48h] [rbp-29h] BYREF
  struct IMFSensorProfileCollection *v47; // [rsp+50h] [rbp-21h] BYREF
  __int64 v48; // [rsp+58h] [rbp-19h] BYREF
  __int64 v49; // [rsp+60h] [rbp-11h] BYREF
  __int64 (__fastcall ***v50)(_QWORD, GUID *, void **); // [rsp+68h] [rbp-9h] BYREF
  PBYTE PropertyBuffer; // [rsp+70h] [rbp-1h] BYREF
  _BYTE v52[72]; // [rsp+78h] [rbp+7h] BYREF
  unsigned int v53; // [rsp+D8h] [rbp+67h] BYREF
  int v54; // [rsp+E8h] [rbp+77h]

  v54 = a4;
  v6 = 0;
  PropertyBuffer = 0;
  v53 = 0;
  v10 = 0;
  v49 = 0;
  v50 = 0;
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v11 = ClientContextInfoTrace::ClientContextInfoTrace((ClientContextInfoTrace *)v52, a2);
    String = FSString::GetString(v11);
    v13 = "shared";
    if ( a4 != 1 )
      v13 = "controller";
    WPP_SF_qsqs(*((_QWORD *)WPP_GLOBAL_Control + 27), (__int64)String, a3, (__int64)v13);
    v6 = 1;
  }
  if ( (v6 & 1) != 0 )
    FSString::~FSString((FSString *)v52, a2);
  if ( !a2 )
  {
    v14 = -2147024809;
    v15 = -2147024809;
    if ( g_wppLevels )
    {
      v16 = 34;
LABEL_10:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v16, WPP_5ad36017fe0530b92bc74bb758586919_Traceguids, a1, v14);
      goto LABEL_77;
    }
    goto LABEL_77;
  }
  if ( !a3 )
  {
    v14 = -2147024809;
    v15 = -2147024809;
    if ( g_wppLevels )
    {
      v16 = 35;
      goto LABEL_10;
    }
LABEL_77:
    if ( !byte_18010EC4D )
      goto LABEL_82;
    v42 = 53;
    goto LABEL_81;
  }
  if ( !a5 )
  {
    v14 = -2147024809;
    v15 = -2147024809;
    if ( g_wppLevels )
    {
      v16 = 36;
      goto LABEL_10;
    }
    goto LABEL_77;
  }
  v17 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)a3 + 48LL);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v49);
  v14 = v17(a3, &v49);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 37;
      goto LABEL_10;
    }
    goto LABEL_77;
  }
  if ( (unsigned __int8)byte_18010EC4D >= 8u )
  {
    v18 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 40LL))(v49);
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      38,
      (unsigned int)WPP_5ad36017fe0530b92bc74bb758586919_Traceguids,
      a1,
      v18);
  }
  v19 = (_QWORD *)(a1 + 64);
  wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(a1 + 64);
  v14 = MFCreateAttributes((IMFAttributes **)(a1 + 64), 4u);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 39;
      goto LABEL_10;
    }
    goto LABEL_77;
  }
  v14 = (*(__int64 (__fastcall **)(_QWORD, const IID *, const IID *))(*(_QWORD *)*v19 + 192LL))(
          *v19,
          &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE,
          &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 40;
      goto LABEL_10;
    }
    goto LABEL_77;
  }
  v20 = *v19;
  v21 = *(__int64 (__fastcall **)(__int64, const IID *, __int64))(*(_QWORD *)*v19 + 200LL);
  v22 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 40LL))(v49);
  v14 = v21(v20, &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK, v22);
  v15 = v14;
  if ( v14 < 0 )
  {
    if ( g_wppLevels )
    {
      v16 = 41;
      goto LABEL_10;
    }
    goto LABEL_77;
  }
  v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
  v50 = 0;
  if ( v23 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v23)[2])(v23);
  v24 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 40LL))(v49);
  if ( (int)MFCreateSensorGroupWithOptions(v24, 0, &v50) >= 0 )
  {
    v45 = 0;
    v47 = 0;
    v48 = 0;
    v46 = 0;
    v25 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v50;
    v26 = **v50;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v45);
    v27 = v26(v25, &GUID_fa993888_4383_415a_a930_dd472a8cf6f7, &v45);
    v15 = v27;
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_39:
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v46);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v48);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v47);
        wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v45);
        goto LABEL_77;
      }
      v28 = 42;
LABEL_38:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v28, WPP_5ad36017fe0530b92bc74bb758586919_Traceguids, a1, v27);
      goto LABEL_39;
    }
    v29 = v47;
    v30 = v45;
    v31 = *(_QWORD *)v45;
    v47 = 0;
    v32 = *(__int64 (__fastcall **)(void *, GUID *, GUID *, struct IMFSensorProfileCollection **))(v31 + 24);
    if ( v29 )
      (*(void (__fastcall **)(struct IMFSensorProfileCollection *))(*(_QWORD *)v29 + 16LL))(v29);
    v27 = v32(v30, &GUID_00000000_0000_0000_0000_000000000000, &GUID_c95ea55b_0187_48be_9353_8d2507662351, &v47);
    v15 = v27;
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v28 = 43;
      goto LABEL_38;
    }
    v33 = v46;
    v46 = 0;
    if ( v33 )
      (*(void (__fastcall **)(struct IMFSensorProfileCollection *))(*(_QWORD *)v33 + 16LL))(v33);
    v27 = FSCloneProfilesToMepProfiles(v47, L"PHSEQ", &v46);
    v15 = v27;
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v28 = 44;
      goto LABEL_38;
    }
    v34 = v46;
    v35 = **(__int64 (__fastcall ***)(struct IMFSensorProfileCollection *, GUID *, __int64 *))v46;
    wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&v48);
    v27 = v35(v34, &GUID_00000000_0000_0000_c000_000000000046, &v48);
    v15 = v27;
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v28 = 45;
      goto LABEL_38;
    }
    v27 = (*(__int64 (__fastcall **)(_QWORD, __int64 *, __int64))(*(_QWORD *)*v19 + 216LL))(
            *v19,
            MF_DEVICEMFT_SENSORPROFILE_COLLECTION,
            v48);
    v15 = v27;
    if ( v27 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_39;
      v28 = 46;
      goto LABEL_38;
    }
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v46);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v48);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v47);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v45);
  }
  v36 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 40LL))(v49);
  if ( (int)FSGetDeviceFriendlyName(v36, 0, 0, &v53) < 0 )
  {
    v14 = (*(__int64 (__fastcall **)(_QWORD, const IID *, const wchar_t *))(*(_QWORD *)*v19 + 200LL))(
            *v19,
            &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
            L"AV Stream Device");
    v15 = v14;
    if ( v14 < 0 )
    {
      if ( g_wppLevels )
      {
        v16 = 51;
        goto LABEL_10;
      }
      goto LABEL_77;
    }
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 52, WPP_5ad36017fe0530b92bc74bb758586919_Traceguids, a1);
  }
  else
  {
    v37 = v53;
    unique = (const struct std::nothrow_t *)wil::make_unique_nothrow<unsigned short [0]>(&v45, v53);
    wistd::unique_ptr<unsigned long [0],wistd::default_delete<unsigned long [0]>>::operator=(
      (void **)&PropertyBuffer,
      unique);
    v40 = v45;
    v45 = 0;
    if ( v40 )
      operator delete(v40, v39);
    v10 = PropertyBuffer;
    if ( !PropertyBuffer )
    {
      v15 = -2147024882;
      if ( g_wppLevels )
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          (unsigned int)((_DWORD)PropertyBuffer + 47),
          WPP_5ad36017fe0530b92bc74bb758586919_Traceguids,
          a1,
          -2147024882);
      goto LABEL_77;
    }
    memset_0(PropertyBuffer, 0, 2 * v37);
    v41 = (const WCHAR *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v49 + 40LL))(v49);
    v14 = FSGetDeviceFriendlyName(v41, v10, v53, &v53);
    v15 = v14;
    if ( v14 < 0 )
    {
      if ( g_wppLevels )
      {
        v16 = 48;
        goto LABEL_10;
      }
      goto LABEL_77;
    }
    v14 = (*(__int64 (__fastcall **)(_QWORD, const IID *, BYTE *))(*(_QWORD *)*v19 + 200LL))(
            *v19,
            &MF_DEVSOURCE_ATTRIBUTE_FRIENDLY_NAME,
            v10);
    v15 = v14;
    if ( v14 < 0 )
    {
      if ( g_wppLevels )
      {
        v16 = 49;
        goto LABEL_10;
      }
      goto LABEL_77;
    }
    if ( (unsigned __int8)byte_18010EC4D >= 8u )
      WPP_SF_qS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        50,
        (unsigned int)WPP_5ad36017fe0530b92bc74bb758586919_Traceguids,
        a1,
        (__int64)v10);
  }
  *(_DWORD *)(a1 + 104) = v54;
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((__int64 *)(a1 + 72), a3);
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((__int64 *)(a1 + 80), a5);
  wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=((__int64 *)(a1 + 88), (__int64)a2);
  if ( v15 < 0 )
    goto LABEL_77;
  if ( (unsigned __int8)byte_18010EC4D < 8u )
    goto LABEL_82;
  v42 = 54;
LABEL_81:
  WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 27), v42, WPP_5ad36017fe0530b92bc74bb758586919_Traceguids, a1, v15);
LABEL_82:
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>((__int64 *)&v50);
  wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&v49);
  if ( v10 )
    operator delete(v10, v43);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x18003a914  mov     [rsp-8+arg_0], rbx
0x18003a919  mov     [rsp-8+arg_18], r9d
0x18003a91e  push    rbp
0x18003a91f  push    rsi
0x18003a920  push    rdi
0x18003a921  push    r12
0x18003a923  push    r13
0x18003a925  push    r14
0x18003a927  push    r15
0x18003a929  lea     rbp, [rsp-1Fh]
0x18003a92e  sub     rsp, 90h
0x18003a935  xor     edi, edi
0x18003a937  mov     ebx, r9d
0x18003a93a  mov     eax, edi
0x18003a93c  mov     r12, r8
0x18003a93f  mov     [rbp+4Fh+arg_8], eax
0x18003a942  mov     r13, rdx
0x18003a945  mov     [rbp+4Fh+PropertyBuffer], rdi
0x18003a949  mov     rsi, rcx
0x18003a94c  mov     [rbp+4Fh+arg_8], edi
0x18003a94f  mov     r15d, edi
0x18003a952  mov     [rbp+4Fh+var_60], rdi
0x18003a956  mov     [rbp+4Fh+var_58], rdi
0x18003a95a  cmp     cs:byte_18010EC4D, 8
0x18003a961  lea     r14d, [rdi+1]
0x18003a965  jb      short loc_18003A9BF
0x18003a967  lea     rcx, [rbp+4Fh+var_48]; this
0x18003a96b  call    ??0ClientContextInfoTrace@@QEAA@PEAUIFSClientContextInfo@@@Z; ClientContextInfoTrace::ClientContextInfoTrace(IFSClientContextInfo *)
0x18003a970  mov     rcx, rax; this
0x18003a973  call    ?GetString@FSString@@QEBAPEBDXZ; FSString::GetString(void)
0x18003a978  lea     rdx, aController; "controller"
0x18003a97f  cmp     ebx, r14d
0x18003a982  lea     rcx, aShared; "shared"
0x18003a989  mov     r9, rsi
0x18003a98c  cmovnz  rcx, rdx
0x18003a990  lea     r8, WPP_5ad36017fe0530b92bc74bb758586919_Traceguids
0x18003a997  mov     [rsp+0C0h+var_90], rcx; __int64
0x18003a99c  lea     edx, [rdi+21h]
0x18003a99f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a9a6  mov     qword ptr [rsp+0C0h+var_98], r12; char
0x18003a9ab  mov     [rsp+0C0h+var_A0], rax; __int64
0x18003a9b0  mov     rcx, [rcx+0D8h]; LoggerHandle
0x18003a9b7  call    WPP_SF_qsqs
0x18003a9bc  mov     eax, r14d
0x18003a9bf  test    r14b, al
0x18003a9c2  jz      short loc_18003A9CD
0x18003a9c4  lea     rcx, [rbp+4Fh+var_48]; this
0x18003a9c8  call    ??1FSString@@QEAA@XZ; FSString::~FSString(void)
0x18003a9cd  test    r13, r13
0x18003a9d0  jnz     short loc_18003AA0D
0x18003a9d2  mov     eax, 80070057h
0x18003a9d7  mov     ebx, eax
0x18003a9d9  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18003a9e0  jb      loc_18003AF77
0x18003a9e6  lea     edx, [r13+22h]
0x18003a9ea  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18003a9ee  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a9f5  lea     r8, WPP_5ad36017fe0530b92bc74bb758586919_Traceguids
0x18003a9fc  mov     r9, rsi
0x18003a9ff  mov     rcx, [rcx+10h]
0x18003aa03  call    WPP_SF_qD
0x18003aa08  jmp     loc_18003AF77
0x18003aa0d  test    r12, r12
0x18003aa10  jnz     short loc_18003AA2D
0x18003aa12  mov     eax, 80070057h
0x18003aa17  mov     ebx, eax
0x18003aa19  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18003aa20  jb      loc_18003AF77
0x18003aa26  lea     edx, [r12+23h]
0x18003aa2b  jmp     short loc_18003A9EA
0x18003aa2d  cmp     [rbp+4Fh+arg_20], rdi
0x18003aa31  jnz     short loc_18003AA4E
0x18003aa33  mov     eax, 80070057h
0x18003aa38  mov     ebx, eax
0x18003aa3a  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18003aa41  jb      loc_18003AF77
0x18003aa47  mov     edx, 24h ; '$'
0x18003aa4c  jmp     short loc_18003A9EA
0x18003aa4e  mov     rax, [r12]
0x18003aa52  lea     rcx, [rbp+4Fh+var_60]
0x18003aa56  mov     rbx, [rax+30h]
0x18003aa5a  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003aa5f  lea     rdx, [rbp+4Fh+var_60]
0x18003aa63  mov     rcx, r12
0x18003aa66  mov     rax, rbx
0x18003aa69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aa6e  mov     ebx, eax
0x18003aa70  test    eax, eax
0x18003aa72  jns     short loc_18003AA8B
0x18003aa74  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, r14b; MFWppLevels g_wppLevels
0x18003aa7b  jb      loc_18003AF77
0x18003aa81  mov     edx, 25h ; '%'
0x18003aa86  jmp     loc_18003A9EA
0x18003aa8b  cmp     cs:byte_18010EC4D, 8
0x18003aa92  jb      short loc_18003AACB
0x18003aa94  mov     rcx, [rbp+4Fh+var_60]
0x18003aa98  mov     rax, [rcx]
0x18003aa9b  mov     rax, [rax+28h]
0x18003aa9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aaa4  mov     rcx, cs:WPP_GLOBAL_Control
0x18003aaab  lea     r8, WPP_5ad36017fe0530b92bc74bb758586919_Traceguids
0x18003aab2  mov     edx, 26h ; '&'
0x18003aab7  mov     [rsp+0C0h+var_A0], rax
0x18003aabc  mov     r9, rsi
0x18003aabf  mov     rcx, [rcx+0D8h]
0x18003aac6  call    WPP_SF_qS
0x18003aacb  lea     r14, [rsi+40h]
0x18003aacf  mov     rcx, r14
0x18003aad2  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003aad7  mov     edx, 4; cInitialSize
0x18003aadc  mov     rcx, r14; ppMFAttributes
0x18003aadf  call    cs:__imp_MFCreateAttributes
0x18003aae5  mov     ebx, eax
0x18003aae7  test    eax, eax
0x18003aae9  jns     short loc_18003AB02
0x18003aaeb  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003aaf2  jb      loc_18003AF77
0x18003aaf8  mov     edx, 27h ; '''
0x18003aafd  jmp     loc_18003A9EA
0x18003ab02  mov     rcx, [r14]
0x18003ab05  lea     r8, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID
0x18003ab0c  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE
0x18003ab13  mov     rax, [rcx]
0x18003ab16  mov     rax, [rax+0C0h]
0x18003ab1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab22  mov     ebx, eax
0x18003ab24  test    eax, eax
0x18003ab26  jns     short loc_18003AB3F
0x18003ab28  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ab2f  jb      loc_18003AF77
0x18003ab35  mov     edx, 28h ; '('
0x18003ab3a  jmp     loc_18003A9EA
0x18003ab3f  mov     rdi, [r14]
0x18003ab42  mov     rcx, [rbp+4Fh+var_60]
0x18003ab46  mov     rax, [rdi]
0x18003ab49  mov     rdx, [rcx]
0x18003ab4c  mov     rbx, [rax+0C8h]
0x18003ab53  mov     rax, [rdx+28h]
0x18003ab57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab5c  mov     r8, rax
0x18003ab5f  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x18003ab66  mov     rax, rbx
0x18003ab69  mov     rcx, rdi
0x18003ab6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab71  xor     edi, edi
0x18003ab73  mov     ebx, eax
0x18003ab75  test    eax, eax
0x18003ab77  jns     short loc_18003AB8E
0x18003ab79  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ab80  jb      loc_18003AF77
0x18003ab86  lea     edx, [rdi+29h]
0x18003ab89  jmp     loc_18003A9EA
0x18003ab8e  mov     rcx, [rbp+4Fh+var_58]
0x18003ab92  mov     [rbp+4Fh+var_58], rdi
0x18003ab96  test    rcx, rcx
0x18003ab99  jz      short loc_18003ABA7
0x18003ab9b  mov     rax, [rcx]
0x18003ab9e  mov     rax, [rax+10h]
0x18003aba2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aba7  mov     rcx, [rbp+4Fh+var_60]
0x18003abab  mov     rax, [rcx]
0x18003abae  mov     rax, [rax+28h]
0x18003abb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abb7  lea     r8, [rbp+4Fh+var_58]
0x18003abbb  xor     edx, edx
0x18003abbd  mov     rcx, rax
0x18003abc0  call    cs:__imp_MFCreateSensorGroupWithOptions
0x18003abc6  test    eax, eax
0x18003abc8  js      loc_18003ADAA
0x18003abce  mov     [rbp+4Fh+var_80], rdi
0x18003abd2  lea     rcx, [rbp+4Fh+var_80]
0x18003abd6  mov     [rbp+4Fh+var_70], rdi
0x18003abda  mov     [rbp+4Fh+var_68], rdi
0x18003abde  mov     [rbp+4Fh+var_78], rdi
0x18003abe2  mov     rdi, [rbp+4Fh+var_58]
0x18003abe6  mov     rax, [rdi]
0x18003abe9  mov     rbx, [rax]
0x18003abec  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003abf1  lea     r8, [rbp+4Fh+var_80]
0x18003abf5  mov     rcx, rdi
0x18003abf8  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x18003abff  mov     rax, rbx
0x18003ac02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac07  mov     ebx, eax
0x18003ac09  test    eax, eax
0x18003ac0b  jns     short loc_18003AC62
0x18003ac0d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ac14  jb      short loc_18003AC39
0x18003ac16  mov     edx, 2Ah ; '*'
0x18003ac1b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003ac22  lea     r8, WPP_5ad36017fe0530b92bc74bb758586919_Traceguids
0x18003ac29  mov     r9, rsi
0x18003ac2c  mov     dword ptr [rsp+0C0h+var_A0], eax
0x18003ac30  mov     rcx, [rcx+10h]
0x18003ac34  call    WPP_SF_qD
0x18003ac39  lea     rcx, [rbp+4Fh+var_78]; void *
0x18003ac3d  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003ac42  lea     rcx, [rbp+4Fh+var_68]; void *
0x18003ac46  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003ac4b  lea     rcx, [rbp+4Fh+var_70]; void *
0x18003ac4f  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003ac54  lea     rcx, [rbp+4Fh+var_80]; void *
0x18003ac58  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003ac5d  jmp     loc_18003AF77
0x18003ac62  mov     rcx, [rbp+4Fh+var_70]
0x18003ac66  mov     rbx, [rbp+4Fh+var_80]
0x18003ac6a  mov     rax, [rbx]
0x18003ac6d  mov     [rbp+4Fh+var_70], r15
0x18003ac71  mov     rdi, [rax+18h]
0x18003ac75  test    rcx, rcx
0x18003ac78  jz      short loc_18003AC86
0x18003ac7a  mov     rdx, [rcx]
0x18003ac7d  mov     rax, [rdx+10h]
0x18003ac81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac86  lea     r9, [rbp+4Fh+var_70]
0x18003ac8a  mov     rcx, rbx
0x18003ac8d  lea     r8, _GUID_c95ea55b_0187_48be_9353_8d2507662351
0x18003ac94  mov     rax, rdi
0x18003ac97  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x18003ac9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aca3  xor     edi, edi
0x18003aca5  mov     ebx, eax
0x18003aca7  test    eax, eax
0x18003aca9  jns     short loc_18003ACBC
0x18003acab  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003acb2  jb      short loc_18003AC39
0x18003acb4  lea     edx, [rdi+2Bh]
0x18003acb7  jmp     loc_18003AC1B
0x18003acbc  mov     rcx, [rbp+4Fh+var_78]
0x18003acc0  mov     [rbp+4Fh+var_78], rdi
0x18003acc4  test    rcx, rcx
0x18003acc7  jz      short loc_18003ACD5
0x18003acc9  mov     rax, [rcx]
0x18003accc  mov     rax, [rax+10h]
0x18003acd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acd5  mov     rcx, [rbp+4Fh+var_70]; struct IMFSensorProfileCollection *
0x18003acd9  lea     r8, [rbp+4Fh+var_78]; struct IMFSensorProfileCollection **
0x18003acdd  lea     rdx, aPhseq; "PHSEQ"
0x18003ace4  call    ?FSCloneProfilesToMepProfiles@@YAJPEAUIMFSensorProfileCollection@@PEBGPEAPEAU1@@Z; FSCloneProfilesToMepProfiles(IMFSensorProfileCollection *,ushort const *,IMFSensorProfileCollection * *)
0x18003ace9  mov     ebx, eax
0x18003aceb  test    eax, eax
0x18003aced  jns     short loc_18003AD06
0x18003acef  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003acf6  jb      loc_18003AC39
0x18003acfc  mov     edx, 2Ch ; ','
0x18003ad01  jmp     loc_18003AC1B
0x18003ad06  mov     rdi, [rbp+4Fh+var_78]
0x18003ad0a  lea     rcx, [rbp+4Fh+var_68]
0x18003ad0e  mov     rax, [rdi]
0x18003ad11  mov     rbx, [rax]
0x18003ad14  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x18003ad19  lea     r8, [rbp+4Fh+var_68]
0x18003ad1d  mov     rcx, rdi
0x18003ad20  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18003ad27  mov     rax, rbx
0x18003ad2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad2f  xor     edi, edi
0x18003ad31  mov     ebx, eax
0x18003ad33  test    eax, eax
0x18003ad35  jns     short loc_18003AD4C
0x18003ad37  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ad3e  jb      loc_18003AC39
0x18003ad44  lea     edx, [rdi+2Dh]
0x18003ad47  jmp     loc_18003AC1B
0x18003ad4c  mov     rcx, [r14]
0x18003ad4f  lea     rdx, MF_DEVICEMFT_SENSORPROFILE_COLLECTION
0x18003ad56  mov     r8, [rbp+4Fh+var_68]
0x18003ad5a  mov     rax, [rcx]
0x18003ad5d  mov     rax, [rax+0D8h]
0x18003ad64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad69  mov     ebx, eax
0x18003ad6b  test    eax, eax
0x18003ad6d  jns     short loc_18003AD86
0x18003ad6f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18003ad76  jb      loc_18003AC39
0x18003ad7c  mov     edx, 2Eh ; '.'
0x18003ad81  jmp     loc_18003AC1B
0x18003ad86  lea     rcx, [rbp+4Fh+var_78]; void *
0x18003ad8a  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003ad8f  lea     rcx, [rbp+4Fh+var_68]; void *
0x18003ad93  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003ad98  lea     rcx, [rbp+4Fh+var_70]; void *
0x18003ad9c  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003ada1  lea     rcx, [rbp+4Fh+var_80]; void *
0x18003ada5  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x18003adaa  mov     rcx, [rbp+4Fh+var_60]
0x18003adae  mov     rax, [rcx]
0x18003adb1  mov     rax, [rax+28h]
0x18003adb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003adba  mov     rcx, rax; pszDeviceInterface
0x18003adbd  lea     r9, [rbp+4Fh+arg_8]; unsigned int *
0x18003adc1  xor     r8d, r8d; unsigned int
0x18003adc4  xor     edx, edx; PropertyBuffer
0x18003adc6  call    ?FSGetDeviceFriendlyName@@YAJPEBGPEAGKPEAK@Z; FSGetDeviceFriendlyName(ushort const *,ushort *,ulong,ulong *)
0x18003adcb  test    eax, eax
0x18003adcd  js      loc_18003AEE4
0x18003add3  mov     ebx, [rbp+4Fh+arg_8]
0x18003add6  lea     rcx, [rbp+4Fh+var_80]
0x18003adda  mov     edx, ebx
0x18003addc  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
  ... truncated ...
```
