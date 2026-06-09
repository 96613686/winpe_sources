# HamDebugOpenPackageHandle

- ea: `0x18000fe70`
- end: `0x18000ff1c`
- name: `HamDebugOpenPackageHandle`
- size: `172`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, void *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x18000fe70`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x18000fe9a`
- `ntdll!RtlLengthSid` at `0x18000fe9a`
- `RPCRT4!NdrClientCall3` at `0x18000fed2`
- `RPCRT4!NdrClientCall3` at `0x18000fed2`
- `RPCRT4!RpcExceptionFilter` at `0x18001b56e`
- `RPCRT4!RpcExceptionFilter` at `0x18001b56e`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000feee`
- `RPCRT4!I_RpcMapWin32Status` at `0x18000feee`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamDebugOpenPackageHandle(_QWORD *a1, __int64 a2, void *a3, _QWORD *a4)
{
  CLIENT_CALL_RETURN result; // rax
  ULONG v9; // [rsp+30h] [rbp-38h]
  __int64 v10; // [rsp+70h] [rbp+8h] BYREF
  _QWORD *v11; // [rsp+88h] [rbp+20h]

  v11 = a4;
  v10 = 0;
  v9 = RtlLengthSid(a3);
  result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DEE0, 2u, 0, *a1, a2, a3, v9, &v10).Pointer;
  if ( SLODWORD(result.Simple) >= 0 )
    *a4 = v10;
  return result;
}

```

## disassembly

```asm
0x18000fe70  mov     [rsp+arg_8], rbx
0x18000fe75  mov     [rsp+arg_18], r9
0x18000fe7a  push    rsi
0x18000fe7b  push    rdi
0x18000fe7c  push    r14
0x18000fe7e  sub     rsp, 50h
0x18000fe82  mov     rbx, r9
0x18000fe85  mov     rdi, r8
0x18000fe88  mov     rsi, rdx
0x18000fe8b  mov     r14, rcx
0x18000fe8e  mov     [rsp+68h+arg_0], 0
0x18000fe97  mov     rcx, r8; Sid
0x18000fe9a  call    cs:__imp_RtlLengthSid
0x18000fea0  mov     [rsp+68h+var_20], 0
0x18000fea9  lea     rcx, [rsp+68h+arg_0]
0x18000feae  mov     [rsp+68h+var_30], rcx
0x18000feb3  mov     [rsp+68h+var_38], eax
0x18000feb7  mov     [rsp+68h+var_40], rdi
0x18000febc  mov     [rsp+68h+var_48], rsi
0x18000fec1  mov     r9, [r14]
0x18000fec4  xor     r8d, r8d; pReturnValue
0x18000fec7  lea     edx, [r8+2]; nProcNum
0x18000fecb  lea     rcx, stru_18001DEE0; pProxyInfo
0x18000fed2  call    cs:__imp_NdrClientCall3
0x18000fed8  mov     [rsp+68h+var_20], rax
0x18000fedd  mov     [rsp+68h+var_28], eax
0x18000fee1  jmp     short loc_18000FF00
0x18000fee3  mov     [rsp+68h+arg_0], 0FFFFFFFFFFFFFFFFh
0x18000feec  mov     ecx, eax; Status
0x18000feee  call    cs:__imp_I_RpcMapWin32Status
0x18000fef4  mov     [rsp+68h+var_28], eax
0x18000fef8  mov     rbx, [rsp+68h+arg_18]
0x18000ff00  test    eax, eax
0x18000ff02  jns     short loc_18000FF12
0x18000ff04  mov     rbx, [rsp+68h+arg_8]
0x18000ff09  add     rsp, 50h
0x18000ff0d  pop     r14
0x18000ff0f  pop     rdi
0x18000ff10  pop     rsi
0x18000ff11  retn
0x18000ff12  mov     rcx, [rsp+68h+arg_0]
0x18000ff17  mov     [rbx], rcx
0x18000ff1a  jmp     short loc_18000FF04
0x18001b560  push    rbp
0x18001b562  sub     rsp, 40h
0x18001b566  mov     rbp, rdx
0x18001b569  mov     rcx, [rcx]
0x18001b56c  mov     ecx, [rcx]; ExceptionCode
0x18001b56e  call    cs:__imp_RpcExceptionFilter
0x18001b574  nop
0x18001b575  add     rsp, 40h
0x18001b579  pop     rbp
0x18001b57a  retn
```
