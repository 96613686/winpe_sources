# CAvEndpointBuilder::SetBluetoothProperties(IMMDevice *,ENDPOINT_DESCRIPTOR const *)

- ea: `0x180052cb8`
- end: `0x180052f93`
- name: `?SetBluetoothProperties@CAvEndpointBuilder@@AEAAJPEAUIMMDevice@@PEBUENDPOINT_DESCRIPTOR@@@Z`
- size: `731`
- prototype: `__int64 __fastcall(CAvEndpointBuilder *__hidden this, struct IMMDevice *, const struct ENDPOINT_DESCRIPTOR *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000c0d0`

## callees

- `0x180006b0c`
- `0x18000fb60`
- `0x180010da8`
- `0x180021030`
- `0x1800338e0`
- `0x180037090`
- `0x180049c50`
- `0x180052cb8`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052eb2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052f48`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052eb2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180052f48`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052e5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052f58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052e5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052f58`

## string_xrefs

- `0x180052d52`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180052da2`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180052ded`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180052e44`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180052e9d`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
__int64 __fastcall CAvEndpointBuilder::SetBluetoothProperties(
        CAvEndpointBuilder *this,
        struct IMMDevice *a2,
        const struct ENDPOINT_DESCRIPTOR *a3)
{
  struct IMMDeviceVtbl *lpVtbl; // rax
  int v5; // eax
  unsigned int v6; // ebx
  __int64 v7; // rdx
  struct IUnknownVtbl *v8; // rax
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, LPVOID *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r9
  struct IPropertyStore *v18; // [rsp+20h] [rbp-40h] BYREF
  __int128 v19; // [rsp+28h] [rbp-38h] BYREF
  __int64 v20; // [rsp+38h] [rbp-28h]
  PROPVARIANT pvar[2]; // [rsp+40h] [rbp-20h] BYREF
  __int64 v22; // [rsp+50h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  CAvEndpointBuilder *v24; // [rsp+90h] [rbp+30h] BYREF
  __int64 v25; // [rsp+98h] [rbp+38h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp+48h] BYREF

  v24 = this;
  v19 = 0;
  v20 = 0;
  lpVtbl = a2->lpVtbl;
  v18 = 0;
  v5 = ((__int64 (__fastcall *)(struct IMMDevice *, __int64, struct IPropertyStore **))lpVtbl->OpenPropertyStore)(
         a2,
         2,
         &v18);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 6972;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v5,
      (int)v18);
    goto LABEL_32;
  }
  v19 = 0;
  v20 = 0;
  LOWORD(v19) = 11;
  WORD4(v19) = -1;
  v5 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))v18->lpVtbl->SetValue)(
         v18,
         PKEY_Endpoint_IsBluetooth,
         &v19);
  v6 = v5;
  if ( v5 < 0 )
  {
    v7 = 6979;
    goto LABEL_5;
  }
  v24 = 0;
  v8 = g_DeviceEnumerator->lpVtbl;
  v24 = 0;
  v9 = ((__int64 (__fastcall *)(struct IUnknown *, _QWORD, CAvEndpointBuilder **))v8[1].Release)(
         g_DeviceEnumerator,
         *((_QWORD *)a3 + 5),
         &v24);
  v6 = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B47,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v9,
      (int)v18);
LABEL_8:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
    goto LABEL_32;
  }
  v25 = 0;
  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v25);
  v10 = wil::com_query_to_nothrow<IPnpDevnode,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(&v24, &v25);
  v6 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4A,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v10,
      (int)v18);
LABEL_11:
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
    goto LABEL_8;
  }
  pv = 0;
  v11 = v25;
  v12 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v25 + 32LL);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &pv,
    0);
  v13 = v12(v11, &pv);
  v6 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1B4D,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v13,
      (int)v18);
    goto LABEL_14;
  }
  *(_OWORD *)pvar = 0;
  v22 = 0;
  v14 = ((__int64 (__fastcall *)(struct IPropertyStore *, const PROPERTYKEY *, PROPVARIANT *))v18->lpVtbl->GetValue)(
          v18,
          &PKEY_Device_ContainerId,
          pvar);
  v6 = v14;
  if ( v14 < 0 )
  {
    v15 = 6992;
LABEL_18:
    v16 = (unsigned int)v14;
LABEL_19:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)v16,
      (int)v18);
    PropVariantClear(pvar);
LABEL_14:
    if ( pv )
      CoTaskMemFree(pv);
    goto LABEL_11;
  }
  if ( LOWORD(pvar[0]) != 72 )
  {
    v6 = -2147024809;
    v16 = 2147942487LL;
    v15 = 6993;
    goto LABEL_19;
  }
  v19 = 0;
  v20 = 0;
  if ( *((_DWORD *)a3 + 60) )
  {
    LOWORD(v19) = 11;
    WORD4(v19) = -1;
  }
  v14 = ((__int64 (__fastcall *)(struct IPropertyStore *, __int64 *, __int128 *))v18->lpVtbl->SetValue)(
          v18,
          PKEY_Endpoint_IsMuxedEndpoint,
          &v19);
  v6 = v14;
  if ( v14 < 0 )
  {
    v15 = 7001;
    goto LABEL_18;
  }
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl'::`2'::impl) )
  {
    v14 = DetectBluetoothBroadcastCapability(*((struct IConnector **)a3 + 1), v18);
    v6 = v14;
    if ( v14 < 0 )
    {
      v15 = 7005;
      goto LABEL_18;
    }
  }
  PropVariantClear(pvar);
  if ( pv )
    CoTaskMemFree(pv);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v25);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  v6 = 0;
