# StateRepository::Entity::Package::FindByPackageTypeAndNEFlags(StateRepository::Database &,StateRepository::PackageType,StateRepository::PackageFlags,StateRepository::Statement &)

- ea: `0x180022410`
- end: `0x1800224d5`
- name: `?FindByPackageTypeAndNEFlags@Package@Entity@StateRepository@@SAJAEAVDatabase@3@W4PackageType@3@W4PackageFlags@3@AEAVStatement@3@@Z`
- size: `197`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update`

## callers

- `0x1800132e8`

## callees

- `0x18000a3c0`
- `0x180022284`
- `0x1800222cc`
- `0x180022410`
- `0x18002a124`
- `0x18002f010`

## string_xrefs

- `0x180022488`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-package-custom.cpp`
- `0x180022450`: `SELECT _PackageID, _Revision, _WorkId, PackageFamily, ResourceId, Architecture, Version, PackageFullName, IsInbox, PackageType, Flags, Flags2, DisplayName, PublisherDisplayName, Description, Logo, OSMinVersion, OSMaxVersionTested, TargetDeviceFamily, Capabilities, SupportedUsers, SignatureOrigin, PackageOrigin, Enterprise, SourceBundle, EditionId, OSVersionWhenIndexed, InPlaceUpdateBaseline, _Dictionary FROM Package WHERE PackageType & ? !=0 AND Flags & ? =0 AND _WorkId=0;`
- `0x180022463`: `SELECT _PackageID, _Revision, _WorkId, PackageFamily, ResourceId, Architecture, Version, PackageFullName, IsInbox, PackageType, Flags, Flags2, DisplayName, PublisherDisplayName, Description, Logo, OSMinVersion, OSMaxVersionTested, TargetDeviceFamily, Capabilities, SupportedUsers, SignatureOrigin, PackageOrigin, Enterprise, SourceBundle, EditionId, OSVersionWhenIndexed, InPlaceUpdateBaseline, _Dictionary FROM Package WHERE PackageType & ? !=0 AND Flags & ? =0 AND (_WorkId=0 OR _WorkId=?);`

## pseudocode

```c
__int64 StateRepository::Entity::Package::FindByPackageTypeAndNEFlags()
{
  __int64 v0; // rax
  struct StateRepository::StatementExecution::StatementBinderFunc *v1; // r9
  StateRepository::StatementExecution *v2; // r10
  int v3; // eax
  unsigned int v4; // ebx
  struct StateRepository::Statement *v6; // [rsp+20h] [rbp-69h] BYREF
  int v7; // [rsp+28h] [rbp-61h] BYREF
  _QWORD v8[4]; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v9[18]; // [rsp+50h] [rbp-39h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  LODWORD(v6) = 0x800000;
  v7 = 1;
  v0 = lambda_bcdb7cc532dd5d24722c5dcec1073ab9_::_lambda_bcdb7cc532dd5d24722c5dcec1073ab9_(v8, &v7, &v6);
  StateRepository::StatementExecution::StatementBinderFunc::StatementBinderFunc__lambda_bcdb7cc532dd5d24722c5dcec1073ab9___(
    v9,
    v0);
  v8[2] = 3;
  v8[0] = "SELECT _PackageID, _Revision, _WorkId, PackageFamily, ResourceId, Architecture, Version, PackageFullName, IsIn"
          "box, PackageType, Flags, Flags2, DisplayName, PublisherDisplayName, Description, Logo, OSMinVersion, OSMaxVers"
          "ionTested, TargetDeviceFamily, Capabilities, SupportedUsers, SignatureOrigin, PackageOrigin, Enterprise, Sourc"
          "eBundle, EditionId, OSVersionWhenIndexed, InPlaceUpdateBaseline, _Dictionary FROM Package WHERE PackageType & "
          "? !=0 AND Flags & ? =0 AND _WorkId=0;";
  v8[1] = "SELECT _PackageID, _Revision, _WorkId, PackageFamily, ResourceId, Architecture, Version, PackageFullName, IsIn"
          "box, PackageType, Flags, Flags2, DisplayName, PublisherDisplayName, Description, Logo, OSMinVersion, OSMaxVers"
          "ionTested, TargetDeviceFamily, Capabilities, SupportedUsers, SignatureOrigin, PackageOrigin, Enterprise, Sourc"
          "eBundle, EditionId, OSVersionWhenIndexed, InPlaceUpdateBaseline, _Dictionary FROM Package WHERE PackageType & "
          "? !=0 AND Flags & ? =0 AND (_WorkId=0 OR _WorkId=?);";
  v3 = StateRepository::StatementExecution::PrepareAndBindAndFindBy(
         v2,
         (struct StateRepository::Database *)v8,
         (const struct StateRepository::StatementExecution::StatementDefinition *)v9,
         v1,
         v6);
  v4 = v3;
  if ( v3 >= 0 )
  {
    (**(void (__fastcall ***)(_QWORD, _QWORD))v9[0])(v9[0], 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1257,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-package-custom.cpp",
      (const char *)(unsigned int)v3,
      (int)v6);
    (**(void (__fastcall ***)(_QWORD, _QWORD))v9[0])(v9[0], 0);
    return v4;
  }
}

```

