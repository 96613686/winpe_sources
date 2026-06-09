# HamQueryTaskCompletionsForTerminateGraph

- ea: `0x180019f20`
- end: `0x180019f92`
- name: `HamQueryTaskCompletionsForTerminateGraph`
- size: `114`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x180019f20`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180019f5c`
- `RPCRT4!NdrClientCall3` at `0x180019f5c`
- `RPCRT4!I_RpcMapWin32Status` at `0x180019f6f`
- `RPCRT4!I_RpcMapWin32Status` at `0x180019f6f`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamQueryTaskCompletionsForTerminateGraph(_QWORD *a1, __int64 a2, _QWORD *a3)
{
  CLIENT_CALL_RETURN result; // rax
  __int64 v5; // [rsp+50h] [rbp+8h] BYREF
  _QWORD *v6; // [rsp+60h] [rbp+18h]
  CLIENT_CALL_RETURN v7; // [rsp+68h] [rbp+20h]

  v6 = a3;
  v5 = 0;
  v7.Simple = 0;
  result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DF70, 2u, 0, *a1, a2, &v5).Pointer;
  v7.Pointer = result.Pointer;
  if ( SLODWORD(result.Simple) >= 0 )
  {
    *a3 = v5;
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180019f20  mov     r11, rsp
0x180019f23  mov     [r11+18h], r8
0x180019f27  push    rbx
0x180019f28  sub     rsp, 40h
0x180019f2c  mov     rbx, r8
0x180019f2f  mov     qword ptr [r11+8], 0
0x180019f37  mov     qword ptr [r11+20h], 0
0x180019f3f  lea     rax, [r11+8]
0x180019f43  mov     [r11-20h], rax
0x180019f47  mov     [r11-28h], rdx
0x180019f4b  mov     r9, [rcx]
0x180019f4e  xor     r8d, r8d; pReturnValue
0x180019f51  lea     edx, [r8+2]; nProcNum
0x180019f55  lea     rcx, stru_18001DF70; pProxyInfo
0x180019f5c  call    cs:__imp_NdrClientCall3
0x180019f62  mov     [rsp+48h+arg_18], rax
0x180019f67  mov     [rsp+48h+var_18], eax
0x180019f6b  jmp     short loc_180019F7E
0x180019f6d  mov     ecx, eax; Status
0x180019f6f  call    cs:__imp_I_RpcMapWin32Status
0x180019f75  mov     [rsp+48h+var_18], eax
0x180019f79  mov     rbx, [rsp+48h+arg_10]
0x180019f7e  test    eax, eax
0x180019f80  js      short loc_180019F8C
0x180019f82  mov     rax, [rsp+48h+arg_0]
0x180019f87  mov     [rbx], rax
0x180019f8a  xor     eax, eax
0x180019f8c  add     rsp, 40h
0x180019f90  pop     rbx
0x180019f91  retn
0x18001ba86  push    rbp
0x18001ba88  sub     rsp, 30h
0x18001ba8c  mov     rbp, rdx
0x18001ba8f  mov     rcx, [rcx]
0x18001ba92  mov     ecx, [rcx]; ExceptionCode
0x18001ba94  call    cs:__imp_RpcExceptionFilter
0x18001ba9a  nop
0x18001ba9b  add     rsp, 30h
0x18001ba9f  pop     rbp
0x18001baa0  retn
```
