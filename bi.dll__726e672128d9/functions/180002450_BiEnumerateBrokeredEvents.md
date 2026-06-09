# BiEnumerateBrokeredEvents

- ea: `0x180002450`
- end: `0x1800024e6`
- name: `BiEnumerateBrokeredEvents`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180002450`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x1800024aa`
- `RPCRT4!NdrClientCall3` at `0x1800024aa`
- `RPCRT4!RpcBindingFree` at `0x1800024d4`
- `RPCRT4!RpcBindingFree` at `0x1800024d4`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800024c0`
- `RPCRT4!I_RpcMapWin32Status` at `0x1800024c0`

## pseudocode

```c
__int64 __fastcall BiEnumerateBrokeredEvents(__int64 a1, __int64 a2, __int64 a3)
{
  int Pointer; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp+20h] BYREF

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0xBu, 0, Binding, a1, a2, a3).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002450  mov     rax, rsp
0x180002453  push    rbx
0x180002454  push    rsi
0x180002455  push    rdi
0x180002456  push    r14
0x180002458  sub     rsp, 58h
0x18000245c  mov     rdi, r8
0x18000245f  mov     rsi, rdx
0x180002462  mov     r14, rcx
0x180002465  mov     qword ptr [rax+20h], 0
0x18000246d  lea     rcx, [rax+20h]
0x180002471  call    BipCreateRpcBinding
0x180002476  mov     ebx, eax
0x180002478  test    eax, eax
0x18000247a  js      short loc_1800024DA
0x18000247c  mov     [rsp+78h+var_30], 0
0x180002485  mov     [rsp+78h+var_48], rdi
0x18000248a  mov     [rsp+78h+var_50], rsi
0x18000248f  mov     [rsp+78h+var_58], r14
0x180002494  mov     r9, [rsp+78h+Binding]
0x18000249c  xor     r8d, r8d; pReturnValue
0x18000249f  lea     edx, [r8+0Bh]; nProcNum
0x1800024a3  lea     rcx, pProxyInfo; pProxyInfo
0x1800024aa  call    cs:__imp_NdrClientCall3
0x1800024b0  mov     rbx, rax
0x1800024b3  mov     [rsp+78h+var_30], rax
0x1800024b8  mov     [rsp+78h+var_38], eax
0x1800024bc  jmp     short loc_1800024CC
0x1800024be  mov     ecx, eax; Status
0x1800024c0  call    cs:__imp_I_RpcMapWin32Status
0x1800024c6  mov     ebx, eax
0x1800024c8  mov     [rsp+78h+var_38], eax
0x1800024cc  lea     rcx, [rsp+78h+Binding]; Binding
0x1800024d4  call    cs:__imp_RpcBindingFree
0x1800024da  mov     eax, ebx
0x1800024dc  add     rsp, 58h
0x1800024e0  pop     r14
0x1800024e2  pop     rdi
0x1800024e3  pop     rsi
0x1800024e4  pop     rbx
0x1800024e5  retn
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
