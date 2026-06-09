# FaxStartPrintJob2W

- ea: `0x180025df0`
- end: `0x180026ab5`
- name: `FaxStartPrintJob2W`
- size: `3269`
- prototype: `__int64 __usercall@<rax>(LPWSTR pPrinterName@<rcx>, __int64)`
- caller_count: `2`
- callee_count: `15`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1800259ec`
- `0x180026ae0`

## callees

- `0x1800084ac`
- `0x18000abe4`
- `0x18000ac14`
- `0x180014314`
- `0x180016124`
- `0x18001a7a0`
- `0x180021530`
- `0x180025104`
- `0x180025df0`
- `0x18002bab8`
- `0x18002bb58`
- `0x18002f9ac`
- `0x18003015c`
- `0x180030314`
- `0x18003d510`

## import_xrefs

- `msvcrt!wcsstr` at `0x1800261e9`
- `msvcrt!wcsstr` at `0x1800261e9`
- `KERNEL32!SetLastError` at `0x180025fab`
- `KERNEL32!SetLastError` at `0x18002601b`
- `KERNEL32!SetLastError` at `0x180026120`
- `KERNEL32!SetLastError` at `0x1800262a7`
- `KERNEL32!SetLastError` at `0x180026397`
- `KERNEL32!SetLastError` at `0x180026667`
- `KERNEL32!SetLastError` at `0x1800267b3`
- `KERNEL32!SetLastError` at `0x180026a7f`
- `KERNEL32!SetLastError` at `0x180025fab`
- `KERNEL32!SetLastError` at `0x18002601b`
- `KERNEL32!SetLastError` at `0x180026120`
- `KERNEL32!SetLastError` at `0x1800262a7`
- `KERNEL32!SetLastError` at `0x180026397`
- `KERNEL32!SetLastError` at `0x180026667`
- `KERNEL32!SetLastError` at `0x1800267b3`
- `KERNEL32!SetLastError` at `0x180026a7f`
- `KERNEL32!GetLastError` at `0x180026077`
- `KERNEL32!GetLastError` at `0x180026184`
- `KERNEL32!GetLastError` at `0x18002631b`
- `KERNEL32!GetLastError` at `0x180026401`
- `KERNEL32!GetLastError` at `0x1800264fd`
- `KERNEL32!GetLastError` at `0x18002657c`
- `KERNEL32!GetLastError` at `0x18002660d`
- `KERNEL32!GetLastError` at `0x1800267ed`
- `KERNEL32!GetLastError` at `0x180026889`
- `KERNEL32!GetLastError` at `0x1800268f7`
- `KERNEL32!GetLastError` at `0x180026986`
- `KERNEL32!GetLastError` at `0x180026077`
- `KERNEL32!GetLastError` at `0x180026184`
- `KERNEL32!GetLastError` at `0x18002631b`
- `KERNEL32!GetLastError` at `0x180026401`
- `KERNEL32!GetLastError` at `0x1800264fd`
- `KERNEL32!GetLastError` at `0x18002657c`
- `KERNEL32!GetLastError` at `0x18002660d`
- `KERNEL32!GetLastError` at `0x1800267ed`
- `KERNEL32!GetLastError` at `0x180026889`
- `KERNEL32!GetLastError` at `0x1800268f7`
- `KERNEL32!GetLastError` at `0x180026986`
- `WINSPOOL!GetPrinterW` at `0x1800260c4`
- `WINSPOOL!GetPrinterW` at `0x180026150`
- `WINSPOOL!GetPrinterW` at `0x1800260c4`
- `WINSPOOL!GetPrinterW` at `0x180026150`
- `WINSPOOL!OpenPrinterW` at `0x180026037`
- `WINSPOOL!OpenPrinterW` at `0x180026037`
- `WINSPOOL!SetJobW` at `0x1800265bc`
- `WINSPOOL!SetJobW` at `0x180026853`
- `WINSPOOL!SetJobW` at `0x1800265bc`
- `WINSPOOL!SetJobW` at `0x180026853`
- `WINSPOOL!ClosePrinter` at `0x180026940`
- `WINSPOOL!ClosePrinter` at `0x180026a02`
- `WINSPOOL!ClosePrinter` at `0x180026940`
- `WINSPOOL!ClosePrinter` at `0x180026a02`
- `WINSPOOL!DocumentPropertiesW` at `0x1800262dd`
- `WINSPOOL!DocumentPropertiesW` at `0x1800263c2`
- `WINSPOOL!DocumentPropertiesW` at `0x1800262dd`
- `WINSPOOL!DocumentPropertiesW` at `0x1800263c2`
- `GDI32!DeleteDC` at `0x180026954`
- `GDI32!DeleteDC` at `0x180026954`
- `GDI32!StartDocW` at `0x180026538`
- `GDI32!StartDocW` at `0x180026538`
- `GDI32!CreateDCW` at `0x1800264b4`
- `GDI32!CreateDCW` at `0x1800264b4`

## string_xrefs

- `0x180026732`: `<$FAXTAG$ SDR_COMPANY>`

## pseudocode

```c
__int64 __fastcall FaxStartPrintJob2W(LPWSTR pPrinterName, __int64 a2, __int16 a3, signed int *a4, __int64 a5)
{
  __int64 v5; // r12
  WCHAR *v7; // rdx
  signed int *v8; // rax
  _DWORD *v9; // rcx
  _WORD *v10; // rax
  __int64 v11; // rdx
  DEVMODEW *v12; // rsi
  void *Job; // r13
  HDC v14; // rdi
  const wchar_t **v15; // r15
  WCHAR *v16; // r14
  LPWSTR v17; // rbx
  char LastError; // al
  DWORD v19; // eax
  signed int started; // r14d
  wchar_t *v21; // rax
  const wchar_t *v22; // rcx
  __int64 v23; // rax
  _WORD *v24; // r8
  __int64 v25; // rdx
  _WORD *v26; // rcx
  unsigned int v27; // edi
  DWORD v28; // ecx
  LONG v29; // eax
  DWORD v30; // eax
  __int64 v31; // rdx
  DWORD v32; // ecx
  _DWORD *v33; // rcx
  _DWORD *v34; // rdx
  unsigned int v35; // eax
  const WCHAR *v36; // rax
  unsigned int v37; // edx
  __int64 v38; // rax
  __int64 v39; // r12
  int v40; // eax
  unsigned int v41; // edi
  DWORD v42; // ecx
  __int64 v43; // rax
  __int64 v44; // rdx
  void *v45; // rbx
  DWORD v46; // eax
  DWORD v47; // eax
  DWORD v48; // eax
  __int64 result; // rax
  HDC DCW; // [rsp+38h] [rbp-C8h]
  unsigned int v52; // [rsp+40h] [rbp-C0h] BYREF
  const wchar_t **v53; // [rsp+48h] [rbp-B8h]
  HANDLE phPrinter; // [rsp+50h] [rbp-B0h] BYREF
  DWORD cbBuf; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR pwszDevice; // [rsp+60h] [rbp-A0h]
  signed int *v57; // [rsp+68h] [rbp-98h]
  __int64 v58; // [rsp+70h] [rbp-90h]
  DOCINFOW v59; // [rsp+78h] [rbp-88h] BYREF
  _QWORD v60[22]; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int16 v61[12]; // [rsp+150h] [rbp+50h] BYREF

  v5 = a5;
  LOWORD(v52) = a3;
  v7 = pPrinterName;
  v58 = a5;
  phPrinter = 0;
  v8 = a4;
  v57 = a4;
  memset(&v59, 0, sizeof(v59));
  cbBuf = 0;
  v9 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids);
    v9 = WPP_GLOBAL_Control;
    v8 = v57;
    v7 = pPrinterName;
  }
  if ( !a2 || *(_DWORD *)a2 != 88 || !v8 || !a5 )
  {
    if ( v9 == (_DWORD *)&WPP_GLOBAL_Control || (v9[7] & 0x1000) == 0 || *((_BYTE *)v9 + 25) < 2u )
      goto LABEL_174;
    v11 = 20;
    goto LABEL_173;
  }
  if ( !*(_QWORD *)(a2 + 80) )
  {
    v10 = *(_WORD **)(a2 + 24);
    if ( !v10 || !*v10 )
    {
      if ( v9 == (_DWORD *)&WPP_GLOBAL_Control || (v9[7] & 0x1000) == 0 || *((_BYTE *)v9 + 25) < 2u )
        goto LABEL_174;
      v11 = 21;
LABEL_173:
      WPP_SF_(*((_QWORD *)v9 + 2), v11, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids);
LABEL_174:
      SetLastError(0x57u);
      return 0;
    }
  }
  if ( *(_QWORD *)(a2 + 64) )
  {
    if ( v9 == (_DWORD *)&WPP_GLOBAL_Control || (v9[7] & 0x1000) == 0 || *((_BYTE *)v9 + 25) < 2u )
      goto LABEL_174;
    v11 = 22;
    goto LABEL_173;
  }
  v53 = 0;
  v12 = 0;
  Job = 0;
  v14 = 0;
  v15 = 0;
  if ( v7 )
  {
    pwszDevice = v7;
    v16 = v7;
    if ( !(unsigned int)IsPrinterFaxPrinter(v7) )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0 )
      {
        v17 = pPrinterName;
      }
      else
      {
        v17 = pPrinterName;
        if ( *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
          WPP_SF_S(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            24,
            WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids,
            pPrinterName);
      }
      SetLastError(0x709u);
      goto LABEL_148;
    }
  }
  else
  {
    pwszDevice = GetFaxPrinterName(0);
    v16 = (WCHAR *)pwszDevice;
    if ( !pwszDevice )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids);
      }
      SetLastError(0x709u);
      goto LABEL_147;
    }
  }
  if ( !OpenPrinterW(v16, &phPrinter, 0) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      LastError = GetLastError();
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        25,
        (unsigned int)WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids,
        (_DWORD)v16,
        LastError);
    }
    goto LABEL_147;
  }
  if ( !GetPrinterW(phPrinter, 2u, 0, 0, &cbBuf) )
  {
    v15 = (const wchar_t **)pMemAlloc(cbBuf);
    if ( !v15 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids);
      }
      SetLastError(8u);
      v15 = 0;
      goto LABEL_147;
    }
  }
  if ( !GetPrinterW(phPrinter, 2u, (LPBYTE)v15, cbBuf, &cbBuf) )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids, v19);
    }
    v53 = 0;
    v12 = 0;
    Job = 0;
    v14 = 0;
    if ( !v15 )
    {
      v15 = 0;
LABEL_147:
      v17 = pPrinterName;
LABEL_148:
      if ( phPrinter )
        ClosePrinter(phPrinter);
      if ( v14
        && !DeleteDC(v14)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v48 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 40, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids, v48);
      }
      if ( v12 )
        pMemFree(v12);
      if ( v15 )
        pMemFree(v15);
      if ( Job )
        pMemFree(Job);
      if ( !v17 )
        pMemFree(v16);
      return 0;
    }
    started = 0;
