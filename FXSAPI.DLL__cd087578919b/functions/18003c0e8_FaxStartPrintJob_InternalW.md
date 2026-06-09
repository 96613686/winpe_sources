# FaxStartPrintJob_InternalW

- ea: `0x18003c0e8`
- end: `0x18003cc77`
- name: `FaxStartPrintJob_InternalW`
- size: `2959`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180038190`

## callees

- `0x1800084ac`
- `0x18000abe4`
- `0x18000ac14`
- `0x180014314`
- `0x180021530`
- `0x180025104`
- `0x18002bab8`
- `0x18002bb58`
- `0x18002fe1c`
- `0x180030314`
- `0x18003c0e8`
- `0x18003d510`

## import_xrefs

- `msvcrt!wcsstr` at `0x18003c4b0`
- `msvcrt!wcsstr` at `0x18003c4b0`
- `KERNEL32!SetLastError` at `0x18003c274`
- `KERNEL32!SetLastError` at `0x18003c413`
- `KERNEL32!SetLastError` at `0x18003c8ea`
- `KERNEL32!SetLastError` at `0x18003ca27`
- `KERNEL32!SetLastError` at `0x18003cc41`
- `KERNEL32!SetLastError` at `0x18003c274`
- `KERNEL32!SetLastError` at `0x18003c413`
- `KERNEL32!SetLastError` at `0x18003c8ea`
- `KERNEL32!SetLastError` at `0x18003ca27`
- `KERNEL32!SetLastError` at `0x18003cc41`
- `KERNEL32!GetLastError` at `0x18003c2fc`
- `KERNEL32!GetLastError` at `0x18003c36e`
- `KERNEL32!GetLastError` at `0x18003c476`
- `KERNEL32!GetLastError` at `0x18003c5ce`
- `KERNEL32!GetLastError` at `0x18003c684`
- `KERNEL32!GetLastError` at `0x18003c772`
- `KERNEL32!GetLastError` at `0x18003c7f8`
- `KERNEL32!GetLastError` at `0x18003c879`
- `KERNEL32!GetLastError` at `0x18003ca56`
- `KERNEL32!GetLastError` at `0x18003cb01`
- `KERNEL32!GetLastError` at `0x18003cb69`
- `KERNEL32!GetLastError` at `0x18003c2fc`
- `KERNEL32!GetLastError` at `0x18003c36e`
- `KERNEL32!GetLastError` at `0x18003c476`
- `KERNEL32!GetLastError` at `0x18003c5ce`
- `KERNEL32!GetLastError` at `0x18003c684`
- `KERNEL32!GetLastError` at `0x18003c772`
- `KERNEL32!GetLastError` at `0x18003c7f8`
- `KERNEL32!GetLastError` at `0x18003c879`
- `KERNEL32!GetLastError` at `0x18003ca56`
- `KERNEL32!GetLastError` at `0x18003cb01`
- `KERNEL32!GetLastError` at `0x18003cb69`
- `WINSPOOL!GetPrinterW` at `0x18003c3bb`
- `WINSPOOL!GetPrinterW` at `0x18003c443`
- `WINSPOOL!GetPrinterW` at `0x18003c3bb`
- `WINSPOOL!GetPrinterW` at `0x18003c443`
- `WINSPOOL!OpenPrinterW` at `0x18003c32f`
- `WINSPOOL!OpenPrinterW` at `0x18003c32f`
- `WINSPOOL!SetJobW` at `0x18003c833`
- `WINSPOOL!SetJobW` at `0x18003cabe`
- `WINSPOOL!SetJobW` at `0x18003c833`
- `WINSPOOL!SetJobW` at `0x18003cabe`
- `WINSPOOL!ClosePrinter` at `0x18003c292`
- `WINSPOOL!ClosePrinter` at `0x18003cbc8`
- `WINSPOOL!ClosePrinter` at `0x18003c292`
- `WINSPOOL!ClosePrinter` at `0x18003cbc8`
- `WINSPOOL!DocumentPropertiesW` at `0x18003c58f`
- `WINSPOOL!DocumentPropertiesW` at `0x18003c644`
- `WINSPOOL!DocumentPropertiesW` at `0x18003c58f`
- `WINSPOOL!DocumentPropertiesW` at `0x18003c644`
- `GDI32!EndDoc` at `0x18003c2b9`
- `GDI32!EndDoc` at `0x18003c2b9`
- `GDI32!DeleteDC` at `0x18003cb3d`
- `GDI32!DeleteDC` at `0x18003cb3d`
- `GDI32!StartDocW` at `0x18003c7b0`
- `GDI32!StartDocW` at `0x18003c7b0`
- `GDI32!CreateDCW` at `0x18003c72a`
- `GDI32!CreateDCW` at `0x18003c72a`

## string_xrefs

- `0x18003c99d`: `<$FAXTAG$ SDR_COMPANY>`

## pseudocode

```c
__int64 __fastcall FaxStartPrintJob_InternalW(__int64 a1, __int64 a2, __int64 a3, DWORD *a4, __int64 a5)
{
  DWORD *v6; // rdi
  _BYTE *v7; // rcx
  _WORD *v8; // rax
  __int64 v9; // rdx
  DEVMODEW *v10; // r15
  void *Job; // r14
  const wchar_t **v12; // rsi
  DWORD v13; // r12d
  WCHAR *FaxPrinterNameOnServer; // rax
  void *v15; // rdi
  WCHAR *v16; // r13
  __int64 v17; // rbx
  DWORD LastError; // eax
  __int64 v19; // rbx
  char v20; // al
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  DWORD v23; // ecx
  __int64 v24; // rbx
  DWORD v25; // eax
  __int64 v26; // rdx
  wchar_t *v27; // rax
  const wchar_t *v28; // rcx
  __int64 v29; // rax
  _WORD *v30; // r8
  __int64 v31; // rdx
  _WORD *v32; // rcx
  unsigned int v33; // edi
  LONG v34; // eax
  _DWORD *v35; // rcx
  _DWORD *v36; // rdx
  unsigned int v37; // eax
  signed int started; // eax
  unsigned int v39; // edx
  __int64 v40; // rbx
  DWORD v41; // eax
  __int64 v42; // rax
  __int64 v43; // r12
  int v44; // eax
  unsigned int v45; // edi
  DWORD v46; // ecx
  __int64 v47; // rax
  __int64 v48; // rax
  __int64 v49; // rdx
  __int64 v50; // rbx
  __int64 v51; // rbx
  DWORD v52; // eax
  __int64 v53; // rbx
  DWORD v54; // eax
  HDC v55; // rax
  WCHAR *pwszDevice; // [rsp+30h] [rbp-D0h]
  void *v58; // [rsp+38h] [rbp-C8h] BYREF
  DWORD JobId; // [rsp+40h] [rbp-C0h]
  HANDLE hPrinter; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cbBuf; // [rsp+50h] [rbp-B0h] BYREF
  HDC hdc; // [rsp+58h] [rbp-A8h]
  DWORD *v63; // [rsp+60h] [rbp-A0h]
  DOCINFOW v64; // [rsp+68h] [rbp-98h] BYREF
  _QWORD v65[22]; // [rsp+90h] [rbp-70h] BYREF
  unsigned __int16 v66[12]; // [rsp+140h] [rbp+40h] BYREF

  v63 = a4;
  v6 = a4;
  hPrinter = 0;
  memset(&v64, 0, 36);
  cbBuf = 0;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 10, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids);
    v7 = WPP_GLOBAL_Control;
  }
  if ( !a2 || *(_DWORD *)a2 != 88 || !v6 || !a5 )
  {
    if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || (v7[28] & 2) == 0 || v7[25] < 2u )
      goto LABEL_162;
    v9 = 11;
    goto LABEL_161;
  }
  if ( *(_QWORD *)(a2 + 80) || (v8 = *(_WORD **)(a2 + 24)) != 0 && *v8 )
  {
    if ( *(_QWORD *)(a2 + 64) )
    {
      if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || (v7[28] & 2) == 0 || v7[25] < 2u )
        goto LABEL_162;
      v9 = 13;
      goto LABEL_161;
    }
    hdc = 0;
    v10 = 0;
    v58 = 0;
    Job = 0;
    v12 = 0;
    v13 = 0;
    FaxPrinterNameOnServer = (WCHAR *)GetFaxPrinterNameOnServer(v7, 0, 0);
    pwszDevice = FaxPrinterNameOnServer;
    if ( !FaxPrinterNameOnServer )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 14, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids);
      }
      SetLastError(0x709u);
