# Windows::Networking::UX::Internal::MBStateBase::DeleteTimer(void)

- ea: `0x18004fdd0`
- end: `0x18004fe5b`
- name: `?DeleteTimer@MBStateBase@Internal@UX@Networking@Windows@@IEAAXXZ`
- size: `139`
- prototype: `void __fastcall(Windows::Networking::UX::Internal::MBStateBase *__hidden this)`
- caller_count: `5`
- callee_count: `4`
- tags: ``

## callers

- `0x18002bc08`
- `0x18004fb28`
- `0x1800503f0`
- `0x180050450`
- `0x180050510`

## callees

- `0x180008c84`
- `0x18000ccb0`
- `0x18004fdd0`
- `0x1800504a4`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18004fe01`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18004fe01`

## string_xrefs

- `0x18004fde0`: `Windows::Networking::UX::Internal::MBStateBase::DeleteTimer`
- `0x18004fe32`: `Windows::Networking::UX::Internal::MBStateBase::DeleteTimer`
- `0x18004fe4a`: `Windows::Networking::UX::Internal::MBStateBase::DeleteTimer`

## pseudocode

```c
void __fastcall Windows::Networking::UX::Internal::MBStateBase::DeleteTimer(
        Windows::Networking::UX::Internal::MBStateBase *this)
{
  void *v2; // rdx
  unsigned int v3; // r8d
  const char *v4; // r9
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  MBSettingUXLogging::Verbose("Windows::Networking::UX::Internal::MBStateBase::DeleteTimer", 124, "Enter");
  v2 = (void *)*((_QWORD *)this + 11);
  if ( v2 == (void *)-1LL )
  {
    MBSettingUXLogging::Error(
      "Windows::Networking::UX::Internal::MBStateBase::DeleteTimer",
      0x8Au,
      "Timer isn't running.");
  }
  else if ( DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL) )
  {
    *((_QWORD *)this + 11) = -1;
  }
  else
  {
    wil::details::in1diag3::Log_GetLastError(retaddr, (void *)0x85, v3, v4);
  }
  MBSettingUXLogging::Verbose("Windows::Networking::UX::Internal::MBStateBase::DeleteTimer", 140, "Exit");
}

```

## disassembly

```asm
0x18004fdd0  push    rbx
0x18004fdd2  sub     rsp, 20h
0x18004fdd6  mov     rbx, rcx
0x18004fdd9  lea     r8, aEnter; "Enter"
0x18004fde0  lea     rcx, aWindowsNetwork_299; "Windows::Networking::UX::Internal::MBSt"...
0x18004fde7  mov     edx, 7Ch ; '|'; unsigned int
0x18004fdec  call    ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
0x18004fdf1  mov     rdx, [rbx+58h]; Timer
0x18004fdf5  cmp     rdx, 0FFFFFFFFFFFFFFFFh
0x18004fdf9  jz      short loc_18004FE26
0x18004fdfb  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18004fdff  xor     ecx, ecx; TimerQueue
0x18004fe01  call    cs:__imp_DeleteTimerQueueTimer
0x18004fe07  test    eax, eax
0x18004fe09  jz      short loc_18004FE15
0x18004fe0b  mov     qword ptr [rbx+58h], 0FFFFFFFFFFFFFFFFh
0x18004fe13  jmp     short loc_18004FE3E
0x18004fe15  mov     rcx, [rsp+28h]; this
0x18004fe1a  mov     edx, 85h; void *
0x18004fe1f  call    ?Log_GetLastError@in1diag3@details@wil@@YAKPEAXIPEBD@Z; wil::details::in1diag3::Log_GetLastError(void *,uint,char const *)
0x18004fe24  jmp     short loc_18004FE3E
0x18004fe26  lea     r8, aTimerIsnTRunni; "Timer isn't running."
0x18004fe2d  mov     edx, 8Ah; unsigned int
0x18004fe32  lea     rcx, aWindowsNetwork_299; "Windows::Networking::UX::Internal::MBSt"...
0x18004fe39  call    ?Error@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Error(char const *,ulong,char const *,...)
0x18004fe3e  lea     r8, aExit; "Exit"
0x18004fe45  mov     edx, 8Ch; unsigned int
0x18004fe4a  lea     rcx, aWindowsNetwork_299; "Windows::Networking::UX::Internal::MBSt"...
0x18004fe51  add     rsp, 20h
0x18004fe55  pop     rbx
0x18004fe56  jmp     ?Verbose@MBSettingUXLogging@@SAXPEBDK0ZZ; MBSettingUXLogging::Verbose(char const *,ulong,char const *,...)
```
