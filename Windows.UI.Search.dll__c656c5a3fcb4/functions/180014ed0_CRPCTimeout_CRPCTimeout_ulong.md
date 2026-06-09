# CRPCTimeout::CRPCTimeout(ulong)

- ea: `0x180014ed0`
- end: `0x180014f52`
- name: `??0CRPCTimeout@@QEAA@K@Z`
- size: `130`
- prototype: `CRPCTimeout *__fastcall(CRPCTimeout *__hidden this, DWORD DueTime)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800151ec`
- `0x18002060c`
- `0x1800221c4`
- `0x1800361f0`
- `0x18003a04c`

## callees

- `0x180014ed0`
- `0x180014f98`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014edf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014edf`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180014f0e`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x180014f0e`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180014f3f`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x180014f3f`

## pseudocode

```c
CRPCTimeout *__fastcall CRPCTimeout::CRPCTimeout(CRPCTimeout *this, DWORD DueTime)
{
  DWORD CurrentThreadId; // eax
  DWORD v5; // esi
  HRESULT v6; // eax

  CurrentThreadId = GetCurrentThreadId();
  *((_BYTE *)this + 4) = 0;
  *(_DWORD *)this = CurrentThreadId;
  *((_DWORD *)this + 2) = -2147467259;
  *((_QWORD *)this + 2) = 0;
  CBaseRPCTimeout::Disarm(this);
  v5 = 5000;
  if ( DueTime )
    v5 = DueTime;
  v6 = CoEnableCallCancellation(0);
  *((_DWORD *)this + 2) = v6;
  if ( v6 >= 0 )
    CreateTimerQueueTimer((PHANDLE)this + 2, 0, CBaseRPCTimeout::s_Callback, this, v5, 0x3E8u, 0);
  return this;
}

```

## disassembly

```asm
0x180014ed0  push    rbx
0x180014ed2  push    rsi
0x180014ed3  push    rdi
0x180014ed4  push    r14
0x180014ed6  sub     rsp, 48h
0x180014eda  mov     ebx, edx
0x180014edc  mov     rdi, rcx
0x180014edf  call    cs:__imp_GetCurrentThreadId
0x180014ee5  mov     rcx, rdi; this
0x180014ee8  mov     byte ptr [rdi+4], 0
0x180014eec  mov     [rdi], eax
0x180014eee  mov     dword ptr [rdi+8], 80004005h
0x180014ef5  mov     qword ptr [rdi+10h], 0
0x180014efd  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x180014f02  test    ebx, ebx
0x180014f04  mov     esi, 1388h
0x180014f09  cmovnz  esi, ebx
0x180014f0c  xor     ecx, ecx; pReserved
0x180014f0e  call    cs:__imp_CoEnableCallCancellation
0x180014f14  mov     [rdi+8], eax
0x180014f17  test    eax, eax
0x180014f19  js      short loc_180014F45
0x180014f1b  mov     [rsp+68h+Flags], 0; Flags
0x180014f23  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x180014f2a  mov     [rsp+68h+Period], 3E8h; Period
0x180014f32  lea     rcx, [rdi+10h]; phNewTimer
0x180014f36  mov     r9, rdi; Parameter
0x180014f39  mov     [rsp+68h+DueTime], esi; DueTime
0x180014f3d  xor     edx, edx; TimerQueue
0x180014f3f  call    cs:__imp_CreateTimerQueueTimer
0x180014f45  mov     rax, rdi
0x180014f48  add     rsp, 48h
0x180014f4c  pop     r14
0x180014f4e  pop     rdi
0x180014f4f  pop     rsi
0x180014f50  pop     rbx
0x180014f51  retn
```