LABEL_27:
      v15 = 0;
LABEL_28:
      v16 = pwszDevice;
LABEL_29:
      if ( hPrinter )
        ClosePrinter(hPrinter);
      if ( v12 )
        pMemFree(v12);
      if ( v13
        && EndDoc(hdc) <= 0
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v17 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        LastError = GetLastError();
        WPP_SF_d(v17, 30, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids, LastError);
      }
      if ( hdc
        && !DeleteDC(hdc)
        && WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v53 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v54 = GetLastError();
        WPP_SF_d(v53, 31, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids, v54);
      }
      if ( v10 )
        pMemFree(v10);
      if ( v15 )
        pMemFree(v15);
      if ( Job )
        pMemFree(Job);
      pMemFree(v16);
      return 0;
    }
    if ( !OpenPrinterW(FaxPrinterNameOnServer, &hPrinter, 0) )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = *((_QWORD *)WPP_GLOBAL_Control + 2);
        v20 = GetLastError();
        v16 = pwszDevice;
        WPP_SF_Sd(v19, 16, (unsigned int)WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids, (_DWORD)pwszDevice, v20);
        v15 = 0;
        goto LABEL_29;
      }
      goto LABEL_27;
    }
    if ( !GetPrinterW(hPrinter, 2u, 0, 0, &cbBuf) )
    {
      v12 = (const wchar_t **)pMemAlloc(cbBuf);
      if ( !v12 )
      {
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_51;
        }
        v22 = 17;
LABEL_50:
        WPP_SF_(v21[2], v22, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids);
LABEL_51:
        v23 = 8;
LABEL_52:
        SetLastError(v23);
LABEL_53:
        v15 = 0;
        goto LABEL_28;
      }
    }
    if ( !GetPrinterW(hPrinter, 2u, (LPBYTE)v12, cbBuf, &cbBuf) )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v25 = GetLastError();
      v26 = 18;
      goto LABEL_59;
    }
    if ( *v12 )
    {
      v27 = wcsstr(*v12, L"\\\\");
      v28 = *v12;
      if ( *v12 == v27 )
      {
        v28 += 2;
        *v12 = v28;
      }
      v29 = 2147483646;
      v30 = (_WORD *)(a5 + 16);
      v31 = 16;
      do
      {
        if ( !v29 )
          break;
        if ( !*v28 )
          break;
        *v30++ = *v28++;
        --v29;
        --v31;
      }
      while ( v31 );
      v32 = v30 - 1;
      v33 = v31 == 0 ? 0x8007007A : 0;
      if ( v31 )
        v32 = v30;
      *v32 = 0;
      if ( !v31 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids, v33);
        }
        v23 = (unsigned __int16)v33;
        if ( (v33 & 0x1FFF0000) != 0x70000 )
          v23 = v33;
        goto LABEL_52;
      }
      v6 = v63;
    }
    else
    {
      *(_WORD *)(a5 + 16) = 0;
    }
    v34 = DocumentPropertiesW(0, hPrinter, 0, 0, 0, 0);
    if ( v34 <= 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v25 = GetLastError();
      v26 = 20;
      goto LABEL_59;
    }
    v10 = (DEVMODEW *)pMemAlloc(v34);
    if ( !v10 )
    {
      v21 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_51;
      }
      v22 = 21;
      goto LABEL_50;
    }
    if ( DocumentPropertiesW(0, hPrinter, 0, v10, 0, 2u) != 1 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v25 = GetLastError();
      v26 = 22;
      goto LABEL_59;
    }
    if ( v10->dmDriverExtra < 0x3D0u )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids);
      }
      v23 = 13;
      goto LABEL_52;
    }
    v35 = (_DWORD *)((char *)v10->dmDeviceName + v10->dmSize);
    v36 = v35 + 1;
    if ( *v35 == 2019649092 )
      v36 = (_DWORD *)((char *)v10->dmDeviceName + v10->dmSize);
    v37 = v36[1] & 0xFFFFFFF7;
    v36[2] = 0;
    v36[1] = v37 | 4;
    hdc = CreateDCW(L"WINSPOOL", pwszDevice, 0, v10);
    if ( !hdc )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v25 = GetLastError();
      v26 = 24;
      goto LABEL_59;
    }
    v64.lpszDocName = *(LPCWSTR *)(a2 + 8);
    v64.lpszOutput = *(LPCWSTR *)(a2 + 80);
    v64.lpszDatatype = 0;
    v64.fwType = 0;
    v64.cbSize = 40;
    started = StartDocW(hdc, &v64);
    JobId = started;
    v13 = started;
    if ( started <= 0 )
    {
      if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v24 = *((_QWORD *)WPP_GLOBAL_Control + 2);
      v25 = GetLastError();
      v26 = 25;
LABEL_59:
      WPP_SF_d(v24, v26, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids, v25);
      goto LABEL_53;
    }
    if ( *(_QWORD *)(a2 + 80) )
    {
      v15 = 0;
    }
    else
    {
      if ( *v6 == -1 )
        SetJobW(hPrinter, started, 0, 0, 1u);
      Job = MyGetJob(hPrinter, v39, v13);
      if ( !Job )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v40 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v41 = GetLastError();
          WPP_SF_d(v40, 26, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids, v41);
        }
