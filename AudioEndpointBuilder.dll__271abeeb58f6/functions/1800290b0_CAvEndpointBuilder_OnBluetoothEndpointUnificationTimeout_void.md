# CAvEndpointBuilder::OnBluetoothEndpointUnificationTimeout(void)

- ea: `0x1800290b0`
- end: `0x18002963b`
- name: `?OnBluetoothEndpointUnificationTimeout@CAvEndpointBuilder@@AEAAJXZ`
- size: `1419`
- prototype: `__int64 __fastcall(LPCRITICAL_SECTION lpCriticalSection)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800290a0`

## callees

- `0x1800035d0`
- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x18001f374`
- `0x180022e38`
- `0x180023d28`
- `0x180023fbc`
- `0x180024264`
- `0x180026f4c`
- `0x1800290b0`
- `0x180029c9c`
- `0x18002e144`
- `0x18003e920`
- `0x1800492f4`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029522`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029157`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180029522`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800290d6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800290d6`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029111`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180029111`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180029148`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180029513`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180029148`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180029513`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002949a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800294a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800294b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029571`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002957c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029587`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002949a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800294a5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800294b0`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029571`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18002957c`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180029587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800294cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800295de`

## string_xrefs

- `0x180029124`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800291ae`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180029560`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18002959b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800295c2`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800295f2`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180029619`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall CAvEndpointBuilder::OnBluetoothEndpointUnificationTimeout(LPCRITICAL_SECTION lpCriticalSection)
{
  HRESULT Instance; // eax
  int v3; // ebx
  HRESULT (__stdcall *QueryInterface)(IUnknown *, const IID *const, void **); // rbx
  __int64 v6; // rdx
  unsigned int v7; // r14d
  __int64 v8; // rax
  int v9; // eax
  struct IMMDevice *v10; // rdi
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v12; // eax
  struct IMMDeviceVtbl *lpVtbl; // rax
  CAvEndpointBuilder *v14; // rcx
  struct IPropertyStoreVtbl *v15; // rax
  const struct _tlgProvider_t *v16; // rax
  int v17; // r8d
  int v18; // r9d
  __int64 v19; // rdx
  __int64 v20; // rdx
  __int64 v21; // rdx
  int ppv; // [rsp+20h] [rbp-E0h]
  _BYTE v23[8]; // [rsp+40h] [rbp-C0h] BYREF
  struct IMMDevice *v24; // [rsp+48h] [rbp-B8h] BYREF
  __int64 *v25; // [rsp+50h] [rbp-B0h] BYREF
  struct IMMEndpointManager *v26; // [rsp+58h] [rbp-A8h] BYREF
  struct IPropertyStore *v27; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v28; // [rsp+68h] [rbp-98h] BYREF
  LPVOID pv; // [rsp+70h] [rbp-90h] BYREF
  int v30; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v31; // [rsp+7Ch] [rbp-84h] BYREF
  int v32; // [rsp+80h] [rbp-80h] BYREF
  PROPVARIANT v33[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v34; // [rsp+98h] [rbp-68h]
  PROPVARIANT pvar[2]; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v36; // [rsp+B0h] [rbp-50h]
  PROPVARIANT v37[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v38; // [rsp+C8h] [rbp-38h]
  PROPVARIANT v39; // [rsp+D0h] [rbp-30h] BYREF
  PROPVARIANT v40; // [rsp+D8h] [rbp-28h] BYREF
  _QWORD v41[2]; // [rsp+E0h] [rbp-20h] BYREF
  _DWORD v42[6]; // [rsp+F0h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+148h] [rbp+48h]

  EnterCriticalSection(lpCriticalSection);
  v41[1] = lpCriticalSection;
  wil::CoInitializeEx(v23);
  v26 = 0;
  Instance = CoCreateInstance(
               &GUID_06cca63e_9941_441b_b004_39f999ada412,
               0,
               0x17u,
               &GUID_6ca19947_8747_46ab_879e_349c4dbb88fb,
               (LPVOID *)&v26);
  v3 = Instance;
  if ( Instance < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AE3,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
LABEL_3:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
    if ( v23[0] )
      CoUninitialize();
    if ( lpCriticalSection )
      LeaveCriticalSection(lpCriticalSection);
    return (unsigned int)v3;
  }
  v25 = 0;
  v31 = 0;
  QueryInterface = g_DeviceEnumerator->lpVtbl[1].QueryInterface;
  wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(&v25);
  v3 = ((__int64 (__fastcall *)(struct IUnknown *, __int64, __int64, __int64 **))QueryInterface)(
         g_DeviceEnumerator,
         2,
         15,
         &v25);
  if ( v3 < 0 )
  {
    v6 = 6888;
LABEL_10:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v3,
      ppv);
LABEL_11:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    goto LABEL_3;
  }
  v3 = (*(__int64 (__fastcall **)(__int64 *, unsigned int *))(*v25 + 24))(v25, &v31);
  if ( v3 < 0 )
  {
    v6 = 6890;
    goto LABEL_10;
  }
  v7 = 0;
  if ( v31 )
  {
    while ( 1 )
    {
      v24 = 0;
      v8 = *v25;
      v24 = 0;
      v9 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, struct IMMDevice **))(v8 + 32))(v25, v7, &v24);
      v3 = v9;
      if ( v9 < 0 )
        break;
      v32 = 0;
      v28 = 0;
      v3 = wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(
             &v24,
             &v28);
      if ( v3 < 0 )
      {
        v21 = 6901;
        goto LABEL_53;
      }
      v3 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v28 + 32LL))(v28, &v32);
      if ( v3 < 0 )
      {
        v21 = 6902;
LABEL_53:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v21,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v3,
          ppv);
        goto LABEL_54;
      }
      if ( v32 < 0 )
      {
        pv = 0;
        v10 = v24;
        GetId = v24->lpVtbl->GetId;
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0);
        v12 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(v10, &pv);
        v3 = v12;
        if ( v12 < 0 )
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AFF,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)(unsigned int)v12,
            ppv);
          goto LABEL_49;
        }
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
        {
          WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 50, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, pv);
        }
        v27 = 0;
        lpVtbl = v24->lpVtbl;
        v27 = 0;
        v3 = ((__int64 (__fastcall *)(struct IMMDevice *, __int64, struct IPropertyStore **))lpVtbl->OpenPropertyStore)(
               v24,
               2,
               &v27);
        if ( v3 < 0 )
        {
          v20 = 6916;
LABEL_46:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v20,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)(unsigned int)v3,
            ppv);
          goto LABEL_47;
        }
        v3 = CAvEndpointBuilder::ClearUnifiedBluetoothEndpointProperties(v14, v27);
        if ( v3 < 0 )
        {
          v20 = 6919;
          goto LABEL_46;
        }
        *(_OWORD *)v33 = 0;
        v34 = 0;
        *(_OWORD *)v37 = 0;
        v38 = 0;
        *(_OWORD *)pvar = 0;
        v36 = 0;
        LOWORD(v33[0]) = 19;
        LODWORD(v33[1]) = 32;
        v3 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v27->lpVtbl->SetValue)(
               v27,
               PKEY_Endpoint_BluetoothUnificationState,
               v33);
        if ( v3 < 0 )
        {
          v19 = 6926;
LABEL_43:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)v19,
            (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
            (const char *)(unsigned int)v3,
            ppv);
          PropVariantClear(pvar);
          PropVariantClear(v37);
          PropVariantClear(v33);
