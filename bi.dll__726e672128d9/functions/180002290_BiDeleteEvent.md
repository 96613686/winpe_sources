# BiDeleteEvent

- ea: `0x180002290`
- end: `0x180002311`
- name: `BiDeleteEvent`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002290`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800022d7`
- `RPCRT4!NdrClientCall3` at `0x1800022d7`
- `RPCRT4!RpcBindingFree` at `0x1800022fe`
- `RPCRT4!RpcBindingFree` at `0x1800022fe`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800022ed`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800022ed`

## pseudocode

```c
__int64 __fastcall BiDeleteEvent(__int64 a1)
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
    v3.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 8u, 0, Binding, a1).Pointer;
    Pointer = (int)v3.Pointer;
    v6.Pointer = v3.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002290  mov     [rsp+arg_0], rbx
0x180002295  push    rdi
0x180002296  sub     rsp, 40h
0x18000229a  mov     rdi, rcx
0x18000229d  mov     [rsp+48h+Binding], 0
0x1800022a6  lea     rcx, [rsp+48h+Binding]
0x1800022ab  call    BipCreateRpcBinding
0x1800022b0  mov     ebx, eax
0x1800022b2  test    eax, eax
0x1800022b4  js      short loc_180002304
0x1800022b6  mov     [rsp+48h+arg_10], 0
0x1800022bf  mov     [rsp+48h+var_28], rdi
0x1800022c4  mov     r9, [rsp+48h+Binding]
0x1800022c9  xor     r8d, r8d; pReturnValue
0x1800022cc  lea     edx, [r8+8]; nProcNum
0x1800022d0  lea     rcx, pProxyInfo; pProxyInfo
0x1800022d7  call    cs:__imp_NdrClientCall3
0x1800022dd  mov     rbx, rax
0x1800022e0  mov     [rsp+48h+arg_10], rax
0x1800022e5  mov     [rsp+48h+var_18], eax
0x1800022e9  jmp     short loc_1800022F9
0x1800022eb  mov     ecx, eax; Status
0x1800022ed  call    cs:__imp_I_RpcMapWin32Status
0x1800022f3  mov     ebx, eax
0x1800022f5  mov     [rsp+48h+var_18], eax
0x1800022f9  lea     rcx, [rsp+48h+Binding]; Binding
0x1800022fe  call    cs:__imp_RpcBindingFree
0x180002304  mov     eax, ebx
0x180002306  mov     rbx, [rsp+48h+arg_0]
0x18000230b  add     rsp, 40h
0x18000230f  pop     rdi
0x180002310  retn
```
