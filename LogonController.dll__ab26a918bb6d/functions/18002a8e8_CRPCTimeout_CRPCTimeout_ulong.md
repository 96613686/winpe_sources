# CRPCTimeout::CRPCTimeout(ulong)

- ea: `0x18002a8e8`
- end: `0x18002a95b`
- name: `??0CRPCTimeout@@QEAA@K@Z`
- size: `115`
- prototype: `CRPCTimeout *__fastcall(PVOID Parameter, unsigned int)`
- caller_count: `7`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180028280`
- `0x180028f70`
- `0x18002a334`
- `0x18002aca0`
- `0x18002b2e8`
- `0x18002f9e0`
- `0x18004c01c`

## callees

- `0x18002a8e8`

## import_xrefs

- `KERNEL32!CreateTimerQueueTimer` at `0x18002a947`
- `KERNEL32!CreateTimerQueueTimer` at `0x18002a947`
- `KERNEL32!GetCurrentThreadId` at `0x18002a8f5`
- `KERNEL32!GetCurrentThreadId` at `0x18002a8f5`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002a912`
- `api-ms-win-core-com-l1-1-0!CoEnableCallCancellation` at `0x18002a912`

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
    CreateTimerQueueTimer((PHANDLE)Parameter + 2, 0, CBaseRPCTimeout::s_Callback, Parameter, 0x1388u, 0x3E8u, 0);
  return (CRPCTimeout *)Parameter;
}

```

## disassembly

```asm
0x18002a8e8  mov     [rsp+arg_0], rbx
0x18002a8ed  push    rdi
0x18002a8ee  sub     rsp, 40h
0x18002a8f2  mov     rbx, rcx
0x18002a8f5  call    cs:__imp_GetCurrentThreadId
0x18002a8fb  xor     ecx, ecx; pReserved
0x18002a8fd  mov     byte ptr [rbx+4], 0
0x18002a901  mov     [rbx], eax
0x18002a903  mov     dword ptr [rbx+8], 80004005h
0x18002a90a  mov     qword ptr [rbx+10h], 0
0x18002a912  call    cs:__imp_CoEnableCallCancellation
0x18002a918  mov     [rbx+8], eax
0x18002a91b  test    eax, eax
0x18002a91d  js      short loc_18002A94D
0x18002a91f  mov     [rsp+48h+Flags], 0; Flags
0x18002a927  lea     r8, ?s_Callback@CBaseRPCTimeout@@CAXPEAXE@Z; Callback
0x18002a92e  mov     [rsp+48h+Period], 3E8h; Period
0x18002a936  lea     rcx, [rbx+10h]; phNewTimer
0x18002a93a  mov     r9, rbx; Parameter
0x18002a93d  mov     [rsp+48h+DueTime], 1388h; DueTime
0x18002a945  xor     edx, edx; TimerQueue
0x18002a947  call    cs:__imp_CreateTimerQueueTimer
0x18002a94d  mov     rax, rbx
0x18002a950  mov     rbx, [rsp+48h+arg_0]
0x18002a955  add     rsp, 40h
0x18002a959  pop     rdi
0x18002a95a  retn
```
