# StateRepository::Entity::PackageExtension::UpdateActivationBy_PrimaryKey(StateRepository::Database &,__int64,__int64)

- ea: `0x18001ed34`
- end: `0x18001ee8e`
- name: `?UpdateActivationBy_PrimaryKey@PackageExtension@Entity@StateRepository@@QEAAJAEAVDatabase@3@_J1@Z`
- size: `346`
- prototype: `int(StateRepository::Entity::PackageExtension *__hidden this, struct StateRepository::Database *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d734`

## callees

- `0x18000a3c0`
- `0x18000c3bc`
- `0x1800182f8`
- `0x180018e04`
- `0x180018f78`
- `0x180019614`
- `0x18001b5a8`
- `0x18001b64c`
- `0x18001b8d4`
- `0x18001ed34`

## string_xrefs

- `0x18001ed5b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension-custom.cpp`
- `0x18001edc8`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension-custom.cpp`
- `0x18001ee45`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension-custom.cpp`
- `0x18001ed87`: `UPDATE PackageExtension SET Activation=? WHERE _PackageExtensionID=? AND _WorkId=?;`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::PackageExtension::UpdateActivationBy_PrimaryKey(
        StateRepository::Entity::PackageExtension *this,
        struct StateRepository::Database *a2,
        __int64 a3,
        __int64 a4)
{
  unsigned int v7; // ebx
  int NoRow; // eax
  __int64 v9; // rdx
  __int64 v10; // r9
  int v11; // eax
  int v13; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  StateRepository::Entity::PackageExtension *v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = this;
  if ( !StateRepository::Database::IsInAutoCommitMode(a2) )
  {
    v15 = 0;
    NoRow = StateRepository::Database::PrepareFromCache(
              a2,
              "UPDATE PackageExtension SET Activation=? WHERE _PackageExtensionID=? AND _WorkId=?;",
              (struct StateRepository::Statement *)&v15);
    v7 = NoRow;
    if ( NoRow >= 0 )
    {
      NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v15, 1, a4);
      v7 = NoRow;
      if ( NoRow >= 0 )
      {
        NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v15, 2, a3);
        v7 = NoRow;
        if ( NoRow >= 0 )
        {
          NoRow = StateRepository::Statement::Bind((StateRepository::Statement *)&v15, 3, *((_QWORD *)a2 + 1));
          v7 = NoRow;
          if ( NoRow >= 0 )
          {
            NoRow = StateRepository::Statement::FetchNoRow((StateRepository::Statement *)&v15);
            v7 = NoRow;
            if ( NoRow >= 0 )
            {
              v11 = StateRepository::Database::AddToCache(a2, (struct StateRepository::Statement *)&v15);
              if ( v11 < 0 )
                wil::details::in1diag3::_Log_Hr(
                  retaddr,
                  (void *)0x15C,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension-custom.cpp",
                  (const char *)(unsigned int)v11,
                  v13);
              if ( (unsigned int)StateRepository::Database::GetChanges(a2) )
              {
                v7 = 0;
                goto LABEL_20;
              }
              v7 = -2147023728;
              v9 = 350;
              v10 = 2147943568LL;
LABEL_8:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v9,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension-custom.cpp",
                (const char *)v10,
                v13);
LABEL_20:
              StateRepository::Statement::~Statement((StateRepository::Statement *)&v15);
              return v7;
            }
            v9 = 346;
          }
          else
          {
            v9 = 344;
          }
        }
        else
        {
          v9 = 343;
        }
      }
      else
      {
        v9 = 342;
      }
    }
    else
    {
      v9 = 341;
    }
    v10 = (unsigned int)NoRow;
    goto LABEL_8;
  }
  v7 = -2140733429;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x151,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension-custom.cpp",
    (const char *)0x8067000BLL,
    v13);
  return v7;
}

