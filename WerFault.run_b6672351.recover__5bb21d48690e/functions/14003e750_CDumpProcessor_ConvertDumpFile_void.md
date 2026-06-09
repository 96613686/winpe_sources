# CDumpProcessor::ConvertDumpFile(void)

- ea: `0x14003e750`
- end: `0x14003ecd5`
- name: `?ConvertDumpFile@CDumpProcessor@@AEAAJXZ`
- size: `1413`
- prototype: `__int64 __fastcall(CDumpProcessor *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x1400401fc`

## callees

- `0x140002748`
- `0x14000ca20`
- `0x1400372dc`
- `0x14003e500`
- `0x14003e750`
- `0x14003ecdc`
- `0x14003f93c`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003ecb2`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14003ecb2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003e8da`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14003e8da`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003e88b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14003e88b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e8eb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14003e8eb`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003e870`
- `api-ms-win-core-processenvironment-l1-1-0!SetEnvironmentVariableW` at `0x14003e870`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003e7a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003ec14`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003e7a2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x14003ec14`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003e7b6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003ec28`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003e7b6`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x14003ec28`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ebee`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14003ebee`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003e7e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003ea24`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003e7e5`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x14003ea24`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003ec02`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x14003ec02`

## string_xrefs

- `0x14003e923`: `UtilDebugCreateEx failed for IDebugClient4`
- `0x14003e98b`: `OpenDumpFileWide failed for %ws`
- `0x14003ea91`: `Copy failed`
- `0x14003e835`: `CreateMiniDumpFile failed`
- `0x14003ea13`: `WriteDumpFileWide failed`
- `0x14003e8d0`: `DebugCreateEx`
- `0x14003e884`: `dbgeng.dll`

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
  signed int v8; // ebx
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
  LPCWSTR lpFileName[2]; // [rsp+68h] [rbp-11h] BYREF
  _WORD v34[44]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag4 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 (__fastcall ***v36)(_QWORD, GUID *, __int64 *); // [rsp+E8h] [rbp+6Fh] BYREF
  __int64 v37; // [rsp+F0h] [rbp+77h] BYREF
  __int64 v38; // [rsp+F8h] [rbp+7Fh] BYREF

  Library = 0;
  v30 = 0;
  v36 = 0;
  v38 = 0;
  v37 = 0;
  hObject = 0;
  lpFileName[0] = v34;
  lpFileName[1] = v34;
  v34[0] = 0;
  v3 = 1;
  CurrentThread = GetCurrentThread();
  if ( !SetThreadPriority(CurrentThread, 0x10000) )
  {
    wil::details::in1diag4::_Log_GetLastError(
      retaddr,
      (void *)0x355,
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
      v8 = CDumpProcessor::CreateMiniDumpFile(this, lpFileName, &hObject);
      if ( v8 < 0 )
      {
        v9 = "CreateMiniDumpFile failed";
        v10 = 878;
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
        v10 = 896;
        goto LABEL_8;
      }
      v11 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v36;
      v36 = 0;
      if ( v11 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v11)[2])(v11);
      ProcAddress = GetProcAddress(Library, "DebugCreateEx");
      if ( ProcAddress )
      {
        v8 = ((__int64 (__fastcall *)(GUID *, __int64, _QWORD))ProcAddress)(
               &GUID_ca83c3de_5089_4cf8_93c8_d892387f2a5e,
               688136,
               &v36);
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
        v10 = 914;
        goto LABEL_8;
      }
      v8 = tlx::queryinterface_unique<IDebugControl,IDebugClient4>(&v38, v36);
      if ( v8 < 0 )
      {
        v9 = "QueryInterface failed for IDebugControl";
        v10 = 925;
        goto LABEL_8;
      }
      v8 = (*v36)[60](v36, *((GUID **)this + 1062), 0);
      if ( v8 < 0 )
      {
        LODWORD(v27) = v8;
        wil::details::in1diag4::Log_HrMsg(
          retaddr,
          (void *)0x3A8,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
          "CDumpProcessor::ConvertDumpFile",
          v27,
          (int)"OpenDumpFileWide failed for %ws",
          *((const char **)this + 1062));
        goto LABEL_41;
      }
      v8 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v38 + 744LL))(v38, 0, 0xFFFFFFFFLL);
      if ( v8 < 0 )
      {
        v9 = "WaitForEvent failed";
        v10 = 945;
        goto LABEL_8;
      }
      v8 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD, HANDLE, __int64, _DWORD, _QWORD))(*v36)[61])(
             v36,
             0,
             hObject,
             1024,
             0,
             0);
      if ( v8 < 0 )
      {
        v9 = "WriteDumpFileWide failed";
        v10 = 957;
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
        (void *)0x3C1,
        (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
        "CDumpProcessor::ConvertDumpFile",
        v27,
        (int)"*** Time for dump conversion (ms): %u",
        v28);
      if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                               (char *)this + 8464,
                               lpFileName[0]) )
      {
        v8 = -2147024882;
        v9 = "Copy failed";
        v10 = 966;
        goto LABEL_8;
      }
      v16 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v36;
      v17 = **v36;
      v31 = 0;
      v32 = &v37;
      v18 = v37;
      v37 = 0;
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
          (void *)0x3E0,
          (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\dumpprocessor.cpp",
          "CDumpProcessor::ConvertDumpFile",
          v27,
          (int)"QueryInterface failed for IDebugDataSpace3",
          v28);
      }
      else
      {
        LODWORD(v27) = 0;
        if ( (*(int (__fastcall **)(__int64, GUID *, _QWORD, _QWORD))(*(_QWORD *)v37 + 240LL))(v37, &GUID_IPT, 0, 0) >= 0 )
          *((_DWORD *)this + 2134) = 1;
      }
    }
  }
  v8 = 0;
LABEL_41:
  v21 = v37;
  v37 = 0;
  if ( v21 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
  v22 = v38;
  v38 = 0;
  if ( v22 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
  v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v36;
  if ( v36 )
  {
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), _QWORD))(*v36)[26])(v36, 0);
    v23 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD))v36;
  }
  v36 = 0;
  if ( v23 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD)))(*v23)[2])(v23);
  if ( (unsigned __int64)hObject + 1 > 1 )
    CloseHandle(hObject);
  if ( v8 < 0 )
    DeleteFileW(lpFileName[0]);
  if ( v3 )
  {
    v24 = GetCurrentThread();
    if ( !SetThreadPriority(v24, 0x20000) )
      wil::details::in1diag4::_Log_GetLastError(
        retaddr,
        (void *)0x350,
        v25,
        "CDumpProcessor::ConvertDumpFile::<lambda_b218bb32adc88dd6ecfe8aba5feb9cc1>::operator ()",
        (const char *)v27);
  }
  if ( lpFileName[0] != v34 )
    operator delete((void *)lpFileName[0], (const struct std::nothrow_t *)&std::nothrow);
  if ( v37 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v37 + 16LL))(v37);
  if ( v38 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v38 + 16LL))(v38);
  if ( v36 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v36)[2])(v36);
  if ( Library )
    FreeLibrary(Library);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x14003e750  push    rbp
0x14003e752  push    rbx
0x14003e753  push    rsi
0x14003e754  push    rdi
0x14003e755  push    r12
0x14003e757  push    r13
0x14003e759  push    r14
0x14003e75b  push    r15
0x14003e75d  lea     rbp, [rsp-1Fh]
0x14003e762  sub     rsp, 98h
0x14003e769  mov     rdi, rcx
0x14003e76c  xor     r12d, r12d
0x14003e76f  mov     esi, r12d
0x14003e772  mov     [rbp+57h+var_88], r12
0x14003e776  mov     [rbp+57h+arg_8], r12
0x14003e77a  mov     [rbp+57h+arg_18], r12
0x14003e77e  mov     [rbp+57h+arg_10], r12
0x14003e782  mov     [rbp+57h+hObject], r12
0x14003e786  lea     rax, [rbp+57h+var_58]
0x14003e78a  mov     [rbp+57h+lpFileName], rax
0x14003e78e  lea     rax, [rbp+57h+var_58]
0x14003e792  mov     [rbp+57h+var_60], rax
0x14003e796  mov     [rbp+57h+var_58], r12w
0x14003e79b  mov     r14b, 1
0x14003e79e  mov     [rbp+57h+arg_1], r14b
0x14003e7a2  call    cs:__imp_GetCurrentThread
0x14003e7a9  nop     dword ptr [rax+rax+00h]
0x14003e7ae  mov     rcx, rax; hThread
0x14003e7b1  mov     edx, 10000h; nPriority
0x14003e7b6  call    cs:__imp_SetThreadPriority
0x14003e7bd  nop     dword ptr [rax+rax+00h]
0x14003e7c2  lea     r13, aCdumpprocessor_6; "CDumpProcessor::ConvertDumpFile"
0x14003e7c9  test    eax, eax
0x14003e7cb  jnz     short loc_14003E7E5
0x14003e7cd  mov     rcx, [rbp+5Fh]; this
0x14003e7d1  mov     r9, r13; char *
0x14003e7d4  mov     edx, 355h; void *
0x14003e7d9  call    ?_Log_GetLastError@in1diag4@details@wil@@YAXPEAXIPEBD1@Z; wil::details::in1diag4::_Log_GetLastError(void *,uint,char const *,char const *)
0x14003e7de  mov     r14b, r12b
0x14003e7e1  mov     [rbp+57h+arg_1], r12b
0x14003e7e5  call    cs:__imp_GetTickCount
0x14003e7ec  nop     dword ptr [rax+rax+00h]
0x14003e7f1  mov     r15d, eax
0x14003e7f4  cmp     [rdi+2130h], r12
0x14003e7fb  jz      loc_14003EB75
0x14003e801  mov     edx, [rdi+1068h]
0x14003e807  lea     ecx, [rdx-1]
0x14003e80a  test    ecx, 0FFFFFFFAh
0x14003e810  jnz     loc_14003EB75
0x14003e816  cmp     edx, 2
0x14003e819  jz      loc_14003EB75
0x14003e81f  lea     r8, [rbp+57h+hObject]
0x14003e823  lea     rdx, [rbp+57h+lpFileName]
0x14003e827  mov     rcx, rdi
0x14003e82a  call    ?CreateMiniDumpFile@CDumpProcessor@@AEAAJPEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@PEAV?$unique_any@Ufile_handle_traits@tlx@@@tlx@@@Z; CDumpProcessor::CreateMiniDumpFile(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,tlx::unique_any<tlx::file_handle_traits> *)
0x14003e82f  mov     ebx, eax
0x14003e831  test    eax, eax
0x14003e833  jns     short loc_14003E862
0x14003e835  lea     rax, aCreateminidump; "CreateMiniDumpFile failed"
0x14003e83c  mov     edx, 36Eh; void *
0x14003e841  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x14003e846  mov     rcx, [rbp+5Fh]; this
0x14003e84a  mov     dword ptr [rsp+0D0h+var_B0], ebx; wil::details *
0x14003e84e  mov     r9, r13; char *
0x14003e851  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003e858  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003e85d  jmp     loc_14003EB78
0x14003e862  lea     rdx, a1; "1"
0x14003e869  lea     rcx, aDbgengNoBugche; "DBGENG_NO_BUGCHECK_ANALYSIS"
0x14003e870  call    cs:__imp_SetEnvironmentVariableW
0x14003e877  nop     dword ptr [rax+rax+00h]
0x14003e87c  xor     edx, edx; hFile
0x14003e87e  mov     r8d, 800h; dwFlags
0x14003e884  lea     rcx, aDbgengDll; "dbgeng.dll"
0x14003e88b  call    cs:__imp_LoadLibraryExW
0x14003e892  nop     dword ptr [rax+rax+00h]
0x14003e897  mov     rsi, rax
0x14003e89a  mov     [rbp+57h+var_88], rax
0x14003e89e  test    rax, rax
0x14003e8a1  jnz     short loc_14003E8B6
0x14003e8a3  mov     ebx, 8007007Eh
0x14003e8a8  lea     rax, aUtilloaddbgeng; "UtilLoadDbgEng failed"
0x14003e8af  mov     edx, 380h
0x14003e8b4  jmp     short loc_14003E841
0x14003e8b6  mov     rcx, [rbp+57h+arg_8]
0x14003e8ba  mov     [rbp+57h+arg_8], r12
0x14003e8be  test    rcx, rcx
0x14003e8c1  jz      short loc_14003E8D0
0x14003e8c3  mov     rax, [rcx]
0x14003e8c6  mov     rax, [rax+10h]
0x14003e8ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e8cf  nop
0x14003e8d0  lea     rdx, aDebugcreateex; "DebugCreateEx"
0x14003e8d7  mov     rcx, rsi; hModule
0x14003e8da  call    cs:__imp_GetProcAddress
0x14003e8e1  nop     dword ptr [rax+rax+00h]
0x14003e8e6  test    rax, rax
0x14003e8e9  jnz     short loc_14003E908
0x14003e8eb  call    cs:__imp_GetLastError
0x14003e8f2  nop     dword ptr [rax+rax+00h]
0x14003e8f7  mov     ebx, eax
0x14003e8f9  test    eax, eax
0x14003e8fb  jle     short loc_14003E91F
0x14003e8fd  movzx   ebx, ax
0x14003e900  or      ebx, 80070000h
0x14003e906  jmp     short loc_14003E91F
0x14003e908  lea     r8, [rbp+57h+arg_8]
0x14003e90c  mov     edx, 0A8008h
0x14003e911  lea     rcx, _GUID_ca83c3de_5089_4cf8_93c8_d892387f2a5e
0x14003e918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e91d  mov     ebx, eax
0x14003e91f  test    ebx, ebx
0x14003e921  jns     short loc_14003E934
0x14003e923  lea     rax, aUtildebugcreat; "UtilDebugCreateEx failed for IDebugClie"...
0x14003e92a  mov     edx, 392h
0x14003e92f  jmp     loc_14003E841
0x14003e934  mov     rdx, [rbp+57h+arg_8]
0x14003e938  lea     rcx, [rbp+57h+arg_18]
0x14003e93c  call    ??$queryinterface_unique@UIDebugControl@@UIDebugClient4@@@tlx@@YAJPEAV?$unique_ptr@UIDebugControl@@Urelease_delete@tlx@@@utl@@AEAUIDebugClient4@@AEBU_GUID@@@Z; tlx::queryinterface_unique<IDebugControl,IDebugClient4>(utl::unique_ptr<IDebugControl,tlx::release_delete> *,IDebugClient4 &,_GUID const &)
0x14003e941  mov     ebx, eax
0x14003e943  test    eax, eax
0x14003e945  jns     short loc_14003E958
0x14003e947  lea     rax, aQueryinterface_1; "QueryInterface failed for IDebugControl"
0x14003e94e  mov     edx, 39Dh
0x14003e953  jmp     loc_14003E841
0x14003e958  mov     rcx, [rbp+57h+arg_8]
0x14003e95c  mov     rax, [rcx]
0x14003e95f  xor     r8d, r8d
0x14003e962  mov     rdx, [rdi+2130h]
0x14003e969  mov     rax, [rax+1E0h]
0x14003e970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e975  mov     ebx, eax
0x14003e977  test    eax, eax
0x14003e979  jns     short loc_14003E9B4
0x14003e97b  mov     rcx, [rbp+5Fh]; this
0x14003e97f  mov     rax, [rdi+2130h]
0x14003e986  mov     [rsp+0D0h+var_A0], rax; char *
0x14003e98b  lea     rax, aOpendumpfilewi; "OpenDumpFileWide failed for %ws"
0x14003e992  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x14003e997  mov     dword ptr [rsp+0D0h+var_B0], ebx; wil::details *
0x14003e99b  mov     r9, r13; char *
0x14003e99e  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003e9a5  mov     edx, 3A8h; void *
0x14003e9aa  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003e9af  jmp     loc_14003EB78
0x14003e9b4  mov     rcx, [rbp+57h+arg_18]
0x14003e9b8  mov     rax, [rcx]
0x14003e9bb  or      r8d, 0FFFFFFFFh
0x14003e9bf  xor     edx, edx
0x14003e9c1  mov     rax, [rax+2E8h]
0x14003e9c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003e9cd  mov     ebx, eax
0x14003e9cf  test    eax, eax
0x14003e9d1  jns     short loc_14003E9E4
0x14003e9d3  lea     rax, aWaitforeventFa; "WaitForEvent failed"
0x14003e9da  mov     edx, 3B1h
0x14003e9df  jmp     loc_14003E841
0x14003e9e4  mov     rcx, [rbp+57h+arg_8]
0x14003e9e8  mov     rax, [rcx]
0x14003e9eb  mov     qword ptr [rsp+0D0h+var_A8], r12
0x14003e9f0  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x14003e9f5  mov     r9d, 400h
0x14003e9fb  mov     r8, [rbp+57h+hObject]
0x14003e9ff  xor     edx, edx
0x14003ea01  mov     rax, [rax+1E8h]
0x14003ea08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ea0d  mov     ebx, eax
0x14003ea0f  test    eax, eax
0x14003ea11  jns     short loc_14003EA24
0x14003ea13  lea     rax, aWritedumpfilew; "WriteDumpFileWide failed"
0x14003ea1a  mov     edx, 3BDh
0x14003ea1f  jmp     loc_14003E841
0x14003ea24  call    cs:__imp_GetTickCount
0x14003ea2b  nop     dword ptr [rax+rax+00h]
0x14003ea30  mov     ecx, eax
0x14003ea32  sub     ecx, r15d
0x14003ea35  lea     edx, [rcx-1]
0x14003ea38  cmp     eax, r15d
0x14003ea3b  cmovnb  edx, ecx
0x14003ea3e  mov     rcx, [rbp+5Fh]; this
0x14003ea42  mov     dword ptr [rsp+0D0h+var_A0], edx; char *
0x14003ea46  lea     rax, aTimeForDumpCon; "*** Time for dump conversion (ms): %u"
0x14003ea4d  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x14003ea52  mov     dword ptr [rsp+0D0h+var_B0], 80000000h; wil::details *
0x14003ea5a  mov     r9, r13; char *
0x14003ea5d  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003ea64  mov     edx, 3C1h; void *
0x14003ea69  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003ea6e  mov     r8, [rbp+57h+var_60]
0x14003ea72  mov     rdx, [rbp+57h+lpFileName]
0x14003ea76  sub     r8, rdx
0x14003ea79  sar     r8, 1
0x14003ea7c  lea     rcx, [rdi+2110h]
0x14003ea83  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W_K@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *,unsigned __int64)
0x14003ea88  test    al, al
0x14003ea8a  jnz     short loc_14003EAA2
0x14003ea8c  mov     ebx, 8007000Eh
0x14003ea91  lea     rax, aCopyFailed; "Copy failed"
0x14003ea98  mov     edx, 3C6h
0x14003ea9d  jmp     loc_14003E841
0x14003eaa2  mov     rbx, [rbp+57h+arg_8]
0x14003eaa6  mov     rax, [rbx]
0x14003eaa9  mov     r15, [rax]
0x14003eaac  mov     [rbp+57h+var_80], r12
0x14003eab0  lea     rax, [rbp+57h+arg_10]
0x14003eab4  mov     [rbp+57h+var_78], rax
0x14003eab8  mov     rcx, [rbp+57h+arg_10]
0x14003eabc  mov     [rbp+57h+arg_10], r12
0x14003eac0  test    rcx, rcx
0x14003eac3  jz      short loc_14003EAD2
0x14003eac5  mov     rax, [rcx]
0x14003eac8  mov     rax, [rax+10h]
0x14003eacc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ead1  nop
0x14003ead2  lea     r8, [rbp+57h+var_80]
0x14003ead6  lea     rdx, _GUID_23f79d6c_8aaf_4f7c_a607_9995f5407e63
0x14003eadd  mov     rcx, rbx
0x14003eae0  mov     rax, r15
0x14003eae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eae8  mov     ebx, eax
0x14003eaea  mov     rax, [rbp+57h+var_80]
0x14003eaee  test    rax, rax
0x14003eaf1  jz      short loc_14003EB0F
0x14003eaf3  mov     rdx, [rbp+57h+var_78]
0x14003eaf7  mov     rcx, [rdx]
0x14003eafa  mov     [rdx], rax
0x14003eafd  test    rcx, rcx
0x14003eb00  jz      short loc_14003EB0F
0x14003eb02  mov     rax, [rcx]
0x14003eb05  mov     rax, [rax+10h]
0x14003eb09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eb0e  nop
0x14003eb0f  test    ebx, ebx
0x14003eb11  js      short loc_14003EB4D
0x14003eb13  mov     rcx, [rbp+57h+arg_10]
0x14003eb17  mov     rax, [rcx]
0x14003eb1a  mov     qword ptr [rsp+0D0h+var_A8], r12
0x14003eb1f  mov     dword ptr [rsp+0D0h+var_B0], r12d
0x14003eb24  xor     r9d, r9d
0x14003eb27  xor     r8d, r8d
0x14003eb2a  lea     rdx, GUID_IPT
0x14003eb31  mov     rax, [rax+0F0h]
0x14003eb38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eb3d  test    eax, eax
0x14003eb3f  js      short loc_14003EB75
0x14003eb41  mov     dword ptr [rdi+2158h], 1
0x14003eb4b  jmp     short loc_14003EB75
0x14003eb4d  mov     rcx, [rbp+5Fh]; this
0x14003eb51  lea     rax, aQueryinterface; "QueryInterface failed for IDebugDataSpa"...
0x14003eb58  mov     qword ptr [rsp+0D0h+var_A8], rax; int
0x14003eb5d  mov     dword ptr [rsp+0D0h+var_B0], ebx; char *
0x14003eb61  mov     r9, r13; char *
0x14003eb64  lea     r8, aOnecoreWindows; "onecore\\windows\\feedback\\core\\werfa"...
0x14003eb6b  mov     edx, 3E0h; void *
0x14003eb70  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x14003eb75  mov     ebx, r12d
0x14003eb78  mov     rcx, [rbp+57h+arg_10]
0x14003eb7c  mov     [rbp+57h+arg_10], r12
0x14003eb80  test    rcx, rcx
0x14003eb83  jz      short loc_14003EB92
0x14003eb85  mov     rax, [rcx]
0x14003eb88  mov     rax, [rax+10h]
0x14003eb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003eb91  nop
0x14003eb92  mov     rcx, [rbp+57h+arg_18]
0x14003eb96  mov     [rbp+57h+arg_18], r12
0x14003eb9a  test    rcx, rcx
0x14003eb9d  jz      short loc_14003EBAC
0x14003eb9f  mov     rax, [rcx]
0x14003eba2  mov     rax, [rax+10h]
0x14003eba6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ebab  nop
0x14003ebac  mov     rcx, [rbp+57h+arg_8]
0x14003ebb0  test    rcx, rcx
0x14003ebb3  jz      short loc_14003EBCA
0x14003ebb5  mov     rax, [rcx]
0x14003ebb8  xor     edx, edx
0x14003ebba  mov     rax, [rax+0D0h]
0x14003ebc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ebc6  mov     rcx, [rbp+57h+arg_8]
0x14003ebca  mov     [rbp+57h+arg_8], r12
0x14003ebce  test    rcx, rcx
0x14003ebd1  jz      short loc_14003EBE0
0x14003ebd3  mov     rax, [rcx]
0x14003ebd6  mov     rax, [rax+10h]
0x14003ebda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14003ebdf  nop
0x14003ebe0  mov     rcx, [rbp+57h+hObject]; hObject
0x14003ebe4  lea     rax, [rcx+1]
0x14003ebe8  cmp     rax, 1
0x14003ebec  jbe     short loc_14003EBFA
0x14003ebee  call    cs:__imp_CloseHandle
0x14003ebf5  nop     dword ptr [rax+rax+00h]
0x14003ebfa  test    ebx, ebx
0x14003ebfc  jns     short loc_14003EC0F
0x14003ebfe  mov     rcx, [rbp+57h+lpFileName]; lpFileName
0x14003ec02  call    cs:__imp_DeleteFileW
0x14003ec09  nop     dword ptr [rax+rax+00h]
0x14003ec0e  nop
0x14003ec0f  test    r14b, r14b
  ... truncated ...
```
