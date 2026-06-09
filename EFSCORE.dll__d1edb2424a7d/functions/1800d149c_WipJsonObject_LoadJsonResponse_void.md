# WipJsonObject::LoadJsonResponse(void *)

- ea: `0x1800d149c`
- end: `0x1800d184c`
- name: `?LoadJsonResponse@WipJsonObject@@QEAAJPEAX@Z`
- size: `944`
- prototype: `int(WipJsonObject *__hidden this, void *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800cfe1c`

## callees

- `0x1800124d8`
- `0x18004844c`
- `0x180048b80`
- `0x180063698`
- `0x180063730`
- `0x1800637e8`
- `0x1800d12a4`
- `0x1800d149c`
- `0x1800d1a6c`
- `0x1800dddf0`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d1550`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d169e`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d1550`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800d169e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d153f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d168b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d173f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d1753`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d17e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d17fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d153f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d168b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d173f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d1753`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d17e3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800d17fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d174d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d1761`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d17f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d180a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d174d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d1761`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d17f1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800d180a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d14fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d15fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1704`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d14fe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1592`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d15fc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d1704`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800d15ef`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800d16fa`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800d15ef`
- `api-ms-win-core-string-l1-1-0!MultiByteToWideChar` at `0x1800d16fa`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800d14f4`
- `WINHTTP!WinHttpQueryDataAvailable` at `0x1800d14f4`
- `WINHTTP!WinHttpReadData` at `0x1800d1588`
- `WINHTTP!WinHttpReadData` at `0x1800d1588`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WipJsonObject::LoadJsonResponse(WipJsonObject *this, void *a2)
{
  signed int LastError; // eax
  unsigned int v5; // ebx
  int v6; // r8d
  __int64 v7; // rdx
  unsigned int v8; // ebx
  HANDLE ProcessHeap; // rax
  CHAR *v10; // rax
  CHAR *v11; // r14
  signed int v12; // eax
  WCHAR *v13; // rsi
  unsigned int v14; // eax
  int v15; // ecx
  __int64 cchWideChar; // r15
  signed int v17; // eax
  HANDLE v18; // rax
  WCHAR *v19; // rax
  int v20; // r8d
  signed int v21; // eax
  __int64 v22; // rax
  HANDLE v23; // rax
  HANDLE v24; // rax
  int v25; // ecx
  HANDLE v26; // rax
  HANDLE v27; // rax
  char lpWideCharStr; // [rsp+20h] [rbp-88h]
  char lpWideCharStra; // [rsp+20h] [rbp-88h]
  char lpWideCharStrb; // [rsp+20h] [rbp-88h]
  SIZE_T dwBytes; // [rsp+40h] [rbp-68h] BYREF
  CHAR *v33; // [rsp+48h] [rbp-60h]
  WCHAR *v34; // [rsp+50h] [rbp-58h]
  _WORD v35[8]; // [rsp+58h] [rbp-50h] BYREF
  __int64 v36; // [rsp+68h] [rbp-40h]
  __int64 v37; // [rsp+70h] [rbp-38h]

  dwBytes = 0;
  v37 = 7;
  v36 = 0;
  v35[0] = 0;
  while ( 1 )
  {
    if ( !WinHttpQueryDataAvailable(a2, (LPDWORD)&dwBytes + 1) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError > 0 )
        v5 = (unsigned __int16)LastError | 0x80070000;
      lpWideCharStr = 106;
      v6 = v5;
      goto LABEL_6;
    }
    v8 = HIDWORD(dwBytes) + 1;
    ProcessHeap = GetProcessHeap();
    v10 = (CHAR *)HeapAlloc(ProcessHeap, 8u, v8);
    v11 = v10;
    v33 = v10;
    if ( !v10 )
    {
      v5 = -2147024882;
      lpWideCharStr = 110;
      v6 = -2147024882;
LABEL_6:
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v6, 47, lpWideCharStr);
      goto LABEL_30;
    }
    if ( !WinHttpReadData(a2, v10, HIDWORD(dwBytes), (LPDWORD)&dwBytes + 1) )
    {
      v12 = GetLastError();
      v5 = v12;
      if ( v12 > 0 )
        v5 = (unsigned __int16)v12 | 0x80070000;
      lpWideCharStra = 117;
LABEL_13:
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v5, 47, lpWideCharStra);
      v13 = 0;
      goto LABEL_28;
    }
    v11[HIDWORD(dwBytes)] = 0;
    v14 = MultiByteToWideChar(0xFDE9u, 0, v11, -1, 0, 0);
    cchWideChar = v14;
    if ( !v14 )
    {
      v17 = GetLastError();
      v5 = v17;
      if ( v17 > 0 )
        v5 = (unsigned __int16)v17 | 0x80070000;
      lpWideCharStra = -122;
      goto LABEL_13;
    }
    fnEfsLogTrace1Strings(v15, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 47, 137);
    v5 = ULongLongToULong(2 * cchWideChar, (unsigned int *)&dwBytes);
    v13 = 0;
    if ( (int)fnEfsLogTrace1String1Dword(
                g_hPublisher,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT,
                (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
                (unsigned int)&sourceString,
                v5,
                47,
                137) < 0 )
      goto LABEL_28;
    v18 = GetProcessHeap();
    v19 = (WCHAR *)HeapAlloc(v18, 8u, (unsigned int)dwBytes);
    v13 = v19;
    v34 = v19;
    if ( !v19 )
    {
      v5 = -2147024882;
      lpWideCharStrb = -116;
      v20 = -2147024882;
      goto LABEL_21;
    }
    if ( !MultiByteToWideChar(0xFDE9u, 0, v11, -1, v19, cchWideChar) )
      break;
    try
    {
      v22 = std::char_traits<unsigned short>::length(v13);
      std::wstring::append(v35, v13, v22);
    }
    catch ( std::bad_alloc )
    {
      LODWORD(dwBytes) = -2147024882;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147024882, 47, 159);
      v13 = v34;
      v11 = v33;
      v5 = dwBytes;
      goto LABEL_28;
    }
    catch ( exception )
    {
      LODWORD(dwBytes) = -2147418113;
      fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, -2147418113, 47, 163);
      v13 = v34;
      v11 = v33;
      v5 = dwBytes;
      goto LABEL_28;
    }
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v11);
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v13);
    if ( !HIDWORD(dwBytes) )
    {
      fnEfsLogTrace1Strings(v25, (unsigned int)EFS_TRACE_START_EVENT, (unsigned int)&sourceString, 47, 171);
      v5 = WipJsonObject::Initialize(this, v35);
      fnEfsLogTrace1String1Dword(
        g_hPublisher,
        (unsigned int)EFS_TRACE_COMPLETE_EVENT,
        (unsigned int)EFS_TRACE_COMPLETE_EVENT_ERROR,
        (unsigned int)&sourceString,
        v5,
        47,
        171);
      goto LABEL_30;
    }
  }
  v21 = GetLastError();
  v5 = v21;
  if ( v21 > 0 )
    v5 = (unsigned __int16)v21 | 0x80070000;
  lpWideCharStrb = -106;
  v20 = v5;
