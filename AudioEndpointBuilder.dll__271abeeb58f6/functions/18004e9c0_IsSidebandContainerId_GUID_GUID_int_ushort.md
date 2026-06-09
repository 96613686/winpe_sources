# IsSidebandContainerId(_GUID,_GUID,int *,ushort * *)

- ea: `0x18004e9c0`
- end: `0x18004edf6`
- name: `?IsSidebandContainerId@@YAJU_GUID@@0PEAHPEAPEAG@Z`
- size: `1078`
- prototype: `__int64 __fastcall(struct _GUID *__struct_ptr, struct _GUID *__struct_ptr, int *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18003b790`

## callees

- `0x180006b0c`
- `0x1800076f0`
- `0x180008404`
- `0x180009650`
- `0x180010da8`
- `0x180021030`
- `0x18003e920`
- `0x18004e9c0`
- `0x180068010`

## import_xrefs

- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x18004ebcb`
- `api-ms-win-devices-query-l1-1-0!DevFindProperty` at `0x18004ebcb`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18004eb8c`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18004eca1`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18004ed93`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18004edca`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18004eb8c`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18004eca1`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18004ed93`
- `api-ms-win-devices-query-l1-1-0!DevFreeObjects` at `0x18004edca`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18004eb56`
- `api-ms-win-devices-query-l1-1-0!DevGetObjects` at `0x18004eb56`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ed7e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec0e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ec8c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004ed7e`

## string_xrefs

