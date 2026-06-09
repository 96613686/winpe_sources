# CModelDownloadComponent::GatherFilesExclusiveMode(ushort const *,ulong,void * *,ushort (* const)[261],ulong *)

- ea: `0x14000ee60`
- end: `0x14000f277`
- name: `?GatherFilesExclusiveMode@CModelDownloadComponent@@AEAAJPEBGKPEAPEAXQEAY0BAF@GPEAK@Z`
- size: `1047`
- prototype: `__int64 __fastcall(CModelDownloadComponent *this, const unsigned __int16 *, __int64, void **, unsigned __int16 (*const)[261], unsigned int *)`
- caller_count: `2`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14000c5f0`
- `0x14000ee60`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x14000985c`
- `0x14000af50`
- `0x14000ee60`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000ef4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscat_s` at `0x14000ef4e`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000eef6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000f0b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000f1fb`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000eef6`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000f0b8`
- `api-ms-win-crt-private-l1-1-0!_o_wcscpy_s` at `0x14000f1fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f0df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f1bd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f0df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f0f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f18e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000f1bd`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000f245`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000f245`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000f05d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000f05d`
- `api-ms-win-core-file-l1-1-0!LockFile` at `0x14000f086`
- `api-ms-win-core-file-l1-1-0!LockFile` at `0x14000f086`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000f0cf`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000f0cf`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000ef78`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000ef78`

## string_xrefs

- `0x14000ef0d`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1980)`
- `0x14000ef2c`: `CModelDownloadComponent::GatherFilesExclusiveMode`
- `0x14000f217`: `CModelDownloadComponent::GatherFilesExclusiveMode`
- `0x14000ef63`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(1985)`
- `0x14000f182`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2003)`
- `0x14000f16b`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2008)`
- `0x14000f026`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2014)`
- `0x14000f154`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2030)`
- `0x14000f13d`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2037)`
- `0x14000f126`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2043)`
- `0x14000f10f`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2052)`
- `0x14000f1d6`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2065)`
- `0x14000f1b0`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2071)`
- `0x14000f210`: `onecoreuap\enduser\nui\onecore\sapi\sapi\sharedlib\modeldownloadcomponent.cpp(2077)`

## pseudocode

