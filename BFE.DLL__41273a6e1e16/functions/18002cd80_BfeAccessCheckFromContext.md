# BfeAccessCheckFromContext

- ea: `0x18002cd80`
- end: `0x18002d018`
- name: `BfeAccessCheckFromContext`
- size: `664`
- prototype: `__int64 __fastcall(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18003592c`
- `0x18004d220`

## callees

- `0x18000fb34`
- `0x180011510`
- `0x180012d8c`
- `0x1800133a0`
- `0x18002cd80`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002ce8e`
- `AUTHZ!AuthzAccessCheck` at `0x18002ce34`
- `AUTHZ!AuthzAccessCheck` at `0x18002ce34`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18002cde2`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18002cde2`

## string_xrefs

- `0x18002ced6`: `BfeAccessCheckFromContext`
- `0x18002cea3`: `AuthzAccessCheck`
- `0x18002cffd`: `AuthzAccessCheck`

## pseudocode

```c
__int64 __fastcall BfeAccessCheckFromContext(
        AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        DWORD a3,
        _DWORD *a4)
{
  DWORD LastError; // eax
  int v9; // r8d
  __int64 v10; // rbx
  _QWORD *v11; // rcx
  __int64 v12; // rax
  int v13; // [rsp+50h] [rbp-79h] BYREF
  unsigned int v14; // [rsp+58h] [rbp-71h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+60h] [rbp-69h] BYREF
  DWORD AccessMask; // [rsp+80h] [rbp-49h] BYREF
  int v17; // [rsp+88h] [rbp-41h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+90h] [rbp-39h] BYREF
  _BYTE v19[16]; // [rsp+B8h] [rbp-11h] BYREF
  const char *v20; // [rsp+C8h] [rbp-1h]
  __int64 v21; // [rsp+D0h] [rbp+7h]
  int *v22; // [rsp+D8h] [rbp+Fh]
  __int64 v23; // [rsp+E0h] [rbp+17h]

  AccessMask = a3;
  v14 = 5;
  memset(&pRequest, 0, sizeof(pRequest));
  v17 = 0;
  *(&pReply.ResultListLength + 1) = 0;
  pReply.SaclEvaluationResults = 0;
  MapGenericMask(&AccessMask, (PGENERIC_MAPPING)&GenericMapping);
  pRequest.DesiredAccess = AccessMask;
  pReply.GrantedAccessMask = (PACCESS_MASK)&v17;
  pReply.ResultListLength = 1;
  pReply.Error = &v14;
  if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
  {
    if ( a4 )
    {
      *a4 = v14 == 0;
      return 0;
    }
    if ( !v14 )
      return 0;
    v12 = WfpReportSysErrorAsWinError(0, "AuthzAccessCheck", v14);
    v11 = WPP_GLOBAL_Control;
    v10 = v12;
  }
  else
  {
    LastError = GetLastError();
    LODWORD(v10) = LastError;
    v11 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
      && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u
      && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_SsD(*((_QWORD *)WPP_GLOBAL_Control + 2), 23, v9, 0, (__int64)"AuthzAccessCheck", LastError);
      v11 = WPP_GLOBAL_Control;
    }
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
    {
      v13 = v10;
      v22 = &v13;
      v20 = "AuthzAccessCheck";
      v21 = 17;
      v23 = 4;
      McGenEventWrite_EtwEventWriteTransfer(
        (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
        (unsigned int)WFP_USERMODE_ERROR,
        v9,
        3,
        (__int64)v19);
      v11 = WPP_GLOBAL_Control;
    }
    if ( (int)v10 > 0 )
      LODWORD(v10) = (unsigned __int16)v10 | 0x80070000;
    v10 = (int)v10;
  }
  if ( v10 )
  {
    if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) >= 2u && (*((_BYTE *)v11 + 28) & 1) != 0 )
      WPP_SF_Ssd(v11[2], 26, v9, 0, (__int64)"BfeAccessCheckFromContext", v10);
    if ( gWfpLogUserModeErrors )
    {
      if ( (byte_1800F6115 & 1) != 0 )
      {
        v13 = v10;
        v22 = &v13;
        v20 = "BfeAccessCheckFromContext";
        v21 = 26;
        v23 = 4;
        McGenEventWrite_EtwEventWriteTransfer(
          (unsigned int)&MICROSOFT_WFP_PROVIDER_Context,
          (unsigned int)WFP_USERMODE_ERROR,
          v9,
          3,
          (__int64)v19);
      }
    }
  }
  return v10;
}

