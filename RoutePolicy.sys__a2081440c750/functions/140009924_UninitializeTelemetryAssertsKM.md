# UninitializeTelemetryAssertsKM

- ea: `0x140009924`
- end: `0x140009a68`
- name: `UninitializeTelemetryAssertsKM`
- size: `324`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140008060`
- `0x14001903c`

## callees

- `0x140009924`

## import_xrefs

- `ntoskrnl!EtwUnregister` at `0x140009a00`
- `ntoskrnl!EtwUnregister` at `0x140009a28`
- `ntoskrnl!EtwUnregister` at `0x140009a50`
- `ntoskrnl!EtwUnregister` at `0x140009a00`
- `ntoskrnl!EtwUnregister` at `0x140009a28`
- `ntoskrnl!EtwUnregister` at `0x140009a50`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400099b0`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400099b0`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000994e`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14000994e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009992`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400099cd`
- `ntoskrnl!ExFreePoolWithTag` at `0x140009992`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400099cd`

## pseudocode

```c
NTSTATUS UninitializeTelemetryAssertsKM()
{
  NTSTATUS result; // eax
  KIRQL v1; // bl
  __int64 v2; // rcx
  __int64 v3; // rax
  REGHANDLE v4; // rcx
  REGHANDLE v5; // rcx
  REGHANDLE v6; // rcx

  result = _InterlockedExchangeAdd(&g_AssertsOperational, 0);
  if ( result )
  {
    _InterlockedDecrement(&g_AssertsOperational);
    v1 = KeAcquireSpinLockRaiseToDpc(&g_AssertSpinLock);
    while ( 1 )
    {
      v2 = g_MicrosoftTelemetryAssertsTriggeredList;
      if ( (__int64 *)g_MicrosoftTelemetryAssertsTriggeredList == &g_MicrosoftTelemetryAssertsTriggeredList )
        break;
      if ( *(__int64 **)(g_MicrosoftTelemetryAssertsTriggeredList + 8) != &g_MicrosoftTelemetryAssertsTriggeredList
        || (v3 = *(_QWORD *)g_MicrosoftTelemetryAssertsTriggeredList,
            *(_QWORD *)(*(_QWORD *)g_MicrosoftTelemetryAssertsTriggeredList + 8LL) != g_MicrosoftTelemetryAssertsTriggeredList) )
      {
        __fastfail(3u);
      }
      g_MicrosoftTelemetryAssertsTriggeredList = *(_QWORD *)g_MicrosoftTelemetryAssertsTriggeredList;
      *(_QWORD *)(v3 + 8) = &g_MicrosoftTelemetryAssertsTriggeredList;
      ExFreePoolWithTag((PVOID)(v2 - 32), 0x74727341u);
    }
    KeReleaseSpinLock(&g_AssertSpinLock, v1);
    if ( g_ModuleName )
    {
      ExFreePoolWithTag(g_ModuleName, 0x74727341u);
      g_ModuleName = 0;
    }
    v4 = qword_140016098;
    dword_140016078 = 0;
    qword_140016098 = 0;
    EtwUnregister(v4);
    v5 = qword_140016028;
    dword_140016008 = 0;
    qword_140016028 = 0;
    EtwUnregister(v5);
    v6 = qword_140016060;
    dword_140016040 = 0;
    qword_140016060 = 0;
    return EtwUnregister(v6);
  }
  return result;
}

```

## disassembly

```asm
0x140009924  mov     [rsp+arg_0], rbx
0x140009929  push    rsi
0x14000992a  sub     rsp, 20h
0x14000992e  xor     eax, eax
0x140009930  lock xadd cs:g_AssertsOperational, eax
0x140009938  test    eax, eax
0x14000993a  jz      loc_140009A5C
0x140009940  lock dec cs:g_AssertsOperational
0x140009947  lea     rcx, g_AssertSpinLock; SpinLock
0x14000994e  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140009955  nop     dword ptr [rax+rax+00h]
0x14000995a  mov     bl, al
0x14000995c  lea     rsi, g_MicrosoftTelemetryAssertsTriggeredList
0x140009963  mov     rcx, cs:g_MicrosoftTelemetryAssertsTriggeredList
0x14000996a  cmp     rcx, rsi
0x14000996d  jz      short loc_1400099A7
0x14000996f  cmp     [rcx+8], rsi
0x140009973  jnz     short loc_1400099A0
0x140009975  mov     rax, [rcx]
0x140009978  cmp     [rax+8], rcx
0x14000997c  jnz     short loc_1400099A0
0x14000997e  mov     cs:g_MicrosoftTelemetryAssertsTriggeredList, rax
0x140009985  add     rcx, 0FFFFFFFFFFFFFFE0h; P
0x140009989  mov     edx, 74727341h; Tag
0x14000998e  mov     [rax+8], rsi
0x140009992  call    cs:__imp_ExFreePoolWithTag
0x140009999  nop     dword ptr [rax+rax+00h]
0x14000999e  jmp     short loc_140009963
0x1400099a0  mov     ecx, 3
0x1400099a5  int     29h; Win8: RtlFailFast(ecx)
0x1400099a7  mov     dl, bl; NewIrql
0x1400099a9  lea     rcx, g_AssertSpinLock; SpinLock
0x1400099b0  call    cs:__imp_KeReleaseSpinLock
0x1400099b7  nop     dword ptr [rax+rax+00h]
0x1400099bc  mov     rcx, cs:g_ModuleName; P
0x1400099c3  test    rcx, rcx
0x1400099c6  jz      short loc_1400099E4
0x1400099c8  mov     edx, 74727341h; Tag
0x1400099cd  call    cs:__imp_ExFreePoolWithTag
0x1400099d4  nop     dword ptr [rax+rax+00h]
0x1400099d9  mov     cs:g_ModuleName, 0
0x1400099e4  mov     rcx, cs:qword_140016098; RegHandle
0x1400099eb  mov     cs:dword_140016078, 0
0x1400099f5  mov     cs:qword_140016098, 0
0x140009a00  call    cs:__imp_EtwUnregister
0x140009a07  nop     dword ptr [rax+rax+00h]
0x140009a0c  mov     rcx, cs:qword_140016028; RegHandle
0x140009a13  mov     cs:dword_140016008, 0
0x140009a1d  mov     cs:qword_140016028, 0
0x140009a28  call    cs:__imp_EtwUnregister
0x140009a2f  nop     dword ptr [rax+rax+00h]
0x140009a34  mov     rcx, cs:qword_140016060; RegHandle
0x140009a3b  mov     cs:dword_140016040, 0
0x140009a45  mov     cs:qword_140016060, 0
0x140009a50  call    cs:__imp_EtwUnregister
0x140009a57  nop     dword ptr [rax+rax+00h]
0x140009a5c  mov     rbx, [rsp+28h+arg_0]
0x140009a61  add     rsp, 20h
0x140009a65  pop     rsi
0x140009a66  retn
```
