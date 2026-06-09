# OpenFontFile

- ea: `0x1800220ec`
- end: `0x180022533`
- name: `OpenFontFile`
- size: `1095`
- prototype: `__int64 __fastcall(HANDLE hPrinter)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x1800211b8`

## callees

- `0x1800220ec`
- `0x18002253c`
- `0x180033504`
- `0x1800487e0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022243`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022336`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800224e9`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022518`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022243`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022336`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x1800224e9`
- `api-ms-win-crt-private-l1-1-0!wcsrchr` at `0x180022518`
- `WINSPOOL!GetPrinterDataW` at `0x180022314`
- `WINSPOOL!GetPrinterDataW` at `0x180022314`
- `WINSPOOL!GetPrinterDriverW` at `0x180022184`
- `WINSPOOL!GetPrinterDriverW` at `0x1800221d6`
- `WINSPOOL!GetPrinterDriverW` at `0x180022184`
- `WINSPOOL!GetPrinterDriverW` at `0x1800221d6`
- `KERNEL32!MapViewOfFile` at `0x1800223e5`
- `KERNEL32!MapViewOfFile` at `0x1800223e5`
- `KERNEL32!CloseHandle` at `0x1800223f1`
- `KERNEL32!CloseHandle` at `0x1800223ff`
- `KERNEL32!CloseHandle` at `0x180022427`
- `KERNEL32!CloseHandle` at `0x1800223f1`
- `KERNEL32!CloseHandle` at `0x1800223ff`
- `KERNEL32!CloseHandle` at `0x180022427`
- `KERNEL32!CreateFileW` at `0x18002238c`
- `KERNEL32!CreateFileW` at `0x18002238c`
- `KERNEL32!GetLastError` at `0x180022192`
- `KERNEL32!GetLastError` at `0x180022192`
- `KERNEL32!LocalFree` at `0x180022233`
- `KERNEL32!LocalFree` at `0x180022286`
- `KERNEL32!LocalFree` at `0x180022233`
- `KERNEL32!LocalFree` at `0x180022286`
- `KERNEL32!LocalAlloc` at `0x180022130`
- `KERNEL32!LocalAlloc` at `0x1800221a7`
- `KERNEL32!LocalAlloc` at `0x180022130`
- `KERNEL32!LocalAlloc` at `0x1800221a7`
- `KERNEL32!GetFileSize` at `0x1800223a0`
- `KERNEL32!GetFileSize` at `0x1800223a0`
- `KERNEL32!CreateFileMappingW` at `0x1800223c5`
- `KERNEL32!CreateFileMappingW` at `0x1800223c5`

## pseudocode

