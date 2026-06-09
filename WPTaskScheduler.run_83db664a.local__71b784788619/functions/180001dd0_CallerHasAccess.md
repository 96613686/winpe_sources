# CallerHasAccess

- ea: `0x180001dd0`
- end: `0x180001e94`
- name: `CallerHasAccess`
- size: `196`
- prototype: `__int64 __fastcall(struct _GUID *)`
- caller_count: `6`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180017470`
- `0x1800174c0`
- `0x180017530`
- `0x180017590`
- `0x1800177a0`
- `0x180017850`

## callees

- `0x180001dd0`
- `0x180002f00`
- `0x18000e970`
- `0x180017370`
- `0x18001ffc0`

## pseudocode

```c
RPC_STATUS __fastcall CallerHasAccess(struct _GUID *a1, int a2)
{
  __int64 **v2; // rax
  void *v4; // rcx
  __int64 v6; // r8
  RPC_STATUS result; // eax
  const unsigned __int16 *v8; // rcx
  unsigned int v9; // ebx
  const unsigned __int16 *v10; // rcx

  v2 = (__int64 **)g_ScheduleMgr;
  v4 = &g_ScheduleMgr;
  while ( 1 )
  {
    if ( v2 == (__int64 **)&g_ScheduleMgr )
    {
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x20) == 0 )
        return -2100362994;
      McTemplateU0j_EventWriteTransfer(
        (__int64)&g_ScheduleMgr,
        (const EVENT_DESCRIPTOR *)ScheduleNotFoundWarning,
        (__int64)a1);
LABEL_17:
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 0x20) != 0 )
        McTemplateU0j_EventWriteTransfer((__int64)v4, (const EVENT_DESCRIPTOR *)ScheduleNotFoundWarning, (__int64)a1);
      return -2100362994;
    }
    v6 = (__int64)v2[2] - *(_QWORD *)&a1->Data1;
    if ( !v6 )
      v6 = (__int64)v2[3] - *(_QWORD *)a1->Data4;
    if ( !v6 )
      break;
    v2 = (__int64 **)*v2;
  }
  if ( !v2 )
    goto LABEL_17;
  result = CScheduleMgr::IsCallerScheduleOwner((CScheduleMgr *)&g_ScheduleMgr, a1);
  v9 = result;
  if ( result < 0 )
  {
    if ( a2
      || (result = TsiCheckCallerCapabilities(v8), result < 0)
      && (result = TsiCheckCallerCapabilities(v10), v9 = result, result < 0) )
    {
      if ( (Microsoft_WindowsPhone_TaskSchedulerEnableBits & 1) != 0 )
        McTemplateU0q_EventWriteTransfer((__int64)v8, (const EVENT_DESCRIPTOR *)SecurityError, v9);
      return v9;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180001dd0  mov     [rsp+arg_0], rbx
0x180001dd5  push    rdi
0x180001dd6  sub     rsp, 20h
0x180001dda  mov     rax, cs:?g_ScheduleMgr@@3VCScheduleMgr@@A; CScheduleMgr g_ScheduleMgr
0x180001de1  mov     rbx, rcx
0x180001de4  lea     rcx, ?g_ScheduleMgr@@3VCScheduleMgr@@A; this
0x180001deb  mov     edi, edx
0x180001ded  cmp     rax, rcx
0x180001df0  jz      short loc_180001E54
0x180001df2  mov     r8, [rax+10h]
0x180001df6  sub     r8, [rbx]
0x180001df9  jnz     short loc_180001E03
0x180001dfb  mov     r8, [rax+18h]
0x180001dff  sub     r8, [rbx+8]
0x180001e03  test    r8, r8
0x180001e06  jz      short loc_180001E0D
0x180001e08  mov     rax, [rax]
0x180001e0b  jmp     short loc_180001DED
0x180001e0d  test    rax, rax
0x180001e10  jz      short loc_180001E6C
0x180001e12  mov     rdx, rbx; struct _GUID *
0x180001e15  call    ?IsCallerScheduleOwner@CScheduleMgr@@QEAA?BJPEBU_GUID@@@Z; CScheduleMgr::IsCallerScheduleOwner(_GUID const *)
0x180001e1a  mov     ebx, eax
0x180001e1c  test    eax, eax
0x180001e1e  jns     short loc_180001E89
0x180001e20  test    edi, edi
0x180001e22  jnz     short loc_180001E38
0x180001e24  call    ?TsiCheckCallerCapabilities@@YAJPEBG@Z; TsiCheckCallerCapabilities(ushort const *)
0x180001e29  test    eax, eax
0x180001e2b  jns     short loc_180001E89
0x180001e2d  call    ?TsiCheckCallerCapabilities@@YAJPEBG@Z; TsiCheckCallerCapabilities(ushort const *)
0x180001e32  mov     ebx, eax
0x180001e34  test    eax, eax
0x180001e36  jns     short loc_180001E89
0x180001e38  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 1
0x180001e3f  jz      short loc_180001E50
0x180001e41  mov     r8d, ebx
0x180001e44  lea     rdx, SecurityError
0x180001e4b  call    McTemplateU0q_EventWriteTransfer
0x180001e50  mov     eax, ebx
0x180001e52  jmp     short loc_180001E89
0x180001e54  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 20h
0x180001e5b  jz      short loc_180001E84
0x180001e5d  mov     r8, rbx
0x180001e60  lea     rdx, ScheduleNotFoundWarning
0x180001e67  call    McTemplateU0j_EventWriteTransfer
0x180001e6c  test    cs:Microsoft_WindowsPhone_TaskSchedulerEnableBits, 20h
0x180001e73  jz      short loc_180001E84
0x180001e75  mov     r8, rbx
0x180001e78  lea     rdx, ScheduleNotFoundWarning
0x180001e7f  call    McTemplateU0j_EventWriteTransfer
0x180001e84  mov     eax, 82CF010Eh
0x180001e89  mov     rbx, [rsp+28h+arg_0]
0x180001e8e  add     rsp, 20h
0x180001e92  pop     rdi
0x180001e93  retn
```
