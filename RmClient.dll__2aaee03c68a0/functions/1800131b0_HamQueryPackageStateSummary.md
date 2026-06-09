# HamQueryPackageStateSummary

- ea: `0x1800131b0`
- end: `0x18001323d`
- name: `HamQueryPackageStateSummary`
- size: `141`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, void *, _DWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800131b0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x1800131d1`
- `ntdll!RtlLengthSid` at `0x1800131d1`
- `RPCRT4!NdrClientCall3` at `0x18001320a`
- `RPCRT4!NdrClientCall3` at `0x18001320a`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013229`
- `RPCRT4!I_RpcMapWin32Status` at `0x180013229`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamQueryPackageStateSummary(_QWORD *a1, __int64 a2, void *a3, _DWORD *a4)
{
  CLIENT_CALL_RETURN result; // rax
  ULONG v9; // [rsp+30h] [rbp-48h]
  _DWORD v10[2]; // [rsp+40h] [rbp-38h] BYREF
  CLIENT_CALL_RETURN v11; // [rsp+48h] [rbp-30h]

  v10[0] = 0;
  v11.Simple = 0;
  v9 = RtlLengthSid(a3);
  result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DD98, 4u, 0, *a1, a2, a3, v9, v10).Pointer;
  v11.Pointer = result.Pointer;
  v10[1] = result.Pointer;
  if ( SLODWORD(result.Simple) >= 0 )
  {
    *a4 = v10[0];
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800131b0  push    rbx
0x1800131b2  push    rsi
0x1800131b3  push    rdi
0x1800131b4  push    r14
0x1800131b6  sub     rsp, 58h
0x1800131ba  mov     rbx, r9
0x1800131bd  mov     rdi, r8
0x1800131c0  mov     rsi, rdx
0x1800131c3  mov     r14, rcx
0x1800131c6  mov     [rsp+78h+var_38], 0
0x1800131ce  mov     rcx, r8; Sid
0x1800131d1  call    cs:__imp_RtlLengthSid
0x1800131d7  nop
0x1800131d8  mov     [rsp+78h+var_30], 0
0x1800131e1  lea     rcx, [rsp+78h+var_38]
0x1800131e6  mov     [rsp+78h+var_40], rcx
0x1800131eb  mov     [rsp+78h+var_48], eax
0x1800131ef  mov     [rsp+78h+var_50], rdi
0x1800131f4  mov     [rsp+78h+var_58], rsi
0x1800131f9  mov     r9, [r14]
0x1800131fc  xor     r8d, r8d; pReturnValue
0x1800131ff  lea     edx, [r8+4]; nProcNum
0x180013203  lea     rcx, stru_18001DD98; pProxyInfo
0x18001320a  call    cs:__imp_NdrClientCall3
0x180013210  mov     [rsp+78h+var_30], rax
0x180013215  mov     [rsp+78h+var_34], eax
0x180013219  test    eax, eax
0x18001321b  js      short loc_180013233
0x18001321d  mov     eax, [rsp+78h+var_38]
0x180013221  mov     [rbx], eax
0x180013223  xor     eax, eax
0x180013225  jmp     short loc_180013233
0x180013227  mov     ecx, eax; Status
0x180013229  call    cs:__imp_I_RpcMapWin32Status
0x18001322f  mov     [rsp+78h+var_34], eax
0x180013233  add     rsp, 58h
0x180013237  pop     r14
0x180013239  pop     rdi
0x18001323a  pop     rsi
0x18001323b  pop     rbx
0x18001323c  retn
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
