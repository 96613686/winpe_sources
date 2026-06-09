# PrincipalHasWriteAccess

- ea: `0x408841`
- end: `0x4088b0`
- name: `PrincipalHasWriteAccess`
- size: `111`
- prototype: `BOOL __fastcall(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext, PSECURITY_DESCRIPTOR pSecurityDescriptor, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x40895f`

## callees

- `0x408841`

## import_xrefs

- `AUTHZ!AuthzAccessCheck` at `0x40888d`
- `AUTHZ!AuthzAccessCheck` at `0x40888d`

## pseudocode

```c
BOOL __fastcall PrincipalHasWriteAccess(
        AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext,
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
        int a3)
{
  int v3; // esi
  _AUTHZ_ACCESS_REQUEST pRequest; // [esp+Ch] [ebp-30h] BYREF
  _AUTHZ_ACCESS_REPLY pReply; // [esp+20h] [ebp-1Ch] BYREF
  int v7; // [esp+30h] [ebp-Ch] BYREF
  int v8; // [esp+34h] [ebp-8h] BYREF

  pRequest.DesiredAccess = 0x2000000;
  pReply.SaclEvaluationResults = 0;
  pReply.GrantedAccessMask = (PACCESS_MASK)&v8;
  v3 = 0;
  v8 = 0;
  pReply.Error = (PDWORD)&v7;
  v7 = 0;
  memset(&pRequest.PrincipalSelfSid, 0, 16);
  pReply.ResultListLength = 1;
  if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &pReply, 0) )
    return (*pReply.GrantedAccessMask & 0x500D0000) != 0;
  return v3;
}

```

## disassembly

```asm
0x408841  mov     edi, edi
0x408843  push    ebp
0x408844  mov     ebp, esp
0x408846  sub     esp, 34h
0x408849  push    esi
0x40884a  push    edi
0x40884b  xor     edi, edi
0x40884d  mov     [ebp+pRequest.DesiredAccess], 2000000h
0x408854  push    edi; phAccessCheckResults
0x408855  lea     eax, [ebp+var_8]
0x408858  mov     [ebp+pReply.SaclEvaluationResults], edi
0x40885b  mov     [ebp+pReply.GrantedAccessMask], eax
0x40885e  mov     esi, edi
0x408860  lea     eax, [ebp+var_C]
0x408863  mov     [ebp+var_8], edi
0x408866  mov     [ebp+pReply.Error], eax
0x408869  lea     eax, [ebp+pReply]
0x40886c  push    eax; pReply
0x40886d  push    edi; OptionalSecurityDescriptorCount
0x40886e  push    edi; OptionalSecurityDescriptorArray
0x40886f  push    edx; pSecurityDescriptor
0x408870  push    edi; hAuditEvent
0x408871  lea     eax, [ebp+pRequest]
0x408874  mov     [ebp+var_C], edi
0x408877  push    eax; pRequest
0x408878  push    ecx; hAuthzClientContext
0x408879  push    edi; Flags
0x40887a  mov     [ebp+pRequest.PrincipalSelfSid], edi
0x40887d  mov     [ebp+pRequest.ObjectTypeList], edi
0x408880  mov     [ebp+pRequest.ObjectTypeListLength], edi
0x408883  mov     [ebp+pRequest.OptionalArguments], edi
0x408886  mov     [ebp+pReply.ResultListLength], 1
0x40888d  call    ds:__imp__AuthzAccessCheck@36; AuthzAccessCheck(x,x,x,x,x,x,x,x,x)
0x408893  test    eax, eax
0x408895  jz      short loc_4088A8
0x408897  mov     eax, [ebp+pReply.GrantedAccessMask]
0x40889a  mov     esi, [eax]
0x40889c  and     esi, 500D0000h
0x4088a2  neg     esi
0x4088a4  sbb     esi, esi
0x4088a6  neg     esi
0x4088a8  pop     edi
0x4088a9  mov     eax, esi
0x4088ab  pop     esi
0x4088ac  leave
0x4088ad  retn    4
```
