# WctCalibrateCsWaitSyscallNumber

- ea: `0x18003afe4`
- end: `0x18003b1f2`
- name: `WctCalibrateCsWaitSyscallNumber`
- size: `526`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `loader_planting`

## callers

- `0x180039ecc`

## callees

- `0x18003ac90`
- `0x18003afe4`
- `0x18003b1f8`
- `0x18003b57c`
- `0x18003b748`
- `0x18005ff74`
- `0x180065090`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18003b145`
- `ntdll!NtQueryInformationThread` at `0x18003b145`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003b0fa`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003b0fa`
- `KERNEL32!EnterCriticalSection` at `0x18003b0d7`
- `KERNEL32!EnterCriticalSection` at `0x18003b0d7`
- `KERNEL32!LeaveCriticalSection` at `0x18003b164`
- `KERNEL32!LeaveCriticalSection` at `0x18003b185`
- `KERNEL32!LeaveCriticalSection` at `0x18003b164`
- `KERNEL32!LeaveCriticalSection` at `0x18003b185`
- `KERNEL32!CreateEventW` at `0x18003b06d`
- `KERNEL32!CreateEventW` at `0x18003b06d`
- `KERNEL32!DeleteCriticalSection` at `0x18003b18f`
- `KERNEL32!DeleteCriticalSection` at `0x18003b18f`
- `KERNEL32!WaitForSingleObject` at `0x18003b179`
- `KERNEL32!WaitForSingleObject` at `0x18003b179`
- `KERNEL32!SetEvent` at `0x18003b16e`
- `KERNEL32!SetEvent` at `0x18003b16e`
- `KERNEL32!InitializeCriticalSection` at `0x18003b0cd`
- `KERNEL32!InitializeCriticalSection` at `0x18003b0cd`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 WctCalibrateCsWaitSyscallNumber()
{
  HANDLE EventW; // rax
  unsigned int v1; // edi
  unsigned int v2; // esi
  HANDLE v3; // rax
  HANDLE v4; // rbx
  DWORD ThreadId; // [rsp+30h] [rbp-49h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-45h] BYREF
  void *v8; // [rsp+38h] [rbp-41h] BYREF
  HANDLE ThreadHandle; // [rsp+40h] [rbp-39h] BYREF
  _QWORD CriticalSection[6]; // [rsp+48h] [rbp-31h] BYREF
  HANDLE hEvent; // [rsp+78h] [rbp-1h]
  __int128 ThreadInformation; // [rsp+80h] [rbp+7h] BYREF
  __int64 v13; // [rsp+90h] [rbp+17h]

  ThreadInformation = 0;
  v13 = 0;
  ReturnLength = 0;
  ThreadId = 0;
  ThreadHandle = 0;
  v8 = 0;
  memset(CriticalSection, 0, sizeof(CriticalSection));
  hEvent = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_4c32fa7a72a13340317baef891270170_Traceguids);
  EventW = CreateEventW(0, 0, 0, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&v8, EventW);
  if ( (unsigned __int64)v8 + 1 > 1 )
  {
    v2 = -1;
    hEvent = v8;
    InitializeCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    EnterCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    v3 = CreateThread(0, 0, WctSyscallCalibratorThreadProc, CriticalSection, 0, &ThreadId);
    tlx::unique_any<tlx::file_handle_traits>::reset(&ThreadHandle, v3);
    v4 = ThreadHandle;
    if ( (unsigned __int64)ThreadHandle + 1 <= 1 )
    {
      LeaveCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    }
    else
    {
      if ( (unsigned int)WctWaitUntilThreadIsBlocked(ThreadId)
        && NtQueryInformationThread(v4, ThreadLastSystemCall, &ThreadInformation, 0x18u, &ReturnLength) >= 0
        && ReturnLength == 24
        && WORD4(ThreadInformation) )
      {
        v2 = WORD4(ThreadInformation);
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
      SetEvent(hEvent);
      WaitForSingleObject(v4, 0xFFFFFFFF);
    }
    DeleteCriticalSection((LPCRITICAL_SECTION)&CriticalSection[1]);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 20, WPP_4c32fa7a72a13340317baef891270170_Traceguids, v2);
    v1 = v2;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 19, WPP_4c32fa7a72a13340317baef891270170_Traceguids, 0xFFFFFFFFLL);
    v1 = -1;
  }
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&v8);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&ThreadHandle);
  return v1;
}

```

