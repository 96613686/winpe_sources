# CPenProcess::EnsureRunning(CPenProcessStartInfo const *,int,int)

- ea: `0x180015660`
- end: `0x1800163b7`
- name: `?EnsureRunning@CPenProcess@@QEAAHPEBUCPenProcessStartInfo@@HH@Z`
- size: `3415`
- prototype: `__int64 __fastcall(CPenProcess *__hidden this, const struct CPenProcessStartInfo *, int, int)`
- caller_count: `2`
- callee_count: `13`
- tags: `loader_planting, service_task`

## callers

- `0x18000fa00`
- `0x180014d40`

## callees

- `0x1800023cc`
- `0x180002cd0`
- `0x180012320`
- `0x180012dc0`
- `0x180015660`
- `0x180016934`
- `0x18001bbe0`
- `0x18002b404`
- `0x18002b4cc`
- `0x18002d378`
- `0x18002d9e0`
- `0x18002dabc`
- `0x180031010`

## import_xrefs

- `ntdll!EtwEventWriteTransfer` at `0x1800157e1`
- `ntdll!EtwEventWriteTransfer` at `0x180015942`
- `ntdll!EtwEventWriteTransfer` at `0x180015d30`
- `ntdll!EtwEventWriteTransfer` at `0x180015ea0`
- `ntdll!EtwEventWriteTransfer` at `0x180016250`
- `ntdll!EtwEventWriteTransfer` at `0x1800157e1`
- `ntdll!EtwEventWriteTransfer` at `0x180015942`
- `ntdll!EtwEventWriteTransfer` at `0x180015d30`
- `ntdll!EtwEventWriteTransfer` at `0x180015ea0`
- `ntdll!EtwEventWriteTransfer` at `0x180016250`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001581f`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x18001581f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800160cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800160cc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158ac`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015846`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800158ac`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800160af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800160d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800160af`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800160d9`
- `USER32!GetSystemMetrics` at `0x180016292`
- `USER32!GetSystemMetrics` at `0x180016292`

## string_xrefs

- `0x180015853`: `PENSERVICE_CPenProcess::EnsureRunning`
- `0x1800159cc`: `PENSERVICE_CPenProcess::EnsureRunning`
- `0x180015b1a`: `PENSERVICE_CPenProcess::EnsureRunning`
- `0x180015c17`: `PENSERVICE_CPenProcess::EnsureRunning`
- `0x180015d95`: `PENSERVICE_CPenProcess::EnsureRunning`
- `0x18001600f`: `PENSERVICE_CPenProcess::EnsureRunning`
- `0x180016141`: `PENSERVICE_CPenProcess::EnsureRunning`
- `0x180016332`: `PENSERVICE_CPenProcess::EnsureRunning`
- `0x18001637c`: `PENSERVICE_CPenProcess::EnsureRunning`
- `0x180015b6b`: `Process already running.`

## pseudocode

