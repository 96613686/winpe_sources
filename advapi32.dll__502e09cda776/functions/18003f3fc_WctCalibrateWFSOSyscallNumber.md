# WctCalibrateWFSOSyscallNumber

- ea: `0x18003f3fc`
- end: `0x18003f5c3`
- name: `WctCalibrateWFSOSyscallNumber`
- size: `455`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x18003e6c8`

## callees

- `0x18003f3fc`
- `0x18003faec`
- `0x18003fb18`
- `0x18003fd04`
- `0x18006c87c`
- `0x1800720b0`

## import_xrefs

- `ntdll!NtQueryInformationThread` at `0x18003f525`
- `ntdll!NtQueryInformationThread` at `0x18003f525`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003f4d6`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18003f4d6`
- `KERNEL32!CreateEventW` at `0x18003f48d`
- `KERNEL32!CreateEventW` at `0x18003f48d`
- `KERNEL32!WaitForSingleObject` at `0x18003f55c`
- `KERNEL32!WaitForSingleObject` at `0x18003f55c`
- `KERNEL32!SetEvent` at `0x18003f54a`
- `KERNEL32!SetEvent` at `0x18003f54a`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 WctCalibrateWFSOSyscallNumber()
{
  unsigned int v0; // edi
  HANDLE v1; // rbx
  HANDLE EventW; // rsi
  __int64 v3; // rcx
  __int64 v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx
  DWORD ThreadId; // [rsp+30h] [rbp-49h] BYREF
  ULONG ReturnLength; // [rsp+34h] [rbp-45h] BYREF
  HANDLE v10; // [rsp+38h] [rbp-41h]
  HANDLE v11; // [rsp+40h] [rbp-39h]
  _OWORD Parameter[3]; // [rsp+48h] [rbp-31h] BYREF
  __int64 v13; // [rsp+78h] [rbp-1h]
  __int128 ThreadInformation; // [rsp+80h] [rbp+7h] BYREF
  __int64 v15; // [rsp+90h] [rbp+17h]

  ThreadInformation = 0;
  v15 = 0;
  ReturnLength = 0;
  ThreadId = 0;
  v0 = -1;
  v1 = 0;
  v11 = 0;
  v10 = 0;
  memset(Parameter, 0, sizeof(Parameter));
  v13 = 0;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 16, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids);
  EventW = CreateEventW(0, 1, 0, 0);
  v10 = EventW;
  tlx::file_handle_traits::operator()(v3, 0);
  if ( (unsigned __int64)EventW + 1 > 1 )
  {
    *(_QWORD *)&Parameter[0] = EventW;
    v1 = CreateThread(0, 0, WctSyscallCalibratorThreadProc, Parameter, 0, &ThreadId);
    v11 = v1;
    tlx::file_handle_traits::operator()(v4, 0);
    if ( (unsigned __int64)v1 + 1 > 1 )
    {
      if ( (unsigned int)WctWaitUntilThreadIsBlocked(ThreadId)
        && NtQueryInformationThread(v1, ThreadLastSystemCall, &ThreadInformation, 0x18u, &ReturnLength) >= 0
        && ReturnLength == 24
        && WORD4(ThreadInformation) )
      {
        v0 = WORD4(ThreadInformation);
      }
      SetEvent(*(HANDLE *)&Parameter[0]);
      WaitForSingleObject(v1, 0xFFFFFFFF);
    }
  }
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 17, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids, v0);
  tlx::file_handle_traits::operator()(v5, EventW);
  tlx::file_handle_traits::operator()(v6, v1);
  return v0;
}

```

## disassembly

