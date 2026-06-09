# GetSsuPath

- ea: `0x180275838`
- end: `0x18027610e`
- name: `GetSsuPath`
- size: `2262`
- prototype: `__int64 __fastcall(wchar_t *)`
- caller_count: `3`
- callee_count: `13`
- tags: `file_ops, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180279074`
- `0x18027a59c`
- `0x18027b984`

## callees

- `0x1800059d0`
- `0x18000a0e8`
- `0x18000c4c4`
- `0x180012460`
- `0x18006618c`
- `0x1800692fc`
- `0x18008b38c`
- `0x18014c4c8`
- `0x1801f250c`
- `0x180275608`
- `0x180275838`
- `0x180276990`
- `0x1802b1010`

## import_xrefs

- `ntdll!RtlFreeHeap` at `0x1802760b8`
- `ntdll!RtlFreeHeap` at `0x1802760b8`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180276010`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1802760d6`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x180276010`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x1802760d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180275ef9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180275ef9`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180275f11`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180275f11`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180275da9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180275dfc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180275da9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180275dfc`

## string_xrefs

- `0x180275c40`: `UpdateAgent`
- `0x180275e8d`: `Failed to get offline servicing stack path`
- `0x1802758bd`: `Unable to load turbostack.dll`
- `0x180276040`: `Failed to copy ssu path.`
- `0x180275d17`: `Microsoft-Windows-ServicingStack,language=neutral,publicKeyToken=31bf3856ad364e35,versionScope=nonSxS,processorArchitecture=amd64`
- `0x180275e3d`: `Turbostack doesn't exist in the caller path (Probably private updateagent testing). Using inbox stack.`
- `0x180275d48`: `Failed to get component version for SSU.`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall GetSsuPath(wchar_t *a1, __int64 a2, _QWORD *a3)
{
  __int64 v6; // rdx
  unsigned int v7; // ebx
  int Turbostack; // eax
  int v9; // ebx
  char v10; // al
  int FunctionPointer; // eax
  __int64 v12; // rdx
  int v13; // eax
  __int64 v14; // rdx
  int v15; // eax
  __int64 v16; // rdx
  int v17; // eax
  __int64 v18; // rdx
  int v19; // eax
  __int64 v20; // rdx
  int v21; // eax
  __int64 v22; // rdx
  int v23; // eax
  __int64 v24; // rdx
  int StackPath; // eax
  __int64 v26; // rdx
  HANDLE ProcessHeap; // rax
  SIZE_T v28; // rdi
  _WORD *v29; // r14
  _WORD *v30; // rsi
  unsigned __int64 v31; // rdi
  __int64 v32; // rax
  __int16 *v33; // rcx
  _WORD *v34; // rdx
  __int16 v35; // r8
  _WORD *v36; // rcx
  __int64 v38; // rdx
  int v39; // eax
  int *v40; // [rsp+20h] [rbp-69h]
  int *v41; // [rsp+20h] [rbp-69h]
  int *v42; // [rsp+20h] [rbp-69h]
  int v43[2]; // [rsp+40h] [rbp-49h] BYREF
  char v44[8]; // [rsp+48h] [rbp-41h] BYREF
  HMODULE hLibModule; // [rsp+50h] [rbp-39h]
  _WORD *v46; // [rsp+58h] [rbp-31h]
  SIZE_T dwBytes[2]; // [rsp+60h] [rbp-29h]
  _WORD *v48; // [rsp+70h] [rbp-19h]
  __int64 v49; // [rsp+78h] [rbp-11h]
  __int64 (*v50)(void); // [rsp+80h] [rbp-9h] BYREF
  __int64 v51; // [rsp+88h] [rbp-1h] BYREF
  __int64 v52; // [rsp+90h] [rbp+7h] BYREF
  LPVOID pv; // [rsp+98h] [rbp+Fh]
  __int64 v54; // [rsp+A0h] [rbp+17h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v49 = -2;
  if ( !a1 )
  {
    v6 = 855;
LABEL_3:
    v7 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v6,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)0x80070057LL,
      (int)v40);
    return v7;
  }
  if ( !a3 )
  {
    v6 = 856;
    goto LABEL_3;
  }
  v44[0] = 0;
  hLibModule = 0;
  Turbostack = LoadTurbostack(0, v44);
  v9 = Turbostack;
  if ( Turbostack < 0 )
    LogAdapter::TraceAtLevelHr<long,>(2, (unsigned int)Turbostack, "Unable to load turbostack.dll");
  v46 = 0;
  v54 = 0;
  if ( v9 < 0 || (v10 = 1, !v44[0]) )
    v10 = 0;
  if ( a2 && v10 )
  {
    v50 = 0;
    FunctionPointer = LoadHelper::GetFunctionPointer((LoadHelper *)v44, "GetIServicingStore", &v50);
    v7 = FunctionPointer;
    if ( FunctionPointer < 0 )
    {
      LODWORD(v50) = FunctionPointer;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get address of function GetIServicingStore.");
        *(_QWORD *)v43 = &v50;
        v40 = v43;
        LOBYTE(v12) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v12,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x367,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)v7,
        (int)v40);
