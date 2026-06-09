# StateRepository::Entity::Application::UpdateActivationBy_PrimaryKey(StateRepository::Database &,__int64,__int64)

- ea: `0x18001cf88`
- end: `0x18001d0e2`
- name: `?UpdateActivationBy_PrimaryKey@Application@Entity@StateRepository@@QEAAJAEAVDatabase@3@_J1@Z`
- size: `346`
- prototype: `int(StateRepository::Entity::Application *__hidden this, struct StateRepository::Database *, __int64, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d31c`

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
- `0x18001cf88`

## string_xrefs

- `0x18001cfaf`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application-custom.cpp`
- `0x18001d01c`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application-custom.cpp`
- `0x18001d099`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application-custom.cpp`
- `0x18001cfdb`: `UPDATE Application SET Activation=? WHERE _ApplicationID=? AND _WorkId=?;`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Application::UpdateActivationBy_PrimaryKey(
        StateRepository::Entity::Application *this,
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
  StateRepository::Entity::Application *v15; // [rsp+50h] [rbp+8h] BYREF

  v15 = this;
  if ( !StateRepository::Database::IsInAutoCommitMode(a2) )
  {
    v15 = 0;
    NoRow = StateRepository::Database::PrepareFromCache(
              a2,
              "UPDATE Application SET Activation=? WHERE _ApplicationID=? AND _WorkId=?;",
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
                  (void *)0x752,
                  (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application-custom.cpp",
                  (const char *)(unsigned int)v11,
                  v13);
              if ( (unsigned int)StateRepository::Database::GetChanges(a2) )
              {
                v7 = 0;
                goto LABEL_20;
              }
              v7 = -2147023728;
              v9 = 1876;
              v10 = 2147943568LL;
LABEL_8:
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)v9,
                (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application-custom.cpp",
                (const char *)v10,
                v13);
LABEL_20:
              StateRepository::Statement::~Statement((StateRepository::Statement *)&v15);
              return v7;
            }
            v9 = 1872;
          }
          else
          {
            v9 = 1870;
          }
        }
        else
        {
          v9 = 1869;
        }
      }
      else
      {
        v9 = 1868;
      }
    }
    else
    {
      v9 = 1867;
    }
    v10 = (unsigned int)NoRow;
    goto LABEL_8;
  }
  v7 = -2140733429;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x747,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application-custom.cpp",
    (const char *)0x8067000BLL,
    v13);
  return v7;
}

```

## disassembly

