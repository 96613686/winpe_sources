# HamCompleteExtendedExecution

- ea: `0x180010d00`
- end: `0x180010dca`
- name: `HamCompleteExtendedExecution`
- size: `202`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x1800092d0`
- `0x180010d00`
- `0x18001ae8e`

## import_xrefs

- `RPCRT4!NdrClientCall3` at `0x180010d4f`
- `RPCRT4!NdrClientCall3` at `0x180010d4f`
- `RPCRT4!RpcExceptionFilter` at `0x18001b67e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b67e`
- `RPCRT4!I_RpcMapWin32Status` at `0x180010d65`
- `RPCRT4!I_RpcMapWin32Status` at `0x180010d65`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamCompleteExtendedExecution(_QWORD *a1, __int64 a2)
{
  CLIENT_CALL_RETURN result; // rax
  _QWORD v5[2]; // [rsp+40h] [rbp-48h] BYREF
  int v6; // [rsp+50h] [rbp-38h]

  memset_0(v5, 0, 0x40u);
  result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DF70, 5u, 0, *a1, a2).Pointer;
  if ( SLODWORD(result.Simple) >= 0 )
  {
    memset_0(v5, 0, 0x40u);
    v5[0] = a2;
    v5[1] = 0;
    v6 = 3;
    HamIpcChannelObjectMakeZombie(a1 + 3, v5);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x180010d00  mov     rax, rsp
0x180010d03  mov     [rax+20h], rbx
0x180010d07  mov     [rax+10h], rdx
0x180010d0b  mov     [rax+8], rcx
0x180010d0f  push    rdi
0x180010d10  sub     rsp, 80h
0x180010d17  mov     rbx, rdx
0x180010d1a  mov     rdi, rcx
0x180010d1d  xor     edx, edx; Val
0x180010d1f  lea     r8d, [rdx+40h]; Size
0x180010d23  lea     rcx, [rax-48h]; void *
0x180010d27  call    memset_0
0x180010d2c  nop
0x180010d2d  mov     [rsp+88h+arg_10], 0
0x180010d39  mov     [rsp+88h+var_68], rbx
0x180010d3e  mov     r9, [rdi]
0x180010d41  xor     r8d, r8d; pReturnValue
0x180010d44  lea     edx, [r8+5]; nProcNum
0x180010d48  lea     rcx, stru_18001DF70; pProxyInfo
0x180010d4f  call    cs:__imp_NdrClientCall3
0x180010d55  mov     [rsp+88h+arg_10], rax
0x180010d5d  mov     [rsp+88h+var_58], eax
0x180010d61  jmp     short loc_180010D7F
0x180010d63  mov     ecx, eax; Status
0x180010d65  call    cs:__imp_I_RpcMapWin32Status
0x180010d6b  mov     [rsp+88h+var_58], eax
0x180010d6f  mov     rbx, [rsp+88h+arg_8]
0x180010d77  mov     rdi, [rsp+88h+arg_0]
0x180010d7f  test    eax, eax
0x180010d81  js      short loc_180010DB9
0x180010d83  xor     edx, edx; Val
0x180010d85  lea     r8d, [rdx+40h]; Size
0x180010d89  lea     rcx, [rsp+88h+var_48]; void *
0x180010d8e  call    memset_0
0x180010d93  mov     [rsp+88h+var_48], rbx
0x180010d98  mov     [rsp+88h+var_40], 0
0x180010da1  mov     [rsp+88h+var_38], 3
0x180010da9  lea     rcx, [rdi+18h]
0x180010dad  lea     rdx, [rsp+88h+var_48]
0x180010db2  call    HamIpcChannelObjectMakeZombie
0x180010db7  xor     eax, eax
0x180010db9  mov     rbx, [rsp+88h+arg_18]
0x180010dc1  add     rsp, 80h
0x180010dc8  pop     rdi
0x180010dc9  retn
0x18001b670  push    rbp
0x18001b672  sub     rsp, 30h
0x18001b676  mov     rbp, rdx
0x18001b679  mov     rcx, [rcx]
0x18001b67c  mov     ecx, [rcx]; ExceptionCode
0x18001b67e  call    cs:__imp_RpcExceptionFilter
0x18001b684  nop
0x18001b685  add     rsp, 30h
0x18001b689  pop     rbp
0x18001b68a  retn
```
