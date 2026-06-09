# WatchDogThreadProc

- ea: `0x140043900`
- end: `0x140043c72`
- name: `WatchDogThreadProc`
- size: `882`
- prototype: `ULONG __stdcall(PVOID Parameter)`
- caller_count: `0`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140001abc`
- `0x140008654`
- `0x1400120ac`
- `0x14001a3cc`
- `0x14003ec14`
- `0x14003f8e0`
- `0x14003fa8c`
- `0x140043854`
- `0x140043900`
- `0x140043c78`
- `0x140043f14`
- `0x140113220`

## import_xrefs

- `KERNEL32!GetThreadPriority` at `0x140043928`
- `KERNEL32!GetThreadPriority` at `0x140043928`
- `KERNEL32!GetCurrentThread` at `0x14004391f`
- `KERNEL32!GetCurrentThread` at `0x14004391f`
- `KERNEL32!SetEvent` at `0x140043b93`
- `KERNEL32!SetEvent` at `0x140043b93`
- `KERNEL32!GetLastError` at `0x1400439f7`
- `KERNEL32!GetLastError` at `0x1400439f7`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1400439d4`
- `KERNEL32!WaitForMultipleObjectsEx` at `0x1400439d4`

## string_xrefs

- `0x140043931`: `WatchDogThreadProc Launched with priority %d`
- `0x1400439e3`: `Dying - Cannot wait in the watch dog thread`
- `0x140043a00`: `Cannot wait in the watch dog thread`
- `0x140043a5c`: `Dying - An unxpected timtout occurred in the watch dog thread`
- `0x140043a6e`: `An unxpected timtout occurred in the watch dog thread`
- `0x140043c08`: `Dying - An unknown handle was signaled in the watch dog thread`
- `0x140043c1c`: `An unknown handle was signaled in the watch dog thread`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall WatchDogThreadProc(PVOID Parameter)
{
  HANDLE CurrentThread; // rax
  int ThreadPriority; // eax
  unsigned __int64 v3; // rdi
  DWORD v4; // eax
  HANDLE v5; // rax
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 result; // rax
  char bAlertable; // [rsp+20h] [rbp-58h]
  HANDLE *lpHandles[2]; // [rsp+30h] [rbp-48h] BYREF
  __int64 v12; // [rsp+40h] [rbp-38h]
  int v13; // [rsp+48h] [rbp-30h]
  _BYTE v14[16]; // [rsp+50h] [rbp-28h] BYREF

  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  Log_Text_F("base\\winsat\\exe\\watchdog.cpp", 113, "WatchDogThreadProc Launched with priority %d", ThreadPriority);
  try
  {
    *(_OWORD *)lpHandles = 0;
    v12 = 0;
    v13 = -1;
    mlib::MWaitList::operator+=(lpHandles, hObject);
    mlib::MWaitList::operator+=(lpHandles, qword_1401C65F0);
    mlib::MWaitList::operator+=(lpHandles, hTimer);
    mlib::MWaitList::operator+=(lpHandles, qword_1401C34C8);
    while ( 1 )
    {
      v3 = lpHandles[1] - lpHandles[0];
      v4 = WaitForMultipleObjectsEx(v3, lpHandles[0], 0, 0x1B7740u, 1);
      v13 = v4;
      if ( v4 == -1 )
      {
        Log_Text_F("base\\winsat\\exe\\watchdog.cpp", 133, "Dying - Cannot wait in the watch dog thread");
        GetLastError();
        Record_Win32Error_w("base\\winsat\\exe\\watchdog.cpp", bAlertable);
        Die();
      }
      if ( v4 - 128 < v3 )
      {
        Log_Text_F("base\\winsat\\exe\\watchdog.cpp", 140, "Dying - The watch dog wait was abandoned");
        Record_InternalError_w("base\\winsat\\exe\\watchdog.cpp");
        Die();
      }
      if ( v4 == 258 )
      {
        byte_1401C34A8 = 1;
        Log_Text_F(
          "base\\winsat\\exe\\watchdog.cpp",
          148,
          "Dying - An unxpected timtout occurred in the watch dog thread");
        Record_InternalError_w("base\\winsat\\exe\\watchdog.cpp");
        Die();
      }
      if ( v4 == 192 )
      {
        Log_Text_F("base\\winsat\\exe\\watchdog.cpp", 155, "Dying - The watch dog wait had an unexpected APC");
        Record_InternalError_w("base\\winsat\\exe\\watchdog.cpp");
        Die();
      }
      v5 = mlib::MWaitList::SignaledHandle((mlib::MWaitList *)lpHandles);
      if ( v5 == qword_1401C34C8 )
      {
        byte_1401C34A8 = 1;
        Log_Text_F("base\\winsat\\exe\\watchdog.cpp", 163, "Dying - Short Watch dog times triggered");
        if ( (Microsoft_Windows_WindowsSystemAssessmentToolEnableBits & 1) != 0 )
          McGenEventWrite_EventWriteTransfer(&WINSAT_ETW_PROVIDER_Context, ShortWatchDogTimeoutEv, v6, 1, v14);
        Die();
      }
      if ( v5 != hTimer )
        break;
      byte_1401C34A8 = 1;
      Log_Text_F(
        "base\\winsat\\exe\\watchdog.cpp",
        170,
        "Assessment watch dog triggered, canceling current assessment, setting main watch dog timer to %0.1f seconds",
        qword_1401C34B8);
      CancelWatchDogTimer(2);
      CancelWatchDogTimer(0);
      CancelWatchDogTimer(1);
      if ( (Microsoft_Windows_WindowsSystemAssessmentToolEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(&WINSAT_ETW_PROVIDER_Context, AssessmentWatchDogTimeoutEv, v7, 1, v14);
      SetEvent(qword_1401C34C0);
      SetWatchDogTimeout(0);
    }
    if ( v5 == hObject )
    {
      byte_1401C34A8 = 1;
      Log_Text_F("base\\winsat\\exe\\watchdog.cpp", 184, "Dying - Main watch dog timer triggred.  Killing this process");
      if ( (Microsoft_Windows_WindowsSystemAssessmentToolEnableBits & 1) != 0 )
        McGenEventWrite_EventWriteTransfer(&WINSAT_ETW_PROVIDER_Context, MainWatchDogTimeoutEv, v8, 1, v14);
      Die();
    }
    if ( v5 != (HANDLE)qword_1401C65F0 )
    {
      Log_Text_F(
        "base\\winsat\\exe\\watchdog.cpp",
        191,
        "Dying - An unknown handle was signaled in the watch dog thread");
      Record_InternalError_w("base\\winsat\\exe\\watchdog.cpp");
      Die();
    }
    if ( lpHandles[0] )
      operator delete(lpHandles[0]);
    result = 0;
  }
  catch ( std::bad_alloc )
  {
    return 14;
  }
  return result;
}

```

## disassembly

```asm
0x140043900  mov     [rsp+arg_0], rsi
0x140043905  mov     [rsp+arg_8], rdi
0x14004390a  push    r14
0x14004390c  sub     rsp, 70h
0x140043910  mov     rax, cs:__security_cookie
0x140043917  xor     rax, rsp
0x14004391a  mov     [rsp+78h+var_18], rax
0x14004391f  call    cs:__imp_GetCurrentThread
0x140043925  mov     rcx, rax; hThread
0x140043928  call    cs:__imp_GetThreadPriority
0x14004392e  mov     r9d, eax
0x140043931  lea     r8, aWatchdogthread; "WatchDogThreadProc Launched with priori"...
0x140043938  mov     edx, 71h ; 'q'
0x14004393d  lea     rsi, aBaseWinsatExeW; "base\\winsat\\exe\\watchdog.cpp"
0x140043944  mov     rcx, rsi
0x140043947  call    Log_Text_F
0x14004394c  nop
0x14004394d  xorps   xmm0, xmm0
0x140043950  movdqu  xmmword ptr [rsp+78h+lpHandles], xmm0
0x140043956  mov     [rsp+78h+var_38], 0
0x14004395f  mov     [rsp+78h+var_30], 0FFFFFFFFh
0x140043967  mov     rdx, cs:hObject
0x14004396e  lea     rcx, [rsp+78h+lpHandles]
0x140043973  call    ??YMWaitList@mlib@@QEAAAEAV01@PEAX@Z; mlib::MWaitList::operator+=(void *)
0x140043978  mov     rdx, cs:qword_1401C65F0
0x14004397f  lea     rcx, [rsp+78h+lpHandles]
0x140043984  call    ??YMWaitList@mlib@@QEAAAEAV01@PEAX@Z; mlib::MWaitList::operator+=(void *)
0x140043989  mov     rdx, cs:hTimer
0x140043990  lea     rcx, [rsp+78h+lpHandles]
0x140043995  call    ??YMWaitList@mlib@@QEAAAEAV01@PEAX@Z; mlib::MWaitList::operator+=(void *)
0x14004399a  mov     rdx, cs:qword_1401C34C8
0x1400439a1  lea     rcx, [rsp+78h+lpHandles]
0x1400439a6  call    ??YMWaitList@mlib@@QEAAAEAV01@PEAX@Z; mlib::MWaitList::operator+=(void *)
0x1400439ab  mov     r14d, 1
0x1400439b1  mov     rdi, [rsp+78h+lpHandles+8]
0x1400439b6  sub     rdi, [rsp+78h+lpHandles]
0x1400439bb  sar     rdi, 3
0x1400439bf  mov     ecx, edi; nCount
0x1400439c1  mov     [rsp+78h+bAlertable], r14d; char
0x1400439c6  mov     r9d, 1B7740h; dwMilliseconds
0x1400439cc  xor     r8d, r8d; bWaitAll
0x1400439cf  mov     rdx, [rsp+78h+lpHandles]; lpHandles
0x1400439d4  call    cs:__imp_WaitForMultipleObjectsEx
0x1400439da  mov     [rsp+78h+var_30], eax
0x1400439de  cmp     eax, 0FFFFFFFFh
0x1400439e1  jnz     short loc_140043A19
0x1400439e3  lea     r8, aDyingCannotWai; "Dying - Cannot wait in the watch dog th"...
0x1400439ea  mov     edx, 85h
0x1400439ef  mov     rcx, rsi
0x1400439f2  call    Log_Text_F
0x1400439f7  call    cs:__imp_GetLastError
0x1400439fd  mov     r8d, eax
0x140043a00  lea     r9, aCannotWaitInTh; "Cannot wait in the watch dog thread"
0x140043a07  mov     edx, 86h
0x140043a0c  mov     rcx, rsi; char *
0x140043a0f  call    Record_Win32Error_w
0x140043a14  call    ?Die@@YAXXZ; Die(void)
0x140043a19  lea     ecx, [rax-80h]
0x140043a1c  cmp     rcx, rdi
0x140043a1f  jnb     short loc_140043A4E
0x140043a21  lea     r8, aDyingTheWatchD; "Dying - The watch dog wait was abandone"...
0x140043a28  mov     edx, 8Ch
0x140043a2d  mov     rcx, rsi
0x140043a30  call    Log_Text_F
0x140043a35  lea     r8, aTheWatchDogWai; "The watch dog wait was abandoned"
0x140043a3c  mov     edx, 8Dh
0x140043a41  mov     rcx, rsi; char *
0x140043a44  call    Record_InternalError_w
0x140043a49  call    ?Die@@YAXXZ; Die(void)
0x140043a4e  cmp     eax, 102h
0x140043a53  jnz     short loc_140043A87
0x140043a55  mov     cs:byte_1401C34A8, r14b
0x140043a5c  lea     r8, aDyingAnUnxpect; "Dying - An unxpected timtout occurred i"...
0x140043a63  lea     edx, [rax-6Eh]
0x140043a66  mov     rcx, rsi
0x140043a69  call    Log_Text_F
0x140043a6e  lea     r8, aAnUnxpectedTim; "An unxpected timtout occurred in the wa"...
0x140043a75  mov     edx, 95h
0x140043a7a  mov     rcx, rsi; char *
0x140043a7d  call    Record_InternalError_w
0x140043a82  call    ?Die@@YAXXZ; Die(void)
0x140043a87  cmp     eax, 0C0h
0x140043a8c  jnz     short loc_140043AB9
0x140043a8e  lea     r8, aDyingTheWatchD_0; "Dying - The watch dog wait had an unexp"...
0x140043a95  lea     edx, [rax-25h]
0x140043a98  mov     rcx, rsi
0x140043a9b  call    Log_Text_F
0x140043aa0  lea     r8, aTheWatchDogWai_0; "The watch dog wait had an unexpected AP"...
0x140043aa7  mov     edx, 9Ch
0x140043aac  mov     rcx, rsi; char *
0x140043aaf  call    Record_InternalError_w
0x140043ab4  call    ?Die@@YAXXZ; Die(void)
0x140043ab9  lea     rcx, [rsp+78h+lpHandles]; this
0x140043abe  call    ?SignaledHandle@MWaitList@mlib@@QEBAPEAXXZ; mlib::MWaitList::SignaledHandle(void)
0x140043ac3  cmp     rax, cs:qword_1401C34C8
0x140043aca  jnz     short loc_140043B15
0x140043acc  mov     cs:byte_1401C34A8, r14b
0x140043ad3  lea     r8, aDyingShortWatc; "Dying - Short Watch dog times triggered"
0x140043ada  mov     edx, 0A3h
0x140043adf  mov     rcx, rsi
0x140043ae2  call    Log_Text_F
0x140043ae7  test    cs:Microsoft_Windows_WindowsSystemAssessmentToolEnableBits, r14b
0x140043aee  jz      short loc_140043B10
0x140043af0  lea     rax, [rsp+78h+var_28]
0x140043af5  mov     qword ptr [rsp+78h+bAlertable], rax
0x140043afa  mov     r9d, r14d
0x140043afd  lea     rdx, ShortWatchDogTimeoutEv
0x140043b04  lea     rcx, WINSAT_ETW_PROVIDER_Context
0x140043b0b  call    McGenEventWrite_EventWriteTransfer
0x140043b10  call    ?Die@@YAXXZ; Die(void)
0x140043b15  cmp     rax, cs:hTimer
0x140043b1c  jnz     loc_140043BAD
0x140043b22  mov     cs:byte_1401C34A8, r14b
0x140043b29  movsd   xmm3, cs:qword_1401C34B8
0x140043b31  movq    r9, xmm3
0x140043b36  lea     r8, aAssessmentWatc; "Assessment watch dog triggered, canceli"...
0x140043b3d  mov     edx, 0AAh
0x140043b42  mov     rcx, rsi
0x140043b45  call    Log_Text_F
0x140043b4a  mov     ecx, 2
0x140043b4f  call    CancelWatchDogTimer
0x140043b54  xor     ecx, ecx
0x140043b56  call    CancelWatchDogTimer
0x140043b5b  mov     ecx, r14d
0x140043b5e  call    CancelWatchDogTimer
0x140043b63  test    cs:Microsoft_Windows_WindowsSystemAssessmentToolEnableBits, r14b
0x140043b6a  jz      short loc_140043B8C
0x140043b6c  lea     rax, [rsp+78h+var_28]
0x140043b71  mov     qword ptr [rsp+78h+bAlertable], rax
0x140043b76  mov     r9d, r14d
0x140043b79  lea     rdx, AssessmentWatchDogTimeoutEv
0x140043b80  lea     rcx, WINSAT_ETW_PROVIDER_Context
0x140043b87  call    McGenEventWrite_EventWriteTransfer
0x140043b8c  mov     rcx, cs:qword_1401C34C0; hEvent
0x140043b93  call    cs:__imp_SetEvent
0x140043b99  movsd   xmm1, cs:qword_1401C34B8
0x140043ba1  xor     ecx, ecx
0x140043ba3  call    SetWatchDogTimeout
0x140043ba8  jmp     loc_1400439B1
0x140043bad  cmp     rax, cs:hObject
0x140043bb4  jnz     short loc_140043BFF
0x140043bb6  mov     cs:byte_1401C34A8, r14b
0x140043bbd  lea     r8, aDyingMainWatch; "Dying - Main watch dog timer triggred. "...
0x140043bc4  mov     edx, 0B8h
0x140043bc9  mov     rcx, rsi
0x140043bcc  call    Log_Text_F
0x140043bd1  test    cs:Microsoft_Windows_WindowsSystemAssessmentToolEnableBits, r14b
0x140043bd8  jz      short loc_140043BFA
0x140043bda  lea     rax, [rsp+78h+var_28]
0x140043bdf  mov     qword ptr [rsp+78h+bAlertable], rax
0x140043be4  mov     r9d, r14d
0x140043be7  lea     rdx, MainWatchDogTimeoutEv
0x140043bee  lea     rcx, WINSAT_ETW_PROVIDER_Context
0x140043bf5  call    McGenEventWrite_EventWriteTransfer
0x140043bfa  call    ?Die@@YAXXZ; Die(void)
0x140043bff  cmp     rax, cs:qword_1401C65F0
0x140043c06  jz      short loc_140043C36
0x140043c08  lea     r8, aDyingAnUnknown; "Dying - An unknown handle was signaled "...
0x140043c0f  mov     edx, 0BFh
0x140043c14  mov     rcx, rsi
0x140043c17  call    Log_Text_F
0x140043c1c  lea     r8, aAnUnknownHandl; "An unknown handle was signaled in the w"...
0x140043c23  mov     edx, 0C0h
0x140043c28  mov     rcx, rsi; char *
0x140043c2b  call    Record_InternalError_w
0x140043c30  call    ?Die@@YAXXZ; Die(void)
0x140043c36  cmp     [rsp+78h+lpHandles], 0
0x140043c3c  jz      short loc_140043C48
0x140043c3e  mov     rcx, [rsp+78h+lpHandles]; Block
0x140043c43  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140043c48  xor     eax, eax
0x140043c4a  jmp     short loc_140043C51
0x140043c4c  mov     eax, 0Eh
0x140043c51  mov     rcx, [rsp+78h+var_18]
0x140043c56  xor     rcx, rsp; StackCookie
0x140043c59  call    __security_check_cookie
0x140043c5e  lea     r11, [rsp+78h+var_8]
0x140043c63  mov     rsi, [r11+10h]
0x140043c67  mov     rdi, [r11+18h]
0x140043c6b  mov     rsp, r11
0x140043c6e  pop     r14
0x140043c70  retn
```
