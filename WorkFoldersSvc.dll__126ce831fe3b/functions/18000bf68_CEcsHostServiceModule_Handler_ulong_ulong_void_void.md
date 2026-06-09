# CEcsHostServiceModule::Handler(ulong,ulong,void *,void *)

- ea: `0x18000bf68`
- end: `0x18000cbc2`
- name: `?Handler@CEcsHostServiceModule@@AEAAKKKPEAX0@Z`
- size: `3162`
- prototype: `unsigned int __fastcall(CEcsHostServiceModule *__hidden this, unsigned int, unsigned int, void *, void *)`
- caller_count: `1`
- callee_count: `26`
- tags: `loader_planting, service_task`

## callers

- `0x180010e50`

## callees

- `0x180002ab0`
- `0x180002fa4`
- `0x180003604`
- `0x18000444c`
- `0x180007b9c`
- `0x180007e10`
- `0x180008108`
- `0x1800083b4`
- `0x1800084ac`
- `0x180008b60`
- `0x180008ba8`
- `0x180008bdc`
- `0x180009384`
- `0x1800093d0`
- `0x1800093f4`
- `0x180009424`
- `0x18000bf68`
- `0x18000fb80`
- `0x18000fd04`
- `0x180010ee0`
- `0x180011070`
- `0x1800110c0`
- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x1800113dc`

## import_xrefs

- `KERNEL32!SubmitThreadpoolWork` at `0x18000c258`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000c37e`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000c578`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000c664`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000c908`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000caa1`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000c258`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000c37e`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000c578`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000c664`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000c908`
- `KERNEL32!SubmitThreadpoolWork` at `0x18000caa1`
- `KERNEL32!CreateThreadpoolWork` at `0x18000c1d7`
- `KERNEL32!CreateThreadpoolWork` at `0x18000c2fd`
- `KERNEL32!CreateThreadpoolWork` at `0x18000c4f6`
- `KERNEL32!CreateThreadpoolWork` at `0x18000c5dc`
- `KERNEL32!CreateThreadpoolWork` at `0x18000c881`
- `KERNEL32!CreateThreadpoolWork` at `0x18000ca1a`
- `KERNEL32!CreateThreadpoolWork` at `0x18000c1d7`
- `KERNEL32!CreateThreadpoolWork` at `0x18000c2fd`
- `KERNEL32!CreateThreadpoolWork` at `0x18000c4f6`
- `KERNEL32!CreateThreadpoolWork` at `0x18000c5dc`
- `KERNEL32!CreateThreadpoolWork` at `0x18000c881`
- `KERNEL32!CreateThreadpoolWork` at `0x18000ca1a`
- `KERNEL32!GetLastError` at `0x18000c2c2`
- `KERNEL32!GetLastError` at `0x18000c2c2`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18000c117`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSQuerySessionInformationW` at `0x18000c117`
- `ext-ms-win-session-wtsapi32-l1-1-0!WTSFreeMemory` at `0x18000c166`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c69a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cafa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c3b4`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000c69a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000cafa`

## string_xrefs

- `0x18000c012`: `CEcsHostServiceModule::Handler`

## pseudocode

```c
// Hidden C++ exception states: #wind=24
__int64 __fastcall CEcsHostServiceModule::Handler(
        CEcsHostServiceModule *this,
        int a2,
        int a3,
        void (__stdcall *a4)(PVOID pMemory))
{
  void (__stdcall *v4)(PVOID); // rsi
  int v5; // r13d
  _BYTE *v7; // rax
  int v8; // r15d
  char v9; // al
  int v10; // edi
  int v11; // edi
  int v12; // edi
  int v13; // edi
  int v14; // edi
  PVOID v15; // rdi
  _DWORD *v16; // rax
  __int64 v17; // rdx
  int v18; // ecx
  DWORD LastError; // eax
  __int64 v20; // r9
  _QWORD *v21; // rcx
  __int64 v22; // rdx
  __int64 v23; // rax
  PVOID *v24; // rcx
  __int64 v25; // rax
  PVOID v26; // r14
  __int64 v27; // rax
  __int64 v28; // r10
  _QWORD *v29; // rdi
  __int64 v30; // rsi
  __int64 v31; // rax
  __int64 v32; // r10
  _QWORD *v33; // rdi
  __int64 v34; // rsi
  CEcsHostServiceModule *v35; // rcx
  int v37; // [rsp+30h] [rbp-208h] BYREF
  int v38; // [rsp+34h] [rbp-204h]
  char v39; // [rsp+38h] [rbp-200h]
  const char *v40; // [rsp+40h] [rbp-1F8h]
  __int64 v41; // [rsp+48h] [rbp-1F0h]
  unsigned int v42; // [rsp+50h] [rbp-1E8h]
  void (__stdcall *v43)(PVOID); // [rsp+58h] [rbp-1E0h] BYREF
  LPWSTR ppBuffer; // [rsp+60h] [rbp-1D8h] BYREF
  _QWORD *v45; // [rsp+68h] [rbp-1D0h] BYREF
  DWORD pBytesReturned; // [rsp+70h] [rbp-1C8h] BYREF
  int pExceptionObject; // [rsp+74h] [rbp-1C4h] BYREF
  int LastFailureAsHRESULT; // [rsp+78h] [rbp-1C0h] BYREF
  int v49; // [rsp+7Ch] [rbp-1BCh] BYREF
  int v50; // [rsp+80h] [rbp-1B8h] BYREF
  int v51; // [rsp+84h] [rbp-1B4h] BYREF
  int v52; // [rsp+88h] [rbp-1B0h] BYREF
  PTP_WORK v53; // [rsp+90h] [rbp-1A8h] BYREF
  PVOID v54; // [rsp+98h] [rbp-1A0h] BYREF
  PTP_WORK v55; // [rsp+A0h] [rbp-198h] BYREF
  PVOID v56; // [rsp+A8h] [rbp-190h] BYREF
  PTP_WORK pwk; // [rsp+B0h] [rbp-188h] BYREF
  PVOID pv; // [rsp+B8h] [rbp-180h] BYREF
  PTP_WORK v59; // [rsp+C0h] [rbp-178h] BYREF
  PTP_WORK v60; // [rsp+C8h] [rbp-170h] BYREF
  PTP_WORK v61; // [rsp+D0h] [rbp-168h] BYREF
  __int64 v62; // [rsp+D8h] [rbp-160h] BYREF
  PTP_WORK v63; // [rsp+E0h] [rbp-158h] BYREF
  PTP_WORK ThreadpoolWork; // [rsp+E8h] [rbp-150h] BYREF
  __int64 v65; // [rsp+F0h] [rbp-148h] BYREF
  PTP_WORK v66; // [rsp+F8h] [rbp-140h] BYREF
  __int64 v67; // [rsp+100h] [rbp-138h] BYREF
  PTP_WORK v68; // [rsp+108h] [rbp-130h] BYREF
  __int64 v69; // [rsp+110h] [rbp-128h] BYREF
  PTP_WORK v70; // [rsp+118h] [rbp-120h] BYREF
  __int64 v71; // [rsp+120h] [rbp-118h] BYREF
  PTP_WORK v72; // [rsp+128h] [rbp-110h] BYREF
  int v73; // [rsp+130h] [rbp-108h] BYREF
  int v74; // [rsp+134h] [rbp-104h] BYREF
  int v75; // [rsp+138h] [rbp-100h] BYREF
  LPCRITICAL_SECTION v76; // [rsp+140h] [rbp-F8h] BYREF
  char v77; // [rsp+148h] [rbp-F0h]
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+150h] [rbp-E8h] BYREF
  char v79; // [rsp+158h] [rbp-E0h]
  LPCRITICAL_SECTION v80; // [rsp+160h] [rbp-D8h] BYREF
  char v81; // [rsp+168h] [rbp-D0h]
  int v82; // [rsp+170h] [rbp-C8h] BYREF
  const ATL::CAtlException *v83; // [rsp+178h] [rbp-C0h] BYREF
  const ATL::CAtlException *v84; // [rsp+180h] [rbp-B8h] BYREF
  const ATL::CAtlException *v85; // [rsp+188h] [rbp-B0h] BYREF
  _BYTE v86[16]; // [rsp+190h] [rbp-A8h] BYREF
  const ATL::CAtlException *v87; // [rsp+1A0h] [rbp-98h] BYREF
  _BYTE v88[32]; // [rsp+1A8h] [rbp-90h] BYREF
  _BYTE v89[32]; // [rsp+1C8h] [rbp-70h] BYREF
  _BYTE v90[32]; // [rsp+1E8h] [rbp-50h] BYREF

  v4 = a4;
  v5 = a3;
  v43 = a4;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v9 = 0;
      v8 = 1;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 28, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
      v7 = WPP_GLOBAL_Control;
    }
  }
  if ( (v7[68] & 8) == 0 || v7[65] < 6u )
    goto LABEL_8;
  v8 = 1;
  v9 = 1;
