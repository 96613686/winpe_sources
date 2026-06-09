# CEndpointCharacteristics::IsFormatSupportedByHwAudioEngine(tWAVEFORMATEX const *)

- ea: `0x180143ce0`
- end: `0x180144278`
- name: `?IsFormatSupportedByHwAudioEngine@CEndpointCharacteristics@@QEAAJPEBUtWAVEFORMATEX@@@Z`
- size: `1432`
- prototype: `int(CEndpointCharacteristics *__hidden this, const struct tWAVEFORMATEX *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e308`
- `0x1800af6ac`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x1800424ec`
- `0x1800cd8d0`
- `0x1800ce75c`
- `0x1800ce774`
- `0x180143ce0`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180143db6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180143de3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180143e62`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180143ed9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180143db6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180143de3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180143e62`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180143ed9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801440a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801440a4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801441a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801441b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144204`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801441a3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801441b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180144204`

## string_xrefs

- `0x180143d55`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180143da1`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180143e50`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180143f1f`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180143f70`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180143fc1`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180144051`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1801440c2`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18014418e`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall CEndpointCharacteristics::IsFormatSupportedByHwAudioEngine(
        CEndpointCharacteristics *this,
        const struct tWAVEFORMATEX *a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  int v6; // eax
  __int64 v7; // r9
  __int64 v8; // rdx
  unsigned int v9; // r15d
  unsigned int v10; // esi
  int v11; // eax
  __int64 v12; // rdx
  __int64 v13; // rdx
  __int64 v14; // r9
  HRESULT (__stdcall *GetDevice)(IMMDeviceEnumerator *, LPCWSTR, IMMDevice **); // rbx
  __int64 v16; // rax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  int v20; // eax
  __int64 v21; // rdx
  __int64 v22; // r9
  __int64 (__fastcall **v23)(_QWORD, _QWORD, _QWORD); // rax
  int v24; // eax
  unsigned int *v25; // rbx
  void *v26; // rdi
  _BYTE *v27; // rdx
  int v28; // eax
  __int64 *v30; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-C8h] BYREF
  int v32[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v33; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v34; // [rsp+50h] [rbp-B0h] BYREF
  int v35; // [rsp+58h] [rbp-A8h] BYREF
  int v36; // [rsp+5Ch] [rbp-A4h] BYREF
  int v37[2]; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT v38[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v39; // [rsp+78h] [rbp-88h]
  PROPVARIANT pvar[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v41; // [rsp+90h] [rbp-70h]
  unsigned int *v42; // [rsp+98h] [rbp-68h]
  _DWORD v43[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v44[112]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  *(_QWORD *)v37 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, GUID *, __int64, _QWORD))(**((_QWORD **)this + 5) + 24LL))(
         *((_QWORD *)this + 5),
         &GUID_2b0711de_dab7_4610_a16f_d3383749b220,
         23,
         0);
  v5 = v4;
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23DC,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v4,
      (int)v37);
    goto LABEL_54;
  }
  *(_OWORD *)pvar = 0;
  v41 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, PROPVARIANT *))(**((_QWORD **)this + 9) + 40LL))(
         *((_QWORD *)this + 9),
         &PKEY_Endpoint_HWAudioEngine_Offload_ConnectorId,
         pvar);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = (unsigned int)v6;
    v8 = 9186;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v7,
      (int)v37);
    PropVariantClear(pvar);
    goto LABEL_54;
  }
  if ( LOWORD(pvar[0]) != 19 )
  {
    v5 = -2147418113;
    v7 = 2147549183LL;
    v8 = 9187;
    goto LABEL_5;
  }
  v9 = (unsigned int)pvar[1];
  PropVariantClear(pvar);
  v30 = 0;
  v43[0] = 590439624;
  v43[1] = 1283267372;
  v43[2] = 1907779772;
  v10 = 104;
  v43[3] = 1730509416;
  v43[4] = 1;
  *(_OWORD *)v38 = 0;
  v39 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, PROPVARIANT *))(**((_QWORD **)this + 9) + 40LL))(
          *((_QWORD *)this + 9),
          v43,
          v38);
  v5 = v11;
  if ( v11 < 0 )
  {
    v13 = 9197;
LABEL_10:
    v14 = (unsigned int)v11;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v14,
      (int)v37);
    PropVariantClear(v38);
LABEL_12:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v30);
    goto LABEL_54;
  }
  if ( LOWORD(v38[0]) != 31 )
  {
    v5 = -2147418113;
    v14 = 2147549183LL;
    v13 = 9198;
    goto LABEL_11;
  }
  GetDevice = g_DeviceEnumerator->lpVtbl->GetDevice;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v30, v12);
  v11 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, PROPVARIANT, __int64 **))GetDevice)(
          g_DeviceEnumerator,
          v38[1],
          &v30);
  v5 = v11;
  if ( v11 < 0 )
  {
    v13 = 9201;
    goto LABEL_10;
  }
  PropVariantClear(v38);
  *(_QWORD *)v32 = 0;
  v16 = *v30;
  *(_QWORD *)v32 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64))(v16 + 24))(
          v30,
          &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
          1);
  v5 = v17;
  if ( v17 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23F6,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v17,
      (int)v32);
LABEL_19:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v32);
    goto LABEL_12;
  }
  v31 = 0;
  v18 = **(_QWORD **)v32;
  v31 = 0;
  v19 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v18 + 56))(*(_QWORD *)v32, v9, &v31);
  v5 = v19;
  if ( v19 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23FA,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v19,
      (int)v32);
LABEL_22:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v31);
    goto LABEL_19;
  }
  v33 = 0;
  v20 = (**v31)(v31, &GUID_9c2c4058_23f5_41de_877a_df3af236a09e, &v33);
  v5 = v20;
  if ( v20 < 0 )
  {
    v21 = 9213;
LABEL_25:
    v22 = (unsigned int)v20;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v22,
      (int)v32);
LABEL_27:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
    goto LABEL_22;
  }
  v35 = 0;
  v20 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v33 + 24LL))(v33, &v35);
  v5 = v20;
  if ( v20 < 0 )
  {
    v21 = 9217;
    goto LABEL_25;
  }
  if ( v35 != 3 )
  {
    v5 = -2147418113;
    v22 = 2147549183LL;
    v21 = 9218;
    goto LABEL_26;
  }
  v34 = 0;
  v23 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v31;
  v34 = 0;
  v24 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, GUID *, __int64 *))v23[13])(
          v31,
          1,
          &GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5,
          &v34);
  v5 = v24;
  if ( v24 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2406,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v24,
      (int)v32);
LABEL_34:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v34);
    goto LABEL_27;
  }
  v42 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2410,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v5,
      (int)v32);
    goto LABEL_34;
  }
  if ( a2->wFormatTag == 0xFFFE && a2->cbSize < 0x16u )
  {
    v5 = -2147024809;
    goto LABEL_42;
  }
  v25 = (unsigned int *)CoTaskMemAlloc(a2->cbSize + 82LL);
  v42 = v25;
  if ( !v25 )
  {
    v5 = -2147024882;
    goto LABEL_42;
  }
  *v25 = a2->cbSize + 82;
  *(_QWORD *)(v25 + 1) = 0;
  v25[3] = 0;
  *((GUID *)v25 + 1) = GUID_73647561_0000_0010_8000_00aa00389b71;
  *((GUID *)v25 + 3) = GUID_05589f81_c356_11ce_bf01_00aa0055595a;
  memcpy_0(v25 + 16, a2, a2->cbSize + 18LL);
  if ( a2->wFormatTag == 0xFFFE )
  {
    *((_OWORD *)v25 + 2) = *(_OWORD *)((char *)&a2[1].nSamplesPerSec + 2);
  }
  else
  {
    *((GUID *)v25 + 2) = GUID_00000000_0000_0010_8000_00aa00389b71;
    v25[8] = a2->wFormatTag;
  }
  v26 = v25;
  memset_0(v44, 0, 0x68u);
  v27 = v25;
  if ( *v25 >= 0x68 )
  {
    v10 = *v25;
  }
  else
  {
    memcpy_0(v44, v25, *v25);
    v27 = v44;
  }
  v36 = 0;
  v28 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, int *))(*(_QWORD *)v34 + 24LL))(v34, v27, v10, &v36);
  v5 = v28;
  if ( v28 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2422,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v28,
      (int)v32);
    CoTaskMemFree(v26);
    goto LABEL_34;
  }
  if ( v36 )
  {
    CoTaskMemFree(v26);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v34);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v31);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v32);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v30);
    v5 = 0;
  }
  else
  {
    CoTaskMemFree(v26);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v34);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v31);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v32);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v30);
    v5 = -2005139333;
  }
LABEL_54:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v37);
  return v5;
}

```