- `0x18004eb67`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004ec51`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x18004eda8`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall IsSidebandContainerId(struct _GUID *a1, struct _GUID *a2, int *a3, unsigned __int16 **a4)
{
  int Objects; // ebx
  __int64 v7; // rdx
  __int64 Property; // rax
  __int64 v10; // rdx
  LPVOID v11; // rcx
  void *v12; // rbx
  int v13; // edi
  __int64 v14; // rdx
  __int64 v15; // rsi
  __int64 (__fastcall *v16)(__int64, void *, _QWORD); // rdi
  __int64 v17; // rcx
  int v18; // [rsp+20h] [rbp-E0h]
  unsigned int v19; // [rsp+40h] [rbp-C0h] BYREF
  char v20; // [rsp+44h] [rbp-BCh] BYREF
  __int64 v21; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v22; // [rsp+50h] [rbp-B0h] BYREF
  __int64 (__fastcall ***v23)(_QWORD, GUID *, __int64 *); // [rsp+58h] [rbp-A8h] BYREF
  __int64 v24; // [rsp+60h] [rbp-A0h] BYREF
  LPVOID pv; // [rsp+68h] [rbp-98h] BYREF
  LPVOID v26[3]; // [rsp+70h] [rbp-90h] BYREF
  char v27; // [rsp+88h] [rbp-78h]
  DEVPROPKEY v28; // [rsp+90h] [rbp-70h] BYREF
  int v29; // [rsp+A4h] [rbp-5Ch]
  __int64 v30; // [rsp+A8h] [rbp-58h]
  _DWORD v31[3]; // [rsp+B0h] [rbp-50h] BYREF
  __int128 v32; // [rsp+BCh] [rbp-44h]
  _BYTE v33[28]; // [rsp+CCh] [rbp-34h] BYREF
  int v34; // [rsp+E8h] [rbp-18h]
  DEVPROPKEY v35; // [rsp+F0h] [rbp-10h]
  int v36; // [rsp+104h] [rbp+4h]
  __int64 v37; // [rsp+108h] [rbp+8h]
  int v38; // [rsp+110h] [rbp+10h]
  int v39; // [rsp+114h] [rbp+14h]
  struct _GUID *v40; // [rsp+118h] [rbp+18h]
  int v41; // [rsp+120h] [rbp+20h]
  DEVPROPKEY v42; // [rsp+128h] [rbp+28h]
  int v43; // [rsp+13Ch] [rbp+3Ch]
  __int64 v44; // [rsp+140h] [rbp+40h]
  int v45; // [rsp+148h] [rbp+48h]
  int v46; // [rsp+14Ch] [rbp+4Ch]
  struct _GUID *v47; // [rsp+150h] [rbp+50h]
  int v48; // [rsp+158h] [rbp+58h]
  DEVPROPKEY v49; // [rsp+160h] [rbp+60h]
  int v50; // [rsp+174h] [rbp+74h]
  __int64 v51; // [rsp+178h] [rbp+78h]
  int v52; // [rsp+180h] [rbp+80h]
  int v53; // [rsp+184h] [rbp+84h]
  char *v54; // [rsp+188h] [rbp+88h]
  int v55; // [rsp+190h] [rbp+90h]
  int v56; // [rsp+198h] [rbp+98h]
  __int128 v57; // [rsp+19Ch] [rbp+9Ch]
  _BYTE v58[28]; // [rsp+1ACh] [rbp+ACh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+218h] [rbp+118h]

  v19 = 0;
  v21 = 0;
  v26[1] = &v21;
  v26[2] = &v19;
  v27 = 1;
  v26[0] = 0;
  v20 = -1;
  v31[0] = 0x100000;
  v31[2] = 0;
  v32 = 0;
  memset(v33, 0, sizeof(v33));
  v34 = 2;
  v35 = DEVPKEY_Device_ContainerId;
  v36 = 0;
  v37 = 0;
  v38 = 13;
  v39 = 16;
  v40 = a1;
  v41 = 2;
  v42 = DEVPKEY_DeviceInterface_ClassGuid;
  v43 = 0;
  v44 = 0;
  v45 = 13;
  v46 = 16;
  v47 = a2;
  v48 = 2;
  v49 = DEVPKEY_DeviceInterface_Enabled;
  v50 = 0;
  v51 = 0;
  v52 = 17;
  v53 = 1;
  v54 = &v20;
  v55 = 0x200000;
  v56 = 0;
  v57 = 0;
  memset(v58, 0, sizeof(v58));
  v28 = DEVPKEY_Device_InstanceId;
  v29 = 0;
  v30 = 0;
  Objects = DevGetObjects(1, 0, 1, &v28, 5, v31, &v19, &v21);
  if ( Objects < 0 )
  {
    v7 = 541;
LABEL_3:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v7,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)Objects,
      v18);
    if ( v21 )
      DevFreeObjects(v19);
    return (unsigned int)Objects;
  }
  if ( !v19 || !v21 )
  {
    v10 = 543;
    goto LABEL_31;
  }
  Property = DevFindProperty(&DEVPKEY_Device_InstanceId, 0, 0, *(unsigned int *)(v21 + 16), *(_QWORD *)(v21 + 24));
  if ( !Property )
  {
    v10 = 552;
LABEL_31:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)0x80070490LL,
      v18);
    if ( v21 )
      DevFreeObjects(v19);
    return 2147943568LL;
  }
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    &pv,
    *(_QWORD *)(Property + 40),
    (unsigned __int64)*(unsigned int *)(Property + 36) >> 1);
  wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
    v26,
    &pv);
  v11 = pv;
  if ( pv )
    CoTaskMemFree(pv);
  v12 = v26[0];
  if ( !v26[0] )
  {
    Objects = -2147024882;
    v7 = 555;
    goto LABEL_3;
  }
  v23 = 0;
  v22 = 0;
  v24 = 0;
  v13 = wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(v11, &v24);
  if ( v13 < 0 )
  {
    v14 = 562;
LABEL_16:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
      (const char *)(unsigned int)v13,
      v18);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
    CoTaskMemFree(v12);
    if ( v21 )
      DevFreeObjects(v19);
    return (unsigned int)v13;
  }
  v15 = v24;
  v16 = *(__int64 (__fastcall **)(__int64, void *, _QWORD))(*(_QWORD *)v24 + 64LL);
  wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v23);
  v13 = v16(v15, v12, &v23);
  if ( v13 < 0 )
  {
    v14 = 563;
    goto LABEL_16;
  }
  v17 = v22;
  v22 = 0;
  if ( v17 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
  v13 = (**v23)(v23, &GUID_d666063f_1587_4e43_81f1_b948e807363f, &v22);
  if ( v13 < 0 )
  {
    v14 = 564;
    goto LABEL_16;
  }
  v13 = (*(__int64 (__fastcall **)(__int64, unsigned __int16 **))(*(_QWORD *)v22 + 40LL))(v22, a4);
  if ( v13 < 0 )
  {
    v14 = 565;
    goto LABEL_16;
  }
  *a3 = 1;
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v22);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v23);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v24);
  CoTaskMemFree(v12);
  if ( v21 )
    DevFreeObjects(v19);
  return 0;
}

