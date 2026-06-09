# RmReportServiceStatus(ulong,ulong)

- ea: `0x180003180`
- end: `0x180003305`
- name: `?RmReportServiceStatus@@YAXKK@Z`
- size: `389`
- prototype: `void __fastcall(unsigned int, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x1800029e0`
- `0x180002f20`

## callees

- `0x180003180`
- `0x180003c70`
- `0x180003fd0`
- `0x18000d2a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032db`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800032db`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800031f8`
- `api-ms-win-service-core-l1-1-0!SetServiceStatus` at `0x1800031f8`

## pseudocode

```c
void __fastcall RmReportServiceStatus(DWORD a1)
{
  signed int LastError; // ebx
  __int64 v3; // rdx
  __int64 v4; // r8
  _SERVICE_STATUS ServiceStatus; // [rsp+60h] [rbp-38h] BYREF

  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
    WPP_SF_Dd(*(_QWORD *)(WPP_GLOBAL_Control + 16LL), 24, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids, a1, 0);
  ServiceStatus.dwServiceType = 32;
  ServiceStatus.dwCurrentState = a1;
  memset(&ServiceStatus.dwControlsAccepted, 0, 20);
  if ( a1 == 1 || a1 == 4 )
  {
    ServiceStatus.dwControlsAccepted = 1025;
  }
  else
  {
    ServiceStatus.dwWaitHint = 5000;
    ServiceStatus.dwCheckPoint = _InterlockedIncrement(&dword_180037EE0);
  }
  LastError = 0;
  if ( !SetServiceStatus(hServiceStatus, &ServiceStatus) )
    LastError = GetLastError();
  if ( (_UNKNOWN *)WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*(_BYTE *)(WPP_GLOBAL_Control + 28LL) & 4) != 0 )
  {
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    WPP_SF_DDDDDDDd(
      *(_QWORD *)(WPP_GLOBAL_Control + 16LL),
      v3,
      v4,
      ServiceStatus.dwServiceType,
      ServiceStatus.dwCurrentState,
      ServiceStatus.dwWin32ExitCode,
      ServiceStatus.dwServiceSpecificExitCode,
      ServiceStatus.dwCheckPoint,
      ServiceStatus.dwControlsAccepted,
      ServiceStatus.dwWaitHint,
      LastError);
  }
}

```

## disassembly

```asm
0x180003180  mov     [rsp+arg_8], rbx
0x180003185  mov     [rsp+arg_10], rsi
0x18000318a  push    rdi
0x18000318b  sub     rsp, 90h
0x180003192  mov     rax, cs:__security_cookie
0x180003199  xor     rax, rsp
0x18000319c  mov     [rsp+98h+var_18], rax
0x1800031a4  mov     ebx, ecx
0x1800031a6  mov     rcx, cs:WPP_GLOBAL_Control
0x1800031ad  lea     rsi, WPP_GLOBAL_Control
0x1800031b4  xor     edi, edi
0x1800031b6  cmp     rcx, rsi
0x1800031b9  jnz     loc_180003287
0x1800031bf  mov     [rsp+98h+ServiceStatus.dwServiceType], 20h ; ' '
0x1800031c7  mov     [rsp+98h+ServiceStatus.dwCurrentState], ebx
0x1800031cb  mov     qword ptr [rsp+98h+ServiceStatus.dwWin32ExitCode], rdi
0x1800031d0  mov     qword ptr [rsp+98h+ServiceStatus.dwCheckPoint], rdi
0x1800031d5  mov     [rsp+98h+ServiceStatus.dwControlsAccepted], edi
0x1800031d9  cmp     ebx, 1
0x1800031dc  jnz     loc_1800032B2
0x1800031e2  mov     [rsp+98h+ServiceStatus.dwControlsAccepted], 401h
0x1800031ea  mov     rcx, cs:hServiceStatus; hServiceStatus
0x1800031f1  lea     rdx, [rsp+98h+ServiceStatus]; lpServiceStatus
0x1800031f6  mov     ebx, edi
0x1800031f8  call    cs:__imp_SetServiceStatus
0x1800031fe  test    eax, eax
0x180003200  jz      loc_1800032DB
0x180003206  mov     rcx, cs:WPP_GLOBAL_Control
0x18000320d  cmp     rcx, rsi
0x180003210  jnz     loc_1800032E8
0x180003216  mov     rcx, [rsp+98h+var_18]
0x18000321e  xor     rcx, rsp; StackCookie
0x180003221  call    __security_check_cookie
0x180003226  lea     r11, [rsp+98h+var_8]
0x18000322e  mov     rbx, [r11+18h]
0x180003232  mov     rsi, [r11+20h]
0x180003236  mov     rsp, r11
0x180003239  pop     rdi
0x18000323a  retn
0x18000323b  test    ebx, ebx
0x18000323d  jg      loc_1800032F7
0x180003243  mov     eax, [rsp+98h+ServiceStatus.dwWaitHint]
0x180003247  mov     r9d, [rsp+98h+ServiceStatus.dwServiceType]
0x18000324c  mov     rcx, [rcx+10h]
0x180003250  mov     [rsp+98h+var_48], ebx
0x180003254  mov     [rsp+98h+var_50], eax
0x180003258  mov     eax, [rsp+98h+ServiceStatus.dwControlsAccepted]
0x18000325c  mov     [rsp+98h+var_58], eax
0x180003260  mov     eax, [rsp+98h+ServiceStatus.dwCheckPoint]
0x180003264  mov     [rsp+98h+var_60], eax
0x180003268  mov     eax, [rsp+98h+ServiceStatus.dwServiceSpecificExitCode]
0x18000326c  mov     [rsp+98h+var_68], eax
0x180003270  mov     eax, [rsp+98h+ServiceStatus.dwWin32ExitCode]
0x180003274  mov     [rsp+98h+var_70], eax
0x180003278  mov     eax, [rsp+98h+ServiceStatus.dwCurrentState]
0x18000327c  mov     [rsp+98h+var_78], eax
0x180003280  call    WPP_SF_DDDDDDDd
0x180003285  jmp     short loc_180003216
0x180003287  test    byte ptr [rcx+1Ch], 4
0x18000328b  jz      loc_1800031BF
0x180003291  mov     rcx, [rcx+10h]
0x180003295  lea     r8, WPP_d42538173eb033b5db6066a79c0c461a_Traceguids
0x18000329c  mov     edx, 18h
0x1800032a1  mov     [rsp+98h+var_78], edi
0x1800032a5  mov     r9d, ebx
0x1800032a8  call    WPP_SF_Dd
0x1800032ad  jmp     loc_1800031BF
0x1800032b2  cmp     ebx, 4
0x1800032b5  jz      loc_1800031E2
0x1800032bb  mov     eax, 1
0x1800032c0  lock xadd cs:dword_180037EE0, eax
0x1800032c8  inc     eax
0x1800032ca  mov     [rsp+98h+ServiceStatus.dwWaitHint], 1388h
0x1800032d2  mov     [rsp+98h+ServiceStatus.dwCheckPoint], eax
0x1800032d6  jmp     loc_1800031EA
0x1800032db  call    cs:__imp_GetLastError
0x1800032e1  mov     ebx, eax
0x1800032e3  jmp     loc_180003206
0x1800032e8  test    byte ptr [rcx+1Ch], 4
0x1800032ec  jz      loc_180003216
0x1800032f2  jmp     loc_18000323B
0x1800032f7  movzx   ebx, bx
0x1800032fa  or      ebx, 80070000h
0x180003300  jmp     loc_180003243
```