LABEL_9:
  v37 = 0;
  v38 = 444;
  v39 = v9;
  v40 = "CEcsHostServiceModule::Handler";
  v41 = 0;
  v42 = 120;
  try
  {
    ServiceStatus.dwWaitHint = 0;
    ServiceStatus.dwWin32ExitCode = 0;
    ServiceStatus.dwServiceSpecificExitCode = 0;
    v10 = a2 - 1;
    if ( v10 )
    {
      v11 = v10 - 3;
      if ( !v11 )
      {
        v42 = 0;
        CEcsHostServiceModule::SetServiceStatus(this, ServiceStatus.dwCurrentState, 1);
        goto LABEL_126;
      }
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 6;
        if ( v13 )
        {
          v14 = v13 - 2;
          if ( v14 )
          {
            if ( v14 != 1 )
              goto LABEL_126;
            if ( v5 != 6 )
              goto LABEL_50;
            if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
            {
              WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 29, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
            }
            try
            {
              CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
                (__int64)&lpCriticalSection,
                &stru_1801AF858);
              if ( ptpcg && std::operator!=<CFileDownloadTask>(&::pv) )
              {
                v15 = ::pv;
                ppBuffer = 0;
                pBytesReturned = 0;
                if ( WTSQuerySessionInformationW(0, *((_DWORD *)v4 + 1), WTSSessionInfo, &ppBuffer, &pBytesReturned) )
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
                  {
                    WPP_SF_di(
                      *((_QWORD *)WPP_GLOBAL_Control + 7),
                      30,
                      WPP_152c595f472e31f48642c74f47fa958e_Traceguids,
                      *((unsigned int *)v4 + 1),
                      *((_QWORD *)ppBuffer + 25));
                  }
                  v43 = WTSFreeMemory;
                  std::unique_ptr<_WTSINFOW,void (*)(void *)>::unique_ptr<_WTSINFOW,void (*)(void *)>(
                    v86,
                    ppBuffer,
                    &v43);
                  v16 = operator new(0x18u);
                  v45 = v16;
                  v17 = *((_QWORD *)ppBuffer + 25);
                  v18 = *((_DWORD *)v4 + 1);
                  *(_QWORD *)v16 = v15;
                  v16[2] = v18;
                  *((_QWORD *)v16 + 2) = v17;
                  wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                    &pv,
                    (__int64)v16);
                  ThreadpoolWork = CreateThreadpoolWork(CEcsHostServiceModule::RemoveSessionThreadProc, pv, &pcbe);
                  pwk = 0;
                  EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&pwk, &ThreadpoolWork);
                  if ( !pwk )
                    v8 = 0;
                  if ( !v8 )
                  {
                    HIWORD(v38) = 536;
                    pExceptionObject = EcsGetLastFailureAsHRESULT();
                    throw (long *)&pExceptionObject;
                  }
                  v37 = 0;
                  LOWORD(v38) = 536;
                  SubmitThreadpoolWork(pwk);
                  std::unique_ptr<unsigned char [0]>::release(&pv);
                  v65 = 0;
                  EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&pwk, &v65);
                  std::unique_ptr<RemoveSessionContext>::~unique_ptr<RemoveSessionContext>(&pv);
                  std::unique_ptr<_WTSINFOW,void (*)(void *)>::~unique_ptr<_WTSINFOW,void (*)(void *)>(v86);
                }
                else
                {
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
                  {
                    LastError = GetLastError();
                    WPP_SF_dd(
                      *((_QWORD *)WPP_GLOBAL_Control + 7),
                      31,
                      WPP_152c595f472e31f48642c74f47fa958e_Traceguids,
                      *((unsigned int *)v4 + 1),
                      LastError);
                  }
                  v66 = CreateThreadpoolWork(CEcsHostServiceModule::RemoveClosedSessionsThreadProc, v15, &pcbe);
                  v59 = 0;
                  EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&v59, &v66);
                  if ( !v59 )
                    v8 = 0;
                  if ( !v8 )
                  {
                    HIWORD(v38) = 552;
                    LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
                    throw (long *)&LastFailureAsHRESULT;
                  }
                  v37 = 0;
                  LOWORD(v38) = 552;
                  SubmitThreadpoolWork(v59);
                  v67 = 0;
                  EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&v59, &v67);
                }
              }
              if ( v79 )
              {
                LeaveCriticalSection(lpCriticalSection);
                v79 = 0;
              }
            }
            catch ( long v73 )
            {
              v37 = v73;
            }
            catch ( std::bad_alloc )
            {
              HIWORD(v38) = 557;
              v37 = -2147024882;
            }
            catch ( std::exception )
            {
              HIWORD(v38) = 557;
              v37 = -2147418113;
            }
            catch ( const ATL::CAtlException *v83 )
            {
              HIWORD(v38) = 557;
              v37 = *(_DWORD *)v83;
            }
            v20 = (unsigned int)v37;
            if ( v37 >= 0 )
              goto LABEL_50;
            v21 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
              || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0
              || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
            {
              goto LABEL_50;
            }
            v22 = 32;
            goto LABEL_49;
          }
          if ( v5 == 32787 )
          {
            try
            {
              CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(
                (__int64)&v80,
                &stru_1801AF858);
              if ( ptpcg && std::operator!=<CFileDownloadTask>(&::pv) )
              {
                v23 = *(_QWORD *)v4 - *(_QWORD *)&GUID_CONSOLE_DISPLAY_STATE.Data1;
                if ( *(_QWORD *)v4 == *(_QWORD *)&GUID_CONSOLE_DISPLAY_STATE.Data1 )
                  v23 = *((_QWORD *)v4 + 1) - *(_QWORD *)GUID_CONSOLE_DISPLAY_STATE.Data4;
                if ( !v23 )
                {
                  v24 = (PVOID *)WPP_GLOBAL_Control;
                  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
                    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
                  {
                    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 33, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
                    v24 = (PVOID *)WPP_GLOBAL_Control;
                  }
                  if ( *((_DWORD *)v4 + 5) )
                  {
                    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 68) & 8) != 0 && *((_BYTE *)v24 + 65) >= 4u )
                      WPP_SF_(v24[7], 35, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
                    v70 = CreateThreadpoolWork(CEcsHostServiceModule::DisplayOnWorkThreadProc, ::pv, &pcbe);
                    v61 = 0;
                    EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&v61, &v70);
                    if ( !v61 )
                    {
                      HIWORD(v38) = 610;
                      v50 = EcsGetLastFailureAsHRESULT();
                      throw (long *)&v50;
                    }
                    v37 = 0;
                    LOWORD(v38) = 610;
                    SubmitThreadpoolWork(v61);
                    v71 = 0;
                    EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&v61, &v71);
                  }
                  else
                  {
                    if ( v24 != &WPP_GLOBAL_Control && (*((_BYTE *)v24 + 68) & 8) != 0 && *((_BYTE *)v24 + 65) >= 4u )
                      WPP_SF_(v24[7], 34, WPP_152c595f472e31f48642c74f47fa958e_Traceguids);
                    v68 = CreateThreadpoolWork(CEcsHostServiceModule::DisplayOffWorkThreadProc, ::pv, &pcbe);
                    v60 = 0;
                    EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&v60, &v68);
                    if ( !v60 )
                    {
                      HIWORD(v38) = 600;
                      v49 = EcsGetLastFailureAsHRESULT();
                      throw (long *)&v49;
                    }
                    v37 = 0;
                    LOWORD(v38) = 600;
                    SubmitThreadpoolWork(v60);
                    v69 = 0;
                    EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&v60, &v69);
                  }
                }
              }
              if ( v81 )
              {
                LeaveCriticalSection(v80);
                v81 = 0;
              }
            }
            catch ( long v74 )
            {
              v37 = v74;
              v4 = v43;
              v5 = a3;
              v8 = 1;
            }
            catch ( std::bad_alloc )
            {
              HIWORD(v38) = 617;
              v37 = -2147024882;
              v4 = v43;
              v5 = a3;
              v8 = 1;
            }
            catch ( std::exception )
            {
              HIWORD(v38) = 617;
              v37 = -2147418113;
              v4 = v43;
              v5 = a3;
              v8 = 1;
            }
            catch ( const ATL::CAtlException *v85 )
            {
              HIWORD(v38) = 617;
              v37 = *(_DWORD *)v85;
              v4 = v43;
              v5 = a3;
              v8 = 1;
            }
            if ( v37 < 0
              && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
              && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
              && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
            {
              WPP_SF_d(
                *((_QWORD *)WPP_GLOBAL_Control + 7),
                36,
                WPP_152c595f472e31f48642c74f47fa958e_Traceguids,
                (unsigned int)v37);
            }
          }
          v42 = 0;
        }
        if ( ((v5 - 0x8000) & 0xFFFFFFFB) != 0 )
          goto LABEL_50;
        try
        {
          CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>((__int64)&v76, &stru_1801AF858);
          if ( ptpcg && std::operator!=<CFileDownloadTask>(&::pv) && *((_DWORD *)v4 + 1) == 5 )
          {
            v25 = *(_QWORD *)((char *)v4 + 12) - *(_QWORD *)&GUID_DEVINTERFACE_VOLUME.Data1;
            if ( !v25 )
              v25 = *(_QWORD *)((char *)v4 + 20) - *(_QWORD *)GUID_DEVINTERFACE_VOLUME.Data4;
            if ( !v25 )
            {
              v26 = ::pv;
              std::wstring::wstring((__int64)v90, (__int64)v4 + 28);
              if ( v5 == 0x8000 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
                {
                  v27 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
                  WPP_SF_S(*(_QWORD *)(v28 + 56), 37, WPP_152c595f472e31f48642c74f47fa958e_Traceguids, v27);
                }
                v29 = operator new(0x28u);
                v45 = v29;
                v63 = (PTP_WORK)v88;
                v30 = std::wstring::wstring((__int64)v88);
                v62 = v30;
                *v29 = v26;
                std::wstring::wstring((__int64)(v29 + 1));
                std::wstring::~wstring(v30);
                wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                  &v54,
                  (__int64)v29);
                v72 = CreateThreadpoolWork(CEcsHostServiceModule::VolumeArrivalThreadProc, v54, &pcbe);
                v53 = 0;
                EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&v53, &v72);
                if ( !v53 )
                  v8 = 0;
                if ( !v8 )
                {
                  HIWORD(v38) = 660;
                  v51 = EcsGetLastFailureAsHRESULT();
                  throw (long *)&v51;
                }
                v37 = 0;
                LOWORD(v38) = 660;
                SubmitThreadpoolWork(v53);
                std::unique_ptr<unsigned char [0]>::release(&v54);
                v62 = 0;
                EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&v53, &v62);
                std::unique_ptr<VolumeRemovalContext>::~unique_ptr<VolumeRemovalContext>(&v54);
              }
              else if ( v5 == 32772 )
              {
                if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
                  && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
                  && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
                {
                  v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v90);
                  WPP_SF_S(*(_QWORD *)(v32 + 56), 38, WPP_152c595f472e31f48642c74f47fa958e_Traceguids, v31);
                }
                v33 = operator new(0x28u);
                v45 = v33;
                v63 = (PTP_WORK)v89;
                v34 = std::wstring::wstring((__int64)v89);
                v62 = v34;
                *v33 = v26;
                std::wstring::wstring((__int64)(v33 + 1));
                std::wstring::~wstring(v34);
                wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                  &v56,
                  (__int64)v33);
                v63 = CreateThreadpoolWork(CEcsHostServiceModule::VolumeRemovalThreadProc, v56, &pcbe);
                v55 = 0;
                EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&v55, &v63);
                if ( !v55 )
                  v8 = 0;
                if ( !v8 )
                {
                  HIWORD(v38) = 672;
                  v52 = EcsGetLastFailureAsHRESULT();
                  throw (long *)&v52;
                }
                v37 = 0;
                LOWORD(v38) = 672;
                SubmitThreadpoolWork(v55);
                std::unique_ptr<unsigned char [0]>::release(&v56);
                v45 = 0;
                EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(&v55, &v45);
                std::unique_ptr<VolumeRemovalContext>::~unique_ptr<VolumeRemovalContext>(&v56);
              }
              std::wstring::~wstring((__int64)v90);
            }
          }
          if ( v77 )
          {
            LeaveCriticalSection(v76);
            v77 = 0;
          }
        }
        catch ( long v75 )
        {
          v37 = v75;
        }
        catch ( std::bad_alloc )
        {
          HIWORD(v38) = 679;
          v37 = -2147024882;
        }
        catch ( std::exception )
        {
          HIWORD(v38) = 679;
          v37 = -2147418113;
        }
        catch ( const ATL::CAtlException *v84 )
        {
          HIWORD(v38) = 679;
          v37 = *(_DWORD *)v84;
        }
        v20 = (unsigned int)v37;
        if ( v37 >= 0 )
          goto LABEL_50;
        v21 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0
          || *((_BYTE *)WPP_GLOBAL_Control + 65) < 2u )
        {
          goto LABEL_50;
        }
        v22 = 39;
