# StateRepository::Entity::PackageAppInstaller::FindByPackage(StateRepository::Database &,__int64,StateRepository::Statement &)

- ea: `0x1800258d4`
- end: `0x18002598b`
- name: `?FindByPackage@PackageAppInstaller@Entity@StateRepository@@SAJAEAVDatabase@3@_JAEAVStatement@3@@Z`
- size: `183`
- prototype: `__int64 __fastcall(struct StateRepository::Database *, __int64, struct StateRepository::Statement *)`
- caller_count: `1`
- callee_count: `4`
- tags: `installer_update`

## callers

- `0x180013c40`

## callees

- `0x18000a3c0`
- `0x1800258d4`
- `0x18002a124`
- `0x18002f010`

## string_xrefs

- `0x18002593e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageappinstaller.cpp`
- `0x180025919`: `SELECT _PackageAppInstallerID, _Revision, _WorkId, Package, AppInstaller, _Dictionary FROM PackageAppInstaller WHERE Package=? AND _WorkId=0;`
- `0x180025924`: `SELECT _PackageAppInstallerID, _Revision, _WorkId, Package, AppInstaller, _Dictionary FROM PackageAppInstaller WHERE Package=? AND (_WorkId=0 OR _WorkId=?);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::PackageAppInstaller::FindByPackage(
        struct StateRepository::Database *a1,
        __int64 a2,
        struct StateRepository::Statement *a3)
{
  int v3; // eax
  unsigned int v4; // ebx
  _QWORD v6[4]; // [rsp+20h] [rbp-59h] BYREF
  _QWORD *v7; // [rsp+40h] [rbp-39h] BYREF
  _QWORD v8[17]; // [rsp+48h] [rbp-31h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]
  __int64 v10; // [rsp+E8h] [rbp+6Fh] BYREF

  v10 = a2;
  v6[2] = 2;
  v8[0] = &off_180030D90;
  v8[1] = &v10;
  v7 = v8;
  v6[1] = "SELECT _PackageAppInstallerID, _Revision, _WorkId, Package, AppInstaller, _Dictionary FROM PackageAppInstaller"
          " WHERE Package=? AND (_WorkId=0 OR _WorkId=?);";
  v3 = StateRepository::StatementExecution::PrepareAndBindAndFindBy(
         a1,
         (struct StateRepository::Database *)v6,
         (const struct StateRepository::StatementExecution::StatementDefinition *)&v7,
         a3,
         (struct StateRepository::Statement *)"SELECT _PackageAppInstallerID, _Revision, _WorkId, Package, AppInstaller, "
                                              "_Dictionary FROM PackageAppInstaller WHERE Package=? AND _WorkId=0;");
  v4 = v3;
  if ( v3 >= 0 )
  {
    (*(void (__fastcall **)(_QWORD *, _QWORD))*v7)(v7, 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x18D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageappinstaller.cpp",
      (const char *)(unsigned int)v3,
      v6[0]);
    (*(void (__fastcall **)(_QWORD *, _QWORD))*v7)(v7, 0);
    return v4;
  }
}

```

## disassembly

```asm
0x1800258d4  mov     [rsp-8+arg_0], rbx
0x1800258d9  mov     [rsp-8+arg_8], rdx
0x1800258de  push    rbp
0x1800258df  lea     rbp, [rsp-57h]
0x1800258e4  sub     rsp, 0D0h
0x1800258eb  lea     rax, off_180030D90
0x1800258f2  mov     [rbp+57h+var_A0], 2
0x1800258fa  mov     [rbp+57h+var_88], rax
0x1800258fe  lea     rdx, [rbp+57h+var_B0]; struct StateRepository::Database *
0x180025902  lea     rax, [rbp+57h+arg_8]
0x180025906  mov     r9, r8; struct StateRepository::StatementExecution::StatementBinderFunc *
0x180025909  mov     [rbp+57h+var_80], rax
0x18002590d  lea     r8, [rbp+57h+var_90]; struct StateRepository::StatementExecution::StatementDefinition *
0x180025911  lea     rax, [rbp+57h+var_88]
0x180025915  mov     [rbp+57h+var_90], rax
0x180025919  lea     rax, aSelectPackagea_2; "SELECT _PackageAppInstallerID, _Revisio"...
0x180025920  mov     [rbp+57h+var_B0], rax
0x180025924  lea     rax, aSelectPackagea_0; "SELECT _PackageAppInstallerID, _Revisio"...
0x18002592b  mov     [rbp+57h+var_A8], rax
0x18002592f  call    ?PrepareAndBindAndFindBy@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFindBy(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,StateRepository::Statement &)
0x180025934  mov     ebx, eax
0x180025936  test    eax, eax
0x180025938  jns     short loc_180025967
0x18002593a  mov     rcx, [rbp+5Fh]; this
0x18002593e  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x180025945  mov     r9d, eax; char *
0x180025948  mov     edx, 18Dh; void *
0x18002594d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025952  mov     rcx, [rbp+57h+var_90]
0x180025956  mov     rdx, [rcx]
0x180025959  mov     rax, [rdx]
0x18002595c  xor     edx, edx
0x18002595e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025963  mov     eax, ebx
0x180025965  jmp     short loc_18002597A
0x180025967  mov     rcx, [rbp+57h+var_90]
0x18002596b  xor     edx, edx
0x18002596d  mov     rax, [rcx]
0x180025970  mov     rax, [rax]
0x180025973  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025978  xor     eax, eax
0x18002597a  mov     rbx, [rsp+0D0h+arg_0]
0x180025982  add     rsp, 0D0h
0x180025989  pop     rbp
0x18002598a  retn
```