```

## disassembly

```asm
0x18001ed34  mov     [rsp+arg_0], rcx
0x18001ed39  push    rbx
0x18001ed3a  push    rbp
0x18001ed3b  push    rsi
0x18001ed3c  push    rdi
0x18001ed3d  sub     rsp, 28h
0x18001ed41  mov     rcx, rdx; this
0x18001ed44  mov     rsi, r9
0x18001ed47  mov     rbp, r8
0x18001ed4a  mov     rdi, rdx
0x18001ed4d  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001ed52  test    al, al
0x18001ed54  jz      short loc_18001ED79
0x18001ed56  mov     rcx, [rsp+48h]; this
0x18001ed5b  lea     r8, aOnecoreBaseApp_60; "onecore\\base\\appmodel\\staterepositor"...
0x18001ed62  mov     ebx, 8067000Bh
0x18001ed67  mov     edx, 151h; void *
0x18001ed6c  mov     r9d, ebx; char *
0x18001ed6f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ed74  jmp     loc_18001EE83
0x18001ed79  lea     r8, [rsp+48h+arg_0]; struct StateRepository::Statement *
0x18001ed7e  mov     [rsp+48h+arg_0], 0
0x18001ed87  lea     rdx, aUpdatePackagee; "UPDATE PackageExtension SET Activation="...
0x18001ed8e  mov     rcx, rdi; this
0x18001ed91  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18001ed96  mov     ebx, eax
0x18001ed98  test    eax, eax
0x18001ed9a  jns     short loc_18001EDA3
0x18001ed9c  mov     edx, 155h
0x18001eda1  jmp     short loc_18001EDC0
0x18001eda3  mov     r8, rsi; __int64
0x18001eda6  lea     rcx, [rsp+48h+arg_0]; this
0x18001edab  mov     edx, 1; int
0x18001edb0  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001edb5  mov     ebx, eax
0x18001edb7  test    eax, eax
0x18001edb9  jns     short loc_18001EDD9
0x18001edbb  mov     edx, 156h; void *
0x18001edc0  mov     r9d, eax; char *
0x18001edc3  mov     rcx, [rsp+48h]; this
0x18001edc8  lea     r8, aOnecoreBaseApp_60; "onecore\\base\\appmodel\\staterepositor"...
0x18001edcf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001edd4  jmp     loc_18001EE79
0x18001edd9  mov     r8, rbp; __int64
0x18001eddc  lea     rcx, [rsp+48h+arg_0]; this
0x18001ede1  mov     edx, 2; int
0x18001ede6  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001edeb  mov     ebx, eax
0x18001eded  test    eax, eax
0x18001edef  jns     short loc_18001EDF8
0x18001edf1  mov     edx, 157h
0x18001edf6  jmp     short loc_18001EDC0
0x18001edf8  mov     r8, [rdi+8]; __int64
0x18001edfc  lea     rcx, [rsp+48h+arg_0]; this
0x18001ee01  mov     edx, 3; int
0x18001ee06  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001ee0b  mov     ebx, eax
0x18001ee0d  test    eax, eax
0x18001ee0f  jns     short loc_18001EE18
0x18001ee11  mov     edx, 158h
0x18001ee16  jmp     short loc_18001EDC0
0x18001ee18  lea     rcx, [rsp+48h+arg_0]; this
0x18001ee1d  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x18001ee22  mov     ebx, eax
0x18001ee24  test    eax, eax
0x18001ee26  jns     short loc_18001EE2F
0x18001ee28  mov     edx, 15Ah
0x18001ee2d  jmp     short loc_18001EDC0
0x18001ee2f  lea     rdx, [rsp+48h+arg_0]; struct StateRepository::Statement *
0x18001ee34  mov     rcx, rdi; this
0x18001ee37  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18001ee3c  test    eax, eax
0x18001ee3e  jns     short loc_18001EE59
0x18001ee40  mov     rcx, [rsp+48h]; this
0x18001ee45  lea     r8, aOnecoreBaseApp_60; "onecore\\base\\appmodel\\staterepositor"...
0x18001ee4c  mov     r9d, eax; char *
0x18001ee4f  mov     edx, 15Ch; void *
0x18001ee54  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001ee59  mov     rcx, rdi; this
0x18001ee5c  call    ?GetChanges@Database@StateRepository@@QEBAHXZ; StateRepository::Database::GetChanges(void)
0x18001ee61  test    eax, eax
0x18001ee63  jnz     short loc_18001EE77
0x18001ee65  mov     ebx, 80070490h
0x18001ee6a  mov     edx, 15Eh
0x18001ee6f  mov     r9d, ebx
0x18001ee72  jmp     loc_18001EDC3
0x18001ee77  xor     ebx, ebx
0x18001ee79  lea     rcx, [rsp+48h+arg_0]; this
0x18001ee7e  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18001ee83  mov     eax, ebx
0x18001ee85  add     rsp, 28h
0x18001ee89  pop     rdi
0x18001ee8a  pop     rsi
0x18001ee8b  pop     rbp
0x18001ee8c  pop     rbx
0x18001ee8d  retn
```
