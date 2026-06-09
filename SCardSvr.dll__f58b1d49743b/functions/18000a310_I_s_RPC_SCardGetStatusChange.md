# I_s_RPC_SCardGetStatusChange

- ea: `0x18000a310`
- end: `0x18000c23c`
- name: `I_s_RPC_SCardGetStatusChange`
- size: `7980`
- prototype: `__int64 __usercall@<rax>(PVOID Context@<rcx>, __int64, int, __int64, __int64)`
- caller_count: `1`
- callee_count: `27`
- tags: `file_ops, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x180009420`

## callees

- `0x180003860`
- `0x1800075d0`
- `0x180009150`
- `0x180009190`
- `0x1800098b0`
- `0x180009b30`
- `0x180009d80`
- `0x18000a2c0`
- `0x18000a310`
- `0x18000c250`
- `0x18000c870`
- `0x18000cd80`
- `0x18000cf60`
- `0x18000fb50`
- `0x1800125e0`
- `0x180014180`
- `0x180019bc4`
- `0x18001c330`
- `0x18001c370`
- `0x180023168`
- `0x180023174`
- `0x180023276`
- `0x180023282`
- `0x180028b78`
- `0x18002ab90`
- `0x18003261b`
- `0x180037010`

## import_xrefs

- `msvcrt!_wcsnicmp` at `0x18000a7fc`
- `msvcrt!_wcsnicmp` at `0x18000a7fc`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000abc9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000aca6`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000abc9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000aca6`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a967`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ad79`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000adc7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c093`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000a967`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000ad79`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000adc7`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18000c093`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a8dc`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x18000a8dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8cb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a8cb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b5f0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b988`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000b9cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bc5f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bca1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bcc3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf09`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bf52`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c09d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000c1b4`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000af0e`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18000af0e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a51f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a554`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a5a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a946`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ab4d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ab77`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ac2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ac54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b853`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b87e`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a51f`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a554`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a5a9`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000a946`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ab4d`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ab77`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ac2a`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000ac54`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b853`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x18000b87e`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a412`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a429`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a412`
- `api-ms-win-core-processthreads-l1-1-0!TlsSetValue` at `0x18000a429`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000b0fe`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18000b0fe`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18000a9cb`
- `RPCRT4!RpcServerUnsubscribeForNotification` at `0x18000a9cb`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18000a4ea`
- `RPCRT4!RpcServerSubscribeForNotification` at `0x18000a4ea`
- `KERNEL32!UnregisterWaitEx` at `0x18000a9ef`
- `KERNEL32!UnregisterWaitEx` at `0x18000a9ef`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18000a48d`
- `KERNEL32!RegisterWaitForSingleObject` at `0x18000a48d`
- `KERNEL32!lstrcmpiW` at `0x18000a729`
- `KERNEL32!lstrcmpiW` at `0x18000b171`
- `KERNEL32!lstrcmpiW` at `0x18000a729`
- `KERNEL32!lstrcmpiW` at `0x18000b171`

## pseudocode

