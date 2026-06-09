# WsbkExecuteRevertJournal(ushort const *,ushort const *,ushort const *,void (*)(ulong,ulong,void *),void *)

- ea: `0x18004927c`
- end: `0x180049e51`
- name: `?WsbkExecuteRevertJournal@@YAJPEBG00P6AXKKPEAX@Z1@Z`
- size: `3029`
- prototype: `__int64 __usercall@<rax>(const unsigned __int16 *@<rcx>, const unsigned __int16 *@<rdx>, const unsigned __int16 *@<r8>, void (*)(unsigned int, unsigned int, void *)@<r9>, void *)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, reparse_path, loader_planting, installer_update, broker_com_uri`

## callers

- `0x1800170f0`

## callees

- `0x180009e04`
- `0x18001c548`
- `0x18003bb74`
- `0x18003d0a0`
- `0x18003df50`
- `0x18004927c`
- `0x18004c180`
- `0x18004c9cc`
- `0x18004cac0`
- `0x18004d784`
- `0x18004d9c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180049a96`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180049a96`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180049aa6`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180049aa6`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800492d5`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x1800492d5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049347`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800494f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049ca5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049cbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049cf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049d0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049d29`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049347`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800494f0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049ca5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049cbe`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049cf3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049d0c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180049d29`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049358`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049501`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049358`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180049501`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049cb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049ccc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049d01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049d1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049d37`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049cb3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049ccc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049d01`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049d1a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180049d37`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004947a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004968d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800496fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004978e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800498d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800499a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800499ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049377`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049400`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004947a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049522`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049596`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049617`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004968d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800496fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004978e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049815`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049833`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800498d3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049944`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800499a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800499ff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049ad7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049b83`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049bbf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049bd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c14`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049c2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049d7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180049df6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180049806`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180049806`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049abf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049d56`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049abf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049d46`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180049d56`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180049c06`
- `api-ms-win-core-file-l2-1-2!CopyFileW` at `0x180049c06`
- `ntdll!RtlNtStatusToDosError` at `0x180049a6f`
- `ntdll!RtlNtStatusToDosError` at `0x180049a6f`
- `WDSCORE!CurrentIP` at `0x18004937f`
- `WDSCORE!CurrentIP` at `0x180049408`
- `WDSCORE!CurrentIP` at `0x180049482`
- `WDSCORE!CurrentIP` at `0x18004952a`
- `WDSCORE!CurrentIP` at `0x18004959e`
- `WDSCORE!CurrentIP` at `0x18004961f`
- `WDSCORE!CurrentIP` at `0x180049695`
- `WDSCORE!CurrentIP` at `0x180049703`
- `WDSCORE!CurrentIP` at `0x180049796`
- `WDSCORE!CurrentIP` at `0x18004983b`
- `WDSCORE!CurrentIP` at `0x1800498db`
- `WDSCORE!CurrentIP` at `0x18004994c`
- `WDSCORE!CurrentIP` at `0x1800499a9`
- `WDSCORE!CurrentIP` at `0x180049a07`
- `WDSCORE!CurrentIP` at `0x180049adf`
- `WDSCORE!CurrentIP` at `0x180049c34`
- `WDSCORE!CurrentIP` at `0x180049d87`
- `WDSCORE!CurrentIP` at `0x180049dfe`
- `WDSCORE!CurrentIP` at `0x18004937f`
- `WDSCORE!CurrentIP` at `0x180049408`
- `WDSCORE!CurrentIP` at `0x180049482`
- `WDSCORE!CurrentIP` at `0x18004952a`
- `WDSCORE!CurrentIP` at `0x18004959e`
- `WDSCORE!CurrentIP` at `0x18004961f`
- `WDSCORE!CurrentIP` at `0x180049695`
- `WDSCORE!CurrentIP` at `0x180049703`
- `WDSCORE!CurrentIP` at `0x180049796`
- `WDSCORE!CurrentIP` at `0x18004983b`
- `WDSCORE!CurrentIP` at `0x1800498db`
- `WDSCORE!CurrentIP` at `0x18004994c`
- `WDSCORE!CurrentIP` at `0x1800499a9`
- `WDSCORE!CurrentIP` at `0x180049a07`
- `WDSCORE!CurrentIP` at `0x180049adf`
- `WDSCORE!CurrentIP` at `0x180049c34`
- `WDSCORE!CurrentIP` at `0x180049d87`
- `WDSCORE!CurrentIP` at `0x180049dfe`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800493de`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004992c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004999b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800499f9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180049a66`
- `WDSCORE!WdsSetupLogMessageW` at `0x180049b33`
- `WDSCORE!WdsSetupLogMessageW` at `0x180049c92`
- `WDSCORE!WdsSetupLogMessageW` at `0x180049de5`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800493de`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004992c`
- `WDSCORE!WdsSetupLogMessageW` at `0x18004999b`
- `WDSCORE!WdsSetupLogMessageW` at `0x1800499f9`
- `WDSCORE!WdsSetupLogMessageW` at `0x180049a66`
- `WDSCORE!WdsSetupLogMessageW` at `0x180049b33`
- `WDSCORE!WdsSetupLogMessageW` at `0x180049c92`
- `WDSCORE!WdsSetupLogMessageW` at `0x180049de5`
- `FLTLIB!FilterConnectCommunicationPort` at `0x18004977f`
- `FLTLIB!FilterConnectCommunicationPort` at `0x18004977f`

## string_xrefs

