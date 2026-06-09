# Windows::Compat::Appraiser::AuxJsonOutputter::MakeFileUserReadable(ushort *)

- ea: `0x1800fc3f0`
- end: `0x1800fc707`
- name: `?MakeFileUserReadable@AuxJsonOutputter@Appraiser@Compat@Windows@@CAJPEAG@Z`
- size: `791`
- prototype: `__int64 __fastcall(char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800fcc90`

## callees

- `0x18002ebb8`
- `0x1800301d0`
- `0x1800fc3f0`

## import_xrefs

- `KERNEL32!LocalFree` at `0x1800fc6bc`
- `KERNEL32!LocalFree` at `0x1800fc6cb`
- `KERNEL32!LocalFree` at `0x1800fc6bc`
- `KERNEL32!LocalFree` at `0x1800fc6cb`
- `KERNEL32!GetProcessHeap` at `0x1800fc547`
- `KERNEL32!GetProcessHeap` at `0x1800fc6d6`
- `KERNEL32!GetProcessHeap` at `0x1800fc547`
- `KERNEL32!GetProcessHeap` at `0x1800fc6d6`
- `KERNEL32!HeapAlloc` at `0x1800fc555`
- `KERNEL32!HeapAlloc` at `0x1800fc555`
- `KERNEL32!GetLastError` at `0x1800fc583`
- `KERNEL32!GetLastError` at `0x1800fc583`
- `KERNEL32!HeapFree` at `0x1800fc6e4`
- `KERNEL32!HeapFree` at `0x1800fc6e4`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1800fc65f`
- `ADVAPI32!SetNamedSecurityInfoW` at `0x1800fc65f`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800fc4dd`
- `ADVAPI32!GetNamedSecurityInfoW` at `0x1800fc4dd`
- `ADVAPI32!CreateWellKnownSid` at `0x1800fc579`
- `ADVAPI32!CreateWellKnownSid` at `0x1800fc579`
- `ADVAPI32!SetEntriesInAclW` at `0x1800fc5ef`
- `ADVAPI32!SetEntriesInAclW` at `0x1800fc5ef`
- `SHLWAPI!PathFileExistsW` at `0x1800fc436`
- `SHLWAPI!PathFileExistsW` at `0x1800fc436`

## string_xrefs

