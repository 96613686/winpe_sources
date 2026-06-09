# StorageService::TriggerStorageOptimization(unsigned __int64 *)

- ea: `0x180032088`
- end: `0x180032536`
- name: `?TriggerStorageOptimization@StorageService@@QEAAJPEA_K@Z`
- size: `1198`
- prototype: `__int64 __fastcall(StorageService *__hidden this, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task`

## callers

- `0x180037a50`

## callees

- `0x180001148`
- `0x180001248`
- `0x180003534`
- `0x18000d030`
- `0x18000ddb0`
- `0x18001cf70`
- `0x18001dc9c`
- `0x18001dd2c`
- `0x180024638`
- `0x18002fb98`
- `0x18003037c`
- `0x180030b04`
- `0x180032088`
- `0x18003253c`
- `0x180033d44`
- `0x1800375c0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800322cd`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800322cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032306`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800322d7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032306`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003229f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x18003229f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800322fc`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x1800322fc`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180032173`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003223b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180032360`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180032173`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003223b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x180032360`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180032323`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180032323`

## pseudocode

```c
__int64 __fastcall StorageService::TriggerStorageOptimization(StorageService *this, unsigned __int64 *a2)
{
  bool IsZero; // al
  struct _GUID *v4; // r9
  unsigned __int8 v5; // r12
  ULONGLONG TickCount64; // r14
  ULONGLONG v7; // rsi
  __int64 v8; // rcx
  signed int StorageDeviceInfo; // ebx
  __int64 v10; // rcx
  ULONGLONG v11; // rdi
  signed int LastError; // eax
  signed int v13; // eax
  signed int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // rcx
  __int64 v17; // rdx
  __int64 v18; // rcx
  ULONGLONG v19; // rcx
  __int64 v20; // rdi
  double v21; // xmm7_8
  double v22; // xmm7_8
  __int64 v23; // rcx
  double v24; // xmm6_8
  double v25; // xmm6_8
  union _ULARGE_INTEGER v26; // rcx
  struct _PROCESS_INFORMATION *v27; // rdx
  int v28; // r9d
  __int64 v30; // [rsp+78h] [rbp-90h] BYREF
  union _ULARGE_INTEGER v31; // [rsp+80h] [rbp-88h] BYREF
  union _ULARGE_INTEGER v32; // [rsp+88h] [rbp-80h] BYREF
  DWORD ExitCode; // [rsp+90h] [rbp-78h] BYREF
  signed int v34; // [rsp+94h] [rbp-74h] BYREF
  int v35; // [rsp+98h] [rbp-70h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+A0h] [rbp-68h] BYREF
  union _ULARGE_INTEGER v37; // [rsp+A8h] [rbp-60h] BYREF
  union _ULARGE_INTEGER v38; // [rsp+B0h] [rbp-58h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+B8h] [rbp-50h] BYREF
  __int64 v40; // [rsp+D0h] [rbp-38h] BYREF
  ULONGLONG v41; // [rsp+D8h] [rbp-30h] BYREF
  __int64 v42; // [rsp+E0h] [rbp-28h] BYREF
  union _ULARGE_INTEGER v43; // [rsp+E8h] [rbp-20h] BYREF
  union _ULARGE_INTEGER v44; // [rsp+F0h] [rbp-18h] BYREF
  double v45; // [rsp+F8h] [rbp-10h] BYREF
  double v46; // [rsp+100h] [rbp-8h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+108h] [rbp+0h] BYREF
  __int64 v48; // [rsp+178h] [rbp+70h] BYREF
  int v49; // [rsp+180h] [rbp+78h]
  int v50; // [rsp+184h] [rbp+7Ch]
  __int64 v51; // [rsp+188h] [rbp+80h]
  int v52; // [rsp+190h] [rbp+88h] BYREF
  char v53; // [rsp+194h] [rbp+8Ch]
  _BYTE v54[16]; // [rsp+198h] [rbp+90h] BYREF
  struct _GUID v55; // [rsp+1A8h] [rbp+A0h] BYREF
  int v56; // [rsp+1B8h] [rbp+B0h] BYREF
  WCHAR v57[558]; // [rsp+1BCh] [rbp+B4h] BYREF

  v52 = 0;
  v53 = 0;
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(&v52);
  if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    if ( !v53 || (IsZero = _tlgGuidIsZero(&v55), v4 = &v55, IsZero) )
      v4 = 0;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1800BF000,
      byte_1800A7B91,
      v54,
      v4);
  }
  LODWORD(v30) = 0;
  SystemTimeAsFileTime = 0;
  *a2 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  memset_0(&StartupInfo, 0, sizeof(StartupInfo));
  v5 = 0;
  TickCount64 = GetTickCount64();
  v31.QuadPart = 0;
  v38.QuadPart = 0;
  v37.QuadPart = 0;
  v32.QuadPart = 0;
  v7 = 0;
  memset_0(v57, 0, 0x454u);
  v56 = 1112;
  StorageDeviceInfo = StorageService::GetStorageDeviceInfo(v8, 0, 0, 0, &v56);
  if ( StorageDeviceInfo < 0 )
  {
    v11 = TickCount64;
  }
  else
  {
    SvcGetStorageDeviceSize(0, v57, 0, &v32, &v31);
    if ( (int)StorageService::GetStoragePolicySettings(v10, 0, 0, &v30) >= 0 && (_DWORD)v30 == 1 )
    {
      v51 = 1;
      v48 = 24;
      v49 = 0;
      v50 = -1;
      StorageService::TriggerStoragePolicies(
        (StorageService *)&g_StorageService,
        (struct _STORAGE_TRIGGER_POLICIES_PARAMETERS *)&v48);
      v5 = 1;
    }
    v11 = GetTickCount64();
    SvcGetStorageDeviceSize(0, v57, 0, &v32, &v37);
    if ( CreateProcessW(
           L"defrag.exe",
           (LPWSTR)L" /AllVolumes /NormalPriority /SlabConsolidate",
           0,
           0,
           0,
           0x8000000u,
           0,
           0,
           &StartupInfo,
           &ProcessInformation) )
    {
      goto LABEL_18;
    }
    LastError = GetLastError();
    StorageDeviceInfo = LastError;
    if ( LastError > 0 )
      StorageDeviceInfo = (unsigned __int16)LastError | 0x80070000;
    if ( StorageDeviceInfo >= 0 )
    {
LABEL_18:
      if ( !WaitForSingleObject(ProcessInformation.hProcess, 0xFFFFFFFF) )
        goto LABEL_19;
      v13 = GetLastError();
      StorageDeviceInfo = v13;
      if ( v13 > 0 )
        StorageDeviceInfo = (unsigned __int16)v13 | 0x80070000;
      if ( StorageDeviceInfo >= 0 )
      {
LABEL_19:
        ExitCode = 0;
        if ( GetExitCodeProcess(ProcessInformation.hProcess, &ExitCode) )
          goto LABEL_23;
        v14 = GetLastError();
        StorageDeviceInfo = v14;
        if ( v14 > 0 )
          StorageDeviceInfo = (unsigned __int16)v14 | 0x80070000;
        if ( StorageDeviceInfo >= 0 )
        {
LABEL_23:
          GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
          StorageDeviceInfo = Util::WriteUserRegKey(v16, v15, L"OptimizeStorageLastRunHighPart");
          if ( StorageDeviceInfo >= 0 )
            StorageDeviceInfo = Util::WriteUserRegKey(v18, v17, L"OptimizeStorageLastRunLowPart");
        }
      }
    }
  }
  v19 = GetTickCount64();
  v20 = v11 - TickCount64;
  if ( v20 < 0 )
    v21 = (double)(int)(v20 & 1 | ((unsigned __int64)v20 >> 1)) + (double)(int)(v20 & 1 | ((unsigned __int64)v20 >> 1));
  else
    v21 = (double)(int)v20;
  v22 = v21 / 1000.0;
  v23 = v19 - TickCount64;
  if ( v23 < 0 )
    v24 = (double)(int)(v23 & 1 | ((unsigned __int64)v23 >> 1)) + (double)(int)(v23 & 1 | ((unsigned __int64)v23 >> 1));
  else
    v24 = (double)(int)v23;
  v25 = v24 / 1000.0;
  SvcGetStorageDeviceSize(0, v57, 0, &v32, &v38);
  v26 = v38;
  if ( v38.QuadPart > v31.QuadPart )
    *a2 = v38.QuadPart - v31.QuadPart;
  if ( v26.QuadPart > v37.QuadPart )
    v7 = v26.QuadPart - v37.QuadPart;
  LogSpaceFreed((v7 + 0xFFFFF) >> 20);
  v52 = 2;
  if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    v40 = 0x1000000;
    v34 = StorageDeviceInfo;
    v41 = v7;
    v42 = *a2;
    v43 = v31;
    v44 = v32;
    v45 = v25;
    v46 = v22;
    v35 = v5;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
      (unsigned int)&dword_1800BF000,
      (unsigned int)&unk_1800A7E08,
      (unsigned int)v54,
      v28,
      (__int64)&v35,
      (__int64)&v46,
      (__int64)&v45,
      (__int64)&v44,
      (__int64)&v43,
      (__int64)&v42,
      (__int64)&v41,
      (__int64)&v34,
      (__int64)&v40);
  }
  wil::details::CloseProcessInformation((wil::details *)&ProcessInformation, v27);
  _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(&v52);
  return (unsigned int)StorageDeviceInfo;
}

```

