# BiActivateDeferredWorkItem

- ea: `0x1800018e0`
- end: `0x18000195f`
- name: `BiActivateDeferredWorkItem`
- size: `127`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800018e0`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180001925`
- `RPCRT4!NdrClientCall3` at `0x180001925`
- `RPCRT4!RpcBindingFree` at `0x18000194c`
- `RPCRT4!RpcBindingFree` at `0x18000194c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000193b`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000193b`

## pseudocode

```c
__int64 __fastcall BiActivateDeferredWorkItem(__int64 a1)
{
  int Pointer; // ebx
  CLIENT_CALL_RETURN v3; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v6; // [rsp+60h] [rbp+18h]

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v6.Simple = 0;
    v3.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0, 0, Binding, a1).Pointer;
    Pointer = (int)v3.Pointer;
    v6.Pointer = v3.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800018e0  mov     [rsp+arg_0], rbx
0x1800018e5  push    rdi
0x1800018e6  sub     rsp, 40h
0x1800018ea  mov     rdi, rcx
0x1800018ed  mov     [rsp+48h+Binding], 0
0x1800018f6  lea     rcx, [rsp+48h+Binding]
0x1800018fb  call    BipCreateRpcBinding
0x180001900  mov     ebx, eax
0x180001902  test    eax, eax
0x180001904  js      short loc_180001952
0x180001906  mov     [rsp+48h+arg_10], 0
0x18000190f  mov     [rsp+48h+var_28], rdi
0x180001914  mov     r9, [rsp+48h+Binding]
0x180001919  xor     r8d, r8d; pReturnValue
0x18000191c  xor     edx, edx; nProcNum
0x18000191e  lea     rcx, pProxyInfo; pProxyInfo
0x180001925  call    cs:__imp_NdrClientCall3
0x18000192b  mov     rbx, rax
0x18000192e  mov     [rsp+48h+arg_10], rax
0x180001933  mov     [rsp+48h+var_18], eax
0x180001937  jmp     short loc_180001947
0x180001939  mov     ecx, eax; Status
0x18000193b  call    cs:__imp_I_RpcMapWin32Status
0x180001941  mov     ebx, eax
0x180001943  mov     [rsp+48h+var_18], eax
0x180001947  lea     rcx, [rsp+48h+Binding]; Binding
0x18000194c  call    cs:__imp_RpcBindingFree
0x180001952  mov     eax, ebx
0x180001954  mov     rbx, [rsp+48h+arg_0]
0x180001959  add     rsp, 40h
0x18000195d  pop     rdi
0x18000195e  retn
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
