# CompareSecurityContexts

- ea: `0x18001bf10`
- end: `0x18001c15a`
- name: `CompareSecurityContexts`
- size: `586`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180019850`

## callees

- `0x18000fb34`
- `0x180011510`
- `0x180012d8c`
- `0x18001bf10`
- `0x180034240`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c022`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001c022`
- `AUTHZ!AuthzFreeContext` at `0x18001c128`
- `AUTHZ!AuthzFreeContext` at `0x18001c128`
- `AUTHZ!AuthzAccessCheck` at `0x18001c00e`
- `AUTHZ!AuthzAccessCheck` at `0x18001c00e`

## string_xrefs

- `0x18001c031`: `AuthzAccessCheck`
- `0x18001c08e`: `ClientContextFromSid`

## pseudocode

```c
__int64 __fastcall CompareSecurityContexts(__int64 a1, int *a2, _QWORD *a3)
{
  int v5; // ecx
  unsigned int v6; // ebx
  DWORD LastError; // eax
  __int64 v8; // rcx
  __int64 v9; // rax
  int v10; // r8d
  int v11; // edi
  PSECURITY_DESCRIPTOR pSecurityDescriptor; // [rsp+20h] [rbp-E0h]
  int v14; // [rsp+50h] [rbp-B0h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+58h] [rbp-A8h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+60h] [rbp-A0h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v18[2]; // [rsp+A8h] [rbp-58h] BYREF
  _QWORD DynamicGroupArgs[2]; // [rsp+B8h] [rbp-48h] BYREF
  __int128 v20; // [rsp+C8h] [rbp-38h]
  int v21; // [rsp+D8h] [rbp-28h] BYREF
  int v22; // [rsp+DCh] [rbp-24h] BYREF
  int v23; // [rsp+E0h] [rbp-20h] BYREF
  _BYTE v24[16]; // [rsp+E8h] [rbp-18h] BYREF
  const char *v25; // [rsp+F8h] [rbp-8h]
  __int64 v26; // [rsp+100h] [rbp+0h]
  int *v27; // [rsp+108h] [rbp+8h]
  __int64 v28; // [rsp+110h] [rbp+10h]

  hAuthzClientContext = 0;
  v22 = 0;
  v5 = *a2;
  v23 = 0;
  v6 = 2;
  v21 = 0;
  memset(&pReply, 0, 28);
  memset(&pRequest, 0, 36);
  if ( v5 == 13 )
  {
    v18[0] = *((_QWORD *)a2 + 1);
    DynamicGroupArgs[1] = v18;
    DynamicGroupArgs[0] = 1;
    v20 = 0;
    v18[1] = 0;
    v9 = ClientContextFromTokenInformation(DynamicGroupArgs, &hAuthzClientContext);
    v11 = v9;
    if ( !v9 )
    {
LABEL_5:
      pReply.GrantedAccessMask = (PACCESS_MASK)&v22;
      pReply.SaclEvaluationResults = (PDWORD)&v23;
      pRequest.DesiredAccess = 1;
      pReply.Error = (PDWORD)&v21;
      pSecurityDescriptor = *(PSECURITY_DESCRIPTOR *)(a1 + 8);
      memset(&pRequest.PrincipalSelfSid, 0, 20);
      pRequest.OptionalArguments = 0;
      *(_QWORD *)&pReply.ResultListLength = 1;
      if ( AuthzAccessCheck(1u, hAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
      {
        if ( !v21 )
          v6 = 0;
      }
      else
      {
        LastError = GetLastError();
        *a3 = WfpReportSysErrorAsWinError(v8, "AuthzAccessCheck", LastError);
      }
      goto LABEL_17;
    }
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_Ssd(*((_QWORD *)WPP_GLOBAL_Control + 2), 26, v10, 0, (__int64)"ClientContextFromSid", v9);
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v14 = v11;
      v27 = &v14;
      v25 = "ClientContextFromSid";
      v26 = 21;
      v28 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v10,
        3,
        (__int64)v24);
    }
  }
  else
  {
    if ( v5 != 15 )
      __fastfail(5u);
    if ( !ClientContextFromTokenInformation(*((PVOID *)a2 + 1), &hAuthzClientContext) )
      goto LABEL_5;
  }
LABEL_17:
  if ( hAuthzClientContext )
    AuthzFreeContext(hAuthzClientContext);
  return v6;
}