## disassembly

```asm
0x180022410  mov     [rsp-8+arg_0], rbx
0x180022415  push    rbp
0x180022416  lea     rbp, [rsp-57h]
0x18002241b  sub     rsp, 0E0h
0x180022422  mov     r10, rcx
0x180022425  mov     dword ptr [rbp+57h+var_C0], 800000h
0x18002242c  lea     rcx, [rbp+57h+var_B0]
0x180022430  mov     [rbp+57h+var_B8], 1
0x180022437  lea     r8, [rbp+57h+var_C0]
0x18002243b  lea     rdx, [rbp+57h+var_B8]
0x18002243f  call    _lambda_bcdb7cc532dd5d24722c5dcec1073ab9____lambda_bcdb7cc532dd5d24722c5dcec1073ab9_
0x180022444  mov     rdx, rax
0x180022447  lea     rcx, [rbp+57h+var_90]
0x18002244b  call    StateRepository__StatementExecution__StatementBinderFunc__StatementBinderFunc__lambda_bcdb7cc532dd5d24722c5dcec1073ab9___
0x180022450  lea     rcx, aSelectPackagei; "SELECT _PackageID, _Revision, _WorkId, "...
0x180022457  mov     [rbp+57h+var_A0], 3
0x18002245f  mov     [rbp+57h+var_B0], rcx
0x180022463  lea     rax, aSelectPackagei_0; "SELECT _PackageID, _Revision, _WorkId, "...
0x18002246a  mov     rcx, r10; this
0x18002246d  mov     [rbp+57h+var_A8], rax
0x180022471  lea     r8, [rbp+57h+var_90]; struct StateRepository::StatementExecution::StatementDefinition *
0x180022475  lea     rdx, [rbp+57h+var_B0]; struct StateRepository::Database *
0x180022479  call    ?PrepareAndBindAndFindBy@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFindBy(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,StateRepository::Statement &)
0x18002247e  mov     ebx, eax
0x180022480  test    eax, eax
0x180022482  jns     short loc_1800224B1
0x180022484  mov     rcx, [rbp+5Fh]; this
0x180022488  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appmodel\\staterepositor"...
0x18002248f  mov     r9d, eax; char *
0x180022492  mov     edx, 1257h; void *
0x180022497  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002249c  mov     rcx, [rbp+57h+var_90]
0x1800224a0  mov     rdx, [rcx]
0x1800224a3  mov     rax, [rdx]
0x1800224a6  xor     edx, edx
0x1800224a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224ad  mov     eax, ebx
0x1800224af  jmp     short loc_1800224C4
0x1800224b1  mov     rcx, [rbp+57h+var_90]
0x1800224b5  xor     edx, edx
0x1800224b7  mov     rax, [rcx]
0x1800224ba  mov     rax, [rax]
0x1800224bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800224c2  xor     eax, eax
0x1800224c4  mov     rbx, [rsp+0E0h+arg_0]
0x1800224cc  add     rsp, 0E0h
0x1800224d3  pop     rbp
0x1800224d4  retn
```
