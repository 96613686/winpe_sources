# UbpmMaintenanceUninitializeTaskTriggers

- ea: `0x180032bd0`
- end: `0x180032c87`
- name: `UbpmMaintenanceUninitializeTaskTriggers`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180032acc`

## callees

- `0x180032bd0`
- `0x1800351ec`
- `0x180036d44`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x180032c23`
- `ntdll!NtDeleteWnfStateName` at `0x180032c23`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x180032c05`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x180032c05`

## pseudocode

```c
__int64 UbpmMaintenanceUninitializeTaskTriggers()
{
  unsigned int i; // edi
  struct _MAINTENANCE_TRIGGER near **v1; // rbx
  int v2; // eax
  __int64 v3; // rcx
  unsigned int v4; // ebx

  for ( i = 0; ; ++i )
  {
    if ( i >= 5 )
      return 0;
    v1 = &g_MaintenanceTriggers + 2 * i;
    if ( *((_DWORD *)v1 + 2) || *((_DWORD *)v1 + 3) )
    {
      v2 = CSebDeleteEvent(v1[1]);
      if ( v2 < 0 )
        break;
    }
    if ( *(_DWORD *)v1 || *((_DWORD *)v1 + 1) )
    {
      if ( (int)NtDeleteWnfStateName(&g_MaintenanceTriggers + 2 * i) < 0 )
        MicrosoftTelemetryAssertTriggeredNoArgs(v3);
      *v1 = 0;
    }
  }
  v4 = (unsigned __int16)v2;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_78bab00beccc37ee093aed9e3146db9a_Traceguids,
      (unsigned __int16)v2);
  return v4;
}

```

## disassembly

```asm
0x180032bd0  mov     [rsp+arg_0], rbx
0x180032bd5  push    rdi
0x180032bd6  sub     rsp, 20h
0x180032bda  xor     edi, edi
0x180032bdc  cmp     edi, 5
0x180032bdf  jnb     loc_180032C77
0x180032be5  mov     ebx, edi
0x180032be7  lea     rcx, ?g_MaintenanceTriggers@@3PAU_MAINTENANCE_TRIGGER@@A; _MAINTENANCE_TRIGGER near * g_MaintenanceTriggers
0x180032bee  shl     rbx, 4
0x180032bf2  add     rbx, rcx
0x180032bf5  cmp     dword ptr [rbx+8], 0
0x180032bf9  jnz     short loc_180032C01
0x180032bfb  cmp     dword ptr [rbx+0Ch], 0
0x180032bff  jz      short loc_180032C15
0x180032c01  mov     rcx, [rbx+8]
0x180032c05  call    cs:__imp_CSebDeleteEvent
0x180032c0c  nop     dword ptr [rax+rax+00h]
0x180032c11  test    eax, eax
0x180032c13  js      short loc_180032C41
0x180032c15  cmp     dword ptr [rbx], 0
0x180032c18  jnz     short loc_180032C20
0x180032c1a  cmp     dword ptr [rbx+4], 0
0x180032c1e  jz      short loc_180032C3D
0x180032c20  mov     rcx, rbx
0x180032c23  call    cs:__imp_NtDeleteWnfStateName
0x180032c2a  nop     dword ptr [rax+rax+00h]
0x180032c2f  test    eax, eax
0x180032c31  jns     short loc_180032C38
0x180032c33  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180032c38  xor     eax, eax
0x180032c3a  mov     [rbx], rax
0x180032c3d  inc     edi
0x180032c3f  jmp     short loc_180032BDC
0x180032c41  movzx   ebx, ax
0x180032c44  mov     rcx, cs:WPP_GLOBAL_Control
0x180032c4b  lea     rax, WPP_GLOBAL_Control
0x180032c52  cmp     rcx, rax
0x180032c55  jz      short loc_180032C79
0x180032c57  test    byte ptr [rcx+1Ch], 1
0x180032c5b  jz      short loc_180032C79
0x180032c5d  mov     rcx, [rcx+10h]
0x180032c61  lea     r8, WPP_78bab00beccc37ee093aed9e3146db9a_Traceguids
0x180032c68  mov     edx, 0Ah
0x180032c6d  mov     r9d, ebx
0x180032c70  call    WPP_SF_d
0x180032c75  jmp     short loc_180032C79
0x180032c77  xor     ebx, ebx
0x180032c79  mov     eax, ebx
0x180032c7b  mov     rbx, [rsp+28h+arg_0]
0x180032c80  add     rsp, 20h
0x180032c84  pop     rdi
0x180032c85  retn
```
