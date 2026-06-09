# PdcManager::PdcHandler::DisplayStateNotificationCallback(void *,ulong,void *)

- ea: `0x18007f5b0`
- end: `0x18007f691`
- name: `?DisplayStateNotificationCallback@PdcHandler@PdcManager@@CAKPEAXK0@Z`
- size: `225`
- prototype: `unsigned int __fastcall(void *, unsigned int, void *)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x180027630`
- `0x18003a08c`
- `0x18007f5b0`
- `0x18007f698`
- `0x18007f778`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f683`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18007f683`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007f64a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18007f64a`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18007f614`
- `api-ms-win-core-threadpool-l1-2-0!IsThreadpoolTimerSet` at `0x18007f614`

## pseudocode

```c
__int64 __fastcall PdcManager::PdcHandler::DisplayStateNotificationCallback(PTP_TIMER *a1, int a2, _QWORD *a3)
{
  __int64 v4; // rax
  __int64 v5; // rdx
  __int64 v6; // rcx
  LPCRITICAL_SECTION lpCriticalSection; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v9[32]; // [rsp+28h] [rbp-20h] BYREF

  if ( a2 == 32787 )
  {
    v4 = *a3 - *(_QWORD *)&GUID_CONSOLE_DISPLAY_STATE.Data1;
    if ( *a3 == *(_QWORD *)&GUID_CONSOLE_DISPLAY_STATE.Data1 )
      v4 = a3[1] - *(_QWORD *)GUID_CONSOLE_DISPLAY_STATE.Data4;
    if ( !v4 && *((_DWORD *)a3 + 4) == 4 && *((_DWORD *)a3 + 5) )
    {
      lpCriticalSection = 0;
      wil::EnterCriticalSection(&lpCriticalSection, a1 + 4);
      if ( IsThreadpoolTimerSet(a1[296]) )
      {
        SetThreadpoolTimer(a1[296], 0, 0, 0);
        wil::basic_zstring_view<char>::basic_zstring_view<char>(v9, "DisplayTurnedOn");
        PublishPendingGlobalPowerState(a1 + 23, a1 + 24, v9);
      }
      else
      {
        if ( *((_BYTE *)a1 + 188) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5);
        if ( *((_BYTE *)a1 + 196) )
          MicrosoftTelemetryAssertTriggeredNoArgs(v6, v5);
      }
      if ( lpCriticalSection )
        LeaveCriticalSection(lpCriticalSection);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18007f5b0  push    rbx
0x18007f5b2  sub     rsp, 40h
0x18007f5b6  mov     rbx, rcx
0x18007f5b9  cmp     edx, 8013h
0x18007f5bf  jnz     loc_18007F689
0x18007f5c5  mov     rax, [r8]
0x18007f5c8  sub     rax, qword ptr cs:GUID_CONSOLE_DISPLAY_STATE.Data1
0x18007f5cf  jnz     short loc_18007F5DC
0x18007f5d1  mov     rax, [r8+8]
0x18007f5d5  sub     rax, qword ptr cs:GUID_CONSOLE_DISPLAY_STATE.Data4
0x18007f5dc  test    rax, rax
0x18007f5df  jnz     loc_18007F689
0x18007f5e5  cmp     dword ptr [r8+10h], 4
0x18007f5ea  jnz     loc_18007F689
0x18007f5f0  cmp     [r8+14h], eax
0x18007f5f4  jz      loc_18007F689
0x18007f5fa  mov     [rsp+48h+lpCriticalSection], rax
0x18007f5ff  lea     rdx, [rcx+20h]
0x18007f603  lea     rcx, [rsp+48h+lpCriticalSection]
0x18007f608  call    ?EnterCriticalSection@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_CRITICAL_SECTION@@@Z; wil::EnterCriticalSection(_RTL_CRITICAL_SECTION *)
0x18007f60d  mov     rcx, [rbx+940h]; pti
0x18007f614  call    cs:__imp_IsThreadpoolTimerSet
0x18007f61a  test    eax, eax
0x18007f61c  jnz     short loc_18007F63B
0x18007f61e  cmp     [rbx+0BCh], al
0x18007f624  jz      short loc_18007F62B
0x18007f626  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007f62b  cmp     byte ptr [rbx+0C4h], 0
0x18007f632  jz      short loc_18007F679
0x18007f634  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18007f639  jmp     short loc_18007F679
0x18007f63b  xor     r9d, r9d; msWindowLength
0x18007f63e  xor     r8d, r8d; msPeriod
0x18007f641  xor     edx, edx; pftDueTime
0x18007f643  mov     rcx, [rbx+940h]; pti
0x18007f64a  call    cs:__imp_SetThreadpoolTimer
0x18007f650  lea     rdx, aDisplayturnedo; "DisplayTurnedOn"
0x18007f657  lea     rcx, [rsp+48h+var_20]
0x18007f65c  call    ??$?0$0BA@@?$basic_zstring_view@D@wil@@QEAA@AEAY0BA@$$CBD@Z; wil::basic_zstring_view<char>::basic_zstring_view<char>(char const (&)[16])
0x18007f661  lea     rdx, [rbx+0C0h]
0x18007f668  lea     rcx, [rbx+0B8h]
0x18007f66f  lea     r8, [rsp+48h+var_20]
0x18007f674  call    PublishPendingGlobalPowerState
0x18007f679  mov     rcx, [rsp+48h+lpCriticalSection]; lpCriticalSection
0x18007f67e  test    rcx, rcx
0x18007f681  jz      short loc_18007F689
0x18007f683  call    cs:__imp_LeaveCriticalSection
0x18007f689  xor     eax, eax
0x18007f68b  add     rsp, 40h
0x18007f68f  pop     rbx
0x18007f690  retn
```
