# BiCancelWorkItemEx

- ea: `0x180001fa0`
- end: `0x180002030`
- name: `BiCancelWorkItemEx`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001fa0`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180001ff1`
- `RPCRT4!NdrClientCall3` at `0x180001ff1`
- `RPCRT4!RpcBindingFree` at `0x180002018`
- `RPCRT4!RpcBindingFree` at `0x180002018`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002007`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002007`

## pseudocode

```c
__int64 __fastcall BiCancelWorkItemEx(__int64 a1, int a2)
{
  int Pointer; // ebx
  CLIENT_CALL_RETURN v5; // rax
  int v7; // [rsp+28h] [rbp-20h]
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v9; // [rsp+68h] [rbp+20h]

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v9.Simple = 0;
    v7 = a2;
    v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 5u, 0, Binding, a1, v7).Pointer;
    Pointer = (int)v5.Pointer;
    v9.Pointer = v5.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180001fa0  mov     rax, rsp
0x180001fa3  mov     [rax+8], rbx
0x180001fa7  mov     [rax+10h], rsi
0x180001fab  push    rdi
0x180001fac  sub     rsp, 40h
0x180001fb0  mov     edi, edx
0x180001fb2  mov     rsi, rcx
0x180001fb5  mov     qword ptr [rax+18h], 0
0x180001fbd  lea     rcx, [rax+18h]
0x180001fc1  call    BipCreateRpcBinding
0x180001fc6  mov     ebx, eax
0x180001fc8  test    eax, eax
0x180001fca  js      short loc_18000201E
0x180001fcc  mov     [rsp+48h+arg_18], 0
0x180001fd5  mov     [rsp+48h+var_20], edi
0x180001fd9  mov     [rsp+48h+var_28], rsi
0x180001fde  mov     r9, [rsp+48h+Binding]
0x180001fe3  xor     r8d, r8d; pReturnValue
0x180001fe6  lea     edx, [r8+5]; nProcNum
0x180001fea  lea     rcx, pProxyInfo; pProxyInfo
0x180001ff1  call    cs:__imp_NdrClientCall3
0x180001ff7  mov     rbx, rax
0x180001ffa  mov     [rsp+48h+arg_18], rax
0x180001fff  mov     [rsp+48h+var_18], eax
0x180002003  jmp     short loc_180002013
0x180002005  mov     ecx, eax; Status
0x180002007  call    cs:__imp_I_RpcMapWin32Status
0x18000200d  mov     ebx, eax
0x18000200f  mov     [rsp+48h+var_18], eax
0x180002013  lea     rcx, [rsp+48h+Binding]; Binding
0x180002018  call    cs:__imp_RpcBindingFree
0x18000201e  mov     eax, ebx
0x180002020  mov     rbx, [rsp+48h+arg_0]
0x180002025  mov     rsi, [rsp+48h+arg_8]
0x18000202a  add     rsp, 40h
0x18000202e  pop     rdi
0x18000202f  retn
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
