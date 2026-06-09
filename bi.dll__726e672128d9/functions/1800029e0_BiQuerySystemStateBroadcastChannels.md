# BiQuerySystemStateBroadcastChannels

- ea: `0x1800029e0`
- end: `0x180002a61`
- name: `BiQuerySystemStateBroadcastChannels`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800029e0`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002a27`
- `RPCRT4!NdrClientCall3` at `0x180002a27`
- `RPCRT4!RpcBindingFree` at `0x180002a4e`
- `RPCRT4!RpcBindingFree` at `0x180002a4e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002a3d`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002a3d`

## pseudocode

```c
__int64 __fastcall BiQuerySystemStateBroadcastChannels(__int64 a1)
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
    v3.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x12u, 0, Binding, a1).Pointer;
    Pointer = (int)v3.Pointer;
    v6.Pointer = v3.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800029e0  mov     [rsp+arg_0], rbx
0x1800029e5  push    rdi
0x1800029e6  sub     rsp, 40h
0x1800029ea  mov     rdi, rcx
0x1800029ed  mov     [rsp+48h+Binding], 0
0x1800029f6  lea     rcx, [rsp+48h+Binding]
0x1800029fb  call    BipCreateRpcBinding
0x180002a00  mov     ebx, eax
0x180002a02  test    eax, eax
0x180002a04  js      short loc_180002A54
0x180002a06  mov     [rsp+48h+arg_10], 0
0x180002a0f  mov     [rsp+48h+var_28], rdi
0x180002a14  mov     r9, [rsp+48h+Binding]
0x180002a19  xor     r8d, r8d; pReturnValue
0x180002a1c  lea     edx, [r8+12h]; nProcNum
0x180002a20  lea     rcx, pProxyInfo; pProxyInfo
0x180002a27  call    cs:__imp_NdrClientCall3
0x180002a2d  mov     rbx, rax
0x180002a30  mov     [rsp+48h+arg_10], rax
0x180002a35  mov     [rsp+48h+var_18], eax
0x180002a39  jmp     short loc_180002A49
0x180002a3b  mov     ecx, eax; Status
0x180002a3d  call    cs:__imp_I_RpcMapWin32Status
0x180002a43  mov     ebx, eax
0x180002a45  mov     [rsp+48h+var_18], eax
0x180002a49  lea     rcx, [rsp+48h+Binding]; Binding
0x180002a4e  call    cs:__imp_RpcBindingFree
0x180002a54  mov     eax, ebx
0x180002a56  mov     rbx, [rsp+48h+arg_0]
0x180002a5b  add     rsp, 40h
0x180002a5f  pop     rdi
0x180002a60  retn
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
