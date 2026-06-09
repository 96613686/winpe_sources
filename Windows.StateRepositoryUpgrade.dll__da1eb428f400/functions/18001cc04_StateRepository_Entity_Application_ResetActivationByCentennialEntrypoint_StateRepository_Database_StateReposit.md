# StateRepository::Entity::Application::ResetActivationByCentennialEntrypoint(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x18001cc04`
- end: `0x18001cc90`
- name: `?ResetActivationByCentennialEntrypoint@Application@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `140`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000d31c`

## callees

- `0x18000a3c0`
- `0x180018c40`
- `0x180018f78`
- `0x18001b0f0`
- `0x18001b3bc`
- `0x18001cc04`

## string_xrefs

- `0x18001cc1b`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application-custom.cpp`
- `0x18001cc66`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application-custom.cpp`
- `0x18001cc49`: `UPDATE Application SET Activation=0 WHERE Entrypoint IN ('Windows.FullTrustApplication', 'Windows.PartialTrustApplication');`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Application::ResetActivationByCentennialEntrypoint(
        StateRepository::Database *a1)
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
      (void *)0x86E,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application-custom.cpp",
      (const char *)0x8067000BLL,
      v5);
  }
  else
  {
    StateRepository::DatabaseTriggers::Disable(&v7, a1, 0);
    v3 = StateRepository::Database::Execute(
           a1,
           "UPDATE Application SET Activation=0 WHERE Entrypoint IN ('Windows.FullTrustApplication', 'Windows.PartialTrustApplication');",
           0,
           0);
    v2 = v3;
    if ( v3 >= 0 )
      v2 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x873,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application-custom.cpp",
        (const char *)(unsigned int)v3,
        v5);
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v7);
  }
  return v2;
}

```

## disassembly

```asm
0x18001cc04  push    rbx; int
0x18001cc06  sub     rsp, 20h
0x18001cc0a  mov     rbx, rcx
0x18001cc0d  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001cc12  test    al, al
0x18001cc14  jz      short loc_18001CC36
0x18001cc16  mov     rcx, [rsp+28h]; this
0x18001cc1b  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18001cc22  mov     ebx, 8067000Bh
0x18001cc27  mov     edx, 86Eh; void *
0x18001cc2c  mov     r9d, ebx; char *
0x18001cc2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc34  jmp     short loc_18001CC88
0x18001cc36  xor     r8d, r8d
0x18001cc39  lea     rcx, [rsp+28h+arg_10]
0x18001cc3e  mov     rdx, rbx
0x18001cc41  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x18001cc46  xor     r9d, r9d; void *
0x18001cc49  lea     rdx, aUpdateApplicat_8; "UPDATE Application SET Activation=0 WHE"...
0x18001cc50  xor     r8d, r8d; int (*)(void *)
0x18001cc53  mov     rcx, rbx; this
0x18001cc56  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18001cc5b  mov     ebx, eax
0x18001cc5d  test    eax, eax
0x18001cc5f  jns     short loc_18001CC7C
0x18001cc61  mov     rcx, [rsp+28h]; this
0x18001cc66  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18001cc6d  mov     r9d, eax; char *
0x18001cc70  mov     edx, 873h; void *
0x18001cc75  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cc7a  jmp     short loc_18001CC7E
0x18001cc7c  xor     ebx, ebx
0x18001cc7e  lea     rcx, [rsp+28h+arg_10]; this
0x18001cc83  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x18001cc88  mov     eax, ebx
0x18001cc8a  add     rsp, 20h
0x18001cc8e  pop     rbx
0x18001cc8f  retn
```