```c
__int64 __fastcall CModelDownloadComponent::GatherFilesExclusiveMode(
        CModelDownloadComponent *this,
        const unsigned __int16 *a2,
        __int64 a3,
        void **a4,
        unsigned __int16 (*const a5)[261],
        unsigned int *a6)
{
  const unsigned __int16 *v6; // r14
  unsigned int v8; // ebx
  const wchar_t *v9; // rax
  char *FirstFileW; // r15
  int v11; // eax
  char *FileW; // r14
  __int64 v13; // rcx
  DWORD LastError; // eax
  signed int v15; // eax
  DWORD v16; // eax
  __int64 v17; // rcx
  signed int v18; // eax
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR v23[264]; // [rsp+2A0h] [rbp+1A0h] BYREF
  WCHAR FileName[264]; // [rsp+4B0h] [rbp+3B0h] BYREF

  v6 = a2;
  memset_0(FileName, 0, 0x20Au);
  memset_0(v23, 0, 0x20Au);
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v8 = 0;
  if ( (unsigned int)_o_wcscpy_s(FileName, 261, v6) )
  {
    v8 = -2147418113;
    v9 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1980)";
LABEL_3:
    DoTraceMessage(
      2,
      "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
      &NLInternal::s_tracingPrefix,
      L"CModelDownloadComponent::GatherFilesExclusiveMode",
      v9,
      -2147418113);
    return v8;
  }
  if ( (unsigned int)_o_wcscat_s(FileName, 261, L"\\*") )
  {
    v8 = -2147418113;
    v9 = L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(1985)";
    goto LABEL_3;
  }
  FirstFileW = (char *)FindFirstFileW(FileName, &FindFileData);
  if ( FirstFileW != (char *)-1LL )
  {
    do
    {
      if ( FindFileData.cFileName[0] != 46
        || FindFileData.cFileName[1] && (FindFileData.cFileName[1] != 46 || FindFileData.cFileName[2]) )
      {
        if ( *a6 >= 0x7F )
        {
          v8 = -2147024882;
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::GatherFilesExclusiveMode",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2003)",
            -2147024882);
          goto LABEL_40;
        }
        if ( (unsigned int)swprintf_s<261>(v23, L"%s\\%s", v6, FindFileData.cFileName) == -1 )
        {
          v8 = -2147418113;
          DoTraceMessage(
            2,
            "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
            &NLInternal::s_tracingPrefix,
            L"CModelDownloadComponent::GatherFilesExclusiveMode",
            L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2008)",
            -2147418113);
          goto LABEL_40;
        }
        if ( (FindFileData.dwFileAttributes & 0x10) != 0 )
        {
          v11 = CModelDownloadComponent::GatherFilesExclusiveMode(this, v23, 0x80u, a4, a5, a6);
          v8 = v11;
          if ( v11 < 0 )
          {
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::GatherFilesExclusiveMode",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2014)",
              v11);
            goto LABEL_40;
          }
        }
        else
        {
          FileW = (char *)CreateFileW(v23, 0x120116u, 0, 0, 3u, 0x200000u, 0);
          if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
          {
            v8 = -2147024891;
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::GatherFilesExclusiveMode",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2030)",
              -2147024891);
            goto LABEL_40;
          }
          if ( !LockFile(FileW, 0, 0, 0xFFFFFFFF, 0xFFFFFFFF) )
          {
            v8 = -2147024891;
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::GatherFilesExclusiveMode",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2037)",
              -2147024891);
            goto LABEL_40;
          }
          a4[*a6] = FileW;
          v13 = *a6;
          *a6 = v13 + 1;
          if ( (unsigned int)_o_wcscpy_s(&(*a5)[261 * v13], 261, v23) )
          {
            v8 = -2147418113;
            DoTraceMessage(
              2,
              "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
              &NLInternal::s_tracingPrefix,
              L"CModelDownloadComponent::GatherFilesExclusiveMode",
              L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2043)",
              -2147418113);
            goto LABEL_40;
          }
          v6 = a2;
        }
      }
    }
    while ( FindNextFileW(FirstFileW, &FindFileData) );
    LastError = GetLastError();
    if ( LastError != 18 && LastError )
    {
      v15 = GetLastError();
      v8 = v15;
      if ( v15 > 0 )
        v8 = (unsigned __int16)v15 | 0x80070000;
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::GatherFilesExclusiveMode",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2052)",
        v8);
LABEL_40:
      if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
        FindClose(FirstFileW);
      return v8;
    }
LABEL_32:
    v17 = *a6;
    if ( (unsigned int)v17 < 0x80 )
    {
      *a6 = v17 + 1;
      if ( (unsigned int)_o_wcscpy_s(&(*a5)[261 * v17], 261, v6) )
      {
        v8 = -2147418113;
        DoTraceMessage(
          2,
          "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
          &NLInternal::s_tracingPrefix,
          L"CModelDownloadComponent::GatherFilesExclusiveMode",
          L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2077)",
          -2147418113);
      }
    }
    else
    {
      v8 = -2147024882;
      DoTraceMessage(
        2,
        "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
        &NLInternal::s_tracingPrefix,
        L"CModelDownloadComponent::GatherFilesExclusiveMode",
        L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2071)",
        -2147024882);
    }
    goto LABEL_40;
  }
  v16 = GetLastError();
  if ( v16 == 2 || !v16 )
    goto LABEL_32;
  v18 = GetLastError();
  v8 = v18;
  if ( v18 > 0 )
    v8 = (unsigned __int16)v18 | 0x80070000;
  DoTraceMessage(
    2,
    "%Sfunction=%S, fileline=%S, hr=0x%08x\n",
    &NLInternal::s_tracingPrefix,
    L"CModelDownloadComponent::GatherFilesExclusiveMode",
    L"onecoreuap\\enduser\\nui\\onecore\\sapi\\sapi\\sharedlib\\modeldownloadcomponent.cpp(2065)",
    v8);
  return v8;
}

```

