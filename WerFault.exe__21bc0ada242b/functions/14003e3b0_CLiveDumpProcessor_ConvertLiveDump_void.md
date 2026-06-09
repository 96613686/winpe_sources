# CLiveDumpProcessor::ConvertLiveDump(void)

- ea: `0x14003e3b0`
- end: `0x14003e799`
- name: `?ConvertLiveDump@CLiveDumpProcessor@@AEAAJXZ`
- size: `1001`
- prototype: `__int64 __fastcall(CLiveDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x14003ebec`

## callees

- `0x140002728`
- `0x14000c8a0`
- `0x140034d9c`
- `0x14003bc28`
- `0x14003e3b0`
- `0x14003e7a0`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003e784`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003e784`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003e4dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003e4dc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003e48f`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003e48f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e4e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e4e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003e3eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003e3fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003e723`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003e3eb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003e3fd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003e723`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x14003e3f4`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x14003e3f4`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003e409`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003e72f`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003e409`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003e72f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003e70f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003e70f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003e40f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003e625`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003e40f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003e625`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003e71d`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003e71d`

## string_xrefs

- `0x14003e519`: `UtilDebugCreateEx failed for IDebugClient4`
- `0x14003e581`: `OpenDumpFileWide failed for %ws`
- `0x14003e690`: `Copy failed`
- `0x14003e614`: `WriteDumpFileWide failed`
- `0x14003e4d2`: `DebugCreateEx`
- `0x14003e488`: `dbgeng.dll`
- `0x14003e44f`: `CreateLiveMiniDumpFile failed`

## pseudocode

