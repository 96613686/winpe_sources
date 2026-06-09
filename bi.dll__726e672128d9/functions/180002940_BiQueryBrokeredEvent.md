# BiQueryBrokeredEvent

- ea: `0x180002940`
- end: `0x1800029d6`
- name: `BiQueryBrokeredEvent`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002940`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18000299a`
- `RPCRT4!NdrClientCall3` at `0x18000299a`
- `RPCRT4!RpcBindingFree` at `0x1800029c4`
- `RPCRT4!RpcBindingFree` at `0x1800029c4`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800029b0`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800029b0`

## pseudocode

```c
__int64 __fastcall BiQueryBrokeredEvent(__int64 a1, __int64 a2, __int64 a3)
{
  int Pointer; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp+20h] BYREF

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x11u, 0, Binding, a1, a2, a3).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002940  mov     rax, rsp
0x180002943  push    rbx
0x180002944  push    rsi
0x180002945  push    rdi
0x180002946  push    r14
0x180002948  sub     rsp, 58h
0x18000294c  mov     rdi, r8
0x18000294f  mov     rsi, rdx
0x180002952  mov     r14, rcx
0x180002955  mov     qword ptr [rax+20h], 0
0x18000295d  lea     rcx, [rax+20h]
0x180002961  call    BipCreateRpcBinding
0x180002966  mov     ebx, eax
0x180002968  test    eax, eax
0x18000296a  js      short loc_1800029CA
0x18000296c  mov     [rsp+78h+var_30], 0
0x180002975  mov     [rsp+78h+var_48], rdi
0x18000297a  mov     [rsp+78h+var_50], rsi
0x18000297f  mov     [rsp+78h+var_58], r14
0x180002984  mov     r9, [rsp+78h+Binding]
0x18000298c  xor     r8d, r8d; pReturnValue
0x18000298f  lea     edx, [r8+11h]; nProcNum
0x180002993  lea     rcx, pProxyInfo; pProxyInfo
0x18000299a  call    cs:__imp_NdrClientCall3
0x1800029a0  mov     rbx, rax
0x1800029a3  mov     [rsp+78h+var_30], rax
0x1800029a8  mov     [rsp+78h+var_38], eax
0x1800029ac  jmp     short loc_1800029BC
0x1800029ae  mov     ecx, eax; Status
0x1800029b0  call    cs:__imp_I_RpcMapWin32Status
0x1800029b6  mov     ebx, eax
0x1800029b8  mov     [rsp+78h+var_38], eax
0x1800029bc  lea     rcx, [rsp+78h+Binding]; Binding
0x1800029c4  call    cs:__imp_RpcBindingFree
0x1800029ca  mov     eax, ebx
0x1800029cc  add     rsp, 58h
0x1800029d0  pop     r14
0x1800029d2  pop     rdi
0x1800029d3  pop     rsi
0x1800029d4  pop     rbx
0x1800029d5  retn
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
