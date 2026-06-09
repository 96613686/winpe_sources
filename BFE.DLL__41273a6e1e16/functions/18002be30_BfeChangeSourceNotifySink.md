# BfeChangeSourceNotifySink

- ea: `0x18002be30`
- end: `0x18002c12a`
- name: `BfeChangeSourceNotifySink`
- size: `762`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b980`
- `0x18002ba60`
- `0x18002bb10`
- `0x18006a3a0`
- `0x18006dd00`
- `0x180075020`
- `0x1800754b0`

## callees

- `0x18000e250`
- `0x18000fb34`
- `0x180011510`
- `0x1800133a0`
- `0x18002be30`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c10a`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18002c10a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bf3e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002bf3e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bf5e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002bf5e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf8e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002bf8e`
- `AUTHZ!AuthzAccessCheck` at `0x18002bef7`
- `AUTHZ!AuthzAccessCheck` at `0x18002bef7`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18002bea5`
- `api-ms-win-security-base-l1-1-0!MapGenericMask` at `0x18002bea5`

## string_xrefs

- `0x18002bfd7`: `BfeAccessCheckFromContext`
- `0x18002bfaa`: `AuthzAccessCheck`

## pseudocode

```c
void __fastcall BfeChangeSourceNotifySink(__int64 a1, __int64 a2, void *a3)
{
  AUTHZ_CLIENT_CONTEXT_HANDLE v6; // rbx
  __int64 v7; // rbx
  DWORD LastError; // eax
  int v9; // r8d
  signed int v10; // ebx
  _QWORD *v11; // rcx
  bool v12; // zf
  signed int v13; // [rsp+50h] [rbp-69h] BYREF
  int v14; // [rsp+58h] [rbp-61h] BYREF
  struct _AUTHZ_ACCESS_REPLY pReply; // [rsp+60h] [rbp-59h] BYREF
  DWORD AccessMask; // [rsp+80h] [rbp-39h] BYREF
  int v17; // [rsp+88h] [rbp-31h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+90h] [rbp-29h] BYREF
  _BYTE v19[16]; // [rsp+B8h] [rbp-1h] BYREF
  const char *v20; // [rsp+C8h] [rbp+Fh]
  __int64 v21; // [rsp+D0h] [rbp+17h]
  signed int *v22; // [rsp+D8h] [rbp+1Fh]
  __int64 v23; // [rsp+E0h] [rbp+27h]

  if ( !a3 )
  {
LABEL_4:
    if ( !a2 || (*(_QWORD *)(a2 + 8) = *(_QWORD *)(a1 + 48), BfeNotifyOneWay(*(LPCRITICAL_SECTION *)(a1 + 40))) )
    {
      v7 = *(_QWORD *)(a1 + 40);
      EnterCriticalSection((LPCRITICAL_SECTION)v7);
      v12 = *(_DWORD *)(v7 + 84) == 0;
      *(_DWORD *)(v7 + 80) = 1;
      if ( v12 )
      {
        if ( SetEvent(*(HANDLE *)(v7 + 216)) )
          *(_DWORD *)(v7 + 84) = 1;
      }
      LeaveCriticalSection((LPCRITICAL_SECTION)v7);
    }
    return;
  }
  v6 = *(AUTHZ_CLIENT_CONTEXT_HANDLE *)(a1 + 56);
  AccessMask = 128;
  v14 = 5;
  v17 = 0;
  memset(&pRequest, 0, sizeof(pRequest));
  *(&pReply.ResultListLength + 1) = 0;
  pReply.SaclEvaluationResults = 0;
  MapGenericMask(&AccessMask, (PGENERIC_MAPPING)&GenericMapping);
  pRequest.DesiredAccess = AccessMask;
  pReply.GrantedAccessMask = (PACCESS_MASK)&v17;
  pReply.ResultListLength = 1;
  pReply.Error = (PDWORD)&v14;
  if ( AuthzAccessCheck(0, v6, &pRequest, 0, a3, 0, 0, &pReply, 0) )
  {
    if ( v14 )
      return;
    goto LABEL_4;
  }
  LastError = GetLastError();
  v10 = LastError;
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
  v12 = v10 == 0;
  if ( v10 > 0 )
  {
    v10 = (unsigned __int16)v10 | 0x80070000;
    v12 = v10 == 0;
  }
  if ( !v12 )
  {
    if ( v11 != &WPP_GLOBAL_Control && *((_BYTE *)v11 + 25) >= 2u && (*((_BYTE *)v11 + 28) & 1) != 0 )
      WPP_SF_Ssd(v11[2], 26, v9, 0, (__int64)"BfeAccessCheckFromContext", v10);
    if ( gWfpLogUserModeErrors && (byte_1800F6115 & 1) != 0 )
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

```

