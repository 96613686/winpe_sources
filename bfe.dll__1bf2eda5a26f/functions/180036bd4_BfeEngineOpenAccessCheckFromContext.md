# BfeEngineOpenAccessCheckFromContext

- ea: `0x180036bd4`
- end: `0x180036e1e`
- name: `BfeEngineOpenAccessCheckFromContext`
- size: `586`
- prototype: `__int64 __fastcall(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext)`
- caller_count: `1`
- callee_count: `8`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004aeb8`

## callees

- `0x18000f1a8`
- `0x180010ad0`
- `0x18001236c`
- `0x180018b74`
- `0x18002b3f0`
- `0x180036bd4`
- `0x180058b30`
- `0x1800595ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036bfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180036bfe`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036d98`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180036d98`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d20`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180036d20`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180036c20`
- `RPCRT4!RpcServerInqCallAttributesW` at `0x180036c20`
- `AUTHZ!AuthzAccessCheck` at `0x180036cd0`
- `AUTHZ!AuthzAccessCheck` at `0x180036cd0`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180036c74`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x180036c74`

## string_xrefs

- `0x180036d4b`: `BfeAccessCheckFromContext`
- `0x180036d29`: `AuthzAccessCheck`
- `0x180036e0d`: `BfeEngineOpenAccessCheckFromContext`

## pseudocode

```c
__int64 __fastcall BfeEngineOpenAccessCheckFromContext(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext)
{
  __int64 v2; // rbx
  void *pSecurityDescriptor; // rbx
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

  EnterCriticalSection((LPCRITICAL_SECTION)&qword_1800F2668[131]);
  memset_0(v17, 0, 0x6Cu);
  RpcCallAttributes = 2;
  if ( RpcServerInqCallAttributesW(0, &RpcCallAttributes) || (v2 = 0, !v18) )
  {
    pSecurityDescriptor = (void *)qword_1800F2668[173];
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
        if ( MEMORY[0x1800EF078] && (qword_1800F2668[337] & 0x10000000000LL) != 0 )
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
      v5 = BfeAccessCheckFromContext(hAuthzClientContext, (PSECURITY_DESCRIPTOR)qword_1800F2668[174], 1u, 0);
      v2 = v5;
      if ( v5 )
        WfpReportError(v5, "BfeIsAdminContext");
    }
  }
LABEL_15:
  LeaveCriticalSection((LPCRITICAL_SECTION)&qword_1800F2668[131]);
  if ( v2 )
    WfpReportError(v2, "BfeEngineOpenAccessCheckFromContext");
  return v2;
}

```

## disassembly

