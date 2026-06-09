# PrepareReceiptBody

- ea: `0x140067ad0`
- end: `0x140068ab9`
- name: `PrepareReceiptBody`
- size: `4073`
- prototype: `__int64 __fastcall(int, int, __int64, va_list, int, LPWSTR lpBuffer, void *)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140068fdc`

## callees

- `0x140001bac`
- `0x1400027b0`
- `0x140002878`
- `0x140002c73`
- `0x140004c78`
- `0x140004ca8`
- `0x140016244`
- `0x14002d78c`
- `0x14002da4c`
- `0x140052f80`
- `0x140066454`
- `0x140067ad0`
- `0x140068ac0`
- `0x1400695a0`
- `0x140086ec0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x140067bc6`
- `KERNEL32!GetLastError` at `0x140067d55`
- `KERNEL32!GetLastError` at `0x140067e97`
- `KERNEL32!GetLastError` at `0x140067edf`
- `KERNEL32!GetLastError` at `0x140067f71`
- `KERNEL32!GetLastError` at `0x14006807b`
- `KERNEL32!GetLastError` at `0x140068148`
- `KERNEL32!GetLastError` at `0x1400683b3`
- `KERNEL32!GetLastError` at `0x1400684ee`
- `KERNEL32!GetLastError` at `0x140068531`
- `KERNEL32!GetLastError` at `0x14006872c`
- `KERNEL32!GetLastError` at `0x14006884c`
- `KERNEL32!GetLastError` at `0x1400688cf`
- `KERNEL32!GetLastError` at `0x140067bc6`
- `KERNEL32!GetLastError` at `0x140067d55`
- `KERNEL32!GetLastError` at `0x140067e97`
- `KERNEL32!GetLastError` at `0x140067edf`
- `KERNEL32!GetLastError` at `0x140067f71`
- `KERNEL32!GetLastError` at `0x14006807b`
- `KERNEL32!GetLastError` at `0x140068148`
- `KERNEL32!GetLastError` at `0x1400683b3`
- `KERNEL32!GetLastError` at `0x1400684ee`
- `KERNEL32!GetLastError` at `0x140068531`
- `KERNEL32!GetLastError` at `0x14006872c`
- `KERNEL32!GetLastError` at `0x14006884c`
- `KERNEL32!GetLastError` at `0x1400688cf`
- `KERNEL32!SetLastError` at `0x140068969`
- `KERNEL32!SetLastError` at `0x140068969`
- `KERNEL32!LocalFree` at `0x14006813c`
- `KERNEL32!LocalFree` at `0x14006831f`
- `KERNEL32!LocalFree` at `0x140068335`
- `KERNEL32!LocalFree` at `0x1400688c3`
- `KERNEL32!LocalFree` at `0x140068a2c`
- `KERNEL32!LocalFree` at `0x140068a3b`
- `KERNEL32!LocalFree` at `0x14006813c`
- `KERNEL32!LocalFree` at `0x14006831f`
- `KERNEL32!LocalFree` at `0x140068335`
- `KERNEL32!LocalFree` at `0x1400688c3`
- `KERNEL32!LocalFree` at `0x140068a2c`
- `KERNEL32!LocalFree` at `0x140068a3b`
- `KERNEL32!LocalAlloc` at `0x140068832`
- `KERNEL32!LocalAlloc` at `0x14006889c`
- `KERNEL32!LocalAlloc` at `0x140068832`
- `KERNEL32!LocalAlloc` at `0x14006889c`
- `KERNEL32!GetComputerNameW` at `0x140067bb6`
- `KERNEL32!GetComputerNameW` at `0x140067bb6`
- `KERNEL32!FormatMessageW` at `0x140067e87`
- `KERNEL32!FormatMessageW` at `0x14006806b`
- `KERNEL32!FormatMessageW` at `0x14006811f`
- `KERNEL32!FormatMessageW` at `0x140067e87`
- `KERNEL32!FormatMessageW` at `0x14006806b`
- `KERNEL32!FormatMessageW` at `0x14006811f`

## pseudocode

