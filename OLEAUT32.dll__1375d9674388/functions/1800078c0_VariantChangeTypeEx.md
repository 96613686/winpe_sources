# VariantChangeTypeEx

- ea: `0x1800078c0`
- end: `0x180009ebd`
- name: `VariantChangeTypeEx`
- size: `9725`
- prototype: `HRESULT __stdcall(VARIANTARG *pvargDest, const VARIANTARG *pvarSrc, LCID lcid, USHORT wFlags, VARTYPE vt)`
- caller_count: `21`
- callee_count: `74`
- tags: `installer_update`

## callers

- `0x180007890`
- `0x18000ced0`
- `0x180018b80`
- `0x18002620c`
- `0x1800264d4`
- `0x180026a04`
- `0x180027ef0`
- `0x18002a10c`
- `0x18002e040`
- `0x1800302d4`
- `0x180033120`
- `0x180035d50`
- `0x18003a480`
- `0x18003bdd0`
- `0x180070594`
- `0x180070880`
- `0x180071afc`
- `0x180072be0`
- `0x180075200`
- `0x1800758b0`
- `0x180075d50`

## callees

- `0x180002c80`
- `0x180002d20`
- `0x180002e40`
- `0x1800039b8`
- `0x180003ee0`
- `0x1800042d0`
- `0x180004730`
- `0x180004890`
- `0x180005cb0`
- `0x1800070b0`
- `0x180007150`
- `0x180007260`
- `0x180007310`
- `0x1800075f0`
- `0x1800076d0`
- `0x180007778`
- `0x180007840`
- `0x1800078c0`
- `0x18000a830`
- `0x18000a920`
- `0x18000c480`
- `0x18001c520`
- `0x18001f8f0`
- `0x18001fa50`
- `0x180020860`
- `0x180027c44`
- `0x18002a8c0`
- `0x18002e800`
- `0x180030160`
- `0x180030c40`
- `0x180034510`
- `0x180034660`
- `0x180035810`
- `0x180035940`
- `0x180037b60`
- `0x180038550`
- `0x180038cf0`
- `0x18003d108`
- `0x18003d310`
- `0x18003d350`
- `0x18003da00`
- `0x18003da40`
- `0x18003f150`
- `0x1800405a0`
- `0x1800408e0`
- `0x180041708`
- `0x1800418a0`
- `0x180043df0`
- `0x180044610`
- `0x180047460`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800094db`
- `api-ms-win-crt-private-l1-1-0!_o__itow_s` at `0x1800094db`
- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x1800094f3`
- `api-ms-win-crt-private-l1-1-0!_o__ltow_s` at `0x1800094f3`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180007b73`
- `api-ms-win-core-localization-l1-2-0!GetUserDefaultLCID` at `0x180007b73`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180007d2b`
- `api-ms-win-core-localization-l1-2-0!GetSystemDefaultLCID` at `0x180007d2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007a2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009230`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180007a2b`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180009230`

## pseudocode

