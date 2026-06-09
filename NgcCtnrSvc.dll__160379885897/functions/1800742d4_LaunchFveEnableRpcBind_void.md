# LaunchFveEnableRpcBind(void * *)

- ea: `0x1800742d4`
- end: `0x1800743ca`
- name: `?LaunchFveEnableRpcBind@@YAJPEAPEAX@Z`
- size: `246`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180074084`
- `0x180074138`

## callees

- `0x1800742d4`
- `0x1800743d0`

## import_xrefs

- `RPCRT4!RpcBindingFree` at `0x180074378`
- `RPCRT4!RpcBindingFree` at `0x180074399`
- `RPCRT4!RpcBindingFree` at `0x180074378`
- `RPCRT4!RpcBindingFree` at `0x180074399`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180074352`
- `RPCRT4!RpcBindingFromStringBindingW` at `0x180074352`
- `RPCRT4!RpcStringFreeW` at `0x1800743b0`
- `RPCRT4!RpcStringFreeW` at `0x1800743b0`
- `RPCRT4!RpcStringBindingComposeW` at `0x18007432b`
- `RPCRT4!RpcStringBindingComposeW` at `0x18007432b`

## pseudocode

```c
__int64 __fastcall LaunchFveEnableRpcBind(void **a1)
{
  int started; // ebx
  RPC_STATUS v2; // eax
  bool v3; // cc
  RPC_BINDING_HANDLE Binding; // [rsp+40h] [rbp+10h] BYREF
  RPC_WSTR String; // [rsp+48h] [rbp+18h] BYREF

  Binding = 0;
  String = 0;
  started = StartFveEnableService();
  if ( started >= 0 )
  {
    v2 = RpcStringBindingComposeW(
           (RPC_WSTR)L"ab261152-3897-4190-b4ac-64d0f864f3b4",
           (RPC_WSTR)L"ncalrpc",
           0,
           0,
           0,
           &String);
    started = v2;
    v3 = v2 <= 0;
    if ( v2 || (v2 = RpcBindingFromStringBindingW(String, &Binding), started = v2, v3 = v2 <= 0, v2) )
    {
      if ( !v3 )
        started = (unsigned __int16)v2 | 0x80070000;
    }
    else
    {
      if ( _InterlockedExchange64((volatile __int64 *)&g_handle, (__int64)Binding) )
        RpcBindingFree(&Binding);
      Binding = 0;
      started = 0;
    }
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( String )
    RpcStringFreeW(&String);
  return (unsigned int)started;
}

```

## disassembly

```asm
0x1800742d4  mov     [rsp-8+arg_10], rbx
0x1800742d9  mov     [rsp-8+Binding], rcx
0x1800742de  push    rbp
0x1800742df  mov     rbp, rsp
0x1800742e2  sub     rsp, 30h
0x1800742e6  mov     [rbp+Binding], 0
0x1800742ee  mov     [rbp+String], 0
0x1800742f6  call    StartFveEnableService
0x1800742fb  mov     ebx, eax
0x1800742fd  test    eax, eax
0x1800742ff  js      loc_18007438E
0x180074305  lea     rax, [rbp+String]
0x180074309  xor     r9d, r9d; Endpoint
0x18007430c  mov     [rsp+30h+StringBinding], rax; StringBinding
0x180074311  lea     rdx, ProtSeq; "ncalrpc"
0x180074318  xor     r8d, r8d; NetworkAddr
0x18007431b  mov     [rsp+30h+Options], 0; Options
0x180074324  lea     rcx, ObjUuid; "ab261152-3897-4190-b4ac-64d0f864f3b4"
0x18007432b  call    cs:__imp_RpcStringBindingComposeW
0x180074332  nop     dword ptr [rax+rax+00h]
0x180074337  mov     ebx, eax
0x180074339  test    eax, eax
0x18007433b  jz      short loc_18007434A
0x18007433d  jle     short loc_18007438E
0x18007433f  movzx   ebx, ax
0x180074342  or      ebx, 80070000h
0x180074348  jmp     short loc_18007438E
0x18007434a  mov     rcx, [rbp+String]; StringBinding
0x18007434e  lea     rdx, [rbp+Binding]; Binding
0x180074352  call    cs:__imp_RpcBindingFromStringBindingW
0x180074359  nop     dword ptr [rax+rax+00h]
0x18007435e  mov     ebx, eax
0x180074360  test    eax, eax
0x180074362  jnz     short loc_18007433D
0x180074364  mov     rax, [rbp+Binding]
0x180074368  xchg    rax, cs:?g_handle@@3PEAXEA; void * g_handle
0x18007436f  test    rax, rax
0x180074372  jz      short loc_180074384
0x180074374  lea     rcx, [rbp+Binding]; Binding
0x180074378  call    cs:__imp_RpcBindingFree
0x18007437f  nop     dword ptr [rax+rax+00h]
0x180074384  mov     [rbp+Binding], 0
0x18007438c  xor     ebx, ebx
0x18007438e  cmp     [rbp+Binding], 0
0x180074393  jz      short loc_1800743A5
0x180074395  lea     rcx, [rbp+Binding]; Binding
0x180074399  call    cs:__imp_RpcBindingFree
0x1800743a0  nop     dword ptr [rax+rax+00h]
0x1800743a5  cmp     [rbp+String], 0
0x1800743aa  jz      short loc_1800743BC
0x1800743ac  lea     rcx, [rbp+String]; String
0x1800743b0  call    cs:__imp_RpcStringFreeW
0x1800743b7  nop     dword ptr [rax+rax+00h]
0x1800743bc  mov     eax, ebx
0x1800743be  mov     rbx, [rsp+30h+arg_10]
0x1800743c3  add     rsp, 30h
0x1800743c7  pop     rbp
0x1800743c8  retn
```
