# BfeRpcInterfaceCreate

- ea: `0x180030688`
- end: `0x18003087e`
- name: `BfeRpcInterfaceCreate`
- size: `502`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003e660`

## callees

- `0x18001236c`
- `0x180018b74`
- `0x18002f724`
- `0x180030688`
- `0x180058b30`
- `0x180065628`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003072b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003072b`
- `RPCRT4!RpcServerUseProtseqW` at `0x18003077a`
- `RPCRT4!RpcServerUseProtseqW` at `0x18003077a`
- `RPCRT4!RpcServerInqBindings` at `0x1800307ea`
- `RPCRT4!RpcServerInqBindings` at `0x1800307ea`
- `RPCRT4!RpcEpRegisterW` at `0x180030814`
- `RPCRT4!RpcEpRegisterW` at `0x180030814`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800307c3`
- `RPCRT4!RpcServerRegisterIf3` at `0x1800307c3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003083e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18003083e`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180030721`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180030721`

## string_xrefs

- `0x180030735`: `ConvertStringSecurityDescriptorToSecurityDescriptorA`
- `0x18003084e`: `BfeRpcInterfaceCreate`

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
  gBfeRpcIntfc = qword_18008E270;
  xmmword_1800F30D0 = 0;
  *(_OWORD *)&BindingVector = 0;
  v0 = WfpBufferCopy(&dword_1800B4BD4, 4u);
  if ( !v0 )
  {
    *(_QWORD *)&xmmword_1800F30D0 = 1;
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
      v6 = (unsigned int)**((_DWORD **)&xmmword_1800F30D0 + 1);
      if ( (_DWORD)v6 == 3 )
        v5 = SecurityDescriptor;
      LastError = RpcServerUseProtseqW((RPC_WSTR)qword_1800A3BD0[v6], 0xAu, v5);
      if ( LastError )
      {
        v3 = "RpcServerUseProtseqW";
        goto LABEL_5;
      }
    }
    LastError = RpcServerRegisterIf3(qword_18008E270, 0, 0, 41, 1234, 0, BfeRpcSecurityCallback, SecurityDescriptor);
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
    LastError = RpcEpRegisterW(qword_18008E270, BindingVector, 0, (RPC_WSTR)L"Base Firewall Engine API");
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
0x180030688  mov     [rsp+arg_0], rbx
0x18003068d  mov     [rsp+arg_8], rdi
0x180030692  push    r14
0x180030694  sub     rsp, 50h
0x180030698  mov     rax, cs:__security_cookie
0x18003069f  xor     rax, rsp
0x1800306a2  mov     [rsp+58h+var_10], rax
0x1800306a7  xorps   xmm0, xmm0
0x1800306aa  mov     [rsp+58h+SecurityDescriptor], 0
0x1800306b3  movups  cs:gBfeRpcIntfc, xmm0
0x1800306ba  lea     r14, qword_18008E270
0x1800306c1  mov     dword ptr cs:gBfeRpcIntfc+8, 0
0x1800306cb  lea     r9, xmmword_1800F30D0+8
0x1800306d2  mov     qword ptr cs:gBfeRpcIntfc, r14
0x1800306d9  mov     edx, 4; dwBytes
0x1800306de  lea     rcx, dword_1800B4BD4; Src
0x1800306e5  movups  cs:xmmword_1800F30D0, xmm0
0x1800306ec  movups  cs:BindingVector, xmm0
0x1800306f3  call    WfpBufferCopy
0x1800306f8  mov     rbx, rax
0x1800306fb  test    rax, rax
0x1800306fe  jnz     loc_180030834
0x180030704  xor     r9d, r9d; SecurityDescriptorSize
0x180030707  mov     qword ptr cs:xmmword_1800F30D0, 1
0x180030712  lea     r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x180030717  lea     edx, [rax+1]; StringSDRevision
0x18003071a  lea     rcx, aDAGrgwgxWdAGrg; "D:(A;;GRGWGX;;;WD)(A;;GRGWGX;;;RC)(A;;G"...
0x180030721  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180030727  test    eax, eax
0x180030729  jnz     short loc_18003074C
0x18003072b  call    cs:__imp_GetLastError
0x180030731  test    eax, eax
0x180030733  jz      short loc_18003074C
0x180030735  lea     rdx, aConvertstrings_1; "ConvertStringSecurityDescriptorToSecuri"...
0x18003073c  mov     r8d, eax
0x18003073f  call    WfpReportSysErrorAsWinError
0x180030744  mov     rbx, rax
0x180030747  jmp     loc_180030834
0x18003074c  xor     edi, edi
0x18003074e  xor     r8d, r8d
0x180030751  cmp     rdi, 1
0x180030755  jnb     short loc_180030792
0x180030757  mov     rax, qword ptr cs:xmmword_1800F30D0+8
0x18003075e  mov     edx, 0Ah; MaxCalls
0x180030763  mov     ecx, [rax+rdi*4]
0x180030766  lea     rax, qword_1800A3BD0
0x18003076d  cmp     ecx, 3
0x180030770  cmovz   r8, [rsp+58h+SecurityDescriptor]; SecurityDescriptor
0x180030776  mov     rcx, [rax+rcx*8]; Protseq
0x18003077a  call    cs:__imp_RpcServerUseProtseqW
0x180030780  test    eax, eax
0x180030782  jnz     short loc_180030789
0x180030784  inc     rdi
0x180030787  jmp     short loc_18003074E
0x180030789  lea     rdx, aRpcserverusepr; "RpcServerUseProtseqW"
0x180030790  jmp     short loc_18003073C
0x180030792  mov     rax, [rsp+58h+SecurityDescriptor]
0x180030797  mov     r9d, 29h ; ')'
0x18003079d  mov     [rsp+58h+var_20], rax
0x1800307a2  xor     edx, edx
0x1800307a4  lea     rax, BfeRpcSecurityCallback
0x1800307ab  mov     rcx, r14
0x1800307ae  mov     [rsp+58h+var_28], rax
0x1800307b3  mov     [rsp+58h+var_30], 0
0x1800307bb  mov     [rsp+58h+var_38], 4D2h
0x1800307c3  call    cs:__imp_RpcServerRegisterIf3
0x1800307c9  test    eax, eax
0x1800307cb  jz      short loc_1800307D9
0x1800307cd  lea     rdx, aRpcserverregis; "RpcServerRegisterIfEx"
0x1800307d4  jmp     loc_18003073C
0x1800307d9  lea     rcx, BindingVector; BindingVector
0x1800307e0  mov     dword ptr cs:BindingVector+0Ch, 1
0x1800307ea  call    cs:__imp_RpcServerInqBindings
0x1800307f0  test    eax, eax
0x1800307f2  jz      short loc_180030800
0x1800307f4  lea     rdx, aRpcserverinqbi; "RpcServerInqBindings"
0x1800307fb  jmp     loc_18003073C
0x180030800  mov     rdx, qword ptr cs:BindingVector; BindingVector
0x180030807  lea     r9, Annotation; "Base Firewall Engine API"
0x18003080e  xor     r8d, r8d; UuidVector
0x180030811  mov     rcx, r14; IfSpec
0x180030814  call    cs:__imp_RpcEpRegisterW
0x18003081a  test    eax, eax
0x18003081c  jz      short loc_18003082A
0x18003081e  lea     rdx, aRpcepregisterw; "RpcEpRegisterW"
0x180030825  jmp     loc_18003073C
0x18003082a  mov     dword ptr cs:BindingVector+8, 1
0x180030834  mov     rcx, [rsp+58h+SecurityDescriptor]; hMem
0x180030839  test    rcx, rcx
0x18003083c  jz      short loc_180030844
0x18003083e  call    cs:__imp_LocalFree
0x180030844  test    rbx, rbx
0x180030847  jz      short loc_18003085D
0x180030849  call    BfeRpcInterfaceDestroy
0x18003084e  lea     rdx, aBferpcinterfac; "BfeRpcInterfaceCreate"
0x180030855  mov     rcx, rbx
0x180030858  call    WfpReportError
0x18003085d  mov     rax, rbx
0x180030860  mov     rcx, [rsp+58h+var_10]
0x180030865  xor     rcx, rsp; StackCookie
0x180030868  call    __security_check_cookie
0x18003086d  mov     rbx, [rsp+58h+arg_0]
0x180030872  mov     rdi, [rsp+58h+arg_8]
0x180030877  add     rsp, 50h
0x18003087b  pop     r14
0x18003087d  retn
```