```c
_QWORD *__fastcall OpenFontFile(HANDLE hPrinter)
{
  _QWORD *result; // rax
  __int64 v3; // rbx
  LPVOID *v4; // rsi
  BYTE *v5; // rax
  BYTE *v6; // rdi
  _WORD *v7; // r8
  __int64 v8; // r15
  _WORD *v9; // rax
  __int64 v10; // rcx
  __int64 v11; // rdx
  _WORD *v12; // rcx
  wchar_t *v13; // rax
  __int64 v14; // r8
  const wchar_t *v15; // rcx
  bool v16; // zf
  __int64 v17; // rax
  _WORD *v18; // r8
  _WORD *v19; // rdx
  DWORD PrinterDataW; // eax
  __int64 v21; // rdi
  wchar_t *v22; // rax
  BYTE *v23; // rax
  HANDLE FileW; // rax
  HANDLE FileMappingW; // rax
  void *v26; // r14
  _DWORD *v27; // rax
  _DWORD *v28; // rcx
  __int64 v29; // r8
  unsigned __int64 v30; // rdx
  _WORD *v31; // rax
  __int64 v32; // rdx
  wchar_t *v33; // rax
  wchar_t *v34; // rax
  DWORD FileSize; // [rsp+40h] [rbp-C0h] BYREF
  DWORD pcbNeeded; // [rsp+44h] [rbp-BCh] BYREF
  DWORD pType; // [rsp+48h] [rbp-B8h] BYREF
  wchar_t pData[264]; // [rsp+50h] [rbp-B0h] BYREF

  FileSize = 0;
  pType = 0;
  result = LocalAlloc(0, 0x258u);
  v3 = (__int64)result;
  if ( result )
  {
    v4 = (LPVOID *)(result + 72);
    *(_DWORD *)result = 1718514793;
    result[1] = hPrinter;
    result[2] = 0;
    *((_DWORD *)result + 143) = 0;
    result[72] = 0;
    pcbNeeded = 0;
    if ( GetPrinterDriverW(hPrinter, 0, 3u, 0, 0, &pcbNeeded) )
      goto LABEL_13;
    if ( GetLastError() != 122 )
      goto LABEL_13;
    v5 = (BYTE *)LocalAlloc(0, pcbNeeded);
    v6 = v5;
    if ( !v5 )
      goto LABEL_13;
    if ( !GetPrinterDriverW(hPrinter, 0, 3u, v5, pcbNeeded, &pcbNeeded) )
    {
      LocalFree(v6);
      goto LABEL_13;
    }
    v7 = (_WORD *)*((_QWORD *)v6 + 3);
    v8 = 2147483646;
    v9 = (_WORD *)(v3 + 24);
    v10 = 2147483646;
    v11 = 260;
    do
    {
      if ( !v10 )
        break;
      if ( !*v7 )
        break;
      *v9++ = *v7++;
      --v10;
      --v11;
    }
    while ( v11 );
    v12 = v9 - 1;
    if ( v11 )
      v12 = v9;
    *v12 = 0;
    LocalFree(v6);
    v13 = wcsrchr((const wchar_t *)(v3 + 24), 0x5Cu);
    if ( !v13 )
      goto LABEL_13;
    *v13 = 0;
    v34 = wcsrchr((const wchar_t *)(v3 + 24), 0x5Cu);
    if ( !v34 )
      goto LABEL_13;
    *v34 = 0;
    v33 = wcsrchr((const wchar_t *)(v3 + 24), 0x5Cu);
    if ( !v33 )
      goto LABEL_13;
    *v33 = 0;
    v32 = 260;
    v31 = (_WORD *)(v3 + 24);
    do
    {
      if ( !*v31 )
        break;
      ++v31;
      --v32;
    }
    while ( v32 );
    v14 = (260 - v32) & -(__int64)(v32 != 0);
    if ( v32 )
    {
      v15 = L"\\unifont\\";
      v17 = 260 - v14;
      v16 = v14 == 260;
      v18 = (_WORD *)(v3 + 24 + 2 * v14);
      if ( !v16 )
      {
        do
        {
          if ( !v8 )
            break;
          if ( !*v15 )
            break;
          *v18++ = *v15++;
          --v8;
          --v17;
        }
        while ( v17 );
      }
      v19 = v18 - 1;
      if ( v17 )
        v19 = v18;
      *v19 = 0;
    }
    FileSize = 520;
    PrinterDataW = GetPrinterDataW(hPrinter, (LPWSTR)L"ExternalFontFile", &pType, (LPBYTE)pData, 0x208u, &FileSize);
    if ( PrinterDataW != 234 )
    {
      if ( PrinterDataW )
        goto LABEL_13;
    }
    v21 = 0;
    v22 = wcsrchr(pData, 0x5Cu);
    if ( v22 )
      v23 = (BYTE *)(v22 + 1);
    else
      v23 = (BYTE *)pData;
    StringCchCatW((STRSAFE_LPWSTR)(v3 + 24), 0x104u, (STRSAFE_LPCWSTR)v23);
    if ( !v4 )
      goto LABEL_33;
    FileW = CreateFileW((LPCWSTR)(v3 + 24), 0x80000000, 1u, 0, 3u, 0x100080u, 0);
    v21 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
LABEL_34:
      *v4 = 0;
      goto LABEL_35;
    }
    FileSize = GetFileSize(FileW, 0);
    if ( FileSize == -1
      || (FileMappingW = CreateFileMappingW((HANDLE)v21, 0, 2u, 0, 0, 0), (v26 = FileMappingW) == 0)
      || (*v4 = MapViewOfFile(FileMappingW, 4u, 0, 0, 0), CloseHandle(v26), !*v4) )
    {
LABEL_33:
      CloseHandle((HANDLE)v21);
      v21 = -1;
      if ( v4 )
        goto LABEL_34;
    }
LABEL_35:
    v27 = *v4;
    *(_QWORD *)(v3 + 544) = *v4;
    if ( v27 )
    {
      CloseHandle((HANDLE)v21);
      v28 = *v4;
      *(_QWORD *)(v3 + 552) = *v4;
      if ( FileSize >= 0x30 && *v28 == 826689109 && v28[1] == 65537 && v28[2] == 48 )
      {
        v29 = (unsigned int)v28[6];
        if ( !(_DWORD)v29 )
        {
LABEL_45:
          *(_DWORD *)(v3 + 568) = 0;
          *(_DWORD *)(v3 + 572) = 1;
          *(_QWORD *)(v3 + 584) = 0;
          *(_DWORD *)(v3 + 592) = 0;
          return (_QWORD *)v3;
        }
        v30 = 36LL * (unsigned int)v28[3];
        if ( v30 <= 0xFFFFFFFF && (int)v30 + (int)v29 >= (unsigned int)v30 && FileSize >= (int)v30 + (int)v29 )
        {
          *(_QWORD *)(v3 + 560) = (char *)v28 + v29;
          goto LABEL_45;
        }
      }
    }
LABEL_13:
    FICloseFontFile((HLOCAL)v3);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800220ec  push    rbp
0x1800220ee  push    rbx
0x1800220ef  push    rsi
0x1800220f0  push    rdi
0x1800220f1  push    r12
0x1800220f3  push    r13
0x1800220f5  push    r14
0x1800220f7  push    r15
0x1800220f9  lea     rbp, [rsp-178h]
0x180022101  sub     rsp, 278h
0x180022108  mov     rax, cs:__security_cookie
0x18002210f  xor     rax, rsp
0x180022112  mov     [rbp+1B0h+var_50], rax
0x180022119  mov     r12, rcx
0x18002211c  xor     r13d, r13d
0x18002211f  xor     ecx, ecx; uFlags
0x180022121  mov     [rsp+2B0h+var_270], r13d
0x180022126  mov     edx, 258h; uBytes
0x18002212b  mov     [rsp+2B0h+pType], r13d
0x180022130  call    cs:__imp_LocalAlloc
0x180022136  mov     rbx, rax
0x180022139  test    rax, rax
0x18002213c  jz      loc_18002250A
0x180022142  lea     rsi, [rax+240h]
0x180022149  mov     dword ptr [rax], 666E7469h
0x18002214f  mov     [rax+8], r12
0x180022153  lea     r14d, [r13+3]
0x180022157  mov     [rax+10h], r13
0x18002215b  xor     r9d, r9d; pDriverInfo
0x18002215e  mov     [rax+23Ch], r13d
0x180022165  mov     r8d, r14d; Level
0x180022168  lea     rax, [rsp+2B0h+var_26C]
0x18002216d  mov     [rsi], r13
0x180022170  mov     [rsp+2B0h+pcbNeeded], rax; pcbNeeded
0x180022175  xor     edx, edx; pEnvironment
0x180022177  mov     rcx, r12; hPrinter
0x18002217a  mov     [rsp+2B0h+cbBuf], r13d; cbBuf
0x18002217f  mov     [rsp+2B0h+var_26C], r13d
0x180022184  call    cs:__imp_GetPrinterDriverW
0x18002218a  test    eax, eax
0x18002218c  jnz     loc_180022252
0x180022192  call    cs:__imp_GetLastError
0x180022198  cmp     eax, 7Ah ; 'z'
0x18002219b  jnz     loc_180022252
0x1800221a1  mov     edx, [rsp+2B0h+var_26C]; uBytes
0x1800221a5  xor     ecx, ecx; uFlags
0x1800221a7  call    cs:__imp_LocalAlloc
0x1800221ad  mov     rdi, rax
0x1800221b0  test    rax, rax
0x1800221b3  jz      loc_180022252
0x1800221b9  lea     rax, [rsp+2B0h+var_26C]
0x1800221be  mov     r9, rdi; pDriverInfo
0x1800221c1  mov     [rsp+2B0h+pcbNeeded], rax; pcbNeeded
0x1800221c6  mov     r8d, r14d; Level
0x1800221c9  mov     eax, [rsp+2B0h+var_26C]
0x1800221cd  xor     edx, edx; pEnvironment
0x1800221cf  mov     rcx, r12; hPrinter
0x1800221d2  mov     [rsp+2B0h+cbBuf], eax; cbBuf
0x1800221d6  call    cs:__imp_GetPrinterDriverW
0x1800221dc  test    eax, eax
0x1800221de  jz      loc_180022283
0x1800221e4  mov     r8, [rdi+18h]
0x1800221e8  lea     r14, [rbx+18h]
0x1800221ec  mov     r15d, 7FFFFFFEh
0x1800221f2  mov     rax, r14
0x1800221f5  mov     ecx, r15d
0x1800221f8  mov     edx, 104h
0x1800221fd  test    rcx, rcx
0x180022200  jz      short loc_180022221
0x180022202  movzx   r9d, word ptr [r8]
0x180022206  test    r9w, r9w
0x18002220a  jz      short loc_180022221
0x18002220c  mov     [rax], r9w
0x180022210  add     r8, 2
0x180022214  add     rax, 2
0x180022218  dec     rcx
0x18002221b  sub     rdx, 1
0x18002221f  jnz     short loc_1800221FD
0x180022221  test    rdx, rdx
0x180022224  lea     rcx, [rax-2]
0x180022228  cmovnz  rcx, rax
0x18002222c  mov     [rcx], r13w
0x180022230  mov     rcx, rdi; hMem
0x180022233  call    cs:__imp_LocalFree
0x180022239  mov     edi, 5Ch ; '\'
0x18002223e  mov     rcx, r14; Str
0x180022241  mov     edx, edi; Ch
0x180022243  call    cs:__imp_wcsrchr
0x180022249  test    rax, rax
0x18002224c  jnz     loc_18002250F
0x180022252  mov     rcx, rbx; hMem
0x180022255  call    FICloseFontFile
0x18002225a  mov     rbx, r13
0x18002225d  mov     rax, rbx
0x180022260  mov     rcx, [rbp+1B0h+var_50]
0x180022267  xor     rcx, rsp; StackCookie
0x18002226a  call    __security_check_cookie
0x18002226f  add     rsp, 278h
0x180022276  pop     r15
0x180022278  pop     r14
0x18002227a  pop     r13
0x18002227c  pop     r12
0x18002227e  pop     rdi
0x18002227f  pop     rsi
0x180022280  pop     rbx
0x180022281  pop     rbp
0x180022282  retn
0x180022283  mov     rcx, rdi; hMem
0x180022286  call    cs:__imp_LocalFree
0x18002228c  jmp     short loc_180022252
0x18002228e  mov     rcx, r9
0x180022291  mov     rax, rdx
0x180022294  sub     rcx, rdx
0x180022297  neg     rax
0x18002229a  sbb     r8, r8
0x18002229d  and     r8, rcx
0x1800222a0  test    rdx, rdx
0x1800222a3  jz      short loc_1800222E9
0x1800222a5  mov     rax, r9
0x1800222a8  lea     rcx, aUnifont; "\\unifont\\"
0x1800222af  sub     rax, r8
0x1800222b2  lea     r8, [r14+r8*2]
0x1800222b6  jz      short loc_1800222DA
0x1800222b8  test    r15, r15
0x1800222bb  jz      short loc_1800222DA
0x1800222bd  movzx   edx, word ptr [rcx]
0x1800222c0  test    dx, dx
0x1800222c3  jz      short loc_1800222DA
0x1800222c5  mov     [r8], dx
0x1800222c9  add     rcx, 2
0x1800222cd  add     r8, 2
0x1800222d1  dec     r15
0x1800222d4  sub     rax, 1
0x1800222d8  jnz     short loc_1800222B8
0x1800222da  test    rax, rax
0x1800222dd  lea     rdx, [r8-2]
0x1800222e1  cmovnz  rdx, r8
0x1800222e5  mov     [rdx], r13w
0x1800222e9  mov     ecx, 208h
0x1800222ee  lea     rax, [rsp+2B0h+var_270]
0x1800222f3  mov     [rsp+2B0h+pcbNeeded], rax; pcbNeeded
0x1800222f8  lea     r9, [rsp+2B0h+pData]; pData
0x1800222fd  mov     [rsp+2B0h+cbBuf], ecx; nSize
0x180022301  lea     r8, [rsp+2B0h+pType]; pType
0x180022306  mov     [rsp+2B0h+var_270], ecx
0x18002230a  lea     rdx, aExternalfontfi; "ExternalFontFile"
0x180022311  mov     rcx, r12; hPrinter
0x180022314  call    cs:__imp_GetPrinterDataW
0x18002231a  cmp     eax, 0EAh
0x18002231f  jz      short loc_180022329
0x180022321  test    eax, eax
0x180022323  jnz     loc_180022252
0x180022329  mov     edx, 5Ch ; '\'; Ch
0x18002232e  lea     rcx, [rsp+2B0h+pData]; Str
0x180022333  mov     rdi, r13
0x180022336  call    cs:__imp_wcsrchr
0x18002233c  test    rax, rax
0x18002233f  jz      loc_180022529
0x180022345  add     rax, 2
0x180022349  mov     r8, rax; pszSrc
0x18002234c  mov     edx, 104h; cchDest
0x180022351  mov     rcx, r14; pszDest
0x180022354  call    StringCchCatW
0x180022359  mov     r15d, 0FFFFFFFFh
0x18002235f  test    rsi, rsi
0x180022362  jz      loc_1800223FC
0x180022368  xor     r9d, r9d; lpSecurityAttributes
0x18002236b  mov     [rsp+2B0h+hTemplateFile], r13; hTemplateFile
0x180022370  mov     dword ptr [rsp+2B0h+pcbNeeded], 100080h; dwFlagsAndAttributes
0x180022378  mov     edx, 80000000h; dwDesiredAccess
0x18002237d  mov     rcx, r14; lpFileName
0x180022380  mov     [rsp+2B0h+cbBuf], 3; dwCreationDisposition
0x180022388  lea     r8d, [r9+1]; dwShareMode
0x18002238c  call    cs:__imp_CreateFileW
0x180022392  mov     rdi, rax
0x180022395  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180022399  jz      short loc_18002240E
0x18002239b  xor     edx, edx; lpFileSizeHigh
0x18002239d  mov     rcx, rax; hFile
0x1800223a0  call    cs:__imp_GetFileSize
0x1800223a6  mov     [rsp+2B0h+var_270], eax
0x1800223aa  cmp     eax, r15d
0x1800223ad  jz      short loc_1800223FC
0x1800223af  xor     r9d, r9d; dwMaximumSizeHigh
0x1800223b2  mov     [rsp+2B0h+pcbNeeded], r13; lpName
0x1800223b7  xor     edx, edx; lpFileMappingAttributes
0x1800223b9  mov     [rsp+2B0h+cbBuf], r13d; dwMaximumSizeLow
0x1800223be  mov     rcx, rdi; hFile
0x1800223c1  lea     r8d, [r9+2]; flProtect
0x1800223c5  call    cs:__imp_CreateFileMappingW
0x1800223cb  mov     r14, rax
0x1800223ce  test    rax, rax
0x1800223d1  jz      short loc_1800223FC
0x1800223d3  xor     r9d, r9d; dwFileOffsetLow
0x1800223d6  mov     qword ptr [rsp+2B0h+cbBuf], r13; dwNumberOfBytesToMap
0x1800223db  xor     r8d, r8d; dwFileOffsetHigh
0x1800223de  mov     rcx, rax; hFileMappingObject
0x1800223e1  lea     edx, [r9+4]; dwDesiredAccess
0x1800223e5  call    cs:__imp_MapViewOfFile
0x1800223eb  mov     rcx, r14; hObject
0x1800223ee  mov     [rsi], rax
0x1800223f1  call    cs:__imp_CloseHandle
0x1800223f7  cmp     [rsi], r13
0x1800223fa  jnz     short loc_180022411
0x1800223fc  mov     rcx, rdi; hObject
0x1800223ff  call    cs:__imp_CloseHandle
0x180022405  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180022409  test    rsi, rsi
0x18002240c  jz      short loc_180022411
0x18002240e  mov     [rsi], r13
0x180022411  mov     rax, [rsi]
0x180022414  mov     [rbx+220h], rax
0x18002241b  test    rax, rax
0x18002241e  jz      loc_180022252
0x180022424  mov     rcx, rdi; hObject
0x180022427  call    cs:__imp_CloseHandle
0x18002242d  mov     rcx, [rsi]
0x180022430  mov     [rbx+228h], rcx
0x180022437  cmp     [rsp+2B0h+var_270], 30h ; '0'
0x18002243c  jb      loc_180022252
0x180022442  cmp     dword ptr [rcx], 31464655h
0x180022448  jnz     loc_180022252
0x18002244e  cmp     dword ptr [rcx+4], 10001h
0x180022455  jnz     loc_180022252
0x18002245b  cmp     dword ptr [rcx+8], 30h ; '0'
0x18002245f  jnz     loc_180022252
0x180022465  mov     r8d, [rcx+18h]
0x180022469  test    r8d, r8d
0x18002246c  jz      short loc_1800224A3
0x18002246e  mov     eax, [rcx+0Ch]
0x180022471  lea     rdx, [rax+rax*8]
0x180022475  shl     rdx, 2
0x180022479  cmp     rdx, r15
0x18002247c  ja      loc_180022252
0x180022482  lea     eax, [rdx+r8]
0x180022486  cmp     eax, edx
0x180022488  jb      loc_180022252
0x18002248e  cmp     [rsp+2B0h+var_270], eax
0x180022492  jb      loc_180022252
0x180022498  lea     rax, [rcx+r8]
0x18002249c  mov     [rbx+230h], rax
0x1800224a3  mov     [rbx+238h], r13d
0x1800224aa  mov     dword ptr [rbx+23Ch], 1
0x1800224b4  mov     [rbx+248h], r13
0x1800224bb  mov     [rbx+250h], r13d
0x1800224c2  jmp     loc_18002225D
0x1800224c7  cmp     [rax], r13w
0x1800224cb  jz      loc_18002228E
0x1800224d1  add     rax, 2
0x1800224d5  sub     rdx, 1
0x1800224d9  jnz     short loc_1800224C7
0x1800224db  jmp     loc_18002228E
0x1800224e0  mov     edx, edi; Ch
0x1800224e2  mov     [rax], r13w
0x1800224e6  mov     rcx, r14; Str
0x1800224e9  call    cs:__imp_wcsrchr
0x1800224ef  test    rax, rax
0x1800224f2  jz      loc_180022252
0x1800224f8  mov     r9d, 104h
0x1800224fe  mov     [rax], r13w
0x180022502  mov     edx, r9d
0x180022505  mov     rax, r14
0x180022508  jmp     short loc_1800224C7
0x18002250a  jmp     loc_180022260
0x18002250f  mov     edx, edi; Ch
0x180022511  mov     [rax], r13w
0x180022515  mov     rcx, r14; Str
0x180022518  call    cs:__imp_wcsrchr
0x18002251e  test    rax, rax
0x180022521  jz      loc_180022252
0x180022527  jmp     short loc_1800224E0
0x180022529  lea     rax, [rsp+2B0h+pData]
0x18002252e  jmp     loc_180022349
```
