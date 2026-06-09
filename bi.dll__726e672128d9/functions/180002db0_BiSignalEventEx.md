# BiSignalEventEx

- ea: `0x180002db0`
- end: `0x180002e64`
- name: `BiSignalEventEx`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180003200`

## callees

- `0x180002db0`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002e29`
- `RPCRT4!NdrClientCall3` at `0x180002e29`
- `RPCRT4!RpcBindingFree` at `0x180002e50`
- `RPCRT4!RpcBindingFree` at `0x180002e50`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002e3f`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002e3f`

## pseudocode

```c
__int64 __fastcall BiSignalEventEx(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
{
  int Pointer; // ebx
  CLIENT_CALL_RETURN v11; // rax
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v15; // [rsp+60h] [rbp-38h]

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v15.Simple = 0;
    v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x17u, 0, Binding, a1, a2, a3, a4, a5, a6).Pointer;
    Pointer = (int)v11.Pointer;
    v15.Pointer = v11.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002db0  push    rbx
0x180002db2  push    rsi
0x180002db3  push    rdi
0x180002db4  push    r14
0x180002db6  push    r15
0x180002db8  sub     rsp, 70h
0x180002dbc  mov     rdi, r9
0x180002dbf  mov     rsi, r8
0x180002dc2  mov     r14, rdx
0x180002dc5  mov     r15, rcx
0x180002dc8  mov     [rsp+98h+Binding], 0
0x180002dd1  lea     rcx, [rsp+98h+Binding]
0x180002dd6  call    BipCreateRpcBinding
0x180002ddb  mov     ebx, eax
0x180002ddd  test    eax, eax
0x180002ddf  js      short loc_180002E56
0x180002de1  mov     [rsp+98h+var_38], 0
0x180002dea  mov     rax, [rsp+98h+arg_28]
0x180002df2  mov     [rsp+98h+var_50], rax
0x180002df7  mov     eax, [rsp+98h+arg_20]
0x180002dfe  mov     [rsp+98h+var_58], eax
0x180002e02  mov     [rsp+98h+var_60], rdi
0x180002e07  mov     [rsp+98h+var_68], rsi
0x180002e0c  mov     [rsp+98h+var_70], r14
0x180002e11  mov     [rsp+98h+var_78], r15
0x180002e16  mov     r9, [rsp+98h+Binding]
0x180002e1b  xor     r8d, r8d; pReturnValue
0x180002e1e  lea     edx, [r8+17h]; nProcNum
0x180002e22  lea     rcx, pProxyInfo; pProxyInfo
0x180002e29  call    cs:__imp_NdrClientCall3
0x180002e2f  mov     rbx, rax
0x180002e32  mov     [rsp+98h+var_38], rax
0x180002e37  mov     [rsp+98h+var_48], eax
0x180002e3b  jmp     short loc_180002E4B
0x180002e3d  mov     ecx, eax; Status
0x180002e3f  call    cs:__imp_I_RpcMapWin32Status
0x180002e45  mov     ebx, eax
0x180002e47  mov     [rsp+98h+var_48], eax
0x180002e4b  lea     rcx, [rsp+98h+Binding]; Binding
0x180002e50  call    cs:__imp_RpcBindingFree
0x180002e56  mov     eax, ebx
0x180002e58  add     rsp, 70h
0x180002e5c  pop     r15
0x180002e5e  pop     r14
0x180002e60  pop     rdi
0x180002e61  pop     rsi
0x180002e62  pop     rbx
0x180002e63  retn
0x1800038c6  push    rbp
0x1800038c8  sub     rsp, 50h
0x1800038cc  mov     rbp, rdx
0x1800038cf  mov     rcx, [rcx]
0x1800038d2  mov     ecx, [rcx]; ExceptionCode
0x1800038d4  call    cs:__imp_RpcExceptionFilter
0x1800038da  nop
0x1800038db  add     rsp, 50h
0x1800038df  pop     rbp
0x1800038e0  retn
```
