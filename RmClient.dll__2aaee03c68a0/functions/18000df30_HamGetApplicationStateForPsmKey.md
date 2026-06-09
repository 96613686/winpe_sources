# HamGetApplicationStateForPsmKey

- ea: `0x18000df30`
- end: `0x18000dfc5`
- name: `HamGetApplicationStateForPsmKey`
- size: `149`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, void *, __int64, __int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000df30`

## import_xrefs

- `ntdll!RtlValidSid` at `0x18000df49`
- `ntdll!RtlValidSid` at `0x18000df49`
- `ntdll!RtlLengthSid` at `0x18000df56`
- `ntdll!RtlLengthSid` at `0x18000df56`
- `RPCRT4!NdrClientCall3` at `0x18000df97`
- `RPCRT4!NdrClientCall3` at `0x18000df97`
- `RPCRT4!RpcExceptionFilter` at `0x18001b45e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b45e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000dfaa`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000dfaa`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamGetApplicationStateForPsmKey(_QWORD *a1, __int64 a2, void *a3, __int64 a4, __int64 a5)
{
  ULONG v10; // [rsp+30h] [rbp-58h]

  if ( RtlValidSid(a3) )
  {
    v10 = RtlLengthSid(a3);
    return NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DD98, 2u, 0, *a1, a2, a3, v10, a4, a5);
  }
  else
  {
    return (CLIENT_CALL_RETURN)3221225713LL;
  }
}

```

## disassembly

```asm
0x18000df30  push    rbx
0x18000df32  push    rsi
0x18000df33  push    rdi
0x18000df34  push    r14
0x18000df36  sub     rsp, 68h
0x18000df3a  mov     rdi, r9
0x18000df3d  mov     rbx, r8
0x18000df40  mov     rsi, rdx
0x18000df43  mov     r14, rcx
0x18000df46  mov     rcx, r8; Sid
0x18000df49  call    cs:__imp_RtlValidSid
0x18000df4f  test    al, al
0x18000df51  jz      short loc_18000DFBE
0x18000df53  mov     rcx, rbx; Sid
0x18000df56  call    cs:__imp_RtlLengthSid
0x18000df5c  mov     [rsp+88h+var_30], 0
0x18000df65  mov     rcx, [rsp+88h+arg_20]
0x18000df6d  mov     [rsp+88h+var_48], rcx
0x18000df72  mov     [rsp+88h+var_50], rdi
0x18000df77  mov     [rsp+88h+var_58], eax
0x18000df7b  mov     [rsp+88h+var_60], rbx
0x18000df80  mov     [rsp+88h+var_68], rsi
0x18000df85  mov     r9, [r14]
0x18000df88  xor     r8d, r8d; pReturnValue
0x18000df8b  mov     edx, 2; nProcNum
0x18000df90  lea     rcx, stru_18001DD98; pProxyInfo
0x18000df97  call    cs:__imp_NdrClientCall3
0x18000df9d  mov     [rsp+88h+var_30], rax
0x18000dfa2  mov     [rsp+88h+var_38], eax
0x18000dfa6  jmp     short loc_18000DFB4
0x18000dfa8  mov     ecx, eax; Status
0x18000dfaa  call    cs:__imp_I_RpcMapWin32Status
0x18000dfb0  mov     [rsp+88h+var_38], eax
0x18000dfb4  add     rsp, 68h
0x18000dfb8  pop     r14
0x18000dfba  pop     rdi
0x18000dfbb  pop     rsi
0x18000dfbc  pop     rbx
0x18000dfbd  retn
0x18000dfbe  mov     eax, 0C00000F1h
0x18000dfc3  jmp     short loc_18000DFB4
0x18001b450  push    rbp
0x18001b452  sub     rsp, 50h
0x18001b456  mov     rbp, rdx
0x18001b459  mov     rcx, [rcx]
0x18001b45c  mov     ecx, [rcx]; ExceptionCode
0x18001b45e  call    cs:__imp_RpcExceptionFilter
0x18001b464  nop
0x18001b465  add     rsp, 50h
0x18001b469  pop     rbp
0x18001b46a  retn
```
