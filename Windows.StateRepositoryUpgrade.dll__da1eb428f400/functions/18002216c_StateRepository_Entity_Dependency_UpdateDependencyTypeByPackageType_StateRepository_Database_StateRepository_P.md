# StateRepository::Entity::Dependency::UpdateDependencyTypeByPackageType(StateRepository::Database &,StateRepository::PackageType,StateRepository::DependencyType)

- ea: `0x18002216c`
- end: `0x18002227d`
- name: `?UpdateDependencyTypeByPackageType@Dependency@Entity@StateRepository@@SAJAEAVDatabase@3@W4PackageType@3@W4DependencyType@3@@Z`
- size: `273`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000ec40`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018f78`
- `0x180019614`
- `0x18001b5a8`
- `0x18001b5dc`
- `0x18001b8d4`
- `0x18002216c`

## string_xrefs

- `0x18002218b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-dependency-custom.cpp`
- `0x1800221f5`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-dependency-custom.cpp`
- `0x180022252`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-dependency-custom.cpp`
- `0x1800221b7`: `UPDATE Dependency SET DependencyType=? WHERE _DependencyID IN(SELECT d._DependencyID FROM Dependency AS d INNER JOIN PackageFamily AS pf ON pf.Name=d.Name INNER JOIN Package AS p ON p.PackageFamily=pf._PackageFamilyID WHERE p.PackageType=?);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Dependency::UpdateDependencyTypeByPackageType(
        StateRepository::Database *a1,
        int a2,
        int a3)
{
  unsigned int v6; // ebx
  int NoRow; // eax
  __int64 v8; // rdx
  int v9; // eax
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  __int64 v13; // [rsp+68h] [rbp+20h] BYREF

  if ( !StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v13 = 0;
    NoRow = StateRepository::Database::PrepareFromCache(
              a1,
              "UPDATE Dependency SET DependencyType=? WHERE _DependencyID IN(SELECT d._DependencyID FROM Dependency AS d "
              "INNER JOIN PackageFamily AS pf ON pf.Name=d.Name INNER JOIN Package AS p ON p.PackageFamily=pf._PackageFam"
              "ilyID WHERE p.PackageType=?);",
              (struct StateRepository::Statement *)&v13);
    v6 = NoRow;
    if ( NoRow >= 0 )
    {
      NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v13, 1, a3);
      v6 = NoRow;
      if ( NoRow >= 0 )
      {
        NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v13, 2, a2);
        v6 = NoRow;
        if ( NoRow >= 0 )
        {
          NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v13);
          v6 = NoRow;
          if ( NoRow >= 0 )
          {
            v9 = StateRepository::Database::AddToCache(a1, (struct StateRepository::Statement *)&v13);
            if ( v9 < 0 )
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0x5B,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-dependency-custom.cpp",
                (const char *)(unsigned int)v9,
                v11);
            v6 = 0;
            goto LABEL_15;
          }
          v8 = 89;
        }
        else
        {
          v8 = 87;
        }
      }
      else
      {
        v8 = 86;
      }
    }
    else
    {
      v8 = 85;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-dependency-custom.cpp",
      (const char *)(unsigned int)NoRow,
      v11);
LABEL_15:
    StateRepository::Statement::~Statement((StateRepository::Statement *)&v13);
    return v6;
  }
  v6 = -2140733429;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x4A,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-dependency-custom.cpp",
    (const char *)0x8067000BLL,
    v11);
  return v6;
}

```

## disassembly

```asm
0x18002216c  push    rbx
0x18002216e  push    rbp
0x18002216f  push    rsi
0x180022170  push    rdi
0x180022171  sub     rsp, 28h
0x180022175  mov     esi, r8d
0x180022178  mov     ebp, edx
0x18002217a  mov     rdi, rcx
0x18002217d  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180022182  test    al, al
0x180022184  jz      short loc_1800221A9
0x180022186  mov     rcx, [rsp+48h]; this
0x18002218b  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\staterepositor"...
0x180022192  mov     ebx, 8067000Bh
0x180022197  mov     edx, 4Ah ; 'J'; void *
0x18002219c  mov     r9d, ebx; char *
0x18002219f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800221a4  jmp     loc_180022272
0x1800221a9  lea     r8, [rsp+48h+arg_18]; struct StateRepository::Statement *
0x1800221ae  mov     [rsp+48h+arg_18], 0
0x1800221b7  lea     rdx, aUpdateDependen; "UPDATE Dependency SET DependencyType=? "...
0x1800221be  mov     rcx, rdi; this
0x1800221c1  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x1800221c6  mov     ebx, eax
0x1800221c8  test    eax, eax
0x1800221ca  jns     short loc_1800221D3
0x1800221cc  mov     edx, 55h ; 'U'
0x1800221d1  jmp     short loc_1800221F0
0x1800221d3  mov     r8d, esi; int
0x1800221d6  lea     rcx, [rsp+48h+arg_18]; this
0x1800221db  mov     edx, 1; int
0x1800221e0  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x1800221e5  mov     ebx, eax
0x1800221e7  test    eax, eax
0x1800221e9  jns     short loc_180022206
0x1800221eb  mov     edx, 56h ; 'V'; void *
0x1800221f0  mov     rcx, [rsp+48h]; this
0x1800221f5  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\staterepositor"...
0x1800221fc  mov     r9d, eax; char *
0x1800221ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180022204  jmp     short loc_180022268
0x180022206  mov     r8d, ebp; int
0x180022209  lea     rcx, [rsp+48h+arg_18]; this
0x18002220e  mov     edx, 2; int
0x180022213  call    ?Bind@Statement@StateRepository@@QEAAJHH@Z; StateRepository::Statement::Bind(int,int)
0x180022218  mov     ebx, eax
0x18002221a  test    eax, eax
0x18002221c  jns     short loc_180022225
0x18002221e  mov     edx, 57h ; 'W'
0x180022223  jmp     short loc_1800221F0
0x180022225  lea     rcx, [rsp+48h+arg_18]; this
0x18002222a  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x18002222f  mov     ebx, eax
0x180022231  test    eax, eax
0x180022233  jns     short loc_18002223C
0x180022235  mov     edx, 59h ; 'Y'
0x18002223a  jmp     short loc_1800221F0
0x18002223c  lea     rdx, [rsp+48h+arg_18]; struct StateRepository::Statement *
0x180022241  mov     rcx, rdi; this
0x180022244  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x180022249  test    eax, eax
0x18002224b  jns     short loc_180022266
0x18002224d  mov     rcx, [rsp+48h]; this
0x180022252  lea     r8, aOnecoreBaseApp_29; "onecore\\base\\appmodel\\staterepositor"...
0x180022259  mov     r9d, eax; char *
0x18002225c  mov     edx, 5Bh ; '['; void *
0x180022261  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180022266  xor     ebx, ebx
0x180022268  lea     rcx, [rsp+48h+arg_18]; this
0x18002226d  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x180022272  mov     eax, ebx
0x180022274  add     rsp, 28h
0x180022278  pop     rdi
0x180022279  pop     rsi
0x18002227a  pop     rbp
0x18002227b  pop     rbx
0x18002227c  retn
```
