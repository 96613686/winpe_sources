# CShellProtectedRegLock::Lock(void)

- ea: `0x180195f54`
- end: `0x18019617d`
- name: `?Lock@CShellProtectedRegLock@@QEAAXXZ`
- size: `553`
- prototype: `void __fastcall(CShellProtectedRegLock *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, authz_impersonation, registry_config, installer_update, broker_com_uri`

## callers

- `0x1801968e8`

## callees

- `0x1800aed10`
- `0x1800ba45d`
- `0x180194d48`
- `0x180195f54`
- `0x180196ae4`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180196097`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1801960ec`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x180196097`
- `api-ms-win-security-base-l1-1-0!AddAce` at `0x1801960ec`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180196001`
- `api-ms-win-security-base-l1-1-0!GetLengthSid` at `0x180196001`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180195fb7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180195fe5`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180195fb7`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180195fe5`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019614b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18019614b`
- `ADVAPI32!GetAce` at `0x1801960c6`
- `ADVAPI32!GetAce` at `0x1801960c6`
- `ADVAPI32!InitializeAcl` at `0x180196054`
- `ADVAPI32!InitializeAcl` at `0x180196054`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18019613c`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x18019613c`

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
    if ( !(unsigned __int8)anonymous_namespace_::_IsLocalSystemSid(**(PSID **)this) )
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
0x180195f54  mov     [rsp-28h+arg_8], rbx
0x180195f59  mov     [rsp-28h+arg_10], rsi
0x180195f5e  push    rbp
0x180195f5f  push    rdi
0x180195f60  push    r13
0x180195f62  push    r14
0x180195f64  push    r15
0x180195f66  mov     rbp, rsp
0x180195f69  sub     rsp, 70h
0x180195f6d  mov     rax, cs:__security_cookie
0x180195f74  xor     rax, rsp
0x180195f77  mov     [rbp+var_10], rax
0x180195f7b  cmp     qword ptr [rcx+10h], 0
0x180195f80  mov     rdi, rcx
0x180195f83  jz      loc_180196157
0x180195f89  mov     rcx, [rcx]
0x180195f8c  mov     rcx, [rcx]; pSid2
0x180195f8f  call    _anonymous_namespace____IsLocalSystemSid
0x180195f94  test    al, al
0x180195f96  jnz     loc_180196157
0x180195f9c  mov     rcx, [rdi+10h]; pAcl
0x180195fa0  lea     rdx, [rbp+pAclInformation]; pAclInformation
0x180195fa4  xor     eax, eax
0x180195fa6  mov     [rbp+pAclInformation], rax
0x180195faa  mov     [rbp+var_18], eax
0x180195fad  lea     esi, [rax+2]
0x180195fb0  mov     r9d, esi; dwAclInformationClass
0x180195fb3  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180195fb7  call    cs:__imp_GetAclInformation
0x180195fbe  nop     dword ptr [rax+rax+00h]
0x180195fc3  test    eax, eax
0x180195fc5  jz      loc_180196157
0x180195fcb  mov     rcx, [rdi+10h]; pAcl
0x180195fcf  lea     r9d, [rsi-1]; dwAclInformationClass
0x180195fd3  mov     ebx, dword ptr [rbp+pAclInformation+4]
0x180195fd6  lea     r8d, [rsi+2]; nAclInformationLength
0x180195fda  lea     rdx, [rbp+dwAclRevision]; pAclInformation
0x180195fde  mov     [rbp+dwAclRevision], 0
0x180195fe5  call    cs:__imp_GetAclInformation
0x180195fec  nop     dword ptr [rax+rax+00h]
0x180195ff1  mov     rcx, [rdi]
0x180195ff4  mov     r15d, esi
0x180195ff7  test    eax, eax
0x180195ff9  cmovnz  r15d, [rbp+dwAclRevision]
0x180195ffe  mov     rcx, [rcx]; pSid
0x180196001  call    cs:__imp_GetLengthSid
0x180196008  nop     dword ptr [rax+rax+00h]
0x18019600d  mov     r13d, eax
0x180196010  mov     eax, 0FFFFh
0x180196015  lea     esi, [r13+8]
0x180196019  cmp     esi, eax
0x18019601b  ja      loc_180196157
0x180196021  add     ebx, esi
0x180196023  cmp     ebx, eax
0x180196025  ja      loc_180196157
0x18019602b  lea     r8d, [rbx+rsi]; unsigned __int64
0x18019602f  mov     [rbp+pAcl], 0
0x180196037  lea     r9, [rbp+pAcl]; void **
0x18019603b  call    ?Alloc@CTLocalAllocPolicy@@SAJPEAXK_KPEAPEAX@Z; CTLocalAllocPolicy::Alloc(void *,ulong,unsigned __int64,void * *)
0x180196040  test    eax, eax
0x180196042  js      loc_180196157
0x180196048  mov     r14, [rbp+pAcl]
0x18019604c  mov     r8d, r15d; dwAclRevision
0x18019604f  mov     rcx, r14; pAcl
0x180196052  mov     edx, ebx; nAclLength
0x180196054  call    cs:__imp_InitializeAcl
0x18019605b  nop     dword ptr [rax+rax+00h]
0x180196060  add     rbx, r14
0x180196063  mov     r8d, r13d; Size
0x180196066  mov     byte ptr [rbx], 1
0x180196069  lea     rcx, [rbx+8]; void *
0x18019606d  mov     [rbx+2], si
0x180196071  mov     dword ptr [rbx+4], 2
0x180196078  mov     rdx, [rdi]
0x18019607b  mov     rdx, [rdx]; Src
0x18019607e  call    memcpy_0
0x180196083  or      r13d, 0FFFFFFFFh
0x180196087  mov     [rsp+70h+nAceListLength], esi; nAceListLength
0x18019608b  mov     r8d, r13d; dwStartingAceIndex
0x18019608e  mov     r9, rbx; pAceList
0x180196091  mov     edx, r15d; dwAceRevision
0x180196094  mov     rcx, r14; pAcl
0x180196097  call    cs:__imp_AddAce
0x18019609e  nop     dword ptr [rax+rax+00h]
0x1801960a3  test    eax, eax
0x1801960a5  jz      loc_180196148
0x1801960ab  xor     esi, esi
0x1801960ad  xor     ebx, ebx
0x1801960af  cmp     dword ptr [rbp+pAclInformation], ebx
0x1801960b2  jbe     short loc_180196114
0x1801960b4  mov     rcx, [rdi+10h]; pAcl
0x1801960b8  lea     r8, [rbp+pAcl]; pAce
0x1801960bc  mov     edx, ebx; dwAceIndex
0x1801960be  mov     [rbp+pAcl], 0
0x1801960c6  call    cs:__imp_GetAce
0x1801960cd  nop     dword ptr [rax+rax+00h]
0x1801960d2  test    eax, eax
0x1801960d4  jz      short loc_180196104
0x1801960d6  mov     r9, [rbp+pAcl]; pAceList
0x1801960da  mov     r8d, r13d; dwStartingAceIndex
0x1801960dd  mov     edx, r15d; dwAceRevision
0x1801960e0  mov     rcx, r14; pAcl
0x1801960e3  movzx   eax, word ptr [r9+2]
0x1801960e8  mov     [rsp+70h+nAceListLength], eax; nAceListLength
0x1801960ec  call    cs:__imp_AddAce
0x1801960f3  nop     dword ptr [rax+rax+00h]
0x1801960f8  test    eax, eax
0x1801960fa  mov     eax, 1
0x1801960ff  cmovz   esi, eax
0x180196102  jmp     short loc_180196109
0x180196104  mov     eax, 1
0x180196109  add     ebx, eax
0x18019610b  cmp     ebx, dword ptr [rbp+pAclInformation]
0x18019610e  jb      short loc_1801960B4
0x180196110  test    esi, esi
0x180196112  jnz     short loc_180196148
0x180196114  mov     rcx, [rdi+8]; handle
0x180196118  xor     r9d, r9d; psidOwner
0x18019611b  mov     [rsp+70h+pSacl], 0; pSacl
0x180196124  mov     r8d, 20000004h; SecurityInfo
0x18019612a  mov     [rsp+70h+pDacl], r14; pDacl
0x18019612f  mov     qword ptr [rsp+70h+nAceListLength], 0; psidGroup
0x180196138  lea     edx, [r9+4]; ObjectType
0x18019613c  call    cs:__imp_SetSecurityInfo
0x180196143  nop     dword ptr [rax+rax+00h]
0x180196148  mov     rcx, r14; hMem
0x18019614b  call    cs:__imp_LocalFree
0x180196152  nop     dword ptr [rax+rax+00h]
0x180196157  mov     rcx, [rbp+var_10]
0x18019615b  xor     rcx, rsp; StackCookie
0x18019615e  call    __security_check_cookie
0x180196163  lea     r11, [rsp+70h+var_s0]
0x180196168  mov     rbx, [r11+38h]
0x18019616c  mov     rsi, [r11+40h]
0x180196170  mov     rsp, r11
0x180196173  pop     r15
0x180196175  pop     r14
0x180196177  pop     r13
0x180196179  pop     rdi
0x18019617a  pop     rbp
0x18019617b  retn
```