LABEL_139:
    pMemFree(v15);
    if ( started
      && (int)EndDocEx(0) <= 0
      && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v47 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids, v47);
    }
    v16 = (WCHAR *)pwszDevice;
    v15 = v53;
    goto LABEL_147;
  }
  started = 0;
  if ( *v15 )
  {
    v21 = wcsstr(*v15, L"\\\\");
    v22 = *v15;
    if ( *v15 == v21 )
    {
      v22 += 2;
      *v15 = v22;
    }
    v23 = 2147483646;
    v24 = (_WORD *)(a5 + 16);
    v25 = 16;
    do
    {
      if ( !v23 )
        break;
      if ( !*v22 )
        break;
      *v24++ = *v22++;
      --v23;
      --v25;
    }
    while ( v25 );
    v26 = v24 - 1;
    v27 = v25 == 0 ? 0x8007007A : 0;
    if ( v25 )
      v26 = v24;
    *v26 = 0;
    if ( !v25 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 28, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids, v27);
      }
      v28 = (unsigned __int16)v27;
      if ( (v27 & 0x1FFF0000) != 0x70000 )
        v28 = v27;
      SetLastError(v28);
      v14 = 0;
      goto LABEL_139;
    }
    v14 = 0;
  }
  else
  {
    *(_WORD *)(a5 + 16) = 0;
  }
  v29 = DocumentPropertiesW(0, phPrinter, 0, 0, 0, 0);
  if ( v29 <= 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_139;
    }
    v30 = GetLastError();
    v31 = 29;
    goto LABEL_78;
  }
  v12 = (DEVMODEW *)pMemAlloc(v29);
  if ( !v12 )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 30, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids);
    }
    v32 = 8;
