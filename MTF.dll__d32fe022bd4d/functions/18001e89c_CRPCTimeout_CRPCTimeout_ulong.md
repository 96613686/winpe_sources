# CRPCTimeout::CRPCTimeout(ulong)

- ea: `0x18001e89c`
- end: `0x18001e90c`
- name: `??0CRPCTimeout@@QEAA@K@Z`
- size: `112`
- prototype: `CRPCTimeout *__fastcall(PVOID Parameter, unsigned int)`
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180020110`
- `0x180021530`
- `0x180022728`

## callees

- `0x18001e89c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18001e8c6`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18001e8c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e8a9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e8a9`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001e8f8`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18001e8f8`

## pseudocode

```c
CRPCTimeout *__fastcall CRPCTimeout::CRPCTimeout(PVOID Parameter)
{
  DWORD CurrentThreadId; // eax
  HRESULT v3; // eax

  CurrentThreadId = GetCurrentThreadId();
  *((_BYTE *)Parameter + 4) = 0;
  *(_DWORD *)Parameter = CurrentThreadId;
  *((_DWORD *)Parameter + 2) = -2147467259;
  *((_QWORD *)Parameter + 2) = 0;
  v3 = CoEnableCallCancellation(0);
  *((_DWORD *)Parameter + 2) = v3;
  if ( v3 >= 0 )
    CreateTimerQueueTimer((PHANDLE)Parameter + 2, 0, CBaseRPCTimeout::s_Callback, Parameter, 0x3E8u, 0x3E8u, 0);
  return (CRPCTimeout *)Parameter;
}

```

## disassembly

```asm
0x18001e89c  mov     [rsp+arg_0], rbx
0x18001e8a1  push    rdi
0x18001e8a2  sub     rsp, 40h
0x18001e8a6  mov     rbx, rcx
0x18001e8a9  call    cs:__imp_GetCurrentThreadId
0x18001e8af  xor     ecx, ecx; pReserved
0x18001e8b1  mov     byte ptr [rbx+4], 0
0x18001e8b5  mov     [rbx], eax
0x18001e8b7  mov     dword ptr [rbx+8], 80004005h
0x18001e8be  mov     qword ptr [rbx+10h], 0
0x18001e8c6  call    cs:__imp_CoEnableCallCancellation
0x18001e8cc  mov     [rbx+8], eax
0x18001e8cf  test    eax, eax
0x18001e8d1  js      short loc_18001E8FE
0x18001e8d3  mov     eax, 3E8h
0x18001e8d8  mov     [rsp+48h+Flags], 0; Flags
0x18001e8e0  mov     [rsp+48h+Period], eax; Period
0x18001e8e4  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18001e8eb  mov     r9, rbx; Parameter
0x18001e8ee  mov     [rsp+48h+DueTime], eax; DueTime
0x18001e8f2  xor     edx, edx; TimerQueue
0x18001e8f4  lea     rcx, [rbx+10h]; phNewTimer
0x18001e8f8  call    cs:__imp_CreateTimerQueueTimer
0x18001e8fe  mov     rax, rbx
0x18001e901  mov     rbx, [rsp+48h+arg_0]
0x18001e906  add     rsp, 40h
0x18001e90a  pop     rdi
0x18001e90b  retn
```
