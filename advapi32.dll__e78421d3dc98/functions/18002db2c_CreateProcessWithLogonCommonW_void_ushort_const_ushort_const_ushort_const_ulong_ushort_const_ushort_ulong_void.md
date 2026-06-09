# CreateProcessWithLogonCommonW(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort *,ulong,void *,ushort const *,_STARTUPINFOW *,_PROCESS_INFORMATION *)

- ea: `0x18002db2c`
- end: `0x18002e997`
- name: `?CreateProcessWithLogonCommonW@@YAHPEAXPEBG11K1PEAGK01PEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `3691`
- prototype: `int(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int16 *, unsigned int, void *, const unsigned __int16 *, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18002dac0`
- `0x180051b20`

## callees

- `0x180017554`
- `0x18002b8c0`
- `0x18002cad0`
- `0x18002cb0c`
- `0x18002db2c`
- `0x180033c30`
- `0x1800345d0`
- `0x180034e30`
- `0x1800380c0`
- `0x18003cff4`
- `0x18006505a`
- `0x180065090`

## import_xrefs

- `msvcrt!wcschr` at `0x18002e155`
- `msvcrt!wcschr` at `0x18002e155`
- `ntdll!RtlNtStatusToDosError` at `0x18002dd20`
- `ntdll!RtlNtStatusToDosError` at `0x18002dd20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002e798`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002de42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18002de42`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e472`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18002e472`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x18002de4b`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x18002de4b`
- `KERNEL32!GetLastError` at `0x18002e258`
- `KERNEL32!GetLastError` at `0x18002e883`
- `KERNEL32!GetLastError` at `0x18002e258`
- `KERNEL32!GetLastError` at `0x18002e883`
- `KERNEL32!CloseHandle` at `0x18002e413`
- `KERNEL32!CloseHandle` at `0x18002e413`
- `KERNEL32!CreateFileW` at `0x18002e3e3`
- `KERNEL32!CreateFileW` at `0x18002e3e3`
- `KERNEL32!HeapAlloc` at `0x18002dcc3`
- `KERNEL32!HeapAlloc` at `0x18002de6c`
- `KERNEL32!HeapAlloc` at `0x18002ded2`
- `KERNEL32!HeapAlloc` at `0x18002df9a`
- `KERNEL32!HeapAlloc` at `0x18002dfb8`
- `KERNEL32!HeapAlloc` at `0x18002dcc3`
- `KERNEL32!HeapAlloc` at `0x18002de6c`
- `KERNEL32!HeapAlloc` at `0x18002ded2`
- `KERNEL32!HeapAlloc` at `0x18002df9a`
- `KERNEL32!HeapAlloc` at `0x18002dfb8`
- `KERNEL32!GetProcessHeap` at `0x18002dbe3`
- `KERNEL32!GetProcessHeap` at `0x18002dbe3`
- `KERNEL32!HeapFree` at `0x18002e22d`
- `KERNEL32!HeapFree` at `0x18002e23f`
- `KERNEL32!HeapFree` at `0x18002e313`
- `KERNEL32!HeapFree` at `0x18002e326`
- `KERNEL32!HeapFree` at `0x18002e336`
- `KERNEL32!HeapFree` at `0x18002e448`
- `KERNEL32!HeapFree` at `0x18002e920`
- `KERNEL32!HeapFree` at `0x18002e938`
- `KERNEL32!HeapFree` at `0x18002e94b`
- `KERNEL32!HeapFree` at `0x18002e963`
- `KERNEL32!HeapFree` at `0x1800655fe`
- `KERNEL32!HeapFree` at `0x18006561e`
- `KERNEL32!HeapFree` at `0x180065634`
- `KERNEL32!HeapFree` at `0x18006564a`
- `KERNEL32!HeapFree` at `0x18002e22d`
- `KERNEL32!HeapFree` at `0x18002e23f`
- `KERNEL32!HeapFree` at `0x18002e313`
- `KERNEL32!HeapFree` at `0x18002e326`
- `KERNEL32!HeapFree` at `0x18002e336`
- `KERNEL32!HeapFree` at `0x18002e448`
- `KERNEL32!HeapFree` at `0x18002e920`
- `KERNEL32!HeapFree` at `0x18002e938`
- `KERNEL32!HeapFree` at `0x18002e94b`
- `KERNEL32!HeapFree` at `0x18002e963`
- `KERNEL32!HeapFree` at `0x1800655fe`
- `KERNEL32!HeapFree` at `0x18006561e`
- `KERNEL32!HeapFree` at `0x180065634`
- `KERNEL32!HeapFree` at `0x18006564a`
- `KERNEL32!SearchPathW` at `0x18002e0e5`
- `KERNEL32!SearchPathW` at `0x18002e0e5`
- `KERNEL32!GetFullPathNameW` at `0x18002e3ba`
- `KERNEL32!GetFullPathNameW` at `0x18002e3ba`
- `KERNEL32!GetFileAttributesW` at `0x18002e0fd`
- `KERNEL32!GetFileAttributesW` at `0x18002e0fd`
- `KERNEL32!SetLastError` at `0x18002e250`
- `KERNEL32!SetLastError` at `0x18002e759`
- `KERNEL32!SetLastError` at `0x18002e96b`
- `KERNEL32!SetLastError` at `0x180065654`
- `KERNEL32!SetLastError` at `0x18002e250`
- `KERNEL32!SetLastError` at `0x18002e759`
- `KERNEL32!SetLastError` at `0x18002e96b`
- `KERNEL32!SetLastError` at `0x180065654`
- `CRYPTBASE!SystemFunction040` at `0x18002dd12`
- `CRYPTBASE!SystemFunction040` at `0x18002dd12`
- `USER32!GetThreadDesktop` at `0x18002e7a0`
- `USER32!GetThreadDesktop` at `0x18002e7a0`
- `USER32!GetUserObjectInformationW` at `0x18002e7ed`
- `USER32!GetUserObjectInformationW` at `0x18002e851`
- `USER32!GetUserObjectInformationW` at `0x18002e7ed`
- `USER32!GetUserObjectInformationW` at `0x18002e851`
- `USER32!GetProcessWindowStation` at `0x18002e786`
- `USER32!GetProcessWindowStation` at `0x18002e786`

## pseudocode

```c
_BOOL8 __fastcall CreateProcessWithLogonCommonW(
        void *a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        const unsigned __int16 *a4,
        unsigned int a5,
        const unsigned __int16 *a6,
        unsigned __int16 *a7,
        unsigned int a8,
        void *a9,
        unsigned __int16 *a10,
        struct _STARTUPINFOW *a11,
        struct _PROCESS_INFORMATION *a12)
{
  unsigned __int16 *v14; // r13
  int v15; // r14d
  int LastError; // ebx
  HANDLE ProcessHeap; // r12
  __int64 v18; // rax
  unsigned int v19; // ecx
  unsigned __int64 v20; // rdi
  unsigned int v21; // eax
  unsigned __int64 v22; // r12
  unsigned __int16 *v23; // rax
  unsigned __int16 *v24; // r11
  int v25; // eax
  int v26; // eax
  ULONG v27; // eax
  size_t v28; // rcx
  unsigned int v29; // r14d
  HANDLE CurrentProcess; // rax
  const wchar_t *v31; // rdi
  LPCWSTR v32; // r12
  unsigned __int64 v33; // r12
  unsigned __int16 *v34; // rax
  wchar_t *v35; // r13
  HRESULT v36; // r8d
  size_t v37; // rdi
  size_t v38; // rdi
  unsigned __int16 *v39; // r15
  const WCHAR *v40; // rax
  int v41; // eax
  WCHAR *lpBuffer; // r11
  wchar_t *v43; // rdi
  wchar_t v44; // ax
  wchar_t *v45; // rax
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v47; // rbx
  wchar_t *v48; // r15
  int v49; // eax
  wchar_t v50; // ax
  void *v51; // rdi
  HANDLE FileW; // rax
  unsigned int v53; // eax
  BOOL v54; // r15d
  HWINSTA ProcessWindowStation; // rbx
  HDESK ThreadDesktop; // rdi
  DWORD CurrentThreadId; // eax
  BOOL UserObjectInformationW; // ecx
  __int64 v59; // rax
  const wchar_t *v60; // rax
  struct _PROCESS_INFORMATION *v61; // rcx
  __int64 v62; // rcx
  bool v63; // zf
  __int64 v64; // rcx
  unsigned __int16 *v65; // rax
  HANDLE hHeap; // [rsp+48h] [rbp-680h]
  int v68; // [rsp+50h] [rbp-678h]
  unsigned __int16 *v69; // [rsp+58h] [rbp-670h]
  DWORD nLengthNeeded; // [rsp+60h] [rbp-668h] BYREF
  __int16 v71; // [rsp+64h] [rbp-664h]
  unsigned __int16 *v72; // [rsp+68h] [rbp-660h]
  LPVOID lpMem; // [rsp+70h] [rbp-658h]
  LPCWSTR lpFileName; // [rsp+78h] [rbp-650h] BYREF
  STRSAFE_PCNZWCH psz; // [rsp+80h] [rbp-648h] BYREF
  unsigned __int16 *v76; // [rsp+88h] [rbp-640h]
  wchar_t *Str; // [rsp+90h] [rbp-638h]
  size_t pcchLength; // [rsp+98h] [rbp-630h] BYREF
  int v79; // [rsp+A0h] [rbp-628h]
  BOOL v80; // [rsp+A4h] [rbp-624h]
  int v81; // [rsp+A8h] [rbp-620h]
  size_t v82; // [rsp+B0h] [rbp-618h] BYREF
  wchar_t *v83; // [rsp+B8h] [rbp-610h]
  unsigned __int16 *v84; // [rsp+C0h] [rbp-608h] BYREF
  unsigned __int16 *v85; // [rsp+C8h] [rbp-600h] BYREF
  unsigned __int64 v86; // [rsp+D0h] [rbp-5F8h] BYREF
  unsigned __int64 v87; // [rsp+D8h] [rbp-5F0h] BYREF
  unsigned __int64 v88; // [rsp+E0h] [rbp-5E8h] BYREF
  void *Src; // [rsp+E8h] [rbp-5E0h]
  BOOL v90; // [rsp+F0h] [rbp-5D8h]
  LPWSTR FilePart; // [rsp+F8h] [rbp-5D0h] BYREF
  unsigned __int16 *v92; // [rsp+100h] [rbp-5C8h]
  struct _STARTUPINFOW *v93; // [rsp+108h] [rbp-5C0h]
  struct _PROCESS_INFORMATION *v94; // [rsp+110h] [rbp-5B8h]
  int v95; // [rsp+130h] [rbp-598h] BYREF
  unsigned __int16 *v96; // [rsp+138h] [rbp-590h]
  int v97; // [rsp+140h] [rbp-588h]
  unsigned __int16 *v98; // [rsp+148h] [rbp-580h]
  __int16 v99; // [rsp+150h] [rbp-578h]
  __int16 v100; // [rsp+152h] [rbp-576h]
  const wchar_t *v101; // [rsp+158h] [rbp-570h]
  int v102; // [rsp+160h] [rbp-568h]
  LPVOID v103; // [rsp+168h] [rbp-560h]
  int v104; // [rsp+170h] [rbp-558h]
  unsigned __int16 *v105; // [rsp+178h] [rbp-550h]
  int v106; // [rsp+180h] [rbp-548h]
  unsigned __int16 *v107; // [rsp+188h] [rbp-540h]
  char v108[16]; // [rsp+190h] [rbp-538h] BYREF
  const wchar_t *v109; // [rsp+1A0h] [rbp-528h]
  char v110[8]; // [rsp+1F8h] [rbp-4D0h] BYREF
  LPVOID v111; // [rsp+200h] [rbp-4C8h]
  DWORD CurrentProcessId; // [rsp+208h] [rbp-4C0h]
  __int64 v113; // [rsp+20Ch] [rbp-4BCh]
  unsigned int v114; // [rsp+214h] [rbp-4B4h]
  unsigned int v115; // [rsp+218h] [rbp-4B0h]
  int v116; // [rsp+21Ch] [rbp-4ACh]
  __int64 v117; // [rsp+220h] [rbp-4A8h]
  __int64 v118; // [rsp+228h] [rbp-4A0h]
  void *v119; // [rsp+230h] [rbp-498h]
  __int128 v120; // [rsp+240h] [rbp-488h] BYREF
  DWORD dwErrCode[4]; // [rsp+250h] [rbp-478h]
  _WORD pvInfo[528]; // [rsp+260h] [rbp-468h] BYREF

  v84 = a3;
  v85 = a2;
  v94 = a12;
  psz = a7;
  Src = a9;
  v92 = a10;
  v93 = a11;
  v14 = 0;
  lpFileName = 0;
  v15 = 0;
  v68 = 0;
  v81 = 0;
  LastError = 0;
  ProcessHeap = GetProcessHeap();
  hHeap = ProcessHeap;
  lpMem = 0;
  v72 = 0;
  v69 = 0;
  memset_0(&v95, 0, 0x108u);
  v120 = 0;
  *(_OWORD *)dwErrCode = 0;
  memset_0(pvInfo, 0, 0x414u);
  v119 = a1;
  if ( a4 && *a4 )
  {
    v18 = -1;
    do
      ++v18;
    while ( a4[v18] );
    v19 = v18 + 1;
    v20 = (unsigned int)(v18 + 1);
    v21 = (2 * ((_BYTE)v18 + 1)) & 7;
    if ( v21 )
    {
      v22 = v19 + ((8 - (unsigned __int64)v21) >> 1);
      v68 = v22;
    }
    else
    {
      LODWORD(v22) = v19;
      v68 = v19;
    }
    v81 = v22;
    if ( (unsigned int)v22 < v19 || (unsigned int)v22 >= 0x7FFE )
    {
      LastError = 111;
      goto LABEL_160;
    }
    v23 = (unsigned __int16 *)HeapAlloc(hHeap, 0, 2LL * (unsigned int)(v22 + 1));
    v24 = v23;
    v69 = v23;
    if ( !v23 )
    {
      LastError = 8;
      goto LABEL_161;
    }
    v25 = StringCchCopyW(v23, v20, a4);
    if ( v25 < 0 )
    {
      LastError = v25;
      goto LABEL_161;
    }
    v26 = SystemFunction040(v24, 2 * v22, 2u);
    if ( v26 < 0 )
    {
      v27 = RtlNtStatusToDosError(v26);
LABEL_16:
      LastError = v27;
      goto LABEL_160;
    }
    v24 = v69;
    v69[(unsigned int)v22] = 0;
    v99 = v22;
    v100 = v22 + 1;
    v101 = v69;
    ProcessHeap = hHeap;
  }
  else
  {
    v101 = &P;
    pcchLength = 0;
    LastError = StringLengthWorkerW(&P, 0xFFFEu, &pcchLength);
    v28 = pcchLength;
    if ( LastError < 0 )
      v28 = 0;
    pcchLength = v28;
    if ( LastError < 0 )
      goto LABEL_159;
    v99 = v28;
    v100 = v28 + 1;
    v24 = 0;
  }
  if ( (a8 & 0x8000B) != 0 || (a5 & 0xFFFFFFFC) != 0 )
  {
    LastError = 87;
    goto LABEL_161;
  }
  v29 = a8 | 0x4000200;
  if ( (a8 & 0x8000000) == 0 )
    v29 = a8 | 0x4000210;
  if ( (v29 & 0x1E0) == 0 )
  {
    CurrentProcess = GetCurrentProcess();
    if ( GetPriorityClass(CurrentProcess) == 64 )
      v29 |= 0x40u;
  }
  lpMem = HeapAlloc(ProcessHeap, 0, 0x208u);
  v31 = psz;
  if ( psz )
  {
    if ( (int)StringCchLengthW(psz, 0x401u, (unsigned __int64 *)&lpFileName) < 0 )
    {
LABEL_33:
      LastError = -2147024809;
      goto LABEL_160;
    }
    v32 = lpFileName;
  }
  else
  {
    v32 = 0;
    lpFileName = 0;
  }
  v33 = (unsigned __int64)(v32 + 131);
  lpFileName = (LPCWSTR)v33;
  v34 = (unsigned __int16 *)HeapAlloc(hHeap, 0, 2 * v33);
  v14 = v34;
  v72 = v34;
  if ( !lpMem || !v34 )
    goto LABEL_102;
  if ( a6 )
  {
    FilePart = 0;
    if ( GetFullPathNameW(a6, 0x104u, (LPWSTR)lpMem, &FilePart)
      && (FileW = CreateFileW(a6, 0x80000000, 3u, 0, 3u, 0, 0), FileW != (HANDLE)-1LL) )
    {
      CloseHandle(FileW);
    }
    else
    {
      LastError = StringCchCopyW((unsigned __int16 *)lpMem, 0x104u, a6);
      if ( LastError < 0 )
        goto LABEL_160;
    }
    if ( !psz )
    {
      HeapFree(hHeap, 0, v14);
      v14 = 0;
      v72 = 0;
      goto LABEL_112;
    }
    LastError = StringCchCopyW(v14, v33, psz);
    if ( LastError >= 0 )
      goto LABEL_112;
LABEL_160:
    v24 = v69;
LABEL_161:
    v51 = hHeap;
LABEL_162:
    v54 = 0;
LABEL_163:
    v15 = v68;
    goto LABEL_164;
  }
  if ( !v31 )
  {
LABEL_102:
    LastError = 87;
    goto LABEL_160;
  }
  nLengthNeeded = 0;
  v71 = 0;
  Str = 0;
  v35 = 0;
  v83 = 0;
  v76 = 0;
  v79 = 1;
  v82 = 0;
  v36 = StringLengthWorkerW(v31, 0x401u, &v82);
  v37 = v82;
  if ( v36 < 0 )
    v37 = 0;
  v82 = v37;
  if ( v36 < 0 )
  {
    LastError = -2147024809;
LABEL_45:
    v14 = v72;
    goto LABEL_160;
  }
  v38 = v37 + 1;
  v82 = v38;
  v39 = (unsigned __int16 *)HeapAlloc(hHeap, 0, 2 * v38);
  pcchLength = (size_t)v39;
  v40 = (const WCHAR *)HeapAlloc(hHeap, 0, 0x20Au);
  lpFileName = v40;
  if ( !v39 || !v40 )
  {
    LastError = 8;
    goto LABEL_45;
  }
  v41 = StringCchCopyW(v39, v38, psz);
  if ( v41 < 0 )
  {
    LastError = v41;
    goto LABEL_45;
  }
  v43 = v39;
  v76 = v39;
  v44 = *v39;
  if ( *v39 != 34 )
  {
    while ( v44 == 32 || v44 == 9 )
    {
      v76 = ++v43;
      v44 = *v43;
    }
    v45 = v43;
    Str = v43;
    while ( 1 )
    {
      if ( !*v43 )
        goto LABEL_67;
      if ( *v43 == 32 || *v43 == 9 )
        break;
      v76 = ++v43;
    }
    nLengthNeeded = *v43;
    v71 = nLengthNeeded;
    v45 = Str;
    goto LABEL_66;
  }
  v79 = 0;
  v43 = v39 + 1;
  v76 = v39 + 1;
  v45 = v39 + 1;
  Str = v39 + 1;
  while ( *v43 )
  {
    if ( *v43 == 34 )
    {
      nLengthNeeded = 34;
      v71 = 34;
LABEL_66:
      v83 = v43;
      v35 = v43;
      *v43 = 0;
      break;
    }
    v76 = ++v43;
  }
LABEL_67:
  while ( SearchPathW(0, v45, L".exe", 0x105u, lpBuffer, 0) - 1 > 0x103 )
  {
    if ( LastError )
      SetLastError(LastError);
    else
      LastError = GetLastError();
LABEL_85:
    if ( v35 )
    {
      *v35 = nLengthNeeded;
      v35 = 0;
      v83 = 0;
      v76 = ++v43;
    }
    v50 = *v43;
    if ( !*v43 || !v79 )
    {
      v51 = hHeap;
      HeapFree(hHeap, 0, (LPVOID)lpFileName);
      HeapFree(hHeap, 0, (LPVOID)pcchLength);
      HeapFree(hHeap, 0, lpMem);
      lpMem = 0;
      v14 = v72;
      LastError = StringCchCopyW(v72, v33, psz);
      if ( LastError >= 0 )
        goto LABEL_112;
      v24 = v69;
      goto LABEL_162;
    }
    while ( v50 == 32 || v50 == 9 )
    {
      v76 = ++v43;
      v50 = *v43;
    }
    while ( *v43 )
    {
      if ( *v43 == 32 || *v43 == 9 )
      {
        nLengthNeeded = *v43;
        v71 = nLengthNeeded;
        *v43 = 0;
        v35 = v43;
        v83 = v43;
        break;
      }
      v76 = ++v43;
    }
    v45 = Str;
    lpBuffer = (WCHAR *)lpFileName;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) != 0 )
    goto LABEL_85;
  LastError = StringCchCopyW((unsigned __int16 *)lpMem, 0x104u, lpFileName);
  if ( LastError < 0 )
    goto LABEL_45;
  v47 = psz;
  if ( *psz == 34 || (v48 = Str, !wcschr(Str, 0x20u)) )
  {
    v14 = v72;
    v49 = StringCchCopyW(v72, v33, v47);
  }
  else
  {
    v14 = v72;
    LastError = StringCchCopyW(v72, v33, L"\"");
    if ( LastError >= 0 )
      LastError = StringCchCatW(v72, v33, v48);
    if ( LastError < 0 )
      goto LABEL_160;
    LastError = StringCchCatW(v72, v33, L"\"");
    if ( LastError < 0 )
      goto LABEL_160;
    v88 = 0;
    if ( (int)StringCchLengthW(v48, 0x104u, &v88) < 0 )
      goto LABEL_33;
    v49 = StringCchCatW(v72, v33, &psz[v88]);
  }
  LastError = v49;
  if ( v49 < 0 )
    goto LABEL_160;
  HeapFree(hHeap, 0, (LPVOID)pcchLength);
  HeapFree(hHeap, 0, (LPVOID)lpFileName);
LABEL_112:
  v113 = 0;
  v114 = a5;
  CurrentProcessId = GetCurrentProcessId();
  v115 = v29;
  v117 = 0;
  v118 = 0;
  v96 = v85;
  if ( v85 )
  {
    psz = 0;
    LastError = StringCchLengthW(v85, 0xFFFEu, (unsigned __int64 *)&psz);
    if ( LastError >= 0 )
    {
      LOWORD(v95) = (_WORD)psz;
      HIWORD(v95) = (_WORD)psz + 1;
      goto LABEL_116;
    }
    goto LABEL_160;
  }
  v95 = 0;
LABEL_116:
  v98 = v84;
  if ( !v84 )
  {
    v97 = 0;
LABEL_120:
    v103 = lpMem;
    if ( lpMem )
    {
      v87 = 0;
      LastError = StringCchLengthW((const unsigned __int16 *)lpMem, 0xFFFEu, &v87);
      if ( LastError < 0 )
        goto LABEL_160;
      LOWORD(v102) = v87;
      HIWORD(v102) = v87 + 1;
    }
    else
    {
      v102 = 0;
    }
    v105 = v14;
    if ( v14 )
    {
      v84 = 0;
      LastError = StringCchLengthW(v14, 0xFFFEu, (unsigned __int64 *)&v84);
      if ( LastError < 0 )
        goto LABEL_160;
      LOWORD(v104) = (_WORD)v84;
      HIWORD(v104) = (_WORD)v84 + 1;
    }
    else
    {
      v104 = 0;
    }
    v107 = v92;
    if ( v92 )
    {
      v85 = 0;
      LastError = StringCchLengthW(v92, 0xFFFEu, (unsigned __int64 *)&v85);
      if ( LastError < 0 )
        goto LABEL_160;
      LOWORD(v106) = (_WORD)v85;
      HIWORD(v106) = (_WORD)v85 + 1;
    }
    else
    {
      v106 = 0;
    }
    if ( (v115 & 0x400) != 0 )
      v53 = To_SECL_BLOB_W((unsigned __int16 *)Src, (struct _SECL_BLOB *)v110);
    else
      v53 = To_SECL_BLOB_A(Src, (struct _SECL_BLOB *)v110);
    LastError = v53;
    if ( !v53 )
    {
      LastError = StartInfo_To_SECL_STARTUPINFOW(v93, (struct _SECL_STARTUPINFOW *)v108);
      if ( !LastError )
      {
        if ( v109 && *v109 )
        {
          v116 |= 1u;
        }
        else
        {
          nLengthNeeded = 0;
          ProcessWindowStation = 0;
          ThreadDesktop = 0;
          if ( (unsigned __int8)IsGetThreadDesktopPresent() )
            ProcessWindowStation = GetProcessWindowStation();
          if ( (unsigned __int8)IsGetThreadDesktopPresent() )
          {
            CurrentThreadId = GetCurrentThreadId();
            ThreadDesktop = GetThreadDesktop(CurrentThreadId);
          }
          v80 = 0;
          v109 = &P;
          if ( (unsigned __int8)IsGetThreadDesktopPresent() )
          {
            UserObjectInformationW = GetUserObjectInformationW(ProcessWindowStation, 2, pvInfo, 0x208u, &nLengthNeeded);
            v80 = UserObjectInformationW;
            if ( UserObjectInformationW )
            {
              v59 = -1;
              do
                ++v59;
              while ( pvInfo[v59] );
              pvInfo[(unsigned int)v59] = 92;
              nLengthNeeded = v59 + 1;
              UserObjectInformationW = GetUserObjectInformationW(
                                         ThreadDesktop,
                                         2,
                                         &pvInfo[(unsigned int)(v59 + 1)],
                                         0x208u,
                                         &nLengthNeeded);
              v80 = UserObjectInformationW;
              v60 = pvInfo;
              if ( !UserObjectInformationW )
                v60 = v109;
              v109 = v60;
            }
            if ( !UserObjectInformationW )
            {
              v27 = GetLastError();
              goto LABEL_16;
            }
          }
        }
        LastError = c_SeclCreateProcessWithLogonW((struct _SECL_SLI *)&v95, (struct _SECL_SLRI *)&v120);
        if ( LastError )
          goto LABEL_160;
        LastError = dwErrCode[2];
        v54 = dwErrCode[2] == 0;
        v90 = v54;
        if ( dwErrCode[2] )
        {
          SetLastError(dwErrCode[2]);
        }
        else
        {
          v61 = v94;
          *(_OWORD *)&v94->hProcess = v120;
          v61->dwProcessId = dwErrCode[0];
          v61->dwThreadId = dwErrCode[1];
          LastError = 0;
        }
        v51 = hHeap;
        v24 = v69;
        goto LABEL_163;
      }
    }
    goto LABEL_160;
  }
  v86 = 0;
  LastError = StringCchLengthW(v84, 0xFFFEu, &v86);
  if ( LastError >= 0 )
  {
    LOWORD(v97) = v86;
    HIWORD(v97) = v86 + 1;
    goto LABEL_120;
  }
  v15 = v68;
LABEL_159:
  v54 = 0;
  v24 = v69;
  v51 = hHeap;
LABEL_164:
  if ( v24 )
  {
    v62 = (unsigned int)(v15 + 1);
    v63 = 2 * v62 == 0;
    v64 = 2 * v62;
    v65 = v24;
    if ( !v63 )
    {
      do
      {
        *(_BYTE *)v65 = 0;
        v65 = (unsigned __int16 *)((char *)v65 + 1);
        --v64;
      }
      while ( v64 );
    }
    HeapFree(v51, 0, v24);
  }
  if ( v111 )
    HeapFree(v51, 0, v111);
  if ( v14 )
    HeapFree(v51, 0, v14);
  if ( lpMem )
    HeapFree(v51, 0, lpMem);
  SetLastError(LastError);
  return v54;
}

```

## disassembly

```asm
0x18002db2c  push    rbx
0x18002db2e  push    rsi
0x18002db2f  push    rdi
0x18002db30  push    r12
0x18002db32  push    r13
0x18002db34  push    r14
0x18002db36  push    r15
0x18002db38  sub     rsp, 690h
0x18002db3f  mov     rax, cs:__security_cookie
0x18002db46  xor     rax, rsp
0x18002db49  mov     [rsp+6C8h+var_48], rax
0x18002db51  mov     rsi, r9
0x18002db54  mov     [rsp+6C8h+var_608], r8
0x18002db5c  mov     [rsp+6C8h+var_600], rdx
0x18002db64  mov     rdi, rcx
0x18002db67  mov     rax, [rsp+6C8h+arg_58]
0x18002db6f  mov     [rsp+6C8h+var_5B8], rax
0x18002db77  mov     r15, [rsp+6C8h+arg_28]
0x18002db7f  mov     rax, [rsp+6C8h+arg_30]
0x18002db87  mov     [rsp+6C8h+psz], rax
0x18002db8f  mov     rax, [rsp+6C8h+arg_40]
0x18002db97  mov     [rsp+6C8h+Src], rax
0x18002db9f  mov     rax, [rsp+6C8h+arg_48]
0x18002dba7  mov     [rsp+6C8h+var_5C8], rax
0x18002dbaf  mov     rax, [rsp+6C8h+arg_50]
0x18002dbb7  mov     [rsp+6C8h+var_5C0], rax
0x18002dbbf  xor     r13d, r13d
0x18002dbc2  mov     [rsp+6C8h+var_684], r13d
0x18002dbc7  mov     [rsp+6C8h+lpFileName], r13
0x18002dbcc  mov     r14d, r13d
0x18002dbcf  mov     [rsp+6C8h+var_678], r14
0x18002dbd4  mov     [rsp+6C8h+var_620], r13d
0x18002dbdc  mov     ebx, r13d
0x18002dbdf  mov     [rsp+6C8h+var_688], ebx
0x18002dbe3  call    cs:__imp_GetProcessHeap
0x18002dbe9  mov     r12, rax
0x18002dbec  mov     [rsp+6C8h+hHeap], rax
0x18002dbf1  mov     [rsp+6C8h+lpMem], r13
0x18002dbf6  mov     [rsp+6C8h+var_660], r13
0x18002dbfb  xor     ecx, ecx
0x18002dbfd  mov     [rsp+6C8h+var_670], rcx
0x18002dc02  xor     edx, edx; Val
0x18002dc04  mov     r8d, 108h; Size
0x18002dc0a  lea     rcx, [rsp+6C8h+var_598]; void *
0x18002dc12  call    memset_0
0x18002dc17  xorps   xmm0, xmm0
0x18002dc1a  movups  [rsp+6C8h+var_488], xmm0
0x18002dc22  movups  xmmword ptr [rsp+6C8h+dwErrCode], xmm0
0x18002dc2a  xor     edx, edx; Val
0x18002dc2c  mov     r8d, 414h; Size
0x18002dc32  lea     rcx, [rsp+6C8h+pvInfo]; void *
0x18002dc3a  call    memset_0
0x18002dc3f  nop
0x18002dc40  mov     [rsp+6C8h+var_498], rdi
0x18002dc48  xor     edx, edx; dwFlags
0x18002dc4a  test    rsi, rsi
0x18002dc4d  jz      loc_18002DD7E
0x18002dc53  cmp     dx, [rsi]
0x18002dc56  jz      loc_18002DD7E
0x18002dc5c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002dc60  inc     rax
0x18002dc63  cmp     [rsi+rax*2], dx
0x18002dc67  jnz     short loc_18002DC60
0x18002dc69  lea     ecx, [rax+1]
0x18002dc6c  mov     edi, ecx
0x18002dc6e  lea     rax, [rcx+rcx]
0x18002dc72  and     eax, 7
0x18002dc75  jnz     short loc_18002DC81
0x18002dc77  mov     r12d, edi
0x18002dc7a  mov     [rsp+6C8h+var_678], rdi
0x18002dc7f  jmp     short loc_18002DC95
0x18002dc81  mov     r12d, 8
0x18002dc87  sub     r12, rax
0x18002dc8a  shr     r12, 1
0x18002dc8d  add     r12, rdi
0x18002dc90  mov     [rsp+6C8h+var_678], r12
0x18002dc95  mov     [rsp+6C8h+var_620], r12d
0x18002dc9d  cmp     r12d, ecx
0x18002dca0  jb      loc_18002DD6D
0x18002dca6  cmp     r12d, 7FFEh
0x18002dcad  jnb     loc_18002DD6D
0x18002dcb3  lea     r14d, [r12+1]
0x18002dcb8  mov     r8d, r14d
0x18002dcbb  add     r8, r8; dwBytes
0x18002dcbe  mov     rcx, [rsp+6C8h+hHeap]; hHeap
0x18002dcc3  call    cs:__imp_HeapAlloc
0x18002dcc9  mov     r11, rax
0x18002dccc  mov     [rsp+6C8h+var_670], rax
0x18002dcd1  xor     edx, edx
0x18002dcd3  test    rax, rax
0x18002dcd6  jnz     short loc_18002DCE9
0x18002dcd8  lea     ebx, [rax+8]
0x18002dcdb  mov     [rsp+6C8h+var_688], ebx
0x18002dcdf  mov     esi, 1
0x18002dce4  jmp     loc_18002E8EE
0x18002dce9  mov     r8, rsi; unsigned __int16 *
0x18002dcec  mov     rdx, rdi; unsigned __int64
0x18002dcef  mov     rcx, r11; unsigned __int16 *
0x18002dcf2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002dcf7  xor     edx, edx
0x18002dcf9  test    eax, eax
0x18002dcfb  jns     short loc_18002DD05
0x18002dcfd  mov     ebx, eax
0x18002dcff  mov     [rsp+6C8h+var_688], eax
0x18002dd03  jmp     short loc_18002DCDF
0x18002dd05  lea     edx, [r12+r12]; MemorySize
0x18002dd09  mov     r8d, 2; OptionFlags
0x18002dd0f  mov     rcx, r11; Memory
0x18002dd12  call    cs:__imp_SystemFunction040
0x18002dd18  xor     edx, edx
0x18002dd1a  test    eax, eax
0x18002dd1c  jns     short loc_18002DD38
0x18002dd1e  mov     ecx, eax; Status
0x18002dd20  call    cs:__imp_RtlNtStatusToDosError
0x18002dd26  mov     esi, 1
0x18002dd2b  mov     [rsp+6C8h+var_688], eax
0x18002dd2f  mov     ebx, eax
0x18002dd31  xor     edx, edx
0x18002dd33  jmp     loc_18002E8E9
0x18002dd38  mov     ecx, r12d
0x18002dd3b  mov     eax, edx
0x18002dd3d  mov     r11, [rsp+6C8h+var_670]
0x18002dd42  mov     [r11+rcx*2], dx
0x18002dd47  mov     [rsp+6C8h+var_578], r12w
0x18002dd50  mov     [rsp+6C8h+var_576], r14w
0x18002dd59  mov     [rsp+6C8h+var_570], r11
0x18002dd61  mov     esi, 1
0x18002dd66  mov     r12, [rsp+6C8h+hHeap]
0x18002dd6b  jmp     short loc_18002DDEB
0x18002dd6d  mov     ebx, 6Fh ; 'o'
0x18002dd72  mov     [rsp+6C8h+var_688], ebx
0x18002dd76  lea     esi, [rbx-6Eh]
0x18002dd79  jmp     loc_18002E8E9
0x18002dd7e  lea     rax, P
0x18002dd85  mov     [rsp+6C8h+var_570], rax
0x18002dd8d  mov     [rsp+6C8h+pcchLength], rdx
0x18002dd95  lea     r8, [rsp+6C8h+pcchLength]; pcchLength
0x18002dd9d  mov     edx, 0FFFEh; cchMax
0x18002dda2  mov     rcx, rax; psz
0x18002dda5  call    StringLengthWorkerW
0x18002ddaa  mov     ebx, eax
0x18002ddac  mov     rcx, [rsp+6C8h+pcchLength]
0x18002ddb4  xor     edx, edx
0x18002ddb6  mov     eax, edx
0x18002ddb8  test    ebx, ebx
0x18002ddba  cmovs   rcx, rdx
0x18002ddbe  mov     [rsp+6C8h+pcchLength], rcx
0x18002ddc6  mov     [rsp+6C8h+var_688], ebx
0x18002ddca  lea     esi, [rdx+1]
0x18002ddcd  js      loc_18002E8D8
0x18002ddd3  mov     [rsp+6C8h+var_578], cx
0x18002dddb  add     cx, si
0x18002ddde  mov     [rsp+6C8h+var_576], cx
0x18002dde6  mov     r11, [rsp+6C8h+var_670]
0x18002ddeb  mov     r14d, [rsp+6C8h+arg_38]
0x18002ddf3  test    r14d, 8000Bh
0x18002ddfa  jz      short loc_18002DE0A
0x18002ddfc  mov     ebx, 57h ; 'W'
0x18002de01  mov     [rsp+6C8h+var_688], ebx
0x18002de05  jmp     loc_18002E8EE
0x18002de0a  test    [rsp+6C8h+arg_20], 0FFFFFFFCh
0x18002de15  jnz     short loc_18002DDFC
0x18002de17  or      r14d, 4000200h
0x18002de1e  mov     [rsp+6C8h+arg_38], r14d
0x18002de26  bt      r14d, 1Bh
0x18002de2b  jb      short loc_18002DE39
0x18002de2d  or      r14d, 10h
0x18002de31  mov     [rsp+6C8h+arg_38], r14d
0x18002de39  test    r14d, 1E0h
0x18002de40  jnz     short loc_18002DE61
0x18002de42  call    cs:__imp_GetCurrentProcess
0x18002de48  mov     rcx, rax; hProcess
0x18002de4b  call    cs:__imp_GetPriorityClass
0x18002de51  cmp     eax, 40h ; '@'
0x18002de54  jnz     short loc_18002DE61
0x18002de56  or      r14d, eax
0x18002de59  mov     [rsp+6C8h+arg_38], r14d
0x18002de61  xor     edx, edx; dwFlags
0x18002de63  mov     r8d, 208h; dwBytes
0x18002de69  mov     rcx, r12; hHeap
0x18002de6c  call    cs:__imp_HeapAlloc
0x18002de72  mov     [rsp+6C8h+lpMem], rax
0x18002de77  mov     rdi, [rsp+6C8h+psz]
0x18002de7f  xor     ecx, ecx
0x18002de81  test    rdi, rdi
0x18002de84  jz      short loc_18002DEB3
0x18002de86  lea     r8, [rsp+6C8h+lpFileName]; unsigned __int64 *
0x18002de8b  mov     edx, 401h; unsigned __int64
0x18002de90  mov     rcx, rdi; unsigned __int16 *
0x18002de93  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x18002de98  xor     edx, edx
0x18002de9a  test    eax, eax
0x18002de9c  jns     short loc_18002DEAC
0x18002de9e  mov     ebx, 80070057h
0x18002dea3  mov     [rsp+6C8h+var_688], ebx
0x18002dea7  jmp     loc_18002E8E9
0x18002deac  mov     r12, [rsp+6C8h+lpFileName]
0x18002deb1  jmp     short loc_18002DEBB
0x18002deb3  mov     r12, rcx
0x18002deb6  mov     [rsp+6C8h+lpFileName], rcx
0x18002debb  add     r12, 106h
0x18002dec2  mov     [rsp+6C8h+lpFileName], r12
0x18002dec7  lea     r8, [r12+r12]; dwBytes
0x18002decb  xor     edx, edx; dwFlags
0x18002decd  mov     rcx, [rsp+6C8h+hHeap]; hHeap
0x18002ded2  call    cs:__imp_HeapAlloc
0x18002ded8  mov     r13, rax
0x18002dedb  mov     [rsp+6C8h+var_660], rax
0x18002dee0  mov     r11, [rsp+6C8h+lpMem]
0x18002dee5  xor     edx, edx
0x18002dee7  test    r11, r11
0x18002deea  jz      loc_18002E393
0x18002def0  test    rax, rax
0x18002def3  jz      loc_18002E393
0x18002def9  test    r15, r15
0x18002defc  jnz     loc_18002E39D
0x18002df02  test    rdi, rdi
0x18002df05  jz      loc_18002E393
0x18002df0b  mov     [rsp+6C8h+nLengthNeeded], edx
0x18002df0f  mov     [rsp+6C8h+var_664], dx
0x18002df14  mov     [rsp+6C8h+Str], rdx
0x18002df1c  mov     r13d, edx
0x18002df1f  mov     [rsp+6C8h+var_610], rdx
0x18002df27  mov     [rsp+6C8h+var_640], rdx
0x18002df2f  mov     [rsp+6C8h+var_628], esi
0x18002df36  mov     [rsp+6C8h+var_618], rdx
0x18002df3e  lea     r8, [rsp+6C8h+var_618]; pcchLength
0x18002df46  mov     edx, 401h; cchMax
0x18002df4b  mov     rcx, rdi; psz
0x18002df4e  call    StringLengthWorkerW
0x18002df53  mov     r8d, eax
0x18002df56  mov     rdi, [rsp+6C8h+var_618]
0x18002df5e  xor     edx, edx; dwFlags
0x18002df60  mov     eax, edx
0x18002df62  test    r8d, r8d
0x18002df65  cmovs   rdi, rdx
0x18002df69  mov     [rsp+6C8h+var_618], rdi
0x18002df71  jns     short loc_18002DF86
0x18002df73  mov     ebx, 80070057h
0x18002df78  mov     [rsp+6C8h+var_688], ebx
0x18002df7c  mov     r13, [rsp+6C8h+var_660]
0x18002df81  jmp     loc_18002E8E9
0x18002df86  add     rdi, rsi
0x18002df89  mov     [rsp+6C8h+var_618], rdi
0x18002df91  lea     r8, [rdi+rdi]; dwBytes
0x18002df95  mov     rcx, [rsp+6C8h+hHeap]; hHeap
0x18002df9a  call    cs:__imp_HeapAlloc
0x18002dfa0  mov     r15, rax
0x18002dfa3  mov     [rsp+6C8h+pcchLength], rax
0x18002dfab  xor     edx, edx; dwFlags
0x18002dfad  mov     r8d, 20Ah; dwBytes
0x18002dfb3  mov     rcx, [rsp+6C8h+hHeap]; hHeap
0x18002dfb8  call    cs:__imp_HeapAlloc
0x18002dfbe  mov     r11, rax
0x18002dfc1  mov     [rsp+6C8h+lpFileName], rax
0x18002dfc6  xor     edx, edx
0x18002dfc8  test    r15, r15
0x18002dfcb  jz      loc_18002E389
0x18002dfd1  test    rax, rax
0x18002dfd4  jz      loc_18002E389
0x18002dfda  mov     r8, [rsp+6C8h+psz]; unsigned __int16 *
0x18002dfe2  mov     rdx, rdi; unsigned __int64
0x18002dfe5  mov     rcx, r15; unsigned __int16 *
0x18002dfe8  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18002dfed  xor     edx, edx
0x18002dfef  test    eax, eax
0x18002dff1  jns     short loc_18002DFFB
0x18002dff3  mov     ebx, eax
0x18002dff5  mov     [rsp+6C8h+var_688], eax
0x18002dff9  jmp     short loc_18002DF7C
0x18002dffb  mov     rdi, r15
0x18002dffe  mov     [rsp+6C8h+var_640], r15
0x18002e006  movzx   eax, word ptr [r15]
0x18002e00a  mov     ecx, 22h ; '"'
0x18002e00f  cmp     ax, cx
0x18002e012  jnz     short loc_18002E063
0x18002e014  mov     [rsp+6C8h+var_628], edx
0x18002e01b  lea     rdi, [r15+2]
0x18002e01f  mov     [rsp+6C8h+var_640], rdi
0x18002e027  mov     rax, rdi
0x18002e02a  mov     [rsp+6C8h+Str], rax
0x18002e032  cmp     [rdi], dx
0x18002e035  jz      short loc_18002E05B
0x18002e037  cmp     [rdi], cx
0x18002e03a  jnz     short loc_18002E04D
0x18002e03c  mov     [rsp+6C8h+nLengthNeeded], ecx
0x18002e040  mov     [rsp+6C8h+var_664], cx
0x18002e045  mov     r15d, 20h ; ' '
0x18002e04b  jmp     short loc_18002E0BB
0x18002e04d  add     rdi, 2
0x18002e051  mov     [rsp+6C8h+var_640], rdi
0x18002e059  jmp     short loc_18002E032
0x18002e05b  mov     r15d, 20h ; ' '
0x18002e061  jmp     short loc_18002E0C9
0x18002e063  mov     r15d, 20h ; ' '
0x18002e069  cmp     ax, r15w
0x18002e06d  jz      loc_18002E375
0x18002e073  cmp     ax, 9
0x18002e077  jz      loc_18002E375
0x18002e07d  mov     rax, rdi
  ... truncated ...
```
