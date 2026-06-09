# BuildUserSD(void *,void *,ulong,bool *,void *)

- ea: `0x180025d20`
- end: `0x180025ff0`
- name: `?BuildUserSD@@YAJPEAX0KPEA_N0@Z`
- size: `720`
- prototype: `int(void *, void *, unsigned int, bool *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x180025924`

## callees

- `0x18000556c`
- `0x180006eac`
- `0x180025d20`
- `0x18002b724`
- `0x180069730`

## import_xrefs

- `ntdll!RtlCreateAcl` at `0x180025e9c`
- `ntdll!RtlCreateAcl` at `0x180025e9c`
- `ntdll!RtlGetAce` at `0x180025edd`
- `ntdll!RtlGetAce` at `0x180025edd`
- `ntdll!RtlAddAce` at `0x180025f26`
- `ntdll!RtlAddAce` at `0x180025f26`
- `ntdll!RtlLengthSid` at `0x180025e3f`
- `ntdll!RtlLengthSid` at `0x180025e3f`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180025fa1`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x180025fa1`
- `ntdll!RtlAddAccessAllowedAce` at `0x180025f64`
- `ntdll!RtlAddAccessAllowedAce` at `0x180025f64`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180025d69`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x180025d69`
- `ntdll!RtlQueryInformationAcl` at `0x180025dfb`
- `ntdll!RtlQueryInformationAcl` at `0x180025e28`
- `ntdll!RtlQueryInformationAcl` at `0x180025dfb`
- `ntdll!RtlQueryInformationAcl` at `0x180025e28`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025e61`
- `api-ms-win-core-heap-l1-1-0!HeapAlloc` at `0x180025e61`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025e50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180025e50`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180025dac`
- `api-ms-win-security-base-l1-1-0!GetAce` at `0x180025dac`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180025dc6`
- `api-ms-win-security-base-l1-1-0!EqualSid` at `0x180025dc6`

## string_xrefs

- `0x180025d7f`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025e7b`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025ead`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025eee`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025f37`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025f75`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`
- `0x180025fb2`: `onecoreuap\internal\sdk\inc\UserModelTokenHelpers.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  void *v20; // rdx
  NTSTATUS v21; // eax
  void *v22; // rdx
  NTSTATUS v23; // eax
  void *v24; // rdx
  NTSTATUS v25; // eax
  void *v26; // rdx
  NTSTATUS v27; // eax
  void *v28; // rdx
  ULONG AceListLength; // [rsp+20h] [rbp-50h]
  ULONG AceListLengtha; // [rsp+20h] [rbp-50h]
  unsigned __int8 DaclDefaulted; // [rsp+30h] [rbp-40h] BYREF
  unsigned __int8 DaclPresent[3]; // [rsp+31h] [rbp-3Fh] BYREF
  ULONG AclRevision; // [rsp+34h] [rbp-3Ch] BYREF
  PACL Dacl; // [rsp+38h] [rbp-38h] BYREF
  LPVOID pAce; // [rsp+40h] [rbp-30h] BYREF
  PVOID Ace; // [rsp+48h] [rbp-28h] BYREF
  __int64 Information; // [rsp+50h] [rbp-20h] BYREF
  int v38; // [rsp+58h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+38h]

  DaclPresent[0] = 0;
  Dacl = 0;
  DaclDefaulted = 0;
  DaclSecurityDescriptor = RtlGetDaclSecurityDescriptor(a1, DaclPresent, &Dacl, &DaclDefaulted);
  if ( DaclSecurityDescriptor >= 0 )
  {
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
    v38 = 0;
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
        v21 = RtlGetAce(Dacl, 0, &Ace);
        if ( v21 >= 0 )
        {
          v23 = RtlAddAce(v17, AclRevision, 0, Ace, HIDWORD(Information) - 8);
          if ( v23 >= 0 )
          {
            v25 = RtlAddAccessAllowedAce(v17, AclRevision, a3, a2);
            if ( v25 >= 0 )
            {
              v27 = RtlSetDaclSecurityDescriptor(SecurityDescriptor, 1u, v17, 0);
              if ( v27 >= 0 )
                return 0;
              v18 = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x53,
                      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                      (const char *)(unsigned int)v27,
                      AceListLengtha);
              wil::details::FreeProcessHeap((wil::details *)v17, v28);
            }
            else
            {
              v18 = wil::details::in1diag3::Return_NtStatus(
                      retaddr,
                      (void *)0x51,
                      (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                      (const char *)(unsigned int)v25,
                      AceListLengtha);
              wil::details::FreeProcessHeap((wil::details *)v17, v26);
            }
          }
          else
          {
            v18 = wil::details::in1diag3::Return_NtStatus(
                    retaddr,
                    (void *)0x4E,
                    (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                    (const char *)(unsigned int)v23,
                    AceListLengtha);
            wil::details::FreeProcessHeap((wil::details *)v17, v24);
          }
        }
        else
        {
          v18 = wil::details::in1diag3::Return_NtStatus(
                  retaddr,
                  (void *)0x4C,
                  (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                  (const char *)(unsigned int)v21,
                  AceListLength);
          wil::details::FreeProcessHeap((wil::details *)v17, v22);
        }
      }
      else
      {
        v18 = wil::details::in1diag3::Return_NtStatus(
                retaddr,
                (void *)0x49,
                (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
                (const char *)(unsigned int)Acl,
                AceListLength);
        wil::details::FreeProcessHeap((wil::details *)v17, v20);
      }
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
  v9 = 41;
  return wil::details::in1diag3::Return_NtStatus(
           retaddr,
           (void *)v9,
           (unsigned int)"onecoreuap\\internal\\sdk\\inc\\UserModelTokenHelpers.h",
           (const char *)(unsigned int)DaclSecurityDescriptor,
           AceListLength);
}

```

