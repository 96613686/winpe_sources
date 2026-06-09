# UbpmpUninitializeMaintenanceLevels(void)

- ea: `0x18002c32c`
- end: `0x18002c3c7`
- name: `?UbpmpUninitializeMaintenanceLevels@@YAXXZ`
- size: `155`
- prototype: `void(void)`
- caller_count: `3`
- callee_count: `2`
- tags: ``

## callers

- `0x18002c0b4`
- `0x180032acc`
- `0x180038be8`

## callees

- `0x18002c32c`
- `0x180032f78`

## import_xrefs

- `EventAggregation!EADeleteAggregateEvent` at `0x18002c36a`
- `EventAggregation!EADeleteAggregateEvent` at `0x18002c36a`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x18002c354`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFree` at `0x18002c354`

## pseudocode

```c
void UbpmpUninitializeMaintenanceLevels(void)
{
  unsigned int i; // ebx
  unsigned __int64 v1; // rdi
  __int64 v2; // rcx
  __int64 v3; // rcx

  for ( i = 0; i < 5; ++i )
  {
    v1 = (unsigned __int64)i << 6;
    v2 = *(_QWORD *)((char *)&g_MaintenancePilot + v1 + 104);
    if ( v2 )
      CrmActivityFree(v2);
    v3 = *(_QWORD *)((char *)&g_MaintenancePilot + v1 + 96);
    if ( v3
      && (unsigned int)EADeleteAggregateEvent(v3)
      && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_dd(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids, i);
    }
  }
}

```

## disassembly

```asm
0x18002c32c  mov     [rsp+arg_0], rbx
0x18002c331  mov     [rsp+arg_8], rsi
0x18002c336  push    rdi
0x18002c337  sub     rsp, 30h
0x18002c33b  xor     ebx, ebx
0x18002c33d  lea     rsi, ?g_MaintenancePilot@@3U_UBPM_MAINTENANCE_GLOBAL_STATE@@A; _UBPM_MAINTENANCE_GLOBAL_STATE g_MaintenancePilot
0x18002c344  mov     edi, ebx
0x18002c346  shl     rdi, 6
0x18002c34a  mov     rcx, [rdi+rsi+68h]
0x18002c34f  test    rcx, rcx
0x18002c352  jz      short loc_18002C360
0x18002c354  call    cs:__imp_CrmActivityFree
0x18002c35b  nop     dword ptr [rax+rax+00h]
0x18002c360  mov     rcx, [rdi+rsi+60h]
0x18002c365  test    rcx, rcx
0x18002c368  jz      short loc_18002C3AF
0x18002c36a  call    cs:__imp_EADeleteAggregateEvent
0x18002c371  nop     dword ptr [rax+rax+00h]
0x18002c376  test    eax, eax
0x18002c378  jz      short loc_18002C3AF
0x18002c37a  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c381  lea     rdx, WPP_GLOBAL_Control
0x18002c388  cmp     rcx, rdx
0x18002c38b  jz      short loc_18002C3AF
0x18002c38d  test    byte ptr [rcx+1Ch], 1
0x18002c391  jz      short loc_18002C3AF
0x18002c393  mov     rcx, [rcx+10h]
0x18002c397  lea     r8, WPP_e8737fd78cd23c19c4aa7846d1bfb582_Traceguids
0x18002c39e  mov     edx, 12h
0x18002c3a3  mov     [rsp+38h+var_18], eax
0x18002c3a7  mov     r9d, ebx
0x18002c3aa  call    WPP_SF_dd
0x18002c3af  inc     ebx
0x18002c3b1  cmp     ebx, 5
0x18002c3b4  jb      short loc_18002C344
0x18002c3b6  mov     rbx, [rsp+38h+arg_0]
0x18002c3bb  mov     rsi, [rsp+38h+arg_8]
0x18002c3c0  add     rsp, 30h
0x18002c3c4  pop     rdi
0x18002c3c5  retn
```
