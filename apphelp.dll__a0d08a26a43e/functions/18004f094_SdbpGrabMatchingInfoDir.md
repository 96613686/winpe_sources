# SdbpGrabMatchingInfoDir

- ea: `0x18004f094`
- end: `0x18004fb2f`
- name: `SdbpGrabMatchingInfoDir`
- size: `2715`
- prototype: `__int64 __fastcall(void *, __int64, int, const WCHAR *, wchar_t *, wchar_t *, int)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, registry_config, loader_planting`

## callers

- `0x18004ecc0`
- `0x18004f094`

## callees

- `0x180004ff0`
- `0x1800055e0`
- `0x180005660`
- `0x18000f114`
- `0x1800159e0`
- `0x180018f20`
- `0x18001a540`
- `0x180028a98`
- `0x180029220`
- `0x18002a8fc`
- `0x180039a5a`
- `0x18004f060`
- `0x18004f094`
- `0x180059175`
- `0x1800591b0`
- `0x18005a010`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x18004f151`
- `ntdll!RtlAllocateHeap` at `0x18004f151`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004f825`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004faef`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004f825`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18004faef`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004f2cc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004f2f6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004f429`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004f928`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004fac5`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004f2cc`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004f2f6`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004f429`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004f928`
- `api-ms-win-core-file-l1-1-0!WriteFile` at `0x18004fac5`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004f807`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004fa31`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004f807`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x18004fa31`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004f1fd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004f893`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004f1fd`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18004f893`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f211`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f211`

## string_xrefs

- `0x18004f1d3`: `StringCchCopy failed [%x]`
- `0x18004f26b`: `<?xml version="1.0" encoding="UTF-16"?>\n<DATABASE>\n`
- `0x18004f329`: `String copy failed`

## pseudocode

```c
__int64 __fastcall SdbpGrabMatchingInfoDir(
        void *a1,
        __int64 a2,
        int a3,
        const WCHAR *a4,
        wchar_t *a5,
        wchar_t *a6,
        int a7)
{
  const WCHAR *v7; // rdi
  unsigned __int16 v8; // si
  __int64 v9; // r14
  unsigned int v10; // esi
  _WORD *Heap; // r13
  __int64 v12; // rax
  const wchar_t *v13; // r8
  int v14; // eax
  __int64 v15; // r15
  int v16; // r10d
  _WORD *v17; // rbx
  HANDLE v18; // rbx
  __int64 v19; // r8
  __int64 v20; // rdx
  __int64 v21; // rcx
  __int64 v22; // r8
  int v23; // r12d
  const wchar_t *v24; // r10
  WCHAR v25; // ax
  const WCHAR *v26; // rcx
  const wchar_t *v27; // rbx
  const wchar_t *v28; // rdx
  WCHAR *cFileName; // rcx
  wchar_t *v30; // rax
  int j; // ebx
  int v32; // eax
  int v33; // ecx
  int v34; // eax
  int v35; // edi
  int v36; // eax
  wchar_t *v37; // rax
  wchar_t *v38; // rbx
  __int64 v39; // rcx
  int v40; // r14d
  wchar_t *v41; // rdi
  int FileAttributes; // eax
  __int64 v43; // r12
  unsigned int i; // r15d
  unsigned __int16 *v45; // rsi
  __int64 v46; // rbx
  int v47; // ebx
  wchar_t *v48; // r12
  LPCWSTR v49; // rdi
  __int64 v50; // rdi
  unsigned int (__fastcall *v51)(_QWORD, LPCWSTR, wchar_t *, __int64, _WORD *); // rax
  __int64 v52; // r8
  unsigned int v53; // eax
  int v54; // edx
  int v55; // edx
  __int64 v56; // r10
  unsigned int v57; // r10d
  __int64 v58; // r8
  DWORD Format; // [rsp+28h] [rbp-D8h]
  char Args; // [rsp+30h] [rbp-D0h]
  char Argsa; // [rsp+30h] [rbp-D0h]
  int v63; // [rsp+40h] [rbp-C0h]
  DWORD NumberOfBytesWritten; // [rsp+44h] [rbp-BCh] BYREF
  __int64 FirstFileW; // [rsp+48h] [rbp-B8h]
  int v66; // [rsp+50h] [rbp-B0h]
  int v67; // [rsp+54h] [rbp-ACh]
  unsigned int v68; // [rsp+58h] [rbp-A8h]
  __int64 v69; // [rsp+60h] [rbp-A0h]
  unsigned int v70; // [rsp+68h] [rbp-98h] BYREF
  wchar_t *v71; // [rsp+70h] [rbp-90h]
  HANDLE hFile; // [rsp+78h] [rbp-88h]
  _WORD *v73; // [rsp+80h] [rbp-80h]
  LPCWSTR lpFileName; // [rsp+88h] [rbp-78h]
  wchar_t *v75; // [rsp+90h] [rbp-70h]
  __int64 v76; // [rsp+98h] [rbp-68h]
  __int64 v77; // [rsp+A0h] [rbp-60h]
  __int64 v78; // [rsp+A8h] [rbp-58h] BYREF
  wchar_t *v79; // [rsp+B0h] [rbp-50h]
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+C0h] [rbp-40h] BYREF

  v7 = a4;
  v8 = a3;
  v77 = a2;
  hFile = a1;
  v67 = a3;
  v79 = a5;
  v71 = a6;
  lpFileName = a4;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v9 = v8;
  v10 = 0;
  v69 = 0;
  v63 = v9;
  NumberOfBytesWritten = 0;
  v70 = 0;
  v68 = 0;
  if ( !a7 || (unsigned int)(v9 - 4) > 1 )
  {
    Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 0x2000u);
    if ( !Heap )
    {
      AslLogCallPrintf(1, "SdbpGrabMatchingInfoDir", 281, "Unable to allocate grabmi buffer");
      return v10;
    }
    v12 = -1;
    do
      ++v12;
    while ( a6[v12] );
    if ( (_DWORD)v9 == 5 )
    {
      if ( !a5 )
        goto LABEL_151;
      v13 = a5;
    }
    else
    {
      v13 = L"*";
    }
    v75 = &a6[v12];
    v76 = 4096 - (v75 - v7);
    v14 = RtlStringCchCopyW(v75, v76, v13);
    if ( v14 < 0 )
    {
      AslLogCallPrintf(1, "SdbpGrabMatchingInfoDir", 305, "StringCchCopy failed [%x]", v14);
      goto LABEL_151;
    }
    FirstFileW = (__int64)FindFirstFileW(v7, &FindFileData);
    v15 = FirstFileW;
    if ( FirstFileW == -1 )
    {
      Format = GetLastError();
      AslLogCallPrintf(1, "SdbpGrabMatchingInfoDir", 315, "FindFirstFile Failed on [%ws] [%d]", v7, Format);
      goto LABEL_151;
    }
    v16 = 0;
    v17 = 0;
    v73 = 0;
    if ( !a7 )
    {
      if ( *(_DWORD *)(v77 + 24) )
      {
        *v75 = 0;
        if ( (int)RtlStringCchPrintfW(Heap, 4096, L"<?xml version=\"1.0\" encoding=\"UTF-16\"?>\r\n<DATABASE>\r\n") < 0 )
        {
          AslLogCallPrintf(1, "SdbpGrabMatchingInfoDir", 333, "lpData is too small");
          goto LABEL_150;
        }
        v18 = hFile;
        WriteFile(hFile, byte_180080720, 2u, &NumberOfBytesWritten, 0);
        v19 = -1;
        do
          ++v19;
        while ( Heap[v19] );
        WriteFile(v18, Heap, 2 * v19, &NumberOfBytesWritten, 0);
        v16 = 0;
      }
      if ( (_DWORD)v9 == 4 )
      {
        v20 = -1;
        do
          ++v20;
        while ( a5[v20] );
        if ( (int)RtlStringCchCopyW(a5, v20 + 1, L"SYSTEM INFO") < 0 )
        {
          AslLogCallPrintf(1, "SdbpGrabMatchingInfoDir", 353, "String copy failed");
          goto LABEL_150;
        }
      }
      if ( (int)RtlStringCchPrintfExW(Heap, v16, (wchar_t *)L"<EXE NAME=\"", Args) < 0 )
      {
        AslLogCallPrintf(1, "SdbpGrabMatchingInfoDir", 365, "lpData is to small");
        goto LABEL_150;
      }
      if ( !SdbpSanitizeXML(&Heap[4096 - (int)v69], v69, a5) )
        goto LABEL_150;
      v21 = -1;
      do
        ++v21;
      while ( Heap[v21] );
      if ( (int)RtlStringCchPrintfExW(&Heap[(int)v21], 0, (wchar_t *)L"\" FILTER=\"%s\">\r\n", (char)g_szFilterDesc[v9]) < 0 )
        goto LABEL_150;
      v17 = Heap;
      v22 = -1;
      v73 = Heap;
      do
        ++v22;
      while ( Heap[v22] );
      WriteFile(hFile, Heap, 2 * v22, &NumberOfBytesWritten, 0);
    }
    v66 = 0;
    v23 = 0;
    if ( (_DWORD)v9 == 1 || (unsigned int)(v9 - 4) <= 1 )
    {
      v23 = 10;
      v66 = 10;
    }
    while ( 1 )
    {
      if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        goto LABEL_102;
      if ( (int)RtlStringCchCopyW(v75, v76, FindFileData.cFileName) < 0 )
        goto LABEL_150;
      v25 = *v7;
      v26 = v7;
      v27 = v24;
      if ( *v7 )
      {
        while ( 1 )
        {
          switch ( v25 )
          {
            case ' ':
              goto LABEL_46;
            case '.':
              v27 = v26;
              break;
            case '\\':
LABEL_46:
              v27 = v24;
              break;
          }
          v26 = (const WCHAR *)SdbpCharNext(v26);
          v24 = 0;
          v25 = *v26;
          if ( !*v26 )
          {
            v15 = FirstFileW;
            break;
          }
        }
      }
      if ( !v27 )
        v27 = v26;
      if ( (unsigned int)v9 >= 2 )
        break;
      v35 = (int)v24;
      if ( *g_szGrabmiFilterNormal[0] != (_WORD)v24 )
      {
        do
        {
          if ( v27 )
          {
            v36 = wcsicmp_0(v27, g_szGrabmiFilterNormal[v35]);
            LODWORD(v24) = 0;
            if ( !v36 )
              break;
          }
          ++v35;
        }
        while ( *g_szGrabmiFilterNormal[v35] != (_WORD)v24 );
        v15 = FirstFileW;
      }
      if ( *g_szGrabmiFilterNormal[v35] == (_WORD)v24 )
      {
LABEL_73:
        if ( v23 >= 10 )
        {
          v17 = v73;
          goto LABEL_102;
        }
        v66 = v23 + 1;
      }
LABEL_75:
      v37 = L"    <SYS NAME=\"";
      if ( (_DWORD)v9 != 2 )
        v37 = (wchar_t *)L"    <MATCHING_FILE NAME=\"";
      if ( (int)RtlStringCchPrintfExW(Heap, (int)v24, v37, Args) < 0 )
        goto LABEL_150;
      v38 = v71;
      if ( !SdbpSanitizeXML(&Heap[4096 - (int)v69], v69, v71) )
        goto LABEL_150;
      v39 = -1;
      do
        ++v39;
      while ( Heap[v39] );
      if ( (int)RtlStringCchPrintfExW(&Heap[(int)v39], 0, (wchar_t *)L"\" ", Argsa) < 0 )
        goto LABEL_150;
      v78 = 0;
      v40 = 4096 - v69;
      v41 = &Heap[4096 - (int)v69];
      FileAttributes = SdbGetFileAttributes((__int64)lpFileName, &v78, &v70);
      v43 = v78;
      if ( FileAttributes )
      {
        for ( i = 0; ; ++i )
        {
          if ( i >= v70 )
          {
            v10 = v68;
            v15 = FirstFileW;
            v38 = v71;
            break;
          }
          v45 = (unsigned __int16 *)(v43 + 16LL * (int)i);
          if ( SdbFormatAttribute(v45, v41, 4096 - v40) )
          {
            v46 = -1;
            do
              ++v46;
            while ( v41[v46] );
            if ( v63 != 2 || *v45 == 16413 || *v45 == 16414 || *v45 == 20483 || *v45 == 20486 )
            {
              v47 = v46 + 1;
              v40 += v47;
              if ( v40 >= 4096 )
                AslLogCallPrintf(
                  1,
                  "SdbpGrabMatchingInfoDir",
                  573,
                  "lpBuffer is too small to handle attributes for %ws",
                  v71);
              if ( (int)RtlStringCchCatW(v41, 4096, L" ") < 0 )
              {
                v10 = v68;
                v15 = FirstFileW;
                goto LABEL_150;
              }
              v41 += v47;
            }
          }
        }
      }
      if ( (int)RtlStringCchPrintfW(v41, 4096, L"/>\r\n") >= 0 )
      {
        v50 = v77;
        v17 = Heap;
        v73 = Heap;
        v51 = *(unsigned int (__fastcall **)(_QWORD, LPCWSTR, wchar_t *, __int64, _WORD *))(v77 + 8);
        if ( v51 )
        {
          if ( !v51(*(_QWORD *)v77, lpFileName, v71, v43, Heap) )
            v10 = -1;
          v68 = v10;
        }
        v52 = -1;
        do
          ++v52;
        while ( Heap[v52] );
        WriteFile(hFile, Heap, 2 * v52, &NumberOfBytesWritten, 0);
        if ( v43 )
          SdbFreeFileAttributes(v43);
        v53 = *(_DWORD *)(v50 + 16);
        if ( v53 )
        {
          if ( ++*(_DWORD *)(v50 + 20) >= v53 && v10 != -1 )
            goto LABEL_136;
        }
      }
      else
      {
        AslLogCallPrintf(1, "SdbpGrabMatchingInfoDir", 594, "lpBuffer is too small to handle attributes for %ws", v38);
        v17 = v73;
      }
      LODWORD(v9) = v63;
LABEL_102:
      if ( !FindNextFileW((HANDLE)v15, &FindFileData) || (v23 = v66, v10 == -1) )
      {
        FindClose((HANDLE)v15);
        v15 = -1;
        FirstFileW = -1;
        if ( v10 != -1 && (unsigned int)(v9 - 4) > 1 )
        {
          if ( a7 < 3 && v67 >= 0 )
          {
            v48 = v75;
            if ( (int)RtlStringCchCopyW(v75, v76, L"*") >= 0 )
            {
              v49 = lpFileName;
              FirstFileW = (__int64)FindFirstFileW(lpFileName, &FindFileData);
              v15 = FirstFileW;
              if ( FirstFileW != -1 )
              {
                while ( 1 )
                {
                  if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
                  {
                    v54 = FindFileData.cFileName[0] - 46;
                    if ( FindFileData.cFileName[0] == 46 )
                      v54 = FindFileData.cFileName[1];
                    if ( v54 )
                    {
                      v55 = FindFileData.cFileName[0] - 46;
                      if ( FindFileData.cFileName[0] == 46 )
                      {
                        v55 = FindFileData.cFileName[1] - 46;
                        if ( FindFileData.cFileName[1] == 46 )
                          v55 = FindFileData.cFileName[2];
                      }
                      if ( v55 )
                      {
                        if ( (int)RtlStringCchCopyW(v48, v76, FindFileData.cFileName) < 0
                          || (int)RtlStringCchCatW(v48, v56, L"\\") < 0 )
                        {
                          goto LABEL_150;
                        }
                        v10 = SdbpGrabMatchingInfoDir((_DWORD)hFile, v77, v67, (_DWORD)v49, 0, (__int64)v71, a7 + 1);
                        if ( v10 == -1 )
                          goto LABEL_136;
                      }
                    }
                  }
                  if ( !FindNextFileW((HANDLE)v15, &FindFileData) )
                    goto LABEL_136;
                }
              }
              AslLogCallPrintf(1, "SdbpGrabMatchingInfoDir", 664, "%ws contains no matching files", v49);
            }
            goto LABEL_151;
          }
          v10 = 1;
          if ( !a7 )
          {
LABEL_139:
            if ( (int)RtlStringCchCopyW(v17, 4096, L"</EXE>\r\n") >= 0
              && ((v67 & 0x10000000) != 0 || (int)RtlStringCchCatW(v17, v57, L"</DATABASE>\r\n") >= 0) )
            {
              v58 = -1;
              do
                ++v58;
              while ( v17[v58] );
              WriteFile(hFile, v17, 2 * v58, &NumberOfBytesWritten, 0);
              goto LABEL_145;
            }
            goto LABEL_147;
          }
LABEL_151:
          AslFree(NtCurrentPeb()->ProcessHeap, Heap);
          return v10;
        }
LABEL_136:
        if ( !a7 )
        {
          v15 = FirstFileW;
          goto LABEL_139;
        }
LABEL_145:
        v15 = FirstFileW;
        if ( v10 != -1 )
          v10 = 1;
LABEL_147:
        if ( v15 == -1 )
          goto LABEL_151;
LABEL_150:
        FindClose((HANDLE)v15);
        goto LABEL_151;
      }
      v7 = lpFileName;
    }
    switch ( (_DWORD)v9 )
    {
      case 2:
        if ( !v27 )
          goto LABEL_75;
        v28 = L".sys";
        cFileName = (WCHAR *)v27;
        break;
      case 4:
        v30 = g_szGrabmiFilterSystem[0];
        for ( j = (int)v24; *v30 != (_WORD)v24; v30 = g_szGrabmiFilterSystem[j] )
        {
          v32 = wcsicmp_0(FindFileData.cFileName, g_szGrabmiFilterSystem[j]);
          LODWORD(v24) = 0;
          if ( !v32 )
            break;
          ++j;
        }
        v33 = (int)v24;
        LOBYTE(v33) = *g_szGrabmiFilterSystem[j] == (wchar_t)v24;
LABEL_65:
        if ( v33 )
          goto LABEL_73;
        goto LABEL_75;
      case 5:
        v28 = v79;
        cFileName = FindFileData.cFileName;
        break;
      default:
        goto LABEL_75;
    }
    v34 = wcsicmp_0(cFileName, v28);
    LODWORD(v24) = 0;
    v33 = v34;
    goto LABEL_65;
  }
  return v10;
}

