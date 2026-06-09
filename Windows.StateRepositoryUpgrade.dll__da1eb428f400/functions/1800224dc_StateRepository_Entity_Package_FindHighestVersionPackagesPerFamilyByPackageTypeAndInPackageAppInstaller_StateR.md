# StateRepository::Entity::Package::FindHighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller(StateRepository::Database &,StateRepository::PackageType,StateRepository::Statement &)

- ea: `0x1800224dc`
- end: `0x180022599`
- name: `?FindHighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller@Package@Entity@StateRepository@@SAJAEAVDatabase@3@W4PackageType@3@AEAVStatement@3@@Z`
- size: `189`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x180013c40`

## callees

- `0x18000829c`
- `0x18000a3c0`
- `0x1800222a8`
- `0x1800224dc`
- `0x18002a124`
- `0x18002f010`

## string_xrefs

- `0x18002254c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package-custom.cpp`
- `0x180022514`: `SELECT p._PackageID, p._Revision, p._WorkId, p.PackageFamily, p.ResourceId, p.Architecture, p.Version, p.PackageFullName, p.IsInbox, p.PackageType, p.Flags, p.Flags2, p.DisplayName, p.PublisherDisplayName, p.Description, p.Logo, p.OSMinVersion, p.OSMaxVersionTested, p.TargetDeviceFamily, p.Capabilities, p.SupportedUsers, p.SignatureOrigin, p.PackageOrigin, p.Enterprise, p.SourceBundle, p.EditionId, p.OSVersionWhenIndexed, p.InPlaceUpdateBaseline, p._Dictionary FROM Package AS p WHERE (p.PackageF`
- `0x180022527`: `SELECT p._PackageID, p._Revision, p._WorkId, p.PackageFamily, p.ResourceId, p.Architecture, p.Version, p.PackageFullName, p.IsInbox, p.PackageType, p.Flags, p.Flags2, p.DisplayName, p.PublisherDisplayName, p.Description, p.Logo, p.OSMinVersion, p.OSMaxVersionTested, p.TargetDeviceFamily, p.Capabilities, p.SupportedUsers, p.SignatureOrigin, p.PackageOrigin, p.Enterprise, p.SourceBundle, p.EditionId, p.OSVersionWhenIndexed, p.InPlaceUpdateBaseline, p._Dictionary FROM Package AS p WHERE (p.PackageF`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Package::FindHighestVersionPackagesPerFamilyByPackageTypeAndInPackageAppInstaller(
        __int64 a1,
        __int64 a2,
        __int64 a3)
{
  __int64 v3; // rax
  struct StateRepository::StatementExecution::StatementBinderFunc *v4; // r9
  StateRepository::StatementExecution *v5; // r10
  int v6; // eax
  unsigned int v7; // ebx
  struct StateRepository::Statement *v9; // [rsp+20h] [rbp-59h] BYREF
  _QWORD v10[3]; // [rsp+28h] [rbp-51h] BYREF
  _QWORD v11[18]; // [rsp+40h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  char v13; // [rsp+F8h] [rbp+7Fh] BYREF

  LODWORD(v9) = 1;
  v3 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v13, &v9, a3, a3);
  StateRepository::StatementExecution::StatementBinderFunc::StatementBinderFunc__lambda_d4a0a62bd9599993fad7f5125f7355ce___(
    v11,
    v3);
  v10[2] = 2;
  v10[0] = "SELECT p._PackageID, p._Revision, p._WorkId, p.PackageFamily, p.ResourceId, p.Architecture, p.Version, p.Pack"
           "ageFullName, p.IsInbox, p.PackageType, p.Flags, p.Flags2, p.DisplayName, p.PublisherDisplayName, p.Descriptio"
           "n, p.Logo, p.OSMinVersion, p.OSMaxVersionTested, p.TargetDeviceFamily, p.Capabilities, p.SupportedUsers, p.Si"
           "gnatureOrigin, p.PackageOrigin, p.Enterprise, p.SourceBundle, p.EditionId, p.OSVersionWhenIndexed, p.InPlaceU"
           "pdateBaseline, p._Dictionary FROM Package AS p WHERE (p.PackageFamily, p.Version, p.PackageType) IN ( SELECT "
           "PackageFamily, MAX_UINT(Version), PackageType FROM Package WHERE _PackageID IN (SELECT Package FROM PackageAp"
           "pInstaller) AND PackageType & ? != 0 AND _WorkId=0 GROUP BY PackageFamily);";
  v10[1] = "SELECT p._PackageID, p._Revision, p._WorkId, p.PackageFamily, p.ResourceId, p.Architecture, p.Version, p.Pack"
           "ageFullName, p.IsInbox, p.PackageType, p.Flags, p.Flags2, p.DisplayName, p.PublisherDisplayName, p.Descriptio"
           "n, p.Logo, p.OSMinVersion, p.OSMaxVersionTested, p.TargetDeviceFamily, p.Capabilities, p.SupportedUsers, p.Si"
           "gnatureOrigin, p.PackageOrigin, p.Enterprise, p.SourceBundle, p.EditionId, p.OSVersionWhenIndexed, p.InPlaceU"
           "pdateBaseline, p._Dictionary FROM Package AS p WHERE (p.PackageFamily, p.Version, p.PackageType) IN ( SELECT "
           "PackageFamily, MAX_UINT(Version), PackageType FROM Package WHERE _PackageID IN (SELECT Package FROM PackageAp"
           "pInstaller) AND PackageType & ? != 0 AND (_WorkId=0 OR _WorkId=?) GROUP BY PackageFamily);";
  v6 = StateRepository::StatementExecution::PrepareAndBindAndFindBy(
         v5,
         (struct StateRepository::Database *)v10,
         (const struct StateRepository::StatementExecution::StatementDefinition *)v11,
         v4,
         v9);
  v7 = v6;
  if ( v6 >= 0 )
  {
    (**(void (__fastcall ***)(_QWORD, _QWORD))v11[0])(v11[0], 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x138A,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package-custom.cpp",
      (const char *)(unsigned int)v6,
      (int)v9);
    (**(void (__fastcall ***)(_QWORD, _QWORD))v11[0])(v11[0], 0);
    return v7;
  }
}

```

## disassembly

```asm
0x1800224dc  mov     [rsp-8+arg_0], rbx
0x1800224e1  push    rbp
0x1800224e2  lea     rbp, [rsp-57h]
0x1800224e7  sub     rsp, 0D0h
0x1800224ee  mov     r10, rcx
0x1800224f1  mov     dword ptr [rbp+57h+var_B0], 1
0x1800224f8  lea     rcx, [rbp+57h+arg_18]
0x1800224fc  mov     r9, r8
0x1800224ff  lea     rdx, [rbp+57h+var_B0]
0x180022503  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x180022508  mov     rdx, rax
0x18002250b  lea     rcx, [rbp+57h+var_90]
0x18002250f  call    StateRepository__StatementExecution__StatementBinderFunc__StatementBinderFunc__lambda_d4a0a62bd9599993fad7f5125f7355ce___
0x180022514  lea     rcx, aSelectPPackage_0; "SELECT p._PackageID, p._Revision, p._Wo"...
0x18002251b  mov     [rbp+57h+var_98], 2
0x180022523  mov     [rbp+57h+var_A8], rcx
0x180022527  lea     rax, aSelectPPackage; "SELECT p._PackageID, p._Revision, p._Wo"...
0x18002252e  mov     rcx, r10; this
0x180022531  mov     [rbp+57h+var_A0], rax
0x180022535  lea     r8, [rbp+57h+var_90]; struct StateRepository::StatementExecution::StatementDefinition *
0x180022539  lea     rdx, [rbp+57h+var_A8]; struct StateRepository::Database *
0x18002253d  call    ?PrepareAndBindAndFindBy@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFindBy(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,StateRepository::Statement &)
0x180022542  mov     ebx, eax
0x180022544  test    eax, eax
0x180022546  jns     short loc_180022575
0x180022548  mov     rcx, [rbp+5Fh]; this
0x18002254c  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x180022553  mov     r9d, eax; char *
0x180022556  mov     edx, 138Ah; void *
0x18002255b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022560  mov     rcx, [rbp+57h+var_90]
0x180022564  mov     rdx, [rcx]
0x180022567  mov     rax, [rdx]
0x18002256a  xor     edx, edx
0x18002256c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022571  mov     eax, ebx
0x180022573  jmp     short loc_180022588
0x180022575  mov     rcx, [rbp+57h+var_90]
0x180022579  xor     edx, edx
0x18002257b  mov     rax, [rcx]
0x18002257e  mov     rax, [rax]
0x180022581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022586  xor     eax, eax
0x180022588  mov     rbx, [rsp+0D0h+arg_0]
0x180022590  add     rsp, 0D0h
0x180022597  pop     rbp
0x180022598  retn
```
