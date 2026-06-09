# FileSaveRestoreOnINFW

- ea: `0x180010050`
- end: `0x18001033c`
- name: `FileSaveRestoreOnINFW`
- size: `748`
- prototype: `HRESULT __stdcall(HWND hWnd, LPCWSTR pszTitle, LPCWSTR pszINF, LPCWSTR pszSection, LPCWSTR pszBackupDir, LPCWSTR pszBaseBackupFile, DWORD dwFlags)`
- caller_count: `1`
- callee_count: `15`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x18000ff40`

## callees

- `0x1800022bc`
- `0x180003180`
- `0x1800035c8`
- `0x180004700`
- `0x180004754`
- `0x180007454`
- `0x1800082f0`
- `0x18000c574`
- `0x18000d6cc`
- `0x180010050`
- `0x1800198d0`
- `0x18001a688`
- `0x18001b294`
- `0x18001b94e`
- `0x18001b980`

## import_xrefs

- `SHLWAPI!PathRemoveFileSpecW` at `0x1800101ca`
- `SHLWAPI!PathRemoveFileSpecW` at `0x1800101ca`
- `SHLWAPI!PathFileExistsW` at `0x18001025f`
- `SHLWAPI!PathFileExistsW` at `0x18001025f`

## pseudocode

```c
HRESULT __stdcall FileSaveRestoreOnINFW(
        HWND hWnd,
        LPCWSTR pszTitle,
        LPCWSTR pszINF,
        LPCWSTR pszSection,
        LPCWSTR pszBackupDir,
        LPCWSTR pszBaseBackupFile,
        DWORD dwFlags)
{
  int v10; // r12d
  LPCWSTR v11; // rdx
  DWORD v12; // r14d
  __int64 v13; // r9
  const WCHAR *v14; // r8
  const unsigned __int16 *v15; // rcx
  const unsigned __int16 *v16; // r10
  HRESULT v17; // ebx
  LPCWSTR v18; // rbx
  ULONG v20; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v21; // [rsp+28h] [rbp-D8h]
  LPCWSTR v23; // [rsp+48h] [rbp-B8h]
  HWND v24; // [rsp+50h] [rbp-B0h]
  WCHAR SectionName[104]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR pszPathOut[264]; // [rsp+130h] [rbp+30h] BYREF
  unsigned __int16 v27[264]; // [rsp+340h] [rbp+240h] BYREF
  WCHAR pszPath[264]; // [rsp+550h] [rbp+450h] BYREF

  memset_0(SectionName, 0, 0xC8u);
  memset_0(pszPath, 0, 0x208u);
  v10 = 0;
  v11 = pszINF;
  if ( !pszINF )
    v11 = L"NULL";
  AdvWriteToLog(L"FileSaveRestoreOnINF: Inf=%1\r\n", v11);
  v12 = dwFlags;
  v13 = 1;
  if ( (dwFlags & 8) != 0 )
    word_1800257D2 = 1;
  v24 = ::hWnd;
  if ( hWnd != HWND_MESSAGE|0x2LL )
    ::hWnd = hWnd;
  v14 = pszTitleString;
  v23 = pszTitleString;
  if ( pszTitle )
    pszTitleString = pszTitle;
  if ( !pszBackupDir || !*pszBackupDir || !pszBaseBackupFile || !*pszBaseBackupFile )
    goto LABEL_19;
  if ( (dwFlags & 1) != 0 && !pszINF && !pszSection )
    v12 = dwFlags | 0x100;
  if ( (v12 & 0x100) != 0 )
    goto LABEL_21;
  if ( IsFullPath(pszINF) )
  {
    v10 = v13;
    v17 = CommonInstallInit(v15, v16, SectionName, 0x64u, 0, 0, 0);
    if ( v17 < 0 )
    {
LABEL_34:
      CommonInstallCleanup();
LABEL_35:
      v14 = v23;
      goto LABEL_36;
    }
LABEL_21:
    if ( pszINF )
    {
      StringCchCopyW(pszPath, 0x104u, (size_t *)pszINF);
      PathRemoveFileSpecW(pszPath);
    }
    memset_0(v27, 0, 0x208u);
    if ( pszINF )
    {
      GetTranslatedString(pszINF, SectionName, L"CatalogName", v27, 0x104u, 0);
    }
    else
    {
      StringCchCopyW(pszPathOut, 0x104u, (size_t *)pszBackupDir);
      v18 = pszBaseBackupFile;
      if ( !(unsigned int)PathIsUnc2((unsigned __int16 *)pszBaseBackupFile)
        && !IsExtendedLengthDosDevicePath(pszBaseBackupFile)
        && *pszBaseBackupFile == 92 )
      {
        do
          ++v18;
        while ( *v18 == 92 );
      }
      PathCchCombineEx(pszPathOut, 0x104u, pszPathOut, v18, v20);
      StringCchCatW(pszPathOut, 260, L".cat");
      if ( PathFileExistsW(pszPathOut) )
        StringCchPrintfW(v27, 0x104u, L"%s.cat", pszBaseBackupFile);
    }
    if ( v27[0] )
      v27[0] = 0;
    v17 = ProcessAllFiles(hWnd, SectionName, pszPath, pszBackupDir, pszBaseBackupFile, v21, v12);
    if ( !v10 )
      goto LABEL_35;
    goto LABEL_34;
  }
LABEL_19:
  v17 = -2147024809;
LABEL_36:
  ::hWnd = v24;
  pszTitleString = v14;
  AdvWriteToLog(L"FileSaveRestoreOnINF: End hr=0x%1!x!\r\n", (unsigned int)v17, v14, v13);
  return v17;
}

