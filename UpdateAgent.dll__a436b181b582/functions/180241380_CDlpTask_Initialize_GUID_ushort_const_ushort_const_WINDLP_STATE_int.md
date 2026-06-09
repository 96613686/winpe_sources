# CDlpTask::Initialize(_GUID,ushort const *,ushort const *,WINDLP_STATE,int)

- ea: `0x180241380`
- end: `0x18024297f`
- name: `?Initialize@CDlpTask@@QEAAJU_GUID@@PEBG1W4WINDLP_STATE@@H@Z`
- size: `5631`
- prototype: `int __high(struct _GUID, const unsigned __int16 *, const unsigned __int16 *, enum WINDLP_STATE, int)`
- caller_count: `2`
- callee_count: `15`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x18022f350`
- `0x1802324e0`

## callees

- `0x1800059d0`
- `0x180006a18`
- `0x180008fbc`
- `0x180039f90`
- `0x18006968c`
- `0x180077664`
- `0x18022edf8`
- `0x180233cf0`
- `0x18023f308`
- `0x180241380`
- `0x180247474`
- `0x18024bb90`
- `0x18024bd68`
- `0x18029ea98`
- `0x1802b1010`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180241ae2`
- `api-ms-win-core-file-l1-1-0!GetFullPathNameW` at `0x180241ae2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180241a2f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180241b75`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180241a2f`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180241b75`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180241589`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180241650`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180241717`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180242490`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180242557`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180242620`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180241589`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180241650`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180241717`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180242490`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180242557`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x180242620`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180241420`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180242373`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180241420`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180242373`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802413f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180242330`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1802413f6`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180242330`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802414c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802414ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180242411`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180242457`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802414c7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1802414ff`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180242411`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180242457`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802414dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180241513`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180242426`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18024246c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1802414dd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180241513`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180242426`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18024246c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802415c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180241687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024174e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180241af2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802424c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024258e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180242657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180242764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180242878`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802415c0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180241687`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024174e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180241af2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1802424c7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18024258e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180242657`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180242764`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180242878`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18024272d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180242841`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18024272d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180242841`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802415a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024166b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180241732`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802424ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180242572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024263b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180242748`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024285c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802415a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024166b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180241732`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1802424ab`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180242572`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024263b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180242748`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18024285c`

## string_xrefs

