# IkeAuthzAccessCheck

- ea: `0x1800ec38c`
- end: `0x1800ec4d1`
- name: `IkeAuthzAccessCheck`
- size: `325`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64, DWORD)`
- caller_count: `9`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006e8d0`
- `0x18006ea70`
- `0x18006ec50`
- `0x18006f0b0`
- `0x18006f400`
- `0x18006f4b0`
- `0x1800ec1fc`
- `0x1800ec660`
- `0x1800ec7c4`

## callees

- `0x1800061ec`
- `0x180008388`
- `0x18004aa3c`
- `0x180050850`
- `0x1800ec38c`
- `0x1800ec5cc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec463`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ec463`
- `AUTHZ!AuthzAccessCheck` at `0x1800ec459`
- `AUTHZ!AuthzAccessCheck` at `0x1800ec459`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800ec40d`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800ec40d`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x1800ec497`
- `RPCRT4!RpcFreeAuthorizationContext` at `0x1800ec497`

## string_xrefs

- `0x1800ec3ce`: `IkeAuthzAccessCheck`
- `0x1800ec49f`: `IkeAuthzAccessCheck`
- `0x1800ec4ab`: `IkeAuthzAccessCheck`
- `0x1800ec47d`: `AuthzAccessCheck`

## pseudocode

```c
__int64 __fastcall IkeAuthzAccessCheck(PSECURITY_DESCRIPTOR pSecurityDescriptor, __int64 a2, DWORD a3)
{
  __int64 AuthzContextFromRpcClientBinding; // rbx
  __int64 v6; // rcx
  __int64 LastError; // r8
  unsigned int v9; // [rsp+50h] [rbp-39h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+58h] [rbp-31h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+60h] [rbp-29h] BYREF
  DWORD AccessMask[4]; // [rsp+80h] [rbp-9h] BYREF
  int v13; // [rsp+90h] [rbp+7h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+98h] [rbp+Fh] BYREF

  AccessMask[0] = a3;
  v13 = 0;
  v9 = 5;
  hAuthzClientContext = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  memset(&pReply, 0, sizeof(pReply));
  TraceLogHelper("IkeAuthzAccessCheck", 1);
  AuthzContextFromRpcClientBinding = IkeGetAuthzContextFromRpcClientBinding(a2, &hAuthzClientContext);
  if ( !AuthzContextFromRpcClientBinding )
  {
    MapGenericMask(AccessMask, (PGENERIC_MAPPING)&IKE_GENERIC_MAPPING);
    pReply.GrantedAccessMask = (PACCESS_MASK)&v13;
    pReply.Error = &v9;
    pRequest.DesiredAccess = AccessMask[0];
    pReply.ResultListLength = 1;
    if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
    {
      LastError = v9;
      if ( !v9 )
        goto LABEL_6;
    }
    else
    {
      LastError = GetLastError();
    }
    AuthzContextFromRpcClientBinding = WfpReportSysErrorAsWinError(v6, "AuthzAccessCheck", LastError, 1);
  }
LABEL_6:
  if ( hAuthzClientContext )
    RpcFreeAuthorizationContext((PVOID *)&hAuthzClientContext);
  TraceLogHelper("IkeAuthzAccessCheck", 0);
  return IkeReturnError(AuthzContextFromRpcClientBinding, "IkeAuthzAccessCheck");
}

```

## disassembly

