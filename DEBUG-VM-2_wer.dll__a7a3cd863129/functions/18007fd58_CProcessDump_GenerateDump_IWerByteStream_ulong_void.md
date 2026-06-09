# CProcessDump::GenerateDump(IWerByteStream *,ulong,void *)

- ea: `0x18007fd58`
- end: `0x1800813cb`
- name: `?GenerateDump@CProcessDump@@AEAAJPEAUIWerByteStream@@KPEAX@Z`
- size: `5747`
- prototype: `__int64 __fastcall(CProcessDump *__hidden this, struct IWerByteStream *, unsigned int, void *)`
- caller_count: `2`
- callee_count: `31`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18007f818`
- `0x180081ef0`

## callees

- `0x18000193c`
- `0x18000716c`
- `0x180007db4`
- `0x180007de0`
- `0x180009ad4`
- `0x18000c390`
- `0x18000dad0`
- `0x1800144f0`
- `0x18001f458`
- `0x18001fe24`
- `0x1800241a0`
- `0x18002c95c`
- `0x1800303dc`
- `0x1800306e4`
- `0x180036cb0`
- `0x18003bf14`
- `0x180045bdc`
- `0x18004c8ec`
- `0x180050db0`
- `0x1800517cc`
- `0x180051efc`
- `0x180051fa4`
- `0x18007fd58`
- `0x180081b60`
- `0x180082150`
- `0x180095730`
- `0x18009589c`
- `0x180095c60`
- `0x180095d9c`
- `0x18009d1f8`
- `0x1800ac010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008062d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080672`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080b95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080be0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18008062d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080672`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080b95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180080be0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800803a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080442`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008047f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800804d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008068b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080a95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180081250`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180081261`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080393`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800803a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080442`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008047f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1800804d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18008068b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180080a95`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180081250`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180081261`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800803b4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180080450`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008126f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1800803b4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x180080450`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18008126f`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18008039c`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18008039c`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180080a8f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceFrequency` at `0x180080a8f`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800806a8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180080a85`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x1800806a8`
- `api-ms-win-core-profile-l1-1-0!QueryPerformanceCounter` at `0x180080a85`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800806cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800806dd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800806cb`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1800806dd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800803be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008045e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080861`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800803be`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008045e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080861`
- `ntdll!NtSetInformationThread` at `0x180080499`
- `ntdll!NtSetInformationThread` at `0x180080499`
- `ntdll!RtlEnableThreadProfiling` at `0x1800804e5`
- `ntdll!RtlEnableThreadProfiling` at `0x1800804e5`
- `ntdll!RtlReadThreadProfilingData` at `0x180080b72`
- `ntdll!RtlReadThreadProfilingData` at `0x180080b72`
- `ntdll!RtlDisableThreadProfiling` at `0x180080b7f`
- `ntdll!RtlDisableThreadProfiling` at `0x180080b7f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800811d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800811d0`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800806d7`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800806d7`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800811be`
- `api-ms-win-core-memory-l1-1-0!UnmapViewOfFile` at `0x1800811be`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180080415`
- `api-ms-win-core-processsnapshot-l1-1-0!PssQuerySnapshot` at `0x180080415`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080643`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080662`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080bf6`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080c25`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080643`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080662`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080bf6`
- `api-ms-win-core-psapi-l1-1-0!K32GetProcessMemoryInfo` at `0x180080c25`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18008069b`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180080aa5`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x18008069b`
- `api-ms-win-core-realtime-l1-1-0!QueryThreadCycleTime` at `0x180080aa5`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x180080682`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x180080ba5`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x180080682`
- `api-ms-win-core-processtopology-obsolete-l1-1-0!GetProcessIoCounters` at `0x180080ba5`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080813`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x18008087b`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080eea`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080f7c`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080fad`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080fe3`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080813`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x18008087b`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080eea`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080f7c`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080fad`
- `ext-ms-win-wer-xbox-l1-2-0!XerProgressCallback` at `0x180080fe3`
- `dbghelp!MiniDumpWriteDump` at `0x180080850`
- `dbghelp!MiniDumpWriteDump` at `0x180080850`

## string_xrefs

