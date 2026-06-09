# IncThreadCountIfNotStopping(char const *,ulong)

- ea: `0x1800131bc`
- end: `0x180013279`
- name: `?IncThreadCountIfNotStopping@@YAHPEBDK@Z`
- size: `189`
- prototype: `__int64 __fastcall(const char *, char)`
- caller_count: `5`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18000a1c0`
- `0x18000bc10`
- `0x18000be70`
- `0x18000e038`
- `0x180012a40`

## callees

- `0x18000a644`
- `0x1800111f4`
- `0x1800131bc`
- `0x180013640`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001322b`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001322b`

## pseudocode

```c
__int64 __fastcall IncThreadCountIfNotStopping(const char *a1, char a2)
{
  int v4; // r8d
  signed __int32 v6; // ebx

  if ( (unsigned int)SMIsShuttingDown() )
  {
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, &WPP_9af3fee475e93b32a0602d07f2745aa6_Traceguids);
    return 0;
  }
  else
  {
    v6 = _InterlockedIncrement((volatile signed __int32 *)&g_cThreads);
    if ( v6 == 1 && g_ThreadsCompletedEvent )
      ResetEvent(g_ThreadsCompletedEvent);
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 8) != 0 )
      WPP_SF_dsd(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, v4, v6, (__int64)a1, a2);
    return 1;
  }
}

```

## disassembly

```asm
0x1800131bc  mov     [rsp+arg_0], rbx
0x1800131c1  mov     [rsp+arg_8], rsi
0x1800131c6  push    rdi
0x1800131c7  sub     rsp, 30h
0x1800131cb  mov     edi, edx
0x1800131cd  mov     rsi, rcx
0x1800131d0  call    ?SMIsShuttingDown@@YAHXZ; SMIsShuttingDown(void)
0x1800131d5  test    eax, eax
0x1800131d7  jz      short loc_18001320B
0x1800131d9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800131e0  lea     rax, WPP_GLOBAL_Control
0x1800131e7  cmp     rcx, rax
0x1800131ea  jz      short loc_180013207
0x1800131ec  test    byte ptr [rcx+1Ch], 4
0x1800131f0  jz      short loc_180013207
0x1800131f2  mov     rcx, [rcx+10h]
0x1800131f6  lea     r8, WPP_9af3fee475e93b32a0602d07f2745aa6_Traceguids
0x1800131fd  mov     edx, 0Ch
0x180013202  call    WPP_SF_
0x180013207  xor     eax, eax
0x180013209  jmp     short loc_180013269
0x18001320b  mov     ebx, 1
0x180013210  lock xadd cs:?g_cThreads@@3KA, ebx; ulong g_cThreads
0x180013218  inc     ebx
0x18001321a  cmp     ebx, 1
0x18001321d  jnz     short loc_180013231
0x18001321f  mov     rcx, cs:?g_ThreadsCompletedEvent@@3PEAXEA; hEvent
0x180013226  test    rcx, rcx
0x180013229  jz      short loc_180013231
0x18001322b  call    cs:__imp_ResetEvent
0x180013231  mov     rcx, cs:WPP_GLOBAL_Control
0x180013238  lea     rax, WPP_GLOBAL_Control
0x18001323f  cmp     rcx, rax
0x180013242  jz      short loc_180013264
0x180013244  test    byte ptr [rcx+1Ch], 8
0x180013248  jz      short loc_180013264
0x18001324a  mov     rcx, [rcx+10h]
0x18001324e  mov     edx, 0Dh
0x180013253  mov     [rsp+38h+var_10], edi
0x180013257  mov     r9d, ebx
0x18001325a  mov     [rsp+38h+var_18], rsi
0x18001325f  call    WPP_SF_dsd
0x180013264  mov     eax, 1
0x180013269  mov     rbx, [rsp+38h+arg_0]
0x18001326e  mov     rsi, [rsp+38h+arg_8]
0x180013273  add     rsp, 30h
0x180013277  pop     rdi
0x180013278  retn
```
