# PopulateMulticastSessionId(IConnector *,IPropertyStore *)

- ea: `0x180051ae0`
- end: `0x18005251b`
- name: `?PopulateMulticastSessionId@@YAJPEAUIConnector@@PEAUIPropertyStore@@@Z`
- size: `2619`
- prototype: `__int64 __fastcall(struct IConnector *, struct IPropertyStore *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18004a344`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180022b04`
- `0x180024fd4`
- `0x18003e920`
- `0x180051ae0`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051ffc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052395`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180051ffc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052395`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800524e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800524ef`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800524e4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800524ef`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051d4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051f1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005213b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800522e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800523cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052470`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051baf`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051c86`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051d4d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051e31`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180051f1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052034`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005213b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052207`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800522e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800523cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052470`

## string_xrefs

- `0x180051b93`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051c6a`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051d31`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051e15`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180051eff`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180052018`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18005211f`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800521eb`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800522c4`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800523b0`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall PopulateMulticastSessionId(struct IConnector *a1, struct IPropertyStore *a2)
{
  int v2; // eax
  unsigned int v3; // ebx
  __int64 v4; // rbx
  __int64 (__fastcall *v5)(__int64, __int64 *); // rdi
  __int64 v6; // rcx
  int v7; // eax
  __int64 v8; // rdi
  __int64 (__fastcall *v9)(__int64, LPVOID *); // rbx
  int v10; // eax
  struct IUnknown *v11; // r9
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  __int64 v13; // rcx
  int v14; // eax
  __int64 v15; // rbx
  __int64 (__fastcall *v16)(__int64, GUID *, __int64); // rdi
  __int64 v17; // rcx
  int v18; // eax
  char *v19; // rax
  int v20; // eax
  __int64 v21; // r8
  int v22; // eax
  int v23; // eax
  char *v24; // rax
  int v26; // [rsp+20h] [rbp-E0h]
  struct IPropertyStore *v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28[2]; // [rsp+48h] [rbp-B8h] BYREF
  LPVOID pv; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v30; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v32; // [rsp+68h] [rbp-98h] BYREF
  int v33; // [rsp+70h] [rbp-90h]
  PROPVARIANT pvar[2]; // [rsp+78h] [rbp-88h] BYREF
  char *v35; // [rsp+88h] [rbp-78h]
  PROPVARIANT v36[2]; // [rsp+90h] [rbp-70h] BYREF
  char *v37; // [rsp+A0h] [rbp-60h]
  int v38; // [rsp+A8h] [rbp-58h] BYREF
  __int128 v39; // [rsp+ACh] [rbp-54h]
  int v40; // [rsp+BCh] [rbp-44h]
  struct IConnector *v41; // [rsp+C0h] [rbp-40h] BYREF
  _QWORD v42[3]; // [rsp+C8h] [rbp-38h] BYREF
  _QWORD v43[6]; // [rsp+E0h] [rbp-20h] BYREF
  char v44; // [rsp+110h] [rbp+10h]
  __int128 v45; // [rsp+118h] [rbp+18h] BYREF
  __int128 v46; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+158h] [rbp+58h]

  v41 = a1;
  v27 = a2;
  *(_OWORD *)v36 = 0;
  v37 = 0;
  *(_OWORD *)pvar = 0;
  v35 = 0;
  v43[3] = &v27;
  v43[4] = v36;
  v43[5] = pvar;
  v44 = 1;
  v38 = 0;
  v39 = 0;
  v40 = 0;
  v33 = 0;
  v45 = 0;
  *(_QWORD *)v28 = 0;
  v31 = 0;
  v30 = 0;
  pv = 0;
  v32 = 0;
  v2 = wil::com_query_to_nothrow<IPart,IConnector * &>(&v41, &v32);
  v3 = v2;
  if ( v2 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1082,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v2,
      v26);
    if ( pv )
      CoTaskMemFree(pv);
LABEL_50:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v28);
    ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v27->lpVtbl->SetValue)(
      v27,
      PKEY_Multicast_Target_SessionDescriptor,
      v36);
    ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v27->lpVtbl->SetValue)(
      v27,
      PKEY_Multicast_Child_SessionDescriptor,
      pvar);
    goto LABEL_55;
  }
  v4 = v32;
  v5 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 96LL);
  v6 = v31;
  v31 = 0;
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = v5(v4, &v31);
  v3 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1083,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v7,
      v26);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_50;
  }
  v8 = v31;
  v9 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v31 + 64LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v10 = v9(v8, &pv);
  v3 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1084,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v10,
      v26);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_50;
  }
  v11 = g_DeviceEnumerator;
  Release = g_DeviceEnumerator->lpVtbl[1].Release;
  v13 = v30;
  v30 = 0;
  if ( v13 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v11 = g_DeviceEnumerator;
  }
  v14 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, __int64 *))Release)(v11, pv, &v30);
  v3 = v14;
  if ( v14 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1085,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v14,
      v26);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_50;
  }
  v15 = v30;
  v16 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v30 + 24LL);
  v17 = *(_QWORD *)v28;
  *(_QWORD *)v28 = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v18 = v16(v15, &GUID_28f54685_06fd_11d2_b27a_00a0c9223196, 1);
  v3 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1086,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v18,
      (int)v28);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_50;
  }
  v38 = 18193273;
  *(_QWORD *)&v39 = *(_QWORD *)&GUID_01159b79_0ea6_4923_80f5_3258d1fd9156.Data2;
  *((_QWORD *)&v39 + 1) = *(unsigned int *)&GUID_01159b79_0ea6_4923_80f5_3258d1fd9156.Data4[4] | 0x400000000LL;
  v40 = 1;
  if ( (*(int (__fastcall **)(_QWORD, int *, __int64, __int128 *))(**(_QWORD **)v28 + 24LL))(
         *(_QWORD *)v28,
         &v38,
         24,
         &v45) >= 0 )
  {
    v19 = (char *)CoTaskMemAlloc(0x24u);
    if ( !v19 )
    {
      v3 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1091,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)0x8007000ELL,
        16);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_50;
    }
    *(_DWORD *)v19 = 1;
    *(IID *)(v19 + 4) = BLUETOOTH_AUDIO_BROADCAST_PROVIDER;
    *(_OWORD *)(v19 + 20) = v45;
    LOWORD(v36[0]) = 65;
    LODWORD(v36[1]) = 36;
    v41 = 0;
    v37 = v19;
    v42[0] = 72;
    v42[2] = 0;
    v42[1] = BLUETOOTHLE_AUDIO_RESOURCE_MANAGER;
    v20 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, _QWORD *))v27->lpVtbl->SetValue)(
            v27,
            PKEY_Endpoint_CustomResourceManager,
            v42);
    v3 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x109E,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v20,
        16);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_50;
    }
    v46 = 0;
    v21 = -1;
    do
      ++v21;
    while ( *((_WORD *)pv + v21) );
    v22 = GenerateClass5Guid(BLUETOOTHLE_AUDIO_RESOURCE_MANAGER, pv, (unsigned int)(2 * v21), &v46);
    v3 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10A5,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v22,
        16);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_50;
    }
    v43[0] = 72;
    v43[2] = 0;
    v43[1] = &v46;
    v23 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, _QWORD *))v27->lpVtbl->SetValue)(
            v27,
            PKEY_Endpoint_CustomResourceManagerContext,
            v43);
    v3 = v23;
    if ( v23 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10AA,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v23,
        16);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_50;
    }
  }
  HIDWORD(v39) = 5;
  if ( (*(int (__fastcall **)(_QWORD, int *, __int64, __int128 *))(**(_QWORD **)v28 + 24LL))(
         *(_QWORD *)v28,
         &v38,
         24,
         &v45) >= 0 )
  {
    v24 = (char *)CoTaskMemAlloc(0x24u);
    if ( !v24 )
    {
      v3 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10B5,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)0x8007000ELL,
        16);
      if ( pv )
        CoTaskMemFree(pv);
      goto LABEL_50;
    }
    *(_DWORD *)v24 = 1;
    *(IID *)(v24 + 4) = BLUETOOTH_AUDIO_BROADCAST_PROVIDER;
    *(_OWORD *)(v24 + 20) = v45;
    LOWORD(pvar[0]) = 65;
    LODWORD(pvar[1]) = 36;
    v35 = v24;
  }
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v30);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v28);
  ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v27->lpVtbl->SetValue)(
    v27,
    PKEY_Multicast_Target_SessionDescriptor,
    v36);
  ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v27->lpVtbl->SetValue)(
    v27,
    PKEY_Multicast_Child_SessionDescriptor,
    pvar);
  v3 = 0;
LABEL_55:
  PropVariantClear(pvar);
  PropVariantClear(v36);
  return v3;
}

```

