# CDlpTask::Initialize(_GUID,ushort const *,ushort const *,WINDLP_STATE,int)

- ea: `0x140041e6c`
- end: `0x1400433d3`
- name: `?Initialize@CDlpTask@@QEAAJU_GUID@@PEBG1W4WINDLP_STATE@@H@Z`
- size: `5479`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, registry_config, service_task`

## callers

- `0x14002fef0`
- `0x1400332b0`

## callees

- `0x140002116`
- `0x140002a98`
- `0x140005e4c`
- `0x1400076c8`
- `0x140008434`
- `0x140009f00`
- `0x140011154`
- `0x1400111f0`
- `0x1400135b8`
- `0x140034ab4`
- `0x140038e64`
- `0x140040374`
- `0x140041e6c`
- `0x140047754`
- `0x14004c024`
- `0x140080d36`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x140041fe4`
- `KERNEL32!CloseHandle` at `0x1400420af`
- `KERNEL32!CloseHandle` at `0x14004217a`
- `KERNEL32!CloseHandle` at `0x140042e2e`
- `KERNEL32!CloseHandle` at `0x140042ef6`
- `KERNEL32!CloseHandle` at `0x140042fc0`
- `KERNEL32!CloseHandle` at `0x1400430ce`
- `KERNEL32!CloseHandle` at `0x1400431f1`
- `KERNEL32!CloseHandle` at `0x140041fe4`
- `KERNEL32!CloseHandle` at `0x1400420af`
- `KERNEL32!CloseHandle` at `0x14004217a`
- `KERNEL32!CloseHandle` at `0x140042e2e`
- `KERNEL32!CloseHandle` at `0x140042ef6`
- `KERNEL32!CloseHandle` at `0x140042fc0`
- `KERNEL32!CloseHandle` at `0x1400430ce`
- `KERNEL32!CloseHandle` at `0x1400431f1`
- `KERNEL32!HeapFree` at `0x140043355`
- `KERNEL32!HeapFree` at `0x140043383`
- `KERNEL32!HeapFree` at `0x140043355`
- `KERNEL32!HeapFree` at `0x140043383`
- `KERNEL32!GetProcessHeap` at `0x140043340`
- `KERNEL32!GetProcessHeap` at `0x14004336e`
- `KERNEL32!GetProcessHeap` at `0x140043340`
- `KERNEL32!GetProcessHeap` at `0x14004336e`
- `KERNEL32!CreateThread` at `0x1400430b3`
- `KERNEL32!CreateThread` at `0x1400431d6`
- `KERNEL32!CreateThread` at `0x1400430b3`
- `KERNEL32!CreateThread` at `0x1400431d6`
- `KERNEL32!GetLastError` at `0x140042003`
- `KERNEL32!GetLastError` at `0x1400420ce`
- `KERNEL32!GetLastError` at `0x140042199`
- `KERNEL32!GetLastError` at `0x14004253a`
- `KERNEL32!GetLastError` at `0x140042e4a`
- `KERNEL32!GetLastError` at `0x140042f12`
- `KERNEL32!GetLastError` at `0x140042fdc`
- `KERNEL32!GetLastError` at `0x1400430ea`
- `KERNEL32!GetLastError` at `0x14004320d`
- `KERNEL32!GetLastError` at `0x140042003`
- `KERNEL32!GetLastError` at `0x1400420ce`
- `KERNEL32!GetLastError` at `0x140042199`
- `KERNEL32!GetLastError` at `0x14004253a`
- `KERNEL32!GetLastError` at `0x140042e4a`
- `KERNEL32!GetLastError` at `0x140042f12`
- `KERNEL32!GetLastError` at `0x140042fdc`
- `KERNEL32!GetLastError` at `0x1400430ea`
- `KERNEL32!GetLastError` at `0x14004320d`
- `KERNEL32!CreateEventW` at `0x140041fc9`
- `KERNEL32!CreateEventW` at `0x140042094`
- `KERNEL32!CreateEventW` at `0x14004215f`
- `KERNEL32!CreateEventW` at `0x140042e13`
- `KERNEL32!CreateEventW` at `0x140042edb`
- `KERNEL32!CreateEventW` at `0x140042fa5`
- `KERNEL32!CreateEventW` at `0x140041fc9`
- `KERNEL32!CreateEventW` at `0x140042094`
- `KERNEL32!CreateEventW` at `0x14004215f`
- `KERNEL32!CreateEventW` at `0x140042e13`
- `KERNEL32!CreateEventW` at `0x140042edb`
- `KERNEL32!CreateEventW` at `0x140042fa5`
- `KERNEL32!GetFileAttributesW` at `0x140042471`
- `KERNEL32!GetFileAttributesW` at `0x1400425be`
- `KERNEL32!GetFileAttributesW` at `0x140042471`
- `KERNEL32!GetFileAttributesW` at `0x1400425be`
- `KERNEL32!LeaveCriticalSection` at `0x140042d58`
- `KERNEL32!LeaveCriticalSection` at `0x140042d58`
- `KERNEL32!GetFullPathNameW` at `0x140042526`
- `KERNEL32!GetFullPathNameW` at `0x140042526`
- `KERNEL32!EnterCriticalSection` at `0x140042d12`
- `KERNEL32!EnterCriticalSection` at `0x140042d12`

