# Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::OnNotification(_CMS_PROCESS_NOTIFICATION const &)

- ea: `0x18000606c`
- end: `0x1800061ba`
- name: `?OnNotification@?$InProcNotificationSubscriber@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAAXAEBU_CMS_PROCESS_NOTIFICATION@@@Z`
- size: `334`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180006260`

## callees

- `0x1800048a0`
- `0x18000606c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000616c`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18000616c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006091`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000614f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180006091`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000614f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800060c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006133`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000617a`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800060c2`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180006133`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18000617a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060ef`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800060ef`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18000613d`
- `api-ms-win-core-synch-l1-2-0!WakeConditionVariable` at `0x18000613d`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800060e1`
- `api-ms-win-core-synch-l1-2-0!SleepConditionVariableSRW` at `0x1800060e1`

## string_xrefs

- `0x180006196`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall Csl::InProcNotificationSubscriber<_CMS_PROCESS_NOTIFICATION,1>::OnNotification(__int64 a1, __int64 *a2)
{
  __int64 v3; // rbx
  unsigned __int8 (__fastcall *v4)(__int64 *, __int64, _QWORD); // rax
  const char *v5; // r9
  char v6; // al
  RTL_SRWLOCK *v7; // rbx
  __int64 v8; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  __int64 v10; // [rsp+30h] [rbp+8h] BYREF

  v3 = *(_QWORD *)(a1 + 8);
  v10 = *a2;
  AcquireSRWLockExclusive((PSRWLOCK)(v3 + 40));
  v4 = *(unsigned __int8 (__fastcall **)(__int64 *, __int64, _QWORD))(v3 + 80);
  if ( !v4 || v4(&v10, v3 + 24, *(_QWORD *)(v3 + 88)) )
  {
    while ( *(_QWORD *)(v3 + 72) == 1 )
    {
      if ( SleepConditionVariableSRW((PCONDITION_VARIABLE)(v3 + 32), (PSRWLOCK)(v3 + 40), 0x3A98u, 0) )
      {
        v6 = 0;
      }
      else
      {
        if ( GetLastError() != 1460 )
          wil::details::in1diag3::_FailFast_Unexpected(
            retaddr,
            (void *)0xF46,
            (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
            v5);
        v6 = 1;
      }
      if ( v6 )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x86,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslBuffer.h",
          v5);
    }
    *(_QWORD *)(v3 + 8LL * *(_QWORD *)(v3 + 64) + 48) = v10;
    *(_QWORD *)(v3 + 64) = 0;
    ++*(_QWORD *)(v3 + 72);
    if ( v3 != -40 )
      ReleaseSRWLockExclusive((PSRWLOCK)(v3 + 40));
    WakeConditionVariable((PCONDITION_VARIABLE)(v3 + 24));
  }
  else if ( v3 != -40 )
  {
    ReleaseSRWLockExclusive((PSRWLOCK)(v3 + 40));
  }
  v7 = (RTL_SRWLOCK *)(*(_QWORD *)(a1 + 8) + 16LL);
  AcquireSRWLockExclusive(v7);
  v8 = *(_QWORD *)(a1 + 8);
  if ( !*(_BYTE *)(v8 + 104) && !*(_BYTE *)(v8 + 96) )
  {
    *(_BYTE *)(v8 + 96) = 1;
    SubmitThreadpoolWork(*(PTP_WORK *)a1);
  }
  if ( v7 )
    ReleaseSRWLockExclusive(v7);
}

```

## disassembly

