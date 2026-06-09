# CRPCTimeout::~CRPCTimeout(void)

- ea: `0x18001f364`
- end: `0x18001f3a5`
- name: `??1CRPCTimeout@@QEAA@XZ`
- size: `65`
- prototype: `void __fastcall(CRPCTimeout *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x18002db8b`
- `0x18002dc89`
- `0x18002dd88`

## callees

- `0x18001f364`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18001f37c`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18001f37c`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001f391`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18001f391`

## pseudocode

```c
void __fastcall CRPCTimeout::~CRPCTimeout(CRPCTimeout *this)
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
0x18001f364  push    rbx
0x18001f366  sub     rsp, 20h
0x18001f36a  cmp     dword ptr [rcx+8], 0
0x18001f36e  mov     rbx, rcx
0x18001f371  jl      short loc_18001F39F
0x18001f373  mov     dword ptr [rcx+8], 80004005h
0x18001f37a  xor     ecx, ecx; pReserved
0x18001f37c  call    cs:__imp_CoDisableCallCancellation
0x18001f382  mov     rdx, [rbx+10h]; Timer
0x18001f386  test    rdx, rdx
0x18001f389  jz      short loc_18001F39F
0x18001f38b  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18001f38f  xor     ecx, ecx; TimerQueue
0x18001f391  call    cs:__imp_DeleteTimerQueueTimer
0x18001f397  mov     qword ptr [rbx+10h], 0
0x18001f39f  add     rsp, 20h
0x18001f3a3  pop     rbx
0x18001f3a4  retn
```