## disassembly

```asm
0x180051ae0  mov     [rsp-8+arg_10], rbx
0x180051ae5  mov     [rsp-8+arg_18], rsi
0x180051aea  push    rbp
0x180051aeb  push    rdi
0x180051aec  push    r13
0x180051aee  lea     rbp, [rsp-40h]
0x180051af3  sub     rsp, 140h
0x180051afa  mov     rax, cs:__security_cookie
0x180051b01  xor     rax, rsp
0x180051b04  mov     [rbp+50h+var_18], rax
0x180051b08  mov     [rbp+50h+var_90], rcx
0x180051b0c  mov     [rsp+150h+var_110], rdx
0x180051b11  xorps   xmm0, xmm0
0x180051b14  xor     eax, eax
0x180051b16  movups  xmmword ptr [rbp+50h+var_C0], xmm0
0x180051b1a  mov     [rbp+50h+var_B0], rax
0x180051b1e  movups  xmmword ptr [rsp+150h+pvar], xmm0
0x180051b23  mov     [rbp+50h+var_C8], rax
0x180051b27  lea     rax, [rsp+150h+var_110]
0x180051b2c  mov     [rbp+50h+var_58], rax
0x180051b30  lea     rax, [rbp+50h+var_C0]
0x180051b34  mov     [rbp+50h+var_50], rax
0x180051b38  lea     rax, [rsp+150h+pvar]
0x180051b3d  mov     [rbp+50h+var_48], rax
0x180051b41  mov     [rbp+50h+var_40], 1
0x180051b45  xor     esi, esi
0x180051b47  mov     [rbp+50h+var_A8], esi
0x180051b4a  xor     eax, eax
0x180051b4c  movups  [rbp+50h+var_A4], xmm0
0x180051b50  mov     [rbp+50h+var_94], eax
0x180051b53  mov     [rsp+150h+var_E0], esi
0x180051b57  movups  [rbp+50h+var_38], xmm0
0x180051b5b  mov     qword ptr [rsp+150h+var_108], rsi
0x180051b60  mov     [rsp+150h+var_F0], rsi
0x180051b65  mov     [rsp+150h+var_F8], rsi
0x180051b6a  mov     [rsp+150h+pv], rsi
0x180051b6f  mov     [rsp+150h+var_E8], rsi
0x180051b74  lea     rdx, [rsp+150h+var_E8]
0x180051b79  lea     rcx, [rbp+50h+var_90]
0x180051b7d  call    ??$com_query_to_nothrow@UIPart@@AEAPEAUIConnector@@@wil@@YAJAEAPEAUIConnector@@PEAPEAUIPart@@@Z; wil::com_query_to_nothrow<IPart,IConnector * &>(IConnector * &,IPart * *)
0x180051b82  mov     ebx, eax
0x180051b84  test    eax, eax
0x180051b86  jns     loc_180051C21
0x180051b8c  mov     rcx, [rbp+58h]; this
0x180051b90  mov     r9d, eax; char *
0x180051b93  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180051b9a  mov     edx, 1082h; void *
0x180051b9f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051ba4  nop
0x180051ba5  mov     rcx, [rsp+150h+pv]; pv
0x180051baa  test    rcx, rcx
0x180051bad  jz      short loc_180051BB6
0x180051baf  call    cs:__imp_CoTaskMemFree
0x180051bb5  nop
0x180051bb6  lea     rcx, [rsp+150h+var_F8]
0x180051bbb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051bc0  nop
0x180051bc1  lea     rcx, [rsp+150h+var_F0]
0x180051bc6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051bcb  nop
0x180051bcc  lea     rcx, [rsp+150h+var_E8]
0x180051bd1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051bd6  nop
0x180051bd7  lea     rcx, [rsp+150h+var_108]
0x180051bdc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051be1  nop
0x180051be2  mov     rcx, [rsp+150h+var_110]
0x180051be7  mov     rax, [rcx]
0x180051bea  lea     r8, [rbp+50h+var_C0]
0x180051bee  lea     rdx, PKEY_Multicast_Target_SessionDescriptor
0x180051bf5  mov     rax, [rax+30h]
0x180051bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051bfe  mov     rcx, [rsp+150h+var_110]
0x180051c03  mov     rax, [rcx]
0x180051c06  lea     r8, [rsp+150h+pvar]
0x180051c0b  lea     rdx, PKEY_Multicast_Child_SessionDescriptor
0x180051c12  mov     rax, [rax+30h]
0x180051c16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c1b  nop
0x180051c1c  jmp     loc_1800524DF
0x180051c21  mov     rbx, [rsp+150h+var_E8]
0x180051c26  mov     rax, [rbx]
0x180051c29  mov     rdi, [rax+60h]
0x180051c2d  mov     rcx, [rsp+150h+var_F0]
0x180051c32  mov     [rsp+150h+var_F0], rsi
0x180051c37  test    rcx, rcx
0x180051c3a  jz      short loc_180051C49
0x180051c3c  mov     rdx, [rcx]
0x180051c3f  mov     rax, [rdx+10h]
0x180051c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c48  nop
0x180051c49  lea     rdx, [rsp+150h+var_F0]
0x180051c4e  mov     rcx, rbx
0x180051c51  mov     rax, rdi
0x180051c54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051c59  mov     ebx, eax
0x180051c5b  test    eax, eax
0x180051c5d  jns     loc_180051CF8
0x180051c63  mov     rcx, [rbp+58h]; this
0x180051c67  mov     r9d, eax; char *
0x180051c6a  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180051c71  mov     edx, 1083h; void *
0x180051c76  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051c7b  nop
0x180051c7c  mov     rcx, [rsp+150h+pv]; pv
0x180051c81  test    rcx, rcx
0x180051c84  jz      short loc_180051C8D
0x180051c86  call    cs:__imp_CoTaskMemFree
0x180051c8c  nop
0x180051c8d  lea     rcx, [rsp+150h+var_F8]
0x180051c92  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051c97  nop
0x180051c98  lea     rcx, [rsp+150h+var_F0]
0x180051c9d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051ca2  nop
0x180051ca3  lea     rcx, [rsp+150h+var_E8]
0x180051ca8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051cad  nop
0x180051cae  lea     rcx, [rsp+150h+var_108]
0x180051cb3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051cb8  nop
0x180051cb9  mov     rcx, [rsp+150h+var_110]
0x180051cbe  mov     rax, [rcx]
0x180051cc1  lea     r8, [rbp+50h+var_C0]
0x180051cc5  lea     rdx, PKEY_Multicast_Target_SessionDescriptor
0x180051ccc  mov     rax, [rax+30h]
0x180051cd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051cd5  mov     rcx, [rsp+150h+var_110]
0x180051cda  mov     rax, [rcx]
0x180051cdd  lea     r8, [rsp+150h+pvar]
0x180051ce2  lea     rdx, PKEY_Multicast_Child_SessionDescriptor
0x180051ce9  mov     rax, [rax+30h]
0x180051ced  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051cf2  nop
0x180051cf3  jmp     loc_1800524DF
0x180051cf8  mov     rdi, [rsp+150h+var_F0]
0x180051cfd  mov     rax, [rdi]
0x180051d00  mov     rbx, [rax+40h]
0x180051d04  xor     edx, edx
0x180051d06  lea     rcx, [rsp+150h+pv]
0x180051d0b  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180051d10  lea     rdx, [rsp+150h+pv]
0x180051d15  mov     rcx, rdi
0x180051d18  mov     rax, rbx
0x180051d1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d20  mov     ebx, eax
0x180051d22  test    eax, eax
0x180051d24  jns     loc_180051DBF
0x180051d2a  mov     rcx, [rbp+58h]; this
0x180051d2e  mov     r9d, eax; char *
0x180051d31  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180051d38  mov     edx, 1084h; void *
0x180051d3d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051d42  nop
0x180051d43  mov     rcx, [rsp+150h+pv]; pv
0x180051d48  test    rcx, rcx
0x180051d4b  jz      short loc_180051D54
0x180051d4d  call    cs:__imp_CoTaskMemFree
0x180051d53  nop
0x180051d54  lea     rcx, [rsp+150h+var_F8]
0x180051d59  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051d5e  nop
0x180051d5f  lea     rcx, [rsp+150h+var_F0]
0x180051d64  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051d69  nop
0x180051d6a  lea     rcx, [rsp+150h+var_E8]
0x180051d6f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051d74  nop
0x180051d75  lea     rcx, [rsp+150h+var_108]
0x180051d7a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051d7f  nop
0x180051d80  mov     rcx, [rsp+150h+var_110]
0x180051d85  mov     rax, [rcx]
0x180051d88  lea     r8, [rbp+50h+var_C0]
0x180051d8c  lea     rdx, PKEY_Multicast_Target_SessionDescriptor
0x180051d93  mov     rax, [rax+30h]
0x180051d97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051d9c  mov     rcx, [rsp+150h+var_110]
0x180051da1  mov     rax, [rcx]
0x180051da4  lea     r8, [rsp+150h+pvar]
0x180051da9  lea     rdx, PKEY_Multicast_Child_SessionDescriptor
0x180051db0  mov     rax, [rax+30h]
0x180051db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051db9  nop
0x180051dba  jmp     loc_1800524DF
0x180051dbf  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180051dc6  mov     rax, [r9]
0x180051dc9  mov     rbx, [rax+28h]
0x180051dcd  mov     rcx, [rsp+150h+var_F8]
0x180051dd2  mov     [rsp+150h+var_F8], rsi
0x180051dd7  test    rcx, rcx
0x180051dda  jz      short loc_180051DEF
0x180051ddc  mov     rax, [rcx]
0x180051ddf  mov     rax, [rax+10h]
0x180051de3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051de8  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180051def  lea     r8, [rsp+150h+var_F8]
0x180051df4  mov     rdx, [rsp+150h+pv]
0x180051df9  mov     rcx, r9
0x180051dfc  mov     rax, rbx
0x180051dff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e04  mov     ebx, eax
0x180051e06  test    eax, eax
0x180051e08  jns     loc_180051EA3
0x180051e0e  mov     rcx, [rbp+58h]; this
0x180051e12  mov     r9d, eax; char *
0x180051e15  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180051e1c  mov     edx, 1085h; void *
0x180051e21  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051e26  nop
0x180051e27  mov     rcx, [rsp+150h+pv]; pv
0x180051e2c  test    rcx, rcx
0x180051e2f  jz      short loc_180051E38
0x180051e31  call    cs:__imp_CoTaskMemFree
0x180051e37  nop
0x180051e38  lea     rcx, [rsp+150h+var_F8]
0x180051e3d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051e42  nop
0x180051e43  lea     rcx, [rsp+150h+var_F0]
0x180051e48  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051e4d  nop
0x180051e4e  lea     rcx, [rsp+150h+var_E8]
0x180051e53  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051e58  nop
0x180051e59  lea     rcx, [rsp+150h+var_108]
0x180051e5e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051e63  nop
0x180051e64  mov     rcx, [rsp+150h+var_110]
0x180051e69  mov     rax, [rcx]
0x180051e6c  lea     r8, [rbp+50h+var_C0]
0x180051e70  lea     rdx, PKEY_Multicast_Target_SessionDescriptor
0x180051e77  mov     rax, [rax+30h]
0x180051e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e80  mov     rcx, [rsp+150h+var_110]
0x180051e85  mov     rax, [rcx]
0x180051e88  lea     r8, [rsp+150h+pvar]
0x180051e8d  lea     rdx, PKEY_Multicast_Child_SessionDescriptor
0x180051e94  mov     rax, [rax+30h]
0x180051e98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051e9d  nop
0x180051e9e  jmp     loc_1800524DF
0x180051ea3  mov     rbx, [rsp+150h+var_F8]
0x180051ea8  mov     rax, [rbx]
0x180051eab  mov     rdi, [rax+18h]
0x180051eaf  mov     rcx, qword ptr [rsp+150h+var_108]
0x180051eb4  mov     qword ptr [rsp+150h+var_108], rsi
0x180051eb9  test    rcx, rcx
0x180051ebc  jz      short loc_180051ECB
0x180051ebe  mov     rax, [rcx]
0x180051ec1  mov     rax, [rax+10h]
0x180051ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051eca  nop
0x180051ecb  lea     rax, [rsp+150h+var_108]
0x180051ed0  mov     qword ptr [rsp+150h+var_130], rax; int
0x180051ed5  xor     r9d, r9d
0x180051ed8  lea     r8d, [r9+1]
0x180051edc  lea     rdx, _GUID_28f54685_06fd_11d2_b27a_00a0c9223196
0x180051ee3  mov     rcx, rbx
0x180051ee6  mov     rax, rdi
0x180051ee9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051eee  mov     ebx, eax
0x180051ef0  test    eax, eax
0x180051ef2  jns     loc_180051F8D
0x180051ef8  mov     rcx, [rbp+58h]; this
0x180051efc  mov     r9d, eax; char *
0x180051eff  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180051f06  mov     edx, 1086h; void *
0x180051f0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180051f10  nop
0x180051f11  mov     rcx, [rsp+150h+pv]; pv
0x180051f16  test    rcx, rcx
0x180051f19  jz      short loc_180051F22
0x180051f1b  call    cs:__imp_CoTaskMemFree
0x180051f21  nop
0x180051f22  lea     rcx, [rsp+150h+var_F8]
0x180051f27  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051f2c  nop
0x180051f2d  lea     rcx, [rsp+150h+var_F0]
0x180051f32  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051f37  nop
0x180051f38  lea     rcx, [rsp+150h+var_E8]
0x180051f3d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051f42  nop
0x180051f43  lea     rcx, [rsp+150h+var_108]
0x180051f48  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180051f4d  nop
0x180051f4e  mov     rcx, [rsp+150h+var_110]
0x180051f53  mov     rax, [rcx]
0x180051f56  lea     r8, [rbp+50h+var_C0]
0x180051f5a  lea     rdx, PKEY_Multicast_Target_SessionDescriptor
0x180051f61  mov     rax, [rax+30h]
0x180051f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f6a  mov     rcx, [rsp+150h+var_110]
0x180051f6f  mov     rax, [rcx]
0x180051f72  lea     r8, [rsp+150h+pvar]
0x180051f77  lea     rdx, PKEY_Multicast_Child_SessionDescriptor
0x180051f7e  mov     rax, [rax+30h]
0x180051f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180051f87  nop
0x180051f88  jmp     loc_1800524DF
  ... truncated ...
```
