# NAEnableRpcInterface(void *,ushort const *)

- ea: `0x18001e770`
- end: `0x18001e8ce`
- name: `?NAEnableRpcInterface@@YAKPEAXPEBG@Z`
- size: `350`
- prototype: `__int64 __fastcall(RPC_IF_HANDLE IfSpec, LPCWSTR StringSecurityDescriptor)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800091c0`

## callees

- `0x18001e770`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7b5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7b5`
- `RPCRT4!RpcBindingVectorFree` at `0x18001e7fa`
- `RPCRT4!RpcBindingVectorFree` at `0x18001e7fa`
- `RPCRT4!RpcServerInqBindings` at `0x18001e83a`
- `RPCRT4!RpcServerInqBindings` at `0x18001e83a`
- `RPCRT4!RpcServerRegisterIf3` at `0x18001e878`
- `RPCRT4!RpcServerRegisterIf3` at `0x18001e878`
- `RPCRT4!RpcServerUnregisterIf` at `0x18001e7df`
- `RPCRT4!RpcServerUnregisterIf` at `0x18001e7df`
- `RPCRT4!RpcServerUseProtseqW` at `0x18001e82a`
- `RPCRT4!RpcServerUseProtseqW` at `0x18001e82a`
- `RPCRT4!RpcEpRegisterW` at `0x18001e89c`
- `RPCRT4!RpcEpRegisterW` at `0x18001e89c`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7cc`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001e7cc`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001e7ab`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18001e7ab`

## pseudocode

```c
__int64 __fastcall NAEnableRpcInterface(RPC_IF_HANDLE IfSpec, LPCWSTR StringSecurityDescriptor)
{
  const WCHAR *v3; // rcx
  DWORD LastError; // ebx
  int v5; // edi
  RPC_BINDING_VECTOR *BindingVector; // [rsp+68h] [rbp+28h] BYREF
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+70h] [rbp+30h] BYREF

  BindingVector = 0;
  SecurityDescriptor = 0;
  v3 = L"O:SYD:(A;;GRGWGX;;;SY)";
  if ( StringSecurityDescriptor )
    v3 = StringSecurityDescriptor;
  if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(v3, 1u, &SecurityDescriptor, 0) )
  {
    LastError = GetLastError();
    v5 = 0;
    if ( !LastError )
      return LastError;
    goto LABEL_5;
  }
  v5 = 0;
  if ( g_pBindingVector )
  {
    BindingVector = g_pBindingVector;
  }
  else
  {
    LastError = RpcServerUseProtseqW((RPC_WSTR)L"ncalrpc", 0xAu, 0);
    if ( LastError )
      goto LABEL_5;
    LastError = RpcServerInqBindings(&BindingVector);
    if ( LastError )
      goto LABEL_5;
  }
  LastError = RpcServerRegisterIf3(IfSpec, 0, 0, 41, 1234, 0, 0, SecurityDescriptor);
  if ( LastError
    || (v5 = 1, (LastError = RpcEpRegisterW(IfSpec, BindingVector, 0, (RPC_WSTR)L"NaturalAuthentication")) != 0) )
  {
LABEL_5:
    if ( SecurityDescriptor )
      LocalFree(SecurityDescriptor);
    if ( v5 )
      RpcServerUnregisterIf(IfSpec, 0, 1u);
    if ( BindingVector && !g_pBindingVector )
      RpcBindingVectorFree(&BindingVector);
    return LastError;
  }
  if ( !g_pBindingVector )
    g_pBindingVector = BindingVector;
  BindingVector = 0;
  return LastError;
}

