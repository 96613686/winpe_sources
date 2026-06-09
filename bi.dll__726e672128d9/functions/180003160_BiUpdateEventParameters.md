# BiUpdateEventParameters

- ea: `0x180003160`
- end: `0x1800031f2`
- name: `BiUpdateEventParameters`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x180003160`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800031b3`
- `RPCRT4!NdrClientCall3` at `0x1800031b3`
- `RPCRT4!RpcBindingFree` at `0x1800031da`
- `RPCRT4!RpcBindingFree` at `0x1800031da`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800031c9`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800031c9`

## pseudocode

```c
__int64 __fastcall BiUpdateEventParameters(__int64 a1, __int64 a2)
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
    v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Au, 0, Binding, a1, a2).Pointer;
    Pointer = (int)v5.Pointer;
    v8.Pointer = v5.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180003160  mov     rax, rsp
0x180003163  mov     [rax+8], rbx
0x180003167  mov     [rax+10h], rsi
0x18000316b  push    rdi
0x18000316c  sub     rsp, 40h
0x180003170  mov     rdi, rdx
0x180003173  mov     rsi, rcx
0x180003176  mov     qword ptr [rax+18h], 0
0x18000317e  lea     rcx, [rax+18h]
0x180003182  call    BipCreateRpcBinding
0x180003187  mov     ebx, eax
0x180003189  test    eax, eax
0x18000318b  js      short loc_1800031E0
0x18000318d  mov     [rsp+48h+arg_18], 0
0x180003196  mov     [rsp+48h+var_20], rdi
0x18000319b  mov     [rsp+48h+var_28], rsi
0x1800031a0  mov     r9, [rsp+48h+Binding]
0x1800031a5  xor     r8d, r8d; pReturnValue
0x1800031a8  lea     edx, [r8+1Ah]; nProcNum
0x1800031ac  lea     rcx, pProxyInfo; pProxyInfo
0x1800031b3  call    cs:__imp_NdrClientCall3
0x1800031b9  mov     rbx, rax
0x1800031bc  mov     [rsp+48h+arg_18], rax
0x1800031c1  mov     [rsp+48h+var_18], eax
0x1800031c5  jmp     short loc_1800031D5
0x1800031c7  mov     ecx, eax; Status
0x1800031c9  call    cs:__imp_I_RpcMapWin32Status
0x1800031cf  mov     ebx, eax
0x1800031d1  mov     [rsp+48h+var_18], eax
0x1800031d5  lea     rcx, [rsp+48h+Binding]; Binding
0x1800031da  call    cs:__imp_RpcBindingFree
0x1800031e0  mov     eax, ebx
0x1800031e2  mov     rbx, [rsp+48h+arg_0]
0x1800031e7  mov     rsi, [rsp+48h+arg_8]
0x1800031ec  add     rsp, 40h
0x1800031f0  pop     rdi
0x1800031f1  retn
```