- `0x18008007f`: `\\?\Wer:\Temp`
- `0x180080f0a`: `\\?\Wer:\Temp`
- `0x1800802f4`: `Failed to create memory-mapped stream for unencrypted dump: %08X.`
- `0x180080338`: `Failed to create temporary file for unencrypted dump: %08X.`
- `0x180080379`: `Failed to create transient file for dump: %08X.`
- `0x1800803d3`: `Failed to set debug thread priority %d: HRESULT %08X.`
- `0x1800804f9`: `Failed to enable thread profiling: Win32 error %u.`
- `0x180080c63`: `MiniDumpWriteDump took:\n- Ticks     : %14u ms.\n- Cycles    : %14I64u.`
- `0x180080d88`: `MiniDumpWriteDump I/O counters:\n- Reads     : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\n- Writes    : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\n- Other     : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\n`
- `0x180080e07`: `MiniDumpWriteDump read memory failures: %u.\n`
- `0x180080e39`: `Write buffer:\n- Buffer size           : %u bytes.\n- Flushes (full+partial): %u + %u.\n`
- `0x180080e47`: `Write buffer disabled.\n`
- `0x180080e83`: `MiniDumpWriteDump failed: %08X.`
- `0x180080f26`: `Failed to create temporary file for encrypted dump: %08X.`
- `0x180080ff5`: `Failed to copy encrypted dump: %08X.`
- `0x180081195`: `Failed to copy transient dump: %08X.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall CProcessDump::GenerateDump(CProcessDump *this, struct IWerByteStream *a2, unsigned int a3, void *a4)
{
  char v4; // r13
  int v7; // r14d
  int v8; // esi
  BOOL v9; // ebx
  unsigned int v10; // eax
  char v11; // di
  int v12; // eax
  signed int v13; // r12d
  int v14; // ecx
  int v15; // r13d
  MINIDUMP_TYPE v16; // r13d
  _QWORD *v17; // rbx
  unsigned int (__fastcall *v18)(_QWORD, _QWORD **); // rdi
  BOOL v19; // esi
  unsigned int v20; // edi
  int v21; // eax
  int New; // eax
  int v23; // eax
  HANDLE v24; // rax
  int v25; // ebx
  HANDLE v26; // rax
  DWORD v27; // eax
  void *v28; // r14
  HANDLE v29; // rbx
  HANDLE CurrentThread; // rax
  DWORD LastError; // eax
  unsigned int v32; // eax
  HANDLE v33; // rax
  NTSTATUS v34; // eax
  HANDLE v35; // rax
  unsigned int v36; // eax
  HANDLE CurrentProcess; // rax
  HANDLE v38; // rax
  HANDLE v39; // rax
  DWORD TickCount; // ebx
  DWORD v41; // eax
  void ***v42; // rdi
  struct IWerByteStream *p_hFile; // rbx
  int v44; // eax
  BOOL v45; // ebx
  __int64 v46; // rcx
  int FinalPathByHandle; // eax
  int v48; // edx
  int v49; // r8d
  int v50; // ecx
  int v51; // r9d
  HANDLE v52; // rax
  __int16 *v53; // rax
  _OWORD *v54; // rcx
  __int64 v55; // rdx
  __int64 v56; // r8
  __int64 v57; // rcx
  int v58; // r14d
  BOOL v59; // edi
  HANDLE v60; // rax
  HANDLE v61; // rax
  HANDLE v62; // rbx
  unsigned __int64 v63; // r13
  __int64 v64; // rdx
  __int64 v65; // rcx
  __int64 v66; // r8
  ULONGLONG v67; // r14
  ULONGLONG v68; // rsi
  ULONGLONG v69; // rdi
  ULONGLONG v70; // rbx
  ULONGLONG v71; // r11
  ULONGLONG v72; // r10
  unsigned int v73; // r13d
  __int64 v74; // rdx
  __int64 v75; // rcx
  __int64 v76; // r8
  __int64 v77; // r9
  const wchar_t *v78; // r8
  int v79; // eax
  int v80; // eax
  __int64 v81; // rbx
  int v82; // eax
  int v83; // eax
  void ***v84; // rcx
  int v85; // eax
  int v86; // eax
  __int64 v87; // rdx
  __int64 v88; // rcx
  __int64 v89; // r8
  int v90; // ebx
  HANDLE v91; // rax
  int v92; // edx
  _QWORD *v93; // rbx
  void (__fastcall *v94)(_QWORD, _QWORD **); // rdi
  PMINIDUMP_EXCEPTION_INFORMATION ExceptionParam; // [rsp+20h] [rbp-E0h]
  PMINIDUMP_EXCEPTION_INFORMATION ExceptionParama; // [rsp+20h] [rbp-E0h]
  PMINIDUMP_USER_STREAM_INFORMATION UserStreamParam; // [rsp+28h] [rbp-D8h]
  unsigned int v99; // [rsp+60h] [rbp-A0h]
  char v100; // [rsp+64h] [rbp-9Ch]
  int v101; // [rsp+68h] [rbp-98h]
  BOOL v102; // [rsp+6Ch] [rbp-94h]
  BOOL v103; // [rsp+70h] [rbp-90h]
  BOOL ProcessMemoryInfo; // [rsp+74h] [rbp-8Ch]
  int v105; // [rsp+78h] [rbp-88h]
  BOOL v106; // [rsp+7Ch] [rbp-84h]
  void **v107; // [rsp+80h] [rbp-80h] BYREF
  struct IWerByteStream *v108; // [rsp+88h] [rbp-78h]
  int v109; // [rsp+90h] [rbp-70h]
  unsigned int v110; // [rsp+94h] [rbp-6Ch]
  int ThreadPriority; // [rsp+98h] [rbp-68h]
  __int64 v112; // [rsp+A0h] [rbp-60h] BYREF
  LARGE_INTEGER Frequency; // [rsp+A8h] [rbp-58h] BYREF
  struct IWerByteStream *v114; // [rsp+B0h] [rbp-50h]
  void **v115; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v116; // [rsp+C0h] [rbp-40h]
  void **v117; // [rsp+C8h] [rbp-38h] BYREF
  struct IWerByteStream *v118; // [rsp+D0h] [rbp-30h]
  MINIDUMP_TYPE v119; // [rsp+D8h] [rbp-28h] BYREF
  signed int v120; // [rsp+DCh] [rbp-24h] BYREF
  BOOL ProcessIoCounters; // [rsp+E0h] [rbp-20h]
  HANDLE v122; // [rsp+E8h] [rbp-18h]
  __int64 v123; // [rsp+F0h] [rbp-10h] BYREF
  CProcessDump *v124; // [rsp+F8h] [rbp-8h]
  __int64 v125; // [rsp+100h] [rbp+0h]
  char v126; // [rsp+108h] [rbp+8h]
  __int128 v127; // [rsp+110h] [rbp+10h] BYREF
  __int128 v128; // [rsp+120h] [rbp+20h]
  __int128 v129; // [rsp+130h] [rbp+30h]
  __int128 v130; // [rsp+140h] [rbp+40h]
  __int128 v131; // [rsp+150h] [rbp+50h]
  __int128 v132; // [rsp+160h] [rbp+60h]
  __int128 v133; // [rsp+170h] [rbp+70h]
  _QWORD *v134; // [rsp+180h] [rbp+80h] BYREF
  int v135; // [rsp+188h] [rbp+88h]
  int v136; // [rsp+18Ch] [rbp+8Ch]
  __int128 v137; // [rsp+190h] [rbp+90h]
  __int128 v138; // [rsp+1A0h] [rbp+A0h]
  __int128 v139; // [rsp+1B0h] [rbp+B0h]
  __int128 v140; // [rsp+1C0h] [rbp+C0h]
  __int128 v141; // [rsp+1D0h] [rbp+D0h]
  __int128 v142; // [rsp+1E0h] [rbp+E0h]
  CProcessDump *v143; // [rsp+1F0h] [rbp+F0h]
  LARGE_INTEGER v144; // [rsp+1F8h] [rbp+F8h] BYREF
  HANDLE Process; // [rsp+200h] [rbp+100h] BYREF
  LARGE_INTEGER PerformanceCount; // [rsp+208h] [rbp+108h] BYREF
  unsigned __int64 v147; // [rsp+210h] [rbp+110h] BYREF
  unsigned __int64 CycleTime; // [rsp+218h] [rbp+118h] BYREF
  HANDLE v149; // [rsp+220h] [rbp+120h]
  __int128 v150; // [rsp+228h] [rbp+128h] BYREF
  _QWORD v151[2]; // [rsp+238h] [rbp+138h] BYREF
  __int64 v152[2]; // [rsp+248h] [rbp+148h] BYREF
  _WORD v153[8]; // [rsp+258h] [rbp+158h] BYREF
  _QWORD v154[2]; // [rsp+268h] [rbp+168h] BYREF
  _WORD v155[8]; // [rsp+278h] [rbp+178h] BYREF
  __int64 v156; // [rsp+288h] [rbp+188h] BYREF
  struct _MINIDUMP_CALLBACK_INFORMATION CallbackParam; // [rsp+290h] [rbp+190h] BYREF
  __int64 v158; // [rsp+2A0h] [rbp+1A0h] BYREF
  __int64 v159; // [rsp+2A8h] [rbp+1A8h] BYREF
  HANDLE hObject[2]; // [rsp+2B0h] [rbp+1B0h] BYREF
  __int128 v161; // [rsp+2C0h] [rbp+1C0h]
  __int128 v162; // [rsp+2D0h] [rbp+1D0h]
  LPCVOID lpBaseAddress[2]; // [rsp+2E0h] [rbp+1E0h]
  __int128 v164; // [rsp+2F0h] [rbp+1F0h]
  const wchar_t *v165; // [rsp+300h] [rbp+200h] BYREF
  void **hFile; // [rsp+308h] [rbp+208h] BYREF
  __int128 v167; // [rsp+310h] [rbp+210h]
  __int128 v168; // [rsp+320h] [rbp+220h]
  _QWORD v169[2]; // [rsp+330h] [rbp+230h] BYREF
  int v170; // [rsp+340h] [rbp+240h]
  _BYTE v171[288]; // [rsp+350h] [rbp+250h] BYREF
  struct _IO_COUNTERS v172; // [rsp+470h] [rbp+370h] BYREF
  _IO_COUNTERS IoCounters; // [rsp+4A0h] [rbp+3A0h] BYREF
  PROCESS_MEMORY_COUNTERS v174; // [rsp+4D0h] [rbp+3D0h] BYREF
  PROCESS_MEMORY_COUNTERS ppsmemCounters; // [rsp+520h] [rbp+420h] BYREF
  PROCESS_MEMORY_COUNTERS v176; // [rsp+570h] [rbp+470h] BYREF
  PROCESS_MEMORY_COUNTERS v177; // [rsp+5C0h] [rbp+4C0h] BYREF
  __int16 v178; // [rsp+610h] [rbp+510h] BYREF
  char v179; // [rsp+612h] [rbp+512h]
  unsigned int v180; // [rsp+614h] [rbp+514h]

  v149 = a4;
  v4 = a3;
  v99 = a3;
  v114 = a2;
  v143 = this;
  CallbackParam = 0;
  v150 = 0;
  v123 = 0;
  v124 = 0;
  v125 = 0;
  v126 = 0;
  ThreadPriority = 0x7FFFFFFF;
  v107 = &CFileByteStream::`vftable';
  v108 = 0;
  memset_0(hObject, 0, 0x50u);
  v151[0] = &CByteStreamAdapter::`vftable';
  v151[1] = hObject;
  v169[0] = &CIStreamAdapter::`vftable';
  v169[1] = a2;
  v170 = 1;
  v115 = &CFileByteStream::`vftable';
  v116 = 0;
  v117 = &CFileByteStream::`vftable';
  v118 = 0;
  hFile = &CBufferedWriteStream::`vftable';
  v167 = 0;
  v168 = 0;
  memset_0(&v134, 0, 0x70u);
  Process = 0;
  v112 = 0;
  memset_0(&v178, 0, 0x120u);
  memset_0(&ppsmemCounters, 0, sizeof(ppsmemCounters));
  memset_0(&v174, 0, sizeof(v174));
  memset_0(&v176, 0, sizeof(v176));
  memset_0(&v177, 0, sizeof(v177));
  memset(&IoCounters, 0, sizeof(IoCounters));
  memset(&v172, 0, sizeof(v172));
  PerformanceCount.QuadPart = 0;
  v144.QuadPart = 0;
  Frequency.QuadPart = 0;
  CycleTime = 0;
  v147 = 0;
  if ( !*(_DWORD *)this )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  if ( !*((_QWORD *)this + 14) && !*((_QWORD *)this + 96) )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  if ( !*((_DWORD *)this + 30) )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  memset_0(&v127, 0, 0x50u);
  *(_OWORD *)hObject = v127;
  v161 = v128;
  v162 = v129;
  *(_OWORD *)lpBaseAddress = v130;
  v164 = v131;
  v7 = *((_DWORD *)this + 21);
  v105 = v7;
  if ( (*((_DWORD *)this + 44) & 0x40000000) != 0 && !*((_DWORD *)this + 17) && *((_DWORD *)this + 15) == 0x80000000 )
  {
    v101 = 1;
    v8 = 8;
  }
  else
  {
    v101 = 0;
    v8 = 0;
  }
  v9 = 0;
  v106 = 0;
  v10 = 0x80000;
  if ( *((_DWORD *)this + 20) != -1 )
    v10 = *((_DWORD *)this + 20);
  v110 = v10;
  if ( !(unsigned __int8)IsXerTransportEventUploadCompletePresent()
    || (v11 = 1, !CRegSetting::GetDwordData((CRegSetting *)(*((_QWORD *)this + 2) + 51680LL))) )
  {
    v11 = 0;
  }
  v100 = v11;
  if ( *((_DWORD *)this + 18) != -1 )
  {
    v9 = *((_DWORD *)this + 18) != 0;
    v106 = v9;
  }
  if ( v7 )
  {
    v12 = CProcessDump::InitializeDumpEncryptor(this);
    v13 = v12;
    if ( v12 < 0 )
    {
      CProcessDump::LogTrace(this, 0, L"Failed to initialize dump encryptor: %08X.", (unsigned int)v12);
      goto LABEL_210;
    }
    if ( v11 )
    {
      CFileByteStream::CreateNew((CFileByteStream *)&v107, L"\\\\?\\Wer:\\Temp", L".udf", 0, 0x4000100u, 0);
    }
    else if ( *((_QWORD *)this + 12) )
    {
      v21 = MmsCreate(hObject);
      v13 = v21;
      if ( v21 < 0 )
      {
        CProcessDump::LogTrace(
          this,
          0,
          L"Failed to create memory-mapped stream for unencrypted dump: %08X.",
          (unsigned int)v21);
        goto LABEL_210;
      }
    }
    else
    {
      if ( !*((_QWORD *)this + 13) )
        ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
      New = CFileByteStream::CreateNew((CFileByteStream *)&v107, 0, L".udf", 0, 0x4000100u, 0);
      v13 = New;
      if ( New < 0 )
      {
        CProcessDump::LogTrace(
          this,
          0,
          L"Failed to create temporary file for unencrypted dump: %08X.",
          (unsigned int)New);
        goto LABEL_210;
      }
    }
  }
  else if ( v9 )
  {
    v23 = CFileByteStream::CreateNew((CFileByteStream *)&v117, 0, L".tdf", 0, 0x4000100u, 0);
    v13 = v23;
    if ( v23 < 0 )
    {
      CProcessDump::LogTrace(this, 0, L"Failed to create transient file for dump: %08X.", (unsigned int)v23);
      goto LABEL_210;
    }
  }
  v109 = 50;
  v14 = *((_DWORD *)this + 43);
  if ( !v14 )
  {
    v14 = *((_DWORD *)this + 52);
    if ( *((_DWORD *)this + 42) != 3 )
      v14 |= 0x400u;
  }
  v15 = v14 | 0x20000;
  if ( (v14 & 2) == 0 )
    v15 = v14;
  v16 = v15 & 0x5FFFFFF;
  LODWORD(v150) = *((_DWORD *)this + 48);
  *(_QWORD *)((char *)&v150 + 4) = *((_QWORD *)this + 228);
  HIDWORD(v150) = *((_DWORD *)this + 458);
  if ( !*((_QWORD *)this + 1) )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  v17 = (_QWORD *)*((_QWORD *)this + 1);
  v18 = (unsigned int (__fastcall *)(_QWORD, _QWORD **))v17[2];
  if ( !v18 )
  {
    v19 = 0;
LABEL_58:
    v20 = v99;
    if ( v101 )
      goto LABEL_59;
    goto LABEL_49;
  }
  memset_0(&v127, 0, 0x70u);
  v136 = HIDWORD(v127);
  v137 = v128;
  v138 = v129;
  v139 = v130;
  v140 = v131;
  v141 = v132;
  v142 = v133;
  v134 = v17;
  v135 = 19;
  *(_QWORD *)&v137 = v17[8];
  *((_QWORD *)&v137 + 1) = *((_QWORD *)this + 95);
  *(_QWORD *)&v138 = __PAIR64__(HIDWORD(v143), (unsigned int)this);
  DWORD2(v138) = *((_DWORD *)this + 42);
  HIDWORD(v138) = v16;
  *(_QWORD *)&v139 = *(_QWORD *)((char *)this + 172);
  DWORD2(v139) = *((_DWORD *)this + 30);
  HIDWORD(v139) = *((_DWORD *)this + 48);
  LODWORD(v140) = *((_DWORD *)this + 31);
  *((_QWORD *)&v140 + 1) = (char *)this + 200;
  *(_QWORD *)&v141 = (char *)this + 1824;
  *((_QWORD *)&v141 + 1) = CProcessDump::static_vLogCallbackRoutine;
  *(_QWORD *)&v142 = __PAIR64__(HIDWORD(v143), (unsigned int)this);
  DWORD2(v142) = v8 | (v99 >> 4) & 2 | (v7 != 0 ? 4 : 0) | (*((_DWORD *)this + 32) != 0);
  v19 = 0;
  if ( !v18(v17[3], &v134) )
    goto LABEL_58;
  v20 = v99 & 0xFFFFFFDF | (32 * ((DWORD2(v142) >> 1) & 1));
  LOBYTE(v99) = v20;
  v105 = (DWORD2(v142) >> 2) & 1;
  if ( (BYTE8(v142) & 8) != 0 && !*((_DWORD *)this + 17) && *((_DWORD *)this + 15) == 0x80000000 )
  {
    v101 = 1;
LABEL_59:
    CurrentThread = GetCurrentThread();
    if ( !SetThreadPriority(CurrentThread, 0x10000) )
    {
      v101 = 0;
      LastError = GetLastError();
      v32 = ERROR_HR_FROM_WIN32(LastError);
      CProcessDump::LogTrace(this, 1u, L"Failed to enable background priority: HRESULT %08X.", v32);
    }
    v33 = GetCurrentThread();
    v34 = NtSetInformationThread(v33, ThreadIoPriority, &qword_1800BE9E0, 4u);
    if ( v34 < 0 )
      CProcessDump::LogTrace(this, 1u, L"Failed to bump I/O priority to Low: NTSTATUS %08X.", (unsigned int)v34);
    goto LABEL_52;
  }
  v101 = 0;
LABEL_49:
  if ( *((_DWORD *)this + 15) != 0x80000000 )
  {
    v24 = GetCurrentThread();
    ThreadPriority = GetThreadPriority(v24);
    v25 = *((_DWORD *)this + 15);
    v26 = GetCurrentThread();
    if ( !SetThreadPriority(v26, v25) )
    {
      v27 = GetLastError();
      LODWORD(ExceptionParam) = ERROR_HR_FROM_WIN32(v27);
      CProcessDump::LogTrace(
        this,
        1u,
        L"Failed to set debug thread priority %d: HRESULT %08X.",
        *((unsigned int *)this + 15),
        ExceptionParam);
    }
  }
LABEL_52:
  v28 = (void *)*((_QWORD *)this + 96);
  if ( !v28 || (v20 & 0x20) != 0 )
  {
    v28 = (void *)*((_QWORD *)this + 14);
    v29 = v28;
  }
  else
  {
    v29 = 0;
    if ( !(unsigned int)PssQuerySnapshot(*((_QWORD *)this + 96), 1, &Process) )
      v29 = Process;
  }
  v122 = v29;
  if ( *((_DWORD *)this + 16) )
  {
    v35 = GetCurrentThread();
    v36 = RtlEnableThreadProfiling(v35, 1, 0, &v112);
    v109 = v36;
    if ( v36 )
    {
      v112 = 0;
      CProcessDump::LogTrace(this, 1u, L"Failed to enable thread profiling: Win32 error %u.", v36);
    }
  }
  memset_0(&v127, 0, 0x48u);
  *(_OWORD *)&ppsmemCounters.cb = v127;
  *(_OWORD *)&ppsmemCounters.WorkingSetSize = v128;
  *(_OWORD *)&ppsmemCounters.QuotaPagedPoolUsage = v129;
  *(_OWORD *)&ppsmemCounters.QuotaNonPagedPoolUsage = v130;
  ppsmemCounters.PeakPagefileUsage = v131;
  memset_0(&v127, 0, 0x48u);
  *(_OWORD *)&v174.cb = v127;
  *(_OWORD *)&v174.WorkingSetSize = v128;
  *(_OWORD *)&v174.QuotaPagedPoolUsage = v129;
  *(_OWORD *)&v174.QuotaNonPagedPoolUsage = v130;
  v174.PeakPagefileUsage = v131;
  memset_0(&v127, 0, 0x48u);
  *(_OWORD *)&v176.cb = v127;
  *(_OWORD *)&v176.WorkingSetSize = v128;
  *(_OWORD *)&v176.QuotaPagedPoolUsage = v129;
  *(_OWORD *)&v176.QuotaNonPagedPoolUsage = v130;
  v176.PeakPagefileUsage = v131;
  memset_0(&v127, 0, 0x48u);
  *(_OWORD *)&v177.cb = v127;
  *(_OWORD *)&v177.WorkingSetSize = v128;
  *(_OWORD *)&v177.QuotaPagedPoolUsage = v129;
  *(_OWORD *)&v177.QuotaNonPagedPoolUsage = v130;
  v177.PeakPagefileUsage = v131;
  CurrentProcess = GetCurrentProcess();
  ProcessMemoryInfo = K32GetProcessMemoryInfo(CurrentProcess, &ppsmemCounters, 0x48u);
  if ( v29 )
    v102 = K32GetProcessMemoryInfo(v29, &v176, 0x48u);
  else
    v102 = 0;
  v38 = GetCurrentProcess();
  ProcessIoCounters = GetProcessIoCounters(v38, &IoCounters);
  v39 = GetCurrentThread();
  QueryThreadCycleTime(v39, &CycleTime);
  QueryPerformanceCounter(&PerformanceCount);
  if ( *((_DWORD *)this + 14) )
  {
    CProcessDump::LogTrace(this, 2u, L"Sleeping for %u ms.");
    TickCount = GetTickCount();
    Sleep(*((_DWORD *)this + 14));
    v41 = GetTickCount();
    CProcessDump::LogTrace(this, 2u, L"Woke up, slept for %u ms.", v41 - TickCount);
  }
  v124 = this;
  LODWORD(v125) = v20;
  CallbackParam.CallbackRoutine = (MINIDUMP_CALLBACK_ROUTINE)CProcessDump::static_MiniDumpCallback;
  CallbackParam.CallbackParam = &v123;
  if ( !v105 )
  {
    if ( !v106 )
    {
      v42 = (void ***)v114;
      p_hFile = v114;
      goto LABEL_89;
    }
    v42 = &v117;
    p_hFile = v118;
    if ( v118 )
    {
LABEL_87:
      v126 = 0;
      goto LABEL_90;
    }
LABEL_86:
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
    goto LABEL_87;
  }
  if ( v100 )
  {
    if ( !*((_QWORD *)this + 13) )
      ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
    v42 = &v107;
    p_hFile = v108;
    if ( v108 )
      goto LABEL_87;
    goto LABEL_86;
  }
  if ( !*((_QWORD *)this + 12) )
  {
    if ( !*((_QWORD *)this + 13) )
      ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
    v42 = &v107;
    p_hFile = v108;
    if ( v108 )
      goto LABEL_87;
    goto LABEL_86;
  }
  v42 = (void ***)v151;
  p_hFile = (struct IWerByteStream *)v151;
LABEL_89:
  v126 = 1;
LABEL_90:
  v103 = 0;
  if ( v110 )
  {
    v44 = CBufferedWriteStream::Initialize((CBufferedWriteStream *)&hFile, (struct IWerByteStream *)v42, v110);
    v19 = v44 >= 0;
    v103 = v19;
    if ( v44 < 0 )
    {
      v103 = 0;
    }
    else
    {
      p_hFile = (struct IWerByteStream *)&hFile;
      v126 = 1;
    }
  }
  *((_QWORD *)this + 230) = 0;
  if ( *((_DWORD *)this + 19) )
  {
    v13 = -2147023773;
  }
  else
  {
    if ( (unsigned __int8)IsXerProgressCallbackPresent() )
      XerProgressCallback(3);
    v45 = MiniDumpWriteDump(
            v28,
            *((_DWORD *)this + 30),
            p_hFile,
            v16,
            (PMINIDUMP_EXCEPTION_INFORMATION)((unsigned __int64)&v150
                                            & ((unsigned __int128)-(__int128)*((unsigned __int64 *)this + 228) >> 64)),
            0,
            &CallbackParam);
    if ( v45 )
      v13 = 0;
    else
      v13 = GetLastError();
    if ( (unsigned __int8)IsXerProgressCallbackPresent() )
      XerProgressCallback(4);
    v152[0] = (__int64)v153;
    v152[1] = (__int64)v153;
    v153[0] = 0;
    v46 = *((_QWORD *)this + 2);
    if ( v46 )
      CReport::GetUniqueIdentifier(v46, v152);
    else
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
        v152,
        L"{00000000-0000-0000-0000-000000000000}");
    v154[0] = v155;
    v154[1] = v155;
    v155[0] = 0;
    if ( v149 == (HANDLE)-1LL )
    {
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(v154, &Src);
    }
    else
    {
      FinalPathByHandle = _werDetail::UtilGetFinalPathByHandle(v149);
      if ( FinalPathByHandle < 0
        && WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control
        && (WPP_GLOBAL_Control[14] & 2) != 0 )
      {
        WPP_SF_d(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          10,
          WPP_4909ce9a3d833966bf1277dfd490a226_Traceguids,
          (unsigned int)FinalPathByHandle);
      }
    }
    if ( (unsigned int)dword_1800D8000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 0x400000000000LL) )
    {
      v156 = v154[0];
      v119 = v16;
      v159 = v152[0];
      v165 = L"ProcessDump";
      v120 = v13;
      v158 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        v50,
        (unsigned int)byte_1800C80F9,
        v49,
        v51,
        (__int64)&v158,
        (__int64)&v120,
        (__int64)&v165,
        (__int64)&v159,
        (__int64)&v119,
        (__int64)&v156);
    }
    if ( WPP_GLOBAL_Control != (wchar_t *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[14] & 4) != 0 )
      WPP_SF_DSD(*((_QWORD *)WPP_GLOBAL_Control + 2), v48, v49, v13, v152[0], v16);
    if ( !v45 && v13 >= 0 )
      v13 = -2147467259;
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v154);
    utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(v152);
  }
  if ( v19 )
    CBufferedWriteStream::Flush((CBufferedWriteStream *)&hFile, *(void **)(*((_QWORD *)this + 1) + 64LL));
  QueryPerformanceCounter(&v144);
  QueryPerformanceFrequency(&Frequency);
  v52 = GetCurrentThread();
  QueryThreadCycleTime(v52, &v147);
  if ( !Frequency.QuadPart )
    ((void (*)(void))MicrosoftTelemetryAssertTriggeredNoArgs)();
  memset_0(v171, 0, sizeof(v171));
  v53 = &v178;
  v54 = v171;
  v55 = 2;
  v56 = 128;
  do
  {
    *(_OWORD *)v53 = *v54;
    *((_OWORD *)v53 + 1) = v54[1];
    *((_OWORD *)v53 + 2) = v54[2];
    *((_OWORD *)v53 + 3) = v54[3];
    *((_OWORD *)v53 + 4) = v54[4];
    *((_OWORD *)v53 + 5) = v54[5];
    *((_OWORD *)v53 + 6) = v54[6];
    *((_OWORD *)v53 + 7) = v54[7];
    v53 += 64;
    v54 += 8;
    --v55;
  }
  while ( v55 );
  *(_OWORD *)v53 = *v54;
  *((_OWORD *)v53 + 1) = v54[1];
  v57 = v112;
  if ( v112 )
  {
    if ( !*((_DWORD *)this + 16) )
    {
      MicrosoftTelemetryAssertTriggeredNoArgs(v112, 0, 128);
      v57 = v112;
    }
    v178 = 288;
    v179 = 1;
    v58 = RtlReadThreadProfilingData(v57, 1, &v178);
    RtlDisableThreadProfiling(v112);
  }
  else
  {
    v58 = v109;
  }
  v59 = ProcessIoCounters;
  if ( ProcessIoCounters )
  {
    v60 = GetCurrentProcess();
    v59 = GetProcessIoCounters(v60, &v172);
  }
  else
  {
    memset(&v172, 0, sizeof(v172));
  }
  if ( ProcessMemoryInfo )
  {
    v61 = GetCurrentProcess();
    ProcessMemoryInfo = K32GetProcessMemoryInfo(v61, &v174, 0x48u);
  }
  if ( v102 )
  {
    v62 = v122;
    if ( !v122 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v57, v55, v56);
    v102 = K32GetProcessMemoryInfo(v62, &v177, 0x48u);
  }
  v63 = (unsigned __int64)(1000 * (v144.QuadPart - PerformanceCount.QuadPart)) / Frequency.QuadPart;
  CProcessDump::LogTrace(
    this,
    2u,
    L"MiniDumpWriteDump took:\r\n- Ticks     : %14u ms.\r\n- Cycles    : %14I64u.",
    (unsigned int)v63,
    v147 - CycleTime);
  if ( !v58 )
    CProcessDump::LogTrace(this, 0x40000002u, L"- CSwitches : %14u.", v180);
  if ( v59 )
  {
    v67 = v172.ReadOperationCount - IoCounters.ReadOperationCount;
    v172.ReadOperationCount -= IoCounters.ReadOperationCount;
    v68 = v172.ReadTransferCount - IoCounters.ReadTransferCount;
    v172.ReadTransferCount -= IoCounters.ReadTransferCount;
    v69 = v172.WriteOperationCount - IoCounters.WriteOperationCount;
    v172.WriteOperationCount -= IoCounters.WriteOperationCount;
    v70 = v172.WriteTransferCount - IoCounters.WriteTransferCount;
    v172.WriteTransferCount -= IoCounters.WriteTransferCount;
    v71 = v172.OtherOperationCount - IoCounters.OtherOperationCount;
    v172.OtherOperationCount -= IoCounters.OtherOperationCount;
    v72 = v172.OtherTransferCount - IoCounters.OtherTransferCount;
    v172.OtherTransferCount -= IoCounters.OtherTransferCount;
    v73 = (_DWORD)v63 << 10;
    if ( !v73 )
      v73 = 1;
    CProcessDump::LogTrace(
      this,
      2u,
      L"MiniDumpWriteDump I/O counters:\r\n"
       "- Reads     : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\r\n"
       "- Writes    : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\r\n"
       "- Other     : %9I64u ops, %9I64u bytes, %6I64u KB/sec.\r\n",
      v67,
      v68,
      1000 * v68 / v73,
      v69,
      v70,
      1000 * v70 / v73,
      v71,
      v72,
      1000 * v72 / v73);
    v19 = v103;
  }
  if ( ProcessMemoryInfo )
    CProcessDump::LogTrace(this, 2u, L"Page faults (local) : %9u.", v174.PageFaultCount - ppsmemCounters.PageFaultCount);
  if ( v102 )
  {
    if ( !v122 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v65, v64, v66);
    CProcessDump::LogTrace(this, 2u, L"Page faults (remote): %9u.", v177.PageFaultCount - v176.PageFaultCount);
  }
  CProcessDump::LogTrace(this, 2u, L"MiniDumpWriteDump read memory failures: %u.\r\n", HIDWORD(v125));
  if ( v19 )
  {
    LODWORD(UserStreamParam) = HIDWORD(v168);
    LODWORD(ExceptionParama) = DWORD2(v168);
    CProcessDump::LogTrace(
      this,
      2u,
      L"Write buffer:\r\n- Buffer size           : %u bytes.\r\n- Flushes (full+partial): %u + %u.\r\n",
      v110,
      ExceptionParama,
      UserStreamParam);
  }
  else
  {
    CProcessDump::LogTrace(this, 2u, L"Write buffer disabled.\r\n");
  }
  if ( v13 != -2147023673 )
  {
    if ( v13 < 0 )
    {
      v77 = (unsigned int)v13;
      v78 = L"MiniDumpWriteDump failed: %08X.";
LABEL_161:
      CProcessDump::LogTrace(this, 0, v78, v77);
      goto LABEL_209;
    }
    if ( v105 )
    {
      if ( !*((_QWORD *)this + 12) && !*((_QWORD *)this + 13) )
        MicrosoftTelemetryAssertTriggeredNoArgs(v75, v74, v76);
      if ( v100 )
      {
        if ( !*((_QWORD *)this + 13) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v75, v74, v76);
        CProcessDump::LogTrace(this, 2u, L"Streaming-based encryption NOT supported.");
        if ( (unsigned __int8)IsXerProgressCallbackPresent() )
          XerProgressCallback(5);
        v79 = CFileByteStream::CreateNew((CFileByteStream *)&v115, L"\\\\?\\Wer:\\Temp", L".edf", 1u, 0x4000100u, 0);
        v13 = v79;
        if ( v79 < 0 )
        {
LABEL_172:
          CProcessDump::LogTrace(
            this,
            0,
            L"Failed to create temporary file for encrypted dump: %08X.",
            (unsigned int)v79);
          goto LABEL_209;
        }
        v80 = CFileByteStream::SetFilePointer((CFileByteStream *)&v107, 0, 0, 0);
        v13 = v80;
        if ( v80 < 0 )
        {
LABEL_174:
          v77 = (unsigned int)v80;
          v78 = L"Failed to rewind unencrypted dump stream: %08X.";
          goto LABEL_161;
        }
        v13 = (*((__int64 (__fastcall **)(struct IWerByteStream *, __int64))this + 13))(v108, v116);
        if ( (unsigned __int8)IsXerProgressCallbackPresent() )
          XerProgressCallback(6);
        if ( v13 < 0 )
        {
          v77 = (unsigned int)v13;
LABEL_179:
          v78 = L"Dump could not be encrypted: %08X.";
          goto LABEL_161;
        }
        CFileByteStream::Close((CFileByteStream *)&v107);
        if ( (unsigned __int8)IsXerProgressCallbackPresent() )
          XerProgressCallback(7);
        v13 = CByteStream::AlignedCopyTo((CByteStream *)&v115, v114, *(void **)(*((_QWORD *)this + 1) + 64LL), v149);
        if ( (unsigned __int8)IsXerProgressCallbackPresent() )
          XerProgressCallback(8);
        if ( v13 < 0 )
        {
          v77 = (unsigned int)v13;
LABEL_186:
          v78 = L"Failed to copy encrypted dump: %08X.";
          goto LABEL_161;
        }
LABEL_198:
        v84 = &v115;
LABEL_207:
        CFileByteStream::Close((CFileByteStream *)v84);
        goto LABEL_208;
      }
      if ( !*((_QWORD *)this + 12) )
      {
        if ( !*((_QWORD *)this + 13) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v75, v74, v76);
        CProcessDump::LogTrace(this, 2u, L"Streaming-based encryption NOT supported.");
        v79 = CFileByteStream::CreateNew((CFileByteStream *)&v115, 0, L".edf", 1u, 0x4000100u, 0);
        v13 = v79;
        if ( v79 < 0 )
          goto LABEL_172;
        v80 = CFileByteStream::SetFilePointer((CFileByteStream *)&v107, 0, 0, 0);
        v13 = v80;
        if ( v80 < 0 )
          goto LABEL_174;
        v82 = (*((__int64 (__fastcall **)(struct IWerByteStream *, __int64))this + 13))(v108, v116);
        v13 = v82;
        if ( v82 >= 0 )
        {
          CFileByteStream::Close((CFileByteStream *)&v107);
          v83 = CByteStream::CopyTo((CByteStream *)&v115, v114, *(void **)(*((_QWORD *)this + 1) + 64LL));
          v13 = v83;
          if ( v83 < 0 )
          {
            v77 = (unsigned int)v83;
            goto LABEL_186;
          }
          goto LABEL_198;
        }
LABEL_190:
        v77 = (unsigned int)v82;
        goto LABEL_179;
      }
      v81 = v162;
      LODWORD(ExceptionParama) = v162;
      CProcessDump::LogTrace(
        this,
        2u,
        L"Streaming-based encryption supported. Dump size: %08X:%08X.",
        DWORD1(v162),
        ExceptionParama);
      v80 = (*((__int64 (__fastcall **)(HANDLE *, _QWORD, _QWORD, _QWORD))hObject[0] + 5))(
              hObject,
              *(_QWORD *)&DOUBLE_0_0,
              0,
              0);
      v13 = v80;
      if ( v80 < 0 )
        goto LABEL_174;
      v82 = (*((__int64 (__fastcall **)(HANDLE *, _QWORD *, __int64))this + 12))(hObject, v169, v81);
      v13 = v82;
      if ( v82 < 0 )
        goto LABEL_190;
    }
    else if ( v106 )
    {
      if ( !v118 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v75, v74, v76);
      v85 = CFileByteStream::SetFilePointer((CFileByteStream *)&v117, 0, 0, 0);
      v13 = v85;
      if ( v85 < 0 )
      {
        v77 = (unsigned int)v85;
        v78 = L"Failed to rewind transient dump stream: %08X.";
        goto LABEL_161;
      }
      v86 = CByteStream::CopyTo((CByteStream *)&v117, v114, *(void **)(*((_QWORD *)this + 1) + 64LL));
      v13 = v86;
      if ( v86 < 0 )
      {
        v77 = (unsigned int)v86;
        v78 = L"Failed to copy transient dump: %08X.";
        goto LABEL_161;
      }
      v84 = &v117;
      goto LABEL_207;
    }
LABEL_208:
    v13 = 0;
    goto LABEL_209;
  }
  CProcessDump::LogTrace(this, 1u, L"Minidump generation canceled.");
  v13 = -2145681407;
LABEL_209:
  v4 = v99;
LABEL_210:
  if ( lpBaseAddress[1] )
    UnmapViewOfFile(lpBaseAddress[1]);
  if ( hObject[1] )
    CloseHandle(hObject[1]);
  memset_0(&v127, 0, 0x50u);
  *(_OWORD *)hObject = v127;
  v161 = v128;
  v162 = v129;
  *(_OWORD *)lpBaseAddress = v130;
  v164 = v131;
  if ( (!*((_QWORD *)this + 96) || (v4 & 0x20) != 0) && *((_QWORD *)this + 14) )
    CProcessDump::LogProcessTerminationState(this);
  v90 = ThreadPriority;
  if ( ThreadPriority == 0x7FFFFFFF )
  {
    if ( !v101 )
      goto LABEL_225;
    v91 = GetCurrentThread();
    v92 = 0x20000;
  }
  else
  {
    if ( v101 )
      MicrosoftTelemetryAssertTriggeredNoArgs(v88, v87, v89);
    v91 = GetCurrentThread();
    v92 = v90;
  }
  SetThreadPriority(v91, v92);
LABEL_225:
  if ( !*((_QWORD *)this + 1) )
    MicrosoftTelemetryAssertTriggeredNoArgs(v88, v87, v89);
  v93 = (_QWORD *)*((_QWORD *)this + 1);
  v94 = (void (__fastcall *)(_QWORD, _QWORD **))v93[2];
  if ( v94 )
  {
    memset_0(&v127, 0, 0x70u);
    v136 = HIDWORD(v127);
    v137 = v128;
    v138 = v129;
    v139 = v130;
    v140 = v131;
    v141 = v132;
    v142 = v133;
    v134 = v93;
    v135 = 20;
    *(_QWORD *)&v137 = v93[8];
    *((_QWORD *)&v137 + 1) = *((_QWORD *)this + 95);
    *(_QWORD *)&v138 = __PAIR64__(HIDWORD(v143), (unsigned int)this);
    DWORD2(v138) = v13;
    *(_QWORD *)&v139 = CProcessDump::static_vLogCallbackRoutine;
    *((_QWORD *)&v139 + 1) = __PAIR64__(HIDWORD(v143), (unsigned int)this);
    v94(v93[3], &v134);
  }
  CBufferedWriteStream::~CBufferedWriteStream((CBufferedWriteStream *)&hFile);
  CFileByteStream::~CFileByteStream((CFileByteStream *)&v117);
  CFileByteStream::~CFileByteStream((CFileByteStream *)&v115);
  CIStreamAdapter::~CIStreamAdapter((CIStreamAdapter *)v169);
  v151[0] = &CByteStreamAdapter::`vftable';
  CFileByteStream::~CFileByteStream((CFileByteStream *)&v107);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x18007fd58  push    rbp