## disassembly

```asm
0x14000ee60  mov     [rsp-8+arg_10], rbx
0x14000ee65  push    rbp
0x14000ee66  push    rsi
0x14000ee67  push    rdi
0x14000ee68  push    r12
0x14000ee6a  push    r13
0x14000ee6c  push    r14
0x14000ee6e  push    r15
0x14000ee70  lea     rbp, [rsp-5D0h]
0x14000ee78  sub     rsp, 6D0h
0x14000ee7f  mov     rax, cs:__security_cookie
0x14000ee86  xor     rax, rsp
0x14000ee89  mov     [rbp+600h+var_40], rax
0x14000ee90  mov     r12, [rbp+600h+arg_20]
0x14000ee97  mov     r14, rdx
0x14000ee9a  mov     rsi, [rbp+600h+arg_28]
0x14000eea1  mov     ebx, 20Ah
0x14000eea6  mov     [rsp+700h+var_6B8], rdx
0x14000eeab  mov     r8d, ebx; Size
0x14000eeae  mov     [rsp+700h+var_6C0], rcx
0x14000eeb3  xor     edx, edx; Val
0x14000eeb5  lea     rcx, [rbp+600h+FileName]; void *
0x14000eebc  mov     r13, r9
0x14000eebf  call    memset_0
0x14000eec4  mov     r8d, ebx; Size
0x14000eec7  lea     rcx, [rbp+600h+var_460]; void *
0x14000eece  xor     edx, edx; Val
0x14000eed0  call    memset_0
0x14000eed5  xor     edx, edx; Val
0x14000eed7  lea     r8d, [rbx+46h]; Size
0x14000eedb  lea     rcx, [rsp+700h+FindFileData]; void *
0x14000eee0  call    memset_0
0x14000eee5  mov     edi, 105h
0x14000eeea  lea     rcx, [rbp+600h+FileName]
0x14000eef1  mov     edx, edi
0x14000eef3  mov     r8, r14
0x14000eef6  call    cs:__imp__o_wcscpy_s
0x14000eefc  xor     ebx, ebx
0x14000eefe  test    eax, eax
0x14000ef00  jz      short loc_14000EF3D
0x14000ef02  mov     eax, 8000FFFFh
0x14000ef07  mov     ebx, eax
0x14000ef09  mov     [rsp+700h+dwFlagsAndAttributes], eax
0x14000ef0d  lea     rax, aOnecoreuapEndu_103; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000ef14  mov     ecx, 2; int
0x14000ef19  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000ef20  mov     qword ptr [rsp+700h+dwCreationDisposition], rax
0x14000ef25  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000ef2c  lea     r9, aCmodeldownload_16; "CModelDownloadComponent::GatherFilesExc"...
0x14000ef33  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000ef38  jmp     loc_14000F24B
0x14000ef3d  lea     r8, asc_1400273E4; "\\*"
0x14000ef44  mov     rdx, rdi
0x14000ef47  lea     rcx, [rbp+600h+FileName]
0x14000ef4e  call    cs:__imp__o_wcscat_s
0x14000ef54  test    eax, eax
0x14000ef56  jz      short loc_14000EF6C
0x14000ef58  mov     eax, 8000FFFFh
0x14000ef5d  mov     ebx, eax
0x14000ef5f  mov     [rsp+700h+dwFlagsAndAttributes], eax
0x14000ef63  lea     rax, aOnecoreuapEndu_66; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000ef6a  jmp     short loc_14000EF14
0x14000ef6c  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x14000ef71  lea     rcx, [rbp+600h+FileName]; lpFileName
0x14000ef78  call    cs:__imp_FindFirstFileW
0x14000ef7e  mov     r15, rax
0x14000ef81  mov     edi, 2
0x14000ef86  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000ef8a  jz      loc_14000F18E
0x14000ef90  xor     ecx, ecx
0x14000ef92  cmp     [rsp+700h+FindFileData.cFileName], 2Eh ; '.'
0x14000ef98  movzx   eax, [rsp+700h+FindFileData.cFileName+2]
0x14000ef9d  jnz     short loc_14000EFC0
0x14000ef9f  test    ax, ax
0x14000efa2  jz      loc_14000F0C7
0x14000efa8  cmp     [rsp+700h+FindFileData.cFileName], 2Eh ; '.'
0x14000efae  jnz     short loc_14000EFC0
0x14000efb0  cmp     ax, 2Eh ; '.'
0x14000efb4  jnz     short loc_14000EFC0
0x14000efb6  cmp     [rbp+600h+FindFileData.cFileName+4], cx
0x14000efba  jz      loc_14000F0C7
0x14000efc0  cmp     dword ptr [rsi], 7Fh
0x14000efc3  jnb     loc_14000F177
0x14000efc9  lea     r9, [rsp+700h+FindFileData.cFileName]
0x14000efce  mov     r8, r14
0x14000efd1  lea     rdx, aSS; "%s\\%s"
0x14000efd8  lea     rcx, [rbp+600h+var_460]
0x14000efdf  call    ??$swprintf_s@$0BAF@@@YAHAEAY0BAF@GPEBGZZ; swprintf_s<261>(ushort (&)[261],ushort const *,...)
0x14000efe4  cmp     eax, 0FFFFFFFFh
0x14000efe7  jz      loc_14000F160
0x14000efed  test    byte ptr [rsp+700h+FindFileData.dwFileAttributes], 10h
0x14000eff2  jz      short loc_14000F032
0x14000eff4  mov     rcx, [rsp+700h+var_6C0]; this
0x14000eff9  lea     rdx, [rbp+600h+var_460]; unsigned __int16 *
0x14000f000  mov     qword ptr [rsp+700h+dwFlagsAndAttributes], rsi; unsigned int *
0x14000f005  mov     r9, r13; void **
0x14000f008  mov     r8d, 80h; unsigned int
0x14000f00e  mov     qword ptr [rsp+700h+dwCreationDisposition], r12; unsigned __int16 (*)[261]
0x14000f013  call    ?GatherFilesExclusiveMode@CModelDownloadComponent@@AEAAJPEBGKPEAPEAXQEAY0BAF@GPEAK@Z; CModelDownloadComponent::GatherFilesExclusiveMode(ushort const *,ulong,void * *,ushort (* const)[261],ulong *)
0x14000f018  mov     ebx, eax
0x14000f01a  test    eax, eax
0x14000f01c  jns     loc_14000F0C7
0x14000f022  mov     [rsp+700h+dwFlagsAndAttributes], eax
0x14000f026  lea     rax, aOnecoreuapEndu_117; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f02d  jmp     loc_14000F217
0x14000f032  mov     [rsp+700h+hTemplateFile], 0; hTemplateFile
0x14000f03b  lea     rcx, [rbp+600h+var_460]; lpFileName
0x14000f042  mov     [rsp+700h+dwFlagsAndAttributes], 200000h; dwFlagsAndAttributes
0x14000f04a  xor     r9d, r9d; lpSecurityAttributes
0x14000f04d  xor     r8d, r8d; dwShareMode
0x14000f050  mov     [rsp+700h+dwCreationDisposition], 3; dwCreationDisposition
0x14000f058  mov     edx, 120116h; dwDesiredAccess
0x14000f05d  call    cs:__imp_CreateFileW
0x14000f063  mov     r14, rax
0x14000f066  lea     rcx, [rax-1]
0x14000f06a  cmp     rcx, 0FFFFFFFFFFFFFFFDh
0x14000f06e  ja      loc_14000F149
0x14000f074  or      eax, 0FFFFFFFFh
0x14000f077  xor     r8d, r8d; dwFileOffsetHigh
0x14000f07a  mov     r9d, eax; nNumberOfBytesToLockLow
0x14000f07d  mov     [rsp+700h+dwCreationDisposition], eax; nNumberOfBytesToLockHigh
0x14000f081  xor     edx, edx; dwFileOffsetLow
0x14000f083  mov     rcx, r14; hFile
0x14000f086  call    cs:__imp_LockFile
0x14000f08c  test    eax, eax
0x14000f08e  jz      loc_14000F132
0x14000f094  mov     eax, [rsi]
0x14000f096  lea     r8, [rbp+600h+var_460]
0x14000f09d  mov     edx, 105h
0x14000f0a2  mov     [r13+rax*8+0], r14
0x14000f0a7  mov     ecx, [rsi]
0x14000f0a9  lea     eax, [rcx+1]
0x14000f0ac  imul    rcx, 20Ah
0x14000f0b3  mov     [rsi], eax
0x14000f0b5  add     rcx, r12
0x14000f0b8  call    cs:__imp__o_wcscpy_s
0x14000f0be  test    eax, eax
0x14000f0c0  jnz     short loc_14000F11B
0x14000f0c2  mov     r14, [rsp+700h+var_6B8]
0x14000f0c7  lea     rdx, [rsp+700h+FindFileData]; lpFindFileData
0x14000f0cc  mov     rcx, r15; hFindFile
0x14000f0cf  call    cs:__imp_FindNextFileW
0x14000f0d5  xor     ecx, ecx
0x14000f0d7  test    eax, eax
0x14000f0d9  jnz     loc_14000EF92
0x14000f0df  call    cs:__imp_GetLastError
0x14000f0e5  cmp     eax, 12h
0x14000f0e8  jz      loc_14000F19B
0x14000f0ee  test    eax, eax
0x14000f0f0  jz      loc_14000F19B
0x14000f0f6  call    cs:__imp_GetLastError
0x14000f0fc  mov     ebx, eax
0x14000f0fe  test    eax, eax
0x14000f100  jle     short loc_14000F10B
0x14000f102  movzx   ebx, ax
0x14000f105  or      ebx, 80070000h
0x14000f10b  mov     [rsp+700h+dwFlagsAndAttributes], ebx
0x14000f10f  lea     rax, aOnecoreuapEndu_79; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f116  jmp     loc_14000F217
0x14000f11b  mov     eax, 8000FFFFh
0x14000f120  mov     ebx, eax
0x14000f122  mov     [rsp+700h+dwFlagsAndAttributes], eax
0x14000f126  lea     rax, aOnecoreuapEndu_67; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f12d  jmp     loc_14000F217
0x14000f132  mov     eax, 80070005h
0x14000f137  mov     ebx, eax
0x14000f139  mov     [rsp+700h+dwFlagsAndAttributes], eax
0x14000f13d  lea     rax, aOnecoreuapEndu_34; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f144  jmp     loc_14000F217
0x14000f149  mov     eax, 80070005h
0x14000f14e  mov     ebx, eax
0x14000f150  mov     [rsp+700h+dwFlagsAndAttributes], eax
0x14000f154  lea     rax, aOnecoreuapEndu_33; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f15b  jmp     loc_14000F217
0x14000f160  mov     eax, 8000FFFFh
0x14000f165  mov     ebx, eax
0x14000f167  mov     [rsp+700h+dwFlagsAndAttributes], eax
0x14000f16b  lea     rax, aOnecoreuapEndu_15; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f172  jmp     loc_14000F217
0x14000f177  mov     eax, 8007000Eh
0x14000f17c  mov     ebx, eax
0x14000f17e  mov     [rsp+700h+dwFlagsAndAttributes], eax
0x14000f182  lea     rax, aOnecoreuapEndu_172; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f189  jmp     loc_14000F217
0x14000f18e  call    cs:__imp_GetLastError
0x14000f194  cmp     eax, edi
0x14000f196  jnz     short loc_14000F1B9
0x14000f198  xor     r13d, r13d
0x14000f19b  mov     ecx, [rsi]
0x14000f19d  cmp     ecx, 80h
0x14000f1a3  jb      short loc_14000F1E4
0x14000f1a5  mov     eax, 8007000Eh
0x14000f1aa  mov     ebx, eax
0x14000f1ac  mov     [rsp+700h+dwFlagsAndAttributes], eax
0x14000f1b0  lea     rax, aOnecoreuapEndu_40; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f1b7  jmp     short loc_14000F217
0x14000f1b9  test    eax, eax
0x14000f1bb  jz      short loc_14000F19B
0x14000f1bd  call    cs:__imp_GetLastError
0x14000f1c3  mov     ebx, eax
0x14000f1c5  test    eax, eax
0x14000f1c7  jle     short loc_14000F1D2
0x14000f1c9  movzx   ebx, ax
0x14000f1cc  or      ebx, 80070000h
0x14000f1d2  mov     [rsp+700h+dwFlagsAndAttributes], ebx
0x14000f1d6  lea     rax, aOnecoreuapEndu_96; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f1dd  mov     ecx, edi
0x14000f1df  jmp     loc_14000EF19
0x14000f1e4  lea     eax, [rcx+1]
0x14000f1e7  mov     r8, r14
0x14000f1ea  imul    rcx, 20Ah
0x14000f1f1  mov     edx, 105h
0x14000f1f6  mov     [rsi], eax
0x14000f1f8  add     rcx, r12
0x14000f1fb  call    cs:__imp__o_wcscpy_s
0x14000f201  test    eax, eax
0x14000f203  jz      short loc_14000F238
0x14000f205  mov     eax, 8000FFFFh
0x14000f20a  mov     ebx, eax
0x14000f20c  mov     [rsp+700h+dwFlagsAndAttributes], eax
0x14000f210  lea     rax, aOnecoreuapEndu_86; "onecoreuap\\enduser\\nui\\onecore\\sapi"...
0x14000f217  lea     r9, aCmodeldownload_16; "CModelDownloadComponent::GatherFilesExc"...
0x14000f21e  mov     qword ptr [rsp+700h+dwCreationDisposition], rax
0x14000f223  lea     r8, ?s_tracingPrefix@NLInternal@@3PAGA; ushort near * NLInternal::s_tracingPrefix
0x14000f22a  mov     ecx, edi; int
0x14000f22c  lea     rdx, aSfunctionSFile; "%Sfunction=%S, fileline=%S, hr=0x%08x\n"
0x14000f233  call    ?DoTraceMessage@@YAXHPEBDZZ; DoTraceMessage(int,char const *,...)
0x14000f238  lea     rax, [r15-1]
0x14000f23c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000f240  ja      short loc_14000F24B
0x14000f242  mov     rcx, r15; hFindFile
0x14000f245  call    cs:__imp_FindClose
0x14000f24b  mov     eax, ebx
0x14000f24d  mov     rcx, [rbp+600h+var_40]
0x14000f254  xor     rcx, rsp; StackCookie
0x14000f257  call    __security_check_cookie
0x14000f25c  mov     rbx, [rsp+700h+arg_10]
0x14000f264  add     rsp, 6D0h
0x14000f26b  pop     r15
0x14000f26d  pop     r14
0x14000f26f  pop     r13
0x14000f271  pop     r12
0x14000f273  pop     rdi
0x14000f274  pop     rsi
0x14000f275  pop     rbp
0x14000f276  retn
```
