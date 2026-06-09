# BiDiscardPendingActivations

- ea: `0x1800023c0`
- end: `0x180002441`
- name: `BiDiscardPendingActivations`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800023c0`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002407`
- `RPCRT4!NdrClientCall3` at `0x180002407`
- `RPCRT4!RpcBindingFree` at `0x18000242e`
- `RPCRT4!RpcBindingFree` at `0x18000242e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000241d`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000241d`

## pseudocode

```c
__int64 __fastcall BiDiscardPendingActivations(__int64 a1)
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
    v3.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xAu, 0, Binding, a1).Pointer;
    Pointer = (int)v3.Pointer;
    v6.Pointer = v3.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800023c0  mov     [rsp+arg_0], rbx
0x1800023c5  push    rdi
0x1800023c6  sub     rsp, 40h
0x1800023ca  mov     rdi, rcx
0x1800023cd  mov     [rsp+48h+Binding], 0
0x1800023d6  lea     rcx, [rsp+48h+Binding]
0x1800023db  call    BipCreateRpcBinding
0x1800023e0  mov     ebx, eax
0x1800023e2  test    eax, eax
0x1800023e4  js      short loc_180002434
0x1800023e6  mov     [rsp+48h+arg_10], 0
0x1800023ef  mov     [rsp+48h+var_28], rdi
0x1800023f4  mov     r9, [rsp+48h+Binding]
0x1800023f9  xor     r8d, r8d; pReturnValue
0x1800023fc  lea     edx, [r8+0Ah]; nProcNum
0x180002400  lea     rcx, pProxyInfo; pProxyInfo
0x180002407  call    cs:__imp_NdrClientCall3
0x18000240d  mov     rbx, rax
0x180002410  mov     [rsp+48h+arg_10], rax
0x180002415  mov     [rsp+48h+var_18], eax
0x180002419  jmp     short loc_180002429
0x18000241b  mov     ecx, eax; Status
0x18000241d  call    cs:__imp_I_RpcMapWin32Status
0x180002423  mov     ebx, eax
0x180002425  mov     [rsp+48h+var_18], eax
0x180002429  lea     rcx, [rsp+48h+Binding]; Binding
0x18000242e  call    cs:__imp_RpcBindingFree
0x180002434  mov     eax, ebx
0x180002436  mov     rbx, [rsp+48h+arg_0]
0x18000243b  add     rsp, 40h
0x18000243f  pop     rdi
0x180002440  retn
```
