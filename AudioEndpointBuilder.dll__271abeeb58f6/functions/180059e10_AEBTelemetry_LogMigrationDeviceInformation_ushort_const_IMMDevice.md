# AEBTelemetry::LogMigrationDeviceInformation(ushort const *,IMMDevice *)

- ea: `0x180059e10`
- end: `0x18005a2a4`
- name: `?LogMigrationDeviceInformation@AEBTelemetry@@SAXPEBGPEAUIMMDevice@@@Z`
- size: `1172`
- prototype: `void __fastcall(const unsigned __int16 *, struct IMMDevice *)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180039ef4`

## callees

- `0x180002924`
- `0x180006b0c`
- `0x18000fb60`
- `0x18001f374`
- `0x1800252a4`
- `0x180029c9c`
- `0x180059e10`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a05a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a217`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a222`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a22d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a238`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a243`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a251`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a25f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a26d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a05a`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a217`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a222`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a22d`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a238`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a243`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a251`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a25f`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x18005a26d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a27d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a27d`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
void __fastcall AEBTelemetry::LogMigrationDeviceInformation(const unsigned __int16 *a1, struct IMMDevice *a2)
{
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v5; // ebx
  HRESULT (__stdcall *OpenPropertyStore)(IMMDevice *, DWORD, IPropertyStore **); // rsi
  const struct _tlgProvider_t *v7; // rax
  int v8; // r8d
  int v9; // r9d
  PROPVARIANT v10; // rcx
  GUID *v11; // rax
  char v12; // al
  char v13; // cl
  char v14; // cl
  PROPVARIANT v15; // rax
  PROPVARIANT v16; // rax
  PROPVARIANT v17; // rax
  char v18[8]; // [rsp+90h] [rbp-80h] BYREF
  __int64 v19; // [rsp+98h] [rbp-78h] BYREF
  int v20; // [rsp+A0h] [rbp-70h] BYREF
  int v21; // [rsp+A4h] [rbp-6Ch] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-68h] BYREF
  int v23; // [rsp+B0h] [rbp-60h] BYREF
  int v24; // [rsp+B4h] [rbp-5Ch] BYREF
  __int64 v25; // [rsp+B8h] [rbp-58h] BYREF
  PROPVARIANT v26; // [rsp+C0h] [rbp-50h] BYREF
  GUID *v27; // [rsp+C8h] [rbp-48h] BYREF
  LPVOID v28; // [rsp+D0h] [rbp-40h] BYREF
  PROPVARIANT v29; // [rsp+D8h] [rbp-38h] BYREF
  PROPVARIANT v30; // [rsp+E0h] [rbp-30h] BYREF
  PROPVARIANT v31; // [rsp+E8h] [rbp-28h] BYREF
  const unsigned __int16 *v32; // [rsp+F0h] [rbp-20h] BYREF
  __int64 v33; // [rsp+F8h] [rbp-18h] BYREF
  PROPVARIANT pvar[2]; // [rsp+100h] [rbp-10h] BYREF
  __int64 v35; // [rsp+110h] [rbp+0h]
  PROPVARIANT v36[2]; // [rsp+118h] [rbp+8h] BYREF
  __int64 v37; // [rsp+128h] [rbp+18h]
  PROPVARIANT v38[2]; // [rsp+130h] [rbp+20h] BYREF
  __int64 v39; // [rsp+140h] [rbp+30h]
  PROPVARIANT v40[2]; // [rsp+148h] [rbp+38h] BYREF
  __int64 v41; // [rsp+158h] [rbp+48h]
  PROPVARIANT v42[2]; // [rsp+160h] [rbp+50h] BYREF
  __int64 v43; // [rsp+170h] [rbp+60h]
  PROPVARIANT v44[2]; // [rsp+178h] [rbp+68h] BYREF
  __int64 v45; // [rsp+188h] [rbp+78h]
  PROPVARIANT v46[2]; // [rsp+190h] [rbp+80h] BYREF
  __int64 v47; // [rsp+1A0h] [rbp+90h]
  PROPVARIANT v48[2]; // [rsp+1A8h] [rbp+98h] BYREF
  __int64 v49; // [rsp+1B8h] [rbp+A8h]
  PROPVARIANT v50[2]; // [rsp+1C0h] [rbp+B0h] BYREF
  __int64 v51; // [rsp+1D0h] [rbp+C0h]
  struct IMMDevice *v52; // [rsp+218h] [rbp+108h] BYREF
  char v53; // [rsp+220h] [rbp+110h] BYREF
  char v54; // [rsp+228h] [rbp+118h] BYREF

  v52 = a2;
  v20 = 2;
  v25 = 0;
  if ( (int)wil::com_query_to_nothrow<IMMEndpoint,IMMDevice * &>(&v52, &v25) >= 0 )
    (*(void (__fastcall **)(__int64, int *))(*(_QWORD *)v25 + 24LL))(v25, &v20);
  pv = 0;
  GetId = a2->lpVtbl->GetId;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  ((void (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a2, &pv);
  *(_OWORD *)v50 = 0;
  v51 = 0;
  *(_OWORD *)v48 = 0;
  v49 = 0;
  *(_OWORD *)v46 = 0;
  v47 = 0;
  *(_OWORD *)v44 = 0;
  v45 = 0;
  *(_OWORD *)v42 = 0;
  v43 = 0;
  *(_OWORD *)v40 = 0;
  v41 = 0;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  v5 = 10;
  *(_OWORD *)v36 = 0;
  v37 = 0;
  v19 = 0;
  v21 = 0;
  ((void (__fastcall *)(struct IMMDevice *, int *))a2->lpVtbl->GetState)(a2, &v21);
  OpenPropertyStore = a2->lpVtbl->OpenPropertyStore;
  v19 = 0;
  if ( ((int (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))OpenPropertyStore)(a2, 0, &v19) >= 0 )
  {
    (*(void (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v19 + 40LL))(
      v19,
      &DEVPKEY_Device_EnumeratorName,
      v50);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v19 + 40LL))(v19, PKEY_Endpoint_Devnode, v48);
    (*(void (__fastcall **)(__int64, const DEVPROPKEY *, PROPVARIANT *))(*(_QWORD *)v19 + 40LL))(
      v19,
      &DEVPKEY_Device_ContainerId,
      v46);
    (*(void (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v19 + 40LL))(
      v19,
      &PKEY_AudioEndpoint_JackSubType,
      v44);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v19 + 40LL))(
      v19,
      PKEY_Endpoint_IsBluetooth,
      v42);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v19 + 40LL))(v19, PKEY_Endpoint_IsUSB, v40);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v19 + 40LL))(
      v19,
      PKEY_Endpoint_IsSideband,
      v38);
    (*(void (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v19 + 40LL))(
      v19,
      PKEY_AudioEndpoint_PersistentId,
      v36);
    *(_OWORD *)pvar = 0;
    v35 = 0;
    if ( (*(int (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v19 + 40LL))(
           v19,
           &PKEY_AudioEndpoint_FormFactor,
           pvar) >= 0
      && LOWORD(pvar[0]) == 19 )
    {
      v5 = (int)pvar[1];
    }
    PropVariantClear(pvar);
  }
  v7 = AudioEndpointBuilderTelemetryProvider::Provider();
  if ( *(_DWORD *)v7 > 4u && (unsigned __int8)tlgKeywordOn(v7, 0x400000000000LL, v7) )
  {
    v10 = 0;
    if ( LOWORD(v36[0]) == 31 )
      v10 = v36[1];
    v26 = v10;
    LOBYTE(v52) = v20;
    if ( LOWORD(v46[0]) != 72 || (v11 = (GUID *)v46[1]) == 0 )
      v11 = &GUID_00000000_0000_0000_0000_000000000000;
    v27 = v11;
    v12 = 1;
    if ( LOWORD(v38[0]) != 11 || (v13 = 1, !LOWORD(v38[1])) )
      v13 = 0;
    v53 = v13;
    if ( LOWORD(v40[0]) != 11 || (v14 = 1, !LOWORD(v40[1])) )
      v14 = 0;
    v54 = v14;
    if ( LOWORD(v42[0]) != 11 || !LOWORD(v42[1]) )
      v12 = 0;
    v18[0] = v12;
    v28 = pv;
    v15 = 0;
    if ( LOWORD(v44[0]) == 31 )
      v15 = v44[1];
    v29 = v15;
    v23 = v5;
    v16 = 0;
    if ( LOWORD(v48[0]) == 31 )
      v16 = v48[1];
    v30 = v16;
    v17 = 0;
    if ( LOWORD(v50[0]) == 31 )
      v17 = v50[1];
    v31 = v17;
    v24 = v21;
    v32 = a1;
    v33 = 16779264;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<unsigned short>>(
      v8,
      (unsigned int)&dword_180077C4C,
      v8,
      v9,
      (__int64)&v33,
      (__int64)&v32,
      (__int64)&v24,
      (__int64)&v31,
      (__int64)&v30,
      (__int64)&v23,
      (__int64)&v29,
      (__int64)&v28,
      (__int64)v18,
      (__int64)&v54,
      (__int64)&v53,
      (__int64)&v27,
      (__int64)&v52,
      (__int64)&v26);
  }
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v19);
  PropVariantClear(v36);
  PropVariantClear(v38);
  PropVariantClear(v40);
  PropVariantClear(v42);
  PropVariantClear(v44);
  PropVariantClear(v46);
  PropVariantClear(v48);
  PropVariantClear(v50);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
}

