# BiCancelWorkItem

- ea: `0x180001f10`
- end: `0x180001f99`
- name: `BiCancelWorkItem`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f10`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180001f5f`
- `RPCRT4!NdrClientCall3` at `0x180001f5f`
- `RPCRT4!RpcBindingFree` at `0x180001f86`
- `RPCRT4!RpcBindingFree` at `0x180001f86`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001f75`
- `RPCRT4!I_RpcMapWin32Status` at `0x180001f75`

## pseudocode

```c
__int64 __fastcall BiCancelWorkItem(__int64 a1)
{
  int Pointer; // ebx
  CLIENT_CALL_RETURN v3; // rax
  int v5; // [rsp+28h] [rbp-20h]
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp+10h] BYREF
  CLIENT_CALL_RETURN v7; // [rsp+60h] [rbp+18h]

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v7.Simple = 0;
    v5 = 0;
    v3.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 5u, 0, Binding, a1, v5).Pointer;
    Pointer = (int)v3.Pointer;
    v7.Pointer = v3.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180001f10  mov     [rsp+arg_0], rbx
0x180001f15  push    rdi
0x180001f16  sub     rsp, 40h
0x180001f1a  mov     rdi, rcx
0x180001f1d  mov     [rsp+48h+Binding], 0
0x180001f26  lea     rcx, [rsp+48h+Binding]
0x180001f2b  call    BipCreateRpcBinding
0x180001f30  mov     ebx, eax
0x180001f32  test    eax, eax
0x180001f34  js      short loc_180001F8C
0x180001f36  mov     [rsp+48h+arg_10], 0
0x180001f3f  mov     [rsp+48h+var_20], 0
0x180001f47  mov     [rsp+48h+var_28], rdi
0x180001f4c  mov     r9, [rsp+48h+Binding]
0x180001f51  xor     r8d, r8d; pReturnValue
0x180001f54  lea     edx, [r8+5]; nProcNum
0x180001f58  lea     rcx, pProxyInfo; pProxyInfo
0x180001f5f  call    cs:__imp_NdrClientCall3
0x180001f65  mov     rbx, rax
0x180001f68  mov     [rsp+48h+arg_10], rax
0x180001f6d  mov     [rsp+48h+var_18], eax
0x180001f71  jmp     short loc_180001F81
0x180001f73  mov     ecx, eax; Status
0x180001f75  call    cs:__imp_I_RpcMapWin32Status
0x180001f7b  mov     ebx, eax
0x180001f7d  mov     [rsp+48h+var_18], eax
0x180001f81  lea     rcx, [rsp+48h+Binding]; Binding
0x180001f86  call    cs:__imp_RpcBindingFree
0x180001f8c  mov     eax, ebx
0x180001f8e  mov     rbx, [rsp+48h+arg_0]
0x180001f93  add     rsp, 40h
0x180001f97  pop     rdi
0x180001f98  retn
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
