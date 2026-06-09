# OutOfBoundsEffect::HardwareRender(IImageBuffer *,IImageBuffer * *,RectT<IntegerTypes> const &,RectT<IntegerTypes> const &,ChannelFormat,IShader *)

- ea: `0x1801b4174`
- end: `0x1801b4c29`
- name: `?HardwareRender@OutOfBoundsEffect@@AEAAXPEAUIImageBuffer@@PEAPEAU2@AEBU?$RectT@UIntegerTypes@@@@2W4ChannelFormat@@PEAUIShader@@@Z`
- size: `2741`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x1801b3ba0`

## callees

- `0x18001db0c`
- `0x1801b2fdc`
- `0x1801b4174`
- `0x1801b521c`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1801b46a6`
- `OLEAUT32!__imp_VariantClear` at `0x1801b4946`
- `OLEAUT32!__imp_VariantClear` at `0x1801b46a6`
- `OLEAUT32!__imp_VariantClear` at `0x1801b4946`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b4453`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b46ca`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b4453`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801b46ca`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801b4a46`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801b4a5d`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801b4a46`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801b4a5d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801b4500`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801b45a9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801b478d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801b484a`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801b4500`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801b45a9`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801b478d`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801b484a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801b44d2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801b457d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801b475e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801b481e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801b44d2`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801b457d`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801b475e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801b481e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801b446f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801b46e6`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801b446f`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801b46e6`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801b4a39`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801b4a50`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801b4a39`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801b4a50`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801b45ee`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801b4891`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801b45ee`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801b4891`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801b4607`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801b48a5`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801b4607`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801b48a5`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801b4a2f`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x1801b4a2f`

## string_xrefs

- `0x1801b4421`: `MirrorExtension`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
HRESULT __fastcall OutOfBoundsEffect::HardwareRender(
        __int64 a1,
        __int64 a2,
        _QWORD *a3,
        int *a4,
        int *a5,
        unsigned int a6,
        __int64 a7)
{
  __int64 v8; // r10
  __int64 (__fastcall *v9)(__int64, _QWORD, unsigned __int64, _QWORD, _DWORD); // r11
  __int64 v10; // rdx
  __int64 v11; // rcx
  int v12; // eax
  int v13; // eax
  int v14; // ebx
  __int64 v15; // r15
  int v16; // eax
  int v17; // eax
  SAFEARRAY *v18; // rax
  SAFEARRAY *v19; // rdi
  HRESULT v20; // eax
  __int64 v21; // rcx
  float v22; // xmm6_4
  HRESULT LBound; // eax
  __int64 v24; // rbx
  HRESULT UBound; // eax
  __int64 v26; // rcx
  float v27; // xmm6_4
  HRESULT v28; // eax
  HRESULT v29; // eax
  __int64 (__fastcall *v30)(__int64, const wchar_t *, __int128 *); // rbx
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v33; // ebx
  SAFEARRAY *v34; // rax
  SAFEARRAY *v35; // rbx
  HRESULT v36; // eax
  __int64 v37; // rdx
  __int64 v38; // rcx
  float v39; // xmm6_4
  HRESULT v40; // eax
  __int64 cElements; // r13
  HRESULT v42; // eax
  __int64 v43; // rdx
  __int64 v44; // rcx
  float v45; // xmm6_4
  HRESULT v46; // eax
  HRESULT v47; // eax
  __int64 v48; // r13
  __int64 (__fastcall *v49)(__int64, const wchar_t *, __int128 *); // r12
  HRESULT v50; // ecx
  VARTYPE v51; // dx
  int v52; // r12d
  void *v53; // r12
  int v54; // eax
  int v55; // eax
  __int64 v56; // rax
  __int64 v57; // rcx
  HRESULT result; // eax
  SAFEARRAYBOUND rgsabound; // [rsp+50h] [rbp-B0h] BYREF
  LONG plLbound; // [rsp+58h] [rbp-A8h] BYREF
  LONG plUbound[2]; // [rsp+60h] [rbp-A0h] BYREF
  VARIANTARG pvt; // [rsp+68h] [rbp-98h] BYREF
  int *v64; // [rsp+80h] [rbp-80h]
  __int64 v65; // [rsp+88h] [rbp-78h]
  __int64 v66; // [rsp+90h] [rbp-70h] BYREF
  __int64 v67; // [rsp+98h] [rbp-68h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-60h] BYREF
  void *Block; // [rsp+A8h] [rbp-58h]
  __int128 v70; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v71; // [rsp+C0h] [rbp-40h]
  __int64 v72; // [rsp+C8h] [rbp-38h]
  __int64 v73; // [rsp+D0h] [rbp-30h]
  __int64 v74; // [rsp+D8h] [rbp-28h]
  __int64 v75; // [rsp+E0h] [rbp-20h]
  int *v76; // [rsp+E8h] [rbp-18h]
  _QWORD *v77; // [rsp+F0h] [rbp-10h]
  SAFEARRAY *v78; // [rsp+F8h] [rbp-8h]
  SAFEARRAY *v79; // [rsp+100h] [rbp+0h]
  _BYTE v80[24]; // [rsp+108h] [rbp+8h] BYREF
  int v81; // [rsp+120h] [rbp+20h]
  __int128 v82; // [rsp+130h] [rbp+30h] BYREF
  __int128 v83; // [rsp+140h] [rbp+40h]

  v76 = a4;
  v77 = a3;
  v64 = a5;
  v68 = a7;
  v65 = 0;
  v8 = *(_QWORD *)(a1 + 128);
  v9 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64, _QWORD, _DWORD))(*(_QWORD *)v8 + 248LL);
  v10 = a4[3] - (__int64)a4[1];
  if ( (unsigned __int64)(v10 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_90;
  v11 = a4[2] - (__int64)*a4;
  if ( (unsigned __int64)(v11 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_90;
  *(_QWORD *)plUbound = __PAIR64__(v10, v11);
  v12 = v9(v8, *(_QWORD *)a4, __PAIR64__(v10, v11), a6, 0);
  if ( v12 < 0 )
    ATL::BaseAtlThrow(v12);
  memset(v80, 0, sizeof(v80));
  v81 = 0;
  v13 = (*(__int64 (__fastcall **)(__int64, _BYTE *))(*(_QWORD *)a2 + 56LL))(a2, v80);
  if ( v13 < 0 )
    ATL::BaseAtlThrow(v13);
  v14 = *(_DWORD *)&v80[12];
  *(_QWORD *)&v70 = *(_QWORD *)&v80[12];
  plUbound[0] = *(_DWORD *)&v80[16];
  v74 = *(int *)&v80[12];
  v73 = *(int *)&v80[12] + (__int64)*(int *)&v80[20];
  if ( (unsigned __int64)(v73 + 0x80000000LL) > 0xFFFFFFFF
    || (DWORD2(v70) = *(_DWORD *)&v80[12] + *(_DWORD *)&v80[20],
        v75 = *(int *)&v80[16] + (__int64)v81,
        (unsigned __int64)(v75 + 0x80000000LL) > 0xFFFFFFFF) )
  {
LABEL_90:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  HIDWORD(v70) = *(_DWORD *)&v80[16] + v81;
  v71 = 0;
  v72 = 0;
  v67 = 0;
  v66 = 0;
  OutOfBoundsEffect::GetLockAndTexture(a2, 0, *(_DWORD *)v80, (unsigned int)&v70, (__int64)&v67, 4, (__int64)&v66);
  v15 = v66;
  v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, const wchar_t *, __int64))(*(_QWORD *)a7 + 112LL))(
          a7,
          0,
          L"Input0",
          v66);
  if ( v16 < 0 )
    ATL::BaseAtlThrow(v16);
  v17 = (*(__int64 (__fastcall **)(__int64, const wchar_t *))(*(_QWORD *)a7 + 88LL))(a7, L"MirrorExtension");
  if ( v17 < 0 )
    ATL::BaseAtlThrow(v17);
  rgsabound = (SAFEARRAYBOUND)2LL;
  v18 = SafeArrayCreate(4u, 1u, &rgsabound);
  v19 = v18;
  v78 = v18;
  if ( v18 )
    v20 = SafeArrayLock(v18);
  else
    v20 = -2147024882;
  if ( v20 < 0 )
    ATL::BaseAtlThrow(v20);
  v21 = v64[2] - (__int64)*v64;
  if ( (unsigned __int64)(v21 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_110;
  v22 = (float)(v14 - *v64) / (float)(int)v21;
  if ( !v19 )
    ATL::BaseAtlThrow(-2147467259);
  plLbound = 0;
  LBound = SafeArrayGetLBound(v19, 1u, &plLbound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  v24 = plLbound;
  if ( plLbound > 0 )
    goto LABEL_109;
  plLbound = 0;
  UBound = SafeArrayGetUBound(v19, 1u, &plLbound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( plLbound < 0 )
LABEL_109:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v19->pvData - v24) = v22;
  v26 = v64[3] - (__int64)v64[1];
  if ( (unsigned __int64)(v26 + 0x80000000LL) > 0xFFFFFFFF )
LABEL_110:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  v27 = (float)(plUbound[0] - v64[1]) / (float)(int)v26;
  plLbound = 0;
  v28 = SafeArrayGetLBound(v19, 1u, &plLbound);
  if ( v28 < 0 )
    ATL::BaseAtlThrow(v28);
  if ( plLbound > 1 )
    goto LABEL_109;
  rgsabound.cElements = 0;
  v29 = SafeArrayGetUBound(v19, 1u, (LONG *)&rgsabound);
  if ( v29 < 0 )
    ATL::BaseAtlThrow(v29);
  if ( (int)rgsabound.cElements < 1 )
    goto LABEL_109;
  *((float *)v19->pvData + 1 - plLbound) = v27;
  v30 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int128 *))(*(_QWORD *)a7 + 104LL);
  rgsabound = 0;
  Vartype = SafeArrayCopy(v19, (SAFEARRAY **)&rgsabound);
  if ( Vartype < 0 )
    goto LABEL_31;
  Vartype = SafeArrayGetVartype(v19, &pvt.vt);
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v19->fFeatures & 0x440) == 0x440 )
    vt = 9;
  if ( Vartype < 0 )
  {
LABEL_31:
    pvt.lVal = Vartype;
    pvt.vt = 10;
  }
  else
  {
    pvt.vt = vt | 0x2000;
    pvt.decVal.8 = (union tagDEC::$D28E26DEC3EC762C06C2AA9D0F7AC301)rgsabound;
  }
  if ( Vartype < 0 )
  {
    if ( Vartype != -2147024882 )
      ATL::BaseAtlThrow(Vartype);
    ATL::BaseAtlThrow(-2147024882);
  }
  v82 = *(_OWORD *)&pvt.vt;
  *(_QWORD *)&v83 = pvt.pRecInfo;
  v33 = v30(a7, L"fl2TotalBoundsCoordinatesToInputTextureCoordinatesOffset", &v82);
  VariantClear(&pvt);
  if ( v33 < 0 )
    ATL::BaseAtlThrow(v33);
  rgsabound = (SAFEARRAYBOUND)2LL;
  v34 = SafeArrayCreate(4u, 1u, &rgsabound);
  v35 = v34;
  v79 = v34;
  if ( v34 )
    v36 = SafeArrayLock(v34);
  else
    v36 = -2147024882;
  if ( v36 < 0 )
    ATL::BaseAtlThrow(v36);
  v37 = v64[2] - (__int64)*v64;
  if ( (unsigned __int64)(v37 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_107;
  v38 = (int)v73 - v74;
  if ( (unsigned __int64)(v38 + 0x80000000LL) > 0xFFFFFFFF )
    goto LABEL_107;
  v39 = (float)(int)v37 / (float)(int)v38;
  if ( !v35 )
    ATL::BaseAtlThrow(-2147467259);
  rgsabound.cElements = 0;
  v40 = SafeArrayGetLBound(v35, 1u, (LONG *)&rgsabound);
  if ( v40 < 0 )
    ATL::BaseAtlThrow(v40);
  cElements = (int)rgsabound.cElements;
  if ( (int)rgsabound.cElements > 0 )
    goto LABEL_106;
  rgsabound.cElements = 0;
  v42 = SafeArrayGetUBound(v35, 1u, (LONG *)&rgsabound);
  if ( v42 < 0 )
    ATL::BaseAtlThrow(v42);
  if ( (rgsabound.cElements & 0x80000000) != 0 )
LABEL_106:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v35->pvData - cElements) = v39;
  v43 = v64[3] - (__int64)v64[1];
  if ( (unsigned __int64)(v43 + 0x80000000LL) > 0xFFFFFFFF
    || (v44 = (int)v75 - (__int64)plUbound[0], (unsigned __int64)(v44 + 0x80000000LL) > 0xFFFFFFFF) )
  {
LABEL_107:
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  v45 = (float)(int)v43 / (float)(int)v44;
  plLbound = 0;
  v46 = SafeArrayGetLBound(v35, 1u, &plLbound);
  if ( v46 < 0 )
    ATL::BaseAtlThrow(v46);
  if ( plLbound > 1 )
    goto LABEL_106;
  plUbound[0] = 0;
  v47 = SafeArrayGetUBound(v35, 1u, plUbound);
  if ( v47 < 0 )
    ATL::BaseAtlThrow(v47);
  if ( plUbound[0] < 1 )
    goto LABEL_106;
  *((float *)v35->pvData + 1 - plLbound) = v45;
  v48 = v68;
  v49 = *(__int64 (__fastcall **)(__int64, const wchar_t *, __int128 *))(*(_QWORD *)v68 + 104LL);
  *(_QWORD *)plUbound = 0;
  v50 = SafeArrayCopy(v35, (SAFEARRAY **)plUbound);
  if ( v50 < 0 )
    goto LABEL_60;
  v50 = SafeArrayGetVartype(v35, &pvt.vt);
  v51 = pvt.vt;
  if ( v50 >= 0 && pvt.vt == 13 && (v35->fFeatures & 0x440) == 0x440 )
    v51 = 9;
  if ( v50 < 0 )
  {
LABEL_60:
    pvt.lVal = v50;
    pvt.vt = 10;
  }
  else
  {
    pvt.vt = v51 | 0x2000;
    pvt.llVal = *(_QWORD *)plUbound;
  }
  if ( v50 < 0 )
  {
    if ( v50 != -2147024882 )
      ATL::BaseAtlThrow(v50);
    ATL::BaseAtlThrow(-2147024882);
  }
  v82 = *(_OWORD *)&pvt.vt;
  *(_QWORD *)&v83 = pvt.pRecInfo;
  v52 = v49(v48, L"fl2TotalBoundsCoordinatesToInputTextureCoordinatesFactor", &v82);
  VariantClear(&pvt);
  if ( v52 < 0 )
    ATL::BaseAtlThrow(v52);
  v82 = v70;
  v83 = *(_OWORD *)v64;
  v68 = 0;
  Block = 0;
  VertexBuffer::GenerateVertexBuffer((unsigned int)&v68, (_DWORD)v76, (unsigned int)&v82, 2, (__int64)v76);
  v53 = Block;
  v54 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD, _QWORD, void *))(*(_QWORD *)v48 + 128LL))(
          v48,
          (unsigned int)v68,
          HIDWORD(v68),
          (unsigned int)(8 * HIDWORD(v68) + 12),
          Block);
  if ( v54 < 0 )
    ATL::BaseAtlThrow(v54);
  v55 = (*(__int64 (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v48 + 120LL))(v48, 0);
  if ( v55 < 0 )
    ATL::BaseAtlThrow(v55);
  v56 = v65;
  v65 = 0;
  *v77 = v56;
  if ( v53 )
  {
    v57 = ImagingEngine::s_singleton ? *((_QWORD *)ImagingEngine::s_singleton + 10) : 0LL;
    if ( !v57 || (*(unsigned int (__fastcall **)(__int64, void *))(*(_QWORD *)v57 + 88LL))(v57, v53) != 0 )
      free(v53);
  }
  if ( SafeArrayUnlock(v35) >= 0 )
    SafeArrayDestroy(v35);
  result = SafeArrayUnlock(v19);
  if ( result >= 0 )
    result = SafeArrayDestroy(v19);
  if ( v15 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v67 )
    result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v67 + 16LL))(v67);
  if ( v65 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v65 + 16LL))(v65);
  return result;
}

```

