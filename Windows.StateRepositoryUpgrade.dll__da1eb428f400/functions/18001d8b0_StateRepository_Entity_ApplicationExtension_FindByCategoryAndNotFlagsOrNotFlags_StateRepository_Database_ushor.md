# StateRepository::Entity::ApplicationExtension::FindByCategoryAndNotFlagsOrNotFlags(StateRepository::Database &,ushort const *,StateRepository::ApplicationExtensionFlags,StateRepository::ApplicationExtensionFlags,StateRepository::Statement &)

- ea: `0x18001d8b0`
- end: `0x18001d988`
- name: `?FindByCategoryAndNotFlagsOrNotFlags@ApplicationExtension@Entity@StateRepository@@SAJAEAVDatabase@3@PEBGW4ApplicationExtensionFlags@3@2AEAVStatement@3@@Z`
- size: `216`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting`

## callers

- `0x1800141f0`

## callees

- `0x18000a3c0`
- `0x18001d6c4`
- `0x18001d6f0`
- `0x18001d8b0`
- `0x18002a124`
- `0x18002f010`

## string_xrefs

- `0x18001d93b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`
- `0x18001d903`: `SELECT _ApplicationExtensionID, _Revision, _WorkId, Application, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPath, Id, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE Category=?1 AND (Flags & ?2 = 0 OR Flags & ?3 = 0) AND _WorkId=0;`
- `0x18001d90e`: `SELECT _ApplicationExtensionID, _Revision, _WorkId, Application, "Index", Category, Activation, HostId, Executable, Entrypoint, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPath, Id, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE Category=?1 AND (Flags & ?2 = 0 OR Flags & ?3 = 0) AND (_WorkId=0 OR _WorkId=?4);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::ApplicationExtension::FindByCategoryAndNotFlagsOrNotFlags(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        struct StateRepository::StatementExecution::StatementBinderFunc *a5)
{
  __int64 v5; // rax
  StateRepository::StatementExecution *v6; // r10
  int v7; // eax
  unsigned int v8; // ebx
  struct StateRepository::Statement *v10; // [rsp+20h] [rbp-71h] BYREF
  int v11; // [rsp+28h] [rbp-69h] BYREF
  const WCHAR *v12; // [rsp+30h] [rbp-61h] BYREF
  _QWORD v13[3]; // [rsp+38h] [rbp-59h] BYREF
  _QWORD v14[18]; // [rsp+50h] [rbp-41h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  LODWORD(v10) = 48;
  v12 = L"windows.fullTrustProcess";
  v11 = 128;
  v5 = lambda_5cfa40fb4bedf52bb922d5d14416393c_::_lambda_5cfa40fb4bedf52bb922d5d14416393c_(v13, &v12, &v11, &v10);
  StateRepository::StatementExecution::StatementBinderFunc::StatementBinderFunc__lambda_5cfa40fb4bedf52bb922d5d14416393c___(
    v14,
    v5);
  v13[0] = "SELECT _ApplicationExtensionID, _Revision, _WorkId, Application, \"Index\", Category, Activation, HostId, Exe"
           "cutable, Entrypoint, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPat"
           "h, Id, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE Category=?1 AND (Flags & ?2 = 0 OR F"
           "lags & ?3 = 0) AND _WorkId=0;";
  v13[1] = "SELECT _ApplicationExtensionID, _Revision, _WorkId, Application, \"Index\", Category, Activation, HostId, Exe"
           "cutable, Entrypoint, RuntimeType, StartPage, ResourceGroup, Flags, Subsystem, Parameters, CurrentDirectoryPat"
           "h, Id, _LocalizedDictionary, _Dictionary FROM ApplicationExtension WHERE Category=?1 AND (Flags & ?2 = 0 OR F"
           "lags & ?3 = 0) AND (_WorkId=0 OR _WorkId=?4);";
  v13[2] = 4;
  v7 = StateRepository::StatementExecution::PrepareAndBindAndFindBy(
         v6,
         (struct StateRepository::Database *)v13,
         (const struct StateRepository::StatementExecution::StatementDefinition *)v14,
         a5,
         v10);
  v8 = v7;
  if ( v7 >= 0 )
  {
    (**(void (__fastcall ***)(_QWORD, _QWORD))v14[0])(v14[0], 0);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x47B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
      (const char *)(unsigned int)v7,
      (int)v10);
    (**(void (__fastcall ***)(_QWORD, _QWORD))v14[0])(v14[0], 0);
    return v8;
  }
}