LABEL_32:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v18);
  return v6;
}

```

## disassembly

```asm
0x180052cb8  mov     [rsp-28h+arg_10], rbx
0x180052cbd  mov     [rsp-28h+arg_0], rcx
0x180052cc2  push    rbp
0x180052cc3  push    rsi
0x180052cc4  push    rdi
0x180052cc5  push    r12
0x180052cc7  push    r15
0x180052cc9  mov     rbp, rsp
0x180052ccc  sub     rsp, 60h
0x180052cd0  mov     rsi, r8
0x180052cd3  mov     rcx, rdx
0x180052cd6  xorps   xmm0, xmm0
0x180052cd9  xor     eax, eax
0x180052cdb  movups  [rbp+var_38], xmm0
0x180052cdf  mov     [rbp+var_28], rax
0x180052ce3  mov     rax, [rdx]
0x180052ce6  mov     [rbp+var_40], 0
0x180052cee  lea     r8, [rbp+var_40]
0x180052cf2  mov     edx, 2
0x180052cf7  mov     rax, [rax+20h]
0x180052cfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d00  mov     ebx, eax
0x180052d02  test    eax, eax
0x180052d04  jns     short loc_180052D0D
0x180052d06  mov     edx, 1B3Ch
0x180052d0b  jmp     short loc_180052D52
0x180052d0d  xorps   xmm0, xmm0
0x180052d10  xor     eax, eax
0x180052d12  movups  [rbp+var_38], xmm0
0x180052d16  mov     [rbp+var_28], rax
0x180052d1a  lea     r15d, [rax+0Bh]
0x180052d1e  mov     word ptr [rbp+var_38], r15w
0x180052d23  or      r12d, 0FFFFFFFFh
0x180052d27  mov     word ptr [rbp+var_38+8], r12w
0x180052d2c  mov     rcx, [rbp+var_40]
0x180052d30  mov     rax, [rcx]
0x180052d33  lea     r8, [rbp+var_38]
0x180052d37  lea     rdx, PKEY_Endpoint_IsBluetooth
0x180052d3e  mov     rax, [rax+30h]
0x180052d42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d47  mov     ebx, eax
0x180052d49  test    eax, eax
0x180052d4b  jns     short loc_180052D6A
0x180052d4d  mov     edx, 1B43h; void *
0x180052d52  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180052d59  mov     r9d, eax; char *
0x180052d5c  mov     rcx, [rbp+28h]; this
0x180052d60  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052d65  jmp     loc_180052F74
0x180052d6a  mov     [rbp+arg_0], 0
0x180052d72  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180052d79  mov     rax, [rcx]
0x180052d7c  mov     [rbp+arg_0], 0
0x180052d84  lea     r8, [rbp+arg_0]
0x180052d88  mov     rdx, [rsi+28h]
0x180052d8c  mov     rax, [rax+28h]
0x180052d90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052d95  mov     ebx, eax
0x180052d97  test    eax, eax
0x180052d99  jns     short loc_180052DC2
0x180052d9b  mov     rcx, [rbp+28h]; this
0x180052d9f  mov     r9d, eax; char *
0x180052da2  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180052da9  mov     edx, 1B47h; void *
0x180052dae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052db3  nop
0x180052db4  lea     rcx, [rbp+arg_0]
0x180052db8  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180052dbd  jmp     loc_180052F74
0x180052dc2  mov     [rbp+arg_8], 0
0x180052dca  lea     rcx, [rbp+arg_8]
0x180052dce  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x180052dd3  lea     rdx, [rbp+arg_8]
0x180052dd7  lea     rcx, [rbp+arg_0]
0x180052ddb  call    ??$com_query_to_nothrow@UIPnpDevnode@@AEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@@wil@@YAJAEAV?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@0@PEAPEAUIPnpDevnode@@@Z; wil::com_query_to_nothrow<IPnpDevnode,wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &>(wil::com_ptr_t<IMMDevice,wil::err_returncode_policy> &,IPnpDevnode * *)
0x180052de0  mov     ebx, eax
0x180052de2  test    eax, eax
0x180052de4  jns     short loc_180052E0A
0x180052de6  mov     rcx, [rbp+28h]; this
0x180052dea  mov     r9d, eax; char *
0x180052ded  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180052df4  mov     edx, 1B4Ah; void *
0x180052df9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052dfe  nop
0x180052dff  lea     rcx, [rbp+arg_8]
0x180052e03  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180052e08  jmp     short loc_180052DB4
0x180052e0a  mov     [rbp+pv], 0
0x180052e12  mov     rdi, [rbp+arg_8]
0x180052e16  mov     rax, [rdi]
0x180052e19  mov     rbx, [rax+20h]
0x180052e1d  xor     edx, edx
0x180052e1f  lea     rcx, [rbp+pv]
0x180052e23  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180052e28  lea     rdx, [rbp+pv]
0x180052e2c  mov     rcx, rdi
0x180052e2f  mov     rax, rbx
0x180052e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e37  mov     ebx, eax
0x180052e39  test    eax, eax
0x180052e3b  jns     short loc_180052E67
0x180052e3d  mov     rcx, [rbp+28h]; this
0x180052e41  mov     r9d, eax; char *
0x180052e44  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180052e4b  mov     edx, 1B4Dh; void *
0x180052e50  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052e55  nop
0x180052e56  mov     rcx, [rbp+pv]; pv
0x180052e5a  test    rcx, rcx
0x180052e5d  jz      short loc_180052DFF
0x180052e5f  call    cs:__imp_CoTaskMemFree
0x180052e65  jmp     short loc_180052DFF
0x180052e67  xorps   xmm0, xmm0
0x180052e6a  xor     eax, eax
0x180052e6c  movups  xmmword ptr [rbp+pvar], xmm0
0x180052e70  mov     [rbp+var_10], rax
0x180052e74  mov     rcx, [rbp+var_40]
0x180052e78  mov     rax, [rcx]
0x180052e7b  lea     r8, [rbp+pvar]
0x180052e7f  lea     rdx, PKEY_Device_ContainerId
0x180052e86  mov     rax, [rax+28h]
0x180052e8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052e8f  mov     ebx, eax
0x180052e91  test    eax, eax
0x180052e93  jns     short loc_180052EBA
0x180052e95  mov     edx, 1B50h; void *
0x180052e9a  mov     r9d, eax; char *
0x180052e9d  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180052ea4  mov     rcx, [rbp+28h]; this
0x180052ea8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052ead  nop
0x180052eae  lea     rcx, [rbp+pvar]; pvar
0x180052eb2  call    cs:__imp_PropVariantClear
0x180052eb8  jmp     short loc_180052E56
0x180052eba  cmp     word ptr [rbp+pvar], 48h ; 'H'
0x180052ebf  jz      short loc_180052ED0
0x180052ec1  mov     ebx, 80070057h
0x180052ec6  mov     r9d, ebx
0x180052ec9  mov     edx, 1B51h
0x180052ece  jmp     short loc_180052E9D
0x180052ed0  xorps   xmm0, xmm0
0x180052ed3  xor     eax, eax
0x180052ed5  movups  [rbp+var_38], xmm0
0x180052ed9  mov     [rbp+var_28], rax
0x180052edd  cmp     [rsi+0F0h], eax
0x180052ee3  jz      short loc_180052EEF
0x180052ee5  mov     word ptr [rbp+var_38], r15w
0x180052eea  mov     word ptr [rbp+var_38+8], r12w
0x180052eef  mov     rcx, [rbp+var_40]
0x180052ef3  mov     rax, [rcx]
0x180052ef6  lea     r8, [rbp+var_38]
0x180052efa  lea     rdx, PKEY_Endpoint_IsMuxedEndpoint
0x180052f01  mov     rax, [rax+30h]
0x180052f05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052f0a  mov     ebx, eax
0x180052f0c  test    eax, eax
0x180052f0e  jns     short loc_180052F17
0x180052f10  mov     edx, 1B59h
0x180052f15  jmp     short loc_180052E9A
0x180052f17  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_56664216@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216> `wil::Feature<__WilFeatureTraits_Feature_56664216>::GetImpl(void)'::`2'::impl
0x180052f1e  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_56664216@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56664216>::__private_IsEnabled(void)
0x180052f23  test    al, al
0x180052f25  jz      short loc_180052F44
0x180052f27  mov     rdx, [rbp+var_40]; struct IPropertyStore *
0x180052f2b  mov     rcx, [rsi+8]; struct IConnector *
0x180052f2f  call    ?DetectBluetoothBroadcastCapability@@YAJPEAUIConnector@@PEAUIPropertyStore@@@Z; DetectBluetoothBroadcastCapability(IConnector *,IPropertyStore *)
0x180052f34  mov     ebx, eax
0x180052f36  test    eax, eax
0x180052f38  jns     short loc_180052F44
0x180052f3a  mov     edx, 1B5Dh
0x180052f3f  jmp     loc_180052E9A
0x180052f44  lea     rcx, [rbp+pvar]; pvar
0x180052f48  call    cs:__imp_PropVariantClear
0x180052f4e  nop
0x180052f4f  mov     rcx, [rbp+pv]; pv
0x180052f53  test    rcx, rcx
0x180052f56  jz      short loc_180052F5F
0x180052f58  call    cs:__imp_CoTaskMemFree
0x180052f5e  nop
0x180052f5f  lea     rcx, [rbp+arg_8]
0x180052f63  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180052f68  nop
0x180052f69  lea     rcx, [rbp+arg_0]
0x180052f6d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180052f72  xor     ebx, ebx
0x180052f74  lea     rcx, [rbp+var_40]
0x180052f78  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180052f7d  mov     eax, ebx
0x180052f7f  mov     rbx, [rsp+60h+arg_10]
0x180052f87  add     rsp, 60h
0x180052f8b  pop     r15
0x180052f8d  pop     r12
0x180052f8f  pop     rdi
0x180052f90  pop     rsi
0x180052f91  pop     rbp
0x180052f92  retn
```
