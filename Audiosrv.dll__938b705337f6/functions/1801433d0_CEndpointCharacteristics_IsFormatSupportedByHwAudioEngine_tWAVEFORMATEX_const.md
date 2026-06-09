# CEndpointCharacteristics::IsFormatSupportedByHwAudioEngine(tWAVEFORMATEX const *)

- ea: `0x1801433d0`
- end: `0x180143968`
- name: `?IsFormatSupportedByHwAudioEngine@CEndpointCharacteristics@@QEAAJPEBUtWAVEFORMATEX@@@Z`
- size: `1432`
- prototype: `int(CEndpointCharacteristics *__hidden this, const struct tWAVEFORMATEX *)`
- caller_count: `2`
- callee_count: `8`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e1b8`
- `0x1800b139c`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x1800423cc`
- `0x1800cf8c0`
- `0x1800d074c`
- `0x1800d0764`
- `0x1801433d0`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801434a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801434d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180143552`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801435c9`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801434a6`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801434d3`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180143552`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1801435c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180143794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180143794`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180143893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801438a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801438f4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180143893`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801438a8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801438f4`

## string_xrefs

- `0x180143445`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180143491`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180143540`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18014360f`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180143660`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1801436b1`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x180143741`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x1801437b2`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`
- `0x18014387e`: `avcore\audiocore\server\lib\audioserviceutil\endpointcharacteristics.cpp`

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
  __int64 v13; // r9
  HRESULT (__stdcall *GetDevice)(IMMDeviceEnumerator *, LPCWSTR, IMMDevice **); // rbx
  __int64 v15; // rax
  int v16; // eax
  __int64 v17; // rax
  int v18; // eax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // r9
  __int64 (__fastcall **v22)(_QWORD, _QWORD, _QWORD); // rax
  int v23; // eax
  unsigned int *v24; // rbx
  void *v25; // rdi
  _BYTE *v26; // rdx
  int v27; // eax
  __int64 *v29; // [rsp+30h] [rbp-D0h] BYREF
  __int64 (__fastcall ***v30)(_QWORD, GUID *, __int64 *); // [rsp+38h] [rbp-C8h] BYREF
  int v31[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v32; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v33; // [rsp+50h] [rbp-B0h] BYREF
  int v34; // [rsp+58h] [rbp-A8h] BYREF
  int v35; // [rsp+5Ch] [rbp-A4h] BYREF
  int v36[2]; // [rsp+60h] [rbp-A0h] BYREF
  PROPVARIANT v37[2]; // [rsp+68h] [rbp-98h] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h]
  PROPVARIANT pvar[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v40; // [rsp+90h] [rbp-70h]
  unsigned int *v41; // [rsp+98h] [rbp-68h]
  _DWORD v42[8]; // [rsp+A0h] [rbp-60h] BYREF
  _BYTE v43[112]; // [rsp+C0h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+168h] [rbp+68h]

  *(_QWORD *)v36 = 0;
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
      (void *)0x23DD,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v4,
      (int)v36);
    goto LABEL_54;
  }
  *(_OWORD *)pvar = 0;
  v40 = 0;
  v6 = (*(__int64 (__fastcall **)(_QWORD, const struct _tagpropertykey *, PROPVARIANT *))(**((_QWORD **)this + 9) + 40LL))(
         *((_QWORD *)this + 9),
         &PKEY_Endpoint_HWAudioEngine_Offload_ConnectorId,
         pvar);
  v5 = v6;
  if ( v6 < 0 )
  {
    v7 = (unsigned int)v6;
    v8 = 9187;
LABEL_5:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v7,
      (int)v36);
    PropVariantClear(pvar);
    goto LABEL_54;
  }
  if ( LOWORD(pvar[0]) != 19 )
  {
    v5 = -2147418113;
    v7 = 2147549183LL;
    v8 = 9188;
    goto LABEL_5;
  }
  v9 = (unsigned int)pvar[1];
  PropVariantClear(pvar);
  v29 = 0;
  v42[0] = 590439624;
  v42[1] = 1283267372;
  v42[2] = 1907779772;
  v10 = 104;
  v42[3] = 1730509416;
  v42[4] = 1;
  *(_OWORD *)v37 = 0;
  v38 = 0;
  v11 = (*(__int64 (__fastcall **)(_QWORD, _DWORD *, PROPVARIANT *))(**((_QWORD **)this + 9) + 40LL))(
          *((_QWORD *)this + 9),
          v42,
          v37);
  v5 = v11;
  if ( v11 < 0 )
  {
    v12 = 9198;
LABEL_10:
    v13 = (unsigned int)v11;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v13,
      (int)v36);
    PropVariantClear(v37);
