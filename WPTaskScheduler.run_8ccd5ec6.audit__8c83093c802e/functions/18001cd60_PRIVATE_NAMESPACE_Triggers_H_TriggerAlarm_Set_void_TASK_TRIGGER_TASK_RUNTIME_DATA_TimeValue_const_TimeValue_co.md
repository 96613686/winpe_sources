# PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::Set(void *,_TASK_TRIGGER *,_TASK_RUNTIME_DATA *,TimeValue const &,TimeValue const &,uchar,ulong)

- ea: `0x18001cd60`
- end: `0x18001cf81`
- name: `?Set@TriggerAlarm@PRIVATE_NAMESPACE_Triggers_H@@EEAAJPEAXPEAU_TASK_TRIGGER@@PEAU_TASK_RUNTIME_DATA@@AEBVTimeValue@@3EK@Z`
- size: `545`
- prototype: `__int64 __fastcall(PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *__hidden this, void *, struct _TASK_TRIGGER *, struct _TASK_RUNTIME_DATA *, const struct TimeValue *, const struct TimeValue *, unsigned __int8, unsigned int)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task`

## callees

- `0x18000c540`
- `0x18000c700`
- `0x18000ea40`
- `0x18000eef0`
- `0x180018498`
- `0x18001cb3c`
- `0x18001cd60`
- `0x18001d954`
- `0x180020c30`

## pseudocode