```c
__int64 __fastcall CPenProcess::EnsureRunning(CPenProcess *this, const struct CPenProcessStartInfo *a2, int a3, int a4)
{
  __int64 v6; // rcx
  const wchar_t *v9; // rcx
  __int64 v10; // rbx
  __int64 v11; // rax
  bool v12; // zf
  unsigned int v13; // eax
  void *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r9
  char LastError; // al
  DWORD v18; // eax
  struct _GUID *v20; // r10
  const WCHAR *v21; // rdi
  unsigned int v22; // ebx
  __int64 v23; // rcx
  void *v24; // rax
  const WCHAR *v25; // rax
  unsigned int v26; // ebx
  struct _GUID *v27; // rcx
  int v28; // edx
  const WCHAR *v29; // rax
  unsigned int v30; // ebx
  const WCHAR *v31; // rax
  unsigned int v32; // ebx
  void *v33; // rcx
  void *v34; // rcx
  const WCHAR *v35; // rdi
  unsigned int v36; // ebx
  int SystemMetrics; // eax
  __int64 v38; // rbx
  int ManualOverride; // eax
  int v40; // edx
  int v41; // ecx
  DWORD v42; // [rsp+40h] [rbp-89h] BYREF
  __int64 v43; // [rsp+48h] [rbp-81h] BYREF
  __int64 v44; // [rsp+50h] [rbp-79h]
  DWORD ExitCode; // [rsp+58h] [rbp-71h] BYREF
  const char *v46; // [rsp+60h] [rbp-69h] BYREF
  int v47; // [rsp+68h] [rbp-61h] BYREF
  __int128 v48; // [rsp+6Ch] [rbp-5Dh]
  __int16 *v49; // [rsp+80h] [rbp-49h] BYREF
  int v50; // [rsp+88h] [rbp-41h]
  int v51; // [rsp+8Ch] [rbp-3Dh]
  char *v52; // [rsp+90h] [rbp-39h]
  int v53; // [rsp+98h] [rbp-31h]
  int v54; // [rsp+9Ch] [rbp-2Dh]
  DWORD *v55; // [rsp+A0h] [rbp-29h]
  __int64 v56; // [rsp+A8h] [rbp-21h]
  DWORD *v57; // [rsp+B0h] [rbp-19h]
  __int64 v58; // [rsp+B8h] [rbp-11h]
  DWORD *p_ExitCode; // [rsp+C0h] [rbp-9h]
  __int64 v60; // [rsp+C8h] [rbp-1h]

  v6 = *(_QWORD *)this;
  if ( v6 )
    v9 = *(const wchar_t **)(v6 + 544);
  else
    v9 = L"(unknown)";
  v10 = -1;
  if ( (unsigned int)dword_1800411A8 > 5
    && (qword_1800411B8 & 0x4000000) != 0
    && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
  {
    ExitCode = *((_DWORD *)this + 271);
    LODWORD(v46) = *((_DWORD *)this + 8);
    p_ExitCode = &ExitCode;
    v60 = 4;
    if ( v9 )
    {
      v11 = -1;
      do
        v12 = v9[++v11] == 0;
      while ( !v12 );
      v13 = 2 * v11 + 2;
    }
    else
    {
      v9 = &Data;
      v13 = 2;
    }
    v58 = v13;
    v57 = (DWORD *)v9;
    v55 = (DWORD *)&v46;
    v49 = (__int16 *)off_1800411B0;
    v56 = 4;
    v43 = 0x50B000000LL;
    v44 = 0x4000000;
    v50 = *(unsigned __int16 *)off_1800411B0;
    v52 = (char *)&unk_18003ADB8;
    v51 = 2;
    v53 = 72;
    v54 = 1;
    v42 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EtwEventWriteTransfer(qword_1800411C8, &v43, 0, 0, 5, &v49);
  }
  if ( a2 )
  {
    *(_OWORD *)((char *)this + 8) = *(_OWORD *)a2;
    *((_QWORD *)this + 3) = *((_QWORD *)a2 + 2);
  }
  v14 = (void *)*((_QWORD *)this + 136);
  if ( v14 )
  {
    ExitCode = 0;
    if ( !GetExitCodeProcess(v14, &ExitCode) )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_sd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          23,
          (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
          (unsigned int)"PENSERVICE_CPenProcess::EnsureRunning",
          LastError);
      }
      if ( (unsigned int)dword_1800411A8 > 5
        && (qword_1800411B8 & 0x4000000) != 0
        && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
      {
        v18 = GetLastError();
        v56 = 4;
        v42 = v18;
        v43 = 0x50B000000LL;
        v55 = &v42;
        v49 = (__int16 *)off_1800411B0;
        v44 = 0x4000000;
        v50 = *(unsigned __int16 *)off_1800411B0;
        v52 = &byte_18003ACB7;
        v51 = 2;
        v53 = 64;
        v54 = 1;
        LODWORD(v46) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(qword_1800411C8, &v43, 0, 0, 3, &v49);
        return 0;
      }
      return 0;
    }
    v20 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    {
      WPP_SF_sSdS(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        (unsigned int)&WPP_GLOBAL_Control,
        v15,
        v16,
        (__int64)this + 36,
        ExitCode,
        (__int64)this + 558);
      v20 = WPP_GLOBAL_Control;
    }
    switch ( ExitCode )
    {
      case 0x103u:
        if ( v20 != (struct _GUID *)&WPP_GLOBAL_Control && (v20[1].Data4[4] & 0x10) != 0 )
          WPP_SF_sS(
            *(_QWORD *)&v20[1].Data1,
            25,
            (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
            (unsigned int)"PENSERVICE_CPenProcess::EnsureRunning",
            (__int64)this + 558);
        if ( (unsigned int)dword_1800411A8 > 5
          && (qword_1800411B8 & 0x4000000) != 0
          && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
        {
          v58 = 21;
          v57 = (DWORD *)"Process still active";
          v21 = (const WCHAR *)((char *)this + 558);
          if ( v21 )
          {
            do
              v12 = v21[++v10] == 0;
            while ( !v12 );
            v22 = 2 * v10 + 2;
          }
          else
          {
            v21 = &Data;
            v22 = 2;
          }
          v49 = (__int16 *)off_1800411B0;
          v55 = (DWORD *)v21;
          v56 = v22;
          v43 = 0x50B000000LL;
          v44 = 0x4000000;
          v50 = *(unsigned __int16 *)off_1800411B0;
          v52 = (char *)&unk_18003AF40;
          v51 = 2;
          v53 = 58;
          v54 = 1;
          v42 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_1800411C8, &v43, 0, 0, 4, &v49);
        }
        return 1;
      case 0x16u:
      case 0x40010004u:
        if ( v20 != (struct _GUID *)&WPP_GLOBAL_Control && (v20[1].Data4[4] & 0x10) != 0 )
          WPP_SF_sS(
            *(_QWORD *)&v20[1].Data1,
            26,
            (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
            (unsigned int)"PENSERVICE_CPenProcess::EnsureRunning",
            (__int64)this + 558);
        if ( (unsigned int)dword_1800411A8 > 5
          && (qword_1800411B8 & 0x4000000) != 0
          && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
        {
          v42 = *((_DWORD *)this + 271);
          v43 = (__int64)"Process exited due to end of session";
          v46 = (char *)this + 558;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            qword_1800411C0,
            (int)byte_18003AB4B,
            v15,
            v16,
            (const WCHAR **)&v46,
            (const unsigned __int16 **)&v43,
            (__int64)&v42);
        }
        *((_DWORD *)this + 270) = 3;
        v33 = (void *)*((_QWORD *)this + 136);
        if ( v33 )
        {
          CloseHandle(v33);
          *((_QWORD *)this + 136) = 0;
        }
        v34 = (void *)*((_QWORD *)this + 137);
        if ( v34 )
        {
          ReleaseMutex(v34);
          CloseHandle(*((HANDLE *)this + 137));
          *((_QWORD *)this + 137) = 0;
        }
        *((_DWORD *)this + 271) = 0;
        if ( !a3 )
        {
          CPenProcess::ShutdownWatchDogThread(this);
          return 0;
        }
        break;
      case 0x17u:
        if ( v20 != (struct _GUID *)&WPP_GLOBAL_Control && (v20[1].Data4[4] & 0x10) != 0 )
          WPP_SF_sS(
            *(_QWORD *)&v20[1].Data1,
            27,
            (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
            (unsigned int)"PENSERVICE_CPenProcess::EnsureRunning",
            (__int64)this + 558);
        if ( (unsigned int)dword_1800411A8 > 5
          && (qword_1800411B8 & 0x4000000) != 0
          && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
        {
          v42 = *((_DWORD *)this + 271);
          v46 = "Process already running.";
          v43 = (__int64)this + 558;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
            qword_1800411C0,
            (int)&word_18003AE8E,
            v15,
            v16,
            (const WCHAR **)&v43,
            (const unsigned __int16 **)&v46,
            (__int64)&v42);
        }
        SH<void *,SH_HANDLE>::Reset((char *)this + 1088);
        v23 = *(_QWORD *)this;
        *((_DWORD *)this + 271) = 0;
        if ( !(*(unsigned int (__fastcall **)(__int64))(*(_QWORD *)v23 + 24LL))(v23) )
          return 0;
        v24 = CPenProcess::OpenProcessMutexInSession(this);
        *((_QWORD *)this + 137) = v24;
        if ( v24 )
          return 1;
        if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
          WPP_SF_sS(
            *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
            28,
            (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
            (unsigned int)"PENSERVICE_CPenProcess::EnsureRunning",
            (__int64)this + 558);
        if ( (unsigned int)dword_1800411A8 > 5
          && (qword_1800411B8 & 0x4000000) != 0
          && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
        {
          v25 = (const WCHAR *)((char *)this + 558);
          if ( this == (CPenProcess *)-558LL )
          {
            v25 = &Data;
            v26 = 2;
          }
          else
          {
            do
              v12 = v25[++v10] == 0;
            while ( !v12 );
            v26 = 2 * v10 + 2;
          }
          v55 = (DWORD *)v25;
          v49 = (__int16 *)off_1800411B0;
          v56 = v26;
          v43 = 0x50B000000LL;
          v44 = 0x4000000;
          v50 = *(unsigned __int16 *)off_1800411B0;
          v52 = (char *)word_18003AEEA;
          v51 = 2;
          v53 = 74;
          v54 = 1;
          v42 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_1800411C8, &v43, 0, 0, 3, &v49);
        }
        break;
      case 0x18u:
        if ( v20 != (struct _GUID *)&WPP_GLOBAL_Control && (v20[1].Data4[4] & 0x10) != 0 )
          WPP_SF_sS(
            *(_QWORD *)&v20[1].Data1,
            29,
            (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
            (unsigned int)"PENSERVICE_CPenProcess::EnsureRunning",
            (__int64)this + 558);
        if ( (unsigned int)dword_1800411A8 > 5
          && (qword_1800411B8 & 0x4000000) != 0
          && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
        {
          v29 = (const WCHAR *)((char *)this + 558);
          if ( this == (CPenProcess *)-558LL )
          {
            v29 = &Data;
            v30 = 2;
          }
          else
          {
            do
              v12 = v29[++v10] == 0;
            while ( !v12 );
            v30 = 2 * v10 + 2;
          }
          v55 = (DWORD *)v29;
          v49 = (__int16 *)off_1800411B0;
          v56 = v30;
          v43 = 0x50B000000LL;
          v44 = 0x4000000;
          v50 = *(unsigned __int16 *)off_1800411B0;
          v52 = &byte_18003AE57;
          v51 = 2;
          v53 = 54;
          v54 = 1;
          v42 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_1800411C8, &v43, 0, 0, 3, &v49);
        }
        SH<void *,SH_HANDLE>::Reset((char *)this + 1088);
        *((_DWORD *)this + 271) = 0;
        if ( !a4 )
          return 0;
        break;
      default:
        if ( v20 != (struct _GUID *)&WPP_GLOBAL_Control && (v20[1].Data4[4] & 0x10) != 0 )
          WPP_SF_sdS(
            *(_QWORD *)&v20[1].Data1,
            (unsigned int)&WPP_GLOBAL_Control,
            v15,
            v16,
            ExitCode,
            (__int64)this + 558);
        if ( (unsigned int)dword_1800411A8 > 5
          && (qword_1800411B8 & 0x4000000) != 0
          && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
        {
          v42 = ExitCode;
          v31 = (const WCHAR *)((char *)this + 558);
          v57 = &v42;
          v58 = 4;
          if ( this == (CPenProcess *)-558LL )
          {
            v31 = &Data;
            v32 = 2;
          }
          else
          {
            do
              v12 = v31[++v10] == 0;
            while ( !v12 );
            v32 = 2 * v10 + 2;
          }
          v55 = (DWORD *)v31;
          v49 = (__int16 *)off_1800411B0;
          v56 = v32;
          v43 = 0x50B000000LL;
          v44 = 0x4000000;
          v50 = *(unsigned __int16 *)off_1800411B0;
          v52 = byte_18003B07B;
          v51 = 2;
          v53 = 80;
          v54 = 1;
          LODWORD(v46) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
          EtwEventWriteTransfer(qword_1800411C8, &v43, 0, 0, 4, &v49);
        }
        break;
    }
  }
  else
  {
    if ( *((_QWORD *)this + 137) )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
        WPP_SF_sS(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          31,
          (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
          (unsigned int)"PENSERVICE_CPenProcess::EnsureRunning",
          (__int64)this + 558);
      if ( (unsigned int)dword_1800411A8 > 5
        && (qword_1800411B8 & 0x4000000) != 0
        && (qword_1800411C0 & 0x4000000) == qword_1800411C0 )
      {
        v35 = (const WCHAR *)((char *)this + 558);
        if ( v35 )
        {
          do
            v12 = v35[++v10] == 0;
          while ( !v12 );
          v36 = 2 * v10 + 2;
        }
        else
        {
          v35 = &Data;
          v36 = 2;
        }
        v49 = (__int16 *)off_1800411B0;
        v55 = (DWORD *)v35;
        v56 = v36;
        v43 = 0x50B000000LL;
        v44 = 0x4000000;
        v50 = *(unsigned __int16 *)off_1800411B0;
        v52 = (char *)&word_18003AF86;
        v51 = 2;
        v53 = 74;
        v54 = 1;
        v42 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EtwEventWriteTransfer(qword_1800411C8, &v43, 0, 0, 3, &v49);
      }
      return 1;
    }
    if ( *((_DWORD *)this + 270) == 3 && !a3 )
      return 0;
  }
  if ( !*(_QWORD *)this )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[1].Data4[4] & 0x10) == 0 )
      return 0;
    v28 = 32;
    goto LABEL_131;
  }
  v47 = (unsigned __int8)byte_180041270;
  v48 = 0;
  SystemMetrics = GetSystemMetrics(67);
  v38 = *(_QWORD *)this;
  *((_QWORD *)&v48 + 1) = __PAIR64__(HIDWORD(qword_180041278), dword_180041274);
  DWORD1(v48) = SystemMetrics != 0;
  ManualOverride = GetManualOverride();
  v40 = ManualOverride;
  if ( ManualOverride != 2 )
  {
    v41 = *(_DWORD *)(v38 + 8);
    ManualOverride = 0;
    if ( v41 != -1 )
    {
      if ( ((4 << v41) & v40) != 0 )
        ManualOverride = 2;
      else
        ManualOverride = v40 & 1;
    }
  }
  LODWORD(v48) = ManualOverride;
  if ( !a3
    && (*((_DWORD *)this + 3)
     || !(*(unsigned int (__fastcall **)(_QWORD, int *))(**(_QWORD **)this + 48LL))(*(_QWORD *)this, &v47)) )
  {
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control || (WPP_GLOBAL_Control[1].Data4[4] & 0x10) == 0 )
      return 0;
    v28 = 34;
LABEL_131:
    WPP_SF_sS(
      *(_QWORD *)&v27[1].Data1,
      v28,
      (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
      (unsigned int)"PENSERVICE_CPenProcess::EnsureRunning",
      (__int64)this + 558);
    return 0;
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sS(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      33,
      (unsigned int)WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids,
      (unsigned int)"PENSERVICE_CPenProcess::EnsureRunning",
      (__int64)this + 558);
  return CPenProcess::Restart(this);
}

```

