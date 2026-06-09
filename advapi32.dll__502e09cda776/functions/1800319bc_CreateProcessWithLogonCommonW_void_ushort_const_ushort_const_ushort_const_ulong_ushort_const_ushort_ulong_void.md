# CreateProcessWithLogonCommonW(void *,ushort const *,ushort const *,ushort const *,ulong,ushort const *,ushort *,ulong,void *,ushort const *,_STARTUPINFOW *,_PROCESS_INFORMATION *)

- ea: `0x1800319bc`
- end: `0x18003290d`
- name: `?CreateProcessWithLogonCommonW@@YAHPEAXPEBG11K1PEAGK01PEAU_STARTUPINFOW@@PEAU_PROCESS_INFORMATION@@@Z`
- size: `3921`
- prototype: `int(void *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, unsigned int, const unsigned __int16 *, unsigned __int16 *, unsigned int, void *, const unsigned __int16 *, struct _STARTUPINFOW *, struct _PROCESS_INFORMATION *)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180031950`
- `0x18005c620`

## callees

- `0x180002e84`
- `0x18002ec60`
- `0x18002f694`
- `0x18002f6d0`
- `0x1800319bc`
- `0x1800377a4`
- `0x180038204`
- `0x180038b58`
- `0x18003c2a4`
- `0x1800415f4`
- `0x18007205a`
- `0x1800720b0`

## import_xrefs

