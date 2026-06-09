# BiQueryUserSession

- ea: `0x180002b10`
- end: `0x180002ba0`
- name: `BiQueryUserSession`
- size: `144`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002b10`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002b61`
- `RPCRT4!NdrClientCall3` at `0x180002b61`
- `RPCRT4!RpcBindingFree` at `0x180002b88`
- `RPCRT4!RpcBindingFree` at `0x180002b88`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002b77`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002b77`

## pseudocode

```c
__int64 __fastcall BiQueryUserSession(int a1, __int64 a2)
{
  int Pointer; // ebx
  CLIENT_CALL_RETURN v5; // rax
  int v7; // [rsp+20h] [rbp-28h]
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v9; // [rsp+68h] [rbp+20h]

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v9.Simple = 0;
    v7 = a1;
    v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x14u, 0, Binding, v7, a2).Pointer;
    Pointer = (int)v5.Pointer;
    v9.Pointer = v5.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002b10  mov     rax, rsp
0x180002b13  mov     [rax+8], rbx
0x180002b17  mov     [rax+10h], rsi
0x180002b1b  push    rdi
0x180002b1c  sub     rsp, 40h
0x180002b20  mov     rdi, rdx
0x180002b23  mov     esi, ecx
0x180002b25  mov     qword ptr [rax+18h], 0
0x180002b2d  lea     rcx, [rax+18h]
0x180002b31  call    BipCreateRpcBinding
0x180002b36  mov     ebx, eax
0x180002b38  test    eax, eax
0x180002b3a  js      short loc_180002B8E
0x180002b3c  mov     [rsp+48h+arg_18], 0
0x180002b45  mov     [rsp+48h+var_20], rdi
0x180002b4a  mov     [rsp+48h+var_28], esi
0x180002b4e  mov     r9, [rsp+48h+Binding]
0x180002b53  xor     r8d, r8d; pReturnValue
0x180002b56  lea     edx, [r8+14h]; nProcNum
0x180002b5a  lea     rcx, pProxyInfo; pProxyInfo
0x180002b61  call    cs:__imp_NdrClientCall3
0x180002b67  mov     rbx, rax
0x180002b6a  mov     [rsp+48h+arg_18], rax
0x180002b6f  mov     [rsp+48h+var_18], eax
0x180002b73  jmp     short loc_180002B83
0x180002b75  mov     ecx, eax; Status
0x180002b77  call    cs:__imp_I_RpcMapWin32Status
0x180002b7d  mov     ebx, eax
0x180002b7f  mov     [rsp+48h+var_18], eax
0x180002b83  lea     rcx, [rsp+48h+Binding]; Binding
0x180002b88  call    cs:__imp_RpcBindingFree
0x180002b8e  mov     eax, ebx
0x180002b90  mov     rbx, [rsp+48h+arg_0]
0x180002b95  mov     rsi, [rsp+48h+arg_8]
0x180002b9a  add     rsp, 40h
0x180002b9e  pop     rdi
0x180002b9f  retn
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