```asm
0x180036bd4  push    rbp
0x180036bd6  push    rbx
0x180036bd7  push    rdi
0x180036bd8  push    r12
0x180036bda  lea     rbp, [rsp-78h]
0x180036bdf  sub     rsp, 178h
0x180036be6  mov     rax, cs:__security_cookie
0x180036bed  xor     rax, rsp
0x180036bf0  mov     [rbp+90h+var_30], rax
0x180036bf4  mov     rdi, rcx
0x180036bf7  lea     rcx, qword_1800F2668+418h; lpCriticalSection
0x180036bfe  call    cs:__imp_EnterCriticalSection
0x180036c04  xor     edx, edx; Val
0x180036c06  lea     rcx, [rbp+90h+var_CC]; void *
0x180036c0a  lea     r8d, [rdx+6Ch]; Size
0x180036c0e  call    memset_0
0x180036c13  lea     rdx, [rbp+90h+RpcCallAttributes]; RpcCallAttributes
0x180036c17  mov     [rbp+90h+RpcCallAttributes], 2
0x180036c1e  xor     ecx, ecx; ClientBinding
0x180036c20  call    cs:__imp_RpcServerInqCallAttributesW
0x180036c26  test    eax, eax
0x180036c28  jnz     short loc_180036C35
0x180036c2a  xor     ebx, ebx
0x180036c2c  cmp     [rbp+90h+var_9C], ebx
0x180036c2f  jnz     loc_180036D91
0x180036c35  mov     rbx, cs:qword_1800F2668+568h
0x180036c3c  lea     rdx, GenericMapping; GenericMapping
0x180036c43  xorps   xmm0, xmm0
0x180036c46  mov     [rbp+90h+AccessMask], 40h ; '@'
0x180036c4d  xor     eax, eax
0x180036c4f  mov     [rsp+190h+var_138], 5
0x180036c57  lea     rcx, [rbp+90h+AccessMask]; AccessMask
0x180036c5b  mov     [rbp+90h+pRequest.OptionalArguments], rax
0x180036c5f  movups  xmmword ptr [rbp+90h+pRequest.DesiredAccess], xmm0
0x180036c63  mov     [rbp+90h+var_108], eax
0x180036c66  movups  xmmword ptr [rbp+90h+pRequest.ObjectTypeList], xmm0
0x180036c6a  movups  xmmword ptr [rsp+190h+var_130.ResultListLength], xmm0
0x180036c6f  movups  xmmword ptr [rsp+190h+var_130.SaclEvaluationResults], xmm0
0x180036c74  call    cs:__imp_MapGenericMask
0x180036c7a  mov     eax, [rbp+90h+AccessMask]
0x180036c7d  lea     r8, [rbp+90h+pRequest]; pRequest
0x180036c81  mov     [rbp+90h+pRequest.DesiredAccess], eax
0x180036c84  xor     r9d, r9d; hAuditEvent
0x180036c87  mov     [rsp+190h+phAccessCheckResults], 0; phAccessCheckResults
0x180036c90  lea     rax, [rbp+90h+var_108]
0x180036c94  mov     [rsp+190h+var_130.GrantedAccessMask], rax
0x180036c99  mov     rdx, rdi; hAuthzClientContext
0x180036c9c  lea     rax, [rsp+190h+var_138]
0x180036ca1  mov     [rsp+190h+var_130.ResultListLength], 1
0x180036ca9  mov     [rsp+190h+var_130.Error], rax
0x180036cae  xor     ecx, ecx; Flags
0x180036cb0  lea     rax, [rsp+190h+var_130]
0x180036cb5  mov     [rsp+190h+pReply], rax; pReply
0x180036cba  mov     [rsp+190h+OptionalSecurityDescriptorCount], 0; OptionalSecurityDescriptorCount
0x180036cc2  mov     [rsp+190h+OptionalSecurityDescriptorArray], 0; OptionalSecurityDescriptorArray
0x180036ccb  mov     [rsp+190h+pSecurityDescriptor], rbx; pSecurityDescriptor
0x180036cd0  call    cs:__imp_AuthzAccessCheck
0x180036cd6  test    eax, eax
0x180036cd8  jz      short loc_180036D20
0x180036cda  xor     eax, eax
0x180036cdc  cmp     [rsp+190h+var_138], eax
0x180036ce0  setz    al
0x180036ce3  xor     ebx, ebx
0x180036ce5  test    eax, eax
0x180036ce7  jnz     loc_180036D91
0x180036ced  mov     rdx, cs:qword_1800F2668+570h; pSecurityDescriptor
0x180036cf4  lea     r8d, [rax+1]
0x180036cf8  xor     r9d, r9d
0x180036cfb  mov     rcx, rdi; hAuthzClientContext
0x180036cfe  call    BfeAccessCheckFromContext
0x180036d03  mov     rbx, rax
0x180036d06  test    rax, rax
0x180036d09  jz      loc_180036D91
0x180036d0f  lea     rdx, aBfeisadmincont; "BfeIsAdminContext"
0x180036d16  mov     rcx, rax
0x180036d19  call    WfpReportError
0x180036d1e  jmp     short loc_180036D91
0x180036d20  call    cs:__imp_GetLastError
0x180036d26  mov     r8d, eax
0x180036d29  lea     rdx, aAuthzaccessche; "AuthzAccessCheck"
0x180036d30  call    WfpReportSysErrorAsWinError
0x180036d35  mov     rbx, rax
0x180036d38  test    rax, rax
0x180036d3b  jz      short loc_180036D86
0x180036d3d  mov     rcx, cs:WPP_GLOBAL_Control
0x180036d44  lea     rax, WPP_GLOBAL_Control
0x180036d4b  lea     r12, aBfeaccesscheck_0; "BfeAccessCheckFromContext"
0x180036d52  cmp     rcx, rax
0x180036d55  jz      short loc_180036D7D
0x180036d57  cmp     byte ptr [rcx+19h], 2
0x180036d5b  jb      short loc_180036D7D
0x180036d5d  test    byte ptr [rcx+1Ch], 1
0x180036d61  jz      short loc_180036D7D
0x180036d63  mov     rcx, [rcx+10h]
0x180036d67  mov     edx, 1Ah
0x180036d6c  mov     dword ptr [rsp+190h+OptionalSecurityDescriptorArray], ebx
0x180036d70  xor     r9d, r9d
0x180036d73  mov     [rsp+190h+pSecurityDescriptor], r12
0x180036d78  call    WPP_SF_Ssd
0x180036d7d  cmp     dword ptr cs:1800EF078h, 0
0x180036d84  jnz     short loc_180036DBF
0x180036d86  xor     eax, eax
0x180036d88  test    rbx, rbx
0x180036d8b  jz      loc_180036CE5
0x180036d91  lea     rcx, qword_1800F2668+418h; lpCriticalSection
0x180036d98  call    cs:__imp_LeaveCriticalSection
0x180036d9e  test    rbx, rbx
0x180036da1  jnz     short loc_180036E0D
0x180036da3  mov     rax, rbx
0x180036da6  mov     rcx, [rbp+90h+var_30]
0x180036daa  xor     rcx, rsp; StackCookie
0x180036dad  call    __security_check_cookie
0x180036db2  add     rsp, 178h
0x180036db9  pop     r12
0x180036dbb  pop     rdi
0x180036dbc  pop     rbx
0x180036dbd  pop     rbp
0x180036dbe  retn
0x180036dbf  test    byte ptr cs:qword_1800F2668+0A8Dh, 1
0x180036dc6  jz      short loc_180036D86
0x180036dc8  lea     rax, [rsp+190h+var_140]
0x180036dcd  mov     [rsp+190h+var_140], ebx
0x180036dd1  mov     [rbp+90h+var_40], rax
0x180036dd5  lea     rdx, WFP_USERMODE_ERROR
0x180036ddc  lea     rax, [rbp+90h+var_60]
0x180036de0  mov     [rbp+90h+var_50], r12
0x180036de4  mov     r9d, 3
0x180036dea  mov     [rsp+190h+pSecurityDescriptor], rax
0x180036def  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x180036df6  mov     [rbp+90h+var_48], 1Ah
0x180036dfe  mov     [rbp+90h+var_38], 4
0x180036e06  call    McGenEventWrite_EtwEventWriteTransfer
0x180036e0b  jmp     short loc_180036D91
0x180036e0d  lea     rdx, aBfeengineopena; "BfeEngineOpenAccessCheckFromContext"
0x180036e14  mov     rcx, rbx
0x180036e17  call    WfpReportError
0x180036e1c  jmp     short loc_180036DA3
```