```

## disassembly

```asm
0x18004f094  push    rbp
0x18004f096  push    rbx
0x18004f097  push    rsi
0x18004f098  push    rdi
0x18004f099  push    r12
0x18004f09b  push    r13
0x18004f09d  push    r14
0x18004f09f  push    r15
0x18004f0a1  lea     rbp, [rsp-228h]
0x18004f0a9  sub     rsp, 328h
0x18004f0b0  mov     rax, cs:__security_cookie
0x18004f0b7  xor     rax, rsp
0x18004f0ba  mov     [rbp+260h+var_50], rax
0x18004f0c1  mov     r12, [rbp+260h+arg_20]
0x18004f0c8  mov     rdi, r9
0x18004f0cb  mov     rbx, [rbp+260h+arg_28]
0x18004f0d2  mov     esi, r8d
0x18004f0d5  mov     r8d, 250h; Size
0x18004f0db  mov     [rbp+260h+var_2C0], rdx
0x18004f0df  xor     edx, edx; Val
0x18004f0e1  mov     [rsp+360h+hFile], rcx
0x18004f0e6  lea     rcx, [rbp+260h+FindFileData]; void *
0x18004f0ea  mov     [rsp+360h+var_30C], esi
0x18004f0ee  mov     [rbp+260h+var_2B0], r12
0x18004f0f2  mov     [rsp+360h+var_2F0], rbx
0x18004f0f7  mov     [rbp+260h+lpFileName], r9
0x18004f0fb  call    memset_0
0x18004f100  xor     r15d, r15d
0x18004f103  movzx   r14d, si
0x18004f107  mov     esi, r15d
0x18004f10a  mov     [rsp+360h+var_300], r15
0x18004f10f  mov     [rsp+360h+var_320], r14d
0x18004f114  mov     [rsp+360h+NumberOfBytesWritten], r15d
0x18004f119  mov     [rsp+360h+var_2F8], r15d
0x18004f11e  mov     [rsp+360h+var_308], r15d
0x18004f123  cmp     [rbp+260h+arg_30], r15d
0x18004f12a  jz      short loc_18004F139
0x18004f12c  lea     eax, [r14-4]
0x18004f130  cmp     eax, 1
0x18004f133  jbe     loc_18004FB0A
0x18004f139  mov     rcx, gs:60h
0x18004f142  mov     edx, 8; Flags
0x18004f147  mov     r8d, 2000h; Size
0x18004f14d  mov     rcx, [rcx+30h]; HeapHandle
0x18004f151  call    cs:__imp_RtlAllocateHeap
0x18004f157  mov     r13, rax
0x18004f15a  test    rax, rax
0x18004f15d  jnz     short loc_18004F180
0x18004f15f  lea     r9, aUnableToAlloca_1; "Unable to allocate grabmi buffer"
0x18004f166  mov     r8d, 119h
0x18004f16c  lea     rdx, aSdbpgrabmatchi; "SdbpGrabMatchingInfoDir"
0x18004f173  lea     ecx, [rax+1]
0x18004f176  call    AslLogCallPrintf
0x18004f17b  jmp     loc_18004FB0A
0x18004f180  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004f184  inc     rax
0x18004f187  cmp     [rbx+rax*2], r15w
0x18004f18c  jnz     short loc_18004F184
0x18004f18e  cmp     r14d, 5
0x18004f192  jnz     short loc_18004F1A2
0x18004f194  test    r12, r12
0x18004f197  jz      loc_18004FAF5
0x18004f19d  mov     r8, r12
0x18004f1a0  jmp     short loc_18004F1A9
0x18004f1a2  lea     r8, asc_18005E8F8; "*"
0x18004f1a9  lea     rcx, [rbx+rax*2]
0x18004f1ad  mov     edx, 1000h
0x18004f1b2  mov     rax, rcx
0x18004f1b5  mov     [rbp+260h+var_2D0], rcx
0x18004f1b9  sub     rax, rdi
0x18004f1bc  sar     rax, 1
0x18004f1bf  sub     rdx, rax
0x18004f1c2  mov     [rbp+260h+var_2C8], rdx
0x18004f1c6  call    RtlStringCchCopyW
0x18004f1cb  test    eax, eax
0x18004f1cd  jns     short loc_18004F1F6
0x18004f1cf  mov     dword ptr [rsp+360h+lpOverlapped], eax
0x18004f1d3  lea     r9, aStringcchcopyF; "StringCchCopy failed [%x]"
0x18004f1da  mov     r8d, 131h
0x18004f1e0  lea     rdx, aSdbpgrabmatchi; "SdbpGrabMatchingInfoDir"
0x18004f1e7  mov     ecx, 1
0x18004f1ec  call    AslLogCallPrintf
0x18004f1f1  jmp     loc_18004FAF5
0x18004f1f6  lea     rdx, [rbp+260h+FindFileData]; lpFindFileData
0x18004f1fa  mov     rcx, rdi; lpFileName
0x18004f1fd  call    cs:__imp_FindFirstFileW
0x18004f203  mov     [rsp+360h+var_318], rax
0x18004f208  mov     r15, rax
0x18004f20b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f20f  jnz     short loc_18004F242
0x18004f211  call    cs:__imp_GetLastError
0x18004f217  mov     dword ptr [rsp+360h+Format], eax
0x18004f21b  lea     r9, aFindfirstfileF_0; "FindFirstFile Failed on [%ws] [%d]"
0x18004f222  mov     r8d, 13Bh
0x18004f228  mov     [rsp+360h+lpOverlapped], rdi
0x18004f22d  lea     rdx, aSdbpgrabmatchi; "SdbpGrabMatchingInfoDir"
0x18004f234  lea     ecx, [r15+2]
0x18004f238  call    AslLogCallPrintf
0x18004f23d  jmp     loc_18004FAF5
0x18004f242  xor     r10d, r10d
0x18004f245  mov     ebx, r10d
0x18004f248  mov     [rbp+260h+var_2E0], rbx
0x18004f24c  cmp     [rbp+260h+arg_30], r10d
0x18004f253  jnz     loc_18004F432
0x18004f259  mov     rax, [rbp+260h+var_2C0]
0x18004f25d  cmp     [rax+18h], r10d
0x18004f261  jz      loc_18004F2FF
0x18004f267  mov     rcx, [rbp+260h+var_2D0]
0x18004f26b  lea     r8, aXmlVersion10En; "<?xml version=\"1.0\" encoding=\"UTF-16"...
0x18004f272  mov     edx, 1000h
0x18004f277  mov     [rcx], r10w
0x18004f27b  mov     rcx, r13
0x18004f27e  call    RtlStringCchPrintfW
0x18004f283  xor     r10d, r10d
0x18004f286  test    eax, eax
0x18004f288  jns     short loc_18004F2AD
0x18004f28a  lea     r9, aLpdataIsTooSma; "lpData is too small"
0x18004f291  mov     r8d, 14Dh
0x18004f297  lea     rdx, aSdbpgrabmatchi; "SdbpGrabMatchingInfoDir"
0x18004f29e  mov     ecx, 1
0x18004f2a3  call    AslLogCallPrintf
0x18004f2a8  jmp     loc_18004FAEC
0x18004f2ad  mov     rbx, [rsp+360h+hFile]
0x18004f2b2  lea     r9, [rsp+360h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004f2b7  mov     rcx, rbx; hFile
0x18004f2ba  mov     [rsp+360h+lpOverlapped], r10; lpOverlapped
0x18004f2bf  mov     r8d, 2; nNumberOfBytesToWrite
0x18004f2c5  lea     rdx, byte_180080720; lpBuffer
0x18004f2cc  call    cs:__imp_WriteFile
0x18004f2d2  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004f2d6  xor     eax, eax
0x18004f2d8  inc     r8
0x18004f2db  cmp     [r13+r8*2+0], ax
0x18004f2e1  jnz     short loc_18004F2D8
0x18004f2e3  add     r8d, r8d; nNumberOfBytesToWrite
0x18004f2e6  mov     [rsp+360h+lpOverlapped], rax; lpOverlapped
0x18004f2eb  lea     r9, [rsp+360h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004f2f0  mov     rdx, r13; lpBuffer
0x18004f2f3  mov     rcx, rbx; hFile
0x18004f2f6  call    cs:__imp_WriteFile
0x18004f2fc  xor     r10d, r10d
0x18004f2ff  cmp     r14d, 4
0x18004f303  jnz     short loc_18004F33B
0x18004f305  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18004f309  inc     rdx
0x18004f30c  cmp     [r12+rdx*2], r10w
0x18004f311  jnz     short loc_18004F309
0x18004f313  inc     rdx
0x18004f316  lea     r8, aSystemInfo; "SYSTEM INFO"
0x18004f31d  mov     rcx, r12
0x18004f320  call    RtlStringCchCopyW
0x18004f325  test    eax, eax
0x18004f327  jns     short loc_18004F33B
0x18004f329  lea     r9, aStringCopyFail; "String copy failed"
0x18004f330  mov     r8d, 161h
0x18004f336  jmp     loc_18004F297
0x18004f33b  lea     rax, aExeName; "<EXE NAME=\""
0x18004f342  mov     ebx, 1000h
0x18004f347  mov     [rsp+360h+Format], rax; Format
0x18004f34c  lea     r9, [rsp+360h+var_300]
0x18004f351  mov     edx, ebx
0x18004f353  mov     [rsp+360h+lpOverlapped], r10; int
0x18004f358  xor     r8d, r8d
0x18004f35b  mov     rcx, r13; Buffer
0x18004f35e  call    RtlStringCchPrintfExW
0x18004f363  test    eax, eax
0x18004f365  jns     short loc_18004F379
0x18004f367  lea     r9, aLpdataIsToSmal; "lpData is to small"
0x18004f36e  mov     r8d, 16Dh
0x18004f374  jmp     loc_18004F297
0x18004f379  mov     eax, ebx
0x18004f37b  mov     edx, ebx
0x18004f37d  sub     eax, dword ptr [rsp+360h+var_300]
0x18004f381  mov     r8, r12
0x18004f384  sub     edx, eax
0x18004f386  cdqe
0x18004f388  lea     rcx, ds:0[rax*2]
0x18004f390  add     rcx, r13
0x18004f393  call    SdbpSanitizeXML
0x18004f398  xor     r12d, r12d
0x18004f39b  test    eax, eax
0x18004f39d  jz      loc_18004FAEC
0x18004f3a3  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004f3a7  inc     rcx
0x18004f3aa  cmp     [r13+rcx*2+0], r12w
0x18004f3b0  jnz     short loc_18004F3A7
0x18004f3b2  movsxd  rax, ecx
0x18004f3b5  lea     r9, [rsp+360h+var_300]
0x18004f3ba  mov     edx, ebx
0x18004f3bc  xor     r8d, r8d
0x18004f3bf  sub     edx, ecx
0x18004f3c1  lea     rcx, ds:0[rax*2]
0x18004f3c9  lea     rax, __ImageBase
0x18004f3d0  add     rcx, r13; Buffer
0x18004f3d3  mov     rax, ds:rva g_szFilterDesc[rax+r14*8]
0x18004f3db  mov     qword ptr [rsp+360h+Args], rax; Args
0x18004f3e0  lea     rax, aFilterS; "\" FILTER=\"%s\">\r\n"
0x18004f3e7  mov     [rsp+360h+Format], rax; Format
0x18004f3ec  mov     [rsp+360h+lpOverlapped], r12; int
0x18004f3f1  call    RtlStringCchPrintfExW
0x18004f3f6  test    eax, eax
0x18004f3f8  js      loc_18004FAEC
0x18004f3fe  mov     rbx, r13
0x18004f401  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004f405  mov     [rbp+260h+var_2E0], rbx
0x18004f409  inc     r8
0x18004f40c  cmp     [r13+r8*2+0], r12w
0x18004f412  jnz     short loc_18004F409
0x18004f414  mov     rcx, [rsp+360h+hFile]; hFile
0x18004f419  lea     r9, [rsp+360h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x18004f41e  add     r8d, r8d; nNumberOfBytesToWrite
0x18004f421  mov     [rsp+360h+lpOverlapped], r12; lpOverlapped
0x18004f426  mov     rdx, r13; lpBuffer
0x18004f429  call    cs:__imp_WriteFile
0x18004f42f  xor     r10d, r10d
0x18004f432  mov     eax, r14d
0x18004f435  mov     [rsp+360h+var_310], r10d
0x18004f43a  mov     r12d, r10d
0x18004f43d  sub     eax, 1
0x18004f440  jz      short loc_18004F44C
0x18004f442  sub     eax, 3
0x18004f445  jz      short loc_18004F44C
0x18004f447  cmp     eax, 1
0x18004f44a  jnz     short loc_18004F45D
0x18004f44c  mov     r12d, 0Ah
0x18004f452  mov     [rsp+360h+var_310], r12d
0x18004f457  jmp     short loc_18004F45D
0x18004f459  mov     rdi, [rbp+260h+lpFileName]
0x18004f45d  test    byte ptr [rbp+260h+FindFileData.dwFileAttributes], 10h
0x18004f461  jnz     loc_18004F800
0x18004f467  mov     rdx, [rbp+260h+var_2C8]
0x18004f46b  lea     r8, [rbp+260h+FindFileData.cFileName]
0x18004f46f  mov     rcx, [rbp+260h+var_2D0]
0x18004f473  call    RtlStringCchCopyW
0x18004f478  test    eax, eax
0x18004f47a  js      loc_18004FAEC
0x18004f480  movzx   eax, word ptr [rdi]
0x18004f483  mov     rcx, rdi
0x18004f486  mov     rbx, r10
0x18004f489  test    ax, ax
0x18004f48c  jz      short loc_18004F4C1
0x18004f48e  mov     r15d, 2Eh ; '.'
0x18004f494  cmp     ax, 20h ; ' '
0x18004f498  jz      short loc_18004F4A6
0x18004f49a  cmp     ax, r15w
0x18004f49e  jz      short loc_18004F4FA
0x18004f4a0  cmp     ax, 5Ch ; '\'
0x18004f4a4  jnz     short loc_18004F4A9
0x18004f4a6  mov     rbx, r10
0x18004f4a9  call    SdbpCharNext
0x18004f4ae  mov     rcx, rax
0x18004f4b1  xor     r10d, r10d
0x18004f4b4  movzx   eax, word ptr [rax]
0x18004f4b7  test    ax, ax
0x18004f4ba  jnz     short loc_18004F494
0x18004f4bc  mov     r15, [rsp+360h+var_318]
0x18004f4c1  test    rbx, rbx
0x18004f4c4  mov     eax, r14d
0x18004f4c7  cmovz   rbx, rcx
0x18004f4cb  test    r14d, r14d
0x18004f4ce  jz      loc_18004F57A
0x18004f4d4  sub     eax, 1
0x18004f4d7  jz      loc_18004F57A
0x18004f4dd  sub     eax, 1
0x18004f4e0  jz      short loc_18004F557
0x18004f4e2  sub     eax, 2
0x18004f4e5  jz      short loc_18004F4FF
0x18004f4e7  cmp     eax, 1
0x18004f4ea  jnz     loc_18004F5F2
0x18004f4f0  mov     rdx, [rbp+260h+var_2B0]
0x18004f4f4  lea     rcx, [rbp+260h+FindFileData.cFileName]
0x18004f4f8  jmp     short loc_18004F56A
0x18004f4fa  mov     rbx, rcx
0x18004f4fd  jmp     short loc_18004F4A9
0x18004f4ff  mov     rax, cs:g_szGrabmiFilterSystem
0x18004f506  lea     rdi, __ImageBase
0x18004f50d  mov     ebx, r10d
0x18004f510  cmp     [rax], r10w
0x18004f514  jz      short loc_18004F540
0x18004f516  movsxd  rdx, ebx
0x18004f519  lea     rcx, [rbp+260h+FindFileData.cFileName]; String1
0x18004f51d  mov     rdx, ds:rva g_szGrabmiFilterSystem[rdi+rdx*8]; String2
0x18004f525  call    _wcsicmp_0
0x18004f52a  xor     r10d, r10d
0x18004f52d  test    eax, eax
0x18004f52f  jz      short loc_18004F540
0x18004f531  inc     ebx
0x18004f533  movsxd  rax, ebx
0x18004f536  mov     rax, ds:rva g_szGrabmiFilterSystem[rdi+rax*8]
0x18004f53e  jmp     short loc_18004F510
0x18004f540  movsxd  rax, ebx
0x18004f543  mov     ecx, r10d
0x18004f546  mov     rax, ds:rva g_szGrabmiFilterSystem[rdi+rax*8]
0x18004f54e  cmp     [rax], r10w
0x18004f552  setz    cl
0x18004f555  jmp     short loc_18004F574
0x18004f557  test    rbx, rbx
0x18004f55a  jz      loc_18004F5F2
0x18004f560  lea     rdx, aSys_0; ".sys"
0x18004f567  mov     rcx, rbx; String1
  ... truncated ...
```
