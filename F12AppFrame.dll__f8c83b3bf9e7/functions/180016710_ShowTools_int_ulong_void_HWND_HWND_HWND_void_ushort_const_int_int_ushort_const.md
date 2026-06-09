# ShowTools(int,ulong,void *,HWND__ *,HWND__ *,HWND__ *,void *,ushort const *,int,int,ushort const *)

- ea: `0x180016710`
- end: `0x1800170d1`
- name: `?ShowTools@@YAHHKPEAXPEAUHWND__@@110PEBGHH2@Z`
- size: `2497`
- prototype: `__int64 __fastcall(int, DWORD, void *, HWND, HWND, HWND, HANDLE hSourceHandle, const unsigned __int16 *, int, unsigned int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `15`
- tags: `authz_impersonation`

## callers

- `0x180014740`

## callees

- `0x180001800`
- `0x180005d88`
- `0x180005e44`
- `0x180006b40`
- `0x180006c88`
- `0x18000d48c`
- `0x180012210`
- `0x180016710`
- `0x180017a80`
- `0x18001f024`
- `0x180020090`
- `0x180022c00`
- `0x180030590`
- `0x1800323dc`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016a5b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016a72`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016c7a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016c91`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016d4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016d63`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016a5b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016a72`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016c7a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016c91`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016d4c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180016d63`
- `KERNEL32!EnterCriticalSection` at `0x180016c14`
- `KERNEL32!EnterCriticalSection` at `0x180016c14`
- `KERNEL32!LeaveCriticalSection` at `0x180016c5a`
- `KERNEL32!LeaveCriticalSection` at `0x180016c5a`
- `KERNEL32!GetCurrentThreadId` at `0x180016c25`
- `KERNEL32!GetCurrentThreadId` at `0x180016c25`
- `KERNEL32!CloseHandle` at `0x180016a9a`
- `KERNEL32!CloseHandle` at `0x180016aaf`
- `KERNEL32!CloseHandle` at `0x180016abd`
- `KERNEL32!CloseHandle` at `0x180016ac7`
- `KERNEL32!CloseHandle` at `0x180016cb9`
- `KERNEL32!CloseHandle` at `0x180016cce`
- `KERNEL32!CloseHandle` at `0x180016cdc`
- `KERNEL32!CloseHandle` at `0x180016ce6`
- `KERNEL32!CloseHandle` at `0x180016d8b`
- `KERNEL32!CloseHandle` at `0x180016da0`
- `KERNEL32!CloseHandle` at `0x180016dae`
- `KERNEL32!CloseHandle` at `0x180016db8`
- `KERNEL32!CloseHandle` at `0x180016dfa`
- `KERNEL32!CloseHandle` at `0x180016e0f`
- `KERNEL32!CloseHandle` at `0x180016e1d`
- `KERNEL32!CloseHandle` at `0x180016e27`
- `KERNEL32!CloseHandle` at `0x180016e69`
- `KERNEL32!CloseHandle` at `0x180016e7e`
- `KERNEL32!CloseHandle` at `0x180016e8c`
- `KERNEL32!CloseHandle` at `0x180016e96`
- `KERNEL32!CloseHandle` at `0x180016ed8`
- `KERNEL32!CloseHandle` at `0x180016eed`
- `KERNEL32!CloseHandle` at `0x180016efb`
- `KERNEL32!CloseHandle` at `0x180016f05`
- `KERNEL32!CloseHandle` at `0x180016f49`
- `KERNEL32!CloseHandle` at `0x180016f5e`
- `KERNEL32!CloseHandle` at `0x180016f6c`
- `KERNEL32!CloseHandle` at `0x180016f76`
- `KERNEL32!CloseHandle` at `0x180016fa3`
- `KERNEL32!CloseHandle` at `0x180016fb8`
- `KERNEL32!CloseHandle` at `0x180016fc6`
- `KERNEL32!CloseHandle` at `0x180016fd0`
- `KERNEL32!CloseHandle` at `0x180016ffd`
- `KERNEL32!CloseHandle` at `0x18001700b`
- `KERNEL32!CloseHandle` at `0x180017015`
- `KERNEL32!CloseHandle` at `0x18001703b`
- `KERNEL32!CloseHandle` at `0x180016a9a`
- `KERNEL32!CloseHandle` at `0x180016aaf`
- `KERNEL32!CloseHandle` at `0x180016abd`
- `KERNEL32!CloseHandle` at `0x180016ac7`
- `KERNEL32!CloseHandle` at `0x180016cb9`
- `KERNEL32!CloseHandle` at `0x180016cce`
- `KERNEL32!CloseHandle` at `0x180016cdc`
- `KERNEL32!CloseHandle` at `0x180016ce6`
- `KERNEL32!CloseHandle` at `0x180016d8b`
- `KERNEL32!CloseHandle` at `0x180016da0`
- `KERNEL32!CloseHandle` at `0x180016dae`
- `KERNEL32!CloseHandle` at `0x180016db8`
- `KERNEL32!CloseHandle` at `0x180016dfa`
- `KERNEL32!CloseHandle` at `0x180016e0f`
- `KERNEL32!CloseHandle` at `0x180016e1d`
- `KERNEL32!CloseHandle` at `0x180016e27`
- `KERNEL32!CloseHandle` at `0x180016e69`
- `KERNEL32!CloseHandle` at `0x180016e7e`
- `KERNEL32!CloseHandle` at `0x180016e8c`
- `KERNEL32!CloseHandle` at `0x180016e96`
- `KERNEL32!CloseHandle` at `0x180016ed8`
- `KERNEL32!CloseHandle` at `0x180016eed`
- `KERNEL32!CloseHandle` at `0x180016efb`
- `KERNEL32!CloseHandle` at `0x180016f05`
- `KERNEL32!CloseHandle` at `0x180016f49`
- `KERNEL32!CloseHandle` at `0x180016f5e`
- `KERNEL32!CloseHandle` at `0x180016f6c`
- `KERNEL32!CloseHandle` at `0x180016f76`
- `KERNEL32!CloseHandle` at `0x180016fa3`
- `KERNEL32!CloseHandle` at `0x180016fb8`
- `KERNEL32!CloseHandle` at `0x180016fc6`
- `KERNEL32!CloseHandle` at `0x180016fd0`
- `KERNEL32!CloseHandle` at `0x180016ffd`
- `KERNEL32!CloseHandle` at `0x18001700b`
- `KERNEL32!CloseHandle` at `0x180017015`
- `KERNEL32!CloseHandle` at `0x18001703b`
- `KERNEL32!CreateEventW` at `0x180016b82`
- `KERNEL32!CreateEventW` at `0x180016b97`
- `KERNEL32!CreateEventW` at `0x180016b82`
- `KERNEL32!CreateEventW` at `0x180016b97`
- `KERNEL32!CreateThread` at `0x180016bcf`
- `KERNEL32!CreateThread` at `0x180016bcf`
- `KERNEL32!OpenThread` at `0x18001685b`
- `KERNEL32!OpenThread` at `0x18001685b`
- `KERNEL32!GetProcessIdOfThread` at `0x180016874`
- `KERNEL32!GetProcessIdOfThread` at `0x180016874`
- `KERNEL32!OpenProcess` at `0x180016887`
- `KERNEL32!OpenProcess` at `0x180016887`
- `KERNEL32!DuplicateHandle` at `0x1800168d2`
- `KERNEL32!DuplicateHandle` at `0x18001690f`
- `KERNEL32!DuplicateHandle` at `0x1800168d2`
- `KERNEL32!DuplicateHandle` at `0x18001690f`
- `KERNEL32!GetCurrentProcess` at `0x1800168a6`
- `KERNEL32!GetCurrentProcess` at `0x1800168e7`
- `KERNEL32!GetCurrentProcess` at `0x1800168a6`
- `KERNEL32!GetCurrentProcess` at `0x1800168e7`
- `USER32!MessageBoxW` at `0x1800167d0`
- `USER32!MessageBoxW` at `0x1800167d0`

## pseudocode

```c
__int64 __fastcall ShowTools(
        int a1,
        DWORD a2,
        void *a3,
        HWND a4,
        HWND a5,
        HWND a6,
        HANDLE hSourceHandle,
        const unsigned __int16 *a8,
        int a9,
        unsigned int a10,
        const unsigned __int16 *a11)
{
  int EnvironmentVariableW; // eax
  unsigned __int16 *v14; // rdi
  int v15; // edx
  void (*v16)(void); // rax
  HANDLE v17; // rax
  void *v18; // rsi
  DWORD ProcessIdOfThread; // r13d
  HANDLE v20; // r14
  HANDLE CurrentProcess; // rax
  HANDLE v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  __int64 v25; // rbx
  WTL::CAppModule *v26; // rcx
  int v27; // edx
  enum LaunchMode *v28; // r9
  _QWORD *v29; // rdx
  HANDLE v30; // rax
  HANDLE v31; // rax
  unsigned int v32; // r13d
  struct _RTL_CRITICAL_SECTION *v33; // r12
  _DWORD *v34; // r15
  DWORD CurrentThreadId; // eax
  int v36; // edx
  HANDLE TargetHandle; // [rsp+50h] [rbp-B0h] BYREF
  HANDLE hObject; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v40; // [rsp+60h] [rbp-A0h] BYREF
  int v41; // [rsp+68h] [rbp-98h] BYREF
  int nCmdShow; // [rsp+6Ch] [rbp-94h]
  __int64 v43; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int16 *v44; // [rsp+78h] [rbp-88h] BYREF
  const unsigned __int16 *v45; // [rsp+80h] [rbp-80h]
  HWND v46; // [rsp+88h] [rbp-78h]
  char v47; // [rsp+90h] [rbp-70h]
  void **v48; // [rsp+A0h] [rbp-60h] BYREF
  void *v49; // [rsp+A8h] [rbp-58h]
  __int64 v50; // [rsp+B0h] [rbp-50h]
  void *Block; // [rsp+B8h] [rbp-48h]
  __int64 v52; // [rsp+C0h] [rbp-40h]
  const unsigned __int16 *v53; // [rsp+100h] [rbp+0h]
  _QWORD v54[7]; // [rsp+108h] [rbp+8h] BYREF
  _QWORD *v55; // [rsp+140h] [rbp+40h]
  HANDLE v56; // [rsp+148h] [rbp+48h]
  HANDLE v57; // [rsp+150h] [rbp+50h]
  HANDLE Parameter; // [rsp+160h] [rbp+60h] BYREF
  DWORD ThreadId; // [rsp+168h] [rbp+68h] BYREF
  HANDLE v60; // [rsp+170h] [rbp+70h]
  HANDLE EventW; // [rsp+178h] [rbp+78h]
  HANDLE v62; // [rsp+180h] [rbp+80h]
  _BYTE v63[56]; // [rsp+188h] [rbp+88h] BYREF
  __int64 v64; // [rsp+1C0h] [rbp+C0h]
  _BYTE v65[736]; // [rsp+1D0h] [rbp+D0h] BYREF

  v46 = a4;
  nCmdShow = a1;
  v45 = a8;
  v53 = a11;
  v44 = (unsigned __int16 *)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  EnvironmentVariableW = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::GetEnvironmentVariableW(
                           &v44,
                           L"F12BREAKONSTART");
  v14 = v44;
  if ( EnvironmentVariableW )
  {
    v15 = *v44 - 49;
    if ( *v44 == 49 )
      v15 = v44[1];
    if ( !v15 )
      MessageBoxW(
        0,
        L"Attach now...\nTo avoid this dialog, clear F12BREAKONSTART\nenvironment variable",
        L"Debug message",
        0x40u);
  }
  v40 = 0;
  if ( !hSourceHandle )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
    {
      v16 = *(void (**)(void))(**((_QWORD **)v14 - 3) + 8LL);
      goto LABEL_127;
    }
    return 0xFFFFFFFFLL;
  }
  if ( a2 - 1 > 0x7FFFFFFD && a2 < 0x80000001 )
    goto LABEL_9;
  switch ( (_DWORD)a3 )
  {
    case 0:
      goto LABEL_9;
    case 0x7FFFFFFF:
      goto LABEL_9;
    case 0x80000000:
      goto LABEL_9;
  }
  if ( (unsigned int)((_DWORD)hSourceHandle + 0x7FFFFFFF) > 0xFFFFFFFD )
    goto LABEL_9;
  v17 = OpenThread(0x800u, 0, a2);
  v18 = v17;
  v56 = v17;
  if ( !v17 )
    goto LABEL_9;
  ProcessIdOfThread = GetProcessIdOfThread(v17);
  v20 = OpenProcess(0x100040u, 0, ProcessIdOfThread);
  v57 = v20;
  if ( !v20 )
  {
    CloseHandle(v18);
    goto LABEL_9;
  }
  TargetHandle = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !DuplicateHandle(v20, a3, CurrentProcess, &TargetHandle, 2u, 0, 3u) )
  {
    if ( TargetHandle )
    {
      CloseHandle(TargetHandle);
      TargetHandle = 0;
    }
    CloseHandle(v20);
    CloseHandle(v18);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    goto LABEL_9;
  }
  hObject = 0;
  v22 = GetCurrentProcess();
  if ( !DuplicateHandle(v20, hSourceHandle, v22, &hObject, 2u, 0, 3u) )
  {
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( TargetHandle )
    {
      CloseHandle(TargetHandle);
      TargetHandle = 0;
    }
    CloseHandle(v20);
    CloseHandle(v18);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    goto LABEL_9;
  }
  v43 = 0;
  if ( (unsigned int)Win32Helpers::CreateInstance<ILocalDebuggeeScriptHostFactory2>(v24, v23, &v43) )
  {
    if ( v43 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v43 + 16LL))(v43);
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( TargetHandle )
    {
      CloseHandle(TargetHandle);
      TargetHandle = 0;
    }
    CloseHandle(v20);
    CloseHandle(v18);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    goto LABEL_9;
  }
  v25 = v43;
  if ( (*(unsigned int (__fastcall **)(__int64, _QWORD, HANDLE, HANDLE))(*(_QWORD *)v43 + 32LL))(
         v43,
         ProcessIdOfThread,
         hObject,
         TargetHandle) )
  {
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( TargetHandle )
    {
      CloseHandle(TargetHandle);
      TargetHandle = 0;
    }
    CloseHandle(v20);
    CloseHandle(v18);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    goto LABEL_9;
  }
  TargetHandle = 0;
  hObject = 0;
  if ( (**(unsigned int (__fastcall ***)(__int64, GUID *, __int64 *))v25)(
         v25,
         &GUID_8c0c62b4_37f1_11e3_8259_6c3be516ead0,
         &v40) )
  {
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( TargetHandle )
    {
      CloseHandle(TargetHandle);
      TargetHandle = 0;
    }
    CloseHandle(v20);
    CloseHandle(v18);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    goto LABEL_9;
  }
  if ( !v40 )
  {
    if ( v25 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( TargetHandle )
    {
      CloseHandle(TargetHandle);
      TargetHandle = 0;
    }
    CloseHandle(v20);
    CloseHandle(v18);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    goto LABEL_9;
  }
  v48 = &WTL::CMessageLoop::`vftable';
  v49 = 0;
  v50 = 0;
  Block = 0;
  v52 = 0;
  WTL::CAppModule::AddMessageLoop(v26, (struct WTL::CMessageLoop *)&v48);
  v41 = 0;
  F12::GetLaunchMode((F12 *)a10, v27, (int)&v41, v28);
  FrameWindow::FrameWindow(v65, v40, ProcessIdOfThread, a2, v46, a5, v45, a9 != 0, v41, v53);
  if ( (unsigned int)FrameWindow::Initialize((FrameWindow *)v65, nCmdShow, a6) )
  {
    FrameWindow::~FrameWindow((FrameWindow *)v65);
    if ( Block )
    {
      free(Block);
      Block = 0;
    }
    v52 = 0;
    if ( v49 )
    {
      free(v49);
      v49 = 0;
    }
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( TargetHandle )
    {
      CloseHandle(TargetHandle);
      TargetHandle = 0;
    }
    CloseHandle(v20);
    CloseHandle(v18);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
    goto LABEL_9;
  }
  v54[0] = &std::_Func_impl_no_alloc<_lambda_fbbe5ba746a02a93b5ed26e262a97d58_,void,>::`vftable';
  v54[1] = v65;
  v55 = v54;
  v46 = (HWND)v54;
  Parameter = v20;
  ThreadId = 0;
  v60 = 0;
  EventW = 0;
  v62 = 0;
  v45 = (const unsigned __int16 *)v63;
  v64 = 0;
  v64 = std::_Func_impl_no_alloc__lambda_fbbe5ba746a02a93b5ed26e262a97d58__void_::_Move(v54, v63);
  if ( v55 )
  {
    v29 = v54;
    LOBYTE(v29) = v55 != v54;
    (*(void (__fastcall **)(_QWORD *, _QWORD *))(*v55 + 32LL))(v55, v29);
    v55 = 0;
  }
  EventW = CreateEventW(0, 1, 0, 0);
  v30 = CreateEventW(0, 1, 0, 0);
  v62 = v30;
  if ( !EventW
    || !v30
    || (v31 = CreateThread(0, 0x1000u, F12::ProcessWatcher::WatcherThreadProc, &Parameter, 0, &ThreadId)) == 0 )
  {
    if ( !(unsigned int)ATL::AtlHresultFromLastError() )
      goto LABEL_42;
    F12::ProcessWatcher::~ProcessWatcher((F12::ProcessWatcher *)&Parameter);
    FrameWindow::~FrameWindow((FrameWindow *)v65);
    if ( Block )
    {
      free(Block);
      Block = 0;
    }
    v52 = 0;
    if ( v49 )
    {
      free(v49);
      v49 = 0;
    }
    v50 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
    if ( hObject )
    {
      CloseHandle(hObject);
      hObject = 0;
    }
    if ( TargetHandle )
    {
      CloseHandle(TargetHandle);
      TargetHandle = 0;
    }
    CloseHandle(v20);
    CloseHandle(v18);
    if ( v40 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
LABEL_9:
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
    {
      v16 = *(void (**)(void))(**((_QWORD **)v14 - 3) + 8LL);
LABEL_127:
      v16();
      return 0xFFFFFFFFLL;
    }
    return 0xFFFFFFFFLL;
  }
  v60 = v31;
LABEL_42:
  v32 = WTL::CMessageLoop::Run((WTL::CMessageLoop *)&v48);
  F12::ProcessWatcher::~ProcessWatcher((F12::ProcessWatcher *)&Parameter);
  v33 = (struct _RTL_CRITICAL_SECTION *)((char *)ATL::_pAtlModule + 24);
  v46 = (HWND)((char *)ATL::_pAtlModule + 24);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)ATL::_pAtlModule + 24));
  v47 = 1;
  v34 = qword_180050788;
  CurrentThreadId = GetCurrentThreadId();
  if ( (int)v34[4] > 0 )
  {
    v36 = 0;
    while ( *(_DWORD *)(*(_QWORD *)v34 + 4LL * v36) != CurrentThreadId )
    {
      if ( ++v36 >= v34[4] )
        goto LABEL_49;
    }
    if ( v36 != -1 )
      ATL::CSimpleMap<unsigned long,WTL::CMessageLoop *,ATL::CSimpleMapEqualHelper<unsigned long,WTL::CMessageLoop *>>::RemoveAt(v34);
  }
