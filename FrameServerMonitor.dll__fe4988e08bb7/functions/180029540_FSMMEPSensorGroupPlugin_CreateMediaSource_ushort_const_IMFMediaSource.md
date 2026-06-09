# FSMMEPSensorGroupPlugin::CreateMediaSource(ushort const *,IMFMediaSource * *)

- ea: `0x180029540`
- end: `0x180029c78`
- name: `?CreateMediaSource@FSMMEPSensorGroupPlugin@@UEAAJPEBGPEAPEAUIMFMediaSource@@@Z`
- size: `1848`
- prototype: `__int64 __fastcall(FSMMEPSensorGroupPlugin *this, const char *, struct IMFMediaSource **)`
- caller_count: `0`
- callee_count: `8`
- tags: `reparse_path, registry_config, loader_planting, broker_com_uri`

## callees

- `0x180005f98`
- `0x180006a68`
- `0x180006a98`
- `0x180006ae8`
- `0x18000d62c`
- `0x180029540`
- `0x1800440a0`
- `0x18004d010`

## import_xrefs

- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x18002973e`
- `MFSENSORGROUP!MFCreateSensorGroupWithOptions` at `0x18002973e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029a36`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029a36`
- `MF!MFCreateDeviceSourceActivate` at `0x180029929`
- `MF!MFCreateDeviceSourceActivate` at `0x180029929`
- `MFPlat!MFCreateAttributes` at `0x180029644`
- `MFPlat!MFCreateAttributes` at `0x180029644`
- `MFPlat!MFCreateCollection` at `0x180029969`
- `MFPlat!MFCreateCollection` at `0x180029969`

## pseudocode