## disassembly

```asm
0x1801b4174  mov     rax, rsp
0x1801b4177  push    rbp
0x1801b4178  push    rbx
0x1801b4179  push    rsi
0x1801b417a  push    rdi
0x1801b417b  push    r12
0x1801b417d  push    r13
0x1801b417f  push    r14
0x1801b4181  push    r15
0x1801b4183  lea     rbp, [rsp-78h]
0x1801b4188  sub     rsp, 178h
0x1801b418f  movaps  xmmword ptr [rax-58h], xmm6
0x1801b4193  mov     rax, cs:__security_cookie
0x1801b419a  xor     rax, rsp
0x1801b419d  mov     [rbp+0B0h+var_60], rax
0x1801b41a1  mov     r15, r9
0x1801b41a4  mov     [rbp+0B0h+var_C8], r9
0x1801b41a8  mov     [rbp+0B0h+var_C0], r8
0x1801b41ac  mov     rdi, rdx
0x1801b41af  mov     rdx, [rbp+0B0h+arg_20]
0x1801b41b6  mov     [rbp+0B0h+var_130], rdx
0x1801b41ba  mov     r13, [rbp+0B0h+arg_30]
0x1801b41c1  mov     [rbp+0B0h+var_110], r13
0x1801b41c5  xor     r14d, r14d
0x1801b41c8  mov     [rbp+0B0h+var_128], r14
0x1801b41cc  mov     r10, [rcx+80h]
0x1801b41d3  mov     rax, [r10]
0x1801b41d6  mov     r11, [rax+0F8h]
0x1801b41dd  movsxd  rax, dword ptr [r9+4]
0x1801b41e1  movsxd  rdx, dword ptr [r9+0Ch]
0x1801b41e5  sub     rdx, rax
0x1801b41e8  mov     esi, 80000000h
0x1801b41ed  lea     rax, [rsi+rdx]
0x1801b41f1  mov     r12d, 0FFFFFFFFh
0x1801b41f7  cmp     rax, r12
0x1801b41fa  ja      loc_1801B4B20
0x1801b4200  movsxd  rax, dword ptr [r9]
0x1801b4203  movsxd  rcx, dword ptr [r9+8]
0x1801b4207  sub     rcx, rax
0x1801b420a  lea     rax, [rsi+rcx]
0x1801b420e  cmp     rax, r12
0x1801b4211  ja      loc_1801B4B20
0x1801b4217  mov     [rsp+1B0h+plUbound], ecx
0x1801b421b  mov     [rsp+1B0h+plUbound+4], edx
0x1801b421f  lea     rax, [rbp+0B0h+var_128]
0x1801b4223  mov     [rsp+1B0h+var_178], rax
0x1801b4228  mov     dword ptr [rsp+1B0h+var_180], r14d
0x1801b422d  mov     dword ptr [rsp+1B0h+var_188], 4
0x1801b4235  mov     dword ptr [rsp+1B0h+var_190], r14d
0x1801b423a  mov     r9d, [rbp+0B0h+arg_28]
0x1801b4241  mov     r8, qword ptr [rsp+1B0h+plUbound]
0x1801b4246  mov     rdx, [r15]
0x1801b4249  mov     rcx, r10
0x1801b424c  mov     rax, r11
0x1801b424f  call    cs:__guard_dispatch_icall_fptr
0x1801b4255  test    eax, eax
0x1801b4257  js      loc_1801B4AFB
0x1801b425d  xorps   xmm0, xmm0
0x1801b4260  xor     eax, eax
0x1801b4262  movups  [rbp+0B0h+var_A8], xmm0
0x1801b4266  mov     [rbp+0B0h+var_98], rax
0x1801b426a  mov     [rbp+0B0h+var_90], eax
0x1801b426d  mov     rax, [rdi]
0x1801b4270  lea     rdx, [rbp+0B0h+var_A8]
0x1801b4274  mov     rcx, rdi
0x1801b4277  mov     rax, [rax+38h]
0x1801b427b  call    cs:__guard_dispatch_icall_fptr
0x1801b4281  test    eax, eax
0x1801b4283  js      loc_1801B4C21
0x1801b4289  movsxd  rbx, dword ptr [rbp+0B0h+var_A8+0Ch]
0x1801b428d  mov     dword ptr [rbp+0B0h+var_100], ebx
0x1801b4290  movsxd  rdx, dword ptr [rbp+0B0h+var_98]
0x1801b4294  mov     [rsp+1B0h+plUbound], edx
0x1801b4298  mov     dword ptr [rbp+0B0h+var_100+4], edx
0x1801b429b  mov     [rbp+0B0h+var_D8], rbx
0x1801b429f  movsxd  rcx, dword ptr [rbp+0B0h+var_98+4]
0x1801b42a3  add     rcx, rbx
0x1801b42a6  mov     [rbp+0B0h+var_E0], rcx
0x1801b42aa  lea     rax, [rsi+rcx]
0x1801b42ae  cmp     rax, r12
0x1801b42b1  ja      loc_1801B4B20
0x1801b42b7  mov     dword ptr [rbp+0B0h+var_100+8], ecx
0x1801b42ba  movsxd  rcx, [rbp+0B0h+var_90]
0x1801b42be  add     rcx, rdx
0x1801b42c1  mov     [rbp+0B0h+var_D0], rcx
0x1801b42c5  lea     rax, [rsi+rcx]
0x1801b42c9  cmp     rax, r12
0x1801b42cc  ja      loc_1801B4B20
0x1801b42d2  mov     dword ptr [rbp+0B0h+var_100+0Ch], ecx
0x1801b42d5  mov     esi, r14d
0x1801b42d8  mov     [rbp+0B0h+var_F0], r14
0x1801b42dc  mov     [rbp+0B0h+var_E8], r14
0x1801b42e0  mov     r10, [rbp+0B0h+var_128]
0x1801b42e4  lea     r12d, [r14+1]
0x1801b42e8  test    r10, r10
0x1801b42eb  jz      loc_1801B43C0
0x1801b42f1  mov     qword ptr [rsp+1B0h+rgsabound.cElements], r14
0x1801b42f6  mov     rax, [r15]
0x1801b42f9  mov     [rbp+0B0h+var_118], rax
0x1801b42fd  movsxd  rdx, dword ptr [r15+0Ch]
0x1801b4301  movsxd  rax, dword ptr [r15+4]
0x1801b4305  sub     rdx, rax
0x1801b4308  mov     r8d, 80000000h
0x1801b430e  lea     rax, [rdx+r8]
0x1801b4312  mov     r9d, 0FFFFFFFFh
0x1801b4318  cmp     rax, r9
0x1801b431b  ja      loc_1801B4B3C
0x1801b4321  movsxd  rcx, dword ptr [r15+8]
0x1801b4325  movsxd  rax, dword ptr [r15]
0x1801b4328  sub     rcx, rax
0x1801b432b  lea     rax, [r8+rcx]
0x1801b432f  cmp     rax, r9
0x1801b4332  ja      loc_1801B4B3C
0x1801b4338  mov     [rsp+1B0h+plLbound], ecx
0x1801b433c  mov     [rsp+1B0h+var_154], edx
0x1801b4340  mov     rax, [r10]
0x1801b4343  lea     rcx, [rsp+1B0h+rgsabound]
0x1801b4348  mov     [rsp+1B0h+var_180], rcx
0x1801b434d  lea     rcx, [rsp+1B0h+plLbound]
0x1801b4352  mov     [rsp+1B0h+var_188], rcx
0x1801b4357  lea     rcx, [rbp+0B0h+var_118]
0x1801b435b  mov     [rsp+1B0h+var_190], rcx
0x1801b4360  xor     r9d, r9d
0x1801b4363  mov     r8d, [rbp+0B0h+arg_28]
0x1801b436a  mov     edx, r12d
0x1801b436d  mov     rcx, r10
0x1801b4370  mov     rax, [rax+58h]
0x1801b4374  call    cs:__guard_dispatch_icall_fptr
0x1801b437a  test    eax, eax
0x1801b437c  js      loc_1801B4B34
0x1801b4382  mov     [rbp+0B0h+var_120], r14
0x1801b4386  mov     rsi, qword ptr [rsp+1B0h+rgsabound.cElements]
0x1801b438b  test    rsi, rsi
0x1801b438e  jz      short loc_1801B43B8
0x1801b4390  mov     rax, [rsi]
0x1801b4393  lea     r8, [rbp+0B0h+var_120]
0x1801b4397  xor     edx, edx
0x1801b4399  mov     rcx, rsi
0x1801b439c  mov     rax, [rax+50h]
0x1801b43a0  call    cs:__guard_dispatch_icall_fptr
0x1801b43a6  cmp     eax, 0FFFFFFFFh
0x1801b43a9  jle     loc_1801B4B29
0x1801b43af  mov     rsi, qword ptr [rsp+1B0h+rgsabound.cElements]
0x1801b43b4  mov     r14, [rbp+0B0h+var_120]
0x1801b43b8  mov     [rbp+0B0h+var_F0], rsi
0x1801b43bc  mov     [rbp+0B0h+var_E8], r14
0x1801b43c0  mov     [rbp+0B0h+var_118], 0
0x1801b43c8  mov     [rbp+0B0h+var_120], 0
0x1801b43d0  lea     rax, [rbp+0B0h+var_120]
0x1801b43d4  mov     [rsp+1B0h+var_180], rax
0x1801b43d9  lea     rax, [rbp+0B0h+var_118]
0x1801b43dd  mov     [rsp+1B0h+var_190], rax
0x1801b43e2  lea     r9, [rbp+0B0h+var_100]
0x1801b43e6  mov     r8d, dword ptr [rbp+0B0h+var_A8]
0x1801b43ea  xor     edx, edx
0x1801b43ec  mov     rcx, rdi
0x1801b43ef  call    ?GetLockAndTexture@OutOfBoundsEffect@@CAXPEAUIImageBuffer@@W4AccessType@@W4ChannelFormat@@AEBU?$RectT@UIntegerTypes@@@@PEAPEAUIImageBufferLock@@HPEAPEAUITexture@@@Z; OutOfBoundsEffect::GetLockAndTexture(IImageBuffer *,AccessType,ChannelFormat,RectT<IntegerTypes> const &,IImageBufferLock * *,int,ITexture * *)
0x1801b43f4  mov     rax, [r13+0]
0x1801b43f8  mov     r15, [rbp+0B0h+var_120]
0x1801b43fc  mov     r9, r15
0x1801b43ff  lea     r8, aInput0_0; "Input0"
0x1801b4406  xor     edx, edx
0x1801b4408  mov     rcx, r13
0x1801b440b  mov     rax, [rax+70h]
0x1801b440f  call    cs:__guard_dispatch_icall_fptr
0x1801b4415  test    eax, eax
0x1801b4417  js      loc_1801B4C15
0x1801b441d  mov     rax, [r13+0]
0x1801b4421  lea     rdx, aMirrorextensio; "MirrorExtension"
0x1801b4428  mov     rcx, r13
0x1801b442b  mov     rax, [rax+58h]
0x1801b442f  call    cs:__guard_dispatch_icall_fptr
0x1801b4435  test    eax, eax
0x1801b4437  js      loc_1801B4C0D
0x1801b443d  mov     qword ptr [rsp+1B0h+rgsabound.cElements], 2
0x1801b4446  mov     ecx, 4; vt
0x1801b444b  lea     r8, [rsp+1B0h+rgsabound]; rgsabound
0x1801b4450  mov     edx, r12d; cDims
0x1801b4453  call    cs:__imp_SafeArrayCreate
0x1801b4459  mov     rdi, rax
0x1801b445c  mov     [rbp+0B0h+var_B8], rax
0x1801b4460  test    rax, rax
0x1801b4463  jnz     short loc_1801B446C
0x1801b4465  mov     eax, 8007000Eh
0x1801b446a  jmp     short loc_1801B4475
0x1801b446c  mov     rcx, rdi; psa
0x1801b446f  call    cs:__imp_SafeArrayLock
0x1801b4475  test    eax, eax
0x1801b4477  js      loc_1801B4B45
0x1801b447d  mov     rdx, [rbp+0B0h+var_130]
0x1801b4481  movsxd  rax, dword ptr [rdx]
0x1801b4484  movsxd  rcx, dword ptr [rdx+8]
0x1801b4488  sub     rcx, rax
0x1801b448b  mov     eax, 80000000h
0x1801b4490  add     rax, rcx
0x1801b4493  mov     r8d, 0FFFFFFFFh
0x1801b4499  cmp     rax, r8
0x1801b449c  ja      loc_1801B4C04
0x1801b44a2  sub     ebx, [rdx]
0x1801b44a4  movd    xmm6, ebx
0x1801b44a8  cvtdq2ps xmm6, xmm6
0x1801b44ab  movd    xmm0, ecx
0x1801b44af  cvtdq2ps xmm0, xmm0
0x1801b44b2  divss   xmm6, xmm0
0x1801b44b6  test    rdi, rdi
0x1801b44b9  jz      loc_1801B4B50
0x1801b44bf  mov     [rsp+1B0h+plLbound], 0
0x1801b44c7  lea     r8, [rsp+1B0h+plLbound]; plLbound
0x1801b44cc  mov     edx, r12d; nDim
0x1801b44cf  mov     rcx, rdi; psa
0x1801b44d2  call    cs:__imp_SafeArrayGetLBound
0x1801b44d8  test    eax, eax
0x1801b44da  js      loc_1801B4B5B
0x1801b44e0  movsxd  rbx, [rsp+1B0h+plLbound]
0x1801b44e5  test    ebx, ebx
0x1801b44e7  jg      loc_1801B4BF9
0x1801b44ed  mov     [rsp+1B0h+plLbound], 0
0x1801b44f5  lea     r8, [rsp+1B0h+plLbound]; plUbound
0x1801b44fa  mov     edx, r12d; nDim
0x1801b44fd  mov     rcx, rdi; psa
0x1801b4500  call    cs:__imp_SafeArrayGetUBound
0x1801b4506  test    eax, eax
0x1801b4508  js      loc_1801B4B63
0x1801b450e  cmp     [rsp+1B0h+plLbound], 0
0x1801b4513  jl      loc_1801B4BF9
0x1801b4519  mov     rcx, rbx
0x1801b451c  shl     rcx, 2
0x1801b4520  mov     rax, [rdi+10h]
0x1801b4524  sub     rax, rcx
0x1801b4527  movss   dword ptr [rax], xmm6
0x1801b452b  mov     rdx, [rbp+0B0h+var_130]
0x1801b452f  movsxd  rax, dword ptr [rdx+4]
0x1801b4533  movsxd  rcx, dword ptr [rdx+0Ch]
0x1801b4537  sub     rcx, rax
0x1801b453a  mov     eax, 80000000h
0x1801b453f  add     rax, rcx
0x1801b4542  mov     r8d, 0FFFFFFFFh
0x1801b4548  cmp     rax, r8
0x1801b454b  ja      loc_1801B4C04
0x1801b4551  mov     eax, [rsp+1B0h+plUbound]
0x1801b4555  sub     eax, [rdx+4]
0x1801b4558  movd    xmm6, eax
0x1801b455c  cvtdq2ps xmm6, xmm6
0x1801b455f  movd    xmm0, ecx
0x1801b4563  cvtdq2ps xmm0, xmm0
0x1801b4566  divss   xmm6, xmm0
0x1801b456a  mov     [rsp+1B0h+plLbound], 0
0x1801b4572  lea     r8, [rsp+1B0h+plLbound]; plLbound
0x1801b4577  mov     edx, r12d; nDim
0x1801b457a  mov     rcx, rdi; psa
0x1801b457d  call    cs:__imp_SafeArrayGetLBound
0x1801b4583  test    eax, eax
0x1801b4585  js      loc_1801B4B6B
0x1801b458b  cmp     [rsp+1B0h+plLbound], r12d
0x1801b4590  jg      loc_1801B4BF9
0x1801b4596  mov     [rsp+1B0h+rgsabound.cElements], 0
0x1801b459e  lea     r8, [rsp+1B0h+rgsabound]; plUbound
0x1801b45a3  mov     edx, r12d; nDim
0x1801b45a6  mov     rcx, rdi; psa
0x1801b45a9  call    cs:__imp_SafeArrayGetUBound
0x1801b45af  test    eax, eax
0x1801b45b1  js      loc_1801B4B73
0x1801b45b7  cmp     [rsp+1B0h+rgsabound.cElements], r12d
0x1801b45bc  jl      loc_1801B4BF9
0x1801b45c2  mov     eax, r12d
0x1801b45c5  sub     eax, [rsp+1B0h+plLbound]
0x1801b45c9  movsxd  rcx, eax
0x1801b45cc  mov     rax, [rdi+10h]
0x1801b45d0  movss   dword ptr [rax+rcx*4], xmm6
0x1801b45d5  mov     rax, [r13+0]
0x1801b45d9  mov     rbx, [rax+68h]
0x1801b45dd  mov     qword ptr [rsp+1B0h+rgsabound.cElements], 0
0x1801b45e6  lea     rdx, [rsp+1B0h+rgsabound]; ppsaOut
0x1801b45eb  mov     rcx, rdi; psa
0x1801b45ee  call    cs:__imp_SafeArrayCopy
0x1801b45f4  mov     ecx, eax
0x1801b45f6  mov     eax, 0Ah
0x1801b45fb  test    ecx, ecx
0x1801b45fd  js      short loc_1801B4656
0x1801b45ff  lea     rdx, [rsp+1B0h+pvt]; pvt
0x1801b4604  mov     rcx, rdi; psa
0x1801b4607  call    cs:__imp_SafeArrayGetVartype
0x1801b460d  mov     ecx, eax; int
0x1801b460f  movzx   edx, [rsp+1B0h+pvt]
0x1801b4614  test    eax, eax
0x1801b4616  js      short loc_1801B4637
0x1801b4618  cmp     dx, 0Dh
0x1801b461c  jnz     short loc_1801B4637
0x1801b461e  movzx   eax, word ptr [rdi+2]
0x1801b4622  mov     r8d, 440h
0x1801b4628  and     ax, r8w
0x1801b462c  cmp     ax, r8w
0x1801b4630  jnz     short loc_1801B4637
0x1801b4632  mov     edx, 9
0x1801b4637  test    ecx, ecx
0x1801b4639  js      short loc_1801B4651
0x1801b463b  or      dx, 2000h
0x1801b4640  mov     [rsp+1B0h+pvt], dx
0x1801b4645  mov     rax, qword ptr [rsp+1B0h+rgsabound.cElements]
0x1801b464a  mov     qword ptr [rsp+1B0h+pvt+8], rax
  ... truncated ...
```