LABEL_49:
  LeaveCriticalSection(v33);
  FrameWindow::~FrameWindow((FrameWindow *)v65);
  if ( Block )
  {
    free(Block);
    Block = 0;
  }
  v52 = 0;
  if ( v49 )
  {
    free(v49);
    v49 = 0;
  }
  v50 = 0;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v25 + 16LL))(v25);
  if ( hObject )
  {
    CloseHandle(hObject);
    hObject = 0;
  }
  if ( TargetHandle )
  {
    CloseHandle(TargetHandle);
    TargetHandle = 0;
  }
  CloseHandle(v20);
  CloseHandle(v18);
  if ( v40 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v40 + 16LL))(v40);
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)v14 - 2, 0xFFFFFFFF) <= 1 )
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v14 - 3) + 8LL))(*((_QWORD *)v14 - 3));
  return v32;
}

```

## disassembly

```asm
0x180016710  mov     [rsp-8+arg_18], rbx
0x180016715  push    rbp
0x180016716  push    rsi
0x180016717  push    rdi
0x180016718  push    r12
0x18001671a  push    r13
0x18001671c  push    r14
0x18001671e  push    r15
0x180016720  lea     rbp, [rsp-3C0h]
0x180016728  sub     rsp, 4C0h
0x18001672f  mov     rax, cs:__security_cookie
0x180016736  xor     rax, rsp
0x180016739  mov     [rbp+3F0h+var_40], rax
0x180016740  mov     [rbp+3F0h+var_468], r9
0x180016744  mov     rbx, r8
0x180016747  mov     r15d, edx
0x18001674a  mov     [rsp+4F0h+nCmdShow], ecx
0x18001674e  mov     r12, [rbp+3F0h+hSourceHandle]
0x180016755  mov     rax, [rbp+3F0h+arg_38]
0x18001675c  mov     [rbp+3F0h+var_470], rax
0x180016760  mov     rax, [rbp+3F0h+arg_50]
0x180016767  mov     [rbp+3F0h+var_3F0], rax
0x18001676b  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180016772  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180016779  mov     rax, [rax+18h]
0x18001677d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016782  add     rax, 18h
0x180016786  mov     [rsp+4F0h+var_478], rax
0x18001678b  lea     rdx, aF12breakonstar; "F12BREAKONSTART"
0x180016792  lea     rcx, [rsp+4F0h+var_478]
0x180016797  call    ?GetEnvironmentVariableW@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::GetEnvironmentVariableW(ushort const *)
0x18001679c  mov     rdi, [rsp+4F0h+var_478]
0x1800167a1  test    eax, eax
0x1800167a3  jz      short loc_1800167D6
0x1800167a5  movzx   edx, word ptr [rdi]
0x1800167a8  sub     edx, 31h ; '1'
0x1800167ab  jnz     short loc_1800167B8
0x1800167ad  movzx   edx, word ptr [rdi+2]
0x1800167b1  xor     eax, eax
0x1800167b3  movzx   ecx, ax
0x1800167b6  sub     edx, ecx
0x1800167b8  test    edx, edx
0x1800167ba  jnz     short loc_1800167D6
0x1800167bc  lea     r9d, [rdx+40h]; uType
0x1800167c0  lea     r8, Caption; "Debug message"
0x1800167c7  lea     rdx, Text; "Attach now...\nTo avoid this dialog, cl"...
0x1800167ce  xor     ecx, ecx; hWnd
0x1800167d0  call    cs:__imp_MessageBoxW
0x1800167d6  mov     [rsp+4F0h+var_490], 0
0x1800167df  test    r12, r12
0x1800167e2  jz      loc_180017084
0x1800167e8  lea     eax, [r15-1]
0x1800167ec  cmp     eax, 7FFFFFFDh
0x1800167f1  jbe     short loc_180016820
0x1800167f3  cmp     r15d, 80000001h
0x1800167fa  jnb     short loc_180016820
0x1800167fc  lea     rdx, [rdi-18h]
0x180016800  or      eax, 0FFFFFFFFh
0x180016803  lock xadd [rdx+10h], eax
0x180016808  sub     eax, 1
0x18001680b  jg      loc_1800170A4
0x180016811  mov     rcx, [rdx]
0x180016814  mov     rax, [rcx]
0x180016817  mov     rax, [rax+8]
0x18001681b  jmp     loc_18001709F
0x180016820  test    ebx, ebx
0x180016822  jz      loc_18001707F
0x180016828  cmp     ebx, 7FFFFFFFh
0x18001682e  jz      loc_18001707F
0x180016834  cmp     ebx, 80000000h
0x18001683a  jz      loc_18001707F
0x180016840  lea     eax, [r12+7FFFFFFFh]
0x180016848  cmp     eax, 0FFFFFFFDh
0x18001684b  ja      loc_18001707A
0x180016851  mov     r8d, r15d; dwThreadId
0x180016854  xor     edx, edx; bInheritHandle
0x180016856  mov     ecx, 800h; dwDesiredAccess
0x18001685b  call    cs:__imp_OpenThread
0x180016861  mov     rsi, rax
0x180016864  mov     [rbp+3F0h+var_3A8], rax
0x180016868  test    rax, rax
0x18001686b  jz      loc_18001705E
0x180016871  mov     rcx, rax; Thread
0x180016874  call    cs:__imp_GetProcessIdOfThread
0x18001687a  mov     r13d, eax
0x18001687d  mov     r8d, eax; dwProcessId
0x180016880  xor     edx, edx; bInheritHandle
0x180016882  mov     ecx, 100040h; dwDesiredAccess
0x180016887  call    cs:__imp_OpenProcess
0x18001688d  mov     r14, rax
0x180016890  mov     [rbp+3F0h+var_3A0], rax
0x180016894  test    rax, rax
0x180016897  jz      loc_180017038
0x18001689d  mov     [rsp+4F0h+TargetHandle], 0
0x1800168a6  call    cs:__imp_GetCurrentProcess
0x1800168ac  mov     [rsp+4F0h+dwOptions], 3; dwOptions
0x1800168b4  mov     [rsp+4F0h+bInheritHandle], 0; bInheritHandle
0x1800168bc  mov     [rsp+4F0h+dwDesiredAccess], 2; dwDesiredAccess
0x1800168c4  lea     r9, [rsp+4F0h+TargetHandle]; lpTargetHandle
0x1800168c9  mov     r8, rax; hTargetProcessHandle
0x1800168cc  mov     rdx, rbx; hSourceHandle
0x1800168cf  mov     rcx, r14; hSourceProcessHandle
0x1800168d2  call    cs:__imp_DuplicateHandle
0x1800168d8  xor     ebx, ebx
0x1800168da  test    eax, eax
0x1800168dc  jz      loc_180016FF3
0x1800168e2  mov     [rsp+4F0h+hObject], rbx
0x1800168e7  call    cs:__imp_GetCurrentProcess
0x1800168ed  mov     [rsp+4F0h+dwOptions], 3; dwOptions
0x1800168f5  mov     [rsp+4F0h+bInheritHandle], ebx; bInheritHandle
0x1800168f9  mov     [rsp+4F0h+dwDesiredAccess], 2; dwDesiredAccess
0x180016901  lea     r9, [rsp+4F0h+hObject]; lpTargetHandle
0x180016906  mov     r8, rax; hTargetProcessHandle
0x180016909  mov     rdx, r12; hSourceHandle
0x18001690c  mov     rcx, r14; hSourceProcessHandle
0x18001690f  call    cs:__imp_DuplicateHandle
0x180016915  xor     r12d, r12d
0x180016918  test    eax, eax
0x18001691a  jz      loc_180016F99
0x180016920  mov     [rsp+4F0h+var_480], r12
0x180016925  lea     r8, [rsp+4F0h+var_480]
0x18001692a  call    ??$CreateInstance@UILocalDebuggeeScriptHostFactory2@@@Win32Helpers@@YAJPEBGAEBU_GUID@@PEAPEAUILocalDebuggeeScriptHostFactory2@@@Z; Win32Helpers::CreateInstance<ILocalDebuggeeScriptHostFactory2>(ushort const *,_GUID const &,ILocalDebuggeeScriptHostFactory2 * *)
0x18001692f  test    eax, eax
0x180016931  jnz     loc_180016F28
0x180016937  mov     rbx, [rsp+4F0h+var_480]
0x18001693c  mov     rax, [rbx]
0x18001693f  mov     r9, [rsp+4F0h+TargetHandle]
0x180016944  mov     r8, [rsp+4F0h+hObject]
0x180016949  mov     edx, r13d
0x18001694c  mov     rcx, rbx
0x18001694f  mov     rax, [rax+20h]
0x180016953  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016958  test    eax, eax
0x18001695a  jnz     loc_180016EB9
0x180016960  mov     [rsp+4F0h+TargetHandle], r12
0x180016965  mov     [rsp+4F0h+hObject], r12
0x18001696a  mov     rax, [rbx]
0x18001696d  lea     r8, [rsp+4F0h+var_490]
0x180016972  lea     rdx, _GUID_8c0c62b4_37f1_11e3_8259_6c3be516ead0
0x180016979  mov     rcx, rbx
0x18001697c  mov     rax, [rax]
0x18001697f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016984  nop
0x180016985  test    eax, eax
0x180016987  jnz     loc_180016E4A
0x18001698d  cmp     [rsp+4F0h+var_490], r12
0x180016992  jz      loc_180016DDB
0x180016998  lea     rax, ??_7CMessageLoop@WTL@@6B@; const WTL::CMessageLoop::`vftable'
0x18001699f  mov     [rbp+3F0h+var_450], rax
0x1800169a3  mov     [rbp+3F0h+var_448], r12
0x1800169a7  mov     [rbp+3F0h+var_440], r12
0x1800169ab  mov     [rbp+3F0h+Block], r12
0x1800169af  mov     [rbp+3F0h+var_430], r12
0x1800169b3  lea     rdx, [rbp+3F0h+var_450]; struct WTL::CMessageLoop *
0x1800169b7  call    ?AddMessageLoop@CAppModule@WTL@@QEAAHPEAVCMessageLoop@2@@Z; WTL::CAppModule::AddMessageLoop(WTL::CMessageLoop *)
0x1800169bc  mov     [rsp+4F0h+var_488], r12d
0x1800169c1  lea     r8, [rsp+4F0h+var_488]; int
0x1800169c6  mov     ecx, dword ptr [rbp+3F0h+arg_48]; this
0x1800169cc  call    ?GetLaunchMode@F12@@YAXHHAEAW4LaunchMode@@@Z; F12::GetLaunchMode(int,int,LaunchMode &)
0x1800169d1  cmp     [rbp+3F0h+arg_40], r12d
0x1800169d8  setnz   cl
0x1800169db  mov     rax, [rbp+3F0h+var_3F0]
0x1800169df  mov     [rsp+4F0h+var_4A8], rax
0x1800169e4  mov     eax, [rsp+4F0h+var_488]
0x1800169e8  mov     [rsp+4F0h+var_4B0], eax
0x1800169ec  mov     [rsp+4F0h+var_4B8], cl
0x1800169f0  mov     rax, [rbp+3F0h+var_470]
0x1800169f4  mov     qword ptr [rsp+4F0h+dwOptions], rax
0x1800169f9  mov     rax, [rbp+3F0h+arg_20]
0x180016a00  mov     qword ptr [rsp+4F0h+bInheritHandle], rax
0x180016a05  mov     rax, [rbp+3F0h+var_468]
0x180016a09  mov     qword ptr [rsp+4F0h+dwDesiredAccess], rax
0x180016a0e  mov     r9d, r15d
0x180016a11  mov     r8d, r13d
0x180016a14  mov     rdx, [rsp+4F0h+var_490]
0x180016a19  lea     rcx, [rbp+3F0h+var_320]
0x180016a20  call    ??0FrameWindow@@QEAA@PEAUIScriptHostFactory@@KKPEAUHWND__@@1PEBG_NW4LaunchMode@@2@Z; FrameWindow::FrameWindow(IScriptHostFactory *,ulong,ulong,HWND__ *,HWND__ *,ushort const *,bool,LaunchMode,ushort const *)
0x180016a25  nop
0x180016a26  mov     r8, [rbp+3F0h+arg_28]; HWND
0x180016a2d  mov     edx, [rsp+4F0h+nCmdShow]; nCmdShow
0x180016a31  lea     rcx, [rbp+3F0h+var_320]; this
0x180016a38  call    ?Initialize@FrameWindow@@QEAAJHPEAUHWND__@@@Z; FrameWindow::Initialize(int,HWND__ *)
0x180016a3d  test    eax, eax
0x180016a3f  jz      loc_180016AEA
0x180016a45  lea     rcx, [rbp+3F0h+var_320]; this
0x180016a4c  call    ??1FrameWindow@@UEAA@XZ; FrameWindow::~FrameWindow(void)
0x180016a51  nop
0x180016a52  mov     rcx, [rbp+3F0h+Block]; Block
0x180016a56  test    rcx, rcx
0x180016a59  jz      short loc_180016A65
0x180016a5b  call    cs:__imp_free
0x180016a61  mov     [rbp+3F0h+Block], r12
0x180016a65  mov     [rbp+3F0h+var_430], r12
0x180016a69  mov     rcx, [rbp+3F0h+var_448]; Block
0x180016a6d  test    rcx, rcx
0x180016a70  jz      short loc_180016A7C
0x180016a72  call    cs:__imp_free
0x180016a78  mov     [rbp+3F0h+var_448], r12
0x180016a7c  mov     [rbp+3F0h+var_440], r12
0x180016a80  mov     rax, [rbx]
0x180016a83  mov     rcx, rbx
0x180016a86  mov     rax, [rax+10h]
0x180016a8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a8f  nop
0x180016a90  mov     rcx, [rsp+4F0h+hObject]; hObject
0x180016a95  test    rcx, rcx
0x180016a98  jz      short loc_180016AA5
0x180016a9a  call    cs:__imp_CloseHandle
0x180016aa0  mov     [rsp+4F0h+hObject], r12
0x180016aa5  mov     rcx, [rsp+4F0h+TargetHandle]; hObject
0x180016aaa  test    rcx, rcx
0x180016aad  jz      short loc_180016ABA
0x180016aaf  call    cs:__imp_CloseHandle
0x180016ab5  mov     [rsp+4F0h+TargetHandle], r12
0x180016aba  mov     rcx, r14; hObject
0x180016abd  call    cs:__imp_CloseHandle
0x180016ac3  nop
0x180016ac4  mov     rcx, rsi; hObject
0x180016ac7  call    cs:__imp_CloseHandle
0x180016acd  nop
0x180016ace  mov     rcx, [rsp+4F0h+var_490]
0x180016ad3  test    rcx, rcx
0x180016ad6  jz      short loc_180016AE5
0x180016ad8  mov     rax, [rcx]
0x180016adb  mov     rax, [rax+10h]
0x180016adf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ae4  nop
0x180016ae5  jmp     loc_1800167FC
0x180016aea  lea     rax, ??_7?$_Func_impl_no_alloc@V_lambda_fbbe5ba746a02a93b5ed26e262a97d58_@@X$$V@std@@6B@; const std::_Func_impl_no_alloc<_lambda_fbbe5ba746a02a93b5ed26e262a97d58_,void,>::`vftable'
0x180016af1  mov     [rbp+3F0h+var_3E8], rax
0x180016af5  lea     rax, [rbp+3F0h+var_320]
0x180016afc  mov     [rbp+3F0h+var_3E0], rax
0x180016b00  lea     rax, [rbp+3F0h+var_3E8]
0x180016b04  mov     [rbp+3F0h+var_3B0], rax
0x180016b08  lea     rax, [rbp+3F0h+var_3E8]
0x180016b0c  mov     [rbp+3F0h+var_468], rax
0x180016b10  mov     [rbp+3F0h+Parameter], r14
0x180016b14  mov     [rbp+3F0h+ThreadId], r12d
0x180016b18  mov     [rbp+3F0h+var_380], r12
0x180016b1c  mov     [rbp+3F0h+var_378], r12
0x180016b20  mov     [rbp+3F0h+var_370], r12
0x180016b27  lea     rax, [rbp+3F0h+var_368]
0x180016b2e  mov     [rbp+3F0h+var_470], rax
0x180016b32  mov     [rbp+3F0h+var_330], r12
0x180016b39  lea     rdx, [rbp+3F0h+var_368]
0x180016b40  lea     rcx, [rbp+3F0h+var_3E8]
0x180016b44  call    std___Func_impl_no_alloc__lambda_fbbe5ba746a02a93b5ed26e262a97d58__void____Move
0x180016b49  mov     [rbp+3F0h+var_330], rax
0x180016b50  mov     rcx, [rbp+3F0h+var_3B0]
0x180016b54  test    rcx, rcx
0x180016b57  jz      short loc_180016B73
0x180016b59  mov     rax, [rcx]
0x180016b5c  lea     rdx, [rbp+3F0h+var_3E8]
0x180016b60  cmp     rcx, rdx
0x180016b63  setnz   dl
0x180016b66  mov     rax, [rax+20h]
0x180016b6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b6f  mov     [rbp+3F0h+var_3B0], r12
0x180016b73  xor     r9d, r9d; lpName
0x180016b76  xor     r8d, r8d; bInitialState
0x180016b79  lea     r15d, [r9+1]
0x180016b7d  mov     edx, r15d; bManualReset
0x180016b80  xor     ecx, ecx; lpEventAttributes
0x180016b82  call    cs:__imp_CreateEventW
0x180016b88  mov     [rbp+3F0h+var_378], rax
0x180016b8c  xor     r9d, r9d; lpName
0x180016b8f  xor     r8d, r8d; bInitialState
0x180016b92  mov     edx, r15d; bManualReset
0x180016b95  xor     ecx, ecx; lpEventAttributes
0x180016b97  call    cs:__imp_CreateEventW
0x180016b9d  mov     [rbp+3F0h+var_370], rax
0x180016ba4  cmp     [rbp+3F0h+var_378], r12
0x180016ba8  jz      short loc_180016BE0
0x180016baa  test    rax, rax
0x180016bad  jz      short loc_180016BE0
0x180016baf  lea     rax, [rbp+3F0h+ThreadId]
0x180016bb3  mov     qword ptr [rsp+4F0h+bInheritHandle], rax; lpThreadId
0x180016bb8  mov     [rsp+4F0h+dwDesiredAccess], r12d; dwCreationFlags
0x180016bbd  lea     r9, [rbp+3F0h+Parameter]; lpParameter
0x180016bc1  lea     r8, ?WatcherThreadProc@ProcessWatcher@F12@@CAKPEAX@Z; lpStartAddress
0x180016bc8  mov     edx, 1000h; dwStackSize
0x180016bcd  xor     ecx, ecx; lpThreadAttributes
0x180016bcf  call    cs:__imp_CreateThread
0x180016bd5  test    rax, rax
0x180016bd8  jz      short loc_180016BE0
0x180016bda  mov     [rbp+3F0h+var_380], rax
0x180016bde  jmp     short loc_180016BED
0x180016be0  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180016be5  test    eax, eax
0x180016be7  jnz     loc_180016D2C
0x180016bed  lea     rcx, [rbp+3F0h+var_450]; this
0x180016bf1  call    ?Run@CMessageLoop@WTL@@QEAAHXZ; WTL::CMessageLoop::Run(void)
0x180016bf6  mov     r13d, eax
0x180016bf9  lea     rcx, [rbp+3F0h+Parameter]; this
0x180016bfd  call    ??1ProcessWatcher@F12@@QEAA@XZ; F12::ProcessWatcher::~ProcessWatcher(void)
0x180016c02  mov     r12, cs:?_pAtlModule@ATL@@3PEAVCAtlModule@1@EA; ATL::CAtlModule * ATL::_pAtlModule
0x180016c09  add     r12, 18h
0x180016c0d  mov     [rbp+3F0h+var_468], r12
0x180016c11  mov     rcx, r12; lpCriticalSection
0x180016c14  call    cs:__imp_EnterCriticalSection
  ... truncated ...
```