```c
__int64 __fastcall CLiveDumpProcessor::ConvertLiveDump(CLiveDumpProcessor *this)
{
  HMODULE Library; // rdi
  HANDLE CurrentThread; // rax
  int ThreadPriority; // r15d
  HANDLE v5; // rax
  DWORD TickCount; // r14d
  signed int v7; // ebx
  const char *v8; // rax
  __int64 v9; // rdx
  __int64 v10; // rcx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  DWORD v13; // eax
  int v14; // edx
  __int64 v15; // rcx
  __int64 v16; // rcx
  HANDLE v17; // rax
  wil::details *v19; // [rsp+20h] [rbp-48h]
  char *v20; // [rsp+30h] [rbp-38h]
  LPCWSTR lpFileName[2]; // [rsp+40h] [rbp-28h] BYREF
  _WORD v22[12]; // [rsp+50h] [rbp-18h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+98h] [rbp+30h]
  __int64 v24; // [rsp+A0h] [rbp+38h] BYREF
  __int64 v25; // [rsp+A8h] [rbp+40h] BYREF
  HANDLE hObject; // [rsp+B0h] [rbp+48h] BYREF
  HMODULE v27; // [rsp+B8h] [rbp+50h]

  Library = 0;
  v27 = 0;
  v24 = 0;
  v25 = 0;
  hObject = 0;
  lpFileName[0] = v22;
  lpFileName[1] = v22;
  v22[0] = 0;
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  v5 = GetCurrentThread();
  SetThreadPriority(v5, -1);
  TickCount = GetTickCount();
  if ( *((_QWORD *)this + 1049) == *((_QWORD *)this + 1050) || *((_DWORD *)this + 1032) != 6 )
  {
    v7 = -2147467259;
  }
  else
  {
    v7 = CLiveDumpProcessor::CreateLiveMiniDumpFile(this, lpFileName, &hObject);
    if ( v7 < 0 )
    {
      v8 = "CreateLiveMiniDumpFile failed";
      v9 = 351;
LABEL_5:
      LODWORD(v19) = v7;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)v9,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
        "CLiveDumpProcessor::ConvertLiveDump",
        v19,
        (int)v8,
        v20);
      goto LABEL_30;
    }
    Library = LoadLibraryExW(L"dbgeng.dll", 0, 0x800u);
    v27 = Library;
    if ( !Library )
    {
      v7 = -2147024770;
      v8 = "UtilLoadDbgEng failed";
      v9 = 362;
      goto LABEL_5;
    }
    v10 = v24;
    v24 = 0;
    if ( v10 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
    ProcAddress = GetProcAddress(Library, "DebugCreateEx");
    if ( ProcAddress )
    {
      v7 = ((__int64 (__fastcall *)(GUID *, __int64, __int64 *))ProcAddress)(
             &GUID_ca83c3de_5089_4cf8_93c8_d892387f2a5e,
             688136,
             &v24);
    }
    else
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
    }
    if ( v7 < 0 )
    {
      v8 = "UtilDebugCreateEx failed for IDebugClient4";
      v9 = 380;
      goto LABEL_5;
    }
    v7 = tlx::queryinterface_unique<IDebugControl,IDebugClient4>(&v25, v24);
    if ( v7 < 0 )
    {
      v8 = "QueryInterface failed for IDebugControl";
      v9 = 391;
      goto LABEL_5;
    }
    v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v24 + 480LL))(v24, *((_QWORD *)this + 1049), 0);
    if ( v7 >= 0 )
    {
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v25 + 744LL))(v25, 0, 0xFFFFFFFFLL);
      if ( v7 < 0 )
      {
        v8 = "WaitForEvent failed";
        v9 = 411;
        goto LABEL_5;
      }
      v7 = (*(__int64 (__fastcall **)(__int64, _QWORD, HANDLE, __int64, _DWORD, _QWORD))(*(_QWORD *)v24 + 488LL))(
             v24,
             0,
             hObject,
             1024,
             0,
             0);
      if ( v7 < 0 )
      {
        v8 = "WriteDumpFileWide failed";
        v9 = 423;
        goto LABEL_5;
      }
      v13 = GetTickCount();
      v14 = v13 - TickCount - 1;
      if ( v13 >= TickCount )
        v14 = v13 - TickCount;
      LODWORD(v20) = v14;
      LODWORD(v19) = 0x80000000;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x1AB,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
        "CLiveDumpProcessor::ConvertLiveDump",
        v19,
        (int)"*** Time for dump conversion (ms): %u",
        v20);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               (char *)this + 8360,
                               lpFileName[0]) )
      {
        v7 = -2147024882;
        v8 = "Copy failed";
        v9 = 432;
        goto LABEL_5;
      }
      v7 = 0;
    }
    else
    {
      LODWORD(v19) = v7;
      wil::details::in1diag4::Log_HrMsg(
        retaddr,
        (void *)0x192,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\livedumpprocessor.cpp",
        "CLiveDumpProcessor::ConvertLiveDump",
        v19,
        (int)"OpenDumpFileWide failed for %ws",
        *((const char **)this + 1049));
    }
  }
LABEL_30:
  v15 = v25;
  v25 = 0;
  if ( v15 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v24 )
  {
    (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v24 + 208LL))(v24, 0);
    v16 = v24;
    v24 = 0;
    if ( v16 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 16LL))(v16);
  }
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( v7 < 0 )
    DeleteFileW(lpFileName[0]);
  v17 = GetCurrentThread();
  SetThreadPriority(v17, ThreadPriority);
  if ( lpFileName[0] != v22 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v25 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( v24 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v24 + 16LL))(v24);
  if ( Library )
    FreeLibrary(Library);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x14003e3b0  push    rbp
0x14003e3b2  push    rbx
0x14003e3b3  push    rsi
0x14003e3b4  push    rdi
0x14003e3b5  push    r14
0x14003e3b7  push    r15
0x14003e3b9  mov     rbp, rsp
0x14003e3bc  sub     rsp, 68h
0x14003e3c0  mov     rsi, rcx
0x14003e3c3  xor     edi, edi
0x14003e3c5  mov     [rbp+arg_18], rdi
0x14003e3c9  mov     [rbp+arg_0], rdi
0x14003e3cd  mov     [rbp+arg_8], rdi
0x14003e3d1  mov     [rbp+hObject], rdi
0x14003e3d5  lea     rax, [rbp+var_18]
0x14003e3d9  mov     [rbp+lpFileName], rax
0x14003e3dd  lea     rax, [rbp+var_18]
0x14003e3e1  mov     [rbp+var_20], rax
0x14003e3e5  xor     eax, eax
0x14003e3e7  mov     [rbp+var_18], ax
0x14003e3eb  call    cs:__imp_GetCurrentThread
0x14003e3f1  mov     rcx, rax; hThread
0x14003e3f4  call    cs:__imp_GetThreadPriority
0x14003e3fa  mov     r15d, eax
0x14003e3fd  call    cs:__imp_GetCurrentThread
0x14003e403  mov     rcx, rax; hThread
0x14003e406  or      edx, 0FFFFFFFFh; nPriority
0x14003e409  call    cs:__imp_SetThreadPriority
0x14003e40f  call    cs:__imp_GetTickCount
0x14003e415  mov     r14d, eax
0x14003e418  mov     rcx, [rsi+20D0h]
0x14003e41f  cmp     [rsi+20C8h], rcx
0x14003e426  jz      loc_14003E6A5
0x14003e42c  cmp     dword ptr [rsi+1020h], 6
0x14003e433  jnz     loc_14003E6A5
0x14003e439  lea     r8, [rbp+hObject]
0x14003e43d  lea     rdx, [rbp+lpFileName]
0x14003e441  mov     rcx, rsi
0x14003e444  call    ?CreateLiveMiniDumpFile@CLiveDumpProcessor@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CLiveDumpProcessor::CreateLiveMiniDumpFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,tlx::unique_any<tlx::file_handle_traits> *)
0x14003e449  mov     ebx, eax
0x14003e44b  test    eax, eax
0x14003e44d  jns     short loc_14003E480
0x14003e44f  lea     rax, aCreatelivemini; "CreateLiveMiniDumpFile failed"
0x14003e456  mov     edx, 15Fh; void *
0x14003e45b  mov     qword ptr [rsp+68h+var_40], rax; int
0x14003e460  mov     rcx, [rbp+30h]; this
0x14003e464  mov     dword ptr [rsp+68h+var_48], ebx; wil::details *
0x14003e468  lea     r9, aClivedumpproce_4; "CLiveDumpProcessor::ConvertLiveDump"
0x14003e46f  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003e476  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003e47b  jmp     loc_14003E6AA
0x14003e480  xor     edx, edx; hFile
0x14003e482  mov     r8d, 800h; dwFlags
0x14003e488  lea     rcx, aDbgengDll; "dbgeng.dll"
0x14003e48f  call    cs:__imp_LoadLibraryExW
0x14003e495  mov     rdi, rax
0x14003e498  mov     [rbp+arg_18], rax
0x14003e49c  test    rax, rax
0x14003e49f  jnz     short loc_14003E4B4
0x14003e4a1  mov     ebx, 8007007Eh
0x14003e4a6  lea     rax, aUtilloaddbgeng; "UtilLoadDbgEng failed"
0x14003e4ad  mov     edx, 16Ah
0x14003e4b2  jmp     short loc_14003E45B
0x14003e4b4  mov     rcx, [rbp+arg_0]
0x14003e4b8  mov     [rbp+arg_0], 0
0x14003e4c0  test    rcx, rcx
0x14003e4c3  jz      short loc_14003E4D2
0x14003e4c5  mov     rax, [rcx]
0x14003e4c8  mov     rax, [rax+10h]
0x14003e4cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e4d1  nop
0x14003e4d2  lea     rdx, aDebugcreateex; "DebugCreateEx"
0x14003e4d9  mov     rcx, rdi; hModule
0x14003e4dc  call    cs:__imp_GetProcAddress
0x14003e4e2  test    rax, rax
0x14003e4e5  jnz     short loc_14003E4FE
0x14003e4e7  call    cs:__imp_GetLastError
0x14003e4ed  mov     ebx, eax
0x14003e4ef  test    eax, eax
0x14003e4f1  jle     short loc_14003E515
0x14003e4f3  movzx   ebx, ax
0x14003e4f6  or      ebx, 80070000h
0x14003e4fc  jmp     short loc_14003E515
0x14003e4fe  lea     r8, [rbp+arg_0]
0x14003e502  mov     edx, 0A8008h
0x14003e507  lea     rcx, _GUID_ca83c3de_5089_4cf8_93c8_d892387f2a5e
0x14003e50e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e513  mov     ebx, eax
0x14003e515  test    ebx, ebx
0x14003e517  jns     short loc_14003E52A
0x14003e519  lea     rax, aUtildebugcreat; "UtilDebugCreateEx failed for IDebugClie"...
0x14003e520  mov     edx, 17Ch
0x14003e525  jmp     loc_14003E45B
0x14003e52a  mov     rdx, [rbp+arg_0]
0x14003e52e  lea     rcx, [rbp+arg_8]
0x14003e532  call    ??$queryinterface_unique@UIDebugControl@@UIDebugClient4@@@tlx@@YAJPEAV?$unique_ptr@UIDebugControl@@Urelease_delete@tlx@@@utl@@AEAUIDebugClient4@@AEBU_GUID@@@Z; tlx::queryinterface_unique<IDebugControl,IDebugClient4>(utl::unique_ptr<IDebugControl,tlx::release_delete> *,IDebugClient4 &,_GUID const &)
0x14003e537  mov     ebx, eax
0x14003e539  test    eax, eax
0x14003e53b  jns     short loc_14003E54E
0x14003e53d  lea     rax, aQueryinterface_1; "QueryInterface failed for IDebugControl"
0x14003e544  mov     edx, 187h
0x14003e549  jmp     loc_14003E45B
0x14003e54e  mov     rcx, [rbp+arg_0]
0x14003e552  mov     rax, [rcx]
0x14003e555  xor     r8d, r8d
0x14003e558  mov     rdx, [rsi+20C8h]
0x14003e55f  mov     rax, [rax+1E0h]
0x14003e566  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e56b  mov     ebx, eax
0x14003e56d  test    eax, eax
0x14003e56f  jns     short loc_14003E5AE
0x14003e571  mov     rcx, [rbp+30h]; this
0x14003e575  mov     rax, [rsi+20C8h]
0x14003e57c  mov     [rsp+68h+var_38], rax; char *
0x14003e581  lea     rax, aOpendumpfilewi; "OpenDumpFileWide failed for %ws"
0x14003e588  mov     qword ptr [rsp+68h+var_40], rax; int
0x14003e58d  mov     dword ptr [rsp+68h+var_48], ebx; wil::details *
0x14003e591  lea     r9, aClivedumpproce_4; "CLiveDumpProcessor::ConvertLiveDump"
0x14003e598  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003e59f  mov     edx, 192h; void *
0x14003e5a4  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003e5a9  jmp     loc_14003E6AA
0x14003e5ae  mov     rcx, [rbp+arg_8]
0x14003e5b2  mov     rax, [rcx]
0x14003e5b5  or      r8d, 0FFFFFFFFh
0x14003e5b9  xor     edx, edx
0x14003e5bb  mov     rax, [rax+2E8h]
0x14003e5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e5c7  mov     ebx, eax
0x14003e5c9  test    eax, eax
0x14003e5cb  jns     short loc_14003E5DE
0x14003e5cd  lea     rax, aWaitforeventFa; "WaitForEvent failed"
0x14003e5d4  mov     edx, 19Bh
0x14003e5d9  jmp     loc_14003E45B
0x14003e5de  mov     rcx, [rbp+arg_0]
0x14003e5e2  mov     rax, [rcx]
0x14003e5e5  mov     qword ptr [rsp+68h+var_40], 0
0x14003e5ee  mov     dword ptr [rsp+68h+var_48], 0
0x14003e5f6  mov     r9d, 400h
0x14003e5fc  mov     r8, [rbp+hObject]
0x14003e600  xor     edx, edx
0x14003e602  mov     rax, [rax+1E8h]
0x14003e609  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e60e  mov     ebx, eax
0x14003e610  test    eax, eax
0x14003e612  jns     short loc_14003E625
0x14003e614  lea     rax, aWritedumpfilew; "WriteDumpFileWide failed"
0x14003e61b  mov     edx, 1A7h
0x14003e620  jmp     loc_14003E45B
0x14003e625  call    cs:__imp_GetTickCount
0x14003e62b  mov     ecx, eax
0x14003e62d  sub     ecx, r14d
0x14003e630  lea     edx, [rcx-1]
0x14003e633  cmp     eax, r14d
0x14003e636  cmovnb  edx, ecx
0x14003e639  mov     rcx, [rbp+30h]; this
0x14003e63d  mov     dword ptr [rsp+68h+var_38], edx; char *
0x14003e641  lea     rax, aTimeForDumpCon; "*** Time for dump conversion (ms): %u"
0x14003e648  mov     qword ptr [rsp+68h+var_40], rax; int
0x14003e64d  mov     dword ptr [rsp+68h+var_48], 80000000h; wil::details *
0x14003e655  lea     r9, aClivedumpproce_4; "CLiveDumpProcessor::ConvertLiveDump"
0x14003e65c  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x14003e663  mov     edx, 1ABh; void *
0x14003e668  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003e66d  mov     r8, [rbp+var_20]
0x14003e671  mov     rdx, [rbp+lpFileName]
0x14003e675  sub     r8, rdx
0x14003e678  sar     r8, 1
0x14003e67b  lea     rcx, [rsi+20A8h]
0x14003e682  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003e687  test    al, al
0x14003e689  jnz     short loc_14003E6A1
0x14003e68b  mov     ebx, 8007000Eh
0x14003e690  lea     rax, aCopyFailed; "Copy failed"
0x14003e697  mov     edx, 1B0h
0x14003e69c  jmp     loc_14003E45B
0x14003e6a1  xor     ebx, ebx
0x14003e6a3  jmp     short loc_14003E6AA
0x14003e6a5  mov     ebx, 80004005h
0x14003e6aa  mov     rcx, [rbp+arg_8]
0x14003e6ae  mov     [rbp+arg_8], 0
0x14003e6b6  test    rcx, rcx
0x14003e6b9  jz      short loc_14003E6C8
0x14003e6bb  mov     rax, [rcx]
0x14003e6be  mov     rax, [rax+10h]
0x14003e6c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e6c7  nop
0x14003e6c8  mov     rcx, [rbp+arg_0]
0x14003e6cc  test    rcx, rcx
0x14003e6cf  jz      short loc_14003E701
0x14003e6d1  mov     rax, [rcx]
0x14003e6d4  xor     edx, edx
0x14003e6d6  mov     rax, [rax+0D0h]
0x14003e6dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e6e2  nop
0x14003e6e3  mov     rcx, [rbp+arg_0]
0x14003e6e7  mov     [rbp+arg_0], 0
0x14003e6ef  test    rcx, rcx
0x14003e6f2  jz      short loc_14003E701
0x14003e6f4  mov     rax, [rcx]
0x14003e6f7  mov     rax, [rax+10h]
0x14003e6fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e700  nop
0x14003e701  mov     rcx, [rbp+hObject]; hObject
0x14003e705  lea     rax, [rcx+1]
0x14003e709  cmp     rax, 1
0x14003e70d  jbe     short loc_14003E715
0x14003e70f  call    cs:__imp_CloseHandle
0x14003e715  test    ebx, ebx
0x14003e717  jns     short loc_14003E723
0x14003e719  mov     rcx, [rbp+lpFileName]; lpFileName
0x14003e71d  call    cs:__imp_DeleteFileW
0x14003e723  call    cs:__imp_GetCurrentThread
0x14003e729  mov     rcx, rax; hThread
0x14003e72c  mov     edx, r15d; nPriority
0x14003e72f  call    cs:__imp_SetThreadPriority
0x14003e735  nop
0x14003e736  lea     rax, [rbp+var_18]
0x14003e73a  mov     rcx, [rbp+lpFileName]; void *
0x14003e73e  cmp     rcx, rax
0x14003e741  jz      short loc_14003E750
0x14003e743  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x14003e74a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x14003e74f  nop
0x14003e750  mov     rcx, [rbp+arg_8]
0x14003e754  test    rcx, rcx
0x14003e757  jz      short loc_14003E766
0x14003e759  mov     rax, [rcx]
0x14003e75c  mov     rax, [rax+10h]
0x14003e760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e765  nop
0x14003e766  mov     rcx, [rbp+arg_0]
0x14003e76a  test    rcx, rcx
0x14003e76d  jz      short loc_14003E77C
0x14003e76f  mov     rax, [rcx]
0x14003e772  mov     rax, [rax+10h]
0x14003e776  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e77b  nop
0x14003e77c  test    rdi, rdi
0x14003e77f  jz      short loc_14003E78A
0x14003e781  mov     rcx, rdi; hLibModule
0x14003e784  call    cs:__imp_FreeLibrary
0x14003e78a  mov     eax, ebx
0x14003e78c  add     rsp, 68h
0x14003e790  pop     r15
0x14003e792  pop     r14
0x14003e794  pop     rdi
0x14003e795  pop     rsi
0x14003e796  pop     rbx
0x14003e797  pop     rbp
0x14003e798  retn
```
