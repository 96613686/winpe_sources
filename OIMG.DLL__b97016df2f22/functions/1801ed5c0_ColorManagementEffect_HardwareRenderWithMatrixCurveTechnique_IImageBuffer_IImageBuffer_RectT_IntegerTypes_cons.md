# ColorManagementEffect::HardwareRenderWithMatrixCurveTechnique(IImageBuffer *,IImageBuffer * *,RectT<IntegerTypes> const &,ChannelFormat,IShader *)

- ea: `0x1801ed5c0`
- end: `0x1801ee86f`
- name: `?HardwareRenderWithMatrixCurveTechnique@ColorManagementEffect@@AEAAXPEAUIImageBuffer@@PEAPEAU2@AEBU?$RectT@UIntegerTypes@@@@W4ChannelFormat@@PEAUIShader@@@Z`
- size: `4783`
- prototype: `__int64 __usercall@<rax>(ColorManagementEffect *this@<rcx>, int, struct IShader *)`
- caller_count: `1`
- callee_count: `12`
- tags: `loader_planting`

## callers

- `0x1801ecf90`

## callees

- `0x18001db0c`
- `0x1801985ac`
- `0x1801a9894`
- `0x1801d4c84`
- `0x1801ec4a0`
- `0x1801ec8dc`
- `0x1801ed5c0`
- `0x1801f1ee0`
- `0x1801f2324`
- `0x1804c6944`
- `0x18056bd00`
- `0x18056dce0`

## import_xrefs

- `OLEAUT32!__imp_VariantClear` at `0x1801edbe4`
- `OLEAUT32!__imp_VariantClear` at `0x1801edbe4`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801ed712`
- `OLEAUT32!__imp_SafeArrayCreate` at `0x1801ed712`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801ee680`
- `OLEAUT32!__imp_SafeArrayDestroy` at `0x1801ee680`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed780`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed7ed`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed85f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed8cd`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed937`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed9a7`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801eda15`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801eda83`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801edaed`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed780`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed7ed`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed85f`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed8cd`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed937`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801ed9a7`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801eda15`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801eda83`
- `OLEAUT32!__imp_SafeArrayGetUBound` at `0x1801edaed`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed755`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed7c4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed832`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed8a0`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed90e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed97a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed9e8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801eda56`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801edac4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed755`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed7c4`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed832`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed8a0`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed90e`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed97a`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801ed9e8`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801eda56`
- `OLEAUT32!__imp_SafeArrayGetLBound` at `0x1801edac4`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801ed72e`
- `OLEAUT32!__imp_SafeArrayLock` at `0x1801ed72e`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801ee673`
- `OLEAUT32!__imp_SafeArrayUnlock` at `0x1801ee673`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801edb39`
- `OLEAUT32!__imp_SafeArrayCopy` at `0x1801edb39`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801edb4c`
- `OLEAUT32!__imp_SafeArrayGetVartype` at `0x1801edb4c`

## pseudocode

