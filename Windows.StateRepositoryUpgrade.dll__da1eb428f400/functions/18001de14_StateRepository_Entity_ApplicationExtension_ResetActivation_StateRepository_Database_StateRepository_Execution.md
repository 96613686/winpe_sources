# StateRepository::Entity::ApplicationExtension::ResetActivation(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x18001de14`
- end: `0x18001dea0`
- name: `?ResetActivation@ApplicationExtension@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d54c`

## callees

- `0x18000a3c0`
- `0x180018c40`
- `0x180018f78`
- `0x18001b0f0`
- `0x18001b3bc`
- `0x18001de14`

## string_xrefs

- `0x18001de2b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`
- `0x18001de76`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`
- `0x18001de59`: `UPDATE ApplicationExtension SET Activation=0;`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::ApplicationExtension::ResetActivation(StateRepository::Database *a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v7; // [rsp+40h] [rbp+18h] BYREF

  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v2 = -2140733429;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x459,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
      (const char *)0x8067000BLL,
      v5);
  }
  else
  {
    StateRepository::DatabaseTriggers::Disable(&v7, a1, 0);
    v3 = StateRepository::Database::Execute(a1, "UPDATE ApplicationExtension SET Activation=0;", 0, 0);
    v2 = v3;
    if ( v3 >= 0 )
      v2 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x45E,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
        (const char *)(unsigned int)v3,
        v5);
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v7);
  }
  return v2;
}

```

## disassembly

```asm
0x18001de14  push    rbx; int
0x18001de16  sub     rsp, 20h
0x18001de1a  mov     rbx, rcx
0x18001de1d  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001de22  test    al, al
0x18001de24  jz      short loc_18001DE46
0x18001de26  mov     rcx, [rsp+28h]; this
0x18001de2b  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001de32  mov     ebx, 8067000Bh
0x18001de37  mov     edx, 459h; void *
0x18001de3c  mov     r9d, ebx; char *
0x18001de3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de44  jmp     short loc_18001DE98
0x18001de46  xor     r8d, r8d
0x18001de49  lea     rcx, [rsp+28h+arg_10]
0x18001de4e  mov     rdx, rbx
0x18001de51  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x18001de56  xor     r9d, r9d; void *
0x18001de59  lea     rdx, aUpdateApplicat_1; "UPDATE ApplicationExtension SET Activat"...
0x18001de60  xor     r8d, r8d; int (*)(void *)
0x18001de63  mov     rcx, rbx; this
0x18001de66  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18001de6b  mov     ebx, eax
0x18001de6d  test    eax, eax
0x18001de6f  jns     short loc_18001DE8C
0x18001de71  mov     rcx, [rsp+28h]; this
0x18001de76  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001de7d  mov     r9d, eax; char *
0x18001de80  mov     edx, 45Eh; void *
0x18001de85  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001de8a  jmp     short loc_18001DE8E
0x18001de8c  xor     ebx, ebx
0x18001de8e  lea     rcx, [rsp+28h+arg_10]; this
0x18001de93  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x18001de98  mov     eax, ebx
0x18001de9a  add     rsp, 20h
0x18001de9e  pop     rbx
0x18001de9f  retn
```
