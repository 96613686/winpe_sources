# InitializeWatchDogSystem

- ea: `0x140043ce4`
- end: `0x140043f0e`
- name: `InitializeWatchDogSystem`
- size: `554`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14001a54c`

## callees

- `0x14000b048`
- `0x14003fa8c`
- `0x140043ce4`

## import_xrefs

- `KERNEL32!CreateWaitableTimerW` at `0x140043db1`
- `KERNEL32!CreateWaitableTimerW` at `0x140043dde`
- `KERNEL32!CreateWaitableTimerW` at `0x140043e2e`
- `KERNEL32!CreateWaitableTimerW` at `0x140043db1`
- `KERNEL32!CreateWaitableTimerW` at `0x140043dde`
- `KERNEL32!CreateWaitableTimerW` at `0x140043e2e`
- `KERNEL32!CreateThread` at `0x140043e9b`
- `KERNEL32!CreateThread` at `0x140043e9b`
- `KERNEL32!CloseHandle` at `0x140043e1a`
- `KERNEL32!CloseHandle` at `0x140043e6a`
- `KERNEL32!CloseHandle` at `0x140043ed7`
- `KERNEL32!CloseHandle` at `0x140043ee4`
- `KERNEL32!CloseHandle` at `0x140043e1a`
- `KERNEL32!CloseHandle` at `0x140043e6a`
- `KERNEL32!CloseHandle` at `0x140043ed7`
- `KERNEL32!CloseHandle` at `0x140043ee4`
- `KERNEL32!GetLastError` at `0x140043d16`
- `KERNEL32!GetLastError` at `0x140043d4f`
- `KERNEL32!GetLastError` at `0x140043d84`
- `KERNEL32!GetLastError` at `0x140043dc3`
- `KERNEL32!GetLastError` at `0x140043df0`
- `KERNEL32!GetLastError` at `0x140043e40`
- `KERNEL32!GetLastError` at `0x140043ead`
- `KERNEL32!GetLastError` at `0x140043d16`
- `KERNEL32!GetLastError` at `0x140043d4f`
- `KERNEL32!GetLastError` at `0x140043d84`
- `KERNEL32!GetLastError` at `0x140043dc3`
- `KERNEL32!GetLastError` at `0x140043df0`
- `KERNEL32!GetLastError` at `0x140043e40`
- `KERNEL32!GetLastError` at `0x140043ead`
- `KERNEL32!Sleep` at `0x140043efb`
- `KERNEL32!Sleep` at `0x140043efb`
- `KERNEL32!WaitForSingleObject` at `0x140043d0b`
- `KERNEL32!WaitForSingleObject` at `0x140043d0b`

## string_xrefs

- `0x140043d8a`: `Cannot create watch dog stop event`
- `0x140043dc9`: `Cannot create watch dog timer`
- `0x140043df6`: `Cannot create short watch dog timer`
- `0x140043e46`: `Cannot create short watch dog timer`
- `0x140043eb3`: `Cannot start watch dog thread`

## pseudocode

```c
__int64 __fastcall InitializeWatchDogSystem(void *a1, double a2)
{
  int v4; // r8d
  unsigned int v5; // eax
  HANDLE v6; // rcx
  unsigned int v7; // ebx
  char dwCreationFlags; // [rsp+20h] [rbp-28h]
  char dwCreationFlagsa; // [rsp+20h] [rbp-28h]

  if ( qword_1401C34A0 )
    return 183;
  if ( WaitForSingleObject(a1, 0) == -1 || a2 < 1.0 )
  {
    GetLastError();
    Record_Win32Error_w("base\\winsat\\exe\\watchdog.cpp", dwCreationFlags);
    return 87;
  }
  qword_1401C34B8 = *(_QWORD *)&a2;
  qword_1401C34C0 = a1;
  if ( !mlib::MEvent::Create((mlib::MEvent *)&qword_1401C65F0, 0, v4) || (hObject = CreateWaitableTimerW(0, 0, 0)) == 0 )
  {
    GetLastError();
    return Record_Win32Error_w("base\\winsat\\exe\\watchdog.cpp", dwCreationFlags);
  }
  hTimer = CreateWaitableTimerW(0, 0, 0);
  if ( !hTimer )
  {
    GetLastError();
    v5 = Record_Win32Error_w("base\\winsat\\exe\\watchdog.cpp", dwCreationFlags);
    v6 = hObject;
    v7 = v5;
LABEL_11:
    CloseHandle(v6);
    return v7;
  }
  qword_1401C34C8 = CreateWaitableTimerW(0, 0, 0);
  if ( !qword_1401C34C8 )
  {
    GetLastError();
    v7 = Record_Win32Error_w("base\\winsat\\exe\\watchdog.cpp", dwCreationFlags);
    CloseHandle(hObject);
    v6 = hTimer;
    goto LABEL_11;
  }
  qword_1401C34A0 = CreateThread(0, 0, WatchDogThreadProc, 0, 0, &ThreadId);
  if ( !qword_1401C34A0 )
  {
    GetLastError();
    v7 = Record_Win32Error_w("base\\winsat\\exe\\watchdog.cpp", dwCreationFlagsa);
    CloseHandle(hObject);
    CloseHandle(hTimer);
    v6 = qword_1401C34C8;
    goto LABEL_11;
  }
  Sleep(0x20u);
  return 0;
}