- `0x1800fc451`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fc48c`: `onecore\base\appcompat\appraiser\outputters\auxjson.cpp`
- `0x1800fc5a7`: `Failed to create UserSid: [0x%x].`
- `0x1800fc4f6`: `Failed to get dacl from file: [0x%x].`
- `0x1800fc524`: `Failed to get dacl from file: [0x%x].`
- `0x1800fc458`: `Windows::Compat::Appraiser::AuxJsonOutputter::MakeFileUserReadable`
- `0x1800fc480`: `Windows::Compat::Appraiser::AuxJsonOutputter::MakeFileUserReadable`
- `0x1800fc440`: `File %ls to re-ACL does not exist.`
- `0x1800fc499`: `File %ls to re-ACL does not exist.`
- `0x1800fc678`: `Failed to Set new Security info: [0x%x].`
- `0x1800fc695`: `Failed to Set new Security info: [0x%x].`
- `0x1800fc608`: `Failed to set entries in acl: [0x%x]`
- `0x1800fc625`: `Failed to set entries in acl: [0x%x]`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::AuxJsonOutputter::MakeFileUserReadable(WCHAR *a1)
{
  WCHAR *v2; // r15
  signed int v3; // ebx
  char v4; // dl
  signed int NamedSecurityInfoW; // eax
  const char *v6; // r9
  HANDLE ProcessHeap; // rax
  WCHAR *v8; // rax
  signed int LastError; // eax
  signed int v10; // eax
  signed int v11; // eax
  HANDLE v12; // rax
  PSID *ppsidGroup; // [rsp+20h] [rbp-60h]
  const char *ppDacl; // [rsp+28h] [rbp-58h]
  PACL *ppSacl; // [rsp+30h] [rbp-50h]
  PSECURITY_DESCRIPTOR hMem; // [rsp+40h] [rbp-40h] BYREF
  struct _EXPLICIT_ACCESS_W pListOfExplicitEntries; // [rsp+48h] [rbp-38h] BYREF
  DWORD cbSid; // [rsp+C8h] [rbp+48h] BYREF
  PACL NewAcl; // [rsp+D0h] [rbp+50h] BYREF
  PACL OldAcl; // [rsp+D8h] [rbp+58h] BYREF

  memset(&pListOfExplicitEntries, 0, sizeof(pListOfExplicitEntries));
  cbSid = 0;
  v2 = 0;
  OldAcl = 0;
  NewAcl = 0;
  hMem = 0;
  if ( !PathFileExistsW(a1) )
  {
    ppSacl = (PACL *)a1;
    ppDacl = "File %ls to re-ACL does not exist.";
    v3 = -2147024809;
    v4 = 100;
LABEL_3:
    LODWORD(ppsidGroup) = v3;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v4,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::MakeFileUserReadable",
      (const char *)ppsidGroup,
      (int)ppDacl,
      (const char *)ppSacl);
    goto LABEL_34;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x464u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::MakeFileUserReadable",
      "File %ls to re-ACL does not exist.",
      a1);
  NamedSecurityInfoW = GetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, &OldAcl, 0, &hMem);
  v3 = NamedSecurityInfoW;
  if ( NamedSecurityInfoW > 0 )
    v3 = (unsigned __int16)NamedSecurityInfoW | 0x80070000;
  if ( v3 < 0 )
  {
    v6 = "Failed to get dacl from file: [0x%x].";
    v4 = 114;
LABEL_10:
    LODWORD(ppSacl) = v3;
    LODWORD(ppDacl) = (_DWORD)v6;
    goto LABEL_3;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x472u,
      "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
      "Windows::Compat::Appraiser::AuxJsonOutputter::MakeFileUserReadable",
      "Failed to get dacl from file: [0x%x].",
      v3);
  cbSid = 68;
  ProcessHeap = GetProcessHeap();
  v8 = (WCHAR *)HeapAlloc(ProcessHeap, 0, 0x44u);
  v2 = v8;
  if ( v8 )
  {
    if ( !CreateWellKnownSid(WinBuiltinUsersSid, 0, v8, &cbSid) )
    {
      LastError = GetLastError();
      v3 = LastError;
      if ( LastError > 0 )
        v3 = (unsigned __int16)LastError | 0x80070000;
      v4 = 127;
      if ( v3 >= 0 )
        v3 = -2147467259;
      LODWORD(ppSacl) = v3;
      ppDacl = "Failed to create UserSid: [0x%x].";
      goto LABEL_3;
    }
    pListOfExplicitEntries.grfAccessPermissions = 0x80000000;
    pListOfExplicitEntries.grfAccessMode = SET_ACCESS;
    pListOfExplicitEntries.grfInheritance = 2;
    *(_QWORD *)&pListOfExplicitEntries.Trustee.MultipleTrusteeOperation = 0;
    pListOfExplicitEntries.Trustee.pMultipleTrustee = 0;
    pListOfExplicitEntries.Trustee.TrusteeType = TRUSTEE_IS_WELL_KNOWN_GROUP;
    pListOfExplicitEntries.Trustee.ptstrName = v2;
    v10 = SetEntriesInAclW(1u, &pListOfExplicitEntries, OldAcl, &NewAcl);
    v3 = v10;
    if ( v10 > 0 )
      v3 = (unsigned __int16)v10 | 0x80070000;
    if ( v3 < 0 )
    {
      v6 = "Failed to set entries in acl: [0x%x]";
      v4 = -104;
      goto LABEL_10;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x498u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
        "Windows::Compat::Appraiser::AuxJsonOutputter::MakeFileUserReadable",
        "Failed to set entries in acl: [0x%x]",
        v3);
    v11 = SetNamedSecurityInfoW(a1, SE_FILE_OBJECT, 4u, 0, 0, NewAcl, 0);
    v3 = v11;
    if ( v11 > 0 )
      v3 = (unsigned __int16)v11 | 0x80070000;
    if ( v3 < 0 )
    {
      v6 = "Failed to Set new Security info: [0x%x].";
      v4 = -91;
      goto LABEL_10;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x4A5u,
        "onecore\\base\\appcompat\\appraiser\\outputters\\auxjson.cpp",
        "Windows::Compat::Appraiser::AuxJsonOutputter::MakeFileUserReadable",
        "Failed to Set new Security info: [0x%x].",
        v3);
    v3 = 0;
  }
  else
  {
    v3 = -2147024882;
  }
LABEL_34:
  if ( hMem )
    LocalFree(hMem);
  if ( NewAcl )
    LocalFree(NewAcl);
  if ( v2 )
  {
    v12 = GetProcessHeap();
    HeapFree(v12, 0, v2);
  }
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1800fc3f0  mov     [rsp-38h+arg_0], rbx
0x1800fc3f5  push    rbp
0x1800fc3f6  push    rsi
0x1800fc3f7  push    rdi
0x1800fc3f8  push    r12
0x1800fc3fa  push    r13
0x1800fc3fc  push    r14
0x1800fc3fe  push    r15
0x1800fc400  mov     rbp, rsp
0x1800fc403  sub     rsp, 80h
0x1800fc40a  xor     r13d, r13d
0x1800fc40d  xorps   xmm0, xmm0
0x1800fc410  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee+4], xmm0
0x1800fc414  mov     r12, rcx
0x1800fc417  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], r13d
0x1800fc41b  movups  xmmword ptr [rbp+pListOfExplicitEntries.Trustee.TrusteeType], xmm0
0x1800fc41f  mov     [rbp+cbSid], r13d
0x1800fc423  mov     r15d, r13d
0x1800fc426  movups  xmmword ptr [rbp+pListOfExplicitEntries.grfAccessMode], xmm0
0x1800fc42a  mov     [rbp+OldAcl], r13
0x1800fc42e  mov     [rbp+NewAcl], r13
0x1800fc432  mov     [rbp+hMem], r13
0x1800fc436  call    cs:__imp_PathFileExistsW
0x1800fc43c  test    eax, eax
0x1800fc43e  jnz     short loc_1800FC47A
0x1800fc440  lea     r9, aFileLsToReAclD; "File %ls to re-ACL does not exist."
0x1800fc447  mov     [rsp+80h+ppSacl], r12; char *
0x1800fc44c  mov     [rsp+80h+ppDacl], r9; int
0x1800fc451  lea     r8, aOnecoreBaseApp_62; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800fc458  lea     r9, aWindowsCompatA_468; "Windows::Compat::Appraiser::AuxJsonOutp"...
0x1800fc45f  mov     ebx, 80070057h
0x1800fc464  mov     edx, 464h; bool
0x1800fc469  lea     ecx, [rax+1]; this
0x1800fc46c  mov     dword ptr [rsp+80h+ppsidGroup], ebx; char *
0x1800fc470  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800fc475  jmp     loc_1800FC6B3
0x1800fc47a  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fc480  lea     rsi, aWindowsCompatA_468; "Windows::Compat::Appraiser::AuxJsonOutp"...
0x1800fc487  mov     edi, 1
0x1800fc48c  lea     r14, aOnecoreBaseApp_62; "onecore\\base\\appcompat\\appraiser\\ou"...
0x1800fc493  and     eax, edi
0x1800fc495  test    al, al
0x1800fc497  jz      short loc_1800FC4B5
0x1800fc499  lea     r9, aFileLsToReAclD; "File %ls to re-ACL does not exist."
0x1800fc4a0  mov     [rsp+80h+ppsidGroup], r12
0x1800fc4a5  mov     r8, rsi; char *
0x1800fc4a8  mov     rdx, r14; char *
0x1800fc4ab  mov     ecx, 464h; unsigned int
0x1800fc4b0  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fc4b5  lea     rax, [rbp+hMem]
0x1800fc4b9  xor     r9d, r9d; ppsidOwner
0x1800fc4bc  mov     [rsp+80h+ppSecurityDescriptor], rax; ppSecurityDescriptor
0x1800fc4c1  mov     edx, edi; ObjectType
0x1800fc4c3  lea     rax, [rbp+OldAcl]
0x1800fc4c7  mov     [rsp+80h+ppSacl], r13; ppSacl
0x1800fc4cc  mov     [rsp+80h+ppDacl], rax; ppDacl
0x1800fc4d1  mov     rcx, r12; pObjectName
0x1800fc4d4  lea     r8d, [r9+4]; SecurityInfo
0x1800fc4d8  mov     [rsp+80h+ppsidGroup], r13; ppsidGroup
0x1800fc4dd  call    cs:__imp_GetNamedSecurityInfoW
0x1800fc4e3  mov     ebx, eax
0x1800fc4e5  test    eax, eax
0x1800fc4e7  jle     short loc_1800FC4F2
0x1800fc4e9  movzx   ebx, ax
0x1800fc4ec  or      ebx, 80070000h
0x1800fc4f2  test    ebx, ebx
0x1800fc4f4  jns     short loc_1800FC518
0x1800fc4f6  lea     r9, aFailedToGetDac; "Failed to get dacl from file: [0x%x]."
0x1800fc4fd  mov     edx, 472h
0x1800fc502  mov     dword ptr [rsp+80h+ppSacl], ebx
0x1800fc506  mov     [rsp+80h+ppDacl], r9
0x1800fc50b  mov     r8, r14
0x1800fc50e  mov     r9, rsi
0x1800fc511  mov     ecx, edi
0x1800fc513  jmp     loc_1800FC46C
0x1800fc518  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fc51e  and     eax, edi
0x1800fc520  test    al, al
0x1800fc522  jz      short loc_1800FC53F
0x1800fc524  lea     r9, aFailedToGetDac; "Failed to get dacl from file: [0x%x]."
0x1800fc52b  mov     dword ptr [rsp+80h+ppsidGroup], ebx
0x1800fc52f  mov     r8, rsi; char *
0x1800fc532  mov     rdx, r14; char *
0x1800fc535  mov     ecx, 472h; unsigned int
0x1800fc53a  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fc53f  mov     ebx, 44h ; 'D'
0x1800fc544  mov     [rbp+cbSid], ebx
0x1800fc547  call    cs:__imp_GetProcessHeap
0x1800fc54d  mov     r8d, ebx; dwBytes
0x1800fc550  xor     edx, edx; dwFlags
0x1800fc552  mov     rcx, rax; hHeap
0x1800fc555  call    cs:__imp_HeapAlloc
0x1800fc55b  mov     r15, rax
0x1800fc55e  test    rax, rax
0x1800fc561  jnz     short loc_1800FC56D
0x1800fc563  mov     ebx, 8007000Eh
0x1800fc568  jmp     loc_1800FC6B3
0x1800fc56d  xor     edx, edx; DomainSid
0x1800fc56f  lea     r9, [rbp+cbSid]; cbSid
0x1800fc573  mov     r8, r15; pSid
0x1800fc576  lea     ecx, [rdx+1Bh]; WellKnownSidType
0x1800fc579  call    cs:__imp_CreateWellKnownSid
0x1800fc57f  test    eax, eax
0x1800fc581  jnz     short loc_1800FC5BC
0x1800fc583  call    cs:__imp_GetLastError
0x1800fc589  mov     ebx, eax
0x1800fc58b  test    eax, eax
0x1800fc58d  jle     short loc_1800FC598
0x1800fc58f  movzx   ebx, ax
0x1800fc592  or      ebx, 80070000h
0x1800fc598  mov     eax, 80004005h
0x1800fc59d  test    ebx, ebx
0x1800fc59f  mov     edx, 47Fh
0x1800fc5a4  cmovns  ebx, eax
0x1800fc5a7  lea     rax, aFailedToCreate_32; "Failed to create UserSid: [0x%x]."
0x1800fc5ae  mov     dword ptr [rsp+80h+ppSacl], ebx
0x1800fc5b2  mov     [rsp+80h+ppDacl], rax
0x1800fc5b7  jmp     loc_1800FC50B
0x1800fc5bc  mov     r8, [rbp+OldAcl]; OldAcl
0x1800fc5c0  lea     r9, [rbp+NewAcl]; NewAcl
0x1800fc5c4  mov     eax, 2
0x1800fc5c9  mov     [rbp+pListOfExplicitEntries.grfAccessPermissions], 80000000h
0x1800fc5d0  lea     rdx, [rbp+pListOfExplicitEntries]; pListOfExplicitEntries
0x1800fc5d4  mov     [rbp+pListOfExplicitEntries.grfAccessMode], eax
0x1800fc5d7  mov     ecx, edi; cCountOfExplicitEntries
0x1800fc5d9  mov     [rbp+pListOfExplicitEntries.grfInheritance], eax
0x1800fc5dc  mov     qword ptr [rbp+pListOfExplicitEntries.Trustee.MultipleTrusteeOperation], r13
0x1800fc5e0  mov     [rbp+pListOfExplicitEntries.Trustee.pMultipleTrustee], r13
0x1800fc5e4  mov     [rbp+pListOfExplicitEntries.Trustee.TrusteeType], 5
0x1800fc5eb  mov     [rbp+pListOfExplicitEntries.Trustee.ptstrName], r15
0x1800fc5ef  call    cs:__imp_SetEntriesInAclW
0x1800fc5f5  mov     ebx, eax
0x1800fc5f7  test    eax, eax
0x1800fc5f9  jle     short loc_1800FC604
0x1800fc5fb  movzx   ebx, ax
0x1800fc5fe  or      ebx, 80070000h
0x1800fc604  test    ebx, ebx
0x1800fc606  jns     short loc_1800FC619
0x1800fc608  lea     r9, aFailedToSetEnt; "Failed to set entries in acl: [0x%x]"
0x1800fc60f  mov     edx, 498h
0x1800fc614  jmp     loc_1800FC502
0x1800fc619  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fc61f  and     eax, edi
0x1800fc621  test    al, al
0x1800fc623  jz      short loc_1800FC640
0x1800fc625  lea     r9, aFailedToSetEnt; "Failed to set entries in acl: [0x%x]"
0x1800fc62c  mov     dword ptr [rsp+80h+ppsidGroup], ebx
0x1800fc630  mov     r8, rsi; char *
0x1800fc633  mov     rdx, r14; char *
0x1800fc636  mov     ecx, 498h; unsigned int
0x1800fc63b  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fc640  mov     rax, [rbp+NewAcl]
0x1800fc644  xor     r9d, r9d; psidOwner
0x1800fc647  mov     [rsp+80h+ppSacl], r13; pSacl
0x1800fc64c  mov     edx, edi; ObjectType
0x1800fc64e  mov     [rsp+80h+ppDacl], rax; pDacl
0x1800fc653  mov     rcx, r12; pObjectName
0x1800fc656  mov     [rsp+80h+ppsidGroup], r13; psidGroup
0x1800fc65b  lea     r8d, [r9+4]; SecurityInfo
0x1800fc65f  call    cs:__imp_SetNamedSecurityInfoW
0x1800fc665  mov     ebx, eax
0x1800fc667  test    eax, eax
0x1800fc669  jle     short loc_1800FC674
0x1800fc66b  movzx   ebx, ax
0x1800fc66e  or      ebx, 80070000h
0x1800fc674  test    ebx, ebx
0x1800fc676  jns     short loc_1800FC689
0x1800fc678  lea     r9, aFailedToSetNew; "Failed to Set new Security info: [0x%x]"...
0x1800fc67f  mov     edx, 4A5h
0x1800fc684  jmp     loc_1800FC502
0x1800fc689  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800fc68f  and     eax, edi
0x1800fc691  test    al, al
0x1800fc693  jz      short loc_1800FC6B0
0x1800fc695  lea     r9, aFailedToSetNew; "Failed to Set new Security info: [0x%x]"...
0x1800fc69c  mov     dword ptr [rsp+80h+ppsidGroup], ebx
0x1800fc6a0  mov     r8, rsi; char *
0x1800fc6a3  mov     rdx, r14; char *
0x1800fc6a6  mov     ecx, 4A5h; unsigned int
0x1800fc6ab  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800fc6b0  mov     ebx, r13d
0x1800fc6b3  mov     rcx, [rbp+hMem]; hMem
0x1800fc6b7  test    rcx, rcx
0x1800fc6ba  jz      short loc_1800FC6C2
0x1800fc6bc  call    cs:__imp_LocalFree
0x1800fc6c2  mov     rcx, [rbp+NewAcl]; hMem
0x1800fc6c6  test    rcx, rcx
0x1800fc6c9  jz      short loc_1800FC6D1
0x1800fc6cb  call    cs:__imp_LocalFree
0x1800fc6d1  test    r15, r15
0x1800fc6d4  jz      short loc_1800FC6EA
0x1800fc6d6  call    cs:__imp_GetProcessHeap
0x1800fc6dc  mov     r8, r15; lpMem
0x1800fc6df  xor     edx, edx; dwFlags
0x1800fc6e1  mov     rcx, rax; hHeap
0x1800fc6e4  call    cs:__imp_HeapFree
0x1800fc6ea  mov     eax, ebx
0x1800fc6ec  mov     rbx, [rsp+80h+arg_0]
0x1800fc6f4  add     rsp, 80h
0x1800fc6fb  pop     r15
0x1800fc6fd  pop     r14
0x1800fc6ff  pop     r13
0x1800fc701  pop     r12
0x1800fc703  pop     rdi
0x1800fc704  pop     rsi
0x1800fc705  pop     rbp
0x1800fc706  retn
```
