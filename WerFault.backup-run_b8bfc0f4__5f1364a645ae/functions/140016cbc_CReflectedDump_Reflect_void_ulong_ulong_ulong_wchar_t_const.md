# CReflectedDump::Reflect(void *,ulong,ulong,ulong,wchar_t const *)

- ea: `0x140016cbc`
- end: `0x14001751c`
- name: `?Reflect@CReflectedDump@@IEAAJPEAXKKKPEB_W@Z`
- size: `2144`
- prototype: `__int64 __fastcall(CReflectedDump *this, HANDLE ProcessHandle, DWORD dwThreadId, unsigned int, char, wchar_t *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140017530`

## callees

- `0x140001d40`
- `0x140002470`
- `0x1400030a8`
- `0x1400032ef`
- `0x1400032fb`
- `0x140003313`
- `0x140005498`
- `0x14000b408`
- `0x14001444c`
- `0x140014474`
- `0x1400144b4`
- `0x140014ddc`
- `0x140016004`
- `0x14001623c`
- `0x140016500`
- `0x140016cbc`
- `0x140017d6c`
- `0x140018830`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400171f3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14001728c`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x1400171f3`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x14001728c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016e6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016e81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016ec9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400174d5`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016e6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016e81`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140016ec9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400174d5`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140017131`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140017131`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140017280`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400173ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400173fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400174aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140017280`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400173ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400173fd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400174aa`
- `ntdll!RtlCreateProcessReflection` at `0x140017425`
- `ntdll!RtlCreateProcessReflection` at `0x140017425`
- `ntdll!NtResumeProcess` at `0x140016eb4`
- `ntdll!NtResumeProcess` at `0x1400173df`
- `ntdll!NtResumeProcess` at `0x140016eb4`
- `ntdll!NtResumeProcess` at `0x1400173df`
- `ntdll!NtSuspendProcess` at `0x1400171ab`
- `ntdll!NtSuspendProcess` at `0x1400171ab`
- `wer!WerpValidateReportKey` at `0x140016e0f`
- `wer!WerpValidateReportKey` at `0x140016e0f`
- `wer!WerpGetStorePath` at `0x140016f24`
- `wer!WerpGetStorePath` at `0x140016f24`
- `dbghelp!MiniDumpWriteDump` at `0x1400172ba`
- `dbghelp!MiniDumpWriteDump` at `0x1400172ba`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016ed8`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140016ed8`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CReflectedDump::Reflect(
        CReflectedDump *this,
        HANDLE ProcessHandle,
        DWORD dwThreadId,
        unsigned int a4,
        char a5,
        wchar_t *a6)
{
  DWORD v6; // r13d
  int v9; // r12d
  int DumpSecurityDescriptor; // eax
  int v11; // r14d
  const wchar_t *v12; // rbx
  int StorePath; // eax
  CUserModeHangReport *v14; // rcx
  __int64 v15; // rdx
  __int64 v16; // r9
  HANDLE v17; // rcx
  HANDLE *v19; // rsi
  HANDLE CurrentProcess_0; // rdi
  HANDLE v21; // rbx
  HANDLE v22; // rax
  signed int LastError_0; // eax
  HANDLE v24; // rsi
  DWORD ProcessId; // eax
  int FirstThreadInProcess; // eax
  CUserModeHangReport *v27; // rcx
  __int64 v28; // rdx
  __int64 v29; // r9
  MINIDUMP_TYPE v30; // edi
  DWORD TickCount; // r12d
  DWORD v32; // eax
  int v33; // r8d
  int v34; // r9d
  DWORD v35; // edi
  int ProcessReflection; // r14d
  void *v37; // rcx
  int v38; // [rsp+50h] [rbp-B0h]
  unsigned int v39; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hFile; // [rsp+70h] [rbp-90h] BYREF
  HANDLE ProcessHandlea; // [rsp+78h] [rbp-88h]
  HLOCAL hMem; // [rsp+80h] [rbp-80h] BYREF
  __int128 v46; // [rsp+88h] [rbp-78h]
  __int64 v47; // [rsp+98h] [rbp-68h]
  char *v48; // [rsp+A0h] [rbp-60h] BYREF
  const WCHAR *v49; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v50; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v51; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v52; // [rsp+C0h] [rbp-40h] BYREF
  _MINIDUMP_EXCEPTION_INFORMATION ExceptionParam; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE v54[2]; // [rsp+E0h] [rbp-20h]
  __int128 v55; // [rsp+F0h] [rbp-10h]
  _MINIDUMP_CALLBACK_INFORMATION CallbackParam; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v57[160]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v58[1232]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t v59[264]; // [rsp+680h] [rbp+580h] BYREF

  ProcessHandlea = ProcessHandle;
  v6 = dwThreadId;
  v39 = dwThreadId;
  v38 = 0;
  hFile = 0;
  v40 = a4;
  *(_OWORD *)v54 = 0;
  v9 = 0;
  v55 = 0;
  ExceptionParam = 0;
  memset_0(v57, 0, 0x98u);
  v52 = 0;
  memset_0(v58, 0, sizeof(v58));
  hMem = 0;
  hObject = 0;
  v41 = 0;
  v46 = 0;
  CallbackParam.CallbackRoutine = (MINIDUMP_CALLBACK_ROUTINE)CReflectedDump::static_MiniDumpCallback;
  CallbackParam.CallbackParam = this;
  LODWORD(v46) = 24;
  v47 = 0;
  DumpSecurityDescriptor = GetDumpSecurityDescriptor(ProcessHandle, &hMem);
  v11 = DumpSecurityDescriptor;
  if ( DumpSecurityDescriptor >= 0 )
  {
    v12 = L".mdref";
    *((_QWORD *)&v46 + 1) = hMem;
    if ( (a5 & 2) == 0 )
      v12 = L".tdref";
    if ( a6 && *a6 )
    {
      StorePath = WerpValidateReportKey(a6);
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_15;
        }
        v15 = 31;
        goto LABEL_13;
      }
      v41 = 260;
      StorePath = WerpGetStorePath(3, v59, &v41);
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_15;
        }
        v15 = 32;
        goto LABEL_13;
      }
      StorePath = StringCchCatW(v59, 0x104u, L"\\");
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_15;
        }
        v15 = 33;
        goto LABEL_13;
      }
      StorePath = StringCchCatW(v59, 0x104u, a6);
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_15;
        }
        v15 = 34;
        goto LABEL_13;
      }
      StorePath = StringCchCatW(v59, 0x104u, L"\\");
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_15;
        }
        v15 = 35;
        goto LABEL_13;
      }
      StorePath = UtilGetTempFile(&hFile, v59, v12, (char *)this + 8);
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 36;
LABEL_13:
          v16 = (unsigned int)StorePath;