## disassembly

```asm
0x180015660  push    rbp
0x180015662  push    rbx
0x180015663  push    rsi
0x180015664  push    rdi
0x180015665  push    r12
0x180015667  push    r13
0x180015669  push    r14
0x18001566b  push    r15
0x18001566d  lea     rbp, [rsp-1Fh]
0x180015672  sub     rsp, 0E8h
0x180015679  mov     rax, cs:__security_cookie
0x180015680  xor     rax, rsp
0x180015683  mov     [rbp+57h+var_50], rax
0x180015687  mov     rdi, rcx
0x18001568a  mov     r14d, r9d
0x18001568d  mov     rcx, [rcx]
0x180015690  mov     r13d, r8d
0x180015693  mov     rsi, rdx
0x180015696  test    rcx, rcx
0x180015699  jnz     short loc_1800156A4
0x18001569b  lea     rcx, aUnknown; "(unknown)"
0x1800156a2  jmp     short loc_1800156AB
0x1800156a4  mov     rcx, [rcx+220h]
0x1800156ab  mov     eax, cs:dword_1800411A8
0x1800156b1  lea     r15, _TraceLoggingMetadataEnd
0x1800156b8  xor     r8d, r8d
0x1800156bb  lea     r9, _TraceLoggingMetadata
0x1800156c2  mov     r12d, 4
0x1800156c8  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x1800156cf  cmp     eax, 5
0x1800156d2  jbe     loc_1800157EA
0x1800156d8  mov     rdx, cs:qword_1800411C0
0x1800156df  mov     rax, cs:qword_1800411B8
0x1800156e6  bt      rax, 1Ah
0x1800156eb  jnb     loc_1800157EA
0x1800156f1  mov     rax, rdx
0x1800156f4  and     eax, 4000000h
0x1800156f9  cmp     rax, rdx
0x1800156fc  jnz     loc_1800157EA
0x180015702  mov     eax, [rdi+43Ch]
0x180015708  mov     [rbp+57h+ExitCode], eax
0x18001570b  mov     eax, [rdi+20h]
0x18001570e  mov     dword ptr [rbp+57h+var_C0], eax
0x180015711  lea     rax, [rbp+57h+ExitCode]
0x180015715  mov     [rbp+57h+var_60], rax
0x180015719  mov     [rbp+57h+var_58], r12
0x18001571d  test    rcx, rcx
0x180015720  jz      short loc_180015745
0x180015722  mov     rax, rbx
0x180015725  nop     word ptr [rax+rax+00000000h]
0x180015730  cmp     [rcx+rax*2+2], r8w
0x180015736  lea     rax, [rax+1]
0x18001573a  jnz     short loc_180015730
0x18001573c  lea     eax, ds:2[rax*2]
0x180015743  jmp     short loc_180015751
0x180015745  lea     rcx, Data
0x18001574c  mov     eax, 2
0x180015751  mov     dword ptr [rbp+57h+var_68], eax
0x180015754  lea     rdx, [rsp+120h+var_D8]
0x180015759  mov     [rbp+57h+var_70], rcx
0x18001575d  lea     rax, [rbp+57h+var_C0]
0x180015761  mov     [rbp+57h+var_80], rax
0x180015765  movzx   eax, cs:word_18003ADAE
0x18001576c  mov     dword ptr [rbp+57h+var_D8+4], eax
0x18001576f  mov     rax, cs:off_1800411B0
0x180015776  mov     [rbp+57h+var_A0], rax
0x18001577a  mov     dword ptr [rbp+57h+var_68+4], r8d
0x18001577e  mov     [rbp+57h+var_78], r12
0x180015782  mov     dword ptr [rsp+120h+var_D8], 0B000000h
0x18001578a  mov     [rbp+57h+var_D0], 4000000h
0x180015792  movzx   eax, word ptr [rax]
0x180015795  mov     [rbp+57h+var_98], eax
0x180015798  lea     rax, unk_18003ADB8
0x18001579f  mov     [rbp+57h+var_90], rax
0x1800157a3  mov     rax, r15
0x1800157a6  sub     eax, r9d
0x1800157a9  mov     [rbp+57h+var_94], 2
0x1800157b0  mov     [rbp+57h+var_88], 48h ; 'H'
0x1800157b7  xor     r9d, r9d
0x1800157ba  mov     [rbp+57h+var_84], 1
0x1800157c1  mov     [rsp+120h+var_E0], eax
0x1800157c5  mov     eax, [rsp+120h+var_E0]
0x1800157c9  mov     rcx, cs:qword_1800411C8
0x1800157d0  lea     rax, [rbp+57h+var_A0]
0x1800157d4  mov     [rsp+120h+var_F8], rax
0x1800157d9  mov     dword ptr [rsp+120h+var_100], 5
0x1800157e1  call    cs:__imp_EtwEventWriteTransfer
0x1800157e7  xor     r8d, r8d
0x1800157ea  test    rsi, rsi
0x1800157ed  jz      short loc_180015800
0x1800157ef  movups  xmm0, xmmword ptr [rsi]
0x1800157f2  movups  xmmword ptr [rdi+8], xmm0
0x1800157f6  movsd   xmm1, qword ptr [rsi+10h]
0x1800157fb  movsd   qword ptr [rdi+18h], xmm1
0x180015800  mov     rcx, [rdi+440h]; hProcess
0x180015807  lea     rdx, WPP_GLOBAL_Control
0x18001580e  test    rcx, rcx
0x180015811  jz      loc_18001610C
0x180015817  lea     rdx, [rbp+57h+ExitCode]; lpExitCode
0x18001581b  mov     [rbp+57h+ExitCode], r8d
0x18001581f  call    cs:__imp_GetExitCodeProcess
0x180015825  test    eax, eax
0x180015827  jnz     loc_18001594F
0x18001582d  mov     rax, cs:WPP_GLOBAL_Control
0x180015834  lea     rdx, WPP_GLOBAL_Control
0x18001583b  cmp     rax, rdx
0x18001583e  jz      short loc_180015873
0x180015840  test    [rax+1Ch], r12b
0x180015844  jz      short loc_180015873
0x180015846  call    cs:__imp_GetLastError
0x18001584c  mov     rcx, cs:WPP_GLOBAL_Control
0x180015853  lea     r9, aPenserviceCpen_0; "PENSERVICE_CPenProcess::EnsureRunning"
0x18001585a  mov     edx, 17h
0x18001585f  mov     dword ptr [rsp+120h+var_100], eax
0x180015863  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x18001586a  mov     rcx, [rcx+10h]
0x18001586e  call    WPP_SF_sd
0x180015873  mov     eax, cs:dword_1800411A8
0x180015879  cmp     eax, 5
0x18001587c  jbe     loc_18001634A
0x180015882  mov     rcx, cs:qword_1800411C0
0x180015889  mov     rax, cs:qword_1800411B8
0x180015890  bt      rax, 1Ah
0x180015895  jnb     loc_18001634A
0x18001589b  mov     rax, rcx
0x18001589e  and     eax, 4000000h
0x1800158a3  cmp     rax, rcx
0x1800158a6  jnz     loc_18001634A
0x1800158ac  call    cs:__imp_GetLastError
0x1800158b2  mov     [rbp+57h+var_78], r12
0x1800158b6  lea     rdx, [rsp+120h+var_D8]
0x1800158bb  mov     [rsp+120h+var_E0], eax
0x1800158bf  xor     r9d, r9d
0x1800158c2  lea     rax, [rsp+120h+var_E0]
0x1800158c7  mov     dword ptr [rsp+120h+var_D8], 0B000000h
0x1800158cf  mov     [rbp+57h+var_80], rax
0x1800158d3  xor     r8d, r8d
0x1800158d6  movzx   eax, cs:word_18003ACAD
0x1800158dd  mov     dword ptr [rbp+57h+var_D8+4], eax
0x1800158e0  mov     rax, cs:off_1800411B0
0x1800158e7  mov     [rbp+57h+var_A0], rax
0x1800158eb  mov     [rbp+57h+var_D0], 4000000h
0x1800158f3  movzx   eax, word ptr [rax]
0x1800158f6  mov     [rbp+57h+var_98], eax
0x1800158f9  lea     rax, byte_18003ACB7
0x180015900  mov     [rbp+57h+var_90], rax
0x180015904  lea     rax, _TraceLoggingMetadata
0x18001590b  sub     r15d, eax
0x18001590e  mov     [rbp+57h+var_94], 2
0x180015915  mov     [rbp+57h+var_88], 40h ; '@'
0x18001591c  mov     [rbp+57h+var_84], 1
0x180015923  mov     dword ptr [rbp+57h+var_C0], r15d
0x180015927  mov     eax, dword ptr [rbp+57h+var_C0]
0x18001592a  mov     rcx, cs:qword_1800411C8
0x180015931  lea     rax, [rbp+57h+var_A0]
0x180015935  mov     [rsp+120h+var_F8], rax
0x18001593a  mov     dword ptr [rsp+120h+var_100], 3
0x180015942  call    cs:__imp_EtwEventWriteTransfer
0x180015948  xor     eax, eax
0x18001594a  jmp     loc_180016397
0x18001594f  mov     r10, cs:WPP_GLOBAL_Control
0x180015956  lea     rdx, WPP_GLOBAL_Control
0x18001595d  cmp     r10, rdx
0x180015960  jz      short loc_18001599C
0x180015962  test    byte ptr [r10+1Ch], 10h
0x180015967  jz      short loc_18001599C
0x180015969  lea     rax, [rdi+22Eh]
0x180015970  mov     [rsp+120h+var_F0], rax
0x180015975  lea     rcx, [rdi+24h]
0x180015979  mov     eax, [rbp+57h+ExitCode]
0x18001597c  mov     dword ptr [rsp+120h+var_F8], eax
0x180015980  mov     [rsp+120h+var_100], rcx
0x180015985  mov     rcx, [r10+10h]
0x180015989  call    WPP_SF_sSdS
0x18001598e  mov     r10, cs:WPP_GLOBAL_Control
0x180015995  lea     rdx, WPP_GLOBAL_Control
0x18001599c  mov     ecx, [rbp+57h+ExitCode]
0x18001599f  cmp     ecx, 103h
0x1800159a5  jnz     loc_180015ADB
0x1800159ab  cmp     r10, rdx
0x1800159ae  jz      short loc_1800159DF
0x1800159b0  test    byte ptr [r10+1Ch], 10h
0x1800159b5  jz      short loc_1800159DF
0x1800159b7  mov     rcx, [r10+10h]
0x1800159bb  lea     rax, [rdi+22Eh]
0x1800159c2  mov     edx, 19h
0x1800159c7  mov     [rsp+120h+var_100], rax
0x1800159cc  lea     r9, aPenserviceCpen_0; "PENSERVICE_CPenProcess::EnsureRunning"
0x1800159d3  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x1800159da  call    WPP_SF_sS
0x1800159df  mov     eax, cs:dword_1800411A8
0x1800159e5  cmp     eax, 5
0x1800159e8  jbe     loc_180016256
0x1800159ee  mov     rcx, cs:qword_1800411C0
0x1800159f5  mov     rax, cs:qword_1800411B8
0x1800159fc  bt      rax, 1Ah
0x180015a01  jnb     loc_180016256
0x180015a07  mov     rax, rcx
0x180015a0a  and     eax, 4000000h
0x180015a0f  cmp     rax, rcx
0x180015a12  jnz     loc_180016256
0x180015a18  lea     rax, aProcessStillAc; "Process still active"
0x180015a1f  mov     [rbp+57h+var_68], 15h
0x180015a27  mov     [rbp+57h+var_70], rax
0x180015a2b  xor     eax, eax
0x180015a2d  add     rdi, 22Eh
0x180015a34  jz      short loc_180015A54
0x180015a36  nop     word ptr [rax+rax+00000000h]
0x180015a40  cmp     [rdi+rbx*2+2], ax
0x180015a45  lea     rbx, [rbx+1]
0x180015a49  jnz     short loc_180015A40
0x180015a4b  lea     ebx, ds:2[rbx*2]
0x180015a52  jmp     short loc_180015A60
0x180015a54  lea     rdi, Data
0x180015a5b  mov     ebx, 2
0x180015a60  mov     dword ptr [rbp+57h+var_78+4], eax
0x180015a63  movzx   eax, cs:word_18003AF36
0x180015a6a  mov     dword ptr [rbp+57h+var_D8+4], eax
0x180015a6d  mov     rax, cs:off_1800411B0
0x180015a74  mov     [rbp+57h+var_A0], rax
0x180015a78  mov     [rbp+57h+var_80], rdi
0x180015a7c  mov     dword ptr [rbp+57h+var_78], ebx
0x180015a7f  mov     dword ptr [rsp+120h+var_D8], 0B000000h
0x180015a87  mov     [rbp+57h+var_D0], 4000000h
0x180015a8f  movzx   eax, word ptr [rax]
0x180015a92  mov     [rbp+57h+var_98], eax
0x180015a95  lea     rax, unk_18003AF40
0x180015a9c  mov     [rbp+57h+var_90], rax
0x180015aa0  lea     rax, _TraceLoggingMetadata
0x180015aa7  sub     r15d, eax
0x180015aaa  mov     [rbp+57h+var_94], 2
0x180015ab1  mov     [rbp+57h+var_88], 3Ah ; ':'
0x180015ab8  mov     [rbp+57h+var_84], 1
0x180015abf  mov     [rsp+120h+var_E0], r15d
0x180015ac4  mov     eax, [rsp+120h+var_E0]
0x180015ac8  lea     rax, [rbp+57h+var_A0]
0x180015acc  mov     [rsp+120h+var_F8], rax
0x180015ad1  mov     dword ptr [rsp+120h+var_100], r12d
0x180015ad6  jmp     loc_18001623E
0x180015adb  cmp     ecx, 16h
0x180015ade  jz      loc_180015FEE
0x180015ae4  cmp     ecx, 40010004h
0x180015aea  jz      loc_180015FEE
0x180015af0  cmp     ecx, 17h
0x180015af3  jnz     loc_180015D6B
0x180015af9  cmp     r10, rdx
0x180015afc  jz      short loc_180015B2D
0x180015afe  test    byte ptr [r10+1Ch], 10h
0x180015b03  jz      short loc_180015B2D
0x180015b05  mov     rcx, [r10+10h]
0x180015b09  lea     rax, [rdi+22Eh]
0x180015b10  mov     edx, 1Bh
0x180015b15  mov     [rsp+120h+var_100], rax
0x180015b1a  lea     r9, aPenserviceCpen_0; "PENSERVICE_CPenProcess::EnsureRunning"
0x180015b21  lea     r8, WPP_3ebeadf2ed2d34ad0a320894ebd479c5_Traceguids
0x180015b28  call    WPP_SF_sS
0x180015b2d  mov     eax, cs:dword_1800411A8
0x180015b33  cmp     eax, 5
0x180015b36  jbe     short loc_180015BA4
0x180015b38  mov     rcx, cs:qword_1800411C0
0x180015b3f  mov     rax, cs:qword_1800411B8
0x180015b46  bt      rax, 1Ah
0x180015b4b  jnb     short loc_180015BA4
0x180015b4d  mov     rax, rcx
0x180015b50  and     eax, 4000000h
0x180015b55  cmp     rax, rcx
0x180015b58  jnz     short loc_180015BA4
0x180015b5a  mov     eax, [rdi+43Ch]
0x180015b60  lea     rdx, word_18003AE8E
0x180015b67  mov     [rsp+120h+var_E0], eax
0x180015b6b  lea     rax, aProcessAlready_0; "Process already running."
0x180015b72  mov     [rbp+57h+var_C0], rax
0x180015b76  lea     rax, [rdi+22Eh]
0x180015b7d  mov     [rsp+120h+var_D8], rax
0x180015b82  lea     rax, [rsp+120h+var_E0]
0x180015b87  mov     [rsp+120h+var_F0], rax
0x180015b8c  lea     rax, [rbp+57h+var_C0]
0x180015b90  mov     [rsp+120h+var_F8], rax
0x180015b95  lea     rax, [rsp+120h+var_D8]
0x180015b9a  mov     [rsp+120h+var_100], rax
0x180015b9f  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x180015ba4  lea     rcx, [rdi+440h]
0x180015bab  call    ?Reset@?$SH@PEAXVSH_HANDLE@@@@QEAAXXZ; SH<void *,SH_HANDLE>::Reset(void)
0x180015bb0  mov     rcx, [rdi]
0x180015bb3  mov     dword ptr [rdi+43Ch], 0
0x180015bbd  mov     rax, [rcx]
0x180015bc0  mov     rax, [rax+18h]
0x180015bc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bc9  test    eax, eax
0x180015bcb  jz      loc_18001634A
0x180015bd1  mov     rcx, rdi; this
0x180015bd4  call    ?OpenProcessMutexInSession@CPenProcess@@AEAAPEAXXZ; CPenProcess::OpenProcessMutexInSession(void)
0x180015bd9  mov     [rdi+448h], rax
0x180015be0  test    rax, rax
0x180015be3  jnz     loc_180016256
0x180015be9  mov     rcx, cs:WPP_GLOBAL_Control
0x180015bf0  lea     rdx, WPP_GLOBAL_Control
0x180015bf7  cmp     rcx, rdx
0x180015bfa  jz      short loc_180015C31
0x180015bfc  test    byte ptr [rcx+1Ch], 10h
  ... truncated ...
```