- `0x18004948b`: `WsbkExecuteRevertJournal: Failed NtPathToDos for %s, hr = 0x%08x`
- `0x180049411`: `WsbkExecuteRevertJournal: Failed to copy target volume name %s; hr = 0x%08X`
- `0x1800495a7`: `WsbkExecuteRevertJournal: Failed to copy target volume name %s; hr = 0x%08X`
- `0x18004969e`: `WsbkExecuteRevertJournal: Driver is already loaded but not in restore mode; hr = 0x%x`
- `0x18004979f`: `WsbkExecuteRevertJournal: Failed FilterConnectCommunicationPort, hr = 0x%08X`
- `0x180049844`: `WsbkExecuteRevertJournal: Failed to create the progress thread. Error: 0x%08X`
- `0x180049c3e`: `WsbkExecuteRevertJournal: Failed CopyFileW [%s] -> [%s], hr = 0x%08x`
- `0x180049d91`: `WsbkExecuteRevertJournal: Failed BuildPathHr [%s] + [%s], hr = 0x%08X`
- `0x180049e08`: `WsbkExecuteRevertJournal: Failed BuildPathHr [%s] + [%s], hr = 0x%08X`

## pseudocode

```c
__int64 __fastcall WsbkExecuteRevertJournal(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        void (*a4)(unsigned int, unsigned int, void *),
        HANDLE hHandle)
{
  __int64 v7; // rax
  unsigned __int64 v8; // rdi
  SIZE_T v9; // rbx
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v11; // rax
  char *v12; // r13
  unsigned int v13; // esi
  DWORD v14; // edi
  __int64 v15; // rbx
  struct tagLOG_PARTIAL_MSG *v16; // rax
  DWORD v17; // edi
  __int64 v18; // rbx
  struct tagLOG_PARTIAL_MSG *v19; // rax
  unsigned __int16 *v20; // rcx
  DWORD v21; // edi
  __int64 v22; // rbx
  struct tagLOG_PARTIAL_MSG *v23; // rax
  __int64 v24; // rax
  unsigned __int64 v25; // rdi
  SIZE_T v26; // rbx
  HANDLE v27; // rax
  void *v28; // rax
  void *v29; // r12
  DWORD v30; // edi
  __int64 v31; // rbx
  struct tagLOG_PARTIAL_MSG *v32; // rax
  DWORD v33; // edi
  __int64 v34; // rbx
  struct tagLOG_PARTIAL_MSG *v35; // rax
  DWORD v36; // edi
  __int64 v37; // rbx
  struct tagLOG_PARTIAL_MSG *v38; // rax
  DWORD LastError; // edi
  __int64 v40; // rbx
  struct tagLOG_PARTIAL_MSG *v41; // rax
  DWORD v42; // edi
  __int64 v43; // rbx
  struct tagLOG_PARTIAL_MSG *v44; // rax
  DWORD v45; // edi
  __int64 v46; // rbx
  struct tagLOG_PARTIAL_MSG *v47; // rax
  int v48; // edx
  signed int v49; // eax
  DWORD v50; // edi
  __int64 v51; // rbx
  struct tagLOG_PARTIAL_MSG *v52; // rax
  DWORD v53; // edi
  __int64 v54; // rbx
  struct tagLOG_PARTIAL_MSG *v55; // rax
  NTSTATUS v56; // r12d
  DWORD v57; // edi
  __int64 v58; // rbx
  struct tagLOG_PARTIAL_MSG *v59; // rax
  DWORD v60; // edi
  __int64 v61; // rbx
  struct tagLOG_PARTIAL_MSG *v62; // rax
  DWORD v63; // edi
  __int64 v64; // rax
  const wchar_t *v65; // r8
  __int64 v66; // rbx
  struct tagLOG_PARTIAL_MSG *v67; // rax
  signed int v68; // eax
  int v69; // r12d
  DWORD v70; // edi
  __int64 v71; // rbx
  struct tagLOG_PARTIAL_MSG *v72; // rax
  const wchar_t *v73; // rsi
  STRSAFE_PCNZWCH *v74; // r13
  WCHAR *v75; // rdi
  signed int v76; // eax
  bool v77; // sf
  signed int v78; // eax
  signed int v79; // r12d
  WCHAR *v80; // rbx
  signed int v81; // eax
  bool v82; // sf
  signed int v83; // eax
  signed int v84; // r12d
  signed int v85; // eax
  unsigned int v86; // r12d
  DWORD v87; // edi
  __int64 v88; // rbx
  struct tagLOG_PARTIAL_MSG *v89; // rax
  HANDLE v90; // rax
  HANDLE v91; // rax
  void *v92; // rbx
  HANDLE v93; // rax
  HANDLE v94; // rax
  void *v95; // rbx
  HANDLE v96; // rax
  DWORD v98; // edi
  __int64 v99; // rbx
  struct tagLOG_PARTIAL_MSG *v100; // rax
  DWORD v101; // edi
  __int64 v102; // rbx
  struct tagLOG_PARTIAL_MSG *v103; // rax
  int v104; // [rsp+68h] [rbp-71h] BYREF
  int v105; // [rsp+6Ch] [rbp-6Dh] BYREF
  NTSTATUS Status; // [rsp+70h] [rbp-69h] BYREF
  HANDLE hObject; // [rsp+78h] [rbp-61h] BYREF
  STRSAFE_PCNZWCH pszSrc; // [rsp+80h] [rbp-59h]
  LPVOID lpMem; // [rsp+88h] [rbp-51h] BYREF
  HANDLE hEvent; // [rsp+90h] [rbp-49h] BYREF
  LPVOID v111; // [rsp+98h] [rbp-41h]
  unsigned __int16 *v112; // [rsp+A0h] [rbp-39h]
  _QWORD v113[4]; // [rsp+A8h] [rbp-31h] BYREF
  _QWORD Parameter[12]; // [rsp+C8h] [rbp-11h] BYREF
  const WCHAR *v116; // [rsp+148h] [rbp+6Fh]
  HRESULT IsLoaded; // [rsp+150h] [rbp+77h]
  HANDLE hHandlea; // [rsp+158h] [rbp+7Fh]
  const WCHAR *hHandleb; // [rsp+158h] [rbp+7Fh]

  v104 = 0;
  v105 = 0;
  pszSrc = 0;
  v111 = 0;
  lpMem = 0;
  hObject = (HANDLE)-1LL;
  Status = 0;
  hEvent = CreateEventW(0, 1, 0, 0);
  Parameter[0] = &hObject;
  Parameter[1] = &hEvent;
  Parameter[3] = ProgressCallback;
  Parameter[4] = hHandle;
  v113[0] = L"\\$Windows.~BK\\WinSetupBak.log";
  v113[1] = L"\\WinSetupBak.log";
  v113[2] = L"\\$Windows.~BK\\Operations.jrn";
  v113[3] = L"\\Operations.jrn";
  v7 = -1;
  Parameter[2] = 0;
  do
    ++v7;
  while ( a1[v7] );
  v8 = v7 + 1;
  v9 = 2 * (v7 + 1);
  ProcessHeap = GetProcessHeap();
  v11 = (unsigned __int16 *)HeapAlloc(ProcessHeap, 8u, v9);
  v112 = v11;
  v12 = (char *)v11;
  if ( v11 )
  {
    IsLoaded = StringCchCopyW(v11, v8, a1);
    v13 = IsLoaded;
    if ( IsLoaded >= 0 )
    {
      StrRTrm(v12);
      IsLoaded = NtPathToDos(v20);
      v13 = IsLoaded;
      if ( IsLoaded >= 0 )
      {
        v24 = -1;
        do
          ++v24;
        while ( a2[v24] );
        v25 = v24 + 1;
        v26 = 2 * (v24 + 1);
        v27 = GetProcessHeap();
        v28 = HeapAlloc(v27, 8u, v26);
        v111 = v28;
        v29 = v28;
        if ( v28 )
        {
          IsLoaded = StringCchCopyW((unsigned __int16 *)v28, v25, a2);
          v13 = IsLoaded;
          if ( IsLoaded >= 0 )
          {
            StrRTrm(v29);
            IsLoaded = WsbkIsLoaded(&v104, &v105);
            v13 = IsLoaded;
            if ( IsLoaded >= 0 )
            {
              if ( v104 )
              {
                if ( !v105 )
                {
                  v13 = -2147019873;
                  IsLoaded = -2147019873;
                  LastError = GetLastError();
                  v40 = CurrentIP();
                  v41 = ConstructPartialMsgW(
                          0x2000000,
                          "WsbkExecuteRevertJournal: Driver is already loaded but not in restore mode; hr = 0x%x",
                          -2147019873);
                  WdsSetupLogMessageW(
                    v41,
                    0,
                    L"D",
                    0,
                    4504,
                    L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
                    L"WsbkExecuteRevertJournal",
                    v40,
                    LastError,
                    0,
                    0);
                  goto LABEL_38;
                }
              }
              else
              {
                IsLoaded = WsbkLoad();
                v13 = IsLoaded;
                if ( IsLoaded < 0 )
                {
                  v42 = GetLastError();
                  v43 = CurrentIP();
                  v44 = ConstructPartialMsgW(
                          0x2000000,
                          "WsbkExecuteRevertJournal: Failed to load driver; hr = 0x%x",
                          IsLoaded);
                  WdsSetupLogMessageW(
                    v44,
                    0,
                    L"D",
                    0,
                    4513,
                    L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
                    L"WsbkExecuteRevertJournal",
                    v43,
                    v42,
                    0,
                    0);
                  goto LABEL_38;
                }
                v104 = 1;
              }
              IsLoaded = FilterConnectCommunicationPort(L"\\WinSetupBakPort", 0, 0, 0, 0, &hObject);
              v13 = IsLoaded;
              if ( IsLoaded >= 0 )
              {
                hHandlea = CreateThread(0, 0, WsbkGetMessageThread, Parameter, 0, 0);
                if ( hHandlea )
                {
                  IsLoaded = WsbkSendMessage(
                               (_DWORD)hObject,
                               v48,
                               (_DWORD)v12,
                               (_DWORD)v29,
                               1,
                               (__int64)&Status,
                               (__int64)&lpMem);
                  v13 = IsLoaded;
                  if ( IsLoaded >= 0 )
                  {
                    v56 = Status;
                    if ( Status < 0 )
                    {
                      v57 = GetLastError();
                      v58 = CurrentIP();
                      v59 = ConstructPartialMsgW(0x2000000, "WsbkExecuteRevertJournal: Failure in driver restore.");
                      WdsSetupLogMessageW(
                        v59,
                        0,
                        L"D",
                        0,
                        4559,
                        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
                        L"WsbkExecuteRevertJournal",
                        v58,
                        v57,
                        0,
                        0);
                      v60 = GetLastError();
                      v61 = CurrentIP();
                      v62 = ConstructPartialMsgW(0x2000000, "WsbkExecuteRevertJournal:   Result: 0x%08X", v56);
                      WdsSetupLogMessageW(
                        v62,
                        0,
                        L"D",
                        0,
                        4560,
                        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
                        L"WsbkExecuteRevertJournal",
                        v61,
                        v60,
                        0,
                        0);
                      v63 = GetLastError();
                      v64 = CurrentIP();
                      v65 = L"<NULL>";
                      v66 = v64;
                      if ( lpMem )
                        v65 = (const wchar_t *)lpMem;
                      v67 = ConstructPartialMsgW(0x2000000, "WsbkExecuteRevertJournal:   Message: %s", v65);
                      WdsSetupLogMessageW(
                        v67,
                        0,
                        L"D",
                        0,
                        4561,
                        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
                        L"WsbkExecuteRevertJournal",
                        v66,
                        v63,
                        0,
                        0);
                      v68 = RtlNtStatusToDosError(v56);
                      IsLoaded = v68;
                      v13 = v68;
                      if ( v68 > 0 )
                      {
                        v13 = (unsigned __int16)v68 | 0x80070000;
                        IsLoaded = v13;
                      }
                    }
                  }
                  else
                  {
                    v53 = GetLastError();
                    v54 = CurrentIP();
                    v55 = ConstructPartialMsgW(
                            0x2000000,
                            "WsbkExecuteRevertJournal: Failed WsbkSendMessage, hr = 0x%08X",
                            IsLoaded);
                    WdsSetupLogMessageW(
                      v55,
                      0,
                      L"D",
                      0,
                      4554,
                      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
                      L"WsbkExecuteRevertJournal",
                      v54,
                      v53,
                      0,
                      0);
                  }
                  SetEvent(hEvent);
                  WaitForSingleObject(hHandlea, 0xFFFFFFFF);
                  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_RevertDUTModeVssSnapshotIssue>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_RevertDUTModeVssSnapshotIssue>::GetImpl'::`2'::impl) )
                    CloseHandle(hHandlea);
                }
                else
                {
                  v49 = GetLastError();
                  IsLoaded = v49;
                  v13 = v49;
                  if ( v49 > 0 )
                  {
                    v13 = (unsigned __int16)v49 | 0x80070000;
                    IsLoaded = v13;
                  }
                  v50 = GetLastError();
                  v51 = CurrentIP();
                  v52 = ConstructPartialMsgW(
                          0x2000000,
                          "WsbkExecuteRevertJournal: Failed to create the progress thread. Error: 0x%08X",
                          v13);
                  WdsSetupLogMessageW(
                    v52,
                    0,
                    L"D",
                    0,
                    4539,
                    L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
                    L"WsbkExecuteRevertJournal",
                    v51,
                    v50,
                    0,
                    0);
                }
              }
              else
              {
                v45 = GetLastError();
                v46 = CurrentIP();
                v47 = ConstructPartialMsgW(
                        0x2000000,
                        "WsbkExecuteRevertJournal: Failed FilterConnectCommunicationPort, hr = 0x%08X",
                        IsLoaded);
                WdsSetupLogMessageW(
                  v47,
                  0,
                  L"D",
                  0,
                  4530,
                  L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
                  L"WsbkExecuteRevertJournal",
                  v46,
                  v45,
                  0,
                  0);
              }
            }
            else
            {
              v36 = GetLastError();
              v37 = CurrentIP();
              v38 = ConstructPartialMsgW(
                      0x2000000,
                      "WsbkExecuteRevertJournal: Failed to determine whether driver is loaded; hr = 0x%x",
                      IsLoaded);
              WdsSetupLogMessageW(
                v38,
                0,
                L"D",
                0,
                4495,
                L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
                L"WsbkExecuteRevertJournal",
                v37,
                v36,
                0,
                0);
            }
          }
          else
          {
            v33 = GetLastError();
            v34 = CurrentIP();
            v35 = ConstructPartialMsgW(
                    0x2000000,
                    "WsbkExecuteRevertJournal: Failed to copy target volume name %s; hr = 0x%08X",
                    (const char *)a2,
                    IsLoaded);
            WdsSetupLogMessageW(
              v35,
              0,
              L"D",
              0,
              4486,
              L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
              L"WsbkExecuteRevertJournal",
              v34,
              v33,
              0,
              0);
          }
        }
        else
        {
          v13 = -2147024882;
          IsLoaded = -2147024882;
          v30 = GetLastError();
          v31 = CurrentIP();
          v32 = ConstructPartialMsgW(
                  0x2000000,
                  "WsbkExecuteRevertJournal: Failed to allocate target volume buffer; hr = 0x%08x",
                  -2147024882);
          WdsSetupLogMessageW(
            v32,
            0,
            L"D",
            0,
            4480,
            L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
            L"WsbkExecuteRevertJournal",
            v31,
            v30,
            0,
            0);
        }
      }
      else
      {
        v21 = GetLastError();
        v22 = CurrentIP();
        v23 = ConstructPartialMsgW(
                0x2000000,
                "WsbkExecuteRevertJournal: Failed NtPathToDos for %s, hr = 0x%08x",
                v12,
                IsLoaded);
        WdsSetupLogMessageW(
          v23,
          0,
          L"D",
          0,
          4471,
          L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
          L"WsbkExecuteRevertJournal",
          v22,
          v21,
          0,
          0);
      }
    }
    else
    {
      v17 = GetLastError();
      v18 = CurrentIP();
      v19 = ConstructPartialMsgW(
              0x2000000,
              "WsbkExecuteRevertJournal: Failed to copy target volume name %s; hr = 0x%08X",
              (const char *)a1,
              IsLoaded);
      WdsSetupLogMessageW(
        v19,
        0,
        L"D",
        0,
        4464,
        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
        L"WsbkExecuteRevertJournal",
        v18,
        v17,
        0,
        0);
    }
  }
  else
  {
    v13 = -2147024882;
    IsLoaded = -2147024882;
    v14 = GetLastError();
    v15 = CurrentIP();
    v16 = ConstructPartialMsgW(
            0x2000000,
            "WsbkExecuteRevertJournal: Failed to allocate target volume buffer; hr = 0x%08x",
            -2147024882);
    WdsSetupLogMessageW(
      v16,
      0,
      L"D",
      0,
      4458,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkExecuteRevertJournal",
      v15,
      v14,
      0,
      0);
  }