## disassembly

```asm
0x180143ce0  mov     [rsp-8+arg_10], rbx
0x180143ce5  mov     [rsp-8+arg_18], rsi
0x180143cea  push    rbp
0x180143ceb  push    rdi
0x180143cec  push    r12
0x180143cee  push    r14
0x180143cf0  push    r15
0x180143cf2  lea     rbp, [rsp-40h]
0x180143cf7  sub     rsp, 140h
0x180143cfe  mov     rax, cs:__security_cookie
0x180143d05  xor     rax, rsp
0x180143d08  mov     [rbp+60h+var_30], rax
0x180143d0c  mov     rdi, rdx
0x180143d0f  mov     r14, rcx
0x180143d12  xor     r12d, r12d
0x180143d15  mov     qword ptr [rsp+160h+var_100], r12
0x180143d1a  mov     rcx, [rcx+28h]
0x180143d1e  mov     rax, [rcx]
0x180143d21  mov     qword ptr [rsp+160h+var_100], r12
0x180143d26  lea     rdx, [rsp+160h+var_100]
0x180143d2b  mov     qword ptr [rsp+160h+var_140], rdx; int
0x180143d30  xor     r9d, r9d
0x180143d33  lea     r8d, [r12+17h]
0x180143d38  lea     rdx, _GUID_2b0711de_dab7_4610_a16f_d3383749b220
0x180143d3f  mov     rax, [rax+18h]
0x180143d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143d48  mov     ebx, eax
0x180143d4a  test    eax, eax
0x180143d4c  jns     short loc_180143D6B
0x180143d4e  mov     rcx, [rbp+68h]; this
0x180143d52  mov     r9d, eax; char *
0x180143d55  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143d5c  mov     edx, 23DCh; void *
0x180143d61  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143d66  jmp     loc_180144244
0x180143d6b  xorps   xmm0, xmm0
0x180143d6e  xor     eax, eax
0x180143d70  movups  xmmword ptr [rbp+60h+pvar], xmm0
0x180143d74  mov     [rbp+60h+var_D0], rax
0x180143d78  mov     rcx, [r14+48h]
0x180143d7c  mov     rax, [rcx]
0x180143d7f  lea     r8, [rbp+60h+pvar]
0x180143d83  lea     rdx, PKEY_Endpoint_HWAudioEngine_Offload_ConnectorId
0x180143d8a  mov     rax, [rax+28h]
0x180143d8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143d93  mov     ebx, eax
0x180143d95  test    eax, eax
0x180143d97  jns     short loc_180143DC1
0x180143d99  mov     r9d, eax; char *
0x180143d9c  mov     edx, 23E2h; void *
0x180143da1  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143da8  mov     rcx, [rbp+68h]; this
0x180143dac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143db1  nop
0x180143db2  lea     rcx, [rbp+60h+pvar]; pvar
0x180143db6  call    cs:__imp_PropVariantClear
0x180143dbc  jmp     loc_180144244
0x180143dc1  mov     eax, 13h
0x180143dc6  cmp     ax, word ptr [rbp+60h+pvar]
0x180143dca  jz      short loc_180143DDB
0x180143dcc  mov     ebx, 8000FFFFh
0x180143dd1  mov     r9d, ebx
0x180143dd4  mov     edx, 23E3h
0x180143dd9  jmp     short loc_180143DA1
0x180143ddb  mov     r15d, dword ptr [rbp+60h+pvar+8]
0x180143ddf  lea     rcx, [rbp+60h+pvar]; pvar
0x180143de3  call    cs:__imp_PropVariantClear
0x180143de9  mov     [rsp+160h+var_130], r12
0x180143dee  mov     [rbp+60h+var_C0], 233164C8h
0x180143df5  mov     [rbp+60h+var_BC], 4C7D1B2Ch
0x180143dfc  mov     [rbp+60h+var_B8], 71B668BCh
0x180143e03  mov     esi, 68h ; 'h'
0x180143e08  mov     [rbp+60h+var_B4], 67257A68h
0x180143e0f  mov     [rbp+60h+var_B0], 1
0x180143e16  xorps   xmm0, xmm0
0x180143e19  xor     eax, eax
0x180143e1b  movups  xmmword ptr [rsp+160h+var_F8], xmm0
0x180143e20  mov     [rsp+160h+var_E8], rax
0x180143e25  mov     rcx, [r14+48h]
0x180143e29  mov     rax, [rcx]
0x180143e2c  lea     r8, [rsp+160h+var_F8]
0x180143e31  lea     rdx, [rbp+60h+var_C0]
0x180143e35  mov     rax, [rax+28h]
0x180143e39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143e3e  mov     ebx, eax
0x180143e40  test    eax, eax
0x180143e42  jns     short loc_180143E78
0x180143e44  mov     edx, 23EDh; void *
0x180143e49  mov     r9d, eax; char *
0x180143e4c  mov     rcx, [rbp+68h]; this
0x180143e50  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143e57  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143e5c  nop
0x180143e5d  lea     rcx, [rsp+160h+var_F8]; pvar
0x180143e62  call    cs:__imp_PropVariantClear
0x180143e68  nop
0x180143e69  lea     rcx, [rsp+160h+var_130]
0x180143e6e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180143e73  jmp     loc_180144244
0x180143e78  mov     eax, 1Fh
0x180143e7d  cmp     ax, word ptr [rsp+160h+var_F8]
0x180143e82  jz      short loc_180143E93
0x180143e84  mov     ebx, 8000FFFFh
0x180143e89  mov     r9d, ebx
0x180143e8c  mov     edx, 23EEh
0x180143e91  jmp     short loc_180143E4C
0x180143e93  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180143e9a  mov     rcx, [rax]
0x180143e9d  mov     rbx, [rcx+28h]
0x180143ea1  lea     rcx, [rsp+160h+var_130]
0x180143ea6  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x180143eab  lea     r8, [rsp+160h+var_130]
0x180143eb0  mov     rdx, [rsp+160h+var_F8+8]
0x180143eb5  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x180143ebc  mov     rax, rbx
0x180143ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143ec4  mov     ebx, eax
0x180143ec6  test    eax, eax
0x180143ec8  jns     short loc_180143ED4
0x180143eca  mov     edx, 23F1h
0x180143ecf  jmp     loc_180143E49
0x180143ed4  lea     rcx, [rsp+160h+var_F8]; pvar
0x180143ed9  call    cs:__imp_PropVariantClear
0x180143edf  mov     qword ptr [rsp+160h+var_120], r12
0x180143ee4  mov     rcx, [rsp+160h+var_130]
0x180143ee9  mov     rax, [rcx]
0x180143eec  mov     qword ptr [rsp+160h+var_120], r12
0x180143ef1  lea     rdx, [rsp+160h+var_120]
0x180143ef6  mov     qword ptr [rsp+160h+var_140], rdx; int
0x180143efb  xor     r9d, r9d
0x180143efe  lea     r8d, [r9+1]
0x180143f02  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x180143f09  mov     rax, [rax+18h]
0x180143f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143f12  mov     ebx, eax
0x180143f14  test    eax, eax
0x180143f16  jns     short loc_180143F40
0x180143f18  mov     rcx, [rbp+68h]; this
0x180143f1c  mov     r9d, eax; char *
0x180143f1f  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143f26  mov     edx, 23F6h; void *
0x180143f2b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143f30  nop
0x180143f31  lea     rcx, [rsp+160h+var_120]
0x180143f36  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180143f3b  jmp     loc_180143E69
0x180143f40  mov     [rsp+160h+var_128], r12
0x180143f45  mov     rcx, qword ptr [rsp+160h+var_120]
0x180143f4a  mov     rax, [rcx]
0x180143f4d  mov     [rsp+160h+var_128], r12
0x180143f52  lea     r8, [rsp+160h+var_128]
0x180143f57  mov     edx, r15d
0x180143f5a  mov     rax, [rax+38h]
0x180143f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143f63  mov     ebx, eax
0x180143f65  test    eax, eax
0x180143f67  jns     short loc_180143F8E
0x180143f69  mov     rcx, [rbp+68h]; this
0x180143f6d  mov     r9d, eax; char *
0x180143f70  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143f77  mov     edx, 23FAh; void *
0x180143f7c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143f81  nop
0x180143f82  lea     rcx, [rsp+160h+var_128]
0x180143f87  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180143f8c  jmp     short loc_180143F31
0x180143f8e  mov     [rsp+160h+var_118], r12
0x180143f93  mov     rcx, [rsp+160h+var_128]
0x180143f98  mov     rax, [rcx]
0x180143f9b  lea     r8, [rsp+160h+var_118]
0x180143fa0  lea     rdx, _GUID_9c2c4058_23f5_41de_877a_df3af236a09e
0x180143fa7  mov     rax, [rax]
0x180143faa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143faf  mov     ebx, eax
0x180143fb1  test    eax, eax
0x180143fb3  jns     short loc_180143FDA
0x180143fb5  mov     edx, 23FDh; void *
0x180143fba  mov     r9d, eax; char *
0x180143fbd  mov     rcx, [rbp+68h]; this
0x180143fc1  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143fc8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143fcd  nop
0x180143fce  lea     rcx, [rsp+160h+var_118]
0x180143fd3  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180143fd8  jmp     short loc_180143F82
0x180143fda  mov     [rsp+160h+var_108], r12d
0x180143fdf  mov     rcx, [rsp+160h+var_118]
0x180143fe4  mov     rax, [rcx]
0x180143fe7  lea     rdx, [rsp+160h+var_108]
0x180143fec  mov     rax, [rax+18h]
0x180143ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143ff5  mov     ebx, eax
0x180143ff7  test    eax, eax
0x180143ff9  jns     short loc_180144002
0x180143ffb  mov     edx, 2401h
0x180144000  jmp     short loc_180143FBA
0x180144002  cmp     [rsp+160h+var_108], 3
0x180144007  jz      short loc_180144018
0x180144009  mov     ebx, 8000FFFFh
0x18014400e  mov     r9d, ebx
0x180144011  mov     edx, 2402h
0x180144016  jmp     short loc_180143FBD
0x180144018  mov     [rsp+160h+var_110], r12
0x18014401d  mov     rcx, [rsp+160h+var_128]
0x180144022  mov     rax, [rcx]
0x180144025  mov     [rsp+160h+var_110], r12
0x18014402a  lea     r9, [rsp+160h+var_110]
0x18014402f  lea     r8, _GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5
0x180144036  mov     edx, 1
0x18014403b  mov     rax, [rax+68h]
0x18014403f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144044  mov     ebx, eax
0x180144046  test    eax, eax
0x180144048  jns     short loc_180144072
0x18014404a  mov     rcx, [rbp+68h]; this
0x18014404e  mov     r9d, eax; char *
0x180144051  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x180144058  mov     edx, 2406h; void *
0x18014405d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180144062  nop
0x180144063  lea     rcx, [rsp+160h+var_110]
0x180144068  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18014406d  jmp     loc_180143FCE
0x180144072  mov     [rbp+60h+var_C8], r12
0x180144076  test    rdi, rdi
0x180144079  jnz     short loc_180144082
0x18014407b  mov     ebx, 80004003h
0x180144080  jmp     short loc_1801440BB
0x180144082  mov     r14d, 0FFFEh
0x180144088  cmp     r14w, [rdi]
0x18014408c  jnz     short loc_18014409C
0x18014408e  cmp     word ptr [rdi+10h], 16h
0x180144093  jnb     short loc_18014409C
0x180144095  mov     ebx, 80070057h
0x18014409a  jmp     short loc_1801440BB
0x18014409c  movzx   ecx, word ptr [rdi+10h]
0x1801440a0  add     rcx, 52h ; 'R'; cb
0x1801440a4  call    cs:__imp_CoTaskMemAlloc
0x1801440aa  mov     rbx, rax
0x1801440ad  mov     [rbp+60h+var_C8], rax
0x1801440b1  test    rax, rax
0x1801440b4  jnz     short loc_1801440D6
0x1801440b6  mov     ebx, 8007000Eh
0x1801440bb  mov     rcx, [rbp+68h]; this
0x1801440bf  mov     r9d, ebx; char *
0x1801440c2  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
0x1801440c9  mov     edx, 2410h; void *
0x1801440ce  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801440d3  nop
0x1801440d4  jmp     short loc_180144063
0x1801440d6  movzx   eax, word ptr [rdi+10h]
0x1801440da  add     eax, 52h ; 'R'
0x1801440dd  mov     [rbx], eax
0x1801440df  mov     [rbx+4], r12
0x1801440e3  mov     [rbx+0Ch], r12d
0x1801440e7  movups  xmm0, xmmword ptr cs:_GUID_73647561_0000_0010_8000_00aa00389b71.Data1
0x1801440ee  movdqu  xmmword ptr [rbx+10h], xmm0
0x1801440f3  movups  xmm1, xmmword ptr cs:_GUID_05589f81_c356_11ce_bf01_00aa0055595a.Data1
0x1801440fa  movdqu  xmmword ptr [rbx+30h], xmm1
0x1801440ff  movzx   r8d, word ptr [rdi+10h]
0x180144104  add     r8, 12h; Size
0x180144108  lea     rcx, [rbx+40h]; void *
0x18014410c  mov     rdx, rdi; Src
0x18014410f  call    memcpy_0
0x180144114  cmp     r14w, [rdi]
0x180144118  jnz     short loc_180144125
0x18014411a  movups  xmm0, xmmword ptr [rdi+18h]
0x18014411e  movdqu  xmmword ptr [rbx+20h], xmm0
0x180144123  jmp     short loc_180144137
0x180144125  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data1
0x18014412c  movdqu  xmmword ptr [rbx+20h], xmm0
0x180144131  movzx   eax, word ptr [rdi]
0x180144134  mov     [rbx+20h], eax
0x180144137  mov     rdi, rbx
0x18014413a  mov     r8, rsi; Size
0x18014413d  xor     edx, edx; Val
0x18014413f  lea     rcx, [rbp+60h+var_A0]; void *
0x180144143  call    memset_0
0x180144148  mov     rdx, rbx; Src
0x18014414b  cmp     [rbx], esi
0x18014414d  jnb     short loc_180144161
0x18014414f  mov     r8d, [rbx]; Size
0x180144152  lea     rcx, [rbp+60h+var_A0]; void *
0x180144156  call    memcpy_0
0x18014415b  lea     rdx, [rbp+60h+var_A0]
0x18014415f  jmp     short loc_180144163
0x180144161  mov     esi, [rbx]
0x180144163  mov     [rsp+160h+var_104], r12d
0x180144168  mov     rcx, [rsp+160h+var_110]
0x18014416d  mov     rax, [rcx]
0x180144170  lea     r9, [rsp+160h+var_104]
0x180144175  mov     r8d, esi
0x180144178  mov     rax, [rax+18h]
0x18014417c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180144181  mov     ebx, eax
0x180144183  test    eax, eax
0x180144185  jns     short loc_1801441AE
0x180144187  mov     rcx, [rbp+68h]; this
0x18014418b  mov     r9d, eax; char *
0x18014418e  lea     r8, aAvcoreAudiocor_53; "avcore\\audiocore\\server\\lib\\audiose"...
  ... truncated ...
```
