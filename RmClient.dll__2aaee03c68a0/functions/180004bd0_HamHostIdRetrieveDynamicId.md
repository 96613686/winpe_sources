# HamHostIdRetrieveDynamicId

- ea: `0x180004bd0`
- end: `0x180004c8c`
- name: `HamHostIdRetrieveDynamicId`
- size: `188`
- prototype: `__int64 __fastcall(PSID Sid, int, __int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180002f50`
- `0x180004bd0`

## import_xrefs

- `ntdll!RtlLengthSid` at `0x180004c0b`
- `ntdll!RtlLengthSid` at `0x180004c0b`
- `RPCRT4!NdrClientCall3` at `0x180004c41`
- `RPCRT4!NdrClientCall3` at `0x180004c41`
- `RPCRT4!RpcBindingFree` at `0x180004c76`
- `RPCRT4!RpcBindingFree` at `0x180004c76`
- `RPCRT4!RpcExceptionFilter` at `0x18001b1e2`
- `RPCRT4!RpcExceptionFilter` at `0x18001b1e2`
- `RPCRT4!I_RpcMapWin32Status` at `0x180004c57`
- `RPCRT4!I_RpcMapWin32Status` at `0x180004c57`

## pseudocode

```c
__int64 __fastcall HamHostIdRetrieveDynamicId(PSID Sid, int a2, __int64 a3, __int64 a4)
{
  int Pointer; // ebx
  ULONG v9; // eax
  CLIENT_CALL_RETURN v10; // rax
  ULONG v12; // [rsp+28h] [rbp-80h]
  int v13; // [rsp+30h] [rbp-78h]
  RPC_BINDING_HANDLE Binding; // [rsp+58h] [rbp-50h] BYREF
  CLIENT_CALL_RETURN v15; // [rsp+60h] [rbp-48h]

  Binding = 0;
  Pointer = CempRpcBindToServer(qword_18001DBC0, &Binding);
  if ( Pointer >= 0 )
  {
    v9 = RtlLengthSid(Sid);
    v15.Simple = 0;
    v13 = a2;
    v12 = v9;
    v10.Pointer = NdrClientCall3((MIDL_STUBLESS_PROXY_INFO *)&stru_18001DC20, 3u, 0, Binding, Sid, v12, v13, a3, a4).Pointer;
    Pointer = (int)v10.Pointer;
    v15.Pointer = v10.Pointer;
    if ( SLODWORD(v10.Simple) >= 0 )
      Pointer = 0;
  }
  if ( Binding )
    RpcBindingFree(&Binding);
  return (unsigned int)Pointer;
}

```

## disassembly

```asm
0x180004bd0  push    rbx
0x180004bd2  push    rsi
0x180004bd3  push    rdi
0x180004bd4  push    r12
0x180004bd6  push    r14
0x180004bd8  push    r15
0x180004bda  sub     rsp, 78h
0x180004bde  mov     r14, r9
0x180004be1  mov     r15, r8
0x180004be4  mov     r12d, edx
0x180004be7  mov     rsi, rcx
0x180004bea  xor     edi, edi
0x180004bec  mov     [rsp+0A8h+Binding], rdi
0x180004bf1  lea     rdx, [rsp+0A8h+Binding]
0x180004bf6  lea     rcx, qword_18001DBC0; IfSpec
0x180004bfd  call    CempRpcBindToServer
0x180004c02  mov     ebx, eax
0x180004c04  test    eax, eax
0x180004c06  js      short loc_180004C6A
0x180004c08  mov     rcx, rsi; Sid
0x180004c0b  call    cs:__imp_RtlLengthSid
0x180004c11  nop
0x180004c12  mov     [rsp+0A8h+var_48], rdi
0x180004c17  mov     [rsp+0A8h+var_68], r14
0x180004c1c  mov     [rsp+0A8h+var_70], r15
0x180004c21  mov     [rsp+0A8h+var_78], r12d
0x180004c26  mov     [rsp+0A8h+var_80], eax
0x180004c2a  mov     [rsp+0A8h+var_88], rsi
0x180004c2f  mov     r9, [rsp+0A8h+Binding]
0x180004c34  xor     r8d, r8d; pReturnValue
0x180004c37  lea     edx, [rdi+3]; nProcNum
0x180004c3a  lea     rcx, stru_18001DC20; pProxyInfo
0x180004c41  call    cs:__imp_NdrClientCall3
0x180004c47  mov     rbx, rax
0x180004c4a  mov     [rsp+0A8h+var_48], rax
0x180004c4f  mov     [rsp+0A8h+var_58], eax
0x180004c53  jmp     short loc_180004C65
0x180004c55  mov     ecx, eax; Status
0x180004c57  call    cs:__imp_I_RpcMapWin32Status
0x180004c5d  mov     ebx, eax
0x180004c5f  mov     [rsp+0A8h+var_58], eax
0x180004c63  xor     edi, edi
0x180004c65  test    ebx, ebx
0x180004c67  cmovns  ebx, edi
0x180004c6a  cmp     [rsp+0A8h+Binding], rdi
0x180004c6f  jz      short loc_180004C7C
0x180004c71  lea     rcx, [rsp+0A8h+Binding]; Binding
0x180004c76  call    cs:__imp_RpcBindingFree
0x180004c7c  mov     eax, ebx
0x180004c7e  add     rsp, 78h
0x180004c82  pop     r15
0x180004c84  pop     r14
0x180004c86  pop     r12
0x180004c88  pop     rdi
0x180004c89  pop     rsi
0x180004c8a  pop     rbx
0x180004c8b  retn
0x18001b1d4  push    rbp
0x18001b1d6  sub     rsp, 50h
0x18001b1da  mov     rbp, rdx
0x18001b1dd  mov     rcx, [rcx]
0x18001b1e0  mov     ecx, [rcx]; ExceptionCode
0x18001b1e2  call    cs:__imp_RpcExceptionFilter
0x18001b1e8  nop
0x18001b1e9  add     rsp, 50h
0x18001b1ed  pop     rbp
0x18001b1ee  retn
```
