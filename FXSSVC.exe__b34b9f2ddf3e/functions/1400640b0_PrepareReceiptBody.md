# PrepareReceiptBody

- ea: `0x1400640b0`
- end: `0x140064ff8`
- name: `PrepareReceiptBody`
- size: `3912`
- prototype: `__int64 __fastcall(int, int, int, int, int, LPWSTR, __int64)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callers

- `0x140065504`

## callees

- `0x140001b8c`
- `0x140002790`
- `0x140002858`
- `0x140002c43`
- `0x140004b30`
- `0x140004b58`
- `0x14001598c`
- `0x14002c28c`
- `0x14002c54c`
- `0x14004fc7c`
- `0x140062a68`
- `0x1400640b0`
- `0x140065000`
- `0x140065a98`
- `0x1400818b0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1400641a0`
- `KERNEL32!GetLastError` at `0x140064329`
- `KERNEL32!GetLastError` at `0x14006445f`
- `KERNEL32!GetLastError` at `0x1400644a1`
- `KERNEL32!GetLastError` at `0x14006452d`
- `KERNEL32!GetLastError` at `0x14006462b`
- `KERNEL32!GetLastError` at `0x1400646e6`
- `KERNEL32!GetLastError` at `0x14006493f`
- `KERNEL32!GetLastError` at `0x140064a70`
- `KERNEL32!GetLastError` at `0x140064aad`
- `KERNEL32!GetLastError` at `0x140064ca1`
- `KERNEL32!GetLastError` at `0x140064db5`
- `KERNEL32!GetLastError` at `0x140064e26`
- `KERNEL32!GetLastError` at `0x1400641a0`
- `KERNEL32!GetLastError` at `0x140064329`
- `KERNEL32!GetLastError` at `0x14006445f`
- `KERNEL32!GetLastError` at `0x1400644a1`
- `KERNEL32!GetLastError` at `0x14006452d`
- `KERNEL32!GetLastError` at `0x14006462b`
- `KERNEL32!GetLastError` at `0x1400646e6`
- `KERNEL32!GetLastError` at `0x14006493f`
- `KERNEL32!GetLastError` at `0x140064a70`
- `KERNEL32!GetLastError` at `0x140064aad`
- `KERNEL32!GetLastError` at `0x140064ca1`
- `KERNEL32!GetLastError` at `0x140064db5`
- `KERNEL32!GetLastError` at `0x140064e26`
- `KERNEL32!SetLastError` at `0x140064eba`
- `KERNEL32!SetLastError` at `0x140064eba`
- `KERNEL32!LocalFree` at `0x1400646e0`
- `KERNEL32!LocalFree` at `0x1400648b7`
- `KERNEL32!LocalFree` at `0x1400648c7`
- `KERNEL32!LocalFree` at `0x140064e20`
- `KERNEL32!LocalFree` at `0x140064f77`
- `KERNEL32!LocalFree` at `0x140064f80`
- `KERNEL32!LocalFree` at `0x1400646e0`
- `KERNEL32!LocalFree` at `0x1400648b7`
- `KERNEL32!LocalFree` at `0x1400648c7`
- `KERNEL32!LocalFree` at `0x140064e20`
- `KERNEL32!LocalFree` at `0x140064f77`
- `KERNEL32!LocalFree` at `0x140064f80`
- `KERNEL32!LocalAlloc` at `0x140064da1`
- `KERNEL32!LocalAlloc` at `0x140064dff`
- `KERNEL32!LocalAlloc` at `0x140064da1`
- `KERNEL32!LocalAlloc` at `0x140064dff`
- `KERNEL32!GetComputerNameW` at `0x140064196`
- `KERNEL32!GetComputerNameW` at `0x140064196`
- `KERNEL32!FormatMessageW` at `0x140064455`
- `KERNEL32!FormatMessageW` at `0x140064621`
- `KERNEL32!FormatMessageW` at `0x1400646c9`
- `KERNEL32!FormatMessageW` at `0x140064455`
- `KERNEL32!FormatMessageW` at `0x140064621`
- `KERNEL32!FormatMessageW` at `0x1400646c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  unsigned __int16 *String; // rax
  _QWORD *i; // r15
  __int64 v31; // rcx
  _QWORD *j; // r15
  __int64 v33; // rcx
  unsigned int v34; // ecx
  unsigned __int16 *v35; // rax
  unsigned __int16 *v36; // rbx
  int v38; // ebx
  SIZE_T v39; // r15
  HLOCAL v40; // rax
  unsigned __int16 **v41; // r12
  SIZE_T v42; // rbx
  HLOCAL v43; // rax
  unsigned __int16 **v44; // r13
  DWORD v45; // eax
  unsigned __int16 *v46; // r8
  int v47; // eax
  CMapDeviceId *v48; // rcx
  __int64 v49; // rdx
  unsigned __int16 *v50; // r8
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
  `eh vector constructor iterator'(v72, 0x20u, 3u, std::wstring::wstring, (void (*)(void *))std::wstring::~wstring);
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
    try
    {
      std::wstring::assign((const void **)Src, *(char **)v51);
      std::wstring::append(Block, L"<HTML>");
      std::wstring::append(Block, (void *)L"\n");
      std::wstring::append(Block, L"<HEAD>");
      std::wstring::append(Block, (void *)L"\n");
      std::wstring::append(Block, L"<META HTTP-EQUIV=\"Content-Type\" CONTENT=\"text/html; charset=utf-8\">");
      std::wstring::append(Block, (void *)L"\n");
      std::wstring::append(Block, L"<TITLE>");
      String = GetString(0x1F7Bu);
      std::wstring::append(Block, String);
      std::wstring::append(Block, L"</TITLE>");
      std::wstring::append(Block, (void *)L"\n");
      std::wstring::append(Block, L"</HEAD>");
      std::wstring::append(Block, (void *)L"\n");
      std::wstring::append(Block, L"<BODY>");
      std::wstring::append(Block, (void *)L"\n");
      std::wstring::append(Block, L"<P>");
      std::wstring::append(Block, (void *)L"\n");
      std::wstring::append(Block, *(void **)v52);
      std::wstring::append(Block, (void *)L"\n");
      std::wstring::append(Block, L"</P>");
      std::wstring::append(Block, (void *)L"\n");
    }
    catch ( exception *v56 )
    {
      if ( *(_QWORD *)v51 )
        LocalFree(*(HLOCAL *)v51);
      if ( *(_QWORD *)v52 )
        LocalFree(*(HLOCAL *)v52);
      exception::exception((exception *)v57, v56);
      throw (exception *)v57;
    }
    if ( *(_QWORD *)v51 )
      LocalFree(*(HLOCAL *)v51);
    if ( *(_QWORD *)v52 )
      LocalFree(*(HLOCAL *)v52);
    std::wstring::append(Block, L"<P>");
    std::wstring::append(Block, (void *)L"\n");
    if ( *(_DWORD *)(a3 + 376) )
    {
      std::wstring::append(Block, L"<TABLE BORDER=1 CELLSPACING=0 CELLPADDING=2>");
      std::wstring::append(Block, (void *)L"\n");
      if ( (unsigned int)AddRecipientLine(0, 0, Src, Block) )
      {
        for ( i = *(_QWORD **)(a3 + 216); ; i = (_QWORD *)*i )
        {
          if ( i == (_QWORD *)(a3 + 216) )
          {
            std::wstring::append(Src, (void *)L"\n");
            std::wstring::append(Block, L"</TABLE>");
            std::wstring::append(Block, (void *)L"\n");
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
      std::wstring::append(Block, L"<BR>");
      std::wstring::append(Block, (void *)L"\n");
      std::wstring::append(Block, L"<TABLE BORDER=1 CELLSPACING=0 CELLPADDING=2>");
      std::wstring::append(Block, (void *)L"\n");
      if ( (unsigned int)AddRecipientLine(0, 1, Src, Block) )
      {
        for ( j = *(_QWORD **)(a3 + 216); ; j = (_QWORD *)*j )
        {
          if ( j == (_QWORD *)(a3 + 216) )
          {
            std::wstring::append(Block, L"</TABLE>");
            std::wstring::append(Block, (void *)L"\n");
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
    std::wstring::append(Block, L"</P>");
    std::wstring::append(Block, (void *)L"\n");
    if ( a5 && *(_QWORD *)(a3 + 184) )
    {
      std::wstring::append(Src, L"\n\n");
      std::wstring::append(Block, L"<P>");
      std::wstring::append(Block, (void *)L"\n");
      if ( *(_QWORD *)(a3 + 72) )
        v34 = 8057;
      else
        v34 = 8058;
      v35 = GetString(v34);
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
      std::wstring::append(Src, v35);
      std::wstring::append(Block, v36);
      std::wstring::append(Block, (void *)L"\n");
      std::wstring::append(Block, L"</P>");
      std::wstring::append(Src, (void *)L"\n");
      std::wstring::append(Block, (void *)L"\n");
    }
    std::wstring::append(Block, L"</BODY>");
    std::wstring::append(Block, (void *)L"\n");
    std::wstring::append(Block, L"</HTML>");
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
    v46 = (unsigned __int16 *)Src;
    if ( v63 >= 8 )
      v46 = Src[0];
    v47 = StringCbCopyW(*v41, v39, v46);
    if ( v47 >= 0 )
    {
      v50 = (unsigned __int16 *)Block;
      if ( v60 >= 8 )
        v50 = (unsigned __int16 *)Block[0];
      v47 = StringCbCopyW(*v44, v42, v50);
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
  if ( (unsigned int)PrepareReceiptErrorString(a3, Src) )
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
    `eh vector destructor iterator'(v72, 0x20u, 3u, (void (*)(void *))std::wstring::~wstring);
    return 0;
  }
