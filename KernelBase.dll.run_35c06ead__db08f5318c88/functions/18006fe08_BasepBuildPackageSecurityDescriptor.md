# BasepBuildPackageSecurityDescriptor

- ea: `0x18006fe08`
- end: `0x1800703b4`
- name: `BasepBuildPackageSecurityDescriptor`
- size: `1452`
- prototype: `__int64 __usercall@<rax>(PSECURITY_DESCRIPTOR SecurityDescriptor@<rcx>, PSID Sid@<rdx>, PSID Sid1@<r8>, PSECURITY_DESCRIPTOR)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18006ee28`

## callees

- `0x18006fe08`
- `0x18012d119`
- `0x180188f10`

## import_xrefs

- `ntdll!RtlSubAuthoritySid` at `0x180070186`
- `ntdll!RtlSubAuthoritySid` at `0x180070186`
- `ntdll!RtlEqualSid` at `0x18006ff60`
- `ntdll!RtlEqualSid` at `0x18006ff60`
- `ntdll!RtlGetAce` at `0x18006ff4b`
- `ntdll!RtlGetAce` at `0x18006ffe8`
- `ntdll!RtlGetAce` at `0x18007002f`
- `ntdll!RtlGetAce` at `0x18006ff4b`
- `ntdll!RtlGetAce` at `0x18006ffe8`
- `ntdll!RtlGetAce` at `0x18007002f`
- `ntdll!RtlQueryInformationAcl` at `0x18006fed3`
- `ntdll!RtlQueryInformationAcl` at `0x18006fef2`
- `ntdll!RtlQueryInformationAcl` at `0x18006fed3`
- `ntdll!RtlQueryInformationAcl` at `0x18006fef2`
- `ntdll!RtlSubAuthorityCountSid` at `0x180070172`
- `ntdll!RtlSubAuthorityCountSid` at `0x180070172`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18006feb5`
- `ntdll!RtlGetDaclSecurityDescriptor` at `0x18006feb5`
- `ntdll!RtlCreateAcl` at `0x18006ffce`
- `ntdll!RtlCreateAcl` at `0x18006ffce`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800700bd`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800700ec`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180070118`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180070142`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180070396`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800700bd`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x1800700ec`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180070118`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180070142`
- `ntdll!RtlAddAccessAllowedAceEx` at `0x180070396`
- `ntdll!RtlAddAce` at `0x18007000f`
- `ntdll!RtlAddAce` at `0x18007000f`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006fe98`
- `ntdll!RtlCreateSecurityDescriptor` at `0x18006fe98`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800702c9`
- `ntdll!RtlSetDaclSecurityDescriptor` at `0x1800702c9`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800701e7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180070240`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180070296`
- `ntdll!RtlAllocateAndInitializeSid` at `0x1800701e7`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180070240`
- `ntdll!RtlAllocateAndInitializeSid` at `0x180070296`
- `ntdll!RtlLengthSid` at `0x18006ff05`
- `ntdll!RtlLengthSid` at `0x18006ff79`
- `ntdll!RtlLengthSid` at `0x1800701fd`
- `ntdll!RtlLengthSid` at `0x180070256`
- `ntdll!RtlLengthSid` at `0x1800702a9`
- `ntdll!RtlLengthSid` at `0x18006ff05`
- `ntdll!RtlLengthSid` at `0x18006ff79`
- `ntdll!RtlLengthSid` at `0x1800701fd`
- `ntdll!RtlLengthSid` at `0x180070256`
- `ntdll!RtlLengthSid` at `0x1800702a9`
- `ntdll!RtlFreeHeap` at `0x180070164`
- `ntdll!RtlFreeHeap` at `0x1800702f2`
- `ntdll!RtlFreeHeap` at `0x180070311`
- `ntdll!RtlFreeHeap` at `0x180070330`
- `ntdll!RtlFreeHeap` at `0x180070164`
- `ntdll!RtlFreeHeap` at `0x1800702f2`
- `ntdll!RtlFreeHeap` at `0x180070311`
- `ntdll!RtlFreeHeap` at `0x180070330`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180070051`
- `ntdll!RtlIdentifierAuthoritySid` at `0x180070051`
- `ntdll!RtlAddAccessAllowedAce` at `0x180070099`
- `ntdll!RtlAddAccessAllowedAce` at `0x180070372`
- `ntdll!RtlAddAccessAllowedAce` at `0x180070099`
- `ntdll!RtlAddAccessAllowedAce` at `0x180070372`
- `ntdll!RtlAllocateHeap` at `0x18006ffa4`
- `ntdll!RtlAllocateHeap` at `0x18006ffa4`