```c
// Hidden C++ exception states: #wind=25
HRESULT __fastcall ColorManagementEffect::HardwareRenderWithMatrixCurveTechnique(
        ColorManagementEffect *this,
        __int64 a2,
        _QWORD *a3,
        int *a4,
        unsigned int a5,
        struct IShader *a6)
{
  char v8; // r15
  __int64 v9; // r10
  __int64 (__fastcall *v10)(__int64, _QWORD, unsigned __int64, _QWORD, _DWORD); // r11
  __int64 v11; // rdx
  __int64 v12; // rcx
  int v13; // eax
  int v14; // eax
  SAFEARRAY *v15; // rax
  SAFEARRAY *v16; // rbx
  HRESULT v17; // eax
  HRESULT LBound; // eax
  __int64 v19; // rdi
  HRESULT UBound; // eax
  HRESULT v21; // eax
  HRESULT v22; // eax
  HRESULT v23; // eax
  HRESULT v24; // eax
  HRESULT v25; // eax
  HRESULT v26; // eax
  HRESULT v27; // eax
  HRESULT v28; // eax
  HRESULT v29; // eax
  HRESULT v30; // eax
  HRESULT v31; // eax
  HRESULT v32; // eax
  HRESULT v33; // eax
  HRESULT v34; // eax
  HRESULT v35; // eax
  HRESULT v36; // eax
  __int64 (__fastcall *v37)(struct IShader *, const wchar_t *, __int128 *); // rdi
  HRESULT Vartype; // ecx
  VARTYPE vt; // dx
  int v40; // edi
  __int64 v41; // rcx
  __int64 *v42; // r14
  __int64 v43; // r9
  int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // rcx
  int v47; // eax
  unsigned __int64 v48; // rax
  unsigned __int64 v49; // rcx
  unsigned __int64 v50; // rdi
  unsigned __int64 v51; // rdx
  int v52; // eax
  int v53; // eax
  char v54; // r14
  char v55; // di
  SAFEARRAYBOUND v56; // rcx
  __int64 *v57; // r12
  __int64 v58; // r9
  int v59; // eax
  int v60; // eax
  __int64 v61; // rdi
  LONG lLbound; // r14d
  __int64 v63; // rdx
  __int64 v64; // rcx
  int v65; // r9d
  __int64 v66; // r8
  int v67; // eax
  SAFEARRAYBOUND v68; // rax
  SAFEARRAYBOUND v69; // rcx
  SAFEARRAYBOUND v70; // rdi
  SAFEARRAYBOUND v71; // rdx
  int v72; // eax
  int v73; // eax
  SAFEARRAYBOUND v74; // rdi
  __int64 v75; // rsi
  int *v76; // r14
  __int64 v77; // rdx
  __int64 v78; // rcx
  int v79; // eax
  int v80; // eax
  int v81; // eax
  int v82; // eax
  int *v83; // r14
  int v84; // eax
  int v85; // eax
  int v86; // eax
  const wchar_t *v87; // r12
  __int64 v88; // rax
  const wchar_t *v89; // rcx
  const wchar_t *v90; // r15
  const wchar_t *v91; // r8
  __int64 v92; // rax
  __int64 v93; // rax
  const wchar_t **v94; // rax
  _QWORD *v95; // rdx
  _QWORD *v96; // rdx
  _QWORD *v97; // rdx
  _QWORD *v98; // rdx
  int v99; // eax
  int v100; // eax
  __int64 v101; // rax
  _QWORD *v102; // rdx
  HRESULT result; // eax
  __int64 v104; // [rsp+20h] [rbp-E0h]
  LONG *v105; // [rsp+28h] [rbp-D8h]
  int v106; // [rsp+28h] [rbp-D8h]
  __int64 v107; // [rsp+30h] [rbp-D0h]
  int v108; // [rsp+38h] [rbp-C8h]
  LONG plUbound[2]; // [rsp+50h] [rbp-B0h] BYREF
  LONG plLbound[2]; // [rsp+58h] [rbp-A8h] BYREF
  char v111; // [rsp+60h] [rbp-A0h]
  SAFEARRAYBOUND rgsabound; // [rsp+68h] [rbp-98h] BYREF
  char v113; // [rsp+70h] [rbp-90h]
  SAFEARRAYBOUND v114; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v115; // [rsp+80h] [rbp-80h] BYREF
  int *v116; // [rsp+88h] [rbp-78h] BYREF
  __int64 v117; // [rsp+90h] [rbp-70h]
  __int64 v118; // [rsp+98h] [rbp-68h]
  unsigned __int64 v119; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v120; // [rsp+A8h] [rbp-58h]
  __int64 v121; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v122; // [rsp+B8h] [rbp-48h] BYREF
  VARIANTARG pvt; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v124; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v125; // [rsp+E0h] [rbp-20h]
  __int64 v126; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD *v127; // [rsp+F0h] [rbp-10h]
  double v128[12]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v129; // [rsp+160h] [rbp+60h] BYREF
  _QWORD v130[2]; // [rsp+170h] [rbp+70h]
  __int128 v131; // [rsp+180h] [rbp+80h] BYREF
  __int64 v132; // [rsp+190h] [rbp+90h]
  int v133; // [rsp+198h] [rbp+98h]

  v116 = a4;
  v127 = a3;
  v122 = a2;
  v8 = 0;
  v120 = 0;
  v9 = *((_QWORD *)this + 16);
  v10 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64, _QWORD, _DWORD))(*(_QWORD *)v9 + 248LL);
  v11 = a4[3] - (__int64)a4[1];
  if ( (unsigned __int64)(v11 + 0x80000000LL) > 0xFFFFFFFF
    || (v12 = a4[2] - (__int64)*a4, (unsigned __int64)(v12 + 0x80000000LL) > 0xFFFFFFFF) )
  {
    safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
  }
  v119 = __PAIR64__(v11, v12);
  LODWORD(v105) = 4;
  v13 = v10(v9, *(_QWORD *)a4, __PAIR64__(v11, v12), a5, 0);
  if ( v13 < 0 )
    ATL::BaseAtlThrow(v13);
  v131 = 0;
  v132 = 0;
  v133 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)a2 + 56LL))(a2, &v131);
  if ( v14 < 0 )
    ATL::BaseAtlThrow(v14);
  ColorManagementEffect::SetGammas(this, a6);
  CMatrix3X3::operator*((char *)this + 488, v128, (char *)this + 832);
  rgsabound = (SAFEARRAYBOUND)9LL;
  v15 = SafeArrayCreate(4u, 1u, &rgsabound);
  v16 = v15;
  *(_QWORD *)&v128[10] = v15;
  if ( v15 )
    v17 = SafeArrayLock(v15);
  else
    v17 = -2147024882;
  if ( v17 < 0 )
    ATL::BaseAtlThrow(v17);
  if ( !v16 )
    ATL::BaseAtlThrow(-2147467259);
  plLbound[0] = 0;
  LBound = SafeArrayGetLBound(v16, 1u, plLbound);
  if ( LBound < 0 )
    ATL::BaseAtlThrow(LBound);
  v19 = plLbound[0];
  if ( plLbound[0] > 0 )
    goto LABEL_234;
  plLbound[0] = 0;
  UBound = SafeArrayGetUBound(v16, 1u, plLbound);
  if ( UBound < 0 )
    ATL::BaseAtlThrow(UBound);
  if ( plLbound[0] < 0 )
    goto LABEL_234;
  *((float *)v16->pvData - v19) = v128[0];
  plLbound[0] = 0;
  v21 = SafeArrayGetLBound(v16, 1u, plLbound);
  if ( v21 < 0 )
    ATL::BaseAtlThrow(v21);
  if ( plLbound[0] > 1 )
    goto LABEL_234;
  plUbound[0] = 0;
  v22 = SafeArrayGetUBound(v16, 1u, plUbound);
  if ( v22 < 0 )
    ATL::BaseAtlThrow(v22);
  if ( plUbound[0] < 1 )
    goto LABEL_234;
  *((float *)v16->pvData + 1 - plLbound[0]) = v128[1];
  plLbound[0] = 0;
  v23 = SafeArrayGetLBound(v16, 1u, plLbound);
  if ( v23 < 0 )
    ATL::BaseAtlThrow(v23);
  if ( plLbound[0] > 2 )
    goto LABEL_234;
  plUbound[0] = 0;
  v24 = SafeArrayGetUBound(v16, 1u, plUbound);
  if ( v24 < 0 )
    ATL::BaseAtlThrow(v24);
  if ( plUbound[0] < 2 )
    goto LABEL_234;
  *((float *)v16->pvData + 2 - plLbound[0]) = v128[2];
  plLbound[0] = 0;
  v25 = SafeArrayGetLBound(v16, 1u, plLbound);
  if ( v25 < 0 )
    ATL::BaseAtlThrow(v25);
  if ( plLbound[0] > 3 )
    goto LABEL_234;
  plUbound[0] = 0;
  v26 = SafeArrayGetUBound(v16, 1u, plUbound);
  if ( v26 < 0 )
    ATL::BaseAtlThrow(v26);
  if ( plUbound[0] < 3 )
    goto LABEL_234;
  *((float *)v16->pvData + 3 - plLbound[0]) = v128[3];
  plLbound[0] = 0;
  v27 = SafeArrayGetLBound(v16, 1u, plLbound);
  if ( v27 < 0 )
    ATL::BaseAtlThrow(v27);
  if ( plLbound[0] > 4 )
    goto LABEL_234;
  plUbound[0] = 0;
  v28 = SafeArrayGetUBound(v16, 1u, plUbound);
  if ( v28 < 0 )
    ATL::BaseAtlThrow(v28);
  if ( plUbound[0] < 4 )
    goto LABEL_234;
  *((float *)v16->pvData + 4 - plLbound[0]) = v128[4];
  plLbound[0] = 0;
  v29 = SafeArrayGetLBound(v16, 1u, plLbound);
  if ( v29 < 0 )
    ATL::BaseAtlThrow(v29);
  if ( plLbound[0] > 5 )
    goto LABEL_234;
  plUbound[0] = 0;
  v30 = SafeArrayGetUBound(v16, 1u, plUbound);
  if ( v30 < 0 )
    ATL::BaseAtlThrow(v30);
  if ( plUbound[0] < 5 )
    goto LABEL_234;
  *((float *)v16->pvData + 5 - plLbound[0]) = v128[5];
  plLbound[0] = 0;
  v31 = SafeArrayGetLBound(v16, 1u, plLbound);
  if ( v31 < 0 )
    ATL::BaseAtlThrow(v31);
  if ( plLbound[0] > 6 )
    goto LABEL_234;
  plUbound[0] = 0;
  v32 = SafeArrayGetUBound(v16, 1u, plUbound);
  if ( v32 < 0 )
    ATL::BaseAtlThrow(v32);
  if ( plUbound[0] < 6 )
    goto LABEL_234;
  *((float *)v16->pvData + 6 - plLbound[0]) = v128[6];
  plLbound[0] = 0;
  v33 = SafeArrayGetLBound(v16, 1u, plLbound);
  if ( v33 < 0 )
    ATL::BaseAtlThrow(v33);
  if ( plLbound[0] > 7 )
    goto LABEL_234;
  plUbound[0] = 0;
  v34 = SafeArrayGetUBound(v16, 1u, plUbound);
  if ( v34 < 0 )
    ATL::BaseAtlThrow(v34);
  if ( plUbound[0] < 7 )
    goto LABEL_234;
  *((float *)v16->pvData + 7 - plLbound[0]) = v128[7];
  plLbound[0] = 0;
  v35 = SafeArrayGetLBound(v16, 1u, plLbound);
  if ( v35 < 0 )
    ATL::BaseAtlThrow(v35);
  if ( plLbound[0] > 8 )
    goto LABEL_234;
  plUbound[0] = 0;
  v36 = SafeArrayGetUBound(v16, 1u, plUbound);
  if ( v36 < 0 )
    ATL::BaseAtlThrow(v36);
  if ( plUbound[0] < 8 )
LABEL_234:
    ATL::BaseAtlThrow(-2147024809);
  *((float *)v16->pvData + 8 - plLbound[0]) = v128[8];
  v37 = *(__int64 (__fastcall **)(struct IShader *, const wchar_t *, __int128 *))(*(_QWORD *)a6 + 104LL);
  rgsabound = 0;
  Vartype = SafeArrayCopy(v16, (SAFEARRAY **)&rgsabound);
  if ( Vartype < 0 )
    goto LABEL_53;
  Vartype = SafeArrayGetVartype(v16, &pvt.vt);
  vt = pvt.vt;
  if ( Vartype >= 0 && pvt.vt == 13 && (v16->fFeatures & 0x440) == 0x440 )
    vt = 9;
  if ( Vartype < 0 )
  {
LABEL_53:
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
  v129 = *(_OWORD *)&pvt.vt;
  v130[0] = pvt.pRecInfo;
  v40 = v37(a6, L"colorTransformationMatrix", &v129);
  VariantClear(&pvt);
  if ( v40 < 0 )
    ATL::BaseAtlThrow(v40);
  v118 = 0;
  if ( !*((_DWORD *)this + 62) && !*((_DWORD *)this + 66) && !*((_DWORD *)this + 70) )
  {
    v113 = 0;
    goto LABEL_86;
  }
  v113 = 1;
  rgsabound = 0;
  *(_QWORD *)plLbound = qword_1806A3230;
  v41 = 0;
  *(_QWORD *)plUbound = 0;
  v42 = (__int64 *)((char *)this + 1008);
  v43 = *((_QWORD *)this + 126);
  if ( !v43 )
    goto LABEL_68;
  v44 = (*(__int64 (__fastcall **)(_QWORD, __int64, LONG *))(*(_QWORD *)v43 + 56LL))(
          *((_QWORD *)this + 126),
          1,
          plUbound);
  if ( v44 <= -1 )
    ATL::BaseAtlThrow(v44);
  v41 = *(_QWORD *)plUbound;
  if ( !*(_QWORD *)plUbound )
    goto LABEL_68;
  v105 = plLbound;
  if ( (*(int (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)plUbound + 88LL))(*(_QWORD *)plUbound, 0, 8) < 0
    || *(_QWORD *)plLbound != qword_1806A3230 )
  {
    v41 = *(_QWORD *)plUbound;
LABEL_68:
    v45 = v118;
    if ( v118 )
    {
      v118 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v45 + 16LL))(v45);
      v41 = *(_QWORD *)plUbound;
    }
    if ( v41 )
    {
      *(_QWORD *)plUbound = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v41 + 16LL))(v41);
    }
    v46 = *v42;
    if ( *v42 )
    {
      *v42 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v46 + 16LL))(v46);
    }
    ColorManagementEffect::PrepareBigBuffer<PixelRGBA32F>(
      (_DWORD)this,
      (unsigned int)plUbound,
      *((_QWORD *)this + 30),
      *((_DWORD *)this + 62),
      *((_QWORD *)this + 32),
      *((_DWORD *)this + 66),
      *((_QWORD *)this + 34),
      *((_DWORD *)this + 70));
    v115 = 0;
    v47 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, SAFEARRAYBOUND, _QWORD, unsigned __int64 *))(**(_QWORD **)plUbound + 128LL))(
            *(_QWORD *)plUbound,
            8,
            0,
            rgsabound,
            *(_QWORD *)plLbound,
            &v115);
    if ( v47 < 0 )
      ATL::BaseAtlThrow(v47);
    v48 = *(_QWORD *)plUbound;
    v49 = v115;
    if ( *(_QWORD *)plUbound != v115 )
    {
      v50 = v115;
      if ( v115 )
      {
        (*(void (**)(void))(*(_QWORD *)v115 + 8LL))();
        v48 = *(_QWORD *)plUbound;
        v49 = v115;
      }
      v51 = v48;
      v48 = v50;
      *(_QWORD *)plUbound = v50;
      if ( v51 )
      {
        (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v51 + 16LL))(v51);
        v48 = *(_QWORD *)plUbound;
        v49 = v115;
      }
    }
    if ( v49 )
    {
      (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v49 + 16LL))(v49);
      v48 = *(_QWORD *)plUbound;
    }
    v52 = (*(__int64 (__fastcall **)(unsigned __int64, char *))(*(_QWORD *)v48 + 104LL))(v48, (char *)this + 1008);
    if ( v52 < 0 )
      ATL::BaseAtlThrow(v52);
    v105 = plLbound;
    v53 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64))(**(_QWORD **)plUbound + 88LL))(*(_QWORD *)plUbound, 0, 8);
    if ( v53 < 0 )
      ATL::BaseAtlThrow(v53);
  }
  if ( *(_QWORD *)plUbound )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)plUbound + 16LL))(*(_QWORD *)plUbound);
LABEL_86:
  v117 = 0;
  if ( *((_DWORD *)this + 154) || *((_DWORD *)this + 158) || *((_DWORD *)this + 162) )
  {
    v111 = 1;
    v54 = 1;
    if ( (_DWORD)v131 == 1 )
      goto LABEL_92;
  }
  else
  {
    v111 = 0;
  }
  v54 = 0;
LABEL_92:
  v55 = 0;
  v56 = 0;
  v114 = 0;
  v57 = (__int64 *)((char *)this + 1016);
  v58 = *((_QWORD *)this + 127);
  if ( v58 )
  {
    v59 = (*(__int64 (__fastcall **)(_QWORD, __int64, SAFEARRAYBOUND *))(*(_QWORD *)v58 + 56LL))(
            *((_QWORD *)this + 127),
            1,
            &v114);
    if ( v59 <= -1 )
      ATL::BaseAtlThrow(v59);
    v56 = v114;
    if ( v114 )
    {
      v129 = 0;
      v130[0] = 0;
      LODWORD(v130[1]) = 0;
      v60 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, __int128 *))(**(_QWORD **)&v114 + 56LL))(v114, &v129);
      if ( v60 < 0 )
        ATL::BaseAtlThrow(v60);
      if ( (_DWORD)qword_1806A3230 != HIDWORD(v130[0]) || (v55 = 1, HIDWORD(qword_1806A3230) != LODWORD(v130[1])) )
        v55 = 0;
      v56 = v114;
    }
  }
  if ( v54 && !v55 )
    v8 = 1;
  if ( v111 )
  {
    v115 = 0;
    v61 = qword_1806A3230;
    if ( v8 )
      v61 = qword_1806A3238;
    rgsabound = (SAFEARRAYBOUND)v61;
    *(_QWORD *)plUbound = v61;
    v129 = 0;
    v130[0] = 0;
    LODWORD(v130[1]) = 0;
    if ( v56 )
    {
      if ( (*(int (__fastcall **)(SAFEARRAYBOUND, __int128 *))(**(_QWORD **)&v56 + 56LL))(v56, &v129) >= 0 )
      {
        lLbound = rgsabound.lLbound;
        if ( __PAIR64__(rgsabound.lLbound, v61) == *(_QWORD *)((char *)v130 + 4) )
        {
          v105 = plUbound;
          if ( (*(int (__fastcall **)(SAFEARRAYBOUND, _QWORD, __int64))(**(_QWORD **)&v114 + 88LL))(v114, 0, 8) >= 0
            && plUbound[0] == (_DWORD)v61
            && plUbound[1] == lLbound )
          {
            goto LABEL_132;
          }
        }
      }
      v56 = v114;
    }
    v63 = v117;
    if ( v117 )
    {
      v117 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v63 + 16LL))(v63);
      v56 = v114;
    }
    if ( v56 )
    {
      v114 = 0;
      (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v56 + 16LL))(v56);
    }
    v64 = *v57;
    if ( *v57 )
    {
      *v57 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v64 + 16LL))(v64);
    }
    v65 = *((_DWORD *)this + 154);
    v108 = *((_DWORD *)this + 162);
    v107 = *((_QWORD *)this + 80);
    v106 = *((_DWORD *)this + 158);
    v104 = *((_QWORD *)this + 78);
    v66 = *((_QWORD *)this + 76);
    if ( v8 )
      ColorManagementEffect::PrepareSmallBuffer<PixelRGBA32F>(
        (_DWORD)this,
        (unsigned int)&v114,
        v66,
        v65,
        v104,
        v106,
        v107,
        v108);
    else
      ColorManagementEffect::PrepareBigBuffer<PixelRGBA32F>(
        (_DWORD)this,
        (unsigned int)&v114,
        v66,
        v65,
        v104,
        v106,
        v107,
        v108);
    rgsabound = 0;
    v67 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, __int64, _QWORD, unsigned __int64, _QWORD, SAFEARRAYBOUND *))(**(_QWORD **)&v114 + 128LL))(
            v114,
            8,
            0,
            v115,
            *(_QWORD *)plUbound,
            &rgsabound);
    if ( v67 < 0 )
      ATL::BaseAtlThrow(v67);
    v68 = v114;
    v69 = rgsabound;
    if ( v114 != rgsabound )
    {
      v70 = rgsabound;
      if ( rgsabound )
      {
        (*(void (**)(void))(**(_QWORD **)&rgsabound + 8LL))();
        v68 = v114;
        v69 = rgsabound;
      }
      v71 = v68;
      v68 = v70;
      v114 = v70;
      if ( v71 )
      {
        (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v71 + 16LL))(v71);
        v68 = v114;
        v69 = rgsabound;
      }
    }
    if ( v69 )
    {
      (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v69 + 16LL))(v69);
      v68 = v114;
    }
    v72 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, char *))(**(_QWORD **)&v68 + 104LL))(v68, (char *)this + 1016);
    if ( v72 < 0 )
      ATL::BaseAtlThrow(v72);
    v105 = plUbound;
    v73 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, _QWORD, __int64))(**(_QWORD **)&v114 + 88LL))(v114, 0, 8);
    if ( v73 <= -1 )
      ATL::BaseAtlThrow(v73);
  }
LABEL_132:
  v74 = 0;
  *(_QWORD *)plLbound = 0;
  v75 = 0;
  v125 = 0;
  v76 = v116;
  if ( v120 )
  {
    v116 = *(int **)v116;
    v77 = v76[3] - (__int64)v76[1];
    if ( (unsigned __int64)(v77 + 0x80000000LL) > 0xFFFFFFFF
      || (v78 = v76[2] - (__int64)*v76, (unsigned __int64)(v78 + 0x80000000LL) > 0xFFFFFFFF) )
    {
      safeint_exception_handlers::SafeInt_InvalidParameter::SafeIntOnOverflow();
    }
    v115 = __PAIR64__(v77, v78);
    rgsabound = 0;
    v105 = (LONG *)&v115;
    v79 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, int **))(*(_QWORD *)v120 + 88LL))(
            v120,
            1,
            a5,
            0,
            &v116);
    if ( v79 < 0 )
      ATL::BaseAtlThrow(v79);
    v75 = 0;
    *(_QWORD *)plUbound = 0;
    v74 = rgsabound;
    if ( rgsabound )
    {
      v80 = (*(__int64 (__fastcall **)(SAFEARRAYBOUND, _QWORD, LONG *))(**(_QWORD **)&rgsabound + 80LL))(
              rgsabound,
              0,
              plUbound);
      if ( v80 <= -1 )
        ATL::BaseAtlThrow(v80);
      v74 = rgsabound;
      v75 = *(_QWORD *)plUbound;
    }
    *(SAFEARRAYBOUND *)plLbound = v74;
    v125 = v75;
  }
  rgsabound = 0;
  v116 = 0;
  DenoiserRenderEffect::GetLockAndTexture(v122, 0, v131, (_DWORD)v76, (__int64)&rgsabound, (_DWORD)v105, (__int64)&v116);
  v119 = 0;
  if ( v117 )
  {
    v81 = (*(__int64 (__fastcall **)(__int64, _QWORD, unsigned __int64 *))(*(_QWORD *)v117 + 80LL))(v117, 0, &v119);
    if ( v81 <= -1 )
      ATL::BaseAtlThrow(v81);
  }
  v121 = 0;
  if ( v118 )
  {
    v82 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v118 + 80LL))(v118, 0, &v121);
    if ( v82 <= -1 )
      ATL::BaseAtlThrow(v82);
  }
  v83 = v116;
  v84 = (*(__int64 (__fastcall **)(struct IShader *, _QWORD, const wchar_t *, int *))(*(_QWORD *)a6 + 112LL))(
          a6,
          0,
          L"Input0",
          v116);
  if ( v84 < 0 )
    ATL::BaseAtlThrow(v84);
  v85 = (*(__int64 (__fastcall **)(struct IShader *, __int64, const wchar_t *, unsigned __int64))(*(_QWORD *)a6 + 112LL))(
          a6,
          0xFFFFFFFFLL,
          L"CurveTexture1",
          v119);
  if ( v85 < 0 )
    ATL::BaseAtlThrow(v85);
  v86 = (*(__int64 (__fastcall **)(struct IShader *, __int64, const wchar_t *, __int64))(*(_QWORD *)a6 + 112LL))(
          a6,
          0xFFFFFFFFLL,
          L"CurveTexture2",
          v121);
  if ( v86 < 0 )
    ATL::BaseAtlThrow(v86);
  if ( v8 || (v87 = L"X", (unsigned int)(v131 - 1) <= 1) )
    v87 = &psz;
  v88 = Base::String::String((Base::String *)&v126, L"ColorManagementEffect");
  v89 = L"C";
  if ( v8 )
    v89 = L"T";
  v90 = L"L";
  v91 = L"L";
  if ( v111 )
    v91 = v89;
  v92 = ATL::operator+(plUbound, v88, v91);
  if ( v113 )
    v90 = L"C";
  v93 = ATL::operator+(&v115, v92, v90);
  v94 = (const wchar_t **)ATL::operator+(&v122, v93, v87);
  Base::String::String((Base::String *)&v124, *v94);
  v95 = (_QWORD *)(v122 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v122 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v95 + 8LL))(*v95);
  v96 = (_QWORD *)(v115 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v115 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v96 + 8LL))(*v96);
  v97 = (_QWORD *)(*(_QWORD *)plUbound - 24LL);
  if ( _InterlockedDecrement((volatile signed __int32 *)(*(_QWORD *)plUbound - 24LL + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v97 + 8LL))(*v97);
  v98 = (_QWORD *)(v126 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v126 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v98 + 8LL))(*v98);
  v99 = (*(__int64 (__fastcall **)(struct IShader *, __int64))(*(_QWORD *)a6 + 88LL))(a6, v124);
  if ( v99 < 0 )
    ATL::BaseAtlThrow(v99);
  v100 = (*(__int64 (__fastcall **)(struct IShader *, __int64))(*(_QWORD *)a6 + 120LL))(a6, v75);
  if ( v100 < 0 )
    ATL::BaseAtlThrow(v100);
  v101 = v120;
  v120 = 0;
  *v127 = v101;
  v102 = (_QWORD *)(v124 - 24);
  if ( _InterlockedDecrement((volatile signed __int32 *)(v124 - 24 + 16)) <= 0 )
    (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v102 + 8LL))(*v102);
  if ( v121 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v121 + 16LL))(v121);
  if ( v119 )
    (*(void (__fastcall **)(unsigned __int64))(*(_QWORD *)v119 + 16LL))(v119);
  if ( v83 )
    (*(void (__fastcall **)(int *))(*(_QWORD *)v83 + 16LL))(v83);
  if ( rgsabound )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&rgsabound + 16LL))(rgsabound);
  if ( v75 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v75 + 16LL))(v75);
  if ( v74 )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v74 + 16LL))(v74);
  if ( v114 )
    (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v114 + 16LL))(v114);
  if ( v117 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v117 + 16LL))(v117);
  if ( v118 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v118 + 16LL))(v118);
  result = SafeArrayUnlock(v16);
  if ( result >= 0 )
    result = SafeArrayDestroy(v16);
  if ( v120 )
    return (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v120 + 16LL))(v120);
  return result;
}

```