```c
__int64 __fastcall FSMMEPSensorGroupPlugin::CreateMediaSource(
        FSMMEPSensorGroupPlugin *this,
        const char *a2,
        struct IMFMediaSource **a3)
{
  const char *v6; // r13
  const char *v7; // rax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HRESULT v10; // eax
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  __int64 v14; // rdx
  struct IMFSensorProfileCollection *v15; // rcx
  _QWORD *v16; // rbx
  __int64 v17; // rax
  __int64 (__fastcall *v18)(_QWORD *, GUID *, GUID *, struct IMFSensorProfileCollection **); // rdi
  struct IMFSensorProfileCollection *v19; // rcx
  struct IMFSensorProfileCollection *v20; // rdi
  __int64 (__fastcall *v21)(struct IMFSensorProfileCollection *, GUID *, __int64 *); // rbx
  IMFActivate *v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rcx
  IMFActivate *v24; // rdi
  HRESULT (__stdcall *QueryInterface)(IMFActivate *, const IID *const, void **); // rbx
  LPVOID v26; // rcx
  __int64 (__fastcall ***v27)(_QWORD, _QWORD, _QWORD); // rdi
  __int64 (__fastcall *v28)(_QWORD, GUID *, __int64 *); // rbx
  __int64 v30; // [rsp+30h] [rbp-40h] BYREF
  LPVOID ppv; // [rsp+38h] [rbp-38h] BYREF
  _QWORD *v32; // [rsp+40h] [rbp-30h] BYREF
  IMFAttributes *ppMFAttributes; // [rsp+48h] [rbp-28h] BYREF
  __int64 (__fastcall ***v34)(_QWORD, GUID *, __int64 *); // [rsp+50h] [rbp-20h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, _QWORD **); // [rsp+58h] [rbp-18h] BYREF
  IMFActivate *ppActivate[2]; // [rsp+60h] [rbp-10h] BYREF
  struct IMFSensorProfileCollection *v37; // [rsp+B8h] [rbp+48h] BYREF
  struct IMFSensorProfileCollection *v38; // [rsp+C8h] [rbp+58h] BYREF

  ppActivate[0] = 0;
  ppv = 0;
  ppMFAttributes = 0;
  v34 = 0;
  v30 = 0;
  v35 = 0;
  v6 = L"<nullptr>";
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
  {
    v7 = L"<nullptr>";
    if ( a2 )
      v7 = a2;
    WPP_SF_qS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      19,
      (unsigned int)WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids,
      (_DWORD)this,
      (__int64)v7);
  }
  if ( !a2 )
  {
    v8 = -2147024809;
    if ( !g_wppLevels )
      goto LABEL_93;
    v9 = 20;
    goto LABEL_8;
  }
  if ( !a3 )
  {
    v8 = -2147467261;
    if ( g_wppLevels )
    {
      v9 = 21;
LABEL_8:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v9, WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids, this, v8);
      goto LABEL_93;
    }
    goto LABEL_93;
  }
  *a3 = 0;
  if ( *((_QWORD *)this + 7) == *(_QWORD *)&GUID_00000000_0000_0000_0000_000000000000.Data1
    && *((_QWORD *)this + 8) == *(_QWORD *)GUID_00000000_0000_0000_0000_000000000000.Data4 )
  {
    v8 = -1072875854;
    if ( g_wppLevels )
    {
      v9 = 22;
      goto LABEL_8;
    }
LABEL_93:
    if ( byte_18005E5A5 )
    {
      if ( a2 )
        v6 = a2;
      WPP_SF_qDS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        43,
        (unsigned int)WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids,
        (_DWORD)this,
        v8,
        (__int64)v6);
    }
    goto LABEL_99;
  }
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&ppMFAttributes);
  v10 = MFCreateAttributes(&ppMFAttributes, 3u);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 23;
LABEL_92:
    WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids, this, v10);
    goto LABEL_93;
  }
  v10 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, const IID *))ppMFAttributes->lpVtbl->SetGUID)(
          ppMFAttributes,
          &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE,
          &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 24;
    goto LABEL_92;
  }
  v10 = ((__int64 (__fastcall *)(IMFAttributes *, const IID *, const char *))ppMFAttributes->lpVtbl->SetString)(
          ppMFAttributes,
          &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
          a2);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 25;
    goto LABEL_92;
  }
  v10 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUINT32)(
          ppMFAttributes,
          MF_DEVICESOURCE_MEP_SENSORGROUP_ACTIVATION,
          1);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 26;
    goto LABEL_92;
  }
  v12 = (__int64)v35;
  v35 = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( (int)MFCreateSensorGroupWithOptions(a2, 0, &v35) >= 0 )
  {
    v32 = 0;
    v38 = 0;
    v37 = 0;
    v13 = (**v35)(v35, &GUID_fa993888_4383_415a_a930_dd472a8cf6f7, &v32);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
      {
LABEL_35:
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v37);
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v38);
        wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v32);
        goto LABEL_93;
      }
      v14 = 27;
LABEL_34:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v14, WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids, this, v13);
      goto LABEL_35;
    }
    v15 = v38;
    v16 = v32;
    v17 = *v32;
    v38 = 0;
    v18 = *(__int64 (__fastcall **)(_QWORD *, GUID *, GUID *, struct IMFSensorProfileCollection **))(v17 + 24);
    if ( v15 )
      (*(void (__fastcall **)(struct IMFSensorProfileCollection *))(*(_QWORD *)v15 + 16LL))(v15);
    v13 = v18(v16, &GUID_00000000_0000_0000_0000_000000000000, &GUID_c95ea55b_0187_48be_9353_8d2507662351, &v38);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_35;
      v14 = 28;
      goto LABEL_34;
    }
    v19 = v37;
    v37 = 0;
    if ( v19 )
      (*(void (__fastcall **)(struct IMFSensorProfileCollection *))(*(_QWORD *)v19 + 16LL))(v19);
    v13 = FSCloneProfilesToMepProfiles(v38, L"PHSEQ", &v37);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_35;
      v14 = 29;
      goto LABEL_34;
    }
    v20 = v37;
    v21 = **(__int64 (__fastcall ***)(struct IMFSensorProfileCollection *, GUID *, __int64 *))v37;
    wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v30);
    v13 = v21(v20, &GUID_00000000_0000_0000_c000_000000000046, &v30);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_35;
      v14 = 30;
      goto LABEL_34;
    }
    v13 = ((__int64 (__fastcall *)(IMFAttributes *, __int64 *, __int64))ppMFAttributes->lpVtbl->SetUnknown)(
            ppMFAttributes,
            MF_DEVICEMFT_SENSORPROFILE_COLLECTION,
            v30);
    v8 = v13;
    if ( v13 < 0 )
    {
      if ( !g_wppLevels )
        goto LABEL_35;
      v14 = 31;
      goto LABEL_34;
    }
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v37);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v38);
    wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v32);
  }
  v22 = ppActivate[0];
  ppActivate[0] = 0;
  if ( v22 )
    ((void (__fastcall *)(IMFActivate *))v22->lpVtbl->Release)(v22);
  v10 = MFCreateDeviceSourceActivate(ppMFAttributes, ppActivate);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 32;
    goto LABEL_92;
  }
  v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
  v34 = 0;
  if ( v23 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v23)[2])(v23);
  v10 = MFCreateCollection(&v34);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 33;
    goto LABEL_92;
  }
  v24 = ppActivate[0];
  QueryInterface = ppActivate[0]->lpVtbl->QueryInterface;
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v30);
  v10 = ((__int64 (__fastcall *)(IMFActivate *, GUID *, __int64 *))QueryInterface)(
          v24,
          &GUID_00000000_0000_0000_c000_000000000046,
          &v30);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 34;
    goto LABEL_92;
  }
  v10 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64))(*v34)[5])(v34, v30);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 35;
    goto LABEL_92;
  }
  v26 = ppv;
  ppv = 0;
  if ( v26 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v26 + 16LL))(v26);
  v10 = CoCreateInstance((const IID *const)((char *)this + 56), 0, 1u, &GUID_7fee9e9a_4a89_47a6_899c_b6a53a70fb67, &ppv);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 36;
    goto LABEL_92;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, const IID *, const IID *))(*(_QWORD *)ppv + 192LL))(
          ppv,
          &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE,
          &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 37;
    goto LABEL_92;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, const IID *, const char *))(*(_QWORD *)ppv + 200LL))(
          ppv,
          &MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK,
          a2);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 38;
    goto LABEL_92;
  }
  v27 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v34;
  v28 = **v34;
  wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(&v30);
  v10 = v28(v27, &GUID_00000000_0000_0000_c000_000000000046, &v30);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 39;
    goto LABEL_92;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64))(*(_QWORD *)ppv + 216LL))(
          ppv,
          MF_VIRTUALCAMERA_ASSOCIATED_CAMERA_SOURCES,
          v30);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 40;
    goto LABEL_92;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, __int64 *, __int64))(*(_QWORD *)ppv + 168LL))(
          ppv,
          MF_MEPCMS_PROFILESUPPORT_FLAG,
          1);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 41;
    goto LABEL_92;
  }
  v10 = (*(__int64 (__fastcall **)(LPVOID, GUID *, struct IMFMediaSource **))(*(_QWORD *)ppv + 264LL))(
          ppv,
          &GUID_279a808d_aec7_40c8_9c6b_a6b492c78a66,
          a3);
  v8 = v10;
  if ( v10 < 0 )
  {
    if ( !g_wppLevels )
      goto LABEL_93;
    v11 = 42;
    goto LABEL_92;
  }
  if ( (unsigned __int8)byte_18005E5A5 >= 8u )
    WPP_SF_qDS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      44,
      (unsigned int)WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids,
      (_DWORD)this,
      v10,
      (__int64)a2);
LABEL_99:
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v35);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(&v30);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&v34);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppMFAttributes);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)&ppv);
  wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>((__int64 *)ppActivate);
  return v8;
}

```

