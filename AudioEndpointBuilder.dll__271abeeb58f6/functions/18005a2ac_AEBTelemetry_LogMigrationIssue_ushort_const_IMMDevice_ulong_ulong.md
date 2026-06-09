# AEBTelemetry::LogMigrationIssue(ushort const *,IMMDevice *,ulong,ulong)

- ea: `0x18005a2ac`
- end: `0x18005a724`
- name: `?LogMigrationIssue@AEBTelemetry@@SAXPEBGPEAUIMMDevice@@KK@Z`
- size: `1144`
- prototype: `void __fastcall(const unsigned __int16 *, struct IMMDevice *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180039ef4`

## callees

- `0x180002b7c`
- `0x180006b0c`
- `0x18000fb60`
- `0x18001f374`
- `0x1800252a4`
- `0x180029c9c`
- `0x18005a2ac`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a4d4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a692`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a69d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6e8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a4d4`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a692`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a69d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6a8`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6b3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6be`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6cc`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6da`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a6e8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a6f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a6f8`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall AEBTelemetry::LogMigrationIssue(const unsigned __int16 *a1, struct IMMDevice *a2, int a3, int a4)
{
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v9; // ebx
  struct IMMDeviceVtbl *lpVtbl; // rax
  const struct _tlgProvider_t *v11; // rax
  int v12; // r8d
  int v13; // r9d
  PROPVARIANT v14; // rcx
  GUID *v15; // rax
  char v16; // al
  char v17; // cl
  char v18; // cl
  PROPVARIANT v19; // rax
  PROPVARIANT v20; // rax
  PROPVARIANT v21; // rax
  char v22; // [rsp+A8h] [rbp-80h] BYREF
  char v23; // [rsp+A9h] [rbp-7Fh] BYREF
  char v24[6]; // [rsp+AAh] [rbp-7Eh] BYREF
  __int64 v25; // [rsp+B0h] [rbp-78h] BYREF
  int v26; // [rsp+B8h] [rbp-70h] BYREF
  LPVOID pv; // [rsp+C0h] [rbp-68h] BYREF
  int v28; // [rsp+C8h] [rbp-60h] BYREF
  int v29; // [rsp+CCh] [rbp-5Ch] BYREF
  int v30; // [rsp+D0h] [rbp-58h] BYREF
  __int64 v31; // [rsp+D8h] [rbp-50h] BYREF
  PROPVARIANT v32; // [rsp+E0h] [rbp-48h] BYREF
  GUID *v33; // [rsp+E8h] [rbp-40h] BYREF
  LPVOID v34; // [rsp+F0h] [rbp-38h] BYREF
  PROPVARIANT v35; // [rsp+F8h] [rbp-30h] BYREF
  PROPVARIANT v36; // [rsp+100h] [rbp-28h] BYREF
  PROPVARIANT v37; // [rsp+108h] [rbp-20h] BYREF
  const unsigned __int16 *v38; // [rsp+110h] [rbp-18h] BYREF
  __int64 v39; // [rsp+118h] [rbp-10h] BYREF
  PROPVARIANT pvar[2]; // [rsp+120h] [rbp-8h] BYREF
  __int64 v41; // [rsp+130h] [rbp+8h]
  PROPVARIANT v42[2]; // [rsp+138h] [rbp+10h] BYREF
  __int64 v43; // [rsp+148h] [rbp+20h]
  PROPVARIANT v44[2]; // [rsp+150h] [rbp+28h] BYREF
  __int64 v45; // [rsp+160h] [rbp+38h]
  PROPVARIANT v46[2]; // [rsp+168h] [rbp+40h] BYREF
  __int64 v47; // [rsp+178h] [rbp+50h]
  PROPVARIANT v48[2]; // [rsp+180h] [rbp+58h] BYREF
  __int64 v49; // [rsp+190h] [rbp+68h]
  PROPVARIANT v50[2]; // [rsp+198h] [rbp+70h] BYREF
  __int64 v51; // [rsp+1A8h] [rbp+80h]
  PROPVARIANT v52[2]; // [rsp+1B0h] [rbp+88h] BYREF
  __int64 v53; // [rsp+1C0h] [rbp+98h]
  PROPVARIANT v54[2]; // [rsp+1C8h] [rbp+A0h] BYREF
  __int64 v55; // [rsp+1D8h] [rbp+B0h]
  PROPVARIANT v56[2]; // [rsp+1E0h] [rbp+B8h] BYREF
  __int64 v57; // [rsp+1F0h] [rbp+C8h]
  struct IMMDevice *v58; // [rsp+230h] [rbp+108h] BYREF

  v58 = a2;
  v26 = 2;
  v31 = 0;
  if ( (int)wil::com_query_to_nothrow<IMMEndpoint,IMMDevice * &>(&v58, &v31) >= 0 )
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v31 + 24LL))(v31, &v26);
  pv = 0;
  GetId = a2->lpVtbl->GetId;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  ((void (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a2, &pv);
  *(_OWORD *)v56 = 0;
  v57 = 0;
  *(_OWORD *)v54 = 0;
  v55 = 0;
  *(_OWORD *)v52 = 0;
  v53 = 0;
  *(_OWORD *)v50 = 0;
  v51 = 0;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  v9 = 10;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  v25 = 0;
  lpVtbl = a2->lpVtbl;
  v25 = 0;
  if ( ((int (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))lpVtbl->OpenPropertyStore)(a2, 0, &v25) >= 0 )
  {
    (*(void (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
      v25,
      &DEVPKEY_Device_EnumeratorName,
      v56);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(v25, PKEY_Endpoint_Devnode, v54);
    (*(void (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
      v25,
      &DEVPKEY_Device_ContainerId,
      v52);
    (*(void (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
      v25,
      &PKEY_AudioEndpoint_JackSubType,
      v50);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
      v25,
      PKEY_Endpoint_IsBluetooth,
      v48);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(v25, PKEY_Endpoint_IsUSB, v46);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
      v25,
      PKEY_Endpoint_IsSideband,
      v44);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
      v25,
      PKEY_AudioEndpoint_PersistentId,
      v42);
    *(_OWORD *)pvar = 0;
    v41 = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v25 + 40LL))(
           v25,
           &PKEY_AudioEndpoint_FormFactor,
           pvar) >= 0
      && LOWORD(pvar[0]) == 19 )
    {
      v9 = (int)pvar[1];
    }
    PropVariantClear(pvar);
  }
  v11 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v11 > 3u && (unsigned __int8)tlgKeywordOn(v11, 0x400000000000LL, v11) )
  {
    v14 = 0;
    if ( LOWORD(v42[0]) == 31 )
      v14 = v42[1];
    v32 = v14;
    LOBYTE(v58) = v26;
    if ( LOWORD(v52[0]) != 72 || (v15 = (GUID *)v52[1]) == 0 )
      v15 = &GUID_00000000_0000_0000_0000_000000000000;
    v33 = v15;
    v16 = 1;
    if ( LOWORD(v44[0]) != 11 || (v17 = 1, !LOWORD(v44[1])) )
      v17 = 0;
    v22 = v17;
    if ( LOWORD(v46[0]) != 11 || (v18 = 1, !LOWORD(v46[1])) )
      v18 = 0;
    v23 = v18;
    if ( LOWORD(v48[0]) != 11 || !LOWORD(v48[1]) )
      v16 = 0;
    v24[0] = v16;
    v34 = pv;
    v19 = 0;
    if ( LOWORD(v50[0]) == 31 )
      v19 = v50[1];
    v35 = v19;
    v28 = v9;
    v20 = 0;
    if ( LOWORD(v54[0]) == 31 )
      v20 = v54[1];
    v36 = v20;
    v21 = 0;
    if ( LOWORD(v56[0]) == 31 )
      v21 = v56[1];
    v37 = v21;
    v29 = a4;
    v30 = a3;
    v38 = a1;
    v39 = 16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
      v12,
      (unsigned int)byte_180077D35,
      v12,
      v13,
      (__int64)&v39,
      (__int64)&v38,
      (__int64)&v30,
      (__int64)&v29,
      (__int64)&v37,
      (__int64)&v36,
      (__int64)&v28,
      (__int64)&v35,
      (__int64)&v34,
      (__int64)v24,
      (__int64)&v23,
      (__int64)&v22,
      (__int64)&v33,
      (__int64)&v58,
      (__int64)&v32);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  PropVariantClear(v42);
  PropVariantClear(v44);
  PropVariantClear(v46);
  PropVariantClear(v48);
  PropVariantClear(v50);
  PropVariantClear(v52);
  PropVariantClear(v54);
  PropVariantClear(v56);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v31);
}