```asm
0x1800ec38c  push    rbp
0x1800ec38e  push    rbx
0x1800ec38f  push    rdi
0x1800ec390  lea     rbp, [rsp-47h]
0x1800ec395  sub     rsp, 0D0h
0x1800ec39c  mov     rax, cs:__security_cookie
0x1800ec3a3  xor     rax, rsp
0x1800ec3a6  mov     [rbp+57h+var_20], rax
0x1800ec3aa  xor     eax, eax
0x1800ec3ac  mov     [rbp+57h+AccessMask], r8d
0x1800ec3b0  xorps   xmm0, xmm0
0x1800ec3b3  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x1800ec3b7  mov     rbx, rdx
0x1800ec3ba  mov     [rbp+57h+var_50], eax
0x1800ec3bd  mov     rdi, rcx
0x1800ec3c0  mov     [rbp+57h+var_90], 5
0x1800ec3c7  lea     edx, [rax+1]
0x1800ec3ca  mov     [rbp+57h+hAuthzClientContext], rax
0x1800ec3ce  lea     rcx, aIkeauthzaccess; "IkeAuthzAccessCheck"
0x1800ec3d5  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x1800ec3d9  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x1800ec3dd  movups  xmmword ptr [rbp+57h+var_80.ResultListLength], xmm0
0x1800ec3e1  movups  xmmword ptr [rbp+57h+var_80.SaclEvaluationResults], xmm0
0x1800ec3e5  call    TraceLogHelper
0x1800ec3ea  lea     rdx, [rbp+57h+hAuthzClientContext]
0x1800ec3ee  mov     rcx, rbx
0x1800ec3f1  call    IkeGetAuthzContextFromRpcClientBinding
0x1800ec3f6  mov     rbx, rax
0x1800ec3f9  test    rax, rax
0x1800ec3fc  jnz     loc_1800EC48C
0x1800ec402  lea     rdx, IKE_GENERIC_MAPPING; GenericMapping
0x1800ec409  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x1800ec40d  call    cs:__imp_MapGenericMask
0x1800ec413  mov     ecx, [rbp+57h+AccessMask]
0x1800ec416  lea     rax, [rbp+57h+var_50]
0x1800ec41a  mov     rdx, [rbp+57h+hAuthzClientContext]; hAuthzClientContext
0x1800ec41e  lea     r8, [rbp+57h+pRequest]; pRequest
0x1800ec422  mov     [rsp+0E0h+phAccessCheckResults], rbx; phAccessCheckResults
0x1800ec427  xor     r9d, r9d; hAuditEvent
0x1800ec42a  mov     [rbp+57h+var_80.GrantedAccessMask], rax
0x1800ec42e  lea     rax, [rbp+57h+var_90]
0x1800ec432  mov     [rbp+57h+var_80.Error], rax
0x1800ec436  lea     rax, [rbp+57h+var_80]
0x1800ec43a  mov     [rsp+0E0h+pReply], rax; pReply
0x1800ec43f  mov     [rsp+0E0h+OptionalSecurityDescriptorCount], ebx; OptionalSecurityDescriptorCount
0x1800ec443  mov     [rbp+57h+pRequest.DesiredAccess], ecx
0x1800ec446  xor     ecx, ecx; Flags
0x1800ec448  mov     [rsp+0E0h+OptionalSecurityDescriptorArray], rbx; OptionalSecurityDescriptorArray
0x1800ec44d  mov     [rsp+0E0h+pSecurityDescriptor], rdi; pSecurityDescriptor
0x1800ec452  mov     [rbp+57h+var_80.ResultListLength], 1
0x1800ec459  call    cs:__imp_AuthzAccessCheck
0x1800ec45f  test    eax, eax
0x1800ec461  jnz     short loc_1800EC46E
0x1800ec463  call    cs:__imp_GetLastError
0x1800ec469  mov     r8d, eax
0x1800ec46c  jmp     short loc_1800EC477
0x1800ec46e  mov     r8d, [rbp+57h+var_90]
0x1800ec472  test    r8d, r8d
0x1800ec475  jz      short loc_1800EC48C
0x1800ec477  mov     r9d, 1
0x1800ec47d  lea     rdx, aAuthzaccessche; "AuthzAccessCheck"
0x1800ec484  call    WfpReportSysErrorAsWinError
0x1800ec489  mov     rbx, rax
0x1800ec48c  cmp     [rbp+57h+hAuthzClientContext], 0
0x1800ec491  jz      short loc_1800EC49D
0x1800ec493  lea     rcx, [rbp+57h+hAuthzClientContext]; pAuthzClientContext
0x1800ec497  call    cs:__imp_RpcFreeAuthorizationContext
0x1800ec49d  xor     edx, edx
0x1800ec49f  lea     rcx, aIkeauthzaccess; "IkeAuthzAccessCheck"
0x1800ec4a6  call    TraceLogHelper
0x1800ec4ab  lea     rdx, aIkeauthzaccess; "IkeAuthzAccessCheck"
0x1800ec4b2  mov     rcx, rbx
0x1800ec4b5  call    IkeReturnError
0x1800ec4ba  mov     rcx, [rbp+57h+var_20]
0x1800ec4be  xor     rcx, rsp; StackCookie
0x1800ec4c1  call    __security_check_cookie
0x1800ec4c6  add     rsp, 0D0h
0x1800ec4cd  pop     rdi
0x1800ec4ce  pop     rbx
0x1800ec4cf  pop     rbp
0x1800ec4d0  retn
```
