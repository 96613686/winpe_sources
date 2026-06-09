# BiEnumerateUserSessions

- ea: `0x180002590`
- end: `0x180002622`
- name: `BiEnumerateUserSessions`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002590`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800025e3`
- `RPCRT4!NdrClientCall3` at `0x1800025e3`
- `RPCRT4!RpcBindingFree` at `0x18000260a`
- `RPCRT4!RpcBindingFree` at `0x18000260a`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800025f9`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800025f9`

## pseudocode

```c
__int64 __fastcall BiEnumerateUserSessions(__int64 a1, __int64 a2)
{
  int Pointer; // ebx
  CLIENT_CALL_RETURN v5; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v8; // [rsp+68h] [rbp+20h]

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v8.Simple = 0;
    v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xDu, 0, Binding, a1, a2).Pointer;
    Pointer = (int)v5.Pointer;
    v8.Pointer = v5.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002590  mov     rax, rsp
0x180002593  mov     [rax+8], rbx
0x180002597  mov     [rax+10h], rsi
0x18000259b  push    rdi
0x18000259c  sub     rsp, 40h
0x1800025a0  mov     rdi, rdx
0x1800025a3  mov     rsi, rcx
0x1800025a6  mov     qword ptr [rax+18h], 0
0x1800025ae  lea     rcx, [rax+18h]
0x1800025b2  call    BipCreateRpcBinding
0x1800025b7  mov     ebx, eax
0x1800025b9  test    eax, eax
0x1800025bb  js      short loc_180002610
0x1800025bd  mov     [rsp+48h+arg_18], 0
0x1800025c6  mov     [rsp+48h+var_20], rdi
0x1800025cb  mov     [rsp+48h+var_28], rsi
0x1800025d0  mov     r9, [rsp+48h+Binding]
0x1800025d5  xor     r8d, r8d; pReturnValue
0x1800025d8  lea     edx, [r8+0Dh]; nProcNum
0x1800025dc  lea     rcx, pProxyInfo; pProxyInfo
0x1800025e3  call    cs:__imp_NdrClientCall3
0x1800025e9  mov     rbx, rax
0x1800025ec  mov     [rsp+48h+arg_18], rax
0x1800025f1  mov     [rsp+48h+var_18], eax
0x1800025f5  jmp     short loc_180002605
0x1800025f7  mov     ecx, eax; Status
0x1800025f9  call    cs:__imp_I_RpcMapWin32Status
0x1800025ff  mov     ebx, eax
0x180002601  mov     [rsp+48h+var_18], eax
0x180002605  lea     rcx, [rsp+48h+Binding]; Binding
0x18000260a  call    cs:__imp_RpcBindingFree
0x180002610  mov     eax, ebx
0x180002612  mov     rbx, [rsp+48h+arg_0]
0x180002617  mov     rsi, [rsp+48h+arg_8]
0x18000261c  add     rsp, 40h
0x180002620  pop     rdi
0x180002621  retn
0x180003816  push    rbp
0x180003818  sub     rsp, 30h
0x18000381c  mov     rbp, rdx
0x18000381f  mov     rcx, [rcx]
0x180003822  mov     ecx, [rcx]; ExceptionCode
0x180003824  call    cs:__imp_RpcExceptionFilter
0x18000382a  nop
0x18000382b  add     rsp, 30h
0x18000382f  pop     rbp
0x180003830  retn
```
