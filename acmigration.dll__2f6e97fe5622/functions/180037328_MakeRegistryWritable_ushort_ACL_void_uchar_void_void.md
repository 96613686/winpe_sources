# MakeRegistryWritable(ushort *,_ACL * *,void * *,uchar *,void * *,void * *)

- ea: `0x180037328`
- end: `0x180037550`
- name: `?MakeRegistryWritable@@YAKPEAGPEAPEAU_ACL@@PEAPEAXPEAE22@Z`
- size: `552`
- prototype: `unsigned int __usercall@<eax>(LPWSTR pObjectName@<rcx>, PACL *ppDacl@<rdx>, PSID *ppsidOwner@<r8>, unsigned __int8 *@<r9>, PSECURITY_DESCRIPTOR *ppSecurityDescriptor, void **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180036ee0`

## callees

- `0x180001cf0`
- `0x180037298`
- `0x180037328`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800373f3`
- `KERNEL32!GetLastError` at `0x1800373f3`
- `ntdll!RtlNtStatusToDosError` at `0x180037399`
- `ntdll!RtlNtStatusToDosError` at `0x180037399`
- `ntdll!RtlAdjustPrivilege` at `0x18003738d`
- `ntdll!RtlAdjustPrivilege` at `0x18003738d`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800373e9`
- `ADVAPI32!AllocateAndInitializeSid` at `0x1800373e9`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1800374ad`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180037514`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1800374ad`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x180037514`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18003747a`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800374e1`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x18003747a`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800374e1`
- `ADVAPI32!SetEntriesInAclW` at `0x180037439`
- `ADVAPI32!SetEntriesInAclW` at `0x180037439`

## string_xrefs

- `0x1800373a1`: `RtlAdjustPrivilege Err`
- `0x1800373fb`: `AllocateAndInitializeSid Err`
- `0x180037445`: `SetEntriesInAcl Err`
- `0x180037486`: `GetNamedSecurityInfo OWNER_SECURITY_INFORMATION | DACL_SECURITY_INFORMATIONErr`
- `0x1800374b9`: `SetNamedSecurityInfo OWNER_SECURITY_INFORMATION`
- `0x1800374ed`: `GetNamedSecurityInfo DACL_SECURITY_INFORMATION Err %x\n`
- `0x180037520`: `SetNamedSecurityInfo DACL_SECURITY_INFORMATION Err %x\n`

## pseudocode

