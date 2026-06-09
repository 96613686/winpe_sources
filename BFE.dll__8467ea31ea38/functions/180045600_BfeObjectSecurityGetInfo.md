# BfeObjectSecurityGetInfo

- ea: `0x180045600`
- end: `0x180045743`
- name: `BfeObjectSecurityGetInfo`
- size: `323`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, SECURITY_INFORMATION SecurityInformation)`
- caller_count: `9`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180055a50`
- `0x180060430`
- `0x180060a50`
- `0x180061af0`
- `0x180062630`
- `0x180062ae0`
- `0x1800633a0`
- `0x180063770`
- `0x180064930`

## callees

- `0x18000e000`
- `0x180010360`
- `0x18001236c`
- `0x180018b74`
- `0x180022730`
- `0x180045600`
- `0x180058b30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456df`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180045692`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800456df`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x180045689`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x1800456d1`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x180045689`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x1800456d1`

## string_xrefs

- `0x1800456e8`: `GetPrivateObjectSecurity`
- `0x180045710`: `BfeObjectSecurityGetInfo`

## pseudocode

```c
__int64 __fastcall BfeObjectSecurityGetInfo(
        char *pSecurityDescriptor,
        SECURITY_INFORMATION SecurityInformation,
        _QWORD *a3)
{
  __int64 v3; // rbx
  PSECURITY_DESCRIPTOR v4; // rdi
  BOOL PrivateObjectSecurity; // r14d
  DWORD LastError; // eax
  __int64 v10; // rcx
  PSECURITY_DESCRIPTOR ResultantDescriptor; // [rsp+30h] [rbp-48h] BYREF
  DWORD DescriptorLength; // [rsp+38h] [rbp-40h] BYREF

  v3 = 0;
  v4 = 0;
  ResultantDescriptor = 0;
  DescriptorLength = 0;
  if ( (SecurityInformation & 7) != 0 )
  {
    v3 = BfeAccessCheck(pSecurityDescriptor, 0x20000u, 0);
    if ( v3 )
      goto LABEL_12;
  }
  if ( (SecurityInformation & 8) != 0 )
  {
    v3 = BfeAccessCheck(pSecurityDescriptor, 0x1000000u, 0);
    if ( v3 )
      goto LABEL_12;
  }
  PrivateObjectSecurity = GetPrivateObjectSecurity(pSecurityDescriptor, SecurityInformation, 0, 0, &DescriptorLength);
  if ( GetLastError() == 122 )
  {
    v3 = WfpMemAlloc(DescriptorLength, 0);
    if ( v3 )
    {
LABEL_12:
      WfpMemFree(&ResultantDescriptor);
      if ( v3 )
        WfpReportError(v3, "BfeObjectSecurityGetInfo");
      return v3;
    }
    v4 = ResultantDescriptor;
    PrivateObjectSecurity = GetPrivateObjectSecurity(
                              pSecurityDescriptor,
                              SecurityInformation,
                              ResultantDescriptor,
                              DescriptorLength,
                              &DescriptorLength);
  }
  if ( PrivateObjectSecurity )
  {
    *a3 = v4;
  }
  else
  {
    LastError = GetLastError();
    v3 = WfpReportSysErrorAsWinError(v10, "GetPrivateObjectSecurity", LastError);
  }
  if ( v3 )
    goto LABEL_12;
  return v3;
}

```

## disassembly