```asm
0x18001cf88  mov     [rsp+arg_0], rcx
0x18001cf8d  push    rbx
0x18001cf8e  push    rbp
0x18001cf8f  push    rsi
0x18001cf90  push    rdi
0x18001cf91  sub     rsp, 28h
0x18001cf95  mov     rcx, rdx; this
0x18001cf98  mov     rsi, r9
0x18001cf9b  mov     rbp, r8
0x18001cf9e  mov     rdi, rdx
0x18001cfa1  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001cfa6  test    al, al
0x18001cfa8  jz      short loc_18001CFCD
0x18001cfaa  mov     rcx, [rsp+48h]; this
0x18001cfaf  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18001cfb6  mov     ebx, 8067000Bh
0x18001cfbb  mov     edx, 747h; void *
0x18001cfc0  mov     r9d, ebx; char *
0x18001cfc3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cfc8  jmp     loc_18001D0D7
0x18001cfcd  lea     r8, [rsp+48h+arg_0]; struct StateRepository::Statement *
0x18001cfd2  mov     [rsp+48h+arg_0], 0
0x18001cfdb  lea     rdx, aUpdateApplicat_7; "UPDATE Application SET Activation=? WHE"...
0x18001cfe2  mov     rcx, rdi; this
0x18001cfe5  call    ?PrepareFromCache@Database@StateRepository@@QEAAJPEBDAEAVStatement@2@@Z; StateRepository::Database::PrepareFromCache(char const *,StateRepository::Statement &)
0x18001cfea  mov     ebx, eax
0x18001cfec  test    eax, eax
0x18001cfee  jns     short loc_18001CFF7
0x18001cff0  mov     edx, 74Bh
0x18001cff5  jmp     short loc_18001D014
0x18001cff7  mov     r8, rsi; __int64
0x18001cffa  lea     rcx, [rsp+48h+arg_0]; this
0x18001cfff  mov     edx, 1; int
0x18001d004  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001d009  mov     ebx, eax
0x18001d00b  test    eax, eax
0x18001d00d  jns     short loc_18001D02D
0x18001d00f  mov     edx, 74Ch; void *
0x18001d014  mov     r9d, eax; char *
0x18001d017  mov     rcx, [rsp+48h]; this
0x18001d01c  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18001d023  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001d028  jmp     loc_18001D0CD
0x18001d02d  mov     r8, rbp; __int64
0x18001d030  lea     rcx, [rsp+48h+arg_0]; this
0x18001d035  mov     edx, 2; int
0x18001d03a  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001d03f  mov     ebx, eax
0x18001d041  test    eax, eax
0x18001d043  jns     short loc_18001D04C
0x18001d045  mov     edx, 74Dh
0x18001d04a  jmp     short loc_18001D014
0x18001d04c  mov     r8, [rdi+8]; __int64
0x18001d050  lea     rcx, [rsp+48h+arg_0]; this
0x18001d055  mov     edx, 3; int
0x18001d05a  call    ?Bind@Statement@StateRepository@@QEAAJH_J@Z; StateRepository::Statement::Bind(int,__int64)
0x18001d05f  mov     ebx, eax
0x18001d061  test    eax, eax
0x18001d063  jns     short loc_18001D06C
0x18001d065  mov     edx, 74Eh
0x18001d06a  jmp     short loc_18001D014
0x18001d06c  lea     rcx, [rsp+48h+arg_0]; this
0x18001d071  call    ?FetchNoRow@Statement@StateRepository@@QEAAJXZ; StateRepository::Statement::FetchNoRow(void)
0x18001d076  mov     ebx, eax
0x18001d078  test    eax, eax
0x18001d07a  jns     short loc_18001D083
0x18001d07c  mov     edx, 750h
0x18001d081  jmp     short loc_18001D014
0x18001d083  lea     rdx, [rsp+48h+arg_0]; struct StateRepository::Statement *
0x18001d088  mov     rcx, rdi; this
0x18001d08b  call    ?AddToCache@Database@StateRepository@@QEAAJAEAVStatement@2@@Z; StateRepository::Database::AddToCache(StateRepository::Statement &)
0x18001d090  test    eax, eax
0x18001d092  jns     short loc_18001D0AD
0x18001d094  mov     rcx, [rsp+48h]; this
0x18001d099  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18001d0a0  mov     r9d, eax; char *
0x18001d0a3  mov     edx, 752h; void *
0x18001d0a8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d0ad  mov     rcx, rdi; this
0x18001d0b0  call    ?GetChanges@Database@StateRepository@@QEBAHXZ; StateRepository::Database::GetChanges(void)
0x18001d0b5  test    eax, eax
0x18001d0b7  jnz     short loc_18001D0CB
0x18001d0b9  mov     ebx, 80070490h
0x18001d0be  mov     edx, 754h
0x18001d0c3  mov     r9d, ebx
0x18001d0c6  jmp     loc_18001D017
0x18001d0cb  xor     ebx, ebx
0x18001d0cd  lea     rcx, [rsp+48h+arg_0]; this
0x18001d0d2  call    ??1Statement@StateRepository@@QEAA@XZ; StateRepository::Statement::~Statement(void)
0x18001d0d7  mov     eax, ebx
0x18001d0d9  add     rsp, 28h
0x18001d0dd  pop     rdi
0x18001d0de  pop     rsi
0x18001d0df  pop     rbp
0x18001d0e0  pop     rbx
0x18001d0e1  retn
```
