# TlgUnregisterAggregateProvider

- ea: `0x14000f0c0`
- end: `0x14000f199`
- name: `TlgUnregisterAggregateProvider`
- size: `217`
- prototype: `__int64(void)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000b260`
- `0x140016078`

## callees

- `0x14000eb58`
- `0x14000edc8`
- `0x14000f0c0`
- `0x14000f24c`
- `0x1400132ac`

## import_xrefs

- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f0e7`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14000f0e7`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f14b`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x14000f14b`

## pseudocode

```c
__int64 TlgUnregisterAggregateProvider()
{
  __int64 *i; // rcx
  __int64 v1; // rbx
  __int64 v2; // rdx
  __int64 v3; // r8

  if ( (void (__fastcall *)(const struct _GUID *, __int64, char, __int64, unsigned __int64, struct _EVENT_FILTER_DESCRIPTOR *, _QWORD *))qword_140007038 != TlgAggregateInternalRegisteredProviderEtwCallback )
    return TraceLoggingUnregister_EtwUnregister(&dword_140007010);
  ExAcquirePushLockExclusiveEx(&qword_140007478, 0);
  for ( i = &qword_140007480; ; i = (__int64 *)(v1 + 352) )
  {
    v1 = *i;
    if ( !*i )
      break;
    if ( *(int **)(v1 + 344) == &dword_140007010 )
    {
      *i = *(_QWORD *)(v1 + 352);
      LookUpTableFlushComplete(v1);
      if ( !qword_140007480 )
        TraceLoggingUnregister_EtwUnregister(&dword_1400071C0);
      break;
    }
  }
  ExReleasePushLockExclusiveEx(&qword_140007478, 0);
  if ( v1 )
    CancelTimerCallbacksAndDeleteTimer(v1, v2, v3);
  TraceLoggingUnregister_EtwUnregister(&dword_140007010);
  qword_140007038 = 0;
  return DestroyAggregateSession((PVOID)v1);
}

```

## disassembly

```asm
0x14000f0c0  mov     [rsp+arg_0], rbx
0x14000f0c5  push    rdi
0x14000f0c6  sub     rsp, 20h
0x14000f0ca  lea     rax, ?TlgAggregateInternalRegisteredProviderEtwCallback@@YAXPEBU_GUID@@KE_K1PEAU_EVENT_FILTER_DESCRIPTOR@@PEAX@Z; TlgAggregateInternalRegisteredProviderEtwCallback(_GUID const *,ulong,uchar,unsigned __int64,unsigned __int64,_EVENT_FILTER_DESCRIPTOR *,void *)
0x14000f0d1  cmp     cs:qword_140007038, rax
0x14000f0d8  jnz     loc_14000F181
0x14000f0de  xor     edx, edx
0x14000f0e0  lea     rcx, qword_140007478
0x14000f0e7  call    cs:__imp_ExAcquirePushLockExclusiveEx
0x14000f0ee  nop     dword ptr [rax+rax+00h]
0x14000f0f3  lea     rcx, qword_140007480
0x14000f0fa  lea     rdi, dword_140007010
0x14000f101  mov     rbx, [rcx]
0x14000f104  test    rbx, rbx
0x14000f107  jz      short loc_14000F142
0x14000f109  lea     rax, [rbx+160h]
0x14000f110  cmp     [rbx+158h], rdi
0x14000f117  jz      short loc_14000F11E
0x14000f119  mov     rcx, rax
0x14000f11c  jmp     short loc_14000F101
0x14000f11e  mov     rax, [rax]
0x14000f121  mov     [rcx], rax
0x14000f124  mov     rcx, rbx
0x14000f127  call    LookUpTableFlushComplete
0x14000f12c  cmp     cs:qword_140007480, 0
0x14000f134  jnz     short loc_14000F142
0x14000f136  lea     rcx, dword_1400071C0
0x14000f13d  call    TraceLoggingUnregister_EtwUnregister
0x14000f142  xor     edx, edx
0x14000f144  lea     rcx, qword_140007478
0x14000f14b  call    cs:__imp_ExReleasePushLockExclusiveEx
0x14000f152  nop     dword ptr [rax+rax+00h]
0x14000f157  test    rbx, rbx
0x14000f15a  jz      short loc_14000F164
0x14000f15c  mov     rcx, rbx
0x14000f15f  call    CancelTimerCallbacksAndDeleteTimer
0x14000f164  mov     rcx, rdi
0x14000f167  call    TraceLoggingUnregister_EtwUnregister
0x14000f16c  mov     rcx, rbx; P
0x14000f16f  mov     cs:qword_140007038, 0
0x14000f17a  call    DestroyAggregateSession
0x14000f17f  jmp     short loc_14000F18D
0x14000f181  lea     rcx, dword_140007010
0x14000f188  call    TraceLoggingUnregister_EtwUnregister
0x14000f18d  mov     rbx, [rsp+28h+arg_0]
0x14000f192  add     rsp, 20h
0x14000f196  pop     rdi
0x14000f197  retn
```