LABEL_12:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
    goto LABEL_54;
  }
  if ( LOWORD(v37[0]) != 31 )
  {
    v5 = -2147418113;
    v13 = 2147549183LL;
    v12 = 9199;
    goto LABEL_11;
  }
  GetDevice = g_DeviceEnumerator->lpVtbl->GetDevice;
  wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(&v29);
  v11 = ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, PROPVARIANT, __int64 **))GetDevice)(
          g_DeviceEnumerator,
          v37[1],
          &v29);
  v5 = v11;
  if ( v11 < 0 )
  {
    v12 = 9202;
    goto LABEL_10;
  }
  PropVariantClear(v37);
  *(_QWORD *)v31 = 0;
  v15 = *v29;
  *(_QWORD *)v31 = 0;
  v16 = (*(__int64 (__fastcall **)(__int64 *, GUID *, __int64))(v15 + 24))(
          v29,
          &GUID_2a07407e_6497_4a18_9787_32f79bd0d98f,
          1);
  v5 = v16;
  if ( v16 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23F7,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v16,
      (int)v31);
LABEL_19:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v31);
    goto LABEL_12;
  }
  v30 = 0;
  v17 = **(_QWORD **)v31;
  v30 = 0;
  v18 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))(v17 + 56))(*(_QWORD *)v31, v9, &v30);
  v5 = v18;
  if ( v18 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23FB,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v18,
      (int)v31);
LABEL_22:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v30);
    goto LABEL_19;
  }
  v32 = 0;
  v19 = (**v30)(v30, &GUID_9c2c4058_23f5_41de_877a_df3af236a09e, &v32);
  v5 = v19;
  if ( v19 < 0 )
  {
    v20 = 9214;
LABEL_25:
    v21 = (unsigned int)v19;
LABEL_26:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v21,
      (int)v31);
LABEL_27:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v32);
    goto LABEL_22;
  }
  v34 = 0;
  v19 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v32 + 24LL))(v32, &v34);
  v5 = v19;
  if ( v19 < 0 )
  {
    v20 = 9218;
    goto LABEL_25;
  }
  if ( v34 != 3 )
  {
    v5 = -2147418113;
    v21 = 2147549183LL;
    v20 = 9219;
    goto LABEL_26;
  }
  v33 = 0;
  v22 = (__int64 (__fastcall **)(_QWORD, _QWORD, _QWORD))*v30;
  v33 = 0;
  v23 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), __int64, GUID *, __int64 *))v22[13])(
          v30,
          1,
          &GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5,
          &v33);
  v5 = v23;
  if ( v23 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2407,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v23,
      (int)v31);
LABEL_34:
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
    goto LABEL_27;
  }
  v41 = 0;
  if ( !a2 )
  {
    v5 = -2147467261;
LABEL_42:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2411,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)v5,
      (int)v31);
    goto LABEL_34;
  }
  if ( a2->wFormatTag == 0xFFFE && a2->cbSize < 0x16u )
  {
    v5 = -2147024809;
    goto LABEL_42;
  }
  v24 = (unsigned int *)CoTaskMemAlloc(a2->cbSize + 82LL);
  v41 = v24;
  if ( !v24 )
  {
    v5 = -2147024882;
    goto LABEL_42;
  }
  *v24 = a2->cbSize + 82;
  *(_QWORD *)(v24 + 1) = 0;
  v24[3] = 0;
  *((GUID *)v24 + 1) = GUID_73647561_0000_0010_8000_00aa00389b71;
  *((GUID *)v24 + 3) = GUID_05589f81_c356_11ce_bf01_00aa0055595a;
  memcpy_0(v24 + 16, a2, a2->cbSize + 18LL);
  if ( a2->wFormatTag == 0xFFFE )
  {
    *((_OWORD *)v24 + 2) = *(_OWORD *)((char *)&a2[1].nSamplesPerSec + 2);
  }
  else
  {
    *((GUID *)v24 + 2) = GUID_00000000_0000_0010_8000_00aa00389b71;
    v24[8] = a2->wFormatTag;
  }
  v25 = v24;
  memset_0(v43, 0, 0x68u);
  v26 = v24;
  if ( *v24 >= 0x68 )
  {
    v10 = *v24;
  }
  else
  {
    memcpy_0(v43, v24, *v24);
    v26 = v43;
  }
  v35 = 0;
  v27 = (*(__int64 (__fastcall **)(__int64, _BYTE *, _QWORD, int *))(*(_QWORD *)v33 + 24LL))(v33, v26, v10, &v35);
  v5 = v27;
  if ( v27 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2423,
      (unsigned int)"avcore\\audiocore\\server\\lib\\audioserviceutil\\endpointcharacteristics.cpp",
      (const char *)(unsigned int)v27,
      (int)v31);
    CoTaskMemFree(v25);
    goto LABEL_34;
  }
  if ( v35 )
  {
    CoTaskMemFree(v25);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v32);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v30);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v31);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
    v5 = 0;
  }
  else
  {
    CoTaskMemFree(v25);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v32);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v30);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v31);
    wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v29);
    v5 = -2005139333;
  }