0x18007fd5a  push    rbx
0x18007fd5b  push    rsi
0x18007fd5c  push    rdi
0x18007fd5d  push    r12
0x18007fd5f  push    r13
0x18007fd61  push    r14
0x18007fd63  push    r15
0x18007fd65  lea     rbp, [rsp-648h]
0x18007fd6d  sub     rsp, 748h
0x18007fd74  mov     rax, cs:__security_cookie
0x18007fd7b  xor     rax, rsp
0x18007fd7e  mov     [rbp+680h+var_50], rax
0x18007fd85  mov     [rbp+680h+var_560], r9
0x18007fd8c  mov     r13d, r8d
0x18007fd8f  mov     [rsp+780h+var_720], r8d
0x18007fd94  mov     rbx, rdx
0x18007fd97  mov     [rbp+680h+var_6D0], rdx
0x18007fd9b  mov     r15, rcx
0x18007fd9e  mov     [rbp+680h+var_590], rcx
0x18007fda5  xorps   xmm0, xmm0
0x18007fda8  movups  xmmword ptr [rbp+680h+var_4F0.CallbackRoutine], xmm0
0x18007fdaf  xorps   xmm1, xmm1
0x18007fdb2  movups  [rbp+680h+var_558], xmm1
0x18007fdb9  xor     r12d, r12d
0x18007fdbc  mov     [rbp+680h+var_690], r12
0x18007fdc0  mov     [rbp+680h+var_688], r12
0x18007fdc4  mov     [rbp+680h+var_680], r12
0x18007fdc8  mov     [rbp+680h+var_678], r12b
0x18007fdcc  mov     [rbp+680h+var_6E8], 7FFFFFFFh
0x18007fdd3  lea     rdi, ??_7CFileByteStream@@6B@; const CFileByteStream::`vftable'
0x18007fdda  mov     [rbp+680h+var_700], rdi
0x18007fdde  mov     [rbp+680h+var_6F8], r12
0x18007fde2  lea     esi, [r12+50h]
0x18007fde7  mov     r8d, esi; Size
0x18007fdea  xor     edx, edx; Val
0x18007fdec  lea     rcx, [rbp+680h+hObject]; void *
0x18007fdf3  call    memset_0
0x18007fdf8  lea     rax, ??_7CByteStreamAdapter@@6B@; const CByteStreamAdapter::`vftable'
0x18007fdff  mov     [rbp+680h+var_548], rax
0x18007fe06  lea     rax, [rbp+680h+hObject]
0x18007fe0d  mov     [rbp+680h+var_540], rax
0x18007fe14  lea     rax, ??_7CIStreamAdapter@@6B@; const CIStreamAdapter::`vftable'
0x18007fe1b  mov     [rbp+680h+var_450], rax
0x18007fe22  mov     [rbp+680h+var_448], rbx
0x18007fe29  lea     ebx, [rsi-4Fh]
0x18007fe2c  mov     [rbp+680h+var_440], ebx
0x18007fe32  mov     [rbp+680h+var_6C8], rdi
0x18007fe36  mov     [rbp+680h+var_6C0], r12
0x18007fe3a  mov     [rbp+680h+var_6B8], rdi
0x18007fe3e  mov     [rbp+680h+var_6B0], r12
0x18007fe42  lea     rax, ??_7CBufferedWriteStream@@6B@; const CBufferedWriteStream::`vftable'
0x18007fe49  mov     [rbp+680h+hFile], rax
0x18007fe50  xorps   xmm0, xmm0
0x18007fe53  movdqu  [rbp+680h+var_470], xmm0
0x18007fe5b  movups  [rbp+680h+var_460], xmm0
0x18007fe62  xor     edx, edx; Val
0x18007fe64  lea     r8d, [r12+70h]; Size
0x18007fe69  lea     rcx, [rbp+680h+var_600]; void *
0x18007fe70  call    memset_0
0x18007fe75  mov     [rbp+680h+Process], r12
0x18007fe7c  mov     [rbp+680h+var_6E0], r12
0x18007fe80  xor     edx, edx; Val
0x18007fe82  mov     r8d, 120h; Size
0x18007fe88  lea     rcx, [rbp+680h+var_170]; void *
0x18007fe8f  call    memset_0
0x18007fe94  lea     edi, [rsi-8]
0x18007fe97  mov     r8d, edi; Size
0x18007fe9a  xor     edx, edx; Val
0x18007fe9c  lea     rcx, [rbp+680h+ppsmemCounters]; void *
0x18007fea3  call    memset_0
0x18007fea8  mov     r8d, edi; Size
0x18007feab  xor     edx, edx; Val
0x18007fead  lea     rcx, [rbp+680h+var_2B0]; void *
0x18007feb4  call    memset_0
0x18007feb9  mov     r8d, edi; Size
0x18007febc  xor     edx, edx; Val
0x18007febe  lea     rcx, [rbp+680h+var_210]; void *
0x18007fec5  call    memset_0
0x18007feca  mov     r8d, edi; Size
0x18007fecd  xor     edx, edx; Val
0x18007fecf  lea     rcx, [rbp+680h+var_1C0]; void *
0x18007fed6  call    memset_0
0x18007fedb  xorps   xmm0, xmm0
0x18007fede  movups  xmmword ptr [rbp+680h+IoCounters.ReadOperationCount], xmm0
0x18007fee5  movups  xmmword ptr [rbp+680h+IoCounters.OtherOperationCount], xmm0
0x18007feec  movups  xmmword ptr [rbp+680h+IoCounters.WriteTransferCount], xmm0
0x18007fef3  xorps   xmm1, xmm1
0x18007fef6  movups  xmmword ptr [rbp+680h+var_310.ReadOperationCount], xmm1
0x18007fefd  movups  xmmword ptr [rbp+680h+var_310.OtherOperationCount], xmm1
0x18007ff04  movups  xmmword ptr [rbp+680h+var_310.WriteTransferCount], xmm1
0x18007ff0b  mov     qword ptr [rbp+680h+PerformanceCount], r12
0x18007ff12  mov     qword ptr [rbp+680h+var_588], r12
0x18007ff19  mov     qword ptr [rbp+680h+Frequency], r12
0x18007ff1d  mov     [rbp+680h+CycleTime], r12
0x18007ff24  mov     [rbp+680h+var_570], r12
0x18007ff2b  cmp     [r15], r12d
0x18007ff2e  jnz     short loc_18007FF35
0x18007ff30  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007ff35  cmp     [r15+70h], r12
0x18007ff39  jnz     short loc_18007FF49
0x18007ff3b  cmp     [r15+300h], r12
0x18007ff42  jnz     short loc_18007FF49
0x18007ff44  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007ff49  cmp     [r15+78h], r12d
0x18007ff4d  jnz     short loc_18007FF54
0x18007ff4f  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007ff54  mov     r8, rsi; Size
0x18007ff57  xor     edx, edx; Val
0x18007ff59  lea     rcx, [rbp+680h+var_670]; void *
0x18007ff5d  call    memset_0
0x18007ff62  movups  xmm0, [rbp+680h+var_670]
0x18007ff66  movaps  xmmword ptr [rbp+680h+hObject], xmm0
0x18007ff6d  movups  xmm1, [rbp+680h+var_660]
0x18007ff71  movaps  [rbp+680h+var_4C0], xmm1
0x18007ff78  movups  xmm0, [rbp+680h+var_650]
0x18007ff7c  movaps  [rbp+680h+var_4B0], xmm0
0x18007ff83  movups  xmm1, [rbp+680h+var_640]
0x18007ff87  movaps  xmmword ptr [rbp+680h+lpBaseAddress], xmm1
0x18007ff8e  movups  xmm0, [rbp+680h+var_630]
0x18007ff92  movaps  [rbp+680h+var_490], xmm0
0x18007ff99  mov     r14d, [r15+54h]
0x18007ff9d  mov     [rsp+780h+var_708], r14d
0x18007ffa2  test    dword ptr [r15+0B0h], 40000000h
0x18007ffad  jz      short loc_18007FFCA
0x18007ffaf  cmp     [r15+44h], r12d
0x18007ffb3  jnz     short loc_18007FFCA
0x18007ffb5  cmp     dword ptr [r15+3Ch], 80000000h
0x18007ffbd  jnz     short loc_18007FFCA
0x18007ffbf  mov     [rsp+780h+var_718], ebx
0x18007ffc3  mov     esi, 8
0x18007ffc8  jmp     short loc_18007FFD2
0x18007ffca  mov     [rsp+780h+var_718], r12d
0x18007ffcf  mov     esi, r12d
0x18007ffd2  mov     ebx, r12d
0x18007ffd5  mov     [rsp+780h+var_704], ebx
0x18007ffd9  mov     eax, 80000h
0x18007ffde  cmp     dword ptr [r15+50h], 0FFFFFFFFh
0x18007ffe3  cmovnz  eax, [r15+50h]
0x18007ffe8  mov     [rbp+680h+var_6EC], eax
0x18007ffeb  call    IsXerTransportEventUploadCompletePresent
0x18007fff0  test    al, al
0x18007fff2  jz      short loc_18008000B
0x18007fff4  mov     rcx, [r15+10h]
0x18007fff8  add     rcx, 0C9E0h; this
0x18007ffff  call    ?GetDwordData@CRegSetting@@QEBAKXZ; CRegSetting::GetDwordData(void)
0x180080004  test    eax, eax
0x180080006  mov     dil, 1
0x180080009  jnz     short loc_18008000E
0x18008000b  mov     dil, r12b
0x18008000e  mov     [rsp+780h+var_71C], dil
0x180080013  cmp     dword ptr [r15+48h], 0FFFFFFFFh
0x180080018  jz      short loc_180080028
0x18008001a  mov     ebx, r12d
0x18008001d  cmp     [r15+48h], r12d
0x180080021  setnz   bl
0x180080024  mov     [rsp+780h+var_704], ebx
0x180080028  test    r14d, r14d
0x18008002b  jz      loc_180080344
0x180080031  mov     rcx, r15; this
0x180080034  call    ?InitializeDumpEncryptor@CProcessDump@@AEAAJXZ; CProcessDump::InitializeDumpEncryptor(void)
0x180080039  mov     r12d, eax
0x18008003c  test    eax, eax
0x18008003e  jns     short loc_18008005C
0x180080040  lea     r8, aFailedToInitia; "Failed to initialize dump encryptor: %0"...
0x180080047  mov     r9d, eax
0x18008004a  xor     edx, edx; unsigned int
0x18008004c  mov     rcx, r15; this
0x18008004f  call    ?LogTrace@CProcessDump@@AEAAXKPEB_WZZ; CProcessDump::LogTrace(ulong,wchar_t const *,...)
0x180080054  xor     r14d, r14d
0x180080057  jmp     loc_1800811B2
0x18008005c  xor     r12d, r12d
0x18008005f  test    dil, dil
0x180080062  jz      loc_1800802D7
0x180080068  mov     [rsp+780h+UserStreamParam], r12; struct _SECURITY_ATTRIBUTES *
0x18008006d  mov     dword ptr [rsp+780h+ExceptionParam], 4000100h; unsigned int
0x180080075  xor     r9d, r9d; unsigned int
0x180080078  lea     r8, aUdf; ".udf"
0x18008007f  lea     rdx, aWerTemp; "\\\\?\\Wer:\\Temp"
0x180080086  lea     rcx, [rbp+680h+var_700]; this
0x18008008a  call    ?CreateNew@CFileByteStream@@UEAAJPEB_W0KKPEAU_SECURITY_ATTRIBUTES@@@Z; CFileByteStream::CreateNew(wchar_t const *,wchar_t const *,ulong,ulong,_SECURITY_ATTRIBUTES *)
0x18008008f  mov     [rbp+680h+var_6F0], 32h ; '2'
0x180080096  mov     ecx, [r15+0ACh]
0x18008009d  test    ecx, ecx
0x18008009f  jnz     short loc_1800800B6
0x1800800a1  mov     ecx, [r15+0D0h]
0x1800800a8  cmp     dword ptr [r15+0A8h], 3
0x1800800b0  jz      short loc_1800800B6
0x1800800b2  bts     ecx, 0Ah
0x1800800b6  mov     r13d, ecx
0x1800800b9  bts     r13d, 11h
0x1800800be  test    cl, 2
0x1800800c1  cmovz   r13d, ecx
0x1800800c5  and     r13d, 5FFFFFFh
0x1800800cc  mov     eax, [r15+0C0h]
0x1800800d3  mov     dword ptr [rbp+680h+var_558], eax
0x1800800d9  lea     r12, [r15+720h]
0x1800800e0  mov     rax, [r12]
0x1800800e4  mov     qword ptr [rbp+680h+var_558+4], rax
0x1800800eb  mov     eax, [r15+728h]
0x1800800f2  mov     dword ptr [rbp+680h+var_558+0Ch], eax
0x1800800f8  cmp     qword ptr [r15+8], 0
0x1800800fd  jnz     short loc_180080104
0x1800800ff  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180080104  mov     rbx, [r15+8]
0x180080108  mov     rdi, [rbx+10h]
0x18008010c  test    rdi, rdi
0x18008010f  jz      loc_18008042D
0x180080115  xor     edx, edx; Val
0x180080117  lea     r8d, [rdx+70h]; Size
0x18008011b  lea     rcx, [rbp+680h+var_670]; void *
0x18008011f  call    memset_0
0x180080124  movups  xmm0, [rbp+680h+var_670]
0x180080128  movaps  [rbp+680h+var_600], xmm0
0x18008012f  movups  xmm1, [rbp+680h+var_660]
0x180080133  movaps  [rbp+680h+var_5F0], xmm1
0x18008013a  movups  xmm0, [rbp+680h+var_650]
0x18008013e  movaps  [rbp+680h+var_5E0], xmm0
0x180080145  movups  xmm1, [rbp+680h+var_640]
0x180080149  movaps  [rbp+680h+var_5D0], xmm1
0x180080150  movups  xmm0, [rbp+680h+var_630]
0x180080154  movaps  [rbp+680h+var_5C0], xmm0
0x18008015b  movups  xmm1, [rbp+680h+var_620]
0x18008015f  movaps  [rbp+680h+var_5B0], xmm1
0x180080166  movups  xmm0, [rbp+680h+var_610]
0x18008016a  movaps  [rbp+680h+var_5A0], xmm0
0x180080171  mov     qword ptr [rbp+680h+var_600], rbx
0x180080178  mov     dword ptr [rbp+680h+var_600+8], 13h
0x180080182  mov     rax, [rbx+40h]
0x180080186  mov     qword ptr [rbp+680h+var_5F0], rax
0x18008018d  lea     rcx, [r15+0C8h]
0x180080194  mov     rax, [rcx+230h]
0x18008019b  mov     qword ptr [rbp+680h+var_5F0+8], rax
0x1800801a2  mov     dword ptr [rbp+680h+var_5E0], r15d
0x1800801a9  mov     edx, dword ptr [rbp+680h+var_590+4]
0x1800801af  mov     dword ptr [rbp+680h+var_5E0+4], edx
0x1800801b5  mov     eax, [r15+0A8h]
0x1800801bc  mov     dword ptr [rbp+680h+var_5E0+8], eax
0x1800801c2  mov     dword ptr [rbp+680h+var_5E0+0Ch], r13d
0x1800801c9  mov     eax, [r15+0ACh]
0x1800801d0  mov     dword ptr [rbp+680h+var_5D0], eax
0x1800801d6  mov     eax, [r15+0B0h]
0x1800801dd  mov     dword ptr [rbp+680h+var_5D0+4], eax
0x1800801e3  mov     eax, [r15+78h]
0x1800801e7  mov     dword ptr [rbp+680h+var_5D0+8], eax
0x1800801ed  mov     eax, [r15+0C0h]
0x1800801f4  mov     dword ptr [rbp+680h+var_5D0+0Ch], eax
0x1800801fa  mov     eax, [r15+7Ch]
0x1800801fe  mov     dword ptr [rbp+680h+var_5C0], eax
0x180080204  mov     qword ptr [rbp+680h+var_5C0+8], rcx
0x18008020b  mov     qword ptr [rbp+680h+var_5B0], r12
0x180080212  lea     rax, ?static_vLogCallbackRoutine@CProcessDump@@CAXPEAXKPEB_WPEAD@Z; CProcessDump::static_vLogCallbackRoutine(void *,ulong,wchar_t const *,char *)
0x180080219  mov     qword ptr [rbp+680h+var_5B0+8], rax
0x180080220  mov     dword ptr [rbp+680h+var_5A0], r15d
0x180080227  mov     dword ptr [rbp+680h+var_5A0+4], edx
0x18008022d  xor     r8d, r8d
0x180080230  cmp     [r15+80h], r8d
0x180080237  setnz   r8b
0x18008023b  mov     eax, r14d
0x18008023e  neg     eax
0x180080240  sbb     edx, edx
0x180080242  and     edx, 4
0x180080245  or      r8d, edx
0x180080248  mov     r14d, [rsp+780h+var_720]
0x18008024d  mov     edx, r14d
0x180080250  shr     edx, 4
0x180080253  and     edx, 2
0x180080256  or      r8d, edx
0x180080259  or      r8d, esi
0x18008025c  mov     dword ptr [rbp+680h+var_5A0+8], r8d
0x180080263  lea     rdx, [rbp+680h+var_600]
0x18008026a  mov     rcx, [rbx+18h]
0x18008026e  mov     rax, rdi
0x180080271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080276  xor     esi, esi
0x180080278  test    eax, eax
0x18008027a  jz      loc_18008042F
0x180080280  mov     edx, dword ptr [rbp+680h+var_5A0+8]
0x180080286  mov     edi, edx
0x180080288  shr     edi, 1
0x18008028a  lea     ebx, [rsi+1]
0x18008028d  and     edi, ebx
0x18008028f  shl     edi, 5
0x180080292  mov     eax, r14d
0x180080295  and     eax, 0FFFFFFDFh
0x180080298  or      edi, eax
0x18008029a  mov     [rsp+780h+var_720], edi
0x18008029e  mov     r14d, edx
0x1800802a1  shr     r14d, 2
0x1800802a5  and     r14d, ebx
0x1800802a8  mov     [rsp+780h+var_708], r14d
0x1800802ad  test    dl, 8
0x1800802b0  jz      loc_180080385
0x1800802b6  cmp     [r15+44h], esi
0x1800802ba  jnz     loc_180080385
0x1800802c0  cmp     dword ptr [r15+3Ch], 80000000h
0x1800802c8  jnz     loc_180080385
0x1800802ce  mov     [rsp+780h+var_718], ebx
0x1800802d2  jmp     loc_180080442
0x1800802d7  cmp     [r15+60h], r12
  ... truncated ...
```