LABEL_85:
    SetLastError(v32);
    goto LABEL_139;
  }
  if ( DocumentPropertiesW(0, phPrinter, 0, v12, 0, 2u) != 1 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_139;
    }
    v30 = GetLastError();
    v31 = 31;
    goto LABEL_78;
  }
  if ( v12->dmDriverExtra < 0x3D0u )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 32, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids);
    }
    v32 = 13;
    goto LABEL_85;
  }
  v33 = (_DWORD *)((char *)v12->dmDeviceName + v12->dmSize);
  v34 = v33 + 1;
  if ( *v33 == 2019649092 )
    v34 = (_DWORD *)((char *)v12->dmDeviceName + v12->dmSize);
  v35 = v34[1] & 0xFFFFFFF7;
  v34[2] = 0;
  v34[1] = v35 | 4;
  if ( (_WORD)v52 )
    v12->dmYResolution = v52;
  DCW = CreateDCW(L"WINSPOOL", pwszDevice, 0, v12);
  v14 = DCW;
  if ( !DCW )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_139;
    }
    v30 = GetLastError();
    v31 = 33;
    goto LABEL_78;
  }
  v59.lpszDocName = *(LPCWSTR *)(a2 + 8);
  v36 = *(const WCHAR **)(a2 + 80);
  v59.lpszDatatype = 0;
  v59.fwType = 0;
  v59.lpszOutput = v36;
  v59.cbSize = 40;
  started = StartDocW(DCW, &v59);
  if ( started <= 0 )
  {
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
      || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_139;
    }
    v30 = GetLastError();
    v31 = 34;
    goto LABEL_78;
  }
  if ( *(_QWORD *)(a2 + 80) )
  {
    v45 = 0;
  }
  else
  {
    if ( *v57 == -1 )
      SetJobW(phPrinter, started, 0, 0, 1u);
    Job = MyGetJob(phPrinter, v37, started);
    if ( !Job )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_139;
      }
      v30 = GetLastError();
      v31 = 35;
