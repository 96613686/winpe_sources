# KerbClientIumRpcCleanup(void)

- ea: `0x140014cf4`
- end: `0x140014d63`
- name: `?KerbClientIumRpcCleanup@@YAXXZ`
- size: `111`
- prototype: `void(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1400063f0`
- `0x14000685c`

## callees

- `0x140001288`
- `0x14001212c`
- `0x140014cf4`

## import_xrefs

- `KerbClientShared!KerbClientSharedCleanup` at `0x140014d4b`
- `KerbClientShared!KerbClientSharedCleanup` at `0x140014d4b`
- `ntdll!RtlDeleteCriticalSection` at `0x140014d5c`
- `RPCRT4!RpcServerUnregisterIf` at `0x140014d39`
- `RPCRT4!RpcServerUnregisterIf` at `0x140014d39`

## pseudocode

```c
void KerbClientIumRpcCleanup(void)
{
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      11,
      WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids,
      "KerbClientIumRpcCleanup");
  RpcServerUnregisterIf(qword_14003F1E0, 0, 0);
  TraceLoggingUnregister_EventUnregister(&dword_140052168);
  KerbClientSharedCleanup();
  RtlDeleteCriticalSection(&KeyAgreementTableLock);
}

```

## disassembly

```asm
0x140014cf4  sub     rsp, 28h
0x140014cf8  mov     rcx, cs:WPP_GLOBAL_Control
0x140014cff  lea     rax, WPP_GLOBAL_Control
0x140014d06  cmp     rcx, rax
0x140014d09  jz      short loc_140014D2D
0x140014d0b  test    byte ptr [rcx+1Ch], 4
0x140014d0f  jz      short loc_140014D2D
0x140014d11  mov     rcx, [rcx+10h]
0x140014d15  lea     r9, aKerbclientiumr; "KerbClientIumRpcCleanup"
0x140014d1c  mov     edx, 0Bh
0x140014d21  lea     r8, WPP_d5c6fd37444639aeca2bc0daa2920ffe_Traceguids
0x140014d28  call    WPP_SF_s
0x140014d2d  xor     r8d, r8d; WaitForCallsToComplete
0x140014d30  lea     rcx, qword_14003F1E0; IfSpec
0x140014d37  xor     edx, edx; MgrTypeUuid
0x140014d39  call    cs:__imp_RpcServerUnregisterIf
0x140014d3f  lea     rcx, dword_140052168
0x140014d46  call    TraceLoggingUnregister_EventUnregister
0x140014d4b  call    cs:__imp_?KerbClientSharedCleanup@@YAXXZ; KerbClientSharedCleanup(void)
0x140014d51  lea     rcx, ?KeyAgreementTableLock@@3U_RTL_CRITICAL_SECTION@@A; _RTL_CRITICAL_SECTION KeyAgreementTableLock
0x140014d58  add     rsp, 28h
0x140014d5c  jmp     cs:__imp_RtlDeleteCriticalSection
```
