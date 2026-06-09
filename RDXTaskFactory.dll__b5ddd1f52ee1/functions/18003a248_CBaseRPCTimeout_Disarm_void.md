# CBaseRPCTimeout::Disarm(void)

- ea: `0x18003a248`
- end: `0x18003a289`
- name: `?Disarm@CBaseRPCTimeout@@QEAAXXZ`
- size: `65`
- prototype: `void __fastcall(CBaseRPCTimeout *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180036b50`
- `0x180036cf8`

## callees

- `0x18003a248`

## import_xrefs

- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003a275`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18003a275`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003a260`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18003a260`

## pseudocode

```c
void __fastcall CBaseRPCTimeout::Disarm(CBaseRPCTimeout *this)
{
  void *v2; // rdx

  if ( *((int *)this + 2) >= 0 )
  {
    *((_DWORD *)this + 2) = -2147467259;
    CoDisableCallCancellation(0);
    v2 = (void *)*((_QWORD *)this + 2);
    if ( v2 )
    {
      DeleteTimerQueueTimer(0, v2, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      *((_QWORD *)this + 2) = 0;
    }
  }
}

```

## disassembly

```asm
0x18003a248  push    rbx
0x18003a24a  sub     rsp, 20h
0x18003a24e  cmp     dword ptr [rcx+8], 0
0x18003a252  mov     rbx, rcx
0x18003a255  jl      short loc_18003A283
0x18003a257  mov     dword ptr [rcx+8], 80004005h
0x18003a25e  xor     ecx, ecx; pReserved
0x18003a260  call    cs:__imp_CoDisableCallCancellation
0x18003a266  mov     rdx, [rbx+10h]; Timer
0x18003a26a  test    rdx, rdx
0x18003a26d  jz      short loc_18003A283
0x18003a26f  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18003a273  xor     ecx, ecx; TimerQueue
0x18003a275  call    cs:__imp_DeleteTimerQueueTimer
0x18003a27b  mov     qword ptr [rbx+10h], 0
0x18003a283  add     rsp, 20h
0x18003a287  pop     rbx
0x18003a288  retn
```
