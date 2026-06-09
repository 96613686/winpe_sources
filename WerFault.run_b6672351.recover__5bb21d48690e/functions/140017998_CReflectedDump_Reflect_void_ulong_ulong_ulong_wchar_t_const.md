# CReflectedDump::Reflect(void *,ulong,ulong,ulong,wchar_t const *)

- ea: `0x140017998`
- end: `0x14001826e`
- name: `?Reflect@CReflectedDump@@IEAAJPEAXKKKPEB_W@Z`
- size: `2262`
- prototype: `__int64 __usercall@<rax>(CReflectedDump *__hidden this@<rcx>, HANDLE ProcessHandle@<rdx>, DWORD dwThreadId@<r8d>, unsigned int@<r9d>, unsigned int, const wchar_t *)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140018280`

## callees

- `0x140001d64`
- `0x140002490`
- `0x1400030f8`
- `0x14000333f`
- `0x14000334b`
- `0x140003363`
- `0x140005550`
- `0x14000b448`
- `0x140014ee4`
- `0x140014f14`
- `0x140014f58`
- `0x1400158e8`
- `0x140016c24`
- `0x140016e8c`
- `0x14001715c`
- `0x140017998`
- `0x140018af8`
- `0x140019680`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140017f09`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140017fae`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140017f09`
- `api-ms-win-core-processthreads-l1-1-0!GetProcessId` at `0x140017fae`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017bc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018221`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b51`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017b6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140017bc0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140018221`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140017e3b`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x140017e3b`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140017f9c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140018121`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140018137`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400181f0`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140017f9c`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140018121`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140018137`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400181f0`
- `ntdll!RtlCreateProcessReflection` at `0x140018165`
- `ntdll!RtlCreateProcessReflection` at `0x140018165`
- `ntdll!NtResumeProcess` at `0x140017ba5`
- `ntdll!NtResumeProcess` at `0x14001810d`
- `ntdll!NtResumeProcess` at `0x140017ba5`
- `ntdll!NtResumeProcess` at `0x14001810d`
- `ntdll!NtSuspendProcess` at `0x140017ebb`
- `ntdll!NtSuspendProcess` at `0x140017ebb`
- `wer!WerpValidateReportKey` at `0x140017aee`
- `wer!WerpValidateReportKey` at `0x140017aee`
- `wer!WerpGetStorePath` at `0x140017c28`
- `wer!WerpGetStorePath` at `0x140017c28`
- `dbghelp!MiniDumpWriteDump` at `0x140017fe2`
- `dbghelp!MiniDumpWriteDump` at `0x140017fe2`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017bd5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x140017bd5`

## pseudocode

