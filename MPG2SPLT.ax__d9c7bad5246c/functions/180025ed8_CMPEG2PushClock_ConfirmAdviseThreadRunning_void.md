# CMPEG2PushClock::ConfirmAdviseThreadRunning_(void)

- ea: `0x180025ed8`
- end: `0x180025f9f`
- name: `?ConfirmAdviseThreadRunning_@CMPEG2PushClock@@AEAAJXZ`
- size: `199`
- prototype: `__int64 __fastcall(CMPEG2PushClock *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800259a0`
- `0x180025af8`

## callees

- `0x180025ed8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180025f61`
- `KERNEL32!GetLastError` at `0x180025f61`
- `KERNEL32!SetThreadPriority` at `0x180025f91`
- `KERNEL32!SetThreadPriority` at `0x180025f91`
- `KERNEL32!CreateThread` at `0x180025f4f`
- `KERNEL32!CreateThread` at `0x180025f4f`
- `WINMM!timeGetDevCaps` at `0x180025f0a`
- `WINMM!timeGetDevCaps` at `0x180025f0a`
- `WINMM!timeEndPeriod` at `0x180025f71`
- `WINMM!timeEndPeriod` at `0x180025f71`
- `WINMM!timeBeginPeriod` at `0x180025f29`
- `WINMM!timeBeginPeriod` at `0x180025f29`

## pseudocode

```c
__int64 __fastcall CMPEG2PushClock::ConfirmAdviseThreadRunning_(CMPEG2PushClock *this)
{
  bool v1; // zf
  MMRESULT DevCaps; // eax
  UINT wPeriodMin; // ecx
  HANDLE v5; // rax
  DWORD LastError; // eax
  UINT v7; // ecx
  __int64 result; // rax
  DWORD ThreadId; // [rsp+40h] [rbp+8h] BYREF
  timecaps_tag ptc; // [rsp+48h] [rbp+10h] BYREF

  v1 = *((_QWORD *)this + 37) == 0;
  ThreadId = 0;
  ptc = 0;
  if ( !v1 )
    return 0;
  DevCaps = timeGetDevCaps(&ptc, 8u);
  wPeriodMin = 10;
  if ( !DevCaps && ptc.wPeriodMin >= 0xA )
    wPeriodMin = ptc.wPeriodMin;
  *((_DWORD *)this + 114) = wPeriodMin;
  timeBeginPeriod(wPeriodMin);
  v5 = CreateThread(0, 0, CMPEG2PushClock::ThreadEntry, this, 0, &ThreadId);
  *((_QWORD *)this + 37) = v5;
  if ( v5 )
  {
    SetThreadPriority(v5, 15);
    return 0;
  }
  LastError = GetLastError();
  v7 = *((_DWORD *)this + 114);
  ThreadId = LastError;
  timeEndPeriod(v7);
  result = ThreadId;
  if ( (int)ThreadId > 0 )
    return (unsigned __int16)ThreadId | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180025ed8  push    rbx
0x180025eda  sub     rsp, 30h
0x180025ede  cmp     qword ptr [rcx+128h], 0
0x180025ee6  mov     rbx, rcx
0x180025ee9  mov     [rsp+38h+ThreadId], 0
0x180025ef1  mov     qword ptr [rsp+38h+ptc.wPeriodMin], 0
0x180025efa  jnz     loc_180025F97
0x180025f00  mov     edx, 8; cbtc
0x180025f05  lea     rcx, [rsp+38h+ptc]; ptc
0x180025f0a  call    cs:__imp_timeGetDevCaps
0x180025f10  mov     ecx, 0Ah
0x180025f15  test    eax, eax
0x180025f17  jnz     short loc_180025F23
0x180025f19  cmp     [rsp+38h+ptc.wPeriodMin], ecx
0x180025f1d  jb      short loc_180025F23
0x180025f1f  mov     ecx, [rsp+38h+ptc.wPeriodMin]; uPeriod
0x180025f23  mov     [rbx+1C8h], ecx
0x180025f29  call    cs:__imp_timeBeginPeriod
0x180025f2f  lea     rax, [rsp+38h+ThreadId]
0x180025f34  mov     r9, rbx; lpParameter
0x180025f37  mov     [rsp+38h+lpThreadId], rax; lpThreadId
0x180025f3c  lea     r8, ?ThreadEntry@CMPEG2PushClock@@SAKPEAX@Z; lpStartAddress
0x180025f43  xor     edx, edx; dwStackSize
0x180025f45  mov     [rsp+38h+dwCreationFlags], 0; dwCreationFlags
0x180025f4d  xor     ecx, ecx; lpThreadAttributes
0x180025f4f  call    cs:__imp_CreateThread
0x180025f55  mov     [rbx+128h], rax
0x180025f5c  test    rax, rax
0x180025f5f  jnz     short loc_180025F89
0x180025f61  call    cs:__imp_GetLastError
0x180025f67  mov     ecx, [rbx+1C8h]; uPeriod
0x180025f6d  mov     [rsp+38h+ThreadId], eax
0x180025f71  call    cs:__imp_timeEndPeriod
0x180025f77  mov     eax, [rsp+38h+ThreadId]
0x180025f7b  test    eax, eax
0x180025f7d  jle     short loc_180025F99
0x180025f7f  movzx   eax, ax
0x180025f82  or      eax, 80070000h
0x180025f87  jmp     short loc_180025F99
0x180025f89  mov     edx, 0Fh; nPriority
0x180025f8e  mov     rcx, rax; hThread
0x180025f91  call    cs:__imp_SetThreadPriority
0x180025f97  xor     eax, eax
0x180025f99  add     rsp, 30h
0x180025f9d  pop     rbx
0x180025f9e  retn
```
