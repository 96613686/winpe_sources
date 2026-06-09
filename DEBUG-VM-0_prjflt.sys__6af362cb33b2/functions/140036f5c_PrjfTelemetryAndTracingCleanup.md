# PrjfTelemetryAndTracingCleanup

- ea: `0x140036f5c`
- end: `0x1400370b9`
- name: `PrjfTelemetryAndTracingCleanup`
- size: `349`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x1400413b0`
- `0x1400484e0`

## callees

- `0x140005bf4`
- `0x14000b7b0`
- `0x140036f5c`
- `0x140046614`
- `0x1400467f4`
- `0x1400468e0`

## import_xrefs

- `ntoskrnl!EtwUnregister` at `0x140037000`
- `ntoskrnl!EtwUnregister` at `0x140037055`
- `ntoskrnl!EtwUnregister` at `0x140037082`
- `ntoskrnl!EtwUnregister` at `0x140037000`
- `ntoskrnl!EtwUnregister` at `0x140037055`
- `ntoskrnl!EtwUnregister` at `0x140037082`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140036fcb`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140036fcb`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140036f7f`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x140036f7f`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x1400370a1`
- `WppRecorder!imp_WppRecorderLogDelete` at `0x1400370a1`

## pseudocode

```c
__int64 PrjfTelemetryAndTracingCleanup()
{
  int **v0; // rdi
  __int64 *v1; // rcx
  int ***v2; // rax
  __int64 v3; // rdx
  __int64 v4; // r8
  REGHANDLE v5; // rcx
  REGHANDLE v6; // rcx
  REGHANDLE v7; // rcx

  if ( (void (__fastcall *)(const struct _GUID *, unsigned int, unsigned __int8, unsigned __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, void *))qword_14001A090 == TlgAggregateInternalRegisteredProviderEtwCallback )
  {
    ExAcquirePushLockExclusiveEx(&qword_14001AC08, 0);
    v0 = (int **)qword_14001AC10;
    if ( qword_14001AC10 )
    {
      v1 = &qword_14001AC10;
      while ( 1 )
      {
        v2 = (int ***)(v0 + 44);
        if ( v0[43] == &dword_14001A068 )
          break;
        v0 = *v2;
        v1 = (__int64 *)v2;
        if ( !*v2 )
          goto LABEL_6;
      }
      *v1 = (__int64)*v2;
      LookUpTableFlushComplete(v0);
      if ( !qword_14001AC10 )
      {
        v6 = qword_14001A140;
        dword_14001A120 = 0;
        qword_14001A140 = 0;
        EtwUnregister(v6);
      }
    }
    else
    {
LABEL_6:
      v0 = 0;
    }
    ExReleasePushLockExclusiveEx(&qword_14001AC08, 0);
    if ( v0 )
      CancelTimerCallbacksAndDeleteTimer((__int64)v0, v3, v4);
    v5 = RegHandle;
    dword_14001A068 = 0;
    RegHandle = 0;
    EtwUnregister(v5);
    qword_14001A090 = 0;
    DestroyAggregateSession(v0);
  }
  else
  {
    v7 = RegHandle;
    dword_14001A068 = 0;
    RegHandle = 0;
    EtwUnregister(v7);
  }
  UninitializeTelemetryAssertsKM();
  imp_WppRecorderLogDelete(WPP_GLOBAL_Control, PrjfTraceRecorder);
  return FastWppCleanup();
}

```

## disassembly

```asm
0x140036f5c  push    rdi
0x140036f5e  sub     rsp, 20h
0x140036f62  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x140036f69  cmp     cs:qword_14001A090, rax
0x140036f70  jnz     loc_140037066
0x140036f76  xor     edx, edx
0x140036f78  lea     rcx, qword_14001AC08
0x140036f7f  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x140036f86  nop     dword ptr [rax+rax+00h]
0x140036f8b  mov     rdi, cs:qword_14001AC10
0x140036f92  test    rdi, rdi
0x140036f95  jz      short loc_140036FC0
0x140036f97  lea     rcx, qword_14001AC10
0x140036f9e  lea     rdx, dword_14001A068
0x140036fa5  lea     rax, [rdi+160h]
0x140036fac  cmp     [rdi+158h], rdx
0x140036fb3  jz      short loc_140037021
0x140036fb5  mov     rdi, [rax]
0x140036fb8  mov     rcx, rax
0x140036fbb  test    rdi, rdi
0x140036fbe  jnz     short loc_140036F9E
0x140036fc0  xor     edi, edi
0x140036fc2  xor     edx, edx
0x140036fc4  lea     rcx, qword_14001AC08
0x140036fcb  call    cs:__imp_ExReleasePushLockExclusiveEx
0x140036fd2  nop     dword ptr [rax+rax+00h]
0x140036fd7  test    rdi, rdi
0x140036fda  jz      short loc_140036FE4
0x140036fdc  mov     rcx, rdi
0x140036fdf  call    CancelTimerCallbacksAndDeleteTimer
0x140036fe4  mov     rcx, cs:RegHandle; RegHandle
0x140036feb  mov     cs:dword_14001A068, 0
0x140036ff5  mov     cs:RegHandle, 0
0x140037000  call    cs:__imp_EtwUnregister
0x140037007  nop     dword ptr [rax+rax+00h]
0x14003700c  mov     rcx, rdi; P
0x14003700f  mov     cs:qword_14001A090, 0
0x14003701a  call    DestroyAggregateSession
0x14003701f  jmp     short loc_14003708E
0x140037021  mov     rax, [rax]
0x140037024  mov     [rcx], rax
0x140037027  mov     rcx, rdi
0x14003702a  call    LookUpTableFlushComplete
0x14003702f  cmp     cs:qword_14001AC10, 0
0x140037037  jnz     short loc_140036FC2
0x140037039  mov     rcx, cs:qword_14001A140; RegHandle
0x140037040  mov     cs:dword_14001A120, 0
0x14003704a  mov     cs:qword_14001A140, 0
0x140037055  call    cs:__imp_EtwUnregister
0x14003705c  nop     dword ptr [rax+rax+00h]
0x140037061  jmp     loc_140036FC2
0x140037066  mov     rcx, cs:RegHandle; RegHandle
0x14003706d  mov     cs:dword_14001A068, 0
0x140037077  mov     cs:RegHandle, 0
0x140037082  call    cs:__imp_EtwUnregister
0x140037089  nop     dword ptr [rax+rax+00h]
0x14003708e  call    UninitializeTelemetryAssertsKM
0x140037093  mov     rdx, cs:_PrjfTraceRecorder
0x14003709a  mov     rcx, cs:WPP_GLOBAL_Control
0x1400370a1  call    cs:__imp_imp_WppRecorderLogDelete
0x1400370a8  nop     dword ptr [rax+rax+00h]
0x1400370ad  call    FastWppCleanup
0x1400370b2  add     rsp, 20h
0x1400370b6  pop     rdi
0x1400370b7  retn
```
