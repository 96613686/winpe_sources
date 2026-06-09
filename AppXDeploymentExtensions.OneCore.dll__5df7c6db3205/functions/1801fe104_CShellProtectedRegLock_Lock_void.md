# CShellProtectedRegLock::Lock(void)

- ea: `0x1801fe104`
- end: `0x1801fe2fe`
- name: `?Lock@CShellProtectedRegLock@@QEAAXXZ`
- size: `506`
- prototype: `void __fastcall(CShellProtectedRegLock *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801fea04`

## callees

- `0x1800f0260`
- `0x1800fc211`
- `0x1801fd3b8`
- `0x1801fe104`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801fe146`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x1801fe146`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1801fe16f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1801fe197`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1801fe16f`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x1801fe197`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1801fe260`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x1801fe260`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801fe1ad`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x1801fe1ad`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1801fe237`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1801fe280`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1801fe237`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1801fe280`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1801fe1fa`
- `api-ms-win-security-base-l1-1-0!InitializeAcl` at `0x1801fe1fa`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fe2d3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801fe2d3`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801fe2ca`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x1801fe2ca`

## pseudocode

```c
void __fastcall CShellProtectedRegLock::Lock(CShellProtectedRegLock *this)
{
  struct _ACL *v2; // rcx
  struct _ACL *v3; // rcx
  int v4; // ebx
  DWORD v5; // r15d
  unsigned int v6; // edx
  void *v7; // rcx
  DWORD LengthSid; // r13d
  DWORD nAceListLength; // esi
  __int64 v10; // rbx
  struct _ACL *pDacl; // r14
  _WORD *v12; // rbx
  int v13; // esi
  DWORD v14; // ebx
  struct _ACL *v15; // rcx
  DWORD dwAclRevision; // [rsp+40h] [rbp-30h] BYREF
  PACL pAcl; // [rsp+48h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+50h] [rbp-20h] BYREF
  int v19; // [rsp+58h] [rbp-18h]

  if ( *((_QWORD *)this + 2) )
  {
    if ( !EqualSid(qword_1802A1518, **(PSID **)this) )
    {
      v2 = (struct _ACL *)*((_QWORD *)this + 2);
      pAclInformation = 0;
      v19 = 0;
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
          v10 = nAceListLength + v4;
          if ( (unsigned int)v10 <= 0xFFFF )
          {
            pAcl = 0;
            if ( CTLocalAllocPolicy::Alloc(v7, v6, (unsigned int)v10 + nAceListLength, (void **)&pAcl) >= 0 )
            {
              pDacl = pAcl;
              InitializeAcl(pAcl, v10, v5);
              v12 = (_WORD *)((char *)pDacl + v10);
              *(_BYTE *)v12 = 1;
              v12[1] = LengthSid + 8;
              *((_DWORD *)v12 + 1) = 2;
              memcpy_0(v12 + 4, **(const void ***)this, LengthSid);
              if ( AddAce(pDacl, v5, 0xFFFFFFFF, v12, nAceListLength) )
              {
                v13 = 0;
                v14 = 0;
                if ( !(_DWORD)pAclInformation )
                  goto LABEL_16;
                do
                {
                  v15 = (struct _ACL *)*((_QWORD *)this + 2);
                  pAcl = 0;
                  if ( GetAce(v15, v14, (LPVOID *)&pAcl) )
                  {
                    if ( !AddAce(pDacl, v5, 0xFFFFFFFF, pAcl, pAcl->AclSize) )
                      v13 = 1;
                  }
                  ++v14;
                }
                while ( v14 < (unsigned int)pAclInformation );
                if ( !v13 )
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
0x1801fe104  mov     [rsp-28h+arg_8], rbx
0x1801fe109  mov     [rsp-28h+arg_10], rsi
0x1801fe10e  push    rbp
0x1801fe10f  push    rdi
0x1801fe110  push    r13
0x1801fe112  push    r14
0x1801fe114  push    r15
0x1801fe116  mov     rbp, rsp
0x1801fe119  sub     rsp, 70h
0x1801fe11d  mov     rax, cs:__security_cookie
0x1801fe124  xor     rax, rsp
0x1801fe127  mov     [rbp+var_10], rax
0x1801fe12b  cmp     qword ptr [rcx+10h], 0
0x1801fe130  mov     rdi, rcx
0x1801fe133  jz      loc_1801FE2D9
0x1801fe139  mov     rdx, [rcx]
0x1801fe13c  lea     rcx, qword_1802A1518; pSid1
0x1801fe143  mov     rdx, [rdx]; pSid2
0x1801fe146  call    cs:__imp_EqualSid
0x1801fe14c  test    eax, eax
0x1801fe14e  jnz     loc_1801FE2D9
0x1801fe154  mov     rcx, [rdi+10h]; pAcl
0x1801fe158  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x1801fe15c  xor     eax, eax
0x1801fe15e  mov     [rbp+pAclInformation], rax
0x1801fe162  mov     [rbp+var_18], eax
0x1801fe165  lea     esi, [rax+2]
0x1801fe168  mov     r9d, esi; dwAclInformationClass
0x1801fe16b  lea     r8d, [rax+0Ch]; nAclInformationLength
0x1801fe16f  call    cs:__imp_GetAclInformation
0x1801fe175  test    eax, eax
0x1801fe177  jz      loc_1801FE2D9
0x1801fe17d  mov     rcx, [rdi+10h]; pAcl
0x1801fe181  lea     r9d, [rsi-1]; dwAclInformationClass
0x1801fe185  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x1801fe188  lea     r8d, [rsi+2]; nAclInformationLength
0x1801fe18c  lea     rdx, [rbp+dwAclRevision]; pAclInformation
0x1801fe190  mov     [rbp+dwAclRevision], 0
0x1801fe197  call    cs:__imp_GetAclInformation
0x1801fe19d  mov     rcx, [rdi]
0x1801fe1a0  mov     r15d, esi
0x1801fe1a3  test    eax, eax
0x1801fe1a5  cmovnz  r15d, [rbp+dwAclRevision]
0x1801fe1aa  mov     rcx, [rcx]; pSid
0x1801fe1ad  call    cs:__imp_GetLengthSid
0x1801fe1b3  mov     r13d, eax
0x1801fe1b6  mov     eax, 0FFFFh
0x1801fe1bb  lea     esi, [r13+8]
0x1801fe1bf  cmp     esi, eax
0x1801fe1c1  ja      loc_1801FE2D9
0x1801fe1c7  add     ebx, esi
0x1801fe1c9  cmp     ebx, eax
0x1801fe1cb  ja      loc_1801FE2D9
0x1801fe1d1  lea     r8d, [rbx+rsi]; unsigned __int64
0x1801fe1d5  mov     [rbp+pAcl], 0
0x1801fe1dd  lea     r9, [rbp+pAcl]; void **
0x1801fe1e1  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x1801fe1e6  test    eax, eax
0x1801fe1e8  js      loc_1801FE2D9
0x1801fe1ee  mov     r14, [rbp+pAcl]
0x1801fe1f2  mov     r8d, r15d; dwAclRevision
0x1801fe1f5  mov     rcx, r14; pAcl
0x1801fe1f8  mov     edx, ebx; nAclLength
0x1801fe1fa  call    cs:__imp_InitializeAcl
0x1801fe200  add     rbx, r14
0x1801fe203  mov     r8d, r13d; Size
0x1801fe206  mov     byte ptr [rbx], 1
0x1801fe209  lea     rcx, [rbx+8]; void *
0x1801fe20d  mov     [rbx+2], si
0x1801fe211  mov     dword ptr [rbx+4], 2
0x1801fe218  mov     rdx, [rdi]
0x1801fe21b  mov     rdx, [rdx]; Src
0x1801fe21e  call    memcpy_0
0x1801fe223  or      r13d, 0FFFFFFFFh
0x1801fe227  mov     [rsp+70h+nAceListLength], esi; nAceListLength
0x1801fe22b  mov     r8d, r13d; dwStartingAceIndex
0x1801fe22e  mov     r9, rbx; pAceList
0x1801fe231  mov     edx, r15d; dwAceRevision
0x1801fe234  mov     rcx, r14; pAcl
0x1801fe237  call    cs:__imp_AddAce
0x1801fe23d  test    eax, eax
0x1801fe23f  jz      loc_1801FE2D0
0x1801fe245  xor     esi, esi
0x1801fe247  xor     ebx, ebx
0x1801fe249  cmp     dword ptr [rbp+pAclInformation], ebx
0x1801fe24c  jbe     short loc_1801FE2A2
0x1801fe24e  mov     rcx, [rdi+10h]; pAcl
0x1801fe252  lea     r8, [rbp+pAcl]; pAce
0x1801fe256  mov     edx, ebx; dwAceIndex
0x1801fe258  mov     [rbp+pAcl], 0
0x1801fe260  call    cs:__imp_GetAce
0x1801fe266  test    eax, eax
0x1801fe268  jz      short loc_1801FE292
0x1801fe26a  mov     r9, [rbp+pAcl]; pAceList
0x1801fe26e  mov     r8d, r13d; dwStartingAceIndex
0x1801fe271  mov     edx, r15d; dwAceRevision
0x1801fe274  mov     rcx, r14; pAcl
0x1801fe277  movzx   eax, word ptr [r9+2]
0x1801fe27c  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x1801fe280  call    cs:__imp_AddAce
0x1801fe286  test    eax, eax
0x1801fe288  mov     eax, 1
0x1801fe28d  cmovz   esi, eax
0x1801fe290  jmp     short loc_1801FE297
0x1801fe292  mov     eax, 1
0x1801fe297  add     ebx, eax
0x1801fe299  cmp     ebx, dword ptr [rbp+pAclInformation]
0x1801fe29c  jb      short loc_1801FE24E
0x1801fe29e  test    esi, esi
0x1801fe2a0  jnz     short loc_1801FE2D0
0x1801fe2a2  mov     rcx, [rdi+8]; handle
0x1801fe2a6  xor     r9d, r9d; psidOwner
0x1801fe2a9  mov     [rsp+70h+pSacl], 0; pSacl
0x1801fe2b2  mov     r8d, 20000004h; SecurityInfo
0x1801fe2b8  mov     [rsp+70h+pDacl], r14; pDacl
0x1801fe2bd  mov     qword ptr [rsp+70h+nAceListLength], 0; psidGroup
0x1801fe2c6  lea     edx, [r9+4]; ObjectType
0x1801fe2ca  call    cs:__imp_SetSecurityInfo
0x1801fe2d0  mov     rcx, r14; hMem
0x1801fe2d3  call    cs:__imp_LocalFree
0x1801fe2d9  mov     rcx, [rbp+var_10]
0x1801fe2dd  xor     rcx, rsp; StackCookie
0x1801fe2e0  call    __security_check_cookie
0x1801fe2e5  lea     r11, [rsp+70h+var_s0]
0x1801fe2ea  mov     rbx, [r11+38h]
0x1801fe2ee  mov     rsi, [r11+40h]
0x1801fe2f2  mov     rsp, r11
0x1801fe2f5  pop     r15
0x1801fe2f7  pop     r14
0x1801fe2f9  pop     r13
0x1801fe2fb  pop     rdi
0x1801fe2fc  pop     rbp
0x1801fe2fd  retn
```
