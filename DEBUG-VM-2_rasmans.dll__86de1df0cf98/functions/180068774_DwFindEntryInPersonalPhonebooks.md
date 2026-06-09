# DwFindEntryInPersonalPhonebooks

- ea: `0x180068774`
- end: `0x180068e88`
- name: `DwFindEntryInPersonalPhonebooks`
- size: `1812`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180072928`

## callees

- `0x180005e34`
- `0x18005cd78`
- `0x18005cf68`
- `0x18005d1e0`
- `0x180068774`
- `0x180068e90`
- `0x180069ab4`
- `0x18007b2ec`
- `0x18007b33c`
- `0x1800e7206`
- `0x1800e7260`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068d9a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068ba7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068d9a`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180068be8`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180068be8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180068b98`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180068b98`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180068e26`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180068e26`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800688b5`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x1800688b5`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180068ce9`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x180068ce9`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180068987`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006899b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180068c04`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180068c15`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180068c89`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180068987`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x18006899b`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180068c04`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180068c15`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenW` at `0x180068c89`

## pseudocode

```c
__int64 __fastcall DwFindEntryInPersonalPhonebooks(
        __int64 a1,
        unsigned int a2,
        int a3,
        __int64 a4,
        _QWORD *a5,
        __int64 a6)
{
  __int64 FirstFileW; // r13
  STRSAFE_LPWSTR *v8; // r9
  HRESULT v9; // eax
  unsigned int v10; // ebx
  struct _LIST_ENTRY *v11; // rcx
  __int64 v12; // r9
  __int64 v13; // rdx
  int v14; // ebx
  HRESULT v15; // eax
  unsigned int EntryFromSystem; // eax
  struct _LIST_ENTRY *v17; // rcx
  HRESULT v18; // eax
  DWORD LastError; // eax
  int v20; // ebx
  HRESULT v21; // eax
  bool v22; // zf
  int v23; // eax
  WCHAR *v24; // rax
  size_t *pcchRemaining; // [rsp+20h] [rbp-E0h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR String[264]; // [rsp+2B0h] [rbp+1B0h] BYREF
  WCHAR Buffer[264]; // [rsp+4C0h] [rbp+3C0h] BYREF
  wchar_t pszDest[264]; // [rsp+6D0h] [rbp+5D0h] BYREF

  if ( a1 )
  {
    if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
      && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
    {
      WPP_SF_SDc(WPP_GLOBAL_Control[1].Flink, a2, a3, a1, a2, a3 != 0);
    }
  }
  else if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
         && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
         && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 6u )
  {
    WPP_SF_Dc(WPP_GLOBAL_Control[1].Flink, 827, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, a2, a3 != 0);
  }
  memset_0(pszDest, 0, 0x20Au);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  FirstFileW = -1;
  memset_0(String, 0, 0x20Au);
  memset_0(Buffer, 0, 0x20Au);
  *a5 = 0;
  if ( a3 )
  {
    if ( GetSystemDirectoryW(Buffer, 0x105u) - 1 > 0xF2 )
    {
      v10 = 0;
      goto LABEL_93;
    }
    v9 = StringCchCatExW(Buffer, 0x105u, L"\\Ras\\", v8, pcchRemaining, 0x100u);
    LOWORD(v10) = v9;
    if ( v9 < 0 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
        && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
      {
        WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 828, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, (unsigned int)v9);
        v11 = WPP_GLOBAL_Control;
      }
      v10 = (unsigned __int16)v10;
      goto LABEL_94;
    }
  }
  else if ( !(unsigned int)GetPhonebookDirectory(1u, Buffer) )
  {
    v12 = 621;
    v10 = 621;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_94;
    }
    v13 = 829;
    goto LABEL_92;
  }
  v14 = 260 - lstrlenW(L"*.pbk");
  if ( lstrlenW(String) > v14 )
  {
    v12 = 621;
    v10 = 621;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
      || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
      || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
    {
      goto LABEL_94;
    }
    v13 = 830;
    goto LABEL_92;
  }
  if ( !a3 )
  {
    v15 = StringCchPrintfExW(pszDest, 0x105u, 0, 0, 0x100u, L"%s%s", Buffer, L"rasphone.pbk");
    if ( v15 < 0 )
    {
      v10 = (unsigned __int16)v15;
      if ( (_WORD)v15 )
      {
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
          || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        {
          goto LABEL_94;
        }
        v13 = 831;
LABEL_36:
        v12 = v10;
LABEL_92:
        WPP_SF_d(v11[1].Flink, v13, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v12);
        goto LABEL_93;
      }
      goto LABEL_93;
    }
    EntryFromSystem = DwReadEntryFromSystem(pszDest, (__int64)a5, a6);
    v10 = EntryFromSystem;
    if ( EntryFromSystem )
    {
      v17 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control )
        goto LABEL_48;
      if ( SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0 || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
        goto LABEL_44;
      WPP_SF_d(WPP_GLOBAL_Control[1].Flink, 832, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, EntryFromSystem);
    }
    else if ( *a5 )
    {
      goto LABEL_93;
    }
    v17 = WPP_GLOBAL_Control;
LABEL_44:
    if ( v17 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v17[1].Blink) < 0 && BYTE1(v17[1].Blink) >= 2u )
      WPP_SF_d(v17[1].Flink, 833, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v10);
  }
LABEL_48:
  v18 = StringCchPrintfExW(String, 0x105u, 0, 0, 0x100u, L"%s%s", Buffer, L"*.pbk");
  if ( v18 < 0 )
  {
    v10 = (unsigned __int16)v18;
    if ( (_WORD)v18 )
    {
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_94;
      }
      v13 = 834;
      goto LABEL_36;
    }
LABEL_93:
    v11 = WPP_GLOBAL_Control;
    goto LABEL_94;
  }
  while ( FirstFileW == -1 )
  {
    FirstFileW = (__int64)FindFirstFileW(String, &FindFileData);
    if ( FirstFileW == -1 )
    {
      LastError = GetLastError();
      v10 = LastError;
      if ( !LastError )
        goto LABEL_93;
      v11 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control == (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
        || SBYTE4(WPP_GLOBAL_Control[1].Blink) >= 0
        || BYTE1(WPP_GLOBAL_Control[1].Blink) < 2u )
      {
        goto LABEL_94;
      }
      v13 = 835;
LABEL_91:
      v12 = LastError;
      goto LABEL_92;
    }
LABEL_62:
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 )
    {
      v20 = 260 - lstrlenW(Buffer);
      if ( lstrlenW(FindFileData.cFileName) > v20 )
      {
        v12 = 621;
        v10 = 621;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v13 = 837;
          goto LABEL_92;
        }
        goto LABEL_94;
      }
      v21 = StringCchPrintfExW(String, 0x105u, 0, 0, 0x100u, L"%s%s", Buffer, FindFileData.cFileName);
      if ( v21 < 0 )
      {
        v10 = (unsigned __int16)v21;
        if ( !(_WORD)v21 )
          goto LABEL_93;
        v11 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
          && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
          && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
        {
          v13 = 838;
          goto LABEL_36;
        }
        goto LABEL_94;
      }
      if ( a3 )
      {
        v23 = lstrlenW(String);
        v22 = 2LL * v23 == 0;
        v24 = &String[v23];
        if ( !v22 )
        {
          do
          {
            if ( *v24 == 92 )
              break;
            --v24;
          }
          while ( v24 != String );
        }
        if ( *v24 == 92 )
          ++v24;
        v22 = CompareStringW(0x7Fu, 1u, L"router.pbk", -1, v24, -1) == 2;
      }
      else
      {
        v22 = (unsigned int)CompareStringWrapW(FindFileData.cFileName, L"rasphone.pbk") == 0;
      }
      if ( !v22 )
      {
        v10 = DwReadEntryFromSystem(String, (__int64)a5, a6);
        if ( !v10 )
        {
          if ( *a5 )
            goto LABEL_93;
        }
      }
    }
  }
  if ( FindNextFileW((HANDLE)FirstFileW, &FindFileData) )
    goto LABEL_62;
  LastError = GetLastError();
  v10 = LastError;
  if ( !LastError )
    goto LABEL_93;
  v11 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control
    && SBYTE4(WPP_GLOBAL_Control[1].Blink) < 0
    && BYTE1(WPP_GLOBAL_Control[1].Blink) >= 2u )
  {
    v13 = 836;
    goto LABEL_91;
  }
LABEL_94:
  if ( !*a5 )
  {
    v10 = 623;
    if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v11[1].Blink) < 0 && BYTE1(v11[1].Blink) >= 2u )
    {
      WPP_SF_d(v11[1].Flink, 839, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, 623);
      v11 = WPP_GLOBAL_Control;
    }
  }
  if ( FirstFileW != -1 )
  {
    FindClose((HANDLE)FirstFileW);
    v11 = WPP_GLOBAL_Control;
  }
  if ( v11 != (struct _LIST_ENTRY *)&WPP_GLOBAL_Control && SBYTE4(v11[1].Blink) < 0 && BYTE1(v11[1].Blink) >= 6u )
    WPP_SF_d(v11[1].Flink, 840, &WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids, v10);
  return v10;
}

```

