# MosQueryCatalogExists(bool *,StackMode)

- ea: `0x18000af60`
- end: `0x18000b1c4`
- name: `?MosQueryCatalogExists@@YAJPEA_NW4StackMode@@@Z`
- size: `612`
- prototype: `int __fastcall(bool *, int)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x180001c80`
- `0x180002802`
- `0x180006100`
- `0x180008ac0`
- `0x18000af60`
- `0x18000d1b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0a8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b092`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b0a8`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000b07e`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x18000b07e`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000b0e8`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18000b0e8`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000affe`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000b11a`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000affe`
- `ZTrace_Maps!ZTraceReportOriginationNoThis` at `0x18000b11a`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000afae`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b069`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b188`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000afae`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b069`
- `ZTrace_Maps!ZTraceReportPropagationNoThis` at `0x18000b188`

## string_xrefs

- `0x18000b12e`: `diskcache`
- `0x18000b02b`: `mapscache`

## pseudocode

```c
int __fastcall MosQueryCatalogExists(bool *a1, int a2)
{
  int DataDirectory; // eax
  int v5; // r8d
  int v6; // ecx
  int v8; // eax
  __int64 FirstFileW; // rbx
  int v10; // r8d
  int v11; // ecx
  int v12; // eax
  int v13; // edi
  int v14; // eax
  signed int LastError; // eax
  int v16; // eax
  int v17; // r8d
  _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-688h] BYREF
  WCHAR FileName[264]; // [rsp+2A0h] [rbp-438h] BYREF
  WCHAR pszPathOut[264]; // [rsp+4B0h] [rbp-228h] BYREF

  DataDirectory = MosStorageGetDataDirectory(pszPathOut, 0x104u);
  if ( DataDirectory < 0 )
  {
    v5 = 288;
LABEL_3:
    v6 = DataDirectory;
    return ZTraceReportPropagationNoThis(v6, "MosQueryCatalogExists", v5);
  }
  v8 = 3;
  if ( a2 )
    v8 = a2;
  if ( v8 == 3 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = -1;
    if ( a1 )
    {
      v14 = StringCchPrintfW(
              FileName,
              0x104u,
              L"%s\\%s\\%s\\%08X????????.%s",
              pszPathOut,
              L"mapscache",
              L"region",
              18,
              L"dat",
              -1);
      if ( v14 < 0 )
      {
        v12 = ZTraceReportPropagationNoThis(v14, "MosQueryCatalogExistsInternal_Unified", 331);
        goto LABEL_11;
      }
      FirstFileW = (__int64)FindFirstFileW(FileName, &FindFileData);
      if ( FirstFileW != -1 || GetLastError() == 2 || GetLastError() == 3 )
      {
        v13 = 0;
        *a1 = FirstFileW != -1;
LABEL_23:
        if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
          FindClose((HANDLE)FirstFileW);
        if ( v13 < 0 )
        {
          v5 = 298;
          v6 = v13;
          return ZTraceReportPropagationNoThis(v6, "MosQueryCatalogExists", v5);
        }
        return 0;
      }
      LastError = GetLastError();
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        LastError = -2143748092;
      }
      v10 = 338;
      v11 = LastError;
    }
    else
    {
      v10 = 319;
      v11 = -2147467261;
    }
    v12 = ZTraceReportOriginationNoThis(v11, "MosQueryCatalogExistsInternal_Unified", v10);
LABEL_11:
    v13 = v12;
    goto LABEL_23;
  }
  if ( a1 )
  {
    v16 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s\\%s\\MAP.CTL", pszPathOut, L"diskcache", L"BundleStore");
    if ( v16 >= 0 )
    {
      v16 = FileExists(FileName, a1);
      if ( v16 >= 0 )
        return 0;
      v17 = 359;
    }
    else
    {
      v17 = 357;
    }
    DataDirectory = ZTraceReportPropagationNoThis(v16, "MosQueryCatalogExistsInternal_Mos", v17);
  }
  else
  {
    DataDirectory = ZTraceReportOriginationNoThis(-2147467261, "MosQueryCatalogExistsInternal_Mos", 355);
  }
  if ( DataDirectory < 0 )
  {
    v5 = 302;
    goto LABEL_3;
  }
  return 0;
}

