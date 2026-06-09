# WctCalibrateCsWaitSyscallNumber

- ea: `0x18003f87c`
- end: `0x18003fad4`
- name: `WctCalibrateCsWaitSyscallNumber`
- size: `600`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18003e6c8`

## callees

- `0x18003f87c`
- `0x18003faec`
- `0x18003fb18`
- `0x18003fd04`
- `0x18006c87c`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18003fa04`
- `ntdll!NtQueryInformationThread` at `0x18003fa04`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003f9b1`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003f9b1`
- `KERNEL32!EnterCriticalSection` at `0x18003f988`
- `KERNEL32!EnterCriticalSection` at `0x18003f988`
- `KERNEL32!LeaveCriticalSection` at `0x18003fa29`
- `KERNEL32!LeaveCriticalSection` at `0x18003fa5d`
- `KERNEL32!LeaveCriticalSection` at `0x18003fa29`
- `KERNEL32!LeaveCriticalSection` at `0x18003fa5d`
- `KERNEL32!CreateEventW` at `0x18003f905`
- `KERNEL32!CreateEventW` at `0x18003f905`
- `KERNEL32!DeleteCriticalSection` at `0x18003fa6d`
- `KERNEL32!DeleteCriticalSection` at `0x18003fa6d`
- `KERNEL32!WaitForSingleObject` at `0x18003fa4b`
- `KERNEL32!WaitForSingleObject` at `0x18003fa4b`
- `KERNEL32!SetEvent` at `0x18003fa39`
- `KERNEL32!SetEvent` at `0x18003fa39`
- `KERNEL32!InitializeCriticalSection` at `0x18003f978`
- `KERNEL32!InitializeCriticalSection` at `0x18003f978`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 WctCalibrateCsWaitSyscallNumber()
{
  HANDLE EventW; // rbx
  __int64 v1; // rcx
  void *v2; // rcx
  __int64 v3; // rcx
  unsigned int v5; // edi
  HANDLE v6; // rsi
  __int64 v7; // rcx
  void *v8; // rcx
  __int64 v9; // rcx
  DWORD ThreadId; // [rsp+30h] [rbp-49h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-45h] BYREF
  HANDLE v12; // [rsp+38h] [rbp-41h]
  HANDLE v13; // [rsp+40h] [rbp-39h]
  _QWORD CriticalSection[6]; // [rsp+48h] [rbp-31h] BYREF
  HANDLE hEvent; // [rsp+78h] [rbp-1h]
  __int128 ThreadInformation; // [rsp+80h] [rbp+7h] BYREF
  __int64 v17; // [rsp+90h] [rbp+17h]

  ThreadInformation = 0;
  v17 = 0;
  ReturnLength = 0;
  ThreadId = 0;
  v13 = 0;
  v12 = 0;
  memset(CriticalSection, 0, sizeof(CriticalSection));
  hEvent = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  EventW = CreateEventW(0, 0, 0, 0);
  v12 = EventW;
  tlx::file_handle_traits::operator()(v1, 0);
  if ( (unsigned __int64)EventW + 1 > 1 )
  {
    v5 = -1;
    hEvent = EventW;
    InitializeCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    EnterCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    v6 = CreateThread(0, 0, WctSyscallCalibratorThreadProc, CriticalSection, 0, &ThreadId);
    v13 = v6;
    tlx::file_handle_traits::operator()(v7, 0);
    if ( (unsigned __int64)v6 + 1 <= 1 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    }
    else
    {
      if ( (unsigned int)WctWaitUntilThreadIsBlocked(ThreadId)
        && NtQueryInformationThread(v6, ThreadLastSystemCall, &ThreadInformation, 0x18u, &ReturnLength) >= 0
        && ReturnLength == 24
        && WORD4(ThreadInformation) )
      {
        v5 = WORD4(ThreadInformation);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
      SetEvent(hEvent);
      WaitForSingleObject(v6, 0xFFFFFFFF);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    v8 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v5);
    tlx::file_handle_traits::operator()(v8, EventW);
    tlx::file_handle_traits::operator()(v9, v6);
    return v5;
  }
  else
  {
    v2 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, 0xFFFFFFFFLL);
    tlx::file_handle_traits::operator()(v2, EventW);
    tlx::file_handle_traits::operator()(v3, 0);
    return 0xFFFFFFFFLL;
  }
}

