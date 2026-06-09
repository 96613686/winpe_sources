# CAudioEndpointPluginBuilder::SyncPluginEndpointArrival(IPnpInterface *,int *)

- ea: `0x180055a90`
- end: `0x180056149`
- name: `?SyncPluginEndpointArrival@CAudioEndpointPluginBuilder@@SAJPEAUIPnpInterface@@PEAH@Z`
- size: `1721`
- prototype: `__int64 __fastcall(struct IPnpInterface *, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180035f34`

## callees

- `0x1800035d0`
- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180023d28`
- `0x180023fbc`
- `0x180034c5c`
- `0x180055a90`
- `0x180068010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055db6`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180055db6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055e1e`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180055e1e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055dc4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055dcf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055dda`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005604e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056059`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056064`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056127`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056132`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005613d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055dc4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055dcf`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180055dda`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005604e`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056059`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056064`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056127`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180056132`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005613d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055ba4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005607e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180055ba4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005607e`

## string_xrefs

- `0x180055b79`: `avcore\audiocore\server\audioendpointbuilder\dll\audioendpointpluginbuilder.cpp`
- `0x180056112`: `avcore\audiocore\server\audioendpointbuilder\dll\audioendpointpluginbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
__int64 __fastcall CAudioEndpointPluginBuilder::SyncPluginEndpointArrival(struct IPnpInterface *a1, int *a2)
{
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  unsigned int i; // esi
  __int64 v9; // rbx
  __int64 (__fastcall *v10)(__int64, _QWORD, __int64 *); // rdi
  __int64 v11; // rcx
  HRESULT v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rbx
  __int64 (__fastcall *v15)(__int64, _QWORD, __int64 *); // rdi
  __int64 v16; // rcx
  __int64 (__fastcall *v17)(struct IPnpInterface *, LPVOID *); // rbx
  LPVOID v18; // rcx
  __int64 v19; // rdx
  __int64 (__fastcall *v20)(struct IPnpInterface *, LPVOID *); // rbx
  __int64 (__fastcall *v21)(struct IPnpInterface *, GUID *, __int64 *); // rbx
  __int64 v22; // rcx
  __int64 v23; // rbx
  __int64 (__fastcall *v24)(__int64, __int64, __int64 *); // rdi
  __int64 v25; // rcx
  __int64 v26; // r9
  __int64 v27; // rbx
  __int64 (__fastcall *v28)(__int64, __int64, __int64 *); // rdi
  __int64 v29; // rcx
  int ppv; // [rsp+20h] [rbp-79h]
  __int64 v32; // [rsp+30h] [rbp-69h] BYREF
  __int64 v33; // [rsp+38h] [rbp-61h] BYREF
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-59h] BYREF
  __int64 v35; // [rsp+50h] [rbp-49h]
  PROPVARIANT v36[2]; // [rsp+58h] [rbp-41h] BYREF
  __int64 v37; // [rsp+68h] [rbp-31h]
  PROPVARIANT v38[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v39; // [rsp+80h] [rbp-19h]
  __int64 v40; // [rsp+88h] [rbp-11h] BYREF
  __int64 v41; // [rsp+90h] [rbp-9h] BYREF
  __int64 v42; // [rsp+98h] [rbp-1h] BYREF
  LPVOID v43; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v44; // [rsp+A8h] [rbp+Fh] BYREF
  _QWORD v45[8]; // [rsp+B0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+F8h] [rbp+5Fh]
  unsigned int v47; // [rsp+108h] [rbp+6Fh] BYREF
  int v48; // [rsp+110h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+118h] [rbp+7Fh] BYREF

  v47 = 0;
  v45[0] = 0;
  v33 = 0;
  v44 = 0;
  v40 = 0;
  v43 = 0;
  v42 = 0;
  v41 = 0;
  pv = 0;
  v32 = 0;
  v48 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 22, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids);
  }
  *a2 = 1;
  QueryInterface = g_DeviceEnumerator->lpVtbl[1].QueryInterface;
  wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(v45);
  v5 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, _QWORD *))QueryInterface)(
         g_DeviceEnumerator,
         2,
         15,
         v45);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 591;
    goto LABEL_9;
  }
  v5 = (*(__int64 (__fastcall **)(_QWORD, unsigned int *))(*(_QWORD *)v45[0] + 24LL))(v45[0], &v47);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 594;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audioendpointpluginbuilder.cpp",
      (const char *)(unsigned int)v5,
      ppv);