LABEL_14:
          WPP_SF_d(*((_QWORD *)v14 + 2), v15, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v16);
LABEL_15:
          v9 = 0;
          goto LABEL_16;
        }
        goto LABEL_75;
      }
    }
    else
    {
      StorePath = UtilGetTempFile(&hFile, 0, v12, (char *)this + 8);
      v11 = StorePath;
      if ( StorePath < 0 )
      {
        v14 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          v15 = 37;
          goto LABEL_13;
        }
        goto LABEL_75;
      }
    }
    v19 = (HANDLE *)tlx::replace<tlx::file_handle_traits>(&hObject);
    CurrentProcess_0 = GetCurrentProcess_0();
    v21 = GetCurrentProcess_0();
    v22 = GetCurrentProcess_0();
    if ( !DuplicateHandle(v22, v21, CurrentProcess_0, v19, 0x100000u, 0, 0) )
    {
      LastError_0 = GetLastError_0();
      v11 = LastError_0;
      if ( LastError_0 > 0 )
        v11 = (unsigned __int16)LastError_0 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      v14 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v15 = 38;
        v16 = (unsigned int)v11;
        goto LABEL_14;
      }
      goto LABEL_75;
    }
    v24 = ProcessHandlea;
    if ( (a5 & 1) == 0 )
    {
      if ( (NtSuspendProcess(ProcessHandlea) & 0xC0000000) == 0xC0000000 )
      {
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_d(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            39,
            WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
            (unsigned int)v11);
        }
      }
      else
      {
        v38 = 1;
      }
    }
    if ( !v6 )
    {
      ProcessId = GetProcessId(v24);
      FirstThreadInProcess = GetFirstThreadInProcess(ProcessId, &v39);
      v11 = FirstThreadInProcess;
      if ( FirstThreadInProcess < 0 )
      {
        v27 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control == (CUserModeHangReport *)&WPP_GLOBAL_Control
          || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
        {
          goto LABEL_75;
        }
        v28 = 40;
        v29 = (unsigned int)FirstThreadInProcess;
        goto LABEL_74;
      }
      v6 = v39;
    }
    ExceptionParam.ExceptionPointers = (PEXCEPTION_POINTERS)&v52;
    *((_QWORD *)&v52 + 1) = v58;
    *(_QWORD *)&v52 = v57;
    SetExceptionInformation(v6, v40, &ExceptionParam);
    v30 = (a5 & 2) != 0
        ? MiniDumpWithThreadInfo|MiniDumpWithProcessThreadData|MiniDumpWithUnloadedModules|MiniDumpWithHandleData
        : MiniDumpFilterTriage|MiniDumpWithProcessThreadData|MiniDumpFilterModulePaths|MiniDumpWithUnloadedModules|MiniDumpWithHandleData;
    TickCount = GetTickCount();
    v32 = GetProcessId(v24);
    if ( MiniDumpWriteDump(v24, v32, hFile, v30, &ExceptionParam, 0, &CallbackParam) )
      v11 = 0;
    else
      v11 = GetLastError_0();
    if ( (unsigned int)dword_14007A038 > 5
      && (qword_14007A048 & 0x400000000000LL) != 0
      && (qword_14007A050 & 0x400000000000LL) == qword_14007A050 )
    {
      v40 = (a5 & 2) != 0 ? 4388 : 1048996;
      v48 = (char *)this + 8;
      v39 = v11;
      v49 = &pwzValue;
      v50 = L"Reflection";
      v51 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        qword_14007A050,
        (unsigned int)&unk_14006F108,
        v33,
        v34,
        (__int64)&v51,
        (__int64)&v39,
        (__int64)&v50,
        (__int64)&v49,
        (__int64)&v40,
        (__int64)&v48);
    }
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Dd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        41,
        WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
        (unsigned int)v11,
        v30);
      v27 = WPP_GLOBAL_Control;
    }
    if ( v11 < 0 )
    {
      if ( v27 == (CUserModeHangReport *)&WPP_GLOBAL_Control || (*((_BYTE *)v27 + 28) & 1) == 0 )
        goto LABEL_75;
      v28 = 42;
      goto LABEL_91;
    }
    if ( v38 )
    {
      NtResumeProcess(v24);
      v38 = 0;
    }
    *((_DWORD *)this + 136) = GetTickCount() - TickCount;
    v35 = GetTickCount();
    ProcessReflection = RtlCreateProcessReflection(v24, 12, 0);
    if ( (ProcessReflection & 0xC0000000) != 0xC0000000 )
    {
      if ( (unsigned int)VerifyReflectedProcessHandle(v24, v54[0]) )
      {
        *((_DWORD *)this + 137) = GetTickCount() - v35;
        v37 = (void *)*((_QWORD *)this + 66);
        *((HANDLE *)this + 66) = v54[0];
        if ( (unsigned __int64)v37 + 1 > 1 )
          CloseHandle(v37);
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_Dd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            45,
            WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
            *((unsigned int *)this + 136),
            *((_DWORD *)this + 137));
        }
        v11 = 0;
      }
      else
      {
        v11 = 6;
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 44, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
        }
      }
      goto LABEL_75;
    }
    v11 = ProcessReflection | 0x10000000;
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v28 = 43;
LABEL_91:
      v29 = (unsigned int)v11;
