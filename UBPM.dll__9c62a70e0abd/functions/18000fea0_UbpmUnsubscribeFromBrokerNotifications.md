# UbpmUnsubscribeFromBrokerNotifications

- ea: `0x18000fea0`
- end: `0x1800100a5`
- name: `UbpmUnsubscribeFromBrokerNotifications`
- size: `517`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180001f40`
- `0x18000fdc8`
- `0x18002c05c`

## callees

- `0x18000ebb4`
- `0x18000fea0`
- `0x180036d44`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18000ff77`
- `ntdll!NtDeleteWnfStateName` at `0x18000ff77`
- `EventAggregation!EADeleteAggregateEvent` at `0x18000fef7`
- `EventAggregation!EADeleteAggregateEvent` at `0x180010031`
- `EventAggregation!EADeleteAggregateEvent` at `0x18000fef7`
- `EventAggregation!EADeleteAggregateEvent` at `0x180010031`
- `DABAPI!DabUnregisterTriggerConsumer` at `0x18000ffd9`
- `DABAPI!DabUnregisterTriggerConsumer` at `0x18000ffd9`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18000ff45`
- `CSystemEventsBrokerClient!CSebDeleteEvent` at `0x18000ff45`

## pseudocode

```c
__int64 __fastcall UbpmUnsubscribeFromBrokerNotifications(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  struct _UBPM_REPETITION_CONTEXT **v5; // rdi
  struct _UBPM_REPETITION_CONTEXT *v6; // rax
  __int64 result; // rax
  unsigned __int16 v8; // si
  __int64 v9; // rdi
  __int64 v10; // rcx
  __int64 v11; // rcx
  int v12; // eax
  __int64 v13; // rcx
  __int64 v14; // rax
  _DWORD *v15; // rcx
  __int64 v16; // rcx
  int v17; // eax
  _QWORD *v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rcx
  __int64 v21; // rcx
  struct _UBPM_REPETITION_CONTEXT *v22; // [rsp+30h] [rbp+8h] BYREF

  v5 = (struct _UBPM_REPETITION_CONTEXT **)(a1 + 240);
  while ( 1 )
  {
    v6 = *v5;
    if ( *v5 == (struct _UBPM_REPETITION_CONTEXT *)v5 )
      break;
    if ( *((struct _UBPM_REPETITION_CONTEXT ***)v6 + 1) != v5
      || (v20 = *(_QWORD *)v6, *(struct _UBPM_REPETITION_CONTEXT **)(*(_QWORD *)v6 + 8LL) != v6) )
    {
      __fastfail(3u);
    }
    *v5 = (struct _UBPM_REPETITION_CONTEXT *)v20;
    *(_QWORD *)(v20 + 8) = v5;
    v22 = v6;
    UbpmpDeleteRepetitionContext(&v22, a2, a3, a4);
  }
  result = *(_QWORD *)(a1 + 24);
  v8 = 0;
  if ( *(_DWORD *)(result + 20) )
  {
    do
    {
      v9 = 40LL * v8;
      if ( *(_QWORD *)(v9 + *(_QWORD *)(a1 + 32)) )
      {
        if ( (unsigned int)EADeleteAggregateEvent() )
          MicrosoftTelemetryAssertTriggeredNoArgs(v10);
        *(_QWORD *)(v9 + *(_QWORD *)(a1 + 32)) = 0;
      }
      if ( *(_QWORD *)(v9 + *(_QWORD *)(a1 + 32) + 8) )
      {
        if ( (unsigned int)EADeleteAggregateEvent() )
          MicrosoftTelemetryAssertTriggeredNoArgs(v21);
        *(_QWORD *)(v9 + *(_QWORD *)(a1 + 32) + 8) = 0;
      }
      v11 = v9 + *(_QWORD *)(a1 + 32);
      v12 = *(_DWORD *)(v11 + 24);
      if ( v12 == 2 )
      {
        if ( *(_DWORD *)(v11 + 16) || *(_DWORD *)(v11 + 20) )
        {
          if ( (int)CSebDeleteEvent(*(_QWORD *)(v11 + 16)) < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v13);
          *(_QWORD *)(v9 + *(_QWORD *)(a1 + 32) + 16) = 0;
        }
        v14 = *(_QWORD *)(a1 + 32);
        v15 = (_DWORD *)(v9 + v14 + 32);
        if ( *v15 || *(_DWORD *)(v9 + v14 + 36) )
        {
          if ( (int)NtDeleteWnfStateName(v15) < 0 )
            MicrosoftTelemetryAssertTriggeredNoArgs(v16);
          *(_QWORD *)(v9 + *(_QWORD *)(a1 + 32) + 32) = 0;
        }
      }
      else
      {
        v17 = v12 - 1;
        if ( v17 )
        {
          if ( v17 == 2 )
            *(_BYTE *)(a1 + 40) = 0;
        }
        else
        {
          v18 = (_QWORD *)(v11 + 32);
          if ( *v18 )
          {
            if ( (unsigned int)DabUnregisterTriggerConsumer(v18, 1, 0) )
              MicrosoftTelemetryAssertTriggeredNoArgs(v19);
            *(_QWORD *)(v9 + *(_QWORD *)(a1 + 32) + 32) = 0;
          }
        }
      }
      result = ++v8;
    }
    while ( (unsigned int)v8 < *(_DWORD *)(*(_QWORD *)(a1 + 24) + 20LL) );
  }
  return result;
}