## disassembly

```asm
0x1801ed5c0  push    rbp
0x1801ed5c2  push    rbx
0x1801ed5c3  push    rsi
0x1801ed5c4  push    rdi
0x1801ed5c5  push    r12
0x1801ed5c7  push    r13
0x1801ed5c9  push    r14
0x1801ed5cb  push    r15
0x1801ed5cd  lea     rbp, [rsp-0B8h]
0x1801ed5d5  sub     rsp, 1B8h
0x1801ed5dc  mov     rax, cs:__security_cookie
0x1801ed5e3  xor     rax, rsp
0x1801ed5e6  mov     [rbp+0F0h+var_50], rax
0x1801ed5ed  mov     rbx, r9
0x1801ed5f0  mov     [rbp+0F0h+var_168], rbx
0x1801ed5f4  mov     [rbp+0F0h+var_100], r8
0x1801ed5f8  mov     rdi, rdx
0x1801ed5fb  mov     [rbp+0F0h+var_138], rdx
0x1801ed5ff  mov     rsi, rcx
0x1801ed602  mov     r13, [rbp+0F0h+arg_28]
0x1801ed609  xor     r15d, r15d
0x1801ed60c  mov     [rbp+0F0h+var_148], r15
0x1801ed610  mov     r10, [rcx+80h]
0x1801ed617  mov     rax, [r10]
0x1801ed61a  mov     r11, [rax+0F8h]
0x1801ed621  movsxd  rax, dword ptr [r9+4]
0x1801ed625  movsxd  rdx, dword ptr [r9+0Ch]
0x1801ed629  sub     rdx, rax
0x1801ed62c  mov     r8d, 80000000h
0x1801ed632  lea     rax, [rdx+r8]
0x1801ed636  mov     r9d, 0FFFFFFFFh
0x1801ed63c  cmp     rax, r9
0x1801ed63f  ja      loc_1801EE6D6
0x1801ed645  movsxd  rax, dword ptr [rbx]
0x1801ed648  movsxd  rcx, dword ptr [rbx+8]
0x1801ed64c  sub     rcx, rax
0x1801ed64f  lea     rax, [r8+rcx]
0x1801ed653  cmp     rax, r9
0x1801ed656  ja      loc_1801EE6D6
0x1801ed65c  mov     dword ptr [rbp+0F0h+var_150], ecx
0x1801ed65f  mov     dword ptr [rbp+0F0h+var_150+4], edx
0x1801ed662  lea     rax, [rbp+0F0h+var_148]
0x1801ed666  mov     qword ptr [rsp+1F0h+var_1B8], rax
0x1801ed66b  mov     dword ptr [rsp+1F0h+var_1C0], r15d
0x1801ed670  lea     r14d, [r15+4]
0x1801ed674  mov     dword ptr [rsp+1F0h+var_1C8], r14d
0x1801ed679  mov     dword ptr [rsp+1F0h+var_1D0], r15d
0x1801ed67e  mov     r9d, [rbp+0F0h+arg_20]
0x1801ed685  mov     r8, [rbp+0F0h+var_150]
0x1801ed689  mov     rdx, [rbx]
0x1801ed68c  mov     rcx, r10
0x1801ed68f  mov     rax, r11
0x1801ed692  call    cs:__guard_dispatch_icall_fptr
0x1801ed698  test    eax, eax
0x1801ed69a  js      loc_1801EE6C0
0x1801ed6a0  xorps   xmm0, xmm0
0x1801ed6a3  xor     eax, eax
0x1801ed6a5  movups  [rbp+0F0h+var_70], xmm0
0x1801ed6ac  mov     [rbp+0F0h+var_60], rax
0x1801ed6b3  mov     [rbp+0F0h+var_58], eax
0x1801ed6b9  mov     rax, [rdi]
0x1801ed6bc  lea     rdx, [rbp+0F0h+var_70]
0x1801ed6c3  mov     rcx, rdi
0x1801ed6c6  mov     rax, [rax+38h]
0x1801ed6ca  call    cs:__guard_dispatch_icall_fptr
0x1801ed6d0  test    eax, eax
0x1801ed6d2  js      loc_1801EE867
0x1801ed6d8  mov     rdx, r13; struct IShader *
0x1801ed6db  mov     rcx, rsi; this
0x1801ed6de  call    ?SetGammas@ColorManagementEffect@@AEBAXPEAUIShader@@@Z; ColorManagementEffect::SetGammas(IShader *)
0x1801ed6e3  lea     r8, [rsi+340h]
0x1801ed6ea  lea     rcx, [rsi+1E8h]
0x1801ed6f1  lea     rdx, [rbp+0F0h+var_F0]
0x1801ed6f5  call    ??DCMatrix3X3@@QEBA?AV0@AEBV0@@Z; CMatrix3X3::operator*(CMatrix3X3 const &)
0x1801ed6fa  mov     qword ptr [rsp+1F0h+rgsabound.cElements], 9
0x1801ed703  mov     ecx, r14d; vt
0x1801ed706  lea     r8, [rsp+1F0h+rgsabound]; rgsabound
0x1801ed70b  lea     r12d, [r15+1]
0x1801ed70f  mov     edx, r12d; cDims
0x1801ed712  call    cs:__imp_SafeArrayCreate
0x1801ed718  mov     rbx, rax
0x1801ed71b  mov     [rbp+0F0h+var_A0], rax
0x1801ed71f  test    rax, rax
0x1801ed722  jnz     short loc_1801ED72B
0x1801ed724  mov     eax, 8007000Eh
0x1801ed729  jmp     short loc_1801ED734
0x1801ed72b  mov     rcx, rbx; psa
0x1801ed72e  call    cs:__imp_SafeArrayLock
0x1801ed734  test    eax, eax
0x1801ed736  js      loc_1801EE6DC
0x1801ed73c  test    rbx, rbx
0x1801ed73f  jz      loc_1801EE6E7
0x1801ed745  mov     [rsp+1F0h+plLbound], r15d
0x1801ed74a  lea     r8, [rsp+1F0h+plLbound]; plLbound
0x1801ed74f  mov     edx, r12d; nDim
0x1801ed752  mov     rcx, rbx; psa
0x1801ed755  call    cs:__imp_SafeArrayGetLBound
0x1801ed75b  test    eax, eax
0x1801ed75d  js      loc_1801EE6F2
0x1801ed763  movsxd  rdi, [rsp+1F0h+plLbound]
0x1801ed768  test    edi, edi
0x1801ed76a  jg      loc_1801EE859
0x1801ed770  mov     [rsp+1F0h+plLbound], r15d
0x1801ed775  lea     r8, [rsp+1F0h+plLbound]; plUbound
0x1801ed77a  mov     edx, r12d; nDim
0x1801ed77d  mov     rcx, rbx; psa
0x1801ed780  call    cs:__imp_SafeArrayGetUBound
0x1801ed786  test    eax, eax
0x1801ed788  js      loc_1801EE6FA
0x1801ed78e  cmp     [rsp+1F0h+plLbound], r15d
0x1801ed793  jl      loc_1801EE859
0x1801ed799  movsd   xmm0, [rbp+0F0h+var_F0]
0x1801ed79e  cvtpd2ps xmm0, xmm0
0x1801ed7a2  mov     rcx, rdi
0x1801ed7a5  shl     rcx, 2
0x1801ed7a9  mov     rax, [rbx+10h]
0x1801ed7ad  sub     rax, rcx
0x1801ed7b0  movss   dword ptr [rax], xmm0
0x1801ed7b4  mov     [rsp+1F0h+plLbound], r15d
0x1801ed7b9  lea     r8, [rsp+1F0h+plLbound]; plLbound
0x1801ed7be  mov     edx, r12d; nDim
0x1801ed7c1  mov     rcx, rbx; psa
0x1801ed7c4  call    cs:__imp_SafeArrayGetLBound
0x1801ed7ca  test    eax, eax
0x1801ed7cc  js      loc_1801EE702
0x1801ed7d2  cmp     [rsp+1F0h+plLbound], r12d
0x1801ed7d7  jg      loc_1801EE859
0x1801ed7dd  mov     [rsp+1F0h+plUbound], r15d
0x1801ed7e2  lea     r8, [rsp+1F0h+plUbound]; plUbound
0x1801ed7e7  mov     edx, r12d; nDim
0x1801ed7ea  mov     rcx, rbx; psa
0x1801ed7ed  call    cs:__imp_SafeArrayGetUBound
0x1801ed7f3  test    eax, eax
0x1801ed7f5  js      loc_1801EE70A
0x1801ed7fb  cmp     [rsp+1F0h+plUbound], r12d
0x1801ed800  jl      loc_1801EE859
0x1801ed806  movsd   xmm0, [rbp+0F0h+var_E8]
0x1801ed80b  cvtpd2ps xmm0, xmm0
0x1801ed80f  mov     eax, r12d
0x1801ed812  sub     eax, [rsp+1F0h+plLbound]
0x1801ed816  movsxd  rcx, eax
0x1801ed819  mov     rax, [rbx+10h]
0x1801ed81d  movss   dword ptr [rax+rcx*4], xmm0
0x1801ed822  mov     [rsp+1F0h+plLbound], r15d
0x1801ed827  lea     r8, [rsp+1F0h+plLbound]; plLbound
0x1801ed82c  mov     edx, r12d; nDim
0x1801ed82f  mov     rcx, rbx; psa
0x1801ed832  call    cs:__imp_SafeArrayGetLBound
0x1801ed838  test    eax, eax
0x1801ed83a  js      loc_1801EE712
0x1801ed840  mov     edi, 2
0x1801ed845  cmp     [rsp+1F0h+plLbound], edi
0x1801ed849  jg      loc_1801EE859
0x1801ed84f  mov     [rsp+1F0h+plUbound], r15d
0x1801ed854  lea     r8, [rsp+1F0h+plUbound]; plUbound
0x1801ed859  mov     edx, r12d; nDim
0x1801ed85c  mov     rcx, rbx; psa
0x1801ed85f  call    cs:__imp_SafeArrayGetUBound
0x1801ed865  test    eax, eax
0x1801ed867  js      loc_1801EE71A
0x1801ed86d  cmp     [rsp+1F0h+plUbound], edi
0x1801ed871  jl      loc_1801EE859
0x1801ed877  movsd   xmm0, [rbp+0F0h+var_E0]
0x1801ed87c  cvtpd2ps xmm0, xmm0
0x1801ed880  sub     edi, [rsp+1F0h+plLbound]
0x1801ed884  movsxd  rcx, edi
0x1801ed887  mov     rax, [rbx+10h]
0x1801ed88b  movss   dword ptr [rax+rcx*4], xmm0
0x1801ed890  mov     [rsp+1F0h+plLbound], r15d
0x1801ed895  lea     r8, [rsp+1F0h+plLbound]; plLbound
0x1801ed89a  mov     edx, r12d; nDim
0x1801ed89d  mov     rcx, rbx; psa
0x1801ed8a0  call    cs:__imp_SafeArrayGetLBound
0x1801ed8a6  test    eax, eax
0x1801ed8a8  js      loc_1801EE722
0x1801ed8ae  mov     edi, 3
0x1801ed8b3  cmp     [rsp+1F0h+plLbound], edi
0x1801ed8b7  jg      loc_1801EE859
0x1801ed8bd  mov     [rsp+1F0h+plUbound], r15d
0x1801ed8c2  lea     r8, [rsp+1F0h+plUbound]; plUbound
0x1801ed8c7  mov     edx, r12d; nDim
0x1801ed8ca  mov     rcx, rbx; psa
0x1801ed8cd  call    cs:__imp_SafeArrayGetUBound
0x1801ed8d3  test    eax, eax
0x1801ed8d5  js      loc_1801EE72A
0x1801ed8db  cmp     [rsp+1F0h+plUbound], edi
0x1801ed8df  jl      loc_1801EE859
0x1801ed8e5  movsd   xmm0, [rbp+0F0h+var_D8]
0x1801ed8ea  cvtpd2ps xmm0, xmm0
0x1801ed8ee  sub     edi, [rsp+1F0h+plLbound]
0x1801ed8f2  movsxd  rcx, edi
0x1801ed8f5  mov     rax, [rbx+10h]
0x1801ed8f9  movss   dword ptr [rax+rcx*4], xmm0
0x1801ed8fe  mov     [rsp+1F0h+plLbound], r15d
0x1801ed903  lea     r8, [rsp+1F0h+plLbound]; plLbound
0x1801ed908  mov     edx, r12d; nDim
0x1801ed90b  mov     rcx, rbx; psa
0x1801ed90e  call    cs:__imp_SafeArrayGetLBound
0x1801ed914  test    eax, eax
0x1801ed916  js      loc_1801EE732
0x1801ed91c  cmp     [rsp+1F0h+plLbound], r14d
0x1801ed921  jg      loc_1801EE859
0x1801ed927  mov     [rsp+1F0h+plUbound], r15d
0x1801ed92c  lea     r8, [rsp+1F0h+plUbound]; plUbound
0x1801ed931  mov     edx, r12d; nDim
0x1801ed934  mov     rcx, rbx; psa
0x1801ed937  call    cs:__imp_SafeArrayGetUBound
0x1801ed93d  test    eax, eax
0x1801ed93f  js      loc_1801EE73A
0x1801ed945  cmp     [rsp+1F0h+plUbound], r14d
0x1801ed94a  jl      loc_1801EE859
0x1801ed950  movsd   xmm0, [rbp+0F0h+var_D0]
0x1801ed955  cvtpd2ps xmm0, xmm0
0x1801ed959  sub     r14d, [rsp+1F0h+plLbound]
0x1801ed95e  movsxd  rcx, r14d
0x1801ed961  mov     rax, [rbx+10h]
0x1801ed965  movss   dword ptr [rax+rcx*4], xmm0
0x1801ed96a  mov     [rsp+1F0h+plLbound], r15d
0x1801ed96f  lea     r8, [rsp+1F0h+plLbound]; plLbound
0x1801ed974  mov     edx, r12d; nDim
0x1801ed977  mov     rcx, rbx; psa
0x1801ed97a  call    cs:__imp_SafeArrayGetLBound
0x1801ed980  test    eax, eax
0x1801ed982  js      loc_1801EE742
0x1801ed988  mov     edi, 5
0x1801ed98d  cmp     [rsp+1F0h+plLbound], edi
0x1801ed991  jg      loc_1801EE859
0x1801ed997  mov     [rsp+1F0h+plUbound], r15d
0x1801ed99c  lea     r8, [rsp+1F0h+plUbound]; plUbound
0x1801ed9a1  mov     edx, r12d; nDim
0x1801ed9a4  mov     rcx, rbx; psa
0x1801ed9a7  call    cs:__imp_SafeArrayGetUBound
0x1801ed9ad  test    eax, eax
0x1801ed9af  js      loc_1801EE74A
0x1801ed9b5  cmp     [rsp+1F0h+plUbound], edi
0x1801ed9b9  jl      loc_1801EE859
0x1801ed9bf  movsd   xmm0, [rbp+0F0h+var_C8]
0x1801ed9c4  cvtpd2ps xmm0, xmm0
0x1801ed9c8  sub     edi, [rsp+1F0h+plLbound]
0x1801ed9cc  movsxd  rcx, edi
0x1801ed9cf  mov     rax, [rbx+10h]
0x1801ed9d3  movss   dword ptr [rax+rcx*4], xmm0
0x1801ed9d8  mov     [rsp+1F0h+plLbound], r15d
0x1801ed9dd  lea     r8, [rsp+1F0h+plLbound]; plLbound
0x1801ed9e2  mov     edx, r12d; nDim
0x1801ed9e5  mov     rcx, rbx; psa
0x1801ed9e8  call    cs:__imp_SafeArrayGetLBound
0x1801ed9ee  test    eax, eax
0x1801ed9f0  js      loc_1801EE752
0x1801ed9f6  mov     edi, 6
0x1801ed9fb  cmp     [rsp+1F0h+plLbound], edi
0x1801ed9ff  jg      loc_1801EE859
0x1801eda05  mov     [rsp+1F0h+plUbound], r15d
0x1801eda0a  lea     r8, [rsp+1F0h+plUbound]; plUbound
0x1801eda0f  mov     edx, r12d; nDim
0x1801eda12  mov     rcx, rbx; psa
0x1801eda15  call    cs:__imp_SafeArrayGetUBound
0x1801eda1b  test    eax, eax
0x1801eda1d  js      loc_1801EE75A
0x1801eda23  cmp     [rsp+1F0h+plUbound], edi
0x1801eda27  jl      loc_1801EE859
0x1801eda2d  movsd   xmm0, [rbp+0F0h+var_C0]
0x1801eda32  cvtpd2ps xmm0, xmm0
0x1801eda36  sub     edi, [rsp+1F0h+plLbound]
0x1801eda3a  movsxd  rcx, edi
0x1801eda3d  mov     rax, [rbx+10h]
0x1801eda41  movss   dword ptr [rax+rcx*4], xmm0
0x1801eda46  mov     [rsp+1F0h+plLbound], r15d
0x1801eda4b  lea     r8, [rsp+1F0h+plLbound]; plLbound
0x1801eda50  mov     edx, r12d; nDim
0x1801eda53  mov     rcx, rbx; psa
0x1801eda56  call    cs:__imp_SafeArrayGetLBound
0x1801eda5c  test    eax, eax
0x1801eda5e  js      loc_1801EE762
0x1801eda64  mov     edi, 7
0x1801eda69  cmp     [rsp+1F0h+plLbound], edi
0x1801eda6d  jg      loc_1801EE859
0x1801eda73  mov     [rsp+1F0h+plUbound], r15d
0x1801eda78  lea     r8, [rsp+1F0h+plUbound]; plUbound
0x1801eda7d  mov     edx, r12d; nDim
0x1801eda80  mov     rcx, rbx; psa
0x1801eda83  call    cs:__imp_SafeArrayGetUBound
0x1801eda89  test    eax, eax
0x1801eda8b  js      loc_1801EE76A
0x1801eda91  cmp     [rsp+1F0h+plUbound], edi
0x1801eda95  jl      loc_1801EE859
0x1801eda9b  movsd   xmm0, [rbp+0F0h+var_B8]
0x1801edaa0  cvtpd2ps xmm0, xmm0
0x1801edaa4  sub     edi, [rsp+1F0h+plLbound]
0x1801edaa8  movsxd  rcx, edi
0x1801edaab  mov     rax, [rbx+10h]
0x1801edaaf  movss   dword ptr [rax+rcx*4], xmm0
0x1801edab4  mov     [rsp+1F0h+plLbound], r15d
0x1801edab9  lea     r8, [rsp+1F0h+plLbound]; plLbound
0x1801edabe  mov     edx, r12d; nDim
0x1801edac1  mov     rcx, rbx; psa
0x1801edac4  call    cs:__imp_SafeArrayGetLBound
0x1801edaca  test    eax, eax
0x1801edacc  js      loc_1801EE772
0x1801edad2  cmp     [rsp+1F0h+plLbound], 8
  ... truncated ...
```