## disassembly

```asm
0x180029540  mov     [rsp-38h+arg_0], rbx
0x180029545  push    rbp
0x180029546  push    rsi
0x180029547  push    rdi
0x180029548  push    r12
0x18002954a  push    r13
0x18002954c  push    r14
0x18002954e  push    r15
0x180029550  mov     rbp, rsp
0x180029553  sub     rsp, 70h
0x180029557  xor     edi, edi
0x180029559  mov     r12, r8
0x18002955c  mov     [rbp+ppActivate], rdi
0x180029560  mov     r14, rdx
0x180029563  mov     [rbp+var_38], rdi
0x180029567  mov     rsi, rcx
0x18002956a  mov     [rbp+ppMFAttributes], rdi
0x18002956e  mov     [rbp+var_20], rdi
0x180029572  mov     [rbp+var_40], rdi
0x180029576  mov     [rbp+var_18], rdi
0x18002957a  cmp     cs:byte_18005E5A5, 8
0x180029581  lea     r13, aNullptr; "<nullptr>"
0x180029588  jb      short loc_1800295B9
0x18002958a  mov     r9, rcx
0x18002958d  lea     r8, WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids
0x180029594  mov     rcx, cs:WPP_GLOBAL_Control
0x18002959b  test    rdx, rdx
0x18002959e  mov     rax, r13
0x1800295a1  cmovnz  rax, rdx
0x1800295a5  lea     edx, [rdi+13h]
0x1800295a8  mov     [rsp+70h+ppv], rax
0x1800295ad  mov     rcx, [rcx+0D8h]
0x1800295b4  call    WPP_SF_qS
0x1800295b9  test    r14, r14
0x1800295bc  jnz     short loc_1800295DD
0x1800295be  mov     ebx, 80070057h
0x1800295c3  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800295ca  jb      loc_180029BD4
0x1800295d0  lea     edx, [r14+14h]
0x1800295d4  mov     dword ptr [rsp+70h+ppv], ebx
0x1800295d8  jmp     loc_180029BBA
0x1800295dd  test    r12, r12
0x1800295e0  jnz     short loc_1800295FB
0x1800295e2  mov     ebx, 80004003h
0x1800295e7  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800295ee  jb      loc_180029BD4
0x1800295f4  lea     edx, [r12+15h]
0x1800295f9  jmp     short loc_1800295D4
0x1800295fb  mov     [r12], rdi
0x1800295ff  mov     rax, [rsi+38h]
0x180029603  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data1
0x18002960a  jnz     short loc_180029632
0x18002960c  mov     rax, [rsi+40h]
0x180029610  cmp     rax, qword ptr cs:_GUID_00000000_0000_0000_0000_000000000000.Data4
0x180029617  jnz     short loc_180029632
0x180029619  mov     ebx, 0C00D36B2h
0x18002961e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029625  jb      loc_180029BD4
0x18002962b  mov     edx, 16h
0x180029630  jmp     short loc_1800295D4
0x180029632  lea     rcx, [rbp+ppMFAttributes]
0x180029636  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18002963b  mov     edx, 3; cInitialSize
0x180029640  lea     rcx, [rbp+ppMFAttributes]; ppMFAttributes
0x180029644  call    cs:__imp_MFCreateAttributes
0x18002964a  mov     ebx, eax
0x18002964c  test    eax, eax
0x18002964e  jns     short loc_180029667
0x180029650  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029657  jb      loc_180029BD4
0x18002965d  mov     edx, 17h
0x180029662  jmp     loc_180029BB6
0x180029667  mov     rcx, [rbp+ppMFAttributes]
0x18002966b  lea     r8, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_GUID
0x180029672  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE
0x180029679  mov     rax, [rcx]
0x18002967c  mov     rax, [rax+0C0h]
0x180029683  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029688  mov     ebx, eax
0x18002968a  test    eax, eax
0x18002968c  jns     short loc_1800296A5
0x18002968e  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029695  jb      loc_180029BD4
0x18002969b  mov     edx, 18h
0x1800296a0  jmp     loc_180029BB6
0x1800296a5  mov     rcx, [rbp+ppMFAttributes]
0x1800296a9  lea     rdx, MF_DEVSOURCE_ATTRIBUTE_SOURCE_TYPE_VIDCAP_SYMBOLIC_LINK
0x1800296b0  mov     r8, r14
0x1800296b3  mov     rax, [rcx]
0x1800296b6  mov     rax, [rax+0C8h]
0x1800296bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296c2  mov     ebx, eax
0x1800296c4  test    eax, eax
0x1800296c6  jns     short loc_1800296DF
0x1800296c8  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800296cf  jb      loc_180029BD4
0x1800296d5  mov     edx, 19h
0x1800296da  jmp     loc_180029BB6
0x1800296df  mov     rcx, [rbp+ppMFAttributes]
0x1800296e3  lea     rdx, MF_DEVICESOURCE_MEP_SENSORGROUP_ACTIVATION
0x1800296ea  mov     r8d, 1
0x1800296f0  mov     rax, [rcx]
0x1800296f3  mov     rax, [rax+0A8h]
0x1800296fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800296ff  mov     ebx, eax
0x180029701  test    eax, eax
0x180029703  jns     short loc_18002971C
0x180029705  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002970c  jb      loc_180029BD4
0x180029712  mov     edx, 1Ah
0x180029717  jmp     loc_180029BB6
0x18002971c  mov     rcx, [rbp+var_18]
0x180029720  mov     [rbp+var_18], rdi
0x180029724  test    rcx, rcx
0x180029727  jz      short loc_180029735
0x180029729  mov     rax, [rcx]
0x18002972c  mov     rax, [rax+10h]
0x180029730  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029735  lea     r8, [rbp+var_18]
0x180029739  xor     edx, edx
0x18002973b  mov     rcx, r14
0x18002973e  call    cs:__imp_MFCreateSensorGroupWithOptions
0x180029744  test    eax, eax
0x180029746  js      loc_180029908
0x18002974c  mov     rcx, [rbp+var_18]
0x180029750  lea     r8, [rbp+var_30]
0x180029754  mov     [rbp+var_30], rdi
0x180029758  lea     rdx, _GUID_fa993888_4383_415a_a930_dd472a8cf6f7
0x18002975f  mov     [rbp+arg_18], rdi
0x180029763  mov     [rbp+arg_8], rdi
0x180029767  mov     rax, [rcx]
0x18002976a  mov     rax, [rax]
0x18002976d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029772  mov     ebx, eax
0x180029774  test    eax, eax
0x180029776  jns     short loc_1800297C4
0x180029778  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002977f  jb      short loc_1800297A4
0x180029781  mov     edx, 1Bh
0x180029786  mov     rcx, cs:WPP_GLOBAL_Control
0x18002978d  lea     r8, WPP_dd810a671eb3341ab318e0990182c0d4_Traceguids
0x180029794  mov     r9, rsi
0x180029797  mov     dword ptr [rsp+70h+ppv], eax
0x18002979b  mov     rcx, [rcx+10h]
0x18002979f  call    WPP_SF_qD
0x1800297a4  lea     rcx, [rbp+arg_8]
0x1800297a8  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800297ad  lea     rcx, [rbp+arg_18]
0x1800297b1  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800297b6  lea     rcx, [rbp+var_30]
0x1800297ba  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800297bf  jmp     loc_180029BD4
0x1800297c4  mov     rcx, [rbp+arg_18]
0x1800297c8  mov     rbx, [rbp+var_30]
0x1800297cc  mov     rax, [rbx]
0x1800297cf  mov     [rbp+arg_18], 0
0x1800297d7  mov     rdi, [rax+18h]
0x1800297db  test    rcx, rcx
0x1800297de  jz      short loc_1800297EC
0x1800297e0  mov     rdx, [rcx]
0x1800297e3  mov     rax, [rdx+10h]
0x1800297e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800297ec  lea     r9, [rbp+arg_18]
0x1800297f0  mov     rcx, rbx
0x1800297f3  lea     r8, _GUID_c95ea55b_0187_48be_9353_8d2507662351
0x1800297fa  mov     rax, rdi
0x1800297fd  lea     rdx, _GUID_00000000_0000_0000_0000_000000000000
0x180029804  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029809  xor     edi, edi
0x18002980b  mov     ebx, eax
0x18002980d  test    eax, eax
0x18002980f  jns     short loc_180029822
0x180029811  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x180029818  jb      short loc_1800297A4
0x18002981a  lea     edx, [rdi+1Ch]
0x18002981d  jmp     loc_180029786
0x180029822  mov     rcx, [rbp+arg_8]
0x180029826  mov     [rbp+arg_8], rdi
0x18002982a  test    rcx, rcx
0x18002982d  jz      short loc_18002983B
0x18002982f  mov     rax, [rcx]
0x180029832  mov     rax, [rax+10h]
0x180029836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002983b  mov     rcx, [rbp+arg_18]; struct IMFSensorProfileCollection *
0x18002983f  lea     r8, [rbp+arg_8]; struct IMFSensorProfileCollection **
0x180029843  lea     rdx, aPhseq; "PHSEQ"
0x18002984a  call    ?FSCloneProfilesToMepProfiles@@YAJPEAUIMFSensorProfileCollection@@PEBGPEAPEAU1@@Z; FSCloneProfilesToMepProfiles(IMFSensorProfileCollection *,ushort const *,IMFSensorProfileCollection * *)
0x18002984f  mov     ebx, eax
0x180029851  test    eax, eax
0x180029853  jns     short loc_18002986C
0x180029855  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002985c  jb      loc_1800297A4
0x180029862  mov     edx, 1Dh
0x180029867  jmp     loc_180029786
0x18002986c  mov     rdi, [rbp+arg_8]
0x180029870  lea     rcx, [rbp+var_40]
0x180029874  mov     rax, [rdi]
0x180029877  mov     rbx, [rax]
0x18002987a  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18002987f  lea     r8, [rbp+var_40]
0x180029883  mov     rcx, rdi
0x180029886  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x18002988d  mov     rax, rbx
0x180029890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029895  xor     edi, edi
0x180029897  mov     ebx, eax
0x180029899  test    eax, eax
0x18002989b  jns     short loc_1800298B2
0x18002989d  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800298a4  jb      loc_1800297A4
0x1800298aa  lea     edx, [rdi+1Eh]
0x1800298ad  jmp     loc_180029786
0x1800298b2  mov     rcx, [rbp+ppMFAttributes]
0x1800298b6  lea     rdx, MF_DEVICEMFT_SENSORPROFILE_COLLECTION
0x1800298bd  mov     r8, [rbp+var_40]
0x1800298c1  mov     rax, [rcx]
0x1800298c4  mov     rax, [rax+0D8h]
0x1800298cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800298d0  mov     ebx, eax
0x1800298d2  test    eax, eax
0x1800298d4  jns     short loc_1800298ED
0x1800298d6  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800298dd  jb      loc_1800297A4
0x1800298e3  mov     edx, 1Fh
0x1800298e8  jmp     loc_180029786
0x1800298ed  lea     rcx, [rbp+arg_8]
0x1800298f1  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800298f6  lea     rcx, [rbp+arg_18]
0x1800298fa  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x1800298ff  lea     rcx, [rbp+var_30]
0x180029903  call    ??1?$com_ptr_t@UIFSD3DProxy@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>::~com_ptr_t<IFSD3DProxy,wil::err_returncode_policy>(void)
0x180029908  mov     rcx, [rbp+ppActivate]
0x18002990c  mov     [rbp+ppActivate], rdi
0x180029910  test    rcx, rcx
0x180029913  jz      short loc_180029921
0x180029915  mov     rax, [rcx]
0x180029918  mov     rax, [rax+10h]
0x18002991c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029921  mov     rcx, [rbp+ppMFAttributes]; pAttributes
0x180029925  lea     rdx, [rbp+ppActivate]; ppActivate
0x180029929  call    cs:__imp_MFCreateDeviceSourceActivate
0x18002992f  mov     ebx, eax
0x180029931  test    eax, eax
0x180029933  jns     short loc_18002994C
0x180029935  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002993c  jb      loc_180029BD4
0x180029942  mov     edx, 20h ; ' '
0x180029947  jmp     loc_180029BB6
0x18002994c  mov     rcx, [rbp+var_20]
0x180029950  mov     [rbp+var_20], rdi
0x180029954  test    rcx, rcx
0x180029957  jz      short loc_180029965
0x180029959  mov     rax, [rcx]
0x18002995c  mov     rax, [rax+10h]
0x180029960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029965  lea     rcx, [rbp+var_20]
0x180029969  call    cs:__imp_MFCreateCollection
0x18002996f  mov     ebx, eax
0x180029971  test    eax, eax
0x180029973  jns     short loc_18002998C
0x180029975  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18002997c  jb      loc_180029BD4
0x180029982  mov     edx, 21h ; '!'
0x180029987  jmp     loc_180029BB6
0x18002998c  mov     rdi, [rbp+ppActivate]
0x180029990  lea     rcx, [rbp+var_40]
0x180029994  mov     rax, [rdi]
0x180029997  mov     rbx, [rax]
0x18002999a  call    ?reset@?$com_ptr_t@UIUnknown@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IUnknown,wil::err_returncode_policy>::reset(void)
0x18002999f  lea     r8, [rbp+var_40]
0x1800299a3  mov     rcx, rdi
0x1800299a6  lea     rdx, _GUID_00000000_0000_0000_c000_000000000046
0x1800299ad  mov     rax, rbx
0x1800299b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299b5  xor     edi, edi
0x1800299b7  mov     ebx, eax
0x1800299b9  test    eax, eax
0x1800299bb  jns     short loc_1800299D2
0x1800299bd  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800299c4  jb      loc_180029BD4
0x1800299ca  lea     edx, [rdi+22h]
0x1800299cd  jmp     loc_180029BB6
0x1800299d2  mov     rcx, [rbp+var_20]
0x1800299d6  mov     rdx, [rbp+var_40]
0x1800299da  mov     rax, [rcx]
0x1800299dd  mov     rax, [rax+28h]
0x1800299e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800299e6  mov     ebx, eax
0x1800299e8  test    eax, eax
0x1800299ea  jns     short loc_180029A03
0x1800299ec  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x1800299f3  jb      loc_180029BD4
0x1800299f9  mov     edx, 23h ; '#'
0x1800299fe  jmp     loc_180029BB6
0x180029a03  mov     rcx, [rbp+var_38]
0x180029a07  mov     [rbp+var_38], rdi
0x180029a0b  test    rcx, rcx
0x180029a0e  jz      short loc_180029A1C
0x180029a10  mov     rax, [rcx]
0x180029a13  mov     rax, [rax+10h]
  ... truncated ...
```