```c
// Hidden C++ exception states: #wind=22
__int64 __fastcall I_s_RPC_SCardGetStatusChange(
        char *Context,
        DWORD a2,
        const unsigned __int16 *a3,
        __int64 a4,
        __int64 a5,
        unsigned int a6,
        _QWORD *a7,
        unsigned int *a8)
{
  void *v9; // rsi
  DWORD LastError; // eax
  RPC_STATUS v11; // eax
  __int64 v12; // rcx
  char v13; // di
  char *v14; // r14
  LPVOID Value; // rax
  int v16; // esi
  LPVOID v17; // rbx
  __int64 v18; // rdi
  unsigned int v19; // eax
  unsigned int v20; // r15d
  unsigned int v21; // r14d
  unsigned __int16 *i; // rax
  const unsigned __int16 *v23; // r12
  __int64 v24; // r15
  __int64 **v25; // rcx
  void *v26; // r14
  struct CCriticalSectionObject *v27; // rbx
  unsigned int v28; // eax
  unsigned int v29; // edi
  CReader *v30; // rsi
  const WCHAR *v31; // rdx
  char *v32; // rax
  const unsigned __int8 *v33; // rcx
  const unsigned __int16 *v34; // r9
  __int64 **v35; // rdi
  __int64 *v36; // r13
  _QWORD *v37; // rdi
  unsigned int v38; // r15d
  unsigned int v39; // ebx
  char *v40; // rax
  char *v41; // rdi
  void *v42; // rbx
  unsigned int v43; // eax
  signed int v44; // ebx
  unsigned int *v45; // rdi
  HANDLE ProcessHeap; // rax
  void *v47; // rax
  char *v48; // rbx
  const WCHAR *v49; // rdx
  __int64 v50; // rcx
  char *v51; // r14
  LPVOID v52; // rax
  LPVOID *v53; // rcx
  bool v54; // zf
  HANDLE *v55; // rdi
  void *v56; // rsi
  void *v57; // r14
  RPC_STATUS v58; // eax
  __int64 v59; // rcx
  char v60; // bl
  void **v61; // rbx
  void *v62; // rcx
  unsigned int v64; // r14d
  int v65; // r12d
  _QWORD *v66; // rbx
  __int64 k; // r8
  void *v68; // rbx
  __int64 v69; // rdi
  __int64 v70; // rbx
  LPVOID v71; // rsi
  unsigned int v72; // eax
  __int64 v73; // r15
  __int64 v74; // rbx
  __int64 v75; // rsi
  LPVOID v76; // r14
  unsigned int v77; // eax
  size_t v78; // r12
  const WCHAR *v79; // r14
  void *v80; // rsi
  int v81; // ebx
  __int64 v82; // rdi
  unsigned __int16 v83; // dx
  const unsigned __int8 *v84; // rcx
  const unsigned __int16 *v85; // r9
  int v86; // r14d
  HANDLE *v87; // r15
  int v88; // r8d
  int v89; // r14d
  int *v90; // rax
  int v91; // ecx
  unsigned int v92; // ecx
  __int64 v93; // rbx
  HANDLE v94; // r14
  int v95; // r12d
  HANDLE *v96; // r15
  __int64 v97; // rbx
  HANDLE v98; // rsi
  unsigned int v99; // edi
  DWORD v100; // eax
  PVOID v101; // rcx
  DWORD v102; // ebx
  const WCHAR *v103; // rsi
  unsigned int v104; // ebx
  char *v105; // rax
  int *v106; // rax
  void *v107; // rax
  unsigned int v108; // ecx
  __int64 v109; // rcx
  int v110; // r14d
  int v111; // eax
  _QWORD *v112; // rsi
  CReaderProxy **v113; // rdi
  HANDLE *v114; // rbx
  unsigned int ii; // edx
  HANDLE *v116; // rdi
  unsigned int v117; // edx
  HANDLE *v118; // rsi
  unsigned int n; // edx
  HANDLE v120; // rcx
  void *v121; // rax
  __int64 v122; // rcx
  _QWORD *v123; // rcx
  int v124; // edx
  DWORD v125; // ebx
  __int64 v126; // rcx
  char v127; // di
  __int64 v128; // rcx
  HANDLE *lpHandles; // [rsp+30h] [rbp-208h]
  unsigned int v130; // [rsp+38h] [rbp-200h]
  char *Src; // [rsp+40h] [rbp-1F8h]
  unsigned int v132; // [rsp+48h] [rbp-1F0h]
  void *Block; // [rsp+50h] [rbp-1E8h] BYREF
  unsigned int j; // [rsp+58h] [rbp-1E0h]
  int Size; // [rsp+5Ch] [rbp-1DCh]
  unsigned int Size_4; // [rsp+60h] [rbp-1D8h]
  int v137; // [rsp+64h] [rbp-1D4h]
  signed int v138; // [rsp+68h] [rbp-1D0h]
  void *v139; // [rsp+70h] [rbp-1C8h]
  void **v140; // [rsp+78h] [rbp-1C0h] BYREF
  char *v141; // [rsp+80h] [rbp-1B8h]
  int v142; // [rsp+88h] [rbp-1B0h]
  unsigned int v143; // [rsp+8Ch] [rbp-1ACh]
  void **v144; // [rsp+90h] [rbp-1A8h]
  int v145; // [rsp+98h] [rbp-1A0h]
  unsigned int v146; // [rsp+9Ch] [rbp-19Ch]
  HANDLE *v147; // [rsp+A0h] [rbp-198h]
  unsigned int v148; // [rsp+A8h] [rbp-190h]
  void *v149; // [rsp+B0h] [rbp-188h]
  void *phNewWaitObject; // [rsp+B8h] [rbp-180h] BYREF
  void **v151; // [rsp+C0h] [rbp-178h] BYREF
  int v152; // [rsp+C8h] [rbp-170h]
  unsigned int v153; // [rsp+CCh] [rbp-16Ch]
  void *v154; // [rsp+D0h] [rbp-168h]
  int v155; // [rsp+D8h] [rbp-160h]
  int v156; // [rsp+DCh] [rbp-15Ch]
  __int64 v157; // [rsp+E0h] [rbp-158h]
  void **v158; // [rsp+E8h] [rbp-150h]
  void **v159; // [rsp+F0h] [rbp-148h]
  void *v160; // [rsp+F8h] [rbp-140h]
  int v161; // [rsp+100h] [rbp-138h]
  int v162; // [rsp+104h] [rbp-134h]
  __int64 *v163; // [rsp+108h] [rbp-130h]
  int *v164; // [rsp+110h] [rbp-128h]
  ulong v165; // [rsp+118h] [rbp-120h] BYREF
  ulong v166; // [rsp+11Ch] [rbp-11Ch] BYREF
  ulong v167; // [rsp+120h] [rbp-118h] BYREF
  ulong v168; // [rsp+124h] [rbp-114h] BYREF
  ulong v169; // [rsp+128h] [rbp-110h] BYREF
  ulong v170; // [rsp+12Ch] [rbp-10Ch] BYREF
  ulong v171; // [rsp+130h] [rbp-108h] BYREF
  ulong v172; // [rsp+134h] [rbp-104h] BYREF
  ulong v173; // [rsp+138h] [rbp-100h] BYREF
  ulong v174; // [rsp+13Ch] [rbp-FCh] BYREF
  ulong v175; // [rsp+140h] [rbp-F8h] BYREF
  ulong v176; // [rsp+144h] [rbp-F4h] BYREF
  ulong v177; // [rsp+148h] [rbp-F0h] BYREF
  ulong v178; // [rsp+14Ch] [rbp-ECh] BYREF
  ulong pExceptionObject; // [rsp+150h] [rbp-E8h] BYREF
  ulong v180; // [rsp+154h] [rbp-E4h] BYREF
  ulong v181; // [rsp+158h] [rbp-E0h] BYREF
  ulong v182; // [rsp+15Ch] [rbp-DCh] BYREF
  ulong v183; // [rsp+168h] [rbp-D0h] BYREF
  ulong v184; // [rsp+16Ch] [rbp-CCh] BYREF
  ulong v185; // [rsp+170h] [rbp-C8h] BYREF
  ulong v186; // [rsp+174h] [rbp-C4h] BYREF
  ulong v187; // [rsp+178h] [rbp-C0h] BYREF
  ulong v188; // [rsp+17Ch] [rbp-BCh] BYREF
  ulong v189; // [rsp+180h] [rbp-B8h] BYREF
  ulong v190; // [rsp+184h] [rbp-B4h] BYREF
  ulong v191; // [rsp+18Ch] [rbp-ACh] BYREF
  ulong v192; // [rsp+190h] [rbp-A8h] BYREF
  ulong v193; // [rsp+194h] [rbp-A4h] BYREF
  struct CCriticalSectionObject *v194; // [rsp+198h] [rbp-A0h]
  ulong v195; // [rsp+1A0h] [rbp-98h] BYREF
  ulong v196; // [rsp+1A4h] [rbp-94h] BYREF
  ulong v197; // [rsp+1A8h] [rbp-90h] BYREF
  ulong v198; // [rsp+1ACh] [rbp-8Ch] BYREF
  char *v199; // [rsp+1B0h] [rbp-88h]
  LPVOID *v200; // [rsp+1B8h] [rbp-80h]
  void **v201; // [rsp+1C0h] [rbp-78h]
  char *v202; // [rsp+1C8h] [rbp-70h]
  RPC_ASYNC_NOTIFICATION_INFO NotificationInfo; // [rsp+1D8h] [rbp-60h] BYREF
  unsigned int m; // [rsp+240h] [rbp+8h]
  unsigned int NotificationsQueued; // [rsp+258h] [rbp+20h] BYREF

  v140 = &CBuffer::`vftable';
  Src = 0;
  v141 = 0;
  v142 = 0;
  NotificationsQueued = 0;
  v143 = 0;
  v159 = &CBuffer::`vftable';
  v149 = 0;
  v160 = 0;
  v161 = 0;
  Size_4 = 0;
  v162 = 0;
  Block = 0;
  v151 = &CDynamicArray<CServiceThread>::`vftable';
  v130 = 0;
  v153 = 0;
  j = 0;
  v152 = 0;
  v139 = 0;
  v154 = 0;
  v144 = &CDynamicArray<CServiceThread>::`vftable';
  v146 = 0;
  m = 0;
  v145 = 0;
  lpHandles = 0;
  v147 = 0;
  v158 = (void **)Context;
  v148 = 0;
  if ( !TlsSetValue(dwTlsIndex, *((LPVOID *)Context + 9)) || !TlsSetValue(dword_18004B240, *(LPVOID *)Context) )
    GetLastError();
  _InterlockedExchange(&g_fExtendShutdownTimer, 1);
  memset(&NotificationInfo, 0, sizeof(NotificationInfo));
  phNewWaitObject = 0;
  if ( RegisterWaitForSingleObject(
         &phNewWaitObject,
         *((HANDLE *)Context + 2),
         CalRpcClientDisconnected,
         Context,
         0xFFFFFFFF,
         8u) )
  {
    v9 = phNewWaitObject;
    if ( (char *)phNewWaitObject - 1 > (char *)0xFFFFFFFFFFFFFFFDLL )
      LastError = GetLastError();
    else
      LastError = 0;
    *((_DWORD *)Context + 10) = LastError;
    if ( (unsigned __int64)(*((_QWORD *)Context + 4) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
      CHandleObject::Close((void **)Context + 4);
    *((_QWORD *)Context + 4) = v9;
    NotificationInfo.APC.NotificationRoutine = (PFN_RPCNOTIFICATION_ROUTINE)*((_QWORD *)Context + 2);
    v11 = RpcServerSubscribeForNotification(
            0,
            RpcNotificationClientDisconnect,
            RpcNotificationTypeEvent,
            &NotificationInfo);
    v13 = v11;
    if ( v11 )
    {
      WppTraceIndent(v12, 2);
      v123 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        v124 = 14;
        goto LABEL_256;
      }
    }
  }
  else
  {
    v13 = GetLastError();
    WppTraceIndent(v122, 2);
    v123 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      v124 = 13;
LABEL_256:
      WPP_SF_sD(
        v123[2],
        v124,
        (unsigned int)WPP_8fae02f726263adb5326c29facded416_Traceguids,
        (_DWORD)WPP_pszIndent,
        v13);
    }
  }
  v14 = Context + 80;
  v202 = Context + 80;
  (**((void (__fastcall ***)(char *, _QWORD, _QWORD))Context + 10))(Context + 80, 0, 0);
  Value = TlsGetValue(dwTlsIndex);
  v200 = (LPVOID *)(Context + 136);
  if ( Value == *((LPVOID *)Context + 17) )
  {
    ++*((_DWORD *)Context + 36);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 8LL))(Context + 80);
  }
  else
  {
    v16 = *((_DWORD *)Context + 37);
    (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 8LL))(Context + 80);
    v17 = TlsGetValue(dword_18004B240);
    v18 = *((_QWORD *)v14 + 9);
    while ( 1 )
    {
      v19 = WaitForAnyObject(0xFFFFFFFF, v18, v17, 0);
      if ( v19 == 1 )
        break;
      if ( v19 == 2 )
      {
        v185 = -2146435070;
        throw &v185;
      }
    }
    v201 = (void **)v14;
    (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v14)(v14, 0, 0);
    if ( v16 != *((_DWORD *)v14 + 17) )
    {
      if ( !SetEvent(*((HANDLE *)v14 + 9)) )
      {
        v183 = GetLastError();
        throw &v183;
      }
      v184 = -2146435049;
      throw &v184;
    }
    *v200 = TlsGetValue(dwTlsIndex);
    *((_DWORD *)v14 + 16) = 1;
    (*(void (__fastcall **)(char *))(*(_QWORD *)v14 + 8LL))(v14);
  }
  v201 = v158;
  if ( !*(_BYTE *)a3 )
  {
    v186 = -2146435063;
    throw &v186;
  }
  if ( !a6 )
  {
    v187 = -2146435055;
    throw &v187;
  }
  while ( 2 )
  {
    v156 = 0;
    v163 = 0;
    v155 = 0;
    v137 = 0;
    v20 = 0;
    Size = 0;
    v142 = 0;
    v132 = 0;
    v146 = 0;
    v21 = 0;
    v138 = 0;
    for ( i = (unsigned __int16 *)FirstString(a3); ; i = (unsigned __int16 *)NextString(v23) )
    {
      v23 = i;
      phNewWaitObject = i;
      if ( !i || v21 >= a6 )
        break;
      v24 = v21;
      v157 = v21;
      v164 = (int *)(a5 + 4LL * v21);
      if ( (*v164 & 1) != 0 )
      {
        LOBYTE(NotificationsQueued) = 0;
        CBuffer::Append((CBuffer *)&v140, (const unsigned __int8 *const)&NotificationsQueued, 1u);
        v89 = 1;
        NotificationsQueued = v143;
        v20 = v142;
        Size = v142;
        Src = v141;
        v106 = v164;
        goto LABEL_148;
      }
      if ( v130 > v21 && (v25 = (__int64 **)*((_QWORD *)v139 + (int)v21)) != 0 )
      {
        v36 = *v25;
        v163 = *v25;
      }
      else
      {
        v26 = v158[22];
        v27 = g_pcsControlLocks;
        v194 = g_pcsControlLocks;
        (**(void (__fastcall ***)(struct CCriticalSectionObject *, _QWORD, _QWORD))g_pcsControlLocks)(
          g_pcsControlLocks,
          0,
          0);
        v28 = HIDWORD(qword_18004B0C8);
        v29 = HIDWORD(qword_18004B0C8);
        while ( 1 )
        {
          do
          {
            if ( !v29 )
            {
              v190 = -2146435063;
              throw &v190;
            }
            --v29;
          }
          while ( v28 <= v29 );
          _mm_lfence();
          v30 = (CReader *)*((_QWORD *)qword_18004B0D0 + (int)v29);
          if ( v30 )
          {
            v31 = *((_DWORD *)v30 + 7) ? (const WCHAR *)*((_QWORD *)v30 + 2) : &Data;
            if ( !lstrcmpiW(v23, v31) )
              break;
          }
          v28 = HIDWORD(qword_18004B0C8);
        }
        if ( (*(__int64 (__fastcall **)(CReader *))(*(_QWORD *)v30 + 56LL))(v30) )
        {
          if ( v26 )
          {
            v107 = (void *)(*(__int64 (__fastcall **)(CReader *))(*(_QWORD *)v30 + 56LL))(v30);
            if ( !EqualSid(v107, v26) )
            {
              v188 = -2146435063;
              throw &v188;
            }
          }
        }
        v32 = (char *)operator new(0x20u);
        v35 = (__int64 **)v32;
        v199 = v32;
        if ( v32 )
        {
          *(_OWORD *)(v32 + 8) = 0;
          *((_DWORD *)v32 + 6) = 0;
          *(_QWORD *)v32 = CReader::ReaderProxy(v30);
        }
        else
        {
          v35 = 0;
        }
        if ( !v35 )
        {
          CalaisError(v33, 0xCBu, 0, v34);
          v189 = -2146435066;
          throw &v189;
        }
        (*(void (__fastcall **)(struct CCriticalSectionObject *))(*(_QWORD *)v27 + 8LL))(v27);
        Block = v35;
        v36 = *v35;
        v163 = *v35;
        v37 = v139;
        v64 = v138;
        v65 = j;
        if ( v138 >= j )
        {
          if ( !j )
            v65 = 4;
          for ( j = v65; v138 >= v65; j = v65 )
            v65 *= 2;
          v66 = operator new[](saturated_mul(v65, 8u));
          if ( !v66 )
          {
            v191 = 14;
            throw &v191;
          }
          for ( k = 0; (unsigned int)k < v130; k = (unsigned int)(k + 1) )
            v66[k] = v37[k];
          if ( v37 )
            operator delete[](v37);
          v37 = v66;
          v139 = v66;
          v154 = v66;
          v152 = v65;
        }
        v68 = Block;
        if ( v64 >= v130 )
        {
          if ( v64 > v130 )
            memset_0(&v37[v130], 0, 8LL * (v64 - v130));
          v130 = v64 + 1;
          v153 = v64 + 1;
        }
        v37[v24] = v68;
        Block = 0;
      }
      (*(void (__fastcall **)(__int64 *, _QWORD, _QWORD))v36[1])(v36 + 1, 0, 0);
      if ( !*v36 )
      {
        (*(void (__fastcall **)(__int64 *))(v36[1] + 8))(v36 + 1);
        v192 = -2146435049;
        throw &v192;
      }
      v69 = *v36 + 512;
      v199 = (char *)v69;
      v194 = (struct CCriticalSectionObject *)v69;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v69)(v69, 0, 0);
      if ( *(LPVOID *)(v69 + 104) == TlsGetValue(dwTlsIndex) )
      {
        ++*(_DWORD *)(v69 + 56);
        CAccessLock::UnsignalNoReaders((CAccessLock *)v69);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 8LL))(v69);
      }
      else
      {
        do
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 8LL))(v69);
          v70 = *(_QWORD *)(v69 + 88);
          v71 = TlsGetValue(dword_18004B240);
          while ( 1 )
          {
            v72 = WaitForAnyObject(0xFFFFFFFF, v70, v71, 0);
            if ( v72 == 1 )
              break;
            if ( v72 == 2 )
            {
              v193 = -2146435070;
              throw &v193;
            }
          }
          v194 = (struct CCriticalSectionObject *)v69;
          (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v69)(v69, 0, 0);
        }
        while ( *(_DWORD *)(v69 + 60) && *(LPVOID *)(v69 + 104) != TlsGetValue(dwTlsIndex) );
        ++*(_DWORD *)(v69 + 56);
        if ( !ResetEvent(*(HANDLE *)(v69 + 72)) )
        {
          v195 = GetLastError();
          throw &v195;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 8LL))(v69);
      }
      (*(void (__fastcall **)(__int64 *))(v36[1] + 8))(v36 + 1);
      v73 = *v36;
      v74 = *v36 + 56;
      v194 = (struct CCriticalSectionObject *)v74;
      v157 = v74;
      (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v74)(v74, 0, 0);
      if ( *(LPVOID *)(v74 + 104) == TlsGetValue(dwTlsIndex) )
      {
        ++*(_DWORD *)(v74 + 56);
        CAccessLock::UnsignalNoReaders((CAccessLock *)v74);
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 8LL))(v74);
      }
      else
      {
        do
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 8LL))(v74);
          v75 = *(_QWORD *)(v74 + 88);
          v76 = TlsGetValue(dword_18004B240);
          while ( 1 )
          {
            v77 = WaitForAnyObject(0xFFFFFFFF, v75, v76, 0);
            if ( v77 == 1 )
              break;
            if ( v77 == 2 )
            {
              v196 = -2146435070;
              throw &v196;
            }
          }
          v157 = v74;
          (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v74)(v74, 0, 0);
        }
        while ( *(_DWORD *)(v74 + 60) && *(LPVOID *)(v74 + 104) != TlsGetValue(dwTlsIndex) );
        ++*(_DWORD *)(v74 + 56);
        if ( !ResetEvent(*(HANDLE *)(v74 + 72)) )
        {
          v197 = GetLastError();
          throw &v197;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 8LL))(v74);
      }
      v78 = *(unsigned int *)(v73 + 184);
      if ( *(_DWORD *)(v73 + 188) )
        v79 = *(const WCHAR **)(v73 + 176);
      else
        v79 = &Data;
      if ( Size_4 >= (unsigned int)v78 )
      {
        v80 = v149;
      }
      else
      {
        v80 = operator new[](*(unsigned int *)(v73 + 184));
        if ( !v80 )
        {
          v198 = 14;
          throw &v198;
        }
        if ( v149 )
          operator delete[](v149);
        v149 = v80;
        v160 = v80;
        Size_4 = v78;
        v162 = v78;
      }
      if ( (_DWORD)v78 )
        memcpy_0(v80, v79, v78);
      v161 = v78;
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v74 + 16LL))(v74) )
      {
        (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v74)(v74, 0, 0);
        v54 = (*(_DWORD *)(v74 + 56))-- == 1;
        if ( v54 && !SetEvent(*(HANDLE *)(v74 + 72)) )
        {
          v165 = GetLastError();
          throw &v165;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v74 + 8LL))(v74);
      }
      if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v69 + 16LL))(v69) )
      {
        (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))v69)(v69, 0, 0);
        v54 = (*(_DWORD *)(v69 + 56))-- == 1;
        if ( v54 && !SetEvent(*(HANDLE *)(v69 + 72)) )
        {
          v166 = GetLastError();
          throw &v166;
        }
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v69 + 8LL))(v69);
      }
      v81 = CReaderProxy::AvailabilityStatus(v36);
      v82 = CReaderProxy::ChangeEvent((CReaderProxy *)v36);
      v83 = CReaderProxy::ActivityHash((CReaderProxy *)v36);
      switch ( v81 )
      {
        case 1:
          v86 = 16;
          break;
        case 2:
          v86 = 1056;
          break;
        case 6:
          v86 = 288;
          break;
        default:
          switch ( v81 )
          {
            case 0:
              v87 = lpHandles;
              v88 = m;
              v86 = 5;
              LODWORD(v78) = 0;
              v161 = 0;
              v83 = 0;
              goto LABEL_246;
            case 3:
            case 4:
              v86 = 544;
              goto LABEL_112;
            case 5:
              v86 = 32;
              goto LABEL_112;
            case 7:
              v86 = 416;
              goto LABEL_112;
            case 8:
              v86 = 8;
              goto LABEL_112;
            case 9:
            case 10:
            case 11:
              v86 = 9;
              if ( v130 <= v138 )
                v121 = 0;
              else
                v121 = (void *)*((_QWORD *)v139 + v138);
              Block = v121;
              CDynamicArray<CReaderReference>::Set(&v151, v138, 0);
              CalaisReleaseReader((CReaderProxy ***)&Block);
              v163 = 0;
              v83 = 0;
              v139 = v154;
              v130 = v153;
              j = v152;
              v87 = lpHandles;
              v88 = m;
LABEL_246:
              v82 = 0;
              break;
            default:
              CalaisError(v84, 0x132u, 0, v85);
              v167 = -2146435071;
              throw &v167;
          }
          goto LABEL_113;
      }
LABEL_112:
      v87 = lpHandles;
      v88 = m;
LABEL_113:
      v89 = (v83 << 16) + v86;
      v90 = v164;
      *v164 &= 0xFFFF07BC;
      v91 = *v90;
      if ( ((unsigned __int8)*v90 & (unsigned __int8)v89 & 0x20) != 0 || (unsigned __int16)v91 == (unsigned __int16)v89 )
      {
        v108 = v91 & 0xFFFF0000;
        if ( v108 != (v89 & 0xFFFF0000) )
        {
          if ( v108 )
          {
            LODWORD(v78) = 0;
            v161 = 0;
            v109 = (unsigned __int16)(v83 - 1) << 16;
            v110 = v109 + ((unsigned __int16)v89 ^ 0x30);
            v111 = v110 & 0x30;
            if ( v111 == 16 )
            {
              v89 = v110 & 0xFFFFFC7F;
            }
            else
            {
              if ( v111 != 32 )
              {
                WppTraceIndent(v109, 2);
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
                {
                  WPP_SF_s(
                    *((_QWORD *)WPP_GLOBAL_Control + 2),
                    18,
                    WPP_8fae02f726263adb5326c29facded416_Traceguids,
                    WPP_pszIndent);
                }
                v168 = -2146435071;
                throw &v168;
              }
              v89 = v110 | 0x200;
            }
          }
        }
      }
      ++v137;
      if ( v82 )
      {
        v92 = v132;
        while ( v92 )
        {
          if ( v132 > --v92 && v87[v92] == (HANDLE)v82 )
            goto LABEL_35;
        }
        v93 = v132;
        if ( v132 >= v88 )
        {
          if ( !v88 )
            v88 = 4;
          for ( m = v88; (int)v132 >= v88; m = v88 )
            v88 *= 2;
          v118 = (HANDLE *)operator new[](saturated_mul(v88, 8u));
          if ( !v118 )
          {
            v169 = 14;
            throw &v169;
          }
          for ( n = 0; n < v132; ++n )
            v118[n] = v87[n];
          if ( v87 )
            operator delete[](v87);
          v87 = v118;
          lpHandles = v118;
          v147 = v118;
          v145 = m;
        }
        ++v132;
        v146 = v93 + 1;
        v87[v93] = (HANDLE)v82;
      }
LABEL_35:
      v38 = Size;
      v39 = Size + 1;
      if ( Size )
      {
        if ( NotificationsQueued >= v39 )
        {
          v41 = Src;
        }
        else
        {
          v40 = (char *)operator new[](v39);
          v41 = v40;
          if ( !v40 )
          {
            v170 = 14;
            throw &v170;
          }
          memcpy_0(v40, Src, v38);
          operator delete[](Src);
          Src = v41;
          v141 = v41;
          NotificationsQueued = v39;
          v143 = v39;
        }
      }
      else
      {
        if ( NotificationsQueued >= v39 )
        {
          v41 = Src;
        }
        else
        {
          v41 = (char *)operator new[](v39);
          if ( !v41 )
          {
            v171 = 14;
            throw &v171;
          }
          if ( Src )
            operator delete[](Src);
          Src = v41;
          v141 = v41;
          NotificationsQueued = v39;
          v143 = v39;
        }
        v38 = 0;
      }
      v41[v38] = v78;
      v20 = v38 + 1;
      Size = v20;
      v142 = v20;
      v103 = &Data;
      if ( Size_4 )
        v103 = (const WCHAR *)v149;
      if ( (_DWORD)v78 )
      {
        v104 = v78 + v20;
        if ( v20 )
        {
          if ( NotificationsQueued < v104 )
          {
            v105 = (char *)operator new[](v104);
            v41 = v105;
            if ( !v105 )
            {
              v172 = 14;
              throw &v172;
            }
            memcpy_0(v105, Src, v20);
            operator delete[](Src);
            Src = v41;
            v141 = v41;
            NotificationsQueued = v78 + v20;
            v143 = v78 + v20;
          }
        }
        else
        {
          if ( NotificationsQueued < v104 )
          {
            v41 = (char *)operator new[](v104);
            if ( !v41 )
            {
              v173 = 14;
              throw &v173;
            }
            if ( Src )
              operator delete[](Src);
            Src = v41;
            v141 = v41;
            NotificationsQueued = v78 + v20;
            v143 = v78 + v20;
          }
          v20 = 0;
        }
        memcpy_0(&v41[v20], v103, (unsigned int)v78);
        v20 += v78;
        Size = v20;
        v142 = v20;
      }
      v106 = v164;
      v23 = (const unsigned __int16 *)phNewWaitObject;
      if ( *v164 != v89 )
      {
        v156 = 1;
        v89 |= 2u;
      }
LABEL_148:
      *v106 = v89;
      v21 = ++v138;
    }
    if ( !v137 )
    {
      v174 = -2146435026;
      throw &v174;
    }
    if ( !v156 )
    {
      v94 = *v158;
      v95 = m;
      if ( v132 >= m )
      {
        if ( !m )
          v95 = 4;
        for ( m = v95; (int)v132 >= v95; m = v95 )
          v95 *= 2;
        v114 = (HANDLE *)operator new[](saturated_mul(v95, 8u));
        if ( !v114 )
        {
          v176 = 14;
          throw &v176;
        }
        for ( ii = 0; ii < v132; ++ii )
          v114[ii] = lpHandles[ii];
        if ( lpHandles )
          operator delete[](lpHandles);
        v96 = v114;
        lpHandles = v114;
        v147 = v114;
        v145 = v95;
      }
      else
      {
        v96 = lpHandles;
      }
      v97 = v132 + 1;
      v146 = v132 + 1;
      v96[v132] = v94;
      v98 = g_hCalaisShutdown;
      if ( (unsigned int)v97 >= v95 )
      {
        if ( !v95 )
          v95 = 4;
        for ( m = v95; (int)v97 >= v95; m = v95 )
          v95 *= 2;
        v116 = (HANDLE *)operator new[](saturated_mul(v95, 8u));
        if ( !v116 )
        {
          v177 = 14;
          throw &v177;
        }
        v117 = 0;
        if ( v132 != -1 )
        {
          do
          {
            v116[v117] = v96[v117];
            ++v117;
          }
          while ( v117 < (unsigned int)v97 );
        }
        if ( v96 )
          operator delete[](v96);
        v96 = v116;
        lpHandles = v116;
        v147 = v116;
        v145 = v95;
      }
      v99 = v132 + 2;
      v146 = v132 + 2;
      v96[v97] = v98;
      v100 = WaitForMultipleObjects(v132 + 2, v96, 0, a2);
      v102 = v100;
      if ( v100 == -1 )
      {
        v125 = GetLastError();
        WppTraceIndent(v126, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            19,
            (unsigned int)WPP_8fae02f726263adb5326c29facded416_Traceguids,
            (_DWORD)WPP_pszIndent,
            v125);
        }
        v178 = v125;
        throw &v178;
      }
      if ( v100 == 258 )
      {
        pExceptionObject = -2146435062;
        throw &pExceptionObject;
      }
      if ( v100 >= 0x80 )
      {
        WppTraceIndent(v101, 2);
        v101 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            WPP_8fae02f726263adb5326c29facded416_Traceguids,
            WPP_pszIndent);
        }
        v102 -= 128;
      }
      if ( v102 >= v99 )
      {
        WppTraceIndent(v101, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            WPP_8fae02f726263adb5326c29facded416_Traceguids,
            WPP_pszIndent);
        }
        v180 = -2146435071;
        throw &v180;
      }
      v120 = v96[v102];
      if ( v120 == g_hCalaisShutdown )
      {
        v181 = -2146435054;
        throw &v181;
      }
      if ( v99 <= v102 )
        v120 = 0;
      if ( v94 == v120 )
      {
        v182 = -2146435070;
        throw &v182;
      }
      continue;
    }
    break;
  }
  v42 = Block;
  if ( Block )
  {
    CReaderProxy::Release(*(CReaderProxy **)Block);
    operator delete(v42);
  }
  v43 = v130;
  v44 = v130;
  if ( v130 )
  {
    v112 = v139;
    do
    {
      if ( v43 > --v44 )
      {
        _mm_lfence();
        v113 = (CReaderProxy **)v112[v44];
        if ( v113 )
        {
          CReaderProxy::Release(*v113);
          operator delete(v113);
        }
        v43 = v130;
      }
    }
    while ( v44 );
  }
  v45 = a8;
  *a8 = v20;
  ProcessHeap = GetProcessHeap();
  v47 = HeapAlloc(ProcessHeap, 8u, v20);
  *a7 = v47;
  if ( !v47 )
  {
    v175 = -2146435066;
    throw &v175;
  }
  v48 = Src;
  v49 = &Data;
  if ( NotificationsQueued )
    v49 = (const WCHAR *)Src;
  memcpy_0(v47, v49, *v45);
  if ( v201 )
  {
    v51 = v202;
    (**(void (__fastcall ***)(char *, _QWORD, _QWORD))v202)(v202, 0, 0);
    v52 = TlsGetValue(dwTlsIndex);
    v53 = v200;
    if ( *v200 == v52 )
    {
      v54 = (*((_DWORD *)v51 + 16))-- == 1;
      if ( v54 )
      {
        *v53 = 0;
        if ( !SetEvent(*((HANDLE *)v51 + 9)) )
          GetLastError();
      }
    }
    (*(void (__fastcall **)(char *))(*(_QWORD *)v51 + 8LL))(v51);
  }
  v55 = lpHandles;
  v56 = v139;
  v57 = v149;
  NotificationsQueued = 0;
  if ( v158 )
  {
    v58 = RpcServerUnsubscribeForNotification(0, RpcNotificationClientDisconnect, &NotificationsQueued);
    v60 = v58;
    if ( v58 )
    {
      WppTraceIndent(v59, 2);
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
      {
        WPP_SF_sD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          16,
          (unsigned int)WPP_8fae02f726263adb5326c29facded416_Traceguids,
          (_DWORD)WPP_pszIndent,
          v60);
      }
    }
    v61 = v158;
    v62 = v158[4];
    if ( v62 )
    {
      if ( !UnregisterWaitEx(v62, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
      {
        v127 = GetLastError();
        WppTraceIndent(v128, 2);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            17,
            (unsigned int)WPP_8fae02f726263adb5326c29facded416_Traceguids,
            (_DWORD)WPP_pszIndent,
            v127);
        }
        v55 = lpHandles;
      }
      v61[4] = 0;
    }
    v48 = Src;
  }
  else
  {
    WppTraceIndent(v50, 2);
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x20) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
    {
      WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_8fae02f726263adb5326c29facded416_Traceguids, WPP_pszIndent);
    }
  }
  if ( v55 )
    operator delete[](v55);
  if ( v56 )
    operator delete[](v56);
  if ( v57 )
    operator delete[](v57);
  if ( v48 )
    operator delete[](v48);
  return v148;
}

```