LABEL_163:
  `eh vector destructor iterator'(v72, 0x20u, 3u, (void (*)(void *))std::wstring::~wstring);
  return 1;
}

```

## disassembly

```asm
0x1400640b0  mov     [rsp+arg_0], rbx
0x1400640b5  mov     [rsp+arg_8], rsi
0x1400640ba  push    rdi
0x1400640bb  push    r12
0x1400640bd  push    r13
0x1400640bf  push    r14
0x1400640c1  push    r15
0x1400640c3  sub     rsp, 1A0h
0x1400640ca  mov     rax, cs:__security_cookie
0x1400640d1  xor     rax, rsp
0x1400640d4  mov     [rsp+1C8h+var_38], rax
0x1400640dc  mov     r12, r9
0x1400640df  mov     rbx, r8
0x1400640e2  mov     edi, edx
0x1400640e4  mov     r15d, ecx
0x1400640e7  mov     r13, [rsp+1C8h+arg_28]
0x1400640ef  mov     [rsp+1C8h+hMem], r13
0x1400640f4  mov     rax, [rsp+1C8h+arg_30]
0x1400640fc  mov     [rsp+1C8h+var_168], rax
0x140064101  lea     rax, WPP_GLOBAL_Control
0x140064108  mov     rcx, cs:WPP_GLOBAL_Control
0x14006410f  mov     sil, 4
0x140064112  cmp     rcx, rax
0x140064115  jz      short loc_14006413D
0x140064117  test    [rcx+1Ch], sil
0x14006411b  jz      short loc_14006413D
0x14006411d  cmp     byte ptr [rcx+19h], 5
0x140064121  jb      short loc_14006413D
0x140064123  mov     edx, 26h ; '&'
0x140064128  lea     r14, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids
0x14006412f  mov     r8, r14
0x140064132  mov     rcx, [rcx+10h]
0x140064136  call    WPP_SF_
0x14006413b  jmp     short loc_140064144
0x14006413d  lea     r14, WPP_7145112b98923b2a1d2cd0ecc0229a92_Traceguids
0x140064144  xor     edx, edx; Val
0x140064146  lea     r8d, [rdx+40h]; Size
0x14006414a  lea     rcx, [rsp+1C8h+var_F8]; void *
0x140064152  call    memset_0
0x140064157  lea     rax, ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14006415e  mov     [rsp+1C8h+lpBuffer], rax; void (*)(void *)
0x140064163  lea     r9, ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; void (*)(void *)
0x14006416a  mov     edx, 20h ; ' '; unsigned __int64
0x14006416f  lea     r8d, [rdx-1Dh]; unsigned __int64
0x140064173  lea     rcx, [rsp+1C8h+var_B8]; void *
0x14006417b  call    ??_L@YAXPEAX_K1P6AX0@Z2@Z; `eh vector constructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *),void (*)(void *))
0x140064180  nop
0x140064181  mov     [rsp+1C8h+nSize], 10h
0x140064189  lea     rdx, [rsp+1C8h+nSize]; nSize
0x14006418e  lea     rcx, [rsp+1C8h+Buffer]; lpBuffer
0x140064196  call    cs:__imp_GetComputerNameW
0x14006419c  test    eax, eax
0x14006419e  jnz     short loc_1400641EC
0x1400641a0  call    cs:__imp_GetLastError
0x1400641a6  mov     ebx, eax
0x1400641a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1400641af  lea     rdx, WPP_GLOBAL_Control
0x1400641b6  cmp     rcx, rdx
0x1400641b9  jz      loc_140064EB0
0x1400641bf  test    [rcx+1Ch], sil
0x1400641c3  jz      loc_140064EB0
0x1400641c9  cmp     byte ptr [rcx+19h], 2
0x1400641cd  jb      loc_140064EB0
0x1400641d3  mov     edx, 27h ; '''
0x1400641d8  mov     r9d, eax
0x1400641db  mov     r8, r14
0x1400641de  mov     rcx, [rcx+10h]
0x1400641e2  call    WPP_SF_d
0x1400641e7  jmp     loc_140064EB0
0x1400641ec  test    edi, edi
0x1400641ee  mov     edi, 7
0x1400641f3  mov     [rsp+1C8h+var_108], rdi
0x1400641fb  jnz     loc_1400644DE
0x140064201  mov     [rsp+1C8h+var_110], 0
0x14006420d  xor     eax, eax
0x14006420f  mov     word ptr [rsp+1C8h+Src], ax
0x140064217  mov     rcx, [rbx+248h]
0x14006421e  add     rcx, 1A8h; lpFileTime
0x140064225  lea     rdx, [rsp+1C8h+var_B8]; void *
0x14006422d  call    TimeToString
0x140064232  test    eax, eax
0x140064234  jz      loc_1400644A1
0x14006423a  lea     rcx, [rbx+488h]; lpFileTime
0x140064241  lea     rdx, [rsp+1C8h+var_98]; void *
0x140064249  call    TimeToString
0x14006424e  test    eax, eax
0x140064250  jz      loc_1400644A1
0x140064256  lea     rcx, [rbx+490h]; lpFileTime
0x14006425d  lea     rdx, [rsp+1C8h+var_78]; void *
0x140064265  call    TimeToString
0x14006426a  test    eax, eax
0x14006426c  jz      loc_1400644A1
0x140064272  test    r15d, r15d
0x140064275  jz      loc_140064315
0x14006427b  mov     r8d, 4000100Bh
0x140064281  lea     rax, [rsp+1C8h+var_B8]
0x140064289  cmp     [rsp+1C8h+var_A0], 8
0x140064292  cmovnb  rax, [rsp+1C8h+var_B8]
0x14006429b  mov     [rsp+1C8h+var_F0], rax
0x1400642a3  lea     rax, [rsp+1C8h+Buffer]
0x1400642ab  mov     [rsp+1C8h+var_E8], rax
0x1400642b3  lea     rax, [rsp+1C8h+var_98]
0x1400642bb  cmp     [rsp+1C8h+var_80], 8
0x1400642c4  cmovnb  rax, [rsp+1C8h+var_98]
0x1400642cd  mov     [rsp+1C8h+var_E0], rax
0x1400642d5  lea     rax, [rsp+1C8h+var_78]
0x1400642dd  cmp     [rsp+1C8h+var_60], 8
0x1400642e6  cmovnb  rax, [rsp+1C8h+var_78]
0x1400642ef  mov     [rsp+1C8h+var_D8], rax
0x1400642f7  mov     eax, [rbx+250h]
0x1400642fd  mov     [rsp+1C8h+var_D0], rax
0x140064305  mov     eax, [rbx+40h]
0x140064308  mov     [rsp+1C8h+var_C8], rax
0x140064310  jmp     loc_140064421
0x140064315  lea     rdx, [rsp+1C8h+Src]
0x14006431d  mov     rcx, rbx
0x140064320  call    PrepareReceiptErrorString
0x140064325  test    eax, eax
0x140064327  jnz     short loc_14006436A
0x140064329  call    cs:__imp_GetLastError
0x14006432f  mov     ebx, eax
0x140064331  mov     rcx, cs:WPP_GLOBAL_Control
0x140064338  lea     rdx, WPP_GLOBAL_Control
0x14006433f  cmp     rcx, rdx
0x140064342  jz      short loc_140064365
0x140064344  test    [rcx+1Ch], sil
0x140064348  jz      short loc_140064365
0x14006434a  cmp     byte ptr [rcx+19h], 2
0x14006434e  jb      short loc_140064365
0x140064350  mov     edx, 29h ; ')'
0x140064355  mov     r9d, eax
0x140064358  mov     r8, r14
0x14006435b  mov     rcx, [rcx+10h]
0x14006435f  call    WPP_SF_d
0x140064364  nop
0x140064365  jmp     loc_140064E98
0x14006436a  mov     r8d, 4000100Ch; dwMessageId
0x140064370  lea     rax, [rsp+1C8h+var_B8]
0x140064378  cmp     [rsp+1C8h+var_A0], 8
0x140064381  cmovnb  rax, [rsp+1C8h+var_B8]
0x14006438a  mov     [rsp+1C8h+var_F0], rax
0x140064392  lea     rax, [rsp+1C8h+Buffer]
0x14006439a  mov     [rsp+1C8h+var_E8], rax
0x1400643a2  lea     rax, [rsp+1C8h+var_98]
0x1400643aa  cmp     [rsp+1C8h+var_80], 8
0x1400643b3  cmovnb  rax, [rsp+1C8h+var_98]
0x1400643bc  mov     [rsp+1C8h+var_E0], rax
0x1400643c4  lea     rax, [rsp+1C8h+var_78]
0x1400643cc  cmp     [rsp+1C8h+var_60], 8
0x1400643d5  cmovnb  rax, [rsp+1C8h+var_78]
0x1400643de  mov     [rsp+1C8h+var_D8], rax
0x1400643e6  mov     eax, [rbx+250h]
0x1400643ec  mov     [rsp+1C8h+var_D0], rax
0x1400643f4  mov     eax, [rbx+40h]
0x1400643f7  mov     [rsp+1C8h+var_C8], rax
0x1400643ff  lea     rax, [rsp+1C8h+Src]
0x140064407  cmp     [rsp+1C8h+var_108], 8
0x140064410  cmovnb  rax, [rsp+1C8h+Src]
0x140064419  mov     [rsp+1C8h+var_C0], rax
0x140064421  mov     [rsp+1C8h+var_F8], r12
0x140064429  lea     rax, [rsp+1C8h+var_F8]
0x140064431  mov     [rsp+1C8h+Arguments], rax; Arguments
0x140064436  mov     [rsp+1C8h+var_1A0], 0; nSize
0x14006443e  mov     [rsp+1C8h+lpBuffer], r13; lpBuffer
0x140064443  mov     r9d, 800h; dwLanguageId
0x140064449  mov     rdx, cs:?g_hResource@@3PEAUHINSTANCE__@@EA; lpSource
0x140064450  mov     ecx, 2900h; dwFlags
0x140064455  call    cs:__imp_FormatMessageW
0x14006445b  test    eax, eax
0x14006445d  jnz     short loc_14006449C
0x14006445f  call    cs:__imp_GetLastError
0x140064465  mov     ebx, eax
0x140064467  mov     rcx, cs:WPP_GLOBAL_Control
0x14006446e  lea     rdx, WPP_GLOBAL_Control
0x140064475  cmp     rcx, rdx
0x140064478  jz      loc_140064365
0x14006447e  test    [rcx+1Ch], sil
0x140064482  jz      loc_140064365
0x140064488  cmp     byte ptr [rcx+19h], 2
0x14006448c  jb      loc_140064365
0x140064492  mov     edx, 2Ah ; '*'
0x140064497  jmp     loc_140064355
0x14006449c  jmp     loc_140064FB8
0x1400644a1  call    cs:__imp_GetLastError
0x1400644a7  mov     ebx, eax
0x1400644a9  mov     rcx, cs:WPP_GLOBAL_Control
0x1400644b0  lea     rdx, WPP_GLOBAL_Control
0x1400644b7  cmp     rcx, rdx
0x1400644ba  jz      loc_140064365
0x1400644c0  test    [rcx+1Ch], sil
0x1400644c4  jz      loc_140064365
0x1400644ca  cmp     byte ptr [rcx+19h], 2
0x1400644ce  jb      loc_140064365
0x1400644d4  mov     edx, 28h ; '('
0x1400644d9  jmp     loc_140064355
0x1400644de  xor     r13d, r13d
0x1400644e1  mov     [rsp+1C8h+var_110], r13
0x1400644e9  mov     word ptr [rsp+1C8h+Src], r13w
0x1400644f2  mov     [rsp+1C8h+var_128], rdi
0x1400644fa  mov     [rsp+1C8h+var_130], r13
0x140064502  mov     word ptr [rsp+1C8h+Block], r13w
0x14006450b  mov     qword ptr [rsp+1C8h+var_188], r13
0x140064510  mov     qword ptr [rsp+1C8h+var_180], r13
0x140064515  lea     rcx, [rbx+1A8h]; lpFileTime
0x14006451c  lea     rdx, [rsp+1C8h+var_B8]; void *
0x140064524  call    TimeToString
0x140064529  test    eax, eax
0x14006452b  jnz     short loc_140064596
0x14006452d  call    cs:__imp_GetLastError
0x140064533  mov     ebx, eax
0x140064535  mov     rcx, cs:WPP_GLOBAL_Control
0x14006453c  lea     rdx, WPP_GLOBAL_Control
0x140064543  cmp     rcx, rdx
0x140064546  jz      short loc_140064568
0x140064548  test    [rcx+1Ch], sil
0x14006454c  jz      short loc_140064568
0x14006454e  cmp     byte ptr [rcx+19h], 2
0x140064552  jb      short loc_140064568
0x140064554  lea     edx, [r13+2Bh]
0x140064558  mov     r9d, eax
0x14006455b  mov     r8, r14
0x14006455e  mov     rcx, [rcx+10h]
0x140064562  call    WPP_SF_d
0x140064567  nop
0x140064568  cmp     [rsp+1C8h+var_128], 8
0x140064571  jb      short loc_140064580
0x140064573  mov     rcx, [rsp+1C8h+Block]; Block
0x14006457b  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140064580  mov     [rsp+1C8h+var_130], r13
0x140064588  mov     word ptr [rsp+1C8h+Block], r13w
0x140064591  jmp     loc_140064E90
0x140064596  mov     eax, r15d
0x140064599  neg     eax
0x14006459b  sbb     r13d, r13d
0x14006459e  neg     r15d
0x1400645a1  sbb     r8d, r8d
0x1400645a4  add     r8d, 4000100Eh; dwMessageId
0x1400645ab  mov     [rsp+1C8h+var_F8], r12
0x1400645b3  lea     rax, [rsp+1C8h+var_B8]
0x1400645bb  cmp     [rsp+1C8h+var_A0], 8
0x1400645c4  cmovnb  rax, [rsp+1C8h+var_B8]
0x1400645cd  mov     [rsp+1C8h+var_F0], rax
0x1400645d5  lea     rax, [rsp+1C8h+Buffer]
0x1400645dd  mov     [rsp+1C8h+var_E8], rax
0x1400645e5  mov     eax, [rbx+40h]
0x1400645e8  mov     [rsp+1C8h+var_E0], rax
0x1400645f0  lea     rax, [rsp+1C8h+var_F8]
0x1400645f8  mov     [rsp+1C8h+Arguments], rax; Arguments
0x1400645fd  xor     r15d, r15d
0x140064600  mov     [rsp+1C8h+var_1A0], r15d; nSize
0x140064605  lea     rax, [rsp+1C8h+var_188]
0x14006460a  mov     [rsp+1C8h+lpBuffer], rax; lpBuffer
0x14006460f  mov     r9d, 800h; dwLanguageId
0x140064615  mov     rdx, cs:?g_hResource@@3PEAUHINSTANCE__@@EA; lpSource
0x14006461c  mov     ecx, 2900h; dwFlags
0x140064621  call    cs:__imp_FormatMessageW
0x140064627  test    eax, eax
0x140064629  jnz     short loc_140064694
0x14006462b  call    cs:__imp_GetLastError
0x140064631  mov     ebx, eax
0x140064633  mov     rcx, cs:WPP_GLOBAL_Control
0x14006463a  lea     rdx, WPP_GLOBAL_Control
0x140064641  cmp     rcx, rdx
0x140064644  jz      short loc_140064666
0x140064646  test    [rcx+1Ch], sil
0x14006464a  jz      short loc_140064666
0x14006464c  cmp     byte ptr [rcx+19h], 2
0x140064650  jb      short loc_140064666
0x140064652  lea     edx, [r15+2Ch]
0x140064656  mov     r9d, eax
0x140064659  mov     r8, r14
0x14006465c  mov     rcx, [rcx+10h]
0x140064660  call    WPP_SF_d
0x140064665  nop
0x140064666  cmp     [rsp+1C8h+var_128], 8
0x14006466f  jb      short loc_14006467E
0x140064671  mov     rcx, [rsp+1C8h+Block]; Block
0x140064679  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14006467e  mov     [rsp+1C8h+var_130], r15
0x140064686  mov     word ptr [rsp+1C8h+Block], r15w
0x14006468f  jmp     loc_140064E90
0x140064694  lea     rax, [rsp+1C8h+var_F8]
0x14006469c  mov     [rsp+1C8h+Arguments], rax; Arguments
0x1400646a1  mov     [rsp+1C8h+var_1A0], r15d; nSize
0x1400646a6  lea     rax, [rsp+1C8h+var_180]
0x1400646ab  mov     [rsp+1C8h+lpBuffer], rax; lpBuffer
0x1400646b0  mov     r9d, 800h; dwLanguageId
0x1400646b6  lea     r8d, [r13+40001015h]; dwMessageId
0x1400646bd  mov     rdx, cs:?g_hResource@@3PEAUHINSTANCE__@@EA; lpSource
0x1400646c4  mov     ecx, 2900h; dwFlags
0x1400646c9  call    cs:__imp_FormatMessageW
0x1400646cf  xor     r13d, r13d
0x1400646d2  test    eax, eax
0x1400646d4  jnz     short loc_140064723
0x1400646d6  mov     rcx, qword ptr [rsp+1C8h+var_188]; hMem
0x1400646db  test    rcx, rcx
0x1400646de  jz      short loc_1400646E6
0x1400646e0  call    cs:__imp_LocalFree
0x1400646e6  call    cs:__imp_GetLastError
0x1400646ec  mov     ebx, eax
  ... truncated ...
```
