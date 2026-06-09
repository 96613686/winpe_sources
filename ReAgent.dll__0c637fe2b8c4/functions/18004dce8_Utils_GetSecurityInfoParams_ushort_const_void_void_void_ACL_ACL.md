# Utils::GetSecurityInfoParams(ushort const *,void * *,void * *,void * *,_ACL * *,_ACL * *)

- ea: `0x18004dce8`
- end: `0x18004df5b`
- name: `?GetSecurityInfoParams@Utils@@CAKPEBGPEAPEAX11PEAPEAU_ACL@@2@Z`
- size: `627`
- prototype: `__int64 __fastcall(const unsigned __int16 *, void **, void **, void **, struct _ACL **, struct _ACL **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18004f2ac`

## callees

- `0x18004dce8`
- `0x18004f8a8`
- `0x18004f8d0`
- `0x18005cf30`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18004dd64`
- `KERNEL32!GetLastError` at `0x18004ddff`
- `KERNEL32!GetLastError` at `0x18004de48`
- `KERNEL32!GetLastError` at `0x18004de95`
- `KERNEL32!GetLastError` at `0x18004deda`
- `KERNEL32!GetLastError` at `0x18004dd64`
- `KERNEL32!GetLastError` at `0x18004ddff`
- `KERNEL32!GetLastError` at `0x18004de48`
- `KERNEL32!GetLastError` at `0x18004de95`
- `KERNEL32!GetLastError` at `0x18004deda`
- `KERNEL32!LocalFree` at `0x18004df38`
- `KERNEL32!LocalFree` at `0x18004df38`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18004ded0`
- `ADVAPI32!GetSecurityDescriptorSacl` at `0x18004ded0`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18004de8b`
- `ADVAPI32!GetSecurityDescriptorDacl` at `0x18004de8b`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18004de3e`
- `ADVAPI32!GetSecurityDescriptorGroup` at `0x18004de3e`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18004ddf5`
- `ADVAPI32!GetSecurityDescriptorOwner` at `0x18004ddf5`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004dd5a`
- `ADVAPI32!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x18004dd5a`

## pseudocode

```c
__int64 __fastcall Utils::GetSecurityInfoParams(
        const unsigned __int16 *a1,
        void **a2,
        void **a3,
        void **a4,
        struct _ACL **a5,
        struct _ACL **a6)
{
  DWORD LastError; // ebx
  _QWORD *v10; // rcx
  __int64 v11; // rdx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+20h] [rbp-40h] BYREF
  PSID pOwner; // [rsp+28h] [rbp-38h] BYREF
  PSID pGroup; // [rsp+30h] [rbp-30h] BYREF
  PACL pDacl; // [rsp+38h] [rbp-28h] BYREF
  PACL pSacl; // [rsp+40h] [rbp-20h] BYREF
  WINBOOL bOwnerDefaulted; // [rsp+48h] [rbp-18h] BYREF

  SecurityDescriptor = 0;
  pOwner = 0;
  pGroup = 0;
  pDacl = 0;
  pSacl = 0;
  bOwnerDefaulted = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
         L"O:BAG:BAD:(A;CIOI;GA;;;BA)(A;CIOI;GRGX;;;AU)(A;CIOI;GRGX;;;BU)",
         1u,
         &SecurityDescriptor,
         0) )
  {
    if ( SecurityDescriptor )
    {
      if ( GetSecurityDescriptorOwner(SecurityDescriptor, &pOwner, &bOwnerDefaulted) )
      {
        if ( GetSecurityDescriptorGroup(SecurityDescriptor, &pGroup, &bOwnerDefaulted) )
        {
          if ( GetSecurityDescriptorDacl(SecurityDescriptor, &bOwnerDefaulted, &pDacl, &bOwnerDefaulted) )
          {
            if ( GetSecurityDescriptorSacl(SecurityDescriptor, &bOwnerDefaulted, &pSacl, &bOwnerDefaulted) )
            {
              LastError = 0;
              *a2 = SecurityDescriptor;
              *a3 = pOwner;
              *a4 = pGroup;
              *a5 = pDacl;
              *a6 = pSacl;
              SecurityDescriptor = 0;
            }
            else
            {
              LastError = GetLastError();
              v10 = WPP_GLOBAL_Control;
              if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control
                && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
              {
                v11 = 190;
                goto LABEL_5;
              }
            }
          }
          else
          {
            LastError = GetLastError();
            v10 = WPP_GLOBAL_Control;
            if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
            {
              v11 = 189;
              goto LABEL_5;
            }
          }
        }
        else
        {
          LastError = GetLastError();
          v10 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          {
            v11 = 188;
            goto LABEL_5;
          }
        }
      }
      else
      {
        LastError = GetLastError();
        v10 = WPP_GLOBAL_Control;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        {
          v11 = 187;
          goto LABEL_5;
        }
      }
    }
    else
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 186, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids);
      LastError = 1336;
    }
  }
  else
  {
    LastError = GetLastError();
    v10 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v11 = 185;
LABEL_5:
      WPP_SF_d(v10[2], v11, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids, LastError);
    }
  }
  if ( SecurityDescriptor )
    LocalFree(SecurityDescriptor);
  return LastError;
}

```

