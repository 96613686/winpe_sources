# CheckBluetoothEndpoint(int,__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001,int,wil::unique_struct<tagPROPVARIANT,long (*)(tagPROPVARIANT *),&PropVariantClear(tagPROPVARIANT *),void (*)(tagPROPVARIANT *),&PropVariantInit(tagPROPVARIANT *)> &,IMMDeviceCollection *,IMMDevice * *)

- ea: `0x1800165ec`
- end: `0x180016b1d`
- name: `?CheckBluetoothEndpoint@@YAJHW4__MIDL___MIDL_itf_mmdeviceapi_0000_0000_0001@@HAEAV?$unique_struct@UtagPROPVARIANT@@P6AJPEAU1@@Z$1?PropVariantClear@@YAJ0@ZP6AX0@Z$1?PropVariantInit@@YAX0@Z@wil@@PEAUIMMDeviceCollection@@PEAPEAUIMMDevice@@@Z`
- size: `1329`
- prototype: `__int64 __fastcall(unsigned int, int, int, __int64, __int64 *, __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180016394`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x1800165ec`
- `0x18001d960`
- `0x180021030`
- `0x180023d28`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800167a9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800168c8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800168e3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016952`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016ab5`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800167a9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800168c8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800168e3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016952`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180016ab5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800166a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800167d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ad9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800166a1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800167d1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180016ad9`

## string_xrefs

- `0x18001665a`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18001674b`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180016793`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180016828`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x1800168b2`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CheckBluetoothEndpoint(unsigned int a1, int a2, int a3, __int64 a4, __int64 *a5, __int64 *a6)
{
  __int64 v9; // rax
  int v10; // eax
  unsigned int v11; // ebx
  __int64 v12; // rbx
  __int64 (__fastcall *v13)(__int64, __int64, __int64 *); // rdi
  __int64 v14; // rcx
  int v15; // eax
  int v16; // eax
  _QWORD *v17; // rcx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rbx
  __int64 (__fastcall *v23)(__int64, GUID *, __int64); // rdi
  __int64 v24; // rcx
  __int64 v25; // rdi
  __int64 (__fastcall *v26)(__int64, _QWORD, __int64 *); // rbx
  __int64 v27; // rdi
  __int64 (__fastcall *v28)(__int64, struct IConnector **); // rbx
  __int64 v29; // rdi
  __int64 (__fastcall *v30)(__int64, LPVOID *); // rbx
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  __int64 v32; // rcx
  int *v34; // [rsp+20h] [rbp-79h]
  __int64 v35; // [rsp+30h] [rbp-69h] BYREF
  struct IConnector *v36; // [rsp+38h] [rbp-61h] BYREF
  LPVOID pv; // [rsp+40h] [rbp-59h] BYREF
  __int64 v38; // [rsp+48h] [rbp-51h] BYREF
  __int64 v39; // [rsp+50h] [rbp-49h] BYREF
  __int64 v40; // [rsp+58h] [rbp-41h] BYREF
  __int64 v41; // [rsp+60h] [rbp-39h] BYREF
  __int64 v42; // [rsp+68h] [rbp-31h] BYREF
  PROPVARIANT pvar[2]; // [rsp+70h] [rbp-29h] BYREF
  __int64 v44; // [rsp+80h] [rbp-19h]
  int v45; // [rsp+88h] [rbp-11h] BYREF
  int v46; // [rsp+8Ch] [rbp-Dh] BYREF
  PROPVARIANT v47[2]; // [rsp+90h] [rbp-9h] BYREF
  __int64 v48; // [rsp+A0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+4Fh]

  v40 = 0;
  v42 = 0;
  v41 = 0;
  pv = 0;
  v35 = 0;
  v36 = 0;
  v45 = 0;
  v46 = 0;
  v9 = *a5;
  v39 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, __int64 *))(v9 + 32))(a5, a1, &v39);
  v11 = v10;
  if ( v10 >= 0 )
  {
    v12 = v39;
    v13 = *(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v39 + 32LL);
    v14 = v40;
    v40 = 0;
    if ( v14 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 16LL))(v14);
    v15 = v13(v12, 2, &v40);
    v11 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x151C,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v15,
        (int)v34);
      goto LABEL_18;
    }
    *(_OWORD *)pvar = 0;
    v44 = 0;
    v16 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v40 + 40LL))(
            v40,
            &PKEY_Device_ContainerId,
            pvar);
    v11 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1520,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v16,
        (int)v34);
LABEL_17:
      PropVariantClear(pvar);
LABEL_18:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      if ( pv )
        CoTaskMemFree(pv);
LABEL_61:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v41);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v42);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v40);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
      return v11;
    }
    if ( LOWORD(pvar[0]) != 72 )
      goto LABEL_58;
    v17 = *(_QWORD **)(a4 + 8);
    v18 = *v17 - *(_QWORD *)pvar[1];
    if ( *v17 == *(_QWORD *)pvar[1] )
      v18 = v17[1] - *((_QWORD *)pvar[1] + 1);
    if ( v18 )
    {
LABEL_58:
      PropVariantClear(pvar);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v36);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
      if ( pv )
        CoTaskMemFree(pv);
      v11 = 0;
      goto LABEL_61;
    }
    LODWORD(a5) = 0;
    v38 = 0;
    v19 = wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(
            &v39,
            (__int64)&v38);
    v11 = v19;
    if ( v19 < 0 )
    {
      v20 = 5419;
LABEL_26:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v20,
        (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
        (const char *)(unsigned int)v19,
        (int)v34);
LABEL_27:
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
      goto LABEL_17;
    }
    v19 = (*(__int64 (__fastcall **)(__int64, __int64 **))(*(_QWORD *)v38 + 32LL))(v38, &a5);
    v11 = v19;
    if ( v19 < 0 )
    {
      v20 = 5420;
      goto LABEL_26;
    }
    if ( ((unsigned int)a5 & 0x80000001) != 0 )
    {
      if ( a2 )
      {
LABEL_37:
        v22 = v39;
        v23 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v39 + 24LL);
        v24 = v42;
        v42 = 0;
        if ( v24 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
        v34 = (int *)&v42;
        v19 = v23(v22, &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f, 23);
        v11 = v19;
        if ( v19 < 0 )
        {
          v20 = 5456;
          goto LABEL_26;
        }
        v25 = v42;
        v26 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v42 + 32LL);
        wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v41);
        v19 = v26(v25, 0, &v41);
        v11 = v19;
        if ( v19 < 0 )
        {
          v20 = 5457;
          goto LABEL_26;
        }
        v27 = v41;
        v28 = *(__int64 (__fastcall **)(__int64, struct IConnector **))(*(_QWORD *)v41 + 64LL);
        wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v36);
        v19 = v28(v27, &v36);
        v11 = v19;
        if ( v19 < 0 )
        {
          v20 = 5458;
          goto LABEL_26;
        }
        v29 = v41;
        v30 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v41 + 80LL);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
          &pv,
          0);
        v19 = v30(v29, &pv);
        v11 = v19;
        if ( v19 < 0 )
        {
          v20 = 5459;
          goto LABEL_26;
        }
        Release = g_DeviceEnumerator->lpVtbl[1].Release;
        v35 = 0;
        v19 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, __int64 *))Release)(g_DeviceEnumerator, pv, &v35);
        v11 = v19;
        if ( v19 < 0 )
        {
          v20 = 5460;
          goto LABEL_26;
        }
        v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v35 + 48LL))(v35, &v45);
        v11 = v19;
        if ( v19 < 0 )
        {
          v20 = 5461;
          goto LABEL_26;
        }
        if ( v45 == 1 )
        {
          GetJackProperties(v36, &v46, 0, 0, 0, 0);
          if ( !v46 )
          {
            v32 = v39;
            v39 = 0;
            *a6 = v32;
          }
        }
        goto LABEL_57;
      }
      *(_OWORD *)v47 = 0;
      v48 = 0;
      v21 = (*(__int64 (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v40 + 40LL))(
              v40,
              PKEY_Endpoint_IsMuxedEndpoint,
              v47);
      v11 = v21;
      if ( v21 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x153E,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)(unsigned int)v21,
          (int)v34);
        PropVariantClear(v47);
        goto LABEL_27;
      }
      if ( a3 )
      {
        if ( LOWORD(v47[0]) )
        {
LABEL_36:
          PropVariantClear(v47);
          goto LABEL_37;
        }
      }
      else if ( LOWORD(v47[0]) != 11 || LOWORD(v47[1]) != 0xFFFF )
      {
        goto LABEL_36;
      }
      PropVariantClear(v47);
    }
LABEL_57:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
    goto LABEL_58;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x151B,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v10,
    (int)v34);
  if ( v41 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
  if ( v42 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  return v11;
}

```

