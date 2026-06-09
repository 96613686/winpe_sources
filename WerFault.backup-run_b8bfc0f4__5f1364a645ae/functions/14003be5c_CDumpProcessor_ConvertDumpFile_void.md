# CDumpProcessor::ConvertDumpFile(void)

- ea: `0x14003be5c`
- end: `0x14003c392`
- name: `?ConvertDumpFile@CDumpProcessor@@AEAAJXZ`
- size: `1334`
- prototype: `__int64 __fastcall(CDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x14003d7d4`

## callees

- `0x140002728`
- `0x14000c8a0`
- `0x140034d9c`
- `0x14003bc28`
- `0x14003be5c`
- `0x14003c398`
- `0x14003cf74`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003c376`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003c376`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003bfc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003bfc8`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003bf7f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003bf7f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bfd3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003bfd3`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003bf6a`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003bf6a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003beae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003c2e4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003beae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003c2e4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003bebc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003c2f2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003bebc`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003c2f2`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c2ca`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003c2ca`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003bee5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003c106`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003bee5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003c106`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003c2d8`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003c2d8`

## string_xrefs

- `0x14003c005`: `UtilDebugCreateEx failed for IDebugClient4`
- `0x14003c06d`: `OpenDumpFileWide failed for %ws`
- `0x14003c16d`: `Copy failed`
- `0x14003bf2f`: `CreateMiniDumpFile failed`
- `0x14003c0f5`: `WriteDumpFileWide failed`
- `0x14003bfbe`: `DebugCreateEx`
- `0x14003bf78`: `dbgeng.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDumpProcessor::ConvertDumpFile(CDumpProcessor *this)
{
  HMODULE Library; // rsi
  char v3; // r14
  HANDLE CurrentThread; // rax
  unsigned int v5; // r8d
  DWORD TickCount; // r15d
  int v7; // edx
  int v8; // ebx
  const char *v9; // rax
  __int64 v10; // rdx
  __int64 (__fastcall ***v11)(_QWORD, _QWORD, _QWORD); // rcx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  DWORD v14; // eax
  int v15; // edx
  __int64 (__fastcall ***v16)(_QWORD, _QWORD, _QWORD); // rbx
  __int64 (__fastcall *v17)(_QWORD, GUID *, __int64 *); // r15
  __int64 v18; // rcx
  int v19; // ebx
  __int64 v20; // rcx
  __int64 v21; // rcx
  __int64 v22; // rcx
  __int64 (__fastcall ***v23)(_QWORD, _QWORD, _QWORD); // rcx
  HANDLE v24; // rax
  unsigned int v25; // r8d
  wil::details *v27; // [rsp+20h] [rbp-59h]
  char *v28; // [rsp+30h] [rbp-49h]
  HANDLE hObject; // [rsp+40h] [rbp-39h] BYREF
  HMODULE v30; // [rsp+48h] [rbp-31h]
  __int64 v31; // [rsp+50h] [rbp-29h] BYREF
  __int64 *v32; // [rsp+58h] [rbp-21h]
  LPCWSTR lpFileName; // [rsp+68h] [rbp-11h] BYREF
  _WORD *v34; // [rsp+70h] [rbp-9h]
  _WORD v35[44]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 (__fastcall ***v37)(_QWORD, GUID *, __int64 *); // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v38; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v39; // [rsp+F8h] [rbp+7Fh] BYREF

  Library = 0;
  v30 = 0;
  v37 = 0;
  v39 = 0;
  v38 = 0;
  hObject = 0;
  lpFileName = v35;
  v34 = v35;
  v35[0] = 0;
  v3 = 1;
  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 0x10000) )
  {
    wil::details::in1diag4::_Log_GetLastError(
      retaddr,
      (void *)0x359,
      v5,
      "CDumpProcessor::ConvertDumpFile",
      (const char *)v27);
    v3 = 0;
  }
  TickCount = GetTickCount();
  if ( *((_QWORD *)this + 1062) )
  {
    v7 = *((_DWORD *)this + 1050);
    if ( ((v7 - 1) & 0xFFFFFFFA) == 0 && v7 != 2 )
    {
      v8 = CDumpProcessor::CreateMiniDumpFile((__int64)this, (__int64)&lpFileName, &hObject);
      if ( v8 < 0 )
      {
        v9 = "CreateMiniDumpFile failed";
        v10 = 882;
LABEL_8:
        LODWORD(v27) = v8;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)v10,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
          "CDumpProcessor::ConvertDumpFile",
          v27,
          (int)v9,
          v28);
        goto LABEL_41;
      }
      SetEnvironmentVariableW(L"DBGENG_NO_BUGCHECK_ANALYSIS", L"1");
      Library = LoadLibraryExW(L"dbgeng.dll", 0, 0x800u);
      v30 = Library;
      if ( !Library )
      {
        v8 = -2147024770;
        v9 = "UtilLoadDbgEng failed";
        v10 = 900;
        goto LABEL_8;
      }
      v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
      v37 = 0;
      if ( v11 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v11)[2])(v11);
      ProcAddress = GetProcAddress(Library, "DebugCreateEx");
      if ( ProcAddress )
      {
        v8 = ((__int64 (__fastcall *)(GUID *, __int64, _QWORD))ProcAddress)(
               &GUID_ca83c3de_5089_4cf8_93c8_d892387f2a5e,
               688136,
               &v37);
      }
      else
      {
        LastError = GetLastError();
        v8 = LastError;
        if ( LastError > 0 )
          v8 = (unsigned __int16)LastError | 0x80070000;
      }
      if ( v8 < 0 )
      {
        v9 = "UtilDebugCreateEx failed for IDebugClient4";
        v10 = 918;
        goto LABEL_8;
      }
      v8 = tlx::queryinterface_unique<IDebugControl,IDebugClient4>(&v39, v37);
      if ( v8 < 0 )
      {
        v9 = "QueryInterface failed for IDebugControl";
        v10 = 929;
        goto LABEL_8;
      }
      v8 = (*v37)[60](v37, *((GUID **)this + 1062), 0);
      if ( v8 < 0 )
      {
        LODWORD(v27) = v8;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x3AC,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
          "CDumpProcessor::ConvertDumpFile",
          v27,
          (int)"OpenDumpFileWide failed for %ws",
          *((const char **)this + 1062));
        goto LABEL_41;
      }
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v39 + 744LL))(v39, 0, 0xFFFFFFFFLL);
      if ( v8 < 0 )
      {
        v9 = "WaitForEvent failed";
        v10 = 949;
        goto LABEL_8;
      }
      v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD, HANDLE, __int64, _DWORD, _QWORD))(*v37)[61])(
             v37,
             0,
             hObject,
             1024,
             0,
             0);
      if ( v8 < 0 )
      {
        v9 = "WriteDumpFileWide failed";
        v10 = 961;
        goto LABEL_8;
      }
      v14 = GetTickCount();
      v15 = v14 - TickCount - 1;
      if ( v14 >= TickCount )
        v15 = v14 - TickCount;
      LODWORD(v28) = v15;
      LODWORD(v27) = 0x80000000;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x3C5,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
        "CDumpProcessor::ConvertDumpFile",
        v27,
        (int)"*** Time for dump conversion (ms): %u",
        v28);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               (char *)this + 8464,
                               lpFileName,
                               v34 - lpFileName) )
      {
        v8 = -2147024882;
        v9 = "Copy failed";
        v10 = 970;
        goto LABEL_8;
      }
      v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
      v17 = **v37;
      v31 = 0;
      v32 = &v38;
      v18 = v38;
      v38 = 0;
      if ( v18 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v18 + 16LL))(v18);
      v19 = v17(v16, &GUID_23f79d6c_8aaf_4f7c_a607_9995f5407e63, &v31);
      if ( v31 )
      {
        v20 = *v32;
        *v32 = v31;
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
      }
      if ( v19 < 0 )
      {
        LODWORD(v27) = v19;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x3E4,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
          "CDumpProcessor::ConvertDumpFile",
          v27,
          (int)"QueryInterface failed for IDebugDataSpace3",
          v28);
      }
      else
      {
        LODWORD(v27) = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, _QWORD, _QWORD))(*(_QWORD *)v38 + 240LL))(v38, &GUID_IPT, 0, 0) >= 0 )
          *((_DWORD *)this + 2134) = 1;
      }
    }
  }
  v8 = 0;
