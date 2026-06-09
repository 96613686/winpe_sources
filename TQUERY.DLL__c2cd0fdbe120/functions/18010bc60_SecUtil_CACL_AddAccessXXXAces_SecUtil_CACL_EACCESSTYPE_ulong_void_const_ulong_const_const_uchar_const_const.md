# SecUtil::CACL::AddAccessXXXAces(SecUtil::CACL::EACCESSTYPE,ulong,void * * const,ulong const * const,uchar const * const)

- ea: `0x18010bc60`
- end: `0x18010bdd8`
- name: `?AddAccessXXXAces@CACL@SecUtil@@AEAAXW4EACCESSTYPE@12@KQEAPEAXQEBKQEBE@Z`
- size: `376`
- prototype: ``
- caller_count: `5`
- callee_count: `7`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180064688`
- `0x18010bb54`
- `0x18014164c`
- `0x180142c70`
- `0x1801ffbe8`

## callees

- `0x18010bc60`
- `0x18010bde0`
- `0x180147154`
- `0x180188d90`
- `0x180189280`
- `0x1801895b0`
- `0x1802c0010`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18010bce0`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18010bce0`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18010bcad`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18010bcad`
- `api-ms-win-security-base-l1-1-0!AddAccessAllowedAce` at `0x18010bd42`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18010bcbe`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18010bcbe`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18010bd73`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18010bd73`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SecUtil::CACL::AddAccessXXXAces(PACL *a1, __int64 a2, __int64 a3, PSID *a4, __int64 a5, _BYTE *a6)
{
  DWORD v8; // ebx
  DWORD v9; // ebx
  struct _ACL *v10; // rsi
  struct _ACL *v11; // r8
  const char *v12; // r9
  __int64 i; // rbx
  __int64 v14; // r8
  const char *v15; // r9
  LPVOID pAce[2]; // [rsp+30h] [rbp-58h] BYREF
  DWORD dwAceIndex[4]; // [rsp+40h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  *(_QWORD *)dwAceIndex = 0;
  dwAceIndex[2] = 0;
  GetAclInformation(*a1, dwAceIndex, 0xCu, AclSizeInformation);
  v8 = dwAceIndex[1] + 8;
  v9 = GetLengthSid(*a4) + v8;
  v10 = (struct _ACL *)operator new[](v9);
  pAce[1] = v10;
  if ( !InitializeAcl(v10, v9, 2u) )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x32B,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
      v12);
  SecUtil::AppendACL(v10, *a1, v11);
  for ( i = 0; !(_DWORD)i; i = 1 )
  {
    if ( a5 )
      v14 = *(unsigned int *)(a5 + 4 * i);
    else
      v14 = 270467072;
    if ( !(unsigned int)((__int64 (__fastcall *)(struct _ACL *, __int64, __int64, PSID))AddAccessAllowedAce)(
                          v10,
                          2,
                          v14,
                          *a4) )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x349,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\fteutil\\secutil.cxx",
        v15);
    if ( a6 && *a6 )
    {
      pAce[0] = 0;
      if ( GetAce(v10, dwAceIndex[0], pAce) )
        *((_BYTE *)pAce[0] + 1) = *a6;
    }
  }
  operator delete(*a1);
  *a1 = v10;
}

```

## disassembly

