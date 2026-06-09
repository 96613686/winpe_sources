# InvokeWithRPCTimeout(void *,long (*)(void *),void *)

- ea: `0x180029f64`
- end: `0x18002a04b`
- name: `?InvokeWithRPCTimeout@@YAJPEAXP6AJ0@Z0@Z`
- size: `231`
- prototype: `__int64 __fastcall(void *, int (*)(void *), void *)`
- caller_count: `10`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18002a334`
- `0x18002b2e8`
- `0x18002be30`
- `0x18002d448`
- `0x18002fb04`
- `0x1800312b8`
- `0x180059f80`
- `0x18005caf4`
- `0x180067d20`
- `0x18006a5a0`

## callees

- `0x180029f64`
- `0x18002a060`
- `0x18009d010`

## import_xrefs

- `KERNEL32!DeleteTimerQueueTimer` at `0x18002a01a`
- `KERNEL32!DeleteTimerQueueTimer` at `0x18002a01a`
- `KERNEL32!CreateTimerQueueTimer` at `0x180029fdc`
- `KERNEL32!CreateTimerQueueTimer` at `0x180029fdc`
- `KERNEL32!GetCurrentThreadId` at `0x180029f81`
- `KERNEL32!GetCurrentThreadId` at `0x180029f81`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180029fa3`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180029fa3`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002a004`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002a004`

## pseudocode

```c
__int64 __fastcall InvokeWithRPCTimeout(void *a1, unsigned int (__fastcall *a2)(void *), void *a3)
{
  int v5; // ebx
  DWORD Parameter; // [rsp+40h] [rbp-28h] BYREF
  char v8; // [rsp+44h] [rbp-24h]
  HRESULT v9; // [rsp+48h] [rbp-20h]
  void *phNewTimer; // [rsp+50h] [rbp-18h] BYREF

  if ( (unsigned int)IsDebuggerPresent(a1) )
  {
    return a2(a3);
  }
  else
  {
    v8 = 0;
    Parameter = GetCurrentThreadId();
    phNewTimer = 0;
    v9 = CoEnableCallCancellation(0);
    if ( v9 >= 0 )
      CreateTimerQueueTimer(&phNewTimer, 0, CBaseRPCTimeout::s_Callback, &Parameter, 0x1388u, 0x3E8u, 0);
    v5 = a2(a3);
    if ( v5 < 0 && v8 )
      v5 = -2147417825;
    if ( v9 >= 0 )
    {
      v9 = -2147467259;
      CoDisableCallCancellation(0);
      if ( phNewTimer )
        DeleteTimerQueueTimer(0, phNewTimer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
    }
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180029f64  mov     [rsp+arg_0], rbx
0x180029f69  push    rdi
0x180029f6a  sub     rsp, 60h
0x180029f6e  mov     rbx, r8
0x180029f71  mov     rdi, rdx
0x180029f74  call    ?IsDebuggerPresent@@YAHPEAX@Z; IsDebuggerPresent(void *)
0x180029f79  test    eax, eax
0x180029f7b  jnz     loc_18002A02D
0x180029f81  call    cs:__imp_GetCurrentThreadId
0x180029f87  xor     ecx, ecx; pReserved
0x180029f89  mov     [rsp+68h+var_24], 0
0x180029f8e  mov     [rsp+68h+Parameter], eax
0x180029f92  mov     [rsp+68h+var_20], 80004005h
0x180029f9a  mov     [rsp+68h+phNewTimer], 0
0x180029fa3  call    cs:__imp_CoEnableCallCancellation
0x180029fa9  mov     [rsp+68h+var_20], eax
0x180029fad  test    eax, eax
0x180029faf  js      short loc_180029FE2
0x180029fb1  mov     [rsp+68h+Flags], 0; Flags
0x180029fb9  lea     r9, [rsp+68h+Parameter]; Parameter
0x180029fbe  mov     [rsp+68h+Period], 3E8h; Period
0x180029fc6  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x180029fcd  xor     edx, edx; TimerQueue
0x180029fcf  mov     [rsp+68h+DueTime], 1388h; DueTime
0x180029fd7  lea     rcx, [rsp+68h+phNewTimer]; phNewTimer
0x180029fdc  call    cs:__imp_CreateTimerQueueTimer
0x180029fe2  mov     rcx, rbx
0x180029fe5  mov     rax, rdi
0x180029fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180029fed  mov     ebx, eax
0x180029fef  test    eax, eax
0x180029ff1  js      short loc_18002A03C
0x180029ff3  cmp     [rsp+68h+var_20], 0
0x180029ff8  jl      short loc_18002A020
0x180029ffa  xor     ecx, ecx; pReserved
0x180029ffc  mov     [rsp+68h+var_20], 80004005h
0x18002a004  call    cs:__imp_CoDisableCallCancellation
0x18002a00a  mov     rdx, [rsp+68h+phNewTimer]; Timer
0x18002a00f  test    rdx, rdx
0x18002a012  jz      short loc_18002A020
0x18002a014  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002a018  xor     ecx, ecx; TimerQueue
0x18002a01a  call    cs:__imp_DeleteTimerQueueTimer
0x18002a020  mov     eax, ebx
0x18002a022  mov     rbx, [rsp+68h+arg_0]
0x18002a027  add     rsp, 60h
0x18002a02b  pop     rdi
0x18002a02c  retn
0x18002a02d  mov     rcx, rbx
0x18002a030  mov     rax, rdi
0x18002a033  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a038  mov     ebx, eax
0x18002a03a  jmp     short loc_18002A020
0x18002a03c  cmp     [rsp+68h+var_24], 0
0x18002a041  mov     eax, 8001011Fh
0x18002a046  cmovnz  ebx, eax
0x18002a049  jmp     short loc_180029FF3
```
