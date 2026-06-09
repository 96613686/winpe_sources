# GeolocPlugin::ParseSignal(Microsoft::WRL::ComPtr<IXMLDOMNode>,__int64,std::unique_ptr<GenericPlugin::Signal,std::default_delete<GenericPlugin::Signal>> *,NA_XML_PARSE_ERROR_DETAILS *)

- ea: `0x18003f2b0`
- end: `0x18003f565`
- name: `?ParseSignal@GeolocPlugin@@UEAAJV?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@_JPEAV?$unique_ptr@VSignal@GenericPlugin@@U?$default_delete@VSignal@GenericPlugin@@@std@@@std@@PEAUNA_XML_PARSE_ERROR_DETAILS@@@Z`
- size: `693`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x18000459c`
- `0x18000b7b8`
- `0x180012b0c`
- `0x180014e7c`
- `0x180021df4`
- `0x180029fdc`
- `0x18003e118`
- `0x18003e5b0`
- `0x18003f2b0`
- `0x180046010`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18003f481`
- `OLEAUT32!__imp_VariantInit` at `0x18003f481`
- `OLEAUT32!__imp_VariantClear` at `0x18003f49e`
- `OLEAUT32!__imp_VariantClear` at `0x18003f4f5`
- `OLEAUT32!__imp_VariantClear` at `0x18003f50a`
- `OLEAUT32!__imp_VariantClear` at `0x18003f51f`
- `OLEAUT32!__imp_VariantClear` at `0x18003f49e`
- `OLEAUT32!__imp_VariantClear` at `0x18003f4f5`
- `OLEAUT32!__imp_VariantClear` at `0x18003f50a`
- `OLEAUT32!__imp_VariantClear` at `0x18003f51f`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall GeolocPlugin::ParseSignal(
        float a1,
        __int64 (__fastcall ***a2)(_QWORD, __int64),
        __int64 a3,
        GeolocSignal **a4)
{
  __int64 (__fastcall **v7)(_QWORD, __int64); // rdi
  __int64 (__fastcall *v8)(_QWORD, __int64 *); // rbx
  int v9; // eax
  __int64 v10; // rdi
  __int64 (__fastcall *v11)(__int64, const wchar_t *, __int64 *); // rbx
  int v12; // eax
  int v13; // eax
  __int64 v14; // rdi
  __int64 (__fastcall *v15)(__int64, const wchar_t *, __int64 *); // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rdi
  __int64 (__fastcall *v19)(__int64, const wchar_t *, __int64 *); // rbx
  int v20; // eax
  int v21; // eax
  GeolocSignal *v22; // rbx
  LONG lVal; // edi
  GeolocSignal *v24; // rax
  __int64 v25; // rcx
  GeolocSignal *v26; // rdx
  __int64 v28; // [rsp+38h] [rbp-71h] BYREF
  __int64 v29; // [rsp+40h] [rbp-69h] BYREF
  __int64 v30; // [rsp+48h] [rbp-61h] BYREF
  __int64 v31; // [rsp+50h] [rbp-59h] BYREF
  VARIANTARG v32; // [rsp+58h] [rbp-51h] BYREF
  VARIANTARG v33; // [rsp+70h] [rbp-39h] BYREF
  VARIANTARG v34; // [rsp+88h] [rbp-21h] BYREF
  VARIANTARG pvarg; // [rsp+A0h] [rbp-9h] BYREF
  GeolocSignal *v36; // [rsp+B8h] [rbp+Fh]
  __int64 (__fastcall ***v37)(_QWORD, __int64); // [rsp+110h] [rbp+67h] BYREF

  v37 = a2;
  v28 = 0;
  v7 = *a2;
  v8 = (__int64 (__fastcall *)(_QWORD, __int64 *))*((_QWORD *)**a2 + 17);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  v9 = v8(v7, &v28);
  if ( v9 < 0 )
    _com_issue_error(v9);
  v31 = 0;
  v10 = v28;
  v11 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  v12 = v11(v10, L"latitude", &v31);
  if ( v12 < 0 )
    _com_issue_error(v12);
  v34.vt = 22;
  v34.lVal = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v31 + 64LL))(v31, &v34);
  if ( v13 < 0 )
    _com_issue_error(v13);
  v30 = 0;
  v14 = v28;
  v15 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  v16 = v15(v14, L"longitude", &v30);
  if ( v16 < 0 )
    _com_issue_error(v16);
  v33.vt = 22;
  v33.lVal = 0;
  v17 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v30 + 64LL))(v30, &v33);
  if ( v17 < 0 )
    _com_issue_error(v17);
  v29 = 0;
  v18 = v28;
  v19 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int64 *))(*(_QWORD *)v28 + 56LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  v20 = v19(v18, L"radiusInMeters", &v29);
  if ( v20 < 0 )
    _com_issue_error(v20);
  v32.vt = 22;
  v32.lVal = 0;
  v21 = (*(__int64 (__fastcall **)(__int64, VARIANTARG *))(*(_QWORD *)v29 + 64LL))(v29, &v32);
  if ( v21 < 0 )
    _com_issue_error(v21);
  v22 = (GeolocSignal *)operator new(0x68u);
  v36 = v22;
  if ( v32.vt == 3 )
  {
    lVal = v32.lVal;
  }
  else
  {
    VariantInit(&pvarg);
    _variant_t::ChangeType((_variant_t *)&pvarg, 3u, (const struct _variant_t *)&v32);
    lVal = pvarg.lVal;
    VariantClear(&pvarg);
  }
  _variant_t::operator float((struct _variant_t *)&v33);
  _variant_t::operator float((struct _variant_t *)&v34);
  v24 = GeolocSignal::GeolocSignal(v22, a3, a1, a1, lVal);
  v37 = 0;
  v26 = *a4;
  *a4 = v24;
  if ( v26 )
    std::default_delete<NASignal>::operator()(v25, (__int64 (__fastcall ***)(_QWORD, __int64))v26);
  std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(&v37);
  VariantClear(&v32);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v29);
  VariantClear(&v33);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v30);
  VariantClear(&v34);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v31);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease((__int64 *)a2);
  return 0;
}

