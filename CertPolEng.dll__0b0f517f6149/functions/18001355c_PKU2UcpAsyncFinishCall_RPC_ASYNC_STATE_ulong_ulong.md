# PKU2UcpAsyncFinishCall(_RPC_ASYNC_STATE *,ulong,ulong)

- ea: `0x18001355c`
- end: `0x18001361a`
- name: `?PKU2UcpAsyncFinishCall@@YAKPEAU_RPC_ASYNC_STATE@@KK@Z`
- size: `190`
- prototype: `__int64 __fastcall(PRPC_ASYNC_STATE pAsync, __int64, DWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180013404`

## callees

- `0x18000c344`
- `0x18001355c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001358a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800135cb`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x18001358a`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800135cb`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800135f5`
- `RPCRT4!RpcAsyncCompleteCall` at `0x1800135f5`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800135a2`
- `RPCRT4!RpcAsyncCancelCall` at `0x1800135a2`

## pseudocode

```c
__int64 __fastcall PKU2UcpAsyncFinishCall(PRPC_ASYNC_STATE pAsync, __int64 a2, DWORD a3)
{
  DWORD v3; // ebx
  unsigned int v5; // eax
  __int64 v6; // rdx
  __int64 v7; // rcx
  DWORD v8; // eax
  __int64 v9; // rdx
  __int64 v10; // rcx
  unsigned int v11; // eax
  DWORD Reply; // [rsp+38h] [rbp+10h] BYREF

  Reply = 0;
  v3 = a3;
  if ( !a3 )
    v3 = WaitForSingleObject(pAsync->u.APC.NotificationRoutine, 0x7530u);
  if ( v3 == 258 )
  {
    v5 = RpcAsyncCancelCall(pAsync, 1);
    if ( v5 && (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v7, v6, "RpcAsyncCancelCall", v5);
    v8 = WaitForSingleObject(pAsync->u.APC.NotificationRoutine, 0xFFFFFFFF);
    if ( v8 && (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      McTemplateU0sq_EtwEventWriteTransfer(v10, v9, "WaitForSingleObject", v8);
  }
  v11 = RpcAsyncCompleteCall(pAsync, &Reply);
  if ( !v3 )
  {
    v3 = Reply;
    if ( v11 )
      return v11;
  }
  return v3;
}

```

## disassembly

```asm
0x18001355c  mov     rax, rsp
0x18001355f  mov     [rax+8], rbx
0x180013563  mov     [rax+18h], rsi
0x180013567  mov     [rax+10h], edx
0x18001356a  push    rdi
0x18001356b  sub     rsp, 20h
0x18001356f  mov     dword ptr [rax+10h], 0
0x180013576  mov     ebx, r8d
0x180013579  mov     rsi, rcx
0x18001357c  test    r8d, r8d
0x18001357f  jnz     short loc_180013592
0x180013581  mov     rcx, [rcx+30h]; hHandle
0x180013585  mov     edx, 7530h; dwMilliseconds
0x18001358a  call    cs:__imp_WaitForSingleObject
0x180013590  mov     ebx, eax
0x180013592  cmp     ebx, 102h
0x180013598  jnz     short loc_1800135ED
0x18001359a  mov     edx, 1; fAbort
0x18001359f  mov     rcx, rsi; pAsync
0x1800135a2  call    cs:__imp_RpcAsyncCancelCall
0x1800135a8  test    eax, eax
0x1800135aa  jz      short loc_1800135C4
0x1800135ac  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800135b3  jz      short loc_1800135C4
0x1800135b5  mov     r9d, eax
0x1800135b8  lea     r8, aRpcasynccancel; "RpcAsyncCancelCall"
0x1800135bf  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800135c4  mov     rcx, [rsi+30h]; hHandle
0x1800135c8  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800135cb  call    cs:__imp_WaitForSingleObject
0x1800135d1  test    eax, eax
0x1800135d3  jz      short loc_1800135ED
0x1800135d5  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x1800135dc  jz      short loc_1800135ED
0x1800135de  mov     r9d, eax
0x1800135e1  lea     r8, aWaitforsingleo; "WaitForSingleObject"
0x1800135e8  call    McTemplateU0sq_EtwEventWriteTransfer
0x1800135ed  lea     rdx, [rsp+28h+Reply]; Reply
0x1800135f2  mov     rcx, rsi; pAsync
0x1800135f5  call    cs:__imp_RpcAsyncCompleteCall
0x1800135fb  test    ebx, ebx
0x1800135fd  jnz     short loc_180013608
0x1800135ff  mov     ebx, [rsp+28h+Reply]
0x180013603  test    eax, eax
0x180013605  cmovnz  ebx, eax
0x180013608  mov     rsi, [rsp+28h+arg_10]
0x18001360d  mov     eax, ebx
0x18001360f  mov     rbx, [rsp+28h+arg_0]
0x180013614  add     rsp, 20h
0x180013618  pop     rdi
0x180013619  retn
```