```

## disassembly

```asm
0x180010050  mov     [rsp-8+arg_8], rbx
0x180010055  push    rbp
0x180010056  push    rsi
0x180010057  push    rdi
0x180010058  push    r12
0x18001005a  push    r13
0x18001005c  push    r14
0x18001005e  push    r15
0x180010060  lea     rbp, [rsp-670h]
0x180010068  sub     rsp, 770h
0x18001006f  mov     rax, cs:__security_cookie
0x180010076  xor     rax, rsp
0x180010079  mov     [rbp+6A0h+var_40], rax
0x180010080  mov     r15, [rbp+6A0h+pszBackupDir]
0x180010087  mov     rdi, r8
0x18001008a  mov     rsi, [rbp+6A0h+pszBaseBackupFile]
0x180010091  mov     rbx, rdx
0x180010094  mov     r13, rcx
0x180010097  mov     [rsp+7A0h+var_760], r9
0x18001009c  xor     edx, edx; Val
0x18001009e  lea     rcx, [rsp+7A0h+SectionName]; void *
0x1800100a3  mov     r8d, 0C8h; Size
0x1800100a9  call    memset_0
0x1800100ae  xor     edx, edx; Val
0x1800100b0  lea     rcx, [rbp+6A0h+pszPath]; void *
0x1800100b7  mov     r8d, 208h; Size
0x1800100bd  call    memset_0
0x1800100c2  lea     rax, aNull; "NULL"
0x1800100c9  xor     r12d, r12d
0x1800100cc  test    rdi, rdi
0x1800100cf  lea     rcx, aFilesaverestor_6; "FileSaveRestoreOnINF: Inf=%1\r\n"
0x1800100d6  mov     rdx, rdi
0x1800100d9  cmovz   rdx, rax
0x1800100dd  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x1800100e2  mov     r14d, [rbp+6A0h+dwFlags]
0x1800100e9  lea     r9d, [r12+1]
0x1800100ee  test    r14b, 8
0x1800100f2  jz      short loc_1800100FC
0x1800100f4  mov     cs:word_1800257D2, r9w
0x1800100fc  mov     r8, cs:hWnd
0x180010103  mov     [rsp+7A0h+var_750], r8
0x180010108  cmp     r13, 0FFFFFFFFFFFFFFFFh
0x18001010c  jz      short loc_180010115
0x18001010e  mov     cs:hWnd, r13
0x180010115  mov     r8, cs:pszTitleString
0x18001011c  mov     [rsp+7A0h+var_758], r8
0x180010121  test    rbx, rbx
0x180010124  jz      short loc_18001012D
0x180010126  mov     cs:pszTitleString, rbx
0x18001012d  xor     ebx, ebx
0x18001012f  test    r15, r15
0x180010132  jz      short loc_180010171
0x180010134  cmp     [r15], bx
0x180010138  jz      short loc_180010171
0x18001013a  test    rsi, rsi
0x18001013d  jz      short loc_180010171
0x18001013f  cmp     [rsi], bx
0x180010142  jz      short loc_180010171
0x180010144  mov     r10, [rsp+7A0h+var_760]
0x180010149  mov     eax, 100h
0x18001014e  test    r9b, r14b
0x180010151  jz      short loc_180010160
0x180010153  test    rdi, rdi
0x180010156  jnz     short loc_180010160
0x180010158  test    r10, r10
0x18001015b  jnz     short loc_180010160
0x18001015d  or      r14d, eax
0x180010160  test    eax, r14d
0x180010163  jnz     short loc_1800101AA
0x180010165  mov     rcx, rdi; unsigned __int16 *
0x180010168  call    ?IsFullPath@@YAHPEBG@Z; IsFullPath(ushort const *)
0x18001016d  test    eax, eax
0x18001016f  jnz     short loc_18001017B
0x180010171  mov     ebx, 80070057h
0x180010176  jmp     loc_1800102EF
0x18001017b  mov     r12d, r9d
0x18001017e  mov     [rsp+7A0h+var_770], ebx; unsigned int
0x180010182  mov     dword ptr [rsp+7A0h+var_778], ebx; int
0x180010186  lea     r8, [rsp+7A0h+SectionName]; unsigned __int16 *
0x18001018b  mov     r9d, 64h ; 'd'; unsigned int
0x180010191  mov     qword ptr [rsp+7A0h+var_780], rbx; unsigned __int16 *
0x180010196  mov     rdx, r10; unsigned __int16 *
0x180010199  call    ?CommonInstallInit@@YAJPEBG0PEAGK0HK@Z; CommonInstallInit(ushort const *,ushort const *,ushort *,ulong,ushort const *,int,ulong)
0x18001019e  mov     ebx, eax
0x1800101a0  test    eax, eax
0x1800101a2  js      loc_1800102E5
0x1800101a8  xor     ebx, ebx
0x1800101aa  test    rdi, rdi
0x1800101ad  jz      short loc_1800101D0
0x1800101af  mov     r8, rdi; unsigned __int16 *
0x1800101b2  lea     rcx, [rbp+6A0h+pszPath]; unsigned __int16 *
0x1800101b9  mov     edx, 104h; unsigned __int64
0x1800101be  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800101c3  lea     rcx, [rbp+6A0h+pszPath]; pszPath
0x1800101ca  call    cs:__imp_PathRemoveFileSpecW
0x1800101d0  xor     edx, edx; Val
0x1800101d2  lea     rcx, [rbp+6A0h+var_460]; void *
0x1800101d9  mov     r8d, 208h; Size
0x1800101df  call    memset_0
0x1800101e4  test    rdi, rdi
0x1800101e7  jnz     loc_180010285
0x1800101ed  mov     r8, r15; unsigned __int16 *
0x1800101f0  lea     rcx, [rbp+6A0h+pszPathOut]; unsigned __int16 *
0x1800101f4  mov     edx, 104h; unsigned __int64
0x1800101f9  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800101fe  lea     r8, IsBackslash
0x180010205  xor     edx, edx
0x180010207  mov     rcx, rsi; unsigned __int16 *
0x18001020a  mov     rbx, rsi
0x18001020d  call    PathIsUnc2
0x180010212  test    eax, eax
0x180010214  jnz     short loc_180010232
0x180010216  mov     rcx, rsi; unsigned __int16 *
0x180010219  call    ?IsExtendedLengthDosDevicePath@@YA_NPEBG@Z; IsExtendedLengthDosDevicePath(ushort const *)
0x18001021e  test    al, al
0x180010220  jnz     short loc_180010232
0x180010222  cmp     word ptr [rsi], 5Ch ; '\'
0x180010226  jnz     short loc_180010232
0x180010228  add     rbx, 2
0x18001022c  cmp     word ptr [rbx], 5Ch ; '\'
0x180010230  jz      short loc_180010228
0x180010232  mov     edi, 104h
0x180010237  lea     r8, [rbp+6A0h+pszPathOut]; pszPathIn
0x18001023b  mov     edx, edi; cchPathOut
0x18001023d  lea     rcx, [rbp+6A0h+pszPathOut]; pszPathOut
0x180010241  mov     r9, rbx; pszMore
0x180010244  call    PathCchCombineEx
0x180010249  lea     r8, aCat; ".cat"
0x180010250  mov     edx, edi; unsigned __int64
0x180010252  lea     rcx, [rbp+6A0h+pszPathOut]; unsigned __int16 *
0x180010256  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18001025b  lea     rcx, [rbp+6A0h+pszPathOut]; pszPath
0x18001025f  call    cs:__imp_PathFileExistsW
0x180010265  xor     ebx, ebx
0x180010267  test    eax, eax
0x180010269  jz      short loc_1800102AD
0x18001026b  mov     r9, rsi
0x18001026e  lea     r8, aSCat; "%s.cat"
0x180010275  mov     edx, edi; unsigned __int64
0x180010277  lea     rcx, [rbp+6A0h+var_460]; unsigned __int16 *
0x18001027e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180010283  jmp     short loc_1800102AD
0x180010285  mov     [rsp+7A0h+var_778], rbx; unsigned __int16 *
0x18001028a  lea     r9, [rbp+6A0h+var_460]; unsigned __int16 *
0x180010291  lea     r8, aCatalogname; "CatalogName"
0x180010298  mov     [rsp+7A0h+var_780], 104h; unsigned int
0x1800102a0  lea     rdx, [rsp+7A0h+SectionName]; lpAppName
0x1800102a5  mov     rcx, rdi; unsigned __int16 *
0x1800102a8  call    ?GetTranslatedString@@YAJPEBG00PEAGKPEAK@Z; GetTranslatedString(ushort const *,ushort const *,ushort const *,ushort *,ulong,ulong *)
0x1800102ad  cmp     [rbp+6A0h+var_460], bx
0x1800102b4  jz      short loc_1800102BD
0x1800102b6  mov     [rbp+6A0h+var_460], bx
0x1800102bd  mov     [rsp+7A0h+var_770], r14d; DWORD
0x1800102c2  lea     r8, [rbp+6A0h+pszPath]; SourceRootPath
0x1800102c9  mov     r9, r15; lpDir
0x1800102cc  mov     qword ptr [rsp+7A0h+var_780], rsi; lpBaseName
0x1800102d1  lea     rdx, [rsp+7A0h+SectionName]; SectionName
0x1800102d6  mov     rcx, r13; hWnd
0x1800102d9  call    ?ProcessAllFiles@@YAJPEAUHWND__@@PEBG1111K@Z; ProcessAllFiles(HWND__ *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x1800102de  mov     ebx, eax
0x1800102e0  test    r12d, r12d
0x1800102e3  jz      short loc_1800102EA
0x1800102e5  call    ?CommonInstallCleanup@@YAXXZ; CommonInstallCleanup(void)
0x1800102ea  mov     r8, [rsp+7A0h+var_758]
0x1800102ef  mov     rax, [rsp+7A0h+var_750]
0x1800102f4  lea     rcx, aFilesaverestor_5; "FileSaveRestoreOnINF: End hr=0x%1!x!\r"...
0x1800102fb  mov     edx, ebx
0x1800102fd  mov     cs:hWnd, rax
0x180010304  mov     cs:pszTitleString, r8
0x18001030b  call    ?AdvWriteToLog@@YAXPEBGZZ; AdvWriteToLog(ushort const *,...)
0x180010310  mov     eax, ebx
0x180010312  mov     rcx, [rbp+6A0h+var_40]
0x180010319  xor     rcx, rsp; StackCookie
0x18001031c  call    __security_check_cookie
0x180010321  mov     rbx, [rsp+7A0h+arg_8]
0x180010329  add     rsp, 770h
0x180010330  pop     r15
0x180010332  pop     r14
0x180010334  pop     r13
0x180010336  pop     r12
0x180010338  pop     rdi
0x180010339  pop     rsi
0x18001033a  pop     rbp
0x18001033b  retn
```