```

## disassembly

```asm
0x18001d8b0  mov     [rsp-8+arg_0], rbx
0x18001d8b5  push    rbp
0x18001d8b6  lea     rbp, [rsp-4Fh]
0x18001d8bb  sub     rsp, 0E0h
0x18001d8c2  lea     rax, aWindowsFulltru; "windows.fullTrustProcess"
0x18001d8c9  mov     dword ptr [rbp+4Fh+var_C0], 30h ; '0'
0x18001d8d0  mov     r10, rcx
0x18001d8d3  mov     [rbp+4Fh+var_B0], rax
0x18001d8d7  lea     rcx, [rbp+4Fh+var_A8]
0x18001d8db  mov     [rbp+4Fh+var_B8], 80h
0x18001d8e2  lea     r9, [rbp+4Fh+var_C0]
0x18001d8e6  lea     r8, [rbp+4Fh+var_B8]
0x18001d8ea  lea     rdx, [rbp+4Fh+var_B0]
0x18001d8ee  call    _lambda_5cfa40fb4bedf52bb922d5d14416393c____lambda_5cfa40fb4bedf52bb922d5d14416393c_
0x18001d8f3  mov     rdx, rax
0x18001d8f6  lea     rcx, [rbp+4Fh+var_90]
0x18001d8fa  call    StateRepository__StatementExecution__StatementBinderFunc__StatementBinderFunc__lambda_5cfa40fb4bedf52bb922d5d14416393c___
0x18001d8ff  mov     r9, [rbp+4Fh+arg_20]; struct StateRepository::StatementExecution::StatementBinderFunc *
0x18001d903  lea     rcx, aSelectApplicat_4; "SELECT _ApplicationExtensionID, _Revisi"...
0x18001d90a  mov     [rbp+4Fh+var_A8], rcx
0x18001d90e  lea     rax, aSelectApplicat_0; "SELECT _ApplicationExtensionID, _Revisi"...
0x18001d915  mov     rcx, r10; this
0x18001d918  mov     [rbp+4Fh+var_A0], rax
0x18001d91c  lea     r8, [rbp+4Fh+var_90]; struct StateRepository::StatementExecution::StatementDefinition *
0x18001d920  mov     [rbp+4Fh+var_98], 4
0x18001d928  lea     rdx, [rbp+4Fh+var_A8]; struct StateRepository::Database *
0x18001d92c  call    ?PrepareAndBindAndFindBy@StatementExecution@StateRepository@@YAJAEAVDatabase@2@AEBUStatementDefinition@12@AEAVStatementBinderFunc@12@AEAVStatement@2@@Z; StateRepository::StatementExecution::PrepareAndBindAndFindBy(StateRepository::Database &,StateRepository::StatementExecution::StatementDefinition const &,StateRepository::StatementExecution::StatementBinderFunc &,StateRepository::Statement &)
0x18001d931  mov     ebx, eax
0x18001d933  test    eax, eax
0x18001d935  jns     short loc_18001D964
0x18001d937  mov     rcx, [rbp+57h]; this
0x18001d93b  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001d942  mov     r9d, eax; char *
0x18001d945  mov     edx, 47Bh; void *
0x18001d94a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d94f  mov     rcx, [rbp+4Fh+var_90]
0x18001d953  mov     rdx, [rcx]
0x18001d956  mov     rax, [rdx]
0x18001d959  xor     edx, edx
0x18001d95b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d960  mov     eax, ebx
0x18001d962  jmp     short loc_18001D977
0x18001d964  mov     rcx, [rbp+4Fh+var_90]
0x18001d968  xor     edx, edx
0x18001d96a  mov     rax, [rcx]
0x18001d96d  mov     rax, [rax]
0x18001d970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d975  xor     eax, eax
0x18001d977  mov     rbx, [rsp+0E0h+arg_0]
0x18001d97f  add     rsp, 0E0h
0x18001d986  pop     rbp
0x18001d987  retn
```