## disassembly

```asm
0x18004dce8  push    rbp
0x18004dcea  push    rbx
0x18004dceb  push    rsi
0x18004dcec  push    rdi
0x18004dced  push    r12
0x18004dcef  push    r14
0x18004dcf1  push    r15
0x18004dcf3  mov     rbp, rsp
0x18004dcf6  sub     rsp, 60h
0x18004dcfa  mov     rax, cs:__security_cookie
0x18004dd01  xor     rax, rsp
0x18004dd04  mov     [rbp+var_10], rax
0x18004dd08  mov     r15, [rbp+arg_20]
0x18004dd0c  lea     rcx, StringSecurityDescriptor; "O:BAG:BAD:(A;CIOI;GA;;;BA)(A;CIOI;GRGX;"...
0x18004dd13  mov     r12, [rbp+arg_28]
0x18004dd17  mov     r14, r9
0x18004dd1a  xor     r9d, r9d; SecurityDescriptorSize
0x18004dd1d  mov     [rbp+SecurityDescriptor], 0
0x18004dd25  mov     rsi, r8
0x18004dd28  mov     [rbp+pOwner], 0
0x18004dd30  mov     rdi, rdx
0x18004dd33  mov     [rbp+pGroup], 0
0x18004dd3b  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x18004dd3f  mov     [rbp+pDacl], 0
0x18004dd47  lea     edx, [r9+1]; StringSDRevision
0x18004dd4b  mov     [rbp+pSacl], 0
0x18004dd53  mov     [rbp+bOwnerDefaulted], 0
0x18004dd5a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x18004dd60  test    eax, eax
0x18004dd62  jnz     short loc_18004DDAA
0x18004dd64  call    cs:__imp_GetLastError
0x18004dd6a  mov     ebx, eax
0x18004dd6c  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dd73  lea     rax, WPP_GLOBAL_Control
0x18004dd7a  cmp     rcx, rax
0x18004dd7d  jz      loc_18004DF2F
0x18004dd83  test    byte ptr [rcx+1Ch], 2
0x18004dd87  jz      loc_18004DF2F
0x18004dd8d  mov     edx, 0B9h
0x18004dd92  mov     rcx, [rcx+10h]
0x18004dd96  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004dd9d  mov     r9d, ebx
0x18004dda0  call    WPP_SF_d
0x18004dda5  jmp     loc_18004DF2F
0x18004ddaa  cmp     [rbp+SecurityDescriptor], 0
0x18004ddaf  jnz     short loc_18004DDE9
0x18004ddb1  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ddb8  lea     rax, WPP_GLOBAL_Control
0x18004ddbf  cmp     rcx, rax
0x18004ddc2  jz      short loc_18004DDDF
0x18004ddc4  test    byte ptr [rcx+1Ch], 2
0x18004ddc8  jz      short loc_18004DDDF
0x18004ddca  mov     rcx, [rcx+10h]
0x18004ddce  lea     r8, WPP_3998989ff07a3b09e54778c50f4c4037_Traceguids
0x18004ddd5  mov     edx, 0BAh
0x18004ddda  call    WPP_SF_
0x18004dddf  mov     ebx, 538h
0x18004dde4  jmp     loc_18004DF2F
0x18004dde9  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18004dded  lea     r8, [rbp+bOwnerDefaulted]; lpbOwnerDefaulted
0x18004ddf1  lea     rdx, [rbp+pOwner]; pOwner
0x18004ddf5  call    cs:__imp_GetSecurityDescriptorOwner
0x18004ddfb  test    eax, eax
0x18004ddfd  jnz     short loc_18004DE32
0x18004ddff  call    cs:__imp_GetLastError
0x18004de05  mov     ebx, eax
0x18004de07  mov     rcx, cs:WPP_GLOBAL_Control
0x18004de0e  lea     rax, WPP_GLOBAL_Control
0x18004de15  cmp     rcx, rax
0x18004de18  jz      loc_18004DF2F
0x18004de1e  test    byte ptr [rcx+1Ch], 2
0x18004de22  jz      loc_18004DF2F
0x18004de28  mov     edx, 0BBh
0x18004de2d  jmp     loc_18004DD92
0x18004de32  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18004de36  lea     r8, [rbp+bOwnerDefaulted]; lpbGroupDefaulted
0x18004de3a  lea     rdx, [rbp+pGroup]; pGroup
0x18004de3e  call    cs:__imp_GetSecurityDescriptorGroup
0x18004de44  test    eax, eax
0x18004de46  jnz     short loc_18004DE7B
0x18004de48  call    cs:__imp_GetLastError
0x18004de4e  mov     ebx, eax
0x18004de50  mov     rcx, cs:WPP_GLOBAL_Control
0x18004de57  lea     rax, WPP_GLOBAL_Control
0x18004de5e  cmp     rcx, rax
0x18004de61  jz      loc_18004DF2F
0x18004de67  test    byte ptr [rcx+1Ch], 2
0x18004de6b  jz      loc_18004DF2F
0x18004de71  mov     edx, 0BCh
0x18004de76  jmp     loc_18004DD92
0x18004de7b  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18004de7f  lea     r9, [rbp+bOwnerDefaulted]; lpbDaclDefaulted
0x18004de83  lea     r8, [rbp+pDacl]; pDacl
0x18004de87  lea     rdx, [rbp+bOwnerDefaulted]; lpbDaclPresent
0x18004de8b  call    cs:__imp_GetSecurityDescriptorDacl
0x18004de91  test    eax, eax
0x18004de93  jnz     short loc_18004DEC0
0x18004de95  call    cs:__imp_GetLastError
0x18004de9b  mov     ebx, eax
0x18004de9d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dea4  lea     rax, WPP_GLOBAL_Control
0x18004deab  cmp     rcx, rax
0x18004deae  jz      short loc_18004DF2F
0x18004deb0  test    byte ptr [rcx+1Ch], 2
0x18004deb4  jz      short loc_18004DF2F
0x18004deb6  mov     edx, 0BDh
0x18004debb  jmp     loc_18004DD92
0x18004dec0  mov     rcx, [rbp+SecurityDescriptor]; pSecurityDescriptor
0x18004dec4  lea     r9, [rbp+bOwnerDefaulted]; lpbSaclDefaulted
0x18004dec8  lea     r8, [rbp+pSacl]; pSacl
0x18004decc  lea     rdx, [rbp+bOwnerDefaulted]; lpbSaclPresent
0x18004ded0  call    cs:__imp_GetSecurityDescriptorSacl
0x18004ded6  test    eax, eax
0x18004ded8  jnz     short loc_18004DF05
0x18004deda  call    cs:__imp_GetLastError
0x18004dee0  mov     ebx, eax
0x18004dee2  mov     rcx, cs:WPP_GLOBAL_Control
0x18004dee9  lea     rax, WPP_GLOBAL_Control
0x18004def0  cmp     rcx, rax
0x18004def3  jz      short loc_18004DF2F
0x18004def5  test    byte ptr [rcx+1Ch], 2
0x18004def9  jz      short loc_18004DF2F
0x18004defb  mov     edx, 0BEh
0x18004df00  jmp     loc_18004DD92
0x18004df05  mov     rax, [rbp+SecurityDescriptor]
0x18004df09  xor     ebx, ebx
0x18004df0b  mov     [rdi], rax
0x18004df0e  mov     rax, [rbp+pOwner]
0x18004df12  mov     [rsi], rax
0x18004df15  mov     rax, [rbp+pGroup]
0x18004df19  mov     [r14], rax
0x18004df1c  mov     rax, [rbp+pDacl]
0x18004df20  mov     [r15], rax
0x18004df23  mov     rax, [rbp+pSacl]
0x18004df27  mov     [r12], rax
0x18004df2b  mov     [rbp+SecurityDescriptor], rbx
0x18004df2f  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x18004df33  test    rcx, rcx
0x18004df36  jz      short loc_18004DF3E
0x18004df38  call    cs:__imp_LocalFree
0x18004df3e  mov     eax, ebx
0x18004df40  mov     rcx, [rbp+var_10]
0x18004df44  xor     rcx, rsp; StackCookie
0x18004df47  call    __security_check_cookie
0x18004df4c  add     rsp, 60h
0x18004df50  pop     r15
0x18004df52  pop     r14
0x18004df54  pop     r12
0x18004df56  pop     rdi
0x18004df57  pop     rsi
0x18004df58  pop     rbx
0x18004df59  pop     rbp
0x18004df5a  retn
```