## disassembly

```asm
0x180032088  mov     rax, rsp
0x18003208b  push    rbp
0x18003208c  push    rbx
0x18003208d  push    rsi
0x18003208e  push    rdi
0x18003208f  push    r12
0x180032091  push    r13
0x180032093  push    r14
0x180032095  push    r15
0x180032097  lea     rbp, [rax-588h]
0x18003209e  sub     rsp, 648h
0x1800320a5  movaps  xmmword ptr [rax-58h], xmm6
0x1800320a9  movaps  xmmword ptr [rax-68h], xmm7
0x1800320ad  mov     rax, cs:__security_cookie
0x1800320b4  xor     rax, rsp
0x1800320b7  mov     [rbp+580h+var_70], rax
0x1800320be  mov     r15, rdx
0x1800320c1  xor     r13d, r13d
0x1800320c4  mov     [rbp+580h+var_4F8], r13d
0x1800320cb  mov     [rbp+580h+var_4F4], r13b
0x1800320d2  lea     rcx, [rbp+580h+var_4F8]
0x1800320d9  call    ?zInternalStart@?$_TlgActivityBase@V?$TraceLoggingActivity@$1?StorageServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@QEAAXXZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::zInternalStart(void)
0x1800320de  mov     eax, cs:dword_1800BF000
0x1800320e4  cmp     eax, 5
0x1800320e7  jbe     short loc_180032140
0x1800320e9  mov     rdx, 400000000000h
0x1800320f3  lea     rcx, dword_1800BF000
0x1800320fa  call    _tlgKeywordOn
0x1800320ff  test    al, al
0x180032101  jz      short loc_180032140
0x180032103  cmp     [rbp+580h+var_4F4], r13b
0x18003210a  jz      short loc_180032123
0x18003210c  lea     rcx, [rbp+580h+var_4E0]; struct _GUID *
0x180032113  call    ?_tlgGuidIsZero@@YA_NAEBU_GUID@@@Z; _tlgGuidIsZero(_GUID const &)
0x180032118  test    al, al
0x18003211a  lea     r9, [rbp+580h+var_4E0]
0x180032121  jz      short loc_180032126
0x180032123  mov     r9, r13
0x180032126  lea     r8, [rbp+580h+var_4F0]
0x18003212d  lea     rdx, byte_1800A7B91
0x180032134  lea     rcx, dword_1800BF000
0x18003213b  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180032140  mov     dword ptr [rsp+680h+var_610], r13d
0x180032145  mov     qword ptr [rbp+580h+SystemTimeAsFileTime.dwLowDateTime], r13
0x180032149  mov     [r15], r13
0x18003214c  xorps   xmm0, xmm0
0x18003214f  xor     eax, eax
0x180032151  movups  xmmword ptr [rbp+580h+ProcessInformation.hProcess], xmm0
0x180032155  mov     qword ptr [rbp+580h+ProcessInformation.dwProcessId], rax
0x180032159  movups  xmmword ptr [rbp+580h+ProcessInformation.hProcess], xmm0
0x18003215d  mov     qword ptr [rbp+580h+ProcessInformation.dwProcessId], rax
0x180032161  xor     edx, edx; Val
0x180032163  lea     r8d, [rax+68h]; Size
0x180032167  lea     rcx, [rbp+580h+StartupInfo]; void *
0x18003216b  call    memset_0
0x180032170  mov     r12b, r13b
0x180032173  call    cs:__imp_GetTickCount64
0x180032179  mov     r14, rax
0x18003217c  mov     [rsp+680h+var_608], r13
0x180032181  mov     [rbp+580h+var_5D8], r13
0x180032185  mov     [rbp+580h+var_5E0], r13
0x180032189  mov     [rbp+580h+var_600], r13
0x18003218d  mov     rsi, r13
0x180032190  xor     edx, edx; Val
0x180032192  mov     r8d, 454h; Size
0x180032198  lea     rcx, [rbp+580h+var_4CC]; void *
0x18003219f  call    memset_0
0x1800321a4  mov     [rbp+580h+var_4D0], 458h
0x1800321ae  lea     rax, [rbp+580h+var_4D0]
0x1800321b5  mov     qword ptr [rsp+680h+bInheritHandles], rax
0x1800321ba  xor     r9d, r9d
0x1800321bd  xor     r8d, r8d
0x1800321c0  xor     edx, edx
0x1800321c2  call    ?GetStorageDeviceInfo@StorageService@@QEAAJPEAXW4_STORAGE_DEVICE_TYPE@@KPEAU_STORAGE_DEVICE_INFO@@@Z; StorageService::GetStorageDeviceInfo(void *,_STORAGE_DEVICE_TYPE,ulong,_STORAGE_DEVICE_INFO *)
0x1800321c7  mov     ebx, eax
0x1800321c9  test    eax, eax
0x1800321cb  js      loc_18003235D
0x1800321d1  lea     rax, [rsp+680h+var_608]
0x1800321d6  mov     qword ptr [rsp+680h+bInheritHandles], rax
0x1800321db  lea     r9, [rbp+580h+var_600]
0x1800321df  xor     r8d, r8d
0x1800321e2  lea     rdx, [rbp+580h+var_4CC]
0x1800321e9  xor     ecx, ecx
0x1800321eb  call    SvcGetStorageDeviceSize
0x1800321f0  lea     r9, [rsp+680h+var_610]
0x1800321f5  xor     r8d, r8d
0x1800321f8  xor     edx, edx
0x1800321fa  call    ?GetStoragePolicySettings@StorageService@@QEAAJW4_STORAGE_POLICY@@PEBGPEAK@Z; StorageService::GetStoragePolicySettings(_STORAGE_POLICY,ushort const *,ulong *)
0x1800321ff  test    eax, eax
0x180032201  js      short loc_18003223B
0x180032203  cmp     dword ptr [rsp+680h+var_610], 1
0x180032208  jnz     short loc_18003223B
0x18003220a  mov     [rbp+580h+var_500], 1
0x180032215  mov     [rbp+580h+var_510], 18h
0x18003221d  mov     [rbp+580h+var_508], r13d
0x180032221  mov     [rbp+580h+var_504], 0FFFFFFFFh
0x180032228  lea     rdx, [rbp+580h+var_510]; struct _STORAGE_TRIGGER_POLICIES_PARAMETERS *
0x18003222c  lea     rcx, ?g_StorageService@@3VStorageService@@A; this
0x180032233  call    ?TriggerStoragePolicies@StorageService@@QEAAJPEAU_STORAGE_TRIGGER_POLICIES_PARAMETERS@@@Z; StorageService::TriggerStoragePolicies(_STORAGE_TRIGGER_POLICIES_PARAMETERS *)
0x180032238  mov     r12b, 1
0x18003223b  call    cs:__imp_GetTickCount64
0x180032241  mov     rdi, rax
0x180032244  lea     rax, [rbp+580h+var_5E0]
0x180032248  mov     qword ptr [rsp+680h+bInheritHandles], rax
0x18003224d  lea     r9, [rbp+580h+var_600]
0x180032251  xor     r8d, r8d
0x180032254  lea     rdx, [rbp+580h+var_4CC]
0x18003225b  xor     ecx, ecx
0x18003225d  call    SvcGetStorageDeviceSize
0x180032262  lea     rax, [rbp+580h+ProcessInformation]
0x180032266  mov     [rsp+680h+lpProcessInformation], rax; lpProcessInformation
0x18003226b  lea     rax, [rbp+580h+StartupInfo]
0x18003226f  mov     [rsp+680h+lpStartupInfo], rax; lpStartupInfo
0x180032274  mov     [rsp+680h+lpCurrentDirectory], r13; lpCurrentDirectory
0x180032279  mov     [rsp+680h+lpEnvironment], r13; lpEnvironment
0x18003227e  mov     [rsp+680h+dwCreationFlags], 8000000h; dwCreationFlags
0x180032286  mov     [rsp+680h+bInheritHandles], r13d; bInheritHandles
0x18003228b  xor     r9d, r9d; lpThreadAttributes
0x18003228e  xor     r8d, r8d; lpProcessAttributes
0x180032291  lea     rdx, CommandLine; " /AllVolumes /NormalPriority /SlabConso"...
0x180032298  lea     rcx, ApplicationName; "defrag.exe"
0x18003229f  call    cs:__imp_CreateProcessW
0x1800322a5  test    eax, eax
0x1800322a7  jnz     short loc_1800322C6
0x1800322a9  call    cs:__imp_GetLastError
0x1800322af  mov     ebx, eax
0x1800322b1  test    eax, eax
0x1800322b3  jle     short loc_1800322BE
0x1800322b5  movzx   ebx, ax
0x1800322b8  or      ebx, 80070000h
0x1800322be  test    ebx, ebx
0x1800322c0  js      loc_180032360
0x1800322c6  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800322c9  mov     rcx, [rbp+580h+ProcessInformation.hProcess]; hHandle
0x1800322cd  call    cs:__imp_WaitForSingleObject
0x1800322d3  test    eax, eax
0x1800322d5  jz      short loc_1800322F0
0x1800322d7  call    cs:__imp_GetLastError
0x1800322dd  mov     ebx, eax
0x1800322df  test    eax, eax
0x1800322e1  jle     short loc_1800322EC
0x1800322e3  movzx   ebx, ax
0x1800322e6  or      ebx, 80070000h
0x1800322ec  test    ebx, ebx
0x1800322ee  js      short loc_180032360
0x1800322f0  mov     [rbp+580h+ExitCode], r13d
0x1800322f4  lea     rdx, [rbp+580h+ExitCode]; lpExitCode
0x1800322f8  mov     rcx, [rbp+580h+ProcessInformation.hProcess]; hProcess
0x1800322fc  call    cs:__imp_GetExitCodeProcess
0x180032302  test    eax, eax
0x180032304  jnz     short loc_18003231F
0x180032306  call    cs:__imp_GetLastError
0x18003230c  mov     ebx, eax
0x18003230e  test    eax, eax
0x180032310  jle     short loc_18003231B
0x180032312  movzx   ebx, ax
0x180032315  or      ebx, 80070000h
0x18003231b  test    ebx, ebx
0x18003231d  js      short loc_180032360
0x18003231f  lea     rcx, [rbp+580h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180032323  call    cs:__imp_GetSystemTimeAsFileTime
0x180032329  lea     rax, [rbp+580h+SystemTimeAsFileTime.dwHighDateTime]
0x18003232d  mov     qword ptr [rsp+680h+bInheritHandles], rax
0x180032332  lea     r8, aOptimizestorag_1; "OptimizeStorageLastRunHighPart"
0x180032339  call    Util__WriteUserRegKey
0x18003233e  mov     ebx, eax
0x180032340  test    eax, eax
0x180032342  js      short loc_180032360
0x180032344  lea     rax, [rbp+580h+SystemTimeAsFileTime]
0x180032348  mov     qword ptr [rsp+680h+bInheritHandles], rax
0x18003234d  lea     r8, aOptimizestorag_0; "OptimizeStorageLastRunLowPart"
0x180032354  call    Util__WriteUserRegKey
0x180032359  mov     ebx, eax
0x18003235b  jmp     short loc_180032360
0x18003235d  mov     rdi, r14
0x180032360  call    cs:__imp_GetTickCount64
0x180032366  mov     rcx, rax
0x180032369  sub     rdi, r14
0x18003236c  xorps   xmm7, xmm7
0x18003236f  js      short loc_180032378
0x180032371  cvtsi2sd xmm7, rdi
0x180032376  jmp     short loc_18003238D
0x180032378  mov     rax, rdi
0x18003237b  shr     rax, 1
0x18003237e  and     edi, 1
0x180032381  or      rax, rdi
0x180032384  cvtsi2sd xmm7, rax
0x180032389  addsd   xmm7, xmm7
0x18003238d  movsd   xmm0, cs:__real@408f400000000000
0x180032395  divsd   xmm7, xmm0
0x180032399  sub     rcx, r14
0x18003239c  xorps   xmm6, xmm6
0x18003239f  js      short loc_1800323A8
0x1800323a1  cvtsi2sd xmm6, rcx
0x1800323a6  jmp     short loc_1800323BD
0x1800323a8  mov     rax, rcx
0x1800323ab  shr     rax, 1
0x1800323ae  and     ecx, 1
0x1800323b1  or      rax, rcx
0x1800323b4  cvtsi2sd xmm6, rax
0x1800323b9  addsd   xmm6, xmm6
0x1800323bd  divsd   xmm6, xmm0
0x1800323c1  lea     rax, [rbp+580h+var_5D8]
0x1800323c5  mov     qword ptr [rsp+680h+bInheritHandles], rax
0x1800323ca  lea     r9, [rbp+580h+var_600]
0x1800323ce  xor     r8d, r8d
0x1800323d1  lea     rdx, [rbp+580h+var_4CC]
0x1800323d8  xor     ecx, ecx
0x1800323da  call    SvcGetStorageDeviceSize
0x1800323df  mov     rcx, [rbp+580h+var_5D8]
0x1800323e3  cmp     rcx, [rsp+680h+var_608]
0x1800323e8  jbe     short loc_1800323F5
0x1800323ea  mov     rax, rcx
0x1800323ed  sub     rax, [rsp+680h+var_608]
0x1800323f2  mov     [r15], rax
0x1800323f5  cmp     rcx, [rbp+580h+var_5E0]
0x1800323f9  jbe     short loc_180032402
0x1800323fb  mov     rsi, rcx
0x1800323fe  sub     rsi, [rbp+580h+var_5E0]
0x180032402  lea     rcx, [rsi+0FFFFFh]
0x180032409  shr     rcx, 14h
0x18003240d  call    LogSpaceFreed
0x180032412  mov     [rbp+580h+var_4F8], 2
0x18003241c  mov     eax, cs:dword_1800BF000
0x180032422  cmp     eax, 5
0x180032425  jbe     loc_1800324ED
0x18003242b  mov     rdx, 400000000000h
0x180032435  lea     rcx, dword_1800BF000
0x18003243c  call    _tlgKeywordOn
0x180032441  test    al, al
0x180032443  jz      loc_1800324ED
0x180032449  mov     [rbp+580h+var_5B8], 1000000h
0x180032451  mov     [rbp+580h+var_5F4], ebx
0x180032454  mov     [rbp+580h+var_5B0], rsi
0x180032458  mov     rax, [r15]
0x18003245b  mov     [rbp+580h+var_5A8], rax
0x18003245f  mov     rax, [rsp+680h+var_608]
0x180032464  mov     [rbp+580h+var_5A0], rax
0x180032468  mov     rax, [rbp+580h+var_600]
0x18003246c  mov     [rbp+580h+var_598], rax
0x180032470  movsd   [rbp+580h+var_590], xmm6
0x180032475  movsd   [rbp+580h+var_588], xmm7
0x18003247a  movzx   eax, r12b
0x18003247e  mov     [rbp+580h+var_5F0], eax
0x180032481  lea     rax, [rbp+580h+var_5B8]
0x180032485  mov     [rsp+680h+var_620], rax
0x18003248a  lea     rax, [rbp+580h+var_5F4]
0x18003248e  mov     [rsp+680h+var_628], rax
0x180032493  lea     rax, [rbp+580h+var_5B0]
0x180032497  mov     [rsp+680h+var_630], rax
0x18003249c  lea     rax, [rbp+580h+var_5A8]
0x1800324a0  mov     [rsp+680h+lpProcessInformation], rax
0x1800324a5  lea     rax, [rbp+580h+var_5A0]
0x1800324a9  mov     [rsp+680h+lpStartupInfo], rax
0x1800324ae  lea     rax, [rbp+580h+var_598]
0x1800324b2  mov     [rsp+680h+lpCurrentDirectory], rax
0x1800324b7  lea     rax, [rbp+580h+var_590]
0x1800324bb  mov     [rsp+680h+lpEnvironment], rax
0x1800324c0  lea     rax, [rbp+580h+var_588]
0x1800324c4  mov     qword ptr [rsp+680h+dwCreationFlags], rax
0x1800324c9  lea     rax, [rbp+580h+var_5F0]
0x1800324cd  mov     qword ptr [rsp+680h+bInheritHandles], rax
0x1800324d2  lea     r8, [rbp+580h+var_4F0]
0x1800324d9  lea     rdx, unk_1800A7E08
0x1800324e0  lea     rcx, dword_1800BF000
0x1800324e7  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U2@U2@U2@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4444434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1800324ec  nop
0x1800324ed  lea     rcx, [rbp+580h+ProcessInformation]; this
0x1800324f1  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x1800324f6  nop
0x1800324f7  lea     rcx, [rbp+580h+var_4F8]
0x1800324fe  call    ??1?$_TlgActivityBase@V?$TraceLoggingActivity@$1?StorageServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@$0EAAAAAAAAAAA@$04@@IEAA@XZ; _TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>::~_TlgActivityBase<TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider>,70368744177664,5>(void)
0x180032503  mov     eax, ebx
0x180032505  mov     rcx, [rbp+580h+var_70]
0x18003250c  xor     rcx, rsp; StackCookie
0x18003250f  call    __security_check_cookie
0x180032514  lea     r11, [rsp+680h+var_38]
0x18003251c  movaps  xmm6, xmmword ptr [r11-18h]
0x180032521  movaps  xmm7, xmmword ptr [r11-28h]
0x180032526  mov     rsp, r11
0x180032529  pop     r15
0x18003252b  pop     r14
0x18003252d  pop     r13
0x18003252f  pop     r12
0x180032531  pop     rdi
0x180032532  pop     rsi
0x180032533  pop     rbx
0x180032534  pop     rbp
0x180032535  retn
```
