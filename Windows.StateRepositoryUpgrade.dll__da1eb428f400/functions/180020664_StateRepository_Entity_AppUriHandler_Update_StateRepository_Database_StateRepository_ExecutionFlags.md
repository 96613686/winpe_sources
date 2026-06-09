# StateRepository::Entity::AppUriHandler::Update(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x180020664`
- end: `0x18002070c`
- name: `?Update@AppUriHandler@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `168`
- prototype: `int __high(struct StateRepository::Database *, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e85c`

## callees

- `0x18000a3c0`
- `0x180018f78`
- `0x18001b0f0`
- `0x18001b3bc`
- `0x180020108`
- `0x180020664`

## string_xrefs

- `0x180020685`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`
- `0x1800206dd`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-appurihandler.cpp`
- `0x1800206b5`: `UPDATE AppUriHandler SET _Revision=?, _WorkId=?, HostName=?, Path=?, Extension=?, ProgID=?, AppUriHandlerGroup=?, _Dictionary=? WHERE _AppUriHandlerID=? AND _Revision=? AND _WorkId=0;`
- `0x1800206bc`: `UPDATE AppUriHandler SET _Revision=?, _WorkId=?, HostName=?, Path=?, Extension=?, ProgID=?, AppUriHandlerGroup=?, _Dictionary=? WHERE _AppUriHandlerID=? AND _Revision=? AND (_WorkId=0 OR _WorkId=?);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::AppUriHandler::Update(__int64 a1, StateRepository::Database *a2)
{
  unsigned int v4; // ebx
  char v5; // r9
  const char *v6; // r8
  int v7; // eax
  int v9; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v11; // [rsp+58h] [rbp+20h] BYREF

  if ( StateRepository::Database::IsInAutoCommitMode(a2) )
  {
    v4 = -2140733429;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2AC,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
      (const char *)0x8067000BLL,
      v9);
  }
  else
  {
    StateRepository::DatabaseTriggers::Disable(&v11, a2, 0);
    v6 = "UPDATE AppUriHandler SET _Revision=?, _WorkId=?, HostName=?, Path=?, Extension=?, ProgID=?, AppUriHandlerGroup="
         "?, _Dictionary=? WHERE _AppUriHandlerID=? AND _Revision=? AND (_WorkId=0 OR _WorkId=?);";
    if ( !*((_QWORD *)a2 + 1) )
      v6 = "UPDATE AppUriHandler SET _Revision=?, _WorkId=?, HostName=?, Path=?, Extension=?, ProgID=?, AppUriHandlerGrou"
           "p=?, _Dictionary=? WHERE _AppUriHandlerID=? AND _Revision=? AND _WorkId=0;";
    v7 = StateRepository::Entity::AppUriHandler::BindAndExecuteForAddOrUpdate(a1, a2, v6, v5);
    v4 = v7;
    if ( v7 >= 0 )
      v4 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B4,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-appurihandler.cpp",
        (const char *)(unsigned int)v7,
        v9);
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v11);
  }
  return v4;
}

```

## disassembly

```asm
0x180020664  mov     [rsp+arg_0], rbx
0x180020669  push    rdi
0x18002066a  sub     rsp, 30h
0x18002066e  mov     rdi, rcx
0x180020671  mov     rbx, rdx
0x180020674  mov     rcx, rdx; this
0x180020677  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18002067c  test    al, al
0x18002067e  jz      short loc_1800206A0
0x180020680  mov     rcx, [rsp+38h]; this
0x180020685  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x18002068c  mov     ebx, 8067000Bh
0x180020691  mov     edx, 2ACh; void *
0x180020696  mov     r9d, ebx; char *
0x180020699  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002069e  jmp     short loc_1800206FF
0x1800206a0  xor     r8d, r8d
0x1800206a3  lea     rcx, [rsp+38h+arg_18]
0x1800206a8  mov     rdx, rbx
0x1800206ab  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x1800206b0  cmp     qword ptr [rbx+8], 0
0x1800206b5  lea     rax, aUpdateAppuriha; "UPDATE AppUriHandler SET _Revision=?, _"...
0x1800206bc  lea     r8, aUpdateAppuriha_0; "UPDATE AppUriHandler SET _Revision=?, _"...
0x1800206c3  mov     rdx, rbx
0x1800206c6  cmovz   r8, rax
0x1800206ca  mov     rcx, rdi
0x1800206cd  call    ?BindAndExecuteForAddOrUpdate@AppUriHandler@Entity@StateRepository@@AEAAJAEAVDatabase@3@PEBD_NW4ExecutionFlags@3@@Z; StateRepository::Entity::AppUriHandler::BindAndExecuteForAddOrUpdate(StateRepository::Database &,char const *,bool,StateRepository::ExecutionFlags)
0x1800206d2  mov     ebx, eax
0x1800206d4  test    eax, eax
0x1800206d6  jns     short loc_1800206F3
0x1800206d8  mov     rcx, [rsp+38h]; this
0x1800206dd  lea     r8, aOnecoreBaseApp_46; "onecore\\base\\appmodel\\staterepositor"...
0x1800206e4  mov     r9d, eax; char *
0x1800206e7  mov     edx, 2B4h; void *
0x1800206ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800206f1  jmp     short loc_1800206F5
0x1800206f3  xor     ebx, ebx
0x1800206f5  lea     rcx, [rsp+38h+arg_18]; this
0x1800206fa  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x1800206ff  mov     eax, ebx
0x180020701  mov     rbx, [rsp+38h+arg_0]
0x180020706  add     rsp, 30h
0x18002070a  pop     rdi
0x18002070b  retn
```