LABEL_38:
  if ( v104 )
  {
    v69 = WsbkUnload();
    if ( v69 < 0 )
    {
      v70 = GetLastError();
      v71 = CurrentIP();
      v72 = ConstructPartialMsgW(
              0x2000000,
              "WsbkExecuteRevertJournal: Failed to unload driver after journal revert; hr = 0x%x",
              v69);
      WdsSetupLogMessageW(
        v72,
        0,
        L"D",
        0,
        4587,
        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
        L"WsbkExecuteRevertJournal",
        v71,
        v70,
        0,
        0);
    }
  }
  if ( a3 )
  {
    v73 = a3;
    v74 = (STRSAFE_PCNZWCH *)v113;
    while ( 1 )
    {
      hHandleb = (const WCHAR *)BuildPath(pszSrc, *v74);
      v75 = (WCHAR *)hHandleb;
      if ( hHandleb )
        break;
      v76 = GetLastError();
      v77 = v76 < 0;
      if ( v76 > 0 )
        v77 = 1;
      if ( v77 )
      {
        v78 = GetLastError();
        v79 = v78;
        if ( v78 > 0 )
          v79 = (unsigned __int16)v78 | 0x80070000;
        if ( v79 >= 0 )
          break;
      }
      else
      {
        v79 = -2147467259;
      }
      v98 = GetLastError();
      v99 = CurrentIP();
      v100 = ConstructPartialMsgW(
               0x2000000,
               "WsbkExecuteRevertJournal: Failed BuildPathHr [%s] + [%s], hr = 0x%08X",
               (const char *)pszSrc,
               (const char *)*v74,
               v79);
      WdsSetupLogMessageW(
        v100,
        0,
        L"D",
        0,
        4605,
        L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
        L"WsbkExecuteRevertJournal",
        v99,
        v98,
        0,
        0);
LABEL_66:
      v74 += 2;
      if ( v74 == Parameter )
      {
        v13 = IsLoaded;
        v12 = (char *)v112;
        goto LABEL_68;
      }
    }
    v116 = (const WCHAR *)BuildPath(v73, v74[1]);
    v80 = (WCHAR *)v116;
    if ( v116 )
      goto LABEL_57;
    v81 = GetLastError();
    v82 = v81 < 0;
    if ( v81 > 0 )
      v82 = 1;
    if ( v82 )
    {
      v83 = GetLastError();
      v84 = v83;
      if ( v83 > 0 )
        v84 = (unsigned __int16)v83 | 0x80070000;
      if ( v84 >= 0 )
      {
LABEL_57:
        if ( CopyFileW(hHandleb, v116, 0) )
        {
LABEL_62:
          if ( v75 )
          {
            v90 = GetProcessHeap();
            HeapFree(v90, 0, v75);
          }
          if ( v80 )
          {
            v91 = GetProcessHeap();
            HeapFree(v91, 0, v80);
          }
          goto LABEL_66;
        }
        v85 = GetLastError();
        v86 = v85;
        if ( v85 > 0 )
          v86 = (unsigned __int16)v85 | 0x80070000;
        v87 = GetLastError();
        v88 = CurrentIP();
        v89 = ConstructPartialMsgW(
                0x2000000,
                "WsbkExecuteRevertJournal: Failed CopyFileW [%s] -> [%s], hr = 0x%08x",
                (const char *)hHandleb,
                (const char *)v116,
                v86);
        WdsSetupLogMessageW(
          v89,
          0,
          L"D",
          0,
          4619,
          L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
          L"WsbkExecuteRevertJournal",
          v88,
          v87,
          0,
          0);
LABEL_61:
        v75 = (WCHAR *)hHandleb;
        v80 = (WCHAR *)v116;
        goto LABEL_62;
      }
    }
    else
    {
      v84 = -2147467259;
    }
    v101 = GetLastError();
    v102 = CurrentIP();
    v103 = ConstructPartialMsgW(
             0x2000000,
             "WsbkExecuteRevertJournal: Failed BuildPathHr [%s] + [%s], hr = 0x%08X",
             (const char *)v73,
             (const char *)v74[1],
             v84);
    WdsSetupLogMessageW(
      v103,
      0,
      L"D",
      0,
      4612,
      L"base\\ntsetup\\setupplatform\\deployment\\backup\\api\\winsetupbakapi.cpp",
      L"WsbkExecuteRevertJournal",
      v102,
      v101,
      0,
      0);
    goto LABEL_61;
  }