## disassembly

```asm
0x18003afe4  push    rbp
0x18003afe6  push    rbx
0x18003afe7  push    rsi
0x18003afe8  push    rdi
0x18003afe9  push    r12
0x18003afeb  push    r14
0x18003afed  lea     rbp, [rsp-2Fh]
0x18003aff2  sub     rsp, 0A8h
0x18003aff9  mov     rax, cs:__security_cookie
0x18003b000  xor     rax, rsp
0x18003b003  mov     [rbp+57h+var_38], rax
0x18003b007  xorps   xmm0, xmm0
0x18003b00a  xor     eax, eax
0x18003b00c  movups  [rbp+57h+ThreadInformation], xmm0
0x18003b010  mov     [rbp+57h+var_40], rax
0x18003b014  xor     r14d, r14d
0x18003b017  mov     [rbp+57h+ReturnLength], r14d
0x18003b01b  mov     [rbp+57h+ThreadId], r14d
0x18003b01f  mov     [rbp+57h+ThreadHandle], r14
0x18003b023  mov     [rbp+57h+var_98], r14
0x18003b027  movups  xmmword ptr [rbp+57h+CriticalSection], xmm0
0x18003b02b  movups  xmmword ptr [rbp+57h+CriticalSection+10h], xmm0
0x18003b02f  movups  xmmword ptr [rbp+57h+CriticalSection+20h], xmm0
0x18003b033  mov     [rbp+57h+hEvent], rax
0x18003b037  lea     r12, WPP_GLOBAL_Control
0x18003b03e  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b045  cmp     rcx, r12
0x18003b048  jz      short loc_18003B063
0x18003b04a  test    byte ptr [rcx+1Ch], 4
0x18003b04e  jz      short loc_18003B063
0x18003b050  lea     edx, [rax+12h]
0x18003b053  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003b05a  mov     rcx, [rcx+10h]
0x18003b05e  call    WPP_SF_
0x18003b063  xor     r9d, r9d; lpName
0x18003b066  xor     r8d, r8d; bInitialState
0x18003b069  xor     edx, edx; bManualReset
0x18003b06b  xor     ecx, ecx; lpEventAttributes
0x18003b06d  call    cs:__imp_CreateEventW
0x18003b073  mov     rdx, rax
0x18003b076  lea     rcx, [rbp+57h+var_98]
0x18003b07a  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003b07f  mov     rax, [rbp+57h+var_98]
0x18003b083  lea     rcx, [rax+1]
0x18003b087  cmp     rcx, 1
0x18003b08b  ja      short loc_18003B0C0
0x18003b08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b094  cmp     rcx, r12
0x18003b097  jz      short loc_18003B0B8
0x18003b099  test    byte ptr [rcx+1Ch], 4
0x18003b09d  jz      short loc_18003B0B8
0x18003b09f  mov     edx, 13h
0x18003b0a4  or      r9d, 0FFFFFFFFh
0x18003b0a8  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003b0af  mov     rcx, [rcx+10h]
0x18003b0b3  call    WPP_SF_d
0x18003b0b8  or      edi, 0FFFFFFFFh
0x18003b0bb  jmp     loc_18003B1C1
0x18003b0c0  or      edi, 0FFFFFFFFh
0x18003b0c3  mov     esi, edi
0x18003b0c5  mov     [rbp+57h+hEvent], rax
0x18003b0c9  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18003b0cd  call    cs:__imp_InitializeCriticalSection
0x18003b0d3  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18003b0d7  call    cs:__imp_EnterCriticalSection
0x18003b0dd  lea     rax, [rbp+57h+ThreadId]
0x18003b0e1  mov     [rsp+0D0h+lpThreadId], rax; lpThreadId
0x18003b0e6  mov     [rsp+0D0h+dwCreationFlags], r14d; dwCreationFlags
0x18003b0eb  lea     r9, [rbp+57h+CriticalSection]; lpParameter
0x18003b0ef  lea     r8, WctSyscallCalibratorThreadProc; lpStartAddress
0x18003b0f6  xor     edx, edx; dwStackSize
0x18003b0f8  xor     ecx, ecx; lpThreadAttributes
0x18003b0fa  call    cs:__imp_CreateThread
0x18003b100  mov     rdx, rax
0x18003b103  lea     rcx, [rbp+57h+ThreadHandle]
0x18003b107  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x18003b10c  mov     rbx, [rbp+57h+ThreadHandle]
0x18003b110  lea     rax, [rbx+1]
0x18003b114  cmp     rax, 1
0x18003b118  jbe     short loc_18003B181
0x18003b11a  mov     edx, 25h ; '%'
0x18003b11f  mov     ecx, [rbp+57h+ThreadId]; unsigned int
0x18003b122  call    WctWaitUntilThreadIsBlocked
0x18003b127  test    eax, eax
0x18003b129  jz      short loc_18003B160
0x18003b12b  lea     rax, [rbp+57h+ReturnLength]
0x18003b12f  mov     qword ptr [rsp+0D0h+dwCreationFlags], rax; ReturnLength
0x18003b134  mov     r9d, 18h; ThreadInformationLength
0x18003b13a  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18003b13e  lea     edx, [r9-3]; ThreadInformationClass
0x18003b142  mov     rcx, rbx; ThreadHandle
0x18003b145  call    cs:__imp_NtQueryInformationThread
0x18003b14b  test    eax, eax
0x18003b14d  js      short loc_18003B160
0x18003b14f  cmp     [rbp+57h+ReturnLength], 18h
0x18003b153  jnz     short loc_18003B160
0x18003b155  movzx   eax, word ptr [rbp+57h+ThreadInformation+8]
0x18003b159  test    ax, ax
0x18003b15c  jz      short loc_18003B160
0x18003b15e  mov     esi, eax
0x18003b160  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18003b164  call    cs:__imp_LeaveCriticalSection
0x18003b16a  mov     rcx, [rbp+57h+hEvent]; hEvent
0x18003b16e  call    cs:__imp_SetEvent
0x18003b174  mov     edx, edi; dwMilliseconds
0x18003b176  mov     rcx, rbx; hHandle
0x18003b179  call    cs:__imp_WaitForSingleObject
0x18003b17f  jmp     short loc_18003B18B
0x18003b181  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18003b185  call    cs:__imp_LeaveCriticalSection
0x18003b18b  lea     rcx, [rbp+57h+CriticalSection+8]; lpCriticalSection
0x18003b18f  call    cs:__imp_DeleteCriticalSection
0x18003b195  mov     rcx, cs:WPP_GLOBAL_Control
0x18003b19c  cmp     rcx, r12
0x18003b19f  jz      short loc_18003B1BF
0x18003b1a1  test    byte ptr [rcx+1Ch], 4
0x18003b1a5  jz      short loc_18003B1BF
0x18003b1a7  mov     edx, 14h
0x18003b1ac  mov     r9d, esi
0x18003b1af  lea     r8, WPP_4c32fa7a72a13340317baef891270170_Traceguids
0x18003b1b6  mov     rcx, [rcx+10h]
0x18003b1ba  call    WPP_SF_d
0x18003b1bf  mov     edi, esi
0x18003b1c1  lea     rcx, [rbp+57h+var_98]
0x18003b1c5  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18003b1ca  nop
0x18003b1cb  lea     rcx, [rbp+57h+ThreadHandle]
0x18003b1cf  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x18003b1d4  mov     eax, edi
0x18003b1d6  mov     rcx, [rbp+57h+var_38]
0x18003b1da  xor     rcx, rsp; StackCookie
0x18003b1dd  call    __security_check_cookie
0x18003b1e2  add     rsp, 0A8h
0x18003b1e9  pop     r14
0x18003b1eb  pop     r12
0x18003b1ed  pop     rdi
0x18003b1ee  pop     rsi
0x18003b1ef  pop     rbx
0x18003b1f0  pop     rbp
0x18003b1f1  retn
```
