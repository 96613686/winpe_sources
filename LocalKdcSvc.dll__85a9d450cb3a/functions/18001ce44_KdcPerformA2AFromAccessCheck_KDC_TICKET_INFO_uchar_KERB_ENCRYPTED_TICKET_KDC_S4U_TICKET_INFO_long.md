# KdcPerformA2AFromAccessCheck(_KDC_TICKET_INFO *,uchar *,KERB_ENCRYPTED_TICKET *,_KDC_S4U_TICKET_INFO *,long *)

- ea: `0x18001ce44`
- end: `0x18001d176`
- name: `?KdcPerformA2AFromAccessCheck@@YAJPEAU_KDC_TICKET_INFO@@PEAEPEAUKERB_ENCRYPTED_TICKET@@PEAU_KDC_S4U_TICKET_INFO@@PEAJ@Z`
- size: `818`
- prototype: `int(struct _KDC_TICKET_INFO *, unsigned __int8 *, struct KERB_ENCRYPTED_TICKET *, struct _KDC_S4U_TICKET_INFO *, int *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180016148`

## callees

- `0x180003908`
- `0x1800101ec`
- `0x18001ce44`
- `0x180047d28`
- `0x1800485e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d08c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cf96`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001cff0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d08c`
- `AUTHZ!AuthzModifyClaims` at `0x18001cfcd`
- `AUTHZ!AuthzModifyClaims` at `0x18001cfcd`
- `AUTHZ!AuthzAccessCheck` at `0x18001d069`
- `AUTHZ!AuthzAccessCheck` at `0x18001d069`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18001cf6b`
- `AUTHZ!AuthzInitializeContextFromSid` at `0x18001cf6b`
- `AUTHZ!AuthzFreeContext` at `0x18001d025`
- `AUTHZ!AuthzFreeContext` at `0x18001d0c1`
- `AUTHZ!AuthzFreeContext` at `0x18001d0ea`
- `AUTHZ!AuthzFreeContext` at `0x18001d101`
- `AUTHZ!AuthzFreeContext` at `0x18001d155`
- `AUTHZ!AuthzFreeContext` at `0x18001d025`
- `AUTHZ!AuthzFreeContext` at `0x18001d0c1`
- `AUTHZ!AuthzFreeContext` at `0x18001d0ea`
- `AUTHZ!AuthzFreeContext` at `0x18001d101`
- `AUTHZ!AuthzFreeContext` at `0x18001d155`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall KdcPerformA2AFromAccessCheck(
        struct _KDC_TICKET_INFO *a1,
        unsigned __int8 *a2,
        struct KERB_ENCRYPTED_TICKET *a3,
        struct _KDC_S4U_TICKET_INFO *a4,
        int *a5)
{
  int *v8; // rsi
  unsigned int SidsFromTgt; // ebx
  DWORD LastError; // eax
  __int64 v11; // rdx
  DWORD v12; // eax
  AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext; // [rsp+50h] [rbp-B0h] BYREF
  int v15; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v16; // [rsp+60h] [rbp-A0h]
  __int128 DynamicGroupArgs; // [rsp+68h] [rbp-98h] BYREF
  __int64 v18; // [rsp+78h] [rbp-88h]
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+80h] [rbp-80h] BYREF
  _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+A0h] [rbp-60h] BYREF
  AUTHZ_CLIENT_CONTEXT_HANDLE *p_hAuthzClientContext; // [rsp+C8h] [rbp-38h]
  _BYTE *v22; // [rsp+D0h] [rbp-30h]
  char v23; // [rsp+D8h] [rbp-28h]
  _BYTE v24[128]; // [rsp+E0h] [rbp-20h] BYREF
  int v25; // [rsp+188h] [rbp+88h] BYREF
  int v26; // [rsp+18Ch] [rbp+8Ch]

  v26 = HIDWORD(a4);
  *(_QWORD *)&pReply.ResultListLength = 1;
  pReply.SaclEvaluationResults = 0;
  *(_QWORD *)&pRequest.DesiredAccess = 256;
  *(_QWORD *)&pRequest.ObjectTypeListLength = 0;
  v25 = 0;
  v15 = 5;
  DynamicGroupArgs = 0;
  v18 = 0;
  memset_0(v24, 0, 0x50u);
  hAuthzClientContext = 0;
  v16 = 0;
  p_hAuthzClientContext = &hAuthzClientContext;
  v22 = v24;
  v23 = 1;
  v8 = a5;
  *a5 = 0;
  pRequest.ObjectTypeList = 0;
  pRequest.OptionalArguments = 0;
  pRequest.PrincipalSelfSid = 0;
  pReply.GrantedAccessMask = (PACCESS_MASK)&v25;
  pReply.Error = (PDWORD)&v15;
  SidsFromTgt = KdcGetSidsFromTgt(
                  a3,
                  a1,
                  0,
                  (struct _KDC_AUTHZ_INFO *)&DynamicGroupArgs,
                  (struct _KDC_AUTHZ_GROUP_BUFFERS *)v24,
                  v8,
                  0,
                  0,
                  0);
  if ( SidsFromTgt || !(_QWORD)DynamicGroupArgs )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 78, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, SidsFromTgt);
    *v8 = -1073741595;
    if ( hAuthzClientContext )
      AuthzFreeContext(hAuthzClientContext);
    goto LABEL_35;
  }
  if ( !AuthzInitializeContextFromSid(
          2u,
          *(PSID *)DynamicGroupArgs,
          KdcAuthzRM,
          0,
          0,
          &DynamicGroupArgs,
          &hAuthzClientContext) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      v11 = 79;
LABEL_19:
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), v11, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, LastError);
      goto LABEL_20;
    }
    goto LABEL_20;
  }
  if ( !v18 || (LODWORD(a5) = 1, (unsigned int)AuthzModifyClaims(hAuthzClientContext, 13, &a5)) )
  {
    if ( !AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, a2, 0, 0, &pReply, 0) )
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        v11 = 81;
        goto LABEL_19;
      }
