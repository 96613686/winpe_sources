# CShellProtectedRegLock::Unlock(void)

- ea: `0x180196990`
- end: `0x180196ade`
- name: `?Unlock@CShellProtectedRegLock@@QEAAXXZ`
- size: `334`
- prototype: `void __fastcall(CShellProtectedRegLock *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1801968e8`

## callees

- `0x1800aed10`
- `0x180196990`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180196a18`
- `api-ms-win-security-base-l1-1-0!GetAclInformation` at `0x180196a18`
- `ADVAPI32!GetAce` at `0x180196a4c`
- `ADVAPI32!GetAce` at `0x180196a4c`
- `ADVAPI32!DeleteAce` at `0x180196a71`
- `ADVAPI32!DeleteAce` at `0x180196a71`
- `ADVAPI32!GetSecurityInfo` at `0x1801969e0`
- `ADVAPI32!GetSecurityInfo` at `0x1801969e0`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180196aa9`
- `api-ms-win-security-provider-l1-1-0!SetSecurityInfo` at `0x180196aa9`

## pseudocode

```c
void __fastcall CShellProtectedRegLock::Unlock(HANDLE *this)
{
  PACL *v1; // rdi
  struct _ACL *v3; // rcx
  signed int i; // ebx
  struct _ACL *v5; // rcx
  LPVOID pAce; // [rsp+40h] [rbp-28h] BYREF
  __int64 pAclInformation; // [rsp+48h] [rbp-20h] BYREF
  int v8; // [rsp+50h] [rbp-18h]

  v1 = (PACL *)(this + 2);
  if ( !GetSecurityInfo(this[1], SE_REGISTRY_KEY, 4u, 0, 0, (PACL *)this + 2, 0, this + 3) )
  {
    v3 = *v1;
    pAclInformation = 0;
    v8 = 0;
    if ( v3 )
    {
      if ( GetAclInformation(v3, &pAclInformation, 0xCu, AclSizeInformation) )
      {
        for ( i = pAclInformation - 1; i >= 0; --i )
        {
          v5 = *v1;
          pAce = 0;
          if ( GetAce(v5, i, &pAce) && *(_BYTE *)pAce == 1 && *((_DWORD *)pAce + 1) == 2 )
          {
            if ( DeleteAce(*v1, i) )
              SetSecurityInfo(this[1], SE_REGISTRY_KEY, 4u, 0, 0, *v1, 0);
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180196990  mov     r11, rsp
0x180196993  mov     [r11+10h], rbx
0x180196997  mov     [r11+18h], rsi
0x18019699b  push    rdi
0x18019699c  sub     rsp, 60h
0x1801969a0  mov     rax, cs:__security_cookie
0x1801969a7  xor     rax, rsp
0x1801969aa  mov     [rsp+68h+var_10], rax
0x1801969af  lea     rax, [rcx+18h]
0x1801969b3  xor     r9d, r9d; ppsidOwner
0x1801969b6  mov     [r11-30h], rax
0x1801969ba  lea     rdi, [rcx+10h]
0x1801969be  mov     qword ptr [r11-38h], 0
0x1801969c6  mov     rsi, rcx
0x1801969c9  mov     rcx, [rcx+8]; handle
0x1801969cd  lea     edx, [r9+4]; ObjectType
0x1801969d1  mov     [r11-40h], rdi
0x1801969d5  mov     r8d, edx; SecurityInfo
0x1801969d8  mov     qword ptr [r11-48h], 0
0x1801969e0  call    cs:__imp_GetSecurityInfo
0x1801969e7  nop     dword ptr [rax+rax+00h]
0x1801969ec  test    eax, eax
0x1801969ee  jnz     loc_180196ABE
0x1801969f4  mov     rcx, [rdi]; pAcl
0x1801969f7  xor     eax, eax
0x1801969f9  mov     [rsp+68h+pAclInformation], rax
0x1801969fe  mov     [rsp+68h+var_18], eax
0x180196a02  test    rcx, rcx
0x180196a05  jz      loc_180196ABE
0x180196a0b  lea     r9d, [rax+2]; dwAclInformationClass
0x180196a0f  lea     r8d, [rax+0Ch]; nAclInformationLength
0x180196a13  lea     rdx, [rsp+68h+pAclInformation]; pAclInformation
0x180196a18  call    cs:__imp_GetAclInformation
0x180196a1f  nop     dword ptr [rax+rax+00h]
0x180196a24  test    eax, eax
0x180196a26  jz      loc_180196ABE
0x180196a2c  mov     ebx, dword ptr [rsp+68h+pAclInformation]
0x180196a30  sub     ebx, 1
0x180196a33  js      loc_180196ABE
0x180196a39  mov     rcx, [rdi]; pAcl
0x180196a3c  lea     r8, [rsp+68h+pAce]; pAce
0x180196a41  mov     edx, ebx; dwAceIndex
0x180196a43  mov     [rsp+68h+pAce], 0
0x180196a4c  call    cs:__imp_GetAce
0x180196a53  nop     dword ptr [rax+rax+00h]
0x180196a58  test    eax, eax
0x180196a5a  jz      short loc_180196AB5
0x180196a5c  mov     rax, [rsp+68h+pAce]
0x180196a61  cmp     byte ptr [rax], 1
0x180196a64  jnz     short loc_180196AB5
0x180196a66  cmp     dword ptr [rax+4], 2
0x180196a6a  jnz     short loc_180196AB5
0x180196a6c  mov     rcx, [rdi]; pAcl
0x180196a6f  mov     edx, ebx; dwAceIndex
0x180196a71  call    cs:__imp_DeleteAce
0x180196a78  nop     dword ptr [rax+rax+00h]
0x180196a7d  test    eax, eax
0x180196a7f  jz      short loc_180196AB5
0x180196a81  mov     rax, [rdi]
0x180196a84  xor     r9d, r9d; psidOwner
0x180196a87  mov     rcx, [rsi+8]; handle
0x180196a8b  mov     [rsp+68h+pSacl], 0; pSacl
0x180196a94  mov     [rsp+68h+pDacl], rax; pDacl
0x180196a99  lea     edx, [r9+4]; ObjectType
0x180196a9d  mov     [rsp+68h+psidGroup], 0; psidGroup
0x180196aa6  mov     r8d, edx; SecurityInfo
0x180196aa9  call    cs:__imp_SetSecurityInfo
0x180196ab0  nop     dword ptr [rax+rax+00h]
0x180196ab5  add     ebx, 0FFFFFFFFh
0x180196ab8  jns     loc_180196A39
0x180196abe  mov     rcx, [rsp+68h+var_10]
0x180196ac3  xor     rcx, rsp; StackCookie
0x180196ac6  call    __security_check_cookie
0x180196acb  lea     r11, [rsp+68h+var_8]
0x180196ad0  mov     rbx, [r11+18h]
0x180196ad4  mov     rsi, [r11+20h]
0x180196ad8  mov     rsp, r11
0x180196adb  pop     rdi
0x180196adc  retn
```