LABEL_120:
        v15 = v58;
        goto LABEL_28;
      }
      v42 = *(_QWORD *)(a2 + 72);
      v43 = 0;
      if ( v42 )
        v43 = *(_QWORD *)(a2 + 72);
      v44 = StringCchPrintfW(v66, 0xAu, L"%d", v42 != 0);
      v45 = v44;
      if ( v44 < 0 )
      {
        v46 = (unsigned __int16)v44;
        if ( (v44 & 0x1FFF0000) != 0x70000 )
          v46 = v44;
        SetLastError(v46);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 27, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids, v45);
        }
        v13 = JobId;
        goto LABEL_120;
      }
      v65[7] = v43;
      v65[1] = L"1";
      v65[2] = L"<$FAXTAG$ BILL>";
      v65[3] = *(_QWORD *)(a2 + 56);
      v65[15] = L"1";
      v65[4] = L"<$FAXTAG$ RECEIPT_TYPE>";
      v65[5] = v66;
      v65[6] = L"<$FAXTAG$ RECEIPT_ADDR>";
      v65[8] = L"<$FAXTAG$ SDR_NAME>";
      v65[9] = *(_QWORD *)(a2 + 32);
      v65[10] = L"<$FAXTAG$ SDR_COMPANY>";
      v65[11] = *(_QWORD *)(a2 + 40);
      v65[12] = L"<$FAXTAG$ SDR_DEPT>";
      v65[13] = *(_QWORD *)(a2 + 48);
      v65[14] = L"<$FAXTAG$ RECPCOUNT>";
      v65[18] = L"<$FAXTAG$ REC_NAME>";
      v65[19] = *(_QWORD *)(a2 + 16);
      v65[20] = L"<$FAXTAG$ REC_NUM>";
      v47 = *(_QWORD *)(a2 + 24);
      v65[17] = L"1";
      LODWORD(v58) = 0;
      v65[0] = L"<$FAXTAG$ NEWREC>";
      v65[16] = L"<$FAXTAG$ NEWREC>";
      v65[21] = v47;
      ParamTagsToString(v65, L"<$FAXTAG$ NEWREC>", 0, &v58);
      v48 = pMemAlloc((unsigned int)v58 + 2LL);
      v15 = (void *)v48;
      if ( !v48 )
      {
        SetLastError(8u);
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v50 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          GetLastError();
          WPP_SF_dd(v50, 28, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids);
        }
        v13 = JobId;
        goto LABEL_28;
      }
      ParamTagsToString(v65, v49, v48, &v58);
      v13 = JobId;
      *((_DWORD *)Job + 28) = 0;
      *((_QWORD *)Job + 10) = 0;
      *((_QWORD *)Job + 8) = v15;
      if ( !SetJobW(hPrinter, v13, 2u, (LPBYTE)Job, 0) )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          v51 = *((_QWORD *)WPP_GLOBAL_Control + 2);
          v52 = GetLastError();
          WPP_SF_d(v51, 29, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids, v52);
        }
        goto LABEL_28;
      }
    }
    ClosePrinter(hPrinter);
    pMemFree(v12);
    pMemFree(v10);
    pMemFree(v15);
    pMemFree(Job);
    pMemFree(pwszDevice);
    v55 = hdc;
    *v63 = v13;
    *(_QWORD *)(a5 + 8) = v55;
    return 1;
  }
  if ( v7 == (_BYTE *)&WPP_GLOBAL_Control || (v7[28] & 2) == 0 || v7[25] < 2u )
    goto LABEL_162;
  v9 = 12;
