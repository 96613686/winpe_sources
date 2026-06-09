# StateRepository::Entity::FileTypeAssociation::Update(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x180020058`
- end: `0x180020100`
- name: `?Update@FileTypeAssociation@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `168`
- prototype: `int __high(struct StateRepository::Database *, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000e99c`

## callees

- `0x18000a3c0`
- `0x180018f78`
- `0x18001b0f0`
- `0x18001b3bc`
- `0x18001fafc`
- `0x180020058`

## string_xrefs

- `0x180020079`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`
- `0x1800200d1`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-filetypeassociation.cpp`
- `0x1800200a9`: `UPDATE FileTypeAssociation SET _Revision=?, _WorkId=?, FileType=?, ContentType=?, Extension=?, "Index"=?, ProgID=?, _Dictionary=? WHERE _FileTypeAssociationID=? AND _Revision=? AND _WorkId=0;`
- `0x1800200b0`: `UPDATE FileTypeAssociation SET _Revision=?, _WorkId=?, FileType=?, ContentType=?, Extension=?, "Index"=?, ProgID=?, _Dictionary=? WHERE _FileTypeAssociationID=? AND _Revision=? AND (_WorkId=0 OR _WorkId=?);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::FileTypeAssociation::Update(__int64 a1, StateRepository::Database *a2)
{
  unsigned int v4; // ebx
  const char *v5; // r8
  int v6; // eax
  int v8; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  char v10; // [rsp+58h] [rbp+20h] BYREF

  if ( StateRepository::Database::IsInAutoCommitMode(a2) )
  {
    v4 = -2140733429;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38D,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
      (const char *)0x8067000BLL,
      v8);
  }
  else
  {
    StateRepository::DatabaseTriggers::Disable(&v10, a2, 0);
    v5 = "UPDATE FileTypeAssociation SET _Revision=?, _WorkId=?, FileType=?, ContentType=?, Extension=?, \"Index\"=?, Pro"
         "gID=?, _Dictionary=? WHERE _FileTypeAssociationID=? AND _Revision=? AND (_WorkId=0 OR _WorkId=?);";
    if ( !*((_QWORD *)a2 + 1) )
      v5 = "UPDATE FileTypeAssociation SET _Revision=?, _WorkId=?, FileType=?, ContentType=?, Extension=?, \"Index\"=?, P"
           "rogID=?, _Dictionary=? WHERE _FileTypeAssociationID=? AND _Revision=? AND _WorkId=0;";
    v6 = StateRepository::Entity::FileTypeAssociation::BindAndExecuteForAddOrUpdate(a1, a2, v5);
    v4 = v6;
    if ( v6 >= 0 )
      v4 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x395,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-filetypeassociation.cpp",
        (const char *)(unsigned int)v6,
        v8);
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v10);
  }
  return v4;
}

```

## disassembly

```asm
0x180020058  mov     [rsp+arg_0], rbx
0x18002005d  push    rdi
0x18002005e  sub     rsp, 30h
0x180020062  mov     rdi, rcx
0x180020065  mov     rbx, rdx
0x180020068  mov     rcx, rdx; this
0x18002006b  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180020070  test    al, al
0x180020072  jz      short loc_180020094
0x180020074  mov     rcx, [rsp+38h]; this
0x180020079  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x180020080  mov     ebx, 8067000Bh
0x180020085  mov     edx, 38Dh; void *
0x18002008a  mov     r9d, ebx; char *
0x18002008d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180020092  jmp     short loc_1800200F3
0x180020094  xor     r8d, r8d
0x180020097  lea     rcx, [rsp+38h+arg_18]
0x18002009c  mov     rdx, rbx
0x18002009f  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x1800200a4  cmp     qword ptr [rbx+8], 0
0x1800200a9  lea     rax, aUpdateFiletype; "UPDATE FileTypeAssociation SET _Revisio"...
0x1800200b0  lea     r8, aUpdateFiletype_0; "UPDATE FileTypeAssociation SET _Revisio"...
0x1800200b7  mov     rdx, rbx
0x1800200ba  cmovz   r8, rax
0x1800200be  mov     rcx, rdi
0x1800200c1  call    ?BindAndExecuteForAddOrUpdate@FileTypeAssociation@Entity@StateRepository@@AEAAJAEAVDatabase@3@PEBD_NW4ExecutionFlags@3@@Z; StateRepository::Entity::FileTypeAssociation::BindAndExecuteForAddOrUpdate(StateRepository::Database &,char const *,bool,StateRepository::ExecutionFlags)
0x1800200c6  mov     ebx, eax
0x1800200c8  test    eax, eax
0x1800200ca  jns     short loc_1800200E7
0x1800200cc  mov     rcx, [rsp+38h]; this
0x1800200d1  lea     r8, aOnecoreBaseApp_19; "onecore\\base\\appmodel\\staterepositor"...
0x1800200d8  mov     r9d, eax; char *
0x1800200db  mov     edx, 395h; void *
0x1800200e0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800200e5  jmp     short loc_1800200E9
0x1800200e7  xor     ebx, ebx
0x1800200e9  lea     rcx, [rsp+38h+arg_18]; this
0x1800200ee  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x1800200f3  mov     eax, ebx
0x1800200f5  mov     rbx, [rsp+38h+arg_0]
0x1800200fa  add     rsp, 30h
0x1800200fe  pop     rdi
0x1800200ff  retn
```