```asm
0x18000606c  mov     [rsp+arg_8], rbx
0x180006071  mov     [rsp+arg_10], rsi
0x180006076  push    rdi
0x180006077  sub     rsp, 20h
0x18000607b  mov     rsi, rcx
0x18000607e  mov     rbx, [rcx+8]
0x180006082  mov     rax, [rdx]
0x180006085  mov     [rsp+28h+arg_0], rax
0x18000608a  lea     rdi, [rbx+28h]
0x18000608e  mov     rcx, rdi; SRWLock
0x180006091  call    cs:__imp_AcquireSRWLockExclusive
0x180006097  mov     rax, [rbx+50h]
0x18000609b  test    rax, rax
0x18000609e  jz      short loc_1800060CA
0x1800060a0  mov     r8, [rbx+58h]
0x1800060a4  lea     rdx, [rbx+18h]
0x1800060a8  lea     rcx, [rsp+28h+arg_0]
0x1800060ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060b2  test    al, al
0x1800060b4  jnz     short loc_1800060CA
0x1800060b6  test    rdi, rdi
0x1800060b9  jz      loc_180006144
0x1800060bf  mov     rcx, rdi; SRWLock
0x1800060c2  call    cs:__imp_ReleaseSRWLockExclusive
0x1800060c8  jmp     short loc_180006144
0x1800060ca  cmp     qword ptr [rbx+48h], 1
0x1800060cf  jnz     short loc_180006111
0x1800060d1  lea     rcx, [rbx+20h]; ConditionVariable
0x1800060d5  xor     r9d, r9d; Flags
0x1800060d8  mov     r8d, 3A98h; dwMilliseconds
0x1800060de  mov     rdx, rdi; SRWLock
0x1800060e1  call    cs:__imp_SleepConditionVariableSRW
0x1800060e7  test    eax, eax
0x1800060e9  jz      short loc_1800060EF
0x1800060eb  xor     al, al
0x1800060ed  jmp     short loc_180006102
0x1800060ef  call    cs:__imp_GetLastError
0x1800060f5  cmp     eax, 5B4h
0x1800060fa  jnz     loc_180006191
0x180006100  mov     al, 1
0x180006102  mov     rcx, [rsp+28h]; this
0x180006107  test    al, al
0x180006109  jnz     loc_1800061A8
0x18000610f  jmp     short loc_1800060CA
0x180006111  mov     rdx, [rbx+40h]
0x180006115  mov     rax, [rsp+28h+arg_0]
0x18000611a  mov     [rbx+rdx*8+30h], rax
0x18000611f  mov     qword ptr [rbx+40h], 0
0x180006127  inc     qword ptr [rbx+48h]
0x18000612b  test    rdi, rdi
0x18000612e  jz      short loc_180006139
0x180006130  mov     rcx, rdi; SRWLock
0x180006133  call    cs:__imp_ReleaseSRWLockExclusive
0x180006139  lea     rcx, [rbx+18h]; ConditionVariable
0x18000613d  call    cs:__imp_WakeConditionVariable
0x180006143  nop
0x180006144  mov     rbx, [rsi+8]
0x180006148  add     rbx, 10h
0x18000614c  mov     rcx, rbx; SRWLock
0x18000614f  call    cs:__imp_AcquireSRWLockExclusive
0x180006155  mov     rax, [rsi+8]
0x180006159  cmp     byte ptr [rax+68h], 0
0x18000615d  jnz     short loc_180006172
0x18000615f  cmp     byte ptr [rax+60h], 0
0x180006163  jnz     short loc_180006172
0x180006165  mov     byte ptr [rax+60h], 1
0x180006169  mov     rcx, [rsi]; pwk
0x18000616c  call    cs:__imp_SubmitThreadpoolWork
0x180006172  test    rbx, rbx
0x180006175  jz      short loc_180006181
0x180006177  mov     rcx, rbx; SRWLock
0x18000617a  call    cs:__imp_ReleaseSRWLockExclusive
0x180006180  nop
0x180006181  mov     rbx, [rsp+28h+arg_8]
0x180006186  mov     rsi, [rsp+28h+arg_10]
0x18000618b  add     rsp, 20h
0x18000618f  pop     rdi
0x180006190  retn
0x180006191  mov     rcx, [rsp+28h]; this
0x180006196  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000619d  mov     edx, 0F46h; void *
0x1800061a2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800061a8  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x1800061af  mov     edx, 86h; void *
0x1800061b4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