```

## disassembly

```asm
0x18004e9c0  push    rbp
0x18004e9c2  push    rbx
0x18004e9c3  push    rsi
0x18004e9c4  push    rdi
0x18004e9c5  push    r12
0x18004e9c7  push    r14
0x18004e9c9  push    r15
0x18004e9cb  lea     rbp, [rsp-0E0h]
0x18004e9d3  sub     rsp, 1E0h
0x18004e9da  mov     rax, cs:__security_cookie
0x18004e9e1  xor     rax, rsp
0x18004e9e4  mov     [rbp+110h+var_40], rax
0x18004e9eb  mov     r15, r9
0x18004e9ee  mov     r14, r8
0x18004e9f1  xor     r12d, r12d
0x18004e9f4  mov     [rsp+210h+var_1D0], r12d
0x18004e9f9  mov     [rsp+210h+var_1C8], r12
0x18004e9fe  lea     rax, [rsp+210h+var_1C8]
0x18004ea03  mov     [rsp+210h+var_198], rax
0x18004ea08  lea     rax, [rsp+210h+var_1D0]
0x18004ea0d  mov     [rbp+110h+var_190], rax
0x18004ea11  mov     [rbp+110h+var_188], 1
0x18004ea15  mov     [rsp+210h+var_1A0], r12
0x18004ea1a  mov     [rsp+210h+var_1CC], 0FFh
0x18004ea1f  mov     [rbp+110h+var_160], 100000h
0x18004ea26  mov     [rbp+110h+var_158], r12d
0x18004ea2a  xorps   xmm0, xmm0
0x18004ea2d  movups  [rbp+110h+var_154], xmm0
0x18004ea31  movups  xmmword ptr [rbp+110h+var_144], xmm0
0x18004ea35  movups  xmmword ptr [rbp+110h+var_144+0Ch], xmm0
0x18004ea39  lea     r10d, [r12+2]
0x18004ea3e  mov     [rbp+110h+var_128], r10d
0x18004ea42  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_ContainerId.fmtid.Data1
0x18004ea49  movaps  [rbp+110h+var_120], xmm0
0x18004ea4d  mov     eax, cs:DEVPKEY_Device_ContainerId.pid
0x18004ea53  mov     [rbp+110h+var_110], eax
0x18004ea56  mov     [rbp+110h+var_10C], r12d
0x18004ea5a  mov     [rbp+110h+var_108], r12
0x18004ea5e  lea     r9d, [r12+0Dh]
0x18004ea63  mov     [rbp+110h+var_100], r9d
0x18004ea67  lea     r8d, [r12+10h]
0x18004ea6c  mov     [rbp+110h+var_FC], r8d
0x18004ea70  mov     [rbp+110h+var_F8], rcx
0x18004ea74  mov     [rbp+110h+var_F0], r10d
0x18004ea78  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_ClassGuid.fmtid.Data1
0x18004ea7f  movups  [rbp+110h+var_E8], xmm0
0x18004ea83  mov     eax, cs:DEVPKEY_DeviceInterface_ClassGuid.pid
0x18004ea89  mov     [rbp+110h+var_D8], eax
0x18004ea8c  mov     [rbp+110h+var_D4], r12d
0x18004ea90  mov     [rbp+110h+var_D0], r12
0x18004ea94  mov     [rbp+110h+var_C8], r9d
0x18004ea98  mov     [rbp+110h+var_C4], r8d
0x18004ea9c  mov     [rbp+110h+var_C0], rdx
0x18004eaa0  mov     [rbp+110h+var_B8], r10d
0x18004eaa4  movups  xmm0, xmmword ptr cs:DEVPKEY_DeviceInterface_Enabled.fmtid.Data1
0x18004eaab  movaps  [rbp+110h+var_B0], xmm0
0x18004eaaf  mov     eax, cs:DEVPKEY_DeviceInterface_Enabled.pid
0x18004eab5  mov     [rbp+110h+var_A0], eax
0x18004eab8  mov     [rbp+110h+var_9C], r12d
0x18004eabc  mov     [rbp+110h+var_98], r12
0x18004eac0  mov     [rbp+110h+var_90], 11h
0x18004eaca  mov     [rbp+110h+var_8C], 1
0x18004ead4  lea     rax, [rsp+210h+var_1CC]
0x18004ead9  mov     [rbp+110h+var_88], rax
0x18004eae0  mov     [rbp+110h+var_80], 200000h
0x18004eaea  mov     [rbp+110h+var_78], r12d
0x18004eaf1  xorps   xmm0, xmm0
0x18004eaf4  movups  [rbp+110h+var_74], xmm0
0x18004eafb  movups  xmmword ptr [rbp+110h+var_64], xmm0
0x18004eb02  movups  xmmword ptr [rbp+110h+var_64+0Ch], xmm0
0x18004eb09  movups  xmm0, xmmword ptr cs:DEVPKEY_Device_InstanceId.fmtid.Data1
0x18004eb10  movups  [rbp+110h+var_180], xmm0
0x18004eb14  mov     eax, cs:DEVPKEY_Device_InstanceId.pid
0x18004eb1a  mov     [rbp+110h+var_170], eax
0x18004eb1d  mov     [rbp+110h+var_16C], r12d
0x18004eb21  mov     [rbp+110h+var_168], r12
0x18004eb25  lea     rax, [rsp+210h+var_1C8]
0x18004eb2a  mov     [rsp+210h+var_1D8], rax
0x18004eb2f  lea     rax, [rsp+210h+var_1D0]
0x18004eb34  mov     [rsp+210h+var_1E0], rax
0x18004eb39  lea     rax, [rbp+110h+var_160]
0x18004eb3d  mov     [rsp+210h+var_1E8], rax
0x18004eb42  mov     [rsp+210h+var_1F0], 5; int
0x18004eb4a  lea     r9, [rbp+110h+var_180]
0x18004eb4e  xor     edx, edx
0x18004eb50  lea     ecx, [rdx+1]
0x18004eb53  mov     r8d, ecx
0x18004eb56  call    cs:__imp_DevGetObjects
0x18004eb5c  mov     ebx, eax
0x18004eb5e  test    eax, eax
0x18004eb60  jns     short loc_18004EB99
0x18004eb62  mov     edx, 21Dh; void *
0x18004eb67  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004eb6e  mov     r9d, ebx; char *
0x18004eb71  mov     rcx, [rbp+118h]; this
0x18004eb78  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004eb7d  nop
0x18004eb7e  mov     rdx, [rsp+210h+var_1C8]
0x18004eb83  test    rdx, rdx
0x18004eb86  jz      short loc_18004EB92
0x18004eb88  mov     ecx, [rsp+210h+var_1D0]
0x18004eb8c  call    cs:__imp_DevFreeObjects
0x18004eb92  mov     eax, ebx
0x18004eb94  jmp     loc_18004EDD5
0x18004eb99  cmp     [rsp+210h+var_1D0], r12d
0x18004eb9e  jz      loc_18004ED9D
0x18004eba4  mov     r9, [rsp+210h+var_1C8]
0x18004eba9  test    r9, r9
0x18004ebac  jz      loc_18004ED9D
0x18004ebb2  mov     rax, [r9+18h]
0x18004ebb6  mov     qword ptr [rsp+210h+var_1F0], rax; int
0x18004ebbb  mov     r9d, [r9+10h]
0x18004ebbf  xor     r8d, r8d
0x18004ebc2  xor     edx, edx
0x18004ebc4  lea     rcx, DEVPKEY_Device_InstanceId
0x18004ebcb  call    cs:__imp_DevFindProperty
0x18004ebd1  test    rax, rax
0x18004ebd4  jnz     short loc_18004EBE0
0x18004ebd6  mov     edx, 228h
0x18004ebdb  jmp     loc_18004EDA2
0x18004ebe0  mov     r8d, [rax+24h]
0x18004ebe4  shr     r8, 1
0x18004ebe7  mov     rdx, [rax+28h]
0x18004ebeb  lea     rcx, [rsp+210h+pv]
0x18004ebf0  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18004ebf5  lea     rdx, [rsp+210h+pv]
0x18004ebfa  lea     rcx, [rsp+210h+var_1A0]
0x18004ebff  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18004ec04  mov     rcx, [rsp+210h+pv]; pv
0x18004ec09  test    rcx, rcx
0x18004ec0c  jz      short loc_18004EC14
0x18004ec0e  call    cs:__imp_CoTaskMemFree
0x18004ec14  mov     rbx, [rsp+210h+var_1A0]
0x18004ec19  test    rbx, rbx
0x18004ec1c  jnz     short loc_18004EC2D
0x18004ec1e  mov     ebx, 8007000Eh
0x18004ec23  mov     edx, 22Bh
0x18004ec28  jmp     loc_18004EB67
0x18004ec2d  mov     [rsp+210h+var_1B8], r12
0x18004ec32  mov     [rsp+210h+var_1C0], r12
0x18004ec37  mov     [rsp+210h+var_1B0], r12
0x18004ec3c  lea     rdx, [rsp+210h+var_1B0]
0x18004ec41  call    ??$com_query_to_nothrow@UIPnpDeviceEnumerator@@AEAPEAUIMMDeviceEnumerator@@@wil@@YAJAEAPEAUIMMDeviceEnumerator@@PEAPEAUIPnpDeviceEnumerator@@@Z; wil::com_query_to_nothrow<IPnpDeviceEnumerator,IMMDeviceEnumerator * &>(IMMDeviceEnumerator * &,IPnpDeviceEnumerator * *)
0x18004ec46  mov     edi, eax
0x18004ec48  test    eax, eax
0x18004ec4a  jns     short loc_18004ECAE
0x18004ec4c  mov     edx, 232h; void *
0x18004ec51  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004ec58  mov     r9d, edi; char *
0x18004ec5b  mov     rcx, [rbp+118h]; this
0x18004ec62  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004ec67  nop
0x18004ec68  lea     rcx, [rsp+210h+var_1C0]
0x18004ec6d  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ec72  nop
0x18004ec73  lea     rcx, [rsp+210h+var_1B8]
0x18004ec78  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ec7d  nop
0x18004ec7e  lea     rcx, [rsp+210h+var_1B0]
0x18004ec83  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ec88  nop
0x18004ec89  mov     rcx, rbx; pv
0x18004ec8c  call    cs:__imp_CoTaskMemFree
0x18004ec92  nop
0x18004ec93  mov     rdx, [rsp+210h+var_1C8]
0x18004ec98  test    rdx, rdx
0x18004ec9b  jz      short loc_18004ECA7
0x18004ec9d  mov     ecx, [rsp+210h+var_1D0]
0x18004eca1  call    cs:__imp_DevFreeObjects
0x18004eca7  mov     eax, edi
0x18004eca9  jmp     loc_18004EDD5
0x18004ecae  mov     rsi, [rsp+210h+var_1B0]
0x18004ecb3  mov     rax, [rsi]
0x18004ecb6  mov     rdi, [rax+40h]
0x18004ecba  lea     rcx, [rsp+210h+var_1B8]
0x18004ecbf  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x18004ecc4  lea     r8, [rsp+210h+var_1B8]
0x18004ecc9  mov     rdx, rbx
0x18004eccc  mov     rcx, rsi
0x18004eccf  mov     rax, rdi
0x18004ecd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ecd7  mov     edi, eax
0x18004ecd9  test    eax, eax
0x18004ecdb  jns     short loc_18004ECE7
0x18004ecdd  mov     edx, 233h
0x18004ece2  jmp     loc_18004EC51
0x18004ece7  mov     rcx, [rsp+210h+var_1C0]
0x18004ecec  mov     [rsp+210h+var_1C0], r12
0x18004ecf1  test    rcx, rcx
0x18004ecf4  jz      short loc_18004ED03
0x18004ecf6  mov     rax, [rcx]
0x18004ecf9  mov     rax, [rax+10h]
0x18004ecfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed02  nop
0x18004ed03  mov     rcx, [rsp+210h+var_1B8]
0x18004ed08  mov     rax, [rcx]
0x18004ed0b  lea     r8, [rsp+210h+var_1C0]
0x18004ed10  lea     rdx, _GUID_d666063f_1587_4e43_81f1_b948e807363f
0x18004ed17  mov     rax, [rax]
0x18004ed1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed1f  mov     edi, eax
0x18004ed21  test    eax, eax
0x18004ed23  jns     short loc_18004ED2F
0x18004ed25  mov     edx, 234h
0x18004ed2a  jmp     loc_18004EC51
0x18004ed2f  mov     rcx, [rsp+210h+var_1C0]
0x18004ed34  mov     rax, [rcx]
0x18004ed37  mov     rdx, r15
0x18004ed3a  mov     rax, [rax+28h]
0x18004ed3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ed43  mov     edi, eax
0x18004ed45  test    eax, eax
0x18004ed47  jns     short loc_18004ED53
0x18004ed49  mov     edx, 235h
0x18004ed4e  jmp     loc_18004EC51
0x18004ed53  mov     dword ptr [r14], 1
0x18004ed5a  lea     rcx, [rsp+210h+var_1C0]
0x18004ed5f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ed64  nop
0x18004ed65  lea     rcx, [rsp+210h+var_1B8]
0x18004ed6a  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ed6f  nop
0x18004ed70  lea     rcx, [rsp+210h+var_1B0]
0x18004ed75  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18004ed7a  nop
0x18004ed7b  mov     rcx, rbx; pv
0x18004ed7e  call    cs:__imp_CoTaskMemFree
0x18004ed84  nop
0x18004ed85  mov     rdx, [rsp+210h+var_1C8]
0x18004ed8a  test    rdx, rdx
0x18004ed8d  jz      short loc_18004ED99
0x18004ed8f  mov     ecx, [rsp+210h+var_1D0]
0x18004ed93  call    cs:__imp_DevFreeObjects
0x18004ed99  xor     eax, eax
0x18004ed9b  jmp     short loc_18004EDD5
0x18004ed9d  mov     edx, 21Fh; void *
0x18004eda2  mov     r9d, 80070490h; char *
0x18004eda8  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18004edaf  mov     rcx, [rbp+118h]; this
0x18004edb6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004edbb  nop
0x18004edbc  mov     rdx, [rsp+210h+var_1C8]
0x18004edc1  test    rdx, rdx
0x18004edc4  jz      short loc_18004EDD0
0x18004edc6  mov     ecx, [rsp+210h+var_1D0]
0x18004edca  call    cs:__imp_DevFreeObjects
0x18004edd0  mov     eax, 80070490h
0x18004edd5  mov     rcx, [rbp+110h+var_40]
0x18004eddc  xor     rcx, rsp; StackCookie
0x18004eddf  call    __security_check_cookie
0x18004ede4  add     rsp, 1E0h
0x18004edeb  pop     r15
0x18004eded  pop     r14
0x18004edef  pop     r12
0x18004edf1  pop     rdi
0x18004edf2  pop     rsi
0x18004edf3  pop     rbx
0x18004edf4  pop     rbp
0x18004edf5  retn
```
