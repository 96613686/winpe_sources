# WinSATInitiateAssessment

- ea: `0x18001cc8c`
- end: `0x18001d2fb`
- name: `WinSATInitiateAssessment`
- size: `1647`
- prototype: ``
- caller_count: `1`
- callee_count: `22`
- tags: `authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x18001e270`

## callees

- `0x1800020f4`
- `0x180003640`
- `0x180008490`
- `0x1800084f0`
- `0x18000e124`
- `0x180011600`
- `0x180013e69`
- `0x18001bd74`
- `0x18001be2c`
- `0x18001bed0`
- `0x18001bf2c`
- `0x18001bf9c`
- `0x18001c09c`
- `0x18001c0f4`
- `0x18001c41c`
- `0x18001c46c`
- `0x18001c854`
- `0x18001c900`
- `0x18001c94c`
- `0x18001c9a4`
- `0x18001cb6c`
- `0x18001cc8c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cf43`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001cf43`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d0df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf60`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d0df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d1e9`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001d0c7`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18001d0c7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001d200`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x18001d200`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001d2bf`
- `api-ms-win-core-processthreads-l1-1-0!ResumeThread` at `0x18001d2bf`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18001d14f`
- `api-ms-win-core-wow64-l1-1-0!Wow64DisableWow64FsRedirection` at `0x18001d14f`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18001d263`
- `api-ms-win-core-wow64-l1-1-0!Wow64RevertWow64FsRedirection` at `0x18001d263`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001d071`
- `api-ms-win-core-util-l1-1-0!EncodePointer` at `0x18001d071`
- `USER32!IsWindow` at `0x18001cd2b`
- `USER32!IsWindow` at `0x18001cd2b`
- `SHELL32!ShellExecuteExW` at `0x18001d1d9`
- `SHELL32!ShellExecuteExW` at `0x18001d1d9`

## string_xrefs

