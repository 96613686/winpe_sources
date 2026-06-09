# BfeEngineOpenAccessCheckFromContext

- ea: `0x18003592c`
- end: `0x180035b9e`
- name: `BfeEngineOpenAccessCheckFromContext`
- size: `626`
- prototype: `__int64 __fastcall(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004cce8`

## callees

- `0x18000fb34`
- `0x180011510`
- `0x180012d8c`
- `0x1800197d0`
- `0x18002cd80`
- `0x18003592c`
- `0x18005aa60`
- `0x18005b4fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035956`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180035956`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035b0e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180035b0e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a90`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180035a90`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18003597e`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x18003597e`
- `AUTHZ!AuthzAccessCheck` at `0x180035a3a`
- `AUTHZ!AuthzAccessCheck` at `0x180035a3a`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800359d8`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x1800359d8`

## string_xrefs

- `0x180035ac1`: `BfeAccessCheckFromContext`
- `0x180035a9f`: `AuthzAccessCheck`
- `0x180035b8d`: `BfeEngineOpenAccessCheckFromContext`

## pseudocode

```c
__int64 __fastcall BfeEngineOpenAccessCheckFromContext(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext)
{
  __int64 v2; // rbx
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // rbx
  BOOL v4; // eax
  __int64 v5; // rax
  DWORD LastError; // eax
  __int64 v7; // rcx
  int v8; // r8d
  int v10; // [rsp+50h] [rbp-B0h] BYREF
  int v11; // [rsp+58h] [rbp-A8h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+60h] [rbp-A0h] BYREF
  DWORD AccessMask; // [rsp+80h] [rbp-80h] BYREF
  int v14; // [rsp+88h] [rbp-78h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+90h] [rbp-70h] BYREF
  int RpcCallAttributes; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE v17[48]; // [rsp+C4h] [rbp-3Ch] BYREF
  int v18; // [rsp+F4h] [rbp-Ch]
  _BYTE v19[16]; // [rsp+130h] [rbp+30h] BYREF
  const char *v20; // [rsp+140h] [rbp+40h]
  __int64 v21; // [rsp+148h] [rbp+48h]
  int *v22; // [rsp+150h] [rbp+50h]
  __int64 v23; // [rsp+158h] [rbp+58h]

  EnterCriticalSection(&gBfeAuthz);
  memset_0(v17, 0, 0x6Cu);
  RpcCallAttributes = 2;
  if ( RpcServerInqCallAttributesW(0, &RpcCallAttributes) || (v2 = 0, !v18) )
  {
    pSecurityDescriptor = ParentDescriptor;
    AccessMask = 64;
    v11 = 5;
    memset(&pRequest, 0, sizeof(pRequest));
    v14 = 0;
    *(&pReply.ResultListLength + 1) = 0;
    pReply.SaclEvaluationResults = 0;
    MapGenericMask(&AccessMask, (PGENERIC_MAPPING)&GenericMapping);
    pRequest.DesiredAccess = AccessMask;
    pReply.GrantedAccessMask = (PACCESS_MASK)&v14;
    pReply.ResultListLength = 1;
    pReply.Error = (PDWORD)&v11;
    if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
    {
      v4 = v11 == 0;
      v2 = 0;
    }
    else
    {
      LastError = GetLastError();
      v2 = WfpReportSysErrorAsWinError(v7, "AuthzAccessCheck", LastError);
      if ( v2 )
      {
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        {
          WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v8, 0, (__int64)"BfeAccessCheckFromContext", v2);
        }
        if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
        {
          v10 = v2;
          v22 = &v10;
          v20 = "BfeAccessCheckFromContext";
          v21 = 26;
          v23 = 4;
          McGenEventWrite_EtwEventWriteTransfer(
            (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
            (unsigned int)WFP_USERMODE_ERROR,
            v8,
            3,
            (__int64)v19);
          goto LABEL_15;
        }
      }
      v4 = 0;
      if ( v2 )
        goto LABEL_15;
    }
    if ( !v4 )
    {
      v5 = BfeAccessCheckFromContext(hAuthzClientContext, SecurityDescriptor, 1u, 0);
      v2 = v5;
      if ( v5 )
        WfpReportError(v5, "BfeIsAdminContext");
    }
  }
LABEL_15:
  LeaveCriticalSection(&gBfeAuthz);
  if ( v2 )
    WfpReportError(v2, "BfeEngineOpenAccessCheckFromContext");
  return v2;
}