```

## disassembly

```asm
0x18003f2b0  mov     rax, rsp
0x18003f2b3  mov     [rax+8], rbx
0x18003f2b7  mov     [rax+18h], rsi
0x18003f2bb  mov     [rax+10h], rdx
0x18003f2bf  push    rbp
0x18003f2c0  push    rdi
0x18003f2c1  push    r13
0x18003f2c3  push    r14
0x18003f2c5  push    r15
0x18003f2c7  lea     rbp, [rax-57h]
0x18003f2cb  sub     rsp, 0D0h
0x18003f2d2  movaps  xmmword ptr [rax-38h], xmm6
0x18003f2d6  mov     r14, r9
0x18003f2d9  mov     r15, r8
0x18003f2dc  mov     rsi, rdx
0x18003f2df  mov     [rbp+4Fh+var_C0], 0
0x18003f2e7  mov     rdi, [rdx]
0x18003f2ea  mov     rax, [rdi]
0x18003f2ed  mov     rbx, [rax+88h]
0x18003f2f4  lea     rcx, [rbp+4Fh+var_C0]
0x18003f2f8  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f2fd  lea     rdx, [rbp+4Fh+var_C0]
0x18003f301  mov     rcx, rdi
0x18003f304  mov     rax, rbx
0x18003f307  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f30c  test    eax, eax
0x18003f30e  jns     short loc_18003F318
0x18003f310  mov     ecx, eax; int
0x18003f312  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003f318  mov     [rbp+4Fh+var_A8], 0
0x18003f320  mov     rdi, [rbp+4Fh+var_C0]
0x18003f324  mov     rax, [rdi]
0x18003f327  mov     rbx, [rax+38h]
0x18003f32b  lea     rcx, [rbp+4Fh+var_A8]
0x18003f32f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f334  lea     r8, [rbp+4Fh+var_A8]
0x18003f338  lea     rdx, aLatitude; "latitude"
0x18003f33f  mov     rcx, rdi
0x18003f342  mov     rax, rbx
0x18003f345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f34a  test    eax, eax
0x18003f34c  jns     short loc_18003F356
0x18003f34e  mov     ecx, eax; int
0x18003f350  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003f356  mov     r13d, 16h
0x18003f35c  mov     word ptr [rbp+4Fh+var_70], r13w
0x18003f361  mov     dword ptr [rbp+4Fh+var_70+8], 0
0x18003f368  mov     rcx, [rbp+4Fh+var_A8]
0x18003f36c  mov     rax, [rcx]
0x18003f36f  lea     rdx, [rbp+4Fh+var_70]
0x18003f373  mov     rax, [rax+40h]
0x18003f377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f37c  test    eax, eax
0x18003f37e  jns     short loc_18003F388
0x18003f380  mov     ecx, eax; int
0x18003f382  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003f388  mov     [rbp+4Fh+var_B0], 0
0x18003f390  mov     rdi, [rbp+4Fh+var_C0]
0x18003f394  mov     rax, [rdi]
0x18003f397  mov     rbx, [rax+38h]
0x18003f39b  lea     rcx, [rbp+4Fh+var_B0]
0x18003f39f  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f3a4  lea     r8, [rbp+4Fh+var_B0]
0x18003f3a8  lea     rdx, aLongitude; "longitude"
0x18003f3af  mov     rcx, rdi
0x18003f3b2  mov     rax, rbx
0x18003f3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3ba  test    eax, eax
0x18003f3bc  jns     short loc_18003F3C6
0x18003f3be  mov     ecx, eax; int
0x18003f3c0  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003f3c6  mov     word ptr [rbp+4Fh+var_88], r13w
0x18003f3cb  mov     dword ptr [rbp+4Fh+var_88+8], 0
0x18003f3d2  mov     rcx, [rbp+4Fh+var_B0]
0x18003f3d6  mov     rax, [rcx]
0x18003f3d9  lea     rdx, [rbp+4Fh+var_88]
0x18003f3dd  mov     rax, [rax+40h]
0x18003f3e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f3e6  test    eax, eax
0x18003f3e8  jns     short loc_18003F3F2
0x18003f3ea  mov     ecx, eax; int
0x18003f3ec  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003f3f2  mov     [rbp+4Fh+var_B8], 0
0x18003f3fa  mov     rdi, [rbp+4Fh+var_C0]
0x18003f3fe  mov     rax, [rdi]
0x18003f401  mov     rbx, [rax+38h]
0x18003f405  lea     rcx, [rbp+4Fh+var_B8]
0x18003f409  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f40e  lea     r8, [rbp+4Fh+var_B8]
0x18003f412  lea     rdx, aRadiusinmeters; "radiusInMeters"
0x18003f419  mov     rcx, rdi
0x18003f41c  mov     rax, rbx
0x18003f41f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f424  test    eax, eax
0x18003f426  jns     short loc_18003F430
0x18003f428  mov     ecx, eax; int
0x18003f42a  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003f430  mov     word ptr [rbp+4Fh+var_A0], r13w
0x18003f435  mov     dword ptr [rbp+4Fh+var_A0+8], 0
0x18003f43c  mov     rcx, [rbp+4Fh+var_B8]
0x18003f440  mov     rax, [rcx]
0x18003f443  lea     rdx, [rbp+4Fh+var_A0]
0x18003f447  mov     rax, [rax+40h]
0x18003f44b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f450  test    eax, eax
0x18003f452  jns     short loc_18003F45C
0x18003f454  mov     ecx, eax; int
0x18003f456  call    ?_com_issue_error@@YAXJ@Z; _com_issue_error(long)
0x18003f45c  mov     ecx, 68h ; 'h'; Size
0x18003f461  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18003f466  mov     rbx, rax
0x18003f469  mov     [rbp+4Fh+var_40], rax
0x18003f46d  mov     edi, 3
0x18003f472  cmp     word ptr [rbp+4Fh+var_A0], di
0x18003f476  jnz     short loc_18003F47D
0x18003f478  mov     edi, dword ptr [rbp+4Fh+var_A0+8]
0x18003f47b  jmp     short loc_18003F4A4
0x18003f47d  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18003f481  call    cs:__imp_VariantInit
0x18003f487  nop
0x18003f488  mov     edx, edi; unsigned __int16
0x18003f48a  lea     r8, [rbp+4Fh+var_A0]; struct _variant_t *
0x18003f48e  lea     rcx, [rbp+4Fh+pvarg]; this
0x18003f492  call    ?ChangeType@_variant_t@@QEAAXGPEBV1@@Z; _variant_t::ChangeType(ushort,_variant_t const *)
0x18003f497  mov     edi, dword ptr [rbp+4Fh+pvarg+8]
0x18003f49a  lea     rcx, [rbp+4Fh+pvarg]; pvarg
0x18003f49e  call    cs:__imp_VariantClear
0x18003f4a4  lea     rcx, [rbp+4Fh+var_88]; struct _variant_t *
0x18003f4a8  call    ??B_variant_t@@QEBAMXZ; _variant_t::operator float(void)
0x18003f4ad  movaps  xmm6, xmm0
0x18003f4b0  lea     rcx, [rbp+4Fh+var_70]; struct _variant_t *
0x18003f4b4  call    ??B_variant_t@@QEBAMXZ; _variant_t::operator float(void)
0x18003f4b9  mov     [rsp+0F0h+var_D0], edi; int
0x18003f4bd  movaps  xmm3, xmm6; float
0x18003f4c0  movaps  xmm2, xmm0; float
0x18003f4c3  mov     rdx, r15; __int64
0x18003f4c6  mov     rcx, rbx; this
0x18003f4c9  call    ??0GeolocSignal@@QEAA@_JMMJ@Z; GeolocSignal::GeolocSignal(__int64,float,float,long)
0x18003f4ce  nop
0x18003f4cf  mov     [rbp+4Fh+arg_8], 0
0x18003f4d7  mov     rdx, [r14]
0x18003f4da  mov     [r14], rax
0x18003f4dd  test    rdx, rdx
0x18003f4e0  jz      short loc_18003F4E7
0x18003f4e2  call    ??R?$default_delete@VNASignal@@@std@@QEBAXPEAVNASignal@@@Z; std::default_delete<NASignal>::operator()(NASignal *)
0x18003f4e7  lea     rcx, [rbp+4Fh+arg_8]
0x18003f4eb  call    ??1?$unique_ptr@V_Facet_base@std@@U?$default_delete@V_Facet_base@std@@@2@@std@@QEAA@XZ; std::unique_ptr<std::_Facet_base>::~unique_ptr<std::_Facet_base>(void)
0x18003f4f0  nop
0x18003f4f1  lea     rcx, [rbp+4Fh+var_A0]; pvarg
0x18003f4f5  call    cs:__imp_VariantClear
0x18003f4fb  nop
0x18003f4fc  lea     rcx, [rbp+4Fh+var_B8]
0x18003f500  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f505  nop
0x18003f506  lea     rcx, [rbp+4Fh+var_88]; pvarg
0x18003f50a  call    cs:__imp_VariantClear
0x18003f510  nop
0x18003f511  lea     rcx, [rbp+4Fh+var_B0]
0x18003f515  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f51a  nop
0x18003f51b  lea     rcx, [rbp+4Fh+var_70]; pvarg
0x18003f51f  call    cs:__imp_VariantClear
0x18003f525  nop
0x18003f526  lea     rcx, [rbp+4Fh+var_A8]
0x18003f52a  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f52f  nop
0x18003f530  lea     rcx, [rbp+4Fh+var_C0]
0x18003f534  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f539  nop
0x18003f53a  mov     rcx, rsi
0x18003f53d  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18003f542  xor     eax, eax
0x18003f544  lea     r11, [rsp+0F0h+var_20]
0x18003f54c  mov     rbx, [r11+30h]
0x18003f550  mov     rsi, [r11+40h]
0x18003f554  movaps  xmm6, xmmword ptr [r11-10h]
0x18003f559  mov     rsp, r11
0x18003f55c  pop     r15
0x18003f55e  pop     r14
0x18003f560  pop     r13
0x18003f562  pop     rdi
0x18003f563  pop     rbp
0x18003f564  retn
```