```asm
0x18003f3fc  push    rbp
0x18003f3fe  push    rbx
0x18003f3ff  push    rsi
0x18003f400  push    rdi
0x18003f401  push    r14
0x18003f403  push    r15
0x18003f405  lea     rbp, [rsp-2Fh]
0x18003f40a  sub     rsp, 0A8h
0x18003f411  mov     rax, cs:__security_cookie
0x18003f418  xor     rax, rsp
0x18003f41b  mov     [rbp+57h+var_38], rax
0x18003f41f  xorps   xmm0, xmm0
0x18003f422  xor     eax, eax
0x18003f424  movups  [rbp+57h+ThreadInformation], xmm0
0x18003f428  mov     [rbp+57h+var_40], rax
0x18003f42c  xor     r14d, r14d
0x18003f42f  mov     [rbp+57h+ReturnLength], r14d
0x18003f433  mov     [rbp+57h+ThreadId], r14d
0x18003f437  or      edi, 0FFFFFFFFh
0x18003f43a  mov     ebx, r14d
0x18003f43d  mov     [rbp+57h+var_90], rbx
0x18003f441  mov     [rbp+57h+var_98], r14
0x18003f445  movups  [rbp+57h+Parameter], xmm0
0x18003f449  movups  [rbp+57h+var_78], xmm0
0x18003f44d  movups  [rbp+57h+var_68], xmm0
0x18003f451  mov     [rbp+57h+var_58], rax
0x18003f455  lea     r15, WPP_GLOBAL_Control
0x18003f45c  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f463  cmp     rcx, r15
0x18003f466  jz      short loc_18003F481
0x18003f468  test    byte ptr [rcx+1Ch], 4
0x18003f46c  jz      short loc_18003F481
0x18003f46e  lea     edx, [rax+10h]
0x18003f471  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003f478  mov     rcx, [rcx+10h]
0x18003f47c  call    WPP_SF_
0x18003f481  xor     r9d, r9d; lpName
0x18003f484  xor     r8d, r8d; bInitialState
0x18003f487  lea     edx, [r9+1]; bManualReset
0x18003f48b  xor     ecx, ecx; lpEventAttributes
0x18003f48d  call    cs:__imp_CreateEventW
0x18003f494  nop     dword ptr [rax+rax+00h]
0x18003f499  mov     rsi, rax
0x18003f49c  mov     [rbp+57h+var_98], rax
0x18003f4a0  xor     edx, edx
0x18003f4a2  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f4a7  lea     rax, [rsi+1]
0x18003f4ab  cmp     rax, 1
0x18003f4af  jbe     loc_18003F568
0x18003f4b5  mov     qword ptr [rbp+57h+Parameter], rsi
0x18003f4b9  lea     rax, [rbp+57h+ThreadId]
0x18003f4bd  mov     [rsp+0D0h+lpThreadId], rax; lpThreadId
0x18003f4c2  mov     [rsp+0D0h+dwCreationFlags], r14d; dwCreationFlags
0x18003f4c7  lea     r9, [rbp+57h+Parameter]; lpParameter
0x18003f4cb  lea     r8, WctSyscallCalibratorThreadProc; lpStartAddress
0x18003f4d2  xor     edx, edx; dwStackSize
0x18003f4d4  xor     ecx, ecx; lpThreadAttributes
0x18003f4d6  call    cs:__imp_CreateThread
0x18003f4dd  nop     dword ptr [rax+rax+00h]
0x18003f4e2  mov     rbx, rax
0x18003f4e5  mov     [rbp+57h+var_90], rax
0x18003f4e9  xor     edx, edx
0x18003f4eb  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f4f0  lea     rax, [rbx+1]
0x18003f4f4  cmp     rax, 1
0x18003f4f8  jbe     short loc_18003F568
0x18003f4fa  mov     edx, 6
0x18003f4ff  mov     ecx, [rbp+57h+ThreadId]; unsigned int
0x18003f502  call    WctWaitUntilThreadIsBlocked
0x18003f507  test    eax, eax
0x18003f509  jz      short loc_18003F546
0x18003f50b  lea     rax, [rbp+57h+ReturnLength]
0x18003f50f  mov     qword ptr [rsp+0D0h+dwCreationFlags], rax; ReturnLength
0x18003f514  mov     r9d, 18h; ThreadInformationLength
0x18003f51a  lea     r8, [rbp+57h+ThreadInformation]; ThreadInformation
0x18003f51e  lea     edx, [r9-3]; ThreadInformationClass
0x18003f522  mov     rcx, rbx; ThreadHandle
0x18003f525  call    cs:__imp_NtQueryInformationThread
0x18003f52c  nop     dword ptr [rax+rax+00h]
0x18003f531  test    eax, eax
0x18003f533  js      short loc_18003F546
0x18003f535  cmp     [rbp+57h+ReturnLength], 18h
0x18003f539  jnz     short loc_18003F546
0x18003f53b  movzx   eax, word ptr [rbp+57h+ThreadInformation+8]
0x18003f53f  test    ax, ax
0x18003f542  jz      short loc_18003F546
0x18003f544  mov     edi, eax
0x18003f546  mov     rcx, qword ptr [rbp+57h+Parameter]; hEvent
0x18003f54a  call    cs:__imp_SetEvent
0x18003f551  nop     dword ptr [rax+rax+00h]
0x18003f556  or      edx, 0FFFFFFFFh; dwMilliseconds
0x18003f559  mov     rcx, rbx; hHandle
0x18003f55c  call    cs:__imp_WaitForSingleObject
0x18003f563  nop     dword ptr [rax+rax+00h]
0x18003f568  mov     rcx, cs:WPP_GLOBAL_Control
0x18003f56f  cmp     rcx, r15
0x18003f572  jz      short loc_18003F593
0x18003f574  test    byte ptr [rcx+1Ch], 4
0x18003f578  jz      short loc_18003F593
0x18003f57a  mov     edx, 11h
0x18003f57f  mov     r9d, edi
0x18003f582  lea     r8, WPP_274c2ad4ba1636e1b208947a9db1f3a0_Traceguids
0x18003f589  mov     rcx, [rcx+10h]
0x18003f58d  call    WPP_SF_d
0x18003f592  nop
0x18003f593  mov     rdx, rsi
0x18003f596  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f59b  nop
0x18003f59c  mov     rdx, rbx
0x18003f59f  call    ??Rfile_handle_traits@tlx@@QEBAXPEAX@Z; tlx::file_handle_traits::operator()(void *)
0x18003f5a4  mov     eax, edi
0x18003f5a6  mov     rcx, [rbp+57h+var_38]
0x18003f5aa  xor     rcx, rsp; StackCookie
0x18003f5ad  call    __security_check_cookie
0x18003f5b2  add     rsp, 0A8h
0x18003f5b9  pop     r15
0x18003f5bb  pop     r14
0x18003f5bd  pop     rdi
0x18003f5be  pop     rsi
0x18003f5bf  pop     rbx
0x18003f5c0  pop     rbp
0x18003f5c1  retn
```