- `0x18024148a`: `CDlpTask::Initialize`
- `0x180241ca4`: `CDlpTask::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::Initialize(__int64 a1, __int128 *a2, void *a3, WCHAR *a4, unsigned int a5, int a6)
{
  _DWORD *v10; // rdi
  struct _RTL_CRITICAL_SECTION *v11; // rbx
  signed int v12; // edi
  __int64 v13; // rax
  __int64 v14; // rcx
  int v15; // eax
  __int64 v16; // rdx
  __int64 v17; // r12
  HANDLE v18; // rax
  void *v19; // rbx
  HANDLE v20; // rax
  HANDLE EventW; // rbx
  void *v23; // rcx
  signed int LastError; // eax
  HANDLE v25; // rbx
  void *v26; // rcx
  signed int v27; // eax
  HANDLE v28; // rbx
  void *v29; // rcx
  signed int v30; // eax
  __int64 v31; // rdx
  __int64 v32; // rcx
  int StringCch; // eax
  __int64 v34; // rdx
  int Internal; // eax
  __int64 v36; // rdx
  DWORD FileAttributesW; // ebx
  int v38; // ebx
  signed int v39; // eax
  DWORD v40; // ebx
  int v41; // ebx
  int v42; // eax
  __int64 v43; // rdx
  int v44; // eax
  __int64 v45; // rdx
  __int64 v46; // rax
  __int64 v47; // rcx
  int v48; // eax
  __int64 v49; // rdx
  int v50; // eax
  __int64 v51; // rdx
  int v52; // eax
  __int64 v53; // rdx
  __int64 v54; // rax
  int v55; // eax
  __int64 v56; // rdx
  int v57; // eax
  __int64 v58; // rdx
  int v59; // eax
  __int64 v60; // rdx
  __int64 v61; // rcx
  int v62; // eax
  __int64 v63; // rdx
  __int64 v64; // rdi
  __int64 v65; // rbx
  HANDLE ProcessHeap; // rax
  __int64 v67; // rdi
  __int64 v68; // rbx
  HANDLE v69; // rax
  HANDLE v70; // rbx
  void *v71; // rcx
  signed int v72; // eax
  HANDLE v73; // rbx
  void *v74; // rcx
  signed int v75; // eax
  HANDLE v76; // rbx
  void *v77; // rcx
  signed int v78; // eax
  HANDLE Thread; // rbx
  void *v80; // rcx
  signed int v81; // eax
  HANDLE v82; // rbx
  void *v83; // rcx
  signed int v84; // eax
  int v85; // eax
  __int64 v86; // rdx
  __int64 dwCreationFlags; // [rsp+20h] [rbp-E0h]
  DWORD dwCreationFlagsa; // [rsp+20h] [rbp-E0h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-D8h]
  int lpThreadIda; // [rsp+28h] [rbp-D8h]
  int v91; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v92; // [rsp+40h] [rbp-C0h]
  __int64 v93; // [rsp+48h] [rbp-B8h]
  __int64 v94; // [rsp+50h] [rbp-B0h] BYREF
  __int64 v95; // [rsp+58h] [rbp-A8h]
  LPWSTR FilePart; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v97; // [rsp+70h] [rbp-90h] BYREF
  int v98; // [rsp+80h] [rbp-80h]
  __int64 v99; // [rsp+90h] [rbp-70h]
  WCHAR Buffer[1040]; // [rsp+A0h] [rbp-60h] BYREF

  v99 = -2;
  v94 = 0;
  v93 = 0;
  v95 = 0;
  v92 = 0;
  FilePart = 0;
  v10 = (_DWORD *)(a1 + 296);
  v11 = (struct _RTL_CRITICAL_SECTION *)(a1 + 312);
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 312));
  v98 = 1;
  LODWORD(v10) = *v10;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  LeaveCriticalSection(v11);
  v98 = 0;
  if ( (_DWORD)v10 != -21037378 )
  {
    v12 = -2147023649;
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
    {
LABEL_8:
      v17 = 0;
      goto LABEL_9;
    }
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
    v14 = 0;
    if ( !v13 )
    {
LABEL_7:
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
      goto LABEL_8;
    }
    lpThreadIda = -2147023649;
    dwCreationFlagsa = 723;
LABEL_5:
    v15 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v13,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpTask::Initialize",
            dwCreationFlagsa,
            lpThreadIda);
    v14 = (unsigned int)v15;
    if ( v15 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v15, v16);
    goto LABEL_7;
  }
  *(_DWORD *)(a1 + 1432) = 30000;
  *(_DWORD *)(a1 + 1436) = 1000;
  *(_DWORD *)(a1 + 1440) = 1000;
  EventW = CreateEventW(0, 1, 0, 0);
  v23 = *(void **)(a1 + 232);
  if ( v23 )
    CloseHandle(v23);
  if ( !EventW )
  {
    *(_QWORD *)(a1 + 232) = 0;
    LastError = GetLastError();
    v12 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v12 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
      goto LABEL_8;
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
    v14 = 0;
    if ( v12 >= 0 || !v13 )
      goto LABEL_7;
    lpThreadIda = v12;
    dwCreationFlagsa = 736;
    goto LABEL_5;
  }
  *(_QWORD *)(a1 + 232) = EventW;
  v25 = CreateEventW(0, 0, 0, 0);
  v26 = *(void **)(a1 + 240);
  if ( v26 )
    CloseHandle(v26);
  if ( !v25 )
  {
    *(_QWORD *)(a1 + 240) = 0;
    v27 = GetLastError();
    v12 = v27;
    if ( v27 )
    {
      if ( v27 > 0 )
        v12 = (unsigned __int16)v27 | 0x80070000;
    }
    else
    {
      v12 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
      goto LABEL_8;
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
    v14 = 0;
    if ( v12 >= 0 || !v13 )
      goto LABEL_7;
    lpThreadIda = v12;
    dwCreationFlagsa = 739;
    goto LABEL_5;
  }
  *(_QWORD *)(a1 + 240) = v25;
  v28 = CreateEventW(0, 0, 0, 0);
  v29 = *(void **)(a1 + 248);
  if ( v29 )
    CloseHandle(v29);
  if ( !v28 )
  {
    *(_QWORD *)(a1 + 248) = 0;
    v30 = GetLastError();
    v12 = v30;
    if ( v30 )
    {
      if ( v30 > 0 )
        v12 = (unsigned __int16)v30 | 0x80070000;
    }
    else
    {
      v12 = -2147467259;
    }
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
      goto LABEL_8;
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
    v14 = 0;
    if ( v12 >= 0 || !v13 )
      goto LABEL_7;
    lpThreadIda = v12;
    dwCreationFlagsa = 742;
    goto LABEL_5;
  }
  *(_QWORD *)(a1 + 248) = v28;
  if ( memcmp_0(&WINDLP_TRANSPORT_NONE, a2, 0x10u) )
  {
    v32 = *(_QWORD *)(a1 + 1304);
    v97 = *a2;
    v12 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v32 + 80LL))(v32, &v97, &v94);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_8;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_7;
      lpThreadIda = v12;
      dwCreationFlagsa = 749;
      goto LABEL_5;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 56LL))(v94, a1 + 1488);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_8;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_7;
      lpThreadIda = v12;
      dwCreationFlagsa = 753;
      goto LABEL_5;
    }
    v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v94 + 64LL))(v94, a1 + 1428);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_8;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_7;
      lpThreadIda = v12;
      dwCreationFlagsa = 757;
      goto LABEL_5;
    }
  }
  if ( a3 )
  {
    v91 = 0;
    StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a3, &v91);
    v12 = StringCch;
    if ( StringCch >= 0 )
    {
      Internal = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a3);
      v12 = Internal;
      if ( Internal < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)Internal, v36);
      v93 = v95;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)StringCch, v34);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_8;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_7;
      lpThreadIda = v12;
      dwCreationFlagsa = 765;
      goto LABEL_5;
    }
  }
  if ( !a4 )
  {
    v17 = 0;
    goto LABEL_120;
  }
  if ( a6 )
  {
    FileAttributesW = GetFileAttributesW(a4);
    if ( FileAttributesW == -1 )
      v38 = 0;
    else
      v38 = (FileAttributesW >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v38 )
    {
      v12 = -2147024893;
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_8;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_7;
      lpThreadIda = -2147024893;
      dwCreationFlagsa = 775;
      goto LABEL_5;
    }
    FilePart = 0;
    memset_0(Buffer, 0, sizeof(Buffer));
    if ( !GetFullPathNameW(a4, 0x410u, Buffer, &FilePart) )
    {
      v39 = GetLastError();
      v12 = v39;
      if ( v39 )
      {
        if ( v39 > 0 )
          v12 = (unsigned __int16)v39 | 0x80070000;
      }
      else
      {
        v12 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_8;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( v12 >= 0 || !v13 )
        goto LABEL_7;
      lpThreadIda = v12;
      dwCreationFlagsa = 781;
      goto LABEL_5;
    }
    v40 = GetFileAttributesW(Buffer);
    if ( v40 == -1 )
      v41 = 0;
    else
      v41 = (v40 >> 4) & 1;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v41 )
    {
      v12 = -2147024893;
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_8;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_7;
      lpThreadIda = -2147024893;
      dwCreationFlagsa = 786;
      goto LABEL_5;
    }
    v91 = 0;
    v42 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &v91);
    v12 = v42;
    if ( v42 >= 0 )
    {
      v44 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer);
      v12 = v44;
      if ( v44 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v44, v45);
      v17 = v92;
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v42, v43);
      v17 = 0;
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 791;
      goto LABEL_107;
    }
LABEL_120:
    v54 = *(_QWORD *)(a1 + 1304);
    if ( v54 )
    {
      v12 = 0;
      *(_QWORD *)(a1 + 96) = v54;
    }
    else
    {
      v12 = -2147024809;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(2147942487LL, v31);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
    if ( v12 < 0 )
    {
      if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
      {
        v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
        v47 = 0;
        if ( v46 )
        {
          LODWORD(lpThreadId) = v12;
          LODWORD(dwCreationFlags) = 804;
          goto LABEL_107;
        }
LABEL_109:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v47);
        goto LABEL_9;
      }
      goto LABEL_9;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 432));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 808;
      goto LABEL_107;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 488));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 809;
      goto LABEL_107;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 544));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 810;
      goto LABEL_107;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 600));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 811;
      goto LABEL_107;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 656));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 812;
      goto LABEL_107;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 712));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 813;
      goto LABEL_107;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 768));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 814;
      goto LABEL_107;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 824));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 815;
      goto LABEL_107;
    }
    v55 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 888));
    v12 = v55;
    if ( v55 < 0 || (v55 = CDword::Set((CDword *)(a1 + 872), 0xFFFFFFFF), v12 = v55, v55 < 0) )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v55, v56);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 816;
      goto LABEL_107;
    }
    v57 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 1256));
    v12 = v57;
    if ( v57 < 0 || (v57 = CDword::Set((CDword *)(a1 + 1240), 0xFFFFFFFF), v12 = v57, v57 < 0) )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v57, v58);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 817;
      goto LABEL_107;
    }
    v12 = CProgressData::Init((CProgressData *)(a1 + 936));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 818;
      goto LABEL_107;
    }
    v12 = CProgressData::Init((CProgressData *)(a1 + 1096));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_9;
      v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v47 = 0;
      if ( !v46 )
        goto LABEL_109;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 819;
      goto LABEL_107;
    }
    v59 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 1048));
    v12 = v59;
    if ( v59 >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1048));
      v98 = 1;
      v62 = CProgressList::Reset((CProgressList *)(a1 + 1016));
      v12 = v62;
      if ( v62 >= 0 )
        *(_DWORD *)(a1 + 1020) = 30;
      else
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v62, v63);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
      if ( v98 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1048));
        v98 = 0;
      }
      if ( v12 >= 0 )
      {
LABEL_191:
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
        if ( v12 >= 0 )
        {
          if ( v93 )
          {
            v64 = v93;
            v93 = 0;
            v65 = *(_QWORD *)(a1 + 224);
            if ( v65 )
            {
              ProcessHeap = GetProcessHeap();
              HeapFree(ProcessHeap, 0, (LPVOID)(v65 - 4));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            *(_QWORD *)(a1 + 224) = v64;
          }
          if ( v17 )
          {
            v67 = v17;
            v17 = 0;
            v68 = *(_QWORD *)(a1 + 216);
            if ( v68 )
            {
              v69 = GetProcessHeap();
              HeapFree(v69, 0, (LPVOID)(v68 - 4));
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
            }
            *(_QWORD *)(a1 + 216) = v67;
          }
          v70 = CreateEventW(0, 0, 0, 0);
          v71 = *(void **)(a1 + 256);
          if ( v71 )
            CloseHandle(v71);
          if ( v70 )
          {
            *(_QWORD *)(a1 + 256) = v70;
            v73 = CreateEventW(0, 0, 0, 0);
            v74 = *(void **)(a1 + 264);
            if ( v74 )
              CloseHandle(v74);
            if ( v73 )
            {
              *(_QWORD *)(a1 + 264) = v73;
              v76 = CreateEventW(0, 1, 0, 0);
              v77 = *(void **)(a1 + 272);
              if ( v77 )
                CloseHandle(v77);
              if ( v76 )
              {
                *(_QWORD *)(a1 + 272) = v76;
                *(_QWORD *)(a1 + 1328) = a1;
                *(_QWORD *)(a1 + 1352) = a1 + 392;
                *(_QWORD *)(a1 + 1360) = a1 + 536;
                *(_QWORD *)(a1 + 1336) = *(_QWORD *)(a1 + 256);
                *(_QWORD *)(a1 + 1344) = v76;
                Thread = CreateThread(0, 0, CDlpTask::TaskOperationThreadProc, (LPVOID)(a1 + 1328), 0, 0);
                v80 = *(void **)(a1 + 280);
                if ( v80 )
                  CloseHandle(v80);
                if ( Thread )
                {
                  *(_QWORD *)(a1 + 280) = Thread;
                  *(_QWORD *)(a1 + 1368) = a1;
                  *(_QWORD *)(a1 + 1392) = a1 + 408;
                  *(_QWORD *)(a1 + 1400) = a1 + 592;
                  *(_QWORD *)(a1 + 1376) = *(_QWORD *)(a1 + 264);
                  *(_QWORD *)(a1 + 1384) = *(_QWORD *)(a1 + 272);
                  v82 = CreateThread(0, 0, CDlpTask::TaskOperationThreadProc, (LPVOID)(a1 + 1368), 0, 0);
                  v83 = *(void **)(a1 + 288);
                  if ( v83 )
                    CloseHandle(v83);
                  if ( v82 )
                  {
                    *(_QWORD *)(a1 + 288) = v82;
                    v85 = CDlpState::Set(a1 + 296, a5);
                    v12 = v85;
                    if ( v85 < 0 )
                      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v85, v86);
                    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
                    if ( v12 >= 0 || !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
                      goto LABEL_9;
                    v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
                    v47 = 0;
                    if ( !v46 )
                      goto LABEL_109;
                    LODWORD(lpThreadId) = v12;
                    LODWORD(dwCreationFlags) = 876;
                  }
                  else
                  {
                    *(_QWORD *)(a1 + 288) = 0;
                    v84 = GetLastError();
                    v12 = v84;
                    if ( v84 )
                    {
                      if ( v84 > 0 )
                        v12 = (unsigned __int16)v84 | 0x80070000;
                    }
                    else
                    {
                      v12 = -2147467259;
                    }
                    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
                      goto LABEL_9;
                    v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
                    v47 = 0;
                    if ( v12 >= 0 || !v46 )
                      goto LABEL_109;
                    LODWORD(lpThreadId) = v12;
                    LODWORD(dwCreationFlags) = 872;
                  }
                }
                else
                {
                  *(_QWORD *)(a1 + 280) = 0;
                  v81 = GetLastError();
                  v12 = v81;
                  if ( v81 )
                  {
                    if ( v81 > 0 )
                      v12 = (unsigned __int16)v81 | 0x80070000;
                  }
                  else
                  {
                    v12 = -2147467259;
                  }
                  if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
                    goto LABEL_9;
                  v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
                  v47 = 0;
                  if ( v12 >= 0 || !v46 )
                    goto LABEL_109;
                  LODWORD(lpThreadId) = v12;
                  LODWORD(dwCreationFlags) = 858;
                }
              }
              else
              {
                *(_QWORD *)(a1 + 272) = 0;
                v78 = GetLastError();
                v12 = v78;
                if ( v78 )
                {
                  if ( v78 > 0 )
                    v12 = (unsigned __int16)v78 | 0x80070000;
                }
                else
                {
                  v12 = -2147467259;
                }
                if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
                  goto LABEL_9;
                v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
                v47 = 0;
                if ( v12 >= 0 || !v46 )
                  goto LABEL_109;
                LODWORD(lpThreadId) = v12;
                LODWORD(dwCreationFlags) = 842;
              }
            }
            else
            {
              *(_QWORD *)(a1 + 264) = 0;
              v75 = GetLastError();
              v12 = v75;
              if ( v75 )
              {
                if ( v75 > 0 )
                  v12 = (unsigned __int16)v75 | 0x80070000;
              }
              else
              {
                v12 = -2147467259;
              }
              if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
                goto LABEL_9;
              v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
              v47 = 0;
              if ( v12 >= 0 || !v46 )
                goto LABEL_109;
              LODWORD(lpThreadId) = v12;
              LODWORD(dwCreationFlags) = 839;
            }
          }
          else
          {
            *(_QWORD *)(a1 + 256) = 0;
            v72 = GetLastError();
            v12 = v72;
            if ( v72 )
            {
              if ( v72 > 0 )
                v12 = (unsigned __int16)v72 | 0x80070000;
            }
            else
            {
              v12 = -2147467259;
            }
            if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
              goto LABEL_9;
            v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
            v47 = 0;
            if ( v12 >= 0 || !v46 )
              goto LABEL_109;
            LODWORD(lpThreadId) = v12;
            LODWORD(dwCreationFlags) = 836;
          }
        }
        else
        {
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_9;
          v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v47 = 0;
          if ( !v46 )
            goto LABEL_109;
          LODWORD(lpThreadId) = v12;
          LODWORD(dwCreationFlags) = 820;
        }
LABEL_107:
        v48 = CDlpLogT<CEmptyType>::DlpLogFormat(
                v46,
                4,
                L"%s(%d): Result = 0x%X",
                L"CDlpTask::Initialize",
                dwCreationFlags,
                lpThreadId);
        v47 = (unsigned int)v48;
        if ( v48 < 0 )
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v48, v49);
        goto LABEL_109;
      }
      v61 = (unsigned int)v12;
    }
    else
    {
      v61 = (unsigned int)v59;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v61, v60);
    goto LABEL_191;
  }
  v91 = 0;
  v50 = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(a4, &v91);
  v12 = v50;
  if ( v50 >= 0 )
  {
    v52 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(a4);
    v12 = v52;
    if ( v52 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v52, v53);
    v17 = v92;
  }
  else
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v50, v51);
    v17 = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
  if ( v12 >= 0 )
    goto LABEL_120;
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
  {
    v46 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
    v47 = 0;
    if ( v46 )
    {
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 798;
      goto LABEL_107;
    }
    goto LABEL_109;
  }
LABEL_9:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
  if ( v17 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, (LPVOID)(v17 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v93 )
  {
    v19 = (void *)(v93 - 4);
    v20 = GetProcessHeap();
    HeapFree(v20, 0, v19);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v94 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v94 + 16LL))(v94);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180241380  push    rbp
0x180241382  push    rbx
0x180241383  push    rsi
0x180241384  push    rdi
0x180241385  push    r12
0x180241387  push    r13
0x180241389  push    r14
0x18024138b  push    r15
0x18024138d  lea     rbp, [rsp-7D8h]
0x180241395  sub     rsp, 8D8h
0x18024139c  mov     [rbp+810h+var_880], 0FFFFFFFFFFFFFFFEh
0x1802413a4  mov     rax, cs:__security_cookie
0x1802413ab  xor     rax, rsp
0x1802413ae  mov     [rbp+810h+var_50], rax
0x1802413b5  mov     r14, r9
0x1802413b8  mov     r15, r8
0x1802413bb  mov     r12, rdx
0x1802413be  mov     rsi, rcx
0x1802413c1  mov     [rsp+910h+var_8C0], 0
0x1802413ca  xor     eax, eax
0x1802413cc  mov     [rsp+910h+var_8C8], rax
0x1802413d1  mov     [rsp+910h+var_8B8], rax
0x1802413d6  xor     r13d, r13d
0x1802413d9  mov     [rsp+910h+var_8E0], r13
0x1802413de  mov     [rsp+910h+var_8D0], r13
0x1802413e3  mov     [rsp+910h+FilePart], r13
0x1802413e8  lea     rdi, [rcx+128h]
0x1802413ef  lea     rbx, [rdi+10h]
0x1802413f3  mov     rcx, rbx; lpCriticalSection
0x1802413f6  call    cs:__imp_EnterCriticalSection
0x1802413fd  nop     dword ptr [rax+rax+00h]
0x180241402  mov     r13d, 1
0x180241408  mov     [rbp+810h+var_890], r13d
0x18024140c  mov     edi, [rdi]
0x18024140e  xor     ecx, ecx
0x180241410  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180241415  nop
0x180241416  mov     eax, [rbp+810h+var_890]
0x180241419  test    eax, eax
0x18024141b  jz      short loc_180241433
0x18024141d  mov     rcx, rbx; lpCriticalSection
0x180241420  call    cs:__imp_LeaveCriticalSection
0x180241427  nop     dword ptr [rax+rax+00h]
0x18024142c  mov     [rbp+810h+var_890], 0
0x180241433  cmp     edi, 0FEBEFEBEh
0x180241439  jz      loc_180241563
0x18024143f  mov     edi, 800704DFh
0x180241444  mov     rax, [rsi+0B0h]
0x18024144b  lea     rcx, [rsi+0B0h]
0x180241452  mov     rax, [rax+10h]
0x180241456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024145b  test    rax, rax
0x18024145e  jz      short loc_1802414B5
0x180241460  mov     rax, [rsi+0B0h]
0x180241467  lea     rcx, [rsi+0B0h]
0x18024146e  mov     rax, [rax+10h]
0x180241472  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180241477  xor     ecx, ecx
0x180241479  test    rax, rax
0x18024147c  jz      short loc_1802414B0
0x18024147e  mov     dword ptr [rsp+910h+lpThreadId], edi
0x180241482  mov     dword ptr [rsp+910h+dwCreationFlags], 2D3h
0x18024148a  lea     r9, aCdlptaskInitia; "CDlpTask::Initialize"
0x180241491  lea     r8, aSDResult0xX; "%s(%d): Result = 0x%X"
0x180241498  mov     edx, 4
0x18024149d  mov     rcx, rax
0x1802414a0  call    ?DlpLogFormat@?$CDlpLogT@VCEmptyType@@@@SAJPEAVIDlpManager@@W4WINDLP_LOGLEVEL@@PEBGZZ; CDlpLogT<CEmptyType>::DlpLogFormat(IDlpManager *,WINDLP_LOGLEVEL,ushort const *,...)
0x1802414a5  test    eax, eax
0x1802414a7  mov     ecx, eax
0x1802414a9  jns     short loc_1802414B0
0x1802414ab  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1802414b0  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1802414b5  mov     r12, [rsp+910h+var_8E0]
0x1802414ba  mov     ecx, edi
0x1802414bc  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1802414c1  nop
0x1802414c2  test    r12, r12
0x1802414c5  jz      short loc_1802414F1
0x1802414c7  call    cs:__imp_GetProcessHeap
0x1802414ce  nop     dword ptr [rax+rax+00h]
0x1802414d3  mov     rcx, rax; hHeap
0x1802414d6  lea     r8, [r12-4]; lpMem
0x1802414db  xor     edx, edx; dwFlags
0x1802414dd  call    cs:__imp_HeapFree
0x1802414e4  nop     dword ptr [rax+rax+00h]
0x1802414e9  xor     ecx, ecx
0x1802414eb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1802414f0  nop
0x1802414f1  mov     rax, [rsp+910h+var_8C8]
0x1802414f6  test    rax, rax
0x1802414f9  jz      short loc_180241527
0x1802414fb  lea     rbx, [rax-4]
0x1802414ff  call    cs:__imp_GetProcessHeap
0x180241506  nop     dword ptr [rax+rax+00h]
0x18024150b  mov     rcx, rax; hHeap
0x18024150e  mov     r8, rbx; lpMem
0x180241511  xor     edx, edx; dwFlags
0x180241513  call    cs:__imp_HeapFree
0x18024151a  nop     dword ptr [rax+rax+00h]
0x18024151f  xor     ecx, ecx
0x180241521  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180241526  nop
0x180241527  mov     rcx, [rsp+910h+var_8C0]
0x18024152c  test    rcx, rcx
0x18024152f  jz      short loc_18024153D
0x180241531  mov     rax, [rcx]
0x180241534  mov     rax, [rax+10h]
0x180241538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024153d  mov     eax, edi
0x18024153f  mov     rcx, [rbp+810h+var_50]
0x180241546  xor     rcx, rsp; StackCookie
0x180241549  call    __security_check_cookie
0x18024154e  add     rsp, 8D8h
0x180241555  pop     r15
0x180241557  pop     r14
0x180241559  pop     r13
0x18024155b  pop     r12
0x18024155d  pop     rdi
0x18024155e  pop     rsi
0x18024155f  pop     rbx
0x180241560  pop     rbp
0x180241561  retn
0x180241563  mov     dword ptr [rsi+598h], 7530h
0x18024156d  mov     eax, 3E8h
0x180241572  mov     [rsi+59Ch], eax
0x180241578  mov     [rsi+5A0h], eax
0x18024157e  xor     r9d, r9d; lpName
0x180241581  xor     r8d, r8d; bInitialState
0x180241584  mov     edx, r13d; bManualReset
0x180241587  xor     ecx, ecx; lpEventAttributes
0x180241589  call    cs:__imp_CreateEventW
0x180241590  nop     dword ptr [rax+rax+00h]
0x180241595  mov     rbx, rax
0x180241598  mov     rcx, [rsi+0E8h]; hObject
0x18024159f  test    rcx, rcx
0x1802415a2  jz      short loc_1802415B0
0x1802415a4  call    cs:__imp_CloseHandle
0x1802415ab  nop     dword ptr [rax+rax+00h]
0x1802415b0  test    rbx, rbx
0x1802415b3  jnz     loc_18024163F
0x1802415b9  mov     [rsi+0E8h], rbx
0x1802415c0  call    cs:__imp_GetLastError
0x1802415c7  nop     dword ptr [rax+rax+00h]
0x1802415cc  mov     edi, eax
0x1802415ce  test    eax, eax
0x1802415d0  jnz     short loc_1802415D9
0x1802415d2  mov     edi, 80004005h
0x1802415d7  jmp     short loc_1802415E4
0x1802415d9  jle     short loc_1802415E4
0x1802415db  movzx   edi, ax
0x1802415de  or      edi, 80070000h
0x1802415e4  mov     rax, [rsi+0B0h]
0x1802415eb  lea     rcx, [rsi+0B0h]
0x1802415f2  mov     rax, [rax+10h]
0x1802415f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802415fb  test    rax, rax
0x1802415fe  jz      loc_1802414B5
0x180241604  mov     rax, [rsi+0B0h]
0x18024160b  lea     rcx, [rsi+0B0h]
0x180241612  mov     rax, [rax+10h]
0x180241616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024161b  xor     ecx, ecx
0x18024161d  test    edi, edi
0x18024161f  jns     loc_1802414B0
0x180241625  test    rax, rax
0x180241628  jz      loc_1802414B0
0x18024162e  mov     dword ptr [rsp+910h+lpThreadId], edi
0x180241632  mov     dword ptr [rsp+910h+dwCreationFlags], 2E0h
0x18024163a  jmp     loc_18024148A
0x18024163f  mov     [rsi+0E8h], rbx
0x180241646  xor     r9d, r9d; lpName
0x180241649  xor     r8d, r8d; bInitialState
0x18024164c  xor     edx, edx; bManualReset
0x18024164e  xor     ecx, ecx; lpEventAttributes
0x180241650  call    cs:__imp_CreateEventW
0x180241657  nop     dword ptr [rax+rax+00h]
0x18024165c  mov     rbx, rax
0x18024165f  mov     rcx, [rsi+0F0h]; hObject
0x180241666  test    rcx, rcx
0x180241669  jz      short loc_180241677
0x18024166b  call    cs:__imp_CloseHandle
0x180241672  nop     dword ptr [rax+rax+00h]
0x180241677  test    rbx, rbx
0x18024167a  jnz     loc_180241706
0x180241680  mov     [rsi+0F0h], rbx
0x180241687  call    cs:__imp_GetLastError
0x18024168e  nop     dword ptr [rax+rax+00h]
0x180241693  mov     edi, eax
0x180241695  test    eax, eax
0x180241697  jnz     short loc_1802416A0
0x180241699  mov     edi, 80004005h
0x18024169e  jmp     short loc_1802416AB
0x1802416a0  jle     short loc_1802416AB
0x1802416a2  movzx   edi, ax
0x1802416a5  or      edi, 80070000h
0x1802416ab  mov     rax, [rsi+0B0h]
0x1802416b2  lea     rcx, [rsi+0B0h]
0x1802416b9  mov     rax, [rax+10h]
0x1802416bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802416c2  test    rax, rax
0x1802416c5  jz      loc_1802414B5
0x1802416cb  mov     rax, [rsi+0B0h]
0x1802416d2  lea     rcx, [rsi+0B0h]
0x1802416d9  mov     rax, [rax+10h]
0x1802416dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802416e2  xor     ecx, ecx
0x1802416e4  test    edi, edi
0x1802416e6  jns     loc_1802414B0
0x1802416ec  test    rax, rax
0x1802416ef  jz      loc_1802414B0
0x1802416f5  mov     dword ptr [rsp+910h+lpThreadId], edi
0x1802416f9  mov     dword ptr [rsp+910h+dwCreationFlags], 2E3h
0x180241701  jmp     loc_18024148A
0x180241706  mov     [rsi+0F0h], rbx
0x18024170d  xor     r9d, r9d; lpName
0x180241710  xor     r8d, r8d; bInitialState
0x180241713  xor     edx, edx; bManualReset
0x180241715  xor     ecx, ecx; lpEventAttributes
0x180241717  call    cs:__imp_CreateEventW
0x18024171e  nop     dword ptr [rax+rax+00h]
0x180241723  mov     rbx, rax
0x180241726  mov     rcx, [rsi+0F8h]; hObject
0x18024172d  test    rcx, rcx
0x180241730  jz      short loc_18024173E
0x180241732  call    cs:__imp_CloseHandle
0x180241739  nop     dword ptr [rax+rax+00h]
0x18024173e  test    rbx, rbx
0x180241741  jnz     loc_1802417CD
0x180241747  mov     [rsi+0F8h], rbx
0x18024174e  call    cs:__imp_GetLastError
0x180241755  nop     dword ptr [rax+rax+00h]
0x18024175a  mov     edi, eax
0x18024175c  test    eax, eax
0x18024175e  jnz     short loc_180241767
0x180241760  mov     edi, 80004005h
0x180241765  jmp     short loc_180241772
0x180241767  jle     short loc_180241772
0x180241769  movzx   edi, ax
0x18024176c  or      edi, 80070000h
0x180241772  mov     rax, [rsi+0B0h]
0x180241779  lea     rcx, [rsi+0B0h]
0x180241780  mov     rax, [rax+10h]
0x180241784  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180241789  test    rax, rax
0x18024178c  jz      loc_1802414B5
0x180241792  mov     rax, [rsi+0B0h]
0x180241799  lea     rcx, [rsi+0B0h]
0x1802417a0  mov     rax, [rax+10h]
0x1802417a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1802417a9  xor     ecx, ecx
0x1802417ab  test    edi, edi
0x1802417ad  jns     loc_1802414B0
0x1802417b3  test    rax, rax
0x1802417b6  jz      loc_1802414B0
0x1802417bc  mov     dword ptr [rsp+910h+lpThreadId], edi
0x1802417c0  mov     dword ptr [rsp+910h+dwCreationFlags], 2E6h
0x1802417c8  jmp     loc_18024148A
0x1802417cd  mov     [rsi+0F8h], rbx
0x1802417d4  mov     r8d, 10h; Size
0x1802417da  mov     rdx, r12; Buf2
0x1802417dd  lea     rcx, WINDLP_TRANSPORT_NONE; Buf1
0x1802417e4  call    memcmp_0
0x1802417e9  test    eax, eax
0x1802417eb  jz      loc_180241954
0x1802417f1  mov     rcx, [rsi+518h]
0x1802417f8  movaps  xmm0, xmmword ptr [r12]
0x1802417fd  movdqa  [rsp+910h+var_8A0], xmm0
0x180241803  mov     rax, [rcx]
0x180241806  lea     r8, [rsp+910h+var_8C0]
0x18024180b  lea     rdx, [rsp+910h+var_8A0]
0x180241810  mov     rax, [rax+50h]
0x180241814  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180241819  mov     edi, eax
0x18024181b  test    eax, eax
0x18024181d  jns     short loc_180241872
0x18024181f  mov     rdx, [rsi+0B0h]
0x180241826  lea     rcx, [rsi+0B0h]
0x18024182d  mov     rax, [rdx+10h]
0x180241831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180241836  test    rax, rax
0x180241839  jz      loc_1802414B5
0x18024183f  mov     rax, [rsi+0B0h]
0x180241846  lea     rcx, [rsi+0B0h]
0x18024184d  mov     rax, [rax+10h]
0x180241851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180241856  xor     ecx, ecx
0x180241858  test    rax, rax
0x18024185b  jz      loc_1802414B0
0x180241861  mov     dword ptr [rsp+910h+lpThreadId], edi
0x180241865  mov     dword ptr [rsp+910h+dwCreationFlags], 2EDh
0x18024186d  jmp     loc_18024148A
0x180241872  mov     rcx, [rsp+910h+var_8C0]
0x180241877  mov     rax, [rcx]
0x18024187a  lea     rdx, [rsi+5D0h]
0x180241881  mov     rax, [rax+38h]
0x180241885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18024188a  mov     edi, eax
0x18024188c  test    eax, eax
0x18024188e  jns     short loc_1802418E3
0x180241890  mov     rax, [rsi+0B0h]
  ... truncated ...
```
