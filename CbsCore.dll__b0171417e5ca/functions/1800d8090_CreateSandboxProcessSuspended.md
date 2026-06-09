# CreateSandboxProcessSuspended

- ea: `0x1800d8090`
- end: `0x1800d8a02`
- name: `CreateSandboxProcessSuspended`
- size: `2418`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `11`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180095e58`

## callees

- `0x180033f58`
- `0x18003404c`
- `0x180095e34`
- `0x180098538`
- `0x180099548`
- `0x18009cf78`
- `0x1800d8090`
- `0x1800eb920`
- `0x1800ec920`
- `0x18012b9d0`
- `0x18012ba3c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d827e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d83d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d84ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d88b3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8269`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d827e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d83d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d84ee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8503`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d8714`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800d88b3`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d84da`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d8630`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d84da`
- `api-ms-win-core-processthreads-l1-1-0!InitializeProcThreadAttributeList` at `0x1800d8630`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800d8700`
- `api-ms-win-core-processthreads-l1-1-0!UpdateProcThreadAttribute` at `0x1800d8700`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800d87ab`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800d896f`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800d87ab`
- `api-ms-win-core-processthreads-l1-1-0!DeleteProcThreadAttributeList` at `0x1800d896f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d8232`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d8395`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d8232`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800d8395`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800d889f`
- `api-ms-win-core-processthreads-l1-1-0!CreateProcessW` at `0x1800d889f`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800d8255`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800d83bd`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800d8255`
- `api-ms-win-security-base-l1-1-0!GetKernelObjectSecurity` at `0x1800d83bd`
- `ntdll!RtlFreeHeap` at `0x1800d8210`
- `ntdll!RtlFreeHeap` at `0x1800d832e`
- `ntdll!RtlFreeHeap` at `0x1800d8480`
- `ntdll!RtlFreeHeap` at `0x1800d84ac`
- `ntdll!RtlFreeHeap` at `0x1800d85d4`
- `ntdll!RtlFreeHeap` at `0x1800d8601`
- `ntdll!RtlFreeHeap` at `0x1800d8997`
- `ntdll!RtlFreeHeap` at `0x1800d89c3`
- `ntdll!RtlFreeHeap` at `0x1800d8210`
- `ntdll!RtlFreeHeap` at `0x1800d832e`
- `ntdll!RtlFreeHeap` at `0x1800d8480`
- `ntdll!RtlFreeHeap` at `0x1800d84ac`
- `ntdll!RtlFreeHeap` at `0x1800d85d4`
- `ntdll!RtlFreeHeap` at `0x1800d8601`
- `ntdll!RtlFreeHeap` at `0x1800d8997`
- `ntdll!RtlFreeHeap` at `0x1800d89c3`

## string_xrefs

- `0x1800d8522`: `Unexpected error in InitializeProcThreadAttributeList`
- `0x1800d8663`: `Unexpected error in InitializeProcThreadAttributeList`
- `0x1800d83f0`: `Could not get current process security`
- `0x1800d8738`: `Unable to update process attribute list`
- `0x1800d829d`: `Could not get current process security size`
- `0x1800d8804`: `Failed to impersonate`
- `0x1800d81a6`: `No process main thread handle result specified`

## pseudocode