LABEL_41:
  v21 = v38;
  v38 = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v22 = v39;
  v39 = 0;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
  if ( v37 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD))(*v37)[26])(v37, 0);
    v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v37;
  }
  v37 = 0;
  if ( v23 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v23)[2])(v23);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( v8 < 0 )
    DeleteFileW(lpFileName);
  if ( v3 )
  {
    v24 = GetCurrentThread();
    if ( !SetThreadPriority(v24, 0x20000) )
      wil::details::in1diag4::_Log_GetLastError(
        retaddr,
        (void *)0x354,
        v25,
        "CDumpProcessor::ConvertDumpFile::<lambda_9307bb9f91743f2c055a27a4b8f68368>::operator ()",
        (const char *)v27);
  }
  if ( lpFileName != v35 )
    operator delete((void *)lpFileName, (const struct std::nothrow_t *)&std::nothrow);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v39 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v39 + 16LL))(v39);
  if ( v37 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v37)[2])(v37);
  if ( Library )
    FreeLibrary(Library);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14003be5c  push    rbp
0x14003be5e  push    rbx
0x14003be5f  push    rsi
0x14003be60  push    rdi
0x14003be61  push    r12
0x14003be63  push    r13
0x14003be65  push    r14
0x14003be67  push    r15
0x14003be69  lea     rbp, [rsp-1Fh]
0x14003be6e  sub     rsp, 98h
0x14003be75  mov     rdi, rcx
0x14003be78  xor     r12d, r12d
0x14003be7b  mov     esi, r12d
0x14003be7e  mov     [rbp+57h+var_88], r12
0x14003be82  mov     [rbp+57h+arg_8], r12
0x14003be86  mov     [rbp+57h+arg_18], r12
0x14003be8a  mov     [rbp+57h+arg_10], r12
0x14003be8e  mov     [rbp+57h+hObject], r12
0x14003be92  lea     rax, [rbp+57h+var_58]
0x14003be96  mov     [rbp+57h+lpFileName], rax
0x14003be9a  lea     rax, [rbp+57h+var_58]
0x14003be9e  mov     [rbp+57h+var_60], rax
0x14003bea2  mov     [rbp+57h+var_58], r12w
0x14003bea7  mov     r14b, 1
0x14003beaa  mov     [rbp+57h+arg_1], r14b
0x14003beae  call    cs:__imp_GetCurrentThread
0x14003beb4  mov     rcx, rax; hThread
0x14003beb7  mov     edx, 10000h; nPriority
0x14003bebc  call    cs:__imp_SetThreadPriority
0x14003bec2  lea     r13, aCdumpprocessor_6; "CDumpProcessor::ConvertDumpFile"
0x14003bec9  test    eax, eax
0x14003becb  jnz     short loc_14003BEE5
0x14003becd  mov     rcx, [rbp+5Fh]; this
0x14003bed1  mov     r9, r13; char *
0x14003bed4  mov     edx, 359h; void *
0x14003bed9  call    ?_Log_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_Log_GetLastError(void *,uint,char const *,char const *)
0x14003bede  mov     r14b, r12b
0x14003bee1  mov     [rbp+57h+arg_1], r12b
0x14003bee5  call    cs:__imp_GetTickCount
0x14003beeb  mov     r15d, eax
0x14003beee  cmp     [rdi+2130h], r12
0x14003bef5  jz      loc_14003C251
0x14003befb  mov     edx, [rdi+1068h]
0x14003bf01  lea     ecx, [rdx-1]
0x14003bf04  test    ecx, 0FFFFFFFAh
0x14003bf0a  jnz     loc_14003C251
0x14003bf10  cmp     edx, 2
0x14003bf13  jz      loc_14003C251
0x14003bf19  lea     r8, [rbp+57h+hObject]
0x14003bf1d  lea     rdx, [rbp+57h+lpFileName]
0x14003bf21  mov     rcx, rdi
0x14003bf24  call    ?CreateMiniDumpFile@CDumpProcessor@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CDumpProcessor::CreateMiniDumpFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,tlx::unique_any<tlx::file_handle_traits> *)
0x14003bf29  mov     ebx, eax
0x14003bf2b  test    eax, eax
0x14003bf2d  jns     short loc_14003BF5C
0x14003bf2f  lea     rax, aCreateminidump; "CreateMiniDumpFile failed"
0x14003bf36  mov     edx, 372h; void *
0x14003bf3b  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x14003bf40  mov     rcx, [rbp+5Fh]; this
0x14003bf44  mov     dword ptr [rsp+0D0h+var_B0], ebx; wil::details *
0x14003bf48  mov     r9, r13; char *
0x14003bf4b  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003bf52  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003bf57  jmp     loc_14003C254
0x14003bf5c  lea     rdx, a1; "1"
0x14003bf63  lea     rcx, aDbgengNoBugche; "DBGENG_NO_BUGCHECK_ANALYSIS"
0x14003bf6a  call    cs:__imp_SetEnvironmentVariableW
0x14003bf70  xor     edx, edx; hFile
0x14003bf72  mov     r8d, 800h; dwFlags
0x14003bf78  lea     rcx, aDbgengDll; "dbgeng.dll"
0x14003bf7f  call    cs:__imp_LoadLibraryExW
0x14003bf85  mov     rsi, rax
0x14003bf88  mov     [rbp+57h+var_88], rax
0x14003bf8c  test    rax, rax
0x14003bf8f  jnz     short loc_14003BFA4
0x14003bf91  mov     ebx, 8007007Eh
0x14003bf96  lea     rax, aUtilloaddbgeng; "UtilLoadDbgEng failed"
0x14003bf9d  mov     edx, 384h
0x14003bfa2  jmp     short loc_14003BF3B
0x14003bfa4  mov     rcx, [rbp+57h+arg_8]
0x14003bfa8  mov     [rbp+57h+arg_8], r12
0x14003bfac  test    rcx, rcx
0x14003bfaf  jz      short loc_14003BFBE
0x14003bfb1  mov     rax, [rcx]
0x14003bfb4  mov     rax, [rax+10h]
0x14003bfb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bfbd  nop
0x14003bfbe  lea     rdx, aDebugcreateex; "DebugCreateEx"
0x14003bfc5  mov     rcx, rsi; hModule
0x14003bfc8  call    cs:__imp_GetProcAddress
0x14003bfce  test    rax, rax
0x14003bfd1  jnz     short loc_14003BFEA
0x14003bfd3  call    cs:__imp_GetLastError
0x14003bfd9  mov     ebx, eax
0x14003bfdb  test    eax, eax
0x14003bfdd  jle     short loc_14003C001
0x14003bfdf  movzx   ebx, ax
0x14003bfe2  or      ebx, 80070000h
0x14003bfe8  jmp     short loc_14003C001
0x14003bfea  lea     r8, [rbp+57h+arg_8]
0x14003bfee  mov     edx, 0A8008h
0x14003bff3  lea     rcx, _GUID_ca83c3de_5089_4cf8_93c8_d892387f2a5e
0x14003bffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003bfff  mov     ebx, eax
0x14003c001  test    ebx, ebx
0x14003c003  jns     short loc_14003C016
0x14003c005  lea     rax, aUtildebugcreat; "UtilDebugCreateEx failed for IDebugClie"...
0x14003c00c  mov     edx, 396h
0x14003c011  jmp     loc_14003BF3B
0x14003c016  mov     rdx, [rbp+57h+arg_8]
0x14003c01a  lea     rcx, [rbp+57h+arg_18]
0x14003c01e  call    ??$queryinterface_unique@UIDebugControl@@UIDebugClient4@@@tlx@@YAJPEAV?$unique_ptr@UIDebugControl@@Urelease_delete@tlx@@@utl@@AEAUIDebugClient4@@AEBU_GUID@@@Z; tlx::queryinterface_unique<IDebugControl,IDebugClient4>(utl::unique_ptr<IDebugControl,tlx::release_delete> *,IDebugClient4 &,_GUID const &)
0x14003c023  mov     ebx, eax
0x14003c025  test    eax, eax
0x14003c027  jns     short loc_14003C03A
0x14003c029  lea     rax, aQueryinterface_1; "QueryInterface failed for IDebugControl"
0x14003c030  mov     edx, 3A1h
0x14003c035  jmp     loc_14003BF3B
0x14003c03a  mov     rcx, [rbp+57h+arg_8]
0x14003c03e  mov     rax, [rcx]
0x14003c041  xor     r8d, r8d
0x14003c044  mov     rdx, [rdi+2130h]
0x14003c04b  mov     rax, [rax+1E0h]
0x14003c052  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c057  mov     ebx, eax
0x14003c059  test    eax, eax
0x14003c05b  jns     short loc_14003C096
0x14003c05d  mov     rcx, [rbp+5Fh]; this
0x14003c061  mov     rax, [rdi+2130h]
0x14003c068  mov     [rsp+0D0h+var_A0], rax; char *
0x14003c06d  lea     rax, aOpendumpfilewi; "OpenDumpFileWide failed for %ws"
0x14003c074  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x14003c079  mov     dword ptr [rsp+0D0h+var_B0], ebx; wil::details *
0x14003c07d  mov     r9, r13; char *
0x14003c080  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c087  mov     edx, 3ACh; void *
0x14003c08c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c091  jmp     loc_14003C254
0x14003c096  mov     rcx, [rbp+57h+arg_18]
0x14003c09a  mov     rax, [rcx]
0x14003c09d  or      r8d, 0FFFFFFFFh
0x14003c0a1  xor     edx, edx
0x14003c0a3  mov     rax, [rax+2E8h]
0x14003c0aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c0af  mov     ebx, eax
0x14003c0b1  test    eax, eax
0x14003c0b3  jns     short loc_14003C0C6
0x14003c0b5  lea     rax, aWaitforeventFa; "WaitForEvent failed"
0x14003c0bc  mov     edx, 3B5h
0x14003c0c1  jmp     loc_14003BF3B
0x14003c0c6  mov     rcx, [rbp+57h+arg_8]
0x14003c0ca  mov     rax, [rcx]
0x14003c0cd  mov     qword ptr [rsp+0D0h+var_A8], r12
0x14003c0d2  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x14003c0d7  mov     r9d, 400h
0x14003c0dd  mov     r8, [rbp+57h+hObject]
0x14003c0e1  xor     edx, edx
0x14003c0e3  mov     rax, [rax+1E8h]
0x14003c0ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c0ef  mov     ebx, eax
0x14003c0f1  test    eax, eax
0x14003c0f3  jns     short loc_14003C106
0x14003c0f5  lea     rax, aWritedumpfilew; "WriteDumpFileWide failed"
0x14003c0fc  mov     edx, 3C1h
0x14003c101  jmp     loc_14003BF3B
0x14003c106  call    cs:__imp_GetTickCount
0x14003c10c  mov     ecx, eax
0x14003c10e  sub     ecx, r15d
0x14003c111  lea     edx, [rcx-1]
0x14003c114  cmp     eax, r15d
0x14003c117  cmovnb  edx, ecx
0x14003c11a  mov     rcx, [rbp+5Fh]; this
0x14003c11e  mov     dword ptr [rsp+0D0h+var_A0], edx; char *
0x14003c122  lea     rax, aTimeForDumpCon; "*** Time for dump conversion (ms): %u"
0x14003c129  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x14003c12e  mov     dword ptr [rsp+0D0h+var_B0], 80000000h; wil::details *
0x14003c136  mov     r9, r13; char *
0x14003c139  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c140  mov     edx, 3C5h; void *
0x14003c145  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c14a  mov     r8, [rbp+57h+var_60]
0x14003c14e  mov     rdx, [rbp+57h+lpFileName]
0x14003c152  sub     r8, rdx
0x14003c155  sar     r8, 1
0x14003c158  lea     rcx, [rdi+2110h]
0x14003c15f  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003c164  test    al, al
0x14003c166  jnz     short loc_14003C17E
0x14003c168  mov     ebx, 8007000Eh
0x14003c16d  lea     rax, aCopyFailed; "Copy failed"
0x14003c174  mov     edx, 3CAh
0x14003c179  jmp     loc_14003BF3B
0x14003c17e  mov     rbx, [rbp+57h+arg_8]
0x14003c182  mov     rax, [rbx]
0x14003c185  mov     r15, [rax]
0x14003c188  mov     [rbp+57h+var_80], r12
0x14003c18c  lea     rax, [rbp+57h+arg_10]
0x14003c190  mov     [rbp+57h+var_78], rax
0x14003c194  mov     rcx, [rbp+57h+arg_10]
0x14003c198  mov     [rbp+57h+arg_10], r12
0x14003c19c  test    rcx, rcx
0x14003c19f  jz      short loc_14003C1AE
0x14003c1a1  mov     rax, [rcx]
0x14003c1a4  mov     rax, [rax+10h]
0x14003c1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c1ad  nop
0x14003c1ae  lea     r8, [rbp+57h+var_80]
0x14003c1b2  lea     rdx, _GUID_23f79d6c_8aaf_4f7c_a607_9995f5407e63
0x14003c1b9  mov     rcx, rbx
0x14003c1bc  mov     rax, r15
0x14003c1bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c1c4  mov     ebx, eax
0x14003c1c6  mov     rax, [rbp+57h+var_80]
0x14003c1ca  test    rax, rax
0x14003c1cd  jz      short loc_14003C1EB
0x14003c1cf  mov     rdx, [rbp+57h+var_78]
0x14003c1d3  mov     rcx, [rdx]
0x14003c1d6  mov     [rdx], rax
0x14003c1d9  test    rcx, rcx
0x14003c1dc  jz      short loc_14003C1EB
0x14003c1de  mov     rax, [rcx]
0x14003c1e1  mov     rax, [rax+10h]
0x14003c1e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c1ea  nop
0x14003c1eb  test    ebx, ebx
0x14003c1ed  js      short loc_14003C229
0x14003c1ef  mov     rcx, [rbp+57h+arg_10]
0x14003c1f3  mov     rax, [rcx]
0x14003c1f6  mov     qword ptr [rsp+0D0h+var_A8], r12
0x14003c1fb  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x14003c200  xor     r9d, r9d
0x14003c203  xor     r8d, r8d
0x14003c206  lea     rdx, GUID_IPT
0x14003c20d  mov     rax, [rax+0F0h]
0x14003c214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c219  test    eax, eax
0x14003c21b  js      short loc_14003C251
0x14003c21d  mov     dword ptr [rdi+2158h], 1
0x14003c227  jmp     short loc_14003C251
0x14003c229  mov     rcx, [rbp+5Fh]; this
0x14003c22d  lea     rax, aQueryinterface; "QueryInterface failed for IDebugDataSpa"...
0x14003c234  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x14003c239  mov     dword ptr [rsp+0D0h+var_B0], ebx; char *
0x14003c23d  mov     r9, r13; char *
0x14003c240  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003c247  mov     edx, 3E4h; void *
0x14003c24c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003c251  mov     ebx, r12d
0x14003c254  mov     rcx, [rbp+57h+arg_10]
0x14003c258  mov     [rbp+57h+arg_10], r12
0x14003c25c  test    rcx, rcx
0x14003c25f  jz      short loc_14003C26E
0x14003c261  mov     rax, [rcx]
0x14003c264  mov     rax, [rax+10h]
0x14003c268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c26d  nop
0x14003c26e  mov     rcx, [rbp+57h+arg_18]
0x14003c272  mov     [rbp+57h+arg_18], r12
0x14003c276  test    rcx, rcx
0x14003c279  jz      short loc_14003C288
0x14003c27b  mov     rax, [rcx]
0x14003c27e  mov     rax, [rax+10h]
0x14003c282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c287  nop
0x14003c288  mov     rcx, [rbp+57h+arg_8]
0x14003c28c  test    rcx, rcx
0x14003c28f  jz      short loc_14003C2A6
0x14003c291  mov     rax, [rcx]
0x14003c294  xor     edx, edx
0x14003c296  mov     rax, [rax+0D0h]
0x14003c29d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c2a2  mov     rcx, [rbp+57h+arg_8]
0x14003c2a6  mov     [rbp+57h+arg_8], r12
0x14003c2aa  test    rcx, rcx
0x14003c2ad  jz      short loc_14003C2BC
0x14003c2af  mov     rax, [rcx]
0x14003c2b2  mov     rax, [rax+10h]
0x14003c2b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003c2bb  nop
0x14003c2bc  mov     rcx, [rbp+57h+hObject]; hObject
0x14003c2c0  lea     rax, [rcx+1]
0x14003c2c4  cmp     rax, 1
0x14003c2c8  jbe     short loc_14003C2D0
0x14003c2ca  call    cs:__imp_CloseHandle
0x14003c2d0  test    ebx, ebx
0x14003c2d2  jns     short loc_14003C2DF
0x14003c2d4  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x14003c2d8  call    cs:__imp_DeleteFileW
0x14003c2de  nop
0x14003c2df  test    r14b, r14b
0x14003c2e2  jz      short loc_14003C312
0x14003c2e4  call    cs:__imp_GetCurrentThread
0x14003c2ea  mov     rcx, rax; hThread
0x14003c2ed  mov     edx, 20000h; nPriority
0x14003c2f2  call    cs:__imp_SetThreadPriority
0x14003c2f8  mov     rcx, [rbp+5Fh]; this
0x14003c2fc  test    eax, eax
0x14003c2fe  jnz     short loc_14003C312
0x14003c300  lea     r9, aCdumpprocessor_8; "CDumpProcessor::ConvertDumpFile::<lambd"...
0x14003c307  mov     edx, 354h; void *
  ... truncated ...
```