```c
HRESULT __stdcall VariantChangeTypeEx(
        VARIANTARG *pvargDest,
        const VARIANTARG *pvarSrc,
        LCID lcid,
        USHORT wFlags,
        VARTYPE vt)
{
  int v5; // r13d
  const VARIANTARG *pvarVal; // r14
  unsigned __int16 uiVal; // r12
  signed int ValueProperty; // edi
  ULONG v10; // esi
  LCID UserDefaultLCID; // eax
  __int64 v12; // r9
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  BSTR bstrVal; // r14
  unsigned int v17; // esi
  int v18; // edi
  APP_DATA *Value; // rax
  IRecordInfo *v21; // rax
  IRecordInfo *v22; // rdi
  bool v23; // cf
  IRecordInfo *v24; // xmm1_8
  unsigned __int64 v25; // rcx
  __int64 v26; // rax
  unsigned int v27; // r8d
  char *v28; // rcx
  unsigned int v29; // eax
  OLECHAR *v30; // rdx
  OLECHAR v31; // ax
  const OLECHAR *v32; // rcx
  BYTE *v33; // r10
  INT cDig; // edx
  int v35; // r8d
  int v36; // r9d
  int v37; // eax
  unsigned int Lo; // ecx
  char *v39; // r8
  unsigned int v40; // r9d
  unsigned int v41; // eax
  NUMPARSE *p_pnumprs; // rcx
  __int16 v43; // ax
  __int16 v44; // r10
  __int16 v45; // r11
  const OLECHAR *v46; // rcx
  __int64 v47; // rcx
  HRESULT valid; // eax
  const OLECHAR *v49; // rcx
  unsigned int v50; // eax
  SHORT cVal; // cx
  LONGLONG v52; // rcx
  double dblVal; // xmm0_8
  __int64 (__fastcall ***v54)(_QWORD, GUID *, DECIMAL *, __int64); // rcx
  double v55; // xmm0_8
  const OLECHAR *v56; // rcx
  unsigned __int64 ullVal; // rax
  double v58; // xmm0_8
  unsigned int v59; // ecx
  int v60; // eax
  int lVal; // ecx
  int v62; // eax
  int iVal; // eax
  SHORT v64; // dx
  int v65; // ecx
  LONGLONG v66; // rcx
  __int64 v67; // rax
  unsigned __int64 v68; // rax
  double v69; // xmm0_8
  double fltVal; // xmm0_8
  double v71; // xmm1_8
  double v72; // xmm0_8
  bool v73; // zf
  __int16 v74; // ax
  double v75; // xmm0_8
  double v76; // xmm1_8
  double v77; // xmm0_8
  double v78; // xmm0_8
  double v79; // xmm1_8
  CY cyVal; // rcx
  LONGLONG llVal; // rax
  CY v82; // rcx
  CY v83; // rcx
  CY v84; // rcx
  double v85; // xmm0_8
  double v86; // xmm0_8
  double v87; // xmm0_8
  double v88; // xmm0_8
  double v89; // xmm1_8
  __int64 (__fastcall ***v90)(_QWORD, GUID *, DECIMAL *, __int64); // rcx
  const OLECHAR *v91; // rcx
  __int16 v92; // dx
  int v93; // ecx
  int v94; // ecx
  unsigned __int64 v95; // rdx
  int v96; // eax
  SHORT v97; // ax
  __int64 v98; // rcx
  int v99; // eax
  SAFEARRAY *parray; // r14
  SAFEARRAY *v101; // rsi
  USHORT fFeatures; // ax
  __int64 cDims; // rdi
  char *v104; // rax
  char *v105; // rsi
  __int64 v106; // rax
  bool v107; // zf
  double v108; // xmm1_8
  _BYTE *v109; // r10
  __int64 v110; // rcx
  float v111; // xmm0_4
  __int64 v112; // rax
  __int64 v113; // rcx
  double v114; // xmm0_8
  __int64 v115; // rax
  __int64 v116; // rcx
  double v117; // xmm0_8
  __int64 v118; // rax
  SAFEARRAYBOUND v119; // rcx
  VARIANTARG pvargDesta; // [rsp+30h] [rbp-D8h] BYREF
  IRecordInfo *v121; // [rsp+48h] [rbp-C0h]
  SAFEARRAY *lcida; // [rsp+50h] [rbp-B8h] BYREF
  VARIANTARG pvarg; // [rsp+58h] [rbp-B0h] BYREF
  VARIANT pvar; // [rsp+70h] [rbp-98h] BYREF
  __int64 v125; // [rsp+88h] [rbp-80h]
  NUMPARSE pnumprs; // [rsp+90h] [rbp-78h] BYREF
  BYTE rgbDig[16]; // [rsp+A8h] [rbp-60h] BYREF
  BYTE v128[16]; // [rsp+B8h] [rbp-50h] BYREF
  _WORD v129[32]; // [rsp+C8h] [rbp-40h] BYREF
  _WORD v130[32]; // [rsp+108h] [rbp+0h] BYREF
  OLECHAR psz[40]; // [rsp+148h] [rbp+40h] BYREF

  v5 = wFlags;
  LODWORD(lcida) = lcid;
  v121 = 0;
  *(_QWORD *)&pvar.vt = 0;
  pvarVal = pvarSrc;
  *(_OWORD *)&pvargDesta.decVal.Lo32 = 0;
  *(_OWORD *)&pvarg.decVal.Lo32 = 0;
  if ( !pvargDest || !pvarSrc )
    return -2147024809;
  uiVal = pvarSrc->vt;
  if ( vt >= 0xCu )
  {
    v25 = vt;
    LOWORD(v25) = vt & 0x9FFF;
    if ( (vt & 0x6000) == 0 )
      LOWORD(v25) = vt;
    if ( (unsigned __int16)v25 > 0x24u )
      return -2147352568;
    v26 = 0x1000FF7FFCLL;
    if ( !_bittest64(&v26, v25) )
      return -2147352568;
    if ( (vt & 0xE000) != 0 )
    {
      if ( vt == uiVal && (vt & 0x6000) == 0x6000 )
        return VariantCopy(pvargDest, pvarSrc);
      if ( vt != 8209 )
        return -2147352571;
    }
  }
  ValueProperty = 0;
  *(_DWORD *)&pvarg.vt = 0;
  v10 = ((wFlags & 0xFFFC) << 29) | ((wFlags & 0x80) << 21);
  if ( (lcid & 0xFFFFFBFF) != 0 )
    UserDefaultLCID = lcid;
  else
    UserDefaultLCID = GetUserDefaultLCID();
  if ( UserDefaultLCID == 2048 )
    LOWORD(UserDefaultLCID) = GetSystemDefaultLCID();
  if ( (UserDefaultLCID & 0x3FF) == 0x1E )
  {
    if ( (v5 & 0x20) != 0 )
    {
      *(_DWORD *)&pvarg.vt = 128;
    }
    else if ( (v5 & 0x40) != 0 )
    {
      *(_DWORD *)&pvarg.vt = 256;
    }
  }
  while ( 1 )
  {
    v12 = 0x4000;
    v13 = vt;
LABEL_10:
    v14 = 3 * (unsigned int)uiVal;
    v15 = v13 + 24 * uiVal;
    if ( v15 != 239 )
      break;
LABEL_16:
    if ( (v5 & 1) != 0 )
      goto LABEL_17;
    ValueProperty = ExtractValueProperty(pvarVal->pdispVal, (unsigned int)lcida, (struct tagVARIANT *)&pvarg.decVal.8);
    if ( ValueProperty )
      goto LABEL_17;
    uiVal = pvarg.uiVal;
    pvarVal = (const VARIANTARG *)&pvarg.decVal.8;
  }
  if ( v15 == 1 )
    goto LABEL_27;
  if ( v15 == 200 )
  {
    bstrVal = pvarVal->bstrVal;
    if ( bstrVal )
    {
      v17 = *((_DWORD *)bstrVal - 1);
      v18 = v17 + 25;
      if ( v17 >= 0xFFFFFFE7 )
        goto LABEL_15;
    }
    else
    {
      v17 = 0;
      v18 = 25;
    }
    Value = (APP_DATA *)TlsGetValue(g_itlsAppData);
    if ( Value )
    {
LABEL_21:
      v21 = (IRecordInfo *)APP_DATA::AllocCachedMem(Value, v18 & 0xFFFFFFF0);
      v22 = v21;
      if ( v21 )
      {
        v22 = v21 + 1;
        HIDWORD(v21->lpVtbl) = v17;
        if ( bstrVal )
          memcpy_0(v22, bstrVal, v17);
        *((_BYTE *)&v22->lpVtbl + v17) = 0;
        *(_WORD *)((char *)&v22->lpVtbl + ((v17 + 1) & 0xFFFFFFFE)) = 0;
      }
      pvargDesta.pRecInfo = v22;
      if ( !v22 )
        goto LABEL_26;
      ValueProperty = 0;
    }
    else
    {
      if ( (int)InitAppData() >= 0 )
      {
        Value = (APP_DATA *)TlsGetValue(g_itlsAppData);
        goto LABEL_21;
      }
LABEL_15:
      pvargDesta.pRecInfo = 0;
LABEL_26:
      ValueProperty = -2147024882;
    }
    goto LABEL_27;
  }
  switch ( v15 )
  {
    case 0:
    case 25:
    case 48:
    case 49:
    case 72:
    case 73:
    case 96:
    case 97:
    case 120:
    case 121:
    case 144:
    case 145:
    case 168:
    case 169:
    case 192:
    case 193:
    case 216:
    case 217:
    case 264:
    case 265:
    case 312:
    case 313:
    case 336:
    case 337:
    case 384:
    case 385:
    case 408:
    case 409:
    case 432:
    case 433:
    case 456:
    case 457:
    case 480:
    case 481:
    case 504:
    case 505:
    case 528:
    case 529:
    case 552:
    case 553:
      goto LABEL_27;
    case 2:
    case 11:
    case 18:
      goto LABEL_234;
    case 3:
    case 4:
    case 19:
    case 22:
    case 23:
      *((_DWORD *)&pvargDesta.decVal + 4) = 0;
      goto LABEL_27;
    case 5:
    case 7:
      pvargDesta.pRecInfo = 0;
      goto LABEL_27;
    case 6:
    case 20:
    case 21:
      goto LABEL_372;
    case 8:
      ValueProperty = 0;
      pvargDesta.pRecInfo = (IRecordInfo *)SysAllocString(&::psz);
      if ( !pvargDesta.pRecInfo )
        ValueProperty = -2147024882;
      goto LABEL_27;
    case 14:
      pvargDesta.pRecInfo = 0;
      WORD1(pvargDesta.decVal.Lo64) = 0;
      pvargDesta.cyVal.Hi = 0;
      goto LABEL_27;
    case 16:
    case 17:
      *((_BYTE *)&pvargDesta.decVal + 16) = 0;
      goto LABEL_27;
    case 50:
    case 66:
    case 266:
    case 275:
    case 282:
    case 434:
    case 450:
      *((_WORD *)&pvargDesta.decVal + 8) = pvarVal->iVal;
      goto LABEL_27;
    case 51:
    case 70:
    case 267:
    case 283:
    case 286:
    case 287:
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->iVal;
      goto LABEL_27;
    case 52:
    case 268:
      *((float *)&pvargDesta.decVal + 4) = (float)pvarVal->iVal;
      goto LABEL_27;
    case 53:
    case 269:
      *(double *)&pvargDesta.pRecInfo = (double)pvarVal->iVal;
      goto LABEL_27;
    case 54:
    case 270:
      pvargDesta.pRecInfo = (IRecordInfo *)(10000 * pvarVal->iVal);
      goto LABEL_28;
    case 55:
    case 271:
      iVal = pvarVal->iVal;
      goto LABEL_173;
    case 56:
      goto LABEL_93;
    case 59:
    case 443:
      v107 = pvarVal->iVal == 0;
      goto LABEL_404;
    case 62:
    case 278:
      v64 = pvarVal->iVal;
      *((_DWORD *)&pvargDesta.decVal + 5) = 0;
      v65 = -v64;
      pvargDesta.cyVal.Hi = 0;
      BYTE2(pvargDesta.decVal.Lo64) = 0;
      if ( v64 > 0 )
        LOWORD(v65) = v64;
      BYTE3(pvargDesta.decVal.Lo64) = HIBYTE(v64) & 0x80;
      *((_DWORD *)&pvargDesta.decVal + 4) = (unsigned __int16)v65;
      goto LABEL_28;
    case 64:
      if ( (unsigned __int16)(pvarVal->iVal + 128) > 0xFFu )
        goto LABEL_117;
      *((_BYTE *)&pvargDesta.decVal + 16) = pvarVal->iVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 65:
      if ( pvarVal->iVal > 0xFFu )
        goto LABEL_117;
      *((_BYTE *)&pvargDesta.decVal + 16) = pvarVal->iVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 67:
    case 71:
      if ( pvarVal->iVal < 0 )
        goto LABEL_117;
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->uiVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 68:
    case 284:
    case 285:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->iVal;
      goto LABEL_27;
    case 69:
      if ( pvarVal->iVal < 0 )
        goto LABEL_117;
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->uiVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 74:
    case 530:
      v59 = pvarVal->lVal + 0x8000;
      if ( v59 <= 0xFFFF )
        *((_WORD *)&pvargDesta.decVal + 8) = pvarVal->lVal;
      v60 = 0;
      if ( v59 > 0xFFFF )
        v60 = -2147352566;
      ValueProperty = v60;
      goto LABEL_27;
    case 75:
    case 91:
    case 94:
    case 95:
    case 250:
    case 459:
    case 475:
    case 478:
    case 479:
    case 531:
    case 547:
    case 550:
    case 551:
    case 555:
    case 571:
    case 574:
    case 575:
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->lVal;
      goto LABEL_27;
    case 76:
    case 532:
      *((float *)&pvargDesta.decVal + 4) = (float)pvarVal->lVal;
      goto LABEL_27;
    case 77:
    case 533:
      *(double *)&pvargDesta.pRecInfo = (double)pvarVal->lVal;
      goto LABEL_27;
    case 78:
    case 534:
      pvargDesta.pRecInfo = (IRecordInfo *)(10000LL * pvarVal->lVal);
      goto LABEL_28;
    case 79:
    case 463:
    case 535:
    case 559:
      *(double *)&pvargDesta.pRecInfo = (double)pvarVal->lVal;
      valid = IsValidDate(*(double *)&pvargDesta.pRecInfo);
      goto LABEL_96;
    case 80:
    case 536:
      Lo = pvarVal->cyVal.Lo;
      memset(&pnumprs, 0, sizeof(pnumprs));
      if ( (((v5 & 0x80) << 21) & 0x10000000) != 0 )
      {
        _ltow_s(Lo, (wchar_t *)&pnumprs, 0xCu, 10);
        goto LABEL_408;
      }
      v39 = (char *)v129;
      v40 = Lo >> 31;
      if ( (Lo & 0x80000000) != 0 )
        Lo = -Lo;
      do
      {
        v41 = Lo % 0xA;
        Lo /= 0xAu;
        *(_WORD *)v39 = v41 + 48;
        v39 += 2;
      }
      while ( Lo );
      if ( (unsigned __int64)v40 + ((v39 - (char *)v129) >> 1) + 1 <= 0xC )
      {
        if ( v40 )
          LOWORD(pnumprs.cDig) = 45;
        p_pnumprs = &pnumprs;
        if ( v40 )
          p_pnumprs = (NUMPARSE *)((char *)&pnumprs.cDig + 2);
        do
        {
          v43 = *((_WORD *)v39 - 1);
          v39 -= 2;
          LOWORD(p_pnumprs->cDig) = v43;
          p_pnumprs = (NUMPARSE *)((char *)p_pnumprs + 2);
        }
        while ( v39 > (char *)v129 );
        LOWORD(p_pnumprs->cDig) = 0;
      }
      goto LABEL_79;
    case 83:
    case 467:
    case 539:
    case 563:
      v107 = pvarVal->lVal == 0;
      goto LABEL_404;
    case 86:
    case 542:
      lVal = pvarVal->lVal;
      v62 = -lVal;
      *((_DWORD *)&pvargDesta.decVal + 5) = 0;
      pvargDesta.cyVal.Hi = 0;
      if ( lVal > 0 )
        v62 = lVal;
      BYTE2(pvargDesta.decVal.Lo64) = 0;
      *((_DWORD *)&pvargDesta.decVal + 4) = v62;
      BYTE3(pvargDesta.decVal.Lo64) = HIBYTE(lVal) & 0x80;
      goto LABEL_28;
    case 88:
    case 544:
      if ( (unsigned int)(pvarVal->lVal + 128) > 0xFF )
        goto LABEL_117;
      *((_BYTE *)&pvargDesta.decVal + 16) = pvarVal->lVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 89:
    case 473:
    case 545:
    case 569:
      valid = VarUI1FromUI4(pvarVal->cyVal.Lo, (BYTE *)&pvargDesta.decVal + 16);
      goto LABEL_96;
    case 90:
    case 474:
    case 546:
    case 570:
      valid = VarUI2FromUI4(pvarVal->cyVal.Lo, (USHORT *)&pvargDesta.decVal + 8);
      goto LABEL_96;
    case 92:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->lVal;
      goto LABEL_27;
    case 93:
      if ( pvarVal->lVal < 0 )
        goto LABEL_117;
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->lVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 98:
      fltVal = pvarVal->fltVal;
      goto LABEL_212;
    case 99:
    case 118:
      v85 = pvarVal->fltVal;
      if ( v85 >= -2147483648.5 && v85 < 2147483647.5 )
        goto LABEL_281;
      goto LABEL_117;
    case 100:
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->lVal;
      goto LABEL_27;
    case 101:
      *(double *)&pvargDesta.pRecInfo = pvarVal->fltVal;
      goto LABEL_27;
    case 102:
      ValueProperty = VarCyFromR8(pvarVal->fltVal, (CY *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 103:
      *(double *)&pvargDesta.pRecInfo = pvarVal->fltVal;
      valid = IsValidDate(*(double *)&pvargDesta.pRecInfo);
      goto LABEL_96;
    case 104:
      ValueProperty = VarBstrFromR4(pvarVal->fltVal, (LCID)lcida, v10, (BSTR *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 107:
      v73 = pvarVal->fltVal == 0.0;
      goto LABEL_222;
    case 110:
      ValueProperty = VarDecFromR4(pvarVal->fltVal, (DECIMAL *)&pvargDesta.decVal.8);
      goto LABEL_27;
    case 112:
      v75 = pvarVal->fltVal;
      if ( v75 < -128.5 )
        goto LABEL_117;
      v76 = DOUBLE_127_5;
      goto LABEL_239;
    case 113:
      v75 = pvarVal->fltVal;
      if ( v75 < -0.5 )
        goto LABEL_117;
      v76 = DOUBLE_255_5;
LABEL_239:
      if ( v76 <= v75 )
        goto LABEL_117;
      *((_BYTE *)&pvargDesta.decVal + 16) = ConvI4FromR8(v14, v13, &_ImageBase, v12);
LABEL_288:
      ValueProperty = 0;
      goto LABEL_27;
    case 114:
      v77 = pvarVal->fltVal;
      if ( v77 < -0.5 || v77 >= 65535.5 )
        goto LABEL_117;
      *((_WORD *)&pvargDesta.decVal + 8) = ConvI4FromR8(v14, v13, &_ImageBase, v12);
      goto LABEL_288;
    case 115:
    case 119:
      v87 = pvarVal->fltVal;
      if ( v87 < -0.5 || v87 >= 4294967295.5 )
        goto LABEL_117;
      *((_DWORD *)&pvargDesta.decVal + 4) = ConvUI4FromR8(v14, v13, &_ImageBase, v12);
      goto LABEL_288;
    case 116:
      v86 = pvarVal->fltVal;
      if ( v86 >= -4.611686018427388e18 && v86 < 4.611686018427388e18 )
        goto LABEL_217;
      goto LABEL_117;
    case 117:
      v88 = pvarVal->fltVal;
      if ( v88 >= -0.5 && v88 < 1.844674407370955e19 )
        goto LABEL_142;
      goto LABEL_117;
    case 122:
    case 170:
      fltVal = pvarVal->dblVal;
LABEL_212:
      if ( fltVal < -32768.5 )
        goto LABEL_117;
      v71 = DOUBLE_32767_5;
      goto LABEL_253;
    case 123:
    case 142:
    case 171:
    case 190:
      dblVal = pvarVal->dblVal;
      if ( dblVal < -2147483648.5 || dblVal >= 2147483647.5 )
        goto LABEL_117;
LABEL_281:
      *((_DWORD *)&pvargDesta.decVal + 4) = ConvI4FromR8(v14, v13, &_ImageBase, v12);
      ValueProperty = 0;
      goto LABEL_27;
    case 124:
    case 172:
      v89 = pvarVal->dblVal;
      if ( v89 < COERCE_DOUBLE(dsR4Max ^ _xmm) || v89 > 3.402823567797336e38 )
        goto LABEL_117;
      ValueProperty = 0;
      *((float *)&pvargDesta.decVal + 4) = v89;
      goto LABEL_27;
    case 125:
    case 173:
    case 175:
      goto LABEL_139;
    case 126:
    case 174:
      ValueProperty = VarCyFromR8(pvarVal->dblVal, (CY *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 127:
      ValueProperty = IsValidDate(pvarVal->dblVal);
LABEL_139:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->llVal;
      goto LABEL_27;
    case 128:
      ValueProperty = VarBstrFromR8(pvarVal->dblVal, (LCID)lcida, v10, (BSTR *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 131:
    case 179:
      v73 = pvarVal->dblVal == 0.0;
LABEL_222:
      if ( !v73 )
        goto LABEL_223;
      goto LABEL_234;
    case 134:
    case 182:
      ValueProperty = VarDecFromR8(pvarVal->dblVal, (DECIMAL *)&pvargDesta.decVal.8);
      goto LABEL_27;
    case 136:
    case 184:
      v78 = pvarVal->dblVal;
      if ( v78 < -128.5 )
        goto LABEL_117;
      v79 = DOUBLE_127_5;
      goto LABEL_249;
    case 137:
    case 185:
      v78 = pvarVal->dblVal;
      if ( v78 < -0.5 )
        goto LABEL_117;
      v79 = DOUBLE_255_5;
LABEL_249:
      if ( v79 <= v78 )
        goto LABEL_117;
      LOBYTE(ullVal) = ConvI4FromR8(v14, v13, &_ImageBase, v12);
      goto LABEL_148;
    case 138:
    case 186:
      fltVal = pvarVal->dblVal;
      if ( fltVal < -0.5 )
        goto LABEL_117;
      v71 = DOUBLE_65535_5;
LABEL_253:
      if ( v71 <= fltVal )
        goto LABEL_117;
      LOWORD(v50) = ConvI4FromR8(v14, v13, &_ImageBase, v12);
      goto LABEL_99;
    case 139:
    case 143:
    case 187:
    case 191:
      v58 = pvarVal->dblVal;
      if ( v58 < -0.5 || v58 >= 4294967295.5 )
        goto LABEL_117;
      *((_DWORD *)&pvargDesta.decVal + 4) = ConvUI4FromR8(v14, v13, &_ImageBase, v12);
      ValueProperty = 0;
      goto LABEL_27;
    case 140:
    case 188:
      v72 = pvarVal->dblVal;
      if ( v72 < -4.611686018427388e18 || v72 >= 4.611686018427388e18 )
        goto LABEL_117;
LABEL_217:
      pvargDesta.pRecInfo = (IRecordInfo *)ConvI8FromR8(v14, v13, &_ImageBase, v12);
      ValueProperty = 0;
      goto LABEL_27;
    case 141:
    case 189:
      v55 = pvarVal->dblVal;
      if ( v55 < -0.5 || v55 >= 1.844674407370955e19 )
        goto LABEL_117;
LABEL_142:
      pvargDesta.pRecInfo = (IRecordInfo *)ConvUI8FromR8(v14, v13, &_ImageBase, v12);
      ValueProperty = 0;
      goto LABEL_27;
    case 146:
      cyVal = pvarVal->cyVal;
      LODWORD(lcida) = 0;
      ValueProperty = VarI4FromCy(cyVal, (LONG *)&lcida);
      if ( ValueProperty )
        goto LABEL_27;
      if ( (unsigned int)((_DWORD)lcida + 0x8000) > 0xFFFF )
        goto LABEL_117;
      *((_WORD *)&pvargDesta.decVal + 8) = (_WORD)lcida;
      goto LABEL_27;
    case 147:
    case 166:
      ValueProperty = VarI4FromCy(pvarVal->cyVal, (LONG *)&pvargDesta.decVal + 4);
      goto LABEL_27;
    case 148:
      *((float *)&pvargDesta.decVal + 4) = (double)(int)pvarVal->llVal / 10000.0;
      goto LABEL_28;
    case 149:
      *(double *)&pvargDesta.pRecInfo = (double)(int)pvarVal->llVal / 10000.0;
      goto LABEL_28;
    case 150:
    case 500:
    case 501:
    case 524:
    case 525:
      goto LABEL_109;
    case 151:
      v108 = (double)(int)pvarVal->llVal / 10000.0;
      if ( v108 >= 2958466.0 || v108 <= -657435.0 )
        goto LABEL_117;
      *(double *)&pvargDesta.pRecInfo = (double)(int)pvarVal->llVal / 10000.0;
      goto LABEL_66;
    case 152:
      ValueProperty = VarBstrFromCy(pvarVal->cyVal, (LCID)lcida, v10, (BSTR *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 155:
      if ( pvarVal->llVal )
        *((_WORD *)&pvargDesta.decVal + 8) = -1;
      else
        *((_WORD *)&pvargDesta.decVal + 8) = pvarVal->llVal | HIDWORD(pvarVal->llVal);
      goto LABEL_28;
    case 158:
      llVal = pvarVal->llVal;
      BYTE3(pvargDesta.decVal.Lo64) = HIBYTE(llVal) & 0x80;
      if ( llVal < 0 )
        llVal = -llVal;
      pvargDesta.pRecInfo = (IRecordInfo *)llVal;
      BYTE2(pvargDesta.decVal.Lo64) = 4;
      pvargDesta.cyVal.Hi = 0;
      goto LABEL_28;
    case 160:
      v82 = pvarVal->cyVal;
      LODWORD(lcida) = 0;
      ValueProperty = VarI4FromCy(v82, (LONG *)&lcida);
      if ( ValueProperty )
        goto LABEL_27;
      if ( (unsigned int)((_DWORD)lcida + 0x8000) > 0xFFFF )
        goto LABEL_117;
      valid = VarI1FromI2((SHORT)lcida, (CHAR *)&pvargDesta.decVal + 16);
      goto LABEL_96;
    case 161:
      v83 = pvarVal->cyVal;
      LODWORD(lcida) = 0;
      ValueProperty = VarI4FromCy(v83, (LONG *)&lcida);
      if ( ValueProperty )
        goto LABEL_27;
      if ( (unsigned int)((_DWORD)lcida + 0x8000) > 0xFFFF )
        goto LABEL_117;
      valid = VarUI1FromUI2((USHORT)lcida, (BYTE *)&pvargDesta.decVal + 16);
      goto LABEL_96;
    case 162:
      v84 = pvarVal->cyVal;
      LODWORD(lcida) = 0;
      ValueProperty = VarI4FromCy(v84, (LONG *)&lcida);
      if ( ValueProperty )
        goto LABEL_27;
      valid = VarUI2FromUI4((ULONG)lcida, (USHORT *)&pvargDesta.decVal + 8);
      goto LABEL_96;
    case 163:
    case 167:
      ValueProperty = VarUI4FromR8((double)(int)pvarVal->llVal / 10000.0, (ULONG *)&pvargDesta.decVal + 4);
      goto LABEL_27;
    case 164:
      ValueProperty = VarI8FromCy(pvarVal->cyVal, (LONG64 *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 165:
      ValueProperty = VarUI8FromR8((double)(int)pvarVal->llVal / 10000.0, (ULONG64 *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 176:
      ValueProperty = VarBstrFromDate(
                        pvarVal->dblVal,
                        (LCID)lcida,
                        v10 | *(_DWORD *)&pvarg.vt | v5 & 8,
                        (BSTR *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 194:
      ValueProperty = VarI2FromStr(pvarVal->bstrVal, (LCID)lcida, v10, (SHORT *)&pvargDesta.decVal + 8);
      goto LABEL_27;
    case 195:
    case 214:
      v32 = pvarVal->bstrVal;
      pnumprs.cDig = 11;
      *(_OWORD *)&pnumprs.dwOutFlags = 0;
      pnumprs.dwInFlags = 0x1FFF;
      ValueProperty = VarParseNumFromStr(v32, (LCID)lcida, v10, &pnumprs, rgbDig);
      if ( ValueProperty <= -1 )
        goto LABEL_27;
      v33 = rgbDig;
      cDig = pnumprs.cDig;
      v35 = 0;
      if ( pnumprs.nBaseShift )
      {
        if ( pnumprs.cDig * pnumprs.nBaseShift <= 33 && (pnumprs.cDig * pnumprs.nBaseShift != 33 || rgbDig[0] <= 3u) )
        {
          if ( pnumprs.cDig > 0 )
          {
            do
            {
              v99 = *v33++;
              --cDig;
              v35 = v99 + (v35 << SLOBYTE(pnumprs.nBaseShift));
            }
            while ( cDig > 0 );
          }
          goto LABEL_65;
        }
      }
      else
      {
        v36 = pnumprs.cDig + pnumprs.nPwr10;
        if ( pnumprs.cDig + pnumprs.nPwr10 < 10 )
        {
          if ( v36 > 0 )
            goto LABEL_60;
LABEL_62:
          if ( cDig > 0 && !v36 )
          {
            if ( *v33 > 5u )
              goto LABEL_435;
            if ( *v33 == 5 )
            {
              v109 = v33 + 1;
              if ( (pnumprs.dwOutFlags & 0x20000) != 0 )
                goto LABEL_435;
              while ( cDig > 1 )
              {
                if ( *v109 )
                  goto LABEL_435;
                ++v109;
                --cDig;
              }
              if ( (v35 & 1) != 0 )
LABEL_435:
                ++v35;
            }
          }
          goto LABEL_63;
        }
        if ( v36 == 10 && rgbDig[0] <= 2u )
        {
LABEL_60:
          while ( cDig > 0 )
          {
            v37 = *v33++;
            --v36;
            --cDig;
            v35 = v37 + 10 * v35;
            if ( v36 <= 0 )
              goto LABEL_62;
          }
          v35 *= LODWORD((&ulPower10)[v36]);
LABEL_63:
          if ( (pnumprs.dwOutFlags & 0x10000) != 0 )
          {
            v35 = -v35;
            if ( v35 > 0 )
            {
              ValueProperty = -2147352566;
              goto LABEL_27;
            }
          }
          else if ( v35 < 0 )
          {
            ValueProperty = -2147352566;
            goto LABEL_27;
          }
LABEL_65:
          *((_DWORD *)&pvargDesta.decVal + 4) = v35;
          goto LABEL_66;
        }
      }
LABEL_117:
      ValueProperty = -2147352566;
      goto LABEL_27;
    case 196:
      ValueProperty = VarR4FromStr(pvarVal->bstrVal, (LCID)lcida, v10, (FLOAT *)&pvargDesta.decVal + 4);
      goto LABEL_27;
    case 197:
      ValueProperty = VarR8FromStr(pvarVal->bstrVal, (LCID)lcida, v10, (DOUBLE *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 198:
      ValueProperty = VarCyFromStr(pvarVal->bstrVal, (LCID)lcida, v10, (CY *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 199:
      ValueProperty = VarDateFromStr(pvarVal->bstrVal, (LCID)lcida, v10 | v5 & 8, (DATE *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 203:
      if ( (v5 & 0x10) != 0 )
        v10 |= 0x10u;
      ValueProperty = VarBoolFromStr(pvarVal->bstrVal, (LCID)lcida, v10, (VARIANT_BOOL *)&pvargDesta.decVal + 8);
      goto LABEL_27;
    case 206:
      ValueProperty = VarDecFromStr(pvarVal->bstrVal, (LCID)lcida, v10, (DECIMAL *)&pvargDesta.decVal.8);
      goto LABEL_27;
    case 208:
      v91 = pvarVal->bstrVal;
      pvarg.vt = 0;
      ValueProperty = VarI2FromStr(v91, (LCID)lcida, v10, (SHORT *)&pvarg);
      if ( ValueProperty )
        goto LABEL_27;
      if ( (unsigned __int16)(pvarg.vt + 128) > 0xFFu )
        goto LABEL_117;
      *((_BYTE *)&pvargDesta.decVal + 16) = pvarg.vt;
      goto LABEL_66;
    case 209:
      v56 = pvarVal->bstrVal;
      pvarg.vt = 0;
      ValueProperty = VarI2FromStr(v56, (LCID)lcida, v10, (SHORT *)&pvarg);
      if ( ValueProperty )
        goto LABEL_27;
      LOBYTE(ullVal) = pvarg.vt;
      if ( pvarg.vt <= 0xFFu )
        goto LABEL_148;
      goto LABEL_117;
    case 210:
      v49 = pvarVal->bstrVal;
      *(_DWORD *)&pvarg.vt = 0;
      ValueProperty = VarI4FromStr(v49, (LCID)lcida, v10, (LONG *)&pvarg);
      if ( ValueProperty )
        goto LABEL_27;
      LOWORD(v50) = pvarg.vt;
      if ( *(_DWORD *)&pvarg.vt <= 0xFFFFu )
        goto LABEL_99;
      goto LABEL_117;
    case 211:
    case 215:
      v46 = pvarVal->bstrVal;
      v125 = 0;
      pnumprs.cDig = 11;
      pnumprs.dwInFlags = 0x1FFF;
      *(_OWORD *)&pnumprs.dwOutFlags = 0;
      *(_OWORD *)&pvar.decVal.Lo32 = 0;
      ValueProperty = VarParseNumFromStr(v46, (LCID)lcida, v10, &pnumprs, v128);
      if ( ValueProperty > -1 )
      {
        ValueProperty = VarNumFromParseNum(&pnumprs, v128, 0x80000u, (VARIANT *)&pvar.decVal.8);
        if ( ValueProperty > -1 )
        {
          ValueProperty = 0;
          *((_DWORD *)&pvargDesta.decVal + 4) = *((_DWORD *)&pvar.decVal + 4);
        }
      }
      goto LABEL_27;
    case 212:
      ValueProperty = VarI8FromStr(pvarVal->bstrVal, (LCID)lcida, v10, (LONG64 *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 213:
      ValueProperty = VarUI8FromStr(pvarVal->bstrVal, (LCID)lcida, v10, (ULONG64 *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 218:
    case 219:
    case 220:
    case 221:
    case 222:
    case 223:
    case 224:
    case 227:
    case 230:
    case 232:
    case 233:
    case 234:
    case 235:
    case 236:
    case 237:
    case 238:
      goto LABEL_16;
    case 225:
    case 325:
      v52 = pvarVal->llVal;
      if ( v52 )
        (*(void (__fastcall **)(LONGLONG, __int64, __int16 *, __int64))(*(_QWORD *)v52 + 8LL))(
          v52,
          v13,
          &_ImageBase,
          v12);
LABEL_109:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->llVal;
      goto LABEL_27;
    case 229:
      v54 = (__int64 (__fastcall ***)(_QWORD, GUID *, DECIMAL *, __int64))pvarVal->llVal;
      if ( !v54 )
        goto LABEL_372;
      ValueProperty = (**v54)(v54, &IID_IUnknown, &pvargDesta.decVal + 1, v12);
      goto LABEL_27;
    case 272:
      if ( (v5 & 0x12) != 0 )
      {
        if ( (v5 & 0x10) != 0 )
          v10 |= 0x10u;
        ValueProperty = VarBstrFromBool(pvarVal->iVal, (LCID)lcida, v10, (BSTR *)&pvargDesta.pRecInfo);
        goto LABEL_27;
      }
LABEL_93:
      v47 = (unsigned int)pvarVal->iVal;
      memset(&pnumprs, 0, sizeof(pnumprs));
      if ( (((v5 & 0x80) << 21) & 0x10000000) != 0 )
      {
        _o__itow_s(v47, &pnumprs, 12, 10);
LABEL_408:
        valid = nls_number_to_bstr(
                  (LCID)lcida,
                  ((v5 & 0xFFFFFFFC) << 29) | ((v5 & 0x80) << 21) & 0xEFFFFFFF,
                  (unsigned __int16 *)&pnumprs,
                  (unsigned __int16 **)&pvargDesta.pRecInfo,
                  1);
        goto LABEL_96;
      }
      disp_itoa(v47, &pnumprs, 12, v12);
LABEL_79:
      ValueProperty = 0;
      pvargDesta.pRecInfo = (IRecordInfo *)SysAllocString((const OLECHAR *)&pnumprs);
      if ( !pvargDesta.pRecInfo )
        ValueProperty = -2147024882;
      goto LABEL_27;
    case 280:
    case 281:
      *((_BYTE *)&pvargDesta.decVal + 16) = pvarVal->bVal;
      goto LABEL_28;
    case 321:
      v90 = (__int64 (__fastcall ***)(_QWORD, GUID *, DECIMAL *, __int64))pvarVal->llVal;
      if ( v90 )
        ValueProperty = (**v90)(v90, &IID_IDispatch, &pvargDesta.decVal + 1, v12);
      else
LABEL_372:
        pvargDesta.pRecInfo = 0;
      goto LABEL_27;
    case 338:
      ValueProperty = VarI2FromDec((const DECIMAL *)pvarVal, (SHORT *)&pvargDesta.decVal + 8);
      goto LABEL_27;
    case 339:
    case 358:
      ValueProperty = VarI4FromDec((const DECIMAL *)pvarVal, (LONG *)&pvargDesta.decVal + 4);
      goto LABEL_27;
    case 340:
      valid = VarR4FromDec((const DECIMAL *)pvarVal, (FLOAT *)&pvargDesta.decVal + 4);
      goto LABEL_96;
    case 341:
      ValueProperty = VarR8FromDec((const DECIMAL *)pvarVal, (DOUBLE *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 342:
      ValueProperty = VarCyFromDec((const DECIMAL *)pvarVal, (CY *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 343:
      ValueProperty = VarDateFromDec((const DECIMAL *)pvarVal, (DATE *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 344:
      ValueProperty = VarBstrFromDec((const DECIMAL *)pvarVal, (LCID)lcida, v10, (BSTR *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 347:
      if ( pvarVal->decVal.scale > 0x1Cu || (pvarVal->decVal.sign & 0x7F) != 0 )
        goto LABEL_300;
      if ( pvarVal->decVal.Hi32 | pvarVal->lVal | pvarVal->cyVal.Hi )
        LOWORD(v50) = -1;
      else
        LOWORD(v50) = 0;
      goto LABEL_99;
    case 350:
      pvargDesta.8 = *(union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarVal->vt;
      goto LABEL_27;
    case 352:
      ValueProperty = VarI1FromDec((const DECIMAL *)pvarVal, (CHAR *)&pvargDesta.decVal + 16);
      goto LABEL_27;
    case 353:
      ValueProperty = VarUI1FromDec((const DECIMAL *)pvarVal, (BYTE *)&pvargDesta.decVal + 16);
      goto LABEL_27;
    case 354:
      ValueProperty = VarUI2FromDec((const DECIMAL *)pvarVal, (USHORT *)&pvargDesta.decVal + 8);
      goto LABEL_27;
    case 355:
    case 359:
      ValueProperty = VarUI4FromDec((const DECIMAL *)pvarVal, (ULONG *)&pvargDesta.decVal + 4);
      goto LABEL_27;
    case 356:
      ValueProperty = VarI8FromDec((const DECIMAL *)pvarVal, (LONG64 *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 357:
      ValueProperty = VarUI8FromDec((const DECIMAL *)pvarVal, (ULONG64 *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 386:
      *((_WORD *)&pvargDesta.decVal + 8) = pvarVal->cVal;
      goto LABEL_28;
    case 387:
    case 406:
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->cVal;
      goto LABEL_28;
    case 388:
      *((float *)&pvargDesta.decVal + 4) = (float)pvarVal->cVal;
      goto LABEL_28;
    case 389:
      *(double *)&pvargDesta.pRecInfo = (double)pvarVal->cVal;
      goto LABEL_28;
    case 390:
      pvargDesta.pRecInfo = (IRecordInfo *)(10000 * pvarVal->cVal);
      goto LABEL_28;
    case 391:
      iVal = pvarVal->cVal;
      goto LABEL_173;
    case 392:
      cVal = pvarVal->cVal;
      goto LABEL_105;
    case 395:
    case 419:
      v107 = pvarVal->bVal == 0;
      goto LABEL_404;
    case 398:
      v92 = pvarVal->cVal;
      v93 = pvarVal->cVal;
      *((_DWORD *)&pvargDesta.decVal + 5) = 0;
      v94 = -v93;
      pvargDesta.cyVal.Hi = 0;
      BYTE2(pvargDesta.decVal.Lo64) = 0;
      if ( v94 < 0 )
        LOWORD(v94) = v92;
      *((_DWORD *)&pvargDesta.decVal + 4) = (unsigned __int16)v94;
      BYTE3(pvargDesta.decVal.Lo64) = v92 & 0x80;
      goto LABEL_28;
    case 400:
    case 401:
    case 424:
    case 425:
      *((_BYTE *)&pvargDesta.decVal + 16) = pvarVal->bVal;
      goto LABEL_27;
    case 402:
      LOWORD(v50) = pvarVal->bVal;
      if ( (v50 & 0x80u) == 0 )
        goto LABEL_99;
      ValueProperty = -2147352566;
      goto LABEL_27;
    case 403:
    case 407:
      if ( pvarVal->cVal < 0 )
        goto LABEL_117;
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->bVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 404:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->cVal;
      goto LABEL_28;
    case 405:
      if ( pvarVal->cVal < 0 )
        goto LABEL_117;
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->bVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 410:
    case 426:
      *((_WORD *)&pvargDesta.decVal + 8) = pvarVal->bVal;
      goto LABEL_28;
    case 411:
    case 427:
    case 430:
    case 431:
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->bVal;
      goto LABEL_28;
    case 412:
      *((float *)&pvargDesta.decVal + 4) = (float)pvarVal->bVal;
      goto LABEL_28;
    case 413:
      *(double *)&pvargDesta.pRecInfo = (double)pvarVal->bVal;
      goto LABEL_28;
    case 414:
      pvargDesta.pRecInfo = (IRecordInfo *)(10000LL * pvarVal->bVal);
      goto LABEL_28;
    case 415:
      iVal = pvarVal->bVal;
      goto LABEL_173;
    case 416:
      cVal = pvarVal->bVal;
LABEL_105:
      ValueProperty = VarBstrFromI2(cVal, (LCID)lcida, v10, (BSTR *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 422:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->bVal;
      WORD1(pvargDesta.decVal.Lo64) = 0;
      pvargDesta.cyVal.Hi = 0;
      goto LABEL_28;
    case 428:
    case 429:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->bVal;
      goto LABEL_28;
    case 435:
    case 451:
    case 454:
    case 455:
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->uiVal;
      goto LABEL_27;
    case 436:
      *((float *)&pvargDesta.decVal + 4) = (float)pvarVal->uiVal;
      goto LABEL_27;
    case 437:
      *(double *)&pvargDesta.pRecInfo = (double)pvarVal->uiVal;
      goto LABEL_27;
    case 438:
      pvargDesta.pRecInfo = (IRecordInfo *)(10000LL * pvarVal->uiVal);
      goto LABEL_28;
    case 439:
      iVal = pvarVal->uiVal;
LABEL_173:
      *(double *)&pvargDesta.pRecInfo = (double)iVal;
      valid = IsValidDate((double)iVal);
      goto LABEL_96;
    case 440:
      ValueProperty = VarBstrFromUI4(pvarVal->uiVal, (LCID)lcida, v10, (BSTR *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 446:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->uiVal;
      WORD1(pvargDesta.decVal.Lo64) = 0;
      pvargDesta.cyVal.Hi = 0;
      goto LABEL_28;
    case 448:
      LOWORD(ullVal) = pvarVal->iVal;
      if ( (unsigned __int16)ullVal <= 0x7Fu )
        goto LABEL_148;
      ValueProperty = -2147352566;
      goto LABEL_27;
    case 449:
      v97 = pvarVal->iVal;
      if ( (unsigned __int16)v97 <= 0xFFu )
        *((_BYTE *)&pvargDesta.decVal + 16) = pvarVal->iVal;
      ValueProperty = (unsigned __int16)v97 > 0xFFu ? 0x8002000A : 0;
      goto LABEL_27;
    case 452:
    case 453:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->uiVal;
      goto LABEL_27;
    case 458:
    case 554:
      v50 = pvarVal->cyVal.Lo;
      if ( v50 <= 0x7FFF )
      {
LABEL_99:
        *((_WORD *)&pvargDesta.decVal + 8) = v50;
        goto LABEL_66;
      }
      ValueProperty = -2147352566;
      goto LABEL_27;
    case 460:
    case 556:
      *((float *)&pvargDesta.decVal + 4) = (float)pvarVal->lVal;
      goto LABEL_27;
    case 461:
    case 557:
      *(double *)&pvargDesta.pRecInfo = (double)pvarVal->lVal;
      goto LABEL_27;
    case 462:
    case 558:
      ValueProperty = VarCyFromR8((double)pvarVal->lVal, (CY *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 464:
    case 560:
      v27 = pvarVal->cyVal.Lo;
      if ( (((v5 & 0x80) << 21) & 0x10000000) != 0 )
      {
        valid = VarBstrFromUI8(pvarVal->cyVal.Lo, (LCID)lcida, v10, (BSTR *)&pvargDesta.pRecInfo);
        goto LABEL_96;
      }
      v28 = (char *)v130;
      do
      {
        v29 = v27 % 0xA;
        v27 /= 0xAu;
        *(_WORD *)v28 = v29 + 48;
        v28 += 2;
      }
      while ( v27 );
      if ( (unsigned __int64)(((v28 - (char *)v130) >> 1) + 1) <= 0x28 )
      {
        v30 = psz;
        do
        {
          v31 = *((_WORD *)v28 - 1);
          v28 -= 2;
          *v30++ = v31;
        }
        while ( v28 > (char *)v130 );
        *v30 = 0;
      }
      pvargDesta.pRecInfo = (IRecordInfo *)SysAllocString(psz);
      if ( pvargDesta.pRecInfo )
      {
        ValueProperty = 0;
        goto LABEL_27;
      }
      goto LABEL_26;
    case 470:
    case 566:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->cyVal.Lo;
      WORD1(pvargDesta.decVal.Lo64) = 0;
      pvargDesta.cyVal.Hi = 0;
      goto LABEL_28;
    case 472:
    case 568:
      LODWORD(ullVal) = pvarVal->lVal;
      if ( (unsigned int)ullVal <= 0x7F )
        goto LABEL_148;
      ValueProperty = -2147352566;
      goto LABEL_27;
    case 476:
    case 477:
    case 572:
    case 573:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->cyVal.Lo;
      goto LABEL_27;
    case 482:
      if ( (unsigned __int64)(pvarVal->llVal + 0x8000) > 0xFFFF )
        goto LABEL_117;
      *((_WORD *)&pvargDesta.decVal + 8) = pvarVal->llVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 483:
    case 502:
      if ( (unsigned __int64)(pvarVal->llVal + 0x80000000LL) > 0xFFFFFFFF )
        goto LABEL_117;
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->llVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 484:
      *((float *)&pvargDesta.decVal + 4) = (float)(int)pvarVal->llVal;
      goto LABEL_28;
    case 485:
      *(double *)&pvargDesta.pRecInfo = (double)(int)pvarVal->llVal;
      goto LABEL_27;
    case 486:
      v66 = pvarVal->llVal;
      if ( (unsigned __int64)(v66 + 0x346DC5D638864LL) > 0x68DB8BAC710C8LL )
        goto LABEL_117;
      ValueProperty = 0;
      pvargDesta.pRecInfo = (IRecordInfo *)(10000 * v66);
      goto LABEL_27;
    case 487:
      v69 = (double)(int)pvarVal->llVal;
      *(double *)&pvargDesta.pRecInfo = v69;
      valid = IsValidDate(v69);
      goto LABEL_96;
    case 488:
      ValueProperty = VarBstrFromI8(pvarVal->llVal, (LCID)lcida, v10, (BSTR *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 491:
    case 515:
      v107 = pvarVal->llVal == 0;
LABEL_404:
      if ( v107 )
LABEL_234:
        v74 = 0;
      else
LABEL_223:
        v74 = -1;
      *((_WORD *)&pvargDesta.decVal + 8) = v74;
      goto LABEL_27;
    case 494:
      v67 = pvarVal->llVal;
      BYTE3(pvargDesta.decVal.Lo64) = HIBYTE(v67) & 0x80;
      if ( v67 >= 0 )
        goto LABEL_204;
      if ( v67 == 0x8000000000000000uLL )
      {
        *((_DWORD *)&pvargDesta.decVal + 4) = 0;
        LODWORD(v68) = 0x80000000;
      }
      else
      {
        v67 = -v67;
LABEL_204:
        *((_DWORD *)&pvargDesta.decVal + 4) = v67;
        v68 = HIDWORD(v67);
      }
      *((_DWORD *)&pvargDesta.decVal + 5) = v68;
      pvargDesta.cyVal.Hi = 0;
      BYTE2(pvargDesta.decVal.Lo64) = 0;
      goto LABEL_28;
    case 496:
      if ( (unsigned __int64)(pvarVal->llVal + 128) > 0xFF )
        goto LABEL_117;
      *((_BYTE *)&pvargDesta.decVal + 16) = pvarVal->llVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 497:
    case 521:
      valid = VarUI1FromUI8(pvarVal->ullVal, (BYTE *)&pvargDesta.decVal + 16);
      goto LABEL_96;
    case 498:
    case 522:
      valid = VarUI2FromI8(pvarVal->ullVal, (USHORT *)&pvargDesta.decVal + 8);
      goto LABEL_96;
    case 499:
    case 503:
      if ( pvarVal->llVal > 0xFFFFFFFFuLL )
        goto LABEL_117;
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->llVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 506:
      valid = VarI2FromUI8(pvarVal->ullVal, (SHORT *)&pvargDesta.decVal + 8);
      goto LABEL_96;
    case 507:
    case 526:
      if ( pvarVal->llVal > 0x7FFFFFFFuLL )
        goto LABEL_117;
      *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->llVal;
      ValueProperty = 0;
      goto LABEL_27;
    case 508:
      v110 = pvarVal->llVal;
      if ( v110 < 0 )
      {
        v112 = pvarVal->llVal & 1 | ((unsigned __int64)pvarVal->llVal >> 1);
        v111 = (float)(int)v112 + (float)(int)v112;
      }
      else
      {
        v111 = (float)(int)v110;
      }
      *((float *)&pvargDesta.decVal + 4) = v111;
      goto LABEL_27;
    case 509:
      v113 = pvarVal->llVal;
      if ( v113 < 0 )
      {
        v115 = pvarVal->llVal & 1 | ((unsigned __int64)pvarVal->llVal >> 1);
        v114 = (double)(int)v115 + (double)(int)v115;
      }
      else
      {
        v114 = (double)(int)v113;
      }
      *(double *)&pvargDesta.pRecInfo = v114;
      goto LABEL_27;
    case 510:
      v116 = pvarVal->llVal;
      if ( v116 < 0 )
      {
        v118 = pvarVal->llVal & 1 | ((unsigned __int64)pvarVal->llVal >> 1);
        v117 = (double)(int)v118 + (double)(int)v118;
      }
      else
      {
        v117 = (double)(int)v116;
      }
      valid = VarCyFromR8(v117, (CY *)&pvargDesta.pRecInfo);
      goto LABEL_96;
    case 511:
      v98 = pvarVal->llVal;
      if ( v98 < 0 )
      {
        v106 = pvarVal->llVal & 1 | ((unsigned __int64)pvarVal->llVal >> 1);
        *(double *)&pvargDesta.pRecInfo = (double)(int)v106 + (double)(int)v106;
        valid = IsValidDate(*(double *)&pvargDesta.pRecInfo);
      }
      else
      {
        *(double *)&pvargDesta.pRecInfo = (double)(int)v98;
        valid = IsValidDate((double)(int)v98);
      }
      goto LABEL_96;
    case 512:
      ValueProperty = VarBstrFromUI8(pvarVal->ullVal, (LCID)lcida, v10, (BSTR *)&pvargDesta.pRecInfo);
      goto LABEL_27;
    case 518:
      pvargDesta.pRecInfo = (IRecordInfo *)pvarVal->llVal;
      WORD1(pvargDesta.decVal.Lo64) = 0;
      pvargDesta.cyVal.Hi = 0;
      goto LABEL_28;
    case 520:
      ullVal = pvarVal->ullVal;
      if ( ullVal <= 0x7F )
      {
LABEL_148:
        *((_BYTE *)&pvargDesta.decVal + 16) = ullVal;
        ValueProperty = 0;
      }
      else
      {
        ValueProperty = -2147352566;
      }
      goto LABEL_27;
    case 523:
    case 527:
      v95 = pvarVal->ullVal;
      if ( v95 <= 0xFFFFFFFF )
        *((_DWORD *)&pvargDesta.decVal + 4) = pvarVal->llVal;
      v96 = 0;
      if ( v95 > 0xFFFFFFFF )
        v96 = -2147352566;
      ValueProperty = v96;
      goto LABEL_27;
    case 900:
      *(_OWORD *)&pvargDesta.decVal.Lo32 = 0;
      v121 = 0;
      valid = VariantCopy((VARIANTARG *)&pvargDesta.decVal.8, pvarVal);
      goto LABEL_96;
    default:
      if ( uiVal < 0xCu )
        goto LABEL_85;
      ValueProperty = IsLegalVartype(uiVal);
      if ( ValueProperty < 0 )
        goto LABEL_18;
      if ( (uiVal & (unsigned __int16)v12) != 0 )
      {
        pvarVal = pvarVal->pvarVal;
        if ( !pvarVal )
          goto LABEL_17;
        uiVal &= v44;
        v13 = vt;
        if ( uiVal != 14 )
        {
          if ( uiVal == 12 )
          {
            uiVal = pvarVal->vt;
            if ( pvarVal->vt == v45 )
            {
              VariantClear((VARIANTARG *)&pvarg.decVal.8);
              return -2147024809;
            }
          }
          else
          {
            pvarVal = (const VARIANTARG *)((char *)pvarVal - 8);
          }
        }
        goto LABEL_10;
      }
LABEL_85:
      if ( uiVal == 8209 && vt == 8 )
      {
        valid = BstrFromVector(pvarVal->parray, (BSTR *)&pvargDesta.pRecInfo);
LABEL_96:
        ValueProperty = valid;
        goto LABEL_27;
      }
      if ( vt != 8209 )
        goto LABEL_17;
      if ( uiVal == 8 )
      {
        ValueProperty = VectorFromBstr(pvarVal->bstrVal, (SAFEARRAY **)&pvargDesta.pRecInfo);
        goto LABEL_27;
      }
      if ( uiVal != 8209 )
      {
LABEL_17:
        ValueProperty = -2147352571;
        goto LABEL_18;
      }
      parray = pvarVal->parray;
      v101 = 0;
      lcida = 0;
      pvargDesta.pRecInfo = 0;
      if ( !parray )
      {
LABEL_66:
        ValueProperty = 0;
        goto LABEL_27;
      }
      fFeatures = parray->fFeatures;
      if ( (fFeatures & 0xE0) != 0 )
      {
        if ( (fFeatures & 0x20) != 0 )
        {
          ValueProperty = SafeArrayAllocDescriptorEx(0x24u, parray->cDims, &lcida);
          if ( ValueProperty <= -1 )
            goto LABEL_27;
          v119 = parray[-1].rgsabound[0];
          v101 = lcida;
          lcida[-1].rgsabound[0] = v119;
          if ( v119 )
            (*(void (__fastcall **)(SAFEARRAYBOUND))(**(_QWORD **)&v119 + 8LL))(v119);
        }
        else if ( (fFeatures & 0x40) != 0 )
        {
          ValueProperty = SafeArrayAllocDescriptorEx(0xDu, parray->cDims, &lcida);
          if ( ValueProperty <= -1 )
            goto LABEL_27;
          v101 = lcida;
          *(_OWORD *)&lcida[-1].pvData = *(_OWORD *)&parray[-1].pvData;
        }
        else if ( (fFeatures & 0x80u) != 0 )
        {
          ValueProperty = SafeArrayAllocDescriptorEx(parray[-1].rgsabound[0].lLbound, parray->cDims, &lcida);
          if ( ValueProperty <= -1 )
            goto LABEL_27;
          v101 = lcida;
        }
      }
      else
      {
        cDims = parray->cDims;
        if ( !(_WORD)cDims )
        {
LABEL_300:
          ValueProperty = -2147024809;
          goto LABEL_27;
        }
        v104 = (char *)operator new[](8 * cDims + 40);
        v105 = v104;
        if ( !v104 )
          goto LABEL_26;
        memset_0(v104, 0, 8 * cDims + 40);
        v101 = (SAFEARRAY *)(v105 + 16);
        v101->cDims = cDims;
      }
      v101->cLocks = 0;
      v101->cDims = parray->cDims;
      v101->fFeatures = parray->fFeatures & 0xCFE8;
      v101->cbElements = parray->cbElements;
      memcpy_0(v101->rgsabound, parray->rgsabound, 8LL * parray->cDims);
      ValueProperty = SafeArrayAllocData(v101);
      if ( ValueProperty < 0 || (ValueProperty = SafeArrayCopyData(parray, v101), ValueProperty <= -1) )
      {
        _SafeArrayDestroy(v101, 1);
      }
      else
      {
        pvargDesta.pRecInfo = (IRecordInfo *)v101;
        ValueProperty = 0;
      }
LABEL_27:
      if ( ValueProperty < 0 )
      {
LABEL_18:
        VariantClear((VARIANTARG *)&pvarg.decVal.8);
        return ValueProperty;
      }
      else
      {
LABEL_28:
        v23 = pvargDest->vt < 8u;
        pvargDesta.iVal = vt;
        if ( !v23 )
        {
          ValueProperty = VariantClear(pvargDest);
          if ( ValueProperty <= -1 )
          {
            VariantClear((VARIANTARG *)&pvargDesta.decVal.8);
            goto LABEL_18;
          }
        }
        v23 = pvarg.iVal < 8u;
        v24 = v121;
        *(_OWORD *)&pvargDest->vt = *(_OWORD *)&pvargDesta.decVal.Lo32;
        pvargDest->pRecInfo = v24;
        if ( !v23 )
          VariantClear((VARIANTARG *)&pvarg.decVal.8);
        return 0;
      }
  }
}

```