```c
__int64 __fastcall CreateSandboxProcessSuspended(
        void *a1,
        const WCHAR *a2,
        unsigned __int64 a3,
        HANDLE *a4,
        HANDLE *a5)
{
  unsigned int v9; // edi
  __int64 v10; // rdx
  int v11; // eax
  HANDLE CurrentProcess; // rax
  signed int LastError; // edi
  unsigned int v15; // eax
  int v16; // eax
  PSECURITY_DESCRIPTOR v17; // r8
  DWORD v18; // ebx
  HANDLE v19; // rax
  PSECURITY_DESCRIPTOR v20; // rdi
  signed int v21; // esi
  unsigned int v22; // eax
  __int64 v23; // rdx
  unsigned int v24; // esi
  int v25; // eax
  int v26; // eax
  unsigned int v27; // eax
  int v28; // eax
  int v29; // eax
  unsigned int v30; // eax
  signed int v31; // esi
  unsigned int v32; // eax
  int v33; // eax
  signed int v34; // esi
  unsigned int v35; // eax
  int v36; // eax
  int v37; // eax
  int lpnLengthNeeded; // [rsp+20h] [rbp-E0h]
  unsigned int lpnLengthNeededa; // [rsp+20h] [rbp-E0h]
  unsigned int lpnLengthNeededb; // [rsp+20h] [rbp-E0h]
  unsigned int lpnLengthNeededc; // [rsp+20h] [rbp-E0h]
  unsigned int lpnLengthNeededd; // [rsp+20h] [rbp-E0h]
  unsigned int v43[2]; // [rsp+50h] [rbp-B0h] BYREF
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v45; // [rsp+60h] [rbp-A0h]
  DWORD nLengthNeeded; // [rsp+68h] [rbp-98h] BYREF
  ULONG_PTR Size; // [rsp+70h] [rbp-90h] BYREF
  __int128 Value; // [rsp+78h] [rbp-88h] BYREF
  __int64 v49; // [rsp+88h] [rbp-78h]
  struct _SECURITY_ATTRIBUTES ProcessAttributes; // [rsp+90h] [rbp-70h] BYREF
  struct _PROCESS_INFORMATION ProcessInformation; // [rsp+A8h] [rbp-58h] BYREF
  struct _STARTUPINFOW StartupInfo; // [rsp+C0h] [rbp-40h] BYREF
  PVOID v53; // [rsp+128h] [rbp+28h]
  int v54; // [rsp+130h] [rbp+30h] BYREF
  PVOID P[2]; // [rsp+138h] [rbp+38h] BYREF
  DWORD v56; // [rsp+148h] [rbp+48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  memset_0(&StartupInfo, 0, 0x70u);
  *(_QWORD *)&ProcessAttributes.nLength = 24;
  Size = 0;
  v49 = 0;
  P[0] = 0;
  P[1] = 0;
  pSecurityDescriptor = 0;
  v45 = 0;
  nLengthNeeded = 0;
  v56 = 0;
  memset(&ProcessInformation, 0, sizeof(ProcessInformation));
  *(_OWORD *)&ProcessAttributes.lpSecurityDescriptor = 0;
  Value = 0;
  if ( !a4 )
  {
    v9 = -2147467261;
    v54 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No process handle result specified");
      *(_QWORD *)v43 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v43);
    }
    v10 = 94;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v10,
      (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
      (const char *)0x80004003LL,
      lpnLengthNeeded);
LABEL_10:
    if ( P[0] )
    {
      LOBYTE(v11) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
      if ( !v11 )
        __fastfail(7u);
    }
    return v9;
  }
  if ( !a5 )
  {
    v9 = -2147467261;
    v54 = -2147467261;
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"No process main thread handle result specified");
      *(_QWORD *)v43 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {}",
        (__int64)v43);
    }
    v10 = 95;
    goto LABEL_9;
  }
  *a4 = 0;
  *a5 = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !GetKernelObjectSecurity(CurrentProcess, 4u, 0, 0, &nLengthNeeded) && GetLastError() != 122 )
  {
    LastError = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Could not get current process security size");
      if ( LastError > 0 )
        v15 = (unsigned __int16)LastError | 0x80070000;
      else
        v15 = LastError;
      v54 = v15;
      *(_QWORD *)v43 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v43);
    }
    if ( LastError )
    {
      v9 = wil::details::in1diag3::Return_Win32(
             retaddr,
             (void *)0x73,
             (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
             (const char *)(unsigned int)LastError,
             lpnLengthNeededa);
      goto LABEL_10;
    }
    if ( P[0] )
    {
      LOBYTE(v16) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
      if ( !v16 )
LABEL_101:
        __fastfail(7u);
    }
    return 0;
  }
  if ( !Windows::AutoHeapBlockPtr<_SECURITY_DESCRIPTOR>::AllocateBytes(&pSecurityDescriptor, nLengthNeeded) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x76,
      (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
      (const char *)0x8007000ELL,
      lpnLengthNeededa);
    v17 = pSecurityDescriptor;
    if ( pSecurityDescriptor )
    {
LABEL_57:
      LOBYTE(v28) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v17);
      if ( !v28 )
        __fastfail(7u);
      goto LABEL_59;
    }
    goto LABEL_59;
  }
  v18 = nLengthNeeded;
  v19 = GetCurrentProcess();
  v20 = pSecurityDescriptor;
  if ( !GetKernelObjectSecurity(v19, 4u, pSecurityDescriptor, v18, &v56) )
  {
    v21 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Could not get current process security");
      if ( v21 > 0 )
        v22 = (unsigned __int16)v21 | 0x80070000;
      else
        v22 = v21;
      v54 = v22;
      *(_QWORD *)v43 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v43);
    }
    if ( v21 )
    {
      v23 = 126;
LABEL_37:
      v24 = wil::details::in1diag3::Return_Win32(
              retaddr,
              (void *)v23,
              (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
              (const char *)(unsigned int)v21,
              lpnLengthNeededb);
      goto LABEL_38;
    }
    goto LABEL_96;
  }
  ProcessAttributes.lpSecurityDescriptor = v20;
  if ( !InitializeProcThreadAttributeList(0, 1u, 0, &Size) && GetLastError() != 122 )
  {
    v21 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unexpected error in InitializeProcThreadAttributeList");
      if ( v21 > 0 )
        v27 = (unsigned __int16)v21 | 0x80070000;
      else
        v27 = v21;
      v54 = v27;
      *(_QWORD *)v43 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v43);
    }
    if ( v21 )
    {
      v23 = 134;
      goto LABEL_37;
    }
LABEL_96:
    if ( v20 )
    {
      LOBYTE(v36) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
      if ( !v36 )
        __fastfail(7u);
    }
    if ( P[0] )
    {
      LOBYTE(v37) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
      if ( !v37 )
        goto LABEL_101;
    }
    return 0;
  }
  if ( !Windows::AutoHeapBlockPtr<_PROC_THREAD_ATTRIBUTE_LIST>::AllocateBytes(P, Size) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
      (const char *)0x8007000ELL,
      lpnLengthNeededb);
    if ( v20 )
    {
      v17 = v20;
      goto LABEL_57;
    }
LABEL_59:
    if ( P[0] )
    {
      LOBYTE(v29) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
      if ( !v29 )
        __fastfail(7u);
    }
    return 2147942414LL;
  }
  if ( !InitializeProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)P[0], 1u, 0, &Size) )
  {
    v21 = GetLastError();
    if ( LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        (__int64)LogAdapter::g_Logger,
        0,
        3,
        (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unexpected error in InitializeProcThreadAttributeList");
      if ( v21 > 0 )
        v30 = (unsigned __int16)v21 | 0x80070000;
      else
        v30 = v21;
      v54 = v30;
      *(_QWORD *)v43 = &v54;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        (__int64)LogAdapter::g_Logger,
        1,
        3,
        (__int64)": {0}",
        (__int64)v43);
    }
    if ( v21 )
    {
      v23 = 141;
      goto LABEL_37;
    }
    goto LABEL_96;
  }
  Value = a3;
  v49 = 0;
  if ( UpdateProcThreadAttribute((LPPROC_THREAD_ATTRIBUTE_LIST)P[0], 0, 0x20009u, &Value, 0x18u, 0, 0) )
  {
    StartupInfo.cb = 112;
    StartupInfo.lpDesktop = L"winsta0\\default";
    v53 = P[0];
    pSecurityDescriptor = a1;
    LOBYTE(v45) = 0;
    v33 = NestableImpersonator::Impersonate((NestableImpersonator *)&pSecurityDescriptor);
    v24 = v33;
    if ( v33 < 0 )
    {
      v54 = v33;
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Failed to impersonate");
        *(_QWORD *)v43 = &v54;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {}",
          (__int64)v43);
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
        (const char *)v24,
        lpnLengthNeededc);
      goto LABEL_84;
    }
    if ( CreateProcessW(a2, 0, &ProcessAttributes, 0, 0, 0x80004u, 0, 0, &StartupInfo, &ProcessInformation) )
    {
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&pSecurityDescriptor);
      *a4 = ProcessInformation.hProcess;
      *a5 = ProcessInformation.hThread;
    }
    else
    {
      v34 = GetLastError();
      if ( LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          (__int64)LogAdapter::g_Logger,
          0,
          3,
          (struct Windows::Rtl::IRtlFormattedOutputStream *)"Could not start sandbox process");
        if ( v34 > 0 )
          v35 = (unsigned __int16)v34 | 0x80070000;
        else
          v35 = v34;
        v54 = v35;
        *(_QWORD *)v43 = &v54;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          (__int64)LogAdapter::g_Logger,
          1,
          3,
          (__int64)": {0}",
          (__int64)v43);
      }
      if ( v34 )
      {
        v24 = wil::details::in1diag3::Return_Win32(
                retaddr,
                (void *)0xB6,
                (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
                (const char *)(unsigned int)v34,
                lpnLengthNeededd);
LABEL_84:
        ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&pSecurityDescriptor);
        goto LABEL_79;
      }
      ImpersonatorBase::Unimpersonate((ImpersonatorBase *)&pSecurityDescriptor);
    }
LABEL_95:
    DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)P[0]);
    goto LABEL_96;
  }
  v31 = GetLastError();
  if ( LogAdapter::g_Logger )
  {
    LogAdapter::Logger::LogNumObjects<>(
      (__int64)LogAdapter::g_Logger,
      0,
      3,
      (struct Windows::Rtl::IRtlFormattedOutputStream *)"Unable to update process attribute list");
    if ( v31 > 0 )
      v32 = (unsigned __int16)v31 | 0x80070000;
    else
      v32 = v31;
    v54 = v32;
    *(_QWORD *)v43 = &v54;
    LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
      (__int64)LogAdapter::g_Logger,
      1,
      3,
      (__int64)": {0}",
      (__int64)v43);
  }
  if ( !v31 )
    goto LABEL_95;
  v24 = wil::details::in1diag3::Return_Win32(
          retaddr,
          (void *)0xA1,
          (unsigned int)"onecore\\base\\cbs\\core\\sandboxhelper.cpp",
          (const char *)(unsigned int)v31,
          lpnLengthNeededc);
LABEL_79:
  DeleteProcThreadAttributeList((LPPROC_THREAD_ATTRIBUTE_LIST)P[0]);
LABEL_38:
  if ( v20 )
  {
    LOBYTE(v25) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v20);
    if ( !v25 )
      __fastfail(7u);
  }
  if ( P[0] )
  {
    LOBYTE(v26) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P[0]);
    if ( !v26 )
      __fastfail(7u);
  }
  return v24;
}

```

