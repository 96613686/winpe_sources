# KdcDmsaAuthzCheck(AUTHZ_CLIENT_CONTEXT_HANDLE__ *,uchar *)

- ea: `0x180028a60`
- end: `0x180028b8d`
- name: `?KdcDmsaAuthzCheck@@YAJPEAUAUTHZ_CLIENT_CONTEXT_HANDLE__@@PEAE@Z`
- size: `301`
- prototype: `__int64 __fastcall(AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext, PSECURITY_DESCRIPTOR pSecurityDescriptor)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002b910`

## callees

- `0x1800101c4`
- `0x1800101ec`
- `0x180028a60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180028b13`
- `AUTHZ!AuthzAccessCheck` at `0x180028af0`
- `AUTHZ!AuthzAccessCheck` at `0x180028af0`

## pseudocode

```c
__int64 __fastcall KdcDmsaAuthzCheck(
        AUTHZ_CLIENT_CONTEXT_HANDLE hAuthzClientContext,
        PSECURITY_DESCRIPTOR pSecurityDescriptor)
{
  DWORD LastError; // eax
  struct _AUTHZ_ACCESS_REPLY v4; // [rsp+58h] [rbp+7h] BYREF
  struct _AUTHZ_ACCESS_REQUEST pRequest; // [rsp+78h] [rbp+27h] BYREF
  int v6; // [rsp+B8h] [rbp+67h] BYREF
  int v7; // [rsp+C8h] [rbp+77h] BYREF

  v7 = 5;
  *(&v4.ResultListLength + 1) = 0;
  v4.SaclEvaluationResults = 0;
  *(&pRequest.DesiredAccess + 1) = 0;
  *(&pRequest.ObjectTypeListLength + 1) = 0;
  v6 = 0;
  if ( hAuthzClientContext && pSecurityDescriptor )
  {
    v4.GrantedAccessMask = (PACCESS_MASK)&v6;
    pRequest.DesiredAccess = 16;
    v4.Error = (PDWORD)&v7;
    pRequest.OptionalArguments = 0;
    memset(&pRequest.PrincipalSelfSid, 0, 20);
    v4.ResultListLength = 1;
    if ( AuthzAccessCheck(0, hAuthzClientContext, &pRequest, 0, pSecurityDescriptor, 0, 0, &v4, 0) )
    {
      return *v4.Error != 0 ? 0xC : 0;
    }
    else
    {
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        LastError = GetLastError();
        WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 2), 13, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids, LastError);
      }
      return 0;
    }
  }
  else
  {
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 12, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids);
    return 60;
  }
}

```

## disassembly

```asm
0x180028a60  mov     r11, rsp
0x180028a63  mov     [r11+10h], rbx
0x180028a67  push    rbp
0x180028a68  lea     rbp, [r11-5Fh]
0x180028a6c  sub     rsp, 0A0h
0x180028a73  xor     ebx, ebx
0x180028a75  mov     [rbp+57h+arg_10], 5
0x180028a7c  mov     [rbp+57h+var_4C], ebx
0x180028a7f  mov     [rbp+57h+var_40], rbx
0x180028a83  mov     dword ptr [rbp+57h+pRequest+4], ebx
0x180028a86  mov     dword ptr [rbp+57h+pRequest+1Ch], ebx
0x180028a89  mov     [rbp+57h+arg_0], ebx
0x180028a8c  test    rcx, rcx
0x180028a8f  jz      loc_180028B49
0x180028a95  test    rdx, rdx
0x180028a98  jz      loc_180028B49
0x180028a9e  mov     [r11-68h], rbx
0x180028aa2  lea     rax, [rbp+57h+arg_0]
0x180028aa6  mov     [rbp+57h+var_48], rax
0x180028aaa  lea     r8, [rbp+57h+pRequest]; pRequest
0x180028aae  lea     rax, [rbp+57h+arg_10]
0x180028ab2  mov     [rbp+57h+pRequest.DesiredAccess], 10h
0x180028ab9  mov     [rbp+57h+var_38], rax
0x180028abd  xor     r9d, r9d; hAuditEvent
0x180028ac0  lea     rax, [rbp+57h+var_50]
0x180028ac4  mov     [rbp+57h+pRequest.ObjectTypeList], rbx
0x180028ac8  mov     [r11-70h], rax
0x180028acc  mov     [rsp+30h], ebx; OptionalSecurityDescriptorCount
0x180028ad0  mov     [r11-80h], rbx
0x180028ad4  mov     [rsp+20h], rdx; pSecurityDescriptor
0x180028ad9  mov     rdx, rcx; hAuthzClientContext
0x180028adc  xor     ecx, ecx; Flags
0x180028ade  mov     [rbp+57h+pRequest.ObjectTypeListLength], ebx
0x180028ae1  mov     [rbp+57h+pRequest.OptionalArguments], rbx
0x180028ae5  mov     [rbp+57h+pRequest.PrincipalSelfSid], rbx
0x180028ae9  mov     [rbp+57h+var_50], 1
0x180028af0  call    cs:__imp_AuthzAccessCheck
0x180028af6  test    eax, eax
0x180028af8  jnz     short loc_180028B3A
0x180028afa  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b01  lea     rax, WPP_GLOBAL_Control
0x180028b08  cmp     rcx, rax
0x180028b0b  jz      short loc_180028B36
0x180028b0d  test    byte ptr [rcx+1Ch], 1
0x180028b11  jz      short loc_180028B36
0x180028b13  call    cs:__imp_GetLastError
0x180028b19  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b20  lea     edx, [rbx+0Dh]
0x180028b23  mov     r9d, eax
0x180028b26  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180028b2d  mov     rcx, [rcx+10h]
0x180028b31  call    WPP_SF_d
0x180028b36  xor     eax, eax
0x180028b38  jmp     short loc_180028B7C
0x180028b3a  mov     rax, [rbp+57h+var_38]
0x180028b3e  mov     ecx, [rax]
0x180028b40  neg     ecx
0x180028b42  sbb     eax, eax
0x180028b44  and     eax, 0Ch
0x180028b47  jmp     short loc_180028B7C
0x180028b49  mov     rcx, cs:WPP_GLOBAL_Control
0x180028b50  lea     rax, WPP_GLOBAL_Control
0x180028b57  cmp     rcx, rax
0x180028b5a  jz      short loc_180028B77
0x180028b5c  test    byte ptr [rcx+1Ch], 1
0x180028b60  jz      short loc_180028B77
0x180028b62  mov     rcx, [rcx+10h]
0x180028b66  lea     r8, WPP_a4cc8a90c2ec30bf7078874077240ba4_Traceguids
0x180028b6d  mov     edx, 0Ch
0x180028b72  call    WPP_SF_
0x180028b77  mov     eax, 3Ch ; '<'
0x180028b7c  mov     rbx, [rsp+0A0h+arg_8]
0x180028b84  add     rsp, 0A0h
0x180028b8b  pop     rbp
0x180028b8c  retn
```
