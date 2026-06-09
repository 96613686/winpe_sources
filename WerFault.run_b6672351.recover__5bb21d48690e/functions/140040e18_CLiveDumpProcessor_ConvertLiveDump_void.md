# CLiveDumpProcessor::ConvertLiveDump(void)

- ea: `0x140040e18`
- end: `0x140041256`
- name: `?ConvertLiveDump@CLiveDumpProcessor@@AEAAJXZ`
- size: `1086`
- prototype: `__int64 __fastcall(CLiveDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting`

## callers

- `0x1400416f4`

## callees

- `0x140002748`
- `0x14000ca20`
- `0x1400372dc`
- `0x14003e500`
- `0x140040e18`
- `0x14004125c`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004123a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14004123a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140040f68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140040f68`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140040f15`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x140040f15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040f79`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140040f79`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140040e53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140040e71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400411cd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140040e53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x140040e71`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x1400411cd`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x140040e62`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x140040e62`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140040e83`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1400411df`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x140040e83`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x1400411df`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400411ad`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400411ad`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140040e8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400410bd`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x140040e8f`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x1400410bd`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400411c1`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x1400411c1`

## string_xrefs

- `0x140040fb1`: `UtilDebugCreateEx failed for IDebugClient4`
- `0x140041019`: `OpenDumpFileWide failed for %ws`
- `0x14004112e`: `Copy failed`
- `0x1400410ac`: `WriteDumpFileWide failed`
- `0x140040f5e`: `DebugCreateEx`
- `0x140040f0e`: `dbgeng.dll`
- `0x140040ed5`: `CreateLiveMiniDumpFile failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x140040e18  push    rbp
0x140040e1a  push    rbx
0x140040e1b  push    rsi
0x140040e1c  push    rdi
0x140040e1d  push    r14
0x140040e1f  push    r15
0x140040e21  mov     rbp, rsp
0x140040e24  sub     rsp, 68h
0x140040e28  mov     rsi, rcx
0x140040e2b  xor     edi, edi
0x140040e2d  mov     [rbp+arg_18], rdi
0x140040e31  mov     [rbp+arg_0], rdi
0x140040e35  mov     [rbp+arg_8], rdi
0x140040e39  mov     [rbp+hObject], rdi
0x140040e3d  lea     rax, [rbp+var_18]
0x140040e41  mov     [rbp+lpFileName], rax
0x140040e45  lea     rax, [rbp+var_18]
0x140040e49  mov     [rbp+var_20], rax
0x140040e4d  xor     eax, eax
0x140040e4f  mov     [rbp+var_18], ax
0x140040e53  call    cs:__imp_GetCurrentThread
0x140040e5a  nop     dword ptr [rax+rax+00h]
0x140040e5f  mov     rcx, rax; hThread
0x140040e62  call    cs:__imp_GetThreadPriority
0x140040e69  nop     dword ptr [rax+rax+00h]
0x140040e6e  mov     r15d, eax
0x140040e71  call    cs:__imp_GetCurrentThread
0x140040e78  nop     dword ptr [rax+rax+00h]
0x140040e7d  mov     rcx, rax; hThread
0x140040e80  or      edx, 0FFFFFFFFh; nPriority
0x140040e83  call    cs:__imp_SetThreadPriority
0x140040e8a  nop     dword ptr [rax+rax+00h]
0x140040e8f  call    cs:__imp_GetTickCount
0x140040e96  nop     dword ptr [rax+rax+00h]
0x140040e9b  mov     r14d, eax
0x140040e9e  mov     rcx, [rsi+20D0h]
0x140040ea5  cmp     [rsi+20C8h], rcx
0x140040eac  jz      loc_140041143
0x140040eb2  cmp     dword ptr [rsi+1020h], 6
0x140040eb9  jnz     loc_140041143
0x140040ebf  lea     r8, [rbp+hObject]
0x140040ec3  lea     rdx, [rbp+lpFileName]
0x140040ec7  mov     rcx, rsi
0x140040eca  call    ?CreateLiveMiniDumpFile@CLiveDumpProcessor@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CLiveDumpProcessor::CreateLiveMiniDumpFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,tlx::unique_any<tlx::file_handle_traits> *)
0x140040ecf  mov     ebx, eax
0x140040ed1  test    eax, eax
0x140040ed3  jns     short loc_140040F06
0x140040ed5  lea     rax, aCreatelivemini; "CreateLiveMiniDumpFile failed"
0x140040edc  mov     edx, 15Fh; void *
0x140040ee1  mov     qword ptr [rsp+68h+var_40], rax; int
0x140040ee6  mov     rcx, [rbp+30h]; this
0x140040eea  mov     dword ptr [rsp+68h+var_48], ebx; wil::details *
0x140040eee  lea     r9, aClivedumpproce_4; "CLiveDumpProcessor::ConvertLiveDump"
0x140040ef5  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140040efc  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140040f01  jmp     loc_140041148
0x140040f06  xor     edx, edx; hFile
0x140040f08  mov     r8d, 800h; dwFlags
0x140040f0e  lea     rcx, aDbgengDll; "dbgeng.dll"
0x140040f15  call    cs:__imp_LoadLibraryExW
0x140040f1c  nop     dword ptr [rax+rax+00h]
0x140040f21  mov     rdi, rax
0x140040f24  mov     [rbp+arg_18], rax
0x140040f28  test    rax, rax
0x140040f2b  jnz     short loc_140040F40
0x140040f2d  mov     ebx, 8007007Eh
0x140040f32  lea     rax, aUtilloaddbgeng; "UtilLoadDbgEng failed"
0x140040f39  mov     edx, 16Ah
0x140040f3e  jmp     short loc_140040EE1
0x140040f40  mov     rcx, [rbp+arg_0]
0x140040f44  mov     [rbp+arg_0], 0
0x140040f4c  test    rcx, rcx
0x140040f4f  jz      short loc_140040F5E
0x140040f51  mov     rax, [rcx]
0x140040f54  mov     rax, [rax+10h]
0x140040f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040f5d  nop
0x140040f5e  lea     rdx, aDebugcreateex; "DebugCreateEx"
0x140040f65  mov     rcx, rdi; hModule
0x140040f68  call    cs:__imp_GetProcAddress
0x140040f6f  nop     dword ptr [rax+rax+00h]
0x140040f74  test    rax, rax
0x140040f77  jnz     short loc_140040F96
0x140040f79  call    cs:__imp_GetLastError
0x140040f80  nop     dword ptr [rax+rax+00h]
0x140040f85  mov     ebx, eax
0x140040f87  test    eax, eax
0x140040f89  jle     short loc_140040FAD
0x140040f8b  movzx   ebx, ax
0x140040f8e  or      ebx, 80070000h
0x140040f94  jmp     short loc_140040FAD
0x140040f96  lea     r8, [rbp+arg_0]
0x140040f9a  mov     edx, 0A8008h
0x140040f9f  lea     rcx, _GUID_ca83c3de_5089_4cf8_93c8_d892387f2a5e
0x140040fa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140040fab  mov     ebx, eax
0x140040fad  test    ebx, ebx
0x140040faf  jns     short loc_140040FC2
0x140040fb1  lea     rax, aUtildebugcreat; "UtilDebugCreateEx failed for IDebugClie"...
0x140040fb8  mov     edx, 17Ch
0x140040fbd  jmp     loc_140040EE1
0x140040fc2  mov     rdx, [rbp+arg_0]
0x140040fc6  lea     rcx, [rbp+arg_8]
0x140040fca  call    ??$queryinterface_unique@UIDebugControl@@UIDebugClient4@@@tlx@@YAJPEAV?$unique_ptr@UIDebugControl@@Urelease_delete@tlx@@@utl@@AEAUIDebugClient4@@AEBU_GUID@@@Z; tlx::queryinterface_unique<IDebugControl,IDebugClient4>(utl::unique_ptr<IDebugControl,tlx::release_delete> *,IDebugClient4 &,_GUID const &)
0x140040fcf  mov     ebx, eax
0x140040fd1  test    eax, eax
0x140040fd3  jns     short loc_140040FE6
0x140040fd5  lea     rax, aQueryinterface_1; "QueryInterface failed for IDebugControl"
0x140040fdc  mov     edx, 187h
0x140040fe1  jmp     loc_140040EE1
0x140040fe6  mov     rcx, [rbp+arg_0]
0x140040fea  mov     rax, [rcx]
0x140040fed  xor     r8d, r8d
0x140040ff0  mov     rdx, [rsi+20C8h]
0x140040ff7  mov     rax, [rax+1E0h]
0x140040ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041003  mov     ebx, eax
0x140041005  test    eax, eax
0x140041007  jns     short loc_140041046
0x140041009  mov     rcx, [rbp+30h]; this
0x14004100d  mov     rax, [rsi+20C8h]
0x140041014  mov     [rsp+68h+var_38], rax; char *
0x140041019  lea     rax, aOpendumpfilewi; "OpenDumpFileWide failed for %ws"
0x140041020  mov     qword ptr [rsp+68h+var_40], rax; int
0x140041025  mov     dword ptr [rsp+68h+var_48], ebx; wil::details *
0x140041029  lea     r9, aClivedumpproce_4; "CLiveDumpProcessor::ConvertLiveDump"
0x140041030  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140041037  mov     edx, 192h; void *
0x14004103c  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140041041  jmp     loc_140041148
0x140041046  mov     rcx, [rbp+arg_8]
0x14004104a  mov     rax, [rcx]
0x14004104d  or      r8d, 0FFFFFFFFh
0x140041051  xor     edx, edx
0x140041053  mov     rax, [rax+2E8h]
0x14004105a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004105f  mov     ebx, eax
0x140041061  test    eax, eax
0x140041063  jns     short loc_140041076
0x140041065  lea     rax, aWaitforeventFa; "WaitForEvent failed"
0x14004106c  mov     edx, 19Bh
0x140041071  jmp     loc_140040EE1
0x140041076  mov     rcx, [rbp+arg_0]
0x14004107a  mov     rax, [rcx]
0x14004107d  mov     qword ptr [rsp+68h+var_40], 0
0x140041086  mov     dword ptr [rsp+68h+var_48], 0
0x14004108e  mov     r9d, 400h
0x140041094  mov     r8, [rbp+hObject]
0x140041098  xor     edx, edx
0x14004109a  mov     rax, [rax+1E8h]
0x1400410a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400410a6  mov     ebx, eax
0x1400410a8  test    eax, eax
0x1400410aa  jns     short loc_1400410BD
0x1400410ac  lea     rax, aWritedumpfilew; "WriteDumpFileWide failed"
0x1400410b3  mov     edx, 1A7h
0x1400410b8  jmp     loc_140040EE1
0x1400410bd  call    cs:__imp_GetTickCount
0x1400410c4  nop     dword ptr [rax+rax+00h]
0x1400410c9  mov     ecx, eax
0x1400410cb  sub     ecx, r14d
0x1400410ce  lea     edx, [rcx-1]
0x1400410d1  cmp     eax, r14d
0x1400410d4  cmovnb  edx, ecx
0x1400410d7  mov     rcx, [rbp+30h]; this
0x1400410db  mov     dword ptr [rsp+68h+var_38], edx; char *
0x1400410df  lea     rax, aTimeForDumpCon; "*** Time for dump conversion (ms): %u"
0x1400410e6  mov     qword ptr [rsp+68h+var_40], rax; int
0x1400410eb  mov     dword ptr [rsp+68h+var_48], 80000000h; wil::details *
0x1400410f3  lea     r9, aClivedumpproce_4; "CLiveDumpProcessor::ConvertLiveDump"
0x1400410fa  lea     r8, aOnecoreWindows_5; "onecore\\windows\\feedback\\core\\werfa"...
0x140041101  mov     edx, 1ABh; void *
0x140041106  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14004110b  mov     r8, [rbp+var_20]
0x14004110f  mov     rdx, [rbp+lpFileName]
0x140041113  sub     r8, rdx
0x140041116  sar     r8, 1
0x140041119  lea     rcx, [rsi+20A8h]
0x140041120  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x140041125  test    al, al
0x140041127  jnz     short loc_14004113F
0x140041129  mov     ebx, 8007000Eh
0x14004112e  lea     rax, aCopyFailed; "Copy failed"
0x140041135  mov     edx, 1B0h
0x14004113a  jmp     loc_140040EE1
0x14004113f  xor     ebx, ebx
0x140041141  jmp     short loc_140041148
0x140041143  mov     ebx, 80004005h
0x140041148  mov     rcx, [rbp+arg_8]
0x14004114c  mov     [rbp+arg_8], 0
0x140041154  test    rcx, rcx
0x140041157  jz      short loc_140041166
0x140041159  mov     rax, [rcx]
0x14004115c  mov     rax, [rax+10h]
0x140041160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041165  nop
0x140041166  mov     rcx, [rbp+arg_0]
0x14004116a  test    rcx, rcx
0x14004116d  jz      short loc_14004119F
0x14004116f  mov     rax, [rcx]
0x140041172  xor     edx, edx
0x140041174  mov     rax, [rax+0D0h]
0x14004117b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041180  nop
0x140041181  mov     rcx, [rbp+arg_0]
0x140041185  mov     [rbp+arg_0], 0
0x14004118d  test    rcx, rcx
0x140041190  jz      short loc_14004119F
0x140041192  mov     rax, [rcx]
0x140041195  mov     rax, [rax+10h]
0x140041199  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004119e  nop
0x14004119f  mov     rcx, [rbp+hObject]; hObject
0x1400411a3  lea     rax, [rcx+1]
0x1400411a7  cmp     rax, 1
0x1400411ab  jbe     short loc_1400411B9
0x1400411ad  call    cs:__imp_CloseHandle
0x1400411b4  nop     dword ptr [rax+rax+00h]
0x1400411b9  test    ebx, ebx
0x1400411bb  jns     short loc_1400411CD
0x1400411bd  mov     rcx, [rbp+lpFileName]; lpFileName
0x1400411c1  call    cs:__imp_DeleteFileW
0x1400411c8  nop     dword ptr [rax+rax+00h]
0x1400411cd  call    cs:__imp_GetCurrentThread
0x1400411d4  nop     dword ptr [rax+rax+00h]
0x1400411d9  mov     rcx, rax; hThread
0x1400411dc  mov     edx, r15d; nPriority
0x1400411df  call    cs:__imp_SetThreadPriority
0x1400411e6  nop     dword ptr [rax+rax+00h]
0x1400411eb  nop
0x1400411ec  lea     rax, [rbp+var_18]
0x1400411f0  mov     rcx, [rbp+lpFileName]; void *
0x1400411f4  cmp     rcx, rax
0x1400411f7  jz      short loc_140041206
0x1400411f9  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140041200  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x140041205  nop
0x140041206  mov     rcx, [rbp+arg_8]
0x14004120a  test    rcx, rcx
0x14004120d  jz      short loc_14004121C
0x14004120f  mov     rax, [rcx]
0x140041212  mov     rax, [rax+10h]
0x140041216  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004121b  nop
0x14004121c  mov     rcx, [rbp+arg_0]
0x140041220  test    rcx, rcx
0x140041223  jz      short loc_140041232
0x140041225  mov     rax, [rcx]
0x140041228  mov     rax, [rax+10h]
0x14004122c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041231  nop
0x140041232  test    rdi, rdi
0x140041235  jz      short loc_140041246
0x140041237  mov     rcx, rdi; hLibModule
0x14004123a  call    cs:__imp_FreeLibrary
0x140041241  nop     dword ptr [rax+rax+00h]
0x140041246  mov     eax, ebx
0x140041248  add     rsp, 68h
0x14004124c  pop     r15
0x14004124e  pop     r14
0x140041250  pop     rdi
0x140041251  pop     rsi
0x140041252  pop     rbx
0x140041253  pop     rbp
0x140041254  retn
```