## disassembly

```asm
0x1800165ec  push    rbp
0x1800165ee  push    rbx
0x1800165ef  push    rsi
0x1800165f0  push    rdi
0x1800165f1  push    r12
0x1800165f3  push    r14
0x1800165f5  push    r15
0x1800165f7  lea     rbp, [rsp-17h]
0x1800165fc  sub     rsp, 0B0h
0x180016603  mov     rsi, r9
0x180016606  mov     r15d, r8d
0x180016609  mov     r14d, edx
0x18001660c  mov     edx, ecx
0x18001660e  xor     r12d, r12d
0x180016611  mov     [rbp+47h+var_88], r12
0x180016615  mov     [rbp+47h+var_78], r12
0x180016619  mov     [rbp+47h+var_80], r12
0x18001661d  mov     [rbp+47h+pv], r12
0x180016621  mov     [rbp+47h+var_B0], r12
0x180016625  mov     [rbp+47h+var_A8], r12
0x180016629  mov     [rbp+47h+var_58], r12d
0x18001662d  mov     [rbp+47h+var_54], r12d
0x180016631  mov     rcx, [rbp+47h+arg_20]
0x180016635  mov     rax, [rcx]
0x180016638  mov     [rbp+47h+var_90], r12
0x18001663c  lea     r8, [rbp+47h+var_90]
0x180016640  mov     rax, [rax+20h]
0x180016644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016649  mov     ebx, eax
0x18001664b  test    eax, eax
0x18001664d  jns     loc_180016705
0x180016653  mov     rcx, [rbp+4Fh]; this
0x180016657  mov     r9d, eax; char *
0x18001665a  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180016661  mov     edx, 151Bh; void *
0x180016666  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001666b  nop
0x18001666c  mov     rcx, [rbp+47h+var_A8]
0x180016670  test    rcx, rcx
0x180016673  jz      short loc_180016682
0x180016675  mov     rax, [rcx]
0x180016678  mov     rax, [rax+10h]
0x18001667c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016681  nop
0x180016682  mov     rcx, [rbp+47h+var_B0]
0x180016686  test    rcx, rcx
0x180016689  jz      short loc_180016698
0x18001668b  mov     rax, [rcx]
0x18001668e  mov     rax, [rax+10h]
0x180016692  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016697  nop
0x180016698  mov     rcx, [rbp+47h+pv]; pv
0x18001669c  test    rcx, rcx
0x18001669f  jz      short loc_1800166A8
0x1800166a1  call    cs:__imp_CoTaskMemFree
0x1800166a7  nop
0x1800166a8  mov     rcx, [rbp+47h+var_80]
0x1800166ac  test    rcx, rcx
0x1800166af  jz      short loc_1800166BE
0x1800166b1  mov     rax, [rcx]
0x1800166b4  mov     rax, [rax+10h]
0x1800166b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166bd  nop
0x1800166be  mov     rcx, [rbp+47h+var_78]
0x1800166c2  test    rcx, rcx
0x1800166c5  jz      short loc_1800166D4
0x1800166c7  mov     rax, [rcx]
0x1800166ca  mov     rax, [rax+10h]
0x1800166ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166d3  nop
0x1800166d4  mov     rcx, [rbp+47h+var_88]
0x1800166d8  test    rcx, rcx
0x1800166db  jz      short loc_1800166EA
0x1800166dd  mov     rax, [rcx]
0x1800166e0  mov     rax, [rax+10h]
0x1800166e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166e9  nop
0x1800166ea  mov     rcx, [rbp+47h+var_90]
0x1800166ee  test    rcx, rcx
0x1800166f1  jz      short loc_180016700
0x1800166f3  mov     rax, [rcx]
0x1800166f6  mov     rax, [rax+10h]
0x1800166fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166ff  nop
0x180016700  jmp     loc_180016B09
0x180016705  mov     rbx, [rbp+47h+var_90]
0x180016709  mov     rax, [rbx]
0x18001670c  mov     rdi, [rax+20h]
0x180016710  mov     rcx, [rbp+47h+var_88]
0x180016714  mov     [rbp+47h+var_88], r12
0x180016718  test    rcx, rcx
0x18001671b  jz      short loc_18001672A
0x18001671d  mov     rdx, [rcx]
0x180016720  mov     rax, [rdx+10h]
0x180016724  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016729  nop
0x18001672a  lea     r8, [rbp+47h+var_88]
0x18001672e  mov     edx, 2
0x180016733  mov     rcx, rbx
0x180016736  mov     rax, rdi
0x180016739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001673e  mov     ebx, eax
0x180016740  test    eax, eax
0x180016742  jns     short loc_18001675E
0x180016744  mov     rcx, [rbp+4Fh]; this
0x180016748  mov     r9d, eax; char *
0x18001674b  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180016752  mov     edx, 151Ch; void *
0x180016757  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001675c  jmp     short loc_1800167B0
0x18001675e  xorps   xmm0, xmm0
0x180016761  xor     eax, eax
0x180016763  movups  xmmword ptr [rbp+47h+pvar], xmm0
0x180016767  mov     [rbp+47h+var_60], rax
0x18001676b  mov     rcx, [rbp+47h+var_88]
0x18001676f  mov     rax, [rcx]
0x180016772  lea     r8, [rbp+47h+pvar]
0x180016776  lea     rdx, PKEY_Device_ContainerId
0x18001677d  mov     rax, [rax+28h]
0x180016781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016786  mov     ebx, eax
0x180016788  test    eax, eax
0x18001678a  jns     short loc_1800167DC
0x18001678c  mov     rcx, [rbp+4Fh]; this
0x180016790  mov     r9d, eax; char *
0x180016793  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001679a  mov     edx, 1520h; void *
0x18001679f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800167a4  nop
0x1800167a5  lea     rcx, [rbp+47h+pvar]; pvar
0x1800167a9  call    cs:__imp_PropVariantClear
0x1800167af  nop
0x1800167b0  lea     rcx, [rbp+47h+var_A8]
0x1800167b4  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800167b9  nop
0x1800167ba  lea     rcx, [rbp+47h+var_B0]
0x1800167be  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800167c3  nop
0x1800167c4  mov     rcx, [rbp+47h+pv]; pv
0x1800167c8  test    rcx, rcx
0x1800167cb  jz      loc_180016AE2
0x1800167d1  call    cs:__imp_CoTaskMemFree
0x1800167d7  jmp     loc_180016AE2
0x1800167dc  cmp     word ptr [rbp+47h+pvar], 48h ; 'H'
0x1800167e1  jnz     loc_180016AB1
0x1800167e7  mov     rcx, [rsi+8]
0x1800167eb  mov     rdx, [rbp+47h+pvar+8]
0x1800167ef  mov     rax, [rcx]
0x1800167f2  sub     rax, [rdx]
0x1800167f5  jnz     short loc_1800167FF
0x1800167f7  mov     rax, [rcx+8]
0x1800167fb  sub     rax, [rdx+8]
0x1800167ff  test    rax, rax
0x180016802  jnz     loc_180016AB1
0x180016808  mov     dword ptr [rbp+47h+arg_20], r12d
0x18001680c  mov     [rbp+47h+var_98], r12
0x180016810  lea     rdx, [rbp+47h+var_98]
0x180016814  lea     rcx, [rbp+47h+var_90]
0x180016818  call    ??$com_query_to_nothrow@UIMMEndpointInternal@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIMMEndpointInternal@@@Z; wil::com_query_to_nothrow<IMMEndpointInternal,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IMMEndpointInternal * *)
0x18001681d  mov     ebx, eax
0x18001681f  test    eax, eax
0x180016821  jns     short loc_18001684A
0x180016823  mov     edx, 152Bh; void *
0x180016828  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001682f  mov     r9d, eax; char *
0x180016832  mov     rcx, [rbp+4Fh]; this
0x180016836  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001683b  nop
0x18001683c  lea     rcx, [rbp+47h+var_98]
0x180016840  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180016845  jmp     loc_1800167A5
0x18001684a  mov     rcx, [rbp+47h+var_98]
0x18001684e  mov     rax, [rcx]
0x180016851  lea     rdx, [rbp+47h+arg_20]
0x180016855  mov     rax, [rax+20h]
0x180016859  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001685e  mov     ebx, eax
0x180016860  test    eax, eax
0x180016862  jns     short loc_18001686B
0x180016864  mov     edx, 152Ch
0x180016869  jmp     short loc_180016828
0x18001686b  test    dword ptr [rbp+47h+arg_20], 80000001h
0x180016872  jz      loc_180016AA7
0x180016878  test    r14d, r14d
0x18001687b  jnz     short loc_1800168E9
0x18001687d  xorps   xmm0, xmm0
0x180016880  xor     eax, eax
0x180016882  movups  xmmword ptr [rbp+47h+var_50], xmm0
0x180016886  mov     [rbp+47h+var_40], rax
0x18001688a  mov     rcx, [rbp+47h+var_88]
0x18001688e  mov     rax, [rcx]
0x180016891  lea     r8, [rbp+47h+var_50]
0x180016895  lea     rdx, PKEY_Endpoint_IsMuxedEndpoint
0x18001689c  mov     rax, [rax+28h]
0x1800168a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800168a5  mov     ebx, eax
0x1800168a7  test    eax, eax
0x1800168a9  jns     short loc_1800168D3
0x1800168ab  mov     rcx, [rbp+4Fh]; this
0x1800168af  mov     r9d, eax; char *
0x1800168b2  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x1800168b9  mov     edx, 153Eh; void *
0x1800168be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800168c3  nop
0x1800168c4  lea     rcx, [rbp+47h+var_50]; pvar
0x1800168c8  call    cs:__imp_PropVariantClear
0x1800168ce  jmp     loc_18001683C
0x1800168d3  test    r15d, r15d
0x1800168d6  jz      short loc_180016940
0x1800168d8  cmp     word ptr [rbp+47h+var_50], r12w
0x1800168dd  jz      short loc_18001694E
0x1800168df  lea     rcx, [rbp+47h+var_50]; pvar
0x1800168e3  call    cs:__imp_PropVariantClear
0x1800168e9  mov     rbx, [rbp+47h+var_90]
0x1800168ed  mov     rax, [rbx]
0x1800168f0  mov     rdi, [rax+18h]
0x1800168f4  mov     rcx, [rbp+47h+var_78]
0x1800168f8  mov     [rbp+47h+var_78], r12
0x1800168fc  test    rcx, rcx
0x1800168ff  jz      short loc_18001690E
0x180016901  mov     rax, [rcx]
0x180016904  mov     rax, [rax+10h]
0x180016908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001690d  nop
0x18001690e  lea     rax, [rbp+47h+var_78]
0x180016912  mov     [rsp+0E0h+var_C0], rax
0x180016917  xor     r9d, r9d
0x18001691a  lea     r8d, [r9+17h]
0x18001691e  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180016925  mov     rcx, rbx
0x180016928  mov     rax, rdi
0x18001692b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016930  mov     ebx, eax
0x180016932  test    eax, eax
0x180016934  jns     short loc_18001695D
0x180016936  mov     edx, 1550h
0x18001693b  jmp     loc_180016828
0x180016940  cmp     word ptr [rbp+47h+var_50], 0Bh
0x180016945  jnz     short loc_1800168DF
0x180016947  cmp     word ptr [rbp+47h+var_50+8], 0FFFFh
0x18001694c  jnz     short loc_1800168DF
0x18001694e  lea     rcx, [rbp+47h+var_50]; pvar
0x180016952  call    cs:__imp_PropVariantClear
0x180016958  jmp     loc_180016AA7
0x18001695d  mov     rdi, [rbp+47h+var_78]
0x180016961  mov     rax, [rdi]
0x180016964  mov     rbx, [rax+20h]
0x180016968  lea     rcx, [rbp+47h+var_80]
0x18001696c  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x180016971  lea     r8, [rbp+47h+var_80]
0x180016975  xor     edx, edx
0x180016977  mov     rcx, rdi
0x18001697a  mov     rax, rbx
0x18001697d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016982  mov     ebx, eax
0x180016984  test    eax, eax
0x180016986  jns     short loc_180016992
0x180016988  mov     edx, 1551h
0x18001698d  jmp     loc_180016828
0x180016992  mov     rdi, [rbp+47h+var_80]
0x180016996  mov     rax, [rdi]
0x180016999  mov     rbx, [rax+40h]
0x18001699d  lea     rcx, [rbp+47h+var_A8]
0x1800169a1  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x1800169a6  lea     rdx, [rbp+47h+var_A8]
0x1800169aa  mov     rcx, rdi
0x1800169ad  mov     rax, rbx
0x1800169b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169b5  mov     ebx, eax
0x1800169b7  test    eax, eax
0x1800169b9  jns     short loc_1800169C5
0x1800169bb  mov     edx, 1552h
0x1800169c0  jmp     loc_180016828
0x1800169c5  mov     rdi, [rbp+47h+var_80]
0x1800169c9  mov     rax, [rdi]
0x1800169cc  mov     rbx, [rax+50h]
0x1800169d0  xor     edx, edx
0x1800169d2  lea     rcx, [rbp+47h+pv]
0x1800169d6  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800169db  lea     rdx, [rbp+47h+pv]
0x1800169df  mov     rcx, rdi
0x1800169e2  mov     rax, rbx
0x1800169e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800169ea  mov     ebx, eax
0x1800169ec  test    eax, eax
0x1800169ee  jns     short loc_1800169FA
0x1800169f0  mov     edx, 1553h
0x1800169f5  jmp     loc_180016828
0x1800169fa  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180016a01  mov     rax, [r9]
0x180016a04  mov     rbx, [rax+28h]
0x180016a08  mov     rcx, [rbp+47h+var_B0]
0x180016a0c  mov     [rbp+47h+var_B0], r12
0x180016a10  test    rcx, rcx
0x180016a13  jz      short loc_180016A28
0x180016a15  mov     rax, [rcx]
0x180016a18  mov     rax, [rax+10h]
0x180016a1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a21  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180016a28  lea     r8, [rbp+47h+var_B0]
  ... truncated ...
```
