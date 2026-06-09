# BiEnumerateUserContexts

- ea: `0x1800024f0`
- end: `0x180002582`
- name: `BiEnumerateUserContexts`
- size: `146`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x1800024f0`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002543`
- `RPCRT4!NdrClientCall3` at `0x180002543`
- `RPCRT4!RpcBindingFree` at `0x18000256a`
- `RPCRT4!RpcBindingFree` at `0x18000256a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002559`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002559`

## pseudocode

```c
__int64 __fastcall BiEnumerateUserContexts(__int64 a1, __int64 a2)
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
    v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xCu, 0, Binding, a1, a2).Pointer;
    Pointer = (int)v5.Pointer;
    v8.Pointer = v5.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x1800024f0  mov     rax, rsp
0x1800024f3  mov     [rax+8], rbx
0x1800024f7  mov     [rax+10h], rsi
0x1800024fb  push    rdi
0x1800024fc  sub     rsp, 40h
0x180002500  mov     rdi, rdx
0x180002503  mov     rsi, rcx
0x180002506  mov     qword ptr [rax+18h], 0
0x18000250e  lea     rcx, [rax+18h]
0x180002512  call    BipCreateRpcBinding
0x180002517  mov     ebx, eax
0x180002519  test    eax, eax
0x18000251b  js      short loc_180002570
0x18000251d  mov     [rsp+48h+arg_18], 0
0x180002526  mov     [rsp+48h+var_20], rdi
0x18000252b  mov     [rsp+48h+var_28], rsi
0x180002530  mov     r9, [rsp+48h+Binding]
0x180002535  xor     r8d, r8d; pReturnValue
0x180002538  lea     edx, [r8+0Ch]; nProcNum
0x18000253c  lea     rcx, pProxyInfo; pProxyInfo
0x180002543  call    cs:__imp_NdrClientCall3
0x180002549  mov     rbx, rax
0x18000254c  mov     [rsp+48h+arg_18], rax
0x180002551  mov     [rsp+48h+var_18], eax
0x180002555  jmp     short loc_180002565
0x180002557  mov     ecx, eax; Status
0x180002559  call    cs:__imp_I_RpcMapWin32Status
0x18000255f  mov     ebx, eax
0x180002561  mov     [rsp+48h+var_18], eax
0x180002565  lea     rcx, [rsp+48h+Binding]; Binding
0x18000256a  call    cs:__imp_RpcBindingFree
0x180002570  mov     eax, ebx
0x180002572  mov     rbx, [rsp+48h+arg_0]
0x180002577  mov     rsi, [rsp+48h+arg_8]
0x18000257c  add     rsp, 40h
0x180002580  pop     rdi
0x180002581  retn
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
