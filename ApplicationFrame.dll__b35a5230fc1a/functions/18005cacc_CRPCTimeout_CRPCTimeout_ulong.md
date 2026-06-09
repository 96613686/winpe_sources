# CRPCTimeout::CRPCTimeout(ulong)

- ea: `0x18005cacc`
- end: `0x18005cb44`
- name: `??0CRPCTimeout@@QEAA@K@Z`
- size: `120`
- prototype: `CRPCTimeout *__fastcall(CRPCTimeout *__hidden this, unsigned int)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18005cf48`
- `0x18005dc10`
- `0x18005dd20`

## callees

- `0x18005cacc`
- `0x18005d1fc`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cad9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cad9`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18005cafe`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18005cafe`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005cb30`
- `api-ms-win-core-threadpool-legacy-l1-1-0!CreateTimerQueueTimer` at `0x18005cb30`

## pseudocode

```c
CRPCTimeout *__fastcall CRPCTimeout::CRPCTimeout(CRPCTimeout *this)
{
  DWORD CurrentThreadId; // eax
  HRESULT v3; // eax

  CurrentThreadId = GetCurrentThreadId();
  *((_BYTE *)this + 4) = 0;
  *(_DWORD *)this = CurrentThreadId;
  *((_DWORD *)this + 2) = -2147467259;
  *((_QWORD *)this + 2) = 0;
  CBaseRPCTimeout::Disarm(this);
  v3 = CoEnableCallCancellation(0);
  *((_DWORD *)this + 2) = v3;
  if ( v3 >= 0 )
    CreateTimerQueueTimer((PHANDLE)this + 2, 0, CBaseRPCTimeout::s_Callback, this, 0x3E8u, 0x3E8u, 0);
  return this;
}

```

## disassembly

```asm
0x18005cacc  mov     [rsp+arg_0], rbx
0x18005cad1  push    rdi
0x18005cad2  sub     rsp, 40h
0x18005cad6  mov     rbx, rcx
0x18005cad9  call    cs:__imp_GetCurrentThreadId
0x18005cadf  mov     rcx, rbx; this
0x18005cae2  mov     byte ptr [rbx+4], 0
0x18005cae6  mov     [rbx], eax
0x18005cae8  mov     dword ptr [rbx+8], 80004005h
0x18005caef  mov     qword ptr [rbx+10h], 0
0x18005caf7  call    ?Disarm@CBaseRPCTimeout@@QEAAXXZ; CBaseRPCTimeout::Disarm(void)
0x18005cafc  xor     ecx, ecx; pReserved
0x18005cafe  call    cs:__imp_CoEnableCallCancellation
0x18005cb04  mov     [rbx+8], eax
0x18005cb07  test    eax, eax
0x18005cb09  js      short loc_18005CB36
0x18005cb0b  mov     eax, 3E8h
0x18005cb10  mov     [rsp+48h+Flags], 0; Flags
0x18005cb18  mov     [rsp+48h+Period], eax; Period
0x18005cb1c  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18005cb23  mov     r9, rbx; Parameter
0x18005cb26  mov     [rsp+48h+DueTime], eax; DueTime
0x18005cb2a  xor     edx, edx; TimerQueue
0x18005cb2c  lea     rcx, [rbx+10h]; phNewTimer
0x18005cb30  call    cs:__imp_CreateTimerQueueTimer
0x18005cb36  mov     rax, rbx
0x18005cb39  mov     rbx, [rsp+48h+arg_0]
0x18005cb3e  add     rsp, 40h
0x18005cb42  pop     rdi
0x18005cb43  retn
```
