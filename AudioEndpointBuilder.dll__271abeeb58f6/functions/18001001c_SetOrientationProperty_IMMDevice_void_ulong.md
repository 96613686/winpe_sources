# SetOrientationProperty(IMMDevice *,void *,ulong)

- ea: `0x18001001c`
- end: `0x1800105b1`
- name: `?SetOrientationProperty@@YAJPEAUIMMDevice@@PEAXK@Z`
- size: `1429`
- prototype: `__int64 __fastcall(struct IMMDevice *, void *)`
- caller_count: `2`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x18000fce0`
- `0x18002e144`

## callees

- `0x1800035d0`
- `0x180006b0c`
- `0x18000fb60`
- `0x18001001c`
- `0x180010da8`
- `0x180021030`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010168`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010591`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010168`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180010591`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001029a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800102ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001052e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001053e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100b3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800100c3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001029a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800102ae`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001052e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001053e`

## string_xrefs

- `0x180010098`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`
- `0x180010280`: `avcore\audiocore\server\audioendpointbuilder\dll\avendpointbuilder.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall SetOrientationProperty(struct IMMDevice *a1, void *a2)
{
  struct IMMDeviceVtbl *lpVtbl; // rax
  int v5; // eax
  unsigned int v6; // ebx
  HRESULT (__stdcall *GetId)(IMMDevice *, LPWSTR *); // rbx
  int v8; // eax
  __int64 v9; // rdx
  HRESULT (__stdcall *Activate)(IMMDevice *, const IID *const, DWORD, PROPVARIANT *, void **); // rbx
  __int64 v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, _QWORD, __int64 *); // rbx
  __int64 v15; // rdi
  __int64 (__fastcall *v16)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)); // rbx
  __int64 v17; // rcx
  __int64 v18; // rbx
  __int64 (__fastcall *v19)(__int64, __int64 *); // rdi
  __int64 v20; // rcx
  __int64 v21; // rdi
  __int64 (__fastcall *v22)(__int64, LPVOID *); // rbx
  struct IUnknown *v23; // r9
  ULONG (__stdcall *Release)(IUnknown *); // rbx
  __int64 v25; // rcx
  __int64 v26; // rbx
  __int64 (__fastcall *v27)(__int64, GUID *, __int64); // rdi
  __int64 v28; // rcx
  int *v30; // [rsp+20h] [rbp-69h]
  LPVOID v31; // [rsp+40h] [rbp-49h] BYREF
  __int64 v32; // [rsp+48h] [rbp-41h] BYREF
  __int64 v33; // [rsp+50h] [rbp-39h] BYREF
  __int64 v34; // [rsp+58h] [rbp-31h] BYREF
  __int64 v35; // [rsp+60h] [rbp-29h] BYREF
  int v36[2]; // [rsp+68h] [rbp-21h] BYREF
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+70h] [rbp-19h] BYREF
  __int64 v38; // [rsp+78h] [rbp-11h] BYREF
  __int64 v39; // [rsp+80h] [rbp-9h] BYREF
  PROPVARIANT pvar[2]; // [rsp+88h] [rbp-1h] BYREF
  __int64 v41; // [rsp+98h] [rbp+Fh]
  GUID v42; // [rsp+A0h] [rbp+17h] BYREF
  int v43; // [rsp+B0h] [rbp+27h]
  int v44; // [rsp+B4h] [rbp+2Bh]
  int v45; // [rsp+B8h] [rbp+2Fh]
  int v46; // [rsp+BCh] [rbp+33h]
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]
  int v48; // [rsp+100h] [rbp+77h] BYREF
  LPVOID pv; // [rsp+108h] [rbp+7Fh] BYREF

  *(_OWORD *)pvar = 0;
  v41 = 0;
  *(_QWORD *)v36 = 0;
  v38 = 0;
  v37 = 0;
  v32 = 0;
  v35 = 0;
  v34 = 0;
  v33 = 0;
  v48 = 0;
  v31 = 0;
  pv = 0;
  lpVtbl = a1->lpVtbl;
  v39 = 0;
  v5 = ((__int64 (__fastcall *)(struct IMMDevice *, _QWORD, __int64 *))lpVtbl->OpenPropertyStore)(a1, 0, &v39);
  v6 = v5;
  if ( v5 >= 0 )
  {
    if ( (*(int (__fastcall **)(__int64, __int64 *, PROPVARIANT *))(*(_QWORD *)v39 + 40LL))(
           v39,
           PKEY_Devices_AudioPosture_Support,
           pvar) >= 0
      && LOWORD(pvar[0]) == 11
      && LOWORD(pvar[1]) )
    {
      GetId = a1->lpVtbl->GetId;
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &v31,
        0);
      v8 = ((__int64 (__fastcall *)(struct IMMDevice *, LPVOID *))GetId)(a1, &v31);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 3965;
LABEL_20:
        v12 = (unsigned int)v8;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v9,
          (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
          (const char *)v12,
          (int)v30);
        if ( pv )
          CoTaskMemFree(pv);
        if ( v31 )
          CoTaskMemFree(v31);
LABEL_58:
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v34);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v35);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v37);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v38);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(v36);
        PropVariantClear(pvar);
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v39);
        return v6;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x80000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
      {
        WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids, v31);
      }
      Activate = a1->lpVtbl->Activate;
      v11 = *(_QWORD *)v36;
      *(_QWORD *)v36 = 0;
      if ( v11 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      v30 = v36;
      v8 = ((__int64 (__fastcall *)(struct IMMDevice *, GUID *, __int64))Activate)(
             a1,
             &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
             23);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 3970;
        goto LABEL_20;
      }
      v13 = *(_QWORD *)v36;
      v14 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(**(_QWORD **)v36 + 32LL);
      wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v38);
      v8 = v14(v13, 0, &v38);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 3972;
        goto LABEL_20;
      }
      v15 = v38;
      v16 = *(__int64 (__fastcall **)(__int64, __int64 (__fastcall ****)(_QWORD, GUID *, __int64 *)))(*(_QWORD *)v38 + 64LL);
      wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(&v37);
      v8 = v16(v15, &v37);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 3974;
        goto LABEL_20;
      }
      v17 = v32;
      v32 = 0;
      if ( v17 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
      v8 = (**v37)(v37, &GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9, &v32);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 3976;
        goto LABEL_20;
      }
      v8 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 32LL))(v32, &v48);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 3978;
        goto LABEL_20;
      }
      v18 = v32;
      v19 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v32 + 96LL);
      v20 = v35;
      v35 = 0;
      if ( v20 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      v8 = v19(v18, &v35);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 3981;
        goto LABEL_20;
      }
      v21 = v35;
      v22 = *(__int64 (__fastcall **)(__int64, LPVOID *))(*(_QWORD *)v35 + 64LL);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
        &pv,
        0);
      v8 = v22(v21, &pv);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 3983;
        goto LABEL_20;
      }
      v23 = g_DeviceEnumerator;
      Release = g_DeviceEnumerator->lpVtbl[1].Release;
      v25 = v34;
      v34 = 0;
      if ( v25 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
        v23 = g_DeviceEnumerator;
      }
      v8 = ((__int64 (__fastcall *)(struct IUnknown *, LPVOID, __int64 *))Release)(v23, pv, &v34);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 3985;
        goto LABEL_20;
      }
      v26 = v34;
      v27 = *(__int64 (__fastcall **)(__int64, GUID *, __int64))(*(_QWORD *)v34 + 24LL);
      v28 = v33;
      v33 = 0;
      if ( v28 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      v30 = (int *)&v33;
      v8 = v27(v26, &GUID_28f54685_06fd_11d2_b27a_00a0c9223196, 1);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 3987;
        goto LABEL_20;
      }
      if ( !v33 )
      {
        v6 = -2147023728;
        v12 = 2147943568LL;
        v9 = 3989;
        goto LABEL_21;
      }
      v46 = 0;
      v42 = GUID_a3fb7b0d_474e_4f51_a379_51282dd4fa8f;
      v43 = 1;
      v44 = 2;
      v45 = (unsigned __int16)v48;
      LODWORD(v30) = 4;
      v8 = (*(__int64 (__fastcall **)(__int64, GUID *, __int64, void *))(*(_QWORD *)v33 + 24LL))(v33, &v42, 32, a2);
      v6 = v8;
      if ( v8 < 0 )
      {
        v9 = 4008;
        goto LABEL_20;
      }
    }
    if ( pv )
      CoTaskMemFree(pv);
    if ( v31 )
      CoTaskMemFree(v31);
    v6 = 0;
    goto LABEL_58;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF72,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\avendpointbuilder.cpp",
    (const char *)(unsigned int)v5,
    (int)v30);
  if ( pv )
    CoTaskMemFree(pv);
  PropVariantClear(pvar);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  return v6;
}

```

