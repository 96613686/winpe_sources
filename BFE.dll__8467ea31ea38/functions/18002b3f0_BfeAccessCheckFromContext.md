# BfeAccessCheckFromContext

- ea: `0x18002b3f0`
- end: `0x18002b675`
- name: `BfeAccessCheckFromContext`
- size: `645`
- prototype: `__int64 __fastcall(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext, PSECURITY_DESCRIPTOR pSecurityDescriptor, DWORD, _DWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180036bd4`
- `0x18004b3c0`

## callees

- `0x18000f1a8`
- `0x180010ad0`
- `0x18001236c`
- `0x180012950`
- `0x18002b3f0`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b4f1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b4f1`
- `AUTHZ!AuthzAccessCheck` at `0x18002b49e`
- `AUTHZ!AuthzAccessCheck` at `0x18002b49e`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18002b452`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18002b452`

## string_xrefs

- `0x18002b533`: `BfeAccessCheckFromContext`
- `0x18002b500`: `AuthzAccessCheck`
- `0x18002b65a`: `AuthzAccessCheck`

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
    if ( gWfpLogUserModeErrors && (byte_1800F30F5 & 1) != 0 )
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
      if ( (byte_1800F30F5 & 1) != 0 )
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
0x18002b3f0  push    rbp
0x18002b3f2  push    rbx
0x18002b3f3  push    rsi
0x18002b3f4  push    rdi
0x18002b3f5  push    r14
0x18002b3f7  push    r15
0x18002b3f9  lea     rbp, [rsp-2Fh]
0x18002b3fe  sub     rsp, 0F8h
0x18002b405  mov     rax, cs:__security_cookie
0x18002b40c  xor     rax, rsp
0x18002b40f  mov     [rbp+57h+var_38], rax
0x18002b413  xorps   xmm0, xmm0
0x18002b416  mov     [rbp+57h+AccessMask], r8d
0x18002b41a  mov     rbx, rdx
0x18002b41d  mov     [rbp+57h+var_C8], 5
0x18002b424  mov     rdi, rcx
0x18002b427  lea     rdx, GenericMapping; GenericMapping
0x18002b42e  xor     eax, eax
0x18002b430  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18002b434  xor     r14d, r14d
0x18002b437  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x18002b43b  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x18002b43f  mov     [rbp+57h+var_98], r14d
0x18002b443  mov     rsi, r9
0x18002b446  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x18002b44a  movups  xmmword ptr [rbp+57h+var_C0.ResultListLength], xmm0
0x18002b44e  movups  xmmword ptr [rbp+57h+var_C0.SaclEvaluationResults], xmm0
0x18002b452  call    cs:__imp_MapGenericMask
0x18002b458  mov     eax, [rbp+57h+AccessMask]
0x18002b45b  lea     r8, [rbp+57h+pRequest]; pRequest
0x18002b45f  mov     [rbp+57h+pRequest.DesiredAccess], eax
0x18002b462  xor     r9d, r9d; hAuditEvent
0x18002b465  mov     [rsp+120h+phAccessCheckResults], r14; phAccessCheckResults
0x18002b46a  lea     rax, [rbp+57h+var_98]
0x18002b46e  mov     [rbp+57h+var_C0.GrantedAccessMask], rax
0x18002b472  mov     rdx, rdi; hAuthzClientContext
0x18002b475  lea     rax, [rbp+57h+var_C8]
0x18002b479  mov     [rbp+57h+var_C0.ResultListLength], 1
0x18002b480  mov     [rbp+57h+var_C0.Error], rax
0x18002b484  xor     ecx, ecx; Flags
0x18002b486  lea     rax, [rbp+57h+var_C0]
0x18002b48a  mov     [rsp+120h+pReply], rax; pReply
0x18002b48f  mov     [rsp+120h+OptionalSecurityDescriptorCount], r14d; OptionalSecurityDescriptorCount
0x18002b494  mov     [rsp+120h+OptionalSecurityDescriptorArray], r14; OptionalSecurityDescriptorArray
0x18002b499  mov     [rsp+120h+pSecurityDescriptor], rbx; pSecurityDescriptor
0x18002b49e  call    cs:__imp_AuthzAccessCheck
0x18002b4a4  lea     r15, WPP_GLOBAL_Control
0x18002b4ab  test    eax, eax
0x18002b4ad  jz      short loc_18002B4F1
0x18002b4af  mov     ecx, r14d
0x18002b4b2  test    rsi, rsi
0x18002b4b5  jnz     short loc_18002B4E3
0x18002b4b7  mov     r8d, [rbp+57h+var_C8]
0x18002b4bb  test    r8d, r8d
0x18002b4be  jnz     loc_18002B65A
0x18002b4c4  mov     rax, rcx
0x18002b4c7  mov     rcx, [rbp+57h+var_38]
0x18002b4cb  xor     rcx, rsp; StackCookie
0x18002b4ce  call    __security_check_cookie
0x18002b4d3  add     rsp, 0F8h
0x18002b4da  pop     r15
0x18002b4dc  pop     r14
0x18002b4de  pop     rdi
0x18002b4df  pop     rsi
0x18002b4e0  pop     rbx
0x18002b4e1  pop     rbp
0x18002b4e2  retn
0x18002b4e3  cmp     [rbp+57h+var_C8], r14d
0x18002b4e7  mov     eax, r14d
0x18002b4ea  setz    al
0x18002b4ed  mov     [rsi], eax
0x18002b4ef  jmp     short loc_18002B4C4
0x18002b4f1  call    cs:__imp_GetLastError
0x18002b4f7  mov     ebx, eax
0x18002b4f9  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b500  lea     rdi, aAuthzaccessche; "AuthzAccessCheck"
0x18002b507  cmp     rcx, r15
0x18002b50a  jz      short loc_18002B516
0x18002b50c  cmp     byte ptr [rcx+19h], 2
0x18002b510  jnb     loc_18002B5C2
0x18002b516  cmp     cs:gWfpLogUserModeErrors, r14d
0x18002b51d  jnz     loc_18002B5F2
0x18002b523  test    ebx, ebx
0x18002b525  jg      loc_18002B64C
0x18002b52b  movsxd  rbx, ebx
0x18002b52e  test    rbx, rbx
0x18002b531  jz      short loc_18002B56E
0x18002b533  lea     rdi, aBfeaccesscheck_0; "BfeAccessCheckFromContext"
0x18002b53a  cmp     rcx, r15
0x18002b53d  jz      short loc_18002B565
0x18002b53f  cmp     byte ptr [rcx+19h], 2
0x18002b543  jb      short loc_18002B565
0x18002b545  test    byte ptr [rcx+1Ch], 1
0x18002b549  jz      short loc_18002B565
0x18002b54b  mov     rcx, [rcx+10h]
0x18002b54f  mov     edx, 1Ah
0x18002b554  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], ebx
0x18002b558  xor     r9d, r9d
0x18002b55b  mov     [rsp+120h+pSecurityDescriptor], rdi
0x18002b560  call    WPP_SF_Ssd
0x18002b565  cmp     cs:gWfpLogUserModeErrors, r14d
0x18002b56c  jnz     short loc_18002B576
0x18002b56e  mov     rax, rbx
0x18002b571  jmp     loc_18002B4C7
0x18002b576  test    cs:byte_1800F30F5, 1
0x18002b57d  jz      short loc_18002B56E
0x18002b57f  lea     rax, [rbp+57h+var_D0]
0x18002b583  mov     [rbp+57h+var_D0], ebx
0x18002b586  mov     [rbp+57h+var_48], rax
0x18002b58a  lea     rdx, WFP_USERMODE_ERROR
0x18002b591  lea     rax, [rbp+57h+var_68]
0x18002b595  mov     [rbp+57h+var_58], rdi
0x18002b599  mov     r9d, 3
0x18002b59f  mov     [rsp+120h+pSecurityDescriptor], rax
0x18002b5a4  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18002b5ab  mov     [rbp+57h+var_50], 1Ah
0x18002b5b3  mov     [rbp+57h+var_40], 4
0x18002b5bb  call    McGenEventWrite_EtwEventWriteTransfer
0x18002b5c0  jmp     short loc_18002B56E
0x18002b5c2  test    byte ptr [rcx+1Ch], 1
0x18002b5c6  jz      loc_18002B516
0x18002b5cc  mov     rcx, [rcx+10h]
0x18002b5d0  mov     edx, 17h
0x18002b5d5  mov     dword ptr [rsp+120h+OptionalSecurityDescriptorArray], ebx
0x18002b5d9  xor     r9d, r9d
0x18002b5dc  mov     [rsp+120h+pSecurityDescriptor], rdi
0x18002b5e1  call    WPP_SF_SsD
0x18002b5e6  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b5ed  jmp     loc_18002B516
0x18002b5f2  test    cs:byte_1800F30F5, 1
0x18002b5f9  jz      loc_18002B523
0x18002b5ff  lea     rax, [rbp+57h+var_D0]
0x18002b603  mov     [rbp+57h+var_D0], ebx
0x18002b606  mov     [rbp+57h+var_48], rax
0x18002b60a  lea     rdx, WFP_USERMODE_ERROR
0x18002b611  lea     rax, [rbp+57h+var_68]
0x18002b615  mov     [rbp+57h+var_58], rdi
0x18002b619  mov     r9d, 3
0x18002b61f  mov     [rsp+120h+pSecurityDescriptor], rax
0x18002b624  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18002b62b  mov     [rbp+57h+var_50], 11h
0x18002b633  mov     [rbp+57h+var_40], 4
0x18002b63b  call    McGenEventWrite_EtwEventWriteTransfer
0x18002b640  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b647  jmp     loc_18002B523
0x18002b64c  movzx   ebx, bx
0x18002b64f  or      ebx, 80070000h
0x18002b655  jmp     loc_18002B52B
0x18002b65a  lea     rdx, aAuthzaccessche; "AuthzAccessCheck"
0x18002b661  call    WfpReportSysErrorAsWinError
0x18002b666  mov     rcx, cs:WPP_GLOBAL_Control
0x18002b66d  mov     rbx, rax
0x18002b670  jmp     loc_18002B52E
```
