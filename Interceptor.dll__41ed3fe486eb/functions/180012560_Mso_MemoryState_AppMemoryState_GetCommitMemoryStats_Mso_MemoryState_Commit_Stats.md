# Mso::MemoryState::AppMemoryState::GetCommitMemoryStats(Mso::MemoryState::Commit_Stats *)

- ea: `0x180012560`
- end: `0x18001261c`
- name: `?GetCommitMemoryStats@AppMemoryState@MemoryState@Mso@@UEBA_NPEAUCommit_Stats@23@@Z`
- size: `188`
- prototype: `bool __fastcall(Mso::MemoryState::AppMemoryState *__hidden this, struct Mso::MemoryState::Commit_Stats *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180012560`
- `0x18001410c`
- `0x1800266e0`
- `0x18002b400`

## import_xrefs

- `KERNEL32!GetCurrentProcess` at `0x1800125bc`
- `KERNEL32!GetCurrentProcess` at `0x1800125bc`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x1800125d0`
- `KERNEL32!K32GetProcessMemoryInfo` at `0x1800125d0`

## string_xrefs

- `0x1800125da`: `GetProcessMemoryInfo failed for GetCommitMemoryStats`

## pseudocode

```c
char __fastcall Mso::MemoryState::AppMemoryState::GetCommitMemoryStats(
        Mso::MemoryState::AppMemoryState *this,
        struct Mso::MemoryState::Commit_Stats *a2)
{
  HANDLE CurrentProcess; // rax
  __int64 v5; // r8
  _BYTE ppsmemCounters[80]; // [rsp+20h] [rbp-68h] BYREF

  memset(ppsmemCounters, 0, sizeof(ppsmemCounters));
  *(_DWORD *)ppsmemCounters = 80;
  if ( !a2 )
    return 0;
  *((_QWORD *)a2 + 1) = 0;
  *((_QWORD *)a2 + 2) = 0;
  *((_QWORD *)a2 + 3) = 0;
  *((_QWORD *)a2 + 4) = 0;
  CurrentProcess = GetCurrentProcess();
  if ( !K32GetProcessMemoryInfo(CurrentProcess, (PPROCESS_MEMORY_COUNTERS)ppsmemCounters, 0x50u) )
  {
    Mso::Logging::MsoSendStructuredTraceTag(
      8210338,
      1143,
      v5,
      L"GetProcessMemoryInfo failed for GetCommitMemoryStats",
      *(_QWORD *)ppsmemCounters);
    return 0;
  }
  *((_QWORD *)a2 + 1) = *(_QWORD *)&ppsmemCounters[72];
  *((_QWORD *)a2 + 2) = *(_QWORD *)&ppsmemCounters[64];
  return 1;
}

```

## disassembly

```asm
0x180012560  push    rbx
0x180012562  sub     rsp, 80h
0x180012569  mov     rax, cs:__security_cookie
0x180012570  xor     rax, rsp
0x180012573  mov     [rsp+88h+var_18], rax
0x180012578  mov     rbx, rdx
0x18001257b  lea     rcx, [rsp+88h+ppsmemCounters]; void *
0x180012580  xor     edx, edx; Val
0x180012582  lea     r8d, [rdx+50h]; Size
0x180012586  call    memset
0x18001258b  mov     [rsp+88h+ppsmemCounters.cb], 50h ; 'P'
0x180012593  test    rbx, rbx
0x180012596  jnz     short loc_18001259C
0x180012598  xor     al, al
0x18001259a  jmp     short loc_180012606
0x18001259c  mov     qword ptr [rbx+8], 0
0x1800125a4  mov     qword ptr [rbx+10h], 0
0x1800125ac  mov     qword ptr [rbx+18h], 0
0x1800125b4  mov     qword ptr [rbx+20h], 0
0x1800125bc  call    cs:__imp_GetCurrentProcess
0x1800125c2  mov     r8d, 50h ; 'P'; cb
0x1800125c8  lea     rdx, [rsp+88h+ppsmemCounters]; ppsmemCounters
0x1800125cd  mov     rcx, rax; Process
0x1800125d0  call    cs:__imp_K32GetProcessMemoryInfo
0x1800125d6  test    eax, eax
0x1800125d8  jnz     short loc_1800125F2
0x1800125da  lea     r9, aGetprocessmemo_0; "GetProcessMemoryInfo failed for GetComm"...
0x1800125e1  mov     edx, 477h
0x1800125e6  mov     ecx, 7D47A2h
0x1800125eb  call    ?MsoSendStructuredTraceTag@Logging@Mso@@YAXKW4Category@12@W4Severity@12@PEB_W@Z; Mso::Logging::MsoSendStructuredTraceTag(ulong,Mso::Logging::Category,Mso::Logging::Severity,wchar_t const *)
0x1800125f0  jmp     short loc_180012598
0x1800125f2  mov     rax, [rsp+88h+var_20]
0x1800125f7  mov     [rbx+8], rax
0x1800125fb  mov     rax, [rsp+88h+ppsmemCounters.PeakPagefileUsage]
0x180012600  mov     [rbx+10h], rax
0x180012604  mov     al, 1
0x180012606  mov     rcx, [rsp+88h+var_18]
0x18001260b  xor     rcx, rsp; StackCookie
0x18001260e  call    __security_check_cookie
0x180012613  add     rsp, 80h
0x18001261a  pop     rbx
0x18001261b  retn
```