- `msvcrt!wcschr` at `0x180032030`
- `msvcrt!wcschr` at `0x180032030`
- `ntdll!RtlNtStatusToDosError` at `0x180031bc2`
- `ntdll!RtlNtStatusToDosError` at `0x180031bc2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800326cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800326cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031cea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180031cea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032395`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x180032395`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x180031cf9`
- `api-ms-win-core-processthreads-l1-1-0!GetPriorityClass` at `0x180031cf9`
- `KERNEL32!GetLastError` at `0x18003214b`
- `KERNEL32!GetLastError` at `0x1800327d4`
- `KERNEL32!GetLastError` at `0x18003214b`
- `KERNEL32!GetLastError` at `0x1800327d4`
- `KERNEL32!CloseHandle` at `0x18003232a`
- `KERNEL32!CloseHandle` at `0x18003232a`
- `KERNEL32!CreateFileW` at `0x1800322f4`
- `KERNEL32!CreateFileW` at `0x1800322f4`
- `KERNEL32!HeapAlloc` at `0x180031b59`
- `KERNEL32!HeapAlloc` at `0x180031d20`
- `KERNEL32!HeapAlloc` at `0x180031d8c`
- `KERNEL32!HeapAlloc` at `0x180031e5a`
- `KERNEL32!HeapAlloc` at `0x180031e7e`
- `KERNEL32!HeapAlloc` at `0x180031b59`
- `KERNEL32!HeapAlloc` at `0x180031d20`
- `KERNEL32!HeapAlloc` at `0x180031d8c`
- `KERNEL32!HeapAlloc` at `0x180031e5a`
- `KERNEL32!HeapAlloc` at `0x180031e7e`
- `KERNEL32!GetProcessHeap` at `0x180031a73`
- `KERNEL32!GetProcessHeap` at `0x180031a73`
- `KERNEL32!HeapFree` at `0x18003210e`
- `KERNEL32!HeapFree` at `0x180032126`
- `KERNEL32!HeapFree` at `0x18003220c`
- `KERNEL32!HeapFree` at `0x180032225`
- `KERNEL32!HeapFree` at `0x18003223b`
- `KERNEL32!HeapFree` at `0x180032365`
- `KERNEL32!HeapFree` at `0x180032877`
- `KERNEL32!HeapFree` at `0x180032895`
- `KERNEL32!HeapFree` at `0x1800328ae`
- `KERNEL32!HeapFree` at `0x1800328cc`
- `KERNEL32!HeapFree` at `0x1800726de`
- `KERNEL32!HeapFree` at `0x180072704`
- `KERNEL32!HeapFree` at `0x180072720`
- `KERNEL32!HeapFree` at `0x18007273c`
- `KERNEL32!HeapFree` at `0x18003210e`
- `KERNEL32!HeapFree` at `0x180032126`
- `KERNEL32!HeapFree` at `0x18003220c`
- `KERNEL32!HeapFree` at `0x180032225`
- `KERNEL32!HeapFree` at `0x18003223b`
- `KERNEL32!HeapFree` at `0x180032365`
- `KERNEL32!HeapFree` at `0x180032877`
- `KERNEL32!HeapFree` at `0x180032895`
- `KERNEL32!HeapFree` at `0x1800328ae`
- `KERNEL32!HeapFree` at `0x1800328cc`
- `KERNEL32!HeapFree` at `0x1800726de`
- `KERNEL32!HeapFree` at `0x180072704`
- `KERNEL32!HeapFree` at `0x180072720`
- `KERNEL32!HeapFree` at `0x18007273c`
- `KERNEL32!SearchPathW` at `0x180031fb4`
- `KERNEL32!SearchPathW` at `0x180031fb4`
- `KERNEL32!GetFullPathNameW` at `0x1800322c5`
- `KERNEL32!GetFullPathNameW` at `0x1800322c5`
- `KERNEL32!GetFileAttributesW` at `0x180031fd2`
- `KERNEL32!GetFileAttributesW` at `0x180031fd2`
- `KERNEL32!SetLastError` at `0x18003213d`
- `KERNEL32!SetLastError` at `0x180032682`
- `KERNEL32!SetLastError` at `0x1800328da`
- `KERNEL32!SetLastError` at `0x18007274c`
- `KERNEL32!SetLastError` at `0x18003213d`
- `KERNEL32!SetLastError` at `0x180032682`
- `KERNEL32!SetLastError` at `0x1800328da`
- `KERNEL32!SetLastError` at `0x18007274c`
- `CRYPTBASE!SystemFunction040` at `0x180031bae`
- `CRYPTBASE!SystemFunction040` at `0x180031bae`
- `USER32!GetThreadDesktop` at `0x1800326db`
- `USER32!GetThreadDesktop` at `0x1800326db`
- `USER32!GetUserObjectInformationW` at `0x18003272e`
- `USER32!GetUserObjectInformationW` at `0x18003279c`
- `USER32!GetUserObjectInformationW` at `0x18003272e`
- `USER32!GetUserObjectInformationW` at `0x18003279c`
- `USER32!GetProcessWindowStation` at `0x1800326b5`
- `USER32!GetProcessWindowStation` at `0x1800326b5`

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
0x1800319bc  push    rbx
0x1800319be  push    rsi
0x1800319bf  push    rdi
0x1800319c0  push    r12
0x1800319c2  push    r13
0x1800319c4  push    r14
0x1800319c6  push    r15
0x1800319c8  sub     rsp, 690h
0x1800319cf  mov     rax, cs:__security_cookie
0x1800319d6  xor     rax, rsp
0x1800319d9  mov     [rsp+6C8h+var_48], rax
0x1800319e1  mov     rsi, r9
0x1800319e4  mov     [rsp+6C8h+var_608], r8
0x1800319ec  mov     [rsp+6C8h+var_600], rdx
0x1800319f4  mov     rdi, rcx
0x1800319f7  mov     rax, [rsp+6C8h+arg_58]
0x1800319ff  mov     [rsp+6C8h+var_5B8], rax
0x180031a07  mov     r15, [rsp+6C8h+arg_28]
0x180031a0f  mov     rax, [rsp+6C8h+arg_30]
0x180031a17  mov     [rsp+6C8h+psz], rax
0x180031a1f  mov     rax, [rsp+6C8h+arg_40]
0x180031a27  mov     [rsp+6C8h+Src], rax
0x180031a2f  mov     rax, [rsp+6C8h+arg_48]
0x180031a37  mov     [rsp+6C8h+var_5C8], rax
0x180031a3f  mov     rax, [rsp+6C8h+arg_50]
0x180031a47  mov     [rsp+6C8h+var_5C0], rax
0x180031a4f  xor     r13d, r13d
0x180031a52  mov     [rsp+6C8h+var_684], r13d
0x180031a57  mov     [rsp+6C8h+lpFileName], r13
0x180031a5c  mov     r14d, r13d
0x180031a5f  mov     [rsp+6C8h+var_678], r14
0x180031a64  mov     [rsp+6C8h+var_620], r13d
0x180031a6c  mov     ebx, r13d
0x180031a6f  mov     [rsp+6C8h+var_688], ebx
0x180031a73  call    cs:__imp_GetProcessHeap
0x180031a7a  nop     dword ptr [rax+rax+00h]
0x180031a7f  mov     r12, rax
0x180031a82  mov     [rsp+6C8h+hHeap], rax
0x180031a87  mov     [rsp+6C8h+lpMem], r13
0x180031a8c  mov     [rsp+6C8h+var_660], r13
0x180031a91  xor     ecx, ecx
0x180031a93  mov     [rsp+6C8h+var_670], rcx
0x180031a98  xor     edx, edx; Val
0x180031a9a  mov     r8d, 108h; Size
0x180031aa0  lea     rcx, [rsp+6C8h+var_598]; void *
0x180031aa8  call    memset_0
0x180031aad  xorps   xmm0, xmm0
0x180031ab0  movups  [rsp+6C8h+var_488], xmm0
0x180031ab8  movups  xmmword ptr [rsp+6C8h+dwErrCode], xmm0
0x180031ac0  xor     edx, edx; Val
0x180031ac2  mov     r8d, 414h; Size
0x180031ac8  lea     rcx, [rsp+6C8h+pvInfo]; void *
0x180031ad0  call    memset_0
0x180031ad5  nop
0x180031ad6  mov     [rsp+6C8h+var_498], rdi
0x180031ade  xor     edx, edx; dwFlags
0x180031ae0  test    rsi, rsi
0x180031ae3  jz      loc_180031C26
0x180031ae9  cmp     dx, [rsi]
0x180031aec  jz      loc_180031C26
0x180031af2  or      rax, 0FFFFFFFFFFFFFFFFh
0x180031af6  inc     rax
0x180031af9  cmp     [rsi+rax*2], dx
0x180031afd  jnz     short loc_180031AF6
0x180031aff  lea     ecx, [rax+1]
0x180031b02  mov     edi, ecx
0x180031b04  lea     rax, [rcx+rcx]
0x180031b08  and     eax, 7
0x180031b0b  jnz     short loc_180031B17
0x180031b0d  mov     r12d, edi
0x180031b10  mov     [rsp+6C8h+var_678], rdi
0x180031b15  jmp     short loc_180031B2B
0x180031b17  mov     r12d, 8
0x180031b1d  sub     r12, rax
0x180031b20  shr     r12, 1
0x180031b23  add     r12, rdi
0x180031b26  mov     [rsp+6C8h+var_678], r12
0x180031b2b  mov     [rsp+6C8h+var_620], r12d
0x180031b33  cmp     r12d, ecx
0x180031b36  jb      loc_180031C15
0x180031b3c  cmp     r12d, 7FFEh
0x180031b43  jnb     loc_180031C15
0x180031b49  lea     r14d, [r12+1]
0x180031b4e  mov     r8d, r14d
0x180031b51  add     r8, r8; dwBytes
0x180031b54  mov     rcx, [rsp+6C8h+hHeap]; hHeap
0x180031b59  call    cs:__imp_HeapAlloc
0x180031b60  nop     dword ptr [rax+rax+00h]
0x180031b65  mov     r11, rax
0x180031b68  mov     [rsp+6C8h+var_670], rax
0x180031b6d  xor     edx, edx
0x180031b6f  test    rax, rax
0x180031b72  jnz     short loc_180031B85
0x180031b74  lea     ebx, [rax+8]
0x180031b77  mov     [rsp+6C8h+var_688], ebx
0x180031b7b  mov     esi, 1
0x180031b80  jmp     loc_180032845
0x180031b85  mov     r8, rsi; unsigned __int16 *
0x180031b88  mov     rdx, rdi; unsigned __int64
0x180031b8b  mov     rcx, r11; unsigned __int16 *
0x180031b8e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031b93  xor     edx, edx
0x180031b95  test    eax, eax
0x180031b97  jns     short loc_180031BA1
0x180031b99  mov     ebx, eax
0x180031b9b  mov     [rsp+6C8h+var_688], eax
0x180031b9f  jmp     short loc_180031B7B
0x180031ba1  lea     edx, [r12+r12]; MemorySize
0x180031ba5  mov     r8d, 2; OptionFlags
0x180031bab  mov     rcx, r11; Memory
0x180031bae  call    cs:__imp_SystemFunction040
0x180031bb5  nop     dword ptr [rax+rax+00h]
0x180031bba  xor     edx, edx
0x180031bbc  test    eax, eax
0x180031bbe  jns     short loc_180031BE0
0x180031bc0  mov     ecx, eax; Status
0x180031bc2  call    cs:__imp_RtlNtStatusToDosError
0x180031bc9  nop     dword ptr [rax+rax+00h]
0x180031bce  mov     esi, 1
0x180031bd3  mov     [rsp+6C8h+var_688], eax
0x180031bd7  mov     ebx, eax
0x180031bd9  xor     edx, edx
0x180031bdb  jmp     loc_180032840
0x180031be0  mov     ecx, r12d
0x180031be3  mov     eax, edx
0x180031be5  mov     r11, [rsp+6C8h+var_670]
0x180031bea  mov     [r11+rcx*2], dx
0x180031bef  mov     [rsp+6C8h+var_578], r12w
0x180031bf8  mov     [rsp+6C8h+var_576], r14w
0x180031c01  mov     [rsp+6C8h+var_570], r11
0x180031c09  mov     esi, 1
0x180031c0e  mov     r12, [rsp+6C8h+hHeap]
0x180031c13  jmp     short loc_180031C93
0x180031c15  mov     ebx, 6Fh ; 'o'
0x180031c1a  mov     [rsp+6C8h+var_688], ebx
0x180031c1e  lea     esi, [rbx-6Eh]
0x180031c21  jmp     loc_180032840
0x180031c26  lea     rax, P
0x180031c2d  mov     [rsp+6C8h+var_570], rax
0x180031c35  mov     [rsp+6C8h+pcchLength], rdx
0x180031c3d  lea     r8, [rsp+6C8h+pcchLength]; pcchLength
0x180031c45  mov     edx, 0FFFEh; cchMax
0x180031c4a  mov     rcx, rax; psz
0x180031c4d  call    StringLengthWorkerW
0x180031c52  mov     ebx, eax
0x180031c54  mov     rcx, [rsp+6C8h+pcchLength]
0x180031c5c  xor     edx, edx
0x180031c5e  mov     eax, edx
0x180031c60  test    ebx, ebx
0x180031c62  cmovs   rcx, rdx
0x180031c66  mov     [rsp+6C8h+pcchLength], rcx
0x180031c6e  mov     [rsp+6C8h+var_688], ebx
0x180031c72  lea     esi, [rdx+1]
0x180031c75  js      loc_18003282F
0x180031c7b  mov     [rsp+6C8h+var_578], cx
0x180031c83  add     cx, si
0x180031c86  mov     [rsp+6C8h+var_576], cx
0x180031c8e  mov     r11, [rsp+6C8h+var_670]
0x180031c93  mov     r14d, [rsp+6C8h+arg_38]
0x180031c9b  test    r14d, 8000Bh
0x180031ca2  jz      short loc_180031CB2
0x180031ca4  mov     ebx, 57h ; 'W'
0x180031ca9  mov     [rsp+6C8h+var_688], ebx
0x180031cad  jmp     loc_180032845
0x180031cb2  test    [rsp+6C8h+arg_20], 0FFFFFFFCh
0x180031cbd  jnz     short loc_180031CA4
0x180031cbf  or      r14d, 4000200h
0x180031cc6  mov     [rsp+6C8h+arg_38], r14d
0x180031cce  bt      r14d, 1Bh
0x180031cd3  jb      short loc_180031CE1
0x180031cd5  or      r14d, 10h
0x180031cd9  mov     [rsp+6C8h+arg_38], r14d
0x180031ce1  test    r14d, 1E0h
0x180031ce8  jnz     short loc_180031D15
0x180031cea  call    cs:__imp_GetCurrentProcess
0x180031cf1  nop     dword ptr [rax+rax+00h]
0x180031cf6  mov     rcx, rax; hProcess
0x180031cf9  call    cs:__imp_GetPriorityClass
0x180031d00  nop     dword ptr [rax+rax+00h]
0x180031d05  cmp     eax, 40h ; '@'
0x180031d08  jnz     short loc_180031D15
0x180031d0a  or      r14d, eax
0x180031d0d  mov     [rsp+6C8h+arg_38], r14d
0x180031d15  xor     edx, edx; dwFlags
0x180031d17  mov     r8d, 208h; dwBytes
0x180031d1d  mov     rcx, r12; hHeap
0x180031d20  call    cs:__imp_HeapAlloc
0x180031d27  nop     dword ptr [rax+rax+00h]
0x180031d2c  mov     [rsp+6C8h+lpMem], rax
0x180031d31  mov     rdi, [rsp+6C8h+psz]
0x180031d39  xor     ecx, ecx
0x180031d3b  test    rdi, rdi
0x180031d3e  jz      short loc_180031D6D
0x180031d40  lea     r8, [rsp+6C8h+lpFileName]; unsigned __int64 *
0x180031d45  mov     edx, 401h; unsigned __int64
0x180031d4a  mov     rcx, rdi; unsigned __int16 *
0x180031d4d  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x180031d52  xor     edx, edx
0x180031d54  test    eax, eax
0x180031d56  jns     short loc_180031D66
0x180031d58  mov     ebx, 80070057h
0x180031d5d  mov     [rsp+6C8h+var_688], ebx
0x180031d61  jmp     loc_180032840
0x180031d66  mov     r12, [rsp+6C8h+lpFileName]
0x180031d6b  jmp     short loc_180031D75
0x180031d6d  mov     r12, rcx
0x180031d70  mov     [rsp+6C8h+lpFileName], rcx
0x180031d75  add     r12, 106h
0x180031d7c  mov     [rsp+6C8h+lpFileName], r12
0x180031d81  lea     r8, [r12+r12]; dwBytes
0x180031d85  xor     edx, edx; dwFlags
0x180031d87  mov     rcx, [rsp+6C8h+hHeap]; hHeap
0x180031d8c  call    cs:__imp_HeapAlloc
0x180031d93  nop     dword ptr [rax+rax+00h]
0x180031d98  mov     r13, rax
0x180031d9b  mov     [rsp+6C8h+var_660], rax
0x180031da0  mov     r11, [rsp+6C8h+lpMem]
0x180031da5  xor     edx, edx
0x180031da7  test    r11, r11
0x180031daa  jz      loc_18003229E
0x180031db0  test    rax, rax
0x180031db3  jz      loc_18003229E
0x180031db9  test    r15, r15
0x180031dbc  jnz     loc_1800322A8
0x180031dc2  test    rdi, rdi
0x180031dc5  jz      loc_18003229E
0x180031dcb  mov     [rsp+6C8h+nLengthNeeded], edx
0x180031dcf  mov     [rsp+6C8h+var_664], dx
0x180031dd4  mov     [rsp+6C8h+Str], rdx
0x180031ddc  mov     r13d, edx
0x180031ddf  mov     [rsp+6C8h+var_610], rdx
0x180031de7  mov     [rsp+6C8h+var_640], rdx
0x180031def  mov     [rsp+6C8h+var_628], esi
0x180031df6  mov     [rsp+6C8h+var_618], rdx
0x180031dfe  lea     r8, [rsp+6C8h+var_618]; pcchLength
0x180031e06  mov     edx, 401h; cchMax
0x180031e0b  mov     rcx, rdi; psz
0x180031e0e  call    StringLengthWorkerW
0x180031e13  mov     r8d, eax
0x180031e16  mov     rdi, [rsp+6C8h+var_618]
0x180031e1e  xor     edx, edx; dwFlags
0x180031e20  mov     eax, edx
0x180031e22  test    r8d, r8d
0x180031e25  cmovs   rdi, rdx
0x180031e29  mov     [rsp+6C8h+var_618], rdi
0x180031e31  jns     short loc_180031E46
0x180031e33  mov     ebx, 80070057h
0x180031e38  mov     [rsp+6C8h+var_688], ebx
0x180031e3c  mov     r13, [rsp+6C8h+var_660]
0x180031e41  jmp     loc_180032840
0x180031e46  add     rdi, rsi
0x180031e49  mov     [rsp+6C8h+var_618], rdi
0x180031e51  lea     r8, [rdi+rdi]; dwBytes
0x180031e55  mov     rcx, [rsp+6C8h+hHeap]; hHeap
0x180031e5a  call    cs:__imp_HeapAlloc
0x180031e61  nop     dword ptr [rax+rax+00h]
0x180031e66  mov     r15, rax
0x180031e69  mov     [rsp+6C8h+pcchLength], rax
0x180031e71  xor     edx, edx; dwFlags
0x180031e73  mov     r8d, 20Ah; dwBytes
0x180031e79  mov     rcx, [rsp+6C8h+hHeap]; hHeap
0x180031e7e  call    cs:__imp_HeapAlloc
0x180031e85  nop     dword ptr [rax+rax+00h]
0x180031e8a  mov     r11, rax
0x180031e8d  mov     [rsp+6C8h+lpFileName], rax
0x180031e92  xor     edx, edx
0x180031e94  test    r15, r15
0x180031e97  jz      loc_180032294
0x180031e9d  test    rax, rax
0x180031ea0  jz      loc_180032294
0x180031ea6  mov     r8, [rsp+6C8h+psz]; unsigned __int16 *
0x180031eae  mov     rdx, rdi; unsigned __int64
0x180031eb1  mov     rcx, r15; unsigned __int16 *
0x180031eb4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031eb9  xor     edx, edx
0x180031ebb  test    eax, eax
0x180031ebd  jns     short loc_180031ECA
0x180031ebf  mov     ebx, eax
0x180031ec1  mov     [rsp+6C8h+var_688], eax
0x180031ec5  jmp     loc_180031E3C
0x180031eca  mov     rdi, r15
0x180031ecd  mov     [rsp+6C8h+var_640], r15
0x180031ed5  movzx   eax, word ptr [r15]
0x180031ed9  mov     ecx, 22h ; '"'
0x180031ede  cmp     ax, cx
0x180031ee1  jnz     short loc_180031F32
0x180031ee3  mov     [rsp+6C8h+var_628], edx
0x180031eea  lea     rdi, [r15+2]
0x180031eee  mov     [rsp+6C8h+var_640], rdi
0x180031ef6  mov     rax, rdi
0x180031ef9  mov     [rsp+6C8h+Str], rax
0x180031f01  cmp     [rdi], dx
0x180031f04  jz      short loc_180031F2A
0x180031f06  cmp     [rdi], cx
0x180031f09  jnz     short loc_180031F1C
0x180031f0b  mov     [rsp+6C8h+nLengthNeeded], ecx
0x180031f0f  mov     [rsp+6C8h+var_664], cx
0x180031f14  mov     r15d, 20h ; ' '
0x180031f1a  jmp     short loc_180031F8A
0x180031f1c  add     rdi, 2
  ... truncated ...
```
