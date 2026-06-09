# CBaseRPCTimeout::Disarm(void)

- ea: `0x180014f98`
- end: `0x180014fd9`
- name: `?Disarm@CBaseRPCTimeout@@QEAAXXZ`
- size: `65`
- prototype: `void __fastcall(CBaseRPCTimeout *__hidden this)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180014ed0`
- `0x180014f7c`
- `0x1800151ec`
- `0x18002060c`
- `0x1800221c4`
- `0x1800361f0`
- `0x18003a04c`

## callees

- `0x180014f98`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180014fb0`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x180014fb0`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180014fc5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x180014fc5`

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
0x180014f98  push    rbx
0x180014f9a  sub     rsp, 20h
0x180014f9e  cmp     dword ptr [rcx+8], 0
0x180014fa2  mov     rbx, rcx
0x180014fa5  jl      short loc_180014FD3
0x180014fa7  mov     dword ptr [rcx+8], 80004005h
0x180014fae  xor     ecx, ecx; pReserved
0x180014fb0  call    cs:__imp_CoDisableCallCancellation
0x180014fb6  mov     rdx, [rbx+10h]; Timer
0x180014fba  test    rdx, rdx
0x180014fbd  jz      short loc_180014FD3
0x180014fbf  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x180014fc3  xor     ecx, ecx; TimerQueue
0x180014fc5  call    cs:__imp_DeleteTimerQueueTimer
0x180014fcb  mov     qword ptr [rbx+10h], 0
0x180014fd3  add     rsp, 20h
0x180014fd7  pop     rbx
0x180014fd8  retn
```