LABEL_20:
      *v8 = -1073741595;
      if ( hAuthzClientContext )
        AuthzFreeContext(hAuthzClientContext);
      SidsFromTgt = 60;
LABEL_35:
      KdcFreeAuthzInfo((struct _KDC_AUTHZ_GROUP_BUFFERS *)v24);
      return SidsFromTgt;
    }
    if ( *pReply.Error )
    {
      *v8 = -1073740781;
      if ( hAuthzClientContext )
        AuthzFreeContext(hAuthzClientContext);
      SidsFromTgt = 12;
      goto LABEL_35;
    }
    if ( hAuthzClientContext )
      AuthzFreeContext(hAuthzClientContext);
    KdcFreeAuthzInfo((struct _KDC_AUTHZ_GROUP_BUFFERS *)v24);
    return 0;
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v12 = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 80, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids, v12);
    }
    *v8 = -1073741595;
    if ( hAuthzClientContext )
      AuthzFreeContext(hAuthzClientContext);
    KdcFreeAuthzInfo((struct _KDC_AUTHZ_GROUP_BUFFERS *)v24);
    return 60;
  }
}

```

## disassembly

```asm
0x18001ce44  mov     [rsp-8+arg_18], r9
0x18001ce49  push    rbp
0x18001ce4a  push    rbx
0x18001ce4b  push    rsi
0x18001ce4c  push    rdi
0x18001ce4d  push    r14
0x18001ce4f  push    r15
0x18001ce51  lea     rbp, [rsp-38h]
0x18001ce56  sub     rsp, 138h
0x18001ce5d  mov     rdi, r8
0x18001ce60  mov     r14, rdx
0x18001ce63  mov     rbx, rcx
0x18001ce66  xor     r15d, r15d
0x18001ce69  mov     qword ptr [rbp+60h+var_E0.ResultListLength], 1
0x18001ce71  mov     [rbp+60h+var_E0.SaclEvaluationResults], r15
0x18001ce75  mov     qword ptr [rbp+60h+pRequest.DesiredAccess], 100h
0x18001ce7d  mov     qword ptr [rbp+60h+pRequest.ObjectTypeListLength], r15
0x18001ce81  mov     dword ptr [rbp+60h+arg_18], r15d
0x18001ce88  mov     [rsp+160h+var_108], 5
0x18001ce90  xorps   xmm0, xmm0
0x18001ce93  xor     eax, eax
0x18001ce95  movups  [rsp+160h+var_F8], xmm0
0x18001ce9a  mov     [rsp+160h+var_E8], rax
0x18001ce9f  xor     edx, edx; Val
0x18001cea1  lea     r8d, [r15+50h]; Size
0x18001cea5  lea     rcx, [rbp+60h+var_80]; void *
0x18001cea9  call    memset_0
0x18001ceae  mov     [rsp+160h+hAuthzClientContext], r15
0x18001ceb3  mov     [rsp+160h+var_100], r15
0x18001ceb8  lea     rax, [rsp+160h+hAuthzClientContext]
0x18001cebd  mov     [rbp+60h+var_98], rax
0x18001cec1  lea     rax, [rbp+60h+var_80]
0x18001cec5  mov     [rbp+60h+var_90], rax
0x18001cec9  mov     [rbp+60h+var_88], 1
0x18001cecd  mov     rsi, [rbp+60h+arg_20]
0x18001ced4  mov     [rsi], r15d
0x18001ced7  mov     [rbp+60h+pRequest.ObjectTypeList], r15
0x18001cedb  mov     [rbp+60h+pRequest.OptionalArguments], r15
0x18001cedf  mov     [rbp+60h+pRequest.PrincipalSelfSid], r15
0x18001cee3  lea     rax, [rbp+60h+arg_18]
0x18001ceea  mov     [rbp+60h+var_E0.GrantedAccessMask], rax
0x18001ceee  lea     rax, [rsp+160h+var_108]
0x18001cef3  mov     [rbp+60h+var_E0.Error], rax
0x18001cef7  mov     [rsp+160h+phAccessCheckResults], r15; void **
0x18001cefc  mov     [rsp+160h+pReply], r15; struct _UNICODE_STRING *
0x18001cf01  mov     [rsp+160h+phAuthzClientContext], r15; struct _UNICODE_STRING *
0x18001cf06  mov     [rsp+160h+DynamicGroupArgs], rsi; int *
0x18001cf0b  lea     rax, [rbp+60h+var_80]
0x18001cf0f  mov     qword ptr [rsp+160h+Identifier.LowPart], rax; struct _KDC_AUTHZ_GROUP_BUFFERS *
0x18001cf14  lea     r9, [rsp+160h+var_F8]; struct _KDC_AUTHZ_INFO *
0x18001cf19  xor     r8d, r8d; unsigned __int8
0x18001cf1c  mov     rdx, rbx; struct _KDC_TICKET_INFO *
0x18001cf1f  mov     rcx, rdi; struct KERB_ENCRYPTED_TICKET *
0x18001cf22  call    ?KdcGetSidsFromTgt@@YAJPEAUKERB_ENCRYPTED_TICKET@@PEAU_KDC_TICKET_INFO@@EPEAU_KDC_AUTHZ_INFO@@PEAU_KDC_AUTHZ_GROUP_BUFFERS@@PEAJPEAU_UNICODE_STRING@@5PEAPEAX@Z; KdcGetSidsFromTgt(KERB_ENCRYPTED_TICKET *,_KDC_TICKET_INFO *,uchar,_KDC_AUTHZ_INFO *,_KDC_AUTHZ_GROUP_BUFFERS *,long *,_UNICODE_STRING *,_UNICODE_STRING *,void * *)
0x18001cf27  mov     ebx, eax
0x18001cf29  test    eax, eax
0x18001cf2b  jnz     loc_18001D114
0x18001cf31  mov     rdx, qword ptr [rsp+160h+var_F8]
0x18001cf36  test    rdx, rdx
0x18001cf39  jz      loc_18001D114
0x18001cf3f  lea     rax, [rsp+160h+hAuthzClientContext]
0x18001cf44  mov     [rsp+160h+phAuthzClientContext], rax; phAuthzClientContext
0x18001cf49  lea     rax, [rsp+160h+var_F8]
0x18001cf4e  mov     [rsp+160h+DynamicGroupArgs], rax; DynamicGroupArgs
0x18001cf53  mov     eax, r15d
0x18001cf56  mov     qword ptr [rsp+160h+Identifier.LowPart], rax; Identifier
0x18001cf5b  xor     r9d, r9d; pExpirationTime
0x18001cf5e  mov     r8, cs:?KdcAuthzRM@@3PEAUAUTHZ_RESOURCE_MANAGER_HANDLE__@@EA; hAuthzResourceManager
0x18001cf65  mov     rdx, [rdx]; UserSid
0x18001cf68  lea     ecx, [rbx+2]; Flags
0x18001cf6b  call    cs:__imp_AuthzInitializeContextFromSid
0x18001cf71  test    eax, eax
0x18001cf73  jnz     short loc_18001CFA4
0x18001cf75  lea     rax, WPP_GLOBAL_Control
0x18001cf7c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cf83  cmp     rcx, rax
0x18001cf86  jz      loc_18001D0B1
0x18001cf8c  test    byte ptr [rcx+1Ch], 1
0x18001cf90  jz      loc_18001D0B1
0x18001cf96  call    cs:__imp_GetLastError
0x18001cf9c  lea     edx, [rbx+4Fh]
0x18001cf9f  jmp     loc_18001D097
0x18001cfa4  mov     r9, [rsp+160h+var_E8]
0x18001cfa9  test    r9, r9
0x18001cfac  jz      loc_18001D03E
0x18001cfb2  mov     dword ptr [rbp+60h+arg_20], 1
0x18001cfbc  lea     r8, [rbp+60h+arg_20]
0x18001cfc3  mov     edx, 0Dh
0x18001cfc8  mov     rcx, [rsp+160h+hAuthzClientContext]
0x18001cfcd  call    cs:__imp_AuthzModifyClaims
0x18001cfd3  test    eax, eax
0x18001cfd5  jnz     short loc_18001D03E
0x18001cfd7  lea     rax, WPP_GLOBAL_Control
0x18001cfde  mov     rcx, cs:WPP_GLOBAL_Control
0x18001cfe5  cmp     rcx, rax
0x18001cfe8  jz      short loc_18001D015
0x18001cfea  test    byte ptr [rcx+1Ch], 1
0x18001cfee  jz      short loc_18001D015
0x18001cff0  call    cs:__imp_GetLastError
0x18001cff6  mov     edx, 50h ; 'P'
0x18001cffb  mov     r9d, eax
0x18001cffe  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001d005  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d00c  mov     rcx, [rcx+10h]
0x18001d010  call    WPP_SF_d
0x18001d015  mov     dword ptr [rsi], 0C00000E5h
0x18001d01b  mov     rcx, [rsp+160h+hAuthzClientContext]; hAuthzClientContext
0x18001d020  test    rcx, rcx
0x18001d023  jz      short loc_18001D02B
0x18001d025  call    cs:__imp_AuthzFreeContext
0x18001d02b  lea     rcx, [rbp+60h+var_80]; struct _KDC_AUTHZ_GROUP_BUFFERS *
0x18001d02f  call    ?KdcFreeAuthzInfo@@YAXPEAU_KDC_AUTHZ_GROUP_BUFFERS@@@Z; KdcFreeAuthzInfo(_KDC_AUTHZ_GROUP_BUFFERS *)
0x18001d034  mov     eax, 3Ch ; '<'
0x18001d039  jmp     loc_18001D166
0x18001d03e  mov     [rsp+160h+phAccessCheckResults], r15; phAccessCheckResults
0x18001d043  lea     rax, [rbp+60h+var_E0]
0x18001d047  mov     [rsp+160h+pReply], rax; pReply
0x18001d04c  mov     dword ptr [rsp+160h+phAuthzClientContext], r15d; OptionalSecurityDescriptorCount
0x18001d051  mov     [rsp+160h+DynamicGroupArgs], r15; OptionalSecurityDescriptorArray
0x18001d056  mov     qword ptr [rsp+160h+Identifier.LowPart], r14; pSecurityDescriptor
0x18001d05b  xor     r9d, r9d; hAuditEvent
0x18001d05e  lea     r8, [rbp+60h+pRequest]; pRequest
0x18001d062  mov     rdx, [rsp+160h+hAuthzClientContext]; hAuthzClientContext
0x18001d067  xor     ecx, ecx; Flags
0x18001d069  call    cs:__imp_AuthzAccessCheck
0x18001d06f  test    eax, eax
0x18001d071  jnz     short loc_18001D0D1
0x18001d073  lea     rax, WPP_GLOBAL_Control
0x18001d07a  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d081  cmp     rcx, rax
0x18001d084  jz      short loc_18001D0B1
0x18001d086  test    byte ptr [rcx+1Ch], 1
0x18001d08a  jz      short loc_18001D0B1
0x18001d08c  call    cs:__imp_GetLastError
0x18001d092  mov     edx, 51h ; 'Q'
0x18001d097  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d09e  mov     r9d, eax
0x18001d0a1  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001d0a8  mov     rcx, [rcx+10h]
0x18001d0ac  call    WPP_SF_d
0x18001d0b1  mov     dword ptr [rsi], 0C00000E5h
0x18001d0b7  mov     rcx, [rsp+160h+hAuthzClientContext]; hAuthzClientContext
0x18001d0bc  test    rcx, rcx
0x18001d0bf  jz      short loc_18001D0C7
0x18001d0c1  call    cs:__imp_AuthzFreeContext
0x18001d0c7  mov     ebx, 3Ch ; '<'
0x18001d0cc  jmp     loc_18001D15B
0x18001d0d1  mov     rax, [rbp+60h+var_E0.Error]
0x18001d0d5  cmp     [rax], r15d
0x18001d0d8  jz      short loc_18001D0F7
0x18001d0da  mov     dword ptr [rsi], 0C0000413h
0x18001d0e0  mov     rcx, [rsp+160h+hAuthzClientContext]; hAuthzClientContext
0x18001d0e5  test    rcx, rcx
0x18001d0e8  jz      short loc_18001D0F0
0x18001d0ea  call    cs:__imp_AuthzFreeContext
0x18001d0f0  mov     ebx, 0Ch
0x18001d0f5  jmp     short loc_18001D15B
0x18001d0f7  mov     rcx, [rsp+160h+hAuthzClientContext]; hAuthzClientContext
0x18001d0fc  test    rcx, rcx
0x18001d0ff  jz      short loc_18001D107
0x18001d101  call    cs:__imp_AuthzFreeContext
0x18001d107  lea     rcx, [rbp+60h+var_80]; struct _KDC_AUTHZ_GROUP_BUFFERS *
0x18001d10b  call    ?KdcFreeAuthzInfo@@YAXPEAU_KDC_AUTHZ_GROUP_BUFFERS@@@Z; KdcFreeAuthzInfo(_KDC_AUTHZ_GROUP_BUFFERS *)
0x18001d110  xor     eax, eax
0x18001d112  jmp     short loc_18001D166
0x18001d114  lea     rax, WPP_GLOBAL_Control
0x18001d11b  mov     rcx, cs:WPP_GLOBAL_Control
0x18001d122  cmp     rcx, rax
0x18001d125  jz      short loc_18001D145
0x18001d127  test    byte ptr [rcx+1Ch], 1
0x18001d12b  jz      short loc_18001D145
0x18001d12d  mov     edx, 4Eh ; 'N'
0x18001d132  mov     r9d, ebx
0x18001d135  lea     r8, WPP_8db5ad0f30c43630f747b6011b5f6d43_Traceguids
0x18001d13c  mov     rcx, [rcx+10h]
0x18001d140  call    WPP_SF_d
0x18001d145  mov     dword ptr [rsi], 0C00000E5h
0x18001d14b  mov     rcx, [rsp+160h+hAuthzClientContext]; hAuthzClientContext
0x18001d150  test    rcx, rcx
0x18001d153  jz      short loc_18001D15B
0x18001d155  call    cs:__imp_AuthzFreeContext
0x18001d15b  lea     rcx, [rbp+60h+var_80]; struct _KDC_AUTHZ_GROUP_BUFFERS *
0x18001d15f  call    ?KdcFreeAuthzInfo@@YAXPEAU_KDC_AUTHZ_GROUP_BUFFERS@@@Z; KdcFreeAuthzInfo(_KDC_AUTHZ_GROUP_BUFFERS *)
0x18001d164  mov     eax, ebx
0x18001d166  add     rsp, 138h
0x18001d16d  pop     r15
0x18001d16f  pop     r14
0x18001d171  pop     rdi
0x18001d172  pop     rsi
0x18001d173  pop     rbx
0x18001d174  pop     rbp
0x18001d175  retn
```