LABEL_104:
      if ( hLibModule )
        FreeLibrary(hLibModule);
      return v7;
    }
    v51 = 0;
    v13 = ((__int64 (__fastcall *)(__int64 *))v50)(&v51);
    v7 = v13;
    if ( v13 < 0 )
    {
      LODWORD(v50) = v13;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get IServicingStore.");
        *(_QWORD *)v43 = &v50;
        v40 = v43;
        LOBYTE(v14) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v14,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x36A,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)v7,
        (int)v40);
      if ( v51 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
      }
      goto LABEL_104;
    }
    LODWORD(v41) = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v51 + 24LL))(v51, 4, 0);
    v7 = v15;
    if ( v15 < 0 )
    {
      LODWORD(v50) = v15;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to initialize IServicingStore.");
        *(_QWORD *)v43 = &v50;
        v41 = v43;
        LOBYTE(v16) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v16,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x371,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)v7,
        (int)v41);
      if ( v51 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
      }
      goto LABEL_104;
    }
    v50 = 0;
    v17 = LoadHelper::GetFunctionPointer((LoadHelper *)v44, "GetIServicingQuerier", &v50);
    v7 = v17;
    if ( v17 < 0 )
    {
      LODWORD(v50) = v17;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get address of function GetIServicingQuerier.");
        *(_QWORD *)v43 = &v50;
        v41 = v43;
        LOBYTE(v18) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v18,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x375,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)v7,
        (int)v41);
      if ( v51 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
      }
      goto LABEL_104;
    }
    v52 = 0;
    v19 = ((__int64 (__fastcall *)(__int64 *))v50)(&v52);
    v7 = v19;
    if ( v19 < 0 )
    {
      LODWORD(v50) = v19;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to get IServicingQuerier.");
        *(_QWORD *)v43 = &v50;
        v41 = v43;
        LOBYTE(v20) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v20,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x378,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)v7,
        (int)v41);
      if ( v52 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        v52 = 0;
      }
      if ( v51 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
      }
      goto LABEL_104;
    }
    LODWORD(v42) = 0;
    v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, const OLECHAR *, __int64))(*(_QWORD *)v52 + 24LL))(
            v52,
            0,
            L"UpdateAgent",
            v51);
    v7 = v21;
    if ( v21 < 0 )
    {
      LODWORD(v50) = v21;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to initialize IServicingQuerier.");
        *(_QWORD *)v43 = &v50;
        v42 = v43;
        LOBYTE(v22) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v22,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x37B,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)v7,
        (int)v42);
      if ( v52 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        v52 = 0;
      }
      if ( v51 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
      }
      goto LABEL_104;
    }
    pv = 0;
    v40 = (int *)&v54;
    v23 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, const wchar_t *))(*(_QWORD *)v52 + 56LL))(
            v52,
            1,
            a2,
            L"Microsoft-Windows-ServicingStack,language=neutral,publicKeyToken=31bf3856ad364e35,versionScope=nonSxS,proces"
             "sorArchitecture=amd64");
    v7 = v23;
    if ( v23 < 0 )
    {
      LODWORD(v50) = v23;
      if ( *(_QWORD *)&LogAdapter::g_Logger )
      {
        LogAdapter::Logger::LogNumObjects<>(
          *(_QWORD *)&LogAdapter::g_Logger,
          0,
          3,
          "Failed to get component version for SSU.");
        *(_QWORD *)v43 = &v50;
        v40 = v43;
        LOBYTE(v24) = 1;
        LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
          *(_QWORD *)&LogAdapter::g_Logger,
          v24,
          3,
          ": {}");
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x382,
        (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
        (const char *)v7,
        (int)v40);
      if ( pv )
      {
        CoTaskMemFree(pv);
        pv = 0;
      }
      if ( v52 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
        v52 = 0;
      }
      if ( v51 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
        v51 = 0;
      }
      goto LABEL_104;
    }
    if ( pv )
    {
      CoTaskMemFree(pv);
      pv = 0;
    }
    if ( v52 )
    {
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v52 + 16LL))(v52);
      v52 = 0;
    }
    if ( v51 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v51 + 16LL))(v51);
  }
  else
  {
    CBSWdsLog(
      0x4000000,
      0,
      0,
      "Turbostack doesn't exist in the caller path (Probably private updateagent testing). Using inbox stack.");
  }
  *(_OWORD *)dwBytes = 0;
  v48 = 0;
  StackPath = Windows::AutoSsShim::GetStackPath(a1);
  v7 = StackPath;
  if ( StackPath < 0 )
  {
    LODWORD(v50) = StackPath;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(
        *(_QWORD *)&LogAdapter::g_Logger,
        0,
        3,
        "Failed to get offline servicing stack path");
      *(_QWORD *)v43 = &v50;
      v40 = v43;
      LOBYTE(v26) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v26,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x391,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v7,
      (int)v40);
    if ( v48 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v48);
    goto LABEL_104;
  }
  ProcessHeap = GetProcessHeap();
  v28 = dwBytes[1];
  v29 = HeapAlloc(ProcessHeap, 0, dwBytes[1]);
  v46 = v29;
  if ( !v29 )
  {
    v7 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x394,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)0x8007000ELL,
      (int)v40);
    if ( v48 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v48);
    goto LABEL_104;
  }
  v30 = v48;
  if ( v48 && (v28 - dwBytes[0] < 2 || v48[dwBytes[0] >> 1]) )
  {
    INTERNAL_ERROR_ACTION(-1073741595);
    JUMPOUT(0x18027610DLL);
  }
  v31 = v28 >> 1;
  if ( !v31 )
  {
    v7 = -2147024809;
    goto LABEL_98;
  }
  if ( v31 > 0x7FFFFFFF )
  {
    v7 = -2147024809;
    *v29 = 0;
LABEL_98:
    LODWORD(v50) = v7;
    if ( *(_QWORD *)&LogAdapter::g_Logger )
    {
      LogAdapter::Logger::LogNumObjects<>(*(_QWORD *)&LogAdapter::g_Logger, 0, 3, "Failed to copy ssu path.");
      *(_QWORD *)v43 = &v50;
      v40 = v43;
      LOBYTE(v38) = 1;
      LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(
        *(_QWORD *)&LogAdapter::g_Logger,
        v38,
        3,
        ": {}");
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x395,
      (unsigned int)"onecore\\base\\cbs\\container\\servicingcontainerhelper.cpp",
      (const char *)v7,
      (int)v40);
    if ( v30 )
      anonymous_namespace_::OurRtlFreeStringRoutine(v30);
    LOBYTE(v39) = RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v29);
    if ( !v39 )
      __fastfail(7u);
    goto LABEL_104;
  }
  v32 = 2147483646;
  v33 = v48;
  v34 = v29;
  do
  {
    if ( !v32 )
      break;
    v35 = *v33;
    if ( !*v33 )
      break;
    ++v33;
    *v34++ = v35;
    --v32;
    --v31;
  }
  while ( v31 );
  v7 = v31 == 0 ? 0x8007007A : 0;
  v36 = v34 - 1;
  if ( v31 )
    v36 = v34;
  *v36 = 0;
  if ( !v31 )
    goto LABEL_98;
  v46 = 0;
  *a3 = v29;
  if ( v30 )
    anonymous_namespace_::OurRtlFreeStringRoutine(v30);
  if ( hLibModule )
    FreeLibrary(hLibModule);
  return 0;
}

