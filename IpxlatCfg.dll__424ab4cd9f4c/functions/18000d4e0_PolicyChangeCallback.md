# PolicyChangeCallback

- ea: `0x18000d4e0`
- end: `0x18000d54a`
- name: `PolicyChangeCallback`
- size: `106`
- prototype: `void __fastcall(PTP_CALLBACK_INSTANCE Instance, _QWORD *Context, PTP_WAIT Wait, __int64 WaitResult)`
- caller_count: `0`
- callee_count: `3`
- tags: `registry_config`

## callees

- `0x18000d4e0`
- `0x18000e478`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000d510`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18000d510`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d528`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18000d528`

## pseudocode

```c
void __fastcall PolicyChangeCallback(
        PTP_CALLBACK_INSTANCE Instance,
        _QWORD *Context,
        PTP_WAIT Wait,
        __int64 WaitResult)
{
  if ( phkResult )
  {
    IPxlatPolicyMgrLogger::LogInfo(
      (IPxlatPolicyMgrLogger *)(phkResult + 15),
      L"Calling group policy change callback",
      Wait,
      WaitResult);
    ResetEvent(phkResult[1]);
    SetThreadpoolWait((PTP_WAIT)phkResult[2], phkResult[1], 0);
    if ( Context )
    {
      if ( *Context )
        ((void (__fastcall *)(_QWORD))*Context)(Context[1]);
    }
  }
}

```

## disassembly

```asm
0x18000d4e0  push    rbx
0x18000d4e2  sub     rsp, 20h
0x18000d4e6  mov     rcx, cs:phkResult
0x18000d4ed  mov     rbx, rdx
0x18000d4f0  test    rcx, rcx
0x18000d4f3  jz      short loc_18000D544
0x18000d4f5  add     rcx, 78h ; 'x'; this
0x18000d4f9  lea     rdx, aCallingGroupPo; "Calling group policy change callback"
0x18000d500  call    ?LogInfo@IPxlatPolicyMgrLogger@@QEAAXPEBGZZ; IPxlatPolicyMgrLogger::LogInfo(ushort const *,...)
0x18000d505  mov     rcx, cs:phkResult
0x18000d50c  mov     rcx, [rcx+8]; hEvent
0x18000d510  call    cs:__imp_ResetEvent
0x18000d516  mov     rcx, cs:phkResult
0x18000d51d  xor     r8d, r8d; pftTimeout
0x18000d520  mov     rdx, [rcx+8]; h
0x18000d524  mov     rcx, [rcx+10h]; pwa
0x18000d528  call    cs:__imp_SetThreadpoolWait
0x18000d52e  test    rbx, rbx
0x18000d531  jz      short loc_18000D544
0x18000d533  mov     rax, [rbx]
0x18000d536  test    rax, rax
0x18000d539  jz      short loc_18000D544
0x18000d53b  mov     rcx, [rbx+8]
0x18000d53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d544  add     rsp, 20h
0x18000d548  pop     rbx
0x18000d549  retn
```
