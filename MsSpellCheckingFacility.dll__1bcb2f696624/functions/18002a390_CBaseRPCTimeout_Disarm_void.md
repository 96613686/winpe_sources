# CBaseRPCTimeout::Disarm(void)

- ea: `0x18002a390`
- end: `0x18002a3d1`
- name: `?Disarm@CBaseRPCTimeout@@QEAAXXZ`
- size: `65`
- prototype: `void __fastcall(CBaseRPCTimeout *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002a30c`
- `0x180052660`

## callees

- `0x18002a390`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002a3a8`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002a3a8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002a3bd`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002a3bd`

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
0x18002a390  push    rbx
0x18002a392  sub     rsp, 20h
0x18002a396  cmp     dword ptr [rcx+8], 0
0x18002a39a  mov     rbx, rcx
0x18002a39d  jl      short loc_18002A3CB
0x18002a39f  mov     dword ptr [rcx+8], 80004005h
0x18002a3a6  xor     ecx, ecx; pReserved
0x18002a3a8  call    cs:__imp_CoDisableCallCancellation
0x18002a3ae  mov     rdx, [rbx+10h]; Timer
0x18002a3b2  test    rdx, rdx
0x18002a3b5  jz      short loc_18002A3CB
0x18002a3b7  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002a3bb  xor     ecx, ecx; TimerQueue
0x18002a3bd  call    cs:__imp_DeleteTimerQueueTimer
0x18002a3c3  mov     qword ptr [rbx+10h], 0
0x18002a3cb  add     rsp, 20h
0x18002a3cf  pop     rbx
0x18002a3d0  retn
```
