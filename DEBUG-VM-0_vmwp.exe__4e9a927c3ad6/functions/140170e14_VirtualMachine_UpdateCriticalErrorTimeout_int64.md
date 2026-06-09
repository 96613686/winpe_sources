# VirtualMachine::UpdateCriticalErrorTimeout(__int64)

- ea: `0x140170e14`
- end: `0x140170f74`
- name: `?UpdateCriticalErrorTimeout@VirtualMachine@@AEAAX_J@Z`
- size: `352`
- prototype: `void __fastcall(VirtualMachine *__hidden this, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x14006a530`

## callees

- `0x140132940`
- `0x140170510`
- `0x140170e14`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140170e47`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140170e47`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140170f4a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x140170f4a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140170f1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x140170f1f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x140170e8a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimerEx` at `0x140170e8a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140170eac`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140170eac`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall VirtualMachine::UpdateCriticalErrorTimeout(VirtualMachine *this, __int64 a2)
{
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  char i; // al
  struct _FILETIME v6; // rax
  __int64 v7; // rcx
  struct _FILETIME SystemTimeAsFileTime; // [rsp+38h] [rbp-20h] BYREF

  v4 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 2456);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 2456));
  for ( i = 1; i && *((_QWORD *)this + 306) != a2; i = 0 )
  {
    if ( !*((_DWORD *)this + 626) )
    {
      *((_QWORD *)this + 306) = a2;
      break;
    }
    if ( !SetThreadpoolTimerEx(*((PTP_TIMER *)this + 312), 0, 0, 0) )
      break;
    SystemTimeAsFileTime = 0;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v6 = SystemTimeAsFileTime;
    v7 = *(_QWORD *)((char *)this + 2508);
    if ( *(_QWORD *)&SystemTimeAsFileTime >= 10000000 * a2 + v7 )
    {
      VirtualMachine::StopCritical(this);
      break;
    }
    *((_QWORD *)this + 306) = a2;
    SystemTimeAsFileTime = (struct _FILETIME)(*(_QWORD *)&v6 - 10000000 * a2 - v7);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 312), &SystemTimeAsFileTime, 0, 0);
  }
  LeaveCriticalSection(v4);
}

```

## disassembly

```asm
0x140170e14  mov     [rsp+arg_10], rbx
0x140170e19  mov     [rsp+arg_18], rsi
0x140170e1e  push    rdi
0x140170e1f  sub     rsp, 50h
0x140170e23  mov     rax, cs:__security_cookie
0x140170e2a  xor     rax, rsp
0x140170e2d  mov     [rsp+58h+var_18], rax
0x140170e32  mov     rsi, rdx
0x140170e35  mov     rbx, rcx
0x140170e38  lea     rdi, [rcx+998h]
0x140170e3f  mov     [rsp+58h+var_30], rdi
0x140170e44  mov     rcx, rdi; lpCriticalSection
0x140170e47  call    cs:__imp_EnterCriticalSection
0x140170e4e  nop     dword ptr [rax+rax+00h]
0x140170e53  mov     al, 1
0x140170e55  mov     [rsp+58h+var_28], al
0x140170e59  test    al, al
0x140170e5b  jz      loc_140170F47
0x140170e61  cmp     [rbx+990h], rsi
0x140170e68  jz      loc_140170F47
0x140170e6e  cmp     dword ptr [rbx+9C8h], 0
0x140170e75  jz      loc_140170F40
0x140170e7b  xor     r9d, r9d; msWindowLength
0x140170e7e  xor     r8d, r8d; msPeriod
0x140170e81  xor     edx, edx; pftDueTime
0x140170e83  mov     rcx, [rbx+9C0h]; pti
0x140170e8a  call    cs:__imp_SetThreadpoolTimerEx
0x140170e91  nop     dword ptr [rax+rax+00h]
0x140170e96  test    eax, eax
0x140170e98  jz      loc_140170F47
0x140170e9e  mov     qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], 0
0x140170ea7  lea     rcx, [rsp+58h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140170eac  call    cs:__imp_GetSystemTimeAsFileTime
0x140170eb3  nop     dword ptr [rax+rax+00h]
0x140170eb8  mov     rax, qword ptr [rsp+58h+SystemTimeAsFileTime.dwLowDateTime]
0x140170ebd  mov     [rsp+58h+var_38], rax
0x140170ec2  mov     ecx, [rbx+9CCh]
0x140170ec8  mov     dword ptr [rsp+58h+var_38], ecx
0x140170ecc  mov     ecx, [rbx+9D0h]
0x140170ed2  mov     dword ptr [rsp+58h+var_38+4], ecx
0x140170ed6  imul    r8, rsi, 989680h
0x140170edd  mov     rcx, [rsp+58h+var_38]
0x140170ee2  lea     rdx, [r8+rcx]
0x140170ee6  cmp     rax, rdx
0x140170ee9  jge     short loc_140170F36
0x140170eeb  mov     [rbx+990h], rsi
0x140170ef2  sub     rax, r8
0x140170ef5  sub     rax, rcx
0x140170ef8  mov     [rsp+58h+var_38], rax
0x140170efd  shr     rax, 20h
0x140170f01  mov     [rsp+58h+SystemTimeAsFileTime.dwHighDateTime], eax
0x140170f05  mov     eax, dword ptr [rsp+58h+var_38]
0x140170f09  mov     [rsp+58h+SystemTimeAsFileTime.dwLowDateTime], eax
0x140170f0d  xor     r9d, r9d; msWindowLength
0x140170f10  xor     r8d, r8d; msPeriod
0x140170f13  lea     rdx, [rsp+58h+SystemTimeAsFileTime]; pftDueTime
0x140170f18  mov     rcx, [rbx+9C0h]; pti
0x140170f1f  call    cs:__imp_SetThreadpoolTimer
0x140170f26  nop     dword ptr [rax+rax+00h]
0x140170f2b  xor     al, al
0x140170f2d  mov     [rsp+58h+var_28], al
0x140170f31  jmp     loc_140170E59
0x140170f36  mov     rcx, rbx; this
0x140170f39  call    ?StopCritical@VirtualMachine@@AEAAJXZ; VirtualMachine::StopCritical(void)
0x140170f3e  jmp     short loc_140170F47
0x140170f40  mov     [rbx+990h], rsi
0x140170f47  mov     rcx, rdi; lpCriticalSection
0x140170f4a  call    cs:__imp_LeaveCriticalSection
0x140170f51  nop     dword ptr [rax+rax+00h]
0x140170f56  mov     rcx, [rsp+58h+var_18]
0x140170f5b  xor     rcx, rsp; StackCookie
0x140170f5e  call    __security_check_cookie
0x140170f63  mov     rbx, [rsp+58h+arg_10]
0x140170f68  mov     rsi, [rsp+58h+arg_18]
0x140170f6d  add     rsp, 50h
0x140170f71  pop     rdi
0x140170f72  retn
```