LABEL_10:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_78;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= v47 )
      goto LABEL_75;
    *(_OWORD *)v38 = 0;
    v39 = 0;
    *(_OWORD *)v36 = 0;
    v37 = 0;
    *(_OWORD *)pvar = 0;
    v35 = 0;
    v9 = v45[0];
    v10 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v45[0] + 32LL);
    v11 = v33;
    v33 = 0;
    if ( v11 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    v12 = v10(v9, i, &v33);
    v6 = v12;
    if ( v12 < 0 )
    {
      v19 = 603;
      goto LABEL_86;
    }
    v13 = v32;
    v32 = 0;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
    v12 = wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(
            &v33,
            &v32);
    v6 = v12;
    if ( v12 < 0 )
    {
      v19 = 606;
      goto LABEL_86;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 32LL))(v32, &v48);
    v6 = v12;
    if ( v12 < 0 )
    {
      v19 = 607;
      goto LABEL_86;
    }
    if ( (v48 & 0x20000000) != 0 )
      goto LABEL_39;
    v14 = v33;
    v15 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v33 + 32LL);
    v16 = v40;
    v40 = 0;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
    v12 = v15(v14, 0, &v40);
    v6 = v12;
    if ( v12 < 0 )
    {
      v19 = 616;
      goto LABEL_86;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v40 + 40LL))(
            v40,
            &DEVPKEY_AudioEndpointPlugin_FactoryCLSID,
            v38);
    v6 = v12;
    if ( v12 < 0 )
    {
      v19 = 619;
      goto LABEL_86;
    }
    if ( LOWORD(v38[0]) != 72 )
      goto LABEL_39;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids);
    }
    v12 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v40 + 40LL))(
            v40,
            &DEVPKEY_AudioEndpointPlugin_PnPInterface,
            v36);
    v6 = v12;
    if ( v12 < 0 )
    {
      v19 = 626;
LABEL_86:
      v26 = (unsigned int)v12;
      goto LABEL_87;
    }
    if ( LOWORD(v36[0]) == 31 )
    {
      v17 = *(__int64 (__fastcall **)(struct IPnpInterface *, LPVOID *))(*(_QWORD *)a1 + 32LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pv,
        0);
      v12 = v17(a1, &pv);
      v6 = v12;
      if ( v12 < 0 )
      {
        v19 = 631;
        goto LABEL_86;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 24, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids, pv);
      }
      if ( !(unsigned int)_o__wcsicmp(pv, v36[1]) )
        break;
    }
LABEL_39:
    PropVariantClear(pvar);
    PropVariantClear(v36);
    PropVariantClear(v38);
  }
  v18 = v43;
  v43 = 0;
  if ( v18 )
    (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v18 + 16LL))(v18);
  v12 = CoCreateInstance(
          &GUID_06cca63e_9941_441b_b004_39f999ada412,
          0,
          0x17u,
          &GUID_6ca19947_8747_46ab_879e_349c4dbb88fb,
          &v43);
  v6 = v12;
  if ( v12 < 0 )
  {
    v19 = 638;
    goto LABEL_86;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 25, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids, pv);
  }
  v12 = (*(__int64 (__fastcall **)(LPVOID, __int64, __int64))(*(_QWORD *)v43 + 40LL))(v43, v33, 1);
  v6 = v12;
  if ( v12 < 0 )
  {
    v19 = 641;
    goto LABEL_86;
  }
  *a2 = 0;
  v20 = *(__int64 (__fastcall **)(struct IPnpInterface *, LPVOID *))(*(_QWORD *)a1 + 32LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v12 = v20(a1, &pv);
  v6 = v12;
  if ( v12 < 0 )
  {
    v19 = 647;
    goto LABEL_86;
  }
  v21 = **(__int64 (__fastcall ***)(struct IPnpInterface *, GUID *, __int64 *))a1;
  v22 = v42;
  v42 = 0;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v12 = v21(a1, &GUID_d666063f_1587_4e43_81f1_b948e807363f, &v42);
  v6 = v12;
  if ( v12 < 0 )
  {
    v19 = 649;
    goto LABEL_86;
  }
  v23 = v42;
  v24 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v42 + 32LL);
  v25 = v44;
  v44 = 0;
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  v12 = v24(v23, 2, &v44);
  v6 = v12;
  if ( v12 < 0 )
  {
    v19 = 651;
    goto LABEL_86;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v44 + 40LL))(
          v44,
          &DEVPKEY_Device_FriendlyName,
          pvar);
  v6 = v12;
  if ( v12 < 0 )
  {
    v19 = 654;
    goto LABEL_86;
  }
  if ( LOWORD(pvar[0]) != 31 )
  {
    v6 = -2147024809;
    v26 = 2147942487LL;
    v19 = 655;
LABEL_87:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v19,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\audioendpointpluginbuilder.cpp",
      (const char *)v26,
      ppv);
    PropVariantClear(pvar);
    PropVariantClear(v36);
    PropVariantClear(v38);
    goto LABEL_10;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
  {
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids, pvar[1]);
  }
  v27 = v33;
  v28 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v33 + 32LL);
  v29 = v41;
  v41 = 0;
  if ( v29 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v29 + 16LL))(v29);
  v12 = v28(v27, 2, &v41);
  v6 = v12;
  if ( v12 < 0 )
  {
    v19 = 659;
    goto LABEL_86;
  }
  v12 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v41 + 48LL))(
          v41,
          PKEY_Endpoint_Device_NAME,
          pvar);
  v6 = v12;
  if ( v12 < 0 )
  {
    v19 = 661;
    goto LABEL_86;
  }
  PropVariantClear(pvar);
  PropVariantClear(v36);
  PropVariantClear(v38);
