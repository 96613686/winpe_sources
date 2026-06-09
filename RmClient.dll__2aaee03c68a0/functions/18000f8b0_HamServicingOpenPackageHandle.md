# HamServicingOpenPackageHandle

- ea: `0x18000f8b0`
- end: `0x18000f95e`
- name: `HamServicingOpenPackageHandle`
- size: `174`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, int, void *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting, installer_update`

## callees

- `0x18000f8b0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000f8d3`
- `ntdll!RtlLengthSid` at `0x18000f8d3`
- `RPCRT4!NdrClientCall3` at `0x18000f912`
- `RPCRT4!NdrClientCall3` at `0x18000f912`
- `RPCRT4!RpcExceptionFilter` at `0x18001b54c`
- `RPCRT4!RpcExceptionFilter` at `0x18001b54c`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000f931`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000f931`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamServicingOpenPackageHandle(_QWORD *a1, __int64 a2, int a3, void *a4, _QWORD *a5)
{
  CLIENT_CALL_RETURN result; // rax
  int v10; // [rsp+28h] [rbp-60h]
  ULONG v11; // [rsp+38h] [rbp-50h]
  __int64 v12; // [rsp+90h] [rbp+8h] BYREF

  v12 = 0;
  v11 = RtlLengthSid(a4);
  v10 = a3;
  result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DFA0, 2u, 0, *a1, a2, v10, a4, v11, &v12).Pointer;
  if ( SLODWORD(result.Simple) >= 0 )
    *a5 = v12;
  return result;
}

```

## disassembly

```asm
0x18000f8b0  mov     rax, rsp
0x18000f8b3  push    rbx
0x18000f8b4  push    rsi
0x18000f8b5  push    rdi
0x18000f8b6  push    r14
0x18000f8b8  sub     rsp, 68h
0x18000f8bc  mov     rbx, r9
0x18000f8bf  mov     edi, r8d
0x18000f8c2  mov     rsi, rdx
0x18000f8c5  mov     r14, rcx
0x18000f8c8  mov     qword ptr [rax+8], 0
0x18000f8d0  mov     rcx, rbx; Sid
0x18000f8d3  call    cs:__imp_RtlLengthSid
0x18000f8d9  mov     [rsp+88h+var_30], 0
0x18000f8e2  lea     rcx, [rsp+88h+arg_0]
0x18000f8ea  mov     [rsp+88h+var_48], rcx
0x18000f8ef  mov     [rsp+88h+var_50], eax
0x18000f8f3  mov     [rsp+88h+var_58], rbx
0x18000f8f8  mov     [rsp+88h+var_60], edi
0x18000f8fc  mov     [rsp+88h+var_68], rsi
0x18000f901  mov     r9, [r14]
0x18000f904  xor     r8d, r8d; pReturnValue
0x18000f907  lea     edx, [r8+2]; nProcNum
0x18000f90b  lea     rcx, stru_18001DFA0; pProxyInfo
0x18000f912  call    cs:__imp_NdrClientCall3
0x18000f918  mov     [rsp+88h+var_30], rax
0x18000f91d  mov     [rsp+88h+var_38], eax
0x18000f921  jmp     short loc_18000F93B
0x18000f923  mov     [rsp+88h+arg_0], 0FFFFFFFFFFFFFFFFh
0x18000f92f  mov     ecx, eax; Status
0x18000f931  call    cs:__imp_I_RpcMapWin32Status
0x18000f937  mov     [rsp+88h+var_38], eax
0x18000f93b  test    eax, eax
0x18000f93d  jns     short loc_18000F949
0x18000f93f  add     rsp, 68h
0x18000f943  pop     r14
0x18000f945  pop     rdi
0x18000f946  pop     rsi
0x18000f947  pop     rbx
0x18000f948  retn
0x18000f949  mov     rdx, [rsp+88h+arg_20]
0x18000f951  mov     rcx, [rsp+88h+arg_0]
0x18000f959  mov     [rdx], rcx
0x18000f95c  jmp     short loc_18000F93F
0x18001b53e  push    rbp
0x18001b540  sub     rsp, 50h
0x18001b544  mov     rbp, rdx
0x18001b547  mov     rcx, [rcx]
0x18001b54a  mov     ecx, [rcx]; ExceptionCode
0x18001b54c  call    cs:__imp_RpcExceptionFilter
0x18001b552  nop
0x18001b553  add     rsp, 50h
0x18001b557  pop     rbp
0x18001b558  retn
```