```asm
0x18010bc60  mov     r11, rsp
0x18010bc63  mov     [r11+10h], rbx
0x18010bc67  mov     [r11+18h], rbp
0x18010bc6b  push    rsi
0x18010bc6c  push    rdi
0x18010bc6d  push    r12
0x18010bc6f  push    r14
0x18010bc71  push    r15
0x18010bc73  sub     rsp, 60h
0x18010bc77  mov     rax, cs:__security_cookie
0x18010bc7e  xor     rax, rsp
0x18010bc81  mov     [rsp+88h+var_38], rax
0x18010bc86  mov     rbp, r9
0x18010bc89  mov     r14, rcx
0x18010bc8c  mov     r12, [rsp+88h+arg_20]
0x18010bc94  xor     eax, eax
0x18010bc96  mov     [r11-48h], rax
0x18010bc9a  mov     [rsp+88h+var_40], eax
0x18010bc9e  lea     r9d, [rax+2]; dwAclInformationClass
0x18010bca2  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18010bca6  lea     rdx, [r11-48h]; pAclInformation
0x18010bcaa  mov     rcx, [rcx]; pAcl
0x18010bcad  call    cs:__imp_GetAclInformation
0x18010bcb3  mov     ebx, [rsp+88h+var_44]
0x18010bcb7  add     ebx, 8
0x18010bcba  mov     rcx, [rbp+0]; pSid
0x18010bcbe  call    cs:__imp_GetLengthSid
0x18010bcc4  add     ebx, eax
0x18010bcc6  mov     ecx, ebx; unsigned __int64
0x18010bcc8  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18010bccd  mov     rsi, rax
0x18010bcd0  mov     [rsp+88h+var_50], rax
0x18010bcd5  mov     r8d, 2; dwAclRevision
0x18010bcdb  mov     edx, ebx; nAclLength
0x18010bcdd  mov     rcx, rax; pAcl
0x18010bce0  call    cs:__imp_InitializeAcl
0x18010bce6  test    eax, eax
0x18010bce8  jnz     short loc_18010BD04
0x18010bcea  mov     rcx, [rsp+88h]; this
0x18010bcf2  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010bcf9  mov     edx, 32Bh; void *
0x18010bcfe  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18010bd04  mov     r15, [rsp+88h+arg_28]
0x18010bd0c  mov     rdx, [r14]; PACL
0x18010bd0f  mov     rcx, rsi; pAcl
0x18010bd12  call    ?AppendACL@SecUtil@@YAXPEAU_ACL@@0@Z; SecUtil::AppendACL(_ACL *,_ACL *)
0x18010bd17  xor     ebx, ebx
0x18010bd19  cmp     ebx, 1
0x18010bd1c  jnb     loc_18010BDA7
0x18010bd22  mov     edi, ebx
0x18010bd24  test    r12, r12
0x18010bd27  jz      short loc_18010BD2F
0x18010bd29  mov     r8d, [r12+rbx*4]
0x18010bd2d  jmp     short loc_18010BD35
0x18010bd2f  mov     r8d, 101F0000h
0x18010bd35  mov     r9, [rbp+rdi*8+0]
0x18010bd3a  mov     edx, 2
0x18010bd3f  mov     rcx, rsi
0x18010bd42  mov     rax, cs:__imp_AddAccessAllowedAce
0x18010bd49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010bd4e  test    eax, eax
0x18010bd50  jz      short loc_18010BD8D
0x18010bd52  test    r15, r15
0x18010bd55  jz      short loc_18010BD89
0x18010bd57  cmp     byte ptr [r15+rdi], 0
0x18010bd5c  jz      short loc_18010BD89
0x18010bd5e  mov     [rsp+88h+pAce], 0
0x18010bd67  lea     r8, [rsp+88h+pAce]; pAce
0x18010bd6c  mov     edx, [rsp+88h+dwAceIndex]; dwAceIndex
0x18010bd70  mov     rcx, rsi; pAcl
0x18010bd73  call    cs:__imp_GetAce
0x18010bd79  test    eax, eax
0x18010bd7b  jz      short loc_18010BD89
0x18010bd7d  mov     cl, [r15+rdi]
0x18010bd81  mov     rax, [rsp+88h+pAce]
0x18010bd86  mov     [rax+1], cl
0x18010bd89  inc     ebx
0x18010bd8b  jmp     short loc_18010BD19
0x18010bd8d  mov     rcx, [rsp+88h]; this
0x18010bd95  lea     r8, aOnecoreuapBase_58; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18010bd9c  mov     edx, 349h; void *
0x18010bda1  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x18010bda7  mov     rcx, [r14]; Block
0x18010bdaa  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18010bdaf  mov     [r14], rsi
0x18010bdb2  mov     rcx, [rsp+88h+var_38]
0x18010bdb7  xor     rcx, rsp; StackCookie
0x18010bdba  call    __security_check_cookie
0x18010bdbf  lea     r11, [rsp+88h+var_28]
0x18010bdc4  mov     rbx, [r11+38h]
0x18010bdc8  mov     rbp, [r11+40h]
0x18010bdcc  mov     rsp, r11
0x18010bdcf  pop     r15
0x18010bdd1  pop     r14
0x18010bdd3  pop     r12
0x18010bdd5  pop     rdi
0x18010bdd6  pop     rsi
0x18010bdd7  retn
```