```c
__int64 __fastcall PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::Set(
        PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *this,
        void *a2,
        struct _TASK_TRIGGER *a3,
        const struct _FILETIME *a4)
{
  _OWORD *v6; // rax
  int v7; // ebp
  struct _SYSTEMTIME *v8; // rbx
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rcx
  __int64 v12; // r8
  struct _EVENT_DATA_DESCRIPTOR v14; // [rsp+50h] [rbp-48h] BYREF

  if ( !a3 || !a2 )
    return 2147500035LL;
  v6 = *(_OWORD **)&a3->wBeginDay;
  if ( v6 )
  {
    *((_QWORD *)this + 22) = a2;
    v8 = (struct _SYSTEMTIME *)((char *)this + 208);
    *((_OWORD *)this + 12) = *v6;
    TimeValue::Set(
      (PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm *)((char *)this + 208),
      (const struct _SYSTEMTIME *)this + 12);
    *((_DWORD *)this + 74) = 0;
    *((_DWORD *)this + 28) = 0;
    *((_DWORD *)this + 46) = 0;
    PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::UnregisterAlarmEvent(this, v9, v10);
    if ( (byte_180030D03 & 8) != 0 )
      McGenEventWrite_EventWriteTransfer(v11, (const EVENT_DESCRIPTOR *)AlarmTriggerType, v12, 1u, &v14);
    if ( a4 && (unsigned int)TimeValue::Set(v8, a4) )
    {
      if ( (byte_180030D03 & 8) != 0 )
        McTemplateU0hhhhhhh_EventWriteTransfer(
          v8->wHour,
          (unsigned int)HasRuntimeData,
          v8->wYear,
          v8->wMonth,
          v8->wDay,
          v8->wHour,
          v8->wMinute,
          v8->wSecond,
          v8->wMilliseconds);
      if ( a4[1] )
      {
        TimeValue::Set((LPSYSTEMTIME)((char *)this + 72), a4 + 1);
        if ( (unsigned int)operator<=((char *)this + 72, v8) )
          *((_DWORD *)this + 28) = 0;
      }
    }
    v7 = PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::RegisterAlarmEvent(this);
    if ( v7 >= 0 )
    {
      if ( *((_DWORD *)this + 62) && (byte_180030D04 & 2) != 0 )
        McTemplateU0hhhhhhh_EventWriteTransfer(
          v8->wHour,
          (unsigned int)TriggerStartTimeDate,
          v8->wYear,
          v8->wMonth,
          v8->wDay,
          v8->wHour,
          v8->wMinute,
          v8->wSecond,
          v8->wMilliseconds);
      if ( *((_DWORD *)this + 28) )
      {
        if ( (byte_180030D04 & 2) != 0 )
          McTemplateU0hhhhhhh_EventWriteTransfer(
            *((unsigned __int16 *)this + 40),
            (unsigned int)SnoozedTriggerTimeDate,
            *((unsigned __int16 *)this + 36),
            *((unsigned __int16 *)this + 37),
            *((_WORD *)this + 39),
            *((_WORD *)this + 40),
            *((_WORD *)this + 41),
            *((_WORD *)this + 42),
            *((_WORD *)this + 43));
      }
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18001cd60  push    rbx
0x18001cd62  push    rbp
0x18001cd63  push    rsi
0x18001cd64  push    rdi
0x18001cd65  sub     rsp, 78h
0x18001cd69  mov     rax, cs:__security_cookie
0x18001cd70  xor     rax, rsp
0x18001cd73  mov     [rsp+98h+var_38], rax
0x18001cd78  mov     rbp, r9
0x18001cd7b  mov     rdi, rcx
0x18001cd7e  test    r8, r8
0x18001cd81  jz      loc_18001CF66
0x18001cd87  test    rdx, rdx
0x18001cd8a  jz      loc_18001CF66
0x18001cd90  mov     rax, [r8+8]
0x18001cd94  test    rax, rax
0x18001cd97  jnz     short loc_18001CDA3
0x18001cd99  mov     ebp, 80070057h
0x18001cd9e  jmp     loc_18001CF62
0x18001cda3  mov     [rcx+0B0h], rdx
0x18001cdaa  lea     rbx, [rcx+0D0h]
0x18001cdb1  movups  xmm0, xmmword ptr [rax]
0x18001cdb4  lea     rdx, [rcx+0C0h]; struct _SYSTEMTIME *
0x18001cdbb  mov     rcx, rbx; this
0x18001cdbe  movdqu  xmmword ptr [rdx], xmm0
0x18001cdc2  call    ?Set@TimeValue@@QEAAHAEBU_SYSTEMTIME@@@Z; TimeValue::Set(_SYSTEMTIME const &)
0x18001cdc7  lea     rsi, [rdi+48h]
0x18001cdcb  mov     dword ptr [rdi+128h], 0
0x18001cdd5  mov     rcx, rdi; this
0x18001cdd8  mov     dword ptr [rsi+28h], 0
0x18001cddf  mov     dword ptr [rdi+0B8h], 0
0x18001cde9  call    ?UnregisterAlarmEvent@TriggerAlarm@PRIVATE_NAMESPACE_Triggers_H@@AEAAJXZ; PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::UnregisterAlarmEvent(void)
0x18001cdee  test    cs:byte_180030D03, 8
0x18001cdf5  jz      short loc_18001CE13
0x18001cdf7  lea     rax, [rsp+98h+var_48]
0x18001cdfc  mov     r9d, 1
0x18001ce02  lea     rdx, AlarmTriggerType
0x18001ce09  mov     [rsp+98h+var_78], rax
0x18001ce0e  call    McGenEventWrite_EventWriteTransfer
0x18001ce13  test    rbp, rbp
0x18001ce16  jz      loc_18001CEA3
0x18001ce1c  mov     rdx, rbp; struct _FILETIME *
0x18001ce1f  mov     rcx, rbx; lpSystemTime
0x18001ce22  call    ?Set@TimeValue@@QEAAHAEBU_FILETIME@@@Z; TimeValue::Set(_FILETIME const &)
0x18001ce27  test    eax, eax
0x18001ce29  jz      short loc_18001CEA3
0x18001ce2b  test    cs:byte_180030D03, 8
0x18001ce32  movzx   eax, word ptr [rbx+6]
0x18001ce36  movzx   ecx, word ptr [rbx+8]
0x18001ce3a  movzx   edx, word ptr [rbx+0Ah]
0x18001ce3e  movzx   r8d, word ptr [rbx+0Ch]
0x18001ce43  movzx   r9d, word ptr [rbx+0Eh]
0x18001ce48  jz      short loc_18001CE7A
0x18001ce4a  mov     [rsp+98h+var_58], r9w
0x18001ce50  movzx   r9d, word ptr [rbx+2]
0x18001ce55  mov     [rsp+98h+var_60], r8w
0x18001ce5b  movzx   r8d, word ptr [rbx]
0x18001ce5f  mov     [rsp+98h+var_68], dx
0x18001ce64  lea     rdx, HasRuntimeData
0x18001ce6b  mov     [rsp+98h+var_70], cx
0x18001ce70  mov     word ptr [rsp+98h+var_78], ax
0x18001ce75  call    McTemplateU0hhhhhhh_EventWriteTransfer
0x18001ce7a  mov     eax, [rbp+0Ch]
0x18001ce7d  lea     rdx, [rbp+8]; struct _FILETIME *
0x18001ce81  or      eax, [rdx]
0x18001ce83  jz      short loc_18001CEA3
0x18001ce85  mov     rcx, rsi; lpSystemTime
0x18001ce88  call    ?Set@TimeValue@@QEAAHAEBU_FILETIME@@@Z; TimeValue::Set(_FILETIME const &)
0x18001ce8d  mov     rdx, rbx
0x18001ce90  mov     rcx, rsi
0x18001ce93  call    ??N@YAHAEBVTimeValue@@0@Z; operator<=(TimeValue const &,TimeValue const &)
0x18001ce98  test    eax, eax
0x18001ce9a  jz      short loc_18001CEA3
0x18001ce9c  mov     dword ptr [rdi+70h], 0
0x18001cea3  mov     rcx, rdi; this
0x18001cea6  call    ?RegisterAlarmEvent@TriggerAlarm@PRIVATE_NAMESPACE_Triggers_H@@AEAAJXZ; PRIVATE_NAMESPACE_Triggers_H::TriggerAlarm::RegisterAlarmEvent(void)
0x18001ceab  mov     ebp, eax
0x18001cead  test    eax, eax
0x18001ceaf  js      loc_18001CF62
0x18001ceb5  cmp     dword ptr [rdi+0F8h], 0
0x18001cebc  jz      short loc_18001CF0D
0x18001cebe  test    cs:byte_180030D04, 2
0x18001cec5  movzx   eax, word ptr [rbx+6]
0x18001cec9  movzx   ecx, word ptr [rbx+8]
0x18001cecd  movzx   edx, word ptr [rbx+0Ah]
0x18001ced1  movzx   r8d, word ptr [rbx+0Ch]
0x18001ced6  movzx   r9d, word ptr [rbx+0Eh]
0x18001cedb  jz      short loc_18001CF0D
0x18001cedd  mov     [rsp+98h+var_58], r9w
0x18001cee3  movzx   r9d, word ptr [rbx+2]
0x18001cee8  mov     [rsp+98h+var_60], r8w
0x18001ceee  movzx   r8d, word ptr [rbx]
0x18001cef2  mov     [rsp+98h+var_68], dx
0x18001cef7  lea     rdx, TriggerStartTimeDate
0x18001cefe  mov     [rsp+98h+var_70], cx
0x18001cf03  mov     word ptr [rsp+98h+var_78], ax
0x18001cf08  call    McTemplateU0hhhhhhh_EventWriteTransfer
0x18001cf0d  cmp     dword ptr [rdi+70h], 0
0x18001cf11  jz      short loc_18001CF62
0x18001cf13  test    cs:byte_180030D04, 2
0x18001cf1a  movzx   eax, word ptr [rsi+6]
0x18001cf1e  movzx   ecx, word ptr [rsi+8]
0x18001cf22  movzx   edx, word ptr [rsi+0Ah]
0x18001cf26  movzx   r8d, word ptr [rsi+0Ch]
0x18001cf2b  movzx   r9d, word ptr [rsi+0Eh]
0x18001cf30  jz      short loc_18001CF62
0x18001cf32  mov     [rsp+98h+var_58], r9w
0x18001cf38  movzx   r9d, word ptr [rsi+2]
0x18001cf3d  mov     [rsp+98h+var_60], r8w
0x18001cf43  movzx   r8d, word ptr [rsi]
0x18001cf47  mov     [rsp+98h+var_68], dx
0x18001cf4c  lea     rdx, SnoozedTriggerTimeDate
0x18001cf53  mov     [rsp+98h+var_70], cx
0x18001cf58  mov     word ptr [rsp+98h+var_78], ax
0x18001cf5d  call    McTemplateU0hhhhhhh_EventWriteTransfer
0x18001cf62  mov     eax, ebp
0x18001cf64  jmp     short loc_18001CF6B
0x18001cf66  mov     eax, 80004003h
0x18001cf6b  mov     rcx, [rsp+98h+var_38]
0x18001cf70  xor     rcx, rsp; StackCookie
0x18001cf73  call    __security_check_cookie
0x18001cf78  add     rsp, 78h
0x18001cf7c  pop     rdi
0x18001cf7d  pop     rsi
0x18001cf7e  pop     rbp
0x18001cf7f  pop     rbx
0x18001cf80  retn
```
