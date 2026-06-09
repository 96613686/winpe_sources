# BfeRpcInterfaceCreate

- ea: `0x180031f70`
- end: `0x180032191`
- name: `BfeRpcInterfaceCreate`
- size: `545`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003f8d0`

## callees

- `0x180012d8c`
- `0x1800197d0`
- `0x180031210`
- `0x180031f70`
- `0x18005aa60`
- `0x180067ad8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180032019`
- `RPCRT4!RpcServerUseProtseqW` at `0x18003206e`
- `RPCRT4!RpcServerUseProtseqW` at `0x18003206e`
- `RPCRT4!RpcServerInqBindings` at `0x1800320ea`
- `RPCRT4!RpcServerInqBindings` at `0x1800320ea`
- `RPCRT4!RpcEpRegisterW` at `0x18003211a`
- `RPCRT4!RpcEpRegisterW` at `0x18003211a`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800320bd`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800320bd`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003214a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003214a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032009`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180032009`

## string_xrefs

- `0x180032029`: `ConvertStringSecurityDescriptorToSecurityDescriptorA`
- `0x180032160`: `BfeRpcInterfaceCreate`

## pseudocode

```c
__int64 BfeRpcInterfaceCreate()
{
  __int64 v0; // rbx
  DWORD LastError; // eax
  __int64 v2; // rcx
  const char *v3; // rdx
  __int64 i; // rdi
  PSECURITY_DESCRIPTOR v5; // r8
  __int64 v6; // rcx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+40h] [rbp-18h] BYREF

  SecurityDescriptor = 0;
  *(_OWORD *)&gBfeRpcIntfc = 0;
  *((_DWORD *)&gBfeRpcIntfc + 2) = 0;
  gBfeRpcIntfc = qword_180091270;
  xmmword_1800F60F0 = 0;
  *(_OWORD *)&BindingVector = 0;
  v0 = WfpBufferCopy(&dword_1800B7B04, 4u);
  if ( !v0 )
  {
    *(_QWORD *)&xmmword_1800F60F0 = 1;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;GA;;;BA)(A;;GA;;;OW)(A;;GR;;;AC)",
            1u,
            &SecurityDescriptor,
            0) )
    {
      LastError = GetLastError();
      if ( LastError )
      {
        v3 = "ConvertStringSecurityDescriptorToSecurityDescriptorA";
LABEL_5:
        v0 = WfpReportSysErrorAsWinError(v2, v3, LastError);
        goto LABEL_20;
      }
    }
    for ( i = 0; ; i = 1 )
    {
      v5 = 0;
      if ( i )
        break;
      v6 = (unsigned int)**((_DWORD **)&xmmword_1800F60F0 + 1);
      if ( (_DWORD)v6 == 3 )
        v5 = SecurityDescriptor;
      LastError = RpcServerUseProtseqW((RPC_WSTR)qword_1800A6BC8[v6], 0xAu, v5);
      if ( LastError )
      {
        v3 = "RpcServerUseProtseqW";
        goto LABEL_5;
      }
    }
    LastError = RpcServerRegisterIf3(qword_180091270, 0, 0, 41, 1234, 0, BfeRpcSecurityCallback, SecurityDescriptor);
    if ( LastError )
    {
      v3 = "RpcServerRegisterIfEx";
      goto LABEL_5;
    }
    *((_DWORD *)&BindingVector + 3) = 1;
    LastError = RpcServerInqBindings(&BindingVector);
    if ( LastError )
    {
      v3 = "RpcServerInqBindings";
      goto LABEL_5;
    }
    LastError = RpcEpRegisterW(qword_180091270, BindingVector, 0, (RPC_WSTR)L"Base Firewall Engine API");
    if ( LastError )
    {
      v3 = "RpcEpRegisterW";
      goto LABEL_5;
    }
    *((_DWORD *)&BindingVector + 2) = 1;
  }
LABEL_20:
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  if ( v0 )
  {
    BfeRpcInterfaceDestroy();
    WfpReportError(v0, "BfeRpcInterfaceCreate");
  }
  return v0;
}

