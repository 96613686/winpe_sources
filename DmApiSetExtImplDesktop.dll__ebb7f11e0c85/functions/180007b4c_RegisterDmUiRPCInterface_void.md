# RegisterDmUiRPCInterface(void)

- ea: `0x180007b4c`
- end: `0x180007c85`
- name: `?RegisterDmUiRPCInterface@@YAJXZ`
- size: `313`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800074dc`

## callees

- `0x180007b4c`

## import_xrefs

- `RPCRT4!RpcServerInqBindings` at `0x180007bd3`
- `RPCRT4!RpcServerInqBindings` at `0x180007bd3`
- `RPCRT4!RpcBindingVectorFree` at `0x180007c70`
- `RPCRT4!RpcBindingVectorFree` at `0x180007c70`
- `RPCRT4!RpcServerRegisterIf3` at `0x180007c13`
- `RPCRT4!RpcServerRegisterIf3` at `0x180007c13`
- `RPCRT4!RpcServerUseProtseqW` at `0x180007bab`
- `RPCRT4!RpcServerUseProtseqW` at `0x180007bab`
- `RPCRT4!RpcEpRegisterW` at `0x180007c37`
- `RPCRT4!RpcEpRegisterW` at `0x180007c37`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180007c57`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180007c57`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180007b75`
- `api-ms-win-security-accesshlpr-l1-1-0!QueryTransientObjectSecurityDescriptor` at `0x180007b75`

## string_xrefs

- `0x180007b60`: `DefaultRpcAccess`

## pseudocode

```c
__int64 RegisterDmUiRPCInterface(void)
{
  unsigned int v0; // ebx
  RPC_STATUS v1; // eax
  bool v2; // cc
  RPC_BINDING_VECTOR *BindingVector; // [rsp+50h] [rbp+8h] BYREF
  void *SecurityDescriptor; // [rsp+58h] [rbp+10h] BYREF

  BindingVector = 0;
  SecurityDescriptor = 0;
  v0 = QueryTransientObjectSecurityDescriptor(8, L"DefaultRpcAccess", &SecurityDescriptor);
  if ( (int)(v0 + 0x80000000) < 0 || v0 == -1073741772 )
  {
    v1 = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, SecurityDescriptor);
    v0 = v1;
    v2 = v1 <= 0;
    if ( v1 )
      goto LABEL_4;
    v1 = RpcServerInqBindings(&BindingVector);
    v0 = v1;
    v2 = v1 <= 0;
    if ( v1
      || (v1 = RpcServerRegisterIf3(qword_18000C3F0, 0, 0, 41, 1234, 0, 0, 0), v0 = v1, v2 = v1 <= 0, v1)
      || (v1 = RpcEpRegisterW(qword_18000C3F0, BindingVector, 0, 0), v0 = v1, v2 = v1 <= 0, v1) )
    {
LABEL_4:
      if ( !v2 )
        v0 = (unsigned __int16)v1 | 0x80070000;
    }
  }
  if ( SecurityDescriptor )
    FreeTransientObjectSecurityDescriptor();
  if ( BindingVector )
    RpcBindingVectorFree(&BindingVector);
  return v0;
}

```

## disassembly

```asm
0x180007b4c  push    rbx
0x180007b4e  sub     rsp, 40h
0x180007b52  lea     r8, [rsp+48h+SecurityDescriptor]
0x180007b57  mov     [rsp+48h+BindingVector], 0
0x180007b60  lea     rdx, aDefaultrpcacce; "DefaultRpcAccess"
0x180007b67  mov     [rsp+48h+SecurityDescriptor], 0
0x180007b70  mov     ecx, 8
0x180007b75  call    cs:__imp_QueryTransientObjectSecurityDescriptor
0x180007b7c  nop     dword ptr [rax+rax+00h]
0x180007b81  mov     ecx, 80000000h
0x180007b86  mov     ebx, eax
0x180007b88  add     eax, ecx
0x180007b8a  test    ecx, eax
0x180007b8c  jnz     short loc_180007B9A
0x180007b8e  cmp     ebx, 0C0000034h
0x180007b94  jnz     loc_180007C4D
0x180007b9a  mov     r8, [rsp+48h+SecurityDescriptor]; SecurityDescriptor
0x180007b9f  lea     rcx, Protseq; "ncalrpc"
0x180007ba6  mov     edx, 0Ah; MaxCalls
0x180007bab  call    cs:__imp_RpcServerUseProtseqW
0x180007bb2  nop     dword ptr [rax+rax+00h]
0x180007bb7  mov     ebx, eax
0x180007bb9  test    eax, eax
0x180007bbb  jz      short loc_180007BCE
0x180007bbd  jle     loc_180007C4D
0x180007bc3  movzx   ebx, ax
0x180007bc6  or      ebx, 80070000h
0x180007bcc  jmp     short loc_180007C4D
0x180007bce  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x180007bd3  call    cs:__imp_RpcServerInqBindings
0x180007bda  nop     dword ptr [rax+rax+00h]
0x180007bdf  mov     ebx, eax
0x180007be1  test    eax, eax
0x180007be3  jnz     short loc_180007BBD
0x180007be5  mov     [rsp+48h+var_10], 0
0x180007bee  lea     r9d, [rax+29h]
0x180007bf2  mov     [rsp+48h+var_18], 0
0x180007bfb  lea     rcx, qword_18000C3F0
0x180007c02  mov     [rsp+48h+var_20], eax
0x180007c06  xor     r8d, r8d
0x180007c09  xor     edx, edx
0x180007c0b  mov     [rsp+48h+var_28], 4D2h
0x180007c13  call    cs:__imp_RpcServerRegisterIf3
0x180007c1a  nop     dword ptr [rax+rax+00h]
0x180007c1f  mov     ebx, eax
0x180007c21  test    eax, eax
0x180007c23  jnz     short loc_180007BBD
0x180007c25  mov     rdx, [rsp+48h+BindingVector]; BindingVector
0x180007c2a  lea     rcx, qword_18000C3F0; IfSpec
0x180007c31  xor     r9d, r9d; Annotation
0x180007c34  xor     r8d, r8d; UuidVector
0x180007c37  call    cs:__imp_RpcEpRegisterW
0x180007c3e  nop     dword ptr [rax+rax+00h]
0x180007c43  mov     ebx, eax
0x180007c45  test    eax, eax
0x180007c47  jnz     loc_180007BBD
0x180007c4d  mov     rcx, [rsp+48h+SecurityDescriptor]
0x180007c52  test    rcx, rcx
0x180007c55  jz      short loc_180007C63
0x180007c57  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180007c5e  nop     dword ptr [rax+rax+00h]
0x180007c63  cmp     [rsp+48h+BindingVector], 0
0x180007c69  jz      short loc_180007C7C
0x180007c6b  lea     rcx, [rsp+48h+BindingVector]; BindingVector
0x180007c70  call    cs:__imp_RpcBindingVectorFree
0x180007c77  nop     dword ptr [rax+rax+00h]
0x180007c7c  mov     eax, ebx
0x180007c7e  add     rsp, 40h
0x180007c82  pop     rbx
0x180007c83  retn
```