```

## disassembly

```asm
0x180275838  push    rbp
0x18027583a  push    rbx
0x18027583b  push    rsi
0x18027583c  push    rdi
0x18027583d  push    r12
0x18027583f  push    r14
0x180275841  push    r15
0x180275843  lea     rbp, [rsp-27h]
0x180275848  sub     rsp, 0B0h
0x18027584f  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x180275857  mov     rax, cs:__security_cookie
0x18027585e  xor     rax, rsp
0x180275861  mov     [rbp+57h+var_38], rax
0x180275865  mov     r15, r8
0x180275868  mov     rdi, rdx
0x18027586b  mov     rsi, rcx
0x18027586e  xor     r12d, r12d
0x180275871  test    rcx, rcx
0x180275874  jnz     short loc_180275898
0x180275876  mov     edx, 357h; void *
0x18027587b  mov     ebx, 80070057h
0x180275880  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180275887  mov     r9d, ebx; char *
0x18027588a  mov     rcx, [rbp+5Fh]; this
0x18027588e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180275893  jmp     loc_1802760E2
0x180275898  test    r15, r15
0x18027589b  jnz     short loc_1802758A4
0x18027589d  mov     edx, 358h
0x1802758a2  jmp     short loc_18027587B
0x1802758a4  mov     [rbp+57h+var_98], r12b
0x1802758a8  mov     [rbp+57h+hLibModule], r12
0x1802758ac  lea     rdx, [rbp+57h+var_98]
0x1802758b0  xor     ecx, ecx
0x1802758b2  call    LoadTurbostack
0x1802758b7  mov     ebx, eax
0x1802758b9  test    eax, eax
0x1802758bb  jns     short loc_1802758D0
0x1802758bd  lea     r8, aUnableToLoadTu; "Unable to load turbostack.dll"
0x1802758c4  mov     edx, eax
0x1802758c6  mov     ecx, 2
0x1802758cb  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1802758d0  mov     [rbp+57h+var_88], r12
0x1802758d4  mov     [rbp+57h+var_40], r12
0x1802758d8  test    ebx, ebx
0x1802758da  js      short loc_1802758E4
0x1802758dc  cmp     [rbp+57h+var_98], r12b
0x1802758e0  mov     al, 1
0x1802758e2  jnz     short loc_1802758E7
0x1802758e4  mov     al, r12b
0x1802758e7  test    rdi, rdi
0x1802758ea  jz      loc_180275E3D
0x1802758f0  test    al, al
0x1802758f2  jz      loc_180275E3D
0x1802758f8  mov     [rbp+57h+var_60], r12
0x1802758fc  lea     r8, [rbp+57h+var_60]; __int64 (**)(void)
0x180275900  lea     rdx, aGetiservicings; "GetIServicingStore"
0x180275907  lea     rcx, [rbp+57h+var_98]; this
0x18027590b  call    ?GetFunctionPointer@LoadHelper@@QEAAJQEBDPEAP6A_JXZ@Z; LoadHelper::GetFunctionPointer(char const * const,__int64 (**)(void))
0x180275910  mov     ebx, eax
0x180275912  test    eax, eax
0x180275914  jns     short loc_180275982
0x180275916  mov     dword ptr [rbp+57h+var_60], eax
0x180275919  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180275920  test    rcx, rcx
0x180275923  jz      short loc_180275964
0x180275925  lea     r9, aFailedToGetAdd_0; "Failed to get address of function GetIS"...
0x18027592c  mov     edi, 3
0x180275931  mov     r8d, edi
0x180275934  xor     edx, edx
0x180275936  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x18027593b  lea     rax, [rbp+57h+var_60]
0x18027593f  mov     qword ptr [rbp+57h+var_A0], rax
0x180275943  lea     rax, [rbp+57h+var_A0]
0x180275947  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x18027594c  lea     r9, asc_1802C6678; ": {}"
0x180275953  mov     r8d, edi
0x180275956  mov     dl, 1
0x180275958  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x18027595f  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180275964  mov     rcx, [rbp+5Fh]; this
0x180275968  mov     r9d, ebx; char *
0x18027596b  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180275972  mov     edx, 367h; void *
0x180275977  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18027597c  nop
0x18027597d  jmp     loc_1802760CD
0x180275982  mov     [rbp+57h+var_58], r12
0x180275986  lea     rcx, [rbp+57h+var_58]
0x18027598a  mov     rax, [rbp+57h+var_60]
0x18027598e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275993  mov     ebx, eax
0x180275995  test    eax, eax
0x180275997  jns     loc_180275A22
0x18027599d  mov     dword ptr [rbp+57h+var_60], eax
0x1802759a0  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802759a7  test    rcx, rcx
0x1802759aa  jz      short loc_1802759EB
0x1802759ac  lea     r9, aFailedToGetIse; "Failed to get IServicingStore."
0x1802759b3  mov     edi, 3
0x1802759b8  mov     r8d, edi
0x1802759bb  xor     edx, edx
0x1802759bd  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x1802759c2  lea     rax, [rbp+57h+var_60]
0x1802759c6  mov     qword ptr [rbp+57h+var_A0], rax
0x1802759ca  lea     rax, [rbp+57h+var_A0]
0x1802759ce  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x1802759d3  lea     r9, asc_1802C6678; ": {}"
0x1802759da  mov     r8d, edi
0x1802759dd  mov     dl, 1
0x1802759df  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x1802759e6  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x1802759eb  mov     rcx, [rbp+5Fh]; this
0x1802759ef  mov     r9d, ebx; char *
0x1802759f2  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x1802759f9  mov     edx, 36Ah; void *
0x1802759fe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180275a03  nop
0x180275a04  mov     rcx, [rbp+57h+var_58]
0x180275a08  test    rcx, rcx
0x180275a0b  jz      short loc_180275A1D
0x180275a0d  mov     rax, [rcx]
0x180275a10  mov     rax, [rax+10h]
0x180275a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275a19  mov     [rbp+57h+var_58], r12
0x180275a1d  jmp     loc_18027597D
0x180275a22  mov     rcx, [rbp+57h+var_58]
0x180275a26  mov     rax, [rcx]
0x180275a29  mov     qword ptr [rsp+0E0h+var_C0], r12
0x180275a2e  xor     r9d, r9d
0x180275a31  xor     r8d, r8d
0x180275a34  lea     edx, [r9+4]
0x180275a38  mov     rax, [rax+18h]
0x180275a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275a41  mov     ebx, eax
0x180275a43  test    eax, eax
0x180275a45  jns     loc_180275AD0
0x180275a4b  mov     dword ptr [rbp+57h+var_60], eax
0x180275a4e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180275a55  test    rcx, rcx
0x180275a58  jz      short loc_180275A99
0x180275a5a  lea     r9, aFailedToInitia_0; "Failed to initialize IServicingStore."
0x180275a61  mov     edi, 3
0x180275a66  mov     r8d, edi
0x180275a69  xor     edx, edx
0x180275a6b  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180275a70  lea     rax, [rbp+57h+var_60]
0x180275a74  mov     qword ptr [rbp+57h+var_A0], rax
0x180275a78  lea     rax, [rbp+57h+var_A0]
0x180275a7c  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180275a81  lea     r9, asc_1802C6678; ": {}"
0x180275a88  mov     r8d, edi
0x180275a8b  mov     dl, 1
0x180275a8d  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180275a94  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180275a99  mov     rcx, [rbp+5Fh]; this
0x180275a9d  mov     r9d, ebx; char *
0x180275aa0  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180275aa7  mov     edx, 371h; void *
0x180275aac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180275ab1  nop
0x180275ab2  mov     rcx, [rbp+57h+var_58]
0x180275ab6  test    rcx, rcx
0x180275ab9  jz      short loc_180275ACB
0x180275abb  mov     rax, [rcx]
0x180275abe  mov     rax, [rax+10h]
0x180275ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275ac7  mov     [rbp+57h+var_58], r12
0x180275acb  jmp     loc_18027597D
0x180275ad0  mov     [rbp+57h+var_60], r12
0x180275ad4  lea     r8, [rbp+57h+var_60]; __int64 (**)(void)
0x180275ad8  lea     rdx, aGetiservicingq; "GetIServicingQuerier"
0x180275adf  lea     rcx, [rbp+57h+var_98]; this
0x180275ae3  call    ?GetFunctionPointer@LoadHelper@@QEAAJQEBDPEAP6A_JXZ@Z; LoadHelper::GetFunctionPointer(char const * const,__int64 (**)(void))
0x180275ae8  mov     ebx, eax
0x180275aea  test    eax, eax
0x180275aec  jns     loc_180275B77
0x180275af2  mov     dword ptr [rbp+57h+var_60], eax
0x180275af5  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180275afc  test    rcx, rcx
0x180275aff  jz      short loc_180275B40
0x180275b01  lea     r9, aFailedToGetAdd_25; "Failed to get address of function GetIS"...
0x180275b08  mov     edi, 3
0x180275b0d  mov     r8d, edi
0x180275b10  xor     edx, edx
0x180275b12  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180275b17  lea     rax, [rbp+57h+var_60]
0x180275b1b  mov     qword ptr [rbp+57h+var_A0], rax
0x180275b1f  lea     rax, [rbp+57h+var_A0]
0x180275b23  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180275b28  lea     r9, asc_1802C6678; ": {}"
0x180275b2f  mov     r8d, edi
0x180275b32  mov     dl, 1
0x180275b34  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180275b3b  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180275b40  mov     rcx, [rbp+5Fh]; this
0x180275b44  mov     r9d, ebx; char *
0x180275b47  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180275b4e  mov     edx, 375h; void *
0x180275b53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180275b58  nop
0x180275b59  mov     rcx, [rbp+57h+var_58]
0x180275b5d  test    rcx, rcx
0x180275b60  jz      short loc_180275B72
0x180275b62  mov     rax, [rcx]
0x180275b65  mov     rax, [rax+10h]
0x180275b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275b6e  mov     [rbp+57h+var_58], r12
0x180275b72  jmp     loc_18027597D
0x180275b77  mov     [rbp+57h+var_50], r12
0x180275b7b  lea     rcx, [rbp+57h+var_50]
0x180275b7f  mov     rax, [rbp+57h+var_60]
0x180275b83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275b88  mov     ebx, eax
0x180275b8a  test    eax, eax
0x180275b8c  jns     loc_180275C30
0x180275b92  mov     dword ptr [rbp+57h+var_60], eax
0x180275b95  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180275b9c  test    rcx, rcx
0x180275b9f  jz      short loc_180275BE0
0x180275ba1  lea     r9, aFailedToGetIse_0; "Failed to get IServicingQuerier."
0x180275ba8  mov     edi, 3
0x180275bad  mov     r8d, edi
0x180275bb0  xor     edx, edx
0x180275bb2  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180275bb7  lea     rax, [rbp+57h+var_60]
0x180275bbb  mov     qword ptr [rbp+57h+var_A0], rax
0x180275bbf  lea     rax, [rbp+57h+var_A0]
0x180275bc3  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180275bc8  lea     r9, asc_1802C6678; ": {}"
0x180275bcf  mov     r8d, edi
0x180275bd2  mov     dl, 1
0x180275bd4  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180275bdb  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180275be0  mov     rcx, [rbp+5Fh]; this
0x180275be4  mov     r9d, ebx; char *
0x180275be7  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180275bee  mov     edx, 378h; void *
0x180275bf3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180275bf8  nop
0x180275bf9  mov     rcx, [rbp+57h+var_50]
0x180275bfd  test    rcx, rcx
0x180275c00  jz      short loc_180275C12
0x180275c02  mov     rax, [rcx]
0x180275c05  mov     rax, [rax+10h]
0x180275c09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275c0e  mov     [rbp+57h+var_50], r12
0x180275c12  mov     rcx, [rbp+57h+var_58]
0x180275c16  test    rcx, rcx
0x180275c19  jz      short loc_180275C2B
0x180275c1b  mov     rax, [rcx]
0x180275c1e  mov     rax, [rax+10h]
0x180275c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275c27  mov     [rbp+57h+var_58], r12
0x180275c2b  jmp     loc_18027597D
0x180275c30  mov     rcx, [rbp+57h+var_50]
0x180275c34  mov     rax, [rcx]
0x180275c37  mov     qword ptr [rsp+0E0h+var_C0], r12
0x180275c3c  mov     r9, [rbp+57h+var_58]
0x180275c40  lea     r8, aUpdateagent; "UpdateAgent"
0x180275c47  xor     edx, edx
0x180275c49  mov     rax, [rax+18h]
0x180275c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275c52  mov     ebx, eax
0x180275c54  test    eax, eax
0x180275c56  jns     loc_180275CFA
0x180275c5c  mov     dword ptr [rbp+57h+var_60], eax
0x180275c5f  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180275c66  test    rcx, rcx
0x180275c69  jz      short loc_180275CAA
0x180275c6b  lea     r9, aFailedToInitia; "Failed to initialize IServicingQuerier."
0x180275c72  mov     edi, 3
0x180275c77  mov     r8d, edi
0x180275c7a  xor     edx, edx
0x180275c7c  call    ??$LogNumObjects@$$V@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBD@Z; LogAdapter::Logger::LogNumObjects<>(bool,LogAdapter::LogLevel,char const * const)
0x180275c81  lea     rax, [rbp+57h+var_60]
0x180275c85  mov     qword ptr [rbp+57h+var_A0], rax
0x180275c89  lea     rax, [rbp+57h+var_A0]
0x180275c8d  mov     qword ptr [rsp+0E0h+var_C0], rax; int
0x180275c92  lea     r9, asc_1802C6678; ": {}"
0x180275c99  mov     r8d, edi
0x180275c9c  mov     dl, 1
0x180275c9e  mov     rcx, cs:?g_Logger@LogAdapter@@3PEAVLogger@1@EA; LogAdapter::Logger * LogAdapter::g_Logger
0x180275ca5  call    ??$LogNumObjects@U?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Logger@LogAdapter@@AEAAJ_NW4LogLevel@1@QEBDAEBU?$FormatHResultWrapper@J@Rtl@WCP@Windows@@@Z; LogAdapter::Logger::LogNumObjects<Windows::WCP::Rtl::FormatHResultWrapper<long>>(bool,LogAdapter::LogLevel,char const * const,Windows::WCP::Rtl::FormatHResultWrapper<long> const &)
0x180275caa  mov     rcx, [rbp+5Fh]; this
0x180275cae  mov     r9d, ebx; char *
0x180275cb1  lea     r8, aOnecoreBaseCbs_9; "onecore\\base\\cbs\\container\\servicin"...
0x180275cb8  mov     edx, 37Bh; void *
0x180275cbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180275cc2  nop
0x180275cc3  mov     rcx, [rbp+57h+var_50]
0x180275cc7  test    rcx, rcx
0x180275cca  jz      short loc_180275CDC
0x180275ccc  mov     rax, [rcx]
0x180275ccf  mov     rax, [rax+10h]
0x180275cd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180275cd8  mov     [rbp+57h+var_50], r12
0x180275cdc  mov     rcx, [rbp+57h+var_58]
0x180275ce0  test    rcx, rcx
0x180275ce3  jz      short loc_180275CF5
  ... truncated ...
```
