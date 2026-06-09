# BiDisassociateWorkItem

- ea: `0x180002320`
- end: `0x1800023b1`
- name: `BiDisassociateWorkItem`
- size: `145`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002320`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002372`
- `RPCRT4!NdrClientCall3` at `0x180002372`
- `RPCRT4!RpcBindingFree` at `0x180002399`
- `RPCRT4!RpcBindingFree` at `0x180002399`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002388`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002388`

## pseudocode

```c
__int64 __fastcall BiDisassociateWorkItem(__int64 a1, unsigned __int8 a2)
{
  int v2; // edi
  int Pointer; // ebx
  CLIENT_CALL_RETURN v5; // rax
  int v7; // [rsp+28h] [rbp-20h]
  RPC_BINDING_HANDLE Binding; // [rsp+60h] [rbp+18h] BYREF
  CLIENT_CALL_RETURN v9; // [rsp+68h] [rbp+20h]

  v2 = a2;
  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v9.Simple = 0;
    v7 = v2;
    v5.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 9u, 0, Binding, a1, v7).Pointer;
    Pointer = (int)v5.Pointer;
    v9.Pointer = v5.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002320  mov     rax, rsp
0x180002323  mov     [rax+8], rbx
0x180002327  mov     [rax+10h], rsi
0x18000232b  push    rdi
0x18000232c  sub     rsp, 40h
0x180002330  movzx   edi, dl
0x180002333  mov     rsi, rcx
0x180002336  mov     qword ptr [rax+18h], 0
0x18000233e  lea     rcx, [rax+18h]
0x180002342  call    BipCreateRpcBinding
0x180002347  mov     ebx, eax
0x180002349  test    eax, eax
0x18000234b  js      short loc_18000239F
0x18000234d  mov     [rsp+48h+arg_18], 0
0x180002356  mov     [rsp+48h+var_20], edi
0x18000235a  mov     [rsp+48h+var_28], rsi
0x18000235f  mov     r9, [rsp+48h+Binding]
0x180002364  xor     r8d, r8d; pReturnValue
0x180002367  lea     edx, [r8+9]; nProcNum
0x18000236b  lea     rcx, pProxyInfo; pProxyInfo
0x180002372  call    cs:__imp_NdrClientCall3
0x180002378  mov     rbx, rax
0x18000237b  mov     [rsp+48h+arg_18], rax
0x180002380  mov     [rsp+48h+var_18], eax
0x180002384  jmp     short loc_180002394
0x180002386  mov     ecx, eax; Status
0x180002388  call    cs:__imp_I_RpcMapWin32Status
0x18000238e  mov     ebx, eax
0x180002390  mov     [rsp+48h+var_18], eax
0x180002394  lea     rcx, [rsp+48h+Binding]; Binding
0x180002399  call    cs:__imp_RpcBindingFree
0x18000239f  mov     eax, ebx
0x1800023a1  mov     rbx, [rsp+48h+arg_0]
0x1800023a6  mov     rsi, [rsp+48h+arg_8]
0x1800023ab  add     rsp, 40h
0x1800023af  pop     rdi
0x1800023b0  retn
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