## string_xrefs

- `0x140042416`: `CDlpTask::Initialize`
- `0x140042756`: `CDlpTask::Initialize`
- `0x140043302`: `CDlpTask::Initialize`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CDlpTask::Initialize(__int64 a1, __int128 *a2, WCHAR *a3, WCHAR *a4, unsigned int a5, int a6)
{
  __int64 v10; // rsi
  __int64 v11; // rdi
  int v12; // ebx
  __int64 v13; // rax
  unsigned int v14; // r14d
  HANDLE EventW; // rbx
  void *v16; // rcx
  signed int v17; // eax
  HANDLE v18; // rbx
  void *v19; // rcx
  signed int LastError; // eax
  HANDLE v21; // rbx
  void *v22; // rcx
  signed int v23; // eax
  __int64 v24; // rcx
  __int64 v25; // rax
  unsigned int v26; // esi
  int v27; // eax
  DWORD FileAttributesW; // ebx
  int v29; // ebx
  signed int v30; // eax
  DWORD v31; // ebx
  int v32; // ebx
  int StringCch; // eax
  int v34; // eax
  __int64 v35; // rax
  unsigned int v36; // edi
  int v37; // eax
  __int64 v38; // rax
  int v39; // eax
  int v40; // eax
  __int64 v41; // rdx
  __int64 v42; // rdx
  HANDLE v43; // rbx
  void *v44; // rcx
  signed int v45; // eax
  HANDLE v46; // rbx
  void *v47; // rcx
  signed int v48; // eax
  HANDLE v49; // rbx
  void *v50; // rcx
  signed int v51; // eax
  __int64 v52; // rax
  HANDLE Thread; // rbx
  void *v54; // rcx
  signed int v55; // eax
  __int64 v56; // rax
  __int64 v57; // rax
  HANDLE v58; // rbx
  void *v59; // rcx
  signed int v60; // eax
  int v61; // eax
  int v62; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v64; // rax
  __int64 dwCreationFlags; // [rsp+20h] [rbp-E0h]
  LPDWORD lpThreadId; // [rsp+28h] [rbp-D8h]
  unsigned int v68; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v69; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v70; // [rsp+40h] [rbp-C0h]
  __int64 v71; // [rsp+48h] [rbp-B8h] BYREF
  LPWSTR FilePart; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v73; // [rsp+60h] [rbp-A0h] BYREF
  int v74; // [rsp+70h] [rbp-90h]
  __int64 v75; // [rsp+80h] [rbp-80h]
  WCHAR Buffer[1040]; // [rsp+90h] [rbp-70h] BYREF

  v75 = -2;
  v71 = 0;
  v10 = 0;
  v70 = 0;
  v11 = 0;
  v69 = 0;
  v68 = 0;
  FilePart = 0;
  v12 = CDlpState::Get((CDlpState *)(a1 + 296), (enum WINDLP_STATE *)&v68);
  if ( v12 < 0 )
  {
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
      goto LABEL_248;
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
    v14 = 0;
    if ( !v13 )
      goto LABEL_247;
    LODWORD(lpThreadId) = v12;
    LODWORD(dwCreationFlags) = 722;
    goto LABEL_245;
  }
  if ( v68 != -21037378 )
  {
    v12 = -2147023649;
    if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
      goto LABEL_248;
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
    v14 = 0;
    if ( !v13 )
      goto LABEL_247;
    LODWORD(lpThreadId) = -2147023649;
    LODWORD(dwCreationFlags) = 723;
    goto LABEL_245;
  }
  *(_DWORD *)(a1 + 1432) = 30000;
  *(_DWORD *)(a1 + 1436) = 1000;
  *(_DWORD *)(a1 + 1440) = 1000;
  EventW = CreateEventW(0, 1, 0, 0);
  v16 = *(void **)(a1 + 232);
  if ( v16 )
    CloseHandle(v16);
  if ( EventW )
  {
    *(_QWORD *)(a1 + 232) = EventW;
    v18 = CreateEventW(0, 0, 0, 0);
    v19 = *(void **)(a1 + 240);
    if ( v19 )
      CloseHandle(v19);
    if ( !v18 )
    {
      *(_QWORD *)(a1 + 240) = 0;
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v12 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v12 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( v12 >= 0 || !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 739;
      goto LABEL_245;
    }
    *(_QWORD *)(a1 + 240) = v18;
    v21 = CreateEventW(0, 0, 0, 0);
    v22 = *(void **)(a1 + 248);
    if ( v22 )
      CloseHandle(v22);
    if ( !v21 )
    {
      *(_QWORD *)(a1 + 248) = 0;
      v23 = GetLastError();
      v12 = v23;
      if ( v23 )
      {
        if ( v23 > 0 )
          v12 = (unsigned __int16)v23 | 0x80070000;
      }
      else
      {
        v12 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( v12 >= 0 || !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 742;
      goto LABEL_245;
    }
    *(_QWORD *)(a1 + 248) = v21;
    if ( memcmp_0(&WINDLP_TRANSPORT_NONE, a2, 0x10u) )
    {
      v24 = *(_QWORD *)(a1 + 1304);
      v73 = *a2;
      v12 = (*(__int64 (__fastcall **)(__int64, __int128 *, __int64 *))(*(_QWORD *)v24 + 80LL))(v24, &v73, &v71);
      if ( v12 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
          goto LABEL_248;
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
        v14 = 0;
        if ( !v13 )
          goto LABEL_247;
        LODWORD(lpThreadId) = v12;
        LODWORD(dwCreationFlags) = 749;
        goto LABEL_245;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 56LL))(v71, a1 + 1488);
      if ( v12 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
          goto LABEL_248;
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
        v14 = 0;
        if ( !v13 )
          goto LABEL_247;
        LODWORD(lpThreadId) = v12;
        LODWORD(dwCreationFlags) = 753;
        goto LABEL_245;
      }
      v12 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v71 + 64LL))(v71, a1 + 1428);
      if ( v12 < 0 )
      {
        if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
          goto LABEL_248;
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
        v14 = 0;
        if ( !v13 )
          goto LABEL_247;
        LODWORD(lpThreadId) = v12;
        LODWORD(dwCreationFlags) = 757;
        goto LABEL_245;
      }
    }
    if ( a3 )
    {
      v12 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(a3);
      a3 = 0;
      if ( v12 < 0 )
      {
        if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        {
          v25 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v26 = 0;
          if ( v25 )
          {
            v27 = CDlpLogT<CEmptyType>::DlpLogFormat(
                    v25,
                    4,
                    L"%s(%d): Result = 0x%X",
                    L"CDlpTask::Initialize",
                    765,
                    v12);
            v26 = v27;
            if ( v27 < 0 )
              CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v27);
          }
          CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v26);
        }
        v10 = v70;
        goto LABEL_248;
      }
      v10 = v70;
    }
    if ( a4 )
    {
      if ( a6 == (_DWORD)a3 )
      {
        v12 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::Create(a4);
        if ( v12 < 0 )
        {
          if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
          {
            v35 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
            v36 = (unsigned int)a3;
            if ( v35 )
            {
              v37 = CDlpLogT<CEmptyType>::DlpLogFormat(
                      v35,
                      4,
                      L"%s(%d): Result = 0x%X",
                      L"CDlpTask::Initialize",
                      798,
                      v12);
              v36 = v37;
              if ( v37 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v37);
            }
            CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v36);
          }
          v11 = v69;
          goto LABEL_248;
        }
        v11 = v69;
      }
      else
      {
        FileAttributesW = GetFileAttributesW(a4);
        if ( FileAttributesW == -1 )
          v29 = (int)a3;
        else
          v29 = (FileAttributesW >> 4) & 1;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( !v29 )
        {
          v12 = -2147024893;
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_248;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = (unsigned int)a3;
          if ( !v13 )
            goto LABEL_247;
          LODWORD(lpThreadId) = -2147024893;
          LODWORD(dwCreationFlags) = 775;
          goto LABEL_245;
        }
        FilePart = a3;
        memset_0(Buffer, 0, sizeof(Buffer));
        if ( !GetFullPathNameW(a4, 0x410u, Buffer, &FilePart) )
        {
          v30 = GetLastError();
          v12 = v30;
          if ( v30 )
          {
            if ( v30 > 0 )
              v12 = (unsigned __int16)v30 | 0x80070000;
          }
          else
          {
            v12 = -2147467259;
          }
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_248;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = (unsigned int)a3;
          if ( v12 >= 0 || !v13 )
            goto LABEL_247;
          LODWORD(lpThreadId) = v12;
          LODWORD(dwCreationFlags) = 781;
          goto LABEL_245;
        }
        v31 = GetFileAttributesW(Buffer);
        if ( v31 == -1 )
          v32 = (int)a3;
        else
          v32 = (v31 >> 4) & 1;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( !v32 )
        {
          v12 = -2147024893;
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_248;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = (unsigned int)a3;
          if ( !v13 )
            goto LABEL_247;
          LODWORD(lpThreadId) = -2147024893;
          LODWORD(dwCreationFlags) = 786;
          goto LABEL_245;
        }
        v68 = (unsigned int)a3;
        StringCch = CGlobalHelpersT<CEmptyType>::GetStringCchLength<unsigned long>(Buffer, &v68, 0x7FFFFFFF);
        v12 = StringCch;
        if ( StringCch >= 0 )
        {
          v34 = CImmutableStringsT<unsigned short,CImmutableStringsPolicyDefault>::CreateInternal(Buffer, v68, &v69);
          v12 = v34;
          if ( v34 < 0 )
            CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v34);
          v11 = v69;
        }
        else
        {
          CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(StringCch);
        }
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
        if ( v12 < 0 )
        {
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_248;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = (unsigned int)a3;
          if ( !v13 )
            goto LABEL_247;
          LODWORD(lpThreadId) = v12;
          LODWORD(dwCreationFlags) = 791;
          goto LABEL_245;
        }
      }
    }
    v38 = *(_QWORD *)(a1 + 1304);
    v12 = (int)a3;
    if ( v38 )
    {
      *(_QWORD *)(a1 + 96) = v38;
    }
    else
    {
      v12 = -2147024809;
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(-2147024809);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 804;
      goto LABEL_245;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 432));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 808;
      goto LABEL_245;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 488));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 809;
      goto LABEL_245;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 544));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 810;
      goto LABEL_245;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 600));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 811;
      goto LABEL_245;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 656));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 812;
      goto LABEL_245;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 712));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 813;
      goto LABEL_245;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 768));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 814;
      goto LABEL_245;
    }
    v12 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 824));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 815;
      goto LABEL_245;
    }
    v12 = CDword::Init((CDword *)(a1 + 872), 0xFFFFFFFF);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 816;
      goto LABEL_245;
    }
    v12 = CDword::Init((CDword *)(a1 + 1240), 0xFFFFFFFF);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 817;
      goto LABEL_245;
    }
    v12 = CProgressData::Init((CProgressData *)(a1 + 936));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 818;
      goto LABEL_245;
    }
    v12 = CProgressData::Init((CProgressData *)(a1 + 1096));
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = (unsigned int)a3;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 819;
      goto LABEL_245;
    }
    v39 = CExclusiveAcquireLock::Init((CExclusiveAcquireLock *)(a1 + 1048));
    v12 = v39;
    if ( v39 >= 0 )
    {
      EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 1048));
      v74 = 1;
      v40 = CProgressList::Reset((CProgressList *)(a1 + 1016));
      v12 = v40;
      if ( v40 >= 0 )
        *(_DWORD *)(a1 + 1020) = 30;
      else
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v40);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
      if ( v74 )
      {
        LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 1048));
        v74 = 0;
      }
      if ( v12 < 0 )
        CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
    }
    else
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v39);
    }
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
    if ( v12 < 0 )
    {
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 820;
      goto LABEL_245;
    }
    if ( v10 )
    {
      v41 = v10;
      v10 = 0;
      SH<unsigned short *,SH_SSTRING>::Attach((__int64 *)(a1 + 224), v41);
    }
    if ( v11 )
    {
      v42 = v11;
      v11 = 0;
      SH<unsigned short *,SH_SSTRING>::Attach((__int64 *)(a1 + 216), v42);
    }
    v43 = CreateEventW(0, 0, 0, 0);
    v44 = *(void **)(a1 + 256);
    if ( v44 )
      CloseHandle(v44);
    if ( v43 )
    {
      *(_QWORD *)(a1 + 256) = v43;
      v46 = CreateEventW(0, 0, 0, 0);
      v47 = *(void **)(a1 + 264);
      if ( v47 )
        CloseHandle(v47);
      if ( v46 )
      {
        *(_QWORD *)(a1 + 264) = v46;
        v49 = CreateEventW(0, 1, 0, 0);
        v50 = *(void **)(a1 + 272);
        if ( v50 )
          CloseHandle(v50);
        if ( v49 )
        {
          *(_QWORD *)(a1 + 272) = v49;
          *(_QWORD *)(a1 + 1328) = a1;
          *(_QWORD *)(a1 + 1352) = a1 + 392;
          *(_QWORD *)(a1 + 1360) = a1 + 536;
          v52 = *(_QWORD *)(a1 + 256);
          if ( !v52 )
            v52 = 0;
          *(_QWORD *)(a1 + 1336) = v52;
          *(_QWORD *)(a1 + 1344) = v49;
          Thread = CreateThread(0, 0, CDlpTask::TaskOperationThreadProc, (LPVOID)(a1 + 1328), 0, 0);
          v54 = *(void **)(a1 + 280);
          if ( v54 )
            CloseHandle(v54);
          if ( Thread )
          {
            *(_QWORD *)(a1 + 280) = Thread;
            *(_QWORD *)(a1 + 1368) = a1;
            *(_QWORD *)(a1 + 1392) = a1 + 408;
            *(_QWORD *)(a1 + 1400) = a1 + 592;
            v56 = *(_QWORD *)(a1 + 264);
            if ( !v56 )
              v56 = 0;
            *(_QWORD *)(a1 + 1376) = v56;
            v57 = *(_QWORD *)(a1 + 272);
            if ( !v57 )
              v57 = 0;
            *(_QWORD *)(a1 + 1384) = v57;
            v58 = CreateThread(0, 0, CDlpTask::TaskOperationThreadProc, (LPVOID)(a1 + 1368), 0, 0);
            v59 = *(void **)(a1 + 288);
            if ( v59 )
              CloseHandle(v59);
            if ( v58 )
            {
              *(_QWORD *)(a1 + 288) = v58;
              v61 = CDlpState::Set(a1 + 296, a5);
              v12 = v61;
              if ( v61 < 0 )
                CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v61);
              CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
              if ( v12 >= 0 || !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
                goto LABEL_248;
              v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
              v14 = 0;
              if ( !v13 )
                goto LABEL_247;
              LODWORD(lpThreadId) = v12;
              LODWORD(dwCreationFlags) = 876;
            }
            else
            {
              *(_QWORD *)(a1 + 288) = 0;
              v60 = GetLastError();
              v12 = v60;
              if ( v60 )
              {
                if ( v60 > 0 )
                  v12 = (unsigned __int16)v60 | 0x80070000;
              }
              else
              {
                v12 = -2147467259;
              }
              if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
                goto LABEL_248;
              v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
              v14 = 0;
              if ( v12 >= 0 || !v13 )
                goto LABEL_247;
              LODWORD(lpThreadId) = v12;
              LODWORD(dwCreationFlags) = 872;
            }
          }
          else
          {
            *(_QWORD *)(a1 + 280) = 0;
            v55 = GetLastError();
            v12 = v55;
            if ( v55 )
            {
              if ( v55 > 0 )
                v12 = (unsigned __int16)v55 | 0x80070000;
            }
            else
            {
              v12 = -2147467259;
            }
            if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
              goto LABEL_248;
            v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
            v14 = 0;
            if ( v12 >= 0 || !v13 )
              goto LABEL_247;
            LODWORD(lpThreadId) = v12;
            LODWORD(dwCreationFlags) = 858;
          }
        }
        else
        {
          *(_QWORD *)(a1 + 272) = 0;
          v51 = GetLastError();
          v12 = v51;
          if ( v51 )
          {
            if ( v51 > 0 )
              v12 = (unsigned __int16)v51 | 0x80070000;
          }
          else
          {
            v12 = -2147467259;
          }
          if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
            goto LABEL_248;
          v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
          v14 = 0;
          if ( v12 >= 0 || !v13 )
            goto LABEL_247;
          LODWORD(lpThreadId) = v12;
          LODWORD(dwCreationFlags) = 842;
        }
      }
      else
      {
        *(_QWORD *)(a1 + 264) = 0;
        v48 = GetLastError();
        v12 = v48;
        if ( v48 )
        {
          if ( v48 > 0 )
            v12 = (unsigned __int16)v48 | 0x80070000;
        }
        else
        {
          v12 = -2147467259;
        }
        if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
          goto LABEL_248;
        v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
        v14 = 0;
        if ( v12 >= 0 || !v13 )
          goto LABEL_247;
        LODWORD(lpThreadId) = v12;
        LODWORD(dwCreationFlags) = 839;
      }
    }
    else
    {
      *(_QWORD *)(a1 + 256) = 0;
      v45 = GetLastError();
      v12 = v45;
      if ( v45 )
      {
        if ( v45 > 0 )
          v12 = (unsigned __int16)v45 | 0x80070000;
      }
      else
      {
        v12 = -2147467259;
      }
      if ( !(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
        goto LABEL_248;
      v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
      v14 = 0;
      if ( v12 >= 0 || !v13 )
        goto LABEL_247;
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 836;
    }
LABEL_245:
    v62 = CDlpLogT<CEmptyType>::DlpLogFormat(
            v13,
            4,
            L"%s(%d): Result = 0x%X",
            L"CDlpTask::Initialize",
            dwCreationFlags,
            lpThreadId);
    v14 = v62;
    if ( v62 < 0 )
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v62);
    goto LABEL_247;
  }
  *(_QWORD *)(a1 + 232) = 0;
  v17 = GetLastError();
  v12 = v17;
  if ( v17 )
  {
    if ( v17 > 0 )
      v12 = (unsigned __int16)v17 | 0x80070000;
  }
  else
  {
    v12 = -2147467259;
  }
  if ( (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176) )
  {
    v13 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)(a1 + 176) + 16LL))(a1 + 176);
    v14 = 0;
    if ( v12 < 0 && v13 )
    {
      LODWORD(lpThreadId) = v12;
      LODWORD(dwCreationFlags) = 736;
      goto LABEL_245;
    }
