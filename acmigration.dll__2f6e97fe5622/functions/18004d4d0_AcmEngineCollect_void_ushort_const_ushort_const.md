# AcmEngineCollect(void *,ushort const *,ushort const *)

- ea: `0x18004d4d0`
- end: `0x18004e1ba`
- name: `?AcmEngineCollect@@YAJPEAXPEBG1@Z`
- size: `3306`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName, const unsigned __int16 *Src, const unsigned __int16 *)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001cf0`
- `0x180002790`
- `0x180002874`
- `0x18000a654`
- `0x18004d4d0`
- `0x1800543c0`
- `0x180059f10`
- `0x180059fac`
- `0x180065144`
- `0x18006a010`

## import_xrefs

- `KERNEL32!HeapReAlloc` at `0x18004d8f4`
- `KERNEL32!HeapReAlloc` at `0x18004d9eb`
- `KERNEL32!HeapReAlloc` at `0x18004db23`
- `KERNEL32!HeapReAlloc` at `0x18004dc02`
- `KERNEL32!HeapReAlloc` at `0x18004dcef`
- `KERNEL32!HeapReAlloc` at `0x18004ddf2`
- `KERNEL32!HeapReAlloc` at `0x18004debb`
- `KERNEL32!HeapReAlloc` at `0x18004df9e`
- `KERNEL32!HeapReAlloc` at `0x18004d8f4`
- `KERNEL32!HeapReAlloc` at `0x18004d9eb`
- `KERNEL32!HeapReAlloc` at `0x18004db23`
- `KERNEL32!HeapReAlloc` at `0x18004dc02`
- `KERNEL32!HeapReAlloc` at `0x18004dcef`
- `KERNEL32!HeapReAlloc` at `0x18004ddf2`
- `KERNEL32!HeapReAlloc` at `0x18004debb`
- `KERNEL32!HeapReAlloc` at `0x18004df9e`
- `KERNEL32!WriteFile` at `0x18004e0cc`
- `KERNEL32!WriteFile` at `0x18004e0cc`
- `KERNEL32!DeleteFileW` at `0x18004e0ff`
- `KERNEL32!DeleteFileW` at `0x18004e0ff`
- `KERNEL32!CreateFileW` at `0x18004e08a`
- `KERNEL32!CreateFileW` at `0x18004e08a`
- `KERNEL32!GetProcessHeap` at `0x18004d5f2`
- `KERNEL32!GetProcessHeap` at `0x18004d5f2`
- `KERNEL32!HeapAlloc` at `0x18004d823`
- `KERNEL32!HeapAlloc` at `0x18004d8cc`
- `KERNEL32!HeapAlloc` at `0x18004d9c3`
- `KERNEL32!HeapAlloc` at `0x18004db00`
- `KERNEL32!HeapAlloc` at `0x18004dbdf`
- `KERNEL32!HeapAlloc` at `0x18004dccc`
- `KERNEL32!HeapAlloc` at `0x18004ddcf`
- `KERNEL32!HeapAlloc` at `0x18004de98`
- `KERNEL32!HeapAlloc` at `0x18004df7b`
- `KERNEL32!HeapAlloc` at `0x18004d823`
- `KERNEL32!HeapAlloc` at `0x18004d8cc`
- `KERNEL32!HeapAlloc` at `0x18004d9c3`
- `KERNEL32!HeapAlloc` at `0x18004db00`
- `KERNEL32!HeapAlloc` at `0x18004dbdf`
- `KERNEL32!HeapAlloc` at `0x18004dccc`
- `KERNEL32!HeapAlloc` at `0x18004ddcf`
- `KERNEL32!HeapAlloc` at `0x18004de98`
- `KERNEL32!HeapAlloc` at `0x18004df7b`
- `KERNEL32!CloseHandle` at `0x18004e0ed`
- `KERNEL32!CloseHandle` at `0x18004e0ed`
- `KERNEL32!GetLastError` at `0x18004e099`
- `KERNEL32!GetLastError` at `0x18004e099`
- `KERNEL32!HeapFree` at `0x18004e16a`
- `KERNEL32!HeapFree` at `0x18004e16a`

## string_xrefs

- `0x18004d656`: `Failed to ensure directory [%S] [%x]`
- `0x18004d6b5`: `Failed to construct shim working directory path [%x]`
- `0x18004da60`: `Failed to write shim name to state stream [%x]`
- `0x18004dd58`: `Failed to write commandline to state stream [%x]`
- `0x18004e007`: `Failed to write apply state to state stream [%x]`
- `0x18004e04c`: `Failed to make state file path [%x]`

## pseudocode

```c
__int64 __fastcall AcmEngineCollect(WCHAR *lpPathName, const unsigned __int16 *Src, unsigned __int16 *a3)
{
  const wchar_t *v3; // r13
  unsigned __int64 v6; // rbx
  __int64 v7; // rsi
  __int64 v8; // r14
  const wchar_t **v9; // rcx
  __int64 v10; // r14
  int LastError; // ebx
  HANDLE ProcessHeap; // r9
  unsigned __int64 v13; // rsi
  int v14; // ebx
  __int64 v15; // r8
  HRESULT v16; // eax
  const char *v17; // r9
  __int64 v18; // r8
  int v19; // ebx
  void *v20; // rbx
  int v21; // eax
  __int64 v22; // rax
  __int64 v23; // r14
  unsigned __int64 v24; // r15
  unsigned __int64 v25; // r13
  char *v26; // rax
  char *v27; // rbx
  unsigned __int64 v28; // rax
  char *v29; // rcx
  bool v30; // sf
  size_t v31; // rdx
  unsigned __int64 v32; // rbx
  SIZE_T v33; // r14
  char *v34; // rax
  char *v35; // r13
  int v36; // eax
  unsigned __int64 v37; // rax
  size_t v38; // r13
  unsigned __int64 v39; // rbx
  SIZE_T v40; // r14
  char *v41; // rax
  char *v42; // r12
  char *v43; // rcx
  int v44; // eax
  unsigned __int64 v45; // rcx
  __int64 v46; // rax
  unsigned int v47; // ecx
  unsigned __int64 v48; // r14
  unsigned __int64 v49; // rbx
  unsigned __int64 v50; // r13
  char *v51; // r12
  SIZE_T v52; // r15
  char *v53; // rax
  char *v54; // r13
  int v55; // eax
  bool v56; // sf
  size_t v57; // rax
  unsigned __int64 v58; // rbx
  SIZE_T v59; // r15
  char *v60; // rax
  char *v61; // r13
  unsigned __int64 v62; // r15
  unsigned __int64 v63; // rax
  unsigned __int64 v64; // rax
  size_t v65; // r13
  unsigned __int64 v66; // rbx
  SIZE_T v67; // r15
  char *v68; // rax
  __int64 v69; // rax
  unsigned __int64 v70; // rcx
  unsigned __int64 v71; // r14
  unsigned __int64 v72; // rbx
  char *v73; // r13
  unsigned __int64 v74; // rdx
  SIZE_T v75; // r15
  char *v76; // rax
  char *v77; // r12
  int v78; // eax
  bool v79; // sf
  unsigned __int64 v80; // rbx
  SIZE_T v81; // r15
  char *v82; // rax
  char *v83; // r12
  unsigned __int64 v84; // rcx
  unsigned __int64 v85; // rax
  unsigned __int64 v86; // rax
  unsigned __int64 v87; // rcx
  unsigned __int64 v88; // rbx
  SIZE_T v89; // r15
  char *v90; // rax
  char *v91; // r12
  __int64 v92; // rax
  unsigned __int64 v93; // rcx
  HANDLE FileW; // r14
  char *v95; // rbx
  DWORD v96; // r8d
  bool v97; // sf
  DWORD dwCreationDisposition[2]; // [rsp+20h] [rbp-4F8h]
  wchar_t *dwCreationDispositiona; // [rsp+20h] [rbp-4F8h]
  DWORD dwFlagsAndAttributes[2]; // [rsp+28h] [rbp-4F0h]
  DWORD dwFlagsAndAttributesa[2]; // [rsp+28h] [rbp-4F0h]
  char *lpMem; // [rsp+40h] [rbp-4D8h]
  unsigned __int64 v104; // [rsp+48h] [rbp-4D0h]
  size_t Size; // [rsp+50h] [rbp-4C8h]
  size_t Sizea; // [rsp+50h] [rbp-4C8h]
  size_t Sizeb; // [rsp+50h] [rbp-4C8h]
  size_t Sizec; // [rsp+50h] [rbp-4C8h]
  __int64 v109; // [rsp+58h] [rbp-4C0h] BYREF
  const unsigned __int16 *Srca; // [rsp+60h] [rbp-4B8h] BYREF
  int v111; // [rsp+68h] [rbp-4B0h] BYREF
  void *v112; // [rsp+70h] [rbp-4A8h]
  HANDLE hHeap[2]; // [rsp+78h] [rbp-4A0h]
  __int128 v114; // [rsp+88h] [rbp-490h]
  __int128 v115; // [rsp+98h] [rbp-480h]
  int v116; // [rsp+A8h] [rbp-470h]
  wchar_t pszDest[264]; // [rsp+B0h] [rbp-468h] BYREF
  wchar_t FileName[264]; // [rsp+2C0h] [rbp-258h] BYREF

  v3 = a3;
  Srca = Src;
  v112 = a3;
  memset_0(pszDest, 0, 0x208u);
  memset_0(FileName, 0, 0x208u);
  *(_OWORD *)hHeap = 0;
  v114 = 0;
  v115 = 0;
  v111 = 0;
  if ( !lpPathName || !Src )
  {
    AslLogCallPrintf(1, "AcmEngineCollect", 596, "Invalid arguments");
    return 2147942487LL;
  }
  v6 = *((_QWORD *)lpPathName + 66);
  if ( v6 && (v7 = *((_QWORD *)lpPathName + 65)) != 0 )
  {
    v8 = 0;
    while ( 1 )
    {
      v9 = *(const wchar_t ***)(v7 + 8 * v8);
      if ( v9 )
      {
        if ( !wcsicmp(*v9, Src) )
          break;
      }
      if ( ++v8 >= v6 )
        goto LABEL_9;
    }
    v10 = *(_QWORD *)(v7 + 8 * v8);
  }
  else
  {
LABEL_9:
    v10 = 0;
  }
  v109 = v10;
  if ( v10 )
  {
    ProcessHeap = GetProcessHeap();
    hHeap[0] = ProcessHeap;
    v13 = 0;
    hHeap[1] = 0;
    v104 = 0;
    *(_QWORD *)&v114 = 0;
    lpMem = 0;
    *((_QWORD *)&v115 + 1) = 0;
    if ( *(_QWORD *)(v10 + 16) )
    {
      v14 = AslPathEnsureDirectory(lpPathName);
      if ( v14 < 0 )
      {
        LastError = v14 | 0x10000000;
        dwFlagsAndAttributes[0] = LastError;
        dwCreationDispositiona = lpPathName;
        v15 = 633;
LABEL_16:
        AslLogCallPrintf(
          1,
          "AcmEngineCollect",
          v15,
          "Failed to ensure directory [%S] [%x]",
          dwCreationDispositiona,
          *(_QWORD *)dwFlagsAndAttributes);
        goto LABEL_240;
      }
      v16 = StringCchPrintfW(
              pszDest,
              0x104u,
              L"%s\\%s%d",
              lpPathName,
              L"MigShim",
              _InterlockedIncrement((volatile signed __int32 *)lpPathName + 134));
      LastError = v16;
      if ( v16 < 0 )
      {
        v17 = "Failed to construct shim working directory path [%x]";
        v18 = 649;
LABEL_19:
        dwCreationDisposition[0] = v16;
        AslLogCallPrintf(1, "AcmEngineCollect", v18, v17, *(_QWORD *)dwCreationDisposition);
        goto LABEL_240;
      }
      v19 = AslPathEnsureDirectory(pszDest);
      if ( v19 < 0 )
      {
        LastError = v19 | 0x10000000;
        dwFlagsAndAttributes[0] = LastError;
        dwCreationDispositiona = pszDest;
        v15 = 656;
        goto LABEL_16;
      }
      v20 = v112;
      v21 = (*(__int64 (__fastcall **)(int *, wchar_t *, void *, _QWORD))(v10 + 16))(
              &v111,
              pszDest,
              v112,
              *(_QWORD *)(v10 + 40));
      v116 = v21;
      if ( v21 < 0 )
      {
        if ( !v20 )
          v3 = L"null";
        AslLogCallPrintf(2, "AcmEngineCollect", 679, "Collect failed for shim [%S (%S)] [%x]", Src, v3, v21);
        AslPathRemoveDirectory(pszDest);
        LastError = 0;
        goto LABEL_243;
      }
      ProcessHeap = hHeap[0];
    }
    if ( v111 || !*(_QWORD *)(v10 + 24) )
    {
LABEL_239:
      LastError = 0;
      goto LABEL_240;
    }
    v22 = -1;
    do
      ++v22;
    while ( Src[v22] );
    v23 = (unsigned int)(2 * v22 + 2);
    v24 = 0;
    LODWORD(v109) = 1;
    HIDWORD(v109) = 2 * v22 + 2;
    LODWORD(Srca) = 0;
    v25 = 4096;
    v26 = (char *)HeapAlloc(ProcessHeap, 0, 0x1000u);
    v27 = v26;
    if ( v26 )
      memset_0(v26, 0, 0x1000u);
    if ( v27 )
    {
      v29 = v27;
      lpMem = v27;
      v104 = 4096;
      *(_QWORD *)v27 = v109;
      v13 = 8;
      v24 = 8;
      LastError = 0;
      v28 = 8;
    }
    else
    {
      LastError = -2147024882;
      v28 = 0;
      v29 = 0;
      v25 = 0;
    }
    v30 = LastError < 0;
    if ( LastError )
    {
LABEL_83:
      if ( v30 )
      {
        dwCreationDisposition[0] = LastError;
        AslLogCallPrintf(
          1,
          "AcmEngineCollect",
          696,
          "Failed to write shim name to state stream [%x]",
          *(_QWORD *)dwCreationDisposition);
        goto LABEL_240;
      }
      if ( !v112 )
        goto LABEL_156;
      v46 = -1;
      do
        ++v46;
      while ( *((_WORD *)v112 + v46) );
      v47 = 2 * v46 + 2;
      LODWORD(Srca) = v47;
      v48 = v13;
      LODWORD(Sizea) = 2;
      HIDWORD(Sizea) = v47;
      LODWORD(v109) = 0;
      if ( (v13 & 3) != 0 )
      {
        LastError = -2147024809;
LABEL_155:
        dwCreationDisposition[0] = LastError;
        AslLogCallPrintf(
          1,
          "AcmEngineCollect",
          706,
          "Failed to write commandline to state stream [%x]",
          *(_QWORD *)dwCreationDisposition);
        goto LABEL_240;
      }
      v49 = v13 + 8;
      if ( v13 + 8 < v13 )
        goto LABEL_152;
      v50 = v104;
      v51 = lpMem;
      if ( v49 > v104 )
      {
        if ( v13 + 4103 < v13 + 8 )
        {
          LastError = -2147483637;
          goto LABEL_108;
        }
        v52 = (v13 + 4103) & 0xFFFFFFFFFFFFF000uLL;
        if ( lpMem )
        {
          v54 = (char *)HeapReAlloc(hHeap[0], 0, lpMem, v52);
        }
        else
        {
          v53 = (char *)HeapAlloc(hHeap[0], 0, v52);
          v54 = v53;
          if ( v53 )
            memset_0(v53, 0, v52);
        }
        v47 = (unsigned int)Srca;
        if ( !v54 )
        {
          LastError = -2147024882;
          v50 = v104;
          goto LABEL_108;
        }
        v51 = v54;
        lpMem = v54;
        v50 = (v13 + 4103) & 0xFFFFFFFFFFFFF000uLL;
        v104 = v50;
      }
      *(_QWORD *)&v51[v13] = Sizea;
      if ( v49 < v13 )
      {
        v48 = -1;
        v55 = -2147024362;
        v49 = -1;
      }
      else
      {
        v48 = v13 + 8;
        v55 = 0;
      }
      if ( v55 < 0 )
        goto LABEL_148;
      if ( v13 <= v49 )
        v13 = v48;
      LastError = 0;
LABEL_108:
      v56 = LastError < 0;
      if ( LastError )
        goto LABEL_154;
      if ( !v47 )
        goto LABEL_110;
      v57 = v47;
      Sizeb = v47;
      v58 = v47 + v48;
      if ( v58 < v48 )
      {
        LastError = -2147024809;
LABEL_130:
        v56 = LastError < 0;
        if ( LastError )
          goto LABEL_154;
        v64 = v48 & 3;
        if ( (v48 & 3) == 0 )
        {
LABEL_153:
          v56 = LastError < 0;
LABEL_154:
          if ( v56 )
            goto LABEL_155;
LABEL_156:
          v71 = v13;
          LODWORD(v109) = 0;
          if ( (v13 & 3) != 0 )
          {
            LastError = -2147024809;
LABEL_221:
            dwCreationDisposition[0] = LastError;
            AslLogCallPrintf(
              1,
              "AcmEngineCollect",
              716,
              "Failed to write apply state to state stream [%x]",
              *(_QWORD *)dwCreationDisposition);
            goto LABEL_240;
          }
          v72 = v13 + 8;
          v73 = lpMem;
          if ( v13 + 8 < v13 )
            goto LABEL_218;
          v74 = v104;
          if ( v72 > v104 )
          {
            if ( v13 + 4103 < v13 + 8 )
            {
              LastError = -2147483637;
              goto LABEL_176;
            }
            v75 = (v13 + 4103) & 0xFFFFFFFFFFFFF000uLL;
            if ( lpMem )
            {
              v77 = (char *)HeapReAlloc(hHeap[0], 0, lpMem, v75);
            }
            else
            {
              v76 = (char *)HeapAlloc(hHeap[0], 0, v75);
              v77 = v76;
              if ( v76 )
                memset_0(v76, 0, v75);
            }
            if ( !v77 )
            {
              LastError = -2147024882;
              v74 = v104;
              goto LABEL_176;
            }
            v73 = v77;
            lpMem = v77;
            v74 = (v13 + 4103) & 0xFFFFFFFFFFFFF000uLL;
            v104 = v74;
          }
          *(_QWORD *)&v73[v13] = 0x400000003LL;
          if ( v72 < v13 )
          {
            v71 = -1;
            v72 = -1;
            v78 = -2147024362;
          }
          else
          {
            v71 = v13 + 8;
            v78 = 0;
          }
          if ( v78 < 0 )
            goto LABEL_214;
          if ( v13 <= v72 )
            v13 = v71;
          LastError = 0;
LABEL_176:
          v79 = LastError < 0;
          if ( LastError )
            goto LABEL_220;
          v80 = v71 + 4;
          if ( v71 + 4 < v71 )
          {
            LastError = -2147024809;
          }
          else
          {
            if ( v80 > v74 )
            {
              if ( v71 + 4099 < v71 + 4 )
              {
LABEL_191:
                LastError = -2147483637;
                goto LABEL_196;
              }
              v81 = (v71 + 4099) & 0xFFFFFFFFFFFFF000uLL;
              if ( v73 )
              {
                v83 = (char *)HeapReAlloc(hHeap[0], 0, v73, v81);
              }
              else
              {
                v82 = (char *)HeapAlloc(hHeap[0], 0, v81);
                v83 = v82;
                if ( v82 )
                  memset_0(v82, 0, v81);
              }
              if ( !v83 )
              {
                LastError = -2147024882;
                v74 = v104;
                goto LABEL_196;
              }
              v73 = v83;
              lpMem = v83;
              v74 = (v71 + 4099) & 0xFFFFFFFFFFFFF000uLL;
            }
            v84 = v71;
            *(_DWORD *)&v73[v71] = v111;
            if ( v80 < v71 )
            {
              v85 = -1;
              v71 = -1;
            }
            else
            {
              v71 += 4LL;
              v85 = v80;
            }
            if ( v80 < v84 )
              goto LABEL_191;
            if ( v13 <= v85 )
              v13 = v71;
            LastError = 0;
          }
LABEL_196:
          v79 = LastError < 0;
          if ( LastError )
            goto LABEL_220;
          v86 = v71 & 3;
          if ( (v71 & 3) == 0 )
          {
LABEL_219:
            v79 = LastError < 0;
LABEL_220:
            if ( v79 )
              goto LABEL_221;
            v16 = StringCchPrintfW(FileName, 0x104u, L"%s\\%s", pszDest, L"State");
            LastError = v16;
            if ( v16 < 0 )
            {
              v17 = "Failed to make state file path [%x]";
              v18 = 726;
              goto LABEL_19;
            }
            LODWORD(Srca) = 0;
            FileW = CreateFileW(FileName, 0xC0000000, 0, 0, 2u, 0x80u, 0);
            if ( FileW != (HANDLE)-1LL )
            {
              v95 = v73;
              if ( !v13 )
              {
LABEL_231:
                LastError = 0;
LABEL_232:
                if ( FileW != (HANDLE)-1LL )
                  CloseHandle(FileW);
                v97 = LastError < 0;
                if ( LastError )
                {
                  DeleteFileW(FileName);
                  v97 = LastError < 0;
                  if ( LastError > 0 )
                  {
                    LastError = (unsigned __int16)LastError | 0x80070000;
                    v97 = LastError < 0;
                  }
                }
                if ( v97 )
                {
                  dwFlagsAndAttributesa[0] = LastError;
                  AslLogCallPrintf(
                    1,
                    "AcmEngineCollect",
                    732,
                    "Failed to save shim state to file [%S] [%x]",
                    FileName,
                    *(_QWORD *)dwFlagsAndAttributesa);
                  goto LABEL_240;
                }
                goto LABEL_239;
              }
              while ( 1 )
              {
                v96 = v13;
                if ( v13 >= 0xFFFFFFFF )
                  v96 = -1;
                if ( !WriteFile(FileW, v95, v96, (LPDWORD)&Srca, 0) )
                  break;
                v95 += (unsigned int)Srca;
                v13 -= (unsigned int)Srca;
                if ( !v13 )
                  goto LABEL_231;
              }
            }
            LastError = GetLastError();
            goto LABEL_232;
          }
          v87 = 4 - v86;
          Sizec = 4 - v86;
          if ( 4 == v86 )
          {
LABEL_199:
            LastError = 0;
            goto LABEL_219;
          }
          v88 = v87 + v71;
          if ( v87 + v71 >= v71 )
          {
            if ( v88 > v74 )
            {
              if ( v88 + 4095 < v88 )
                goto LABEL_214;
              v89 = (v88 + 4095) & 0xFFFFFFFFFFFFF000uLL;
              if ( v73 )
              {
                v91 = (char *)HeapReAlloc(hHeap[0], 0, v73, v89);
              }
              else
              {
                v90 = (char *)HeapAlloc(hHeap[0], 0, v89);
                v91 = v90;
                if ( v90 )
                  memset_0(v90, 0, v89);
              }
              if ( !v91 )
              {
                LastError = -2147024882;
                goto LABEL_219;
              }
              v73 = v91;
              lpMem = v91;
            }
            memcpy_0(&v73[v71], &v109, Sizec);
            if ( v88 < v71 )
            {
              v93 = -1;
              v92 = -1;
            }
            else
            {
              v92 = v88;
              v93 = v88;
            }
            if ( v88 >= v71 )
            {
              if ( v13 <= v93 )
                v13 = v92;
              goto LABEL_199;
            }
LABEL_214:
            LastError = -2147483637;
            goto LABEL_219;
          }
LABEL_218:
          LastError = -2147024809;
          goto LABEL_219;
        }
        v65 = 4 - v64;
        if ( 4 == v64 )
        {
LABEL_133:
          LastError = 0;
          goto LABEL_153;
        }
        v66 = v48 + v65;
        if ( v48 + v65 >= v48 )
        {
          if ( v66 > v104 )
          {
            if ( v66 + 4095 < v66 )
              goto LABEL_148;
            v67 = (v66 + 4095) & 0xFFFFFFFFFFFFF000uLL;
            if ( v51 )
            {
              v51 = (char *)HeapReAlloc(hHeap[0], 0, v51, v67);
            }
            else
            {
              v68 = (char *)HeapAlloc(hHeap[0], 0, v67);
              v51 = v68;
              if ( v68 )
                memset_0(v68, 0, v67);
            }
            if ( !v51 )
            {
              LastError = -2147024882;
              goto LABEL_153;
            }
            lpMem = v51;
            v104 = (v66 + 4095) & 0xFFFFFFFFFFFFF000uLL;
          }
          memcpy_0(&v51[v48], &v109, v65);
          if ( v66 < v48 )
          {
            v70 = -1;
            v69 = -1;
          }
          else
          {
            v69 = v48 + v65;
            v70 = v48 + v65;
          }
          if ( v66 >= v48 )
          {
            if ( v13 <= v70 )
              v13 = v69;
            goto LABEL_133;
          }
LABEL_148:
          LastError = -2147483637;
          goto LABEL_153;
        }
LABEL_152:
        LastError = -2147024809;
        goto LABEL_153;
      }
      if ( v58 > v50 )
      {
        if ( v58 + 4095 < v58 )
        {
LABEL_125:
          LastError = -2147483637;
          goto LABEL_130;
        }
        v59 = (v58 + 4095) & 0xFFFFFFFFFFFFF000uLL;
        if ( v51 )
        {
          v61 = (char *)HeapReAlloc(hHeap[0], 0, v51, v59);
        }
        else
        {
          v60 = (char *)HeapAlloc(hHeap[0], 0, v59);
          v61 = v60;
          if ( v60 )
            memset_0(v60, 0, v59);
        }
        if ( !v61 )
        {
          LastError = -2147024882;
          goto LABEL_130;
        }
        v51 = v61;
        lpMem = v61;
        v104 = (v58 + 4095) & 0xFFFFFFFFFFFFF000uLL;
        v57 = Sizeb;
      }
      v62 = v48;
      memcpy_0(&v51[v48], v112, v57);
      if ( v58 < v48 )
      {
        v63 = -1;
        v48 = -1;
      }
      else
      {
        v48 = v58;
        v63 = v58;
      }
      if ( v58 >= v62 )
      {
        if ( v13 <= v63 )
          v13 = v48;
LABEL_110:
        LastError = 0;
        goto LABEL_130;
      }
      goto LABEL_125;
    }
    if ( !(_DWORD)v23 )
      goto LABEL_38;
    v31 = (unsigned int)v23;
    Size = (unsigned int)v23;
    v32 = v23 + v28;
    if ( v23 + v28 < v28 )
    {
      LastError = -2147024809;
LABEL_58:
      v30 = LastError < 0;
      if ( LastError )
        goto LABEL_83;
      v37 = v24 & 3;
      if ( (v24 & 3) == 0 )
        goto LABEL_82;
      v38 = 4 - v37;
      if ( 4 == v37 )
        goto LABEL_61;
      v39 = v24 + v38;
      if ( v24 + v38 < v24 )
      {
        LastError = -2147024809;
        goto LABEL_82;
      }
      if ( v39 <= v104 )
      {
        v43 = lpMem;
      }
      else
      {
        if ( v39 + 4095 < v39 )
          goto LABEL_77;
        v40 = (v39 + 4095) & 0xFFFFFFFFFFFFF000uLL;
        if ( lpMem )
        {
          v42 = (char *)HeapReAlloc(hHeap[0], 0, lpMem, v40);
        }
        else
        {
          v41 = (char *)HeapAlloc(hHeap[0], 0, v40);
          v42 = v41;
          if ( v41 )
            memset_0(v41, 0, v40);
        }
        if ( !v42 )
        {
          LastError = -2147024882;
          goto LABEL_82;
        }
        v43 = v42;
        lpMem = v42;
        v104 = (v39 + 4095) & 0xFFFFFFFFFFFFF000uLL;
      }
      memcpy_0(&v43[v24], &Srca, v38);
      if ( v39 < v24 )
      {
        v45 = -1;
        v39 = -1;
        v44 = -2147024362;
      }
      else
      {
        v44 = 0;
        v45 = v24 + v38;
      }
      if ( v44 >= 0 )
      {
        if ( v13 <= v45 )
          v13 = v39;
LABEL_61:
        LastError = 0;
LABEL_82:
        v30 = LastError < 0;
        goto LABEL_83;
      }
LABEL_77:
      LastError = -2147483637;
      goto LABEL_82;
    }
    if ( v32 > v25 )
    {
      if ( v32 + 4095 < v32 )
      {
LABEL_53:
        LastError = -2147483637;
        goto LABEL_58;
      }
      v33 = (v32 + 4095) & 0xFFFFFFFFFFFFF000uLL;
      if ( v29 )
      {
        v35 = (char *)HeapReAlloc(hHeap[0], 0, v29, v33);
      }
      else
      {
        v34 = (char *)HeapAlloc(hHeap[0], 0, v33);
        v35 = v34;
        if ( v34 )
          memset_0(v34, 0, v33);
      }
      if ( !v35 )
      {
        LastError = -2147024882;
        goto LABEL_58;
      }
      v29 = v35;
      lpMem = v35;
      v104 = (v32 + 4095) & 0xFFFFFFFFFFFFF000uLL;
      v31 = Size;
    }
    memcpy_0(&v29[v24], Src, v31);
    if ( v32 < v24 )
    {
      v24 = -1;
      v36 = -2147024362;
      v32 = -1;
    }
    else
    {
      v24 = v32;
      v36 = 0;
    }
    if ( v36 >= 0 )
    {
      if ( v13 <= v32 )
        v13 = v24;
LABEL_38:
      LastError = 0;
      goto LABEL_58;
    }
    goto LABEL_53;
  }
  LastError = -2147023728;
  AslLogCallPrintf(1, "AcmEngineCollect", 607, "Failed to find shim [%S]", Src);
  lpMem = (char *)*((_QWORD *)&v115 + 1);
LABEL_240:
  if ( LastError < 0 && pszDest[0] )
    AslPathRemoveDirectory(pszDest);
LABEL_243:
  if ( lpMem )
    HeapFree(hHeap[0], 0, lpMem);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x18004d4d0  push    rbx
0x18004d4d2  push    rsi
0x18004d4d3  push    rdi
0x18004d4d4  push    r12
0x18004d4d6  push    r13
0x18004d4d8  push    r14
0x18004d4da  push    r15
0x18004d4dc  sub     rsp, 4E0h
0x18004d4e3  mov     rax, cs:__security_cookie
0x18004d4ea  xor     rax, rsp
0x18004d4ed  mov     [rsp+518h+var_48], rax
0x18004d4f5  mov     r13, r8
0x18004d4f8  mov     r12, rdx
0x18004d4fb  mov     r15, rcx
0x18004d4fe  mov     [rsp+518h+Size], r8
0x18004d503  mov     [rsp+518h+Src], rdx
0x18004d508  mov     [rsp+518h+var_4A8], r8
0x18004d50d  mov     ebx, 208h
0x18004d512  mov     r8d, ebx; Size
0x18004d515  xor     edx, edx; Val
0x18004d517  lea     rcx, [rsp+518h+pszDest]; void *
0x18004d51f  call    memset_0
0x18004d524  mov     r8d, ebx; Size
0x18004d527  xor     edx, edx; Val
0x18004d529  lea     rcx, [rsp+518h+FileName]; void *
0x18004d531  call    memset_0
0x18004d536  xorps   xmm0, xmm0
0x18004d539  movups  xmmword ptr [rsp+518h+hHeap], xmm0
0x18004d53e  movups  [rsp+518h+var_490], xmm0
0x18004d546  movups  [rsp+518h+var_480], xmm0
0x18004d54e  xor     edi, edi
0x18004d550  mov     [rsp+518h+var_4B0], edi
0x18004d554  test    r15, r15
0x18004d557  jz      loc_18004E174
0x18004d55d  test    r12, r12
0x18004d560  jz      loc_18004E174
0x18004d566  mov     rbx, [r15+210h]
0x18004d56d  test    rbx, rbx
0x18004d570  jz      short loc_18004D5A6
0x18004d572  mov     rsi, [r15+208h]
0x18004d579  test    rsi, rsi
0x18004d57c  jz      short loc_18004D5A6
0x18004d57e  mov     r14d, edi
0x18004d581  test    rbx, rbx
0x18004d584  jz      short loc_18004D5A6
0x18004d586  mov     rcx, [rsi+r14*8]
0x18004d58a  test    rcx, rcx
0x18004d58d  jz      short loc_18004D59E
0x18004d58f  mov     rdx, r12; String2
0x18004d592  mov     rcx, [rcx]; String1
0x18004d595  call    _wcsicmp
0x18004d59a  test    eax, eax
0x18004d59c  jz      short loc_18004D5EC
0x18004d59e  inc     r14
0x18004d5a1  cmp     r14, rbx
0x18004d5a4  jb      short loc_18004D586
0x18004d5a6  mov     r14, rdi
0x18004d5a9  mov     [rsp+518h+var_4C0], r14
0x18004d5ae  test    r14, r14
0x18004d5b1  jnz     short loc_18004D5F2
0x18004d5b3  mov     ebx, 80070490h
0x18004d5b8  mov     qword ptr [rsp+518h+dwCreationDisposition], r12
0x18004d5bd  lea     r9, aFailedToFindSh; "Failed to find shim [%S]"
0x18004d5c4  mov     r8d, 25Fh
0x18004d5ca  lea     rdx, aAcmenginecolle_0; "AcmEngineCollect"
0x18004d5d1  lea     ecx, [r14+1]
0x18004d5d5  call    AslLogCallPrintf
0x18004d5da  mov     r13, qword ptr [rsp+518h+var_480+8]
0x18004d5e2  mov     [rsp+518h+lpMem], r13
0x18004d5e7  jmp     loc_18004E13B
0x18004d5ec  mov     r14, [rsi+r14*8]
0x18004d5f0  jmp     short loc_18004D5A9
0x18004d5f2  call    cs:__imp_GetProcessHeap
0x18004d5f8  mov     r9, rax
0x18004d5fb  mov     [rsp+518h+hHeap], rax
0x18004d600  mov     rsi, rdi
0x18004d603  mov     [rsp+518h+hHeap+8], rdi
0x18004d60b  mov     rdx, rdi
0x18004d60e  mov     [rsp+518h+var_4D0], rdx
0x18004d613  mov     qword ptr [rsp+518h+var_490], rdx
0x18004d61b  mov     rcx, rdi
0x18004d61e  mov     [rsp+518h+lpMem], rcx
0x18004d623  mov     qword ptr [rsp+518h+var_480+8], rcx
0x18004d62b  cmp     [r14+10h], rdi
0x18004d62f  jz      loc_18004D7D7
0x18004d635  mov     rcx, r15; lpPathName
0x18004d638  call    AslPathEnsureDirectory
0x18004d63d  mov     ebx, eax
0x18004d63f  test    eax, eax
0x18004d641  jns     short loc_18004D673
0x18004d643  bts     ebx, 1Ch
0x18004d647  mov     [rsp+518h+dwFlagsAndAttributes], ebx
0x18004d64b  mov     qword ptr [rsp+518h+dwCreationDisposition], r15
0x18004d650  mov     r8d, 279h
0x18004d656  lea     r9, aFailedToEnsure_0; "Failed to ensure directory [%S] [%x]"
0x18004d65d  lea     rdx, aAcmenginecolle_0; "AcmEngineCollect"
0x18004d664  mov     ecx, 1
0x18004d669  call    AslLogCallPrintf
0x18004d66e  jmp     loc_18004E13B
0x18004d673  mov     eax, 1
0x18004d678  lock xadd [r15+218h], eax
0x18004d681  inc     eax
0x18004d683  mov     [rsp+518h+dwFlagsAndAttributes], eax
0x18004d687  lea     rax, aMigshim; "MigShim"
0x18004d68e  mov     qword ptr [rsp+518h+dwCreationDisposition], rax
0x18004d693  mov     r9, r15
0x18004d696  lea     r8, aSSD; "%s\\%s%d"
0x18004d69d  mov     edx, 104h; cchDest
0x18004d6a2  lea     rcx, [rsp+518h+pszDest]; pszDest
0x18004d6aa  call    StringCchPrintfW
0x18004d6af  mov     ebx, eax
0x18004d6b1  test    eax, eax
0x18004d6b3  jns     short loc_18004D6DC
0x18004d6b5  lea     r9, aFailedToConstr_0; "Failed to construct shim working direct"...
0x18004d6bc  mov     r8d, 289h
0x18004d6c2  mov     [rsp+518h+dwCreationDisposition], eax
0x18004d6c6  lea     rdx, aAcmenginecolle_0; "AcmEngineCollect"
0x18004d6cd  mov     ecx, 1
0x18004d6d2  call    AslLogCallPrintf
0x18004d6d7  jmp     loc_18004E13B
0x18004d6dc  mov     edx, 1
0x18004d6e1  lea     rcx, [rsp+518h+pszDest]; lpPathName
0x18004d6e9  call    AslPathEnsureDirectory
0x18004d6ee  mov     ebx, eax
0x18004d6f0  test    eax, eax
0x18004d6f2  jns     short loc_18004D714
0x18004d6f4  bts     ebx, 1Ch
0x18004d6f8  mov     [rsp+518h+dwFlagsAndAttributes], ebx
0x18004d6fc  lea     rax, [rsp+518h+pszDest]
0x18004d704  mov     qword ptr [rsp+518h+dwCreationDisposition], rax
0x18004d709  mov     r8d, 290h
0x18004d70f  jmp     loc_18004D656
0x18004d714  mov     r9, [r14+28h]
0x18004d718  mov     rbx, [rsp+518h+var_4A8]
0x18004d71d  mov     r8, rbx
0x18004d720  lea     rdx, [rsp+518h+pszDest]
0x18004d728  lea     rcx, [rsp+518h+var_4B0]
0x18004d72d  mov     rax, [r14+10h]
0x18004d731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004d736  mov     [rsp+518h+var_470], eax
0x18004d73d  jmp     short loc_18004D780
0x18004d73f  bts     eax, 1Ch
0x18004d743  mov     [rsp+518h+var_470], eax
0x18004d74a  xor     edi, edi
0x18004d74c  mov     rcx, qword ptr [rsp+518h+var_480+8]
0x18004d754  mov     [rsp+518h+lpMem], rcx
0x18004d759  mov     rdx, qword ptr [rsp+518h+var_490]
0x18004d761  mov     [rsp+518h+var_4D0], rdx
0x18004d766  mov     rsi, [rsp+518h+hHeap+8]
0x18004d76e  mov     r14, [rsp+518h+var_4C0]
0x18004d773  mov     r13, [rsp+518h+Size]
0x18004d778  mov     r12, [rsp+518h+Src]
0x18004d77d  mov     rbx, r13
0x18004d780  test    eax, eax
0x18004d782  jns     short loc_18004D7D2
0x18004d784  lea     rcx, aNull; "null"
0x18004d78b  test    rbx, rbx
0x18004d78e  cmovz   r13, rcx
0x18004d792  mov     dword ptr [rsp+518h+hTemplateFile], eax
0x18004d796  mov     qword ptr [rsp+518h+dwFlagsAndAttributes], r13
0x18004d79b  mov     qword ptr [rsp+518h+dwCreationDisposition], r12
0x18004d7a0  lea     r9, aCollectFailedF; "Collect failed for shim [%S (%S)] [%x]"
0x18004d7a7  mov     r8d, 2A7h
0x18004d7ad  lea     rdx, aAcmenginecolle_0; "AcmEngineCollect"
0x18004d7b4  mov     ecx, 2
0x18004d7b9  call    AslLogCallPrintf
0x18004d7be  lea     rcx, [rsp+518h+pszDest]
0x18004d7c6  call    AslPathRemoveDirectory
0x18004d7cb  mov     ebx, edi
0x18004d7cd  jmp     loc_18004E156
0x18004d7d2  mov     r9, [rsp+518h+hHeap]
0x18004d7d7  cmp     [rsp+518h+var_4B0], edi
0x18004d7db  jnz     loc_18004E139
0x18004d7e1  cmp     [r14+18h], rdi
0x18004d7e5  jz      loc_18004E139
0x18004d7eb  or      rax, 0FFFFFFFFFFFFFFFFh
0x18004d7ef  inc     rax
0x18004d7f2  cmp     [r12+rax*2], di
0x18004d7f7  jnz     short loc_18004D7EF
0x18004d7f9  lea     r14d, ds:2[rax*2]
0x18004d801  mov     r15, rdi
0x18004d804  mov     dword ptr [rsp+518h+var_4C0], 1
0x18004d80c  mov     dword ptr [rsp+518h+var_4C0+4], r14d
0x18004d811  mov     dword ptr [rsp+518h+Src], edi
0x18004d815  mov     r13d, 1000h
0x18004d81b  mov     r8d, r13d; dwBytes
0x18004d81e  xor     edx, edx; dwFlags
0x18004d820  mov     rcx, r9; hHeap
0x18004d823  call    cs:__imp_HeapAlloc
0x18004d829  mov     rbx, rax
0x18004d82c  test    rax, rax
0x18004d82f  jz      short loc_18004D83E
0x18004d831  mov     r8d, r13d; Size
0x18004d834  xor     edx, edx; Val
0x18004d836  mov     rcx, rax; void *
0x18004d839  call    memset_0
0x18004d83e  test    rbx, rbx
0x18004d841  jnz     short loc_18004D857
0x18004d843  mov     ebx, 8007000Eh
0x18004d848  mov     rax, rdi
0x18004d84b  mov     rcx, [rsp+518h+lpMem]
0x18004d850  mov     r13, [rsp+518h+var_4D0]
0x18004d855  jmp     short loc_18004D878
0x18004d857  mov     rcx, rbx
0x18004d85a  mov     [rsp+518h+lpMem], rbx
0x18004d85f  mov     [rsp+518h+var_4D0], r13
0x18004d864  mov     rax, [rsp+518h+var_4C0]
0x18004d869  mov     [rbx], rax
0x18004d86c  mov     esi, 8
0x18004d871  mov     r15d, esi
0x18004d874  mov     ebx, edi
0x18004d876  mov     eax, esi
0x18004d878  test    ebx, ebx
0x18004d87a  jnz     loc_18004DA5A
0x18004d880  test    r14d, r14d
0x18004d883  jnz     short loc_18004D88C
0x18004d885  mov     ebx, edi
0x18004d887  jmp     loc_18004D960
0x18004d88c  mov     edx, r14d
0x18004d88f  mov     [rsp+518h+Size], rdx
0x18004d894  lea     rbx, [r14+rax]
0x18004d898  cmp     rbx, rax
0x18004d89b  jb      loc_18004D95B
0x18004d8a1  cmp     rbx, r13
0x18004d8a4  jbe     short loc_18004D91B
0x18004d8a6  lea     r14, [rbx+0FFFh]
0x18004d8ad  cmp     r14, rbx
0x18004d8b0  jb      loc_18004D948
0x18004d8b6  and     r14, 0FFFFFFFFFFFFF000h
0x18004d8bd  xor     edx, edx; dwFlags
0x18004d8bf  test    rcx, rcx
0x18004d8c2  jnz     short loc_18004D8E9
0x18004d8c4  mov     r8, r14; dwBytes
0x18004d8c7  mov     rcx, [rsp+518h+hHeap]; hHeap
0x18004d8cc  call    cs:__imp_HeapAlloc
0x18004d8d2  mov     r13, rax
0x18004d8d5  test    rax, rax
0x18004d8d8  jz      short loc_18004D8FD
0x18004d8da  mov     r8, r14; Size
0x18004d8dd  xor     edx, edx; Val
0x18004d8df  mov     rcx, rax; void *
0x18004d8e2  call    memset_0
0x18004d8e7  jmp     short loc_18004D8FD
0x18004d8e9  mov     r9, r14; dwBytes
0x18004d8ec  mov     r8, rcx; lpMem
0x18004d8ef  mov     rcx, [rsp+518h+hHeap]; hHeap
0x18004d8f4  call    cs:__imp_HeapReAlloc
0x18004d8fa  mov     r13, rax
0x18004d8fd  test    r13, r13
0x18004d900  jnz     short loc_18004D909
0x18004d902  mov     ebx, 8007000Eh
0x18004d907  jmp     short loc_18004D960
0x18004d909  mov     rcx, r13
0x18004d90c  mov     [rsp+518h+lpMem], rcx
0x18004d911  mov     [rsp+518h+var_4D0], r14
0x18004d916  mov     rdx, [rsp+518h+Size]
0x18004d91b  add     rcx, r15; void *
0x18004d91e  mov     r8, rdx; Size
0x18004d921  mov     rdx, r12; Src
0x18004d924  call    memcpy_0
0x18004d929  cmp     rbx, r15
0x18004d92c  jb      short loc_18004D935
0x18004d92e  mov     r15, rbx
0x18004d931  mov     eax, edi
0x18004d933  jmp     short loc_18004D944
0x18004d935  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18004d939  mov     r15, rcx
0x18004d93c  mov     eax, 80070216h
0x18004d941  mov     rbx, rcx
0x18004d944  test    eax, eax
0x18004d946  jns     short loc_18004D94F
0x18004d948  mov     ebx, 8000000Bh
0x18004d94d  jmp     short loc_18004D960
0x18004d94f  cmp     rsi, rbx
0x18004d952  cmovbe  rsi, r15
0x18004d956  jmp     loc_18004D885
0x18004d95b  mov     ebx, 80070057h
0x18004d960  test    ebx, ebx
0x18004d962  jnz     loc_18004DA5A
0x18004d968  mov     rax, r15
0x18004d96b  and     eax, 3
0x18004d96e  jz      loc_18004DA58
0x18004d974  lea     r13d, [rbx+4]
0x18004d978  sub     r13, rax
0x18004d97b  jnz     short loc_18004D984
0x18004d97d  mov     ebx, edi
0x18004d97f  jmp     loc_18004DA58
0x18004d984  lea     rbx, [r15+r13]
0x18004d988  cmp     rbx, r15
0x18004d98b  jb      loc_18004DA53
0x18004d991  cmp     rbx, [rsp+518h+var_4D0]
0x18004d996  jbe     short loc_18004DA0F
0x18004d998  lea     r14, [rbx+0FFFh]
0x18004d99f  cmp     r14, rbx
0x18004d9a2  jb      loc_18004DA40
0x18004d9a8  and     r14, 0FFFFFFFFFFFFF000h
0x18004d9af  mov     rcx, [rsp+518h+lpMem]
0x18004d9b4  xor     edx, edx; dwFlags
0x18004d9b6  test    rcx, rcx
0x18004d9b9  jnz     short loc_18004D9E0
  ... truncated ...
```