```

## disassembly

```asm
0x18003592c  push    rbp
0x18003592e  push    rbx
0x18003592f  push    rdi
0x180035930  push    r12
0x180035932  lea     rbp, [rsp-78h]
0x180035937  sub     rsp, 178h
0x18003593e  mov     rax, cs:__security_cookie
0x180035945  xor     rax, rsp
0x180035948  mov     [rbp+90h+var_30], rax
0x18003594c  mov     rdi, rcx
0x18003594f  lea     rcx, gBfeAuthz; lpCriticalSection
0x180035956  call    cs:__imp_EnterCriticalSection
0x18003595d  nop     dword ptr [rax+rax+00h]
0x180035962  xor     edx, edx; Val
0x180035964  lea     rcx, [rbp+90h+var_CC]; void *
0x180035968  lea     r8d, [rdx+6Ch]; Size
0x18003596c  call    memset_0
0x180035971  lea     rdx, [rbp+90h+RpcCallAttributes]; RpcCallAttributes
0x180035975  mov     [rbp+90h+RpcCallAttributes], 2
0x18003597c  xor     ecx, ecx; ClientBinding
0x18003597e  call    cs:__imp_RpcServerInqCallAttributesW
0x180035985  nop     dword ptr [rax+rax+00h]
0x18003598a  test    eax, eax
0x18003598c  jnz     short loc_180035999
0x18003598e  xor     ebx, ebx
0x180035990  cmp     [rbp+90h+var_9C], ebx
0x180035993  jnz     loc_180035B07
0x180035999  mov     rbx, cs:ParentDescriptor
0x1800359a0  lea     rdx, GenericMapping; GenericMapping
0x1800359a7  xorps   xmm0, xmm0
0x1800359aa  mov     [rbp+90h+AccessMask], 40h ; '@'
0x1800359b1  xor     eax, eax
0x1800359b3  mov     [rsp+190h+var_138], 5
0x1800359bb  lea     rcx, [rbp+90h+AccessMask]; AccessMask
0x1800359bf  mov     [rbp+90h+pRequest.OptionalArguments], rax
0x1800359c3  movups  xmmword ptr [rbp+90h+pRequest.DesiredAccess], xmm0
0x1800359c7  mov     [rbp+90h+var_108], eax
0x1800359ca  movups  xmmword ptr [rbp+90h+pRequest.ObjectTypeList], xmm0
0x1800359ce  movups  xmmword ptr [rsp+190h+var_130.ResultListLength], xmm0
0x1800359d3  movups  xmmword ptr [rsp+190h+var_130.SaclEvaluationResults], xmm0
0x1800359d8  call    cs:__imp_MapGenericMask
0x1800359df  nop     dword ptr [rax+rax+00h]
0x1800359e4  mov     eax, [rbp+90h+AccessMask]
0x1800359e7  lea     r8, [rbp+90h+pRequest]; pRequest
0x1800359eb  mov     [rbp+90h+pRequest.DesiredAccess], eax
0x1800359ee  xor     r9d, r9d; hAuditEvent
0x1800359f1  mov     [rsp+190h+phAccessCheckResults], 0; phAccessCheckResults
0x1800359fa  lea     rax, [rbp+90h+var_108]
0x1800359fe  mov     [rsp+190h+var_130.GrantedAccessMask], rax
0x180035a03  mov     rdx, rdi; hAuthzClientContext
0x180035a06  lea     rax, [rsp+190h+var_138]
0x180035a0b  mov     [rsp+190h+var_130.ResultListLength], 1
0x180035a13  mov     [rsp+190h+var_130.Error], rax
0x180035a18  xor     ecx, ecx; Flags
0x180035a1a  lea     rax, [rsp+190h+var_130]
0x180035a1f  mov     [rsp+190h+pReply], rax; pReply
0x180035a24  mov     [rsp+190h+OptionalSecurityDescriptorCount], 0; OptionalSecurityDescriptorCount
0x180035a2c  mov     [rsp+190h+OptionalSecurityDescriptorArray], 0; OptionalSecurityDescriptorArray
0x180035a35  mov     [rsp+190h+pSecurityDescriptor], rbx; pSecurityDescriptor
0x180035a3a  call    cs:__imp_AuthzAccessCheck
0x180035a41  nop     dword ptr [rax+rax+00h]
0x180035a46  test    eax, eax
0x180035a48  jz      short loc_180035A90
0x180035a4a  xor     eax, eax
0x180035a4c  cmp     [rsp+190h+var_138], eax
0x180035a50  setz    al
0x180035a53  xor     ebx, ebx
0x180035a55  test    eax, eax
0x180035a57  jnz     loc_180035B07
0x180035a5d  mov     rdx, cs:SecurityDescriptor; pSecurityDescriptor
0x180035a64  lea     r8d, [rax+1]
0x180035a68  xor     r9d, r9d
0x180035a6b  mov     rcx, rdi; hAuthzClientContext
0x180035a6e  call    BfeAccessCheckFromContext
0x180035a73  mov     rbx, rax
0x180035a76  test    rax, rax
0x180035a79  jz      loc_180035B07
0x180035a7f  lea     rdx, aBfeisadmincont; "BfeIsAdminContext"
0x180035a86  mov     rcx, rax
0x180035a89  call    WfpReportError
0x180035a8e  jmp     short loc_180035B07
0x180035a90  call    cs:__imp_GetLastError
0x180035a97  nop     dword ptr [rax+rax+00h]
0x180035a9c  mov     r8d, eax
0x180035a9f  lea     rdx, aAuthzaccessche; "AuthzAccessCheck"
0x180035aa6  call    WfpReportSysErrorAsWinError
0x180035aab  mov     rbx, rax
0x180035aae  test    rax, rax
0x180035ab1  jz      short loc_180035AFC
0x180035ab3  mov     rcx, cs:WPP_GLOBAL_Control
0x180035aba  lea     rax, WPP_GLOBAL_Control
0x180035ac1  lea     r12, aBfeaccesscheck_0; "BfeAccessCheckFromContext"
0x180035ac8  cmp     rcx, rax
0x180035acb  jz      short loc_180035AF3
0x180035acd  cmp     byte ptr [rcx+19h], 2
0x180035ad1  jb      short loc_180035AF3
0x180035ad3  test    byte ptr [rcx+1Ch], 1
0x180035ad7  jz      short loc_180035AF3
0x180035ad9  mov     rcx, [rcx+10h]
0x180035add  mov     edx, 1Ah
0x180035ae2  mov     dword ptr [rsp+190h+OptionalSecurityDescriptorArray], ebx
0x180035ae6  xor     r9d, r9d
0x180035ae9  mov     [rsp+190h+pSecurityDescriptor], r12
0x180035aee  call    WPP_SF_Ssd
0x180035af3  cmp     cs:gWfpLogUserModeErrors, 0
0x180035afa  jnz     short loc_180035B3C
0x180035afc  xor     eax, eax
0x180035afe  test    rbx, rbx
0x180035b01  jz      loc_180035A55
0x180035b07  lea     rcx, gBfeAuthz; lpCriticalSection
0x180035b0e  call    cs:__imp_LeaveCriticalSection
0x180035b15  nop     dword ptr [rax+rax+00h]
0x180035b1a  test    rbx, rbx
0x180035b1d  jnz     short loc_180035B8D
0x180035b1f  mov     rax, rbx
0x180035b22  mov     rcx, [rbp+90h+var_30]
0x180035b26  xor     rcx, rsp; StackCookie
0x180035b29  call    __security_check_cookie
0x180035b2e  add     rsp, 178h
0x180035b35  pop     r12
0x180035b37  pop     rdi
0x180035b38  pop     rbx
0x180035b39  pop     rbp
0x180035b3a  retn
0x180035b3c  test    cs:byte_1800F6115, 1
0x180035b43  jz      short loc_180035AFC
0x180035b45  lea     rax, [rsp+190h+var_140]
0x180035b4a  mov     [rsp+190h+var_140], ebx
0x180035b4e  mov     [rbp+90h+var_40], rax
0x180035b52  lea     rdx, WFP_USERMODE_ERROR
0x180035b59  lea     rax, [rbp+90h+var_60]
0x180035b5d  mov     [rbp+90h+var_50], r12
0x180035b61  mov     r9d, 3
0x180035b67  mov     [rsp+190h+pSecurityDescriptor], rax
0x180035b6c  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180035b73  mov     [rbp+90h+var_48], 1Ah
0x180035b7b  mov     [rbp+90h+var_38], 4
0x180035b83  call    McGenEventWrite_EtwEventWriteTransfer
0x180035b88  jmp     loc_180035B07
0x180035b8d  lea     rdx, aBfeengineopena; "BfeEngineOpenAccessCheckFromContext"
0x180035b94  mov     rcx, rbx
0x180035b97  call    WfpReportError
0x180035b9c  jmp     short loc_180035B1F
```
