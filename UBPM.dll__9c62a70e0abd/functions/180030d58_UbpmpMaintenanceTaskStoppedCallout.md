# UbpmpMaintenanceTaskStoppedCallout

- ea: `0x180030d58`
- end: `0x180030e9d`
- name: `UbpmpMaintenanceTaskStoppedCallout`
- size: `325`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: `service_task, broker_com_uri`

## callers

- `0x180007ec0`
- `0x180008430`
- `0x180009a30`
- `0x18000a230`

## callees

- `0x18001b74c`
- `0x180028fe8`
- `0x18002b784`
- `0x18002ee00`
- `0x18002f53c`
- `0x18002fc2c`
- `0x180030b14`
- `0x180030d58`
- `0x1800310dc`
- `0x180036d44`
- `0x180040260`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180030dfa`
- `api-ms-win-core-sysinfo-l1-1-0!GetLocalTime` at `0x180030dfa`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityStop` at `0x180030db8`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityStop` at `0x180030db8`

## pseudocode

```c
ULONG __fastcall UbpmpMaintenanceTaskStoppedCallout(__int64 a1, __int64 a2, __int64 a3)
{
  unsigned __int8 v3; // al
  char v4; // bp
  unsigned __int64 v5; // rdi
  __int64 v8; // r8
  __int64 v9; // r9
  unsigned int v10; // r8d
  unsigned int v11; // r9d
  __int64 v12; // rdx
  __int64 v13; // r8
  __int64 v14; // rcx
  __int64 v15; // rcx
  ULONG result; // eax
  int v17; // [rsp+30h] [rbp-48h] BYREF
  struct _SYSTEMTIME SystemTime; // [rsp+38h] [rbp-40h] BYREF

  v3 = *(_BYTE *)(a1 + 40);
  v4 = a3;
  v5 = (unsigned __int64)v3 << 6;
  SystemTime = 0;
  if ( v3 >= 5u )
    MicrosoftTelemetryAssertTriggeredNoArgs();
  LOBYTE(a3) = v4;
  UbpmTelemMaintenanceTaskStopped(a1, *(_QWORD *)(a2 + 112), a3);
  if ( *(_QWORD *)((char *)&g_MaintenancePilot + v5 + 104) )
    CrmActivityStop();
  UbpmTelemMaintenanceTaskRundown(1u, a1, *(_BYTE *)(a1 + 40));
  if ( *(_BYTE *)(*(_QWORD *)(*(_QWORD *)(a1 + 24) + 48LL) + 28LL) )
    byte_18004FC31 = 0;
  --*(_DWORD *)((char *)&g_MaintenancePilot + v5 + 124);
  if ( UbpmpMaintenanceTotalTasksRunning()
    || (GetLocalTime(&SystemTime),
        UbpmpReportMaintenanceState(&SystemTime, (const unsigned __int16 *)1, v10, v11),
        UbpmTakeMaintenancePdcReference(0, v12, v13),
        !(unsigned int)UbpmpCheckQueueMaintenanceLauncher()) )
  {
    if ( qword_18004FC48 )
    {
      v15 = *(_QWORD *)(a2 + 16);
      if ( v15 )
      {
        UbpmpSleepStudyStopReportingBlocker(v15, *(_QWORD *)(*(_QWORD *)(a1 + 24) + 8LL));
        v14 = 0;
        *(_QWORD *)(a2 + 16) = 0;
      }
      else
      {
        v14 = 30;
      }
    }
    else
    {
      v14 = 20;
    }
  }
  else
  {
    v14 = 10;
  }
  result = dword_18004F0F0;
  if ( (unsigned int)dword_18004F0F0 > 4 )
  {
    v17 = v14;
    return _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
             v14,
             (unsigned __int8 *)&word_1800470FE,
             v8,
             v9,
             (__int64)&v17);
  }
  return result;
}