```

## disassembly

```asm
0x18003f87c  push    rbp
0x18003f87e  push    rbx
0x18003f87f  push    rsi
0x18003f880  push    rdi
0x18003f881  push    r12
0x18003f883  push    r14
0x18003f885  lea     rbp, [rsp-2Fh]
0x18003f88a  sub     rsp, 0A8h
0x18003f891  mov     rax, cs:__security_cookie
0x18003f898  xor     rax, rsp
0x18003f89b  mov     [rbp+57h+var_38], rax
0x18003f89f  xorps   xmm0, xmm0
0x18003f8a2  xor     eax, eax
0x18003f8a4  movups  [rbp+57h+ThreadInformation], xmm0
0x18003f8a8  mov     [rbp+57h+var_40], rax
0x18003f8ac  xor     r14d, r14d
0x18003f8af  mov     [rbp+57h+ReturnLength], r14d
0x18003f8b3  mov     [rbp+57h+ThreadId], r14d
0x18003f8b7  mov     [rbp+57h+var_90], r14
0x18003f8bb  mov     [rbp+57h+var_98], r14
0x18003f8bf  movups  xmmword ptr [rbp+57h+CriticalSection], xmm0
0x18003f8c3  movups  xmmword ptr [rbp+57h+CriticalSection+10h], xmm0
0x18003f8c7  movups  xmmword ptr [rbp+57h+CriticalSection+20h], xmm0
0x18003f8cb  mov     [rbp+57h+hEvent], rax
0x18003f8cf  lea     r12, WPP_GLOBAL_Control
0x18003f8d6  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f8dd  cmp     rcx, r12
0x18003f8e0  jz      short loc_18003F8FB
0x18003f8e2  test    byte ptr [rcx+1Ch], 4
0x18003f8e6  jz      short loc_18003F8FB
0x18003f8e8  lea     edx, [rax+12h]
0x18003f8eb  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003f8f2  mov     rcx, [rcx+10h]
0x18003f8f6  call    WPP_SF_
0x18003f8fb  xor     r9d, r9d; lpName
0x18003f8fe  xor     r8d, r8d; bInitialState
0x18003f901  xor     edx, edx; bManualReset
0x18003f903  xor     ecx, ecx; lpEventAttributes
0x18003f905  call    cs:__imp_CreateEventW
0x18003f90c  nop     dword ptr [rax+rax+00h]
0x18003f911  mov     rbx, rax
0x18003f914  mov     [rbp+57h+var_98], rax
0x18003f918  xor     edx, edx
0x18003f91a  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f91f  lea     rcx, [rbx+1]
0x18003f923  cmp     rcx, 1
0x18003f927  ja      short loc_18003F96D
0x18003f929  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f930  cmp     rcx, r12
0x18003f933  jz      short loc_18003F955
0x18003f935  test    byte ptr [rcx+1Ch], 4
0x18003f939  jz      short loc_18003F955
0x18003f93b  mov     edx, 13h
0x18003f940  or      r9d, 0FFFFFFFFh
0x18003f944  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003f94b  mov     rcx, [rcx+10h]
0x18003f94f  call    WPP_SF_d
0x18003f954  nop
0x18003f955  mov     rdx, rbx
0x18003f958  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f95d  nop
0x18003f95e  xor     edx, edx
0x18003f960  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f965  or      eax, 0FFFFFFFFh
0x18003f968  jmp     loc_18003FAB7
0x18003f96d  or      edi, 0FFFFFFFFh
0x18003f970  mov     [rbp+57h+hEvent], rbx
0x18003f974  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18003f978  call    cs:__imp_InitializeCriticalSection
0x18003f97f  nop     dword ptr [rax+rax+00h]
0x18003f984  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18003f988  call    cs:__imp_EnterCriticalSection
0x18003f98f  nop     dword ptr [rax+rax+00h]
0x18003f994  lea     rax, [rbp+57h+ThreadId]
0x18003f998  mov     [rsp+0D0h+lpThreadId], rax; lpThreadId
0x18003f99d  mov     [rsp+0D0h+dwCreationFlags], r14d; dwCreationFlags
0x18003f9a2  lea     r9, [rbp+57h+CriticalSection]; lpParameter
0x18003f9a6  lea     r8, WctSyscallCalibratorThreadProc; lpStartAddress
0x18003f9ad  xor     edx, edx; dwStackSize
0x18003f9af  xor     ecx, ecx; lpThreadAttributes
0x18003f9b1  call    cs:__imp_CreateThread
0x18003f9b8  nop     dword ptr [rax+rax+00h]
0x18003f9bd  mov     rsi, rax
0x18003f9c0  mov     [rbp+57h+var_90], rax
0x18003f9c4  xor     edx, edx
0x18003f9c6  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f9cb  lea     rcx, [rsi+1]
0x18003f9cf  cmp     rcx, 1
0x18003f9d3  jbe     loc_18003FA59
0x18003f9d9  mov     edx, 25h ; '%'
0x18003f9de  mov     ecx, [rbp+57h+ThreadId]; unsigned int
0x18003f9e1  call    WctWaitUntilThreadIsBlocked
0x18003f9e6  test    eax, eax
0x18003f9e8  jz      short loc_18003FA25
0x18003f9ea  lea     rax, [rbp+57h+ReturnLength]
0x18003f9ee  mov     qword ptr [rsp+0D0h+dwCreationFlags], rax; ReturnLength
0x18003f9f3  mov     r9d, 18h; ThreadInformationLength
0x18003f9f9  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18003f9fd  lea     edx, [r9-3]; ThreadInformationClass
0x18003fa01  mov     rcx, rsi; ThreadHandle
0x18003fa04  call    cs:__imp_NtQueryInformationThread
0x18003fa0b  nop     dword ptr [rax+rax+00h]
0x18003fa10  test    eax, eax
0x18003fa12  js      short loc_18003FA25
0x18003fa14  cmp     [rbp+57h+ReturnLength], 18h
0x18003fa18  jnz     short loc_18003FA25
0x18003fa1a  movzx   eax, word ptr [rbp+57h+ThreadInformation+8]
0x18003fa1e  test    ax, ax
0x18003fa21  jz      short loc_18003FA25
0x18003fa23  mov     edi, eax
0x18003fa25  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18003fa29  call    cs:__imp_LeaveCriticalSection
0x18003fa30  nop     dword ptr [rax+rax+00h]
0x18003fa35  mov     rcx, [rbp+57h+hEvent]; hEvent
0x18003fa39  call    cs:__imp_SetEvent
0x18003fa40  nop     dword ptr [rax+rax+00h]
0x18003fa45  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003fa48  mov     rcx, rsi; hHandle
0x18003fa4b  call    cs:__imp_WaitForSingleObject
0x18003fa52  nop     dword ptr [rax+rax+00h]
0x18003fa57  jmp     short loc_18003FA69
0x18003fa59  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18003fa5d  call    cs:__imp_LeaveCriticalSection
0x18003fa64  nop     dword ptr [rax+rax+00h]
0x18003fa69  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18003fa6d  call    cs:__imp_DeleteCriticalSection
0x18003fa74  nop     dword ptr [rax+rax+00h]
0x18003fa79  mov     rcx, cs:WPP_GLOBAL_Control
0x18003fa80  cmp     rcx, r12
0x18003fa83  jz      short loc_18003FAA4
0x18003fa85  test    byte ptr [rcx+1Ch], 4
0x18003fa89  jz      short loc_18003FAA4
0x18003fa8b  mov     edx, 14h
0x18003fa90  mov     r9d, edi
0x18003fa93  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003fa9a  mov     rcx, [rcx+10h]
0x18003fa9e  call    WPP_SF_d
0x18003faa3  nop
0x18003faa4  mov     rdx, rbx
0x18003faa7  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003faac  nop
0x18003faad  mov     rdx, rsi
0x18003fab0  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003fab5  mov     eax, edi
0x18003fab7  mov     rcx, [rbp+57h+var_38]
0x18003fabb  xor     rcx, rsp; StackCookie
0x18003fabe  call    __security_check_cookie
0x18003fac3  add     rsp, 0A8h
0x18003faca  pop     r14
0x18003facc  pop     r12
0x18003face  pop     rdi
0x18003facf  pop     rsi
0x18003fad0  pop     rbx
0x18003fad1  pop     rbp
0x18003fad2  retn
```