```c
__int64 __fastcall MakeRegistryWritable(
        LPWSTR pObjectName,
        PACL *ppDacl,
        PSID *ppsidOwner,
        unsigned __int8 *a4,
        PSECURITY_DESCRIPTOR *ppSecurityDescriptor,
        void **a6)
{
  NTSTATUS v9; // eax
  ULONG LastError; // eax
  ULONG v11; // ebx
  char *v12; // rcx
  PSID psidOwner; // [rsp+60h] [rbp-49h] BYREF
  PACL NewAcl; // [rsp+68h] [rbp-41h] BYREF
  _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+70h] [rbp-39h] BYREF
  _SID_IDENTIFIER_AUTHORITY pIdentifierAuthority; // [rsp+A0h] [rbp-9h] BYREF

  psidOwner = 0;
  *(_DWORD *)pIdentifierAuthority.Value = 0;
  *(_WORD *)&pIdentifierAuthority.Value[4] = 1280;
  NewAcl = 0;
  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  v9 = RtlAdjustPrivilege(9u, 1u, 0, a4);
  if ( v9 )
  {
    LastError = RtlNtStatusToDosError(v9);
    v11 = LastError;
    v12 = "RtlAdjustPrivilege Err";
LABEL_15:
    LogMsg(v12, LastError);
    return v11;
  }
  if ( !AllocateAndInitializeSid(&pIdentifierAuthority, 2u, 0x20u, 0x220u, 0, 0, 0, 0, 0, 0, &psidOwner) )
  {
    LastError = GetLastError();
    v11 = LastError;
    v12 = "AllocateAndInitializeSid Err";
    goto LABEL_15;
  }
  *(_QWORD *)&pListOfExplicitEntries.Trustee.TrusteeType = 2;
  pListOfExplicitEntries.Trustee.ptstrName = (LPWCH)psidOwner;
  pListOfExplicitEntries.grfAccessPermissions = 0x10000000;
  memset(&pListOfExplicitEntries.grfInheritance + 1, 0, 20);
  *(_QWORD *)&pListOfExplicitEntries.grfAccessMode = 2;
  LastError = SetEntriesInAclW(1u, &pListOfExplicitEntries, 0, &NewAcl);
  v11 = LastError;
  if ( LastError )
  {
    v12 = "SetEntriesInAcl Err";
    goto LABEL_15;
  }
  LastError = GetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 1u, ppsidOwner, 0, 0, 0, ppSecurityDescriptor);
  v11 = LastError;
  if ( LastError )
  {
    v12 = "GetNamedSecurityInfo OWNER_SECURITY_INFORMATION | DACL_SECURITY_INFORMATIONErr";
    goto LABEL_15;
  }
  LastError = SetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 1u, psidOwner, 0, 0, 0);
  v11 = LastError;
  if ( LastError )
  {
    v12 = "SetNamedSecurityInfo OWNER_SECURITY_INFORMATION";
    goto LABEL_15;
  }
  LastError = GetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 4u, 0, 0, ppDacl, 0, a6);
  v11 = LastError;
  if ( LastError )
  {
    v12 = "GetNamedSecurityInfo DACL_SECURITY_INFORMATION Err %x\n";
    goto LABEL_15;
  }
  LastError = SetNamedSecurityInfoW(pObjectName, SE_REGISTRY_KEY, 4u, 0, 0, NewAcl, 0);
  v11 = LastError;
  if ( LastError )
  {
    v12 = "SetNamedSecurityInfo DACL_SECURITY_INFORMATION Err %x\n";
    goto LABEL_15;
  }
  return v11;
}

```

## disassembly

