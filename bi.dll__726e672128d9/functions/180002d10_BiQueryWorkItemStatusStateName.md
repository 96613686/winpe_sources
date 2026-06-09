# BiQueryWorkItemStatusStateName

- ea: `0x180002d10`
- end: `0x180002da2`
- name: `BiQueryWorkItemStatusStateName`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002d10`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002d63`
- `RPCRT4!NdrClientCall3` at `0x180002d63`
- `RPCRT4!RpcExceptionFilter` at `0x180003824`
- `RPCRT4!RpcExceptionFilter` at `0x180003824`
- `RPCRT4!RpcBindingFree` at `0x180002d8a`
- `RPCRT4!RpcBindingFree` at `0x180002d8a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002d79`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002d79`

## pseudocode

```c
__int64 __fastcall BiQueryWorkItemStatusStateName(__int64 a1, __int64 a2)
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
    v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x16u, 0, Binding, a1, a2).Pointer;
    Pointer = (int)v5.Pointer;
    v8.Pointer = v5.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002d10  mov     rax, rsp
0x180002d13  mov     [rax+8], rbx
0x180002d17  mov     [rax+10h], rsi
0x180002d1b  push    rdi
0x180002d1c  sub     rsp, 40h
0x180002d20  mov     rdi, rdx
0x180002d23  mov     rsi, rcx
0x180002d26  mov     qword ptr [rax+18h], 0
0x180002d2e  lea     rcx, [rax+18h]
0x180002d32  call    BipCreateRpcBinding
0x180002d37  mov     ebx, eax
0x180002d39  test    eax, eax
0x180002d3b  js      short loc_180002D90
0x180002d3d  mov     [rsp+48h+arg_18], 0
0x180002d46  mov     [rsp+48h+var_20], rdi
0x180002d4b  mov     [rsp+48h+var_28], rsi
0x180002d50  mov     r9, [rsp+48h+Binding]
0x180002d55  xor     r8d, r8d; pReturnValue
0x180002d58  lea     edx, [r8+16h]; nProcNum
0x180002d5c  lea     rcx, pProxyInfo; pProxyInfo
0x180002d63  call    cs:__imp_NdrClientCall3
0x180002d69  mov     rbx, rax
0x180002d6c  mov     [rsp+48h+arg_18], rax
0x180002d71  mov     [rsp+48h+var_18], eax
0x180002d75  jmp     short loc_180002D85
0x180002d77  mov     ecx, eax; Status
0x180002d79  call    cs:__imp_I_RpcMapWin32Status
0x180002d7f  mov     ebx, eax
0x180002d81  mov     [rsp+48h+var_18], eax
0x180002d85  lea     rcx, [rsp+48h+Binding]; Binding
0x180002d8a  call    cs:__imp_RpcBindingFree
0x180002d90  mov     eax, ebx
0x180002d92  mov     rbx, [rsp+48h+arg_0]
0x180002d97  mov     rsi, [rsp+48h+arg_8]
0x180002d9c  add     rsp, 40h
0x180002da0  pop     rdi
0x180002da1  retn
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