```

## disassembly

```asm
0x180030d58  push    rbx
0x180030d5a  push    rbp
0x180030d5b  push    rsi
0x180030d5c  push    rdi
0x180030d5d  push    r14
0x180030d5f  sub     rsp, 50h
0x180030d63  mov     rax, cs:__security_cookie
0x180030d6a  xor     rax, rsp
0x180030d6d  mov     [rsp+78h+var_30], rax
0x180030d72  movzx   eax, byte ptr [rcx+28h]
0x180030d76  xorps   xmm0, xmm0
0x180030d79  mov     edi, eax
0x180030d7b  mov     bpl, r8b
0x180030d7e  shl     rdi, 6
0x180030d82  mov     rsi, rdx
0x180030d85  mov     rbx, rcx
0x180030d88  movups  xmmword ptr [rsp+78h+SystemTime.wYear], xmm0
0x180030d8d  cmp     al, 5
0x180030d8f  jb      short loc_180030D96
0x180030d91  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180030d96  mov     rdx, [rsi+70h]
0x180030d9a  mov     r8b, bpl
0x180030d9d  mov     rcx, rbx
0x180030da0  call    UbpmTelemMaintenanceTaskStopped
0x180030da5  lea     r14, ?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x180030dac  xor     ebp, ebp
0x180030dae  mov     rcx, [rdi+r14+68h]
0x180030db3  test    rcx, rcx
0x180030db6  jz      short loc_180030DC4
0x180030db8  call    cs:__imp_CrmActivityStop
0x180030dbf  nop     dword ptr [rax+rax+00h]
0x180030dc4  mov     r8b, [rbx+28h]
0x180030dc8  mov     rdx, rbx
0x180030dcb  mov     cl, 1
0x180030dcd  call    UbpmTelemMaintenanceTaskRundown
0x180030dd2  mov     rax, [rbx+18h]
0x180030dd6  mov     rcx, [rax+30h]
0x180030dda  cmp     [rcx+1Ch], bpl
0x180030dde  jz      short loc_180030DE7
0x180030de0  mov     cs:byte_18004FC31, bpl
0x180030de7  dec     dword ptr [rdi+r14+7Ch]
0x180030dec  call    ?UbpmpMaintenanceTotalTasksRunning@@YAKXZ; UbpmpMaintenanceTotalTasksRunning(void)
0x180030df1  test    eax, eax
0x180030df3  jnz     short loc_180030E2C
0x180030df5  lea     rcx, [rsp+78h+SystemTime]; lpSystemTime
0x180030dfa  call    cs:__imp_GetLocalTime
0x180030e01  nop     dword ptr [rax+rax+00h]
0x180030e06  mov     edx, 1; unsigned int
0x180030e0b  lea     rcx, [rsp+78h+SystemTime]; lpTime
0x180030e10  call    ?UbpmpReportMaintenanceState@@YAXPEAU_SYSTEMTIME@@K@Z; UbpmpReportMaintenanceState(_SYSTEMTIME *,ulong)
0x180030e15  xor     ecx, ecx; unsigned __int8
0x180030e17  call    ?UbpmTakeMaintenancePdcReference@@YAXE@Z; UbpmTakeMaintenancePdcReference(uchar)
0x180030e1c  call    UbpmpCheckQueueMaintenanceLauncher
0x180030e21  test    eax, eax
0x180030e23  jz      short loc_180030E2C
0x180030e25  mov     ecx, 0Ah
0x180030e2a  jmp     short loc_180030E5F
0x180030e2c  cmp     cs:qword_18004FC48, rbp
0x180030e33  jnz     short loc_180030E3C
0x180030e35  mov     ecx, 14h
0x180030e3a  jmp     short loc_180030E5F
0x180030e3c  mov     rcx, [rsi+10h]
0x180030e40  test    rcx, rcx
0x180030e43  jnz     short loc_180030E4C
0x180030e45  mov     ecx, 1Eh
0x180030e4a  jmp     short loc_180030E5F
0x180030e4c  mov     rdx, [rbx+18h]
0x180030e50  mov     rdx, [rdx+8]
0x180030e54  call    UbpmpSleepStudyStopReportingBlocker
0x180030e59  mov     ecx, ebp
0x180030e5b  mov     [rsi+10h], rbp
0x180030e5f  mov     eax, cs:dword_18004F0F0
0x180030e65  cmp     eax, 4
0x180030e68  jbe     short loc_180030E84
0x180030e6a  lea     rax, [rsp+78h+var_48]
0x180030e6f  mov     [rsp+78h+var_48], ecx
0x180030e73  lea     rdx, word_1800470FE
0x180030e7a  mov     [rsp+78h+var_58], rax
0x180030e7f  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180030e84  mov     rcx, [rsp+78h+var_30]
0x180030e89  xor     rcx, rsp; StackCookie
0x180030e8c  call    __security_check_cookie
0x180030e91  add     rsp, 50h
0x180030e95  pop     r14
0x180030e97  pop     rdi
0x180030e98  pop     rsi
0x180030e99  pop     rbp
0x180030e9a  pop     rbx
0x180030e9b  retn
```