## pseudocode

```c
NTSTATUS __fastcall BasepBuildPackageSecurityDescriptor(
        PSECURITY_DESCRIPTOR SecurityDescriptor,
        PSID Sid,
        PSID Sid1,
        char a4,
        PSECURITY_DESCRIPTOR SecurityDescriptora)
{
  ULONG v5; // esi
  NTSTATUS result; // eax
  NTSTATUS Acl; // ebx
  ULONG v12; // eax
  int v13; // r12d
  int v14; // edi
  int v15; // r13d
  int v16; // r15d
  ULONG i; // ebx
  char v18; // r14
  ULONG v19; // ebx
  ACL *Heap; // rax
  ACL *v21; // rdi
  ULONG j; // ebx
  char *v23; // rsi
  PSID_IDENTIFIER_AUTHORITY v24; // rax
  int v25; // ecx
  PSID v26; // rsi
  PSID v27; // rsi
  ULONG AclRevision; // [rsp+60h] [rbp-71h] BYREF
  unsigned __int8 DaclDefaulted; // [rsp+64h] [rbp-6Dh] BYREF
  unsigned __int8 DaclPresent[3]; // [rsp+65h] [rbp-6Ch] BYREF
  int v31; // [rsp+68h] [rbp-69h]
  unsigned __int16 v32; // [rsp+6Ch] [rbp-65h]
  PACL Dacl; // [rsp+70h] [rbp-61h] BYREF
  PVOID Ace; // [rsp+78h] [rbp-59h] BYREF
  PSID P; // [rsp+80h] [rbp-51h] BYREF
  PSID v36; // [rsp+88h] [rbp-49h] BYREF
  PSID v37; // [rsp+90h] [rbp-41h] BYREF
  int v38; // [rsp+98h] [rbp-39h]
  PVOID AceList; // [rsp+A0h] [rbp-31h] BYREF
  PSID Sida; // [rsp+A8h] [rbp-29h]
  PSID pSid; // [rsp+B0h] [rbp-21h]
  PSECURITY_DESCRIPTOR v42; // [rsp+B8h] [rbp-19h]
  struct _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+C0h] [rbp-11h] BYREF
  struct _SID_IDENTIFIER_AUTHORITY v44; // [rsp+C8h] [rbp-9h] BYREF
  __int64 Information; // [rsp+D0h] [rbp-1h] BYREF
  int v46; // [rsp+D8h] [rbp+7h]

  v5 = 0;
  pSid = Sid;
  Sida = Sid1;
  Information = 0;
  v46 = 0;
  v42 = SecurityDescriptora;
  AceList = 0;
  AclRevision = 0;
  Ace = 0;
  Dacl = 0;
  DaclDefaulted = 0;
  DaclPresent[0] = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 1280;
  *(_DWORD *)v44.Value = 0;
  *(_WORD *)&v44.Value[4] = 256;
  P = 0;
  v37 = 0;
  v36 = 0;
  result = RtlCreateSecurityDescriptor(SecurityDescriptora, 1u);
  if ( result < 0 )
    return result;
  result = RtlGetDaclSecurityDescriptor(SecurityDescriptor, DaclPresent, &Dacl, &DaclDefaulted);
  if ( result < 0 )
    return result;
  Acl = RtlQueryInformationAcl(Dacl, &Information, 0xCu, AclSizeInformation);
  if ( Acl >= 0 )
  {
    Acl = RtlQueryInformationAcl(Dacl, &AclRevision, 4u, AclRevisionInformation);
    if ( Acl >= 0 )
    {
      v12 = RtlLengthSid(Sid);
      v13 = HIDWORD(Information) + 2 * v12;
      v38 = a4 & 1;
      if ( (a4 & 1) != 0 )
      {
        Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &P);
        if ( Acl < 0 )
          goto LABEL_49;
        v14 = 1;
        v5 = RtlLengthSid(P);
      }
      else
      {
        v14 = 0;
      }
      v15 = a4 & 4;
      if ( (a4 & 4) != 0 )
      {
        Acl = RtlAllocateAndInitializeSid(&v44, 1u, 0, 0, 0, 0, 0, 0, 0, 0, &v36);
        if ( Acl < 0 )
          goto LABEL_49;
        ++v14;
        v5 += RtlLengthSid(v36);
      }
      v16 = a4 & 2;
      if ( !v16 )
        goto LABEL_9;
      Acl = RtlAllocateAndInitializeSid(&IdentifierAuthority, 1u, 0xCu, 0, 0, 0, 0, 0, 0, 0, &v37);
      if ( Acl >= 0 )
      {
        ++v14;
        v5 += RtlLengthSid(v37);
LABEL_9:
        for ( i = 0; ; ++i )
        {
          if ( i >= (unsigned int)Information || RtlGetAce(Dacl, i, &Ace) < 0 )
          {
            v18 = 0;
            v14 += 2;
            v5 += 2 * RtlLengthSid(Sida);
            goto LABEL_15;
          }
          if ( RtlEqualSid(Sid1, (char *)Ace + 8) )
            break;
        }
        v18 = 1;
LABEL_15:
        v19 = (v5 + v13 + 19 + 8 * v14) & 0xFFFFFFFC;
        Heap = (ACL *)RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 0, v19);
        v21 = Heap;
        if ( !Heap )
          return -1073741801;
        memset_0(Heap, 0, v19);
        Acl = RtlCreateAcl(v21, v19, AclRevision);
        if ( Acl < 0 )
          goto LABEL_34;
        Acl = RtlGetAce(Dacl, 0, &AceList);
        if ( Acl < 0 )
          goto LABEL_34;
        Acl = RtlAddAce(v21, AclRevision, 0, AceList, HIDWORD(Information) - 8);
        if ( Acl < 0 )
          goto LABEL_34;
        for ( j = 0; j < (unsigned int)Information; ++j )
        {
          if ( RtlGetAce(v21, j, &Ace) < 0 )
            break;
          v23 = (char *)Ace + 8;
          v31 = 0;
          v32 = 1280;
          v24 = RtlIdentifierAuthoritySid((char *)Ace + 8);
          v25 = -*(_DWORD *)v24->Value;
          if ( !*(_DWORD *)v24->Value )
            v25 = v32 - *(unsigned __int16 *)&v24->Value[4];
          if ( !v25
            && *RtlSubAuthorityCountSid(v23) == 3
            && *RtlSubAuthoritySid(v23, 0) == 5
            && (*((_BYTE *)Ace + 1) & 8) == 0 )
          {
            *((_DWORD *)Ace + 1) = 983055;
          }
        }
        if ( !v18 )
        {
          v27 = Sida;
          Acl = RtlAddAccessAllowedAce(v21, AclRevision, 0xF000Fu, Sida);
          if ( Acl < 0 )
            goto LABEL_34;
          Acl = RtlAddAccessAllowedAceEx(v21, AclRevision, 0xBu, 0x10000000u, v27);
          if ( Acl < 0 )
            goto LABEL_34;
        }
        if ( (v26 = pSid, Acl = RtlAddAccessAllowedAce(v21, AclRevision, 0xF000Fu, pSid), Acl < 0)
          || (Acl = RtlAddAccessAllowedAceEx(v21, AclRevision, 0xBu, 0x10000000u, v26), Acl < 0)
          || v38 && (Acl = RtlAddAccessAllowedAceEx(v21, AclRevision, 0xBu, 0x10000000u, P), Acl < 0)
          || v15 && (Acl = RtlAddAccessAllowedAceEx(v21, AclRevision, 0xBu, 0xA0000000, v36), Acl < 0)
          || v16 && (Acl = RtlAddAccessAllowedAceEx(v21, AclRevision, 0xBu, 0xA0000000, v37), Acl < 0)
          || (Acl = RtlSetDaclSecurityDescriptor(v42, 1u, v21, 0), Acl < 0) )
        {
LABEL_34:
          RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v21);
        }
      }
    }
  }
LABEL_49:
  if ( P )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, P);
  if ( v36 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v36);
  if ( v37 )
    RtlFreeHeap(NtCurrentPeb()->ProcessHeap, 0, v37);
  return Acl;
}

```