LABEL_75:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  if ( pv )
    CoTaskMemFree(pv);
  v6 = 0;
LABEL_78:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v44);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v45);
  return v6;
}

```

## disassembly

```asm
0x180055a90  push    rbp
0x180055a92  push    rbx
0x180055a93  push    rsi
0x180055a94  push    rdi
0x180055a95  push    r12
0x180055a97  push    r14
0x180055a99  push    r15
0x180055a9b  lea     rbp, [rsp-27h]
0x180055aa0  sub     rsp, 0C0h
0x180055aa7  mov     r15, rdx
0x180055aaa  mov     r14, rcx
0x180055aad  xor     r12d, r12d
0x180055ab0  mov     [rbp+57h+arg_8], r12d
0x180055ab4  mov     [rbp+57h+var_40], r12
0x180055ab8  mov     [rbp+57h+var_B8], r12
0x180055abc  mov     [rbp+57h+var_48], r12
0x180055ac0  mov     [rbp+57h+var_68], r12
0x180055ac4  mov     [rbp+57h+var_50], r12
0x180055ac8  mov     [rbp+57h+var_58], r12
0x180055acc  mov     [rbp+57h+var_60], r12
0x180055ad0  mov     [rbp+57h+pv], r12
0x180055ad4  mov     [rbp+57h+var_C0], r12
0x180055ad8  mov     [rbp+57h+arg_10], r12d
0x180055adc  lea     rax, WPP_GLOBAL_Control
0x180055ae3  mov     rcx, cs:WPP_GLOBAL_Control
0x180055aea  cmp     rcx, rax
0x180055aed  jz      short loc_180055B13
0x180055aef  test    dword ptr [rcx+1Ch], 80000h
0x180055af6  jz      short loc_180055B13
0x180055af8  cmp     byte ptr [rcx+19h], 4
0x180055afc  jb      short loc_180055B13
0x180055afe  lea     edx, [r12+16h]
0x180055b03  lea     r8, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids
0x180055b0a  mov     rcx, [rcx+10h]
0x180055b0e  call    WPP_SF_
0x180055b13  mov     dword ptr [r15], 1
0x180055b1a  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180055b21  mov     rcx, [rax]
0x180055b24  mov     rbx, [rcx+18h]
0x180055b28  lea     rcx, [rbp+57h+var_40]
0x180055b2c  call    ?reset@?$com_ptr_t@UIMMDeviceCollection@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(void)
0x180055b31  lea     r9, [rbp+57h+var_40]
0x180055b35  mov     edx, 2
0x180055b3a  lea     r8d, [rdx+0Dh]
0x180055b3e  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180055b45  mov     rax, rbx
0x180055b48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b4d  mov     ebx, eax
0x180055b4f  test    eax, eax
0x180055b51  jns     short loc_180055B5A
0x180055b53  mov     edx, 24Fh
0x180055b58  jmp     short loc_180055B79
0x180055b5a  mov     rcx, [rbp+57h+var_40]
0x180055b5e  mov     rax, [rcx]
0x180055b61  lea     rdx, [rbp+57h+arg_8]
0x180055b65  mov     rax, [rax+18h]
0x180055b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055b6e  mov     ebx, eax
0x180055b70  test    eax, eax
0x180055b72  jns     short loc_180055BAF
0x180055b74  mov     edx, 252h; void *
0x180055b79  lea     r8, aAvcoreAudiocor_7; "avcore\\audiocore\\server\\audioendpoin"...
0x180055b80  mov     r9d, eax; char *
0x180055b83  mov     rcx, [rbp+5Fh]; this
0x180055b87  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180055b8c  nop
0x180055b8d  lea     rcx, [rbp+57h+var_C0]
0x180055b91  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180055b96  nop
0x180055b97  mov     rcx, [rbp+57h+pv]; pv
0x180055b9b  test    rcx, rcx
0x180055b9e  jz      loc_180056087
0x180055ba4  call    cs:__imp_CoTaskMemFree
0x180055baa  jmp     loc_180056087
0x180055baf  mov     esi, r12d
0x180055bb2  cmp     esi, [rbp+57h+arg_8]
0x180055bb5  jnb     loc_18005606B
0x180055bbb  xorps   xmm0, xmm0
0x180055bbe  xor     eax, eax
0x180055bc0  movups  xmmword ptr [rbp+57h+var_80], xmm0
0x180055bc4  mov     [rbp+57h+var_70], rax
0x180055bc8  movups  xmmword ptr [rbp+57h+var_98], xmm0
0x180055bcc  mov     [rbp+57h+var_88], rax
0x180055bd0  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180055bd4  mov     [rbp+57h+var_A0], rax
0x180055bd8  mov     rbx, [rbp+57h+var_40]
0x180055bdc  mov     rax, [rbx]
0x180055bdf  mov     rdi, [rax+20h]
0x180055be3  mov     rcx, [rbp+57h+var_B8]
0x180055be7  mov     [rbp+57h+var_B8], r12
0x180055beb  test    rcx, rcx
0x180055bee  jz      short loc_180055BFD
0x180055bf0  mov     rdx, [rcx]
0x180055bf3  mov     rax, [rdx+10h]
0x180055bf7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055bfc  nop
0x180055bfd  lea     r8, [rbp+57h+var_B8]
0x180055c01  mov     edx, esi
0x180055c03  mov     rcx, rbx
0x180055c06  mov     rax, rdi
0x180055c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c0e  mov     ebx, eax
0x180055c10  test    eax, eax
0x180055c12  js      loc_18005610A
0x180055c18  mov     rcx, [rbp+57h+var_C0]
0x180055c1c  mov     [rbp+57h+var_C0], r12
0x180055c20  test    rcx, rcx
0x180055c23  jz      short loc_180055C32
0x180055c25  mov     rax, [rcx]
0x180055c28  mov     rax, [rax+10h]
0x180055c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c31  nop
0x180055c32  lea     rdx, [rbp+57h+var_C0]
0x180055c36  lea     rcx, [rbp+57h+var_B8]
0x180055c3a  call    ??$com_query_to_nothrow@UIMMEndpointInternal@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIMMEndpointInternal@@@Z; wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IMMEndpointInternal * *)
0x180055c3f  mov     ebx, eax
0x180055c41  test    eax, eax
0x180055c43  js      loc_180056103
0x180055c49  mov     rcx, [rbp+57h+var_C0]
0x180055c4d  mov     rax, [rcx]
0x180055c50  lea     rdx, [rbp+57h+arg_10]
0x180055c54  mov     rax, [rax+20h]
0x180055c58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c5d  mov     ebx, eax
0x180055c5f  test    eax, eax
0x180055c61  js      loc_1800560FC
0x180055c67  test    [rbp+57h+arg_10], 20000000h
0x180055c6e  jnz     loc_180055DC0
0x180055c74  mov     rbx, [rbp+57h+var_B8]
0x180055c78  mov     rax, [rbx]
0x180055c7b  mov     rdi, [rax+20h]
0x180055c7f  mov     rcx, [rbp+57h+var_68]
0x180055c83  mov     [rbp+57h+var_68], r12
0x180055c87  test    rcx, rcx
0x180055c8a  jz      short loc_180055C99
0x180055c8c  mov     rdx, [rcx]
0x180055c8f  mov     rax, [rdx+10h]
0x180055c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055c98  nop
0x180055c99  lea     r8, [rbp+57h+var_68]
0x180055c9d  xor     edx, edx
0x180055c9f  mov     rcx, rbx
0x180055ca2  mov     rax, rdi
0x180055ca5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055caa  mov     ebx, eax
0x180055cac  test    eax, eax
0x180055cae  js      loc_1800560F5
0x180055cb4  mov     rcx, [rbp+57h+var_68]
0x180055cb8  mov     rax, [rcx]
0x180055cbb  lea     r8, [rbp+57h+var_80]
0x180055cbf  lea     rdx, DEVPKEY_AudioEndpointPlugin_FactoryCLSID
0x180055cc6  mov     rax, [rax+28h]
0x180055cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ccf  mov     ebx, eax
0x180055cd1  test    eax, eax
0x180055cd3  js      loc_1800560EE
0x180055cd9  cmp     word ptr [rbp+57h+var_80], 48h ; 'H'
0x180055cde  jnz     loc_180055DC0
0x180055ce4  mov     rcx, cs:WPP_GLOBAL_Control
0x180055ceb  lea     rax, WPP_GLOBAL_Control
0x180055cf2  mov     edi, 80000h
0x180055cf7  cmp     rcx, rax
0x180055cfa  jz      short loc_180055D1C
0x180055cfc  test    [rcx+1Ch], edi
0x180055cff  jz      short loc_180055D1C
0x180055d01  cmp     byte ptr [rcx+19h], 4
0x180055d05  jb      short loc_180055D1C
0x180055d07  mov     edx, 17h
0x180055d0c  lea     r8, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids
0x180055d13  mov     rcx, [rcx+10h]
0x180055d17  call    WPP_SF_
0x180055d1c  mov     rcx, [rbp+57h+var_68]
0x180055d20  mov     rax, [rcx]
0x180055d23  lea     r8, [rbp+57h+var_98]
0x180055d27  lea     rdx, DEVPKEY_AudioEndpointPlugin_PnPInterface
0x180055d2e  mov     rax, [rax+28h]
0x180055d32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d37  mov     ebx, eax
0x180055d39  test    eax, eax
0x180055d3b  js      loc_1800560E7
0x180055d41  mov     eax, 1Fh
0x180055d46  cmp     ax, word ptr [rbp+57h+var_98]
0x180055d4a  jnz     short loc_180055DC0
0x180055d4c  mov     rax, [r14]
0x180055d4f  mov     rbx, [rax+20h]
0x180055d53  xor     edx, edx
0x180055d55  lea     rcx, [rbp+57h+pv]
0x180055d59  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180055d5e  lea     rdx, [rbp+57h+pv]
0x180055d62  mov     rcx, r14
0x180055d65  mov     rax, rbx
0x180055d68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055d6d  mov     ebx, eax
0x180055d6f  test    eax, eax
0x180055d71  js      loc_1800560E0
0x180055d77  mov     rcx, cs:WPP_GLOBAL_Control
0x180055d7e  lea     rax, WPP_GLOBAL_Control
0x180055d85  cmp     rcx, rax
0x180055d88  jz      short loc_180055DAE
0x180055d8a  test    [rcx+1Ch], edi
0x180055d8d  jz      short loc_180055DAE
0x180055d8f  cmp     byte ptr [rcx+19h], 4
0x180055d93  jb      short loc_180055DAE
0x180055d95  mov     edx, 18h
0x180055d9a  mov     r9, [rbp+57h+pv]
0x180055d9e  lea     r8, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids
0x180055da5  mov     rcx, [rcx+10h]
0x180055da9  call    WPP_SF_S
0x180055dae  mov     rdx, [rbp+57h+var_98+8]
0x180055db2  mov     rcx, [rbp+57h+pv]
0x180055db6  call    cs:__imp__o__wcsicmp
0x180055dbc  test    eax, eax
0x180055dbe  jz      short loc_180055DE7
0x180055dc0  lea     rcx, [rbp+57h+pvar]; pvar
0x180055dc4  call    cs:__imp_PropVariantClear
0x180055dca  nop
0x180055dcb  lea     rcx, [rbp+57h+var_98]; pvar
0x180055dcf  call    cs:__imp_PropVariantClear
0x180055dd5  nop
0x180055dd6  lea     rcx, [rbp+57h+var_80]; pvar
0x180055dda  call    cs:__imp_PropVariantClear
0x180055de0  inc     esi
0x180055de2  jmp     loc_180055BB2
0x180055de7  mov     rcx, [rbp+57h+var_50]
0x180055deb  mov     [rbp+57h+var_50], r12
0x180055def  test    rcx, rcx
0x180055df2  jz      short loc_180055E01
0x180055df4  mov     rax, [rcx]
0x180055df7  mov     rax, [rax+10h]
0x180055dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e00  nop
0x180055e01  lea     rax, [rbp+57h+var_50]
0x180055e05  mov     qword ptr [rsp+0F0h+ppv], rax; ppv
0x180055e0a  lea     r9, _GUID_6ca19947_8747_46ab_879e_349c4dbb88fb; riid
0x180055e11  xor     edx, edx; pUnkOuter
0x180055e13  lea     r8d, [rdx+17h]; dwClsContext
0x180055e17  lea     rcx, _GUID_06cca63e_9941_441b_b004_39f999ada412; rclsid
0x180055e1e  call    cs:__imp_CoCreateInstance
0x180055e24  mov     ebx, eax
0x180055e26  test    eax, eax
0x180055e28  jns     short loc_180055E34
0x180055e2a  mov     edx, 27Eh
0x180055e2f  jmp     loc_18005610F
0x180055e34  mov     rcx, cs:WPP_GLOBAL_Control
0x180055e3b  lea     rsi, WPP_GLOBAL_Control
0x180055e42  cmp     rcx, rsi
0x180055e45  jz      short loc_180055E6B
0x180055e47  test    [rcx+1Ch], edi
0x180055e4a  jz      short loc_180055E6B
0x180055e4c  cmp     byte ptr [rcx+19h], 4
0x180055e50  jb      short loc_180055E6B
0x180055e52  mov     edx, 19h
0x180055e57  mov     r9, [rbp+57h+pv]
0x180055e5b  lea     r8, WPP_2805e6110d3c3df85a880848e67000dd_Traceguids
0x180055e62  mov     rcx, [rcx+10h]
0x180055e66  call    WPP_SF_S
0x180055e6b  mov     rcx, [rbp+57h+var_50]
0x180055e6f  mov     rax, [rcx]
0x180055e72  mov     r8d, 1
0x180055e78  mov     rdx, [rbp+57h+var_B8]
0x180055e7c  mov     rax, [rax+28h]
0x180055e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055e85  mov     ebx, eax
0x180055e87  test    eax, eax
0x180055e89  jns     short loc_180055E95
0x180055e8b  mov     edx, 281h
0x180055e90  jmp     loc_18005610F
0x180055e95  mov     [r15], r12d
0x180055e98  mov     rax, [r14]
0x180055e9b  mov     rbx, [rax+20h]
0x180055e9f  xor     edx, edx
0x180055ea1  lea     rcx, [rbp+57h+pv]
0x180055ea5  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180055eaa  lea     rdx, [rbp+57h+pv]
0x180055eae  mov     rcx, r14
0x180055eb1  mov     rax, rbx
0x180055eb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055eb9  mov     ebx, eax
0x180055ebb  test    eax, eax
0x180055ebd  jns     short loc_180055EC9
0x180055ebf  mov     edx, 287h
0x180055ec4  jmp     loc_18005610F
0x180055ec9  mov     rax, [r14]
0x180055ecc  mov     rbx, [rax]
0x180055ecf  mov     rcx, [rbp+57h+var_58]
0x180055ed3  mov     [rbp+57h+var_58], r12
0x180055ed7  test    rcx, rcx
0x180055eda  jz      short loc_180055EE9
0x180055edc  mov     rdx, [rcx]
0x180055edf  mov     rax, [rdx+10h]
0x180055ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055ee8  nop
0x180055ee9  lea     r8, [rbp+57h+var_58]
0x180055eed  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x180055ef4  mov     rcx, r14
0x180055ef7  mov     rax, rbx
0x180055efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055eff  mov     ebx, eax
0x180055f01  test    eax, eax
0x180055f03  jns     short loc_180055F0F
  ... truncated ...
```