LABEL_247:
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v14);
  }
LABEL_248:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v12);
  if ( v11 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v11 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v10 )
  {
    v64 = GetProcessHeap();
    HeapFree(v64, 0, (LPVOID)(v10 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v71 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v71 + 16LL))(v71);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140041e6c  push    rbp
0x140041e6e  push    rbx
0x140041e6f  push    rsi
0x140041e70  push    rdi
0x140041e71  push    r12
0x140041e73  push    r13
0x140041e75  push    r14
0x140041e77  push    r15
0x140041e79  lea     rbp, [rsp-7C8h]
0x140041e81  sub     rsp, 8C8h
0x140041e88  mov     [rbp+800h+var_880], 0FFFFFFFFFFFFFFFEh
0x140041e90  mov     rax, cs:__security_cookie
0x140041e97  xor     rax, rsp
0x140041e9a  mov     [rbp+800h+var_50], rax
0x140041ea1  mov     r15, r9
0x140041ea4  mov     r12, r8
0x140041ea7  mov     r13, rdx
0x140041eaa  mov     r14, rcx
0x140041ead  xor     eax, eax
0x140041eaf  mov     [rsp+900h+var_8B8], rax
0x140041eb4  mov     esi, eax
0x140041eb6  mov     [rsp+900h+var_8C0], rax
0x140041ebb  mov     edi, eax
0x140041ebd  mov     [rsp+900h+var_8C8], rax
0x140041ec2  mov     [rsp+900h+var_8D0], eax
0x140041ec6  mov     [rsp+900h+FilePart], rax
0x140041ecb  add     rcx, 128h; this
0x140041ed2  lea     rdx, [rsp+900h+var_8D0]; enum WINDLP_STATE *
0x140041ed7  call    ?Get@CDlpState@@QEAAJPEAW4WINDLP_STATE@@@Z; CDlpState::Get(WINDLP_STATE *)
0x140041edc  mov     ebx, eax
0x140041ede  test    eax, eax
0x140041ee0  jns     short loc_140041F39
0x140041ee2  mov     rdx, [r14+0B0h]
0x140041ee9  lea     rcx, [r14+0B0h]
0x140041ef0  mov     rax, [rdx+10h]
0x140041ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041ef9  xor     r12d, r12d
0x140041efc  test    rax, rax
0x140041eff  jz      loc_140043333
0x140041f05  mov     rax, [r14+0B0h]
0x140041f0c  lea     rcx, [r14+0B0h]
0x140041f13  mov     rax, [rax+10h]
0x140041f17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041f1c  mov     r14d, r12d
0x140041f1f  test    rax, rax
0x140041f22  jz      loc_14004332B
0x140041f28  mov     dword ptr [rsp+900h+lpThreadId], ebx
0x140041f2c  mov     dword ptr [rsp+900h+dwCreationFlags], 2D2h
0x140041f34  jmp     loc_140043302
0x140041f39  cmp     [rsp+900h+var_8D0], 0FEBEFEBEh
0x140041f41  jz      short loc_140041F9F
0x140041f43  mov     ebx, 800704DFh
0x140041f48  mov     rax, [r14+0B0h]
0x140041f4f  lea     rcx, [r14+0B0h]
0x140041f56  mov     rax, [rax+10h]
0x140041f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041f5f  xor     r12d, r12d
0x140041f62  test    rax, rax
0x140041f65  jz      loc_140043333
0x140041f6b  mov     rax, [r14+0B0h]
0x140041f72  lea     rcx, [r14+0B0h]
0x140041f79  mov     rax, [rax+10h]
0x140041f7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140041f82  mov     r14d, r12d
0x140041f85  test    rax, rax
0x140041f88  jz      loc_14004332B
0x140041f8e  mov     dword ptr [rsp+900h+lpThreadId], ebx
0x140041f92  mov     dword ptr [rsp+900h+dwCreationFlags], 2D3h
0x140041f9a  jmp     loc_140043302
0x140041f9f  mov     dword ptr [r14+598h], 7530h
0x140041faa  mov     eax, 3E8h
0x140041faf  mov     [r14+59Ch], eax
0x140041fb6  mov     [r14+5A0h], eax
0x140041fbd  xor     r9d, r9d; lpName
0x140041fc0  xor     r8d, r8d; bInitialState
0x140041fc3  lea     edx, [r9+1]; bManualReset
0x140041fc7  xor     ecx, ecx; lpEventAttributes
0x140041fc9  call    cs:__imp_CreateEventW
0x140041fd0  nop     dword ptr [rax+rax+00h]
0x140041fd5  mov     rbx, rax
0x140041fd8  mov     rcx, [r14+0E8h]; hObject
0x140041fdf  test    rcx, rcx
0x140041fe2  jz      short loc_140041FF0
0x140041fe4  call    cs:__imp_CloseHandle
0x140041feb  nop     dword ptr [rax+rax+00h]
0x140041ff0  test    rbx, rbx
0x140041ff3  jnz     loc_140042083
0x140041ff9  xor     r12d, r12d
0x140041ffc  mov     [r14+0E8h], r12
0x140042003  call    cs:__imp_GetLastError
0x14004200a  nop     dword ptr [rax+rax+00h]
0x14004200f  mov     ebx, eax
0x140042011  test    eax, eax
0x140042013  jnz     short loc_14004201C
0x140042015  mov     ebx, 80004005h
0x14004201a  jmp     short loc_140042027
0x14004201c  jle     short loc_140042027
0x14004201e  movzx   ebx, ax
0x140042021  or      ebx, 80070000h
0x140042027  mov     rax, [r14+0B0h]
0x14004202e  lea     rcx, [r14+0B0h]
0x140042035  mov     rax, [rax+10h]
0x140042039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004203e  test    rax, rax
0x140042041  jz      loc_140043333
0x140042047  mov     rax, [r14+0B0h]
0x14004204e  lea     rcx, [r14+0B0h]
0x140042055  mov     rax, [rax+10h]
0x140042059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004205e  mov     r14d, r12d
0x140042061  test    ebx, ebx
0x140042063  jns     loc_14004332B
0x140042069  test    rax, rax
0x14004206c  jz      loc_14004332B
0x140042072  mov     dword ptr [rsp+900h+lpThreadId], ebx
0x140042076  mov     dword ptr [rsp+900h+dwCreationFlags], 2E0h
0x14004207e  jmp     loc_140043302
0x140042083  mov     [r14+0E8h], rbx
0x14004208a  xor     r9d, r9d; lpName
0x14004208d  xor     r8d, r8d; bInitialState
0x140042090  xor     edx, edx; bManualReset
0x140042092  xor     ecx, ecx; lpEventAttributes
0x140042094  call    cs:__imp_CreateEventW
0x14004209b  nop     dword ptr [rax+rax+00h]
0x1400420a0  mov     rbx, rax
0x1400420a3  mov     rcx, [r14+0F0h]; hObject
0x1400420aa  test    rcx, rcx
0x1400420ad  jz      short loc_1400420BB
0x1400420af  call    cs:__imp_CloseHandle
0x1400420b6  nop     dword ptr [rax+rax+00h]
0x1400420bb  test    rbx, rbx
0x1400420be  jnz     loc_14004214E
0x1400420c4  xor     r12d, r12d
0x1400420c7  mov     [r14+0F0h], r12
0x1400420ce  call    cs:__imp_GetLastError
0x1400420d5  nop     dword ptr [rax+rax+00h]
0x1400420da  mov     ebx, eax
0x1400420dc  test    eax, eax
0x1400420de  jnz     short loc_1400420E7
0x1400420e0  mov     ebx, 80004005h
0x1400420e5  jmp     short loc_1400420F2
0x1400420e7  jle     short loc_1400420F2
0x1400420e9  movzx   ebx, ax
0x1400420ec  or      ebx, 80070000h
0x1400420f2  mov     rax, [r14+0B0h]
0x1400420f9  lea     rcx, [r14+0B0h]
0x140042100  mov     rax, [rax+10h]
0x140042104  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042109  test    rax, rax
0x14004210c  jz      loc_140043333
0x140042112  mov     rax, [r14+0B0h]
0x140042119  lea     rcx, [r14+0B0h]
0x140042120  mov     rax, [rax+10h]
0x140042124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042129  mov     r14d, r12d
0x14004212c  test    ebx, ebx
0x14004212e  jns     loc_14004332B
0x140042134  test    rax, rax
0x140042137  jz      loc_14004332B
0x14004213d  mov     dword ptr [rsp+900h+lpThreadId], ebx
0x140042141  mov     dword ptr [rsp+900h+dwCreationFlags], 2E3h
0x140042149  jmp     loc_140043302
0x14004214e  mov     [r14+0F0h], rbx
0x140042155  xor     r9d, r9d; lpName
0x140042158  xor     r8d, r8d; bInitialState
0x14004215b  xor     edx, edx; bManualReset
0x14004215d  xor     ecx, ecx; lpEventAttributes
0x14004215f  call    cs:__imp_CreateEventW
0x140042166  nop     dword ptr [rax+rax+00h]
0x14004216b  mov     rbx, rax
0x14004216e  mov     rcx, [r14+0F8h]; hObject
0x140042175  test    rcx, rcx
0x140042178  jz      short loc_140042186
0x14004217a  call    cs:__imp_CloseHandle
0x140042181  nop     dword ptr [rax+rax+00h]
0x140042186  test    rbx, rbx
0x140042189  jnz     loc_140042219
0x14004218f  xor     r12d, r12d
0x140042192  mov     [r14+0F8h], r12
0x140042199  call    cs:__imp_GetLastError
0x1400421a0  nop     dword ptr [rax+rax+00h]
0x1400421a5  mov     ebx, eax
0x1400421a7  test    eax, eax
0x1400421a9  jnz     short loc_1400421B2
0x1400421ab  mov     ebx, 80004005h
0x1400421b0  jmp     short loc_1400421BD
0x1400421b2  jle     short loc_1400421BD
0x1400421b4  movzx   ebx, ax
0x1400421b7  or      ebx, 80070000h
0x1400421bd  mov     rax, [r14+0B0h]
0x1400421c4  lea     rcx, [r14+0B0h]
0x1400421cb  mov     rax, [rax+10h]
0x1400421cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400421d4  test    rax, rax
0x1400421d7  jz      loc_140043333
0x1400421dd  mov     rax, [r14+0B0h]
0x1400421e4  lea     rcx, [r14+0B0h]
0x1400421eb  mov     rax, [rax+10h]
0x1400421ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400421f4  mov     r14d, r12d
0x1400421f7  test    ebx, ebx
0x1400421f9  jns     loc_14004332B
0x1400421ff  test    rax, rax
0x140042202  jz      loc_14004332B
0x140042208  mov     dword ptr [rsp+900h+lpThreadId], ebx
0x14004220c  mov     dword ptr [rsp+900h+dwCreationFlags], 2E6h
0x140042214  jmp     loc_140043302
0x140042219  mov     [r14+0F8h], rbx
0x140042220  mov     r8d, 10h; Size
0x140042226  mov     rdx, r13; Buf2
0x140042229  lea     rcx, WINDLP_TRANSPORT_NONE; Buf1
0x140042230  call    memcmp_0
0x140042235  test    eax, eax
0x140042237  jz      loc_1400423AC
0x14004223d  mov     rcx, [r14+518h]
0x140042244  movaps  xmm0, xmmword ptr [r13+0]
0x140042249  movdqa  [rsp+900h+var_8A0], xmm0
0x14004224f  mov     rax, [rcx]
0x140042252  lea     r8, [rsp+900h+var_8B8]
0x140042257  lea     rdx, [rsp+900h+var_8A0]
0x14004225c  mov     rax, [rax+50h]
0x140042260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042265  mov     ebx, eax
0x140042267  test    eax, eax
0x140042269  jns     short loc_1400422C2
0x14004226b  mov     rax, [r14+0B0h]
0x140042272  lea     rcx, [r14+0B0h]
0x140042279  mov     rax, [rax+10h]
0x14004227d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140042282  xor     r12d, r12d
0x140042285  test    rax, rax
0x140042288  jz      loc_140043333
0x14004228e  mov     rax, [r14+0B0h]
0x140042295  lea     rcx, [r14+0B0h]
0x14004229c  mov     rax, [rax+10h]
0x1400422a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400422a5  mov     r14d, r12d
0x1400422a8  test    rax, rax
0x1400422ab  jz      loc_14004332B
0x1400422b1  mov     dword ptr [rsp+900h+lpThreadId], ebx
0x1400422b5  mov     dword ptr [rsp+900h+dwCreationFlags], 2EDh
0x1400422bd  jmp     loc_140043302
0x1400422c2  lea     rdx, [r14+5D0h]
0x1400422c9  mov     rcx, [rsp+900h+var_8B8]
0x1400422ce  mov     rax, [rcx]
0x1400422d1  mov     rax, [rax+38h]
0x1400422d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400422da  mov     ebx, eax
0x1400422dc  test    eax, eax
0x1400422de  jns     short loc_140042337
0x1400422e0  mov     rax, [r14+0B0h]
0x1400422e7  lea     rcx, [r14+0B0h]
0x1400422ee  mov     rax, [rax+10h]
0x1400422f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400422f7  xor     r12d, r12d
0x1400422fa  test    rax, rax
0x1400422fd  jz      loc_140043333
0x140042303  mov     rax, [r14+0B0h]
0x14004230a  lea     rcx, [r14+0B0h]
0x140042311  mov     rax, [rax+10h]
0x140042315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004231a  mov     r14d, r12d
0x14004231d  test    rax, rax
0x140042320  jz      loc_14004332B
0x140042326  mov     dword ptr [rsp+900h+lpThreadId], ebx
0x14004232a  mov     dword ptr [rsp+900h+dwCreationFlags], 2F1h
0x140042332  jmp     loc_140043302
0x140042337  lea     rdx, [r14+594h]
0x14004233e  mov     rcx, [rsp+900h+var_8B8]
0x140042343  mov     rax, [rcx]
0x140042346  mov     rax, [rax+40h]
0x14004234a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004234f  mov     ebx, eax
0x140042351  test    eax, eax
0x140042353  jns     short loc_1400423AC
0x140042355  mov     rax, [r14+0B0h]
0x14004235c  lea     rcx, [r14+0B0h]
0x140042363  mov     rax, [rax+10h]
0x140042367  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004236c  xor     r12d, r12d
0x14004236f  test    rax, rax
0x140042372  jz      loc_140043333
0x140042378  mov     rax, [r14+0B0h]
0x14004237f  lea     rcx, [r14+0B0h]
0x140042386  mov     rax, [rax+10h]
0x14004238a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004238f  mov     r14d, r12d
0x140042392  test    rax, rax
0x140042395  jz      loc_14004332B
0x14004239b  mov     dword ptr [rsp+900h+lpThreadId], ebx
0x14004239f  mov     dword ptr [rsp+900h+dwCreationFlags], 2F5h
0x1400423a7  jmp     loc_140043302
0x1400423ac  test    r12, r12
0x1400423af  jz      loc_140042454
0x1400423b5  lea     rdx, [rsp+900h+var_8C0]
0x1400423ba  mov     rcx, r12; Src
0x1400423bd  call    ?Create@?$CImmutableStringsT@GVCImmutableStringsPolicyDefault@@@@SAJPEBGPEAPEAG@Z; CImmutableStringsT<ushort,CImmutableStringsPolicyDefault>::Create(ushort const *,ushort * *)
0x1400423c2  mov     ebx, eax
0x1400423c4  xor     r12d, r12d
0x1400423c7  test    eax, eax
  ... truncated ...
```