## disassembly

```asm
0x18006fe08  mov     [rsp-8+arg_18], rbx
0x18006fe0d  push    rbp
0x18006fe0e  push    rsi
0x18006fe0f  push    rdi
0x18006fe10  push    r12
0x18006fe12  push    r13
0x18006fe14  push    r14
0x18006fe16  push    r15
0x18006fe18  lea     rbp, [rsp-1Fh]
0x18006fe1d  sub     rsp, 0F0h
0x18006fe24  mov     rax, cs:__security_cookie
0x18006fe2b  xor     rax, rsp
0x18006fe2e  mov     [rbp+4Fh+var_40], rax
0x18006fe32  mov     rax, [rbp+4Fh+SecurityDescriptor]
0x18006fe36  xor     esi, esi
0x18006fe38  mov     rbx, rcx
0x18006fe3b  mov     [rbp+4Fh+pSid], rdx
0x18006fe3f  xor     ecx, ecx
0x18006fe41  mov     [rbp+4Fh+Sid], r8
0x18006fe45  mov     rdi, rdx
0x18006fe48  mov     [rbp+4Fh+Information], rcx
0x18006fe4c  mov     [rbp+4Fh+var_48], ecx
0x18006fe4f  lea     r13d, [rsi+1]
0x18006fe53  mov     edx, r13d; Revision
0x18006fe56  mov     [rbp+4Fh+var_68], rax
0x18006fe5a  mov     rcx, rax; SecurityDescriptor
0x18006fe5d  mov     [rbp+4Fh+AceList], rsi
0x18006fe61  mov     r15d, r9d
0x18006fe64  mov     [rbp+4Fh+AclRevision], esi
0x18006fe67  mov     r14, r8
0x18006fe6a  mov     [rbp+4Fh+Ace], rsi
0x18006fe6e  mov     [rbp+4Fh+Dacl], rsi
0x18006fe72  mov     [rbp+4Fh+DaclDefaulted], sil
0x18006fe76  mov     [rbp+4Fh+DaclPresent], sil
0x18006fe7a  mov     dword ptr [rbp+4Fh+IdentifierAuthority.Value], esi
0x18006fe7d  mov     word ptr [rbp+4Fh+IdentifierAuthority.Value+4], 500h
0x18006fe83  mov     dword ptr [rbp+4Fh+var_58.Value], esi
0x18006fe86  mov     word ptr [rbp+4Fh+var_58.Value+4], 100h
0x18006fe8c  mov     [rbp+4Fh+P], rsi
0x18006fe90  mov     [rbp+4Fh+var_90], rsi
0x18006fe94  mov     [rbp+4Fh+var_98], rsi
0x18006fe98  call    cs:__imp_RtlCreateSecurityDescriptor
0x18006fe9e  test    eax, eax
0x18006fea0  js      loc_180070338
0x18006fea6  lea     r9, [rbp+4Fh+DaclDefaulted]; DaclDefaulted
0x18006feaa  mov     rcx, rbx; SecurityDescriptor
0x18006fead  lea     r8, [rbp+4Fh+Dacl]; Dacl
0x18006feb1  lea     rdx, [rbp+4Fh+DaclPresent]; DaclPresent
0x18006feb5  call    cs:__imp_RtlGetDaclSecurityDescriptor
0x18006febb  test    eax, eax
0x18006febd  js      loc_180070338
0x18006fec3  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x18006fec7  lea     r9d, [rsi+2]; InformationClass
0x18006fecb  lea     r8d, [rsi+0Ch]; InformationLength
0x18006fecf  lea     rdx, [rbp+4Fh+Information]; Information
0x18006fed3  call    cs:__imp_RtlQueryInformationAcl
0x18006fed9  mov     ebx, eax
0x18006fedb  test    eax, eax
0x18006fedd  js      loc_1800702D9
0x18006fee3  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x18006fee7  lea     r8d, [rsi+4]; InformationLength
0x18006feeb  mov     r9d, r13d; InformationClass
0x18006feee  lea     rdx, [rbp+4Fh+AclRevision]; Information
0x18006fef2  call    cs:__imp_RtlQueryInformationAcl
0x18006fef8  mov     ebx, eax
0x18006fefa  test    eax, eax
0x18006fefc  js      loc_1800702D9
0x18006ff02  mov     rcx, rdi; Sid
0x18006ff05  call    cs:__imp_RtlLengthSid
0x18006ff0b  mov     ecx, dword ptr [rbp+4Fh+Information+4]
0x18006ff0e  lea     r12d, [rcx+rax*2]
0x18006ff12  mov     eax, r15d
0x18006ff15  and     eax, r13d
0x18006ff18  mov     [rbp+4Fh+var_88], eax
0x18006ff1b  jnz     loc_180070263
0x18006ff21  mov     edi, esi
0x18006ff23  mov     r13d, r15d
0x18006ff26  and     r13d, 4
0x18006ff2a  jnz     loc_180070211
0x18006ff30  and     r15d, 2
0x18006ff34  jnz     loc_1800701B7
0x18006ff3a  xor     ebx, ebx
0x18006ff3c  cmp     ebx, dword ptr [rbp+4Fh+Information]
0x18006ff3f  jnb     short loc_18006FF72
0x18006ff41  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x18006ff45  lea     r8, [rbp+4Fh+Ace]; Ace
0x18006ff49  mov     edx, ebx; AceIndex
0x18006ff4b  call    cs:__imp_RtlGetAce
0x18006ff51  test    eax, eax
0x18006ff53  js      short loc_18006FF72
0x18006ff55  mov     rdx, [rbp+4Fh+Ace]
0x18006ff59  mov     rcx, r14; Sid1
0x18006ff5c  add     rdx, 8; Sid2
0x18006ff60  call    cs:__imp_RtlEqualSid
0x18006ff66  test    al, al
0x18006ff68  jnz     loc_1800701AF
0x18006ff6e  inc     ebx
0x18006ff70  jmp     short loc_18006FF3C
0x18006ff72  mov     rcx, [rbp+4Fh+Sid]; Sid
0x18006ff76  xor     r14b, r14b
0x18006ff79  call    cs:__imp_RtlLengthSid
0x18006ff7f  add     edi, 2
0x18006ff82  lea     esi, [rsi+rax*2]
0x18006ff85  mov     rcx, gs:60h
0x18006ff8e  lea     ebx, [r12+13h]
0x18006ff93  lea     ebx, [rbx+rdi*8]
0x18006ff96  xor     edx, edx; Flags
0x18006ff98  add     ebx, esi
0x18006ff9a  and     ebx, 0FFFFFFFCh
0x18006ff9d  mov     rcx, [rcx+30h]; HeapHandle
0x18006ffa1  mov     r8d, ebx; Size
0x18006ffa4  call    cs:__imp_RtlAllocateHeap
0x18006ffaa  xor     esi, esi
0x18006ffac  mov     rdi, rax
0x18006ffaf  test    rax, rax
0x18006ffb2  jz      loc_1800702B6
0x18006ffb8  mov     r8d, ebx; Size
0x18006ffbb  xor     edx, edx; Val
0x18006ffbd  mov     rcx, rax; void *
0x18006ffc0  call    memset_0
0x18006ffc5  mov     r8d, [rbp+4Fh+AclRevision]; AclRevision
0x18006ffc9  mov     edx, ebx; AclSize
0x18006ffcb  mov     rcx, rdi; Acl
0x18006ffce  call    cs:__imp_RtlCreateAcl
0x18006ffd4  mov     ebx, eax
0x18006ffd6  test    eax, eax
0x18006ffd8  js      loc_180070152
0x18006ffde  mov     rcx, [rbp+4Fh+Dacl]; Acl
0x18006ffe2  lea     r8, [rbp+4Fh+AceList]; Ace
0x18006ffe6  xor     edx, edx; AceIndex
0x18006ffe8  call    cs:__imp_RtlGetAce
0x18006ffee  mov     ebx, eax
0x18006fff0  test    eax, eax
0x18006fff2  js      loc_180070152
0x18006fff8  mov     eax, dword ptr [rbp+4Fh+Information+4]
0x18006fffb  xor     r8d, r8d; StartingAceIndex
0x18006fffe  mov     r9, [rbp+4Fh+AceList]; AceList
0x180070002  add     eax, 0FFFFFFF8h
0x180070005  mov     edx, [rbp+4Fh+AclRevision]; AceRevision
0x180070008  mov     rcx, rdi; Acl
0x18007000b  mov     [rsp+120h+AceListLength], eax; AceListLength
0x18007000f  call    cs:__imp_RtlAddAce
0x180070015  mov     ebx, eax
0x180070017  test    eax, eax
0x180070019  js      loc_180070152
0x18007001f  mov     ebx, esi
0x180070021  cmp     dword ptr [rbp+4Fh+Information], esi
0x180070024  jbe     short loc_180070077
0x180070026  lea     r8, [rbp+4Fh+Ace]; Ace
0x18007002a  mov     edx, ebx; AceIndex
0x18007002c  mov     rcx, rdi; Acl
0x18007002f  call    cs:__imp_RtlGetAce
0x180070035  test    eax, eax
0x180070037  js      short loc_180070077
0x180070039  mov     rsi, [rbp+4Fh+Ace]
0x18007003d  xor     r12d, r12d
0x180070040  add     rsi, 8
0x180070044  mov     [rbp+4Fh+var_B8], r12d
0x180070048  mov     rcx, rsi; Sid
0x18007004b  mov     [rbp+4Fh+var_B4], 500h
0x180070051  call    cs:__imp_RtlIdentifierAuthoritySid
0x180070057  mov     ecx, r12d
0x18007005a  sub     ecx, [rax]
0x18007005c  jnz     short loc_180070068
0x18007005e  movzx   ecx, [rbp+4Fh+var_B4]
0x180070062  movzx   eax, word ptr [rax+4]
0x180070066  sub     ecx, eax
0x180070068  test    ecx, ecx
0x18007006a  jz      loc_18007016F
0x180070070  inc     ebx
0x180070072  cmp     ebx, dword ptr [rbp+4Fh+Information]
0x180070075  jb      short loc_180070026
0x180070077  mov     r12d, 0Bh
0x18007007d  test    r14b, r14b
0x180070080  jz      loc_18007035F
0x180070086  mov     rsi, [rbp+4Fh+pSid]
0x18007008a  mov     r8d, 0F000Fh; AccessMask
0x180070090  mov     edx, [rbp+4Fh+AclRevision]; Revision
0x180070093  mov     r9, rsi; Sid
0x180070096  mov     rcx, rdi; Acl
0x180070099  call    cs:__imp_RtlAddAccessAllowedAce
0x18007009f  mov     ebx, eax
0x1800700a1  test    eax, eax
0x1800700a3  js      loc_18007020A
0x1800700a9  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x1800700ac  mov     r9d, 10000000h; AccessMask
0x1800700b2  mov     r8d, r12d; AceFlags
0x1800700b5  mov     qword ptr [rsp+120h+AceListLength], rsi; pSid
0x1800700ba  mov     rcx, rdi; pAcl
0x1800700bd  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1800700c3  xor     esi, esi
0x1800700c5  mov     ebx, eax
0x1800700c7  test    eax, eax
0x1800700c9  js      loc_180070152
0x1800700cf  cmp     [rbp+4Fh+var_88], esi
0x1800700d2  jz      short loc_1800700F8
0x1800700d4  mov     rax, [rbp+4Fh+P]
0x1800700d8  mov     r9d, 10000000h; AccessMask
0x1800700de  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x1800700e1  mov     r8d, r12d; AceFlags
0x1800700e4  mov     rcx, rdi; pAcl
0x1800700e7  mov     qword ptr [rsp+120h+AceListLength], rax; pSid
0x1800700ec  call    cs:__imp_RtlAddAccessAllowedAceEx
0x1800700f2  mov     ebx, eax
0x1800700f4  test    eax, eax
0x1800700f6  js      short loc_180070152
0x1800700f8  mov     r14d, 0A0000000h
0x1800700fe  test    r13d, r13d
0x180070101  jz      short loc_180070124
0x180070103  mov     rax, [rbp+4Fh+var_98]
0x180070107  mov     r9d, r14d; AccessMask
0x18007010a  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x18007010d  mov     r8d, r12d; AceFlags
0x180070110  mov     rcx, rdi; pAcl
0x180070113  mov     qword ptr [rsp+120h+AceListLength], rax; pSid
0x180070118  call    cs:__imp_RtlAddAccessAllowedAceEx
0x18007011e  mov     ebx, eax
0x180070120  test    eax, eax
0x180070122  js      short loc_180070152
0x180070124  test    r15d, r15d
0x180070127  jz      loc_1800702BD
0x18007012d  mov     rax, [rbp+4Fh+var_90]
0x180070131  mov     r9d, r14d; AccessMask
0x180070134  mov     edx, [rbp+4Fh+AclRevision]; dwAceRevision
0x180070137  mov     r8d, r12d; AceFlags
0x18007013a  mov     rcx, rdi; pAcl
0x18007013d  mov     qword ptr [rsp+120h+AceListLength], rax; pSid
0x180070142  call    cs:__imp_RtlAddAccessAllowedAceEx
0x180070148  mov     ebx, eax
0x18007014a  test    eax, eax
0x18007014c  jns     loc_1800702BD
0x180070152  mov     rcx, gs:60h
0x18007015b  mov     r8, rdi; P
0x18007015e  xor     edx, edx; Flags
0x180070160  mov     rcx, [rcx+30h]; HeapHandle
0x180070164  call    cs:__imp_RtlFreeHeap
0x18007016a  jmp     loc_1800702D9
0x18007016f  mov     rcx, rsi; Sid
0x180070172  call    cs:__imp_RtlSubAuthorityCountSid
0x180070178  cmp     byte ptr [rax], 3
0x18007017b  jnz     loc_180070070
0x180070181  xor     edx, edx; SubAuthority
0x180070183  mov     rcx, rsi; Sid
0x180070186  call    cs:__imp_RtlSubAuthoritySid
0x18007018c  cmp     dword ptr [rax], 5
0x18007018f  jnz     loc_180070070
0x180070195  mov     rax, [rbp+4Fh+Ace]
0x180070199  test    byte ptr [rax+1], 8
0x18007019d  jnz     loc_180070070
0x1800701a3  mov     dword ptr [rax+4], 0F000Fh
0x1800701aa  jmp     loc_180070070
0x1800701af  mov     r14b, 1
0x1800701b2  jmp     loc_18006FF85
0x1800701b7  lea     rax, [rbp+4Fh+var_90]
0x1800701bb  xor     r9d, r9d; SubAuthority1
0x1800701be  mov     [rsp+120h+var_D0], rax; Sid
0x1800701c3  lea     rcx, [rbp+4Fh+IdentifierAuthority]; IdentifierAuthority
0x1800701c7  xor     eax, eax
0x1800701c9  mov     dl, 1; SubAuthorityCount
0x1800701cb  mov     [rsp+120h+SubAuthority7], eax; SubAuthority7
0x1800701cf  mov     [rsp+120h+SubAuthority6], eax; SubAuthority6
0x1800701d3  mov     [rsp+120h+SubAuthority5], eax; SubAuthority5
0x1800701d7  mov     [rsp+120h+SubAuthority4], eax; SubAuthority4
0x1800701db  lea     r8d, [rax+0Ch]; SubAuthority0
0x1800701df  mov     [rsp+120h+SubAuthority3], eax; SubAuthority3
0x1800701e3  mov     [rsp+120h+AceListLength], eax; SubAuthority2
0x1800701e7  call    cs:__imp_RtlAllocateAndInitializeSid
0x1800701ed  mov     ebx, eax
0x1800701ef  test    eax, eax
0x1800701f1  js      loc_1800703AD
0x1800701f7  mov     rcx, [rbp+4Fh+var_90]; Sid
0x1800701fb  inc     edi
0x1800701fd  call    cs:__imp_RtlLengthSid
0x180070203  add     esi, eax
0x180070205  jmp     loc_18006FF3A
0x18007020a  xor     esi, esi
0x18007020c  jmp     loc_180070152
0x180070211  lea     rax, [rbp+4Fh+var_98]
0x180070215  xor     r9d, r9d; SubAuthority1
0x180070218  mov     [rsp+120h+var_D0], rax; Sid
0x18007021d  lea     rcx, [rbp+4Fh+var_58]; IdentifierAuthority
0x180070221  xor     eax, eax
0x180070223  xor     r8d, r8d; SubAuthority0
0x180070226  mov     [rsp+120h+SubAuthority7], eax; SubAuthority7
0x18007022a  mov     dl, 1; SubAuthorityCount
0x18007022c  mov     [rsp+120h+SubAuthority6], eax; SubAuthority6
0x180070230  mov     [rsp+120h+SubAuthority5], eax; SubAuthority5
0x180070234  mov     [rsp+120h+SubAuthority4], eax; SubAuthority4
0x180070238  mov     [rsp+120h+SubAuthority3], eax; SubAuthority3
0x18007023c  mov     [rsp+120h+AceListLength], eax; SubAuthority2
0x180070240  call    cs:__imp_RtlAllocateAndInitializeSid
0x180070246  mov     ebx, eax
0x180070248  test    eax, eax
0x18007024a  js      loc_1800703AD
0x180070250  mov     rcx, [rbp+4Fh+var_98]; Sid
0x180070254  inc     edi
0x180070256  call    cs:__imp_RtlLengthSid
0x18007025c  add     esi, eax
0x18007025e  jmp     loc_18006FF30
0x180070263  lea     rax, [rbp+4Fh+P]
  ... truncated ...
```
