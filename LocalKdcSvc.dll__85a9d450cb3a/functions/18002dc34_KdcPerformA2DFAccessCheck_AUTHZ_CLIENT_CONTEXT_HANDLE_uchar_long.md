# KdcPerformA2DFAccessCheck(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,uchar *,long *)

- ea: `0x18002dc34`
- end: `0x18002dd41`
- name: `?KdcPerformA2DFAccessCheck@@YAJPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAEPEAJ@Z`
- size: `269`
- prototype: `__int64 __fastcall(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext, PSECURITY_DESCRIPTOR pSecurityDescriptor, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180024ffc`

## callees

- `0x1800101ec`
- `0x18002dc34`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcee`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcee`
- `AUTHZ!AuthzAccessCheck` at `0x18002dccb`
- `AUTHZ!AuthzAccessCheck` at `0x18002dccb`

## pseudocode

```c
__int64 __fastcall KdcPerformA2DFAccessCheck(
        AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        int *a3)
{
  DWORD LastError; // eax
  __int64 result; // rax
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+50h] [rbp+7h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+70h] [rbp+27h] BYREF
  int v8; // [rsp+B0h] [rbp+67h] BYREF
  int v9; // [rsp+C0h] [rbp+77h] BYREF

  v9 = 5;
  *(&pReply.ResultListLength + 1) = 0;
  pReply.SaclEvaluationResults = 0;
  *(&pRequest.DesiredAccess + 1) = 0;
  *(&pRequest.ObjectTypeListLength + 1) = 0;
  v8 = 0;
  *a3 = 0;
  if ( !hAuthzClientContext )
    *a3 = -1073740781;
  pReply.GrantedAccessMask = (PACCESS_MASK)&v8;
  pRequest.DesiredAccess = 256;
  pReply.Error = (PDWORD)&v9;
  pRequest.OptionalArguments = 0;
  memset(&pRequest.PrincipalSelfSid, 0, 20);
  pReply.ResultListLength = 1;
  if ( !AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 107, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, LastError);
    }
    goto LABEL_8;
  }
  if ( *pReply.Error )
  {
LABEL_8:
    result = 12;
    *a3 = -1073740781;
    return result;
  }
  return 0;
}

```

## disassembly

```asm
0x18002dc34  mov     [rsp-8+arg_8], rbx
0x18002dc39  mov     [rsp-8+arg_18], rdi
0x18002dc3e  push    rbp
0x18002dc3f  lea     rbp, [rsp-57h]
0x18002dc44  sub     rsp, 0A0h
0x18002dc4b  xor     edi, edi
0x18002dc4d  mov     [rbp+57h+arg_10], 5
0x18002dc54  mov     dword ptr [rbp+57h+var_50+4], edi
0x18002dc57  mov     rbx, r8
0x18002dc5a  mov     [rbp+57h+var_50.SaclEvaluationResults], rdi
0x18002dc5e  mov     dword ptr [rbp+57h+pRequest+4], edi
0x18002dc61  mov     dword ptr [rbp+57h+pRequest+1Ch], edi
0x18002dc64  mov     [rbp+57h+arg_0], edi
0x18002dc67  mov     [r8], edi
0x18002dc6a  test    rcx, rcx
0x18002dc6d  jnz     short loc_18002DC76
0x18002dc6f  mov     dword ptr [r8], 0C0000413h
0x18002dc76  mov     [rsp+0A0h+phAccessCheckResults], rdi; phAccessCheckResults
0x18002dc7b  lea     rax, [rbp+57h+arg_0]
0x18002dc7f  mov     [rbp+57h+var_50.GrantedAccessMask], rax
0x18002dc83  lea     r8, [rbp+57h+pRequest]; pRequest
0x18002dc87  lea     rax, [rbp+57h+arg_10]
0x18002dc8b  mov     [rbp+57h+pRequest.DesiredAccess], 100h
0x18002dc92  mov     [rbp+57h+var_50.Error], rax
0x18002dc96  xor     r9d, r9d; hAuditEvent
0x18002dc99  lea     rax, [rbp+57h+var_50]
0x18002dc9d  mov     [rbp+57h+pRequest.ObjectTypeList], rdi
0x18002dca1  mov     [rsp+0A0h+pReply], rax; pReply
0x18002dca6  mov     [rsp+0A0h+OptionalSecurityDescriptorCount], edi; OptionalSecurityDescriptorCount
0x18002dcaa  mov     [rsp+0A0h+OptionalSecurityDescriptorArray], rdi; OptionalSecurityDescriptorArray
0x18002dcaf  mov     [rsp+0A0h+pSecurityDescriptor], rdx; pSecurityDescriptor
0x18002dcb4  mov     rdx, rcx; hAuthzClientContext
0x18002dcb7  xor     ecx, ecx; Flags
0x18002dcb9  mov     [rbp+57h+pRequest.ObjectTypeListLength], edi
0x18002dcbc  mov     [rbp+57h+pRequest.OptionalArguments], rdi
0x18002dcc0  mov     [rbp+57h+pRequest.PrincipalSelfSid], rdi
0x18002dcc4  mov     [rbp+57h+var_50.ResultListLength], 1
0x18002dccb  call    cs:__imp_AuthzAccessCheck
0x18002dcd1  test    eax, eax
0x18002dcd3  jnz     short loc_18002DD15
0x18002dcd5  mov     rax, cs:WPP_GLOBAL_Control
0x18002dcdc  lea     rcx, WPP_GLOBAL_Control
0x18002dce3  cmp     rax, rcx
0x18002dce6  jz      short loc_18002DD1D
0x18002dce8  test    byte ptr [rax+1Ch], 1
0x18002dcec  jz      short loc_18002DD1D
0x18002dcee  call    cs:__imp_GetLastError
0x18002dcf4  mov     rcx, cs:WPP_GLOBAL_Control
0x18002dcfb  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x18002dd02  mov     edx, 6Bh ; 'k'
0x18002dd07  mov     r9d, eax
0x18002dd0a  mov     rcx, [rcx+10h]
0x18002dd0e  call    WPP_SF_d
0x18002dd13  jmp     short loc_18002DD1D
0x18002dd15  mov     rax, [rbp+57h+var_50.Error]
0x18002dd19  cmp     [rax], edi
0x18002dd1b  jz      short loc_18002DD2A
0x18002dd1d  mov     eax, 0Ch
0x18002dd22  mov     dword ptr [rbx], 0C0000413h
0x18002dd28  jmp     short loc_18002DD2C
0x18002dd2a  mov     eax, edi
0x18002dd2c  lea     r11, [rsp+0A0h+var_s0]
0x18002dd34  mov     rbx, [r11+18h]
0x18002dd38  mov     rdi, [r11+28h]
0x18002dd3c  mov     rsp, r11
0x18002dd3f  pop     rbp
0x18002dd40  retn
```