LABEL_74:
      WPP_SF_d(*((_QWORD *)v27 + 2), v28, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids, v29);
    }
LABEL_75:
    v9 = v38;
    goto LABEL_16;
  }
  if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      30,
      WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids,
      (unsigned int)DumpSecurityDescriptor);
  }
LABEL_16:
  v17 = hObject;
  hObject = 0;
  if ( (unsigned __int64)v17 + 1 > 1 )
    CloseHandle(v17);
  if ( (unsigned __int64)hFile + 1 > 1 )
    CloseHandle(hFile);
  if ( v54[1] )
  {
    CloseHandle_0(v54[1]);
    v54[1] = 0;
  }
  if ( v11 < 0 )
    CReflectedDump::Cleanup(this);
  if ( v9 )
    NtResumeProcess(ProcessHandlea);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( hMem )
    LocalFree(hMem);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140016cbc  mov     [rsp-8+arg_18], rbx
0x140016cc1  push    rbp
0x140016cc2  push    rsi
0x140016cc3  push    rdi
0x140016cc4  push    r12
0x140016cc6  push    r13
0x140016cc8  push    r14
0x140016cca  push    r15
0x140016ccc  lea     rbp, [rsp-7A0h]
0x140016cd4  sub     rsp, 8A0h
0x140016cdb  mov     rax, cs:__security_cookie
0x140016ce2  xor     rax, rsp
0x140016ce5  mov     [rbp+7D0h+var_40], rax
0x140016cec  mov     rdi, [rbp+7D0h+arg_28]
0x140016cf3  xorps   xmm0, xmm0
0x140016cf6  xor     ebx, ebx
0x140016cf8  mov     [rsp+8D0h+ProcessHandle], rdx
0x140016cfd  mov     r13d, r8d
0x140016d00  mov     [rsp+8D0h+var_878], r8d
0x140016d05  mov     rsi, rdx
0x140016d08  mov     [rsp+8D0h+var_880], ebx
0x140016d0c  mov     r15, rcx
0x140016d0f  mov     [rsp+8D0h+hFile], rbx
0x140016d14  xor     edx, edx; Val
0x140016d16  mov     [rsp+8D0h+var_870], r9d
0x140016d1b  mov     r8d, 98h; Size
0x140016d21  lea     rcx, [rbp+7D0h+var_7C0]; void *
0x140016d25  movups  xmmword ptr [rbp+7D0h+var_7F0], xmm0
0x140016d29  mov     r12d, ebx
0x140016d2c  movups  [rbp+7D0h+var_7E0], xmm0
0x140016d30  movups  xmmword ptr [rbp+7D0h+ExceptionParam.ThreadId], xmm0
0x140016d34  call    memset_0
0x140016d39  xorps   xmm0, xmm0
0x140016d3c  lea     rcx, [rbp+7D0h+var_720]; void *
0x140016d43  xor     edx, edx; Val
0x140016d45  mov     r8d, 4D0h; Size
0x140016d4b  movups  [rbp+7D0h+var_810], xmm0
0x140016d4f  call    memset_0
0x140016d54  xor     eax, eax
0x140016d56  mov     [rbp+7D0h+hMem], rbx
0x140016d5a  mov     [rbp+7D0h+var_838], rax
0x140016d5e  lea     rdx, [rbp+7D0h+hMem]; SecurityDescriptor
0x140016d62  xorps   xmm0, xmm0
0x140016d65  mov     [rsp+8D0h+hObject], rbx
0x140016d6a  lea     rax, ?static_MiniDumpCallback@CReflectedDump@@KAHPEAXQEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@@Z; CReflectedDump::static_MiniDumpCallback(void *,_MINIDUMP_CALLBACK_INPUT * const,_MINIDUMP_CALLBACK_OUTPUT *)
0x140016d71  mov     [rsp+8D0h+var_86C], ebx
0x140016d75  movups  [rbp+7D0h+var_848], xmm0
0x140016d79  mov     rcx, rsi; ProcessHandle
0x140016d7c  mov     [rbp+7D0h+CallbackParam.CallbackRoutine], rax
0x140016d80  mov     [rbp+7D0h+CallbackParam.CallbackParam], r15
0x140016d84  mov     dword ptr [rbp+7D0h+var_848], 18h
0x140016d8b  mov     dword ptr [rbp+7D0h+var_838], ebx
0x140016d8e  call    GetDumpSecurityDescriptor
0x140016d93  xor     esi, esi
0x140016d95  mov     r14d, eax
0x140016d98  test    eax, eax
0x140016d9a  jns     short loc_140016DD5
0x140016d9c  mov     rcx, cs:WPP_GLOBAL_Control
0x140016da3  lea     rbx, WPP_GLOBAL_Control
0x140016daa  cmp     rcx, rbx
0x140016dad  jz      loc_140016E54
0x140016db3  test    byte ptr [rcx+1Ch], 1
0x140016db7  jz      loc_140016E54
0x140016dbd  mov     rcx, [rcx+10h]
0x140016dc1  lea     edx, [rsi+1Eh]
0x140016dc4  mov     r9d, eax
0x140016dc7  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140016dce  call    WPP_SF_d
0x140016dd3  jmp     short loc_140016E54
0x140016dd5  mov     rax, [rbp+7D0h+hMem]
0x140016dd9  lea     rbx, aMdref; ".mdref"
0x140016de0  mov     r12d, dword ptr [rbp+7D0h+arg_20]
0x140016de7  and     r12d, 2
0x140016deb  mov     qword ptr [rbp+7D0h+var_848+8], rax
0x140016def  lea     rax, aTdref; ".tdref"
0x140016df6  cmovz   rbx, rax
0x140016dfa  test    rdi, rdi
0x140016dfd  jz      loc_140017095
0x140016e03  cmp     [rdi], si
0x140016e06  jz      loc_140017095
0x140016e0c  mov     rcx, rdi
0x140016e0f  call    cs:__imp_WerpValidateReportKey
0x140016e15  mov     r14d, eax
0x140016e18  test    eax, eax
0x140016e1a  jns     loc_140016F0B
0x140016e20  mov     rcx, cs:WPP_GLOBAL_Control
0x140016e27  lea     rbx, WPP_GLOBAL_Control
0x140016e2e  cmp     rcx, rbx
0x140016e31  jz      short loc_140016E51
0x140016e33  test    byte ptr [rcx+1Ch], 1
0x140016e37  jz      short loc_140016E51
0x140016e39  mov     edx, 1Fh
0x140016e3e  mov     r9d, eax
0x140016e41  mov     rcx, [rcx+10h]
0x140016e45  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140016e4c  call    WPP_SF_d
0x140016e51  mov     r12d, esi
0x140016e54  mov     rcx, [rsp+8D0h+hObject]; hObject
0x140016e59  mov     [rsp+8D0h+hObject], 0
0x140016e62  lea     rax, [rcx+1]
0x140016e66  cmp     rax, 1
0x140016e6a  jbe     short loc_140016E72
0x140016e6c  call    cs:__imp_CloseHandle
0x140016e72  mov     rcx, [rsp+8D0h+hFile]; hObject
0x140016e77  lea     rax, [rcx+1]
0x140016e7b  cmp     rax, 1
0x140016e7f  jbe     short loc_140016E87
0x140016e81  call    cs:__imp_CloseHandle
0x140016e87  mov     rcx, [rbp+7D0h+var_7F0+8]; hObject
0x140016e8b  test    rcx, rcx
0x140016e8e  jz      short loc_140016E9D
0x140016e90  call    CloseHandle_0
0x140016e95  mov     [rbp+7D0h+var_7F0+8], 0
0x140016e9d  test    r14d, r14d
0x140016ea0  jns     short loc_140016EAA
0x140016ea2  mov     rcx, r15; this
0x140016ea5  call    ?Cleanup@CReflectedDump@@QEAAXXZ; CReflectedDump::Cleanup(void)
0x140016eaa  test    r12d, r12d
0x140016ead  jz      short loc_140016EBA
0x140016eaf  mov     rcx, [rsp+8D0h+ProcessHandle]; ProcessHandle
0x140016eb4  call    cs:__imp_NtResumeProcess
0x140016eba  mov     rcx, [rsp+8D0h+hObject]; hObject
0x140016ebf  lea     rax, [rcx+1]
0x140016ec3  cmp     rax, 1
0x140016ec7  jbe     short loc_140016ECF
0x140016ec9  call    cs:__imp_CloseHandle
0x140016ecf  mov     rcx, [rbp+7D0h+hMem]; hMem
0x140016ed3  test    rcx, rcx
0x140016ed6  jz      short loc_140016EDE
0x140016ed8  call    cs:__imp_LocalFree
0x140016ede  mov     eax, r14d
0x140016ee1  mov     rcx, [rbp+7D0h+var_40]
0x140016ee8  xor     rcx, rsp; StackCookie
0x140016eeb  call    __security_check_cookie
0x140016ef0  mov     rbx, [rsp+8D0h+arg_18]
0x140016ef8  add     rsp, 8A0h
0x140016eff  pop     r15
0x140016f01  pop     r14
0x140016f03  pop     r13
0x140016f05  pop     r12
0x140016f07  pop     rdi
0x140016f08  pop     rsi
0x140016f09  pop     rbp
0x140016f0a  retn
0x140016f0b  lea     r8, [rsp+8D0h+var_86C]
0x140016f10  mov     [rsp+8D0h+var_86C], 104h
0x140016f18  lea     rdx, [rbp+7D0h+var_250]
0x140016f1f  mov     ecx, 3
0x140016f24  call    cs:__imp_WerpGetStorePath
0x140016f2a  mov     r14d, eax
0x140016f2d  test    eax, eax
0x140016f2f  jns     short loc_140016F5C
0x140016f31  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f38  lea     rbx, WPP_GLOBAL_Control
0x140016f3f  cmp     rcx, rbx
0x140016f42  jz      loc_140016E51
0x140016f48  test    byte ptr [rcx+1Ch], 1
0x140016f4c  jz      loc_140016E51
0x140016f52  mov     edx, 20h ; ' '
0x140016f57  jmp     loc_140016E3E
0x140016f5c  lea     r8, SubBlock; "\\"
0x140016f63  mov     edx, 104h; unsigned __int64
0x140016f68  lea     rcx, [rbp+7D0h+var_250]; wchar_t *
0x140016f6f  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140016f74  mov     r14d, eax
0x140016f77  test    eax, eax
0x140016f79  jns     short loc_140016FA6
0x140016f7b  mov     rcx, cs:WPP_GLOBAL_Control
0x140016f82  lea     rbx, WPP_GLOBAL_Control
0x140016f89  cmp     rcx, rbx
0x140016f8c  jz      loc_140016E51
0x140016f92  test    byte ptr [rcx+1Ch], 1
0x140016f96  jz      loc_140016E51
0x140016f9c  mov     edx, 21h ; '!'
0x140016fa1  jmp     loc_140016E3E
0x140016fa6  mov     r8, rdi; wchar_t *
0x140016fa9  lea     rcx, [rbp+7D0h+var_250]; wchar_t *
0x140016fb0  mov     edi, 104h
0x140016fb5  mov     edx, edi; unsigned __int64
0x140016fb7  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140016fbc  mov     r14d, eax
0x140016fbf  test    eax, eax
0x140016fc1  jns     short loc_140016FEE
0x140016fc3  mov     rcx, cs:WPP_GLOBAL_Control
0x140016fca  lea     rbx, WPP_GLOBAL_Control
0x140016fd1  cmp     rcx, rbx
0x140016fd4  jz      loc_140016E51
0x140016fda  test    byte ptr [rcx+1Ch], 1
0x140016fde  jz      loc_140016E51
0x140016fe4  mov     edx, 22h ; '"'
0x140016fe9  jmp     loc_140016E3E
0x140016fee  lea     r8, SubBlock; "\\"
0x140016ff5  mov     rdx, rdi; unsigned __int64
0x140016ff8  lea     rcx, [rbp+7D0h+var_250]; wchar_t *
0x140016fff  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140017004  mov     r14d, eax
0x140017007  test    eax, eax
0x140017009  jns     short loc_140017036
0x14001700b  mov     rcx, cs:WPP_GLOBAL_Control
0x140017012  lea     rbx, WPP_GLOBAL_Control
0x140017019  cmp     rcx, rbx
0x14001701c  jz      loc_140016E51
0x140017022  test    byte ptr [rcx+1Ch], 1
0x140017026  jz      loc_140016E51
0x14001702c  mov     edx, 23h ; '#'
0x140017031  jmp     loc_140016E3E
0x140017036  mov     dword ptr [rsp+8D0h+var_898], esi
0x14001703a  lea     rax, [rbp+7D0h+var_848]
0x14001703e  mov     [rsp+8D0h+dwOptions], esi
0x140017042  lea     r9, [r15+8]
0x140017046  mov     r8, rbx
0x140017049  mov     qword ptr [rsp+8D0h+bInheritHandle], rax
0x14001704e  lea     rdx, [rbp+7D0h+var_250]
0x140017055  lea     rcx, [rsp+8D0h+hFile]
0x14001705a  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x14001705f  mov     r14d, eax
0x140017062  test    eax, eax
0x140017064  jns     loc_1400170EB
0x14001706a  mov     rcx, cs:WPP_GLOBAL_Control
0x140017071  lea     rbx, WPP_GLOBAL_Control
0x140017078  cmp     rcx, rbx
0x14001707b  jz      loc_140017235
0x140017081  test    byte ptr [rcx+1Ch], 1
0x140017085  jz      loc_140017235
0x14001708b  mov     edx, 24h ; '$'
0x140017090  jmp     loc_140016E3E
0x140017095  mov     dword ptr [rsp+8D0h+var_898], esi
0x140017099  lea     rax, [rbp+7D0h+var_848]
0x14001709d  mov     [rsp+8D0h+dwOptions], esi
0x1400170a1  lea     r9, [r15+8]
0x1400170a5  mov     r8, rbx
0x1400170a8  mov     qword ptr [rsp+8D0h+bInheritHandle], rax
0x1400170ad  xor     edx, edx
0x1400170af  lea     rcx, [rsp+8D0h+hFile]
0x1400170b4  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x1400170b9  mov     r14d, eax
0x1400170bc  test    eax, eax
0x1400170be  jns     short loc_1400170EB
0x1400170c0  mov     rcx, cs:WPP_GLOBAL_Control
0x1400170c7  lea     rbx, WPP_GLOBAL_Control
0x1400170ce  cmp     rcx, rbx
0x1400170d1  jz      loc_140017235
0x1400170d7  test    byte ptr [rcx+1Ch], 1
0x1400170db  jz      loc_140017235
0x1400170e1  mov     edx, 25h ; '%'
0x1400170e6  jmp     loc_140016E3E
0x1400170eb  lea     rcx, [rsp+8D0h+hObject]
0x1400170f0  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x1400170f5  mov     rsi, rax
0x1400170f8  call    GetCurrentProcess_0
0x1400170fd  mov     rdi, rax
0x140017100  call    GetCurrentProcess_0
0x140017105  mov     rbx, rax
0x140017108  call    GetCurrentProcess_0
0x14001710d  mov     [rsp+8D0h+dwOptions], 0; dwOptions
0x140017115  mov     r9, rsi; lpTargetHandle
0x140017118  mov     [rsp+8D0h+bInheritHandle], 0; bInheritHandle
0x140017120  mov     r8, rdi; hTargetProcessHandle
0x140017123  mov     rdx, rbx; hSourceHandle
0x140017126  mov     [rsp+8D0h+dwDesiredAccess], 100000h; dwDesiredAccess
0x14001712e  mov     rcx, rax; hSourceProcessHandle
0x140017131  call    cs:__imp_DuplicateHandle
0x140017137  xor     esi, esi
0x140017139  test    eax, eax
0x14001713b  jnz     short loc_14001718E
0x14001713d  call    GetLastError_0
0x140017142  mov     r14d, eax
0x140017145  test    eax, eax
0x140017147  jle     short loc_140017154
0x140017149  movzx   r14d, ax
0x14001714d  or      r14d, 80070000h
0x140017154  test    r14d, r14d
0x140017157  mov     eax, 80004005h
0x14001715c  cmovns  r14d, eax
0x140017160  mov     rcx, cs:WPP_GLOBAL_Control
0x140017167  lea     rbx, WPP_GLOBAL_Control
0x14001716e  cmp     rcx, rbx
0x140017171  jz      loc_140017235
0x140017177  test    byte ptr [rcx+1Ch], 1
0x14001717b  jz      loc_140017235
0x140017181  mov     edx, 26h ; '&'
0x140017186  mov     r9d, r14d
0x140017189  jmp     loc_140016E41
0x14001718e  test    [rbp+7D0h+arg_20], 1
0x140017195  lea     rbx, WPP_GLOBAL_Control
0x14001719c  mov     rsi, [rsp+8D0h+ProcessHandle]
0x1400171a1  mov     edi, 0C0000000h
0x1400171a6  jnz     short loc_1400171EB
0x1400171a8  mov     rcx, rsi; ProcessHandle
0x1400171ab  call    cs:__imp_NtSuspendProcess
0x1400171b1  and     eax, edi
0x1400171b3  cmp     eax, edi
0x1400171b5  jnz     short loc_1400171E3
0x1400171b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400171be  cmp     rcx, rbx
0x1400171c1  jz      short loc_1400171EB
0x1400171c3  test    byte ptr [rcx+1Ch], 1
0x1400171c7  jz      short loc_1400171EB
0x1400171c9  mov     rcx, [rcx+10h]
0x1400171cd  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
  ... truncated ...
```
