# PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::SetSnoozeTimer(TimeValue const &,TimeValue const &)

- ea: `0x18001d4e8`
- end: `0x18001d5ea`
- name: `?SetSnoozeTimer@TriggerPeriodicBase@PRIVATE_NAMESPACE_Triggers_H@@AEAAJAEBVTimeValue@@0@Z`
- size: `258`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this, const struct TimeValue *, const struct TimeValue *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a160`

## callees

- `0x180001cd0`
- `0x180005c30`
- `0x18000d8c0`
- `0x18001d4e8`
- `0x180020c30`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d533`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18001d533`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d54a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d5a6`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d54a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18001d5a6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5ae`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d5ae`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase::SetSnoozeTimer(
        PRIVATE_NAMESPACE_Triggers_H::TriggerPeriodicBase *this,
        const struct TimeValue *a2,
        const struct TimeValue *a3)
{
  struct _TP_TIMER *v5; // rcx
  unsigned int v6; // ebx
  struct _TP_TIMER *v7; // rcx
  signed int LastError; // eax
  struct _FILETIME pftDueTime; // [rsp+20h] [rbp-138h] BYREF
  TIME_ZONE_INFORMATION TimeZoneInformation; // [rsp+30h] [rbp-128h] BYREF
  struct _FILETIME v12; // [rsp+120h] [rbp-38h]

  v5 = (struct _TP_TIMER *)*((_QWORD *)this + 55);
  if ( v5 )
    SetThreadpoolTimer(v5, 0, 0, 0);
  else
    *((_QWORD *)this + 55) = CreateThreadpoolTimer(
                               CScheduleMgr::BaseSnoozeCallback,
                               *((PVOID *)this + 22),
                               &ThreadpoolCallBackEnvironment);
  if ( *((_QWORD *)this + 55) )
  {
    v6 = 0;
    TimeInfo::TimeInfo(&TimeZoneInformation);
    if ( (*(_BYTE *)(*((_QWORD *)this + 22) + 44LL) & 8) != 0 )
      TimeInfo::SetUTC(&TimeZoneInformation, a3);
    else
      TimeInfo::SetLocal(&TimeZoneInformation, (SYSTEMTIME *)a3);
    v7 = (struct _TP_TIMER *)*((_QWORD *)this + 55);
    pftDueTime = v12;
    SetThreadpoolTimer(v7, &pftDueTime, 0, 0);
  }
  else
  {
    LastError = GetLastError();
    v6 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return v6;
}

```

## disassembly

```asm
0x18001d4e8  mov     [rsp+arg_8], rbx
0x18001d4ed  mov     [rsp+arg_10], rsi
0x18001d4f2  push    rdi
0x18001d4f3  sub     rsp, 150h
0x18001d4fa  mov     rax, cs:__security_cookie
0x18001d501  xor     rax, rsp
0x18001d504  mov     [rsp+158h+var_18], rax
0x18001d50c  mov     rdi, rcx
0x18001d50f  mov     rsi, r8
0x18001d512  mov     rcx, [rcx+1B8h]; pti
0x18001d519  test    rcx, rcx
0x18001d51c  jnz     short loc_18001D542
0x18001d51e  mov     rdx, [rdi+0B0h]; pv
0x18001d525  lea     r8, ?ThreadpoolCallBackEnvironment@@3U_TP_CALLBACK_ENVIRON_V3@@A; pcbe
0x18001d52c  lea     rcx, ?BaseSnoozeCallback@CScheduleMgr@@SAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18001d533  call    cs:__imp_CreateThreadpoolTimer
0x18001d539  mov     [rdi+1B8h], rax
0x18001d540  jmp     short loc_18001D550
0x18001d542  xor     r9d, r9d; msWindowLength
0x18001d545  xor     r8d, r8d; msPeriod
0x18001d548  xor     edx, edx; pftDueTime
0x18001d54a  call    cs:__imp_SetThreadpoolTimer
0x18001d550  cmp     qword ptr [rdi+1B8h], 0
0x18001d558  jz      short loc_18001D5AE
0x18001d55a  lea     rcx, [rsp+158h+TimeZoneInformation]; lpTimeZoneInformation
0x18001d55f  xor     ebx, ebx
0x18001d561  call    ??0TimeInfo@@QEAA@XZ; TimeInfo::TimeInfo(void)
0x18001d566  mov     rax, [rdi+0B0h]
0x18001d56d  lea     rcx, [rsp+158h+TimeZoneInformation]; lpTimeZoneInformation
0x18001d572  mov     rdx, rsi; struct TimeValue *
0x18001d575  test    byte ptr [rax+2Ch], 8
0x18001d579  jz      short loc_18001D582
0x18001d57b  call    ?SetUTC@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetUTC(TimeValue const &)
0x18001d580  jmp     short loc_18001D587
0x18001d582  call    ?SetLocal@TimeInfo@@QEAAXAEBVTimeValue@@@Z; TimeInfo::SetLocal(TimeValue const &)
0x18001d587  mov     rax, [rsp+158h+var_38]
0x18001d58f  lea     rdx, [rsp+158h+pftDueTime]; pftDueTime
0x18001d594  mov     rcx, [rdi+1B8h]; pti
0x18001d59b  xor     r9d, r9d; msWindowLength
0x18001d59e  xor     r8d, r8d; msPeriod
0x18001d5a1  mov     qword ptr [rsp+158h+pftDueTime.dwLowDateTime], rax
0x18001d5a6  call    cs:__imp_SetThreadpoolTimer
0x18001d5ac  jmp     short loc_18001D5C3
0x18001d5ae  call    cs:__imp_GetLastError
0x18001d5b4  mov     ebx, eax
0x18001d5b6  test    eax, eax
0x18001d5b8  jle     short loc_18001D5C3
0x18001d5ba  movzx   ebx, ax
0x18001d5bd  or      ebx, 80070000h
0x18001d5c3  mov     eax, ebx
0x18001d5c5  mov     rcx, [rsp+158h+var_18]
0x18001d5cd  xor     rcx, rsp; StackCookie
0x18001d5d0  call    __security_check_cookie
0x18001d5d5  lea     r11, [rsp+158h+var_8]
0x18001d5dd  mov     rbx, [r11+18h]
0x18001d5e1  mov     rsi, [r11+20h]
0x18001d5e5  mov     rsp, r11
0x18001d5e8  pop     rdi
0x18001d5e9  retn
```
