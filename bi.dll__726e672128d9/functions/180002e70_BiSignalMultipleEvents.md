# BiSignalMultipleEvents

- ea: `0x180002e70`
- end: `0x180002f24`
- name: `BiSignalMultipleEvents`
- size: `180`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002e70`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002ee9`
- `RPCRT4!NdrClientCall3` at `0x180002ee9`
- `RPCRT4!RpcBindingFree` at `0x180002f10`
- `RPCRT4!RpcBindingFree` at `0x180002f10`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002eff`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002eff`

## pseudocode

```c
__int64 __fastcall BiSignalMultipleEvents(__int64 a1, int a2, __int64 a3, __int64 a4, __int64 a5, int a6)
{
  int Pointer; // ebx
  CLIENT_CALL_RETURN v11; // rax
  int v13; // [rsp+28h] [rbp-70h]
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v16; // [rsp+60h] [rbp-38h]

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v16.Simple = 0;
    v13 = a2;
    v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x18u, 0, Binding, a1, v13, a3, a4, a5, a6).Pointer;
    Pointer = (int)v11.Pointer;
    v16.Pointer = v11.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002e70  push    rbx
0x180002e72  push    rsi
0x180002e73  push    rdi
0x180002e74  push    r14
0x180002e76  push    r15
0x180002e78  sub     rsp, 70h
0x180002e7c  mov     rdi, r9
0x180002e7f  mov     rsi, r8
0x180002e82  mov     r14d, edx
0x180002e85  mov     r15, rcx
0x180002e88  mov     [rsp+98h+Binding], 0
0x180002e91  lea     rcx, [rsp+98h+Binding]
0x180002e96  call    BipCreateRpcBinding
0x180002e9b  mov     ebx, eax
0x180002e9d  test    eax, eax
0x180002e9f  js      short loc_180002F16
0x180002ea1  mov     [rsp+98h+var_38], 0
0x180002eaa  mov     eax, [rsp+98h+arg_28]
0x180002eb1  mov     [rsp+98h+var_50], eax
0x180002eb5  mov     rax, [rsp+98h+arg_20]
0x180002ebd  mov     [rsp+98h+var_58], rax
0x180002ec2  mov     [rsp+98h+var_60], rdi
0x180002ec7  mov     [rsp+98h+var_68], rsi
0x180002ecc  mov     [rsp+98h+var_70], r14d
0x180002ed1  mov     [rsp+98h+var_78], r15
0x180002ed6  mov     r9, [rsp+98h+Binding]
0x180002edb  xor     r8d, r8d; pReturnValue
0x180002ede  lea     edx, [r8+18h]; nProcNum
0x180002ee2  lea     rcx, pProxyInfo; pProxyInfo
0x180002ee9  call    cs:__imp_NdrClientCall3
0x180002eef  mov     rbx, rax
0x180002ef2  mov     [rsp+98h+var_38], rax
0x180002ef7  mov     [rsp+98h+var_48], eax
0x180002efb  jmp     short loc_180002F0B
0x180002efd  mov     ecx, eax; Status
0x180002eff  call    cs:__imp_I_RpcMapWin32Status
0x180002f05  mov     ebx, eax
0x180002f07  mov     [rsp+98h+var_48], eax
0x180002f0b  lea     rcx, [rsp+98h+Binding]; Binding
0x180002f10  call    cs:__imp_RpcBindingFree
0x180002f16  mov     eax, ebx
0x180002f18  add     rsp, 70h
0x180002f1c  pop     r15
0x180002f1e  pop     r14
0x180002f20  pop     rdi
0x180002f21  pop     rsi
0x180002f22  pop     rbx
0x180002f23  retn
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