LABEL_161:
  WPP_SF_(*((_QWORD *)v7 + 2), v9, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids);
LABEL_162:
  SetLastError(0x57u);
  return 0;
}

```

## disassembly

```asm
0x18003c0e8  mov     [rsp-8+arg_0], rbx
0x18003c0ed  push    rbp
0x18003c0ee  push    rsi
0x18003c0ef  push    rdi
0x18003c0f0  push    r12
0x18003c0f2  push    r13
0x18003c0f4  push    r14
0x18003c0f6  push    r15
0x18003c0f8  lea     rbp, [rsp-60h]
0x18003c0fd  sub     rsp, 160h
0x18003c104  mov     rax, cs:__security_cookie
0x18003c10b  xor     rax, rsp
0x18003c10e  mov     [rbp+90h+var_38], rax
0x18003c112  mov     r13, [rbp+90h+arg_20]
0x18003c119  xorps   xmm0, xmm0
0x18003c11c  mov     rbx, rdx
0x18003c11f  mov     [rsp+190h+var_130], r9
0x18003c124  xor     edx, edx
0x18003c126  mov     rdi, r9
0x18003c129  xor     eax, eax
0x18003c12b  mov     [rsp+190h+hPrinter], rdx
0x18003c130  mov     [rbp+90h+var_128.fwType], eax
0x18003c133  movups  xmmword ptr [rsp+190h+var_128.cbSize], xmm0
0x18003c138  mov     [rsp+190h+cbBuf], edx
0x18003c13c  movups  xmmword ptr [rsp+190h+var_128.lpszOutput], xmm0
0x18003c141  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c148  lea     r8, WPP_GLOBAL_Control
0x18003c14f  cmp     rcx, r8
0x18003c152  jz      short loc_18003C183
0x18003c154  test    byte ptr [rcx+1Ch], 2
0x18003c158  jz      short loc_18003C183
0x18003c15a  cmp     byte ptr [rcx+19h], 5
0x18003c15e  jb      short loc_18003C183
0x18003c160  mov     rcx, [rcx+10h]
0x18003c164  lea     edx, [rax+0Ah]
0x18003c167  lea     r8, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids
0x18003c16e  call    WPP_SF_
0x18003c173  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c17a  lea     r8, WPP_GLOBAL_Control
0x18003c181  xor     edx, edx
0x18003c183  test    rbx, rbx
0x18003c186  jz      loc_18003CC16
0x18003c18c  cmp     dword ptr [rbx], 58h ; 'X'
0x18003c18f  jnz     loc_18003CC16
0x18003c195  test    rdi, rdi
0x18003c198  jz      loc_18003CC16
0x18003c19e  test    r13, r13
0x18003c1a1  jz      loc_18003CC16
0x18003c1a7  cmp     [rbx+50h], rdx
0x18003c1ab  jnz     short loc_18003C1E2
0x18003c1ad  mov     rax, [rbx+18h]
0x18003c1b1  test    rax, rax
0x18003c1b4  jz      short loc_18003C1BB
0x18003c1b6  cmp     [rax], dx
0x18003c1b9  jnz     short loc_18003C1E2
0x18003c1bb  cmp     rcx, r8
0x18003c1be  jz      loc_18003CC3C
0x18003c1c4  test    byte ptr [rcx+1Ch], 2
0x18003c1c8  jz      loc_18003CC3C
0x18003c1ce  cmp     byte ptr [rcx+19h], 2
0x18003c1d2  jb      loc_18003CC3C
0x18003c1d8  mov     edx, 0Ch
0x18003c1dd  jmp     loc_18003CC2C
0x18003c1e2  cmp     [rbx+40h], rdx
0x18003c1e6  jz      short loc_18003C20F
0x18003c1e8  cmp     rcx, r8
0x18003c1eb  jz      loc_18003CC3C
0x18003c1f1  test    byte ptr [rcx+1Ch], 2
0x18003c1f5  jz      loc_18003CC3C
0x18003c1fb  cmp     byte ptr [rcx+19h], 2
0x18003c1ff  jb      loc_18003CC3C
0x18003c205  mov     edx, 0Dh
0x18003c20a  jmp     loc_18003CC2C
0x18003c20f  xor     r8d, r8d
0x18003c212  mov     [rsp+190h+hdc], rdx
0x18003c217  mov     r15, rdx
0x18003c21a  mov     [rsp+190h+var_158], rdx
0x18003c21f  mov     r14, rdx
0x18003c222  mov     rsi, rdx
0x18003c225  mov     r12d, edx
0x18003c228  call    GetFaxPrinterNameOnServer
0x18003c22d  mov     [rsp+190h+pwszDevice], rax
0x18003c232  test    rax, rax
0x18003c235  jnz     loc_18003C324
0x18003c23b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c242  lea     rax, WPP_GLOBAL_Control
0x18003c249  cmp     rcx, rax
0x18003c24c  jz      short loc_18003C26F
0x18003c24e  test    byte ptr [rcx+1Ch], 2
0x18003c252  jz      short loc_18003C26F
0x18003c254  cmp     byte ptr [rcx+19h], 2
0x18003c258  jb      short loc_18003C26F
0x18003c25a  mov     rcx, [rcx+10h]
0x18003c25e  lea     r8, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids
0x18003c265  mov     edx, 0Eh
0x18003c26a  call    WPP_SF_
0x18003c26f  mov     ecx, 709h; dwErrCode
0x18003c274  call    cs:__imp_SetLastError
0x18003c27b  nop     dword ptr [rax+rax+00h]
0x18003c280  mov     rdi, rsi
0x18003c283  mov     r13, [rsp+190h+pwszDevice]
0x18003c288  mov     rcx, [rsp+190h+hPrinter]; hPrinter
0x18003c28d  test    rcx, rcx
0x18003c290  jz      short loc_18003C29E
0x18003c292  call    cs:__imp_ClosePrinter
0x18003c299  nop     dword ptr [rax+rax+00h]
0x18003c29e  test    rsi, rsi
0x18003c2a1  jz      short loc_18003C2AB
0x18003c2a3  mov     rcx, rsi; lpMem
0x18003c2a6  call    pMemFree
0x18003c2ab  test    r12d, r12d
0x18003c2ae  jz      loc_18003CB29
0x18003c2b4  mov     rcx, [rsp+190h+hdc]; hdc
0x18003c2b9  call    cs:__imp_EndDoc
0x18003c2c0  nop     dword ptr [rax+rax+00h]
0x18003c2c5  test    eax, eax
0x18003c2c7  jg      loc_18003CB29
0x18003c2cd  mov     rbx, cs:WPP_GLOBAL_Control
0x18003c2d4  lea     r12, WPP_GLOBAL_Control
0x18003c2db  cmp     rbx, r12
0x18003c2de  jz      loc_18003CB30
0x18003c2e4  test    byte ptr [rbx+1Ch], 2
0x18003c2e8  jz      loc_18003CB30
0x18003c2ee  cmp     byte ptr [rbx+19h], 2
0x18003c2f2  jb      loc_18003CB30
0x18003c2f8  mov     rbx, [rbx+10h]
0x18003c2fc  call    cs:__imp_GetLastError
0x18003c303  nop     dword ptr [rax+rax+00h]
0x18003c308  mov     edx, 1Eh
0x18003c30d  lea     r8, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids
0x18003c314  mov     r9d, eax
0x18003c317  mov     rcx, rbx
0x18003c31a  call    WPP_SF_d
0x18003c31f  jmp     loc_18003CB30
0x18003c324  xor     r8d, r8d; pDefault
0x18003c327  lea     rdx, [rsp+190h+hPrinter]; phPrinter
0x18003c32c  mov     rcx, rax; pPrinterName
0x18003c32f  call    cs:__imp_OpenPrinterW
0x18003c336  nop     dword ptr [rax+rax+00h]
0x18003c33b  test    eax, eax
0x18003c33d  jnz     short loc_18003C3A2
0x18003c33f  mov     rbx, cs:WPP_GLOBAL_Control
0x18003c346  lea     rax, WPP_GLOBAL_Control
0x18003c34d  cmp     rbx, rax
0x18003c350  jz      loc_18003C280
0x18003c356  test    byte ptr [rbx+1Ch], 2
0x18003c35a  jz      loc_18003C280
0x18003c360  cmp     byte ptr [rbx+19h], 2
0x18003c364  jb      loc_18003C280
0x18003c36a  mov     rbx, [rbx+10h]
0x18003c36e  call    cs:__imp_GetLastError
0x18003c375  nop     dword ptr [rax+rax+00h]
0x18003c37a  mov     r13, [rsp+190h+pwszDevice]
0x18003c37f  lea     r8, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids
0x18003c386  mov     r9, r13
0x18003c389  mov     dword ptr [rsp+190h+pcbNeeded], eax
0x18003c38d  mov     edx, 10h
0x18003c392  mov     rcx, rbx
0x18003c395  call    WPP_SF_Sd
0x18003c39a  mov     rdi, rsi
0x18003c39d  jmp     loc_18003C288
0x18003c3a2  mov     rcx, [rsp+190h+hPrinter]; hPrinter
0x18003c3a7  lea     rax, [rsp+190h+cbBuf]
0x18003c3ac  xor     r9d, r9d; cbBuf
0x18003c3af  mov     [rsp+190h+pcbNeeded], rax; pcbNeeded
0x18003c3b4  xor     r8d, r8d; pPrinter
0x18003c3b7  lea     edx, [r9+2]; Level
0x18003c3bb  call    cs:__imp_GetPrinterW
0x18003c3c2  nop     dword ptr [rax+rax+00h]
0x18003c3c7  test    eax, eax
0x18003c3c9  jnz     short loc_18003C427
0x18003c3cb  mov     ecx, [rsp+190h+cbBuf]; dwBytes
0x18003c3cf  call    pMemAlloc
0x18003c3d4  mov     rsi, rax
0x18003c3d7  test    rax, rax
0x18003c3da  jnz     short loc_18003C427
0x18003c3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c3e3  lea     rax, WPP_GLOBAL_Control
0x18003c3ea  cmp     rcx, rax
0x18003c3ed  jz      short loc_18003C40E
0x18003c3ef  test    byte ptr [rcx+1Ch], 2
0x18003c3f3  jz      short loc_18003C40E
0x18003c3f5  cmp     byte ptr [rcx+19h], 2
0x18003c3f9  jb      short loc_18003C40E
0x18003c3fb  lea     edx, [rsi+11h]
0x18003c3fe  mov     rcx, [rcx+10h]
0x18003c402  lea     r8, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids
0x18003c409  call    WPP_SF_
0x18003c40e  mov     ecx, 8; dwErrCode
0x18003c413  call    cs:__imp_SetLastError
0x18003c41a  nop     dword ptr [rax+rax+00h]
0x18003c41f  mov     rdi, r14
0x18003c422  jmp     loc_18003C283
0x18003c427  mov     r9d, [rsp+190h+cbBuf]; cbBuf
0x18003c42c  lea     rax, [rsp+190h+cbBuf]
0x18003c431  mov     rcx, [rsp+190h+hPrinter]; hPrinter
0x18003c436  mov     r8, rsi; pPrinter
0x18003c439  mov     edx, 2; Level
0x18003c43e  mov     [rsp+190h+pcbNeeded], rax; pcbNeeded
0x18003c443  call    cs:__imp_GetPrinterW
0x18003c44a  nop     dword ptr [rax+rax+00h]
0x18003c44f  test    eax, eax
0x18003c451  jnz     short loc_18003C49B
0x18003c453  mov     rbx, cs:WPP_GLOBAL_Control
0x18003c45a  lea     rax, WPP_GLOBAL_Control
0x18003c461  cmp     rbx, rax
0x18003c464  jz      short loc_18003C41F
0x18003c466  test    byte ptr [rbx+1Ch], 2
0x18003c46a  jz      short loc_18003C41F
0x18003c46c  cmp     byte ptr [rbx+19h], 2
0x18003c470  jb      short loc_18003C41F
0x18003c472  mov     rbx, [rbx+10h]
0x18003c476  call    cs:__imp_GetLastError
0x18003c47d  nop     dword ptr [rax+rax+00h]
0x18003c482  mov     edx, 12h
0x18003c487  mov     r9d, eax
0x18003c48a  lea     r8, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids
0x18003c491  mov     rcx, rbx
0x18003c494  call    WPP_SF_d
0x18003c499  jmp     short loc_18003C41F
0x18003c49b  mov     rcx, [rsi]; Str
0x18003c49e  xor     eax, eax
0x18003c4a0  test    rcx, rcx
0x18003c4a3  jz      loc_18003C56D
0x18003c4a9  lea     rdx, SubStr; "\\\\"
0x18003c4b0  call    cs:__imp_wcsstr
0x18003c4b7  nop     dword ptr [rax+rax+00h]
0x18003c4bc  mov     rcx, [rsi]
0x18003c4bf  cmp     rcx, rax
0x18003c4c2  jnz     short loc_18003C4CB
0x18003c4c4  add     rcx, 4
0x18003c4c8  mov     [rsi], rcx
0x18003c4cb  mov     eax, 7FFFFFFEh
0x18003c4d0  lea     r8, [r13+10h]
0x18003c4d4  mov     edx, 10h
0x18003c4d9  test    rax, rax
0x18003c4dc  jz      short loc_18003C4FD
0x18003c4de  movzx   r9d, word ptr [rcx]
0x18003c4e2  test    r9w, r9w
0x18003c4e6  jz      short loc_18003C4FD
0x18003c4e8  mov     [r8], r9w
0x18003c4ec  add     rcx, 2
0x18003c4f0  add     r8, 2
0x18003c4f4  dec     rax
0x18003c4f7  sub     rdx, 1
0x18003c4fb  jnz     short loc_18003C4D9
0x18003c4fd  mov     rax, rdx
0x18003c500  lea     rcx, [r8-2]
0x18003c504  neg     rax
0x18003c507  sbb     edi, edi
0x18003c509  xor     eax, eax
0x18003c50b  not     edi
0x18003c50d  and     edi, 8007007Ah
0x18003c513  test    rdx, rdx
0x18003c516  cmovnz  rcx, r8
0x18003c51a  mov     [rcx], ax
0x18003c51d  jnz     short loc_18003C574
0x18003c51f  mov     rcx, cs:WPP_GLOBAL_Control
0x18003c526  lea     rax, WPP_GLOBAL_Control
0x18003c52d  cmp     rcx, rax
0x18003c530  jz      short loc_18003C556
0x18003c532  test    byte ptr [rcx+1Ch], 2
0x18003c536  jz      short loc_18003C556
0x18003c538  cmp     byte ptr [rcx+19h], 2
0x18003c53c  jb      short loc_18003C556
0x18003c53e  mov     rcx, [rcx+10h]
0x18003c542  lea     r8, WPP_53ac507df2233db26b2ec95954f4ae53_Traceguids
0x18003c549  mov     edx, 13h
0x18003c54e  mov     r9d, edi
0x18003c551  call    WPP_SF_d
0x18003c556  mov     eax, edi
0x18003c558  movzx   ecx, di
0x18003c55b  and     eax, 1FFF0000h
0x18003c560  cmp     eax, 70000h
0x18003c565  cmovnz  ecx, edi
0x18003c568  jmp     loc_18003C413
0x18003c56d  mov     [r13+10h], ax
0x18003c572  jmp     short loc_18003C579
0x18003c574  mov     rdi, [rsp+190h+var_130]
0x18003c579  mov     rdx, [rsp+190h+hPrinter]; hPrinter
0x18003c57e  xor     r9d, r9d; pDevModeOutput
0x18003c581  mov     [rsp+190h+fMode], eax; fMode
0x18003c585  xor     r8d, r8d; pDeviceName
0x18003c588  xor     ecx, ecx; hWnd
0x18003c58a  mov     [rsp+190h+pcbNeeded], rax; pDevModeInput
0x18003c58f  call    cs:__imp_DocumentPropertiesW
0x18003c596  nop     dword ptr [rax+rax+00h]
0x18003c59b  test    eax, eax
0x18003c59d  jg      short loc_18003C5E4
0x18003c59f  mov     rbx, cs:WPP_GLOBAL_Control
0x18003c5a6  lea     rax, WPP_GLOBAL_Control
0x18003c5ad  cmp     rbx, rax
0x18003c5b0  jz      loc_18003C41F
0x18003c5b6  test    byte ptr [rbx+1Ch], 2
0x18003c5ba  jz      loc_18003C41F
0x18003c5c0  cmp     byte ptr [rbx+19h], 2
0x18003c5c4  jb      loc_18003C41F
0x18003c5ca  mov     rbx, [rbx+10h]
0x18003c5ce  call    cs:__imp_GetLastError
0x18003c5d5  nop     dword ptr [rax+rax+00h]
  ... truncated ...
```
