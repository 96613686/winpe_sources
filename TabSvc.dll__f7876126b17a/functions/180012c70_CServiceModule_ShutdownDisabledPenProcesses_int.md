# CServiceModule::ShutdownDisabledPenProcesses(int)

- ea: `0x180012c70`
- end: `0x180012d3b`
- name: `?ShutdownDisabledPenProcesses@CServiceModule@@QEAAXH@Z`
- size: `203`
- prototype: `void __fastcall(CServiceModule *__hidden this, int)`
- caller_count: `3`
- callee_count: `4`
- tags: `service_task`

## callers

- `0x18000ed70`
- `0x18000fa00`
- `0x18002638c`

## callees

- `0x180012c70`
- `0x18001a174`
- `0x1800286b0`
- `0x18002b3a8`

## string_xrefs

- `0x180012cb7`: `PENSERVICE_CServiceModule::ShutdownDisabledPenProcesses`
- `0x180012cfb`: `PENSERVICE_CServiceModule::ShutdownDisabledPenProcesses`

## pseudocode

```c
void __fastcall CServiceModule::ShutdownDisabledPenProcesses(CServiceModule *this)
{
  struct _GUID *v2; // rcx
  unsigned __int64 v3; // r8
  const struct _GUID *v4; // rcx
  struct _GUID *v5; // rax
  unsigned __int64 v6; // r8

  v2 = WPP_GLOBAL_Control;
  v3 = *(_QWORD *)WPP_GLOBAL_Control[3].Data4;
  if ( v3 )
  {
    PrivateTraceEvent(WPP_GLOBAL_Control, 0x61Bu, v3, 1u);
    v2 = WPP_GLOBAL_Control;
  }
  if ( v2 != (struct _GUID *)&WPP_GLOBAL_Control && (v2[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v2[1].Data1,
      52,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::ShutdownDisabledPenProcesses");
  CServiceModule::_RemovePenProcessesWorker(this, 1, 1u, -1);
  v5 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      53,
      WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids,
      "PENSERVICE_CServiceModule::ShutdownDisabledPenProcesses");
    v5 = WPP_GLOBAL_Control;
  }
  v6 = *(_QWORD *)v5[3].Data4;
  if ( v6 )
    PrivateTraceEvent(v4, 0x61Bu, v6, 2u);
}

```

## disassembly

```asm
0x180012c70  mov     [rsp+arg_0], rbx
0x180012c75  push    rdi
0x180012c76  sub     rsp, 20h
0x180012c7a  mov     rbx, rcx
0x180012c7d  mov     rcx, cs:WPP_GLOBAL_Control; struct _GUID *
0x180012c84  mov     r8, [rcx+38h]; unsigned __int64
0x180012c88  test    r8, r8
0x180012c8b  jz      short loc_180012CA1
0x180012c8d  mov     r9b, 1; unsigned __int8
0x180012c90  mov     edx, 61Bh; unsigned int
0x180012c95  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180012c9a  mov     rcx, cs:WPP_GLOBAL_Control
0x180012ca1  lea     rdi, WPP_GLOBAL_Control
0x180012ca8  cmp     rcx, rdi
0x180012cab  jz      short loc_180012CCF
0x180012cad  test    byte ptr [rcx+1Ch], 10h
0x180012cb1  jz      short loc_180012CCF
0x180012cb3  mov     rcx, [rcx+10h]
0x180012cb7  lea     r9, aPenserviceCser_27; "PENSERVICE_CServiceModule::ShutdownDisa"...
0x180012cbe  mov     edx, 34h ; '4'
0x180012cc3  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180012cca  call    WPP_SF_s
0x180012ccf  mov     edx, 1; unsigned int
0x180012cd4  mov     r9d, 0FFFFFFFFh; unsigned int
0x180012cda  mov     r8d, edx; unsigned int
0x180012cdd  mov     rcx, rbx; this
0x180012ce0  call    ?_RemovePenProcessesWorker@CServiceModule@@AEAAXKKK@Z; CServiceModule::_RemovePenProcessesWorker(ulong,ulong,ulong)
0x180012ce5  mov     rax, cs:WPP_GLOBAL_Control
0x180012cec  cmp     rax, rdi
0x180012cef  jz      short loc_180012D1A
0x180012cf1  test    byte ptr [rax+1Ch], 10h
0x180012cf5  jz      short loc_180012D1A
0x180012cf7  mov     rcx, [rax+10h]
0x180012cfb  lea     r9, aPenserviceCser_27; "PENSERVICE_CServiceModule::ShutdownDisa"...
0x180012d02  mov     edx, 35h ; '5'
0x180012d07  lea     r8, WPP_689c0dbffb35351eabe1c9663a4c4c53_Traceguids
0x180012d0e  call    WPP_SF_s
0x180012d13  mov     rax, cs:WPP_GLOBAL_Control
0x180012d1a  mov     r8, [rax+38h]; unsigned __int64
0x180012d1e  test    r8, r8
0x180012d21  jz      short loc_180012D30
0x180012d23  mov     r9b, 2; unsigned __int8
0x180012d26  mov     edx, 61Bh; unsigned int
0x180012d2b  call    ?PrivateTraceEvent@@YAXPEBU_GUID@@K_KE@Z; PrivateTraceEvent(_GUID const *,ulong,unsigned __int64,uchar)
0x180012d30  mov     rbx, [rsp+28h+arg_0]
0x180012d35  add     rsp, 20h
0x180012d39  pop     rdi
0x180012d3a  retn
```
