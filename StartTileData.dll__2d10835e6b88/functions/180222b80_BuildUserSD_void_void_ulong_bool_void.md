# BuildUserSD(void *,void *,ulong,bool *,void *)

- ea: `0x180222b80`
- end: `0x180222dcc`
- name: `?BuildUserSD@@YAJPEAX0KPEA_N0@Z`
- size: `588`
- prototype: `int(void *, void *, unsigned int, bool *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180222944`

## callees

- `0x18001aca4`
- `0x1800a91e8`
- `0x1801b7d08`
- `0x180201e50`
- `0x180222b80`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222cc5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180222cc5`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180222cd6`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180222cd6`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180222c09`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180222c09`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180222c23`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180222c23`
- `ntdll!RtlAddAccessAllowedAce` at `0x180222d7b`
- `ntdll!RtlAddAccessAllowedAce` at `0x180222d7b`
- `ntdll!RtlAddAce` at `0x180222d5e`
- `ntdll!RtlAddAce` at `0x180222d5e`
- `ntdll!RtlGetAce` at `0x180222d36`
- `ntdll!RtlGetAce` at `0x180222d36`
- `ntdll!RtlLengthSid` at `0x180222cb4`
- `ntdll!RtlLengthSid` at `0x180222cb4`
- `ntdll!RtlQueryInformationAcl` at `0x180222c70`
- `ntdll!RtlQueryInformationAcl` at `0x180222c9d`
- `ntdll!RtlQueryInformationAcl` at `0x180222c70`
- `ntdll!RtlQueryInformationAcl` at `0x180222c9d`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180222bc9`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180222bc9`
- `ntdll!RtlCreateAcl` at `0x180222d10`
- `ntdll!RtlCreateAcl` at `0x180222d10`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180222d97`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180222d97`

## string_xrefs

- `0x180222bdc`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180222ce8`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180222dae`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
int __fastcall BuildUserSD(void *a1, void *a2, ACCESS_MASK a3, bool *a4, PSECURITY_DESCRIPTOR SecurityDescriptor)
{
  NTSTATUS DaclSecurityDescriptor; // eax
  __int64 v9; // rdx
  DWORD i; // ebx
  _DWORD *v12; // rdi
  ULONG v13; // eax
  ULONG v14; // r14d
  HANDLE ProcessHeap; // rax
  struct _ACL *v16; // rax
  struct _ACL *v17; // rdi
  int v18; // ebx
  NTSTATUS Acl; // eax
  __int64 v20; // rdx
  void *v21; // rdx
  ULONG AceListLength; // [rsp+20h] [rbp-50h]
  unsigned __int8 DaclDefaulted; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int8 DaclPresent[3]; // [rsp+31h] [rbp-3Fh] BYREF
  ULONG AclRevision; // [rsp+34h] [rbp-3Ch] BYREF
  PACL Dacl; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-30h] BYREF
  PVOID Ace; // [rsp+48h] [rbp-28h] BYREF
  __int64 Information; // [rsp+50h] [rbp-20h] BYREF
  int v30; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  DaclPresent[0] = 0;
  Dacl = 0;
  DaclDefaulted = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(a1, DaclPresent, &Dacl, &DaclDefaulted);
  if ( DaclSecurityDescriptor < 0 )
  {
    v9 = 41;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)DaclSecurityDescriptor,
             AceListLength);
  }
  for ( i = 0; i < Dacl->AceCount; ++i )
  {
    pAce = 0;
    if ( GetAce(Dacl, i, &pAce) )
    {
      v12 = pAce;
      if ( !*(_BYTE *)pAce && EqualSid((char *)pAce + 8, a2) && (a3 & v12[1]) == a3 )
      {
        *a4 = 1;
        return 0;
      }
    }
  }
  Information = 0;
  v30 = 0;
  DaclSecurityDescriptor = RtlQueryInformationAcl(Dacl, &Information, 0xCu, AclSizeInformation);
  if ( DaclSecurityDescriptor < 0 )
  {
    v9 = 61;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)DaclSecurityDescriptor,
             AceListLength);
  }
  AclRevision = 0;
  DaclSecurityDescriptor = RtlQueryInformationAcl(Dacl, &AclRevision, 4u, AclRevisionInformation);
  if ( DaclSecurityDescriptor < 0 )
  {
    v9 = 64;
    return wil::details::in1diag3::Return_NtStatus(
             retaddr,
             (void *)v9,
             (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
             (const char *)(unsigned int)DaclSecurityDescriptor,
             AceListLength);
  }
  v13 = RtlLengthSid(a2);
  v14 = v13 + HIDWORD(Information) + 8;
  ProcessHeap = GetProcessHeap();
  v16 = (struct _ACL *)HeapAlloc(ProcessHeap, 8u, v14);
  v17 = v16;
  if ( v16 )
  {
    Acl = RtlCreateAcl(v16, v14, AclRevision);
    if ( Acl >= 0 )
    {
      Ace = 0;
      Acl = RtlGetAce(Dacl, 0, &Ace);
      if ( Acl >= 0 )
      {
        Acl = RtlAddAce(v17, AclRevision, 0, Ace, HIDWORD(Information) - 8);
        if ( Acl >= 0 )
        {
          Acl = RtlAddAccessAllowedAce(v17, AclRevision, a3, a2);
          if ( Acl >= 0 )
          {
            Acl = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v17, 0);
            if ( Acl >= 0 )
              return 0;
            v20 = 83;
          }
          else
          {
            v20 = 81;
          }
        }
        else
        {
          v20 = 78;
        }
      }
      else
      {
        v20 = 76;
      }
    }
    else
    {
      v20 = 73;
    }
    v18 = wil::details::in1diag3::Return_NtStatus(
            retaddr,
            (void *)v20,
            (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
            (const char *)(unsigned int)Acl,
            AceListLength);
    wil::details::FreeProcessHeap((wil::details *)v17, v21);
  }
  else
  {
    v18 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47,
      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
      (const char *)0x8007000ELL,
      AceListLength);
  }
  return v18;
}

```

