# BiUpdateEventInformation

- ea: `0x1800030c0`
- end: `0x180003155`
- name: `BiUpdateEventInformation`
- size: `149`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `installer_update`

## callees

- `0x1800030c0`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180003119`
- `RPCRT4!NdrClientCall3` at `0x180003119`
- `RPCRT4!RpcBindingFree` at `0x180003143`
- `RPCRT4!RpcBindingFree` at `0x180003143`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000312f`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000312f`

## pseudocode

```c
__int64 __fastcall BiUpdateEventInformation(__int64 a1, __int64 a2, int a3)
{
  int Pointer; // ebx
  int v8; // [rsp+30h] [rbp-48h]
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp+20h] BYREF

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v8 = a3;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x1Cu, 0, Binding, a1, a2, v8).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800030c0  mov     rax, rsp
0x1800030c3  push    rbx
0x1800030c4  push    rsi
0x1800030c5  push    rdi
0x1800030c6  push    r14
0x1800030c8  sub     rsp, 58h
0x1800030cc  mov     edi, r8d
0x1800030cf  mov     rsi, rdx
0x1800030d2  mov     r14, rcx
0x1800030d5  mov     qword ptr [rax+20h], 0
0x1800030dd  lea     rcx, [rax+20h]
0x1800030e1  call    BipCreateRpcBinding
0x1800030e6  mov     ebx, eax
0x1800030e8  test    eax, eax
0x1800030ea  js      short loc_180003149
0x1800030ec  mov     [rsp+78h+var_30], 0
0x1800030f5  mov     [rsp+78h+var_48], edi
0x1800030f9  mov     [rsp+78h+var_50], rsi
0x1800030fe  mov     [rsp+78h+var_58], r14
0x180003103  mov     r9, [rsp+78h+Binding]
0x18000310b  xor     r8d, r8d; pReturnValue
0x18000310e  lea     edx, [r8+1Ch]; nProcNum
0x180003112  lea     rcx, pProxyInfo; pProxyInfo
0x180003119  call    cs:__imp_NdrClientCall3
0x18000311f  mov     rbx, rax
0x180003122  mov     [rsp+78h+var_30], rax
0x180003127  mov     [rsp+78h+var_38], eax
0x18000312b  jmp     short loc_18000313B
0x18000312d  mov     ecx, eax; Status
0x18000312f  call    cs:__imp_I_RpcMapWin32Status
0x180003135  mov     ebx, eax
0x180003137  mov     [rsp+78h+var_38], eax
0x18000313b  lea     rcx, [rsp+78h+Binding]; Binding
0x180003143  call    cs:__imp_RpcBindingFree
0x180003149  mov     eax, ebx
0x18000314b  add     rsp, 58h
0x18000314f  pop     r14
0x180003151  pop     rdi
0x180003152  pop     rsi
0x180003153  pop     rbx
0x180003154  retn
```