```

## disassembly

```asm
0x180059e10  mov     [rsp-8+arg_0], rbx
0x180059e15  mov     [rsp-8+arg_8], rdx
0x180059e1a  push    rbp
0x180059e1b  push    rsi
0x180059e1c  push    rdi
0x180059e1d  push    r14
0x180059e1f  push    r15
0x180059e21  lea     rbp, [rsp-0D0h]
0x180059e29  sub     rsp, 1E0h
0x180059e30  mov     rdi, rdx
0x180059e33  mov     r14, rcx
0x180059e36  mov     [rbp+0F0h+var_160], 2
0x180059e3d  xor     r15d, r15d
0x180059e40  mov     [rbp+0F0h+var_148], r15
0x180059e44  lea     rdx, [rbp+0F0h+var_148]
0x180059e48  lea     rcx, [rbp+0F0h+arg_8]
0x180059e4f  call    ??$com_query_to_nothrow@UIMMEndpoint@@AEAPEAUIMMDevice@@@wil@@YAJAEAPEAUIMMDevice@@PEAPEAUIMMEndpoint@@@Z; wil::com_query_to_nothrow<IMMEndpoint,IMMDevice * &>(IMMDevice * &,IMMEndpoint * *)
0x180059e54  test    eax, eax
0x180059e56  js      short loc_180059E6C
0x180059e58  mov     rcx, [rbp+0F0h+var_148]
0x180059e5c  mov     rax, [rcx]
0x180059e5f  lea     rdx, [rbp+0F0h+var_160]
0x180059e63  mov     rax, [rax+18h]
0x180059e67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e6c  mov     [rbp+0F0h+pv], r15
0x180059e70  mov     rax, [rdi]
0x180059e73  mov     rbx, [rax+28h]
0x180059e77  xor     edx, edx
0x180059e79  lea     rcx, [rbp+0F0h+pv]
0x180059e7d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180059e82  lea     rdx, [rbp+0F0h+pv]
0x180059e86  mov     rcx, rdi
0x180059e89  mov     rax, rbx
0x180059e8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059e91  xorps   xmm0, xmm0
0x180059e94  xor     eax, eax
0x180059e96  movups  xmmword ptr [rbp+0F0h+var_40], xmm0
0x180059e9d  mov     [rbp+0F0h+var_30], rax
0x180059ea4  movups  xmmword ptr [rbp+0F0h+var_58], xmm0
0x180059eab  mov     [rbp+0F0h+var_48], rax
0x180059eb2  movups  xmmword ptr [rbp+0F0h+var_70], xmm0
0x180059eb9  mov     [rbp+0F0h+var_60], rax
0x180059ec0  movups  xmmword ptr [rbp+0F0h+var_88], xmm0
0x180059ec4  mov     [rbp+0F0h+var_78], rax
0x180059ec8  movups  xmmword ptr [rbp+0F0h+var_A0], xmm0
0x180059ecc  mov     [rbp+0F0h+var_90], rax
0x180059ed0  movups  xmmword ptr [rbp+0F0h+var_B8], xmm0
0x180059ed4  mov     [rbp+0F0h+var_A8], rax
0x180059ed8  movups  xmmword ptr [rbp+0F0h+var_D0], xmm0
0x180059edc  mov     [rbp+0F0h+var_C0], rax
0x180059ee0  lea     ebx, [rax+0Ah]
0x180059ee3  movups  xmmword ptr [rbp+0F0h+var_E8], xmm0
0x180059ee7  mov     [rbp+0F0h+var_D8], rax
0x180059eeb  mov     [rbp+0F0h+var_168], r15
0x180059eef  mov     [rbp+0F0h+var_15C], r15d
0x180059ef3  mov     rax, [rdi]
0x180059ef6  lea     rdx, [rbp+0F0h+var_15C]
0x180059efa  mov     rcx, rdi
0x180059efd  mov     rax, [rax+30h]
0x180059f01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f06  mov     rax, [rdi]
0x180059f09  mov     rsi, [rax+20h]
0x180059f0d  mov     rcx, [rbp+0F0h+var_168]
0x180059f11  mov     [rbp+0F0h+var_168], r15
0x180059f15  test    rcx, rcx
0x180059f18  jz      short loc_180059F27
0x180059f1a  mov     rdx, [rcx]
0x180059f1d  mov     rax, [rdx+10h]
0x180059f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f26  nop
0x180059f27  lea     r8, [rbp+0F0h+var_168]
0x180059f2b  xor     edx, edx
0x180059f2d  mov     rcx, rdi
0x180059f30  mov     rax, rsi
0x180059f33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f38  test    eax, eax
0x180059f3a  js      loc_18005A060
0x180059f40  mov     rcx, [rbp+0F0h+var_168]
0x180059f44  mov     rax, [rcx]
0x180059f47  lea     r8, [rbp+0F0h+var_40]
0x180059f4e  lea     rdx, DEVPKEY_Device_EnumeratorName
0x180059f55  mov     rax, [rax+28h]
0x180059f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f5e  mov     rcx, [rbp+0F0h+var_168]
0x180059f62  mov     rax, [rcx]
0x180059f65  lea     r8, [rbp+0F0h+var_58]
0x180059f6c  lea     rdx, PKEY_Endpoint_Devnode
0x180059f73  mov     rax, [rax+28h]
0x180059f77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f7c  mov     rcx, [rbp+0F0h+var_168]
0x180059f80  mov     rax, [rcx]
0x180059f83  lea     r8, [rbp+0F0h+var_70]
0x180059f8a  lea     rdx, DEVPKEY_Device_ContainerId
0x180059f91  mov     rax, [rax+28h]
0x180059f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059f9a  mov     rcx, [rbp+0F0h+var_168]
0x180059f9e  mov     rax, [rcx]
0x180059fa1  lea     r8, [rbp+0F0h+var_88]
0x180059fa5  lea     rdx, PKEY_AudioEndpoint_JackSubType
0x180059fac  mov     rax, [rax+28h]
0x180059fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fb5  mov     rcx, [rbp+0F0h+var_168]
0x180059fb9  mov     rax, [rcx]
0x180059fbc  lea     r8, [rbp+0F0h+var_A0]
0x180059fc0  lea     rdx, PKEY_Endpoint_IsBluetooth
0x180059fc7  mov     rax, [rax+28h]
0x180059fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059fd0  mov     rcx, [rbp+0F0h+var_168]
0x180059fd4  mov     rax, [rcx]
0x180059fd7  lea     r8, [rbp+0F0h+var_B8]
0x180059fdb  lea     rdx, PKEY_Endpoint_IsUSB
0x180059fe2  mov     rax, [rax+28h]
0x180059fe6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180059feb  mov     rcx, [rbp+0F0h+var_168]
0x180059fef  mov     rax, [rcx]
0x180059ff2  lea     r8, [rbp+0F0h+var_D0]
0x180059ff6  lea     rdx, PKEY_Endpoint_IsSideband
0x180059ffd  mov     rax, [rax+28h]
0x18005a001  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a006  mov     rcx, [rbp+0F0h+var_168]
0x18005a00a  mov     rax, [rcx]
0x18005a00d  lea     r8, [rbp+0F0h+var_E8]
0x18005a011  lea     rdx, PKEY_AudioEndpoint_PersistentId
0x18005a018  mov     rax, [rax+28h]
0x18005a01c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a021  xorps   xmm0, xmm0
0x18005a024  xor     eax, eax
0x18005a026  movups  xmmword ptr [rbp+0F0h+pvar], xmm0
0x18005a02a  mov     [rbp+0F0h+var_F0], rax
0x18005a02e  mov     rcx, [rbp+0F0h+var_168]
0x18005a032  mov     rax, [rcx]
0x18005a035  lea     r8, [rbp+0F0h+pvar]
0x18005a039  lea     rdx, PKEY_AudioEndpoint_FormFactor
0x18005a040  mov     rax, [rax+28h]
0x18005a044  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a049  test    eax, eax
0x18005a04b  js      short loc_18005A056
0x18005a04d  cmp     word ptr [rbp+0F0h+pvar], 13h
0x18005a052  cmovz   ebx, dword ptr [rbp+0F0h+pvar+8]
0x18005a056  lea     rcx, [rbp+0F0h+pvar]; pvar
0x18005a05a  call    cs:__imp_PropVariantClear
0x18005a060  call    ?Provider@AudioEndpointBuilderTelemetryProvider@@SAPEBU_tlgProvider_t@@XZ; AudioEndpointBuilderTelemetryProvider::Provider(void)
0x18005a065  mov     r8, rax
0x18005a068  mov     ecx, [rax]
0x18005a06a  cmp     ecx, 4
0x18005a06d  jbe     loc_18005A209
0x18005a073  mov     rdx, 400000000000h
0x18005a07d  mov     rcx, rax
0x18005a080  call    _tlgKeywordOn
0x18005a085  test    al, al
0x18005a087  jz      loc_18005A209
0x18005a08d  mov     rcx, r15
0x18005a090  mov     dx, 1Fh
0x18005a094  cmp     word ptr [rbp+0F0h+var_E8], dx
0x18005a098  cmovz   rcx, [rbp+0F0h+var_E8+8]
0x18005a09d  mov     [rbp+0F0h+var_140], rcx
0x18005a0a1  mov     al, byte ptr [rbp+0F0h+var_160]
0x18005a0a4  mov     byte ptr [rbp+0F0h+arg_8], al
0x18005a0aa  cmp     word ptr [rbp+0F0h+var_70], 48h ; 'H'
0x18005a0b2  jnz     short loc_18005A0C0
0x18005a0b4  mov     rax, [rbp+0F0h+var_70+8]
0x18005a0bb  test    rax, rax
0x18005a0be  jnz     short loc_18005A0C7
0x18005a0c0  lea     rax, _GUID_00000000_0000_0000_0000_000000000000
0x18005a0c7  mov     [rbp+0F0h+var_138], rax
0x18005a0cb  mov     al, 1
0x18005a0cd  cmp     word ptr [rbp+0F0h+var_D0], 0Bh
0x18005a0d2  jnz     short loc_18005A0DD
0x18005a0d4  cmp     word ptr [rbp+0F0h+var_D0+8], r15w
0x18005a0d9  mov     cl, al
0x18005a0db  jnz     short loc_18005A0E0
0x18005a0dd  mov     cl, r15b
0x18005a0e0  mov     [rbp+0F0h+arg_10], cl
0x18005a0e6  cmp     word ptr [rbp+0F0h+var_B8], 0Bh
0x18005a0eb  jnz     short loc_18005A0F6
0x18005a0ed  cmp     word ptr [rbp+0F0h+var_B8+8], r15w
0x18005a0f2  mov     cl, al
0x18005a0f4  jnz     short loc_18005A0F9
0x18005a0f6  mov     cl, r15b
0x18005a0f9  mov     [rbp+0F0h+arg_18], cl
0x18005a0ff  cmp     word ptr [rbp+0F0h+var_A0], 0Bh
0x18005a104  jnz     short loc_18005A10D
0x18005a106  cmp     word ptr [rbp+0F0h+var_A0+8], r15w
0x18005a10b  jnz     short loc_18005A110
0x18005a10d  mov     al, r15b
0x18005a110  mov     [rbp+0F0h+var_170], al
0x18005a113  mov     rax, [rbp+0F0h+pv]
0x18005a117  mov     [rbp+0F0h+var_130], rax
0x18005a11b  mov     rax, r15
0x18005a11e  cmp     word ptr [rbp+0F0h+var_88], dx
0x18005a122  cmovz   rax, [rbp+0F0h+var_88+8]
0x18005a127  mov     [rbp+0F0h+var_128], rax
0x18005a12b  mov     [rbp+0F0h+var_150], ebx
0x18005a12e  mov     rax, r15
0x18005a131  cmp     word ptr [rbp+0F0h+var_58], dx
0x18005a138  cmovz   rax, [rbp+0F0h+var_58+8]
0x18005a140  mov     [rbp+0F0h+var_120], rax
0x18005a144  mov     rax, r15
0x18005a147  cmp     word ptr [rbp+0F0h+var_40], dx
0x18005a14e  cmovz   rax, [rbp+0F0h+var_40+8]
0x18005a156  mov     [rbp+0F0h+var_118], rax
0x18005a15a  mov     eax, [rbp+0F0h+var_15C]
0x18005a15d  mov     [rbp+0F0h+var_14C], eax
0x18005a160  mov     [rbp+0F0h+var_110], r14
0x18005a164  mov     [rbp+0F0h+var_108], 1000800h
0x18005a16c  lea     rax, [rbp+0F0h+var_140]
0x18005a170  mov     [rsp+200h+var_178], rax
0x18005a178  lea     rax, [rbp+0F0h+arg_8]
0x18005a17f  mov     [rsp+200h+var_180], rax
0x18005a187  lea     rax, [rbp+0F0h+var_138]
0x18005a18b  mov     [rsp+200h+var_188], rax
0x18005a190  lea     rax, [rbp+0F0h+arg_10]
0x18005a197  mov     [rsp+200h+var_190], rax
0x18005a19c  lea     rax, [rbp+0F0h+arg_18]
0x18005a1a3  mov     [rsp+200h+var_198], rax
0x18005a1a8  lea     rax, [rbp+0F0h+var_170]
0x18005a1ac  mov     [rsp+200h+var_1A0], rax
0x18005a1b1  lea     rax, [rbp+0F0h+var_130]
0x18005a1b5  mov     [rsp+200h+var_1A8], rax
0x18005a1ba  lea     rax, [rbp+0F0h+var_128]
0x18005a1be  mov     [rsp+200h+var_1B0], rax
0x18005a1c3  lea     rax, [rbp+0F0h+var_150]
0x18005a1c7  mov     [rsp+200h+var_1B8], rax
0x18005a1cc  lea     rax, [rbp+0F0h+var_120]
0x18005a1d0  mov     [rsp+200h+var_1C0], rax
0x18005a1d5  lea     rax, [rbp+0F0h+var_118]
0x18005a1d9  mov     [rsp+200h+var_1C8], rax
0x18005a1de  lea     rax, [rbp+0F0h+var_14C]
0x18005a1e2  mov     [rsp+200h+var_1D0], rax
0x18005a1e7  lea     rax, [rbp+0F0h+var_110]
0x18005a1eb  mov     [rsp+200h+var_1D8], rax
0x18005a1f0  lea     rax, [rbp+0F0h+var_108]
0x18005a1f4  mov     [rsp+200h+var_1E0], rax
0x18005a1f9  lea     rdx, dword_180077C4C
0x18005a200  mov     rcx, r8
0x18005a203  call    ??$Write@U?$_tlgWrapperByVal@$07@@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@U2@U2@U3@U2@U2@U?$_tlgWrapperByVal@$00@@U4@U4@U?$_tlgWrapperByRef@$0BA@@@U4@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$07@@AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@44544AEBU?$_tlgWrapperByVal@$00@@66AEBU?$_tlgWrapperByRef@$0BA@@@64@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByVal<1>,_tlgWrapperByRef<16>,_tlgWrapperByVal<1>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<8> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByVal<1> const &,_tlgWrapperByRef<16> const &,_tlgWrapperByVal<1> const &,_tlgWrapSz<ushort> const &)
0x18005a208  nop
0x18005a209  lea     rcx, [rbp+0F0h+var_168]
0x18005a20d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a212  nop
0x18005a213  lea     rcx, [rbp+0F0h+var_E8]; pvar
0x18005a217  call    cs:__imp_PropVariantClear
0x18005a21d  nop
0x18005a21e  lea     rcx, [rbp+0F0h+var_D0]; pvar
0x18005a222  call    cs:__imp_PropVariantClear
0x18005a228  nop
0x18005a229  lea     rcx, [rbp+0F0h+var_B8]; pvar
0x18005a22d  call    cs:__imp_PropVariantClear
0x18005a233  nop
0x18005a234  lea     rcx, [rbp+0F0h+var_A0]; pvar
0x18005a238  call    cs:__imp_PropVariantClear
0x18005a23e  nop
0x18005a23f  lea     rcx, [rbp+0F0h+var_88]; pvar
0x18005a243  call    cs:__imp_PropVariantClear
0x18005a249  nop
0x18005a24a  lea     rcx, [rbp+0F0h+var_70]; pvar
0x18005a251  call    cs:__imp_PropVariantClear
0x18005a257  nop
0x18005a258  lea     rcx, [rbp+0F0h+var_58]; pvar
0x18005a25f  call    cs:__imp_PropVariantClear
0x18005a265  nop
0x18005a266  lea     rcx, [rbp+0F0h+var_40]; pvar
0x18005a26d  call    cs:__imp_PropVariantClear
0x18005a273  nop
0x18005a274  mov     rcx, [rbp+0F0h+pv]; pv
0x18005a278  test    rcx, rcx
0x18005a27b  jz      short loc_18005A284
0x18005a27d  call    cs:__imp_CoTaskMemFree
0x18005a283  nop
0x18005a284  lea     rcx, [rbp+0F0h+var_148]
0x18005a288  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005a28d  mov     rbx, [rsp+200h+arg_0]
0x18005a295  add     rsp, 1E0h
0x18005a29c  pop     r15
0x18005a29e  pop     r14
0x18005a2a0  pop     rdi
0x18005a2a1  pop     rsi
0x18005a2a2  pop     rbp
0x18005a2a3  retn
```