LABEL_78:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v31, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids, v30);
      goto LABEL_139;
    }
    v38 = *(_QWORD *)(a2 + 72);
    v39 = 0;
    if ( v38 )
      v39 = *(_QWORD *)(a2 + 72);
    v40 = StringCchPrintfW(v61, 0xAu, L"%d", v38 != 0);
    v41 = v40;
    if ( v40 < 0 )
    {
      v42 = (unsigned __int16)v40;
      if ( (v40 & 0x1FFF0000) != 0x70000 )
        v42 = v40;
      SetLastError(v42);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 36, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids, v41);
      }
LABEL_138:
      v14 = DCW;
      goto LABEL_139;
    }
    v60[7] = v39;
    v60[1] = L"1";
    v60[2] = L"<$FAXTAG$ BILL>";
    v60[3] = *(_QWORD *)(a2 + 56);
    v60[15] = L"1";
    v60[4] = L"<$FAXTAG$ RECEIPT_TYPE>";
    v60[17] = L"1";
    v60[5] = v61;
    v60[0] = L"<$FAXTAG$ NEWREC>";
    v60[6] = L"<$FAXTAG$ RECEIPT_ADDR>";
    v60[8] = L"<$FAXTAG$ SDR_NAME>";
    v60[9] = *(_QWORD *)(a2 + 32);
    v60[10] = L"<$FAXTAG$ SDR_COMPANY>";
    v60[11] = *(_QWORD *)(a2 + 40);
    v60[12] = L"<$FAXTAG$ SDR_DEPT>";
    v60[13] = *(_QWORD *)(a2 + 48);
    v60[14] = L"<$FAXTAG$ RECPCOUNT>";
    v60[18] = L"<$FAXTAG$ REC_NAME>";
    v60[19] = *(_QWORD *)(a2 + 16);
    v60[20] = L"<$FAXTAG$ REC_NUM>";
    v60[21] = *(_QWORD *)(a2 + 24);
    v60[16] = L"<$FAXTAG$ NEWREC>";
    v52 = 0;
    ParamTagsToString(v60, L"<$FAXTAG$ NEWREC>", 0, &v52);
    v43 = pMemAlloc(v52 + 2LL);
    v53 = (const wchar_t **)v43;
    v45 = (void *)v43;
    if ( !v43 )
    {
      SetLastError(8u);
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        GetLastError();
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 37, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids);
      }
      goto LABEL_138;
    }
    ParamTagsToString(v60, v44, v43, &v52);
    *((_DWORD *)Job + 28) = 0;
    *((_QWORD *)Job + 10) = 0;
    *((_QWORD *)Job + 8) = v45;
    if ( !SetJobW(phPrinter, started, 2u, (LPBYTE)Job, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_DWORD *)WPP_GLOBAL_Control + 7) & 0x1000) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v46 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids, v46);
      }
      goto LABEL_138;
    }
    v5 = v58;
    v14 = DCW;
  }
  ClosePrinter(phPrinter);
  pMemFree(v15);
  pMemFree(v12);
  pMemFree(v45);
  pMemFree(Job);
  if ( !pPrinterName )
    pMemFree((LPVOID)pwszDevice);
  *v57 = started;
  result = 1;
  *(_QWORD *)(v5 + 8) = v14;
  return result;
}