```asm
0x180037328  push    rbp
0x18003732a  push    rbx
0x18003732b  push    rsi
0x18003732c  push    rdi
0x18003732d  push    r12
0x18003732f  push    r13
0x180037331  push    r14
0x180037333  push    r15
0x180037335  lea     rbp, [rsp-0Fh]
0x18003733a  sub     rsp, 0B8h
0x180037341  mov     rax, cs:__security_cookie
0x180037348  xor     rax, rsp
0x18003734b  mov     [rbp+47h+var_48], rax
0x18003734f  mov     r14, [rbp+47h+ppSecurityDescriptor]
0x180037353  xor     r13d, r13d
0x180037356  mov     r12, [rbp+47h+arg_28]
0x18003735a  xorps   xmm0, xmm0
0x18003735d  mov     rsi, r8
0x180037360  mov     [rbp+47h+psidOwner], r13
0x180037364  mov     r15, rdx
0x180037367  mov     dword ptr [rbp+47h+pIdentifierAuthority.Value], r13d
0x18003736b  mov     rdi, rcx
0x18003736e  mov     word ptr [rbp+47h+pIdentifierAuthority.Value+4], 500h
0x180037374  lea     ecx, [r13+9]; Privilege
0x180037378  mov     [rbp+47h+NewAcl], r13
0x18003737c  xor     r8d, r8d; ForThread
0x18003737f  mov     dl, 1; NewValue
0x180037381  movups  xmmword ptr [rbp+47h+pListOfExplicitEntries.grfAccessPermissions], xmm0
0x180037385  movups  xmmword ptr [rbp+47h+pListOfExplicitEntries.Trustee.pMultipleTrustee], xmm0
0x180037389  movups  xmmword ptr [rbp+47h+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x18003738d  call    cs:__imp_RtlAdjustPrivilege
0x180037393  test    eax, eax
0x180037395  jz      short loc_1800373AD
0x180037397  mov     ecx, eax; Status
0x180037399  call    cs:__imp_RtlNtStatusToDosError
0x18003739f  mov     ebx, eax
0x1800373a1  lea     rcx, aRtladjustprivi_1; "RtlAdjustPrivilege Err"
0x1800373a8  jmp     loc_180037527
0x1800373ad  lea     rax, [rbp+47h+psidOwner]
0x1800373b1  mov     ebx, 2
0x1800373b6  mov     [rsp+0F0h+pSid], rax; pSid
0x1800373bb  lea     rcx, [rbp+47h+pIdentifierAuthority]; pIdentifierAuthority
0x1800373bf  mov     [rsp+0F0h+nSubAuthority7], r13d; nSubAuthority7
0x1800373c4  mov     r9d, 220h; nSubAuthority1
0x1800373ca  mov     [rsp+0F0h+nSubAuthority6], r13d; nSubAuthority6
0x1800373cf  mov     dl, bl; nSubAuthorityCount
0x1800373d1  mov     [rsp+0F0h+nSubAuthority5], r13d; nSubAuthority5
0x1800373d6  lea     r8d, [rbx+1Eh]; nSubAuthority0
0x1800373da  mov     [rsp+0F0h+nSubAuthority4], r13d; nSubAuthority4
0x1800373df  mov     [rsp+0F0h+nSubAuthority3], r13d; nSubAuthority3
0x1800373e4  mov     [rsp+0F0h+nSubAuthority2], r13d; nSubAuthority2
0x1800373e9  call    cs:__imp_AllocateAndInitializeSid
0x1800373ef  test    eax, eax
0x1800373f1  jnz     short loc_180037407
0x1800373f3  call    cs:__imp_GetLastError
0x1800373f9  mov     ebx, eax
0x1800373fb  lea     rcx, aAllocateandini; "AllocateAndInitializeSid Err"
0x180037402  jmp     loc_180037527
0x180037407  mov     rax, [rbp+47h+psidOwner]
0x18003740b  lea     r9, [rbp+47h+NewAcl]; NewAcl
0x18003740f  xor     r8d, r8d; OldAcl
0x180037412  mov     qword ptr [rbp+47h+pListOfExplicitEntries.Trustee.TrusteeType], rbx
0x180037416  xorps   xmm0, xmm0
0x180037419  mov     [rbp+47h+pListOfExplicitEntries.Trustee.ptstrName], rax
0x18003741d  lea     rdx, [rbp+47h+pListOfExplicitEntries]; pListOfExplicitEntries
0x180037421  mov     [rbp+47h+pListOfExplicitEntries.grfAccessPermissions], 10000000h
0x180037428  movdqu  xmmword ptr [rbp+47h+pListOfExplicitEntries+0Ch], xmm0
0x18003742d  lea     ecx, [r8+1]; cCountOfExplicitEntries
0x180037431  mov     qword ptr [rbp+47h+pListOfExplicitEntries.grfAccessMode], rbx
0x180037435  mov     [rbp+47h+pListOfExplicitEntries.Trustee.TrusteeForm], r13d
0x180037439  call    cs:__imp_SetEntriesInAclW
0x18003743f  mov     ebx, eax
0x180037441  test    eax, eax
0x180037443  jz      short loc_180037451
0x180037445  lea     rcx, aSetentriesinac; "SetEntriesInAcl Err"
0x18003744c  jmp     loc_180037527
0x180037451  mov     qword ptr [rsp+0F0h+nSubAuthority5], r14; ppSecurityDescriptor
0x180037456  mov     r9, rsi; ppsidOwner
0x180037459  mov     r14d, 1
0x18003745f  mov     qword ptr [rsp+0F0h+nSubAuthority4], r13; ppSacl
0x180037464  mov     qword ptr [rsp+0F0h+nSubAuthority3], r13; ppDacl
0x180037469  mov     r8d, r14d; SecurityInfo
0x18003746c  mov     rcx, rdi; pObjectName
0x18003746f  mov     qword ptr [rsp+0F0h+nSubAuthority2], r13; ppsidGroup
0x180037474  lea     esi, [r14+3]
0x180037478  mov     edx, esi; ObjectType
0x18003747a  call    cs:__imp_GetNamedSecurityInfoW
0x180037480  mov     ebx, eax
0x180037482  test    eax, eax
0x180037484  jz      short loc_180037492
0x180037486  lea     rcx, aGetnamedsecuri; "GetNamedSecurityInfo OWNER_SECURITY_INF"...
0x18003748d  jmp     loc_180037527
0x180037492  mov     r9, [rbp+47h+psidOwner]; psidOwner
0x180037496  mov     r8d, r14d; SecurityInfo
0x180037499  mov     qword ptr [rsp+0F0h+nSubAuthority4], r13; pSacl
0x18003749e  mov     edx, esi; ObjectType
0x1800374a0  mov     qword ptr [rsp+0F0h+nSubAuthority3], r13; pDacl
0x1800374a5  mov     rcx, rdi; pObjectName
0x1800374a8  mov     qword ptr [rsp+0F0h+nSubAuthority2], r13; psidGroup
0x1800374ad  call    cs:__imp_SetNamedSecurityInfoW
0x1800374b3  mov     ebx, eax
0x1800374b5  test    eax, eax
0x1800374b7  jz      short loc_1800374C2
0x1800374b9  lea     rcx, aSetnamedsecuri_0; "SetNamedSecurityInfo OWNER_SECURITY_INF"...
0x1800374c0  jmp     short loc_180037527
0x1800374c2  mov     qword ptr [rsp+0F0h+nSubAuthority5], r12; ppSecurityDescriptor
0x1800374c7  xor     r9d, r9d; ppsidOwner
0x1800374ca  mov     qword ptr [rsp+0F0h+nSubAuthority4], r13; ppSacl
0x1800374cf  mov     r8d, esi; SecurityInfo
0x1800374d2  mov     qword ptr [rsp+0F0h+nSubAuthority3], r15; ppDacl
0x1800374d7  mov     edx, esi; ObjectType
0x1800374d9  mov     rcx, rdi; pObjectName
0x1800374dc  mov     qword ptr [rsp+0F0h+nSubAuthority2], r13; ppsidGroup
0x1800374e1  call    cs:__imp_GetNamedSecurityInfoW
0x1800374e7  mov     ebx, eax
0x1800374e9  test    eax, eax
0x1800374eb  jz      short loc_1800374F6
0x1800374ed  lea     rcx, aGetnamedsecuri_0; "GetNamedSecurityInfo DACL_SECURITY_INFO"...
0x1800374f4  jmp     short loc_180037527
0x1800374f6  mov     rax, [rbp+47h+NewAcl]
0x1800374fa  xor     r9d, r9d; psidOwner
0x1800374fd  mov     qword ptr [rsp+0F0h+nSubAuthority4], r13; pSacl
0x180037502  mov     r8d, esi; SecurityInfo
0x180037505  mov     qword ptr [rsp+0F0h+nSubAuthority3], rax; pDacl
0x18003750a  mov     edx, esi; ObjectType
0x18003750c  mov     rcx, rdi; pObjectName
0x18003750f  mov     qword ptr [rsp+0F0h+nSubAuthority2], r13; psidGroup
0x180037514  call    cs:__imp_SetNamedSecurityInfoW
0x18003751a  mov     ebx, eax
0x18003751c  test    eax, eax
0x18003751e  jz      short loc_18003752E
0x180037520  lea     rcx, aSetnamedsecuri_2; "SetNamedSecurityInfo DACL_SECURITY_INFO"...
0x180037527  mov     edx, eax; unsigned int
0x180037529  call    ?LogMsg@@YAXPEADK@Z; LogMsg(char *,ulong)
0x18003752e  mov     eax, ebx
0x180037530  mov     rcx, [rbp+47h+var_48]
0x180037534  xor     rcx, rsp; StackCookie
0x180037537  call    __security_check_cookie
0x18003753c  add     rsp, 0B8h
0x180037543  pop     r15
0x180037545  pop     r14
0x180037547  pop     r13
0x180037549  pop     r12
0x18003754b  pop     rdi
0x18003754c  pop     rsi
0x18003754d  pop     rbx
0x18003754e  pop     rbp
0x18003754f  retn
```
