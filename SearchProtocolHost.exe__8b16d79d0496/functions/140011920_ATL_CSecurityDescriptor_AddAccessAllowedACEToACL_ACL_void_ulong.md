# ATL::CSecurityDescriptor::AddAccessAllowedACEToACL(_ACL * *,void *,ulong)

- ea: `0x140011920`
- end: `0x140011a65`
- name: `?AddAccessAllowedACEToACL@CSecurityDescriptor@ATL@@SAJPEAPEAU_ACL@@PEAXK@Z`
- size: `325`
- prototype: `static int(struct _ACL **, void *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14001221c`

## callees

- `0x140005240`
- `0x140011920`
- `0x1400124cc`
- `0x140013310`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140011a2f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x140011a2f`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400119cc`
- `api-ms-win-crt-private-l1-1-0!_o_malloc` at `0x1400119cc`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140011a0f`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x140011a0f`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400119ba`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1400119ba`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400119e5`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1400119e5`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140011970`
- `api-ms-win-security-base-l1-1-0!IsValidSid` at `0x140011970`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14001199e`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x14001199e`

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
0x140011920  mov     [rsp+arg_10], rbx
0x140011925  mov     [rsp+arg_18], rbp
0x14001192a  push    rsi
0x14001192b  push    rdi
0x14001192c  push    r14
0x14001192e  sub     rsp, 40h
0x140011932  mov     rax, cs:__security_cookie
0x140011939  xor     rax, rsp
0x14001193c  mov     [rsp+58h+var_28], rax
0x140011941  xor     eax, eax
0x140011943  mov     rbp, rdx
0x140011946  mov     [rsp+58h+pAclInformation], rax
0x14001194b  mov     rsi, rcx
0x14001194e  mov     [rsp+58h+var_30], eax
0x140011952  test    rcx, rcx
0x140011955  jnz     short loc_140011961
0x140011957  mov     eax, 80004003h
0x14001195c  jmp     loc_140011A45
0x140011961  test    rbp, rbp
0x140011964  jz      loc_140011A40
0x14001196a  mov     r14, [rcx]
0x14001196d  mov     rcx, rbp; pSid
0x140011970  call    cs:__imp_IsValidSid
0x140011976  test    eax, eax
0x140011978  jz      loc_140011A40
0x14001197e  cmp     qword ptr [rsi], 0
0x140011982  mov     dword ptr [rsp+58h+pAclInformation+4], 0
0x14001198a  jz      short loc_1400119B7
0x14001198c  mov     r9d, 2; dwAclInformationClass
0x140011992  lea     rdx, [rsp+58h+pAclInformation]; pAclInformation
0x140011997  mov     rcx, r14; pAcl
0x14001199a  lea     r8d, [r9+0Ah]; nAclInformationLength
0x14001199e  call    cs:__imp_GetAclInformation
0x1400119a4  test    eax, eax
0x1400119a6  jnz     short loc_1400119B7
0x1400119a8  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x1400119ad  mov     ebx, eax
0x1400119af  test    eax, eax
0x1400119b1  js      loc_140011A3C
0x1400119b7  mov     rcx, rbp; pSid
0x1400119ba  call    cs:__imp_GetLengthSid
0x1400119c0  mov     ebx, dword ptr [rsp+58h+pAclInformation+4]
0x1400119c4  add     ebx, 10h
0x1400119c7  add     ebx, eax
0x1400119c9  movsxd  rcx, ebx; Size
0x1400119cc  call    cs:__imp_malloc
0x1400119d2  mov     rdi, rax
0x1400119d5  test    rax, rax
0x1400119d8  jz      short loc_140011A37
0x1400119da  mov     r8d, 2; dwAclRevision
0x1400119e0  mov     edx, ebx; nAclLength
0x1400119e2  mov     rcx, rax; pAcl
0x1400119e5  call    cs:__imp_InitializeAcl
0x1400119eb  test    eax, eax
0x1400119ed  jz      short loc_140011A21
0x1400119ef  mov     rdx, r14; PACL
0x1400119f2  mov     rcx, rdi; pAcl
0x1400119f5  call    ?CopyACL@CSecurityDescriptor@ATL@@SAJPEAU_ACL@@0@Z; ATL::CSecurityDescriptor::CopyACL(_ACL *,_ACL *)
0x1400119fa  mov     ebx, eax
0x1400119fc  test    eax, eax
0x1400119fe  js      short loc_140011A2C
0x140011a00  mov     edx, 2; dwAceRevision
0x140011a05  mov     r9, rbp; pSid
0x140011a08  mov     rcx, rdi; pAcl
0x140011a0b  lea     r8d, [rdx-1]; AccessMask
0x140011a0f  call    cs:__imp_AddAccessAllowedAce
0x140011a15  test    eax, eax
0x140011a17  jz      short loc_140011A21
0x140011a19  mov     [rsi], rdi
0x140011a1c  mov     rcx, r14
0x140011a1f  jmp     short loc_140011A2F
0x140011a21  call    ?ResultFromLastError@@YAJXZ; ResultFromLastError(void)
0x140011a26  mov     ebx, eax
0x140011a28  test    eax, eax
0x140011a2a  jns     short loc_140011A3C
0x140011a2c  mov     rcx, rdi; Block
0x140011a2f  call    cs:__imp_free
0x140011a35  jmp     short loc_140011A3C
0x140011a37  mov     ebx, 8007000Eh
0x140011a3c  mov     eax, ebx
0x140011a3e  jmp     short loc_140011A45
0x140011a40  mov     eax, 80070057h
0x140011a45  mov     rcx, [rsp+58h+var_28]
0x140011a4a  xor     rcx, rsp; StackCookie
0x140011a4d  call    __security_check_cookie
0x140011a52  mov     rbx, [rsp+58h+arg_10]
0x140011a57  mov     rbp, [rsp+58h+arg_18]
0x140011a5c  add     rsp, 40h
0x140011a60  pop     r14
0x140011a62  pop     rdi
0x140011a63  pop     rsi
0x140011a64  retn
```
