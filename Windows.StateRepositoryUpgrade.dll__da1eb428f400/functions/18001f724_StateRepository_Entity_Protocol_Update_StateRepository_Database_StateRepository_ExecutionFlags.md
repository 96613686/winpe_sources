# StateRepository::Entity::Protocol::Update(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x18001f724`
- end: `0x18001f7cc`
- name: `?Update@Protocol@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `168`
- prototype: `int __high(struct StateRepository::Database *, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000eae4`

## callees

- `0x18000a3c0`
- `0x180018f78`
- `0x18001b0f0`
- `0x18001b3bc`
- `0x18001f1c8`
- `0x18001f724`

## string_xrefs

- `0x18001f745`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`
- `0x18001f79d`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-protocol.cpp`
- `0x18001f775`: `UPDATE Protocol SET _Revision=?, _WorkId=?, ProtocolName=?, ReturnResults=?, Extension=?, "Index"=?, ProgID=?, _Dictionary=? WHERE _ProtocolID=? AND _Revision=? AND _WorkId=0;`
- `0x18001f77c`: `UPDATE Protocol SET _Revision=?, _WorkId=?, ProtocolName=?, ReturnResults=?, Extension=?, "Index"=?, ProgID=?, _Dictionary=? WHERE _ProtocolID=? AND _Revision=? AND (_WorkId=0 OR _WorkId=?);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Protocol::Update(__int64 a1, StateRepository::Database *a2)
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
      (void *)0x33B,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
      (const char *)0x8067000BLL,
      v9);
  }
  else
  {
    StateRepository::DatabaseTriggers::Disable(&v11, a2, 0);
    v6 = "UPDATE Protocol SET _Revision=?, _WorkId=?, ProtocolName=?, ReturnResults=?, Extension=?, \"Index\"=?, ProgID=?"
         ", _Dictionary=? WHERE _ProtocolID=? AND _Revision=? AND (_WorkId=0 OR _WorkId=?);";
    if ( !*((_QWORD *)a2 + 1) )
      v6 = "UPDATE Protocol SET _Revision=?, _WorkId=?, ProtocolName=?, ReturnResults=?, Extension=?, \"Index\"=?, ProgID"
           "=?, _Dictionary=? WHERE _ProtocolID=? AND _Revision=? AND _WorkId=0;";
    v7 = StateRepository::Entity::Protocol::BindAndExecuteForAddOrUpdate(a1, a2, v6, v5);
    v4 = v7;
    if ( v7 >= 0 )
      v4 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x343,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-protocol.cpp",
        (const char *)(unsigned int)v7,
        v9);
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v11);
  }
  return v4;
}

```

## disassembly

```asm
0x18001f724  mov     [rsp+arg_0], rbx
0x18001f729  push    rdi
0x18001f72a  sub     rsp, 30h
0x18001f72e  mov     rdi, rcx
0x18001f731  mov     rbx, rdx
0x18001f734  mov     rcx, rdx; this
0x18001f737  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001f73c  test    al, al
0x18001f73e  jz      short loc_18001F760
0x18001f740  mov     rcx, [rsp+38h]; this
0x18001f745  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18001f74c  mov     ebx, 8067000Bh
0x18001f751  mov     edx, 33Bh; void *
0x18001f756  mov     r9d, ebx; char *
0x18001f759  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f75e  jmp     short loc_18001F7BF
0x18001f760  xor     r8d, r8d
0x18001f763  lea     rcx, [rsp+38h+arg_18]
0x18001f768  mov     rdx, rbx
0x18001f76b  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x18001f770  cmp     qword ptr [rbx+8], 0
0x18001f775  lea     rax, aUpdateProtocol; "UPDATE Protocol SET _Revision=?, _WorkI"...
0x18001f77c  lea     r8, aUpdateProtocol_0; "UPDATE Protocol SET _Revision=?, _WorkI"...
0x18001f783  mov     rdx, rbx
0x18001f786  cmovz   r8, rax
0x18001f78a  mov     rcx, rdi
0x18001f78d  call    ?BindAndExecuteForAddOrUpdate@Protocol@Entity@StateRepository@@AEAAJAEAVDatabase@3@PEBD_NW4ExecutionFlags@3@@Z; StateRepository::Entity::Protocol::BindAndExecuteForAddOrUpdate(StateRepository::Database &,char const *,bool,StateRepository::ExecutionFlags)
0x18001f792  mov     ebx, eax
0x18001f794  test    eax, eax
0x18001f796  jns     short loc_18001F7B3
0x18001f798  mov     rcx, [rsp+38h]; this
0x18001f79d  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\staterepositor"...
0x18001f7a4  mov     r9d, eax; char *
0x18001f7a7  mov     edx, 343h; void *
0x18001f7ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f7b1  jmp     short loc_18001F7B5
0x18001f7b3  xor     ebx, ebx
0x18001f7b5  lea     rcx, [rsp+38h+arg_18]; this
0x18001f7ba  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x18001f7bf  mov     eax, ebx
0x18001f7c1  mov     rbx, [rsp+38h+arg_0]
0x18001f7c6  add     rsp, 30h
0x18001f7ca  pop     rdi
0x18001f7cb  retn
```
