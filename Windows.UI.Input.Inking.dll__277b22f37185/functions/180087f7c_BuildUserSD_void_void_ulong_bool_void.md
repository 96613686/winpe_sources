# BuildUserSD(void *,void *,ulong,bool *,void *)

- ea: `0x180087f7c`
- end: `0x1800881c8`
- name: `?BuildUserSD@@YAJPEAX0KPEA_N0@Z`
- size: `588`
- prototype: `int(void *, void *, unsigned int, bool *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180087c40`

## callees

- `0x1800062a0`
- `0x18000e66c`
- `0x18001332c`
- `0x180087f7c`
- `0x180089030`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800880c1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800880c1`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800880d2`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x1800880d2`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008801f`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x18008801f`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180088005`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180088005`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180088193`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180088193`
- `ntdll!RtlAddAccessAllowedAce` at `0x180088177`
- `ntdll!RtlAddAccessAllowedAce` at `0x180088177`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180087fc5`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180087fc5`
- `ntdll!RtlAddAce` at `0x18008815a`
- `ntdll!RtlAddAce` at `0x18008815a`
- `ntdll!RtlGetAce` at `0x180088132`
- `ntdll!RtlGetAce` at `0x180088132`
- `ntdll!RtlCreateAcl` at `0x18008810c`
- `ntdll!RtlCreateAcl` at `0x18008810c`
- `ntdll!RtlLengthSid` at `0x1800880b0`
- `ntdll!RtlLengthSid` at `0x1800880b0`
- `ntdll!RtlQueryInformationAcl` at `0x18008806c`
- `ntdll!RtlQueryInformationAcl` at `0x180088099`
- `ntdll!RtlQueryInformationAcl` at `0x18008806c`
- `ntdll!RtlQueryInformationAcl` at `0x180088099`

## string_xrefs

- `0x180087fd8`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800880e4`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x1800881aa`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

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
0x180087f7c  push    rbp
0x180087f7e  push    rbx
0x180087f7f  push    rsi
0x180087f80  push    rdi
0x180087f81  push    r12
0x180087f83  push    r14
0x180087f85  push    r15
0x180087f87  mov     rbp, rsp
0x180087f8a  sub     rsp, 70h
0x180087f8e  mov     rax, cs:__security_cookie
0x180087f95  xor     rax, rsp
0x180087f98  mov     [rbp+var_10], rax
0x180087f9c  mov     r12, [rbp+SecurityDescriptor]
0x180087fa0  mov     r14, r9
0x180087fa3  mov     esi, r8d
0x180087fa6  mov     [rbp+DaclPresent], 0
0x180087faa  mov     r15, rdx
0x180087fad  mov     [rbp+Dacl], 0
0x180087fb5  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x180087fb9  mov     [rbp+DaclDefaulted], 0
0x180087fbd  lea     r8, [rbp+Dacl]; Dacl
0x180087fc1  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x180087fc5  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180087fcb  test    eax, eax
0x180087fcd  jns     short loc_180087FE9
0x180087fcf  mov     edx, 29h ; ')'; void *
0x180087fd4  mov     rcx, [rbp+38h]; this
0x180087fd8  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180087fdf  mov     r9d, eax; char *
0x180087fe2  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180087fe7  jmp     short loc_18008803C
0x180087fe9  xor     ebx, ebx
0x180087feb  mov     rcx, [rbp+Dacl]; Acl
0x180087fef  movzx   eax, word ptr [rcx+4]
0x180087ff3  cmp     ebx, eax
0x180087ff5  jnb     short loc_180088057
0x180087ff7  lea     r8, [rbp+pAce]; pAce
0x180087ffb  mov     [rbp+pAce], 0
0x180088003  mov     edx, ebx; dwAceIndex
0x180088005  call    cs:__imp_GetAce
0x18008800b  test    eax, eax
0x18008800d  jz      short loc_180088032
0x18008800f  mov     rdi, [rbp+pAce]
0x180088013  cmp     byte ptr [rdi], 0
0x180088016  jnz     short loc_180088032
0x180088018  lea     rcx, [rdi+8]; pSid1
0x18008801c  mov     rdx, r15; pSid2
0x18008801f  call    cs:__imp_EqualSid
0x180088025  test    eax, eax
0x180088027  jz      short loc_180088032
0x180088029  mov     eax, [rdi+4]
0x18008802c  and     eax, esi
0x18008802e  cmp     eax, esi
0x180088030  jz      short loc_180088036
0x180088032  inc     ebx
0x180088034  jmp     short loc_180087FEB
0x180088036  mov     byte ptr [r14], 1
0x18008803a  xor     eax, eax
0x18008803c  mov     rcx, [rbp+var_10]
0x180088040  xor     rcx, rsp; StackCookie
0x180088043  call    __security_check_cookie
0x180088048  add     rsp, 70h
0x18008804c  pop     r15
0x18008804e  pop     r14
0x180088050  pop     r12
0x180088052  pop     rdi
0x180088053  pop     rsi
0x180088054  pop     rbx
0x180088055  pop     rbp
0x180088056  retn
0x180088057  xor     eax, eax
0x180088059  lea     rdx, [rbp+Information]; Information
0x18008805d  mov     [rbp+Information], rax
0x180088061  mov     [rbp+var_18], eax
0x180088064  lea     r9d, [rax+2]; InformationClass
0x180088068  lea     r8d, [rax+0Ch]; InformationLength
0x18008806c  call    cs:__imp_RtlQueryInformationAcl
0x180088072  test    eax, eax
0x180088074  jns     short loc_180088080
0x180088076  mov     edx, 3Dh ; '='
0x18008807b  jmp     loc_180087FD4
0x180088080  mov     rcx, [rbp+Dacl]; Acl
0x180088084  lea     rdx, [rbp+AclRevision]; Information
0x180088088  mov     r9d, 1; InformationClass
0x18008808e  mov     [rbp+AclRevision], 0
0x180088095  lea     r8d, [r9+3]; InformationLength
0x180088099  call    cs:__imp_RtlQueryInformationAcl
0x18008809f  test    eax, eax
0x1800880a1  jns     short loc_1800880AD
0x1800880a3  mov     edx, 40h ; '@'
0x1800880a8  jmp     loc_180087FD4
0x1800880ad  mov     rcx, r15; Sid
0x1800880b0  call    cs:__imp_RtlLengthSid
0x1800880b6  mov     r14d, dword ptr [rbp+Information+4]
0x1800880ba  add     r14d, 8
0x1800880be  add     r14d, eax
0x1800880c1  call    cs:__imp_GetProcessHeap
0x1800880c7  mov     r8d, r14d; dwBytes
0x1800880ca  mov     edx, 8; dwFlags
0x1800880cf  mov     rcx, rax; hHeap
0x1800880d2  call    cs:__imp_HeapAlloc
0x1800880d8  mov     rdi, rax
0x1800880db  test    rax, rax
0x1800880de  jnz     short loc_180088102
0x1800880e0  mov     rcx, [rbp+38h]; this
0x1800880e4  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800880eb  mov     ebx, 8007000Eh
0x1800880f0  lea     edx, [rax+47h]; void *
0x1800880f3  mov     r9d, ebx; char *
0x1800880f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800880fb  mov     eax, ebx
0x1800880fd  jmp     loc_18008803C
0x180088102  mov     r8d, [rbp+AclRevision]; AclRevision
0x180088106  mov     edx, r14d; AclSize
0x180088109  mov     rcx, rdi; Acl
0x18008810c  call    cs:__imp_RtlCreateAcl
0x180088112  test    eax, eax
0x180088114  jns     short loc_180088120
0x180088116  mov     edx, 49h ; 'I'
0x18008811b  jmp     loc_1800881A6
0x180088120  mov     rcx, [rbp+Dacl]; Acl
0x180088124  lea     r8, [rbp+Ace]; Ace
0x180088128  xor     edx, edx; AceIndex
0x18008812a  mov     [rbp+Ace], 0
0x180088132  call    cs:__imp_RtlGetAce
0x180088138  test    eax, eax
0x18008813a  jns     short loc_180088143
0x18008813c  mov     edx, 4Ch ; 'L'
0x180088141  jmp     short loc_1800881A6
0x180088143  mov     eax, dword ptr [rbp+Information+4]
0x180088146  xor     r8d, r8d; StartingAceIndex
0x180088149  mov     r9, [rbp+Ace]; AceList
0x18008814d  add     eax, 0FFFFFFF8h
0x180088150  mov     edx, [rbp+AclRevision]; AceRevision
0x180088153  mov     rcx, rdi; Acl
0x180088156  mov     [rsp+70h+AceListLength], eax; int
0x18008815a  call    cs:__imp_RtlAddAce
0x180088160  test    eax, eax
0x180088162  jns     short loc_18008816B
0x180088164  mov     edx, 4Eh ; 'N'
0x180088169  jmp     short loc_1800881A6
0x18008816b  mov     edx, [rbp+AclRevision]; Revision
0x18008816e  mov     r9, r15; Sid
0x180088171  mov     r8d, esi; AccessMask
0x180088174  mov     rcx, rdi; Acl
0x180088177  call    cs:__imp_RtlAddAccessAllowedAce
0x18008817d  test    eax, eax
0x18008817f  jns     short loc_180088188
0x180088181  mov     edx, 51h ; 'Q'
0x180088186  jmp     short loc_1800881A6
0x180088188  xor     r9d, r9d; DaclDefaulted
0x18008818b  mov     r8, rdi; Dacl
0x18008818e  mov     dl, 1; DaclPresent
0x180088190  mov     rcx, r12; SecurityDescriptor
0x180088193  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180088199  test    eax, eax
0x18008819b  jns     loc_18008803A
0x1800881a1  mov     edx, 53h ; 'S'; void *
0x1800881a6  mov     rcx, [rbp+38h]; this
0x1800881aa  lea     r8, aOnecoreuapInte_0; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x1800881b1  mov     r9d, eax; char *
0x1800881b4  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x1800881b9  mov     rcx, rdi; this
0x1800881bc  mov     ebx, eax
0x1800881be  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x1800881c3  jmp     loc_1800880FB
```