## disassembly

```asm
0x18001001c  mov     [rsp-8+arg_10], r8d
0x180010021  push    rbp
0x180010022  push    rbx
0x180010023  push    rsi
0x180010024  push    rdi
0x180010025  push    r14
0x180010027  lea     rbp, [rsp-37h]
0x18001002c  sub     rsp, 0C0h
0x180010033  mov     rsi, rdx
0x180010036  mov     rdi, rcx
0x180010039  xorps   xmm0, xmm0
0x18001003c  xor     eax, eax
0x18001003e  movups  xmmword ptr [rbp+57h+pvar], xmm0
0x180010042  mov     [rbp+57h+var_48], rax
0x180010046  xor     r14d, r14d
0x180010049  mov     qword ptr [rbp+57h+var_78], r14
0x18001004d  mov     [rbp+57h+var_68], r14
0x180010051  mov     [rbp+57h+var_70], r14
0x180010055  mov     [rbp+57h+var_98], r14
0x180010059  mov     [rbp+57h+var_80], r14
0x18001005d  mov     [rbp+57h+var_88], r14
0x180010061  mov     [rbp+57h+var_90], r14
0x180010065  mov     [rbp+57h+arg_10], r14d
0x180010069  mov     [rbp+57h+var_A0], r14
0x18001006d  mov     [rbp+57h+pv], r14
0x180010071  mov     rax, [rcx]
0x180010074  mov     [rbp+57h+var_60], r14
0x180010078  lea     r8, [rbp+57h+var_60]
0x18001007c  xor     edx, edx
0x18001007e  mov     rax, [rax+20h]
0x180010082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010087  mov     ebx, eax
0x180010089  test    eax, eax
0x18001008b  jns     loc_18001018A
0x180010091  mov     rcx, [rbp+5Fh]; this
0x180010095  mov     r9d, eax; char *
0x180010098  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x18001009f  mov     edx, 0F72h; void *
0x1800100a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800100a9  nop
0x1800100aa  mov     rcx, [rbp+57h+pv]; pv
0x1800100ae  test    rcx, rcx
0x1800100b1  jz      short loc_1800100BA
0x1800100b3  call    cs:__imp_CoTaskMemFree
0x1800100b9  nop
0x1800100ba  mov     rcx, [rbp+57h+var_A0]; pv
0x1800100be  test    rcx, rcx
0x1800100c1  jz      short loc_1800100CA
0x1800100c3  call    cs:__imp_CoTaskMemFree
0x1800100c9  nop
0x1800100ca  mov     rcx, [rbp+57h+var_90]
0x1800100ce  test    rcx, rcx
0x1800100d1  jz      short loc_1800100E0
0x1800100d3  mov     rax, [rcx]
0x1800100d6  mov     rax, [rax+10h]
0x1800100da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100df  nop
0x1800100e0  mov     rcx, [rbp+57h+var_88]
0x1800100e4  test    rcx, rcx
0x1800100e7  jz      short loc_1800100F6
0x1800100e9  mov     rax, [rcx]
0x1800100ec  mov     rax, [rax+10h]
0x1800100f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100f5  nop
0x1800100f6  mov     rcx, [rbp+57h+var_80]
0x1800100fa  test    rcx, rcx
0x1800100fd  jz      short loc_18001010C
0x1800100ff  mov     rax, [rcx]
0x180010102  mov     rax, [rax+10h]
0x180010106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001010b  nop
0x18001010c  mov     rcx, [rbp+57h+var_98]
0x180010110  test    rcx, rcx
0x180010113  jz      short loc_180010122
0x180010115  mov     rax, [rcx]
0x180010118  mov     rax, [rax+10h]
0x18001011c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010121  nop
0x180010122  mov     rcx, [rbp+57h+var_70]
0x180010126  test    rcx, rcx
0x180010129  jz      short loc_180010138
0x18001012b  mov     rax, [rcx]
0x18001012e  mov     rax, [rax+10h]
0x180010132  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010137  nop
0x180010138  mov     rcx, [rbp+57h+var_68]
0x18001013c  test    rcx, rcx
0x18001013f  jz      short loc_18001014E
0x180010141  mov     rax, [rcx]
0x180010144  mov     rax, [rax+10h]
0x180010148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001014d  nop
0x18001014e  mov     rcx, qword ptr [rbp+57h+var_78]
0x180010152  test    rcx, rcx
0x180010155  jz      short loc_180010164
0x180010157  mov     rax, [rcx]
0x18001015a  mov     rax, [rax+10h]
0x18001015e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010163  nop
0x180010164  lea     rcx, [rbp+57h+pvar]; pvar
0x180010168  call    cs:__imp_PropVariantClear
0x18001016e  nop
0x18001016f  mov     rcx, [rbp+57h+var_60]
0x180010173  test    rcx, rcx
0x180010176  jz      short loc_180010185
0x180010178  mov     rax, [rcx]
0x18001017b  mov     rax, [rax+10h]
0x18001017f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010184  nop
0x180010185  jmp     loc_1800105A1
0x18001018a  mov     rcx, [rbp+57h+var_60]
0x18001018e  mov     rax, [rcx]
0x180010191  lea     r8, [rbp+57h+pvar]
0x180010195  lea     rdx, PKEY_Devices_AudioPosture_Support
0x18001019c  mov     rax, [rax+28h]
0x1800101a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101a5  test    eax, eax
0x1800101a7  js      loc_180010525
0x1800101ad  cmp     word ptr [rbp+57h+pvar], 0Bh
0x1800101b2  jnz     loc_180010525
0x1800101b8  cmp     word ptr [rbp+57h+pvar+8], r14w
0x1800101bd  jz      loc_180010525
0x1800101c3  mov     rax, [rdi]
0x1800101c6  mov     rbx, [rax+28h]
0x1800101ca  xor     edx, edx
0x1800101cc  lea     rcx, [rbp+57h+var_A0]
0x1800101d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800101d5  lea     rdx, [rbp+57h+var_A0]
0x1800101d9  mov     rcx, rdi
0x1800101dc  mov     rax, rbx
0x1800101df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101e4  mov     ebx, eax
0x1800101e6  test    eax, eax
0x1800101e8  jns     short loc_1800101F4
0x1800101ea  mov     edx, 0F7Dh
0x1800101ef  jmp     loc_18001027D
0x1800101f4  lea     rax, WPP_GLOBAL_Control
0x1800101fb  mov     rcx, cs:WPP_GLOBAL_Control
0x180010202  cmp     rcx, rax
0x180010205  jz      short loc_18001022F
0x180010207  test    dword ptr [rcx+1Ch], 80000h
0x18001020e  jz      short loc_18001022F
0x180010210  cmp     byte ptr [rcx+19h], 4
0x180010214  jb      short loc_18001022F
0x180010216  mov     edx, 24h ; '$'
0x18001021b  mov     r9, [rbp+57h+var_A0]
0x18001021f  lea     r8, WPP_2d9c823d16a63a6be100bbcd5714e122_Traceguids
0x180010226  mov     rcx, [rcx+10h]
0x18001022a  call    WPP_SF_S
0x18001022f  mov     rax, [rdi]
0x180010232  mov     rbx, [rax+18h]
0x180010236  mov     rcx, qword ptr [rbp+57h+var_78]
0x18001023a  mov     qword ptr [rbp+57h+var_78], r14
0x18001023e  test    rcx, rcx
0x180010241  jz      short loc_180010250
0x180010243  mov     rax, [rcx]
0x180010246  mov     rax, [rax+10h]
0x18001024a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001024f  nop
0x180010250  lea     rax, [rbp+57h+var_78]
0x180010254  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180010259  xor     r9d, r9d
0x18001025c  lea     r8d, [r9+17h]
0x180010260  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180010267  mov     rcx, rdi
0x18001026a  mov     rax, rbx
0x18001026d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010272  mov     ebx, eax
0x180010274  test    eax, eax
0x180010276  jns     short loc_1800102B9
0x180010278  mov     edx, 0F82h; void *
0x18001027d  mov     r9d, eax; char *
0x180010280  lea     r8, aAvcoreAudiocor_6; "avcore\\audiocore\\server\\audioendpoin"...
0x180010287  mov     rcx, [rbp+5Fh]; this
0x18001028b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180010290  nop
0x180010291  mov     rcx, [rbp+57h+pv]; pv
0x180010295  test    rcx, rcx
0x180010298  jz      short loc_1800102A1
0x18001029a  call    cs:__imp_CoTaskMemFree
0x1800102a0  nop
0x1800102a1  mov     rcx, [rbp+57h+var_A0]; pv
0x1800102a5  test    rcx, rcx
0x1800102a8  jz      loc_180010547
0x1800102ae  call    cs:__imp_CoTaskMemFree
0x1800102b4  jmp     loc_180010547
0x1800102b9  mov     rdi, qword ptr [rbp+57h+var_78]
0x1800102bd  mov     rax, [rdi]
0x1800102c0  mov     rbx, [rax+20h]
0x1800102c4  lea     rcx, [rbp+57h+var_68]
0x1800102c8  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x1800102cd  lea     r8, [rbp+57h+var_68]
0x1800102d1  xor     edx, edx
0x1800102d3  mov     rcx, rdi
0x1800102d6  mov     rax, rbx
0x1800102d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800102de  mov     ebx, eax
0x1800102e0  test    eax, eax
0x1800102e2  jns     short loc_1800102EB
0x1800102e4  mov     edx, 0F84h
0x1800102e9  jmp     short loc_18001027D
0x1800102eb  mov     rdi, [rbp+57h+var_68]
0x1800102ef  mov     rax, [rdi]
0x1800102f2  mov     rbx, [rax+40h]
0x1800102f6  lea     rcx, [rbp+57h+var_70]
0x1800102fa  call    ?reset@?$com_ptr_t@UIPnpDevnode@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IPnpDevnode,wil::err_returncode_policy>::reset(void)
0x1800102ff  lea     rdx, [rbp+57h+var_70]
0x180010303  mov     rcx, rdi
0x180010306  mov     rax, rbx
0x180010309  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001030e  mov     ebx, eax
0x180010310  test    eax, eax
0x180010312  jns     short loc_18001031E
0x180010314  mov     edx, 0F86h
0x180010319  jmp     loc_18001027D
0x18001031e  mov     rcx, [rbp+57h+var_98]
0x180010322  mov     [rbp+57h+var_98], r14
0x180010326  test    rcx, rcx
0x180010329  jz      short loc_180010338
0x18001032b  mov     rax, [rcx]
0x18001032e  mov     rax, [rax+10h]
0x180010332  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010337  nop
0x180010338  mov     rcx, [rbp+57h+var_70]
0x18001033c  mov     rax, [rcx]
0x18001033f  lea     r8, [rbp+57h+var_98]
0x180010343  lea     rdx, _GUID_ae2de0e4_5bca_4f2d_aa46_5d13f8fdb3a9
0x18001034a  mov     rax, [rax]
0x18001034d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010352  mov     ebx, eax
0x180010354  test    eax, eax
0x180010356  jns     short loc_180010362
0x180010358  mov     edx, 0F88h
0x18001035d  jmp     loc_18001027D
0x180010362  mov     rcx, [rbp+57h+var_98]
0x180010366  mov     rax, [rcx]
0x180010369  lea     rdx, [rbp+57h+arg_10]
0x18001036d  mov     rax, [rax+20h]
0x180010371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010376  mov     ebx, eax
0x180010378  test    eax, eax
0x18001037a  jns     short loc_180010386
0x18001037c  mov     edx, 0F8Ah
0x180010381  jmp     loc_18001027D
0x180010386  mov     rbx, [rbp+57h+var_98]
0x18001038a  mov     rax, [rbx]
0x18001038d  mov     rdi, [rax+60h]
0x180010391  mov     rcx, [rbp+57h+var_80]
0x180010395  mov     [rbp+57h+var_80], r14
0x180010399  test    rcx, rcx
0x18001039c  jz      short loc_1800103AB
0x18001039e  mov     rdx, [rcx]
0x1800103a1  mov     rax, [rdx+10h]
0x1800103a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103aa  nop
0x1800103ab  lea     rdx, [rbp+57h+var_80]
0x1800103af  mov     rcx, rbx
0x1800103b2  mov     rax, rdi
0x1800103b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103ba  mov     ebx, eax
0x1800103bc  test    eax, eax
0x1800103be  jns     short loc_1800103CA
0x1800103c0  mov     edx, 0F8Dh
0x1800103c5  jmp     loc_18001027D
0x1800103ca  mov     rdi, [rbp+57h+var_80]
0x1800103ce  mov     rax, [rdi]
0x1800103d1  mov     rbx, [rax+40h]
0x1800103d5  xor     edx, edx
0x1800103d7  lea     rcx, [rbp+57h+pv]
0x1800103db  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800103e0  lea     rdx, [rbp+57h+pv]
0x1800103e4  mov     rcx, rdi
0x1800103e7  mov     rax, rbx
0x1800103ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103ef  mov     ebx, eax
0x1800103f1  test    eax, eax
0x1800103f3  jns     short loc_1800103FF
0x1800103f5  mov     edx, 0F8Fh
0x1800103fa  jmp     loc_18001027D
0x1800103ff  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180010406  mov     rax, [r9]
0x180010409  mov     rbx, [rax+28h]
0x18001040d  mov     rcx, [rbp+57h+var_88]
0x180010411  mov     [rbp+57h+var_88], r14
0x180010415  test    rcx, rcx
0x180010418  jz      short loc_18001042D
0x18001041a  mov     rax, [rcx]
0x18001041d  mov     rax, [rax+10h]
0x180010421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010426  mov     r9, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18001042d  lea     r8, [rbp+57h+var_88]
0x180010431  mov     rdx, [rbp+57h+pv]
0x180010435  mov     rcx, r9
0x180010438  mov     rax, rbx
0x18001043b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010440  mov     ebx, eax
0x180010442  test    eax, eax
0x180010444  jns     short loc_180010450
0x180010446  mov     edx, 0F91h
0x18001044b  jmp     loc_18001027D
  ... truncated ...
```