## disassembly

```asm
0x1800078c0  mov     r11, rsp
0x1800078c3  push    rbp
0x1800078c4  push    rdi
0x1800078c5  push    r13
0x1800078c7  push    r14
0x1800078c9  push    r15
0x1800078cb  lea     rbp, [r11-0D8h]
0x1800078d2  sub     rsp, 1B0h
0x1800078d9  mov     rax, cs:__security_cookie
0x1800078e0  xor     rax, rsp
0x1800078e3  mov     [rbp+0D0h+var_40], rax
0x1800078ea  xor     eax, eax
0x1800078ec  movzx   r13d, r9w
0x1800078f0  mov     dword ptr [rsp+1D0h+lcid], r8d
0x1800078f5  xorps   xmm0, xmm0
0x1800078f8  mov     [rsp+1D0h+var_190], rax
0x1800078fd  xorps   xmm1, xmm1
0x180007900  mov     qword ptr [rsp+1D0h+pvar], rax
0x180007905  mov     r14, rdx
0x180007908  mov     r15, rcx
0x18000790b  movups  xmmword ptr [rsp+1D0h+pvargDest+8], xmm0
0x180007910  movups  xmmword ptr [rsp+1D0h+pvarg+8], xmm1
0x180007915  test    rcx, rcx
0x180007918  jz      loc_18000983B
0x18000791e  test    rdx, rdx
0x180007921  jz      loc_18000983B
0x180007927  mov     [r11+20h], rbx
0x18000792b  mov     r10d, 2011h
0x180007931  movzx   ebx, [rbp+0D0h+vt]
0x180007938  mov     [r11-38h], r12
0x18000793c  movzx   r12d, word ptr [rdx]
0x180007940  cmp     ebx, 0Ch
0x180007943  jnb     loc_180007B05
0x180007949  mov     [rsp+1A8h], rsi
0x180007951  xor     edi, edi
0x180007953  mov     esi, r13d
0x180007956  mov     dword ptr [rsp+1D0h+pvarg], edi
0x18000795a  and     esi, 80h
0x180007960  mov     eax, r13d
0x180007963  and     eax, 0FFFFFFFCh
0x180007966  shl     esi, 15h
0x180007969  shl     eax, 1Dh
0x18000796c  or      esi, eax
0x18000796e  test    r8d, 0FFFFFBFFh
0x180007975  jz      loc_180007B73
0x18000797b  mov     eax, r8d
0x18000797e  cmp     eax, 800h
0x180007983  jz      loc_180007D2B
0x180007989  mov     ecx, 3FFh
0x18000798e  and     ax, cx
0x180007991  cmp     ax, 1Eh
0x180007995  jz      loc_18000819A
0x18000799b  mov     r11d, 400Ch
0x1800079a1  mov     r10d, 0BFFFh
0x1800079a7  mov     r9d, 4000h
0x1800079ad  mov     edx, ebx
0x1800079af  lea     r8, __ImageBase
0x1800079b6  movzx   eax, r12w
0x1800079ba  lea     ecx, [rax+rax*2]
0x1800079bd  lea     eax, [rdx+rcx*8]
0x1800079c0  cmp     eax, 0EFh
0x1800079c5  jz      short loc_1800079FE; jumptable 0000000180007B9F cases 218-224,227,230,232-238
0x1800079c7  cmp     eax, 1
0x1800079ca  jz      loc_180007A93; jumptable 0000000180007B9F cases 0,25,48,49,72,73,96,97,120,121,144,145,168,169,192,193,216,217,264,265,312,313,336,337,384,385,408,409,432,433,456,457,480,481,504,505,528,529,552,553
0x1800079d0  cmp     eax, 0C8h
0x1800079d5  jnz     loc_180007B7E
0x1800079db  mov     r14, [r14+8]
0x1800079df  test    r14, r14
0x1800079e2  jz      short loc_180007A1E
0x1800079e4  mov     esi, [r14-4]
0x1800079e8  lea     edi, [rsi+19h]
0x1800079eb  cmp     edi, 19h
0x1800079ee  jnb     short loc_180007A25
0x1800079f0  mov     qword ptr [rsp+1D0h+pvargDest+10h], 0
0x1800079f9  jmp     loc_180007A8E
0x1800079fe  test    r13b, 1; jumptable 0000000180007B9F cases 218-224,227,230,232-238
0x180007a02  jz      loc_180008350
0x180007a08  mov     edi, 80020005h
0x180007a0d  lea     rcx, [rsp+1D0h+pvarg+8]; pvarg
0x180007a12  call    VariantClear
0x180007a17  mov     eax, edi
0x180007a19  jmp     loc_180007ACE
0x180007a1e  xor     esi, esi
0x180007a20  mov     edi, 19h
0x180007a25  mov     ecx, cs:?g_itlsAppData@@3KA; dwTlsIndex
0x180007a2b  call    cs:__imp_TlsGetValue
0x180007a31  test    rax, rax
0x180007a34  jz      loc_18000921D
0x180007a3a  and     edi, 0FFFFFFF0h
0x180007a3d  mov     rcx, rax; this
0x180007a40  mov     edx, edi; unsigned int
0x180007a42  call    ?AllocCachedMem@APP_DATA@@QEAAPEAXK@Z; APP_DATA::AllocCachedMem(ulong)
0x180007a47  mov     rdi, rax
0x180007a4a  test    rax, rax
0x180007a4d  jz      short loc_180007A80
0x180007a4f  add     rdi, 8
0x180007a53  mov     [rax+4], esi
0x180007a56  test    r14, r14
0x180007a59  jz      short loc_180007A69
0x180007a5b  mov     r8d, esi; Size
0x180007a5e  mov     rdx, r14; Src
0x180007a61  mov     rcx, rdi; void *
0x180007a64  call    memcpy_0
0x180007a69  mov     eax, esi
0x180007a6b  lea     ecx, [rsi+1]
0x180007a6e  mov     byte ptr [rax+rdi], 0
0x180007a72  mov     eax, 0FFFFFFFEh
0x180007a77  and     rcx, rax
0x180007a7a  xor     eax, eax
0x180007a7c  mov     [rcx+rdi], ax
0x180007a80  mov     qword ptr [rsp+1D0h+pvargDest+10h], rdi
0x180007a85  test    rdi, rdi
0x180007a88  jnz     loc_180009825
0x180007a8e  mov     edi, 8007000Eh
0x180007a93  test    edi, edi; jumptable 0000000180007B9F cases 0,25,48,49,72,73,96,97,120,121,144,145,168,169,192,193,216,217,264,265,312,313,336,337,384,385,408,409,432,433,456,457,480,481,504,505,528,529,552,553
0x180007a95  js      loc_180007A0D
0x180007a9b  cmp     word ptr [r15], 8
0x180007aa0  mov     word ptr [rsp+1D0h+pvargDest+8], bx
0x180007aa5  jnb     loc_180007C30
0x180007aab  cmp     word ptr [rsp+1D0h+pvarg+8], 8
0x180007ab1  movups  xmm0, xmmword ptr [rsp+1D0h+pvargDest+8]
0x180007ab6  movsd   xmm1, [rsp+1D0h+var_190]
0x180007abc  movups  xmmword ptr [r15], xmm0
0x180007ac0  movsd   qword ptr [r15+10h], xmm1
0x180007ac6  jnb     loc_18000982C
0x180007acc  xor     eax, eax
0x180007ace  mov     rsi, [rsp+1A8h]
0x180007ad6  mov     rbx, [rsp+1D0h+arg_18]
0x180007ade  mov     r12, [rsp+1D0h+var_30]
0x180007ae6  mov     rcx, [rbp+0D0h+var_40]
0x180007aed  xor     rcx, rsp; StackCookie
0x180007af0  call    __security_check_cookie
0x180007af5  add     rsp, 1B0h
0x180007afc  pop     r15
0x180007afe  pop     r14
0x180007b00  pop     r13
0x180007b02  pop     rdi
0x180007b03  pop     rbp
0x180007b04  retn
0x180007b05  mov     r11d, 6000h
0x180007b0b  movzx   eax, bx
0x180007b0e  and     ax, r11w
0x180007b12  movzx   ecx, bx
0x180007b15  mov     r9d, 9FFFh
0x180007b1b  movzx   edx, ax
0x180007b1e  and     cx, r9w
0x180007b22  test    ax, ax
0x180007b25  cmovz   cx, bx
0x180007b29  cmp     cx, 24h ; '$'
0x180007b2d  ja      loc_1800094A4
0x180007b33  mov     rax, 1000FF7FFCh
0x180007b3d  bt      rax, rcx
0x180007b41  jnb     loc_1800094A4
0x180007b47  mov     eax, 0E000h
0x180007b4c  test    ax, bx
0x180007b4f  jz      loc_180007949
0x180007b55  cmp     bx, r12w
0x180007b59  jz      loc_1800083F6
0x180007b5f  cmp     bx, r10w
0x180007b63  jz      loc_180007949
0x180007b69  mov     eax, 80020005h
0x180007b6e  jmp     loc_180007AD6
0x180007b73  call    cs:__imp_GetUserDefaultLCID
0x180007b79  jmp     loc_18000797E
0x180007b7e  cmp     eax, 384h; switch 901 cases
0x180007b83  ja      def_180007B9F; jumptable 0000000180007B9F default case, cases 1,9,10,12,13,15,24,26-47,57,58,60,61,63,81,82,84,85,87,105,106,108,109,111,129,130,132,133,135,153,154,156,157,159,177,178,180,181,183,200-202,204,205,207,226,228,231,239-249,251-263,273,274,276,277,279,288-311,314-320,322-324,326-335,345,346,348,349,351,360-383,393,394,396,397,399,417,418,420,421,423,441,442,444,445,447,465,466,468,469,471,489,490,492,493,495,513,514,516,517,519,537,538,540,541,543,548,549,561,562,564,565,567,576-899
0x180007b89  cdqe
0x180007b8b  movzx   eax, ds:(byte_180009B38 - 180000000h)[r8+rax]
0x180007b94  mov     ecx, ds:(jpt_180007B9F - 180000000h)[r8+rax*4]
0x180007b9c  add     rcx, r8
0x180007b9f  jmp     rcx; switch jump
0x180007ba1  mov     r8d, [r14+8]; jumptable 0000000180007B9F cases 464,560
0x180007ba5  bt      esi, 1Ch
0x180007ba9  jb      loc_1800096AA
0x180007baf  lea     rcx, [rbp+0D0h+var_D0]
0x180007bb3  mov     eax, 0CCCCCCCDh
0x180007bb8  mul     r8d
0x180007bbb  shr     edx, 3
0x180007bbe  lea     eax, [rdx+rdx*4]
0x180007bc1  add     eax, eax
0x180007bc3  sub     r8d, eax
0x180007bc6  mov     eax, r8d
0x180007bc9  mov     r8d, edx
0x180007bcc  add     ax, 30h ; '0'
0x180007bd0  mov     [rcx], ax
0x180007bd3  add     rcx, 2
0x180007bd7  test    edx, edx
0x180007bd9  jnz     short loc_180007BB3
0x180007bdb  lea     rdx, [rbp+0D0h+var_D0]
0x180007bdf  mov     rax, rcx
0x180007be2  sub     rax, rdx
0x180007be5  sar     rax, 1
0x180007be8  inc     rax
0x180007beb  cmp     rax, 28h ; '('
0x180007bef  ja      short loc_180007C12
0x180007bf1  lea     rdx, [rbp+0D0h+psz]
0x180007bf5  movzx   eax, word ptr [rcx-2]
0x180007bf9  sub     rcx, 2
0x180007bfd  mov     [rdx], ax
0x180007c00  lea     rdx, [rdx+2]
0x180007c04  lea     rax, [rbp+0D0h+var_D0]
0x180007c08  cmp     rcx, rax
0x180007c0b  ja      short loc_180007BF5
0x180007c0d  xor     eax, eax
0x180007c0f  mov     [rdx], ax
0x180007c12  lea     rcx, [rbp+0D0h+psz]; psz
0x180007c16  call    SysAllocString
0x180007c1b  mov     qword ptr [rsp+1D0h+pvargDest+10h], rax
0x180007c20  test    rax, rax
0x180007c23  jz      loc_180007A8E
0x180007c29  xor     edi, edi
0x180007c2b  jmp     loc_180007A93; jumptable 0000000180007B9F cases 0,25,48,49,72,73,96,97,120,121,144,145,168,169,192,193,216,217,264,265,312,313,336,337,384,385,408,409,432,433,456,457,480,481,504,505,528,529,552,553
0x180007c30  mov     rcx, r15; pvarg
0x180007c33  call    VariantClear
0x180007c38  mov     edi, eax
0x180007c3a  cmp     eax, 0FFFFFFFFh
0x180007c3d  jg      loc_180007AAB
0x180007c43  lea     rcx, [rsp+1D0h+pvargDest+8]; pvarg
0x180007c48  call    VariantClear
0x180007c4d  jmp     loc_180007A0D
0x180007c52  lea     rcx, psz; jumptable 0000000180007B9F case 8
0x180007c59  call    SysAllocString
0x180007c5e  xor     edi, edi
0x180007c60  mov     qword ptr [rsp+1D0h+pvargDest+10h], rax
0x180007c65  test    rax, rax
0x180007c68  mov     ecx, 8007000Eh
0x180007c6d  cmovz   edi, ecx
0x180007c70  jmp     loc_180007A93; jumptable 0000000180007B9F cases 0,25,48,49,72,73,96,97,120,121,144,145,168,169,192,193,216,217,264,265,312,313,336,337,384,385,408,409,432,433,456,457,480,481,504,505,528,529,552,553
0x180007c75  mov     edx, dword ptr [rsp+1D0h+lcid]; jumptable 0000000180007B9F cases 195,214
0x180007c79  lea     rax, [rbp+0D0h+rgbDig]
0x180007c7d  mov     rcx, [r14+8]; strIn
0x180007c81  lea     r9, [rbp+0D0h+pnumprs]; pnumprs
0x180007c85  xorps   xmm0, xmm0
0x180007c88  mov     [rsp+20h], rax; rgbDig
0x180007c8d  mov     r8d, esi; dwFlags
0x180007c90  mov     [rbp+0D0h+pnumprs.cDig], 0Bh
0x180007c97  movdqu  xmmword ptr [rbp+0D0h+pnumprs.dwOutFlags], xmm0
0x180007c9c  mov     [rbp+0D0h+pnumprs.dwInFlags], 1FFFh
0x180007ca3  call    VarParseNumFromStr
0x180007ca8  mov     edi, eax
0x180007caa  cmp     eax, 0FFFFFFFFh
0x180007cad  jle     loc_180007A93; jumptable 0000000180007B9F cases 0,25,48,49,72,73,96,97,120,121,144,145,168,169,192,193,216,217,264,265,312,313,336,337,384,385,408,409,432,433,456,457,480,481,504,505,528,529,552,553
0x180007cb3  mov     ecx, [rbp+0D0h+pnumprs.nBaseShift]
0x180007cb6  lea     r10, [rbp+0D0h+rgbDig]
0x180007cba  mov     edx, [rbp+0D0h+pnumprs.cDig]
0x180007cbd  xor     r8d, r8d
0x180007cc0  test    ecx, ecx
0x180007cc2  jnz     loc_1800092D0
0x180007cc8  mov     r9d, [rbp+0D0h+pnumprs.nPwr10]
0x180007ccc  mov     r11d, [rbp+0D0h+pnumprs.dwOutFlags]
0x180007cd0  add     r9d, edx
0x180007cd3  cmp     r9d, 0Ah
0x180007cd7  jge     loc_180009291
0x180007cdd  test    r9d, r9d
0x180007ce0  jle     short loc_180007D03
0x180007ce2  test    edx, edx
0x180007ce4  jle     loc_180009483
0x180007cea  movzx   eax, byte ptr [r10]
0x180007cee  lea     ecx, [r8+r8*4]
0x180007cf2  inc     r10
0x180007cf5  dec     r9d
0x180007cf8  dec     edx
0x180007cfa  lea     r8d, [rax+rcx*2]
0x180007cfe  test    r9d, r9d
0x180007d01  jg      short loc_180007CE2
0x180007d03  test    edx, edx
0x180007d05  jg      loc_18000962D
0x180007d0b  bt      r11d, 10h
0x180007d10  jb      loc_18000827E
0x180007d16  test    r8d, r8d
0x180007d19  js      loc_1800081BF
0x180007d1f  mov     dword ptr [rsp+1D0h+pvargDest+10h], r8d
0x180007d24  xor     edi, edi
0x180007d26  jmp     loc_180007A93; jumptable 0000000180007B9F cases 0,25,48,49,72,73,96,97,120,121,144,145,168,169,192,193,216,217,264,265,312,313,336,337,384,385,408,409,432,433,456,457,480,481,504,505,528,529,552,553
0x180007d2b  call    cs:__imp_GetSystemDefaultLCID
0x180007d31  jmp     loc_180007989
0x180007d36  movsx   eax, word ptr [r14+8]; jumptable 0000000180007B9F cases 51,70,267,283,286,287
0x180007d3b  mov     dword ptr [rsp+1D0h+pvargDest+10h], eax
0x180007d3f  jmp     loc_180007A93; jumptable 0000000180007B9F cases 0,25,48,49,72,73,96,97,120,121,144,145,168,169,192,193,216,217,264,265,312,313,336,337,384,385,408,409,432,433,456,457,480,481,504,505,528,529,552,553
0x180007d44  mov     ecx, [r14+8]; jumptable 0000000180007B9F cases 80,536
0x180007d48  xor     eax, eax
0x180007d4a  mov     qword ptr [rbp+0D0h+pnumprs.nBaseShift], rax
0x180007d4e  xorps   xmm0, xmm0
0x180007d51  movups  xmmword ptr [rbp+0D0h+pnumprs.cDig], xmm0
0x180007d55  bt      esi, 1Ch
0x180007d59  jb      loc_1800094E3
0x180007d5f  mov     r9d, ecx
0x180007d62  lea     r8, [rbp+0D0h+var_110]
0x180007d66  shr     r9d, 1Fh
0x180007d6a  test    r9d, r9d
0x180007d6d  jnz     loc_180007EE4
0x180007d73  mov     eax, 0CCCCCCCDh
0x180007d78  mul     ecx
0x180007d7a  shr     edx, 3
0x180007d7d  lea     eax, [rdx+rdx*4]
0x180007d80  add     eax, eax
0x180007d82  sub     ecx, eax
0x180007d84  mov     eax, ecx
0x180007d86  mov     ecx, edx
0x180007d88  add     ax, 30h ; '0'
  ... truncated ...
```