## disassembly

```asm
0x1800d8090  mov     [rsp-8+arg_0], rbx
0x1800d8095  push    rbp
0x1800d8096  push    rsi
0x1800d8097  push    rdi
0x1800d8098  push    r12
0x1800d809a  push    r13
0x1800d809c  push    r14
0x1800d809e  push    r15
0x1800d80a0  lea     rbp, [rsp-60h]
0x1800d80a5  sub     rsp, 160h
0x1800d80ac  mov     rax, cs:__security_cookie
0x1800d80b3  xor     rax, rsp
0x1800d80b6  mov     [rbp+90h+var_40], rax
0x1800d80ba  mov     r14, [rbp+90h+arg_20]
0x1800d80c1  mov     r13, rdx
0x1800d80c4  xor     edx, edx; Val
0x1800d80c6  mov     r12, r8
0x1800d80c9  mov     rsi, rcx
0x1800d80cc  mov     r15, r9
0x1800d80cf  lea     rcx, [rbp+90h+StartupInfo]; void *
0x1800d80d3  lea     r8d, [rdx+70h]; Size
0x1800d80d7  call    memset_0
0x1800d80dc  xor     ebx, ebx
0x1800d80de  mov     qword ptr [rbp+90h+ProcessAttributes.nLength], 18h
0x1800d80e6  xor     eax, eax
0x1800d80e8  mov     [rsp+190h+Size], rbx
0x1800d80ed  mov     qword ptr [rbp+90h+ProcessInformation.dwProcessId], rax
0x1800d80f1  xorps   xmm0, xmm0
0x1800d80f4  mov     [rbp+90h+var_108], rax
0x1800d80f8  xorps   xmm1, xmm1
0x1800d80fb  mov     [rbp+90h+P], rbx
0x1800d80ff  mov     [rbp+90h+var_50], rbx
0x1800d8103  mov     [rsp+190h+pSecurityDescriptor], rbx
0x1800d8108  mov     [rsp+190h+var_130], rbx
0x1800d810d  mov     [rsp+190h+nLengthNeeded], ebx
0x1800d8111  mov     [rbp+90h+var_48], ebx
0x1800d8114  movups  xmmword ptr [rbp+90h+ProcessInformation.hProcess], xmm0
0x1800d8118  movups  xmmword ptr [rbp+90h+ProcessAttributes.lpSecurityDescriptor], xmm0
0x1800d811c  movups  [rsp+190h+Value], xmm1
0x1800d8121  test    r15, r15
0x1800d8124  jnz     short loc_1800D8180
0x1800d8126  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d812d  mov     edi, 80004003h
0x1800d8132  mov     [rbp+90h+var_60], edi
0x1800d8135  test    rcx, rcx
0x1800d8138  jz      short loc_1800D8179
0x1800d813a  lea     ebx, [rax+3]
0x1800d813d  xor     edx, edx
0x1800d813f  mov     r8d, ebx
0x1800d8142  lea     r9, aNoProcessHandl; "No process handle result specified"
0x1800d8149  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d814e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d8155  lea     rax, [rbp+90h+var_60]
0x1800d8159  mov     qword ptr [rsp+190h+var_140], rax
0x1800d815e  lea     r9, asc_1802EE7AC; ": {}"
0x1800d8165  lea     rax, [rsp+190h+var_140]
0x1800d816a  mov     r8d, ebx
0x1800d816d  mov     dl, 1
0x1800d816f  mov     [rsp+190h+lpnLengthNeeded], rax
0x1800d8174  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d8179  mov     edx, 5Eh ; '^'
0x1800d817e  jmp     short loc_1800D81E2
0x1800d8180  test    r14, r14
0x1800d8183  jnz     loc_1800D822C
0x1800d8189  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d8190  mov     edi, 80004003h
0x1800d8195  mov     [rbp+90h+var_60], edi
0x1800d8198  test    rcx, rcx
0x1800d819b  jz      short loc_1800D81DD
0x1800d819d  lea     ebx, [r14+3]
0x1800d81a1  xor     edx, edx
0x1800d81a3  mov     r8d, ebx
0x1800d81a6  lea     r9, aNoProcessMainT; "No process main thread handle result sp"...
0x1800d81ad  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d81b2  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d81b9  lea     rax, [rbp+90h+var_60]
0x1800d81bd  mov     qword ptr [rsp+190h+var_140], rax
0x1800d81c2  lea     r9, asc_1802EE7AC; ": {}"
0x1800d81c9  lea     rax, [rsp+190h+var_140]
0x1800d81ce  mov     r8d, ebx
0x1800d81d1  mov     dl, 1
0x1800d81d3  mov     [rsp+190h+lpnLengthNeeded], rax; int
0x1800d81d8  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d81dd  mov     edx, 5Fh ; '_'; void *
0x1800d81e2  mov     rcx, [rbp+98h]; this
0x1800d81e9  lea     r8, aOnecoreBaseCbs_150; "onecore\\base\\cbs\\core\\sandboxhelper"...
0x1800d81f0  mov     r9d, edi; char *
0x1800d81f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d81f8  mov     r8, [rbp+90h+P]; P
0x1800d81fc  test    r8, r8
0x1800d81ff  jz      short loc_1800D8225
0x1800d8201  mov     rcx, gs:60h
0x1800d820a  xor     edx, edx; Flags
0x1800d820c  mov     rcx, [rcx+30h]; HeapHandle
0x1800d8210  call    cs:__imp_RtlFreeHeap
0x1800d8217  nop     dword ptr [rax+rax+00h]
0x1800d821c  test    eax, eax
0x1800d821e  jnz     short loc_1800D8225
0x1800d8220  lea     ecx, [rax+7]
0x1800d8223  int     29h; Win8: RtlFailFast(ecx)
0x1800d8225  mov     eax, edi
0x1800d8227  jmp     loc_1800D89DA
0x1800d822c  mov     [r15], rbx
0x1800d822f  mov     [r14], rbx
0x1800d8232  call    cs:__imp_GetCurrentProcess
0x1800d8239  nop     dword ptr [rax+rax+00h]
0x1800d823e  xor     r9d, r9d; nLength
0x1800d8241  xor     r8d, r8d; pSecurityDescriptor
0x1800d8244  mov     rcx, rax; Handle
0x1800d8247  lea     rax, [rsp+190h+nLengthNeeded]
0x1800d824c  mov     [rsp+190h+lpnLengthNeeded], rax; int
0x1800d8251  lea     edx, [r9+4]; RequestedInformation
0x1800d8255  call    cs:__imp_GetKernelObjectSecurity
0x1800d825c  nop     dword ptr [rax+rax+00h]
0x1800d8261  test    eax, eax
0x1800d8263  jnz     loc_1800D834A
0x1800d8269  call    cs:__imp_GetLastError
0x1800d8270  nop     dword ptr [rax+rax+00h]
0x1800d8275  cmp     eax, 7Ah ; 'z'
0x1800d8278  jz      loc_1800D834A
0x1800d827e  call    cs:__imp_GetLastError
0x1800d8285  nop     dword ptr [rax+rax+00h]
0x1800d828a  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d8291  mov     edi, eax
0x1800d8293  test    rcx, rcx
0x1800d8296  jz      short loc_1800D82EC
0x1800d8298  mov     ebx, 3
0x1800d829d  lea     r9, aCouldNotGetCur; "Could not get current process security "...
0x1800d82a4  mov     r8d, ebx
0x1800d82a7  xor     edx, edx
0x1800d82a9  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d82ae  test    edi, edi
0x1800d82b0  jg      short loc_1800D82B6
0x1800d82b2  mov     eax, edi
0x1800d82b4  jmp     short loc_1800D82BE
0x1800d82b6  movzx   eax, di
0x1800d82b9  or      eax, 80070000h
0x1800d82be  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d82c5  lea     r9, a0; ": {0}"
0x1800d82cc  mov     [rbp+90h+var_60], eax
0x1800d82cf  mov     r8d, ebx
0x1800d82d2  lea     rax, [rbp+90h+var_60]
0x1800d82d6  mov     dl, 1
0x1800d82d8  mov     qword ptr [rsp+190h+var_140], rax
0x1800d82dd  lea     rax, [rsp+190h+var_140]
0x1800d82e2  mov     [rsp+190h+lpnLengthNeeded], rax; unsigned int
0x1800d82e7  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d82ec  test    edi, edi
0x1800d82ee  jz      short loc_1800D8312
0x1800d82f0  mov     rcx, [rbp+98h]; this
0x1800d82f7  lea     r8, aOnecoreBaseCbs_150; "onecore\\base\\cbs\\core\\sandboxhelper"...
0x1800d82fe  mov     r9d, edi; char *
0x1800d8301  mov     edx, 73h ; 's'; void *
0x1800d8306  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d830b  mov     edi, eax
0x1800d830d  jmp     loc_1800D81F8
0x1800d8312  mov     r8, [rbp+90h+P]; P
0x1800d8316  test    r8, r8
0x1800d8319  jz      loc_1800D89D8
0x1800d831f  mov     rcx, gs:60h
0x1800d8328  xor     edx, edx; Flags
0x1800d832a  mov     rcx, [rcx+30h]; HeapHandle
0x1800d832e  call    cs:__imp_RtlFreeHeap
0x1800d8335  nop     dword ptr [rax+rax+00h]
0x1800d833a  test    eax, eax
0x1800d833c  jnz     loc_1800D89D8
0x1800d8342  lea     ecx, [rax+7]
0x1800d8345  jmp     loc_1800D89D6
0x1800d834a  mov     edx, [rsp+190h+nLengthNeeded]
0x1800d834e  lea     rcx, [rsp+190h+pSecurityDescriptor]
0x1800d8353  call    ?AllocateBytes@?$AutoHeapBlockPtr@U_SECURITY_DESCRIPTOR@@@Windows@@QEAAPEAU_SECURITY_DESCRIPTOR@@_K@Z; Windows::AutoHeapBlockPtr<_SECURITY_DESCRIPTOR>::AllocateBytes(unsigned __int64)
0x1800d8358  test    rax, rax
0x1800d835b  jnz     short loc_1800D8391
0x1800d835d  mov     rcx, [rbp+98h]; this
0x1800d8364  lea     r8, aOnecoreBaseCbs_150; "onecore\\base\\cbs\\core\\sandboxhelper"...
0x1800d836b  mov     r9d, 8007000Eh; char *
0x1800d8371  lea     edx, [rax+76h]; void *
0x1800d8374  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800d8379  mov     r8, [rsp+190h+pSecurityDescriptor]
0x1800d837e  mov     ebx, 7
0x1800d8383  test    r8, r8
0x1800d8386  jz      loc_1800D85E9
0x1800d838c  jmp     loc_1800D85C5
0x1800d8391  mov     ebx, [rsp+190h+nLengthNeeded]
0x1800d8395  call    cs:__imp_GetCurrentProcess
0x1800d839c  nop     dword ptr [rax+rax+00h]
0x1800d83a1  mov     rdi, [rsp+190h+pSecurityDescriptor]
0x1800d83a6  lea     rcx, [rbp+90h+var_48]
0x1800d83aa  mov     [rsp+190h+lpnLengthNeeded], rcx; int
0x1800d83af  mov     r9d, ebx; nLength
0x1800d83b2  mov     rcx, rax; Handle
0x1800d83b5  mov     r8, rdi; pSecurityDescriptor
0x1800d83b8  mov     edx, 4; RequestedInformation
0x1800d83bd  call    cs:__imp_GetKernelObjectSecurity
0x1800d83c4  nop     dword ptr [rax+rax+00h]
0x1800d83c9  test    eax, eax
0x1800d83cb  jnz     loc_1800D84C8
0x1800d83d1  call    cs:__imp_GetLastError
0x1800d83d8  nop     dword ptr [rax+rax+00h]
0x1800d83dd  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d83e4  mov     esi, eax
0x1800d83e6  test    rcx, rcx
0x1800d83e9  jz      short loc_1800D843F
0x1800d83eb  mov     ebx, 3
0x1800d83f0  lea     r9, aCouldNotGetCur_0; "Could not get current process security"
0x1800d83f7  mov     r8d, ebx
0x1800d83fa  xor     edx, edx
0x1800d83fc  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d8401  test    esi, esi
0x1800d8403  jg      short loc_1800D8409
0x1800d8405  mov     eax, esi
0x1800d8407  jmp     short loc_1800D8411
0x1800d8409  movzx   eax, si
0x1800d840c  or      eax, 80070000h
0x1800d8411  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d8418  lea     r9, a0; ": {0}"
0x1800d841f  mov     [rbp+90h+var_60], eax
0x1800d8422  mov     r8d, ebx
0x1800d8425  lea     rax, [rbp+90h+var_60]
0x1800d8429  mov     dl, 1
0x1800d842b  mov     qword ptr [rsp+190h+var_140], rax
0x1800d8430  lea     rax, [rsp+190h+var_140]
0x1800d8435  mov     [rsp+190h+lpnLengthNeeded], rax; unsigned int
0x1800d843a  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d843f  test    esi, esi
0x1800d8441  jz      loc_1800D897B
0x1800d8447  mov     edx, 7Eh ; '~'; void *
0x1800d844c  mov     rcx, [rbp+98h]; this
0x1800d8453  lea     r8, aOnecoreBaseCbs_150; "onecore\\base\\cbs\\core\\sandboxhelper"...
0x1800d845a  mov     r9d, esi; char *
0x1800d845d  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800d8462  mov     esi, eax
0x1800d8464  mov     ebx, 7
0x1800d8469  test    rdi, rdi
0x1800d846c  jz      short loc_1800D8494
0x1800d846e  mov     rcx, gs:60h
0x1800d8477  mov     r8, rdi; P
0x1800d847a  xor     edx, edx; Flags
0x1800d847c  mov     rcx, [rcx+30h]; HeapHandle
0x1800d8480  call    cs:__imp_RtlFreeHeap
0x1800d8487  nop     dword ptr [rax+rax+00h]
0x1800d848c  test    eax, eax
0x1800d848e  jnz     short loc_1800D8494
0x1800d8490  mov     ecx, ebx
0x1800d8492  int     29h; Win8: RtlFailFast(ecx)
0x1800d8494  mov     r8, [rbp+90h+P]; P
0x1800d8498  test    r8, r8
0x1800d849b  jz      short loc_1800D84C1
0x1800d849d  mov     rcx, gs:60h
0x1800d84a6  xor     edx, edx; Flags
0x1800d84a8  mov     rcx, [rcx+30h]; HeapHandle
0x1800d84ac  call    cs:__imp_RtlFreeHeap
0x1800d84b3  nop     dword ptr [rax+rax+00h]
0x1800d84b8  test    eax, eax
0x1800d84ba  jnz     short loc_1800D84C1
0x1800d84bc  mov     rcx, rbx
0x1800d84bf  int     29h; Win8: RtlFailFast(ecx)
0x1800d84c1  mov     eax, esi
0x1800d84c3  jmp     loc_1800D89DA
0x1800d84c8  xor     r8d, r8d; dwFlags
0x1800d84cb  mov     [rbp+90h+ProcessAttributes.lpSecurityDescriptor], rdi
0x1800d84cf  lea     r9, [rsp+190h+Size]; lpSize
0x1800d84d4  xor     ecx, ecx; lpAttributeList
0x1800d84d6  lea     edx, [r8+1]; dwAttributeCount
0x1800d84da  call    cs:__imp_InitializeProcThreadAttributeList
0x1800d84e1  nop     dword ptr [rax+rax+00h]
0x1800d84e6  test    eax, eax
0x1800d84e8  jnz     loc_1800D8583
0x1800d84ee  call    cs:__imp_GetLastError
0x1800d84f5  nop     dword ptr [rax+rax+00h]
0x1800d84fa  cmp     eax, 7Ah ; 'z'
0x1800d84fd  jz      loc_1800D8583
0x1800d8503  call    cs:__imp_GetLastError
0x1800d850a  nop     dword ptr [rax+rax+00h]
0x1800d850f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d8516  mov     esi, eax
0x1800d8518  test    rcx, rcx
0x1800d851b  jz      short loc_1800D8571
0x1800d851d  mov     ebx, 3
0x1800d8522  lea     r9, aUnexpectedErro; "Unexpected error in InitializeProcThrea"...
0x1800d8529  mov     r8d, ebx
0x1800d852c  xor     edx, edx
0x1800d852e  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1800d8533  test    esi, esi
0x1800d8535  jg      short loc_1800D853B
0x1800d8537  mov     eax, esi
0x1800d8539  jmp     short loc_1800D8543
0x1800d853b  movzx   eax, si
0x1800d853e  or      eax, 80070000h
0x1800d8543  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1800d854a  lea     r9, a0; ": {0}"
0x1800d8551  mov     [rbp+90h+var_60], eax
0x1800d8554  mov     r8d, ebx
0x1800d8557  lea     rax, [rbp+90h+var_60]
0x1800d855b  mov     dl, 1
0x1800d855d  mov     qword ptr [rsp+190h+var_140], rax
0x1800d8562  lea     rax, [rsp+190h+var_140]
0x1800d8567  mov     [rsp+190h+lpnLengthNeeded], rax
0x1800d856c  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1800d8571  test    esi, esi
  ... truncated ...
```
