# GetOutboundCommandText

- ea: `0x14002a8b8`
- end: `0x14002bf99`
- name: `GetOutboundCommandText`
- size: `5857`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002cd50`

## callees

- `0x140001bac`
- `0x140004be4`
- `0x140004c78`
- `0x140004ca8`
- `0x140004cec`
- `0x140004e48`
- `0x140004fe4`
- `0x140026fc4`
- `0x1400299d4`
- `0x140029d30`
- `0x14002a8b8`
- `0x14002d68c`
- `0x14002d78c`
- `0x14002da4c`
- `0x140052e68`
- `0x140052f80`
- `0x1400537ec`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x14002a97e`
- `KERNEL32!GetLastError` at `0x14002a9eb`
- `KERNEL32!GetLastError` at `0x14002aa55`
- `KERNEL32!GetLastError` at `0x14002aab4`
- `KERNEL32!GetLastError` at `0x14002ac25`
- `KERNEL32!GetLastError` at `0x14002ad07`
- `KERNEL32!GetLastError` at `0x14002b199`
- `KERNEL32!GetLastError` at `0x14002b271`
- `KERNEL32!GetLastError` at `0x14002a97e`
- `KERNEL32!GetLastError` at `0x14002a9eb`
- `KERNEL32!GetLastError` at `0x14002aa55`
- `KERNEL32!GetLastError` at `0x14002aab4`
- `KERNEL32!GetLastError` at `0x14002ac25`
- `KERNEL32!GetLastError` at `0x14002ad07`
- `KERNEL32!GetLastError` at `0x14002b199`
- `KERNEL32!GetLastError` at `0x14002b271`
- `KERNEL32!FileTimeToSystemTime` at `0x14002a94f`
- `KERNEL32!FileTimeToSystemTime` at `0x14002a9b9`
- `KERNEL32!FileTimeToSystemTime` at `0x14002a94f`
- `KERNEL32!FileTimeToSystemTime` at `0x14002a9b9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall GetOutboundCommandText(__int64 a1, char *a2)
{
  int RealFaxTimeAsSystemTime; // esi
  int v5; // r14d
  BOOL v6; // r12d
  DWORD LastError; // eax
  BOOL v8; // r15d
  DWORD v9; // eax
  __int64 v10; // rcx
  DWORD v11; // eax
  DWORD v12; // eax
  int v13; // eax
  CMapDeviceId *v14; // rcx
  __int64 v15; // rdx
  DWORD v16; // eax
  void **v17; // rdx
  _QWORD *v18; // rax
  DWORD v19; // eax
  void *v20; // rcx
  void **v21; // rdx
  _QWORD *v22; // rax
  unsigned __int16 *String; // rax
  _QWORD *v24; // rax
  unsigned __int16 *v25; // rax
  _QWORD *v26; // rax
  unsigned __int16 *v27; // rax
  _QWORD *v28; // rax
  unsigned __int16 *v29; // rax
  _QWORD *v30; // rax
  __int64 v31; // rcx
  char *v32; // rdx
  unsigned int v33; // ecx
  unsigned __int16 *v34; // rax
  void **v35; // rdx
  _QWORD *v36; // rax
  unsigned __int16 *v37; // rdx
  int v38; // eax
  CMapDeviceId *v39; // rcx
  __int64 v40; // rdx
  DWORD v41; // eax
  void **v42; // rdx
  _QWORD *v43; // rax
  DWORD v44; // eax
  void **v45; // rdx
  _QWORD *v46; // rax
  _QWORD *v47; // rax
  _WORD *v48; // rdx
  __int64 v49; // rax
  _QWORD *v50; // rax
  _QWORD *v51; // rax
  _QWORD *v52; // rax
  _QWORD *v53; // rax
  _QWORD *v54; // rax
  __int64 v56; // rdx
  _QWORD *v57; // rax
  _QWORD *v58; // rax
  _QWORD *v59; // rax
  _QWORD *v60; // rax
  _QWORD *v61; // rax
  _QWORD *v62; // rax
  _QWORD *v63; // rax
  _QWORD *v64; // rax
  _QWORD *v65; // rax
  _QWORD *v66; // rax
  _QWORD *v67; // rax
  _QWORD *v68; // rax
  _QWORD *v69; // rax
  _QWORD *v70; // rax
  _QWORD *v71; // rax
  _QWORD *v72; // rax
  _QWORD *v73; // rax
  _QWORD *v74; // rax
  _QWORD *v75; // rax
  _QWORD *v76; // rax
  _QWORD *v77; // rax
  _QWORD *v78; // rax
  _QWORD *v79; // rax
  _QWORD *v80; // rax
  _QWORD *v81; // rax
  _QWORD *v82; // rax
  _QWORD *v83; // rax
  _QWORD *v84; // rax
  _QWORD *v85; // rax
  _QWORD *v86; // rax
  _QWORD *v87; // rax
  __int64 v88; // [rsp+20h] [rbp-E0h]
  void *v89[3]; // [rsp+30h] [rbp-D0h] BYREF
  unsigned __int64 v90; // [rsp+48h] [rbp-B8h]
  void *v91[2]; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v92; // [rsp+60h] [rbp-A0h]
  unsigned __int64 v93; // [rsp+68h] [rbp-98h]
  void *Block[3]; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v95; // [rsp+88h] [rbp-78h]
  struct _SYSTEMTIME SystemTime; // [rsp+90h] [rbp-70h] BYREF
  SYSTEMTIME UniversalTime; // [rsp+A0h] [rbp-60h] BYREF
  SYSTEMTIME v98; // [rsp+B0h] [rbp-50h] BYREF
  SYSTEMTIME v99; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 Src[104]; // [rsp+D0h] [rbp-30h] BYREF

  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
  }
  RealFaxTimeAsSystemTime = 0;
  v5 = 0;
  v98 = 0;
  v99 = 0;
  UniversalTime = 0;
  SystemTime = 0;
  v6 = FileTimeToSystemTime((const FILETIME *)(*(_QWORD *)(a1 + 584) + 424LL), &SystemTime);
  if ( !v6
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    LastError = GetLastError();
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 53, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, LastError);
  }
  v8 = FileTimeToSystemTime((const FILETIME *)(*(_QWORD *)(a1 + 584) + 424LL), &UniversalTime);
  if ( !v8
    && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v9 = GetLastError();
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      (unsigned int)(v8 + 54),
      WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
      v9);
  }
  v10 = *(_QWORD *)(a1 + 40);
  if ( v10 )
  {
    RealFaxTimeAsSystemTime = GetRealFaxTimeAsSystemTime(v10, 1, &v98);
    if ( !RealFaxTimeAsSystemTime
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v11 = GetLastError();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(RealFaxTimeAsSystemTime + 55),
        WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        v11);
    }
    v5 = GetRealFaxTimeAsSystemTime(*(_QWORD *)(a1 + 40), 2, &v99);
    if ( !v5
      && WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v12 = GetLastError();
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (unsigned int)(v5 + 56),
        WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
        v12);
    }
  }
  v13 = StringCchPrintfW(Src, 0x64u, L"0x%016I64x", *(_QWORD *)(a1 + 16));
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = 57;
    goto LABEL_174;
  }
  std::wstring::append(a2, (char *)L"\"");
  std::wstring::append(a2, (char *)Src);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v13 = StringCchPrintfW(Src, 0x64u, L"0x%016I64x", *(_QWORD *)(*(_QWORD *)(a1 + 584) + 16LL));
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = 58;
    goto LABEL_174;
  }
  std::wstring::append(a2, (char *)Src);
  std::wstring::append(a2, (char *)L"\"\t");
  if ( v6 )
  {
    v93 = 7;
    v92 = 0;
    LOWORD(v91[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&SystemTime, (char *)v91) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v16 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 59, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v16);
      }
      goto LABEL_55;
    }
    v17 = v91;
    if ( v93 >= 8 )
      v17 = (void **)v91[0];
    v18 = FilteredLogString(Block, v17);
    std::wstring::append(a2, v18, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v95 >= 8 )
      operator delete(Block[0]);
    if ( v93 >= 8 )
      operator delete(v91[0]);
  }
  std::wstring::append(a2, (char *)L"\t");
  if ( v8 )
  {
    v93 = 7;
    v92 = 0;
    LOWORD(v91[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&UniversalTime, (char *)v91) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 60, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v19);
      }
LABEL_55:
      if ( v93 >= 8 )
      {
        v20 = v91[0];
LABEL_152:
        operator delete(v20);
        return 0;
      }
      return 0;
    }
    v21 = v91;
    if ( v93 >= 8 )
      v21 = (void **)v91[0];
    v22 = FilteredLogString(Block, v21);
    std::wstring::append(a2, v22, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v95 >= 8 )
      operator delete(Block[0]);
    if ( v93 >= 8 )
      operator delete(v91[0]);
  }
  std::wstring::append(a2, (char *)L"\t\"");
  if ( *(_DWORD *)(a1 + 1844) == 512 )
  {
    String = GetString(0x1F69u);
    v24 = FilteredLogString(v91, String);
    std::wstring::append(a2, v24, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v93 >= 8 )
      operator delete(v91[0]);
    std::wstring::append(a2, (char *)L"\"\t\"");
    std::wstring::append(a2, (char *)L"\"\t\"");
    std::wstring::append(a2, (char *)L"\"\t");
    std::wstring::append(a2, (char *)L"\t");
    std::wstring::append(a2, (char *)L"\t\"");
    std::wstring::append(a2, (char *)L"\"\t\"");
    std::wstring::append(a2, (char *)L"\"\t\"");
    std::wstring::append(a2, (char *)L"\"\t\"");
    std::wstring::append(a2, (char *)L"\"\t");
    std::wstring::append(a2, (char *)L"\t");
    goto LABEL_155;
  }
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 1128LL) == 8 )
  {
    v29 = GetString(0x1F69u);
    v30 = FilteredLogString(v91, v29);
    std::wstring::append(a2, v30, 0, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 1128LL) == 9 )
  {
    v27 = GetString(0x20000008u);
    v28 = FilteredLogString(v91, v27);
    std::wstring::append(a2, v28, 0, 0xFFFFFFFFFFFFFFFFuLL);
  }
  else
  {
    if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 1128LL) != 11
      && (unsigned int)(*(_DWORD *)(*(_QWORD *)(a1 + 40) + 1128LL) - 12) >= 2 )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        LODWORD(v88) = *(_DWORD *)(a1 + 32);
        WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 61, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids);
      }
      goto LABEL_80;
    }
    v25 = GetString(0x1F68u);
    v26 = FilteredLogString(v91, v25);
    std::wstring::append(a2, v26, 0, 0xFFFFFFFFFFFFFFFFuLL);
  }
  if ( v93 >= 8 )
    operator delete(v91[0]);
LABEL_80:
  std::wstring::append(a2, (char *)L"\"\t\"");
  v95 = 7;
  Block[2] = 0;
  LOWORD(Block[0]) = 0;
  v31 = *(_QWORD *)(a1 + 40);
  v32 = (char *)(v31 + 1216);
  if ( v31 != -1216 && *(_WORD *)v32 )
    goto LABEL_90;
  v33 = *(_DWORD *)(v31 + 1132);
  if ( !v33 )
  {
    v32 = (char *)L" ";
LABEL_90:
    std::wstring::assign((char *)Block, v32);
    goto LABEL_91;
  }
  v34 = MapFSPIJobExtendedStatusToString(v33);
  if ( v34 )
  {
    v32 = (char *)v34;
    goto LABEL_90;
  }
  std::wstring::assign((char *)Block, (char *)L" ");
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_DS(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      62,
      (unsigned int)WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids,
      *(_DWORD *)(*(_QWORD *)(a1 + 40) + 1132LL),
      *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 40LL) + 584LL);
  }
LABEL_91:
  v35 = Block;
  if ( v95 >= 8 )
    v35 = (void **)Block[0];
  v36 = FilteredLogString(v91, v35);
  std::wstring::append(a2, v36, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v93 >= 8 )
    operator delete(v91[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  if ( *(_DWORD *)(*(_QWORD *)(a1 + 40) + 1132LL) )
  {
    v38 = StringCchPrintfW(Src, 0x64u, L"0x%08x");
    if ( v38 < 0 )
    {
      v39 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_150;
      }
      v40 = 63;
LABEL_149:
      WPP_SF_d(*((_QWORD *)v39 + 2), v40, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, (unsigned int)v38);
      goto LABEL_150;
    }
    v37 = Src;
  }
  else
  {
    v37 = L" ";
  }
  std::wstring::assign((char *)Block, (char *)v37);
  std::wstring::append(a2, Block, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::append(a2, (char *)L"\"\t");
  if ( RealFaxTimeAsSystemTime )
  {
    v93 = 7;
    v92 = 0;
    LOWORD(v91[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&v98, (char *)v91) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v41 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 64, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v41);
      }
LABEL_122:
      if ( v93 >= 8 )
        operator delete(v91[0]);
      v93 = 7;
      v92 = 0;
      LOWORD(v91[0]) = 0;
LABEL_150:
      if ( v95 >= 8 )
      {
        v20 = Block[0];
        goto LABEL_152;
      }
      return 0;
    }
    v42 = v91;
    if ( v93 >= 8 )
      v42 = (void **)v91[0];
    v43 = FilteredLogString(v89, v42);
    std::wstring::append(a2, v43, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v90 >= 8 )
      operator delete(v89[0]);
    if ( v93 >= 8 )
      operator delete(v91[0]);
  }
  std::wstring::append(a2, (char *)L"\t");
  if ( v5 )
  {
    v93 = 7;
    v92 = 0;
    LOWORD(v91[0]) = 0;
    if ( !(unsigned int)GetFaxTimeAsString(&v99, (char *)v91) )
    {
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v44 = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 65, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, v44);
      }
      goto LABEL_122;
    }
    v45 = v91;
    if ( v93 >= 8 )
      v45 = (void **)v91[0];
    v46 = FilteredLogString(v89, v45);
    std::wstring::append(a2, v46, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v90 >= 8 )
      operator delete(v89[0]);
    if ( v93 >= 8 )
      operator delete(v91[0]);
  }
  std::wstring::append(a2, (char *)L"\t\"");
  v47 = FilteredLogString(v89, *(void **)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 56LL));
  std::wstring::append(a2, v47, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v48 = (_WORD *)(*(_QWORD *)(a1 + 40) + 76LL);
  v49 = -1;
  do
    ++v49;
  while ( v48[v49] );
  if ( v49 )
    v50 = FilteredLogString(v89, v48);
  else
    v50 = FilteredLogString(v89, *(void **)(a1 + 464));
  std::wstring::append(a2, v50, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v51 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 40) + 1144LL));
  std::wstring::append(a2, v51, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v52 = FilteredLogString(v89, *(void **)(*(_QWORD *)(*(_QWORD *)(a1 + 40) + 16LL) + 96LL));
  std::wstring::append(a2, v52, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t");
  v38 = StringCchPrintfW(Src, 0x64u, L"%ld", *(unsigned int *)(*(_QWORD *)(a1 + 40) + 1168LL));
  if ( v38 < 0 )
  {
    v39 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      goto LABEL_150;
    }
    v40 = 66;
    goto LABEL_149;
  }
  std::wstring::append(a2, (char *)Src);
  std::wstring::append(a2, (char *)L"\t");
  if ( v95 >= 8 )
    operator delete(Block[0]);
LABEL_155:
  v13 = StringCchPrintfW(Src, 0x64u, L"%ld", *(unsigned int *)(*(_QWORD *)(a1 + 584) + 64LL), v88);
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = 67;
    goto LABEL_174;
  }
  std::wstring::append(a2, (char *)Src);
  std::wstring::append(a2, (char *)L"\t\"");
  v53 = FilteredLogString(v89, *(void **)(a1 + 56));
  std::wstring::append(a2, v53, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v54 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 160LL));
  std::wstring::append(a2, v54, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t");
  v13 = StringCchPrintfW(Src, 0x64u, L"%ld", *(unsigned int *)(*(_QWORD *)(a1 + 584) + 388LL));
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = 68;
    goto LABEL_174;
  }
  std::wstring::append(a2, (char *)Src);
  std::wstring::append(a2, (char *)L"\t");
  v13 = StringCchPrintfW(Src, 0x64u, L"%d", *(unsigned int *)(a1 + 592));
  if ( v13 < 0 )
  {
    v14 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
    {
      return 0;
    }
    v15 = 69;
LABEL_174:
    WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, (unsigned int)v13);
    return 0;
  }
  std::wstring::append(a2, (char *)Src);
  std::wstring::append(a2, (char *)L"\t\"");
  v56 = *(_QWORD *)(a1 + 584);
  if ( *(_DWORD *)(v56 + 192) == 1 )
  {
    v57 = FilteredLogString(v89, *(void **)(v56 + 184));
    std::wstring::append(a2, v57, 0, 0xFFFFFFFFFFFFFFFFuLL);
    if ( v90 >= 8 )
      operator delete(v89[0]);
  }
  else
  {
    std::wstring::append(a2, (char *)L" ");
  }
  std::wstring::append(a2, (char *)L"\"\t\"");
  v58 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 208LL));
  std::wstring::append(a2, v58, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v59 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 200LL));
  std::wstring::append(a2, v59, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v60 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 400LL));
  std::wstring::append(a2, v60, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v61 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 248LL));
  std::wstring::append(a2, v61, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v62 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 256LL));
  std::wstring::append(a2, v62, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v63 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 264LL));
  std::wstring::append(a2, v63, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v64 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 272LL));
  std::wstring::append(a2, v64, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v65 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 280LL));
  std::wstring::append(a2, v65, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v66 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 296LL));
  std::wstring::append(a2, v66, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v67 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 304LL));
  std::wstring::append(a2, v67, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v68 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 312LL));
  std::wstring::append(a2, v68, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v69 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 320LL));
  std::wstring::append(a2, v69, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v70 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 328LL));
  std::wstring::append(a2, v70, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v71 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 336LL));
  std::wstring::append(a2, v71, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v72 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 344LL));
  std::wstring::append(a2, v72, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v73 = FilteredLogString(v89, *(void **)(*(_QWORD *)(a1 + 584) + 352LL));
  std::wstring::append(a2, v73, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v74 = FilteredLogString(v89, *(void **)(a1 + 456));
  std::wstring::append(a2, v74, 0, 0xFFFFFFFFFFFFFFFFuLL);
  if ( v90 >= 8 )
    operator delete(v89[0]);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v75 = FilteredLogString(v89, *(void **)(a1 + 464));
  std::wstring::append(a2, v75, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v76 = FilteredLogString(v89, *(void **)(a1 + 472));
  std::wstring::append(a2, v76, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v77 = FilteredLogString(v89, *(void **)(a1 + 480));
  std::wstring::append(a2, v77, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v78 = FilteredLogString(v89, *(void **)(a1 + 488));
  std::wstring::append(a2, v78, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v79 = FilteredLogString(v89, *(void **)(a1 + 504));
  std::wstring::append(a2, v79, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v80 = FilteredLogString(v89, *(void **)(a1 + 512));
  std::wstring::append(a2, v80, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v81 = FilteredLogString(v89, *(void **)(a1 + 520));
  std::wstring::append(a2, v81, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v82 = FilteredLogString(v89, *(void **)(a1 + 528));
  std::wstring::append(a2, v82, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v83 = FilteredLogString(v89, *(void **)(a1 + 536));
  std::wstring::append(a2, v83, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v84 = FilteredLogString(v89, *(void **)(a1 + 544));
  std::wstring::append(a2, v84, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v85 = FilteredLogString(v89, *(void **)(a1 + 552));
  std::wstring::append(a2, v85, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v86 = FilteredLogString(v89, *(void **)(a1 + 560));
  std::wstring::append(a2, v86, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\t\"");
  v87 = FilteredLogString(v89, *(void **)(a1 + 360));
  std::wstring::append(a2, v87, 0, 0xFFFFFFFFFFFFFFFFuLL);
  std::wstring::_Tidy(v89, 1, 0);
  std::wstring::append(a2, (char *)L"\"\r\n");
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    if ( *((_QWORD *)a2 + 3) >= 8u )
      a2 = *(char **)a2;
    WPP_SF_S(*((_QWORD *)WPP_GLOBAL_Control + 2), 70, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids, a2);
  }
  return 1;
}

```

