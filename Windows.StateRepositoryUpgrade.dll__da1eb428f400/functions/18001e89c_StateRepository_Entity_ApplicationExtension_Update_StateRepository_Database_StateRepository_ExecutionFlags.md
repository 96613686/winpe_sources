# StateRepository::Entity::ApplicationExtension::Update(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x18001e89c`
- end: `0x18001e94f`
- name: `?Update@ApplicationExtension@Entity@StateRepository@@QEAAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `179`
- prototype: `int __high(struct StateRepository::Database *, enum StateRepository::ExecutionFlags)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x180014504`

## callees

- `0x18000a3c0`
- `0x180018f78`
- `0x18001b0f0`
- `0x18001b3bc`
- `0x18001e0c8`
- `0x18001e89c`

## string_xrefs

- `0x18001e8bd`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension.cpp`
- `0x18001e920`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension.cpp`
- `0x18001e8ed`: `UPDATE ApplicationExtension SET _Revision=?, _WorkId=?, Application=?, "Index"=?, Category=?, Activation=?, HostId=?, Executable=?, Entrypoint=?, RuntimeType=?, StartPage=?, ResourceGroup=?, Flags=?, Subsystem=?, Parameters=?, CurrentDirectoryPath=?, Id=?, _LocalizedDictionary=?, _Dictionary=? WHERE _ApplicationExtensionID=? AND _Revision=? AND _WorkId=0;`
- `0x18001e8f4`: `UPDATE ApplicationExtension SET _Revision=?, _WorkId=?, Application=?, "Index"=?, Category=?, Activation=?, HostId=?, Executable=?, Entrypoint=?, RuntimeType=?, StartPage=?, ResourceGroup=?, Flags=?, Subsystem=?, Parameters=?, CurrentDirectoryPath=?, Id=?, _LocalizedDictionary=?, _Dictionary=? WHERE _ApplicationExtensionID=? AND _Revision=? AND (_WorkId=0 OR _WorkId=?);`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::ApplicationExtension::Update(__int64 a1, StateRepository::Database *a2)
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
      (void *)0x3ED,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension.cpp",
      (const char *)0x8067000BLL,
      v8);
  }
  else
  {
    StateRepository::DatabaseTriggers::Disable(&v10, a2, 0);
    v5 = "UPDATE ApplicationExtension SET _Revision=?, _WorkId=?, Application=?, \"Index\"=?, Category=?, Activation=?, H"
         "ostId=?, Executable=?, Entrypoint=?, RuntimeType=?, StartPage=?, ResourceGroup=?, Flags=?, Subsystem=?, Paramet"
         "ers=?, CurrentDirectoryPath=?, Id=?, _LocalizedDictionary=?, _Dictionary=? WHERE _ApplicationExtensionID=? AND "
         "_Revision=? AND (_WorkId=0 OR _WorkId=?);";
    if ( !*((_QWORD *)a2 + 1) )
      v5 = "UPDATE ApplicationExtension SET _Revision=?, _WorkId=?, Application=?, \"Index\"=?, Category=?, Activation=?,"
           " HostId=?, Executable=?, Entrypoint=?, RuntimeType=?, StartPage=?, ResourceGroup=?, Flags=?, Subsystem=?, Par"
           "ameters=?, CurrentDirectoryPath=?, Id=?, _LocalizedDictionary=?, _Dictionary=? WHERE _ApplicationExtensionID="
           "? AND _Revision=? AND _WorkId=0;";
    v6 = StateRepository::Entity::ApplicationExtension::BindAndExecuteForAddOrUpdate(a1, a2, v5, 0);
    v4 = v6;
    if ( v6 >= 0 )
      v4 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x3F5,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension.cpp",
        (const char *)(unsigned int)v6,
        0);
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v10);
  }
  return v4;
}

```

## disassembly

```asm
0x18001e89c  mov     [rsp+arg_0], rbx
0x18001e8a1  push    rdi
0x18001e8a2  sub     rsp, 30h
0x18001e8a6  mov     rdi, rcx
0x18001e8a9  mov     rbx, rdx
0x18001e8ac  mov     rcx, rdx; this
0x18001e8af  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001e8b4  test    al, al
0x18001e8b6  jz      short loc_18001E8D8
0x18001e8b8  mov     rcx, [rsp+38h]; this
0x18001e8bd  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x18001e8c4  mov     ebx, 8067000Bh
0x18001e8c9  mov     edx, 3EDh; void *
0x18001e8ce  mov     r9d, ebx; char *
0x18001e8d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e8d6  jmp     short loc_18001E942
0x18001e8d8  xor     r8d, r8d
0x18001e8db  lea     rcx, [rsp+38h+arg_18]
0x18001e8e0  mov     rdx, rbx
0x18001e8e3  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x18001e8e8  cmp     qword ptr [rbx+8], 0
0x18001e8ed  lea     rax, aUpdateApplicat_6; "UPDATE ApplicationExtension SET _Revisi"...
0x18001e8f4  lea     r8, aUpdateApplicat; "UPDATE ApplicationExtension SET _Revisi"...
0x18001e8fb  mov     [rsp+38h+var_18], 0; int
0x18001e903  cmovz   r8, rax
0x18001e907  mov     rdx, rbx
0x18001e90a  xor     r9d, r9d
0x18001e90d  mov     rcx, rdi
0x18001e910  call    ?BindAndExecuteForAddOrUpdate@ApplicationExtension@Entity@StateRepository@@AEAAJAEAVDatabase@3@PEBD_NW4ExecutionFlags@3@@Z; StateRepository::Entity::ApplicationExtension::BindAndExecuteForAddOrUpdate(StateRepository::Database &,char const *,bool,StateRepository::ExecutionFlags)
0x18001e915  mov     ebx, eax
0x18001e917  test    eax, eax
0x18001e919  jns     short loc_18001E936
0x18001e91b  mov     rcx, [rsp+38h]; this
0x18001e920  lea     r8, aOnecoreBaseApp_30; "onecore\\base\\appmodel\\staterepositor"...
0x18001e927  mov     r9d, eax; char *
0x18001e92a  mov     edx, 3F5h; void *
0x18001e92f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001e934  jmp     short loc_18001E938
0x18001e936  xor     ebx, ebx
0x18001e938  lea     rcx, [rsp+38h+arg_18]; this
0x18001e93d  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x18001e942  mov     eax, ebx
0x18001e944  mov     rbx, [rsp+38h+arg_0]
0x18001e949  add     rsp, 30h
0x18001e94d  pop     rdi
0x18001e94e  retn
```
