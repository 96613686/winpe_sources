# ATL::CSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,void *,ulong)

- ea: `0x14001ca4c`
- end: `0x14001cb91`
- name: `?AddAccessAllowedACEToACL@CSecurityDescriptor@ATL@@SAJPEAPEAU_ACL@@PEAXK@Z`
- size: `325`
- prototype: `__int64 __fastcall(struct _ACL **, void *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001d34c`

## callees

- `0x1400030a0`
- `0x14001ca4c`
- `0x14001d4e8`
- `0x14001d980`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001cb5b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x14001cb5b`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001caf8`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x14001caf8`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x14001cb3b`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x14001cb3b`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14001cae6`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x14001cae6`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14001ca9c`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x14001ca9c`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14001caca`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14001caca`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14001cb11`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x14001cb11`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
        Error = ResultFromLastError();
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
      Error = ResultFromLastError();
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
0x14001ca4c  mov     [rsp+arg_10], rbx
0x14001ca51  mov     [rsp+arg_18], rbp
0x14001ca56  push    rsi
0x14001ca57  push    rdi
0x14001ca58  push    r14
0x14001ca5a  sub     rsp, 40h
0x14001ca5e  mov     rax, cs:__security_cookie
0x14001ca65  xor     rax, rsp
0x14001ca68  mov     [rsp+58h+var_28], rax
0x14001ca6d  xor     eax, eax
0x14001ca6f  mov     rbp, rdx
0x14001ca72  mov     [rsp+58h+pAclInformation], rax
0x14001ca77  mov     rsi, rcx
0x14001ca7a  mov     [rsp+58h+var_30], eax
0x14001ca7e  test    rcx, rcx
0x14001ca81  jnz     short loc_14001CA8D
0x14001ca83  mov     eax, 80004003h
0x14001ca88  jmp     loc_14001CB71
0x14001ca8d  test    rbp, rbp
0x14001ca90  jz      loc_14001CB6C
0x14001ca96  mov     r14, [rcx]
0x14001ca99  mov     rcx, rbp; pSid
0x14001ca9c  call    cs:__imp_IsValidSid
0x14001caa2  test    eax, eax
0x14001caa4  jz      loc_14001CB6C
0x14001caaa  cmp     qword ptr [rsi], 0
0x14001caae  mov     dword ptr [rsp+58h+pAclInformation+4], 0
0x14001cab6  jz      short loc_14001CAE3
0x14001cab8  mov     r9d, 2; dwAclInformationClass
0x14001cabe  lea     rdx, [rsp+58h+pAclInformation]; pAclInformation
0x14001cac3  mov     rcx, r14; pAcl
0x14001cac6  lea     r8d, [r9+0Ah]; nAclInformationLength
0x14001caca  call    cs:__imp_GetAclInformation
0x14001cad0  test    eax, eax
0x14001cad2  jnz     short loc_14001CAE3
0x14001cad4  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14001cad9  mov     ebx, eax
0x14001cadb  test    eax, eax
0x14001cadd  js      loc_14001CB68
0x14001cae3  mov     rcx, rbp; pSid
0x14001cae6  call    cs:__imp_GetLengthSid
0x14001caec  mov     ebx, dword ptr [rsp+58h+pAclInformation+4]
0x14001caf0  add     ebx, 10h
0x14001caf3  add     ebx, eax
0x14001caf5  movsxd  rcx, ebx; Size
0x14001caf8  call    cs:__imp_malloc
0x14001cafe  mov     rdi, rax
0x14001cb01  test    rax, rax
0x14001cb04  jz      short loc_14001CB63
0x14001cb06  mov     r8d, 2; dwAclRevision
0x14001cb0c  mov     edx, ebx; nAclLength
0x14001cb0e  mov     rcx, rax; pAcl
0x14001cb11  call    cs:__imp_InitializeAcl
0x14001cb17  test    eax, eax
0x14001cb19  jz      short loc_14001CB4D
0x14001cb1b  mov     rdx, r14; PACL
0x14001cb1e  mov     rcx, rdi; pAcl
0x14001cb21  call    ?CopyACL@CSecurityDescriptor@ATL@@SAJPEAU_ACL@@0@Z; ATL::CSecurityDescriptor::CopyACL(_ACL *,_ACL *)
0x14001cb26  mov     ebx, eax
0x14001cb28  test    eax, eax
0x14001cb2a  js      short loc_14001CB58
0x14001cb2c  mov     edx, 2; dwAceRevision
0x14001cb31  mov     r9, rbp; pSid
0x14001cb34  mov     rcx, rdi; pAcl
0x14001cb37  lea     r8d, [rdx-1]; AccessMask
0x14001cb3b  call    cs:__imp_AddAccessAllowedAce
0x14001cb41  test    eax, eax
0x14001cb43  jz      short loc_14001CB4D
0x14001cb45  mov     [rsi], rdi
0x14001cb48  mov     rcx, r14
0x14001cb4b  jmp     short loc_14001CB5B
0x14001cb4d  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x14001cb52  mov     ebx, eax
0x14001cb54  test    eax, eax
0x14001cb56  jns     short loc_14001CB68
0x14001cb58  mov     rcx, rdi; Block
0x14001cb5b  call    cs:__imp_free
0x14001cb61  jmp     short loc_14001CB68
0x14001cb63  mov     ebx, 8007000Eh
0x14001cb68  mov     eax, ebx
0x14001cb6a  jmp     short loc_14001CB71
0x14001cb6c  mov     eax, 80070057h
0x14001cb71  mov     rcx, [rsp+58h+var_28]
0x14001cb76  xor     rcx, rsp; StackCookie
0x14001cb79  call    __security_check_cookie
0x14001cb7e  mov     rbx, [rsp+58h+arg_10]
0x14001cb83  mov     rbp, [rsp+58h+arg_18]
0x14001cb88  add     rsp, 40h
0x14001cb8c  pop     r14
0x14001cb8e  pop     rdi
0x14001cb8f  pop     rsi
0x14001cb90  retn
```