## disassembly

```asm
0x14002a8b8  mov     [rsp-8+arg_10], rbx
0x14002a8bd  push    rbp
0x14002a8be  push    rsi
0x14002a8bf  push    rdi
0x14002a8c0  push    r12
0x14002a8c2  push    r13
0x14002a8c4  push    r14
0x14002a8c6  push    r15
0x14002a8c8  lea     rbp, [rsp-0B0h]
0x14002a8d0  sub     rsp, 1B0h
0x14002a8d7  mov     rax, cs:__security_cookie
0x14002a8de  xor     rax, rsp
0x14002a8e1  mov     [rbp+0E0h+var_40], rax
0x14002a8e8  mov     rbx, rdx
0x14002a8eb  mov     rdi, rcx
0x14002a8ee  lea     r15, WPP_GLOBAL_Control
0x14002a8f5  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a8fc  cmp     rcx, r15
0x14002a8ff  jz      short loc_14002A922
0x14002a901  test    byte ptr [rcx+1Ch], 4
0x14002a905  jz      short loc_14002A922
0x14002a907  cmp     byte ptr [rcx+19h], 5
0x14002a90b  jb      short loc_14002A922
0x14002a90d  mov     edx, 34h ; '4'
0x14002a912  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002a919  mov     rcx, [rcx+10h]
0x14002a91d  call    WPP_SF_
0x14002a922  xor     esi, esi
0x14002a924  xor     r14d, r14d
0x14002a927  xorps   xmm0, xmm0
0x14002a92a  movups  xmmword ptr [rbp+0E0h+var_130.wYear], xmm0
0x14002a92e  xorps   xmm1, xmm1
0x14002a931  movups  xmmword ptr [rbp+0E0h+var_120.wYear], xmm1
0x14002a935  movups  xmmword ptr [rbp+0E0h+UniversalTime.wYear], xmm0
0x14002a939  movups  xmmword ptr [rbp+0E0h+SystemTime.wYear], xmm1
0x14002a93d  mov     rcx, [rdi+248h]
0x14002a944  add     rcx, 1A8h; lpFileTime
0x14002a94b  lea     rdx, [rbp+0E0h+SystemTime]; lpSystemTime
0x14002a94f  call    cs:__imp_FileTimeToSystemTime
0x14002a956  nop     dword ptr [rax+rax+00h]
0x14002a95b  mov     r12d, eax
0x14002a95e  lea     r13d, [rsi+2]
0x14002a962  test    eax, eax
0x14002a964  jnz     short loc_14002A9A7
0x14002a966  mov     rax, cs:WPP_GLOBAL_Control
0x14002a96d  cmp     rax, r15
0x14002a970  jz      short loc_14002A9A7
0x14002a972  test    byte ptr [rax+1Ch], 4
0x14002a976  jz      short loc_14002A9A7
0x14002a978  cmp     [rax+19h], r13b
0x14002a97c  jb      short loc_14002A9A7
0x14002a97e  call    cs:__imp_GetLastError
0x14002a985  nop     dword ptr [rax+rax+00h]
0x14002a98a  lea     edx, [rsi+35h]
0x14002a98d  mov     r9d, eax
0x14002a990  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002a997  mov     rcx, cs:WPP_GLOBAL_Control
0x14002a99e  mov     rcx, [rcx+10h]
0x14002a9a2  call    WPP_SF_d
0x14002a9a7  mov     rcx, [rdi+248h]
0x14002a9ae  add     rcx, 1A8h; lpFileTime
0x14002a9b5  lea     rdx, [rbp+0E0h+UniversalTime]; lpSystemTime
0x14002a9b9  call    cs:__imp_FileTimeToSystemTime
0x14002a9c0  nop     dword ptr [rax+rax+00h]
0x14002a9c5  mov     r15d, eax
0x14002a9c8  test    eax, eax
0x14002a9ca  jnz     short loc_14002AA15
0x14002a9cc  mov     rax, cs:WPP_GLOBAL_Control
0x14002a9d3  lea     rcx, WPP_GLOBAL_Control
0x14002a9da  cmp     rax, rcx
0x14002a9dd  jz      short loc_14002AA15
0x14002a9df  test    byte ptr [rax+1Ch], 4
0x14002a9e3  jz      short loc_14002AA15
0x14002a9e5  cmp     [rax+19h], r13b
0x14002a9e9  jb      short loc_14002AA15
0x14002a9eb  call    cs:__imp_GetLastError
0x14002a9f2  nop     dword ptr [rax+rax+00h]
0x14002a9f7  lea     edx, [r15+36h]
0x14002a9fb  mov     r9d, eax
0x14002a9fe  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002aa05  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa0c  mov     rcx, [rcx+10h]
0x14002aa10  call    WPP_SF_d
0x14002aa15  mov     rcx, [rdi+28h]
0x14002aa19  test    rcx, rcx
0x14002aa1c  jz      loc_14002AADE
0x14002aa22  lea     r8, [rbp+0E0h+var_130]
0x14002aa26  mov     edx, 1
0x14002aa2b  call    ?GetRealFaxTimeAsSystemTime@@YAHQEAU_JOB_ENTRY@@W4FAX_ENUM_TIME_TYPES@@PEAU_SYSTEMTIME@@@Z; GetRealFaxTimeAsSystemTime(_JOB_ENTRY * const,FAX_ENUM_TIME_TYPES,_SYSTEMTIME *)
0x14002aa30  mov     esi, eax
0x14002aa32  test    eax, eax
0x14002aa34  jnz     short loc_14002AA7E
0x14002aa36  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa3d  lea     rax, WPP_GLOBAL_Control
0x14002aa44  cmp     rcx, rax
0x14002aa47  jz      short loc_14002AA7E
0x14002aa49  test    byte ptr [rcx+1Ch], 4
0x14002aa4d  jz      short loc_14002AA7E
0x14002aa4f  cmp     [rcx+19h], r13b
0x14002aa53  jb      short loc_14002AA7E
0x14002aa55  call    cs:__imp_GetLastError
0x14002aa5c  nop     dword ptr [rax+rax+00h]
0x14002aa61  lea     edx, [rsi+37h]
0x14002aa64  mov     r9d, eax
0x14002aa67  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002aa6e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa75  mov     rcx, [rcx+10h]
0x14002aa79  call    WPP_SF_d
0x14002aa7e  lea     r8, [rbp+0E0h+var_120]
0x14002aa82  mov     edx, r13d
0x14002aa85  mov     rcx, [rdi+28h]
0x14002aa89  call    ?GetRealFaxTimeAsSystemTime@@YAHQEAU_JOB_ENTRY@@W4FAX_ENUM_TIME_TYPES@@PEAU_SYSTEMTIME@@@Z; GetRealFaxTimeAsSystemTime(_JOB_ENTRY * const,FAX_ENUM_TIME_TYPES,_SYSTEMTIME *)
0x14002aa8e  mov     r14d, eax
0x14002aa91  test    eax, eax
0x14002aa93  jnz     short loc_14002AADE
0x14002aa95  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aa9c  lea     rax, WPP_GLOBAL_Control
0x14002aaa3  cmp     rcx, rax
0x14002aaa6  jz      short loc_14002AADE
0x14002aaa8  test    byte ptr [rcx+1Ch], 4
0x14002aaac  jz      short loc_14002AADE
0x14002aaae  cmp     [rcx+19h], r13b
0x14002aab2  jb      short loc_14002AADE
0x14002aab4  call    cs:__imp_GetLastError
0x14002aabb  nop     dword ptr [rax+rax+00h]
0x14002aac0  lea     edx, [r14+38h]
0x14002aac4  mov     r9d, eax
0x14002aac7  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002aace  mov     rcx, cs:WPP_GLOBAL_Control
0x14002aad5  mov     rcx, [rcx+10h]
0x14002aad9  call    WPP_SF_d
0x14002aade  mov     r9, [rdi+10h]
0x14002aae2  lea     r8, a0x016i64x; "0x%016I64x"
0x14002aae9  mov     edx, 64h ; 'd'; unsigned __int64
0x14002aaee  lea     rcx, [rbp+0E0h+Src]; unsigned __int16 *
0x14002aaf2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002aaf7  test    eax, eax
0x14002aaf9  jns     short loc_14002AB30
0x14002aafb  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab02  lea     rdx, WPP_GLOBAL_Control
0x14002ab09  cmp     rcx, rdx
0x14002ab0c  jz      loc_14002B6CC
0x14002ab12  test    byte ptr [rcx+1Ch], 4
0x14002ab16  jz      loc_14002B6CC
0x14002ab1c  cmp     [rcx+19h], r13b
0x14002ab20  jb      loc_14002B6CC
0x14002ab26  mov     edx, 39h ; '9'
0x14002ab2b  jmp     loc_14002B6B9
0x14002ab30  lea     rdx, asc_1400930FC; "\""
0x14002ab37  mov     rcx, rbx; Src
0x14002ab3a  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002ab3f  lea     rdx, [rbp+0E0h+Src]; void *
0x14002ab43  mov     rcx, rbx; Src
0x14002ab46  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002ab4b  lea     rdx, asc_140093210; "\"\t\""
0x14002ab52  mov     rcx, rbx; Src
0x14002ab55  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002ab5a  mov     r9, [rdi+248h]
0x14002ab61  mov     r9, [r9+10h]
0x14002ab65  lea     r8, a0x016i64x; "0x%016I64x"
0x14002ab6c  mov     edx, 64h ; 'd'; unsigned __int64
0x14002ab71  lea     rcx, [rbp+0E0h+Src]; unsigned __int16 *
0x14002ab75  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x14002ab7a  test    eax, eax
0x14002ab7c  jns     short loc_14002ABB3
0x14002ab7e  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ab85  lea     rdx, WPP_GLOBAL_Control
0x14002ab8c  cmp     rcx, rdx
0x14002ab8f  jz      loc_14002B6CC
0x14002ab95  test    byte ptr [rcx+1Ch], 4
0x14002ab99  jz      loc_14002B6CC
0x14002ab9f  cmp     [rcx+19h], r13b
0x14002aba3  jb      loc_14002B6CC
0x14002aba9  mov     edx, 3Ah ; ':'
0x14002abae  jmp     loc_14002B6B9
0x14002abb3  lea     rdx, [rbp+0E0h+Src]; void *
0x14002abb7  mov     rcx, rbx; Src
0x14002abba  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002abbf  lea     rdx, asc_140093238; "\"\t"
0x14002abc6  mov     rcx, rbx; Src
0x14002abc9  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002abce  mov     r13d, 8
0x14002abd4  test    r12d, r12d
0x14002abd7  jz      loc_14002ACA7
0x14002abdd  mov     [rsp+1E0h+var_178], 7
0x14002abe6  xor     r12d, r12d
0x14002abe9  mov     [rsp+1E0h+var_180], r12
0x14002abee  mov     word ptr [rsp+1E0h+var_190], r12w
0x14002abf4  lea     rdx, [rsp+1E0h+var_190]; void *
0x14002abf9  lea     rcx, [rbp+0E0h+SystemTime]; lpUniversalTime
0x14002abfd  call    GetFaxTimeAsString
0x14002ac02  test    eax, eax
0x14002ac04  jnz     short loc_14002AC55
0x14002ac06  mov     rax, cs:WPP_GLOBAL_Control
0x14002ac0d  lea     rcx, WPP_GLOBAL_Control
0x14002ac14  cmp     rax, rcx
0x14002ac17  jz      short loc_14002AC50
0x14002ac19  test    byte ptr [rax+1Ch], 4
0x14002ac1d  jz      short loc_14002AC50
0x14002ac1f  cmp     byte ptr [rax+19h], 2
0x14002ac23  jb      short loc_14002AC50
0x14002ac25  call    cs:__imp_GetLastError
0x14002ac2c  nop     dword ptr [rax+rax+00h]
0x14002ac31  lea     edx, [r13+33h]
0x14002ac35  mov     r9d, eax
0x14002ac38  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002ac3f  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ac46  mov     rcx, [rcx+10h]
0x14002ac4a  call    WPP_SF_d
0x14002ac4f  nop
0x14002ac50  jmp     loc_14002AD33
0x14002ac55  lea     rdx, [rsp+1E0h+var_190]
0x14002ac5a  cmp     [rsp+1E0h+var_178], r13
0x14002ac5f  cmovnb  rdx, [rsp+1E0h+var_190]; Src
0x14002ac65  lea     rcx, [rsp+1E0h+Block]; void *
0x14002ac6a  call    FilteredLogString
0x14002ac6f  nop
0x14002ac70  or      r9, 0FFFFFFFFFFFFFFFFh
0x14002ac74  xor     r8d, r8d
0x14002ac77  mov     rdx, rax
0x14002ac7a  mov     rcx, rbx
0x14002ac7d  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14002ac82  nop
0x14002ac83  cmp     [rbp+0E0h+var_158], r13
0x14002ac87  jb      short loc_14002AC94
0x14002ac89  mov     rcx, [rsp+1E0h+Block]; Block
0x14002ac8e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002ac93  nop
0x14002ac94  cmp     [rsp+1E0h+var_178], r13
0x14002ac99  jb      short loc_14002ACAA
0x14002ac9b  mov     rcx, [rsp+1E0h+var_190]; Block
0x14002aca0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002aca5  jmp     short loc_14002ACAA
0x14002aca7  xor     r12d, r12d
0x14002acaa  lea     rdx, asc_140093100; "\t"
0x14002acb1  mov     rcx, rbx; Src
0x14002acb4  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002acb9  test    r15d, r15d
0x14002acbc  jz      loc_14002AD9D
0x14002acc2  mov     [rsp+1E0h+var_178], 7
0x14002accb  mov     [rsp+1E0h+var_180], r12
0x14002acd0  mov     word ptr [rsp+1E0h+var_190], r12w
0x14002acd6  lea     rdx, [rsp+1E0h+var_190]; void *
0x14002acdb  lea     rcx, [rbp+0E0h+UniversalTime]; lpUniversalTime
0x14002acdf  call    GetFaxTimeAsString
0x14002ace4  test    eax, eax
0x14002ace6  jnz     short loc_14002AD48
0x14002ace8  mov     rax, cs:WPP_GLOBAL_Control
0x14002acef  lea     rcx, WPP_GLOBAL_Control
0x14002acf6  cmp     rax, rcx
0x14002acf9  jz      short loc_14002AD33
0x14002acfb  test    byte ptr [rax+1Ch], 4
0x14002acff  jz      short loc_14002AD33
0x14002ad01  cmp     byte ptr [rax+19h], 2
0x14002ad05  jb      short loc_14002AD33
0x14002ad07  call    cs:__imp_GetLastError
0x14002ad0e  nop     dword ptr [rax+rax+00h]
0x14002ad13  mov     edx, 3Ch ; '<'
0x14002ad18  mov     r9d, eax
0x14002ad1b  lea     r8, WPP_4d44c9a766b533c18203e95f56f6fc39_Traceguids
0x14002ad22  mov     rcx, cs:WPP_GLOBAL_Control
0x14002ad29  mov     rcx, [rcx+10h]
0x14002ad2d  call    WPP_SF_d
0x14002ad32  nop
0x14002ad33  cmp     [rsp+1E0h+var_178], r13
0x14002ad38  jb      loc_14002B6CC
0x14002ad3e  mov     rcx, [rsp+1E0h+var_190]
0x14002ad43  jmp     loc_14002B4DD
0x14002ad48  lea     rdx, [rsp+1E0h+var_190]
0x14002ad4d  cmp     [rsp+1E0h+var_178], r13
0x14002ad52  cmovnb  rdx, [rsp+1E0h+var_190]; Src
0x14002ad58  lea     rcx, [rsp+1E0h+Block]; void *
0x14002ad5d  call    FilteredLogString
0x14002ad62  nop
0x14002ad63  or      r15, 0FFFFFFFFFFFFFFFFh
0x14002ad67  mov     r9, r15
0x14002ad6a  xor     r8d, r8d
0x14002ad6d  mov     rdx, rax
0x14002ad70  mov     rcx, rbx
0x14002ad73  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::append(std::wstring const &,unsigned __int64,unsigned __int64)
0x14002ad78  nop
0x14002ad79  cmp     [rbp+0E0h+var_158], r13
0x14002ad7d  jb      short loc_14002AD8A
0x14002ad7f  mov     rcx, [rsp+1E0h+Block]; Block
0x14002ad84  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002ad89  nop
0x14002ad8a  cmp     [rsp+1E0h+var_178], r13
0x14002ad8f  jb      short loc_14002ADA1
0x14002ad91  mov     rcx, [rsp+1E0h+var_190]; Block
0x14002ad96  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002ad9b  jmp     short loc_14002ADA1
0x14002ad9d  or      r15, 0FFFFFFFFFFFFFFFFh
0x14002ada1  lea     rdx, asc_140093240; "\t\""
0x14002ada8  mov     rcx, rbx; Src
0x14002adab  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::append(ushort const *)
0x14002adb0  mov     r9d, [rdi+734h]
0x14002adb7  cmp     r9d, 200h
0x14002adbe  jnz     loc_14002AE93
0x14002adc4  mov     ecx, 1F69h; unsigned int
0x14002adc9  call    ?GetString@@YAPEAGK@Z; GetString(ulong)
  ... truncated ...
```
