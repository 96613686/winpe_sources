# FwppRpcBindingCreateLocal

- ea: `0x180066aa4`
- end: `0x180066bd2`
- name: `FwppRpcBindingCreateLocal`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800668fc`

## callees

- `0x18000c9b4`
- `0x18000dfac`
- `0x1800203c0`
- `0x180066aa4`
- `0x180066c54`

## import_xrefs

- `msrpc!RpcBindingCreateW` at `0x180066b48`
- `msrpc!RpcBindingCreateW` at `0x180066b48`
- `msrpc!RpcBindingSetOption` at `0x180066b62`
- `msrpc!RpcBindingSetOption` at `0x180066b62`

## string_xrefs

- `0x180066bc0`: `RpcBindingCreateW`
- `0x180066baf`: `FwppRpcBindingCreateLocal`

## pseudocode

```c
__int64 __fastcall FwppRpcBindingCreateLocal(__int64 a1, SEC_WINNT_AUTH_IDENTITY_W *a2, RPC_BINDING_HANDLE *a3)
{
  RPC_STATUS v4; // eax
  __int64 v5; // rcx
  __int64 v6; // rbx
  const char *v8; // rdx
  RPC_BINDING_HANDLE Binding; // [rsp+20h] [rbp-59h] BYREF
  RPC_BINDING_HANDLE_SECURITY_V1_W Security; // [rsp+28h] [rbp-51h] BYREF
  int v11; // [rsp+50h] [rbp-29h] BYREF
  __int64 v12; // [rsp+54h] [rbp-25h]
  int v13; // [rsp+5Ch] [rbp-1Dh]
  __int128 v14; // [rsp+60h] [rbp-19h]
  __int64 v15; // [rsp+70h] [rbp-9h]
  __int64 v16; // [rsp+78h] [rbp-1h]
  RPC_BINDING_HANDLE_TEMPLATE_V1_W Template; // [rsp+80h] [rbp+7h] BYREF

  *a3 = 0;
  memset(&Template, 0, sizeof(Template));
  *(_QWORD *)(&Security.Version + 1) = 0;
  HIDWORD(Security.ServerPrincName) = 0;
  v15 = a1;
  Security.AuthIdentity = a2;
  Security.SecurityQos = (RPC_SECURITY_QOS *)&v11;
  Binding = 0;
  Template.Version = 1;
  Template.ProtocolSequence = 3;
  v16 = 1;
  v14 = 0;
  v11 = 4;
  v12 = 1;
  v13 = 2;
  Security.Version = 1;
  Security.AuthnLevel = 6;
  Security.AuthnSvc = 10;
  v4 = RpcBindingCreateW(&Template, &Security, 0, &Binding);
  if ( v4 )
  {
    v8 = "RpcBindingCreateW";
  }
  else
  {
    v4 = RpcBindingSetOption(Binding, 9u, 1u);
    if ( !v4 )
    {
      v6 = 0;
      *a3 = Binding;
      return v6;
    }
    v8 = "RpcBindingSetOption";
  }
  v6 = WfpReportSysErrorAsRpcStatus(v5, (int)v8, v4);
  if ( v6 )
  {
    FwppRpcBindingDestroy(&Binding);
    WfpReportError(v6, (int)"FwppRpcBindingCreateLocal");
  }
  return v6;
}