```

## disassembly

```asm
0x18001bf10  mov     [rsp-8+arg_18], rbx
0x18001bf15  push    rbp
0x18001bf16  push    rsi
0x18001bf17  push    rdi
0x18001bf18  push    r14
0x18001bf1a  push    r15
0x18001bf1c  lea     rbp, [rsp-20h]
0x18001bf21  sub     rsp, 120h
0x18001bf28  mov     rax, cs:__security_cookie
0x18001bf2f  xor     rax, rsp
0x18001bf32  mov     [rbp+40h+var_28], rax
0x18001bf36  xor     r15d, r15d
0x18001bf39  xorps   xmm0, xmm0
0x18001bf3c  mov     r14, rcx
0x18001bf3f  mov     [rsp+140h+hAuthzClientContext], r15
0x18001bf44  xor     ecx, ecx
0x18001bf46  mov     [rbp+40h+var_64], r15d
0x18001bf4a  mov     dword ptr [rbp+40h+pRequest.OptionalArguments], ecx
0x18001bf4d  mov     rsi, r8
0x18001bf50  mov     ecx, [rdx]
0x18001bf52  mov     rax, rdx
0x18001bf55  mov     [rbp+40h+var_60], r15d
0x18001bf59  mov     ebx, 2
0x18001bf5e  mov     [rbp+40h+var_68], r15d
0x18001bf62  movups  xmmword ptr [rsp+140h+var_E0.ResultListLength], xmm0
0x18001bf67  movups  xmmword ptr [rbp+40h+pRequest.DesiredAccess], xmm0
0x18001bf6b  movups  xmmword ptr [rbp+40h+pRequest.ObjectTypeList], xmm0
0x18001bf6f  movups  xmmword ptr [rsp+140h+var_E0.GrantedAccessMask+4], xmm0
0x18001bf74  cmp     ecx, 0Dh
0x18001bf77  jz      loc_18001C045
0x18001bf7d  cmp     ecx, 0Fh
0x18001bf80  jz      short loc_18001BF89
0x18001bf82  mov     ecx, 5
0x18001bf87  int     29h; Win8: RtlFailFast(ecx)
0x18001bf89  mov     rcx, [rax+8]; DynamicGroupArgs
0x18001bf8d  lea     rdx, [rsp+140h+hAuthzClientContext]; phAuthzClientContext
0x18001bf92  call    ClientContextFromTokenInformation
0x18001bf97  test    rax, rax
0x18001bf9a  jnz     loc_18001C11E
0x18001bfa0  mov     rdx, [rsp+140h+hAuthzClientContext]; hAuthzClientContext
0x18001bfa5  lea     rax, [rbp+40h+var_64]
0x18001bfa9  mov     [rsp+140h+var_E0.GrantedAccessMask], rax
0x18001bfae  lea     r8, [rbp+40h+pRequest]; pRequest
0x18001bfb2  mov     [rsp+140h+phAccessCheckResults], r15; phAccessCheckResults
0x18001bfb7  lea     rax, [rbp+40h+var_60]
0x18001bfbb  mov     [rsp+140h+var_E0.SaclEvaluationResults], rax
0x18001bfc0  xorps   xmm0, xmm0
0x18001bfc3  lea     rax, [rbp+40h+var_68]
0x18001bfc7  mov     [rbp+40h+pRequest.DesiredAccess], 1
0x18001bfce  mov     [rsp+140h+var_E0.Error], rax
0x18001bfd3  xor     r9d, r9d; hAuditEvent
0x18001bfd6  lea     rax, [rsp+140h+var_E0]
0x18001bfdb  mov     [rbp+40h+pRequest.ObjectTypeListLength], r15d
0x18001bfdf  mov     [rsp+140h+pReply], rax; pReply
0x18001bfe4  mov     ecx, 1; Flags
0x18001bfe9  mov     rax, [r14+8]
0x18001bfed  mov     [rsp+140h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x18001bff2  mov     [rsp+140h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x18001bff7  mov     [rsp+140h+pSecurityDescriptor], rax; pSecurityDescriptor
0x18001bffc  movdqu  xmmword ptr [rbp+40h+pRequest.PrincipalSelfSid], xmm0
0x18001c001  mov     [rbp+40h+pRequest.OptionalArguments], r15
0x18001c005  mov     qword ptr [rsp+140h+var_E0.ResultListLength], 1
0x18001c00e  call    cs:__imp_AuthzAccessCheck
0x18001c015  nop     dword ptr [rax+rax+00h]
0x18001c01a  test    eax, eax
0x18001c01c  jnz     loc_18001C116
0x18001c022  call    cs:__imp_GetLastError
0x18001c029  nop     dword ptr [rax+rax+00h]
0x18001c02e  mov     r8d, eax
0x18001c031  lea     rdx, aAuthzaccessche; "AuthzAccessCheck"
0x18001c038  call    WfpReportSysErrorAsWinError
0x18001c03d  mov     [rsi], rax
0x18001c040  jmp     loc_18001C11E
0x18001c045  mov     rax, [rdx+8]
0x18001c049  mov     [rbp+40h+var_98], rax
0x18001c04d  lea     rax, [rbp+40h+var_98]
0x18001c051  mov     [rbp+40h+var_80], rax
0x18001c055  mov     [rbp+40h+DynamicGroupArgs], 1
0x18001c05d  movdqu  [rbp+40h+var_78], xmm0
0x18001c062  mov     [rbp+40h+var_90], r15
0x18001c066  lea     rdx, [rsp+140h+hAuthzClientContext]; phAuthzClientContext
0x18001c06b  lea     rcx, [rbp+40h+DynamicGroupArgs]; DynamicGroupArgs
0x18001c06f  call    ClientContextFromTokenInformation
0x18001c074  mov     rdi, rax
0x18001c077  test    rax, rax
0x18001c07a  jz      loc_18001BFA0
0x18001c080  mov     rcx, cs:WPP_GLOBAL_Control
0x18001c087  lea     rax, WPP_GLOBAL_Control
0x18001c08e  lea     rsi, aClientcontextf; "ClientContextFromSid"
0x18001c095  cmp     rcx, rax
0x18001c098  jz      short loc_18001C0BF
0x18001c09a  cmp     [rcx+19h], bl
0x18001c09d  jb      short loc_18001C0BF
0x18001c09f  test    byte ptr [rcx+1Ch], 1
0x18001c0a3  jz      short loc_18001C0BF
0x18001c0a5  mov     rcx, [rcx+10h]
0x18001c0a9  mov     edx, 1Ah
0x18001c0ae  mov     dword ptr [rsp+140h+OptionalSecurityDescriptorArray], edi
0x18001c0b2  xor     r9d, r9d
0x18001c0b5  mov     [rsp+140h+pSecurityDescriptor], rsi
0x18001c0ba  call    WPP_SF_Ssd
0x18001c0bf  cmp     cs:gWfpLogUserModeErrors, r15d
0x18001c0c6  jz      short loc_18001C11E
0x18001c0c8  test    cs:byte_1800F6115, 1
0x18001c0cf  jz      short loc_18001C11E
0x18001c0d1  lea     rax, [rsp+140h+var_F0]
0x18001c0d6  mov     [rsp+140h+var_F0], edi
0x18001c0da  mov     [rbp+40h+var_38], rax
0x18001c0de  lea     rdx, WFP_USERMODE_ERROR
0x18001c0e5  lea     rax, [rbp+40h+var_58]
0x18001c0e9  mov     [rbp+40h+var_48], rsi
0x18001c0ed  mov     r9d, 3
0x18001c0f3  mov     [rsp+140h+pSecurityDescriptor], rax
0x18001c0f8  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18001c0ff  mov     [rbp+40h+var_40], 15h
0x18001c107  mov     [rbp+40h+var_30], 4
0x18001c10f  call    McGenEventWrite_EtwEventWriteTransfer
0x18001c114  jmp     short loc_18001C11E
0x18001c116  cmp     [rbp+40h+var_68], r15d
0x18001c11a  cmovz   ebx, r15d
0x18001c11e  mov     rcx, [rsp+140h+hAuthzClientContext]; hAuthzClientContext
0x18001c123  test    rcx, rcx
0x18001c126  jz      short loc_18001C134
0x18001c128  call    cs:__imp_AuthzFreeContext
0x18001c12f  nop     dword ptr [rax+rax+00h]
0x18001c134  mov     eax, ebx
0x18001c136  mov     rcx, [rbp+40h+var_28]
0x18001c13a  xor     rcx, rsp; StackCookie
0x18001c13d  call    __security_check_cookie
0x18001c142  mov     rbx, [rsp+140h+arg_18]
0x18001c14a  add     rsp, 120h
0x18001c151  pop     r15
0x18001c153  pop     r14
0x18001c155  pop     rdi
0x18001c156  pop     rsi
0x18001c157  pop     rbp
0x18001c158  retn
```