LABEL_47:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
LABEL_49:
          if ( pv )
            CoTaskMemFree(pv);
LABEL_54:
          ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
          goto LABEL_56;
        }
        ((void (__fastcall *)(struct IPropertyStore *, __int64 *, PROPVARIANT *))v27->lpVtbl->GetValue)(
          v27,
          PKEY_Endpoint_Devnode,
          v37);
        v15 = v27->lpVtbl;
        v42[0] = 590439624;
        v42[1] = 1283267372;
        v42[2] = 1907779772;
        v42[3] = 1730509416;
        v42[4] = 1;
        ((void (__fastcall *)(struct IPropertyStore *, _DWORD *, PROPVARIANT *))v15->GetValue)(v27, v42, pvar);
        v16 = AudioEndpointBuilderTelemetryProvider::Provider();
        if ( *(_DWORD *)v16 > 4u && (unsigned __int8)tlgKeywordOn(v16, 0x400000000000LL, v16) )
        {
          v30 = 32;
          v39 = pvar[1];
          v40 = v37[1];
          v41[0] = 33556480;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v17,
            (unsigned int)&byte_180075E7F,
            v17,
            v18,
            (__int64)v41,
            (__int64)&v40,
            (__int64)&v39,
            (__int64)&v30);
        }
        v30 = 0;
        v3 = CheckJackConnection(v24, &v30);
        if ( v3 < 0 )
        {
          v19 = 6941;
          goto LABEL_43;
        }
        v3 = CAvEndpointBuilder::SetEndpointActive((CAvEndpointBuilder *)lpCriticalSection, v26, v24, v30);
        if ( v3 < 0 )
        {
          v19 = 6944;
          goto LABEL_43;
        }
        PropVariantClear(pvar);
        PropVariantClear(v37);
        PropVariantClear(v33);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v27);
        if ( pv )
          CoTaskMemFree(pv);
      }
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
      if ( ++v7 >= v31 )
        goto LABEL_35;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1AF0,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v9,
      ppv);
