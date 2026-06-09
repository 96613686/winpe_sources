# CompareSecurityContexts

- ea: `0x18001b200`
- end: `0x18001b437`
- name: `CompareSecurityContexts`
- size: `567`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180018bf0`

## callees

- `0x18000f1a8`
- `0x180010ad0`
- `0x18001236c`
- `0x18001b200`
- `0x1800362f0`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b30c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001b30c`
- `AUTHZ!AuthzFreeContext` at `0x18001b40c`
- `AUTHZ!AuthzFreeContext` at `0x18001b40c`
- `AUTHZ!AuthzAccessCheck` at `0x18001b2fe`
- `AUTHZ!AuthzAccessCheck` at `0x18001b2fe`

## string_xrefs

- `0x18001b315`: `AuthzAccessCheck`
- `0x18001b372`: `ClientContextFromSid`

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
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
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
0x18001b200  mov     [rsp-8+arg_18], rbx
0x18001b205  push    rbp
0x18001b206  push    rsi
0x18001b207  push    rdi
0x18001b208  push    r14
0x18001b20a  push    r15
0x18001b20c  lea     rbp, [rsp-20h]
0x18001b211  sub     rsp, 120h
0x18001b218  mov     rax, cs:__security_cookie
0x18001b21f  xor     rax, rsp
0x18001b222  mov     [rbp+40h+var_28], rax
0x18001b226  xor     r15d, r15d
0x18001b229  xorps   xmm0, xmm0
0x18001b22c  mov     r14, rcx
0x18001b22f  mov     [rsp+140h+hAuthzClientContext], r15
0x18001b234  xor     ecx, ecx
0x18001b236  mov     [rbp+40h+var_64], r15d
0x18001b23a  mov     dword ptr [rbp+40h+pRequest.OptionalArguments], ecx
0x18001b23d  mov     rsi, r8
0x18001b240  mov     ecx, [rdx]
0x18001b242  mov     rax, rdx
0x18001b245  mov     [rbp+40h+var_60], r15d
0x18001b249  mov     ebx, 2
0x18001b24e  mov     [rbp+40h+var_68], r15d
0x18001b252  movups  xmmword ptr [rsp+140h+var_E0.ResultListLength], xmm0
0x18001b257  movups  xmmword ptr [rbp+40h+pRequest.DesiredAccess], xmm0
0x18001b25b  movups  xmmword ptr [rbp+40h+pRequest.ObjectTypeList], xmm0
0x18001b25f  movups  xmmword ptr [rsp+140h+var_E0.GrantedAccessMask+4], xmm0
0x18001b264  cmp     ecx, 0Dh
0x18001b267  jz      loc_18001B329
0x18001b26d  cmp     ecx, 0Fh
0x18001b270  jz      short loc_18001B279
0x18001b272  mov     ecx, 5
0x18001b277  int     29h; Win8: RtlFailFast(ecx)
0x18001b279  mov     rcx, [rax+8]; DynamicGroupArgs
0x18001b27d  lea     rdx, [rsp+140h+hAuthzClientContext]; phAuthzClientContext
0x18001b282  call    ClientContextFromTokenInformation
0x18001b287  test    rax, rax
0x18001b28a  jnz     loc_18001B402
0x18001b290  mov     rdx, [rsp+140h+hAuthzClientContext]; hAuthzClientContext
0x18001b295  lea     rax, [rbp+40h+var_64]
0x18001b299  mov     [rsp+140h+var_E0.GrantedAccessMask], rax
0x18001b29e  lea     r8, [rbp+40h+pRequest]; pRequest
0x18001b2a2  mov     [rsp+140h+phAccessCheckResults], r15; phAccessCheckResults
0x18001b2a7  lea     rax, [rbp+40h+var_60]
0x18001b2ab  mov     [rsp+140h+var_E0.SaclEvaluationResults], rax
0x18001b2b0  xorps   xmm0, xmm0
0x18001b2b3  lea     rax, [rbp+40h+var_68]
0x18001b2b7  mov     [rbp+40h+pRequest.DesiredAccess], 1
0x18001b2be  mov     [rsp+140h+var_E0.Error], rax
0x18001b2c3  xor     r9d, r9d; hAuditEvent
0x18001b2c6  lea     rax, [rsp+140h+var_E0]
0x18001b2cb  mov     [rbp+40h+pRequest.ObjectTypeListLength], r15d
0x18001b2cf  mov     [rsp+140h+pReply], rax; pReply
0x18001b2d4  mov     ecx, 1; Flags
0x18001b2d9  mov     rax, [r14+8]
0x18001b2dd  mov     [rsp+140h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x18001b2e2  mov     [rsp+140h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x18001b2e7  mov     [rsp+140h+pSecurityDescriptor], rax; pSecurityDescriptor
0x18001b2ec  movdqu  xmmword ptr [rbp+40h+pRequest.PrincipalSelfSid], xmm0
0x18001b2f1  mov     [rbp+40h+pRequest.OptionalArguments], r15
0x18001b2f5  mov     qword ptr [rsp+140h+var_E0.ResultListLength], 1
0x18001b2fe  call    cs:__imp_AuthzAccessCheck
0x18001b304  test    eax, eax
0x18001b306  jnz     loc_18001B3FA
0x18001b30c  call    cs:__imp_GetLastError
0x18001b312  mov     r8d, eax
0x18001b315  lea     rdx, aAuthzaccessche; "AuthzAccessCheck"
0x18001b31c  call    WfpReportSysErrorAsWinError
0x18001b321  mov     [rsi], rax
0x18001b324  jmp     loc_18001B402
0x18001b329  mov     rax, [rdx+8]
0x18001b32d  mov     [rbp+40h+var_98], rax
0x18001b331  lea     rax, [rbp+40h+var_98]
0x18001b335  mov     [rbp+40h+var_80], rax
0x18001b339  mov     [rbp+40h+DynamicGroupArgs], 1
0x18001b341  movdqu  [rbp+40h+var_78], xmm0
0x18001b346  mov     [rbp+40h+var_90], r15
0x18001b34a  lea     rdx, [rsp+140h+hAuthzClientContext]; phAuthzClientContext
0x18001b34f  lea     rcx, [rbp+40h+DynamicGroupArgs]; DynamicGroupArgs
0x18001b353  call    ClientContextFromTokenInformation
0x18001b358  mov     rdi, rax
0x18001b35b  test    rax, rax
0x18001b35e  jz      loc_18001B290
0x18001b364  mov     rcx, cs:WPP_GLOBAL_Control
0x18001b36b  lea     rax, WPP_GLOBAL_Control
0x18001b372  lea     rsi, aClientcontextf; "ClientContextFromSid"
0x18001b379  cmp     rcx, rax
0x18001b37c  jz      short loc_18001B3A3
0x18001b37e  cmp     [rcx+19h], bl
0x18001b381  jb      short loc_18001B3A3
0x18001b383  test    byte ptr [rcx+1Ch], 1
0x18001b387  jz      short loc_18001B3A3
0x18001b389  mov     rcx, [rcx+10h]
0x18001b38d  mov     edx, 1Ah
0x18001b392  mov     dword ptr [rsp+140h+OptionalSecurityDescriptorArray], edi
0x18001b396  xor     r9d, r9d
0x18001b399  mov     [rsp+140h+pSecurityDescriptor], rsi
0x18001b39e  call    WPP_SF_Ssd
0x18001b3a3  cmp     cs:gWfpLogUserModeErrors, r15d
0x18001b3aa  jz      short loc_18001B402
0x18001b3ac  test    cs:byte_1800F30F5, 1
0x18001b3b3  jz      short loc_18001B402
0x18001b3b5  lea     rax, [rsp+140h+var_F0]
0x18001b3ba  mov     [rsp+140h+var_F0], edi
0x18001b3be  mov     [rbp+40h+var_38], rax
0x18001b3c2  lea     rdx, WFP_USERMODE_ERROR
0x18001b3c9  lea     rax, [rbp+40h+var_58]
0x18001b3cd  mov     [rbp+40h+var_48], rsi
0x18001b3d1  mov     r9d, 3
0x18001b3d7  mov     [rsp+140h+pSecurityDescriptor], rax
0x18001b3dc  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18001b3e3  mov     [rbp+40h+var_40], 15h
0x18001b3eb  mov     [rbp+40h+var_30], 4
0x18001b3f3  call    McGenEventWrite_EtwEventWriteTransfer
0x18001b3f8  jmp     short loc_18001B402
0x18001b3fa  cmp     [rbp+40h+var_68], r15d
0x18001b3fe  cmovz   ebx, r15d
0x18001b402  mov     rcx, [rsp+140h+hAuthzClientContext]; hAuthzClientContext
0x18001b407  test    rcx, rcx
0x18001b40a  jz      short loc_18001B412
0x18001b40c  call    cs:__imp_AuthzFreeContext
0x18001b412  mov     eax, ebx
0x18001b414  mov     rcx, [rbp+40h+var_28]
0x18001b418  xor     rcx, rsp; StackCookie
0x18001b41b  call    __security_check_cookie
0x18001b420  mov     rbx, [rsp+140h+arg_18]
0x18001b428  add     rsp, 120h
0x18001b42f  pop     r15
0x18001b431  pop     r14
0x18001b433  pop     rdi
0x18001b434  pop     rsi
0x18001b435  pop     rbp
0x18001b436  retn
```
