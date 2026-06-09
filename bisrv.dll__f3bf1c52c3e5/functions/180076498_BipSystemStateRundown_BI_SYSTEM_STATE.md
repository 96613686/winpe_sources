# BipSystemStateRundown(_BI_SYSTEM_STATE *)

- ea: `0x180076498`
- end: `0x18007656d`
- name: `?BipSystemStateRundown@@YAXPEAU_BI_SYSTEM_STATE@@@Z`
- size: `213`
- prototype: `void __fastcall(struct _BI_SYSTEM_STATE *)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18007b088`

## callees

- `0x180006300`
- `0x1800121b0`
- `0x180076498`

## import_xrefs

- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800764b2`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800764c1`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800764b2`
- `api-ms-win-power-setting-l1-1-0!PowerSettingUnregisterNotification` at `0x1800764c1`
- `ntdll!RtlWaitOnAddress` at `0x18007653e`
- `ntdll!RtlWaitOnAddress` at `0x18007653e`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800764d0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800764df`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800764ee`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800764fd`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800764d0`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800764df`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800764ee`
- `ntdll!RtlUnsubscribeWnfNotificationWaitForCompletion` at `0x1800764fd`

## pseudocode

```c
void __fastcall BipSystemStateRundown(struct _BI_SYSTEM_STATE *a1)
{
  void *v2; // rcx
  void *v3; // rcx
  __int64 v4; // rdx
  int v5; // [rsp+30h] [rbp+8h] BYREF

  v5 = 0;
  v2 = (void *)*((_QWORD *)a1 + 3);
  if ( v2 )
    PowerSettingUnregisterNotification(v2);
  v3 = (void *)*((_QWORD *)a1 + 2);
  if ( v3 )
    PowerSettingUnregisterNotification(v3);
  if ( *((_QWORD *)a1 + 7) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  if ( *((_QWORD *)a1 + 8) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  if ( *((_QWORD *)a1 + 9) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  if ( *((_QWORD *)a1 + 10) )
    RtlUnsubscribeWnfNotificationWaitForCompletion();
  BipSyncAcquireLock((struct _BI_LOCK *)P);
  *((_DWORD *)a1 + 26) |= 1u;
  LOBYTE(v4) = 1;
  BipSyncReleaseLock(P, v4);
  while ( 1 )
  {
    BipSyncAcquireLock((struct _BI_LOCK *)P);
    if ( (*((_DWORD *)a1 + 26) & 4) == 0 )
      break;
    v5 = *((_DWORD *)a1 + 26);
    BipSyncReleaseLock(P, 0);
    RtlWaitOnAddress((char *)a1 + 104, &v5, 4, 0);
  }
  BipSyncReleaseLock(P, 0);
}

```

## disassembly

```asm
0x180076498  push    rbx
0x18007649a  sub     rsp, 20h
0x18007649e  mov     rbx, rcx
0x1800764a1  mov     [rsp+28h+arg_0], 0
0x1800764a9  mov     rcx, [rcx+18h]; RegistrationHandle
0x1800764ad  test    rcx, rcx
0x1800764b0  jz      short loc_1800764B8
0x1800764b2  call    cs:__imp_PowerSettingUnregisterNotification
0x1800764b8  mov     rcx, [rbx+10h]; RegistrationHandle
0x1800764bc  test    rcx, rcx
0x1800764bf  jz      short loc_1800764C7
0x1800764c1  call    cs:__imp_PowerSettingUnregisterNotification
0x1800764c7  mov     rcx, [rbx+38h]
0x1800764cb  test    rcx, rcx
0x1800764ce  jz      short loc_1800764D6
0x1800764d0  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800764d6  mov     rcx, [rbx+40h]
0x1800764da  test    rcx, rcx
0x1800764dd  jz      short loc_1800764E5
0x1800764df  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800764e5  mov     rcx, [rbx+48h]
0x1800764e9  test    rcx, rcx
0x1800764ec  jz      short loc_1800764F4
0x1800764ee  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x1800764f4  mov     rcx, [rbx+50h]
0x1800764f8  test    rcx, rcx
0x1800764fb  jz      short loc_180076503
0x1800764fd  call    cs:__imp_RtlUnsubscribeWnfNotificationWaitForCompletion
0x180076503  mov     rcx, cs:P; struct _BI_LOCK *
0x18007650a  mov     dl, 1
0x18007650c  call    BipSyncAcquireLock
0x180076511  or      dword ptr [rbx+68h], 1
0x180076515  mov     dl, 1
0x180076517  mov     rcx, cs:P
0x18007651e  call    BipSyncReleaseLock
0x180076523  jmp     short loc_180076544
0x180076525  mov     [rsp+28h+arg_0], eax
0x180076529  call    BipSyncReleaseLock
0x18007652e  xor     r9d, r9d
0x180076531  lea     rdx, [rsp+28h+arg_0]
0x180076536  lea     rcx, [rbx+68h]
0x18007653a  lea     r8d, [r9+4]
0x18007653e  call    cs:__imp_RtlWaitOnAddress
0x180076544  mov     rcx, cs:P; struct _BI_LOCK *
0x18007654b  xor     edx, edx
0x18007654d  call    BipSyncAcquireLock
0x180076552  mov     eax, [rbx+68h]
0x180076555  xor     edx, edx
0x180076557  mov     rcx, cs:P
0x18007655e  test    al, 4
0x180076560  jnz     short loc_180076525
0x180076562  call    BipSyncReleaseLock
0x180076567  add     rsp, 20h
0x18007656b  pop     rbx
0x18007656c  retn
```