```

## disassembly

```asm
0x140043ce4  push    rbx
0x140043ce6  sub     rsp, 40h
0x140043cea  cmp     cs:qword_1401C34A0, 0
0x140043cf2  mov     rbx, rcx
0x140043cf5  movaps  [rsp+48h+var_18], xmm6
0x140043cfa  movaps  xmm6, xmm1
0x140043cfd  jz      short loc_140043D09
0x140043cff  mov     eax, 0B7h
0x140043d04  jmp     loc_140043F03
0x140043d09  xor     edx, edx; dwMilliseconds
0x140043d0b  call    cs:__imp_WaitForSingleObject
0x140043d11  cmp     eax, 0FFFFFFFFh
0x140043d14  jnz     short loc_140043D41
0x140043d16  call    cs:__imp_GetLastError
0x140043d1c  lea     r9, aTheTerminateAs; "The terminate assessment event handle i"...
0x140043d23  mov     edx, 0E9h
0x140043d28  mov     r8d, eax
0x140043d2b  lea     rcx, aBaseWinsatExeW; "base\\winsat\\exe\\watchdog.cpp"
0x140043d32  call    Record_Win32Error_w
0x140043d37  mov     eax, 57h ; 'W'
0x140043d3c  jmp     loc_140043F03
0x140043d41  movsd   xmm0, cs:__real@3ff0000000000000
0x140043d49  comisd  xmm0, xmm6
0x140043d4d  jbe     short loc_140043D63
0x140043d4f  call    cs:__imp_GetLastError
0x140043d55  lea     r9, aFinalwaittimes; "FinalWaitTimeSecs parameter is invalid"
0x140043d5c  mov     edx, 0EEh
0x140043d61  jmp     short loc_140043D28
0x140043d63  xor     edx, edx; int
0x140043d65  movsd   cs:qword_1401C34B8, xmm6
0x140043d6d  lea     rcx, qword_1401C65F0; this
0x140043d74  mov     cs:qword_1401C34C0, rbx
0x140043d7b  call    ?Create@MEvent@mlib@@QEAA_NHH@Z; mlib::MEvent::Create(int,int)
0x140043d80  test    al, al
0x140043d82  jnz     short loc_140043DAA
0x140043d84  call    cs:__imp_GetLastError
0x140043d8a  lea     r9, aCannotCreateWa; "Cannot create watch dog stop event"
0x140043d91  mov     edx, 0F6h
0x140043d96  mov     r8d, eax
0x140043d99  lea     rcx, aBaseWinsatExeW; "base\\winsat\\exe\\watchdog.cpp"
0x140043da0  call    Record_Win32Error_w
0x140043da5  jmp     loc_140043F03
0x140043daa  xor     r8d, r8d; lpTimerName
0x140043dad  xor     edx, edx; bManualReset
0x140043daf  xor     ecx, ecx; lpTimerAttributes
0x140043db1  call    cs:__imp_CreateWaitableTimerW
0x140043db7  mov     cs:hObject, rax
0x140043dbe  test    rax, rax
0x140043dc1  jnz     short loc_140043DD7
0x140043dc3  call    cs:__imp_GetLastError
0x140043dc9  lea     r9, aCannotCreateWa_0; "Cannot create watch dog timer"
0x140043dd0  mov     edx, 0FFh
0x140043dd5  jmp     short loc_140043D96
0x140043dd7  xor     r8d, r8d; lpTimerName
0x140043dda  xor     edx, edx; bManualReset
0x140043ddc  xor     ecx, ecx; lpTimerAttributes
0x140043dde  call    cs:__imp_CreateWaitableTimerW
0x140043de4  mov     cs:hTimer, rax
0x140043deb  test    rax, rax
0x140043dee  jnz     short loc_140043E27
0x140043df0  call    cs:__imp_GetLastError
0x140043df6  lea     r9, aCannotCreateSh; "Cannot create short watch dog timer"
0x140043dfd  mov     edx, 108h
0x140043e02  mov     r8d, eax
0x140043e05  lea     rcx, aBaseWinsatExeW; "base\\winsat\\exe\\watchdog.cpp"
0x140043e0c  call    Record_Win32Error_w
0x140043e11  mov     rcx, cs:hObject; hObject
0x140043e18  mov     ebx, eax
0x140043e1a  call    cs:__imp_CloseHandle
0x140043e20  mov     eax, ebx
0x140043e22  jmp     loc_140043F03
0x140043e27  xor     r8d, r8d; lpTimerName
0x140043e2a  xor     edx, edx; bManualReset
0x140043e2c  xor     ecx, ecx; lpTimerAttributes
0x140043e2e  call    cs:__imp_CreateWaitableTimerW
0x140043e34  mov     cs:qword_1401C34C8, rax
0x140043e3b  test    rax, rax
0x140043e3e  jnz     short loc_140043E79
0x140043e40  call    cs:__imp_GetLastError
0x140043e46  lea     r9, aCannotCreateSh; "Cannot create short watch dog timer"
0x140043e4d  mov     edx, 113h
0x140043e52  mov     r8d, eax
0x140043e55  lea     rcx, aBaseWinsatExeW; "base\\winsat\\exe\\watchdog.cpp"
0x140043e5c  call    Record_Win32Error_w
0x140043e61  mov     rcx, cs:hObject; hObject
0x140043e68  mov     ebx, eax
0x140043e6a  call    cs:__imp_CloseHandle
0x140043e70  mov     rcx, cs:hTimer
0x140043e77  jmp     short loc_140043E1A
0x140043e79  lea     rax, ThreadId
0x140043e80  xor     r9d, r9d; lpParameter
0x140043e83  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x140043e88  lea     r8, WatchDogThreadProc; lpStartAddress
0x140043e8f  xor     edx, edx; dwStackSize
0x140043e91  mov     dword ptr [rsp+48h+dwCreationFlags], 0; char
0x140043e99  xor     ecx, ecx; lpThreadAttributes
0x140043e9b  call    cs:__imp_CreateThread
0x140043ea1  mov     cs:qword_1401C34A0, rax
0x140043ea8  test    rax, rax
0x140043eab  jnz     short loc_140043EF6
0x140043ead  call    cs:__imp_GetLastError
0x140043eb3  lea     r9, aCannotStartWat; "Cannot start watch dog thread"
0x140043eba  mov     edx, 122h
0x140043ebf  mov     r8d, eax
0x140043ec2  lea     rcx, aBaseWinsatExeW; "base\\winsat\\exe\\watchdog.cpp"
0x140043ec9  call    Record_Win32Error_w
0x140043ece  mov     rcx, cs:hObject; hObject
0x140043ed5  mov     ebx, eax
0x140043ed7  call    cs:__imp_CloseHandle
0x140043edd  mov     rcx, cs:hTimer; hObject
0x140043ee4  call    cs:__imp_CloseHandle
0x140043eea  mov     rcx, cs:qword_1401C34C8
0x140043ef1  jmp     loc_140043E1A
0x140043ef6  mov     ecx, 20h ; ' '; dwMilliseconds
0x140043efb  call    cs:__imp_Sleep
0x140043f01  xor     eax, eax
0x140043f03  movaps  xmm6, [rsp+48h+var_18]
0x140043f08  add     rsp, 40h
0x140043f0c  pop     rbx
0x140043f0d  retn
```