```

## disassembly

```asm
0x180066aa4  push    rbp
0x180066aa6  push    rbx
0x180066aa7  push    rdi
0x180066aa8  lea     rbp, [rsp-47h]
0x180066aad  sub     rsp, 0C0h
0x180066ab4  mov     rax, cs:__security_cookie
0x180066abb  xor     rax, rsp
0x180066abe  mov     [rbp+57h+var_18], rax
0x180066ac2  xor     eax, eax
0x180066ac4  mov     qword ptr [r8], 0
0x180066acb  xorps   xmm0, xmm0
0x180066ace  mov     qword ptr [rbp+57h+Template.ObjectUuid.Data4], rax
0x180066ad2  movups  xmmword ptr [rbp+57h+Template.Version], xmm0
0x180066ad6  mov     qword ptr [rbp+57h+Security+4], rax
0x180066ada  lea     r9, [rbp+57h+Binding]; Binding
0x180066ade  lea     ebx, [rax+1]
0x180066ae1  mov     dword ptr [rbp+57h+Security.ServerPrincName+4], eax
0x180066ae4  lea     rax, [rbp+57h+var_80]
0x180066ae8  mov     [rbp+57h+var_60], rcx
0x180066aec  mov     rdi, r8
0x180066aef  mov     [rbp+57h+Security.AuthIdentity], rdx
0x180066af3  xor     r8d, r8d; Options
0x180066af6  mov     [rbp+57h+Security.SecurityQos], rax
0x180066afa  lea     rdx, [rbp+57h+Security]; Security
0x180066afe  mov     [rbp+57h+Binding], 0
0x180066b06  lea     rcx, [rbp+57h+Template]; Template
0x180066b0a  mov     [rbp+57h+Template.Version], ebx
0x180066b0d  movups  xmmword ptr [rbp+57h+Template.NetworkAddress], xmm0
0x180066b11  mov     [rbp+57h+Template.ProtocolSequence], 3
0x180066b18  movups  xmmword ptr [rbp+57h+Template.u1], xmm0
0x180066b1c  mov     [rbp+57h+var_58], rbx
0x180066b20  movdqu  [rbp+57h+var_70], xmm0
0x180066b25  mov     [rbp+57h+var_80], 4
0x180066b2c  mov     [rbp+57h+var_7C], rbx
0x180066b30  mov     [rbp+57h+var_74], 2
0x180066b37  mov     [rbp+57h+Security.Version], ebx
0x180066b3a  mov     [rbp+57h+Security.AuthnLevel], 6
0x180066b41  mov     [rbp+57h+Security.AuthnSvc], 0Ah
0x180066b48  call    cs:__imp_RpcBindingCreateW
0x180066b4f  nop     dword ptr [rax+rax+00h]
0x180066b54  test    eax, eax
0x180066b56  jnz     short loc_180066BC0
0x180066b58  mov     rcx, [rbp+57h+Binding]; hBinding
0x180066b5c  lea     edx, [rbx+8]; option
0x180066b5f  mov     r8d, ebx; optionValue
0x180066b62  call    cs:__imp_RpcBindingSetOption
0x180066b69  nop     dword ptr [rax+rax+00h]
0x180066b6e  test    eax, eax
0x180066b70  jnz     short loc_180066BC9
0x180066b72  mov     rax, [rbp+57h+Binding]
0x180066b76  xor     ebx, ebx
0x180066b78  mov     [rdi], rax
0x180066b7b  mov     rax, rbx
0x180066b7e  mov     rcx, [rbp+57h+var_18]
0x180066b82  xor     rcx, rsp; StackCookie
0x180066b85  call    __security_check_cookie
0x180066b8a  add     rsp, 0C0h
0x180066b91  pop     rdi
0x180066b92  pop     rbx
0x180066b93  pop     rbp
0x180066b94  retn
0x180066b96  mov     r8d, eax
0x180066b99  call    WfpReportSysErrorAsRpcStatus
0x180066b9e  mov     rbx, rax
0x180066ba1  test    rax, rax
0x180066ba4  jz      short loc_180066B7B
0x180066ba6  lea     rcx, [rbp+57h+Binding]
0x180066baa  call    FwppRpcBindingDestroy
0x180066baf  lea     rdx, aFwpprpcbinding; "FwppRpcBindingCreateLocal"
0x180066bb6  mov     rcx, rbx
0x180066bb9  call    WfpReportError
0x180066bbe  jmp     short loc_180066B7B
0x180066bc0  lea     rdx, aRpcbindingcrea; "RpcBindingCreateW"
0x180066bc7  jmp     short loc_180066B96
0x180066bc9  lea     rdx, aRpcbindingseto; "RpcBindingSetOption"
0x180066bd0  jmp     short loc_180066B96
```