```

## disassembly

```asm
0x180025df0  mov     [rsp-8+arg_10], rbx
0x180025df5  push    rbp
0x180025df6  push    rsi
0x180025df7  push    rdi
0x180025df8  push    r12
0x180025dfa  push    r13
0x180025dfc  push    r14
0x180025dfe  push    r15
0x180025e00  lea     rbp, [rsp-70h]
0x180025e05  sub     rsp, 170h
0x180025e0c  mov     rax, cs:__security_cookie
0x180025e13  xor     rax, rsp
0x180025e16  mov     [rbp+0A0h+var_38], rax
0x180025e1a  mov     r12, [rbp+0A0h+arg_20]
0x180025e21  xor     r14d, r14d
0x180025e24  xorps   xmm0, xmm0
0x180025e27  mov     [rsp+1A0h+var_170], rcx
0x180025e2c  mov     rbx, rdx
0x180025e2f  mov     word ptr [rsp+1A0h+var_160], r8w
0x180025e35  mov     rdx, rcx
0x180025e38  mov     [rsp+1A0h+var_130], r12
0x180025e3d  xor     ecx, ecx
0x180025e3f  mov     [rsp+1A0h+phPrinter], r14
0x180025e44  mov     rax, r9
0x180025e47  mov     qword ptr [rbp+0A0h+var_128.fwType], rcx
0x180025e4b  mov     [rsp+1A0h+var_138], rax
0x180025e50  movups  xmmword ptr [rsp+1A0h+var_128.cbSize], xmm0
0x180025e55  mov     [rsp+1A0h+cbBuf], r14d
0x180025e5a  movups  xmmword ptr [rbp+0A0h+var_128.lpszOutput], xmm0
0x180025e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e65  lea     r9, WPP_GLOBAL_Control
0x180025e6c  mov     r8d, 1000h
0x180025e72  cmp     rcx, r9
0x180025e75  jz      short loc_180025EB5
0x180025e77  test    [rcx+1Ch], r8d
0x180025e7b  jz      short loc_180025EB5
0x180025e7d  cmp     byte ptr [rcx+19h], 5
0x180025e81  jb      short loc_180025EB5
0x180025e83  mov     rcx, [rcx+10h]
0x180025e87  lea     edx, [r14+13h]
0x180025e8b  lea     r8, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids
0x180025e92  call    WPP_SF_
0x180025e97  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e9e  lea     r9, WPP_GLOBAL_Control
0x180025ea5  mov     rax, [rsp+1A0h+var_138]
0x180025eaa  mov     r8d, 1000h
0x180025eb0  mov     rdx, [rsp+1A0h+var_170]
0x180025eb5  test    rbx, rbx
0x180025eb8  jz      loc_180026A54
0x180025ebe  cmp     dword ptr [rbx], 58h ; 'X'
0x180025ec1  jnz     loc_180026A54
0x180025ec7  test    rax, rax
0x180025eca  jz      loc_180026A54
0x180025ed0  test    r12, r12
0x180025ed3  jz      loc_180026A54
0x180025ed9  cmp     [rbx+50h], r14
0x180025edd  jnz     short loc_180025F15
0x180025edf  mov     rax, [rbx+18h]
0x180025ee3  test    rax, rax
0x180025ee6  jz      short loc_180025EEE
0x180025ee8  cmp     [rax], r14w
0x180025eec  jnz     short loc_180025F15
0x180025eee  cmp     rcx, r9
0x180025ef1  jz      loc_180026A7A
0x180025ef7  test    [rcx+1Ch], r8d
0x180025efb  jz      loc_180026A7A
0x180025f01  cmp     byte ptr [rcx+19h], 2
0x180025f05  jb      loc_180026A7A
0x180025f0b  mov     edx, 15h
0x180025f10  jmp     loc_180026A6A
0x180025f15  cmp     [rbx+40h], r14
0x180025f19  jz      short loc_180025F42
0x180025f1b  cmp     rcx, r9
0x180025f1e  jz      loc_180026A7A
0x180025f24  test    [rcx+1Ch], r8d
0x180025f28  jz      loc_180026A7A
0x180025f2e  cmp     byte ptr [rcx+19h], 2
0x180025f32  jb      loc_180026A7A
0x180025f38  mov     edx, 16h
0x180025f3d  jmp     loc_180026A6A
0x180025f42  mov     [rsp+1A0h+var_158], r14
0x180025f47  mov     rsi, r14
0x180025f4a  mov     r13, r14
0x180025f4d  mov     rdi, r14
0x180025f50  mov     r15, r14
0x180025f53  test    rdx, rdx
0x180025f56  jnz     short loc_180025FBC
0x180025f58  xor     ecx, ecx; void *
0x180025f5a  call    ?GetFaxPrinterName@@YAPEAGPEAX@Z; GetFaxPrinterName(void *)
0x180025f5f  mov     [rsp+1A0h+pwszDevice], rax
0x180025f64  mov     r14, rax
0x180025f67  test    rax, rax
0x180025f6a  jnz     loc_18002602C
0x180025f70  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f77  lea     rax, WPP_GLOBAL_Control
0x180025f7e  cmp     rcx, rax
0x180025f81  jz      short loc_180025FA6
0x180025f83  test    dword ptr [rcx+1Ch], 1000h
0x180025f8a  jz      short loc_180025FA6
0x180025f8c  cmp     byte ptr [rcx+19h], 2
0x180025f90  jb      short loc_180025FA6
0x180025f92  mov     rcx, [rcx+10h]
0x180025f96  lea     edx, [r14+17h]
0x180025f9a  lea     r8, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids
0x180025fa1  call    WPP_SF_
0x180025fa6  mov     ecx, 709h; dwErrCode
0x180025fab  call    cs:__imp_SetLastError
0x180025fb2  nop     dword ptr [rax+rax+00h]
0x180025fb7  jmp     loc_180026931
0x180025fbc  mov     rcx, rdx; pPrinterName
0x180025fbf  mov     [rsp+1A0h+pwszDevice], rdx
0x180025fc4  mov     r14, rdx
0x180025fc7  call    IsPrinterFaxPrinter
0x180025fcc  test    eax, eax
0x180025fce  jnz     short loc_18002602C
0x180025fd0  mov     rcx, cs:WPP_GLOBAL_Control
0x180025fd7  lea     rax, WPP_GLOBAL_Control
0x180025fde  cmp     rcx, rax
0x180025fe1  jz      short loc_180026011
0x180025fe3  test    dword ptr [rcx+1Ch], 1000h
0x180025fea  jz      short loc_180026011
0x180025fec  cmp     byte ptr [rcx+19h], 2
0x180025ff0  mov     rbx, [rsp+1A0h+var_170]
0x180025ff5  jb      short loc_180026016
0x180025ff7  mov     rcx, [rcx+10h]
0x180025ffb  lea     r8, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids
0x180026002  mov     edx, 18h
0x180026007  mov     r9, rbx
0x18002600a  call    WPP_SF_S
0x18002600f  jmp     short loc_180026016
0x180026011  mov     rbx, [rsp+1A0h+var_170]
0x180026016  mov     ecx, 709h; dwErrCode
0x18002601b  call    cs:__imp_SetLastError
0x180026022  nop     dword ptr [rax+rax+00h]
0x180026027  jmp     loc_180026936
0x18002602c  xor     r8d, r8d; pDefault
0x18002602f  lea     rdx, [rsp+1A0h+phPrinter]; phPrinter
0x180026034  mov     rcx, r14; pPrinterName
0x180026037  call    cs:__imp_OpenPrinterW
0x18002603e  nop     dword ptr [rax+rax+00h]
0x180026043  xor     ecx, ecx
0x180026045  test    eax, eax
0x180026047  jnz     short loc_1800260AB
0x180026049  mov     rax, cs:WPP_GLOBAL_Control
0x180026050  lea     rcx, WPP_GLOBAL_Control
0x180026057  cmp     rax, rcx
0x18002605a  jz      loc_180026931
0x180026060  test    dword ptr [rax+1Ch], 1000h
0x180026067  jz      loc_180026931
0x18002606d  cmp     byte ptr [rax+19h], 2
0x180026071  jb      loc_180026931
0x180026077  call    cs:__imp_GetLastError
0x18002607e  nop     dword ptr [rax+rax+00h]
0x180026083  mov     rcx, cs:WPP_GLOBAL_Control
0x18002608a  lea     r8, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids
0x180026091  mov     edx, 19h
0x180026096  mov     dword ptr [rsp+1A0h+pcbNeeded], eax
0x18002609a  mov     r9, r14
0x18002609d  mov     rcx, [rcx+10h]
0x1800260a1  call    WPP_SF_Sd
0x1800260a6  jmp     loc_180026931
0x1800260ab  mov     rcx, [rsp+1A0h+phPrinter]; hPrinter
0x1800260b0  lea     rax, [rsp+1A0h+cbBuf]
0x1800260b5  xor     r9d, r9d; cbBuf
0x1800260b8  mov     [rsp+1A0h+pcbNeeded], rax; pcbNeeded
0x1800260bd  xor     r8d, r8d; pPrinter
0x1800260c0  lea     edx, [r9+2]; Level
0x1800260c4  call    cs:__imp_GetPrinterW
0x1800260cb  nop     dword ptr [rax+rax+00h]
0x1800260d0  test    eax, eax
0x1800260d2  jnz     short loc_180026134
0x1800260d4  mov     ecx, [rsp+1A0h+cbBuf]; dwBytes
0x1800260d8  call    pMemAlloc
0x1800260dd  mov     r15, rax
0x1800260e0  test    rax, rax
0x1800260e3  jnz     short loc_180026134
0x1800260e5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800260ec  lea     rax, WPP_GLOBAL_Control
0x1800260f3  cmp     rcx, rax
0x1800260f6  jz      short loc_18002611B
0x1800260f8  test    dword ptr [rcx+1Ch], 1000h
0x1800260ff  jz      short loc_18002611B
0x180026101  cmp     byte ptr [rcx+19h], 2
0x180026105  jb      short loc_18002611B
0x180026107  mov     rcx, [rcx+10h]
0x18002610b  lea     edx, [r15+1Ah]
0x18002610f  lea     r8, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids
0x180026116  call    WPP_SF_
0x18002611b  mov     ecx, 8; dwErrCode
0x180026120  call    cs:__imp_SetLastError
0x180026127  nop     dword ptr [rax+rax+00h]
0x18002612c  mov     r15, rsi
0x18002612f  jmp     loc_180026931
0x180026134  mov     r9d, [rsp+1A0h+cbBuf]; cbBuf
0x180026139  lea     rax, [rsp+1A0h+cbBuf]
0x18002613e  mov     rcx, [rsp+1A0h+phPrinter]; hPrinter
0x180026143  mov     r8, r15; pPrinter
0x180026146  mov     edx, 2; Level
0x18002614b  mov     [rsp+1A0h+pcbNeeded], rax; pcbNeeded
0x180026150  call    cs:__imp_GetPrinterW
0x180026157  nop     dword ptr [rax+rax+00h]
0x18002615c  xor     ecx, ecx
0x18002615e  test    eax, eax
0x180026160  jnz     short loc_1800261D0
0x180026162  mov     rax, cs:WPP_GLOBAL_Control
0x180026169  lea     r12, WPP_GLOBAL_Control
0x180026170  cmp     rax, r12
0x180026173  jz      short loc_1800261B1
0x180026175  test    dword ptr [rax+1Ch], 1000h
0x18002617c  jz      short loc_1800261B1
0x18002617e  cmp     byte ptr [rax+19h], 2
0x180026182  jb      short loc_1800261B1
0x180026184  call    cs:__imp_GetLastError
0x18002618b  nop     dword ptr [rax+rax+00h]
0x180026190  mov     rcx, cs:WPP_GLOBAL_Control
0x180026197  lea     r8, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids
0x18002619e  mov     edx, 1Bh
0x1800261a3  mov     r9d, eax
0x1800261a6  mov     rcx, [rcx+10h]
0x1800261aa  call    WPP_SF_d
0x1800261af  xor     ecx, ecx
0x1800261b1  mov     [rsp+1A0h+var_158], rcx
0x1800261b6  mov     rsi, rcx
0x1800261b9  mov     r13, rcx
0x1800261bc  mov     rdi, rcx
0x1800261bf  test    r15, r15
0x1800261c2  jz      loc_18002692E
0x1800261c8  mov     r14d, ecx
0x1800261cb  jmp     loc_1800268B9
0x1800261d0  mov     r14d, ecx
0x1800261d3  xor     r10d, r10d
0x1800261d6  mov     rcx, [r15]; Str
0x1800261d9  test    rcx, rcx
0x1800261dc  jz      loc_1800262BB
0x1800261e2  lea     rdx, SubStr; "\\\\"
0x1800261e9  call    cs:__imp_wcsstr
0x1800261f0  nop     dword ptr [rax+rax+00h]
0x1800261f5  mov     rcx, [r15]
0x1800261f8  cmp     rcx, rax
0x1800261fb  jnz     short loc_180026204
0x1800261fd  add     rcx, 4
0x180026201  mov     [r15], rcx
0x180026204  mov     eax, 7FFFFFFEh
0x180026209  lea     r8, [r12+10h]
0x18002620e  mov     edx, 10h
0x180026213  xor     r10d, r10d
0x180026216  test    rax, rax
0x180026219  jz      short loc_18002623A
0x18002621b  movzx   r9d, word ptr [rcx]
0x18002621f  test    r9w, r9w
0x180026223  jz      short loc_18002623A
0x180026225  mov     [r8], r9w
0x180026229  add     rcx, 2
0x18002622d  add     r8, 2
0x180026231  dec     rax
0x180026234  sub     rdx, 1
0x180026238  jnz     short loc_180026216
0x18002623a  mov     rax, rdx
0x18002623d  lea     rcx, [r8-2]
0x180026241  neg     rax
0x180026244  sbb     edi, edi
0x180026246  not     edi
0x180026248  and     edi, 8007007Ah
0x18002624e  test    rdx, rdx
0x180026251  cmovnz  rcx, r8
0x180026255  mov     [rcx], r10w
0x180026259  jnz     short loc_1800262C3
0x18002625b  mov     rcx, cs:WPP_GLOBAL_Control
0x180026262  lea     r12, WPP_GLOBAL_Control
0x180026269  cmp     rcx, r12
0x18002626c  jz      short loc_180026295
0x18002626e  test    dword ptr [rcx+1Ch], 1000h
0x180026275  jz      short loc_180026295
0x180026277  cmp     byte ptr [rcx+19h], 2
0x18002627b  jb      short loc_180026295
0x18002627d  mov     rcx, [rcx+10h]
0x180026281  lea     r8, WPP_4b4d538ff41b3f7b7122920a4eb111f7_Traceguids
0x180026288  mov     edx, 1Ch
0x18002628d  mov     r9d, edi
0x180026290  call    WPP_SF_d
0x180026295  mov     eax, edi
0x180026297  movzx   ecx, di
0x18002629a  and     eax, 1FFF0000h
0x18002629f  cmp     eax, 70000h
0x1800262a4  cmovnz  ecx, edi; dwErrCode
0x1800262a7  call    cs:__imp_SetLastError
0x1800262ae  nop     dword ptr [rax+rax+00h]
0x1800262b3  mov     rdi, rsi
0x1800262b6  jmp     loc_1800268B9
0x1800262bb  mov     [r12+10h], r10w
0x1800262c1  jmp     short loc_1800262C6
0x1800262c3  mov     rdi, rsi
0x1800262c6  mov     rdx, [rsp+1A0h+phPrinter]; hPrinter
0x1800262cb  xor     r9d, r9d; pDevModeOutput
0x1800262ce  mov     [rsp+1A0h+fMode], r10d; fMode
0x1800262d3  xor     r8d, r8d; pDeviceName
0x1800262d6  xor     ecx, ecx; hWnd
0x1800262d8  mov     [rsp+1A0h+pcbNeeded], r10; pDevModeInput
0x1800262dd  call    cs:__imp_DocumentPropertiesW
0x1800262e4  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