```c
__int64 __fastcall PrepareReceiptBody(int a1, int a2, __int64 a3, va_list a4, int a5, LPWSTR lpBuffer, void *a7)
{
  DWORD LastError; // eax
  DWORD v12; // ebx
  DWORD v13; // r8d
  _QWORD *v14; // rax
  _QWORD *v15; // rax
  _QWORD *v16; // rax
  DWORD v17; // eax
  CMapDeviceId *v18; // rcx
  __int64 v19; // rdx
  _QWORD *v20; // rax
  _QWORD *v21; // rax
  _QWORD *v22; // rax
  unsigned __int16 **v23; // rax
  DWORD v24; // eax
  CMapDeviceId *v25; // rcx
  __int64 v26; // rdx
  _QWORD *v27; // rax
  DWORD v28; // eax
  char *String; // rax
  _QWORD *i; // r15
  __int64 v31; // rcx
  _QWORD *j; // r15
  __int64 v33; // rcx
  unsigned int v34; // ecx
  char *v35; // rax
  char *v36; // rbx
  int v38; // ebx
  SIZE_T v39; // r15
  HLOCAL v40; // rax
  unsigned __int16 **v41; // r12
  SIZE_T v42; // rbx
  HLOCAL v43; // rax
  unsigned __int16 **v44; // r13
  DWORD v45; // eax
  const unsigned __int16 *v46; // r8
  int v47; // eax
  CMapDeviceId *v48; // rcx
  __int64 v49; // rdx
  void **v50; // r8
  WCHAR v51[4]; // [rsp+40h] [rbp-188h] BYREF
  WCHAR v52[4]; // [rsp+48h] [rbp-180h] BYREF
  DWORD nSize; // [rsp+50h] [rbp-178h] BYREF
  HLOCAL hMem; // [rsp+58h] [rbp-170h]
  HLOCAL v55; // [rsp+60h] [rbp-168h]
  exception *v56; // [rsp+68h] [rbp-160h] BYREF
  _BYTE v57[24]; // [rsp+70h] [rbp-158h] BYREF
  void *Block[2]; // [rsp+88h] [rbp-140h] BYREF
  __int64 v59; // [rsp+98h] [rbp-130h]
  unsigned __int64 v60; // [rsp+A0h] [rbp-128h]
  unsigned __int16 *Src[2]; // [rsp+A8h] [rbp-120h] BYREF
  __int64 v62; // [rsp+B8h] [rbp-110h]
  unsigned __int64 v63; // [rsp+C0h] [rbp-108h]
  va_list Arguments; // [rsp+D0h] [rbp-F8h] BYREF
  _QWORD *v65; // [rsp+D8h] [rbp-F0h]
  WCHAR *v66; // [rsp+E0h] [rbp-E8h]
  _QWORD *v67; // [rsp+E8h] [rbp-E0h]
  _QWORD *v68; // [rsp+F0h] [rbp-D8h]
  __int64 v69; // [rsp+F8h] [rbp-D0h]
  __int64 v70; // [rsp+100h] [rbp-C8h]
  unsigned __int16 **v71; // [rsp+108h] [rbp-C0h]
  _QWORD v72[3]; // [rsp+110h] [rbp-B8h] BYREF
  unsigned __int64 v73; // [rsp+128h] [rbp-A0h]
  _QWORD v74[3]; // [rsp+130h] [rbp-98h] BYREF
  unsigned __int64 v75; // [rsp+148h] [rbp-80h]
  _QWORD v76[3]; // [rsp+150h] [rbp-78h] BYREF
  unsigned __int64 v77; // [rsp+168h] [rbp-60h]
  WCHAR Buffer[16]; // [rsp+170h] [rbp-58h] BYREF

  hMem = lpBuffer;
  v55 = a7;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 38, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids);
  }
  memset_0(&Arguments, 0, 0x40u);
  `eh vector constructor iterator'(v72, 0x20u, 3u, std::wstring::wstring, std::wstring::~wstring);
  nSize = 16;
  if ( !GetComputerNameW(Buffer, &nSize) )
  {
    LastError = GetLastError();
    v12 = LastError;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 39, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids, LastError);
    }
    goto LABEL_140;
  }
  v63 = 7;
  if ( a2 )
  {
    v62 = 0;
    LOWORD(Src[0]) = 0;
    v60 = 7;
    v59 = 0;
    LOWORD(Block[0]) = 0;
    *(_QWORD *)v51 = 0;
    *(_QWORD *)v52 = 0;
    if ( !(unsigned int)TimeToString((FILETIME *)(a3 + 424), v72) )
    {
      v24 = GetLastError();
      v12 = v24;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v26 = 43;
LABEL_52:
      WPP_SF_d(*((_QWORD *)v25 + 2), v26, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids, v24);
LABEL_53:
      if ( v60 >= 8 )
        operator delete(Block[0]);
      v59 = 0;
      LOWORD(Block[0]) = 0;
LABEL_137:
      v60 = 7;
      goto LABEL_138;
    }
    Arguments = a4;
    v27 = v72;
    if ( v73 >= 8 )
      v27 = (_QWORD *)v72[0];
    v65 = v27;
    v66 = Buffer;
    v67 = (_QWORD *)*(unsigned int *)(a3 + 64);
    if ( !FormatMessageW(0x2900u, g_hResource, 1073745934 - (a1 != 0), 0x800u, v51, 0, &Arguments) )
    {
      v28 = GetLastError();
      v12 = v28;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids, v28);
      }
      if ( v60 >= 8 )
        operator delete(Block[0]);
      v59 = 0;
      LOWORD(Block[0]) = 0;
      goto LABEL_137;
    }
    if ( !FormatMessageW(0x2900u, g_hResource, 1073745941 - (a1 != 0), 0x800u, v52, 0, &Arguments) )
    {
      if ( *(_QWORD *)v51 )
        LocalFree(*(HLOCAL *)v51);
      v24 = GetLastError();
      v12 = v24;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v26 = 45;
      goto LABEL_52;
    }
    if ( __eh34_try(-1, 0) )
    {
      __eh34_scope_strut(0);
      std::wstring::assign((char *)Src, *(char **)v51);
      std::wstring::append((char *)Block, (char *)L"<HTML>");
      std::wstring::append((char *)Block, (char *)L"\n");
      std::wstring::append((char *)Block, (char *)L"<HEAD>");
      std::wstring::append((char *)Block, (char *)L"\n");
      std::wstring::append(
        (char *)Block,
        (char *)L"<META HTTP-EQUIV=\"Content-Type\" CONTENT=\"text/html; charset=utf-8\">");
      std::wstring::append((char *)Block, (char *)L"\n");
      std::wstring::append((char *)Block, (char *)L"<TITLE>");
      String = (char *)GetString(0x1F7Bu);
      std::wstring::append((char *)Block, String);
      std::wstring::append((char *)Block, (char *)L"</TITLE>");
      std::wstring::append((char *)Block, (char *)L"\n");
      std::wstring::append((char *)Block, (char *)L"</HEAD>");
      std::wstring::append((char *)Block, (char *)L"\n");
      std::wstring::append((char *)Block, (char *)L"<BODY>");
      std::wstring::append((char *)Block, (char *)L"\n");
      std::wstring::append((char *)Block, (char *)L"<P>");
      std::wstring::append((char *)Block, (char *)L"\n");
      std::wstring::append((char *)Block, *(char **)v52);
      std::wstring::append((char *)Block, (char *)L"\n");
      std::wstring::append((char *)Block, (char *)L"</P>");
      std::wstring::append((char *)Block, (char *)L"\n");
    }
    if ( __eh34_catch(0) )
    {
      if ( __eh34_catch_type(0, &exception `RTTI Type Descriptor', &v56) )
      {
        if ( *(_QWORD *)v51 )
          LocalFree(*(HLOCAL *)v51);
        if ( *(_QWORD *)v52 )
          LocalFree(*(HLOCAL *)v52);
        exception::exception((exception *)v57, v56);
        throw (exception *)v57;
      }
    }
    if ( *(_QWORD *)v51 )
      LocalFree(*(HLOCAL *)v51);
    if ( *(_QWORD *)v52 )
      LocalFree(*(HLOCAL *)v52);
    std::wstring::append((char *)Block, (char *)L"<P>");
    std::wstring::append((char *)Block, (char *)L"\n");
    if ( *(_DWORD *)(a3 + 376) )
    {
      std::wstring::append((char *)Block, (char *)L"<TABLE BORDER=1 CELLSPACING=0 CELLPADDING=2>");
      std::wstring::append((char *)Block, (char *)L"\n");
      if ( (unsigned int)AddRecipientLine(0, 0, Src, Block) )
      {
        for ( i = *(_QWORD **)(a3 + 216); ; i = (_QWORD *)*i )
        {
          if ( i == (_QWORD *)(a3 + 216) )
          {
            std::wstring::append((char *)Src, (char *)L"\n");
            std::wstring::append((char *)Block, (char *)L"</TABLE>");
            std::wstring::append((char *)Block, (char *)L"\n");
            goto LABEL_89;
          }
          v31 = i[2];
          if ( *(_DWORD *)(v31 + 1844) == 256 && !(unsigned int)AddRecipientLine(v31, 0, Src, Block) )
            break;
        }
        v24 = GetLastError();
        v12 = v24;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_53;
        }
        v26 = 47;
      }
      else
      {
        v24 = GetLastError();
        v12 = v24;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_53;
        }
        v26 = 46;
      }
      goto LABEL_52;
    }
LABEL_89:
    if ( *(_DWORD *)(a3 + 384) )
    {
      std::wstring::append((char *)Block, (char *)L"<BR>");
      std::wstring::append((char *)Block, (char *)L"\n");
      std::wstring::append((char *)Block, (char *)L"<TABLE BORDER=1 CELLSPACING=0 CELLPADDING=2>");
      std::wstring::append((char *)Block, (char *)L"\n");
      if ( (unsigned int)AddRecipientLine(0, 1, Src, Block) )
      {
        for ( j = *(_QWORD **)(a3 + 216); ; j = (_QWORD *)*j )
        {
          if ( j == (_QWORD *)(a3 + 216) )
          {
            std::wstring::append((char *)Block, (char *)L"</TABLE>");
            std::wstring::append((char *)Block, (char *)L"\n");
            goto LABEL_105;
          }
          v33 = j[2];
          if ( *(_DWORD *)(v33 + 1844) == 128 && !(unsigned int)AddRecipientLine(v33, 1, Src, Block) )
            break;
        }
        v24 = GetLastError();
        v12 = v24;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_53;
        }
        v26 = 49;
      }
      else
      {
        v24 = GetLastError();
        v12 = v24;
        v25 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
        {
          goto LABEL_53;
        }
        v26 = 48;
      }
      goto LABEL_52;
    }
LABEL_105:
    std::wstring::append((char *)Block, (char *)L"</P>");
    std::wstring::append((char *)Block, (char *)L"\n");
    if ( a5 && *(_QWORD *)(a3 + 184) )
    {
      std::wstring::append((char *)Src, (char *)L"\n\n");
      std::wstring::append((char *)Block, (char *)L"<P>");
      std::wstring::append((char *)Block, (char *)L"\n");
      if ( *(_QWORD *)(a3 + 72) )
        v34 = 8057;
      else
        v34 = 8058;
      v35 = (char *)GetString(v34);
      v36 = v35;
      if ( !v35 )
      {
        if ( v60 >= 8 )
          operator delete(Block[0]);
        LOWORD(Block[0]) = 0;
        v59 = 0;
        v60 = 7;
        if ( v63 >= 8 )
          operator delete(Src[0]);
        v63 = 7;
        v62 = 0;
        LOWORD(Src[0]) = 0;
        goto LABEL_115;
      }
      std::wstring::append((char *)Src, v35);
      std::wstring::append((char *)Block, v36);
      std::wstring::append((char *)Block, (char *)L"\n");
      std::wstring::append((char *)Block, (char *)L"</P>");
      std::wstring::append((char *)Src, (char *)L"\n");
      std::wstring::append((char *)Block, (char *)L"\n");
    }
    std::wstring::append((char *)Block, (char *)L"</BODY>");
    std::wstring::append((char *)Block, (char *)L"\n");
    std::wstring::append((char *)Block, (char *)L"</HTML>");
    v38 = v59;
    v39 = (unsigned int)(2 * v62 + 2);
    v40 = LocalAlloc(0, v39);
    v41 = (unsigned __int16 **)hMem;
    *(_QWORD *)hMem = v40;
    if ( !v40 )
    {
      v24 = GetLastError();
      v12 = v24;
      v25 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_53;
      }
      v26 = 50;
      goto LABEL_52;
    }
    v42 = (unsigned int)(2 * v38 + 2);
    v43 = LocalAlloc(0, v42);
    v44 = (unsigned __int16 **)v55;
    *(_QWORD *)v55 = v43;
    if ( !v43 )
    {
      if ( *v41 )
        LocalFree(v41);
      v45 = GetLastError();
      v12 = v45;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 51, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids, v45);
      }
      if ( v60 >= 8 )
        operator delete(Block[0]);
      v59 = 0;
      LOWORD(Block[0]) = 0;
      goto LABEL_137;
    }
    v46 = (const unsigned __int16 *)Src;
    if ( v63 >= 8 )
      v46 = Src[0];
    v47 = StringCbCopyW(*v41, v39, v46);
    if ( v47 >= 0 )
    {
      v50 = Block;
      if ( v60 >= 8 )
        v50 = (void **)Block[0];
      v47 = StringCbCopyW(*v44, v42, (const unsigned __int16 *)v50);
      if ( v47 >= 0 )
        goto LABEL_158;
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
LABEL_157:
        LocalFree(v41);
        LocalFree(v44);
LABEL_158:
        if ( v60 >= 8 )
          operator delete(Block[0]);
        v60 = 7;
        v59 = 0;
        LOWORD(Block[0]) = 0;
        goto LABEL_161;
      }
      v49 = 53;
    }
    else
    {
      v48 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (CMapDeviceId *)&WPP_GLOBAL_Control
        || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) == 0
        || *((_BYTE *)WPP_GLOBAL_Control + 25) < 2u )
      {
        goto LABEL_157;
      }
      v49 = 52;
    }
    WPP_SF_d(*((_QWORD *)v48 + 2), v49, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids, (unsigned int)v47);
    goto LABEL_157;
  }
  v62 = 0;
  LOWORD(Src[0]) = 0;
  if ( !(unsigned int)TimeToString((FILETIME *)(*(_QWORD *)(a3 + 584) + 424LL), v72)
    || !(unsigned int)TimeToString((FILETIME *)(a3 + 1160), v74)
    || !(unsigned int)TimeToString((FILETIME *)(a3 + 1168), v76) )
  {
    v17 = GetLastError();
    v12 = v17;
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v19 = 40;
      goto LABEL_27;
    }
    goto LABEL_138;
  }
  if ( a1 )
  {
    v13 = 1073745931;
    v14 = v72;
    if ( v73 >= 8 )
      v14 = (_QWORD *)v72[0];
    v65 = v14;
    v66 = Buffer;
    v15 = v74;
    if ( v75 >= 8 )
      v15 = (_QWORD *)v74[0];
    v67 = v15;
    v16 = v76;
    if ( v77 >= 8 )
      v16 = (_QWORD *)v76[0];
    v68 = v16;
    v69 = *(unsigned int *)(a3 + 592);
    v70 = *(unsigned int *)(a3 + 64);
    goto LABEL_38;
  }
  if ( (unsigned int)PrepareReceiptErrorString(a3, (char *)Src) )
  {
    v13 = 1073745932;
    v20 = v72;
    if ( v73 >= 8 )
      v20 = (_QWORD *)v72[0];
    v65 = v20;
    v66 = Buffer;
    v21 = v74;
    if ( v75 >= 8 )
      v21 = (_QWORD *)v74[0];
    v67 = v21;
    v22 = v76;
    if ( v77 >= 8 )
      v22 = (_QWORD *)v76[0];
    v68 = v22;
    v69 = *(unsigned int *)(a3 + 592);
    v70 = *(unsigned int *)(a3 + 64);
    v23 = Src;
    if ( v63 >= 8 )
      v23 = (unsigned __int16 **)Src[0];
    v71 = v23;
LABEL_38:
    Arguments = a4;
    if ( !FormatMessageW(0x2900u, g_hResource, v13, 0x800u, lpBuffer, 0, &Arguments) )
    {
      v17 = GetLastError();
      v12 = v17;
      v18 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v19 = 42;
        goto LABEL_27;
      }
      goto LABEL_138;
    }
LABEL_161:
    if ( v63 >= 8 )
      operator delete(Src[0]);
    goto LABEL_163;
  }
  v17 = GetLastError();
  v12 = v17;
  v18 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (CMapDeviceId *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    v19 = 41;
LABEL_27:
    WPP_SF_d(*((_QWORD *)v18 + 2), v19, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids, v17);
  }
LABEL_138:
  if ( v63 >= 8 )
    operator delete(Src[0]);
LABEL_140:
  if ( v12 )
  {
    SetLastError(v12);
LABEL_115:
    `eh vector destructor iterator'(v72, 0x20u, 3u, std::wstring::~wstring);
    return 0;
  }
LABEL_163:
  `eh vector destructor iterator'(v72, 0x20u, 3u, std::wstring::~wstring);
  return 1;
}

```

## disassembly

```asm
0x140067ad0  mov     [rsp+arg_0], rbx
0x140067ad5  mov     [rsp+arg_8], rsi
0x140067ada  push    rdi
0x140067adb  push    r12
0x140067add  push    r13
0x140067adf  push    r14
0x140067ae1  push    r15
0x140067ae3  sub     rsp, 1A0h
0x140067aea  mov     rax, cs:__security_cookie
0x140067af1  xor     rax, rsp
0x140067af4  mov     [rsp+1C8h+var_38], rax
0x140067afc  mov     r12, r9
0x140067aff  mov     rbx, r8
0x140067b02  mov     edi, edx
0x140067b04  mov     r15d, ecx
0x140067b07  mov     r13, [rsp+1C8h+arg_28]
0x140067b0f  mov     [rsp+1C8h+hMem], r13
0x140067b14  mov     rax, [rsp+1C8h+arg_30]
0x140067b1c  mov     [rsp+1C8h+var_168], rax
0x140067b21  lea     rax, WPP_GLOBAL_Control
0x140067b28  mov     rcx, cs:WPP_GLOBAL_Control
0x140067b2f  mov     sil, 4
0x140067b32  cmp     rcx, rax
0x140067b35  jz      short loc_140067B5D
0x140067b37  test    [rcx+1Ch], sil
0x140067b3b  jz      short loc_140067B5D
0x140067b3d  cmp     byte ptr [rcx+19h], 5
0x140067b41  jb      short loc_140067B5D
0x140067b43  mov     edx, 26h ; '&'
0x140067b48  lea     r14, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids
0x140067b4f  mov     r8, r14
0x140067b52  mov     rcx, [rcx+10h]
0x140067b56  call    WPP_SF_
0x140067b5b  jmp     short loc_140067B64
0x140067b5d  lea     r14, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids
0x140067b64  xor     edx, edx; Val
0x140067b66  lea     r8d, [rdx+40h]; Size
0x140067b6a  lea     rcx, [rsp+1C8h+var_F8]; void *
0x140067b72  call    memset_0
0x140067b77  lea     rax, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140067b7e  mov     [rsp+1C8h+lpBuffer], rax; void (*)(void *)
0x140067b83  lea     r9, ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x140067b8a  mov     edx, 20h ; ' '; unsigned __int64
0x140067b8f  lea     r8d, [rdx-1Dh]; unsigned __int64
0x140067b93  lea     rcx, [rsp+1C8h+var_B8]; void *
0x140067b9b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140067ba0  nop
0x140067ba1  mov     [rsp+1C8h+nSize], 10h
0x140067ba9  lea     rdx, [rsp+1C8h+nSize]; nSize
0x140067bae  lea     rcx, [rsp+1C8h+Buffer]; lpBuffer
0x140067bb6  call    cs:__imp_GetComputerNameW
0x140067bbd  nop     dword ptr [rax+rax+00h]
0x140067bc2  test    eax, eax
0x140067bc4  jnz     short loc_140067C18
0x140067bc6  call    cs:__imp_GetLastError
0x140067bcd  nop     dword ptr [rax+rax+00h]
0x140067bd2  mov     ebx, eax
0x140067bd4  mov     rcx, cs:WPP_GLOBAL_Control
0x140067bdb  lea     rdx, WPP_GLOBAL_Control
0x140067be2  cmp     rcx, rdx
0x140067be5  jz      loc_14006895F
0x140067beb  test    [rcx+1Ch], sil
0x140067bef  jz      loc_14006895F
0x140067bf5  cmp     byte ptr [rcx+19h], 2
0x140067bf9  jb      loc_14006895F
0x140067bff  mov     edx, 27h ; '''
0x140067c04  mov     r9d, eax
0x140067c07  mov     r8, r14
0x140067c0a  mov     rcx, [rcx+10h]
0x140067c0e  call    WPP_SF_d
0x140067c13  jmp     loc_14006895F
0x140067c18  test    edi, edi
0x140067c1a  mov     edi, 7
0x140067c1f  mov     [rsp+1C8h+var_108], rdi
0x140067c27  jnz     loc_140067F22
0x140067c2d  mov     [rsp+1C8h+var_110], 0
0x140067c39  xor     eax, eax
0x140067c3b  mov     word ptr [rsp+1C8h+Src], ax
0x140067c43  mov     rcx, [rbx+248h]
0x140067c4a  add     rcx, 1A8h; lpFileTime
0x140067c51  lea     rdx, [rsp+1C8h+var_B8]; void *
0x140067c59  call    TimeToString
0x140067c5e  test    eax, eax
0x140067c60  jz      loc_140067EDF
0x140067c66  lea     rcx, [rbx+488h]; lpFileTime
0x140067c6d  lea     rdx, [rsp+1C8h+var_98]; void *
0x140067c75  call    TimeToString
0x140067c7a  test    eax, eax
0x140067c7c  jz      loc_140067EDF
0x140067c82  lea     rcx, [rbx+490h]; lpFileTime
0x140067c89  lea     rdx, [rsp+1C8h+var_78]; void *
0x140067c91  call    TimeToString
0x140067c96  test    eax, eax
0x140067c98  jz      loc_140067EDF
0x140067c9e  test    r15d, r15d
0x140067ca1  jz      loc_140067D41
0x140067ca7  mov     r8d, 4000100Bh
0x140067cad  lea     rax, [rsp+1C8h+var_B8]
0x140067cb5  cmp     [rsp+1C8h+var_A0], 8
0x140067cbe  cmovnb  rax, [rsp+1C8h+var_B8]
0x140067cc7  mov     [rsp+1C8h+var_F0], rax
0x140067ccf  lea     rax, [rsp+1C8h+Buffer]
0x140067cd7  mov     [rsp+1C8h+var_E8], rax
0x140067cdf  lea     rax, [rsp+1C8h+var_98]
0x140067ce7  cmp     [rsp+1C8h+var_80], 8
0x140067cf0  cmovnb  rax, [rsp+1C8h+var_98]
0x140067cf9  mov     [rsp+1C8h+var_E0], rax
0x140067d01  lea     rax, [rsp+1C8h+var_78]
0x140067d09  cmp     [rsp+1C8h+var_60], 8
0x140067d12  cmovnb  rax, [rsp+1C8h+var_78]
0x140067d1b  mov     [rsp+1C8h+var_D8], rax
0x140067d23  mov     eax, [rbx+250h]
0x140067d29  mov     [rsp+1C8h+var_D0], rax
0x140067d31  mov     eax, [rbx+40h]
0x140067d34  mov     [rsp+1C8h+var_C8], rax
0x140067d3c  jmp     loc_140067E53
0x140067d41  lea     rdx, [rsp+1C8h+Src]
0x140067d49  mov     rcx, rbx
0x140067d4c  call    PrepareReceiptErrorString
0x140067d51  test    eax, eax
0x140067d53  jnz     short loc_140067D9C
0x140067d55  call    cs:__imp_GetLastError
0x140067d5c  nop     dword ptr [rax+rax+00h]
0x140067d61  mov     ebx, eax
0x140067d63  mov     rcx, cs:WPP_GLOBAL_Control
0x140067d6a  lea     rdx, WPP_GLOBAL_Control
0x140067d71  cmp     rcx, rdx
0x140067d74  jz      short loc_140067D97
0x140067d76  test    [rcx+1Ch], sil
0x140067d7a  jz      short loc_140067D97
0x140067d7c  cmp     byte ptr [rcx+19h], 2
0x140067d80  jb      short loc_140067D97
0x140067d82  mov     edx, 29h ; ')'
0x140067d87  mov     r9d, eax
0x140067d8a  mov     r8, r14
0x140067d8d  mov     rcx, [rcx+10h]
0x140067d91  call    WPP_SF_d
0x140067d96  nop
0x140067d97  jmp     loc_140068947
0x140067d9c  mov     r8d, 4000100Ch; dwMessageId
0x140067da2  lea     rax, [rsp+1C8h+var_B8]
0x140067daa  cmp     [rsp+1C8h+var_A0], 8
0x140067db3  cmovnb  rax, [rsp+1C8h+var_B8]
0x140067dbc  mov     [rsp+1C8h+var_F0], rax
0x140067dc4  lea     rax, [rsp+1C8h+Buffer]
0x140067dcc  mov     [rsp+1C8h+var_E8], rax
0x140067dd4  lea     rax, [rsp+1C8h+var_98]
0x140067ddc  cmp     [rsp+1C8h+var_80], 8
0x140067de5  cmovnb  rax, [rsp+1C8h+var_98]
0x140067dee  mov     [rsp+1C8h+var_E0], rax
0x140067df6  lea     rax, [rsp+1C8h+var_78]
0x140067dfe  cmp     [rsp+1C8h+var_60], 8
0x140067e07  cmovnb  rax, [rsp+1C8h+var_78]
0x140067e10  mov     [rsp+1C8h+var_D8], rax
0x140067e18  mov     eax, [rbx+250h]
0x140067e1e  mov     [rsp+1C8h+var_D0], rax
0x140067e26  mov     eax, [rbx+40h]
0x140067e29  mov     [rsp+1C8h+var_C8], rax
0x140067e31  lea     rax, [rsp+1C8h+Src]
0x140067e39  cmp     [rsp+1C8h+var_108], 8
0x140067e42  cmovnb  rax, [rsp+1C8h+Src]
0x140067e4b  mov     [rsp+1C8h+var_C0], rax
0x140067e53  mov     [rsp+1C8h+var_F8], r12
0x140067e5b  lea     rax, [rsp+1C8h+var_F8]
0x140067e63  mov     [rsp+1C8h+Arguments], rax; Arguments
0x140067e68  mov     [rsp+1C8h+var_1A0], 0; nSize
0x140067e70  mov     [rsp+1C8h+lpBuffer], r13; lpBuffer
0x140067e75  mov     r9d, 800h; dwLanguageId
0x140067e7b  mov     rdx, cs:?g_hResource@@3PEAUHINSTANCE__@@EA; lpSource
0x140067e82  mov     ecx, 2900h; dwFlags
0x140067e87  call    cs:__imp_FormatMessageW
0x140067e8e  nop     dword ptr [rax+rax+00h]
0x140067e93  test    eax, eax
0x140067e95  jnz     short loc_140067EDA
0x140067e97  call    cs:__imp_GetLastError
0x140067e9e  nop     dword ptr [rax+rax+00h]
0x140067ea3  mov     ebx, eax
0x140067ea5  mov     rcx, cs:WPP_GLOBAL_Control
0x140067eac  lea     rdx, WPP_GLOBAL_Control
0x140067eb3  cmp     rcx, rdx
0x140067eb6  jz      loc_140067D97
0x140067ebc  test    [rcx+1Ch], sil
0x140067ec0  jz      loc_140067D97
0x140067ec6  cmp     byte ptr [rcx+19h], 2
0x140067eca  jb      loc_140067D97
0x140067ed0  mov     edx, 2Ah ; '*'
0x140067ed5  jmp     loc_140067D87
0x140067eda  jmp     loc_140068A79
0x140067edf  call    cs:__imp_GetLastError
0x140067ee6  nop     dword ptr [rax+rax+00h]
0x140067eeb  mov     ebx, eax
0x140067eed  mov     rcx, cs:WPP_GLOBAL_Control
0x140067ef4  lea     rdx, WPP_GLOBAL_Control
0x140067efb  cmp     rcx, rdx
0x140067efe  jz      loc_140067D97
0x140067f04  test    [rcx+1Ch], sil
0x140067f08  jz      loc_140067D97
0x140067f0e  cmp     byte ptr [rcx+19h], 2
0x140067f12  jb      loc_140067D97
0x140067f18  mov     edx, 28h ; '('
0x140067f1d  jmp     loc_140067D87
0x140067f22  xor     r13d, r13d
0x140067f25  mov     [rsp+1C8h+var_110], r13
0x140067f2d  mov     word ptr [rsp+1C8h+Src], r13w
0x140067f36  mov     [rsp+1C8h+var_128], rdi
0x140067f3e  mov     [rsp+1C8h+var_130], r13
0x140067f46  mov     word ptr [rsp+1C8h+Block], r13w
0x140067f4f  mov     qword ptr [rsp+1C8h+var_188], r13
0x140067f54  mov     qword ptr [rsp+1C8h+var_180], r13
0x140067f59  lea     rcx, [rbx+1A8h]; lpFileTime
0x140067f60  lea     rdx, [rsp+1C8h+var_B8]; void *
0x140067f68  call    TimeToString
0x140067f6d  test    eax, eax
0x140067f6f  jnz     short loc_140067FE0
0x140067f71  call    cs:__imp_GetLastError
0x140067f78  nop     dword ptr [rax+rax+00h]
0x140067f7d  mov     ebx, eax
0x140067f7f  mov     rcx, cs:WPP_GLOBAL_Control
0x140067f86  lea     rdx, WPP_GLOBAL_Control
0x140067f8d  cmp     rcx, rdx
0x140067f90  jz      short loc_140067FB2
0x140067f92  test    [rcx+1Ch], sil
0x140067f96  jz      short loc_140067FB2
0x140067f98  cmp     byte ptr [rcx+19h], 2
0x140067f9c  jb      short loc_140067FB2
0x140067f9e  lea     edx, [r13+2Bh]
0x140067fa2  mov     r9d, eax
0x140067fa5  mov     r8, r14
0x140067fa8  mov     rcx, [rcx+10h]
0x140067fac  call    WPP_SF_d
0x140067fb1  nop
0x140067fb2  cmp     [rsp+1C8h+var_128], 8
0x140067fbb  jb      short loc_140067FCA
0x140067fbd  mov     rcx, [rsp+1C8h+Block]; Block
0x140067fc5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140067fca  mov     [rsp+1C8h+var_130], r13
0x140067fd2  mov     word ptr [rsp+1C8h+Block], r13w
0x140067fdb  jmp     loc_14006893F
0x140067fe0  mov     eax, r15d
0x140067fe3  neg     eax
0x140067fe5  sbb     r13d, r13d
0x140067fe8  neg     r15d
0x140067feb  sbb     r8d, r8d
0x140067fee  add     r8d, 4000100Eh; dwMessageId
0x140067ff5  mov     [rsp+1C8h+var_F8], r12
0x140067ffd  lea     rax, [rsp+1C8h+var_B8]
0x140068005  cmp     [rsp+1C8h+var_A0], 8
0x14006800e  cmovnb  rax, [rsp+1C8h+var_B8]
0x140068017  mov     [rsp+1C8h+var_F0], rax
0x14006801f  lea     rax, [rsp+1C8h+Buffer]
0x140068027  mov     [rsp+1C8h+var_E8], rax
0x14006802f  mov     eax, [rbx+40h]
0x140068032  mov     [rsp+1C8h+var_E0], rax
0x14006803a  lea     rax, [rsp+1C8h+var_F8]
0x140068042  mov     [rsp+1C8h+Arguments], rax; Arguments
0x140068047  xor     r15d, r15d
0x14006804a  mov     [rsp+1C8h+var_1A0], r15d; nSize
0x14006804f  lea     rax, [rsp+1C8h+var_188]
0x140068054  mov     [rsp+1C8h+lpBuffer], rax; lpBuffer
0x140068059  mov     r9d, 800h; dwLanguageId
0x14006805f  mov     rdx, cs:?g_hResource@@3PEAUHINSTANCE__@@EA; lpSource
0x140068066  mov     ecx, 2900h; dwFlags
0x14006806b  call    cs:__imp_FormatMessageW
0x140068072  nop     dword ptr [rax+rax+00h]
0x140068077  test    eax, eax
0x140068079  jnz     short loc_1400680EA
0x14006807b  call    cs:__imp_GetLastError
0x140068082  nop     dword ptr [rax+rax+00h]
0x140068087  mov     ebx, eax
0x140068089  mov     rcx, cs:WPP_GLOBAL_Control
0x140068090  lea     rdx, WPP_GLOBAL_Control
0x140068097  cmp     rcx, rdx
0x14006809a  jz      short loc_1400680BC
0x14006809c  test    [rcx+1Ch], sil
0x1400680a0  jz      short loc_1400680BC
0x1400680a2  cmp     byte ptr [rcx+19h], 2
0x1400680a6  jb      short loc_1400680BC
0x1400680a8  lea     edx, [r15+2Ch]
0x1400680ac  mov     r9d, eax
0x1400680af  mov     r8, r14
0x1400680b2  mov     rcx, [rcx+10h]
0x1400680b6  call    WPP_SF_d
0x1400680bb  nop
0x1400680bc  cmp     [rsp+1C8h+var_128], 8
0x1400680c5  jb      short loc_1400680D4
0x1400680c7  mov     rcx, [rsp+1C8h+Block]; Block
0x1400680cf  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1400680d4  mov     [rsp+1C8h+var_130], r15
0x1400680dc  mov     word ptr [rsp+1C8h+Block], r15w
0x1400680e5  jmp     loc_14006893F
0x1400680ea  lea     rax, [rsp+1C8h+var_F8]
0x1400680f2  mov     [rsp+1C8h+Arguments], rax; Arguments
0x1400680f7  mov     [rsp+1C8h+var_1A0], r15d; nSize
0x1400680fc  lea     rax, [rsp+1C8h+var_180]
0x140068101  mov     [rsp+1C8h+lpBuffer], rax; lpBuffer
0x140068106  mov     r9d, 800h; dwLanguageId
0x14006810c  lea     r8d, [r13+40001015h]; dwMessageId
0x140068113  mov     rdx, cs:?g_hResource@@3PEAUHINSTANCE__@@EA; lpSource
0x14006811a  mov     ecx, 2900h; dwFlags
0x14006811f  call    cs:__imp_FormatMessageW
  ... truncated ...
```