```

## disassembly

```asm
0x180031f70  mov     [rsp+arg_0], rbx
0x180031f75  mov     [rsp+arg_8], rdi
0x180031f7a  push    r14
0x180031f7c  sub     rsp, 50h
0x180031f80  mov     rax, cs:__security_cookie
0x180031f87  xor     rax, rsp
0x180031f8a  mov     [rsp+58h+var_10], rax
0x180031f8f  xorps   xmm0, xmm0
0x180031f92  mov     [rsp+58h+SecurityDescriptor], 0
0x180031f9b  movups  cs:gBfeRpcIntfc, xmm0
0x180031fa2  lea     r14, qword_180091270
0x180031fa9  mov     dword ptr cs:gBfeRpcIntfc+8, 0
0x180031fb3  lea     r9, xmmword_1800F60F0+8
0x180031fba  mov     qword ptr cs:gBfeRpcIntfc, r14
0x180031fc1  mov     edx, 4; dwBytes
0x180031fc6  lea     rcx, dword_1800B7B04; Src
0x180031fcd  movups  cs:xmmword_1800F60F0, xmm0
0x180031fd4  movups  cs:BindingVector, xmm0
0x180031fdb  call    WfpBufferCopy
0x180031fe0  mov     rbx, rax
0x180031fe3  test    rax, rax
0x180031fe6  jnz     loc_180032140
0x180031fec  xor     r9d, r9d; SecurityDescriptorSize
0x180031fef  mov     qword ptr cs:xmmword_1800F60F0, 1
0x180031ffa  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x180031fff  lea     edx, [rax+1]; StringSDRevision
0x180032002  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x180032009  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180032010  nop     dword ptr [rax+rax+00h]
0x180032015  test    eax, eax
0x180032017  jnz     short loc_180032040
0x180032019  call    cs:__imp_GetLastError
0x180032020  nop     dword ptr [rax+rax+00h]
0x180032025  test    eax, eax
0x180032027  jz      short loc_180032040
0x180032029  lea     rdx, aConvertstrings_1; "ConvertStringSecurityDescriptorToSecuri"...
0x180032030  mov     r8d, eax
0x180032033  call    WfpReportSysErrorAsWinError
0x180032038  mov     rbx, rax
0x18003203b  jmp     loc_180032140
0x180032040  xor     edi, edi
0x180032042  xor     r8d, r8d
0x180032045  cmp     rdi, 1
0x180032049  jnb     short loc_18003208C
0x18003204b  mov     rax, qword ptr cs:xmmword_1800F60F0+8
0x180032052  mov     edx, 0Ah; MaxCalls
0x180032057  mov     ecx, [rax+rdi*4]
0x18003205a  lea     rax, qword_1800A6BC8
0x180032061  cmp     ecx, 3
0x180032064  cmovz   r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x18003206a  mov     rcx, [rax+rcx*8]; Protseq
0x18003206e  call    cs:__imp_RpcServerUseProtseqW
0x180032075  nop     dword ptr [rax+rax+00h]
0x18003207a  test    eax, eax
0x18003207c  jnz     short loc_180032083
0x18003207e  inc     rdi
0x180032081  jmp     short loc_180032042
0x180032083  lea     rdx, aRpcserverusepr; "RpcServerUseProtseqW"
0x18003208a  jmp     short loc_180032030
0x18003208c  mov     rax, [rsp+58h+SecurityDescriptor]
0x180032091  mov     r9d, 29h ; ')'
0x180032097  mov     [rsp+58h+var_20], rax
0x18003209c  xor     edx, edx
0x18003209e  lea     rax, BfeRpcSecurityCallback
0x1800320a5  mov     rcx, r14
0x1800320a8  mov     [rsp+58h+var_28], rax
0x1800320ad  mov     [rsp+58h+var_30], 0
0x1800320b5  mov     [rsp+58h+var_38], 4D2h
0x1800320bd  call    cs:__imp_RpcServerRegisterIf3
0x1800320c4  nop     dword ptr [rax+rax+00h]
0x1800320c9  test    eax, eax
0x1800320cb  jz      short loc_1800320D9
0x1800320cd  lea     rdx, aRpcserverregis; "RpcServerRegisterIfEx"
0x1800320d4  jmp     loc_180032030
0x1800320d9  lea     rcx, BindingVector; BindingVector
0x1800320e0  mov     dword ptr cs:BindingVector+0Ch, 1
0x1800320ea  call    cs:__imp_RpcServerInqBindings
0x1800320f1  nop     dword ptr [rax+rax+00h]
0x1800320f6  test    eax, eax
0x1800320f8  jz      short loc_180032106
0x1800320fa  lea     rdx, aRpcserverinqbi; "RpcServerInqBindings"
0x180032101  jmp     loc_180032030
0x180032106  mov     rdx, qword ptr cs:BindingVector; BindingVector
0x18003210d  lea     r9, Annotation; "Base Firewall Engine API"
0x180032114  xor     r8d, r8d; UuidVector
0x180032117  mov     rcx, r14; IfSpec
0x18003211a  call    cs:__imp_RpcEpRegisterW
0x180032121  nop     dword ptr [rax+rax+00h]
0x180032126  test    eax, eax
0x180032128  jz      short loc_180032136
0x18003212a  lea     rdx, aRpcepregisterw; "RpcEpRegisterW"
0x180032131  jmp     loc_180032030
0x180032136  mov     dword ptr cs:BindingVector+8, 1
0x180032140  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x180032145  test    rcx, rcx
0x180032148  jz      short loc_180032156
0x18003214a  call    cs:__imp_LocalFree
0x180032151  nop     dword ptr [rax+rax+00h]
0x180032156  test    rbx, rbx
0x180032159  jz      short loc_18003216F
0x18003215b  call    BfeRpcInterfaceDestroy
0x180032160  lea     rdx, aBferpcinterfac; "BfeRpcInterfaceCreate"
0x180032167  mov     rcx, rbx
0x18003216a  call    WfpReportError
0x18003216f  mov     rax, rbx
0x180032172  mov     rcx, [rsp+58h+var_10]
0x180032177  xor     rcx, rsp; StackCookie
0x18003217a  call    __security_check_cookie
0x18003217f  mov     rbx, [rsp+58h+arg_0]
0x180032184  mov     rdi, [rsp+58h+arg_8]
0x180032189  add     rsp, 50h
0x18003218d  pop     r14
0x18003218f  retn
```