## disassembly

```asm
0x18000a310  mov     r11, rsp
0x18000a313  mov     [r11+20h], r9d
0x18000a317  mov     [r11+18h], r8
0x18000a31b  mov     [rsp+arg_8], edx
0x18000a31f  push    rbx
0x18000a320  push    rsi
0x18000a321  push    rdi
0x18000a322  push    r12
0x18000a324  push    r13
0x18000a326  push    r14
0x18000a328  push    r15
0x18000a32a  sub     rsp, 200h
0x18000a331  mov     rbx, rcx
0x18000a334  lea     rcx, ??_7CBuffer@@6B@; const CBuffer::`vftable'
0x18000a33b  mov     [rsp+238h+var_1C0], rcx
0x18000a340  xor     r13d, r13d
0x18000a343  mov     eax, r13d
0x18000a346  mov     [rsp+238h+Src], rax
0x18000a34b  mov     [r11-1B8h], rax
0x18000a352  mov     [r11-1B0h], r13d
0x18000a359  mov     [r11+20h], eax
0x18000a35d  mov     [rsp+238h+var_1AC], eax
0x18000a364  mov     [r11-148h], rcx
0x18000a36b  mov     [r11-188h], rax
0x18000a372  mov     [r11-140h], rax
0x18000a379  mov     [r11-138h], r13d
0x18000a380  mov     eax, r13d
0x18000a383  mov     dword ptr [rsp+238h+Size+4], eax
0x18000a387  mov     [rsp+238h+var_134], eax
0x18000a38e  mov     [rsp+238h+Block], r13
0x18000a393  lea     rax, ??_7?$CDynamicArray@VCServiceThread@@@@6B@; const CDynamicArray<CServiceThread>::`vftable'
0x18000a39a  mov     [r11-178h], rax
0x18000a3a1  mov     eax, r13d
0x18000a3a4  mov     [rsp+238h+var_200], eax
0x18000a3a8  mov     [rsp+238h+var_16C], eax
0x18000a3af  mov     [rsp+238h+var_1E0], eax
0x18000a3b3  mov     [rsp+238h+var_170], eax
0x18000a3ba  mov     eax, r13d
0x18000a3bd  mov     [rsp+238h+var_1C8], rax
0x18000a3c2  mov     [r11-168h], rax
0x18000a3c9  lea     rax, ??_7?$CDynamicArray@VCServiceThread@@@@6B@; const CDynamicArray<CServiceThread>::`vftable'
0x18000a3d0  mov     [r11-1A8h], rax
0x18000a3d7  mov     [r11-19Ch], r13d
0x18000a3de  mov     eax, r13d
0x18000a3e1  mov     [r11+8], eax
0x18000a3e5  mov     [rsp+238h+var_1A0], eax
0x18000a3ec  mov     [rsp+238h+lpHandles], r13
0x18000a3f1  mov     [r11-198h], r13
0x18000a3f8  mov     [rsp+238h+var_150], rbx
0x18000a400  mov     [rsp+238h+var_190], r13d
0x18000a408  mov     rdx, [rbx+48h]; lpTlsValue
0x18000a40c  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000a412  call    cs:__imp_TlsSetValue
0x18000a418  test    eax, eax
0x18000a41a  jz      loc_18000B5F0
0x18000a420  mov     rdx, [rbx]; lpTlsValue
0x18000a423  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000a429  call    cs:__imp_TlsSetValue
0x18000a42f  test    eax, eax
0x18000a431  jz      loc_18000B5F0
0x18000a437  mov     eax, 1
0x18000a43c  xchg    eax, cs:?g_fExtendShutdownTimer@@3JA; long g_fExtendShutdownTimer
0x18000a442  mov     qword ptr [rsp+238h+NotificationInfo], r13
0x18000a44a  xorps   xmm0, xmm0
0x18000a44d  xor     eax, eax
0x18000a44f  movups  xmmword ptr [rsp+238h+NotificationInfo+8], xmm0
0x18000a457  mov     qword ptr [rsp+238h+NotificationInfo+18h], rax
0x18000a45f  mov     [rsp+238h+phNewWaitObject], r13
0x18000a467  mov     [rsp+238h+dwFlags], 8; dwFlags
0x18000a46f  mov     [rsp+238h+dwMilliseconds], 0FFFFFFFFh; unsigned __int16 *
0x18000a477  mov     r9, rbx; Context
0x18000a47a  lea     r8, CalRpcClientDisconnected; Callback
0x18000a481  mov     rdx, [rbx+10h]; hObject
0x18000a485  lea     rcx, [rsp+238h+phNewWaitObject]; phNewWaitObject
0x18000a48d  call    cs:__imp_RegisterWaitForSingleObject
0x18000a493  test    eax, eax
0x18000a495  jz      loc_18000B988
0x18000a49b  mov     rsi, [rsp+238h+phNewWaitObject]
0x18000a4a3  lea     rax, [rsi-1]
0x18000a4a7  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a4ab  ja      loc_18000B9CC
0x18000a4b1  mov     eax, r13d
0x18000a4b4  mov     [rbx+28h], eax
0x18000a4b7  mov     rax, [rbx+20h]
0x18000a4bb  dec     rax
0x18000a4be  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18000a4c2  jbe     loc_18000B9D7
0x18000a4c8  mov     [rbx+20h], rsi
0x18000a4cc  mov     rax, [rbx+10h]
0x18000a4d0  mov     qword ptr [rsp+238h+NotificationInfo], rax
0x18000a4d8  lea     r9, [rsp+238h+NotificationInfo]; NotificationInfo
0x18000a4e0  mov     edx, 1; Notification
0x18000a4e5  xor     ecx, ecx; Binding
0x18000a4e7  mov     r8d, edx; NotificationType
0x18000a4ea  call    cs:__imp_RpcServerSubscribeForNotification
0x18000a4f0  mov     edi, eax
0x18000a4f2  test    eax, eax
0x18000a4f4  jnz     loc_18000B9E5
0x18000a4fa  lea     r14, [rbx+50h]
0x18000a4fe  mov     [rsp+238h+var_70], r14
0x18000a506  mov     rax, [r14]
0x18000a509  xor     r8d, r8d
0x18000a50c  xor     edx, edx
0x18000a50e  mov     rcx, r14
0x18000a511  mov     rax, [rax]
0x18000a514  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a519  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000a51f  call    cs:__imp_TlsGetValue
0x18000a525  lea     rcx, [r14+38h]
0x18000a529  mov     [rsp+238h+var_80], rcx
0x18000a531  cmp     rax, [rcx]
0x18000a534  jz      loc_18000B538
0x18000a53a  mov     esi, [r14+44h]
0x18000a53e  mov     rax, [r14]
0x18000a541  mov     rcx, r14
0x18000a544  mov     rax, [rax+8]
0x18000a548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a54d  nop
0x18000a54e  mov     ecx, cs:dword_18004B240; dwTlsIndex
0x18000a554  call    cs:__imp_TlsGetValue
0x18000a55a  mov     rbx, rax
0x18000a55d  mov     rdi, [r14+48h]
0x18000a561  xor     r9d, r9d
0x18000a564  mov     r8, rbx
0x18000a567  mov     rdx, rdi
0x18000a56a  mov     ecx, 0FFFFFFFFh; dwMilliseconds
0x18000a56f  call    ?WaitForAnyObject@@YAKKZZ; WaitForAnyObject(ulong,...)
0x18000a574  cmp     eax, 1
0x18000a577  jnz     loc_18000B6E9
0x18000a57d  mov     [rsp+238h+var_78], r14
0x18000a585  mov     rax, [r14]
0x18000a588  xor     r8d, r8d
0x18000a58b  xor     edx, edx
0x18000a58d  mov     rcx, r14
0x18000a590  mov     rax, [rax]
0x18000a593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a598  nop
0x18000a599  cmp     esi, [r14+44h]
0x18000a59d  jnz     loc_18000C08F
0x18000a5a3  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x18000a5a9  call    cs:__imp_TlsGetValue
0x18000a5af  mov     rcx, [rsp+238h+var_80]
0x18000a5b7  mov     [rcx], rax
0x18000a5ba  mov     dword ptr [r14+40h], 1
0x18000a5c2  mov     rax, [r14]
0x18000a5c5  mov     rcx, r14
0x18000a5c8  mov     rax, [rax+8]
0x18000a5cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5d1  nop
0x18000a5d2  mov     rax, [rsp+238h+var_150]
0x18000a5da  mov     [rsp+238h+var_78], rax
0x18000a5e2  mov     rax, [rsp+238h+arg_10]
0x18000a5ea  cmp     byte ptr [rax], 0
0x18000a5ed  jz      loc_18000BA3F
0x18000a5f3  cmp     [rsp+238h+arg_28], 0
0x18000a5fb  jz      loc_18000BA5E
0x18000a601  mov     [rsp+238h+var_15C], r13d
0x18000a609  mov     [rsp+238h+var_130], r13
0x18000a611  mov     [rsp+238h+var_160], r13d
0x18000a619  mov     [rsp+238h+var_1D4], r13d
0x18000a61e  mov     r15d, r13d
0x18000a621  mov     dword ptr [rsp+238h+Size], r13d
0x18000a626  mov     [rsp+238h+var_1B0], r13d
0x18000a62e  mov     [rsp+238h+var_1F0], r13d
0x18000a633  mov     [rsp+238h+var_19C], r13d
0x18000a63b  mov     r14d, r13d
0x18000a63e  mov     [rsp+238h+var_1D0], r13d
0x18000a643  mov     rcx, [rsp+238h+arg_10]; unsigned __int16 *
0x18000a64b  call    ?FirstString@@YAPEBGPEBG@Z; FirstString(ushort const *)
0x18000a650  mov     r12, rax
0x18000a653  mov     [rsp+238h+phNewWaitObject], rax
0x18000a65b  test    rax, rax
0x18000a65e  jz      loc_18000A87C
0x18000a664  cmp     r14d, [rsp+238h+arg_28]
0x18000a66c  jnb     loc_18000A87C
0x18000a672  mov     r15d, r14d
0x18000a675  mov     [rsp+238h+var_158], r15
0x18000a67d  mov     rcx, [rsp+238h+arg_20]
0x18000a685  lea     rax, [rcx+r15*4]
0x18000a689  mov     [rsp+238h+var_128], rax
0x18000a691  mov     eax, [rax]
0x18000a693  test    al, 1
0x18000a695  jnz     loc_18000BA7E
0x18000a69b  cmp     [rsp+238h+var_200], r14d
0x18000a6a0  jbe     short loc_18000A6B7
0x18000a6a2  movsxd  rax, r14d
0x18000a6a5  mov     rdi, [rsp+238h+var_1C8]
0x18000a6aa  mov     rcx, [rdi+rax*8]
0x18000a6ae  test    rcx, rcx
0x18000a6b1  jnz     loc_18000B551
0x18000a6b7  mov     rax, [rsp+238h+var_150]
0x18000a6bf  mov     r14, [rax+0B0h]
0x18000a6c6  mov     rbx, cs:?g_pcsControlLocks@@3PAPEAVCCriticalSectionObject@@A; CCriticalSectionObject * near * g_pcsControlLocks
0x18000a6cd  mov     [rsp+238h+var_A0], rbx
0x18000a6d5  mov     rax, [rbx]
0x18000a6d8  xor     r8d, r8d
0x18000a6db  xor     edx, edx
0x18000a6dd  mov     rcx, rbx
0x18000a6e0  mov     rax, [rax]
0x18000a6e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6e8  nop
0x18000a6e9  mov     eax, dword ptr cs:qword_18004B0C8+4
0x18000a6ef  mov     edi, eax
0x18000a6f1  test    edi, edi
0x18000a6f3  jz      loc_18000B257
0x18000a6f9  dec     edi
0x18000a6fb  cmp     eax, edi
0x18000a6fd  jbe     short loc_18000A6F1
0x18000a6ff  lfence
0x18000a702  movsxd  rcx, edi
0x18000a705  mov     rax, cs:qword_18004B0D0
0x18000a70c  mov     rsi, [rax+rcx*8]
0x18000a710  test    rsi, rsi
0x18000a713  jz      short loc_18000A733
0x18000a715  cmp     dword ptr [rsi+1Ch], 0
0x18000a719  ja      loc_18000AA57
0x18000a71f  lea     rdx, Data; lpString2
0x18000a726  mov     rcx, r12; lpString1
0x18000a729  call    cs:__imp_lstrcmpiW
0x18000a72f  test    eax, eax
0x18000a731  jz      short loc_18000A73B
0x18000a733  mov     eax, dword ptr cs:qword_18004B0C8+4
0x18000a739  jmp     short loc_18000A6F1
0x18000a73b  mov     rax, [rsi]
0x18000a73e  mov     rcx, rsi
0x18000a741  mov     rax, [rax+38h]
0x18000a745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a74a  test    rax, rax
0x18000a74d  jnz     loc_18000B0E0
0x18000a753  mov     ecx, 20h ; ' '; Size
0x18000a758  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000a75d  mov     rdi, rax
0x18000a760  mov     [rsp+238h+var_88], rax
0x18000a768  test    rax, rax
0x18000a76b  jz      loc_18000BAD9
0x18000a771  xorps   xmm0, xmm0
0x18000a774  movups  xmmword ptr [rax+8], xmm0
0x18000a778  mov     [rax+18h], r13d
0x18000a77c  mov     rcx, rsi; this
0x18000a77f  call    ?ReaderProxy@CReader@@QEAAPEAVCReaderProxy@@XZ; CReader::ReaderProxy(void)
0x18000a784  mov     [rdi], rax
0x18000a787  test    rdi, rdi
0x18000a78a  jz      loc_18000BAE1
0x18000a790  mov     rax, [rbx]
0x18000a793  mov     rcx, rbx
0x18000a796  mov     rax, [rax+8]
0x18000a79a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a79f  nop
0x18000a7a0  mov     [rsp+238h+Block], rdi
0x18000a7a5  mov     r13, [rdi]
0x18000a7a8  mov     [rsp+238h+var_130], r13
0x18000a7b0  mov     rdi, [rsp+238h+var_1C8]
0x18000a7b5  mov     esi, [rsp+238h+var_200]
0x18000a7b9  cmp     [rsp+238h+Block], 0
0x18000a7bf  jnz     loc_18000AA60
0x18000a7c5  mov     rdx, cs:off_180038110; String2
0x18000a7cc  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000a7d3  mov     rbx, rsi
0x18000a7d6  inc     rbx
0x18000a7d9  cmp     word ptr [rdx+rbx*2], 0
0x18000a7de  jnz     short loc_18000A7D6
0x18000a7e0  xor     r13d, r13d
0x18000a7e3  mov     r12d, r13d
0x18000a7e6  mov     [rsp+238h+var_138], r13d
0x18000a7ee  mov     r8, rbx; MaxCount
0x18000a7f1  mov     rdi, [rsp+238h+phNewWaitObject]
0x18000a7f9  mov     rcx, rdi; String1
0x18000a7fc  call    cs:__imp__wcsnicmp
0x18000a802  test    eax, eax
0x18000a804  jz      loc_18000B166
0x18000a80a  mov     r14d, 5
0x18000a810  mov     r15d, dword ptr [rsp+238h+Size]
0x18000a815  lea     ebx, [r15+1]
0x18000a819  test    r15d, r15d
0x18000a81c  jz      loc_18000AF49
0x18000a822  cmp     [rsp+238h+NotificationsQueued], ebx
0x18000a829  jnb     loc_18000B6DF
0x18000a82f  mov     ecx, ebx; unsigned __int64
0x18000a831  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000a836  mov     rdi, rax
0x18000a839  test    rax, rax
0x18000a83c  jz      loc_18000BE4D
0x18000a842  mov     r8d, r15d; Size
0x18000a845  mov     rdx, [rsp+238h+Src]; Src
0x18000a84a  mov     rcx, rax; void *
0x18000a84d  call    memcpy_0
0x18000a852  mov     rcx, [rsp+238h+Src]; Block
0x18000a857  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x18000a85c  mov     [rsp+238h+Src], rdi
0x18000a861  mov     [rsp+238h+var_1B8], rdi
0x18000a869  mov     [rsp+238h+NotificationsQueued], ebx
0x18000a870  mov     [rsp+238h+var_1AC], ebx
0x18000a877  jmp     loc_18000AF95
0x18000a87c  cmp     [rsp+238h+var_1D4], 0
0x18000a881  jz      loc_18000BEC9
0x18000a887  cmp     [rsp+238h+var_15C], 0
0x18000a88f  jz      loc_18000AEAD
0x18000a895  mov     rbx, [rsp+238h+Block]
0x18000a89a  test    rbx, rbx
0x18000a89d  jz      short loc_18000A8B0
  ... truncated ...
```