## disassembly

```asm
0x180025d20  push    rbp
0x180025d22  push    rbx
0x180025d23  push    rsi
0x180025d24  push    rdi
0x180025d25  push    r12
0x180025d27  push    r14
0x180025d29  push    r15
0x180025d2b  mov     rbp, rsp
0x180025d2e  sub     rsp, 70h
0x180025d32  mov     rax, cs:__security_cookie
0x180025d39  xor     rax, rsp
0x180025d3c  mov     [rbp+var_10], rax
0x180025d40  mov     r14, r9
0x180025d43  mov     esi, r8d
0x180025d46  mov     r15, rdx
0x180025d49  mov     r12, [rbp+SecurityDescriptor]
0x180025d4d  mov     [rbp+DaclPresent], 0
0x180025d51  mov     [rbp+Dacl], 0
0x180025d59  mov     [rbp+DaclDefaulted], 0
0x180025d5d  lea     r9, [rbp+DaclDefaulted]; DaclDefaulted
0x180025d61  lea     r8, [rbp+Dacl]; Dacl
0x180025d65  lea     rdx, [rbp+DaclPresent]; DaclPresent
0x180025d69  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x180025d6f  test    eax, eax
0x180025d71  jns     short loc_180025D90
0x180025d73  mov     edx, 29h ; ')'; void *
0x180025d78  mov     rcx, [rbp+38h]; this
0x180025d7c  mov     r9d, eax; char *
0x180025d7f  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025d86  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025d8b  jmp     loc_180025FD5
0x180025d90  xor     ebx, ebx
0x180025d92  mov     rcx, [rbp+Dacl]; Acl
0x180025d96  movzx   eax, word ptr [rcx+4]
0x180025d9a  cmp     ebx, eax
0x180025d9c  jnb     short loc_180025DE6
0x180025d9e  mov     [rbp+pAce], 0
0x180025da6  lea     r8, [rbp+pAce]; pAce
0x180025daa  mov     edx, ebx; dwAceIndex
0x180025dac  call    cs:__imp_GetAce
0x180025db2  test    eax, eax
0x180025db4  jz      short loc_180025DD9
0x180025db6  mov     rdi, [rbp+pAce]
0x180025dba  cmp     byte ptr [rdi], 0
0x180025dbd  jnz     short loc_180025DD9
0x180025dbf  lea     rcx, [rdi+8]; pSid1
0x180025dc3  mov     rdx, r15; pSid2
0x180025dc6  call    cs:__imp_EqualSid
0x180025dcc  test    eax, eax
0x180025dce  jz      short loc_180025DD9
0x180025dd0  mov     eax, [rdi+4]
0x180025dd3  and     eax, esi
0x180025dd5  cmp     eax, esi
0x180025dd7  jz      short loc_180025DDD
0x180025dd9  inc     ebx
0x180025ddb  jmp     short loc_180025D92
0x180025ddd  mov     byte ptr [r14], 1
0x180025de1  jmp     loc_180025FD3
0x180025de6  xor     eax, eax
0x180025de8  mov     [rbp+Information], rax
0x180025dec  mov     [rbp+var_18], eax
0x180025def  lea     r9d, [rax+2]; InformationClass
0x180025df3  lea     r8d, [rax+0Ch]; InformationLength
0x180025df7  lea     rdx, [rbp+Information]; Information
0x180025dfb  call    cs:__imp_RtlQueryInformationAcl
0x180025e01  test    eax, eax
0x180025e03  jns     short loc_180025E0F
0x180025e05  mov     edx, 3Dh ; '='
0x180025e0a  jmp     loc_180025D78
0x180025e0f  mov     [rbp+AclRevision], 0
0x180025e16  mov     r9d, 1; InformationClass
0x180025e1c  lea     r8d, [r9+3]; InformationLength
0x180025e20  lea     rdx, [rbp+AclRevision]; Information
0x180025e24  mov     rcx, [rbp+Dacl]; Acl
0x180025e28  call    cs:__imp_RtlQueryInformationAcl
0x180025e2e  test    eax, eax
0x180025e30  jns     short loc_180025E3C
0x180025e32  mov     edx, 40h ; '@'
0x180025e37  jmp     loc_180025D78
0x180025e3c  mov     rcx, r15; Sid
0x180025e3f  call    cs:__imp_RtlLengthSid
0x180025e45  mov     r14d, dword ptr [rbp+Information+4]
0x180025e49  add     r14d, 8
0x180025e4d  add     r14d, eax
0x180025e50  call    cs:__imp_GetProcessHeap
0x180025e56  mov     rcx, rax; hHeap
0x180025e59  mov     r8d, r14d; dwBytes
0x180025e5c  mov     edx, 8; dwFlags
0x180025e61  call    cs:__imp_HeapAlloc
0x180025e67  mov     rdi, rax
0x180025e6a  test    rax, rax
0x180025e6d  jnz     short loc_180025E92
0x180025e6f  mov     rcx, [rbp+38h]; this
0x180025e73  mov     ebx, 8007000Eh
0x180025e78  mov     r9d, ebx; char *
0x180025e7b  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025e82  lea     edx, [rax+47h]; void *
0x180025e85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025e8a  nop
0x180025e8b  mov     eax, ebx
0x180025e8d  jmp     loc_180025FD5
0x180025e92  mov     r8d, [rbp+AclRevision]; AclRevision
0x180025e96  mov     edx, r14d; AclSize
0x180025e99  mov     rcx, rdi; Acl
0x180025e9c  call    cs:__imp_RtlCreateAcl
0x180025ea2  test    eax, eax
0x180025ea4  jns     short loc_180025ECB
0x180025ea6  mov     rcx, [rbp+38h]; this
0x180025eaa  mov     r9d, eax; char *
0x180025ead  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025eb4  mov     edx, 49h ; 'I'; void *
0x180025eb9  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025ebe  mov     ebx, eax
0x180025ec0  mov     rcx, rdi; this
0x180025ec3  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025ec8  nop
0x180025ec9  jmp     short loc_180025E8B
0x180025ecb  mov     [rbp+Ace], 0
0x180025ed3  lea     r8, [rbp+Ace]; Ace
0x180025ed7  xor     edx, edx; AceIndex
0x180025ed9  mov     rcx, [rbp+Dacl]; Acl
0x180025edd  call    cs:__imp_RtlGetAce
0x180025ee3  test    eax, eax
0x180025ee5  jns     short loc_180025F0F
0x180025ee7  mov     rcx, [rbp+38h]; this
0x180025eeb  mov     r9d, eax; char *
0x180025eee  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025ef5  mov     edx, 4Ch ; 'L'; void *
0x180025efa  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025eff  mov     ebx, eax
0x180025f01  mov     rcx, rdi; this
0x180025f04  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025f09  nop
0x180025f0a  jmp     loc_180025E8B
0x180025f0f  mov     eax, dword ptr [rbp+Information+4]
0x180025f12  add     eax, 0FFFFFFF8h
0x180025f15  mov     [rsp+70h+AceListLength], eax; int
0x180025f19  mov     r9, [rbp+Ace]; AceList
0x180025f1d  xor     r8d, r8d; StartingAceIndex
0x180025f20  mov     edx, [rbp+AclRevision]; AceRevision
0x180025f23  mov     rcx, rdi; Acl
0x180025f26  call    cs:__imp_RtlAddAce
0x180025f2c  test    eax, eax
0x180025f2e  jns     short loc_180025F58
0x180025f30  mov     rcx, [rbp+38h]; this
0x180025f34  mov     r9d, eax; char *
0x180025f37  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025f3e  mov     edx, 4Eh ; 'N'; void *
0x180025f43  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025f48  mov     ebx, eax
0x180025f4a  mov     rcx, rdi; this
0x180025f4d  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025f52  nop
0x180025f53  jmp     loc_180025E8B
0x180025f58  mov     r9, r15; Sid
0x180025f5b  mov     r8d, esi; AccessMask
0x180025f5e  mov     edx, [rbp+AclRevision]; Revision
0x180025f61  mov     rcx, rdi; Acl
0x180025f64  call    cs:__imp_RtlAddAccessAllowedAce
0x180025f6a  test    eax, eax
0x180025f6c  jns     short loc_180025F96
0x180025f6e  mov     rcx, [rbp+38h]; this
0x180025f72  mov     r9d, eax; char *
0x180025f75  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025f7c  mov     edx, 51h ; 'Q'; void *
0x180025f81  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025f86  mov     ebx, eax
0x180025f88  mov     rcx, rdi; this
0x180025f8b  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025f90  nop
0x180025f91  jmp     loc_180025E8B
0x180025f96  xor     r9d, r9d; DaclDefaulted
0x180025f99  mov     r8, rdi; Dacl
0x180025f9c  mov     dl, 1; DaclPresent
0x180025f9e  mov     rcx, r12; SecurityDescriptor
0x180025fa1  call    cs:__imp_RtlSetDaclSecurityDescriptor
0x180025fa7  test    eax, eax
0x180025fa9  jns     short loc_180025FD3
0x180025fab  mov     rcx, [rbp+38h]; this
0x180025faf  mov     r9d, eax; char *
0x180025fb2  lea     r8, aOnecoreuapInte; "onecoreuap\\internal\\sdk\\inc\\UserMod"...
0x180025fb9  mov     edx, 53h ; 'S'; void *
0x180025fbe  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x180025fc3  mov     ebx, eax
0x180025fc5  mov     rcx, rdi; this
0x180025fc8  call    ?FreeProcessHeap@details@wil@@YAXPEAX@Z; wil::details::FreeProcessHeap(void *)
0x180025fcd  nop
0x180025fce  jmp     loc_180025E8B
0x180025fd3  xor     eax, eax
0x180025fd5  mov     rcx, [rbp+var_10]
0x180025fd9  xor     rcx, rsp; StackCookie
0x180025fdc  call    __security_check_cookie
0x180025fe1  add     rsp, 70h
0x180025fe5  pop     r15
0x180025fe7  pop     r14
0x180025fe9  pop     r12
0x180025feb  pop     rdi
0x180025fec  pop     rsi
0x180025fed  pop     rbx
0x180025fee  pop     rbp
0x180025fef  retn
```
