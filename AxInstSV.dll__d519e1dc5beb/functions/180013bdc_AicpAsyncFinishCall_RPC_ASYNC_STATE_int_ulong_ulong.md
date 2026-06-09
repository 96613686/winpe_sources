# AicpAsyncFinishCall(_RPC_ASYNC_STATE *,int,ulong,ulong)

- ea: `0x180013bdc`
- end: `0x180013c5f`
- name: `?AicpAsyncFinishCall@@YAKPEAU_RPC_ASYNC_STATE@@HKK@Z`
- size: `131`
- prototype: `unsigned int __fastcall(PRPC_ASYNC_STATE pAsync, int, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800138f0`

## callees

- `0x1800023c9`
- `0x180013bdc`

## import_xrefs

- `RPCRT4!RpcAsyncCompleteCall` at `0x180013c3a`
- `RPCRT4!RpcAsyncCompleteCall` at `0x180013c3a`
- `RPCRT4!RpcAsyncCancelCall` at `0x180013c20`
- `RPCRT4!RpcAsyncCancelCall` at `0x180013c20`

## pseudocode

```c
__int64 __fastcall AicpAsyncFinishCall(PRPC_ASYNC_STATE pAsync, __int64 a2, __int64 a3, DWORD a4)
{
  DWORD v4; // ebx
  unsigned int v6; // eax
  DWORD Reply; // [rsp+40h] [rbp+18h] BYREF

  Reply = 0;
  v4 = a4;
  if ( !a4 )
    v4 = WaitForSingleObject_0(pAsync->u.APC.NotificationRoutine, 0xFFFFFFFF);
  if ( v4 == 258 )
  {
    RpcAsyncCancelCall(pAsync, 1);
    WaitForSingleObject_0(pAsync->u.APC.NotificationRoutine, 0xFFFFFFFF);
  }
  v6 = RpcAsyncCompleteCall(pAsync, &Reply);
  if ( !v4 )
  {
    v4 = Reply;
    if ( v6 )
      return v6;
  }
  return v4;
}

```

## disassembly

```asm
0x180013bdc  mov     rax, rsp
0x180013bdf  mov     [rax+8], rbx
0x180013be3  mov     [rax+10h], rsi
0x180013be7  mov     [rax+18h], r8d
0x180013beb  push    rdi
0x180013bec  sub     rsp, 20h
0x180013bf0  mov     dword ptr [rax+18h], 0
0x180013bf7  mov     ebx, r9d
0x180013bfa  mov     rsi, rcx
0x180013bfd  test    r9d, r9d
0x180013c00  jnz     short loc_180013C10
0x180013c02  mov     rcx, [rcx+30h]; hHandle
0x180013c06  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013c09  call    WaitForSingleObject_0
0x180013c0e  mov     ebx, eax
0x180013c10  cmp     ebx, 102h
0x180013c16  jnz     short loc_180013C32
0x180013c18  mov     edx, 1; fAbort
0x180013c1d  mov     rcx, rsi; pAsync
0x180013c20  call    cs:__imp_RpcAsyncCancelCall
0x180013c26  mov     rcx, [rsi+30h]; hHandle
0x180013c2a  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180013c2d  call    WaitForSingleObject_0
0x180013c32  lea     rdx, [rsp+28h+Reply]; Reply
0x180013c37  mov     rcx, rsi; pAsync
0x180013c3a  call    cs:__imp_RpcAsyncCompleteCall
0x180013c40  test    ebx, ebx
0x180013c42  jnz     short loc_180013C4D
0x180013c44  mov     ebx, [rsp+28h+Reply]
0x180013c48  test    eax, eax
0x180013c4a  cmovnz  ebx, eax
0x180013c4d  mov     rsi, [rsp+28h+arg_8]
0x180013c52  mov     eax, ebx
0x180013c54  mov     rbx, [rsp+28h+arg_0]
0x180013c59  add     rsp, 20h
0x180013c5d  pop     rdi
0x180013c5e  retn
```