- `0x18001ce46`: `signaloncompletion`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall WinSATInitiateAssessment(__int64 a1, __int64 a2, __int64 a3, __int64 a4, HWND *a5, HWND a6)
{
  __int64 result; // rax
  unsigned __int64 v9; // rax
  HWND *v10; // rdi
  char has_switch_word; // si
  signed int TheCancelEvent; // ebx
  __int64 v13; // rcx
  bool v14; // bl
  int v15; // ebx
  signed int LastError; // eax
  unsigned int v17; // ebx
  signed int v18; // ebx
  ULONG v19; // eax
  __int64 v20; // [rsp+30h] [rbp-E8h] BYREF
  __int64 v21; // [rsp+38h] [rbp-E0h] BYREF
  __int64 v22; // [rsp+40h] [rbp-D8h] BYREF
  __int64 v23; // [rsp+48h] [rbp-D0h] BYREF
  PVOID OldValue; // [rsp+50h] [rbp-C8h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+58h] [rbp-C0h] BYREF
  __int64 v26; // [rsp+70h] [rbp-A8h] BYREF
  __int64 v27; // [rsp+78h] [rbp-A0h] BYREF
  _BYTE v28[8]; // [rsp+80h] [rbp-98h] BYREF
  __int64 v29; // [rsp+88h] [rbp-90h]
  SHELLEXECUTEINFOW pExecInfo; // [rsp+90h] [rbp-88h] BYREF
  __int64 v31; // [rsp+130h] [rbp+18h] BYREF

  v31 = a3;
  v29 = -2;
  if ( g_InitCount <= 0 )
    return 2147745793LL;
  if ( g_RunState == 1 )
    return 2147745849LL;
  if ( g_RunState == 2 )
    WinSATGetCompletionStatus();
  result = ProbeString(a1);
  if ( (int)result >= 0 )
  {
    try
    {
      v9 = mlib::m_traits<unsigned short>::CStrlen(a1, 0x10000);
    }
    catch ( mlib::CStringTooBig )
    {
      return 2147745802LL;
    }
    try
    {
      if ( v9 > 0x3800 )
        return 2147745802LL;
      v10 = a5;
      if ( *a5 && !IsWindow(*a5) )
        return 2147745804LL;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v31,
        a1);
      v26 = 0;
      has_switch_word = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                          &v31,
                          L"showconwin",
                          &v26);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v20,
        260);
      GetSystemDirectoryInMString((__int64)&v20);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::ensure_trailing_slash(&v20);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
        &v20,
        L"winsat.exe");
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v22,
        128);
      TheCancelEvent = CreateTheCancelEvent(&qword_18004FF78, (__int64)&v22);
      if ( TheCancelEvent < 0 )
      {
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v22);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v20);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
        return (unsigned int)TheCancelEvent;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v21,
        128);
      v13 = mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::first_token(
              &v31,
              v28);
      v14 = 0;
      if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::eqi(v13) )
      {
        v27 = 0;
        if ( !(unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::has_switch_word(
                                 &v31,
                                 L"signaloncompletion",
                                 &v27) )
          v14 = 1;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(v28);
      if ( v14 )
      {
        if ( (unsigned int)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::UuidCreate(&v21) )
        {
          ResetGlobalState();
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v21);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v22);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v20);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
          return 2147942408LL;
        }
        *(&EventAttributes.nLength + 1) = 0;
        *(&EventAttributes.bInheritHandle + 1) = 0;
        EventAttributes.nLength = 24;
        EventAttributes.lpSecurityDescriptor = 0;
        EventAttributes.bInheritHandle = 1;
        v15 = SetAdminRights(&EventAttributes);
        if ( v15 < 0 )
        {
          ResetGlobalState();
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v21);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v22);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v20);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
          return (unsigned int)v15;
        }
        qword_18004FF90 = CreateEventW(&EventAttributes, 0, 0, *(LPCWSTR *)(v21 + 24));
        if ( !qword_18004FF90 )
        {
          ResetGlobalState();
          LastError = GetLastError();
          v17 = LastError;
          if ( LastError > 0 )
            v17 = (unsigned __int16)LastError | 0x80070000;
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v21);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v22);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v20);
          mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
          return v17;
        }
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>(
        &v23,
        1024);
      if ( (unsigned __int8)mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::is_blank(&v31) )
      {
        ResetGlobalState();
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v23);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v21);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v22);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v20);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
        return 2147745801LL;
      }
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::append(
        &v23,
        &v31);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spfa(
        &v23,
        L" -cancelevent %s",
        *(_QWORD *)(v22 + 24));
      if ( qword_18004FF90 )
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::spfa(
          &v23,
          L" -moobegoevent %s",
          *(_QWORD *)(v21 + 24));
      Ptr = EncodePointer(CInitiateWinSAT::WinSATCompletionRoutine);
      qword_18004FF68 = a4;
      *(_OWORD *)&hWnd = *(_OWORD *)v10;
      *(_OWORD *)&wParam = *((_OWORD *)v10 + 1);
      xmmword_18004FFC8 = *((_OWORD *)v10 + 2);
      hThread = CreateThread(0, 0, WinSATWaitngThread, 0, 4u, 0);
      if ( !hThread )
      {
        v18 = GetLastError();
        ResetGlobalState();
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
LABEL_36:
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v23);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v21);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v22);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v20);
        mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
        return (unsigned int)v18;
      }
      CreateStatusObjects();
      OldValue = 0;
      Wow64DisableWow64FsRedirection(&OldValue);
      memset_0(&pExecInfo, 0, sizeof(pExecInfo));
      pExecInfo.cbSize = 112;
      v19 = 17472;
      if ( !has_switch_word )
        v19 = 50240;
      pExecInfo.fMask = v19;
      pExecInfo.hwnd = a6;
      pExecInfo.lpVerb = L"open";
      pExecInfo.lpFile = *(LPCWSTR *)(v20 + 24);
      pExecInfo.lpParameters = *(LPCWSTR *)(v23 + 24);
      if ( !ShellExecuteExW(&pExecInfo) )
      {
        v18 = GetLastError();
        TerminateThread(hThread, 0);
        ResetGlobalState();
        if ( v18 > 0 )
          v18 = (unsigned __int16)v18 | 0x80070000;
        goto LABEL_36;
      }
      Wow64RevertWow64FsRedirection(OldValue);
      g_WinSATProcessInfo = pExecInfo.hProcess;
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v23);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v21);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v22);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v20);
      mlib::fundamental_string<unsigned short,mlib::m_traits<unsigned short>,std::allocator<unsigned short>>::detach_buf(&v31);
      ResumeThread(hThread);
      _InterlockedExchange(&g_RunState, 1);
      result = 0;
    }
    catch ( ... )
    {
      if ( hThread )
        TerminateThread(hThread, 0);
      ResetGlobalState();
      return 2147942408LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18001cc8c  mov     rax, rsp
0x18001cc8f  mov     [rax+18h], r8
0x18001cc93  mov     [rax+10h], edx
0x18001cc96  push    rsi
0x18001cc97  push    rdi
0x18001cc98  push    r14
0x18001cc9a  sub     rsp, 100h
0x18001cca1  mov     qword ptr [rax-90h], 0FFFFFFFFFFFFFFFEh
0x18001ccac  mov     [rax+8], rbx
0x18001ccb0  mov     r14, r9
0x18001ccb3  mov     rbx, rcx
0x18001ccb6  and     dword ptr [rax+10h], 0
0x18001ccba  cmp     cs:?g_InitCount@@3JA, 0; long g_InitCount
0x18001ccc1  jg      short loc_18001CCCD
0x18001ccc3  mov     eax, 80040001h
0x18001ccc8  jmp     loc_18001D2E6
0x18001cccd  mov     eax, cs:?g_RunState@@3JA; long g_RunState
0x18001ccd3  cmp     eax, 1
0x18001ccd6  jnz     short loc_18001CCE2
0x18001ccd8  mov     eax, 80040039h
0x18001ccdd  jmp     loc_18001D2E6
0x18001cce2  cmp     eax, 2
0x18001cce5  jnz     short loc_18001CCEC
0x18001cce7  call    WinSATGetCompletionStatus
0x18001ccec  mov     rcx, rbx
0x18001ccef  call    ProbeString
0x18001ccf4  test    eax, eax
0x18001ccf6  js      loc_18001D2E6
0x18001ccfc  mov     edx, 10000h
0x18001cd01  mov     rcx, rbx
0x18001cd04  call    ?CStrlen@?$m_traits@G@mlib@@SA_KPEBG_K@Z; mlib::m_traits<ushort>::CStrlen(ushort const *,unsigned __int64)
0x18001cd09  cmp     rax, 3800h
0x18001cd0f  jbe     short loc_18001CD1B
0x18001cd11  mov     eax, 8004000Ah
0x18001cd16  jmp     loc_18001D2E6
0x18001cd1b  mov     rdi, [rsp+118h+arg_20]
0x18001cd23  mov     rcx, [rdi]; hWnd
0x18001cd26  test    rcx, rcx
0x18001cd29  jz      short loc_18001CD45
0x18001cd2b  call    cs:__imp_IsWindow
0x18001cd32  nop     dword ptr [rax+rax+00h]
0x18001cd37  test    eax, eax
0x18001cd39  jnz     short loc_18001CD45
0x18001cd3b  mov     eax, 8004000Ch
0x18001cd40  jmp     loc_18001D2E6
0x18001cd45  mov     rdx, rbx
0x18001cd48  lea     rcx, [rsp+118h+arg_10]
0x18001cd50  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(ushort const *)
0x18001cd55  nop
0x18001cd56  and     [rsp+118h+var_A8], 0
0x18001cd5c  lea     r8, [rsp+118h+var_A8]
0x18001cd61  lea     rdx, aShowconwin; "showconwin"
0x18001cd68  lea     rcx, [rsp+118h+arg_10]
0x18001cd70  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x18001cd75  mov     sil, al
0x18001cd78  mov     edx, 104h
0x18001cd7d  lea     rcx, [rsp+118h+var_E8]
0x18001cd82  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18001cd87  nop
0x18001cd88  lea     rcx, [rsp+118h+var_E8]
0x18001cd8d  call    ?GetSystemDirectoryInMString@@YAJAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; GetSystemDirectoryInMString(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x18001cd92  lea     rcx, [rsp+118h+var_E8]
0x18001cd97  call    ?ensure_trailing_slash@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::ensure_trailing_slash(void)
0x18001cd9c  lea     rdx, aWinsatExe; "winsat.exe"
0x18001cda3  lea     rcx, [rsp+118h+var_E8]
0x18001cda8  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(ushort const *)
0x18001cdad  mov     edx, 80h
0x18001cdb2  lea     rcx, [rsp+118h+var_D8]
0x18001cdb7  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18001cdbc  nop
0x18001cdbd  lea     rdx, [rsp+118h+var_D8]
0x18001cdc2  lea     rcx, qword_18004FF78
0x18001cdc9  call    ?CreateTheCancelEvent@@YAJAEAPEAXAEAV?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@@Z; CreateTheCancelEvent(void * &,mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> &)
0x18001cdce  mov     ebx, eax
0x18001cdd0  test    eax, eax
0x18001cdd2  jns     short loc_18001CDFE
0x18001cdd4  lea     rcx, [rsp+118h+var_D8]
0x18001cdd9  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cdde  nop
0x18001cddf  lea     rcx, [rsp+118h+var_E8]
0x18001cde4  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cde9  nop
0x18001cdea  lea     rcx, [rsp+118h+arg_10]
0x18001cdf2  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cdf7  mov     eax, ebx
0x18001cdf9  jmp     loc_18001D2E6
0x18001cdfe  mov     edx, 80h
0x18001ce03  lea     rcx, [rsp+118h+var_E0]
0x18001ce08  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18001ce0d  nop
0x18001ce0e  lea     rdx, [rsp+118h+var_98]
0x18001ce16  lea     rcx, [rsp+118h+arg_10]
0x18001ce1e  call    ?first_token@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA?AV12@PEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::first_token(ushort const *)
0x18001ce23  nop
0x18001ce24  mov     [rsp+118h+arg_8], 1
0x18001ce2f  mov     rcx, rax
0x18001ce32  call    ?eqi@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NPEBG@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::eqi(ushort const *)
0x18001ce37  test    al, al
0x18001ce39  jz      short loc_18001CE62
0x18001ce3b  and     [rsp+118h+var_A0], 0
0x18001ce41  lea     r8, [rsp+118h+var_A0]
0x18001ce46  lea     rdx, aSignaloncomple; "signaloncompletion"
0x18001ce4d  lea     rcx, [rsp+118h+arg_10]
0x18001ce55  call    ?has_switch_word@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA_NPEBGAEA_K_N@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::has_switch_word(ushort const *,unsigned __int64 &,bool)
0x18001ce5a  test    al, al
0x18001ce5c  jnz     short loc_18001CE62
0x18001ce5e  mov     bl, 1
0x18001ce60  jmp     short loc_18001CE64
0x18001ce62  xor     bl, bl
0x18001ce64  lea     rcx, [rsp+118h+var_98]
0x18001ce6c  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001ce71  test    bl, bl
0x18001ce73  jz      loc_18001CFB0
0x18001ce79  lea     rcx, [rsp+118h+var_E0]
0x18001ce7e  call    ?UuidCreate@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAJXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::UuidCreate(void)
0x18001ce83  test    eax, eax
0x18001ce85  jz      short loc_18001CEC5
0x18001ce87  call    ResetGlobalState
0x18001ce8c  nop
0x18001ce8d  lea     rcx, [rsp+118h+var_E0]
0x18001ce92  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001ce97  nop
0x18001ce98  lea     rcx, [rsp+118h+var_D8]
0x18001ce9d  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cea2  nop
0x18001cea3  lea     rcx, [rsp+118h+var_E8]
0x18001cea8  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cead  nop
0x18001ceae  lea     rcx, [rsp+118h+arg_10]
0x18001ceb6  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cebb  mov     eax, 80070008h
0x18001cec0  jmp     loc_18001D2E6
0x18001cec5  and     dword ptr [rsp+118h+EventAttributes+4], 0
0x18001ceca  and     dword ptr [rsp+118h+EventAttributes+14h], 0
0x18001cecf  mov     [rsp+118h+EventAttributes.nLength], 18h
0x18001ced7  and     [rsp+118h+EventAttributes.lpSecurityDescriptor], 0
0x18001cedd  mov     [rsp+118h+EventAttributes.bInheritHandle], 1
0x18001cee5  lea     rcx, [rsp+118h+EventAttributes]
0x18001ceea  call    SetAdminRights
0x18001ceef  mov     ebx, eax
0x18001cef1  test    eax, eax
0x18001cef3  jns     short loc_18001CF30
0x18001cef5  call    ResetGlobalState
0x18001cefa  nop
0x18001cefb  lea     rcx, [rsp+118h+var_E0]
0x18001cf00  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cf05  nop
0x18001cf06  lea     rcx, [rsp+118h+var_D8]
0x18001cf0b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cf10  nop
0x18001cf11  lea     rcx, [rsp+118h+var_E8]
0x18001cf16  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cf1b  nop
0x18001cf1c  lea     rcx, [rsp+118h+arg_10]
0x18001cf24  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cf29  mov     eax, ebx
0x18001cf2b  jmp     loc_18001D2E6
0x18001cf30  mov     rax, [rsp+118h+var_E0]
0x18001cf35  mov     r9, [rax+18h]; lpName
0x18001cf39  xor     r8d, r8d; bInitialState
0x18001cf3c  xor     edx, edx; bManualReset
0x18001cf3e  lea     rcx, [rsp+118h+EventAttributes]; lpEventAttributes
0x18001cf43  call    cs:__imp_CreateEventW
0x18001cf4a  nop     dword ptr [rax+rax+00h]
0x18001cf4f  mov     cs:qword_18004FF90, rax
0x18001cf56  test    rax, rax
0x18001cf59  jnz     short loc_18001CFB0
0x18001cf5b  call    ResetGlobalState
0x18001cf60  call    cs:__imp_GetLastError
0x18001cf67  nop     dword ptr [rax+rax+00h]
0x18001cf6c  mov     ebx, eax
0x18001cf6e  test    eax, eax
0x18001cf70  jle     short loc_18001CF7B
0x18001cf72  movzx   ebx, ax
0x18001cf75  or      ebx, 80070000h
0x18001cf7b  lea     rcx, [rsp+118h+var_E0]
0x18001cf80  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cf85  nop
0x18001cf86  lea     rcx, [rsp+118h+var_D8]
0x18001cf8b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cf90  nop
0x18001cf91  lea     rcx, [rsp+118h+var_E8]
0x18001cf96  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cf9b  nop
0x18001cf9c  lea     rcx, [rsp+118h+arg_10]
0x18001cfa4  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cfa9  mov     eax, ebx
0x18001cfab  jmp     loc_18001D2E6
0x18001cfb0  mov     edx, 400h
0x18001cfb5  lea     rcx, [rsp+118h+var_D0]
0x18001cfba  call    ??0?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAA@_K@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>(unsigned __int64)
0x18001cfbf  nop
0x18001cfc0  lea     rcx, [rsp+118h+arg_10]
0x18001cfc8  call    ?is_blank@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEBA_NXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::is_blank(void)
0x18001cfcd  test    al, al
0x18001cfcf  jz      short loc_18001D01A
0x18001cfd1  call    ResetGlobalState
0x18001cfd6  nop
0x18001cfd7  lea     rcx, [rsp+118h+var_D0]
0x18001cfdc  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cfe1  nop
0x18001cfe2  lea     rcx, [rsp+118h+var_E0]
0x18001cfe7  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cfec  nop
0x18001cfed  lea     rcx, [rsp+118h+var_D8]
0x18001cff2  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001cff7  nop
0x18001cff8  lea     rcx, [rsp+118h+var_E8]
0x18001cffd  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001d002  nop
0x18001d003  lea     rcx, [rsp+118h+arg_10]
0x18001d00b  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001d010  mov     eax, 80040009h
0x18001d015  jmp     loc_18001D2E6
0x18001d01a  lea     rdx, [rsp+118h+arg_10]
0x18001d022  lea     rcx, [rsp+118h+var_D0]
0x18001d027  call    ?append@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAAEAV12@AEBV12@@Z; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::append(mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>> const &)
0x18001d02c  mov     rax, [rsp+118h+var_D8]
0x18001d031  mov     r8, [rax+18h]
0x18001d035  lea     rdx, aCanceleventS; " -cancelevent %s"
0x18001d03c  lea     rcx, [rsp+118h+var_D0]
0x18001d041  call    ?spfa@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spfa(ushort const *,...)
0x18001d046  cmp     cs:qword_18004FF90, 0
0x18001d04e  jz      short loc_18001D06A
0x18001d050  mov     rax, [rsp+118h+var_E0]
0x18001d055  mov     r8, [rax+18h]
0x18001d059  lea     rdx, aMoobegoeventS; " -moobegoevent %s"
0x18001d060  lea     rcx, [rsp+118h+var_D0]
0x18001d065  call    ?spfa@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@QEAAXPEBGZZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::spfa(ushort const *,...)
0x18001d06a  lea     rcx, ?WinSATCompletionRoutine@CInitiateWinSAT@@CAXPEAX0@Z; Ptr
0x18001d071  call    cs:__imp_EncodePointer
0x18001d078  nop     dword ptr [rax+rax+00h]
0x18001d07d  mov     cs:Ptr, rax
0x18001d084  mov     cs:qword_18004FF68, r14
0x18001d08b  movaps  xmm0, xmmword ptr [rdi]
0x18001d08e  movups  cs:hWnd, xmm0
0x18001d095  movaps  xmm1, xmmword ptr [rdi+10h]
0x18001d099  movups  cs:wParam, xmm1
0x18001d0a0  movaps  xmm0, xmmword ptr [rdi+20h]
0x18001d0a4  movups  cs:xmmword_18004FFC8, xmm0
0x18001d0ab  and     [rsp+118h+var_F0], 0
0x18001d0b1  mov     [rsp+118h+dwCreationFlags], 4; dwCreationFlags
0x18001d0b9  xor     r9d, r9d; lpParameter
0x18001d0bc  lea     r8, WinSATWaitngThread; lpStartAddress
0x18001d0c3  xor     edx, edx; dwStackSize
0x18001d0c5  xor     ecx, ecx; lpThreadAttributes
0x18001d0c7  call    cs:__imp_CreateThread
0x18001d0ce  nop     dword ptr [rax+rax+00h]
0x18001d0d3  mov     cs:hThread, rax
0x18001d0da  test    rax, rax
0x18001d0dd  jnz     short loc_18001D13F
0x18001d0df  call    cs:__imp_GetLastError
0x18001d0e6  nop     dword ptr [rax+rax+00h]
0x18001d0eb  mov     ebx, eax
0x18001d0ed  call    ResetGlobalState
0x18001d0f2  test    ebx, ebx
0x18001d0f4  jle     short loc_18001D0FF
0x18001d0f6  movzx   ebx, bx
0x18001d0f9  or      ebx, 80070000h
0x18001d0ff  lea     rcx, [rsp+118h+var_D0]
0x18001d104  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001d109  nop
0x18001d10a  lea     rcx, [rsp+118h+var_E0]
0x18001d10f  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001d114  nop
0x18001d115  lea     rcx, [rsp+118h+var_D8]
0x18001d11a  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001d11f  nop
0x18001d120  lea     rcx, [rsp+118h+var_E8]
0x18001d125  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001d12a  nop
0x18001d12b  lea     rcx, [rsp+118h+arg_10]
0x18001d133  call    ?detach_buf@?$fundamental_string@GV?$m_traits@G@mlib@@V?$allocator@G@std@@@mlib@@IEAAXXZ; mlib::fundamental_string<ushort,mlib::m_traits<ushort>,std::allocator<ushort>>::detach_buf(void)
0x18001d138  mov     eax, ebx
0x18001d13a  jmp     loc_18001D2E6
0x18001d13f  call    CreateStatusObjects
0x18001d144  and     [rsp+118h+OldValue], 0
0x18001d14a  lea     rcx, [rsp+118h+OldValue]; OldValue
0x18001d14f  call    cs:__imp_Wow64DisableWow64FsRedirection
0x18001d156  nop     dword ptr [rax+rax+00h]
0x18001d15b  mov     ebx, 70h ; 'p'
0x18001d160  mov     r8d, ebx; Size
0x18001d163  xor     edx, edx; Val
0x18001d165  lea     rcx, [rsp+118h+pExecInfo]; void *
0x18001d16d  call    memset_0
0x18001d172  mov     [rsp+118h+pExecInfo.cbSize], ebx
0x18001d179  mov     eax, 4440h
0x18001d17e  mov     ecx, 0C440h
0x18001d183  test    sil, sil
0x18001d186  cmovz   eax, ecx
0x18001d189  mov     [rsp+118h+pExecInfo.fMask], eax
0x18001d190  mov     rax, [rsp+118h+arg_28]
0x18001d198  mov     [rsp+118h+pExecInfo.hwnd], rax
0x18001d1a0  lea     rax, aOpen; "open"
0x18001d1a7  mov     [rsp+118h+pExecInfo.lpVerb], rax
0x18001d1af  mov     rax, [rsp+118h+var_E8]
0x18001d1b4  mov     rcx, [rax+18h]
0x18001d1b8  mov     [rsp+118h+pExecInfo.lpFile], rcx
0x18001d1c0  mov     rax, [rsp+118h+var_D0]
0x18001d1c5  mov     rcx, [rax+18h]
  ... truncated ...
```