```c
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
  DWORD TickCount; // r12d
  DWORD v31; // eax
  int v32; // r8d
  int v33; // r9d
  DWORD v34; // edi
  int ProcessReflection; // r14d
  void *v36; // rcx
  int v37; // [rsp+50h] [rbp-B0h]
  unsigned int v38; // [rsp+58h] [rbp-A8h] BYREF
  unsigned int v39; // [rsp+60h] [rbp-A0h] BYREF
  int v40; // [rsp+64h] [rbp-9Ch] BYREF
  HANDLE hObject; // [rsp+68h] [rbp-98h] BYREF
  HANDLE hFile; // [rsp+70h] [rbp-90h] BYREF
  HANDLE ProcessHandlea; // [rsp+78h] [rbp-88h]
  HLOCAL hMem; // [rsp+80h] [rbp-80h]
  __int128 v45; // [rsp+88h] [rbp-78h]
  __int64 v46; // [rsp+98h] [rbp-68h]
  char *v47; // [rsp+A0h] [rbp-60h] BYREF
  const WCHAR *v48; // [rsp+A8h] [rbp-58h] BYREF
  const wchar_t *v49; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v50; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v51; // [rsp+C0h] [rbp-40h] BYREF
  _MINIDUMP_EXCEPTION_INFORMATION ExceptionParam; // [rsp+D0h] [rbp-30h] BYREF
  HANDLE v53[2]; // [rsp+E0h] [rbp-20h]
  __int128 v54; // [rsp+F0h] [rbp-10h]
  _MINIDUMP_CALLBACK_INFORMATION CallbackParam; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v56[160]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v57[1232]; // [rsp+1B0h] [rbp+B0h] BYREF
  wchar_t v58[264]; // [rsp+680h] [rbp+580h] BYREF

  ProcessHandlea = ProcessHandle;
  v6 = dwThreadId;
  v38 = dwThreadId;
  v37 = 0;
  hFile = 0;
  v39 = a4;
  *(_OWORD *)v53 = 0;
  v9 = 0;
  v54 = 0;
  ExceptionParam = 0;
  memset_0(v56, 0, 0x98u);
  v51 = 0;
  memset_0(v57, 0, sizeof(v57));
  hMem = 0;
  hObject = 0;
  v40 = 0;
  v45 = 0;
  CallbackParam.CallbackRoutine = (MINIDUMP_CALLBACK_ROUTINE)CReflectedDump::static_MiniDumpCallback;
  CallbackParam.CallbackParam = this;
  LODWORD(v45) = 24;
  v46 = 0;
  DumpSecurityDescriptor = GetDumpSecurityDescriptor(ProcessHandle);
  v11 = DumpSecurityDescriptor;
  if ( DumpSecurityDescriptor >= 0 )
  {
    v12 = L".mdref";
    *((_QWORD *)&v45 + 1) = hMem;
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
      v40 = 260;
      StorePath = WerpGetStorePath(3, v58, &v40);
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
      StorePath = StringCchCatW(v58, 0x104u, L"\\");
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
      StorePath = StringCchCatW(v58, 0x104u, a6);
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
      StorePath = StringCchCatW(v58, 0x104u, L"\\");
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
      StorePath = UtilGetTempFile(&hFile, v58, v12, (char *)this + 8);
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
        v37 = 1;
      }
    }
    if ( !v6 )
    {
      ProcessId = GetProcessId(v24);
      FirstThreadInProcess = GetFirstThreadInProcess(ProcessId, &v38);
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
      v6 = v38;
    }
    ExceptionParam.ExceptionPointers = (PEXCEPTION_POINTERS)&v51;
    *((_QWORD *)&v51 + 1) = v57;
    *(_QWORD *)&v51 = v56;
    SetExceptionInformation(v6, v39, &ExceptionParam);
    TickCount = GetTickCount();
    v31 = GetProcessId(v24);
    if ( MiniDumpWriteDump(
           v24,
           v31,
           hFile,
           (MINIDUMP_TYPE)((a5 & 2) != 0
                         ? MiniDumpWithThreadInfo|MiniDumpWithProcessThreadData|MiniDumpWithUnloadedModules|MiniDumpWithHandleData
                         : MiniDumpFilterTriage|MiniDumpWithProcessThreadData|MiniDumpFilterModulePaths|MiniDumpWithUnloadedModules|MiniDumpWithHandleData),
           &ExceptionParam,
           0,
           &CallbackParam) )
    {
      v11 = 0;
    }
    else
    {
      v11 = GetLastError_0();
    }
    if ( (unsigned int)dword_14007E038 > 5
      && (qword_14007E048 & 0x400000000000LL) != 0
      && (qword_14007E050 & 0x400000000000LL) == qword_14007E050 )
    {
      v39 = (a5 & 2) != 0 ? 4388 : 1048996;
      v47 = (char *)this + 8;
      v38 = v11;
      v48 = &pwzValue;
      v49 = L"Reflection";
      v50 = 0x1000000;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>,_tlgWrapSz<wchar_t>>(
        qword_14007E050,
        (unsigned int)&unk_1400730A0,
        v32,
        v33,
        (__int64)&v50,
        (__int64)&v38,
        (__int64)&v49,
        (__int64)&v48,
        (__int64)&v39,
        (__int64)&v47);
    }
    v27 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    {
      WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 41, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
      v27 = WPP_GLOBAL_Control;
    }
    if ( v11 < 0 )
    {
      if ( v27 == (CUserModeHangReport *)&WPP_GLOBAL_Control || (*((_BYTE *)v27 + 28) & 1) == 0 )
        goto LABEL_75;
      v28 = 42;
      goto LABEL_91;
    }
    if ( v37 )
    {
      NtResumeProcess(v24);
      v37 = 0;
    }
    *((_DWORD *)this + 136) = GetTickCount() - TickCount;
    v34 = GetTickCount();
    ProcessReflection = RtlCreateProcessReflection(v24, 12, 0);
    if ( (ProcessReflection & 0xC0000000) != 0xC0000000 )
    {
      if ( (unsigned int)VerifyReflectedProcessHandle(v24, v53[0]) )
      {
        *((_DWORD *)this + 137) = GetTickCount() - v34;
        v36 = (void *)*((_QWORD *)this + 66);
        *((HANDLE *)this + 66) = v53[0];
        if ( (unsigned __int64)v36 + 1 > 1 )
          CloseHandle(v36);
        if ( WPP_GLOBAL_Control != (CUserModeHangReport *)&WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        {
          WPP_SF_Dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 45, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids);
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
    v9 = v37;
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
  if ( v53[1] )
  {
    CloseHandle_0(v53[1]);
    v53[1] = 0;
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
0x140017998  mov     [rsp-8+arg_18], rbx
0x14001799d  push    rbp
0x14001799e  push    rsi
0x14001799f  push    rdi
0x1400179a0  push    r12
0x1400179a2  push    r13
0x1400179a4  push    r14
0x1400179a6  push    r15
0x1400179a8  lea     rbp, [rsp-7A0h]
0x1400179b0  sub     rsp, 8A0h
0x1400179b7  mov     rax, cs:__security_cookie
0x1400179be  xor     rax, rsp
0x1400179c1  mov     [rbp+7D0h+var_40], rax
0x1400179c8  mov     rdi, [rbp+7D0h+arg_28]
0x1400179cf  xorps   xmm0, xmm0
0x1400179d2  xor     ebx, ebx
0x1400179d4  mov     [rsp+8D0h+ProcessHandle], rdx
0x1400179d9  mov     r13d, r8d
0x1400179dc  mov     [rsp+8D0h+var_878], r8d
0x1400179e1  mov     rsi, rdx
0x1400179e4  mov     [rsp+8D0h+var_880], ebx
0x1400179e8  mov     r15, rcx
0x1400179eb  mov     [rsp+8D0h+hFile], rbx
0x1400179f0  xor     edx, edx; Val
0x1400179f2  mov     [rsp+8D0h+var_870], r9d
0x1400179f7  mov     r8d, 98h; Size
0x1400179fd  lea     rcx, [rbp+7D0h+var_7C0]; void *
0x140017a01  movups  xmmword ptr [rbp+7D0h+var_7F0], xmm0
0x140017a05  mov     r12d, ebx
0x140017a08  movups  [rbp+7D0h+var_7E0], xmm0
0x140017a0c  movups  xmmword ptr [rbp+7D0h+ExceptionParam.ThreadId], xmm0
0x140017a10  call    memset_0
0x140017a15  xorps   xmm0, xmm0
0x140017a18  lea     rcx, [rbp+7D0h+var_720]; void *
0x140017a1f  xor     edx, edx; Val
0x140017a21  mov     r8d, 4D0h; Size
0x140017a27  movups  [rbp+7D0h+var_810], xmm0
0x140017a2b  call    memset_0
0x140017a30  xor     eax, eax
0x140017a32  mov     [rbp+7D0h+hMem], rbx
0x140017a36  mov     [rbp+7D0h+var_838], rax
0x140017a3a  lea     rdx, [rbp+7D0h+hMem]
0x140017a3e  xorps   xmm0, xmm0
0x140017a41  mov     [rsp+8D0h+hObject], rbx
0x140017a46  lea     rax, ?static_MiniDumpCallback@CReflectedDump@@KAHPEAXQEAU_MINIDUMP_CALLBACK_INPUT@@PEAU_MINIDUMP_CALLBACK_OUTPUT@@@Z; CReflectedDump::static_MiniDumpCallback(void *,_MINIDUMP_CALLBACK_INPUT * const,_MINIDUMP_CALLBACK_OUTPUT *)
0x140017a4d  mov     [rsp+8D0h+var_86C], ebx
0x140017a51  movups  [rbp+7D0h+var_848], xmm0
0x140017a55  mov     rcx, rsi; ProcessHandle
0x140017a58  mov     [rbp+7D0h+CallbackParam.CallbackRoutine], rax
0x140017a5c  mov     [rbp+7D0h+CallbackParam.CallbackParam], r15
0x140017a60  mov     dword ptr [rbp+7D0h+var_848], 18h
0x140017a67  mov     dword ptr [rbp+7D0h+var_838], ebx
0x140017a6a  call    GetDumpSecurityDescriptor
0x140017a6f  xor     esi, esi
0x140017a71  mov     r14d, eax
0x140017a74  test    eax, eax
0x140017a76  jns     short loc_140017AB4
0x140017a78  mov     rcx, cs:WPP_GLOBAL_Control
0x140017a7f  lea     rbx, WPP_GLOBAL_Control
0x140017a86  cmp     rcx, rbx
0x140017a89  jz      loc_140017B39
0x140017a8f  test    byte ptr [rcx+1Ch], 1
0x140017a93  jz      loc_140017B39
0x140017a99  mov     rcx, [rcx+10h]
0x140017a9d  lea     edx, [rsi+1Eh]
0x140017aa0  mov     r9d, eax
0x140017aa3  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140017aaa  call    WPP_SF_d
0x140017aaf  jmp     loc_140017B39
0x140017ab4  mov     rax, [rbp+7D0h+hMem]
0x140017ab8  lea     rbx, aMdref; ".mdref"
0x140017abf  mov     r12d, dword ptr [rbp+7D0h+arg_20]
0x140017ac6  and     r12d, 2
0x140017aca  mov     qword ptr [rbp+7D0h+var_848+8], rax
0x140017ace  lea     rax, aTdref; ".tdref"
0x140017ad5  cmovz   rbx, rax
0x140017ad9  test    rdi, rdi
0x140017adc  jz      loc_140017D9F
0x140017ae2  cmp     [rdi], si
0x140017ae5  jz      loc_140017D9F
0x140017aeb  mov     rcx, rdi
0x140017aee  call    cs:__imp_WerpValidateReportKey
0x140017af5  nop     dword ptr [rax+rax+00h]
0x140017afa  mov     r14d, eax
0x140017afd  test    eax, eax
0x140017aff  jns     loc_140017C0F
0x140017b05  mov     rcx, cs:WPP_GLOBAL_Control
0x140017b0c  lea     rbx, WPP_GLOBAL_Control
0x140017b13  cmp     rcx, rbx
0x140017b16  jz      short loc_140017B36
0x140017b18  test    byte ptr [rcx+1Ch], 1
0x140017b1c  jz      short loc_140017B36
0x140017b1e  mov     edx, 1Fh
0x140017b23  mov     r9d, eax
0x140017b26  mov     rcx, [rcx+10h]
0x140017b2a  lea     r8, WPP_f9e44dbee75b3558d00969aa72bc6ede_Traceguids
0x140017b31  call    WPP_SF_d
0x140017b36  mov     r12d, esi
0x140017b39  mov     rcx, [rsp+8D0h+hObject]; hObject
0x140017b3e  mov     [rsp+8D0h+hObject], 0
0x140017b47  lea     rax, [rcx+1]
0x140017b4b  cmp     rax, 1
0x140017b4f  jbe     short loc_140017B5D
0x140017b51  call    cs:__imp_CloseHandle
0x140017b58  nop     dword ptr [rax+rax+00h]
0x140017b5d  mov     rcx, [rsp+8D0h+hFile]; hObject
0x140017b62  lea     rax, [rcx+1]
0x140017b66  cmp     rax, 1
0x140017b6a  jbe     short loc_140017B78
0x140017b6c  call    cs:__imp_CloseHandle
0x140017b73  nop     dword ptr [rax+rax+00h]
0x140017b78  mov     rcx, [rbp+7D0h+var_7F0+8]; hObject
0x140017b7c  test    rcx, rcx
0x140017b7f  jz      short loc_140017B8E
0x140017b81  call    CloseHandle_0
0x140017b86  mov     [rbp+7D0h+var_7F0+8], 0
0x140017b8e  test    r14d, r14d
0x140017b91  jns     short loc_140017B9B
0x140017b93  mov     rcx, r15; this
0x140017b96  call    ?Cleanup@CReflectedDump@@QEAAXXZ; CReflectedDump::Cleanup(void)
0x140017b9b  test    r12d, r12d
0x140017b9e  jz      short loc_140017BB1
0x140017ba0  mov     rcx, [rsp+8D0h+ProcessHandle]; ProcessHandle
0x140017ba5  call    cs:__imp_NtResumeProcess
0x140017bac  nop     dword ptr [rax+rax+00h]
0x140017bb1  mov     rcx, [rsp+8D0h+hObject]; hObject
0x140017bb6  lea     rax, [rcx+1]
0x140017bba  cmp     rax, 1
0x140017bbe  jbe     short loc_140017BCC
0x140017bc0  call    cs:__imp_CloseHandle
0x140017bc7  nop     dword ptr [rax+rax+00h]
0x140017bcc  mov     rcx, [rbp+7D0h+hMem]; hMem
0x140017bd0  test    rcx, rcx
0x140017bd3  jz      short loc_140017BE1
0x140017bd5  call    cs:__imp_LocalFree
0x140017bdc  nop     dword ptr [rax+rax+00h]
0x140017be1  mov     eax, r14d
0x140017be4  mov     rcx, [rbp+7D0h+var_40]
0x140017beb  xor     rcx, rsp; StackCookie
0x140017bee  call    __security_check_cookie
0x140017bf3  mov     rbx, [rsp+8D0h+arg_18]
0x140017bfb  add     rsp, 8A0h
0x140017c02  pop     r15
0x140017c04  pop     r14
0x140017c06  pop     r13
0x140017c08  pop     r12
0x140017c0a  pop     rdi
0x140017c0b  pop     rsi
0x140017c0c  pop     rbp
0x140017c0d  retn
0x140017c0f  lea     r8, [rsp+8D0h+var_86C]
0x140017c14  mov     [rsp+8D0h+var_86C], 104h
0x140017c1c  lea     rdx, [rbp+7D0h+var_250]
0x140017c23  mov     ecx, 3
0x140017c28  call    cs:__imp_WerpGetStorePath
0x140017c2f  nop     dword ptr [rax+rax+00h]
0x140017c34  mov     r14d, eax
0x140017c37  test    eax, eax
0x140017c39  jns     short loc_140017C66
0x140017c3b  mov     rcx, cs:WPP_GLOBAL_Control
0x140017c42  lea     rbx, WPP_GLOBAL_Control
0x140017c49  cmp     rcx, rbx
0x140017c4c  jz      loc_140017B36
0x140017c52  test    byte ptr [rcx+1Ch], 1
0x140017c56  jz      loc_140017B36
0x140017c5c  mov     edx, 20h ; ' '
0x140017c61  jmp     loc_140017B23
0x140017c66  lea     r8, SubBlock; "\\"
0x140017c6d  mov     edx, 104h; unsigned __int64
0x140017c72  lea     rcx, [rbp+7D0h+var_250]; wchar_t *
0x140017c79  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140017c7e  mov     r14d, eax
0x140017c81  test    eax, eax
0x140017c83  jns     short loc_140017CB0
0x140017c85  mov     rcx, cs:WPP_GLOBAL_Control
0x140017c8c  lea     rbx, WPP_GLOBAL_Control
0x140017c93  cmp     rcx, rbx
0x140017c96  jz      loc_140017B36
0x140017c9c  test    byte ptr [rcx+1Ch], 1
0x140017ca0  jz      loc_140017B36
0x140017ca6  mov     edx, 21h ; '!'
0x140017cab  jmp     loc_140017B23
0x140017cb0  mov     r8, rdi; wchar_t *
0x140017cb3  lea     rcx, [rbp+7D0h+var_250]; wchar_t *
0x140017cba  mov     edi, 104h
0x140017cbf  mov     edx, edi; unsigned __int64
0x140017cc1  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140017cc6  mov     r14d, eax
0x140017cc9  test    eax, eax
0x140017ccb  jns     short loc_140017CF8
0x140017ccd  mov     rcx, cs:WPP_GLOBAL_Control
0x140017cd4  lea     rbx, WPP_GLOBAL_Control
0x140017cdb  cmp     rcx, rbx
0x140017cde  jz      loc_140017B36
0x140017ce4  test    byte ptr [rcx+1Ch], 1
0x140017ce8  jz      loc_140017B36
0x140017cee  mov     edx, 22h ; '"'
0x140017cf3  jmp     loc_140017B23
0x140017cf8  lea     r8, SubBlock; "\\"
0x140017cff  mov     rdx, rdi; unsigned __int64
0x140017d02  lea     rcx, [rbp+7D0h+var_250]; wchar_t *
0x140017d09  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x140017d0e  mov     r14d, eax
0x140017d11  test    eax, eax
0x140017d13  jns     short loc_140017D40
0x140017d15  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d1c  lea     rbx, WPP_GLOBAL_Control
0x140017d23  cmp     rcx, rbx
0x140017d26  jz      loc_140017B36
0x140017d2c  test    byte ptr [rcx+1Ch], 1
0x140017d30  jz      loc_140017B36
0x140017d36  mov     edx, 23h ; '#'
0x140017d3b  jmp     loc_140017B23
0x140017d40  mov     dword ptr [rsp+8D0h+var_898], esi
0x140017d44  lea     rax, [rbp+7D0h+var_848]
0x140017d48  mov     [rsp+8D0h+dwOptions], esi
0x140017d4c  lea     r9, [r15+8]
0x140017d50  mov     r8, rbx
0x140017d53  mov     qword ptr [rsp+8D0h+bInheritHandle], rax
0x140017d58  lea     rdx, [rbp+7D0h+var_250]
0x140017d5f  lea     rcx, [rsp+8D0h+hFile]
0x140017d64  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x140017d69  mov     r14d, eax
0x140017d6c  test    eax, eax
0x140017d6e  jns     loc_140017DF5
0x140017d74  mov     rcx, cs:WPP_GLOBAL_Control
0x140017d7b  lea     rbx, WPP_GLOBAL_Control
0x140017d82  cmp     rcx, rbx
0x140017d85  jz      loc_140017F51
0x140017d8b  test    byte ptr [rcx+1Ch], 1
0x140017d8f  jz      loc_140017F51
0x140017d95  mov     edx, 24h ; '$'
0x140017d9a  jmp     loc_140017B23
0x140017d9f  mov     dword ptr [rsp+8D0h+var_898], esi
0x140017da3  lea     rax, [rbp+7D0h+var_848]
0x140017da7  mov     [rsp+8D0h+dwOptions], esi
0x140017dab  lea     r9, [r15+8]
0x140017daf  mov     r8, rbx
0x140017db2  mov     qword ptr [rsp+8D0h+bInheritHandle], rax
0x140017db7  xor     edx, edx
0x140017db9  lea     rcx, [rsp+8D0h+hFile]
0x140017dbe  call    ?UtilGetTempFile@@YAJPEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@PEB_W1PEA_WKPEAU_SECURITY_ATTRIBUTES@@KK@Z; UtilGetTempFile(tlx::unique_any<tlx::file_handle_traits> *,wchar_t const *,wchar_t const *,wchar_t *,ulong,_SECURITY_ATTRIBUTES *,ulong,ulong)
0x140017dc3  mov     r14d, eax
0x140017dc6  test    eax, eax
0x140017dc8  jns     short loc_140017DF5
0x140017dca  mov     rcx, cs:WPP_GLOBAL_Control
0x140017dd1  lea     rbx, WPP_GLOBAL_Control
0x140017dd8  cmp     rcx, rbx
0x140017ddb  jz      loc_140017F51
0x140017de1  test    byte ptr [rcx+1Ch], 1
0x140017de5  jz      loc_140017F51
0x140017deb  mov     edx, 25h ; '%'
0x140017df0  jmp     loc_140017B23
0x140017df5  lea     rcx, [rsp+8D0h+hObject]
0x140017dfa  call    ??$replace@Ufile_handle_traits@tlx@@@tlx@@YAPEAPEAXAEAV?$unique_any@Ufile_handle_traits@tlx@@@0@@Z; tlx::replace<tlx::file_handle_traits>(tlx::unique_any<tlx::file_handle_traits> &)
0x140017dff  mov     rsi, rax
0x140017e02  call    GetCurrentProcess_0
0x140017e07  mov     rdi, rax
0x140017e0a  call    GetCurrentProcess_0
0x140017e0f  mov     rbx, rax
0x140017e12  call    GetCurrentProcess_0
0x140017e17  mov     [rsp+8D0h+dwOptions], 0; dwOptions
0x140017e1f  mov     r9, rsi; lpTargetHandle
0x140017e22  mov     [rsp+8D0h+bInheritHandle], 0; bInheritHandle
0x140017e2a  mov     r8, rdi; hTargetProcessHandle
0x140017e2d  mov     rdx, rbx; hSourceHandle
0x140017e30  mov     [rsp+8D0h+dwDesiredAccess], 100000h; dwDesiredAccess
0x140017e38  mov     rcx, rax; hSourceProcessHandle
0x140017e3b  call    cs:__imp_DuplicateHandle
0x140017e42  nop     dword ptr [rax+rax+00h]
0x140017e47  xor     esi, esi
0x140017e49  test    eax, eax
0x140017e4b  jnz     short loc_140017E9E
0x140017e4d  call    GetLastError_0
0x140017e52  mov     r14d, eax
0x140017e55  test    eax, eax
0x140017e57  jle     short loc_140017E64
0x140017e59  movzx   r14d, ax
0x140017e5d  or      r14d, 80070000h
0x140017e64  test    r14d, r14d
0x140017e67  mov     eax, 80004005h
0x140017e6c  cmovns  r14d, eax
0x140017e70  mov     rcx, cs:WPP_GLOBAL_Control
0x140017e77  lea     rbx, WPP_GLOBAL_Control
0x140017e7e  cmp     rcx, rbx
0x140017e81  jz      loc_140017F51
0x140017e87  test    byte ptr [rcx+1Ch], 1
0x140017e8b  jz      loc_140017F51
0x140017e91  mov     edx, 26h ; '&'
0x140017e96  mov     r9d, r14d
0x140017e99  jmp     loc_140017B26
0x140017e9e  test    [rbp+7D0h+arg_20], 1
0x140017ea5  lea     rbx, WPP_GLOBAL_Control
0x140017eac  mov     rsi, [rsp+8D0h+ProcessHandle]
0x140017eb1  mov     edi, 0C0000000h
0x140017eb6  jnz     short loc_140017F01
0x140017eb8  mov     rcx, rsi; ProcessHandle
0x140017ebb  call    cs:__imp_NtSuspendProcess
0x140017ec2  nop     dword ptr [rax+rax+00h]
0x140017ec7  and     eax, edi
  ... truncated ...
```
