# HamFullTrustOpenPackageHandle

- ea: `0x1800199f0`
- end: `0x180019a9c`
- name: `HamFullTrustOpenPackageHandle`
- size: `172`
- prototype: `CLIENT_CALL_RETURN __fastcall(_QWORD *, __int64, int, void *, _QWORD *)`
- caller_count: `0`
- callee_count: `1`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x1800199f0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180019a13`
- `ntdll!RtlLengthSid` at `0x180019a13`
- `RPCRT4!NdrClientCall3` at `0x180019a52`
- `RPCRT4!NdrClientCall3` at `0x180019a52`
- `RPCRT4!I_RpcMapWin32Status` at `0x180019a71`
- `RPCRT4!I_RpcMapWin32Status` at `0x180019a71`

## pseudocode

```c
CLIENT_CALL_RETURN __fastcall HamFullTrustOpenPackageHandle(_QWORD *a1, __int64 a2, int a3, void *a4, _QWORD *a5)
{
  CLIENT_CALL_RETURN result; // rax
  int v10; // [rsp+28h] [rbp-60h]
  ULONG v11; // [rsp+38h] [rbp-50h]
  __int64 v12; // [rsp+90h] [rbp+8h] BYREF

  v12 = 0;
  v11 = RtlLengthSid(a4);
  v10 = a3;
  result.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_180020C70, 2u, 0, *a1, a2, v10, a4, v11, &v12).Pointer;
  if ( SLODWORD(result.Simple) >= 0 )
    *a5 = v12;
  return result;
}

```

## disassembly

```asm
0x1800199f0  mov     rax, rsp
0x1800199f3  push    rbx
0x1800199f4  push    rsi
0x1800199f5  push    rdi
0x1800199f6  push    r14
0x1800199f8  sub     rsp, 68h
0x1800199fc  mov     rbx, r9
0x1800199ff  mov     edi, r8d
0x180019a02  mov     rsi, rdx
0x180019a05  mov     r14, rcx
0x180019a08  mov     qword ptr [rax+8], 0
0x180019a10  mov     rcx, rbx; Sid
0x180019a13  call    cs:__imp_RtlLengthSid
0x180019a19  mov     [rsp+88h+var_30], 0
0x180019a22  lea     rcx, [rsp+88h+arg_0]
0x180019a2a  mov     [rsp+88h+var_48], rcx
0x180019a2f  mov     [rsp+88h+var_50], eax
0x180019a33  mov     [rsp+88h+var_58], rbx
0x180019a38  mov     [rsp+88h+var_60], edi
0x180019a3c  mov     [rsp+88h+var_68], rsi
0x180019a41  mov     r9, [r14]
0x180019a44  xor     r8d, r8d; pReturnValue
0x180019a47  lea     edx, [r8+2]; nProcNum
0x180019a4b  lea     rcx, stru_180020C70; pProxyInfo
0x180019a52  call    cs:__imp_NdrClientCall3
0x180019a58  mov     [rsp+88h+var_30], rax
0x180019a5d  mov     [rsp+88h+var_38], eax
0x180019a61  jmp     short loc_180019A7B
0x180019a63  mov     [rsp+88h+arg_0], 0FFFFFFFFFFFFFFFFh
0x180019a6f  mov     ecx, eax; Status
0x180019a71  call    cs:__imp_I_RpcMapWin32Status
0x180019a77  mov     [rsp+88h+var_38], eax
0x180019a7b  test    eax, eax
0x180019a7d  js      short loc_180019A92
0x180019a7f  mov     rdx, [rsp+88h+arg_20]
0x180019a87  mov     rcx, [rsp+88h+arg_0]
0x180019a8f  mov     [rdx], rcx
0x180019a92  add     rsp, 68h
0x180019a96  pop     r14
0x180019a98  pop     rdi
0x180019a99  pop     rsi
0x180019a9a  pop     rbx
0x180019a9b  retn
0x18001bb0e  push    rbp
0x18001bb10  sub     rsp, 50h
0x18001bb14  mov     rbp, rdx
0x18001bb17  mov     rcx, [rcx]
0x18001bb1a  mov     ecx, [rcx]; ExceptionCode
0x18001bb1c  call    cs:__imp_RpcExceptionFilter
0x18001bb22  nop
0x18001bb23  add     rsp, 50h
0x18001bb27  pop     rbp
0x18001bb28  retn
```
