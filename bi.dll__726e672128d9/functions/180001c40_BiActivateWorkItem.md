# BiActivateWorkItem

- ea: `0x180001c40`
- end: `0x180001cc1`
- name: `BiActivateWorkItem`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001c40`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180001c87`
- `RPCRT4!NdrClientCall3` at `0x180001c87`
- `RPCRT4!RpcBindingFree` at `0x180001cae`
- `RPCRT4!RpcBindingFree` at `0x180001cae`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001c9d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001c9d`

## pseudocode

```c
__int64 __fastcall BiActivateWorkItem(__int64 a1)
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
    v3.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 2u, 0, Binding, a1).Pointer;
    Pointer = (int)v3.Pointer;
    v6.Pointer = v3.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180001c40  mov     [rsp+arg_0], rbx
0x180001c45  push    rdi
0x180001c46  sub     rsp, 40h
0x180001c4a  mov     rdi, rcx
0x180001c4d  mov     [rsp+48h+Binding], 0
0x180001c56  lea     rcx, [rsp+48h+Binding]
0x180001c5b  call    BipCreateRpcBinding
0x180001c60  mov     ebx, eax
0x180001c62  test    eax, eax
0x180001c64  js      short loc_180001CB4
0x180001c66  mov     [rsp+48h+arg_10], 0
0x180001c6f  mov     [rsp+48h+var_28], rdi
0x180001c74  mov     r9, [rsp+48h+Binding]
0x180001c79  xor     r8d, r8d; pReturnValue
0x180001c7c  lea     edx, [r8+2]; nProcNum
0x180001c80  lea     rcx, pProxyInfo; pProxyInfo
0x180001c87  call    cs:__imp_NdrClientCall3
0x180001c8d  mov     rbx, rax
0x180001c90  mov     [rsp+48h+arg_10], rax
0x180001c95  mov     [rsp+48h+var_18], eax
0x180001c99  jmp     short loc_180001CA9
0x180001c9b  mov     ecx, eax; Status
0x180001c9d  call    cs:__imp_I_RpcMapWin32Status
0x180001ca3  mov     ebx, eax
0x180001ca5  mov     [rsp+48h+var_18], eax
0x180001ca9  lea     rcx, [rsp+48h+Binding]; Binding
0x180001cae  call    cs:__imp_RpcBindingFree
0x180001cb4  mov     eax, ebx
0x180001cb6  mov     rbx, [rsp+48h+arg_0]
0x180001cbb  add     rsp, 40h
0x180001cbf  pop     rdi
0x180001cc0  retn
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