## disassembly

```asm
0x180068774  mov     [rsp-8+arg_10], rbx
0x180068779  push    rbp
0x18006877a  push    rsi
0x18006877b  push    rdi
0x18006877c  push    r12
0x18006877e  push    r13
0x180068780  push    r14
0x180068782  push    r15
0x180068784  lea     rbp, [rsp-7F0h]
0x18006878c  sub     rsp, 8F0h
0x180068793  mov     rax, cs:__security_cookie
0x18006879a  xor     rax, rsp
0x18006879d  mov     [rbp+820h+var_40], rax
0x1800687a4  mov     rbx, [rbp+820h+arg_20]
0x1800687ab  mov     r14d, r8d
0x1800687ae  mov     rax, [rbp+820h+arg_28]
0x1800687b5  mov     r15d, edx
0x1800687b8  mov     [rsp+920h+var_8E0], rbx
0x1800687bd  mov     r12, rcx
0x1800687c0  mov     [rsp+920h+var_8D8], rax
0x1800687c5  mov     [rsp+920h+var_8D0], r9
0x1800687ca  test    rcx, rcx
0x1800687cd  jz      short loc_18006880A
0x1800687cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800687d6  lea     rdi, WPP_GLOBAL_Control
0x1800687dd  cmp     rcx, rdi
0x1800687e0  jz      short loc_18006884B
0x1800687e2  test    byte ptr [rcx+1Ch], 80h
0x1800687e6  jz      short loc_18006884B
0x1800687e8  cmp     byte ptr [rcx+19h], 6
0x1800687ec  jb      short loc_18006884B
0x1800687ee  mov     rcx, [rcx+10h]
0x1800687f2  test    r8d, r8d
0x1800687f5  mov     r9, r12
0x1800687f8  setnz   al
0x1800687fb  mov     byte ptr [rsp+920h+dwFlags], al
0x1800687ff  mov     dword ptr [rsp+920h+pcchRemaining], edx
0x180068803  call    WPP_SF_SDc
0x180068808  jmp     short loc_18006884B
0x18006880a  mov     rcx, cs:WPP_GLOBAL_Control
0x180068811  lea     rdi, WPP_GLOBAL_Control
0x180068818  cmp     rcx, rdi
0x18006881b  jz      short loc_18006884B
0x18006881d  test    byte ptr [rcx+1Ch], 80h
0x180068821  jz      short loc_18006884B
0x180068823  cmp     byte ptr [rcx+19h], 6
0x180068827  jb      short loc_18006884B
0x180068829  mov     rcx, [rcx+10h]
0x18006882d  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180068834  test    r14d, r14d
0x180068837  mov     edx, 33Bh
0x18006883c  mov     r9d, r15d
0x18006883f  setnz   al
0x180068842  mov     byte ptr [rsp+920h+pcchRemaining], al; pcchRemaining
0x180068846  call    WPP_SF_Dc
0x18006884b  mov     esi, 20Ah
0x180068850  lea     rcx, [rbp+820h+pszDest]; void *
0x180068857  mov     r8d, esi; Size
0x18006885a  xor     edx, edx; Val
0x18006885c  call    memset_0
0x180068861  xor     edx, edx; Val
0x180068863  lea     r8d, [rsi+46h]; Size
0x180068867  lea     rcx, [rsp+920h+FindFileData]; void *
0x18006886c  call    memset_0
0x180068871  mov     r8d, esi; Size
0x180068874  lea     rcx, [rbp+820h+String]; void *
0x18006887b  xor     edx, edx; Val
0x18006887d  or      r13, 0FFFFFFFFFFFFFFFFh
0x180068881  call    memset_0
0x180068886  mov     r8d, esi; Size
0x180068889  lea     rcx, [rbp+820h+Buffer]; void *
0x180068890  xor     edx, edx; Val
0x180068892  call    memset_0
0x180068897  mov     qword ptr [rbx], 0
0x18006889e  mov     esi, 105h
0x1800688a3  test    r14d, r14d
0x1800688a6  jz      loc_180068931
0x1800688ac  mov     edx, esi; uSize
0x1800688ae  lea     rcx, [rbp+820h+Buffer]; lpBuffer
0x1800688b5  call    cs:__imp_GetSystemDirectoryW
0x1800688bb  dec     eax
0x1800688bd  cmp     eax, 0F2h
0x1800688c2  ja      short loc_18006892A
0x1800688c4  lea     r8, aRas; "\\Ras\\"
0x1800688cb  mov     [rsp+920h+dwFlags], 100h; dwFlags
0x1800688d3  mov     edx, esi; cchDest
0x1800688d5  lea     rcx, [rbp+820h+Buffer]; pszDest
0x1800688dc  call    StringCchCatExW
0x1800688e1  mov     ebx, eax
0x1800688e3  test    eax, eax
0x1800688e5  jns     loc_180068980
0x1800688eb  mov     rcx, cs:WPP_GLOBAL_Control
0x1800688f2  cmp     rcx, rdi
0x1800688f5  jz      short loc_180068922
0x1800688f7  test    byte ptr [rcx+1Ch], 80h
0x1800688fb  jz      short loc_180068922
0x1800688fd  cmp     byte ptr [rcx+19h], 2
0x180068901  jb      short loc_180068922
0x180068903  mov     rcx, [rcx+10h]
0x180068907  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x18006890e  mov     edx, 33Ch
0x180068913  mov     r9d, eax
0x180068916  call    WPP_SF_d
0x18006891b  mov     rcx, cs:WPP_GLOBAL_Control
0x180068922  movzx   ebx, bx
0x180068925  jmp     loc_180068DDD
0x18006892a  xor     ebx, ebx
0x18006892c  jmp     loc_180068DD6
0x180068931  mov     r8d, esi
0x180068934  lea     rdx, [rbp+820h+Buffer]
0x18006893b  mov     ecx, 1
0x180068940  call    GetPhonebookDirectory
0x180068945  test    eax, eax
0x180068947  jnz     short loc_180068980
0x180068949  mov     r9d, 26Dh
0x18006894f  mov     ebx, r9d
0x180068952  mov     rcx, cs:WPP_GLOBAL_Control
0x180068959  cmp     rcx, rdi
0x18006895c  jz      loc_180068DDD
0x180068962  test    byte ptr [rcx+1Ch], 80h
0x180068966  jz      loc_180068DDD
0x18006896c  cmp     byte ptr [rcx+19h], 2
0x180068970  jb      loc_180068DDD
0x180068976  mov     edx, 33Dh
0x18006897b  jmp     loc_180068DC6
0x180068980  lea     rcx, aPbk; "*.pbk"
0x180068987  call    cs:__imp_lstrlenW
0x18006898d  mov     ebx, 104h
0x180068992  lea     rcx, [rbp+820h+String]; lpString
0x180068999  sub     ebx, eax
0x18006899b  call    cs:__imp_lstrlenW
0x1800689a1  cmp     eax, ebx
0x1800689a3  jle     short loc_1800689DC
0x1800689a5  mov     r9d, 26Dh
0x1800689ab  mov     ebx, r9d
0x1800689ae  mov     rcx, cs:WPP_GLOBAL_Control
0x1800689b5  cmp     rcx, rdi
0x1800689b8  jz      loc_180068DDD
0x1800689be  test    byte ptr [rcx+1Ch], 80h
0x1800689c2  jz      loc_180068DDD
0x1800689c8  cmp     byte ptr [rcx+19h], 2
0x1800689cc  jb      loc_180068DDD
0x1800689d2  mov     edx, 33Eh
0x1800689d7  jmp     loc_180068DC6
0x1800689dc  lea     rax, aRasphonePbk; "rasphone.pbk"
0x1800689e3  test    r14d, r14d
0x1800689e6  jnz     loc_180068B08
0x1800689ec  mov     [rsp+920h+var_8E8], rax
0x1800689f1  lea     rcx, [rbp+820h+pszDest]; pszDest
0x1800689f8  lea     rax, [rbp+820h+Buffer]
0x1800689ff  xor     r9d, r9d; pcchRemaining
0x180068a02  mov     [rsp+920h+var_8F0], rax
0x180068a07  xor     r8d, r8d; ppszDestEnd
0x180068a0a  lea     rax, aSS_3; "%s%s"
0x180068a11  mov     rdx, rsi; cchDest
0x180068a14  mov     qword ptr [rsp+920h+dwFlags], rax; pszFormat
0x180068a19  mov     dword ptr [rsp+920h+pcchRemaining], 100h; dwFlags
0x180068a21  call    StringCchPrintfExW
0x180068a26  test    eax, eax
0x180068a28  jns     short loc_180068A66
0x180068a2a  movzx   ebx, ax
0x180068a2d  test    ebx, ebx
0x180068a2f  jz      loc_180068DD6
0x180068a35  mov     rcx, cs:WPP_GLOBAL_Control
0x180068a3c  cmp     rcx, rdi
0x180068a3f  jz      loc_180068DDD
0x180068a45  test    byte ptr [rcx+1Ch], 80h
0x180068a49  jz      loc_180068DDD
0x180068a4f  cmp     byte ptr [rcx+19h], 2
0x180068a53  jb      loc_180068DDD
0x180068a59  mov     edx, 33Fh
0x180068a5e  mov     r9d, ebx
0x180068a61  jmp     loc_180068DC6
0x180068a66  mov     rax, [rsp+920h+var_8D8]
0x180068a6b  lea     rcx, [rbp+820h+pszDest]; pszSrc
0x180068a72  mov     r9, [rsp+920h+var_8D0]
0x180068a77  mov     r8d, r15d
0x180068a7a  mov     qword ptr [rsp+920h+dwFlags], rax; __int64
0x180068a7f  mov     rdx, r12
0x180068a82  mov     rax, [rsp+920h+var_8E0]
0x180068a87  mov     [rsp+920h+pcchRemaining], rax; __int64
0x180068a8c  call    DwReadEntryFromSystem
0x180068a91  mov     ebx, eax
0x180068a93  test    eax, eax
0x180068a95  jz      short loc_180068AC9
0x180068a97  mov     rcx, cs:WPP_GLOBAL_Control
0x180068a9e  cmp     rcx, rdi
0x180068aa1  jz      short loc_180068B08
0x180068aa3  test    byte ptr [rcx+1Ch], 80h
0x180068aa7  jz      short loc_180068ADF
0x180068aa9  cmp     byte ptr [rcx+19h], 2
0x180068aad  jb      short loc_180068ADF
0x180068aaf  mov     rcx, [rcx+10h]
0x180068ab3  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180068aba  mov     edx, 340h
0x180068abf  mov     r9d, eax
0x180068ac2  call    WPP_SF_d
0x180068ac7  jmp     short loc_180068AD8
0x180068ac9  mov     rax, [rsp+920h+var_8E0]
0x180068ace  cmp     qword ptr [rax], 0
0x180068ad2  jnz     loc_180068DD6
0x180068ad8  mov     rcx, cs:WPP_GLOBAL_Control
0x180068adf  cmp     rcx, rdi
0x180068ae2  jz      short loc_180068B08
0x180068ae4  test    byte ptr [rcx+1Ch], 80h
0x180068ae8  jz      short loc_180068B08
0x180068aea  cmp     byte ptr [rcx+19h], 2
0x180068aee  jb      short loc_180068B08
0x180068af0  mov     rcx, [rcx+10h]
0x180068af4  lea     r8, WPP_c6c3c1453b9434e492a34eb989dcdbea_Traceguids
0x180068afb  mov     edx, 341h
0x180068b00  mov     r9d, ebx
0x180068b03  call    WPP_SF_d
0x180068b08  lea     rax, aPbk; "*.pbk"
0x180068b0f  xor     r9d, r9d; pcchRemaining
0x180068b12  mov     [rsp+920h+var_8E8], rax
0x180068b17  lea     rcx, [rbp+820h+String]; pszDest
0x180068b1e  lea     rax, [rbp+820h+Buffer]
0x180068b25  xor     r8d, r8d; ppszDestEnd
0x180068b28  mov     [rsp+920h+var_8F0], rax
0x180068b2d  mov     rdx, rsi; cchDest
0x180068b30  lea     rax, aSS_3; "%s%s"
0x180068b37  mov     qword ptr [rsp+920h+dwFlags], rax; pszFormat
0x180068b3c  mov     dword ptr [rsp+920h+pcchRemaining], 100h; dwFlags
0x180068b44  call    StringCchPrintfExW
0x180068b49  test    eax, eax
0x180068b4b  jns     short loc_180068B86
0x180068b4d  movzx   ebx, ax
0x180068b50  test    ebx, ebx
0x180068b52  jz      loc_180068DD6
0x180068b58  mov     rcx, cs:WPP_GLOBAL_Control
0x180068b5f  cmp     rcx, rdi
0x180068b62  jz      loc_180068DDD
0x180068b68  test    byte ptr [rcx+1Ch], 80h
0x180068b6c  jz      loc_180068DDD
0x180068b72  cmp     byte ptr [rcx+19h], 2
0x180068b76  jb      loc_180068DDD
0x180068b7c  mov     edx, 342h
0x180068b81  jmp     loc_180068A5E
0x180068b86  lea     rdx, [rsp+920h+FindFileData]; lpFindFileData
0x180068b8b  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x180068b8f  jnz     short loc_180068BE5
0x180068b91  lea     rcx, [rbp+820h+String]; lpFileName
0x180068b98  call    cs:__imp_FindFirstFileW
0x180068b9e  mov     r13, rax
0x180068ba1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180068ba5  jnz     short loc_180068BF6
0x180068ba7  call    cs:__imp_GetLastError
0x180068bad  mov     ebx, eax
0x180068baf  test    eax, eax
0x180068bb1  jz      loc_180068DD6
0x180068bb7  mov     rcx, cs:WPP_GLOBAL_Control
0x180068bbe  cmp     rcx, rdi
0x180068bc1  jz      loc_180068DDD
0x180068bc7  test    byte ptr [rcx+1Ch], 80h
0x180068bcb  jz      loc_180068DDD
0x180068bd1  cmp     byte ptr [rcx+19h], 2
0x180068bd5  jb      loc_180068DDD
0x180068bdb  mov     edx, 343h
0x180068be0  jmp     loc_180068DC3
0x180068be5  mov     rcx, r13; hFindFile
0x180068be8  call    cs:__imp_FindNextFileW
0x180068bee  test    eax, eax
0x180068bf0  jz      loc_180068D9A
0x180068bf6  test    byte ptr [rsp+920h+FindFileData.dwFileAttributes], 10h
0x180068bfb  jnz     short loc_180068B86
0x180068bfd  lea     rcx, [rbp+820h+Buffer]; lpString
0x180068c04  call    cs:__imp_lstrlenW
0x180068c0a  mov     ebx, 104h
0x180068c0f  lea     rcx, [rbp+820h+FindFileData.cFileName]; lpString
0x180068c13  sub     ebx, eax
0x180068c15  call    cs:__imp_lstrlenW
0x180068c1b  cmp     eax, ebx
0x180068c1d  jg      loc_180068D72
0x180068c23  lea     rax, [rbp+820h+FindFileData.cFileName]
0x180068c27  xor     r9d, r9d; pcchRemaining
0x180068c2a  mov     [rsp+920h+var_8E8], rax
0x180068c2f  lea     rcx, [rbp+820h+String]; pszDest
0x180068c36  lea     rax, [rbp+820h+Buffer]
0x180068c3d  xor     r8d, r8d; ppszDestEnd
0x180068c40  mov     [rsp+920h+var_8F0], rax
0x180068c45  mov     rdx, rsi; cchDest
0x180068c48  lea     rax, aSS_3; "%s%s"
0x180068c4f  mov     qword ptr [rsp+920h+dwFlags], rax; pszFormat
0x180068c54  mov     dword ptr [rsp+920h+pcchRemaining], 100h; dwFlags
0x180068c5c  call    StringCchPrintfExW
0x180068c61  test    eax, eax
0x180068c63  js      loc_180068D41
0x180068c69  test    r14d, r14d
0x180068c6c  jnz     short loc_180068C82
0x180068c6e  lea     rdx, aRasphonePbk; "rasphone.pbk"
0x180068c75  lea     rcx, [rbp+820h+FindFileData.cFileName]; lpString1
0x180068c79  call    CompareStringWrapW
0x180068c7e  test    eax, eax
0x180068c80  jmp     short loc_180068CF2
0x180068c82  lea     rcx, [rbp+820h+String]; lpString
0x180068c89  call    cs:__imp_lstrlenW
0x180068c8f  movsxd  rcx, eax
0x180068c92  lea     rax, [rbp+820h+String]
0x180068c99  add     rcx, rcx
  ... truncated ...
```