LABEL_68:
  v92 = lpMem;
  if ( lpMem )
  {
    v93 = GetProcessHeap();
    HeapFree(v93, 0, v92);
  }
  if ( v12 )
  {
    v94 = GetProcessHeap();
    HeapFree(v94, 0, v12);
  }
  v95 = v111;
  if ( v111 )
  {
    v96 = GetProcessHeap();
    HeapFree(v96, 0, v95);
  }
  if ( hEvent )
    CloseHandle(hEvent);
  if ( hObject != (HANDLE)-1LL )
    CloseHandle(hObject);
  return v13;
}

```

## disassembly

```asm
0x18004927c  mov     rax, rsp
0x18004927f  mov     [rax+8], rbx
0x180049283  mov     [rax+20h], r9
0x180049287  mov     [rax+18h], r8
0x18004928b  push    rbp
0x18004928c  push    rsi
0x18004928d  push    rdi
0x18004928e  push    r12
0x180049290  push    r13
0x180049292  push    r14
0x180049294  push    r15
0x180049296  lea     rbp, [rax-57h]
0x18004929a  sub     rsp, 0F0h
0x1800492a1  xor     r12d, r12d
0x1800492a4  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800492a8  mov     r15, rdx
0x1800492ab  mov     [rbp+4Fh+var_C0], r12d
0x1800492af  mov     r14, rcx
0x1800492b2  mov     [rbp+4Fh+var_BC], r12d
0x1800492b6  xor     r9d, r9d; lpName
0x1800492b9  mov     [rbp+4Fh+pszSrc], r12
0x1800492bd  lea     edx, [rbx+2]; bManualReset
0x1800492c0  mov     [rbp+4Fh+var_90], r12
0x1800492c4  xor     r8d, r8d; bInitialState
0x1800492c7  mov     [rbp+4Fh+lpMem], r12
0x1800492cb  xor     ecx, ecx; lpEventAttributes
0x1800492cd  mov     [rbp+4Fh+hObject], rbx
0x1800492d1  mov     [rbp+4Fh+Status], r12d
0x1800492d5  call    cs:__imp_CreateEventW
0x1800492db  mov     [rbp+4Fh+hEvent], rax
0x1800492df  lea     rax, [rbp+4Fh+hObject]
0x1800492e3  mov     [rbp+4Fh+Parameter], rax
0x1800492e7  lea     rax, [rbp+4Fh+hEvent]
0x1800492eb  mov     [rbp+4Fh+var_58], rax
0x1800492ef  lea     rax, ProgressCallback
0x1800492f6  mov     [rbp+4Fh+var_48], rax
0x1800492fa  mov     rax, [rbp+4Fh+hHandle]
0x1800492fe  mov     [rbp+4Fh+var_40], rax
0x180049302  lea     rax, aWindowsBkWinse; "\\$Windows.~BK\\WinSetupBak.log"
0x180049309  mov     [rbp+4Fh+var_80], rax
0x18004930d  lea     rax, aWinsetupbakLog; "\\WinSetupBak.log"
0x180049314  mov     [rbp+4Fh+var_78], rax
0x180049318  lea     rax, aWindowsBkOpera; "\\$Windows.~BK\\Operations.jrn"
0x18004931f  mov     [rbp+4Fh+var_70], rax
0x180049323  lea     rax, aOperationsJrn_0; "\\Operations.jrn"
0x18004932a  mov     [rbp+4Fh+var_68], rax
0x18004932e  mov     rax, rbx
0x180049331  mov     [rbp+4Fh+var_50], r12
0x180049335  inc     rax
0x180049338  cmp     [r14+rax*2], r12w
0x18004933d  jnz     short loc_180049335
0x18004933f  lea     rdi, [rax+1]
0x180049343  lea     rbx, [rdi+rdi]
0x180049347  call    cs:__imp_GetProcessHeap
0x18004934d  mov     r8, rbx; dwBytes
0x180049350  mov     edx, 8; dwFlags
0x180049355  mov     rcx, rax; hHeap
0x180049358  call    cs:__imp_HeapAlloc
0x18004935e  mov     [rbp+4Fh+var_88], rax
0x180049362  mov     r13, rax
0x180049365  test    rax, rax
0x180049368  jnz     short loc_1800493E9
0x18004936a  mov     r14d, 8007000Eh
0x180049370  mov     esi, r14d
0x180049373  mov     [rbp+4Fh+arg_18], r14d
0x180049377  call    cs:__imp_GetLastError
0x18004937d  mov     edi, eax
0x18004937f  call    cs:__imp_CurrentIP
0x180049385  mov     r8d, r14d
0x180049388  lea     rdx, aWsbkexecuterev_2; "WsbkExecuteRevertJournal: Failed to all"...
0x18004938f  mov     ecx, 2000000h; unsigned int
0x180049394  mov     rbx, rax
0x180049397  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004939c  mov     [rsp+50h], r12d
0x1800493a1  lea     r14, aWsbkexecuterev_11; "WsbkExecuteRevertJournal"
0x1800493a8  mov     qword ptr [rsp+120h+var_D8], r12
0x1800493ad  lea     r15, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x1800493b4  mov     dword ptr [rsp+120h+var_E0], edi
0x1800493b8  mov     qword ptr [rsp+120h+var_E8], rbx
0x1800493bd  mov     [rsp+120h+var_F0], r14
0x1800493c2  mov     [rsp+120h+hPort], r15
0x1800493c7  mov     dword ptr [rsp+120h+lpSecurityAttributes], 116Ah
0x1800493cf  xor     r9d, r9d
0x1800493d2  lea     r8, aD; "D"
0x1800493d9  xor     edx, edx
0x1800493db  mov     rcx, rax
0x1800493de  call    cs:__imp_WdsSetupLogMessageW
0x1800493e4  jmp     loc_180049AC5
0x1800493e9  mov     r8, r14; unsigned __int16 *
0x1800493ec  mov     rdx, rdi; unsigned __int64
0x1800493ef  mov     rcx, r13; unsigned __int16 *
0x1800493f2  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800493f7  mov     [rbp+4Fh+arg_18], eax
0x1800493fa  mov     esi, eax
0x1800493fc  test    eax, eax
0x1800493fe  jns     short loc_180049460
0x180049400  call    cs:__imp_GetLastError
0x180049406  mov     edi, eax
0x180049408  call    cs:__imp_CurrentIP
0x18004940e  mov     r9d, esi
0x180049411  lea     rdx, aWsbkexecuterev_12; "WsbkExecuteRevertJournal: Failed to cop"...
0x180049418  mov     r8, r14
0x18004941b  mov     ecx, 2000000h; unsigned int
0x180049420  mov     rbx, rax
0x180049423  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180049428  mov     [rsp+50h], r12d
0x18004942d  lea     r14, aWsbkexecuterev_11; "WsbkExecuteRevertJournal"
0x180049434  mov     qword ptr [rsp+120h+var_D8], r12
0x180049439  lea     r15, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x180049440  mov     dword ptr [rsp+120h+var_E0], edi
0x180049444  mov     qword ptr [rsp+120h+var_E8], rbx
0x180049449  mov     [rsp+120h+var_F0], r14
0x18004944e  mov     [rsp+120h+hPort], r15
0x180049453  mov     dword ptr [rsp+120h+lpSecurityAttributes], 1170h
0x18004945b  jmp     loc_1800493CF
0x180049460  mov     rcx, r13
0x180049463  call    StrRTrm
0x180049468  lea     rdx, [rbp+4Fh+pszSrc]
0x18004946c  call    NtPathToDos
0x180049471  mov     [rbp+4Fh+arg_18], eax
0x180049474  mov     esi, eax
0x180049476  test    eax, eax
0x180049478  jns     short loc_1800494DA
0x18004947a  call    cs:__imp_GetLastError
0x180049480  mov     edi, eax
0x180049482  call    cs:__imp_CurrentIP
0x180049488  mov     r9d, esi
0x18004948b  lea     rdx, aWsbkexecuterev_6; "WsbkExecuteRevertJournal: Failed NtPath"...
0x180049492  mov     r8, r13
0x180049495  mov     ecx, 2000000h; unsigned int
0x18004949a  mov     rbx, rax
0x18004949d  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800494a2  mov     [rsp+50h], r12d
0x1800494a7  lea     r14, aWsbkexecuterev_11; "WsbkExecuteRevertJournal"
0x1800494ae  mov     qword ptr [rsp+120h+var_D8], r12
0x1800494b3  lea     r15, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x1800494ba  mov     dword ptr [rsp+120h+var_E0], edi
0x1800494be  mov     qword ptr [rsp+120h+var_E8], rbx
0x1800494c3  mov     [rsp+120h+var_F0], r14
0x1800494c8  mov     [rsp+120h+hPort], r15
0x1800494cd  mov     dword ptr [rsp+120h+lpSecurityAttributes], 1177h
0x1800494d5  jmp     loc_1800493CF
0x1800494da  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800494de  inc     rax
0x1800494e1  cmp     [r15+rax*2], r12w
0x1800494e6  jnz     short loc_1800494DE
0x1800494e8  lea     rdi, [rax+1]
0x1800494ec  lea     rbx, [rdi+rdi]
0x1800494f0  call    cs:__imp_GetProcessHeap
0x1800494f6  mov     r8, rbx; dwBytes
0x1800494f9  mov     edx, 8; dwFlags
0x1800494fe  mov     rcx, rax; hHeap
0x180049501  call    cs:__imp_HeapAlloc
0x180049507  xor     ebx, ebx
0x180049509  mov     [rbp+4Fh+var_90], rax
0x18004950d  mov     r12, rax
0x180049510  test    rax, rax
0x180049513  jnz     short loc_18004957F
0x180049515  mov     r14d, 8007000Eh
0x18004951b  mov     esi, r14d
0x18004951e  mov     [rbp+4Fh+arg_18], r14d
0x180049522  call    cs:__imp_GetLastError
0x180049528  mov     edi, eax
0x18004952a  call    cs:__imp_CurrentIP
0x180049530  mov     r8d, r14d
0x180049533  lea     rdx, aWsbkexecuterev_2; "WsbkExecuteRevertJournal: Failed to all"...
0x18004953a  mov     ecx, 2000000h; unsigned int
0x18004953f  mov     rbx, rax
0x180049542  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180049547  mov     [rsp+50h], r12d
0x18004954c  lea     r14, aWsbkexecuterev_11; "WsbkExecuteRevertJournal"
0x180049553  mov     qword ptr [rsp+120h+var_D8], r12
0x180049558  lea     r15, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x18004955f  mov     dword ptr [rsp+120h+var_E0], edi
0x180049563  mov     qword ptr [rsp+120h+var_E8], rbx
0x180049568  mov     [rsp+120h+var_F0], r14
0x18004956d  mov     [rsp+120h+hPort], r15
0x180049572  mov     dword ptr [rsp+120h+lpSecurityAttributes], 1180h
0x18004957a  jmp     loc_1800493CF
0x18004957f  mov     r8, r15; unsigned __int16 *
0x180049582  mov     rdx, rdi; unsigned __int64
0x180049585  mov     rcx, r12; unsigned __int16 *
0x180049588  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004958d  mov     [rbp+4Fh+arg_18], eax
0x180049590  mov     esi, eax
0x180049592  test    eax, eax
0x180049594  jns     short loc_1800495F9
0x180049596  call    cs:__imp_GetLastError
0x18004959c  mov     edi, eax
0x18004959e  call    cs:__imp_CurrentIP
0x1800495a4  mov     r9d, esi
0x1800495a7  lea     rdx, aWsbkexecuterev_12; "WsbkExecuteRevertJournal: Failed to cop"...
0x1800495ae  mov     r8, r15
0x1800495b1  mov     ecx, 2000000h; unsigned int
0x1800495b6  mov     rbx, rax
0x1800495b9  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800495be  xor     r12d, r12d
0x1800495c1  lea     r14, aWsbkexecuterev_11; "WsbkExecuteRevertJournal"
0x1800495c8  mov     [rsp+50h], r12d
0x1800495cd  lea     r15, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x1800495d4  mov     qword ptr [rsp+120h+var_D8], r12
0x1800495d9  mov     dword ptr [rsp+120h+var_E0], edi
0x1800495dd  mov     qword ptr [rsp+120h+var_E8], rbx
0x1800495e2  mov     [rsp+120h+var_F0], r14
0x1800495e7  mov     [rsp+120h+hPort], r15
0x1800495ec  mov     dword ptr [rsp+120h+lpSecurityAttributes], 1186h
0x1800495f4  jmp     loc_1800493CF
0x1800495f9  mov     rcx, r12
0x1800495fc  call    StrRTrm
0x180049601  lea     rdx, [rbp+4Fh+var_BC]
0x180049605  lea     rcx, [rbp+4Fh+var_C0]
0x180049609  call    WsbkIsLoaded
0x18004960e  mov     [rbp+4Fh+arg_18], eax
0x180049611  mov     esi, eax
0x180049613  test    eax, eax
0x180049615  jns     short loc_180049677
0x180049617  call    cs:__imp_GetLastError
0x18004961d  mov     edi, eax
0x18004961f  call    cs:__imp_CurrentIP
0x180049625  mov     r8d, esi
0x180049628  lea     rdx, aWsbkexecuterev_13; "WsbkExecuteRevertJournal: Failed to det"...
0x18004962f  mov     ecx, 2000000h; unsigned int
0x180049634  mov     rbx, rax
0x180049637  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x18004963c  xor     r12d, r12d
0x18004963f  lea     r14, aWsbkexecuterev_11; "WsbkExecuteRevertJournal"
0x180049646  mov     [rsp+50h], r12d
0x18004964b  lea     r15, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x180049652  mov     qword ptr [rsp+120h+var_D8], r12
0x180049657  mov     dword ptr [rsp+120h+var_E0], edi
0x18004965b  mov     qword ptr [rsp+120h+var_E8], rbx
0x180049660  mov     [rsp+120h+var_F0], r14
0x180049665  mov     [rsp+120h+hPort], r15
0x18004966a  mov     dword ptr [rsp+120h+lpSecurityAttributes], 118Fh
0x180049672  jmp     loc_1800493CF
0x180049677  cmp     [rbp+4Fh+var_C0], ebx
0x18004967a  jz      short loc_1800496ED
0x18004967c  cmp     [rbp+4Fh+var_BC], ebx
0x18004967f  jnz     loc_180049762
0x180049685  mov     esi, 8007139Fh
0x18004968a  mov     [rbp+4Fh+arg_18], esi
0x18004968d  call    cs:__imp_GetLastError
0x180049693  mov     edi, eax
0x180049695  call    cs:__imp_CurrentIP
0x18004969b  mov     r8d, esi
0x18004969e  lea     rdx, aWsbkexecuterev; "WsbkExecuteRevertJournal: Driver is alr"...
0x1800496a5  mov     ecx, 2000000h; unsigned int
0x1800496aa  mov     rbx, rax
0x1800496ad  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x1800496b2  xor     r12d, r12d
0x1800496b5  lea     r14, aWsbkexecuterev_11; "WsbkExecuteRevertJournal"
0x1800496bc  mov     [rsp+50h], r12d
0x1800496c1  lea     r15, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x1800496c8  mov     qword ptr [rsp+120h+var_D8], r12
0x1800496cd  mov     dword ptr [rsp+120h+var_E0], edi
0x1800496d1  mov     qword ptr [rsp+120h+var_E8], rbx
0x1800496d6  mov     [rsp+120h+var_F0], r14
0x1800496db  mov     [rsp+120h+hPort], r15
0x1800496e0  mov     dword ptr [rsp+120h+lpSecurityAttributes], 1198h
0x1800496e8  jmp     loc_1800493CF
0x1800496ed  call    WsbkLoad
0x1800496f2  mov     [rbp+4Fh+arg_18], eax
0x1800496f5  mov     esi, eax
0x1800496f7  test    eax, eax
0x1800496f9  jns     short loc_18004975B
0x1800496fb  call    cs:__imp_GetLastError
0x180049701  mov     edi, eax
0x180049703  call    cs:__imp_CurrentIP
0x180049709  mov     r8d, esi
0x18004970c  lea     rdx, aWsbkexecuterev_7; "WsbkExecuteRevertJournal: Failed to loa"...
0x180049713  mov     ecx, 2000000h; unsigned int
0x180049718  mov     rbx, rax
0x18004971b  call    ?ConstructPartialMsgW@@YAPEAUtagLOG_PARTIAL_MSG@@KPEBDZZ; ConstructPartialMsgW(ulong,char const *,...)
0x180049720  xor     r12d, r12d
0x180049723  lea     r14, aWsbkexecuterev_11; "WsbkExecuteRevertJournal"
0x18004972a  mov     [rsp+50h], r12d
0x18004972f  lea     r15, aBaseNtsetupSet_0; "base\\ntsetup\\setupplatform\\deploymen"...
0x180049736  mov     qword ptr [rsp+120h+var_D8], r12
0x18004973b  mov     dword ptr [rsp+120h+var_E0], edi
0x18004973f  mov     qword ptr [rsp+120h+var_E8], rbx
0x180049744  mov     [rsp+120h+var_F0], r14
0x180049749  mov     [rsp+120h+hPort], r15
0x18004974e  mov     dword ptr [rsp+120h+lpSecurityAttributes], 11A1h
0x180049756  jmp     loc_1800493CF
0x18004975b  mov     [rbp+4Fh+var_C0], 1
0x180049762  lea     rax, [rbp+4Fh+hObject]
0x180049766  xor     r9d, r9d; wSizeOfContext
0x180049769  mov     [rsp+120h+hPort], rax; hPort
0x18004976e  lea     rcx, PortName; "\\WinSetupBakPort"
0x180049775  xor     r8d, r8d; lpContext
0x180049778  mov     [rsp+120h+lpSecurityAttributes], rbx; lpSecurityAttributes
0x18004977d  xor     edx, edx; dwOptions
0x18004977f  call    cs:__imp_FilterConnectCommunicationPort
0x180049785  mov     [rbp+4Fh+arg_18], eax
0x180049788  mov     esi, eax
0x18004978a  test    eax, eax
0x18004978c  jns     short loc_1800497EE
0x18004978e  call    cs:__imp_GetLastError
0x180049794  mov     edi, eax
0x180049796  call    cs:__imp_CurrentIP
  ... truncated ...
```
