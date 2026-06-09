# CPersistedControl::WaitForPersistedChanges(void)

- ea: `0x1800368ec`
- end: `0x18003694e`
- name: `?WaitForPersistedChanges@CPersistedControl@@QEAAJXZ`
- size: `98`
- prototype: `__int64 __fastcall(CPersistedControl *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180057e6c`

## callees

- `0x180010da8`
- `0x180030f6c`
- `0x1800368ec`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036915`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x180036915`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036906`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x180036906`

## string_xrefs

- `0x18003692e`: `avcore\audiocore\server\audioendpointbuilder\dll\persist.cpp`

## pseudocode

```c
__int64 __fastcall CPersistedControl::WaitForPersistedChanges(CPersistedControl *this)
{
  struct _TP_TIMER *v2; // rcx
  __int64 v3; // rdx
  bool v4; // r8
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  v2 = (struct _TP_TIMER *)*((_QWORD *)this + 7);
  if ( !v2 )
    return 0;
  SetThreadpoolTimer(v2, 0, 0, 0);
  WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 7), 1);
  v5 = CPersistedControl::SavePersistedState(this, v3, v4);
  v6 = v5;
  if ( v5 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x21A,
    (unsigned int)"avcore\\audiocore\\server\\audioendpointbuilder\\dll\\persist.cpp",
    (const char *)(unsigned int)v5,
    v8);
  return v6;
}

```

## disassembly

```asm
0x1800368ec  push    rbx; int
0x1800368ee  sub     rsp, 20h
0x1800368f2  mov     rbx, rcx
0x1800368f5  mov     rcx, [rcx+38h]; pti
0x1800368f9  test    rcx, rcx
0x1800368fc  jz      short loc_180036946
0x1800368fe  xor     r9d, r9d; msWindowLength
0x180036901  xor     r8d, r8d; msPeriod
0x180036904  xor     edx, edx; pftDueTime
0x180036906  call    cs:__imp_SetThreadpoolTimer
0x18003690c  mov     rcx, [rbx+38h]; pti
0x180036910  mov     edx, 1; fCancelPendingCallbacks
0x180036915  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x18003691b  mov     rcx, rbx; this
0x18003691e  call    ?SavePersistedState@CPersistedControl@@AEAAJXZ; CPersistedControl::SavePersistedState(void)
0x180036923  mov     ebx, eax
0x180036925  test    eax, eax
0x180036927  jns     short loc_180036946
0x180036929  mov     rcx, [rsp+28h]; this
0x18003692e  lea     r8, aAvcoreAudiocor_2; "avcore\\audiocore\\server\\audioendpoin"...
0x180036935  mov     r9d, eax; char *
0x180036938  mov     edx, 21Ah; void *
0x18003693d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180036942  mov     eax, ebx
0x180036944  jmp     short loc_180036948
0x180036946  xor     eax, eax
0x180036948  add     rsp, 20h
0x18003694c  pop     rbx
0x18003694d  retn
```