## disassembly

```asm
0x18002be30  mov     [rsp-8+arg_18], rbx
0x18002be35  push    rbp
0x18002be36  push    rsi
0x18002be37  push    rdi
0x18002be38  push    r14
0x18002be3a  push    r15
0x18002be3c  lea     rbp, [rsp-37h]
0x18002be41  sub     rsp, 0F0h
0x18002be48  mov     rax, cs:__security_cookie
0x18002be4f  xor     rax, rsp
0x18002be52  mov     [rbp+57h+var_28], rax
0x18002be56  mov     rsi, r8
0x18002be59  mov     r14, rdx
0x18002be5c  mov     rdi, rcx
0x18002be5f  test    r8, r8
0x18002be62  jz      loc_18002BF19
0x18002be68  mov     rbx, [rcx+38h]
0x18002be6c  lea     rdx, GenericMapping; GenericMapping
0x18002be73  xorps   xmm0, xmm0
0x18002be76  mov     [rbp+57h+AccessMask], 80h
0x18002be7d  xor     eax, eax
0x18002be7f  mov     [rbp+57h+var_B8], 5
0x18002be86  xor     r15d, r15d
0x18002be89  mov     [rbp+57h+pRequest.OptionalArguments], rax
0x18002be8d  lea     rcx, [rbp+57h+AccessMask]; AccessMask
0x18002be91  mov     [rbp+57h+var_88], r15d
0x18002be95  movups  xmmword ptr [rbp+57h+pRequest.DesiredAccess], xmm0
0x18002be99  movups  xmmword ptr [rbp+57h+pRequest.ObjectTypeList], xmm0
0x18002be9d  movups  xmmword ptr [rbp+57h+var_B0.ResultListLength], xmm0
0x18002bea1  movups  xmmword ptr [rbp+57h+var_B0.SaclEvaluationResults], xmm0
0x18002bea5  call    cs:__imp_MapGenericMask
0x18002beac  nop     dword ptr [rax+rax+00h]
0x18002beb1  mov     eax, [rbp+57h+AccessMask]
0x18002beb4  lea     r8, [rbp+57h+pRequest]; pRequest
0x18002beb8  mov     [rbp+57h+pRequest.DesiredAccess], eax
0x18002bebb  xor     r9d, r9d; hAuditEvent
0x18002bebe  mov     [rsp+110h+phAccessCheckResults], r15; phAccessCheckResults
0x18002bec3  lea     rax, [rbp+57h+var_88]
0x18002bec7  mov     [rbp+57h+var_B0.GrantedAccessMask], rax
0x18002becb  mov     rdx, rbx; hAuthzClientContext
0x18002bece  lea     rax, [rbp+57h+var_B8]
0x18002bed2  mov     [rbp+57h+var_B0.ResultListLength], 1
0x18002bed9  mov     [rbp+57h+var_B0.Error], rax
0x18002bedd  xor     ecx, ecx; Flags
0x18002bedf  lea     rax, [rbp+57h+var_B0]
0x18002bee3  mov     [rsp+110h+pReply], rax; pReply
0x18002bee8  mov     [rsp+110h+OptionalSecurityDescriptorCount], r15d; OptionalSecurityDescriptorCount
0x18002beed  mov     [rsp+110h+OptionalSecurityDescriptorArray], r15; OptionalSecurityDescriptorArray
0x18002bef2  mov     [rsp+110h+pSecurityDescriptor], rsi; pSecurityDescriptor
0x18002bef7  call    cs:__imp_AuthzAccessCheck
0x18002befe  nop     dword ptr [rax+rax+00h]
0x18002bf03  test    eax, eax
0x18002bf05  jz      loc_18002BF8E
0x18002bf0b  cmp     [rbp+57h+var_B8], r15d
0x18002bf0f  mov     eax, r15d
0x18002bf12  setz    al
0x18002bf15  test    eax, eax
0x18002bf17  jz      short loc_18002BF6A
0x18002bf19  test    r14, r14
0x18002bf1c  jz      short loc_18002BF37
0x18002bf1e  mov     rax, [rdi+30h]
0x18002bf22  mov     rdx, r14
0x18002bf25  mov     [r14+8], rax
0x18002bf29  mov     rcx, [rdi+28h]; lpCriticalSection
0x18002bf2d  call    BfeNotifyOneWay
0x18002bf32  test    rax, rax
0x18002bf35  jz      short loc_18002BF6A
0x18002bf37  mov     rbx, [rdi+28h]
0x18002bf3b  mov     rcx, rbx; lpCriticalSection
0x18002bf3e  call    cs:__imp_EnterCriticalSection
0x18002bf45  nop     dword ptr [rax+rax+00h]
0x18002bf4a  cmp     dword ptr [rbx+54h], 0
0x18002bf4e  mov     dword ptr [rbx+50h], 1
0x18002bf55  jz      loc_18002C103
0x18002bf5b  mov     rcx, rbx; lpCriticalSection
0x18002bf5e  call    cs:__imp_LeaveCriticalSection
0x18002bf65  nop     dword ptr [rax+rax+00h]
0x18002bf6a  mov     rcx, [rbp+57h+var_28]
0x18002bf6e  xor     rcx, rsp; StackCookie
0x18002bf71  call    __security_check_cookie
0x18002bf76  mov     rbx, [rsp+110h+arg_18]
0x18002bf7e  add     rsp, 0F0h
0x18002bf85  pop     r15
0x18002bf87  pop     r14
0x18002bf89  pop     rdi
0x18002bf8a  pop     rsi
0x18002bf8b  pop     rbp
0x18002bf8c  retn
0x18002bf8e  call    cs:__imp_GetLastError
0x18002bf95  nop     dword ptr [rax+rax+00h]
0x18002bf9a  mov     ebx, eax
0x18002bf9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18002bfa3  lea     rdi, WPP_GLOBAL_Control
0x18002bfaa  lea     rsi, aAuthzaccessche; "AuthzAccessCheck"
0x18002bfb1  cmp     rcx, rdi
0x18002bfb4  jz      short loc_18002BFC0
0x18002bfb6  cmp     byte ptr [rcx+19h], 2
0x18002bfba  jnb     loc_18002C069
0x18002bfc0  cmp     cs:gWfpLogUserModeErrors, r15d
0x18002bfc7  jnz     loc_18002C099
0x18002bfcd  test    ebx, ebx
0x18002bfcf  jg      loc_18002C0F3
0x18002bfd5  jz      short loc_18002BF6A
0x18002bfd7  lea     rsi, aBfeaccesscheck_0; "BfeAccessCheckFromContext"
0x18002bfde  cmp     rcx, rdi
0x18002bfe1  jz      short loc_18002C009
0x18002bfe3  cmp     byte ptr [rcx+19h], 2
0x18002bfe7  jb      short loc_18002C009
0x18002bfe9  test    byte ptr [rcx+1Ch], 1
0x18002bfed  jz      short loc_18002C009
0x18002bfef  mov     rcx, [rcx+10h]
0x18002bff3  mov     edx, 1Ah
0x18002bff8  mov     dword ptr [rsp+110h+OptionalSecurityDescriptorArray], ebx
0x18002bffc  xor     r9d, r9d
0x18002bfff  mov     [rsp+110h+pSecurityDescriptor], rsi
0x18002c004  call    WPP_SF_Ssd
0x18002c009  cmp     cs:gWfpLogUserModeErrors, r15d
0x18002c010  jz      loc_18002BF6A
0x18002c016  test    cs:byte_1800F6115, 1
0x18002c01d  jz      loc_18002BF6A
0x18002c023  lea     rax, [rbp+57h+var_C0]
0x18002c027  mov     [rbp+57h+var_C0], ebx
0x18002c02a  mov     [rbp+57h+var_38], rax
0x18002c02e  lea     rdx, WFP_USERMODE_ERROR
0x18002c035  lea     rax, [rbp+57h+var_58]
0x18002c039  mov     [rbp+57h+var_48], rsi
0x18002c03d  mov     r9d, 3
0x18002c043  mov     [rsp+110h+pSecurityDescriptor], rax
0x18002c048  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18002c04f  mov     [rbp+57h+var_40], 1Ah
0x18002c057  mov     [rbp+57h+var_30], 4
0x18002c05f  call    McGenEventWrite_EtwEventWriteTransfer
0x18002c064  jmp     loc_18002BF6A
0x18002c069  test    byte ptr [rcx+1Ch], 1
0x18002c06d  jz      loc_18002BFC0
0x18002c073  mov     rcx, [rcx+10h]
0x18002c077  mov     edx, 17h
0x18002c07c  mov     dword ptr [rsp+110h+OptionalSecurityDescriptorArray], ebx
0x18002c080  xor     r9d, r9d
0x18002c083  mov     [rsp+110h+pSecurityDescriptor], rsi
0x18002c088  call    WPP_SF_SsD
0x18002c08d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c094  jmp     loc_18002BFC0
0x18002c099  test    cs:byte_1800F6115, 1
0x18002c0a0  jz      loc_18002BFCD
0x18002c0a6  lea     rax, [rbp+57h+var_C0]
0x18002c0aa  mov     [rbp+57h+var_C0], ebx
0x18002c0ad  mov     [rbp+57h+var_38], rax
0x18002c0b1  lea     rdx, WFP_USERMODE_ERROR
0x18002c0b8  lea     rax, [rbp+57h+var_58]
0x18002c0bc  mov     [rbp+57h+var_48], rsi
0x18002c0c0  mov     r9d, 3
0x18002c0c6  mov     [rsp+110h+pSecurityDescriptor], rax
0x18002c0cb  lea     rcx, MICROSOFT_WFP_PROVIDER_Context
0x18002c0d2  mov     [rbp+57h+var_40], 11h
0x18002c0da  mov     [rbp+57h+var_30], 4
0x18002c0e2  call    McGenEventWrite_EtwEventWriteTransfer
0x18002c0e7  mov     rcx, cs:WPP_GLOBAL_Control
0x18002c0ee  jmp     loc_18002BFCD
0x18002c0f3  movzx   ebx, bx
0x18002c0f6  or      ebx, 80070000h
0x18002c0fc  test    ebx, ebx
0x18002c0fe  jmp     loc_18002BFD5
0x18002c103  mov     rcx, [rbx+0D8h]; hEvent
0x18002c10a  call    cs:__imp_SetEvent
0x18002c111  nop     dword ptr [rax+rax+00h]
0x18002c116  test    eax, eax
0x18002c118  jz      loc_18002BF5B
0x18002c11e  mov     dword ptr [rbx+54h], 1
0x18002c125  jmp     loc_18002BF5B
```
