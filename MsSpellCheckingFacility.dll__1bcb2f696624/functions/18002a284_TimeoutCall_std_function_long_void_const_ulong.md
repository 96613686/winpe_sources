# TimeoutCall(std::function<long (void)> const &,ulong)

- ea: `0x18002a284`
- end: `0x18002a2d7`
- name: `?TimeoutCall@@YAJAEBV?$function@$$A6AJXZ@std@@K@Z`
- size: `83`
- prototype: ``
- caller_count: `16`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180029be0`
- `0x180029c70`
- `0x180029d00`
- `0x180053428`
- `0x180055790`
- `0x180055820`
- `0x180055d30`
- `0x180056c70`
- `0x180057a40`
- `0x180057e44`
- `0x180058ad0`
- `0x180058ca0`
- `0x18005a6d0`
- `0x18005aad0`
- `0x18005bc58`
- `0x18005c680`

## callees

- `0x18002a284`
- `0x18002a2e0`
- `0x18002a30c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002a2b3`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002a2b3`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002a2c9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x18002a2c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall TimeoutCall(__int64 a1)
{
  unsigned int v2; // ebx
  _BYTE v4[8]; // [rsp+20h] [rbp-28h] BYREF
  int v5; // [rsp+28h] [rbp-20h]
  HANDLE Timer; // [rsp+30h] [rbp-18h]

  CRPCTimeout::CRPCTimeout((CRPCTimeout *)v4);
  v2 = std::_Func_class<long,>::operator()(a1);
  if ( v5 >= 0 )
  {
    v5 = -2147467259;
    CoDisableCallCancellation(0);
    if ( Timer )
      DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
  }
  return v2;
}

```

## disassembly

```asm
0x18002a284  push    rbx
0x18002a286  sub     rsp, 40h
0x18002a28a  mov     rbx, rcx
0x18002a28d  lea     rcx, [rsp+48h+var_28]; this
0x18002a292  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18002a297  nop
0x18002a298  mov     rcx, rbx
0x18002a29b  call    ??R?$_Func_class@J$$V@std@@QEBAJXZ; std::_Func_class<long,>::operator()(void)
0x18002a2a0  mov     ebx, eax
0x18002a2a2  cmp     [rsp+48h+var_20], 0
0x18002a2a7  jl      short loc_18002A2CF
0x18002a2a9  mov     [rsp+48h+var_20], 80004005h
0x18002a2b1  xor     ecx, ecx; pReserved
0x18002a2b3  call    cs:__imp_CoDisableCallCancellation
0x18002a2b9  mov     rdx, [rsp+48h+Timer]; Timer
0x18002a2be  test    rdx, rdx
0x18002a2c1  jz      short loc_18002A2CF
0x18002a2c3  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x18002a2c7  xor     ecx, ecx; TimerQueue
0x18002a2c9  call    cs:__imp_DeleteTimerQueueTimer
0x18002a2cf  mov     eax, ebx
0x18002a2d1  add     rsp, 40h
0x18002a2d5  pop     rbx
0x18002a2d6  retn
```
