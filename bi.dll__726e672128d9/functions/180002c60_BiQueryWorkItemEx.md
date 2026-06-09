# BiQueryWorkItemEx

- ea: `0x180002c60`
- end: `0x180002cfd`
- name: `BiQueryWorkItemEx`
- size: `157`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002c60`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002cc2`
- `RPCRT4!NdrClientCall3` at `0x180002cc2`
- `RPCRT4!RpcExceptionFilter` at `0x1800038b2`
- `RPCRT4!RpcExceptionFilter` at `0x1800038b2`
- `RPCRT4!RpcBindingFree` at `0x180002ce9`
- `RPCRT4!RpcBindingFree` at `0x180002ce9`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002cd8`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002cd8`

## pseudocode

```c
__int64 __fastcall BiQueryWorkItemEx(__int64 a1, unsigned __int8 a2, __int64 a3, __int64 a4)
{
  int v6; // r14d
  int Pointer; // ebx
  CLIENT_CALL_RETURN v9; // rax
  int v11; // [rsp+28h] [rbp-60h]
  RPC_BINDING_HANDLE Binding; // [rsp+48h] [rbp-40h] BYREF
  CLIENT_CALL_RETURN v13; // [rsp+50h] [rbp-38h]

  v6 = a2;
  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v13.Simple = 0;
    v11 = v6;
    v9.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x15u, 0, Binding, a1, v11, a3, a4).Pointer;
    Pointer = (int)v9.Pointer;
    v13.Pointer = v9.Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002c60  push    rbx
0x180002c62  push    rsi
0x180002c63  push    rdi
0x180002c64  push    r14
0x180002c66  push    r15
0x180002c68  sub     rsp, 60h
0x180002c6c  mov     rdi, r9
0x180002c6f  mov     rsi, r8
0x180002c72  movzx   r14d, dl
0x180002c76  mov     r15, rcx
0x180002c79  mov     [rsp+88h+Binding], 0
0x180002c82  lea     rcx, [rsp+88h+Binding]
0x180002c87  call    BipCreateRpcBinding
0x180002c8c  mov     ebx, eax
0x180002c8e  test    eax, eax
0x180002c90  js      short loc_180002CEF
0x180002c92  mov     [rsp+88h+var_38], 0
0x180002c9b  mov     [rsp+88h+var_50], rdi
0x180002ca0  mov     [rsp+88h+var_58], rsi
0x180002ca5  mov     [rsp+88h+var_60], r14d
0x180002caa  mov     [rsp+88h+var_68], r15
0x180002caf  mov     r9, [rsp+88h+Binding]
0x180002cb4  xor     r8d, r8d; pReturnValue
0x180002cb7  lea     edx, [r8+15h]; nProcNum
0x180002cbb  lea     rcx, pProxyInfo; pProxyInfo
0x180002cc2  call    cs:__imp_NdrClientCall3
0x180002cc8  mov     rbx, rax
0x180002ccb  mov     [rsp+88h+var_38], rax
0x180002cd0  mov     [rsp+88h+var_48], eax
0x180002cd4  jmp     short loc_180002CE4
0x180002cd6  mov     ecx, eax; Status
0x180002cd8  call    cs:__imp_I_RpcMapWin32Status
0x180002cde  mov     ebx, eax
0x180002ce0  mov     [rsp+88h+var_48], eax
0x180002ce4  lea     rcx, [rsp+88h+Binding]; Binding
0x180002ce9  call    cs:__imp_RpcBindingFree
0x180002cef  mov     eax, ebx
0x180002cf1  add     rsp, 60h
0x180002cf5  pop     r15
0x180002cf7  pop     r14
0x180002cf9  pop     rdi
0x180002cfa  pop     rsi
0x180002cfb  pop     rbx
0x180002cfc  retn
0x1800038a4  push    rbp
0x1800038a6  sub     rsp, 40h
0x1800038aa  mov     rbp, rdx
0x1800038ad  mov     rcx, [rcx]
0x1800038b0  mov     ecx, [rcx]; ExceptionCode
0x1800038b2  call    cs:__imp_RpcExceptionFilter
0x1800038b8  nop
0x1800038b9  add     rsp, 40h
0x1800038bd  pop     rbp
0x1800038be  retn
```