```

## disassembly

```asm
0x18002cd80  push    rbp
0x18002cd82  push    rbx
0x18002cd83  push    rsi
0x18002cd84  push    rdi
0x18002cd85  push    r14
0x18002cd87  push    r15
0x18002cd89  lea     rbp, [rsp-2Fh]
0x18002cd8e  sub     rsp, 0F8h
0x18002cd95  mov     rax, cs:__security_cookie
0x18002cd9c  xor     rax, rsp
0x18002cd9f  mov     [rbp+57h+var_38], rax
0x18002cda3  xorps   xmm0, xmm0
0x18002cda6  mov     [rbp+57h+AccessMask], r8d
0x18002cdaa  mov     rbx, rdx
0x18002cdad  mov     [rbp+57h+var_C8], 5
0x18002cdb4  mov     rdi, rcx
0x18002cdb7  lea     rdx, GenericMapping; GenericMapping
0x18002cdbe  xor     eax, eax
0x18002cdc0  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18002cdc4  xor     r14d, r14d
0x18002cdc7  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x18002cdcb  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x18002cdcf  mov     [rbp+57h+var_98], r14d
0x18002cdd3  mov     rsi, r9
0x18002cdd6  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x18002cdda  movups  xmmword ptr [rbp+57h+var_C0.ResultListLength], xmm0
0x18002cdde  movups  xmmword ptr [rbp+57h+var_C0.SaclEvaluationResults], xmm0
0x18002cde2  call    cs:__imp_MapGenericMask
0x18002cde9  nop     dword ptr [rax+rax+00h]
0x18002cdee  mov     eax, [rbp+57h+AccessMask]
0x18002cdf1  lea     r8, [rbp+57h+pRequest]; pRequest
0x18002cdf5  mov     [rbp+57h+pRequest.DesiredAccess], eax
0x18002cdf8  xor     r9d, r9d; hAuditEvent
0x18002cdfb  mov     [rsp+120h+phAccessCheckResults], r14; phAccessCheckResults
0x18002ce00  lea     rax, [rbp+57h+var_98]
0x18002ce04  mov     [rbp+57h+var_C0.GrantedAccessMask], rax
0x18002ce08  mov     rdx, rdi; hAuthzClientContext
0x18002ce0b  lea     rax, [rbp+57h+var_C8]
0x18002ce0f  mov     [rbp+57h+var_C0.ResultListLength], 1
0x18002ce16  mov     [rbp+57h+var_C0.Error], rax
0x18002ce1a  xor     ecx, ecx; Flags
0x18002ce1c  lea     rax, [rbp+57h+var_C0]
0x18002ce20  mov     [rsp+120h+pReply], rax; pReply
0x18002ce25  mov     [rsp+120h+OptionalSecurityDescriptorCount], r14d; OptionalSecurityDescriptorCount
0x18002ce2a  mov     [rsp+120h+OptionalSecurityDescriptorArray], r14; OptionalSecurityDescriptorArray
0x18002ce2f  mov     [rsp+120h+pSecurityDescriptor], rbx; pSecurityDescriptor
0x18002ce34  call    cs:__imp_AuthzAccessCheck
0x18002ce3b  nop     dword ptr [rax+rax+00h]
0x18002ce40  lea     r15, WPP_GLOBAL_Control
0x18002ce47  test    eax, eax
0x18002ce49  jz      short loc_18002CE8E
0x18002ce4b  mov     ecx, r14d
0x18002ce4e  test    rsi, rsi
0x18002ce51  jnz     short loc_18002CE80
0x18002ce53  mov     r8d, [rbp+57h+var_C8]
0x18002ce57  test    r8d, r8d
0x18002ce5a  jnz     loc_18002CFFD
0x18002ce60  mov     rax, rcx
0x18002ce63  mov     rcx, [rbp+57h+var_38]
0x18002ce67  xor     rcx, rsp; StackCookie
0x18002ce6a  call    __security_check_cookie
0x18002ce6f  add     rsp, 0F8h
0x18002ce76  pop     r15
0x18002ce78  pop     r14
0x18002ce7a  pop     rdi
0x18002ce7b  pop     rsi
0x18002ce7c  pop     rbx
0x18002ce7d  pop     rbp
0x18002ce7e  retn
0x18002ce80  cmp     [rbp+57h+var_C8], r14d
0x18002ce84  mov     eax, r14d
0x18002ce87  setz    al
0x18002ce8a  mov     [rsi], eax
0x18002ce8c  jmp     short loc_18002CE60
0x18002ce8e  call    cs:__imp_GetLastError
0x18002ce95  nop     dword ptr [rax+rax+00h]
0x18002ce9a  mov     ebx, eax
0x18002ce9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cea3  lea     rdi, aAuthzaccessche; "AuthzAccessCheck"
0x18002ceaa  cmp     rcx, r15
0x18002cead  jz      short loc_18002CEB9
0x18002ceaf  cmp     byte ptr [rcx+19h], 2
0x18002ceb3  jnb     loc_18002CF65
0x18002ceb9  cmp     cs:gWfpLogUserModeErrors, r14d
0x18002cec0  jnz     loc_18002CF95
0x18002cec6  test    ebx, ebx
0x18002cec8  jg      loc_18002CFEF
0x18002cece  movsxd  rbx, ebx
0x18002ced1  test    rbx, rbx
0x18002ced4  jz      short loc_18002CF11
0x18002ced6  lea     rdi, aBfeaccesscheck_0; "BfeAccessCheckFromContext"
0x18002cedd  cmp     rcx, r15
0x18002cee0  jz      short loc_18002CF08
0x18002cee2  cmp     byte ptr [rcx+19h], 2
0x18002cee6  jb      short loc_18002CF08
0x18002cee8  test    byte ptr [rcx+1Ch], 1
0x18002ceec  jz      short loc_18002CF08
0x18002ceee  mov     rcx, [rcx+10h]
0x18002cef2  mov     edx, 1Ah
0x18002cef7  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], ebx
0x18002cefb  xor     r9d, r9d
0x18002cefe  mov     [rsp+120h+pSecurityDescriptor], rdi
0x18002cf03  call    WPP_SF_Ssd
0x18002cf08  cmp     cs:gWfpLogUserModeErrors, r14d
0x18002cf0f  jnz     short loc_18002CF19
0x18002cf11  mov     rax, rbx
0x18002cf14  jmp     loc_18002CE63
0x18002cf19  test    cs:byte_1800F6115, 1
0x18002cf20  jz      short loc_18002CF11
0x18002cf22  lea     rax, [rbp+57h+var_D0]
0x18002cf26  mov     [rbp+57h+var_D0], ebx
0x18002cf29  mov     [rbp+57h+var_48], rax
0x18002cf2d  lea     rdx, WFP_USERMODE_ERROR
0x18002cf34  lea     rax, [rbp+57h+var_68]
0x18002cf38  mov     [rbp+57h+var_58], rdi
0x18002cf3c  mov     r9d, 3
0x18002cf42  mov     [rsp+120h+pSecurityDescriptor], rax
0x18002cf47  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18002cf4e  mov     [rbp+57h+var_50], 1Ah
0x18002cf56  mov     [rbp+57h+var_40], 4
0x18002cf5e  call    McGenEventWrite_EtwEventWriteTransfer
0x18002cf63  jmp     short loc_18002CF11
0x18002cf65  test    byte ptr [rcx+1Ch], 1
0x18002cf69  jz      loc_18002CEB9
0x18002cf6f  mov     rcx, [rcx+10h]
0x18002cf73  mov     edx, 17h
0x18002cf78  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], ebx
0x18002cf7c  xor     r9d, r9d
0x18002cf7f  mov     [rsp+120h+pSecurityDescriptor], rdi
0x18002cf84  call    WPP_SF_SsD
0x18002cf89  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cf90  jmp     loc_18002CEB9
0x18002cf95  test    cs:byte_1800F6115, 1
0x18002cf9c  jz      loc_18002CEC6
0x18002cfa2  lea     rax, [rbp+57h+var_D0]
0x18002cfa6  mov     [rbp+57h+var_D0], ebx
0x18002cfa9  mov     [rbp+57h+var_48], rax
0x18002cfad  lea     rdx, WFP_USERMODE_ERROR
0x18002cfb4  lea     rax, [rbp+57h+var_68]
0x18002cfb8  mov     [rbp+57h+var_58], rdi
0x18002cfbc  mov     r9d, 3
0x18002cfc2  mov     [rsp+120h+pSecurityDescriptor], rax
0x18002cfc7  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18002cfce  mov     [rbp+57h+var_50], 11h
0x18002cfd6  mov     [rbp+57h+var_40], 4
0x18002cfde  call    McGenEventWrite_EtwEventWriteTransfer
0x18002cfe3  mov     rcx, cs:WPP_GLOBAL_Control
0x18002cfea  jmp     loc_18002CEC6
0x18002cfef  movzx   ebx, bx
0x18002cff2  or      ebx, 80070000h
0x18002cff8  jmp     loc_18002CECE
0x18002cffd  lea     rdx, aAuthzaccessche; "AuthzAccessCheck"
0x18002d004  call    WfpReportSysErrorAsWinError
0x18002d009  mov     rcx, cs:WPP_GLOBAL_Control
0x18002d010  mov     rbx, rax
0x18002d013  jmp     loc_18002CED1
```
