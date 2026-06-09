# BiQueryUserContext

- ea: `0x180002a70`
- end: `0x180002b06`
- name: `BiQueryUserContext`
- size: `150`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180002a70`
- `0x180003228`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180002aca`
- `RPCRT4!NdrClientCall3` at `0x180002aca`
- `RPCRT4!RpcBindingFree` at `0x180002af4`
- `RPCRT4!RpcBindingFree` at `0x180002af4`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002ae0`
- `RPCRT4!I_RpcMapWin32Status` at `0x180002ae0`

## pseudocode

```c
__int64 __fastcall BiQueryUserContext(__int64 a1, __int64 a2, __int64 a3)
{
  int Pointer; // ebx
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp+20h] BYREF

  Binding = 0;
  Pointer = BipCreateRpcBinding(&Binding);
  if ( Pointer >= 0 )
  {
    Pointer = (unsigned int)NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x13u, 0, Binding, a1, a2, a3).Pointer;
    RpcBindingFree(&Binding);
  }
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180002a70  mov     rax, rsp
0x180002a73  push    rbx
0x180002a74  push    rsi
0x180002a75  push    rdi
0x180002a76  push    r14
0x180002a78  sub     rsp, 58h
0x180002a7c  mov     rdi, r8
0x180002a7f  mov     rsi, rdx
0x180002a82  mov     r14, rcx
0x180002a85  mov     qword ptr [rax+20h], 0
0x180002a8d  lea     rcx, [rax+20h]
0x180002a91  call    BipCreateRpcBinding
0x180002a96  mov     ebx, eax
0x180002a98  test    eax, eax
0x180002a9a  js      short loc_180002AFA
0x180002a9c  mov     [rsp+78h+var_30], 0
0x180002aa5  mov     [rsp+78h+var_48], rdi
0x180002aaa  mov     [rsp+78h+var_50], rsi
0x180002aaf  mov     [rsp+78h+var_58], r14
0x180002ab4  mov     r9, [rsp+78h+Binding]
0x180002abc  xor     r8d, r8d; pReturnValue
0x180002abf  lea     edx, [r8+13h]; nProcNum
0x180002ac3  lea     rcx, pProxyInfo; pProxyInfo
0x180002aca  call    cs:__imp_NdrClientCall3
0x180002ad0  mov     rbx, rax
0x180002ad3  mov     [rsp+78h+var_30], rax
0x180002ad8  mov     [rsp+78h+var_38], eax
0x180002adc  jmp     short loc_180002AEC
0x180002ade  mov     ecx, eax; Status
0x180002ae0  call    cs:__imp_I_RpcMapWin32Status
0x180002ae6  mov     ebx, eax
0x180002ae8  mov     [rsp+78h+var_38], eax
0x180002aec  lea     rcx, [rsp+78h+Binding]; Binding
0x180002af4  call    cs:__imp_RpcBindingFree
0x180002afa  mov     eax, ebx
0x180002afc  add     rsp, 58h
0x180002b00  pop     r14
0x180002b02  pop     rdi
0x180002b03  pop     rsi
0x180002b04  pop     rbx
0x180002b05  retn
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