```

## disassembly

```asm
0x18001e770  mov     [rsp-18h+arg_0], rbx
0x18001e775  push    rbp
0x18001e776  push    rsi
0x18001e777  push    rdi
0x18001e778  mov     rbp, rsp
0x18001e77b  sub     rsp, 40h
0x18001e77f  mov     rsi, rcx
0x18001e782  mov     [rbp+BindingVector], 0
0x18001e78a  test    rdx, rdx
0x18001e78d  mov     [rbp+SecurityDescriptor], 0
0x18001e795  lea     rcx, aOSydAGrgwgxSy; "O:SYD:(A;;GRGWGX;;;SY)"
0x18001e79c  cmovnz  rcx, rdx; StringSecurityDescriptor
0x18001e7a0  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18001e7a4  xor     r9d, r9d; SecurityDescriptorSize
0x18001e7a7  lea     edx, [r9+1]; StringSDRevision
0x18001e7ab  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18001e7b1  test    eax, eax
0x18001e7b3  jnz     short loc_18001E80F
0x18001e7b5  call    cs:__imp_GetLastError
0x18001e7bb  mov     ebx, eax
0x18001e7bd  xor     edi, edi
0x18001e7bf  test    eax, eax
0x18001e7c1  jz      short loc_18001E800
0x18001e7c3  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18001e7c7  test    rcx, rcx
0x18001e7ca  jz      short loc_18001E7D2
0x18001e7cc  call    cs:__imp_LocalFree
0x18001e7d2  test    edi, edi
0x18001e7d4  jz      short loc_18001E7E5
0x18001e7d6  xor     edx, edx; MgrTypeUuid
0x18001e7d8  mov     rcx, rsi; IfSpec
0x18001e7db  lea     r8d, [rdx+1]; WaitForCallsToComplete
0x18001e7df  call    cs:__imp_RpcServerUnregisterIf
0x18001e7e5  cmp     [rbp+BindingVector], 0
0x18001e7ea  jz      short loc_18001E800
0x18001e7ec  cmp     cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA, 0; _RPC_BINDING_VECTOR * g_pBindingVector
0x18001e7f4  jnz     short loc_18001E800
0x18001e7f6  lea     rcx, [rbp+BindingVector]; BindingVector
0x18001e7fa  call    cs:__imp_RpcBindingVectorFree
0x18001e800  mov     eax, ebx
0x18001e802  mov     rbx, [rsp+40h+arg_0]
0x18001e807  add     rsp, 40h
0x18001e80b  pop     rdi
0x18001e80c  pop     rsi
0x18001e80d  pop     rbp
0x18001e80e  retn
0x18001e80f  mov     rax, cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA; _RPC_BINDING_VECTOR * g_pBindingVector
0x18001e816  xor     edi, edi
0x18001e818  test    rax, rax
0x18001e81b  jnz     short loc_18001E84C
0x18001e81d  xor     r8d, r8d; SecurityDescriptor
0x18001e820  lea     edx, [rdi+0Ah]; MaxCalls
0x18001e823  lea     rcx, Protseq; "ncalrpc"
0x18001e82a  call    cs:__imp_RpcServerUseProtseqW
0x18001e830  mov     ebx, eax
0x18001e832  test    eax, eax
0x18001e834  jnz     short loc_18001E7C3
0x18001e836  lea     rcx, [rbp+BindingVector]; BindingVector
0x18001e83a  call    cs:__imp_RpcServerInqBindings
0x18001e840  mov     ebx, eax
0x18001e842  test    eax, eax
0x18001e844  jnz     loc_18001E7C3
0x18001e84a  jmp     short loc_18001E850
0x18001e84c  mov     [rbp+BindingVector], rax
0x18001e850  mov     rax, [rbp+SecurityDescriptor]
0x18001e854  mov     r9d, 29h ; ')'
0x18001e85a  mov     [rsp+40h+var_8], rax
0x18001e85f  xor     r8d, r8d
0x18001e862  mov     [rsp+40h+var_10], rdi
0x18001e867  xor     edx, edx
0x18001e869  mov     [rsp+40h+var_18], edi
0x18001e86d  mov     rcx, rsi
0x18001e870  mov     [rsp+40h+var_20], 4D2h
0x18001e878  call    cs:__imp_RpcServerRegisterIf3
0x18001e87e  mov     ebx, eax
0x18001e880  test    eax, eax
0x18001e882  jnz     loc_18001E7C3
0x18001e888  mov     rdx, [rbp+BindingVector]; BindingVector
0x18001e88c  lea     r9, Annotation; "NaturalAuthentication"
0x18001e893  xor     r8d, r8d; UuidVector
0x18001e896  lea     edi, [rax+1]
0x18001e899  mov     rcx, rsi; IfSpec
0x18001e89c  call    cs:__imp_RpcEpRegisterW
0x18001e8a2  mov     ebx, eax
0x18001e8a4  test    eax, eax
0x18001e8a6  jnz     loc_18001E7C3
0x18001e8ac  cmp     cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA, 0; _RPC_BINDING_VECTOR * g_pBindingVector
0x18001e8b4  jnz     short loc_18001E8C1
0x18001e8b6  mov     rax, [rbp+BindingVector]
0x18001e8ba  mov     cs:?g_pBindingVector@@3PEAU_RPC_BINDING_VECTOR@@EA, rax; _RPC_BINDING_VECTOR * g_pBindingVector
0x18001e8c1  mov     [rbp+BindingVector], 0
0x18001e8c9  jmp     loc_18001E800
```
