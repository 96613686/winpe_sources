# BfeObjectSecurityGetInfo

- ea: `0x1800474b8`
- end: `0x180047614`
- name: `BfeObjectSecurityGetInfo`
- size: `348`
- prototype: `__int64 __fastcall(PSECURITY_DESCRIPTOR pSecurityDescriptor, SECURITY_INFORMATION SecurityInformation)`
- caller_count: `9`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800578a0`
- `0x180062750`
- `0x180062d70`
- `0x180063e20`
- `0x180064980`
- `0x180064e30`
- `0x1800656f0`
- `0x180065ad0`
- `0x180066cc0`

## callees

- `0x18000e7e0`
- `0x180010d60`
- `0x180012d8c`
- `0x1800197d0`
- `0x180024e40`
- `0x1800474b8`
- `0x18005aa60`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475a9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180047550`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800475a9`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x180047541`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x180047595`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x180047541`
- `api-ms-win-security-base-l1-1-0!GetPrivateObjectSecurity` at `0x180047595`

## string_xrefs

- `0x1800475b8`: `GetPrivateObjectSecurity`
- `0x1800475e0`: `BfeObjectSecurityGetInfo`

## pseudocode

```c
__int64 __fastcall BfeObjectSecurityGetInfo(
        PSECURITY_DESCRIPTOR pSecurityDescriptor,
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
    v3 = BfeAccessCheck(pSecurityDescriptor);
    if ( v3 )
      goto LABEL_12;
  }
  if ( (SecurityInformation & 8) != 0 )
  {
    v3 = BfeAccessCheck(pSecurityDescriptor);
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
0x1800474b8  mov     [rsp+arg_18], rbx
0x1800474bd  push    rbp
0x1800474be  push    rsi
0x1800474bf  push    rdi
0x1800474c0  push    r14
0x1800474c2  push    r15
0x1800474c4  sub     rsp, 50h
0x1800474c8  mov     rax, cs:__security_cookie
0x1800474cf  xor     rax, rsp
0x1800474d2  mov     [rsp+78h+var_38], rax
0x1800474d7  xor     ebx, ebx
0x1800474d9  xor     edi, edi
0x1800474db  mov     [rsp+78h+ResultantDescriptor], rdi
0x1800474e0  mov     r15, r8
0x1800474e3  mov     [rsp+78h+DescriptorLength], ebx
0x1800474e7  mov     ebp, edx
0x1800474e9  mov     rsi, rcx
0x1800474ec  test    dl, 7
0x1800474ef  jz      short loc_18004750A
0x1800474f1  xor     r8d, r8d
0x1800474f4  mov     edx, 20000h
0x1800474f9  call    BfeAccessCheck
0x1800474fe  mov     rbx, rax
0x180047501  test    rax, rax
0x180047504  jnz     loc_1800475D1
0x18004750a  test    bpl, 8
0x18004750e  jz      short loc_18004752C
0x180047510  xor     r8d, r8d
0x180047513  mov     edx, 1000000h
0x180047518  mov     rcx, rsi; pSecurityDescriptor
0x18004751b  call    BfeAccessCheck
0x180047520  mov     rbx, rax
0x180047523  test    rax, rax
0x180047526  jnz     loc_1800475D1
0x18004752c  lea     rax, [rsp+78h+DescriptorLength]
0x180047531  xor     r9d, r9d; DescriptorLength
0x180047534  xor     r8d, r8d; ResultantDescriptor
0x180047537  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x18004753c  mov     edx, ebp; SecurityInformation
0x18004753e  mov     rcx, rsi; ObjectDescriptor
0x180047541  call    cs:__imp_GetPrivateObjectSecurity
0x180047548  nop     dword ptr [rax+rax+00h]
0x18004754d  mov     r14d, eax
0x180047550  call    cs:__imp_GetLastError
0x180047557  nop     dword ptr [rax+rax+00h]
0x18004755c  cmp     eax, 7Ah ; 'z'
0x18004755f  jnz     short loc_1800475A4
0x180047561  mov     ecx, [rsp+78h+DescriptorLength]; dwBytes
0x180047565  lea     r8, [rsp+78h+ResultantDescriptor]
0x18004756a  xor     edx, edx; dwFlags
0x18004756c  call    WfpMemAlloc
0x180047571  mov     rbx, rax
0x180047574  test    rax, rax
0x180047577  jnz     short loc_1800475D1
0x180047579  mov     rdi, [rsp+78h+ResultantDescriptor]
0x18004757e  lea     rax, [rsp+78h+DescriptorLength]
0x180047583  mov     r9d, [rsp+78h+DescriptorLength]; DescriptorLength
0x180047588  mov     r8, rdi; ResultantDescriptor
0x18004758b  mov     edx, ebp; SecurityInformation
0x18004758d  mov     [rsp+78h+ReturnLength], rax; ReturnLength
0x180047592  mov     rcx, rsi; ObjectDescriptor
0x180047595  call    cs:__imp_GetPrivateObjectSecurity
0x18004759c  nop     dword ptr [rax+rax+00h]
0x1800475a1  mov     r14d, eax
0x1800475a4  test    r14d, r14d
0x1800475a7  jnz     short loc_1800475C9
0x1800475a9  call    cs:__imp_GetLastError
0x1800475b0  nop     dword ptr [rax+rax+00h]
0x1800475b5  mov     r8d, eax
0x1800475b8  lea     rdx, aGetprivateobje; "GetPrivateObjectSecurity"
0x1800475bf  call    WfpReportSysErrorAsWinError
0x1800475c4  mov     rbx, rax
0x1800475c7  jmp     short loc_1800475CC
0x1800475c9  mov     [r15], rdi
0x1800475cc  test    rbx, rbx
0x1800475cf  jz      short loc_1800475EF
0x1800475d1  lea     rcx, [rsp+78h+ResultantDescriptor]
0x1800475d6  call    WfpMemFree
0x1800475db  test    rbx, rbx
0x1800475de  jz      short loc_1800475EF
0x1800475e0  lea     rdx, aBfeobjectsecur_3; "BfeObjectSecurityGetInfo"
0x1800475e7  mov     rcx, rbx
0x1800475ea  call    WfpReportError
0x1800475ef  mov     rax, rbx
0x1800475f2  mov     rcx, [rsp+78h+var_38]
0x1800475f7  xor     rcx, rsp; StackCookie
0x1800475fa  call    __security_check_cookie
0x1800475ff  mov     rbx, [rsp+78h+arg_18]
0x180047607  add     rsp, 50h
0x18004760b  pop     r15
0x18004760d  pop     r14
0x18004760f  pop     rdi
0x180047610  pop     rsi
0x180047611  pop     rbp
0x180047612  retn
```