## disassembly

```asm
0x180222b80  push    rbp
0x180222b82  push    rbx
0x180222b83  push    rsi
0x180222b84  push    rdi
0x180222b85  push    r12
0x180222b87  push    r14
0x180222b89  push    r15
0x180222b8b  mov     rbp, rsp
0x180222b8e  sub     rsp, 70h
0x180222b92  mov     rax, cs:__security_cookie
0x180222b99  xor     rax, rsp
0x180222b9c  mov     [rbp+var_10], rax
0x180222ba0  mov     r12, [rbp+SecurityDescriptor]
0x180222ba4  mov     r14, r9
0x180222ba7  mov     esi, r8d
0x180222baa  mov     [rbp+DaclPresent], 0
0x180222bae  mov     r15, rdx
0x180222bb1  mov     [rbp+Dacl], 0
0x180222bb9  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x180222bbd  mov     [rbp+DaclDefaulted], 0
0x180222bc1  lea     r8, [rbp+Dacl]; Dacl
0x180222bc5  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x180222bc9  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180222bcf  test    eax, eax
0x180222bd1  jns     short loc_180222BED
0x180222bd3  mov     edx, 29h ; ')'; void *
0x180222bd8  mov     rcx, [rbp+38h]; this
0x180222bdc  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180222be3  mov     r9d, eax; char *
0x180222be6  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180222beb  jmp     short loc_180222C40
0x180222bed  xor     ebx, ebx
0x180222bef  mov     rcx, [rbp+Dacl]; Acl
0x180222bf3  movzx   eax, word ptr [rcx+4]
0x180222bf7  cmp     ebx, eax
0x180222bf9  jnb     short loc_180222C5B
0x180222bfb  lea     r8, [rbp+pAce]; pAce
0x180222bff  mov     [rbp+pAce], 0
0x180222c07  mov     edx, ebx; dwAceIndex
0x180222c09  call    cs:__imp_GetAce
0x180222c0f  test    eax, eax
0x180222c11  jz      short loc_180222C36
0x180222c13  mov     rdi, [rbp+pAce]
0x180222c17  cmp     byte ptr [rdi], 0
0x180222c1a  jnz     short loc_180222C36
0x180222c1c  lea     rcx, [rdi+8]; pSid1
0x180222c20  mov     rdx, r15; pSid2
0x180222c23  call    cs:__imp_EqualSid
0x180222c29  test    eax, eax
0x180222c2b  jz      short loc_180222C36
0x180222c2d  mov     eax, [rdi+4]
0x180222c30  and     eax, esi
0x180222c32  cmp     eax, esi
0x180222c34  jz      short loc_180222C3A
0x180222c36  inc     ebx
0x180222c38  jmp     short loc_180222BEF
0x180222c3a  mov     byte ptr [r14], 1
0x180222c3e  xor     eax, eax
0x180222c40  mov     rcx, [rbp+var_10]
0x180222c44  xor     rcx, rsp; StackCookie
0x180222c47  call    __security_check_cookie
0x180222c4c  add     rsp, 70h
0x180222c50  pop     r15
0x180222c52  pop     r14
0x180222c54  pop     r12
0x180222c56  pop     rdi
0x180222c57  pop     rsi
0x180222c58  pop     rbx
0x180222c59  pop     rbp
0x180222c5a  retn
0x180222c5b  xor     eax, eax
0x180222c5d  lea     rdx, [rbp+Information]; Information
0x180222c61  mov     [rbp+Information], rax
0x180222c65  mov     [rbp+var_18], eax
0x180222c68  lea     r9d, [rax+2]; InformationClass
0x180222c6c  lea     r8d, [rax+0Ch]; InformationLength
0x180222c70  call    cs:__imp_RtlQueryInformationAcl
0x180222c76  test    eax, eax
0x180222c78  jns     short loc_180222C84
0x180222c7a  mov     edx, 3Dh ; '='
0x180222c7f  jmp     loc_180222BD8
0x180222c84  mov     rcx, [rbp+Dacl]; Acl
0x180222c88  lea     rdx, [rbp+AclRevision]; Information
0x180222c8c  mov     r9d, 1; InformationClass
0x180222c92  mov     [rbp+AclRevision], 0
0x180222c99  lea     r8d, [r9+3]; InformationLength
0x180222c9d  call    cs:__imp_RtlQueryInformationAcl
0x180222ca3  test    eax, eax
0x180222ca5  jns     short loc_180222CB1
0x180222ca7  mov     edx, 40h ; '@'
0x180222cac  jmp     loc_180222BD8
0x180222cb1  mov     rcx, r15; Sid
0x180222cb4  call    cs:__imp_RtlLengthSid
0x180222cba  mov     r14d, dword ptr [rbp+Information+4]
0x180222cbe  add     r14d, 8
0x180222cc2  add     r14d, eax
0x180222cc5  call    cs:__imp_GetProcessHeap
0x180222ccb  mov     r8d, r14d; dwBytes
0x180222cce  mov     edx, 8; dwFlags
0x180222cd3  mov     rcx, rax; hHeap
0x180222cd6  call    cs:__imp_HeapAlloc
0x180222cdc  mov     rdi, rax
0x180222cdf  test    rax, rax
0x180222ce2  jnz     short loc_180222D06
0x180222ce4  mov     rcx, [rbp+38h]; this
0x180222ce8  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180222cef  mov     ebx, 8007000Eh
0x180222cf4  lea     edx, [rax+47h]; void *
0x180222cf7  mov     r9d, ebx; char *
0x180222cfa  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180222cff  mov     eax, ebx
0x180222d01  jmp     loc_180222C40
0x180222d06  mov     r8d, [rbp+AclRevision]; AclRevision
0x180222d0a  mov     edx, r14d; AclSize
0x180222d0d  mov     rcx, rdi; Acl
0x180222d10  call    cs:__imp_RtlCreateAcl
0x180222d16  test    eax, eax
0x180222d18  jns     short loc_180222D24
0x180222d1a  mov     edx, 49h ; 'I'
0x180222d1f  jmp     loc_180222DAA
0x180222d24  mov     rcx, [rbp+Dacl]; Acl
0x180222d28  lea     r8, [rbp+Ace]; Ace
0x180222d2c  xor     edx, edx; AceIndex
0x180222d2e  mov     [rbp+Ace], 0
0x180222d36  call    cs:__imp_RtlGetAce
0x180222d3c  test    eax, eax
0x180222d3e  jns     short loc_180222D47
0x180222d40  mov     edx, 4Ch ; 'L'
0x180222d45  jmp     short loc_180222DAA
0x180222d47  mov     eax, dword ptr [rbp+Information+4]
0x180222d4a  xor     r8d, r8d; StartingAceIndex
0x180222d4d  mov     r9, [rbp+Ace]; AceList
0x180222d51  add     eax, 0FFFFFFF8h
0x180222d54  mov     edx, [rbp+AclRevision]; AceRevision
0x180222d57  mov     rcx, rdi; Acl
0x180222d5a  mov     [rsp+70h+AceListLength], eax; int
0x180222d5e  call    cs:__imp_RtlAddAce
0x180222d64  test    eax, eax
0x180222d66  jns     short loc_180222D6F
0x180222d68  mov     edx, 4Eh ; 'N'
0x180222d6d  jmp     short loc_180222DAA
0x180222d6f  mov     edx, [rbp+AclRevision]; Revision
0x180222d72  mov     r9, r15; Sid
0x180222d75  mov     r8d, esi; AccessMask
0x180222d78  mov     rcx, rdi; Acl
0x180222d7b  call    cs:__imp_RtlAddAccessAllowedAce
0x180222d81  test    eax, eax
0x180222d83  jns     short loc_180222D8C
0x180222d85  mov     edx, 51h ; 'Q'
0x180222d8a  jmp     short loc_180222DAA
0x180222d8c  xor     r9d, r9d; DaclDefaulted
0x180222d8f  mov     r8, rdi; Dacl
0x180222d92  mov     dl, 1; DaclPresent
0x180222d94  mov     rcx, r12; SecurityDescriptor
0x180222d97  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180222d9d  test    eax, eax
0x180222d9f  jns     loc_180222C3E
0x180222da5  mov     edx, 53h ; 'S'; void *
0x180222daa  mov     rcx, [rbp+38h]; this
0x180222dae  lea     r8, aOnecoreuapInte_3; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180222db5  mov     r9d, eax; char *
0x180222db8  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180222dbd  mov     rcx, rdi; this
0x180222dc0  mov     ebx, eax
0x180222dc2  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180222dc7  jmp     loc_180222CFF
```
