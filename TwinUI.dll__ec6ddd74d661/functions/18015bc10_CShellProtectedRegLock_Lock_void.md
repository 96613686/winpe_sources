# CShellProtectedRegLock::Lock(void)

- ea: `0x18015bc10`
- end: `0x18015be4c`
- name: `?Lock@CShellProtectedRegLock@@QEAAXXZ`
- size: `572`
- prototype: `void __fastcall(CShellProtectedRegLock *__hidden this)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x18015c4b4`
- `0x18036bfe0`

## callees

- `0x1800a69b8`
- `0x180142e10`
- `0x180145281`
- `0x18015bc10`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015be1a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18015be1a`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18015bc52`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18015bc52`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18015bd95`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x18015bd95`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18015bccb`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x18015bccb`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18015bd23`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x18015bd23`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18015bd66`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18015bdbb`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18015bd66`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x18015bdbb`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18015bc81`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18015bcaf`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18015bc81`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x18015bcaf`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18015be0b`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18015be0b`

## pseudocode

```c
void __fastcall CShellProtectedRegLock::Lock(CShellProtectedRegLock *this)
{
  struct _ACL *v2; // rcx
  struct _ACL *v3; // rcx
  int v4; // ebx
  DWORD v5; // r15d
  void *v6; // rcx
  DWORD LengthSid; // r13d
  DWORD nAceListLength; // esi
  __int64 v9; // rbx
  struct _ACL *pDacl; // r14
  _WORD *v11; // rbx
  int v12; // esi
  DWORD v13; // ebx
  struct _ACL *v14; // rcx
  DWORD dwAclRevision; // [rsp+40h] [rbp-30h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+50h] [rbp-20h] BYREF
  int v18; // [rsp+58h] [rbp-18h]

  if ( *((_QWORD *)this + 2) )
  {
    if ( !EqualSid(qword_18041ECB0, **(PSID **)this) )
    {
      v2 = (struct _ACL *)*((_QWORD *)this + 2);
      pAclInformation = 0;
      v18 = 0;
      if ( GetAclInformation(v2, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        v3 = (struct _ACL *)*((_QWORD *)this + 2);
        v4 = HIDWORD(pAclInformation);
        dwAclRevision = 0;
        v5 = 2;
        if ( GetAclInformation(v3, &dwAclRevision, 4u, AclRevisionInformation) )
          v5 = dwAclRevision;
        LengthSid = GetLengthSid(**(PSID **)this);
        nAceListLength = LengthSid + 8;
        if ( LengthSid + 8 <= 0xFFFF )
        {
          v9 = nAceListLength + v4;
          if ( (unsigned int)v9 <= 0xFFFF )
          {
            pAcl = 0;
            if ( CTLocalAllocPolicy::Alloc(v6, 0x40u, (unsigned int)v9 + nAceListLength, (void **)&pAcl) >= 0 )
            {
              pDacl = pAcl;
              InitializeAcl(pAcl, v9, v5);
              v11 = (_WORD *)((char *)pDacl + v9);
              *(_BYTE *)v11 = 1;
              v11[1] = LengthSid + 8;
              *((_DWORD *)v11 + 1) = 2;
              memcpy_0(v11 + 4, **(const void ***)this, LengthSid);
              if ( AddAce(pDacl, v5, 0xFFFFFFFF, v11, nAceListLength) )
              {
                v12 = 0;
                v13 = 0;
                if ( !(_DWORD)pAclInformation )
                  goto LABEL_16;
                do
                {
                  v14 = (struct _ACL *)*((_QWORD *)this + 2);
                  pAcl = 0;
                  if ( GetAce(v14, v13, (LPVOID *)&pAcl) )
                  {
                    if ( !AddAce(pDacl, v5, 0xFFFFFFFF, pAcl, pAcl->AclSize) )
                      v12 = 1;
                  }
                  ++v13;
                }
                while ( v13 < (unsigned int)pAclInformation );
                if ( !v12 )
LABEL_16:
                  SetSecurityInfo(*((HANDLE *)this + 1), SE_REGISTRY_KEY, 0x20000004u, 0, 0, pDacl, 0);
              }
              LocalFree(pDacl);
            }
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x18015bc10  mov     [rsp-28h+arg_8], rbx
0x18015bc15  mov     [rsp-28h+arg_10], rsi
0x18015bc1a  push    rbp
0x18015bc1b  push    rdi
0x18015bc1c  push    r13
0x18015bc1e  push    r14
0x18015bc20  push    r15
0x18015bc22  mov     rbp, rsp
0x18015bc25  sub     rsp, 70h
0x18015bc29  mov     rax, cs:__security_cookie
0x18015bc30  xor     rax, rsp
0x18015bc33  mov     [rbp+var_10], rax
0x18015bc37  cmp     qword ptr [rcx+10h], 0
0x18015bc3c  mov     rdi, rcx
0x18015bc3f  jz      loc_18015BE26
0x18015bc45  mov     rdx, [rcx]
0x18015bc48  lea     rcx, qword_18041ECB0; pSid1
0x18015bc4f  mov     rdx, [rdx]; pSid2
0x18015bc52  call    cs:__imp_EqualSid
0x18015bc59  nop     dword ptr [rax+rax+00h]
0x18015bc5e  test    eax, eax
0x18015bc60  jnz     loc_18015BE26
0x18015bc66  mov     rcx, [rdi+10h]; pAcl
0x18015bc6a  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x18015bc6e  xor     eax, eax
0x18015bc70  mov     [rbp+pAclInformation], rax
0x18015bc74  mov     [rbp+var_18], eax
0x18015bc77  lea     esi, [rax+2]
0x18015bc7a  mov     r9d, esi; dwAclInformationClass
0x18015bc7d  lea     r8d, [rax+0Ch]; nAclInformationLength
0x18015bc81  call    cs:__imp_GetAclInformation
0x18015bc88  nop     dword ptr [rax+rax+00h]
0x18015bc8d  test    eax, eax
0x18015bc8f  jz      loc_18015BE26
0x18015bc95  mov     rcx, [rdi+10h]; pAcl
0x18015bc99  lea     r9d, [rsi-1]; dwAclInformationClass
0x18015bc9d  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x18015bca0  lea     r8d, [rsi+2]; nAclInformationLength
0x18015bca4  lea     rdx, [rbp+dwAclRevision]; pAclInformation
0x18015bca8  mov     [rbp+dwAclRevision], 0
0x18015bcaf  call    cs:__imp_GetAclInformation
0x18015bcb6  nop     dword ptr [rax+rax+00h]
0x18015bcbb  mov     rcx, [rdi]
0x18015bcbe  mov     r15d, esi
0x18015bcc1  test    eax, eax
0x18015bcc3  cmovnz  r15d, [rbp+dwAclRevision]
0x18015bcc8  mov     rcx, [rcx]; pSid
0x18015bccb  call    cs:__imp_GetLengthSid
0x18015bcd2  nop     dword ptr [rax+rax+00h]
0x18015bcd7  mov     r13d, eax
0x18015bcda  mov     eax, 0FFFFh
0x18015bcdf  lea     esi, [r13+8]
0x18015bce3  cmp     esi, eax
0x18015bce5  ja      loc_18015BE26
0x18015bceb  add     ebx, esi
0x18015bced  cmp     ebx, eax
0x18015bcef  ja      loc_18015BE26
0x18015bcf5  lea     r8d, [rbx+rsi]; unsigned __int64
0x18015bcf9  mov     [rbp+pAcl], 0
0x18015bd01  lea     r9, [rbp+pAcl]; void **
0x18015bd05  mov     edx, 40h ; '@'; unsigned int
0x18015bd0a  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x18015bd0f  test    eax, eax
0x18015bd11  js      loc_18015BE26
0x18015bd17  mov     r14, [rbp+pAcl]
0x18015bd1b  mov     r8d, r15d; dwAclRevision
0x18015bd1e  mov     rcx, r14; pAcl
0x18015bd21  mov     edx, ebx; nAclLength
0x18015bd23  call    cs:__imp_InitializeAcl
0x18015bd2a  nop     dword ptr [rax+rax+00h]
0x18015bd2f  add     rbx, r14
0x18015bd32  mov     r8d, r13d; Size
0x18015bd35  mov     byte ptr [rbx], 1
0x18015bd38  lea     rcx, [rbx+8]; void *
0x18015bd3c  mov     [rbx+2], si
0x18015bd40  mov     dword ptr [rbx+4], 2
0x18015bd47  mov     rdx, [rdi]
0x18015bd4a  mov     rdx, [rdx]; Src
0x18015bd4d  call    memcpy_0
0x18015bd52  or      r13d, 0FFFFFFFFh
0x18015bd56  mov     [rsp+70h+nAceListLength], esi; nAceListLength
0x18015bd5a  mov     r8d, r13d; dwStartingAceIndex
0x18015bd5d  mov     r9, rbx; pAceList
0x18015bd60  mov     edx, r15d; dwAceRevision
0x18015bd63  mov     rcx, r14; pAcl
0x18015bd66  call    cs:__imp_AddAce
0x18015bd6d  nop     dword ptr [rax+rax+00h]
0x18015bd72  test    eax, eax
0x18015bd74  jz      loc_18015BE17
0x18015bd7a  xor     esi, esi
0x18015bd7c  xor     ebx, ebx
0x18015bd7e  cmp     dword ptr [rbp+pAclInformation], ebx
0x18015bd81  jbe     short loc_18015BDE3
0x18015bd83  mov     rcx, [rdi+10h]; pAcl
0x18015bd87  lea     r8, [rbp+pAcl]; pAce
0x18015bd8b  mov     edx, ebx; dwAceIndex
0x18015bd8d  mov     [rbp+pAcl], 0
0x18015bd95  call    cs:__imp_GetAce
0x18015bd9c  nop     dword ptr [rax+rax+00h]
0x18015bda1  test    eax, eax
0x18015bda3  jz      short loc_18015BDD3
0x18015bda5  mov     r9, [rbp+pAcl]; pAceList
0x18015bda9  mov     r8d, r13d; dwStartingAceIndex
0x18015bdac  mov     edx, r15d; dwAceRevision
0x18015bdaf  mov     rcx, r14; pAcl
0x18015bdb2  movzx   eax, word ptr [r9+2]
0x18015bdb7  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x18015bdbb  call    cs:__imp_AddAce
0x18015bdc2  nop     dword ptr [rax+rax+00h]
0x18015bdc7  test    eax, eax
0x18015bdc9  mov     eax, 1
0x18015bdce  cmovz   esi, eax
0x18015bdd1  jmp     short loc_18015BDD8
0x18015bdd3  mov     eax, 1
0x18015bdd8  add     ebx, eax
0x18015bdda  cmp     ebx, dword ptr [rbp+pAclInformation]
0x18015bddd  jb      short loc_18015BD83
0x18015bddf  test    esi, esi
0x18015bde1  jnz     short loc_18015BE17
0x18015bde3  mov     rcx, [rdi+8]; handle
0x18015bde7  xor     r9d, r9d; psidOwner
0x18015bdea  mov     [rsp+70h+pSacl], 0; pSacl
0x18015bdf3  mov     r8d, 20000004h; SecurityInfo
0x18015bdf9  mov     [rsp+70h+pDacl], r14; pDacl
0x18015bdfe  mov     qword ptr [rsp+70h+nAceListLength], 0; psidGroup
0x18015be07  lea     edx, [r9+4]; ObjectType
0x18015be0b  call    cs:__imp_SetSecurityInfo
0x18015be12  nop     dword ptr [rax+rax+00h]
0x18015be17  mov     rcx, r14; hMem
0x18015be1a  call    cs:__imp_LocalFree
0x18015be21  nop     dword ptr [rax+rax+00h]
0x18015be26  mov     rcx, [rbp+var_10]
0x18015be2a  xor     rcx, rsp; StackCookie
0x18015be2d  call    __security_check_cookie
0x18015be32  lea     r11, [rsp+70h+var_s0]
0x18015be37  mov     rbx, [r11+38h]
0x18015be3b  mov     rsi, [r11+40h]
0x18015be3f  mov     rsp, r11
0x18015be42  pop     r15
0x18015be44  pop     r14
0x18015be46  pop     r13
0x18015be48  pop     rdi
0x18015be49  pop     rbp
0x18015be4a  retn
```