LABEL_54:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(v36);
  return v5;
}

```

## disassembly

```asm
0x1801433d0  mov     [rsp-8+arg_10], rbx
0x1801433d5  mov     [rsp-8+arg_18], rsi
0x1801433da  push    rbp
0x1801433db  push    rdi
0x1801433dc  push    r12
0x1801433de  push    r14
0x1801433e0  push    r15
0x1801433e2  lea     rbp, [rsp-40h]
0x1801433e7  sub     rsp, 140h
0x1801433ee  mov     rax, cs:__security_cookie
0x1801433f5  xor     rax, rsp
0x1801433f8  mov     [rbp+60h+var_30], rax
0x1801433fc  mov     rdi, rdx
0x1801433ff  mov     r14, rcx
0x180143402  xor     r12d, r12d
0x180143405  mov     qword ptr [rsp+160h+var_100], r12
0x18014340a  mov     rcx, [rcx+28h]
0x18014340e  mov     rax, [rcx]
0x180143411  mov     qword ptr [rsp+160h+var_100], r12
0x180143416  lea     rdx, [rsp+160h+var_100]
0x18014341b  mov     qword ptr [rsp+160h+var_140], rdx; int
0x180143420  xor     r9d, r9d
0x180143423  lea     r8d, [r12+17h]
0x180143428  lea     rdx, _GUID_2b0711de_dab7_4610_a16f_d3383749b220
0x18014342f  mov     rax, [rax+18h]
0x180143433  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143438  mov     ebx, eax
0x18014343a  test    eax, eax
0x18014343c  jns     short loc_18014345B
0x18014343e  mov     rcx, [rbp+68h]; this
0x180143442  mov     r9d, eax; char *
0x180143445  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x18014344c  mov     edx, 23DDh; void *
0x180143451  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143456  jmp     loc_180143934
0x18014345b  xorps   xmm0, xmm0
0x18014345e  xor     eax, eax
0x180143460  movups  xmmword ptr [rbp+60h+pvar], xmm0
0x180143464  mov     [rbp+60h+var_D0], rax
0x180143468  mov     rcx, [r14+48h]
0x18014346c  mov     rax, [rcx]
0x18014346f  lea     r8, [rbp+60h+pvar]
0x180143473  lea     rdx, PKEY_Endpoint_HWAudioEngine_Offload_ConnectorId
0x18014347a  mov     rax, [rax+28h]
0x18014347e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143483  mov     ebx, eax
0x180143485  test    eax, eax
0x180143487  jns     short loc_1801434B1
0x180143489  mov     r9d, eax; char *
0x18014348c  mov     edx, 23E3h; void *
0x180143491  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143498  mov     rcx, [rbp+68h]; this
0x18014349c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801434a1  nop
0x1801434a2  lea     rcx, [rbp+60h+pvar]; pvar
0x1801434a6  call    cs:__imp_PropVariantClear
0x1801434ac  jmp     loc_180143934
0x1801434b1  mov     eax, 13h
0x1801434b6  cmp     ax, word ptr [rbp+60h+pvar]
0x1801434ba  jz      short loc_1801434CB
0x1801434bc  mov     ebx, 8000FFFFh
0x1801434c1  mov     r9d, ebx
0x1801434c4  mov     edx, 23E4h
0x1801434c9  jmp     short loc_180143491
0x1801434cb  mov     r15d, dword ptr [rbp+60h+pvar+8]
0x1801434cf  lea     rcx, [rbp+60h+pvar]; pvar
0x1801434d3  call    cs:__imp_PropVariantClear
0x1801434d9  mov     [rsp+160h+var_130], r12
0x1801434de  mov     [rbp+60h+var_C0], 233164C8h
0x1801434e5  mov     [rbp+60h+var_BC], 4C7D1B2Ch
0x1801434ec  mov     [rbp+60h+var_B8], 71B668BCh
0x1801434f3  mov     esi, 68h ; 'h'
0x1801434f8  mov     [rbp+60h+var_B4], 67257A68h
0x1801434ff  mov     [rbp+60h+var_B0], 1
0x180143506  xorps   xmm0, xmm0
0x180143509  xor     eax, eax
0x18014350b  movups  xmmword ptr [rsp+160h+var_F8], xmm0
0x180143510  mov     [rsp+160h+var_E8], rax
0x180143515  mov     rcx, [r14+48h]
0x180143519  mov     rax, [rcx]
0x18014351c  lea     r8, [rsp+160h+var_F8]
0x180143521  lea     rdx, [rbp+60h+var_C0]
0x180143525  mov     rax, [rax+28h]
0x180143529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014352e  mov     ebx, eax
0x180143530  test    eax, eax
0x180143532  jns     short loc_180143568
0x180143534  mov     edx, 23EEh; void *
0x180143539  mov     r9d, eax; char *
0x18014353c  mov     rcx, [rbp+68h]; this
0x180143540  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143547  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18014354c  nop
0x18014354d  lea     rcx, [rsp+160h+var_F8]; pvar
0x180143552  call    cs:__imp_PropVariantClear
0x180143558  nop
0x180143559  lea     rcx, [rsp+160h+var_130]
0x18014355e  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180143563  jmp     loc_180143934
0x180143568  mov     eax, 1Fh
0x18014356d  cmp     ax, word ptr [rsp+160h+var_F8]
0x180143572  jz      short loc_180143583
0x180143574  mov     ebx, 8000FFFFh
0x180143579  mov     r9d, ebx
0x18014357c  mov     edx, 23EFh
0x180143581  jmp     short loc_18014353C
0x180143583  mov     rax, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18014358a  mov     rcx, [rax]
0x18014358d  mov     rbx, [rcx+28h]
0x180143591  lea     rcx, [rsp+160h+var_130]
0x180143596  call    ?reset@?$com_ptr_t@UIMMDevice@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IMMDevice,wil::err_returncode_policy>::reset(void)
0x18014359b  lea     r8, [rsp+160h+var_130]
0x1801435a0  mov     rdx, [rsp+160h+var_F8+8]
0x1801435a5  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x1801435ac  mov     rax, rbx
0x1801435af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801435b4  mov     ebx, eax
0x1801435b6  test    eax, eax
0x1801435b8  jns     short loc_1801435C4
0x1801435ba  mov     edx, 23F2h
0x1801435bf  jmp     loc_180143539
0x1801435c4  lea     rcx, [rsp+160h+var_F8]; pvar
0x1801435c9  call    cs:__imp_PropVariantClear
0x1801435cf  mov     qword ptr [rsp+160h+var_120], r12
0x1801435d4  mov     rcx, [rsp+160h+var_130]
0x1801435d9  mov     rax, [rcx]
0x1801435dc  mov     qword ptr [rsp+160h+var_120], r12
0x1801435e1  lea     rdx, [rsp+160h+var_120]
0x1801435e6  mov     qword ptr [rsp+160h+var_140], rdx; int
0x1801435eb  xor     r9d, r9d
0x1801435ee  lea     r8d, [r9+1]
0x1801435f2  lea     rdx, _GUID_2a07407e_6497_4a18_9787_32f79bd0d98f
0x1801435f9  mov     rax, [rax+18h]
0x1801435fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143602  mov     ebx, eax
0x180143604  test    eax, eax
0x180143606  jns     short loc_180143630
0x180143608  mov     rcx, [rbp+68h]; this
0x18014360c  mov     r9d, eax; char *
0x18014360f  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143616  mov     edx, 23F7h; void *
0x18014361b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143620  nop
0x180143621  lea     rcx, [rsp+160h+var_120]
0x180143626  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18014362b  jmp     loc_180143559
0x180143630  mov     [rsp+160h+var_128], r12
0x180143635  mov     rcx, qword ptr [rsp+160h+var_120]
0x18014363a  mov     rax, [rcx]
0x18014363d  mov     [rsp+160h+var_128], r12
0x180143642  lea     r8, [rsp+160h+var_128]
0x180143647  mov     edx, r15d
0x18014364a  mov     rax, [rax+38h]
0x18014364e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143653  mov     ebx, eax
0x180143655  test    eax, eax
0x180143657  jns     short loc_18014367E
0x180143659  mov     rcx, [rbp+68h]; this
0x18014365d  mov     r9d, eax; char *
0x180143660  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143667  mov     edx, 23FBh; void *
0x18014366c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143671  nop
0x180143672  lea     rcx, [rsp+160h+var_128]
0x180143677  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18014367c  jmp     short loc_180143621
0x18014367e  mov     [rsp+160h+var_118], r12
0x180143683  mov     rcx, [rsp+160h+var_128]
0x180143688  mov     rax, [rcx]
0x18014368b  lea     r8, [rsp+160h+var_118]
0x180143690  lea     rdx, _GUID_9c2c4058_23f5_41de_877a_df3af236a09e
0x180143697  mov     rax, [rax]
0x18014369a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014369f  mov     ebx, eax
0x1801436a1  test    eax, eax
0x1801436a3  jns     short loc_1801436CA
0x1801436a5  mov     edx, 23FEh; void *
0x1801436aa  mov     r9d, eax; char *
0x1801436ad  mov     rcx, [rbp+68h]; this
0x1801436b1  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x1801436b8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801436bd  nop
0x1801436be  lea     rcx, [rsp+160h+var_118]
0x1801436c3  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x1801436c8  jmp     short loc_180143672
0x1801436ca  mov     [rsp+160h+var_108], r12d
0x1801436cf  mov     rcx, [rsp+160h+var_118]
0x1801436d4  mov     rax, [rcx]
0x1801436d7  lea     rdx, [rsp+160h+var_108]
0x1801436dc  mov     rax, [rax+18h]
0x1801436e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801436e5  mov     ebx, eax
0x1801436e7  test    eax, eax
0x1801436e9  jns     short loc_1801436F2
0x1801436eb  mov     edx, 2402h
0x1801436f0  jmp     short loc_1801436AA
0x1801436f2  cmp     [rsp+160h+var_108], 3
0x1801436f7  jz      short loc_180143708
0x1801436f9  mov     ebx, 8000FFFFh
0x1801436fe  mov     r9d, ebx
0x180143701  mov     edx, 2403h
0x180143706  jmp     short loc_1801436AD
0x180143708  mov     [rsp+160h+var_110], r12
0x18014370d  mov     rcx, [rsp+160h+var_128]
0x180143712  mov     rax, [rcx]
0x180143715  mov     [rsp+160h+var_110], r12
0x18014371a  lea     r9, [rsp+160h+var_110]
0x18014371f  lea     r8, _GUID_3cb4a69d_bb6f_4d2b_95b7_452d2c155db5
0x180143726  mov     edx, 1
0x18014372b  mov     rax, [rax+68h]
0x18014372f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143734  mov     ebx, eax
0x180143736  test    eax, eax
0x180143738  jns     short loc_180143762
0x18014373a  mov     rcx, [rbp+68h]; this
0x18014373e  mov     r9d, eax; char *
0x180143741  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x180143748  mov     edx, 2407h; void *
0x18014374d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180143752  nop
0x180143753  lea     rcx, [rsp+160h+var_110]
0x180143758  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x18014375d  jmp     loc_1801436BE
0x180143762  mov     [rbp+60h+var_C8], r12
0x180143766  test    rdi, rdi
0x180143769  jnz     short loc_180143772
0x18014376b  mov     ebx, 80004003h
0x180143770  jmp     short loc_1801437AB
0x180143772  mov     r14d, 0FFFEh
0x180143778  cmp     r14w, [rdi]
0x18014377c  jnz     short loc_18014378C
0x18014377e  cmp     word ptr [rdi+10h], 16h
0x180143783  jnb     short loc_18014378C
0x180143785  mov     ebx, 80070057h
0x18014378a  jmp     short loc_1801437AB
0x18014378c  movzx   ecx, word ptr [rdi+10h]
0x180143790  add     rcx, 52h ; 'R'; cb
0x180143794  call    cs:__imp_CoTaskMemAlloc
0x18014379a  mov     rbx, rax
0x18014379d  mov     [rbp+60h+var_C8], rax
0x1801437a1  test    rax, rax
0x1801437a4  jnz     short loc_1801437C6
0x1801437a6  mov     ebx, 8007000Eh
0x1801437ab  mov     rcx, [rbp+68h]; this
0x1801437af  mov     r9d, ebx; char *
0x1801437b2  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
0x1801437b9  mov     edx, 2411h; void *
0x1801437be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801437c3  nop
0x1801437c4  jmp     short loc_180143753
0x1801437c6  movzx   eax, word ptr [rdi+10h]
0x1801437ca  add     eax, 52h ; 'R'
0x1801437cd  mov     [rbx], eax
0x1801437cf  mov     [rbx+4], r12
0x1801437d3  mov     [rbx+0Ch], r12d
0x1801437d7  movups  xmm0, xmmword ptr cs:_GUID_73647561_0000_0010_8000_00aa00389b71.Data1
0x1801437de  movdqu  xmmword ptr [rbx+10h], xmm0
0x1801437e3  movups  xmm1, xmmword ptr cs:_GUID_05589f81_c356_11ce_bf01_00aa0055595a.Data1
0x1801437ea  movdqu  xmmword ptr [rbx+30h], xmm1
0x1801437ef  movzx   r8d, word ptr [rdi+10h]
0x1801437f4  add     r8, 12h; Size
0x1801437f8  lea     rcx, [rbx+40h]; void *
0x1801437fc  mov     rdx, rdi; Src
0x1801437ff  call    memcpy_0
0x180143804  cmp     r14w, [rdi]
0x180143808  jnz     short loc_180143815
0x18014380a  movups  xmm0, xmmword ptr [rdi+18h]
0x18014380e  movdqu  xmmword ptr [rbx+20h], xmm0
0x180143813  jmp     short loc_180143827
0x180143815  movups  xmm0, xmmword ptr cs:_GUID_00000000_0000_0010_8000_00aa00389b71.Data1
0x18014381c  movdqu  xmmword ptr [rbx+20h], xmm0
0x180143821  movzx   eax, word ptr [rdi]
0x180143824  mov     [rbx+20h], eax
0x180143827  mov     rdi, rbx
0x18014382a  mov     r8, rsi; Size
0x18014382d  xor     edx, edx; Val
0x18014382f  lea     rcx, [rbp+60h+var_A0]; void *
0x180143833  call    memset_0
0x180143838  mov     rdx, rbx; Src
0x18014383b  cmp     [rbx], esi
0x18014383d  jnb     short loc_180143851
0x18014383f  mov     r8d, [rbx]; Size
0x180143842  lea     rcx, [rbp+60h+var_A0]; void *
0x180143846  call    memcpy_0
0x18014384b  lea     rdx, [rbp+60h+var_A0]
0x18014384f  jmp     short loc_180143853
0x180143851  mov     esi, [rbx]
0x180143853  mov     [rsp+160h+var_104], r12d
0x180143858  mov     rcx, [rsp+160h+var_110]
0x18014385d  mov     rax, [rcx]
0x180143860  lea     r9, [rsp+160h+var_104]
0x180143865  mov     r8d, esi
0x180143868  mov     rax, [rax+18h]
0x18014386c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180143871  mov     ebx, eax
0x180143873  test    eax, eax
0x180143875  jns     short loc_18014389E
0x180143877  mov     rcx, [rbp+68h]; this
0x18014387b  mov     r9d, eax; char *
0x18014387e  lea     r8, aAvcoreAudiocor_52; "avcore\\audiocore\\server\\lib\\audiose"...
  ... truncated ...
```