```

## disassembly

```asm
0x18000fea0  mov     [rsp+arg_18], rbx
0x18000fea5  push    rdi
0x18000fea6  sub     rsp, 20h
0x18000feaa  mov     rbx, rcx
0x18000fead  lea     rdi, [rcx+0F0h]
0x18000feb4  mov     rax, [rdi]
0x18000feb7  cmp     rax, rdi
0x18000feba  jnz     loc_18000FFF8
0x18000fec0  mov     rax, [rbx+18h]
0x18000fec4  mov     [rsp+28h+arg_8], rbp
0x18000fec9  xor     ebp, ebp
0x18000fecb  mov     [rsp+28h+arg_10], rsi
0x18000fed0  mov     esi, ebp
0x18000fed2  cmp     [rax+14h], ebp
0x18000fed5  jbe     loc_18000FFA9
0x18000fedb  movzx   eax, si
0x18000fede  lea     rcx, [rax+rax*4]
0x18000fee2  mov     rax, [rbx+20h]
0x18000fee6  lea     rdi, ds:0[rcx*8]
0x18000feee  mov     rcx, [rdi+rax]
0x18000fef2  test    rcx, rcx
0x18000fef5  jz      short loc_18000FF13
0x18000fef7  call    cs:__imp_EADeleteAggregateEvent
0x18000fefe  nop     dword ptr [rax+rax+00h]
0x18000ff03  test    eax, eax
0x18000ff05  jnz     loc_180010068
0x18000ff0b  mov     rax, [rbx+20h]
0x18000ff0f  mov     [rdi+rax], rbp
0x18000ff13  mov     rax, [rbx+20h]
0x18000ff17  mov     rcx, [rdi+rax+8]
0x18000ff1c  test    rcx, rcx
0x18000ff1f  jnz     loc_180010031
0x18000ff25  mov     rcx, [rbx+20h]
0x18000ff29  add     rcx, rdi
0x18000ff2c  mov     eax, [rcx+18h]
0x18000ff2f  cmp     eax, 2
0x18000ff32  jnz     loc_18000FFBF
0x18000ff38  cmp     [rcx+10h], ebp
0x18000ff3b  jz      loc_180010083
0x18000ff41  mov     rcx, [rcx+10h]
0x18000ff45  call    cs:__imp_CSebDeleteEvent
0x18000ff4c  nop     dword ptr [rax+rax+00h]
0x18000ff51  test    eax, eax
0x18000ff53  js      loc_180010091
0x18000ff59  mov     rax, [rbx+20h]
0x18000ff5d  xor     ecx, ecx
0x18000ff5f  mov     [rdi+rax+10h], rcx
0x18000ff64  mov     rax, [rbx+20h]
0x18000ff68  lea     rcx, [rax+20h]
0x18000ff6c  add     rcx, rdi
0x18000ff6f  cmp     [rcx], ebp
0x18000ff71  jz      loc_180010022
0x18000ff77  call    cs:__imp_NtDeleteWnfStateName
0x18000ff7e  nop     dword ptr [rax+rax+00h]
0x18000ff83  test    eax, eax
0x18000ff85  js      loc_18001009B
0x18000ff8b  mov     rax, [rbx+20h]
0x18000ff8f  xor     ecx, ecx
0x18000ff91  mov     [rdi+rax+20h], rcx
0x18000ff96  mov     rcx, [rbx+18h]
0x18000ff9a  inc     si
0x18000ff9d  movzx   eax, si
0x18000ffa0  cmp     eax, [rcx+14h]
0x18000ffa3  jb      loc_18000FEDB
0x18000ffa9  mov     rbp, [rsp+28h+arg_8]
0x18000ffae  mov     rsi, [rsp+28h+arg_10]
0x18000ffb3  mov     rbx, [rsp+28h+arg_18]
0x18000ffb8  add     rsp, 20h
0x18000ffbc  pop     rdi
0x18000ffbd  retn
0x18000ffbf  sub     eax, 1
0x18000ffc2  jnz     loc_18001004F
0x18000ffc8  add     rcx, 20h ; ' '
0x18000ffcc  cmp     [rcx], rbp
0x18000ffcf  jz      short loc_18000FF96
0x18000ffd1  xor     r8d, r8d
0x18000ffd4  mov     edx, 1
0x18000ffd9  call    cs:__imp_DabUnregisterTriggerConsumer
0x18000ffe0  nop     dword ptr [rax+rax+00h]
0x18000ffe5  test    eax, eax
0x18000ffe7  jnz     loc_180010079
0x18000ffed  mov     rax, [rbx+20h]
0x18000fff1  mov     [rdi+rax+20h], rbp
0x18000fff6  jmp     short loc_18000FF96
0x18000fff8  cmp     [rax+8], rdi
0x18000fffc  jnz     short loc_180010061
0x18000fffe  mov     rcx, [rax]
0x180010001  cmp     [rcx+8], rax
0x180010005  jnz     short loc_180010061
0x180010007  mov     [rdi], rcx
0x18001000a  mov     [rcx+8], rdi
0x18001000e  lea     rcx, [rsp+28h+arg_0]; struct _UBPM_REPETITION_CONTEXT **
0x180010013  mov     [rsp+28h+arg_0], rax
0x180010018  call    ?UbpmpDeleteRepetitionContext@@YAXPEAPEAU_UBPM_REPETITION_CONTEXT@@@Z; UbpmpDeleteRepetitionContext(_UBPM_REPETITION_CONTEXT * *)
0x18001001d  jmp     loc_18000FEB4
0x180010022  cmp     [rdi+rax+24h], ebp
0x180010026  jz      loc_18000FF96
0x18001002c  jmp     loc_18000FF77
0x180010031  call    cs:__imp_EADeleteAggregateEvent
0x180010038  nop     dword ptr [rax+rax+00h]
0x18001003d  test    eax, eax
0x18001003f  jnz     short loc_180010072
0x180010041  mov     rax, [rbx+20h]
0x180010045  mov     [rdi+rax+8], rbp
0x18001004a  jmp     loc_18000FF25
0x18001004f  cmp     eax, 2
0x180010052  jnz     loc_18000FF96
0x180010058  mov     [rbx+28h], bpl
0x18001005c  jmp     loc_18000FF96
0x180010061  mov     ecx, 3
0x180010066  int     29h; Win8: RtlFailFast(ecx)
0x180010068  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001006d  jmp     loc_18000FF0B
0x180010072  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010077  jmp     short loc_180010041
0x180010079  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x18001007e  jmp     loc_18000FFED
0x180010083  cmp     [rcx+14h], ebp
0x180010086  jz      loc_18000FF64
0x18001008c  jmp     loc_18000FF41
0x180010091  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180010096  jmp     loc_18000FF59
0x18001009b  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x1800100a0  jmp     loc_18000FF8B
```