LABEL_56:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
    goto LABEL_11;
  }
LABEL_35:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v26);
  if ( v23[0] )
    CoUninitialize();
  if ( lpCriticalSection )
    LeaveCriticalSection(lpCriticalSection);
  return 0;
}

```

## disassembly

```asm
0x1800290b0  push    rbp
0x1800290b2  push    rbx
0x1800290b3  push    rsi
0x1800290b4  push    rdi
0x1800290b5  push    r14
0x1800290b7  push    r15
0x1800290b9  lea     rbp, [rsp-18h]
0x1800290be  sub     rsp, 118h
0x1800290c5  mov     rax, cs:__security_cookie
0x1800290cc  xor     rax, rsp
0x1800290cf  mov     [rbp+40h+var_38], rax
0x1800290d3  mov     rsi, rcx
0x1800290d6  call    cs:__imp_EnterCriticalSection
0x1800290dc  mov     [rbp+40h+var_58], rsi
0x1800290e0  lea     rcx, [rsp+140h+var_100]
0x1800290e5  call    ?CoInitializeEx@wil@@YA?AV?$unique_call@P6AXXZ$1?CoUninitialize@@YAXXZ$00@1@K@Z; wil::CoInitializeEx(ulong)
0x1800290ea  nop
0x1800290eb  xor     r15d, r15d
0x1800290ee  mov     [rsp+140h+var_E8], r15
0x1800290f3  lea     rax, [rsp+140h+var_E8]
0x1800290f8  mov     [rsp+140h+ppv], rax; int
0x1800290fd  lea     r9, _GUID_6ca19947_8747_46ab_879e_349c4dbb88fb; riid
0x180029104  xor     edx, edx; pUnkOuter
0x180029106  lea     r8d, [r15+17h]; dwClsContext
0x18002910a  lea     rcx, _GUID_06cca63e_9941_441b_b004_39f999ada412; rclsid
0x180029111  call    cs:__imp_CoCreateInstance
0x180029117  mov     ebx, eax
0x180029119  test    eax, eax
0x18002911b  jns     short loc_180029164
0x18002911d  mov     rcx, [rbp+48h]; this
0x180029121  mov     r9d, eax; char *
0x180029124  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18002912b  mov     edx, 1AE3h; void *
0x180029130  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180029135  nop
0x180029136  lea     rcx, [rsp+140h+var_E8]
0x18002913b  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180029140  nop
0x180029141  cmp     [rsp+140h+var_100], r15b
0x180029146  jz      short loc_18002914F
0x180029148  call    cs:__imp_CoUninitialize
0x18002914e  nop
0x18002914f  test    rsi, rsi
0x180029152  jz      short loc_18002915D
0x180029154  mov     rcx, rsi; lpCriticalSection
0x180029157  call    cs:__imp_LeaveCriticalSection
0x18002915d  mov     eax, ebx
0x18002915f  jmp     loc_18002952A
0x180029164  mov     [rsp+140h+var_F0], r15
0x180029169  mov     [rsp+140h+var_C4], r15d
0x18002916e  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180029175  mov     rcx, [rax]
0x180029178  mov     rbx, [rcx+18h]
0x18002917c  lea     rcx, [rsp+140h+var_F0]
0x180029181  call    ?reset@?$com_ptr_t@UIMMDeviceCollection@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDeviceCollection,wil::err_returncode_policy>::reset(void)
0x180029186  lea     r9, [rsp+140h+var_F0]
0x18002918b  mov     edx, 2
0x180029190  lea     r8d, [rdx+0Dh]
0x180029194  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18002919b  mov     rax, rbx
0x18002919e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291a3  mov     ebx, eax
0x1800291a5  test    eax, eax
0x1800291a7  jns     short loc_1800291D1
0x1800291a9  mov     edx, 1AE8h; void *
0x1800291ae  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800291b5  mov     r9d, ebx; char *
0x1800291b8  mov     rcx, [rbp+48h]; this
0x1800291bc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800291c1  nop
0x1800291c2  lea     rcx, [rsp+140h+var_F0]
0x1800291c7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800291cc  jmp     loc_180029136
0x1800291d1  mov     rcx, [rsp+140h+var_F0]
0x1800291d6  mov     rax, [rcx]
0x1800291d9  lea     rdx, [rsp+140h+var_C4]
0x1800291de  mov     rax, [rax+18h]
0x1800291e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800291e7  mov     ebx, eax
0x1800291e9  test    eax, eax
0x1800291eb  jns     short loc_1800291F4
0x1800291ed  mov     edx, 1AEAh
0x1800291f2  jmp     short loc_1800291AE
0x1800291f4  mov     r14d, r15d
0x1800291f7  cmp     [rsp+140h+var_C4], r15d
0x1800291fc  jbe     loc_1800294F6
0x180029202  mov     [rsp+140h+var_F8], r15
0x180029207  mov     rcx, [rsp+140h+var_F0]
0x18002920c  mov     rax, [rcx]
0x18002920f  mov     [rsp+140h+var_F8], r15
0x180029214  lea     r8, [rsp+140h+var_F8]
0x180029219  mov     edx, r14d
0x18002921c  mov     rax, [rax+20h]
0x180029220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029225  mov     ebx, eax
0x180029227  test    eax, eax
0x180029229  js      loc_180029612
0x18002922f  mov     [rbp+40h+var_C0], r15d
0x180029233  mov     [rsp+140h+var_D8], r15
0x180029238  lea     rdx, [rsp+140h+var_D8]
0x18002923d  lea     rcx, [rsp+140h+var_F8]
0x180029242  call    ??$com_query_to_nothrow@UIMMEndpointInternal@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIMMEndpointInternal@@@Z; wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IMMEndpointInternal * *)
0x180029247  mov     ebx, eax
0x180029249  test    eax, eax
0x18002924b  js      loc_1800295ED
0x180029251  mov     rcx, [rsp+140h+var_D8]
0x180029256  mov     rax, [rcx]
0x180029259  lea     rdx, [rbp+40h+var_C0]
0x18002925d  mov     rax, [rax+20h]
0x180029261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029266  mov     ebx, eax
0x180029268  test    eax, eax
0x18002926a  js      loc_1800295E6
0x180029270  test    [rbp+40h+var_C0], 80000000h
0x180029277  jz      loc_1800294D3
0x18002927d  mov     [rsp+140h+pv], r15
0x180029282  mov     rdi, [rsp+140h+var_F8]
0x180029287  mov     rax, [rdi]
0x18002928a  mov     rbx, [rax+28h]
0x18002928e  xor     edx, edx
0x180029290  lea     rcx, [rsp+140h+pv]
0x180029295  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18002929a  lea     rdx, [rsp+140h+pv]
0x18002929f  mov     rcx, rdi
0x1800292a2  mov     rax, rbx
0x1800292a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800292aa  mov     ebx, eax
0x1800292ac  test    eax, eax
0x1800292ae  js      loc_1800295BB
0x1800292b4  lea     rax, WPP_GLOBAL_Control
0x1800292bb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800292c2  cmp     rcx, rax
0x1800292c5  jz      short loc_1800292F0
0x1800292c7  test    dword ptr [rcx+1Ch], 80000h
0x1800292ce  jz      short loc_1800292F0
0x1800292d0  cmp     byte ptr [rcx+19h], 5
0x1800292d4  jb      short loc_1800292F0
0x1800292d6  mov     edx, 32h ; '2'
0x1800292db  mov     r9, [rsp+140h+pv]
0x1800292e0  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x1800292e7  mov     rcx, [rcx+10h]
0x1800292eb  call    WPP_SF_S
0x1800292f0  mov     [rsp+140h+var_E0], r15
0x1800292f5  mov     rcx, [rsp+140h+var_F8]
0x1800292fa  mov     rax, [rcx]
0x1800292fd  mov     [rsp+140h+var_E0], r15
0x180029302  lea     r8, [rsp+140h+var_E0]
0x180029307  mov     edx, 2
0x18002930c  mov     rax, [rax+20h]
0x180029310  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029315  mov     ebx, eax
0x180029317  test    eax, eax
0x180029319  js      loc_180029596
0x18002931f  mov     rdx, [rsp+140h+var_E0]; struct IPropertyStore *
0x180029324  call    ?ClearUnifiedBluetoothEndpointProperties@CAvEndpointBuilder@@AEAAJPEAUIPropertyStore@@@Z; CAvEndpointBuilder::ClearUnifiedBluetoothEndpointProperties(IPropertyStore *)
0x180029329  mov     ebx, eax
0x18002932b  test    eax, eax
0x18002932d  js      loc_18002958F
0x180029333  xorps   xmm0, xmm0
0x180029336  xor     eax, eax
0x180029338  movups  xmmword ptr [rbp+40h+var_B8], xmm0
0x18002933c  mov     [rbp+40h+var_A8], rax
0x180029340  movups  xmmword ptr [rbp+40h+var_88], xmm0
0x180029344  mov     [rbp+40h+var_78], rax
0x180029348  movups  xmmword ptr [rbp+40h+pvar], xmm0
0x18002934c  mov     [rbp+40h+var_90], rax
0x180029350  mov     eax, 13h
0x180029355  mov     word ptr [rbp+40h+var_B8], ax
0x180029359  mov     dword ptr [rbp+40h+var_B8+8], 20h ; ' '
0x180029360  mov     rcx, [rsp+140h+var_E0]
0x180029365  mov     rax, [rcx]
0x180029368  lea     r8, [rbp+40h+var_B8]
0x18002936c  lea     rdx, PKEY_Endpoint_BluetoothUnificationState
0x180029373  mov     rax, [rax+30h]
0x180029377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002937c  mov     ebx, eax
0x18002937e  test    eax, eax
0x180029380  js      loc_180029554
0x180029386  mov     rcx, [rsp+140h+var_E0]
0x18002938b  mov     rax, [rcx]
0x18002938e  lea     r8, [rbp+40h+var_88]
0x180029392  lea     rdx, PKEY_Endpoint_Devnode
0x180029399  mov     rax, [rax+28h]
0x18002939d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293a2  mov     rcx, [rsp+140h+var_E0]
0x1800293a7  mov     rax, [rcx]
0x1800293aa  mov     [rbp+40h+var_50], 233164C8h
0x1800293b1  mov     [rbp+40h+var_4C], 4C7D1B2Ch
0x1800293b8  mov     [rbp+40h+var_48], 71B668BCh
0x1800293bf  mov     [rbp+40h+var_44], 67257A68h
0x1800293c6  mov     [rbp+40h+var_40], 1
0x1800293cd  lea     r8, [rbp+40h+pvar]
0x1800293d1  lea     rdx, [rbp+40h+var_50]
0x1800293d5  mov     rax, [rax+28h]
0x1800293d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800293de  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x1800293e3  mov     r8, rax
0x1800293e6  mov     ecx, [rax]
0x1800293e8  cmp     ecx, 4
0x1800293eb  jbe     short loc_180029457
0x1800293ed  mov     rdx, 400000000000h
0x1800293f7  mov     rcx, rax
0x1800293fa  call    _tlgKeywordOn
0x1800293ff  test    al, al
0x180029401  jz      short loc_180029457
0x180029403  mov     [rsp+140h+var_C8], 20h ; ' '
0x18002940b  mov     rcx, [rbp+40h+pvar+8]
0x18002940f  mov     [rbp+40h+var_70], rcx
0x180029413  mov     rax, [rbp+40h+var_88+8]
0x180029417  mov     [rbp+40h+var_68], rax
0x18002941b  mov     [rbp+40h+var_60], 2000800h
0x180029423  lea     rax, [rsp+140h+var_C8]
0x180029428  mov     [rsp+140h+var_108], rax
0x18002942d  lea     rax, [rbp+40h+var_70]
0x180029431  mov     [rsp+140h+var_110], rax
0x180029436  lea     rax, [rbp+40h+var_68]
0x18002943a  mov     [rsp+140h+var_118], rax
0x18002943f  lea     rax, [rbp+40h+var_60]
0x180029443  mov     [rsp+140h+ppv], rax
0x180029448  lea     rdx, byte_180075E7F
0x18002944f  mov     rcx, r8
0x180029452  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U2@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@4AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x180029457  mov     [rsp+140h+var_C8], r15d
0x18002945c  lea     rdx, [rsp+140h+var_C8]; int *
0x180029461  mov     rcx, [rsp+140h+var_F8]; struct IMMDevice *
0x180029466  call    ?CheckJackConnection@@YAJPEAUIMMDevice@@PEAH@Z; CheckJackConnection(IMMDevice *,int *)
0x18002946b  mov     ebx, eax
0x18002946d  test    eax, eax
0x18002946f  js      loc_18002954D
0x180029475  mov     r9d, [rsp+140h+var_C8]; int
0x18002947a  mov     r8, [rsp+140h+var_F8]; struct IMMDevice *
0x18002947f  mov     rdx, [rsp+140h+var_E8]; struct IMMEndpointManager *
0x180029484  mov     rcx, rsi; this
0x180029487  call    ?SetEndpointActive@CAvEndpointBuilder@@AEAAJPEAUIMMEndpointManager@@PEAUIMMDevice@@H@Z; CAvEndpointBuilder::SetEndpointActive(IMMEndpointManager *,IMMDevice *,int)
0x18002948c  mov     ebx, eax
0x18002948e  test    eax, eax
0x180029490  js      loc_180029546
0x180029496  lea     rcx, [rbp+40h+pvar]; pvar
0x18002949a  call    cs:__imp_PropVariantClear
0x1800294a0  nop
0x1800294a1  lea     rcx, [rbp+40h+var_88]; pvar
0x1800294a5  call    cs:__imp_PropVariantClear
0x1800294ab  nop
0x1800294ac  lea     rcx, [rbp+40h+var_B8]; pvar
0x1800294b0  call    cs:__imp_PropVariantClear
0x1800294b6  nop
0x1800294b7  lea     rcx, [rsp+140h+var_E0]
0x1800294bc  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800294c1  nop
0x1800294c2  mov     rcx, [rsp+140h+pv]; pv
0x1800294c7  test    rcx, rcx
0x1800294ca  jz      short loc_1800294D3
0x1800294cc  call    cs:__imp_CoTaskMemFree
0x1800294d2  nop
0x1800294d3  lea     rcx, [rsp+140h+var_D8]
0x1800294d8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800294dd  nop
0x1800294de  lea     rcx, [rsp+140h+var_F8]
0x1800294e3  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800294e8  inc     r14d
0x1800294eb  cmp     r14d, [rsp+140h+var_C4]
0x1800294f0  jb      loc_180029202
0x1800294f6  lea     rcx, [rsp+140h+var_F0]
0x1800294fb  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180029500  nop
0x180029501  lea     rcx, [rsp+140h+var_E8]
0x180029506  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18002950b  nop
0x18002950c  cmp     [rsp+140h+var_100], r15b
0x180029511  jz      short loc_18002951A
0x180029513  call    cs:__imp_CoUninitialize
0x180029519  nop
0x18002951a  test    rsi, rsi
0x18002951d  jz      short loc_180029528
0x18002951f  mov     rcx, rsi; lpCriticalSection
0x180029522  call    cs:__imp_LeaveCriticalSection
0x180029528  xor     eax, eax
0x18002952a  mov     rcx, [rbp+40h+var_38]
0x18002952e  xor     rcx, rsp; StackCookie
0x180029531  call    __security_check_cookie
0x180029536  add     rsp, 118h
0x18002953d  pop     r15
0x18002953f  pop     r14
0x180029541  pop     rdi
0x180029542  pop     rsi
0x180029543  pop     rbx
0x180029544  pop     rbp
0x180029545  retn
0x180029546  mov     edx, 1B20h
0x18002954b  jmp     short loc_180029559
0x18002954d  mov     edx, 1B1Dh
0x180029552  jmp     short loc_180029559
0x180029554  mov     edx, 1B0Eh; void *
0x180029559  mov     rcx, [rbp+48h]; this
0x18002955d  mov     r9d, ebx; char *
0x180029560  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180029567  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002956c  nop
0x18002956d  lea     rcx, [rbp+40h+pvar]; pvar
0x180029571  call    cs:__imp_PropVariantClear
  ... truncated ...
```
