# BiSignalTriggerEventEx

- ea: `0x180002f60`
- end: `0x180003014`
- name: `BiSignalTriggerEventEx`
- size: `180`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180002f30`

## callees

- `0x180002f60`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002fd9`
- `RPCRT4!NdrClientCall3` at `0x180002fd9`
- `RPCRT4!RpcExceptionFilter` at `0x1800038d4`
- `RPCRT4!RpcExceptionFilter` at `0x1800038d4`
- `RPCRT4!RpcBindingFree` at `0x180003000`
- `RPCRT4!RpcBindingFree` at `0x180003000`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002fef`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002fef`

## pseudocode

```c
__int64 __fastcall BiSignalTriggerEventEx(__int64 a1, __int64 a2, __int64 a3, __int64 a4, int a5, __int64 a6)
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
    v11.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x19u, 0, Binding, a1, a2, a3, a4, a5, a6).Pointer;
    Pointer = (int)v11.Pointer;
    v15.Pointer = v11.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002f60  push    rbx
0x180002f62  push    rsi
0x180002f63  push    rdi
0x180002f64  push    r14
0x180002f66  push    r15
0x180002f68  sub     rsp, 70h
0x180002f6c  mov     rdi, r9
0x180002f6f  mov     rsi, r8
0x180002f72  mov     r14, rdx
0x180002f75  mov     r15, rcx
0x180002f78  mov     [rsp+98h+Binding], 0
0x180002f81  lea     rcx, [rsp+98h+Binding]
0x180002f86  call    BipCreateRpcBinding
0x180002f8b  mov     ebx, eax
0x180002f8d  test    eax, eax
0x180002f8f  js      short loc_180003006
0x180002f91  mov     [rsp+98h+var_38], 0
0x180002f9a  mov     rax, [rsp+98h+arg_28]
0x180002fa2  mov     [rsp+98h+var_50], rax
0x180002fa7  mov     eax, [rsp+98h+arg_20]
0x180002fae  mov     [rsp+98h+var_58], eax
0x180002fb2  mov     [rsp+98h+var_60], rdi
0x180002fb7  mov     [rsp+98h+var_68], rsi
0x180002fbc  mov     [rsp+98h+var_70], r14
0x180002fc1  mov     [rsp+98h+var_78], r15
0x180002fc6  mov     r9, [rsp+98h+Binding]
0x180002fcb  xor     r8d, r8d; pReturnValue
0x180002fce  lea     edx, [r8+19h]; nProcNum
0x180002fd2  lea     rcx, pProxyInfo; pProxyInfo
0x180002fd9  call    cs:__imp_NdrClientCall3
0x180002fdf  mov     rbx, rax
0x180002fe2  mov     [rsp+98h+var_38], rax
0x180002fe7  mov     [rsp+98h+var_48], eax
0x180002feb  jmp     short loc_180002FFB
0x180002fed  mov     ecx, eax; Status
0x180002fef  call    cs:__imp_I_RpcMapWin32Status
0x180002ff5  mov     ebx, eax
0x180002ff7  mov     [rsp+98h+var_48], eax
0x180002ffb  lea     rcx, [rsp+98h+Binding]; Binding
0x180003000  call    cs:__imp_RpcBindingFree
0x180003006  mov     eax, ebx
0x180003008  add     rsp, 70h
0x18000300c  pop     r15
0x18000300e  pop     r14
0x180003010  pop     rdi
0x180003011  pop     rsi
0x180003012  pop     rbx
0x180003013  retn
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