```asm
0x180045600  mov     [rsp+arg_18], rbx
0x180045605  push    rbp
0x180045606  push    rsi
0x180045607  push    rdi
0x180045608  push    r14
0x18004560a  push    r15
0x18004560c  sub     rsp, 50h
0x180045610  mov     rax, cs:__security_cookie
0x180045617  xor     rax, rsp
0x18004561a  mov     [rsp+78h+var_38], rax
0x18004561f  xor     ebx, ebx
0x180045621  xor     edi, edi
0x180045623  mov     [rsp+78h+ResultantDescriptor], rdi
0x180045628  mov     r15, r8
0x18004562b  mov     [rsp+78h+DescriptorLength], ebx
0x18004562f  mov     ebp, edx
0x180045631  mov     rsi, rcx
0x180045634  test    dl, 7
0x180045637  jz      short loc_180045652
0x180045639  xor     r8d, r8d
0x18004563c  mov     edx, 20000h
0x180045641  call    BfeAccessCheck
0x180045646  mov     rbx, rax
0x180045649  test    rax, rax
0x18004564c  jnz     loc_180045701
0x180045652  test    bpl, 8
0x180045656  jz      short loc_180045674
0x180045658  xor     r8d, r8d
0x18004565b  mov     edx, 1000000h
0x180045660  mov     rcx, rsi; pSecurityDescriptor
0x180045663  call    BfeAccessCheck
0x180045668  mov     rbx, rax
0x18004566b  test    rax, rax
0x18004566e  jnz     loc_180045701
0x180045674  lea     rax, [rsp+78h+DescriptorLength]
0x180045679  xor     r9d, r9d; DescriptorLength
0x18004567c  xor     r8d, r8d; ResultantDescriptor
0x18004567f  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180045684  mov     edx, ebp; SecurityInformation
0x180045686  mov     rcx, rsi; ObjectDescriptor
0x180045689  call    cs:__imp_GetPrivateObjectSecurity
0x18004568f  mov     r14d, eax
0x180045692  call    cs:__imp_GetLastError
0x180045698  cmp     eax, 7Ah ; 'z'
0x18004569b  jnz     short loc_1800456DA
0x18004569d  mov     ecx, [rsp+78h+DescriptorLength]; dwBytes
0x1800456a1  lea     r8, [rsp+78h+ResultantDescriptor]
0x1800456a6  xor     edx, edx; dwFlags
0x1800456a8  call    WfpMemAlloc
0x1800456ad  mov     rbx, rax
0x1800456b0  test    rax, rax
0x1800456b3  jnz     short loc_180045701
0x1800456b5  mov     rdi, [rsp+78h+ResultantDescriptor]
0x1800456ba  lea     rax, [rsp+78h+DescriptorLength]
0x1800456bf  mov     r9d, [rsp+78h+DescriptorLength]; DescriptorLength
0x1800456c4  mov     r8, rdi; ResultantDescriptor
0x1800456c7  mov     edx, ebp; SecurityInformation
0x1800456c9  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x1800456ce  mov     rcx, rsi; ObjectDescriptor
0x1800456d1  call    cs:__imp_GetPrivateObjectSecurity
0x1800456d7  mov     r14d, eax
0x1800456da  test    r14d, r14d
0x1800456dd  jnz     short loc_1800456F9
0x1800456df  call    cs:__imp_GetLastError
0x1800456e5  mov     r8d, eax
0x1800456e8  lea     rdx, aGetprivateobje; "GetPrivateObjectSecurity"
0x1800456ef  call    WfpReportSysErrorAsWinError
0x1800456f4  mov     rbx, rax
0x1800456f7  jmp     short loc_1800456FC
0x1800456f9  mov     [r15], rdi
0x1800456fc  test    rbx, rbx
0x1800456ff  jz      short loc_18004571F
0x180045701  lea     rcx, [rsp+78h+ResultantDescriptor]
0x180045706  call    WfpMemFree
0x18004570b  test    rbx, rbx
0x18004570e  jz      short loc_18004571F
0x180045710  lea     rdx, aBfeobjectsecur_3; "BfeObjectSecurityGetInfo"
0x180045717  mov     rcx, rbx
0x18004571a  call    WfpReportError
0x18004571f  mov     rax, rbx
0x180045722  mov     rcx, [rsp+78h+var_38]
0x180045727  xor     rcx, rsp; StackCookie
0x18004572a  call    __security_check_cookie
0x18004572f  mov     rbx, [rsp+78h+arg_18]
0x180045737  add     rsp, 50h
0x18004573b  pop     r15
0x18004573d  pop     r14
0x18004573f  pop     rdi
0x180045740  pop     rsi
0x180045741  pop     rbp
0x180045742  retn
```
