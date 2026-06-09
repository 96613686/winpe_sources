# BiQueryWorkItem

- ea: `0x180002bb0`
- end: `0x180002c4e`
- name: `BiQueryWorkItem`
- size: `158`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002bb0`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002c12`
- `RPCRT4!NdrClientCall3` at `0x180002c12`
- `RPCRT4!RpcBindingFree` at `0x180002c3c`
- `RPCRT4!RpcBindingFree` at `0x180002c3c`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002c28`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002c28`

## pseudocode

```c
__int64 __fastcall BiQueryWorkItem(__int64 a1, __int64 a2, __int64 a3)
{
  int Pointer; // ebx
  int v8; // [rsp+28h] [rbp-50h]
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp+20h] BYREF

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    v8 = 0;
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x15u, 0, Binding, a1, v8, a2, a3).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002bb0  mov     rax, rsp
0x180002bb3  push    rbx
0x180002bb4  push    rsi
0x180002bb5  push    rdi
0x180002bb6  push    r14
0x180002bb8  sub     rsp, 58h
0x180002bbc  mov     rdi, r8
0x180002bbf  mov     rsi, rdx
0x180002bc2  mov     r14, rcx
0x180002bc5  mov     qword ptr [rax+20h], 0
0x180002bcd  lea     rcx, [rax+20h]
0x180002bd1  call    BipCreateRpcBinding
0x180002bd6  mov     ebx, eax
0x180002bd8  test    eax, eax
0x180002bda  js      short loc_180002C42
0x180002bdc  mov     [rsp+78h+var_30], 0
0x180002be5  mov     [rsp+78h+var_40], rdi
0x180002bea  mov     [rsp+78h+var_48], rsi
0x180002bef  mov     [rsp+78h+var_50], 0
0x180002bf7  mov     [rsp+78h+var_58], r14
0x180002bfc  mov     r9, [rsp+78h+Binding]
0x180002c04  xor     r8d, r8d; pReturnValue
0x180002c07  lea     edx, [r8+15h]; nProcNum
0x180002c0b  lea     rcx, pProxyInfo; pProxyInfo
0x180002c12  call    cs:__imp_NdrClientCall3
0x180002c18  mov     rbx, rax
0x180002c1b  mov     [rsp+78h+var_30], rax
0x180002c20  mov     [rsp+78h+var_38], eax
0x180002c24  jmp     short loc_180002C34
0x180002c26  mov     ecx, eax; Status
0x180002c28  call    cs:__imp_I_RpcMapWin32Status
0x180002c2e  mov     ebx, eax
0x180002c30  mov     [rsp+78h+var_38], eax
0x180002c34  lea     rcx, [rsp+78h+Binding]; Binding
0x180002c3c  call    cs:__imp_RpcBindingFree
0x180002c42  mov     eax, ebx
0x180002c44  add     rsp, 58h
0x180002c48  pop     r14
0x180002c4a  pop     rdi
0x180002c4b  pop     rsi
0x180002c4c  pop     rbx
0x180002c4d  retn
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