LABEL_49:
        WPP_SF_d(v21[7], v22, WPP_152c595f472e31f48642c74f47fa958e_Traceguids, v20);
LABEL_50:
        v42 = 0;
        goto LABEL_126;
      }
    }
    v42 = 0;
    CEcsHostServiceModule::SetServiceStatus(this, 3u, 1);
    CEcsHostServiceModule::SignalShutdown(v35);
  }
  catch ( long v82 )
  {
    v37 = v82;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v38) = 692;
    v37 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v38) = 692;
    v37 = -2147418113;
  }
  catch ( const ATL::CAtlException *v87 )
  {
    HIWORD(v38) = 692;
    v37 = *(_DWORD *)v87;
  }
LABEL_126:
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v37);
  return v42;
}

```

## disassembly

```asm
0x18000bf68  mov     [rsp+arg_0], rbx
0x18000bf6d  mov     [rsp+arg_8], rsi
0x18000bf72  mov     [rsp+arg_10], r8d
0x18000bf77  push    rdi
0x18000bf78  push    r12
0x18000bf7a  push    r13
0x18000bf7c  push    r14
0x18000bf7e  push    r15
0x18000bf80  sub     rsp, 210h
0x18000bf87  mov     rax, cs:__security_cookie
0x18000bf8e  xor     rax, rsp
0x18000bf91  mov     [rsp+238h+var_30], rax
0x18000bf99  mov     rsi, r9
0x18000bf9c  mov     r13d, r8d
0x18000bf9f  mov     edi, edx
0x18000bfa1  mov     [rsp+238h+var_1E0], r9
0x18000bfa6  lea     r12, WPP_GLOBAL_Control
0x18000bfad  mov     rax, cs:WPP_GLOBAL_Control
0x18000bfb4  cmp     rax, r12
0x18000bfb7  jz      short loc_18000BFE1
0x18000bfb9  test    byte ptr [rax+44h], 8
0x18000bfbd  jz      short loc_18000BFFA
0x18000bfbf  cmp     byte ptr [rax+41h], 6
0x18000bfc3  jb      short loc_18000BFE1
0x18000bfc5  mov     edx, 1Ch
0x18000bfca  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000bfd1  mov     rcx, [rax+38h]
0x18000bfd5  call    WPP_SF_
0x18000bfda  mov     rax, cs:WPP_GLOBAL_Control
0x18000bfe1  test    byte ptr [rax+44h], 8
0x18000bfe5  jz      short loc_18000BFFA
0x18000bfe7  cmp     byte ptr [rax+41h], 6
0x18000bfeb  jb      short loc_18000BFFA
0x18000bfed  mov     r15d, 1
0x18000bff3  mov     al, r15b
0x18000bff6  xor     ebx, ebx
0x18000bff8  jmp     short loc_18000C002
0x18000bffa  xor     ebx, ebx
0x18000bffc  mov     al, bl
0x18000bffe  lea     r15d, [rbx+1]
0x18000c002  mov     [rsp+238h+var_208], ebx
0x18000c006  mov     [rsp+238h+var_204], 1BCh
0x18000c00e  mov     [rsp+238h+var_200], al
0x18000c012  lea     rax, aCecshostservic_3; "CEcsHostServiceModule::Handler"
0x18000c019  mov     [rsp+238h+var_1F8], rax
0x18000c01e  mov     [rsp+238h+var_1F0], rbx
0x18000c023  mov     [rsp+238h+var_1E8], 78h ; 'x'
0x18000c02b  mov     cs:ServiceStatus.dwWaitHint, ebx
0x18000c031  mov     cs:ServiceStatus.dwWin32ExitCode, ebx
0x18000c037  mov     cs:ServiceStatus.dwServiceSpecificExitCode, ebx
0x18000c03d  sub     edi, 1
0x18000c040  jz      loc_18000CB68
0x18000c046  sub     edi, 3
0x18000c049  jz      loc_18000CB54
0x18000c04f  sub     edi, 1
0x18000c052  jz      loc_18000CB68
0x18000c058  sub     edi, 6
0x18000c05b  jz      loc_18000C706
0x18000c061  sub     edi, 2
0x18000c064  jz      loc_18000C412
0x18000c06a  cmp     edi, 1
0x18000c06d  jnz     loc_18000CB7F
0x18000c073  cmp     r13d, 6
0x18000c077  jnz     loc_18000C409
0x18000c07d  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c084  cmp     rcx, r12
0x18000c087  jz      short loc_18000C0A9
0x18000c089  test    byte ptr [rcx+44h], 8
0x18000c08d  jz      short loc_18000C0A9
0x18000c08f  cmp     byte ptr [rcx+41h], 4
0x18000c093  jb      short loc_18000C0A9
0x18000c095  lea     edx, [rdi+1Ch]
0x18000c098  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000c09f  mov     rcx, [rcx+38h]
0x18000c0a3  call    WPP_SF_
0x18000c0a8  nop
0x18000c0a9  lea     rdx, stru_1801AF858
0x18000c0b0  lea     rcx, [rsp+238h+lpCriticalSection]
0x18000c0b8  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18000c0bd  nop
0x18000c0be  cmp     cs:ptpcg, rbx
0x18000c0c5  jz      short loc_18000C0CC
0x18000c0c7  mov     al, r15b
0x18000c0ca  jmp     short loc_18000C0CE
0x18000c0cc  mov     al, bl
0x18000c0ce  test    al, al
0x18000c0d0  jz      loc_18000C3A3
0x18000c0d6  lea     rcx, pv
0x18000c0dd  call    ??$?9VCFileDownloadTask@@@std@@YA_NAEBV?$shared_ptr@VCFileDownloadTask@@@0@$$T@Z; std::operator!=<CFileDownloadTask>(std::shared_ptr<CFileDownloadTask> const &,std::nullptr_t)
0x18000c0e2  test    al, al
0x18000c0e4  jz      loc_18000C3A3
0x18000c0ea  mov     rdi, cs:pv
0x18000c0f1  mov     [rsp+238h+ppBuffer], rbx
0x18000c0f6  mov     [rsp+238h+var_1C8], ebx
0x18000c0fa  lea     rax, [rsp+238h+var_1C8]
0x18000c0ff  mov     [rsp+238h+pBytesReturned], rax; pBytesReturned
0x18000c104  lea     r9, [rsp+238h+ppBuffer]; ppBuffer
0x18000c109  mov     r14d, 18h
0x18000c10f  mov     r8d, r14d; WTSInfoClass
0x18000c112  mov     edx, [rsi+4]; SessionId
0x18000c115  xor     ecx, ecx; hServer
0x18000c117  call    cs:__imp_WTSQuerySessionInformationW
0x18000c11d  test    eax, eax
0x18000c11f  jz      loc_18000C2AA
0x18000c125  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c12c  cmp     rcx, r12
0x18000c12f  jz      short loc_18000C166
0x18000c131  test    byte ptr [rcx+44h], 8
0x18000c135  jz      short loc_18000C166
0x18000c137  cmp     byte ptr [rcx+41h], 4
0x18000c13b  jb      short loc_18000C166
0x18000c13d  lea     edx, [r14+6]
0x18000c141  mov     rax, [rsp+238h+ppBuffer]
0x18000c146  mov     r8, [rax+0C8h]
0x18000c14d  mov     [rsp+238h+pBytesReturned], r8
0x18000c152  mov     r9d, [rsi+4]
0x18000c156  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000c15d  mov     rcx, [rcx+38h]
0x18000c161  call    WPP_SF_di
0x18000c166  mov     rax, cs:__imp_WTSFreeMemory
0x18000c16d  mov     [rsp+238h+var_1E0], rax
0x18000c172  lea     r8, [rsp+238h+var_1E0]
0x18000c177  mov     rdx, [rsp+238h+ppBuffer]
0x18000c17c  lea     rcx, [rsp+238h+var_A8]
0x18000c184  call    ??$?0P6AXPEAX@Z$0A@@?$unique_ptr@U_WTSINFOW@@P6AXPEAX@Z@std@@QEAA@PEAU_WTSINFOW@@$$QEAP6AXPEAX@Z@Z; std::unique_ptr<_WTSINFOW,void (*)(void *)>::unique_ptr<_WTSINFOW,void (*)(void *)>(_WTSINFOW *,void (*&&)(void *))
0x18000c189  nop
0x18000c18a  mov     rcx, r14; Size
0x18000c18d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000c192  mov     [rsp+238h+var_1D0], rax
0x18000c197  mov     rcx, [rsp+238h+ppBuffer]
0x18000c19c  mov     rdx, [rcx+0C8h]
0x18000c1a3  mov     ecx, [rsi+4]
0x18000c1a6  mov     [rax], rdi
0x18000c1a9  mov     [rax+8], ecx
0x18000c1ac  mov     [rax+10h], rdx
0x18000c1b0  mov     rdx, rax
0x18000c1b3  lea     rcx, [rsp+238h+pv]
0x18000c1bb  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18000c1c0  nop
0x18000c1c1  lea     r8, pcbe; pcbe
0x18000c1c8  mov     rdx, [rsp+238h+pv]; pv
0x18000c1d0  lea     rcx, ?RemoveSessionThreadProc@CEcsHostServiceModule@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000c1d7  call    cs:__imp_CreateThreadpoolWork
0x18000c1dd  mov     [rsp+238h+var_150], rax
0x18000c1e5  mov     [rsp+238h+pwk], rbx
0x18000c1ed  lea     rdx, [rsp+238h+var_150]
0x18000c1f5  lea     rcx, [rsp+238h+pwk]
0x18000c1fd  call    ?reset@?$EcsUniqueHandle@PEAU_TP_WORK@@UWin32ThreadPoolWorkDeleter@@$0A@@@QEAAXAEBQEAU_TP_WORK@@@Z; EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(_TP_WORK * const &)
0x18000c202  nop
0x18000c203  mov     eax, [rsp+238h+var_208]
0x18000c207  mov     [rsp+238h+var_208], eax
0x18000c20b  mov     rcx, [rsp+238h+pwk]; pwk
0x18000c213  test    rcx, rcx
0x18000c216  jz      short loc_18000C21A
0x18000c218  jmp     short loc_18000C21D
0x18000c21a  mov     r15d, ebx
0x18000c21d  test    r15d, r15d
0x18000c220  jnz     short loc_18000C24A
0x18000c222  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18000c227  mov     [rsp+238h+var_208], eax
0x18000c22b  mov     edx, 218h
0x18000c230  mov     word ptr [rsp+238h+var_204+2], dx
0x18000c235  mov     [rsp+238h+pExceptionObject], eax
0x18000c239  lea     rdx, _TI1J; pThrowInfo
0x18000c240  lea     rcx, [rsp+238h+pExceptionObject]; pExceptionObject
0x18000c245  call    _CxxThrowException_0
0x18000c24a  mov     [rsp+238h+var_208], ebx
0x18000c24e  mov     edx, 218h
0x18000c253  mov     word ptr [rsp+238h+var_204], dx
0x18000c258  call    cs:__imp_SubmitThreadpoolWork
0x18000c25e  lea     rcx, [rsp+238h+pv]
0x18000c266  call    ?release@?$unique_ptr@$$BY0A@EU?$default_delete@$$BY0A@E@std@@@std@@QEAAPEAEXZ; std::unique_ptr<uchar [0]>::release(void)
0x18000c26b  nop
0x18000c26c  mov     [rsp+238h+var_148], rbx
0x18000c274  lea     rdx, [rsp+238h+var_148]
0x18000c27c  lea     rcx, [rsp+238h+pwk]
0x18000c284  call    ?reset@?$EcsUniqueHandle@PEAU_TP_WORK@@UWin32ThreadPoolWorkDeleter@@$0A@@@QEAAXAEBQEAU_TP_WORK@@@Z; EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(_TP_WORK * const &)
0x18000c289  nop
0x18000c28a  lea     rcx, [rsp+238h+pv]
0x18000c292  call    ??1?$unique_ptr@URemoveSessionContext@@U?$default_delete@URemoveSessionContext@@@std@@@std@@QEAA@XZ; std::unique_ptr<RemoveSessionContext>::~unique_ptr<RemoveSessionContext>(void)
0x18000c297  nop
0x18000c298  lea     rcx, [rsp+238h+var_A8]
0x18000c2a0  call    ??1?$unique_ptr@U_WTSINFOW@@P6AXPEAX@Z@std@@QEAA@XZ; std::unique_ptr<_WTSINFOW,void (*)(void *)>::~unique_ptr<_WTSINFOW,void (*)(void *)>(void)
0x18000c2a5  jmp     loc_18000C3A3
0x18000c2aa  mov     rax, cs:WPP_GLOBAL_Control
0x18000c2b1  cmp     rax, r12
0x18000c2b4  jz      short loc_18000C2EC
0x18000c2b6  test    byte ptr [rax+44h], 8
0x18000c2ba  jz      short loc_18000C2EC
0x18000c2bc  cmp     byte ptr [rax+41h], 4
0x18000c2c0  jb      short loc_18000C2EC
0x18000c2c2  call    cs:__imp_GetLastError
0x18000c2c8  mov     edx, 1Fh
0x18000c2cd  mov     dword ptr [rsp+238h+pBytesReturned], eax
0x18000c2d1  mov     r9d, [rsi+4]
0x18000c2d5  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000c2dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c2e3  mov     rcx, [rcx+38h]
0x18000c2e7  call    WPP_SF_dd
0x18000c2ec  lea     r8, pcbe; pcbe
0x18000c2f3  mov     rdx, rdi; pv
0x18000c2f6  lea     rcx, ?RemoveClosedSessionsThreadProc@CEcsHostServiceModule@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18000c2fd  call    cs:__imp_CreateThreadpoolWork
0x18000c303  mov     [rsp+238h+var_140], rax
0x18000c30b  mov     [rsp+238h+var_178], rbx
0x18000c313  lea     rdx, [rsp+238h+var_140]
0x18000c31b  lea     rcx, [rsp+238h+var_178]
0x18000c323  call    ?reset@?$EcsUniqueHandle@PEAU_TP_WORK@@UWin32ThreadPoolWorkDeleter@@$0A@@@QEAAXAEBQEAU_TP_WORK@@@Z; EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(_TP_WORK * const &)
0x18000c328  nop
0x18000c329  mov     eax, [rsp+238h+var_208]
0x18000c32d  mov     [rsp+238h+var_208], eax
0x18000c331  mov     rcx, [rsp+238h+var_178]; pwk
0x18000c339  test    rcx, rcx
0x18000c33c  jz      short loc_18000C340
0x18000c33e  jmp     short loc_18000C343
0x18000c340  mov     r15d, ebx
0x18000c343  test    r15d, r15d
0x18000c346  jnz     short loc_18000C370
0x18000c348  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x18000c34d  mov     [rsp+238h+var_208], eax
0x18000c351  mov     edx, 228h
0x18000c356  mov     word ptr [rsp+238h+var_204+2], dx
0x18000c35b  mov     [rsp+238h+var_1C0], eax
0x18000c35f  lea     rdx, _TI1J; pThrowInfo
0x18000c366  lea     rcx, [rsp+238h+var_1C0]; pExceptionObject
0x18000c36b  call    _CxxThrowException_0
0x18000c370  mov     [rsp+238h+var_208], ebx
0x18000c374  mov     edx, 228h
0x18000c379  mov     word ptr [rsp+238h+var_204], dx
0x18000c37e  call    cs:__imp_SubmitThreadpoolWork
0x18000c384  nop
0x18000c385  mov     [rsp+238h+var_138], rbx
0x18000c38d  lea     rdx, [rsp+238h+var_138]
0x18000c395  lea     rcx, [rsp+238h+var_178]
0x18000c39d  call    ?reset@?$EcsUniqueHandle@PEAU_TP_WORK@@UWin32ThreadPoolWorkDeleter@@$0A@@@QEAAXAEBQEAU_TP_WORK@@@Z; EcsUniqueHandle<_TP_WORK *,Win32ThreadPoolWorkDeleter,0>::reset(_TP_WORK * const &)
0x18000c3a2  nop
0x18000c3a3  cmp     [rsp+238h+var_E0], bl
0x18000c3aa  jz      short loc_18000C3C1
0x18000c3ac  mov     rcx, [rsp+238h+lpCriticalSection]; lpCriticalSection
0x18000c3b4  call    cs:__imp_LeaveCriticalSection
0x18000c3ba  mov     [rsp+238h+var_E0], bl
0x18000c3c1  jmp     short loc_18000C3D2
0x18000c3c3  jmp     short loc_18000C3C9
0x18000c3c5  jmp     short loc_18000C3C9
0x18000c3c7  jmp     short $+2
0x18000c3c9  xor     ebx, ebx
0x18000c3cb  lea     r12, WPP_GLOBAL_Control
0x18000c3d2  mov     r9d, [rsp+238h+var_208]
0x18000c3d7  test    r9d, r9d
0x18000c3da  jns     short loc_18000C409
0x18000c3dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c3e3  cmp     rcx, r12
0x18000c3e6  jz      short loc_18000C409
0x18000c3e8  test    byte ptr [rcx+44h], 8
0x18000c3ec  jz      short loc_18000C409
0x18000c3ee  cmp     byte ptr [rcx+41h], 2
0x18000c3f2  jb      short loc_18000C409
0x18000c3f4  mov     edx, 20h ; ' '
0x18000c3f9  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000c400  mov     rcx, [rcx+38h]
0x18000c404  call    WPP_SF_d
0x18000c409  mov     [rsp+238h+var_1E8], ebx
0x18000c40d  jmp     loc_18000CB7F
0x18000c412  cmp     r13d, 8013h
0x18000c419  jnz     loc_18000C702
0x18000c41f  lea     rdx, stru_1801AF858
0x18000c426  lea     rcx, [rsp+238h+var_D8]
0x18000c42e  call    ??0?$CEcsExclusiveLock@VCEcsCriticalSection@@@@QEAA@AEAVCEcsCriticalSection@@_N@Z; CEcsExclusiveLock<CEcsCriticalSection>::CEcsExclusiveLock<CEcsCriticalSection>(CEcsCriticalSection &,bool)
0x18000c433  nop
0x18000c434  cmp     cs:ptpcg, rbx
0x18000c43b  jz      short loc_18000C442
0x18000c43d  mov     al, r15b
0x18000c440  jmp     short loc_18000C444
0x18000c442  mov     al, bl
0x18000c444  test    al, al
0x18000c446  jz      loc_18000C689
0x18000c44c  lea     rcx, pv
0x18000c453  call    ??$?9VCFileDownloadTask@@@std@@YA_NAEBV?$shared_ptr@VCFileDownloadTask@@@0@$$T@Z; std::operator!=<CFileDownloadTask>(std::shared_ptr<CFileDownloadTask> const &,std::nullptr_t)
0x18000c458  test    al, al
0x18000c45a  jz      loc_18000C689
0x18000c460  mov     rax, [rsi]
0x18000c463  sub     rax, qword ptr cs:GUID_CONSOLE_DISPLAY_STATE.Data1
0x18000c46a  jnz     short loc_18000C477
0x18000c46c  mov     rax, [rsi+8]
0x18000c470  sub     rax, qword ptr cs:GUID_CONSOLE_DISPLAY_STATE.Data4
0x18000c477  test    rax, rax
0x18000c47a  jnz     loc_18000C689
0x18000c480  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c487  cmp     rcx, r12
0x18000c48a  jz      short loc_18000C4B2
0x18000c48c  test    byte ptr [rcx+44h], 8
0x18000c490  jz      short loc_18000C4B2
0x18000c492  cmp     byte ptr [rcx+41h], 4
0x18000c496  jb      short loc_18000C4B2
0x18000c498  lea     edx, [rax+21h]
0x18000c49b  lea     r8, WPP_152c595f472e31f48642c74f47fa958e_Traceguids
0x18000c4a2  mov     rcx, [rcx+38h]
0x18000c4a6  call    WPP_SF_
0x18000c4ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18000c4b2  cmp     [rsi+14h], ebx
  ... truncated ...
```