```

## disassembly

```asm
0x18005a2ac  mov     rax, rsp
0x18005a2af  mov     [rax+8], rbx
0x18005a2b3  mov     [rax+18h], rsi
0x18005a2b7  mov     [rax+10h], rdx
0x18005a2bb  push    rbp
0x18005a2bc  push    rdi
0x18005a2bd  push    r12
0x18005a2bf  push    r14
0x18005a2c1  push    r15
0x18005a2c3  lea     rbp, [rax-0F8h]
0x18005a2ca  sub     rsp, 1F0h
0x18005a2d1  mov     esi, r9d
0x18005a2d4  mov     r14d, r8d
0x18005a2d7  mov     rdi, rdx
0x18005a2da  mov     r15, rcx
0x18005a2dd  mov     [rbp+0F0h+var_160], 2
0x18005a2e4  xor     r12d, r12d
0x18005a2e7  mov     [rbp+0F0h+var_140], r12
0x18005a2eb  lea     rdx, [rbp+0F0h+var_140]
0x18005a2ef  lea     rcx, [rbp+0F0h+arg_8]
0x18005a2f6  call    ??$com_query_to_nothrow@UIMMEndpoint@@AEAPEAUIMMDevice@@@wil@@YAJAEAPEAUIMMDevice@@PEAPEAUIMMEndpoint@@@Z; wil::com_query_to_nothrow<IMMEndpoint,IMMDevice * &>(IMMDevice * &,IMMEndpoint * *)
0x18005a2fb  test    eax, eax
0x18005a2fd  js      short loc_18005A313
0x18005a2ff  mov     rcx, [rbp+0F0h+var_140]
0x18005a303  mov     rax, [rcx]
0x18005a306  lea     rdx, [rbp+0F0h+var_160]
0x18005a30a  mov     rax, [rax+18h]
0x18005a30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a313  mov     [rbp+0F0h+pv], r12
0x18005a317  mov     rax, [rdi]
0x18005a31a  mov     rbx, [rax+28h]
0x18005a31e  xor     edx, edx
0x18005a320  lea     rcx, [rbp+0F0h+pv]
0x18005a324  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18005a329  lea     rdx, [rbp+0F0h+pv]
0x18005a32d  mov     rcx, rdi
0x18005a330  mov     rax, rbx
0x18005a333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a338  xorps   xmm0, xmm0
0x18005a33b  xor     eax, eax
0x18005a33d  movups  xmmword ptr [rbp+0F0h+var_38], xmm0
0x18005a344  mov     [rbp+0F0h+var_28], rax
0x18005a34b  movups  xmmword ptr [rbp+0F0h+var_50], xmm0
0x18005a352  mov     [rbp+0F0h+var_40], rax
0x18005a359  movups  xmmword ptr [rbp+0F0h+var_68], xmm0
0x18005a360  mov     [rbp+0F0h+var_58], rax
0x18005a367  movups  xmmword ptr [rbp+0F0h+var_80], xmm0
0x18005a36b  mov     [rbp+0F0h+var_70], rax
0x18005a372  movups  xmmword ptr [rbp+0F0h+var_98], xmm0
0x18005a376  mov     [rbp+0F0h+var_88], rax
0x18005a37a  movups  xmmword ptr [rbp+0F0h+var_B0], xmm0
0x18005a37e  mov     [rbp+0F0h+var_A0], rax
0x18005a382  movups  xmmword ptr [rbp+0F0h+var_C8], xmm0
0x18005a386  mov     [rbp+0F0h+var_B8], rax
0x18005a38a  lea     ebx, [rax+0Ah]
0x18005a38d  movups  xmmword ptr [rbp+0F0h+var_E0], xmm0
0x18005a391  mov     [rbp+0F0h+var_D0], rax
0x18005a395  mov     [rbp+0F0h+var_168], r12
0x18005a399  mov     rax, [rdi]
0x18005a39c  mov     [rbp+0F0h+var_168], r12
0x18005a3a0  lea     r8, [rbp+0F0h+var_168]
0x18005a3a4  xor     edx, edx
0x18005a3a6  mov     rcx, rdi
0x18005a3a9  mov     rax, [rax+20h]
0x18005a3ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a3b2  test    eax, eax
0x18005a3b4  js      loc_18005A4DA
0x18005a3ba  mov     rcx, [rbp+0F0h+var_168]
0x18005a3be  mov     rax, [rcx]
0x18005a3c1  lea     r8, [rbp+0F0h+var_38]
0x18005a3c8  lea     rdx, DEVPKEY_Device_EnumeratorName
0x18005a3cf  mov     rax, [rax+28h]
0x18005a3d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a3d8  mov     rcx, [rbp+0F0h+var_168]
0x18005a3dc  mov     rax, [rcx]
0x18005a3df  lea     r8, [rbp+0F0h+var_50]
0x18005a3e6  lea     rdx, PKEY_Endpoint_Devnode
0x18005a3ed  mov     rax, [rax+28h]
0x18005a3f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a3f6  mov     rcx, [rbp+0F0h+var_168]
0x18005a3fa  mov     rax, [rcx]
0x18005a3fd  lea     r8, [rbp+0F0h+var_68]
0x18005a404  lea     rdx, DEVPKEY_Device_ContainerId
0x18005a40b  mov     rax, [rax+28h]
0x18005a40f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a414  mov     rcx, [rbp+0F0h+var_168]
0x18005a418  mov     rax, [rcx]
0x18005a41b  lea     r8, [rbp+0F0h+var_80]
0x18005a41f  lea     rdx, PKEY_AudioEndpoint_JackSubType
0x18005a426  mov     rax, [rax+28h]
0x18005a42a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a42f  mov     rcx, [rbp+0F0h+var_168]
0x18005a433  mov     rax, [rcx]
0x18005a436  lea     r8, [rbp+0F0h+var_98]
0x18005a43a  lea     rdx, PKEY_Endpoint_IsBluetooth
0x18005a441  mov     rax, [rax+28h]
0x18005a445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a44a  mov     rcx, [rbp+0F0h+var_168]
0x18005a44e  mov     rax, [rcx]
0x18005a451  lea     r8, [rbp+0F0h+var_B0]
0x18005a455  lea     rdx, PKEY_Endpoint_IsUSB
0x18005a45c  mov     rax, [rax+28h]
0x18005a460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a465  mov     rcx, [rbp+0F0h+var_168]
0x18005a469  mov     rax, [rcx]
0x18005a46c  lea     r8, [rbp+0F0h+var_C8]
0x18005a470  lea     rdx, PKEY_Endpoint_IsSideband
0x18005a477  mov     rax, [rax+28h]
0x18005a47b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a480  mov     rcx, [rbp+0F0h+var_168]
0x18005a484  mov     rax, [rcx]
0x18005a487  lea     r8, [rbp+0F0h+var_E0]
0x18005a48b  lea     rdx, PKEY_AudioEndpoint_PersistentId
0x18005a492  mov     rax, [rax+28h]
0x18005a496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a49b  xorps   xmm0, xmm0
0x18005a49e  xor     eax, eax
0x18005a4a0  movups  xmmword ptr [rbp+0F0h+pvar], xmm0
0x18005a4a4  mov     [rbp+0F0h+var_E8], rax
0x18005a4a8  mov     rcx, [rbp+0F0h+var_168]
0x18005a4ac  mov     rax, [rcx]
0x18005a4af  lea     r8, [rbp+0F0h+pvar]
0x18005a4b3  lea     rdx, PKEY_AudioEndpoint_FormFactor
0x18005a4ba  mov     rax, [rax+28h]
0x18005a4be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a4c3  test    eax, eax
0x18005a4c5  js      short loc_18005A4D0
0x18005a4c7  cmp     word ptr [rbp+0F0h+pvar], 13h
0x18005a4cc  cmovz   ebx, dword ptr [rbp+0F0h+pvar+8]
0x18005a4d0  lea     rcx, [rbp+0F0h+pvar]; pvar
0x18005a4d4  call    cs:__imp_PropVariantClear
0x18005a4da  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005a4df  mov     r8, rax
0x18005a4e2  mov     ecx, [rax]
0x18005a4e4  cmp     ecx, 3
0x18005a4e7  jbe     loc_18005A684
0x18005a4ed  mov     rdx, 400000000000h
0x18005a4f7  mov     rcx, rax
0x18005a4fa  call    _tlgKeywordOn
0x18005a4ff  test    al, al
0x18005a501  jz      loc_18005A684
0x18005a507  mov     rcx, r12
0x18005a50a  mov     dx, 1Fh
0x18005a50e  cmp     word ptr [rbp+0F0h+var_E0], dx
0x18005a512  cmovz   rcx, [rbp+0F0h+var_E0+8]
0x18005a517  mov     [rbp+0F0h+var_138], rcx
0x18005a51b  mov     al, byte ptr [rbp+0F0h+var_160]
0x18005a51e  mov     byte ptr [rbp+0F0h+arg_8], al
0x18005a524  cmp     word ptr [rbp+0F0h+var_68], 48h ; 'H'
0x18005a52c  jnz     short loc_18005A53A
0x18005a52e  mov     rax, [rbp+0F0h+var_68+8]
0x18005a535  test    rax, rax
0x18005a538  jnz     short loc_18005A541
0x18005a53a  lea     rax, _GUID_00000000_0000_0000_0000_000000000000
0x18005a541  mov     [rbp+0F0h+var_130], rax
0x18005a545  mov     al, 1
0x18005a547  cmp     word ptr [rbp+0F0h+var_C8], 0Bh
0x18005a54c  jnz     short loc_18005A557
0x18005a54e  cmp     word ptr [rbp+0F0h+var_C8+8], r12w
0x18005a553  mov     cl, al
0x18005a555  jnz     short loc_18005A55A
0x18005a557  mov     cl, r12b
0x18005a55a  mov     [rbp+0F0h+var_170], cl
0x18005a55d  cmp     word ptr [rbp+0F0h+var_B0], 0Bh
0x18005a562  jnz     short loc_18005A56D
0x18005a564  cmp     word ptr [rbp+0F0h+var_B0+8], r12w
0x18005a569  mov     cl, al
0x18005a56b  jnz     short loc_18005A570
0x18005a56d  mov     cl, r12b
0x18005a570  mov     [rbp+0F0h+var_16F], cl
0x18005a573  cmp     word ptr [rbp+0F0h+var_98], 0Bh
0x18005a578  jnz     short loc_18005A581
0x18005a57a  cmp     word ptr [rbp+0F0h+var_98+8], r12w
0x18005a57f  jnz     short loc_18005A584
0x18005a581  mov     al, r12b
0x18005a584  mov     [rbp+0F0h+var_16E], al
0x18005a587  mov     rax, [rbp+0F0h+pv]
0x18005a58b  mov     [rbp+0F0h+var_128], rax
0x18005a58f  mov     rax, r12
0x18005a592  cmp     word ptr [rbp+0F0h+var_80], dx
0x18005a596  cmovz   rax, [rbp+0F0h+var_80+8]
0x18005a59b  mov     [rbp+0F0h+var_120], rax
0x18005a59f  mov     [rbp+0F0h+var_150], ebx
0x18005a5a2  mov     rax, r12
0x18005a5a5  cmp     word ptr [rbp+0F0h+var_50], dx
0x18005a5ac  cmovz   rax, [rbp+0F0h+var_50+8]
0x18005a5b4  mov     [rbp+0F0h+var_118], rax
0x18005a5b8  mov     rax, r12
0x18005a5bb  cmp     word ptr [rbp+0F0h+var_38], dx
0x18005a5c2  cmovz   rax, [rbp+0F0h+var_38+8]
0x18005a5ca  mov     [rbp+0F0h+var_110], rax
0x18005a5ce  mov     [rbp+0F0h+var_14C], esi
0x18005a5d1  mov     [rbp+0F0h+var_148], r14d
0x18005a5d5  mov     [rbp+0F0h+var_108], r15
0x18005a5d9  mov     [rbp+0F0h+var_100], 1000800h
0x18005a5e1  lea     rax, [rbp+0F0h+var_138]
0x18005a5e5  mov     [rsp+210h+var_180], rax
0x18005a5ed  lea     rax, [rbp+0F0h+arg_8]
0x18005a5f4  mov     [rsp+210h+var_188], rax
0x18005a5fc  lea     rax, [rbp+0F0h+var_130]
0x18005a600  mov     [rsp+210h+var_190], rax
0x18005a608  lea     rax, [rbp+0F0h+var_170]
0x18005a60c  mov     [rsp+210h+var_198], rax
0x18005a611  lea     rax, [rbp+0F0h+var_16F]
0x18005a615  mov     [rsp+210h+var_1A0], rax
0x18005a61a  lea     rax, [rbp+0F0h+var_16E]
0x18005a61e  mov     [rsp+210h+var_1A8], rax
0x18005a623  lea     rax, [rbp+0F0h+var_128]
0x18005a627  mov     [rsp+210h+var_1B0], rax
0x18005a62c  lea     rax, [rbp+0F0h+var_120]
0x18005a630  mov     [rsp+210h+var_1B8], rax
0x18005a635  lea     rax, [rbp+0F0h+var_150]
0x18005a639  mov     [rsp+210h+var_1C0], rax
0x18005a63e  lea     rax, [rbp+0F0h+var_118]
0x18005a642  mov     [rsp+210h+var_1C8], rax
0x18005a647  lea     rax, [rbp+0F0h+var_110]
0x18005a64b  mov     [rsp+210h+var_1D0], rax
0x18005a650  lea     rax, [rbp+0F0h+var_14C]
0x18005a654  mov     [rsp+210h+var_1D8], rax
0x18005a659  lea     rax, [rbp+0F0h+var_148]
0x18005a65d  mov     [rsp+210h+var_1E0], rax
0x18005a662  lea     rax, [rbp+0F0h+var_108]
0x18005a666  mov     [rsp+210h+var_1E8], rax
0x18005a66b  lea     rax, [rbp+0F0h+var_100]
0x18005a66f  mov     [rsp+210h+var_1F0], rax
0x18005a674  lea     rdx, byte_180077D35
0x18005a67b  mov     rcx, r8
0x18005a67e  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U3@U2@U2@U3@U2@U2@U?$_tlgWrapperByVal@$00@@U4@U4@U?$_tlgWrapperByRef@$0BA@@@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@544544AEBU?$_tlgWrapperByVal@$00@@66AEBU?$_tlgWrapperByRef@$0BA@@@64@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18005a683  nop
0x18005a684  lea     rcx, [rbp+0F0h+var_168]
0x18005a688  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a68d  nop
0x18005a68e  lea     rcx, [rbp+0F0h+var_E0]; pvar
0x18005a692  call    cs:__imp_PropVariantClear
0x18005a698  nop
0x18005a699  lea     rcx, [rbp+0F0h+var_C8]; pvar
0x18005a69d  call    cs:__imp_PropVariantClear
0x18005a6a3  nop
0x18005a6a4  lea     rcx, [rbp+0F0h+var_B0]; pvar
0x18005a6a8  call    cs:__imp_PropVariantClear
0x18005a6ae  nop
0x18005a6af  lea     rcx, [rbp+0F0h+var_98]; pvar
0x18005a6b3  call    cs:__imp_PropVariantClear
0x18005a6b9  nop
0x18005a6ba  lea     rcx, [rbp+0F0h+var_80]; pvar
0x18005a6be  call    cs:__imp_PropVariantClear
0x18005a6c4  nop
0x18005a6c5  lea     rcx, [rbp+0F0h+var_68]; pvar
0x18005a6cc  call    cs:__imp_PropVariantClear
0x18005a6d2  nop
0x18005a6d3  lea     rcx, [rbp+0F0h+var_50]; pvar
0x18005a6da  call    cs:__imp_PropVariantClear
0x18005a6e0  nop
0x18005a6e1  lea     rcx, [rbp+0F0h+var_38]; pvar
0x18005a6e8  call    cs:__imp_PropVariantClear
0x18005a6ee  nop
0x18005a6ef  mov     rcx, [rbp+0F0h+pv]; pv
0x18005a6f3  test    rcx, rcx
0x18005a6f6  jz      short loc_18005A6FF
0x18005a6f8  call    cs:__imp_CoTaskMemFree
0x18005a6fe  nop
0x18005a6ff  lea     rcx, [rbp+0F0h+var_140]
0x18005a703  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a708  lea     r11, [rsp+210h+var_20]
0x18005a710  mov     rbx, [r11+30h]
0x18005a714  mov     rsi, [r11+40h]
0x18005a718  mov     rsp, r11
0x18005a71b  pop     r15
0x18005a71d  pop     r14
0x18005a71f  pop     r12
0x18005a721  pop     rdi
0x18005a722  pop     rbp
0x18005a723  retn
```
