# HamRegisterDesktopProcessWithAppContainerToken

- ea: `0x180019fa0`
- end: `0x18001a098`
- name: `HamRegisterDesktopProcessWithAppContainerToken`
- size: `248`
- prototype: `__int64 __fastcall(__int64, int, __int64)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x180002f50`
- `0x18000dfcc`
- `0x180019fa0`
- `0x18001ab9c`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x18001a011`
- `RPCRT4!NdrClientCall3` at `0x18001a011`
- `RPCRT4!RpcBindingFree` at `0x18001a06c`
- `RPCRT4!RpcBindingFree` at `0x18001a06c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001a027`
- `RPCRT4!I_RpcMapWin32Status` at `0x18001a027`

## pseudocode

```c
__int64 __fastcall HamRegisterDesktopProcessWithAppContainerToken(__int64 a1, int a2, __int64 a3)
{
  CLIENT_CALL_RETURN v6; // rbx
  int v8; // [rsp+28h] [rbp-50h]
  _QWORD v9[6]; // [rsp+48h] [rbp-30h] BYREF
  RPC_BINDING_HANDLE Binding; // [rsp+98h] [rbp+20h] BYREF

  v9[0] = 0;
  Binding = 0;
  LODWORD(v6.Pointer) = CempRpcBindToServer(qword_18001DC80, &Binding);
  if ( SLODWORD(v6.Simple) >= 0 )
  {
    v8 = a2;
    v6.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&pProxyInfo, 0x18u, 0, Binding, a1, v8, a3).Pointer;
    v9[1] = v6.Pointer;
    if ( SLODWORD(v6.Simple) >= 0 )
    {
      LODWORD(v6.Pointer) = HamCreateAutoRestartActivityForDesktopBridge(a1, (__int64)v9);
      if ( SLODWORD(v6.Simple) >= 0 )
      {
        LODWORD(v6.Pointer) = 0;
        v9[0] = 0;
      }
    }
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  if ( v9[0] )
    HamCloseActivityForDesktopBridge(a1);
  return LODWORD(v6.Pointer);
}

```

## disassembly

```asm
0x180019fa0  mov     rax, rsp
0x180019fa3  mov     [rax+10h], rbx
0x180019fa7  mov     [rax+8], rcx
0x180019fab  push    rsi
0x180019fac  push    r14
0x180019fae  push    r15
0x180019fb0  sub     rsp, 60h
0x180019fb4  mov     r14, r8
0x180019fb7  mov     r15d, edx
0x180019fba  mov     rsi, rcx
0x180019fbd  mov     qword ptr [rax-30h], 0
0x180019fc5  mov     qword ptr [rax+20h], 0
0x180019fcd  lea     rdx, [rax+20h]
0x180019fd1  lea     rcx, qword_18001DC80; IfSpec
0x180019fd8  call    CempRpcBindToServer
0x180019fdd  mov     ebx, eax
0x180019fdf  test    eax, eax
0x180019fe1  js      short loc_18001A059
0x180019fe3  mov     [rsp+78h+var_28], 0
0x180019fec  mov     [rsp+78h+var_48], r14
0x180019ff1  mov     [rsp+78h+var_50], r15d
0x180019ff6  mov     [rsp+78h+var_58], rsi
0x180019ffb  mov     r9, [rsp+78h+Binding]
0x18001a003  xor     r8d, r8d; pReturnValue
0x18001a006  lea     edx, [r8+18h]; nProcNum
0x18001a00a  lea     rcx, pProxyInfo; pProxyInfo
0x18001a011  call    cs:__imp_NdrClientCall3
0x18001a017  mov     rbx, rax
0x18001a01a  mov     [rsp+78h+var_28], rax
0x18001a01f  mov     [rsp+78h+var_38], eax
0x18001a023  jmp     short loc_18001A03B
0x18001a025  mov     ecx, eax; Status
0x18001a027  call    cs:__imp_I_RpcMapWin32Status
0x18001a02d  mov     ebx, eax
0x18001a02f  mov     [rsp+78h+var_38], eax
0x18001a033  mov     rsi, [rsp+78h+arg_0]
0x18001a03b  test    ebx, ebx
0x18001a03d  js      short loc_18001A059
0x18001a03f  lea     rdx, [rsp+78h+var_30]
0x18001a044  mov     rcx, rsi
0x18001a047  call    HamCreateAutoRestartActivityForDesktopBridge
0x18001a04c  mov     ebx, eax
0x18001a04e  test    eax, eax
0x18001a050  js      short loc_18001A059
0x18001a052  xor     ebx, ebx
0x18001a054  mov     [rsp+78h+var_30], rbx
0x18001a059  cmp     [rsp+78h+Binding], 0
0x18001a062  jz      short loc_18001A072
0x18001a064  lea     rcx, [rsp+78h+Binding]; Binding
0x18001a06c  call    cs:__imp_RpcBindingFree
0x18001a072  mov     rdx, [rsp+78h+var_30]
0x18001a077  test    rdx, rdx
0x18001a07a  jz      short loc_18001A084
0x18001a07c  mov     rcx, rsi
0x18001a07f  call    HamCloseActivityForDesktopBridge
0x18001a084  mov     eax, ebx
0x18001a086  mov     rbx, [rsp+78h+arg_8]
0x18001a08e  add     rsp, 60h
0x18001a092  pop     r15
0x18001a094  pop     r14
0x18001a096  pop     rsi
0x18001a097  retn
0x18001b75e  push    rbp
0x18001b760  sub     rsp, 40h
0x18001b764  mov     rbp, rdx
0x18001b767  mov     rcx, [rcx]
0x18001b76a  mov     ecx, [rcx]; ExceptionCode
0x18001b76c  call    cs:__imp_RpcExceptionFilter
0x18001b772  nop
0x18001b773  add     rsp, 40h
0x18001b777  pop     rbp
0x18001b778  retn
```