LABEL_21:
  fnEfsLogTrace1(g_hPublisher, (unsigned int)EFS_TRACE_ERROR, v20, 47, lpWideCharStrb);
LABEL_28:
  v26 = GetProcessHeap();
  HeapFree(v26, 0, v11);
  if ( v13 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v13);
  }
LABEL_30:
  LOBYTE(v7) = 1;
  std::wstring::_Tidy(v35, v7, 0);
  return v5;
}

```

## disassembly

```asm
0x1800d149c  mov     r11, rsp
0x1800d149f  mov     [r11+18h], rbx
0x1800d14a3  mov     [r11+20h], rsi
0x1800d14a7  push    rdi
0x1800d14a8  push    r12
0x1800d14aa  push    r13
0x1800d14ac  push    r14
0x1800d14ae  push    r15
0x1800d14b0  sub     rsp, 80h
0x1800d14b7  mov     rax, cs:__security_cookie
0x1800d14be  xor     rax, rsp
0x1800d14c1  mov     [rsp+0A8h+var_30], rax
0x1800d14c6  mov     r12, rdx
0x1800d14c9  mov     r13, rcx
0x1800d14cc  xor     edi, edi
0x1800d14ce  mov     dword ptr [rsp+0A8h+dwBytes+4], edi
0x1800d14d2  mov     dword ptr [rsp+0A8h+dwBytes], edi
0x1800d14d6  mov     qword ptr [r11-38h], 7
0x1800d14de  mov     [r11-40h], rdi
0x1800d14e2  mov     [rsp+0A8h+var_50], di
0x1800d14e7  mov     esi, 2Fh ; '/'
0x1800d14ec  lea     rdx, [rsp+0A8h+dwBytes+4]; lpdwNumberOfBytesAvailable
0x1800d14f1  mov     rcx, r12; hRequest
0x1800d14f4  call    cs:__imp_WinHttpQueryDataAvailable
0x1800d14fa  test    eax, eax
0x1800d14fc  jnz     short loc_1800D1539
0x1800d14fe  call    cs:__imp_GetLastError
0x1800d1504  mov     ebx, eax
0x1800d1506  test    eax, eax
0x1800d1508  jle     short loc_1800D1513
0x1800d150a  movzx   ebx, ax
0x1800d150d  or      ebx, 80070000h
0x1800d1513  mov     dword ptr [rsp+0A8h+lpWideCharStr], 16Ah
0x1800d151b  mov     r8d, ebx
0x1800d151e  mov     r9d, esi
0x1800d1521  lea     rdx, EFS_TRACE_ERROR
0x1800d1528  mov     rcx, cs:g_hPublisher
0x1800d152f  call    fnEfsLogTrace1
0x1800d1534  jmp     loc_1800D1811
0x1800d1539  mov     ebx, dword ptr [rsp+0A8h+dwBytes+4]
0x1800d153d  inc     ebx
0x1800d153f  call    cs:__imp_GetProcessHeap
0x1800d1545  mov     r8d, ebx; dwBytes
0x1800d1548  mov     edx, 8; dwFlags
0x1800d154d  mov     rcx, rax; hHeap
0x1800d1550  call    cs:__imp_HeapAlloc
0x1800d1556  mov     r14, rax
0x1800d1559  mov     [rsp+0A8h+var_60], rax
0x1800d155e  test    rax, rax
0x1800d1561  jnz     short loc_1800D1578
0x1800d1563  mov     ebx, 8007000Eh
0x1800d1568  mov     dword ptr [rsp+0A8h+lpWideCharStr], 16Eh
0x1800d1570  mov     r8d, 8007000Eh
0x1800d1576  jmp     short loc_1800D151E
0x1800d1578  lea     r9, [rsp+0A8h+dwBytes+4]; lpdwNumberOfBytesRead
0x1800d157d  mov     r8d, dword ptr [rsp+0A8h+dwBytes+4]; dwNumberOfBytesToRead
0x1800d1582  mov     rdx, r14; lpBuffer
0x1800d1585  mov     rcx, r12; hRequest
0x1800d1588  call    cs:__imp_WinHttpReadData
0x1800d158e  test    eax, eax
0x1800d1590  jnz     short loc_1800D15D0
0x1800d1592  call    cs:__imp_GetLastError
0x1800d1598  mov     ebx, eax
0x1800d159a  test    eax, eax
0x1800d159c  jle     short loc_1800D15A7
0x1800d159e  movzx   ebx, ax
0x1800d15a1  or      ebx, 80070000h
0x1800d15a7  mov     dword ptr [rsp+0A8h+lpWideCharStr], 175h
0x1800d15af  mov     r9d, esi
0x1800d15b2  mov     r8d, ebx
0x1800d15b5  lea     rdx, EFS_TRACE_ERROR
0x1800d15bc  mov     rcx, cs:g_hPublisher
0x1800d15c3  call    fnEfsLogTrace1
0x1800d15c8  mov     rsi, rdi
0x1800d15cb  jmp     loc_1800D17E3
0x1800d15d0  mov     eax, dword ptr [rsp+0A8h+dwBytes+4]
0x1800d15d4  mov     [rax+r14], dil
0x1800d15d8  mov     [rsp+0A8h+cchWideChar], edi; cchWideChar
0x1800d15dc  mov     [rsp+0A8h+lpWideCharStr], rdi; lpWideCharStr
0x1800d15e1  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800d15e5  mov     r8, r14; lpMultiByteStr
0x1800d15e8  xor     edx, edx; dwFlags
0x1800d15ea  mov     ecx, 0FDE9h; CodePage
0x1800d15ef  call    cs:__imp_MultiByteToWideChar
0x1800d15f5  mov     r15d, eax
0x1800d15f8  test    eax, eax
0x1800d15fa  jnz     short loc_1800D161B
0x1800d15fc  call    cs:__imp_GetLastError
0x1800d1602  mov     ebx, eax
0x1800d1604  test    eax, eax
0x1800d1606  jle     short loc_1800D1611
0x1800d1608  movzx   ebx, ax
0x1800d160b  or      ebx, 80070000h
0x1800d1611  mov     dword ptr [rsp+0A8h+lpWideCharStr], 186h
0x1800d1619  jmp     short loc_1800D15AF
0x1800d161b  mov     dword ptr [rsp+0A8h+lpWideCharStr], 189h
0x1800d1623  mov     r9d, esi
0x1800d1626  lea     r8, sourceString
0x1800d162d  lea     rdx, EFS_TRACE_START_EVENT
0x1800d1634  call    fnEfsLogTrace1Strings
0x1800d1639  mov     rcx, r15
0x1800d163c  add     rcx, rcx; unsigned __int64
0x1800d163f  lea     rdx, [rsp+0A8h+dwBytes]; unsigned int *
0x1800d1644  call    ?ULongLongToULong@@YAJ_KPEAK@Z; ULongLongToULong(unsigned __int64,ulong *)
0x1800d1649  mov     ebx, eax
0x1800d164b  mov     rsi, rdi
0x1800d164e  mov     [rsp+0A8h+var_78], 189h
0x1800d1656  mov     [rsp+0A8h+cchWideChar], 2Fh ; '/'
0x1800d165e  mov     dword ptr [rsp+0A8h+lpWideCharStr], eax
0x1800d1662  lea     r9, sourceString
0x1800d1669  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800d1670  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800d1677  mov     rcx, cs:g_hPublisher
0x1800d167e  call    fnEfsLogTrace1String1Dword
0x1800d1683  test    eax, eax
0x1800d1685  js      loc_1800D17E3
0x1800d168b  call    cs:__imp_GetProcessHeap
0x1800d1691  mov     r8d, dword ptr [rsp+0A8h+dwBytes]; dwBytes
0x1800d1696  mov     edx, 8; dwFlags
0x1800d169b  mov     rcx, rax; hHeap
0x1800d169e  call    cs:__imp_HeapAlloc
0x1800d16a4  mov     rsi, rax
0x1800d16a7  mov     [rsp+0A8h+var_58], rax
0x1800d16ac  test    rax, rax
0x1800d16af  jnz     short loc_1800D16E2
0x1800d16b1  mov     ebx, 8007000Eh
0x1800d16b6  mov     dword ptr [rsp+0A8h+lpWideCharStr], 18Ch
0x1800d16be  mov     r8d, 8007000Eh
0x1800d16c4  mov     r9d, 2Fh ; '/'
0x1800d16ca  lea     rdx, EFS_TRACE_ERROR
0x1800d16d1  mov     rcx, cs:g_hPublisher
0x1800d16d8  call    fnEfsLogTrace1
0x1800d16dd  jmp     loc_1800D17E3
0x1800d16e2  mov     [rsp+0A8h+cchWideChar], r15d; cchWideChar
0x1800d16e7  mov     [rsp+0A8h+lpWideCharStr], rsi; lpWideCharStr
0x1800d16ec  or      r9d, 0FFFFFFFFh; cbMultiByte
0x1800d16f0  mov     r8, r14; lpMultiByteStr
0x1800d16f3  xor     edx, edx; dwFlags
0x1800d16f5  mov     ecx, 0FDE9h; CodePage
0x1800d16fa  call    cs:__imp_MultiByteToWideChar
0x1800d1700  test    eax, eax
0x1800d1702  jnz     short loc_1800D1726
0x1800d1704  call    cs:__imp_GetLastError
0x1800d170a  mov     ebx, eax
0x1800d170c  test    eax, eax
0x1800d170e  jle     short loc_1800D1719
0x1800d1710  movzx   ebx, ax
0x1800d1713  or      ebx, 80070000h
0x1800d1719  mov     dword ptr [rsp+0A8h+lpWideCharStr], 196h
0x1800d1721  mov     r8d, ebx
0x1800d1724  jmp     short loc_1800D16C4
0x1800d1726  mov     rcx, rsi
0x1800d1729  call    ?length@?$char_traits@G@std@@SA_KPEBG@Z; std::char_traits<ushort>::length(ushort const *)
0x1800d172e  mov     r8, rax
0x1800d1731  mov     rdx, rsi
0x1800d1734  lea     rcx, [rsp+0A8h+var_50]
0x1800d1739  call    ?append@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::append(ushort const *,unsigned __int64)
0x1800d173e  nop
0x1800d173f  call    cs:__imp_GetProcessHeap
0x1800d1745  mov     rcx, rax; hHeap
0x1800d1748  mov     r8, r14; lpMem
0x1800d174b  xor     edx, edx; dwFlags
0x1800d174d  call    cs:__imp_HeapFree
0x1800d1753  call    cs:__imp_GetProcessHeap
0x1800d1759  mov     rcx, rax; hHeap
0x1800d175c  mov     r8, rsi; lpMem
0x1800d175f  xor     edx, edx; dwFlags
0x1800d1761  call    cs:__imp_HeapFree
0x1800d1767  cmp     dword ptr [rsp+0A8h+dwBytes+4], edi
0x1800d176b  ja      loc_1800D14E7
0x1800d1771  mov     edi, 1ABh
0x1800d1776  mov     dword ptr [rsp+0A8h+lpWideCharStr], edi
0x1800d177a  mov     esi, 2Fh ; '/'
0x1800d177f  mov     r9d, esi
0x1800d1782  lea     r8, sourceString
0x1800d1789  lea     rdx, EFS_TRACE_START_EVENT
0x1800d1790  call    fnEfsLogTrace1Strings
0x1800d1795  lea     rdx, [rsp+0A8h+var_50]
0x1800d179a  mov     rcx, r13
0x1800d179d  call    ?Initialize@WipJsonObject@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; WipJsonObject::Initialize(std::wstring const &)
0x1800d17a2  mov     ebx, eax
0x1800d17a4  mov     [rsp+0A8h+var_78], edi
0x1800d17a8  mov     [rsp+0A8h+cchWideChar], esi
0x1800d17ac  mov     dword ptr [rsp+0A8h+lpWideCharStr], eax
0x1800d17b0  lea     r9, sourceString
0x1800d17b7  lea     r8, EFS_TRACE_COMPLETE_EVENT_ERROR
0x1800d17be  lea     rdx, EFS_TRACE_COMPLETE_EVENT
0x1800d17c5  mov     rcx, cs:g_hPublisher
0x1800d17cc  call    fnEfsLogTrace1String1Dword
0x1800d17d1  jmp     short loc_1800D1811
0x1800d17d3  jmp     short $+2
0x1800d17d5  mov     rsi, [rsp+0A8h+var_58]
0x1800d17da  mov     r14, [rsp+0A8h+var_60]
0x1800d17df  mov     ebx, dword ptr [rsp+0A8h+dwBytes]
0x1800d17e3  call    cs:__imp_GetProcessHeap
0x1800d17e9  mov     rcx, rax; hHeap
0x1800d17ec  mov     r8, r14; lpMem
0x1800d17ef  xor     edx, edx; dwFlags
0x1800d17f1  call    cs:__imp_HeapFree
0x1800d17f7  test    rsi, rsi
0x1800d17fa  jz      short loc_1800D1811
0x1800d17fc  call    cs:__imp_GetProcessHeap
0x1800d1802  mov     rcx, rax; hHeap
0x1800d1805  mov     r8, rsi; lpMem
0x1800d1808  xor     edx, edx; dwFlags
0x1800d180a  call    cs:__imp_HeapFree
0x1800d1810  nop
0x1800d1811  xor     r8d, r8d
0x1800d1814  mov     dl, 1
0x1800d1816  lea     rcx, [rsp+0A8h+var_50]
0x1800d181b  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800d1820  mov     eax, ebx
0x1800d1822  mov     rcx, [rsp+0A8h+var_30]
0x1800d1827  xor     rcx, rsp; StackCookie
0x1800d182a  call    __security_check_cookie
0x1800d182f  lea     r11, [rsp+0A8h+var_28]
0x1800d1837  mov     rbx, [r11+40h]
0x1800d183b  mov     rsi, [r11+48h]
0x1800d183f  mov     rsp, r11
0x1800d1842  pop     r15
0x1800d1844  pop     r14
0x1800d1846  pop     r13
0x1800d1848  pop     r12
0x1800d184a  pop     rdi
0x1800d184b  retn
```
