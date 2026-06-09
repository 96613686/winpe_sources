# StateRepository::Entity::Application::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x18001cc98`
- end: `0x18001cd4f`
- name: `?ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint@Application@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `183`
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
- `0x18001cc98`

## string_xrefs

- `0x18001ccb3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application-custom.cpp`
- `0x18001cd25`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-application-custom.cpp`
- `0x18001cce1`: `UPDATE Application SET Flags=((Flags | 0x14) & ~0x1A0) WHERE Entrypoint='Windows.FullTrustApplication';`
- `0x18001cd03`: `UPDATE Application SET Flags=((Flags | 0x90) & ~0x124) WHERE Entrypoint='Windows.PartialTrustApplication';`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::Application::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(
        StateRepository::Database *a1)
{
  unsigned int v2; // ebx
  int v3; // eax
  __int64 v4; // rdx
  int v6; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v8; // [rsp+40h] [rbp+18h] BYREF

  if ( !StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    StateRepository::DatabaseTriggers::Disable(&v8, a1, 0);
    v3 = StateRepository::Database::Execute(
           a1,
           "UPDATE Application SET Flags=((Flags | 0x14) & ~0x1A0) WHERE Entrypoint='Windows.FullTrustApplication';",
           0,
           0);
    v2 = v3;
    if ( v3 >= 0 )
    {
      v3 = StateRepository::Database::Execute(
             a1,
             "UPDATE Application SET Flags=((Flags | 0x90) & ~0x124) WHERE Entrypoint='Windows.PartialTrustApplication';",
             0,
             0);
      v2 = v3;
      if ( v3 >= 0 )
      {
        v2 = 0;
        goto LABEL_9;
      }
      v4 = 2148;
    }
    else
    {
      v4 = 2142;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application-custom.cpp",
      (const char *)(unsigned int)v3,
      v6);
LABEL_9:
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v8);
    return v2;
  }
  v2 = -2140733429;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x857,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-application-custom.cpp",
    (const char *)0x8067000BLL,
    v6);
  return v2;
}

```

## disassembly

```asm
0x18001cc98  mov     [rsp+arg_0], rbx
0x18001cc9d  push    rdi; int
0x18001cc9e  sub     rsp, 20h
0x18001cca2  mov     rdi, rcx
0x18001cca5  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001ccaa  test    al, al
0x18001ccac  jz      short loc_18001CCCE
0x18001ccae  mov     rcx, [rsp+28h]; this
0x18001ccb3  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18001ccba  mov     ebx, 8067000Bh
0x18001ccbf  mov     edx, 857h; void *
0x18001ccc4  mov     r9d, ebx; char *
0x18001ccc7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cccc  jmp     short loc_18001CD42
0x18001ccce  xor     r8d, r8d
0x18001ccd1  lea     rcx, [rsp+28h+arg_10]
0x18001ccd6  mov     rdx, rdi
0x18001ccd9  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x18001ccde  xor     r9d, r9d; void *
0x18001cce1  lea     rdx, aUpdateApplicat_4; "UPDATE Application SET Flags=((Flags | "...
0x18001cce8  xor     r8d, r8d; int (*)(void *)
0x18001cceb  mov     rcx, rdi; this
0x18001ccee  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18001ccf3  mov     ebx, eax
0x18001ccf5  test    eax, eax
0x18001ccf7  jns     short loc_18001CD00
0x18001ccf9  mov     edx, 85Eh
0x18001ccfe  jmp     short loc_18001CD20
0x18001cd00  xor     r9d, r9d; void *
0x18001cd03  lea     rdx, aUpdateApplicat_2; "UPDATE Application SET Flags=((Flags | "...
0x18001cd0a  xor     r8d, r8d; int (*)(void *)
0x18001cd0d  mov     rcx, rdi; this
0x18001cd10  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18001cd15  mov     ebx, eax
0x18001cd17  test    eax, eax
0x18001cd19  jns     short loc_18001CD36
0x18001cd1b  mov     edx, 864h; void *
0x18001cd20  mov     rcx, [rsp+28h]; this
0x18001cd25  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18001cd2c  mov     r9d, eax; char *
0x18001cd2f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001cd34  jmp     short loc_18001CD38
0x18001cd36  xor     ebx, ebx
0x18001cd38  lea     rcx, [rsp+28h+arg_10]; this
0x18001cd3d  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x18001cd42  mov     eax, ebx
0x18001cd44  mov     rbx, [rsp+28h+arg_0]
0x18001cd49  add     rsp, 20h
0x18001cd4d  pop     rdi
0x18001cd4e  retn
```
