# ATL::CSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,void *,ulong)

- ea: `0x180009420`
- end: `0x180009565`
- name: `?AddAccessAllowedACEToACL@CSecurityDescriptor@ATL@@SAJPEAPEAU_ACL@@PEAXK@Z`
- size: `325`
- prototype: `__int64 __fastcall(struct _ACL **, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180009c88`

## callees

- `0x180001720`
- `0x180009420`
- `0x180009df4`
- `0x18000a22c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000952f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000952f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800094cc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1800094cc`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000950f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18000950f`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009470`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x180009470`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800094ba`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1800094ba`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800094e5`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1800094e5`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000949e`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18000949e`

## pseudocode

```c
__int64 __fastcall ATL::CSecurityDescriptor::AddAccessAllowedACEToACL(struct _ACL **a1, void *a2)
{
  struct _ACL *v5; // r14
  bool v6; // zf
  int Error; // ebx
  DWORD LengthSid; // eax
  signed int v9; // ebx
  struct _ACL *v10; // rax
  struct _ACL *v11; // rdi
  struct _ACL *v12; // rcx
  __int64 pAclInformation; // [rsp+20h] [rbp-38h] BYREF
  int v14; // [rsp+28h] [rbp-30h]

  pAclInformation = 0;
  v14 = 0;
  if ( !a1 )
    return 2147500035LL;
  if ( a2 )
  {
    v5 = *a1;
    if ( IsValidSid(a2) )
    {
      v6 = *a1 == 0;
      HIDWORD(pAclInformation) = 0;
      if ( !v6 && !GetAclInformation(v5, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        Error = ATL::AtlHresultFromLastError();
        if ( Error < 0 )
          return (unsigned int)Error;
      }
      LengthSid = GetLengthSid(a2);
      v9 = LengthSid + HIDWORD(pAclInformation) + 16;
      v10 = (struct _ACL *)malloc(v9);
      v11 = v10;
      if ( !v10 )
        return (unsigned int)-2147024882;
      if ( InitializeAcl(v10, v9, 2u) )
      {
        Error = ATL::CSecurityDescriptor::CopyACL(v11, v5);
        if ( Error < 0 )
        {
LABEL_14:
          v12 = v11;
          goto LABEL_15;
        }
        if ( AddAccessAllowedAce(v11, 2u, 1u, a2) )
        {
          *a1 = v11;
          v12 = v5;
LABEL_15:
          free(v12);
          return (unsigned int)Error;
        }
      }
      Error = ATL::AtlHresultFromLastError();
      if ( Error >= 0 )
        return (unsigned int)Error;
      goto LABEL_14;
    }
  }
  return 2147942487LL;
}

```

## disassembly

```asm
0x180009420  mov     [rsp+arg_10], rbx
0x180009425  mov     [rsp+arg_18], rbp
0x18000942a  push    rsi
0x18000942b  push    rdi
0x18000942c  push    r14
0x18000942e  sub     rsp, 40h
0x180009432  mov     rax, cs:__security_cookie
0x180009439  xor     rax, rsp
0x18000943c  mov     [rsp+58h+var_28], rax
0x180009441  xor     eax, eax
0x180009443  mov     rbp, rdx
0x180009446  mov     [rsp+58h+pAclInformation], rax
0x18000944b  mov     rsi, rcx
0x18000944e  mov     [rsp+58h+var_30], eax
0x180009452  test    rcx, rcx
0x180009455  jnz     short loc_180009461
0x180009457  mov     eax, 80004003h
0x18000945c  jmp     loc_180009545
0x180009461  test    rbp, rbp
0x180009464  jz      loc_180009540
0x18000946a  mov     r14, [rcx]
0x18000946d  mov     rcx, rbp; pSid
0x180009470  call    cs:__imp_IsValidSid
0x180009476  test    eax, eax
0x180009478  jz      loc_180009540
0x18000947e  cmp     qword ptr [rsi], 0
0x180009482  mov     dword ptr [rsp+58h+pAclInformation+4], 0
0x18000948a  jz      short loc_1800094B7
0x18000948c  mov     r9d, 2; dwAclInformationClass
0x180009492  lea     rdx, [rsp+58h+pAclInformation]; pAclInformation
0x180009497  mov     rcx, r14; pAcl
0x18000949a  lea     r8d, [r9+0Ah]; nAclInformationLength
0x18000949e  call    cs:__imp_GetAclInformation
0x1800094a4  test    eax, eax
0x1800094a6  jnz     short loc_1800094B7
0x1800094a8  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x1800094ad  mov     ebx, eax
0x1800094af  test    eax, eax
0x1800094b1  js      loc_18000953C
0x1800094b7  mov     rcx, rbp; pSid
0x1800094ba  call    cs:__imp_GetLengthSid
0x1800094c0  mov     ebx, dword ptr [rsp+58h+pAclInformation+4]
0x1800094c4  add     ebx, 10h
0x1800094c7  add     ebx, eax
0x1800094c9  movsxd  rcx, ebx; Size
0x1800094cc  call    cs:__imp_malloc
0x1800094d2  mov     rdi, rax
0x1800094d5  test    rax, rax
0x1800094d8  jz      short loc_180009537
0x1800094da  mov     r8d, 2; dwAclRevision
0x1800094e0  mov     edx, ebx; nAclLength
0x1800094e2  mov     rcx, rax; pAcl
0x1800094e5  call    cs:__imp_InitializeAcl
0x1800094eb  test    eax, eax
0x1800094ed  jz      short loc_180009521
0x1800094ef  mov     rdx, r14; PACL
0x1800094f2  mov     rcx, rdi; pAcl
0x1800094f5  call    ?CopyACL@CSecurityDescriptor@ATL@@SAJPEAU_ACL@@0@Z; ATL::CSecurityDescriptor::CopyACL(_ACL *,_ACL *)
0x1800094fa  mov     ebx, eax
0x1800094fc  test    eax, eax
0x1800094fe  js      short loc_18000952C
0x180009500  mov     edx, 2; dwAceRevision
0x180009505  mov     r9, rbp; pSid
0x180009508  mov     rcx, rdi; pAcl
0x18000950b  lea     r8d, [rdx-1]; AccessMask
0x18000950f  call    cs:__imp_AddAccessAllowedAce
0x180009515  test    eax, eax
0x180009517  jz      short loc_180009521
0x180009519  mov     [rsi], rdi
0x18000951c  mov     rcx, r14
0x18000951f  jmp     short loc_18000952F
0x180009521  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180009526  mov     ebx, eax
0x180009528  test    eax, eax
0x18000952a  jns     short loc_18000953C
0x18000952c  mov     rcx, rdi; Block
0x18000952f  call    cs:__imp_free
0x180009535  jmp     short loc_18000953C
0x180009537  mov     ebx, 8007000Eh
0x18000953c  mov     eax, ebx
0x18000953e  jmp     short loc_180009545
0x180009540  mov     eax, 80070057h
0x180009545  mov     rcx, [rsp+58h+var_28]
0x18000954a  xor     rcx, rsp; StackCookie
0x18000954d  call    __security_check_cookie
0x180009552  mov     rbx, [rsp+58h+arg_10]
0x180009557  mov     rbp, [rsp+58h+arg_18]
0x18000955c  add     rsp, 40h
0x180009560  pop     r14
0x180009562  pop     rdi
0x180009563  pop     rsi
0x180009564  retn
```
