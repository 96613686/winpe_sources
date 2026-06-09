# ipx::mtf::MtfTransportClientCoreUI::ReleaseProxyStub(void)

- ea: `0x180021530`
- end: `0x1800215ba`
- name: `?ReleaseProxyStub@MtfTransportClientCoreUI@mtf@ipx@@UEAAJXZ`
- size: `138`
- prototype: `__int64 __fastcall(ipx::mtf::MtfTransportClientCoreUI *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x18001f3ac`

## callees

- `0x18001e89c`
- `0x1800209e8`
- `0x180021530`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002158f`
- `api-ms-win-core-com-l1-1-0!CoDisableCallCancellation` at `0x18002158f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800215a5`
- `api-ms-win-core-threadpool-legacy-l1-1-0!DeleteTimerQueueTimer` at `0x1800215a5`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall ipx::mtf::MtfTransportClientCoreUI::ReleaseProxyStub(
        ipx::mtf::MtfTransportClientCoreUI *this,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rcx
  __int64 result; // rax
  _BYTE Parameter[8]; // [rsp+20h] [rbp-28h] BYREF
  int v8; // [rsp+28h] [rbp-20h]
  HANDLE Timer; // [rsp+30h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  try
  {
    if ( *((_QWORD *)this + 40) )
    {
      CRPCTimeout::CRPCTimeout(Parameter);
      v5 = *((_QWORD *)this + 40);
      *((_QWORD *)this + 40) = 0;
      if ( v5 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
      if ( Parameter[4] )
        MtfPlatformTelemetry::ProxyStubTimedOut();
      if ( v8 >= 0 )
      {
        v8 = -2147467259;
        CoDisableCallCancellation(0);
        if ( Timer )
          DeleteTimerQueueTimer(0, Timer, (HANDLE)0xFFFFFFFFFFFFFFFFLL);
      }
    }
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x20C,
                           (unsigned int)"mincore\\textinput\\dev\\mtf\\internal\\transportcui\\transportcoreui.cpp",
                           a4);
  }
  return result;
}

```

## disassembly

```asm
0x180021530  push    rbx
0x180021532  sub     rsp, 40h
0x180021536  mov     rbx, rcx
0x180021539  cmp     qword ptr [rcx+140h], 0
0x180021541  jz      short loc_1800215AB
0x180021543  lea     rcx, [rsp+48h+Parameter]; Parameter
0x180021548  call    ??0CRPCTimeout@@QEAA@K@Z; CRPCTimeout::CRPCTimeout(ulong)
0x18002154d  nop
0x18002154e  mov     rcx, [rbx+140h]
0x180021555  mov     qword ptr [rbx+140h], 0
0x180021560  test    rcx, rcx
0x180021563  jz      short loc_180021571
0x180021565  mov     rax, [rcx]
0x180021568  mov     rax, [rax+10h]
0x18002156c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021571  cmp     [rsp+48h+var_24], 0
0x180021576  jz      short loc_18002157E
0x180021578  call    ?ProxyStubTimedOut@MtfPlatformTelemetry@@SAXXZ; MtfPlatformTelemetry::ProxyStubTimedOut(void)
0x18002157d  nop
0x18002157e  cmp     [rsp+48h+var_20], 0
0x180021583  jl      short loc_1800215AB
0x180021585  mov     [rsp+48h+var_20], 80004005h
0x18002158d  xor     ecx, ecx; pReserved
0x18002158f  call    cs:__imp_CoDisableCallCancellation
0x180021595  mov     rdx, [rsp+48h+Timer]; Timer
0x18002159a  test    rdx, rdx
0x18002159d  jz      short loc_1800215AB
0x18002159f  or      r8, 0FFFFFFFFFFFFFFFFh; CompletionEvent
0x1800215a3  xor     ecx, ecx; TimerQueue
0x1800215a5  call    cs:__imp_DeleteTimerQueueTimer
0x1800215ab  xor     eax, eax
0x1800215ad  jmp     short loc_1800215B3
0x1800215af  mov     eax, [rsp+48h+arg_0]
0x1800215b3  add     rsp, 40h
0x1800215b7  pop     rbx
0x1800215b8  retn
```