```

## disassembly

```asm
0x18000af60  mov     [rsp+arg_8], rbx
0x18000af65  mov     [rsp+arg_10], rsi
0x18000af6a  push    rdi
0x18000af6b  sub     rsp, 6D0h
0x18000af72  mov     rax, cs:__security_cookie
0x18000af79  xor     rax, rsp
0x18000af7c  mov     [rsp+6D8h+var_18], rax
0x18000af84  mov     ebx, edx
0x18000af86  mov     rsi, rcx
0x18000af89  mov     edi, 104h
0x18000af8e  mov     edx, edi; cchPathOut
0x18000af90  lea     rcx, [rsp+6D8h+pszPathOut]; pszPathOut
0x18000af98  call    ?MosStorageGetDataDirectory@@YAJPEAGK@Z; MosStorageGetDataDirectory(ushort *,ulong)
0x18000af9d  test    eax, eax
0x18000af9f  jns     short loc_18000AFB9
0x18000afa1  lea     r8d, [rdi+1Ch]
0x18000afa5  mov     ecx, eax
0x18000afa7  lea     rdx, aMosquerycatalo_0; "MosQueryCatalogExists"
0x18000afae  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000afb4  jmp     loc_18000B19F
0x18000afb9  mov     eax, 3
0x18000afbe  test    ebx, ebx
0x18000afc0  cmovnz  eax, ebx
0x18000afc3  cmp     eax, 3
0x18000afc6  jnz     loc_18000B103
0x18000afcc  xor     edx, edx; Val
0x18000afce  mov     r8d, 250h; Size
0x18000afd4  lea     rcx, [rsp+6D8h+FindFileData]; void *
0x18000afd9  call    memset_0
0x18000afde  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18000afe2  mov     [rsp+6D8h+var_698], rbx
0x18000afe7  test    rsi, rsi
0x18000afea  jnz     short loc_18000B00B
0x18000afec  mov     r8d, 13Fh
0x18000aff2  mov     ecx, 80004003h
0x18000aff7  lea     rdx, aMosquerycatalo_1; "MosQueryCatalogExistsInternal_Unified"
0x18000affe  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000b004  mov     edi, eax
0x18000b006  jmp     loc_18000B0DB
0x18000b00b  lea     rax, aDat; "dat"
0x18000b012  mov     [rsp+6D8h+var_6A0], rax
0x18000b017  mov     [rsp+6D8h+var_6A8], 12h
0x18000b01f  lea     rax, aRegion; "region"
0x18000b026  mov     [rsp+6D8h+var_6B0], rax
0x18000b02b  lea     rax, aMapscache_0; "mapscache"
0x18000b032  mov     [rsp+6D8h+var_6B8], rax
0x18000b037  lea     r9, [rsp+6D8h+pszPathOut]
0x18000b03f  lea     r8, aSSS08xS; "%s\\%s\\%s\\%08X????????.%s"
0x18000b046  mov     rdx, rdi; unsigned __int64
0x18000b049  lea     rcx, [rsp+6D8h+FileName]; unsigned __int16 *
0x18000b051  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b056  test    eax, eax
0x18000b058  jns     short loc_18000B071
0x18000b05a  mov     r8d, 14Bh
0x18000b060  lea     rdx, aMosquerycatalo_1; "MosQueryCatalogExistsInternal_Unified"
0x18000b067  mov     ecx, eax
0x18000b069  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000b06f  jmp     short loc_18000B004
0x18000b071  lea     rdx, [rsp+6D8h+FindFileData]; lpFindFileData
0x18000b076  lea     rcx, [rsp+6D8h+FileName]; lpFileName
0x18000b07e  call    cs:__imp_FindFirstFileW
0x18000b084  mov     rbx, rax
0x18000b087  mov     [rsp+6D8h+var_698], rax
0x18000b08c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000b090  jnz     short loc_18000B0D0
0x18000b092  call    cs:__imp_GetLastError
0x18000b098  cmp     eax, 2
0x18000b09b  jz      short loc_18000B0D0
0x18000b09d  call    cs:__imp_GetLastError
0x18000b0a3  cmp     eax, 3
0x18000b0a6  jz      short loc_18000B0D0
0x18000b0a8  call    cs:__imp_GetLastError
0x18000b0ae  test    eax, eax
0x18000b0b0  jz      short loc_18000B0BE
0x18000b0b2  jle     short loc_18000B0C3
0x18000b0b4  movzx   eax, ax
0x18000b0b7  or      eax, 80070000h
0x18000b0bc  jmp     short loc_18000B0C3
0x18000b0be  mov     eax, 80390004h
0x18000b0c3  mov     r8d, 152h
0x18000b0c9  mov     ecx, eax
0x18000b0cb  jmp     loc_18000AFF7
0x18000b0d0  xor     edi, edi
0x18000b0d2  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18000b0d6  setnz   al
0x18000b0d9  mov     [rsi], al
0x18000b0db  lea     rax, [rbx-1]
0x18000b0df  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000b0e3  ja      short loc_18000B0EE
0x18000b0e5  mov     rcx, rbx; hFindFile
0x18000b0e8  call    cs:__imp_FindClose
0x18000b0ee  test    edi, edi
0x18000b0f0  jns     loc_18000B19D
0x18000b0f6  mov     r8d, 12Ah
0x18000b0fc  mov     ecx, edi
0x18000b0fe  jmp     loc_18000AFA7
0x18000b103  test    rsi, rsi
0x18000b106  jnz     short loc_18000B122
0x18000b108  mov     r8d, 163h
0x18000b10e  lea     rdx, aMosquerycatalo_2; "MosQueryCatalogExistsInternal_Mos"
0x18000b115  mov     ecx, 80004003h
0x18000b11a  call    cs:__imp_?ZTraceReportOriginationNoThis@@YAJHPEBDH@Z; ZTraceReportOriginationNoThis(int,char const *,int)
0x18000b120  jmp     short loc_18000B18E
0x18000b122  lea     rax, aBundlestore; "BundleStore"
0x18000b129  mov     [rsp+6D8h+var_6B0], rax
0x18000b12e  lea     rax, aDiskcache; "diskcache"
0x18000b135  mov     [rsp+6D8h+var_6B8], rax
0x18000b13a  lea     r9, [rsp+6D8h+pszPathOut]
0x18000b142  lea     r8, aSSSMapCtl; "%s\\%s\\%s\\MAP.CTL"
0x18000b149  mov     rdx, rdi; unsigned __int64
0x18000b14c  lea     rcx, [rsp+6D8h+FileName]; unsigned __int16 *
0x18000b154  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18000b159  test    eax, eax
0x18000b15b  jns     short loc_18000B165
0x18000b15d  mov     r8d, 165h
0x18000b163  jmp     short loc_18000B17F
0x18000b165  mov     rdx, rsi; bool *
0x18000b168  lea     rcx, [rsp+6D8h+FileName]; unsigned __int16 *
0x18000b170  call    ?FileExists@@YAJPEBGPEA_N@Z; FileExists(ushort const *,bool *)
0x18000b175  test    eax, eax
0x18000b177  jns     short loc_18000B19D
0x18000b179  mov     r8d, 167h
0x18000b17f  lea     rdx, aMosquerycatalo_2; "MosQueryCatalogExistsInternal_Mos"
0x18000b186  mov     ecx, eax
0x18000b188  call    cs:__imp_?ZTraceReportPropagationNoThis@@YAJHPEBDH@Z; ZTraceReportPropagationNoThis(int,char const *,int)
0x18000b18e  test    eax, eax
0x18000b190  jns     short loc_18000B19D
0x18000b192  mov     r8d, 12Eh
0x18000b198  jmp     loc_18000AFA5
0x18000b19d  xor     eax, eax
0x18000b19f  mov     rcx, [rsp+6D8h+var_18]
0x18000b1a7  xor     rcx, rsp; StackCookie
0x18000b1aa  call    __security_check_cookie
0x18000b1af  lea     r11, [rsp+6D8h+var_8]
0x18000b1b7  mov     rbx, [r11+18h]
0x18000b1bb  mov     rsi, [r11+20h]
0x18000b1bf  mov     rsp, r11
0x18000b1c2  pop     rdi
0x18000b1c3  retn
```
