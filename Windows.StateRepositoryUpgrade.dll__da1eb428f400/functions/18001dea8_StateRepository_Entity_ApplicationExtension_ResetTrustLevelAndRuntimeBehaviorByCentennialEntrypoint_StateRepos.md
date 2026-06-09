# StateRepository::Entity::ApplicationExtension::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x18001dea8`
- end: `0x18001df5f`
- name: `?ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint@ApplicationExtension@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `183`
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
- `0x18001dea8`

## string_xrefs

- `0x18001dec3`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`
- `0x18001df35`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-applicationextension-custom.cpp`
- `0x18001def1`: `UPDATE ApplicationExtension SET Flags=((Flags | 0x14) & ~0x1A0) WHERE Entrypoint='Windows.FullTrustApplication';`
- `0x18001df13`: `UPDATE ApplicationExtension SET Flags=((Flags | 0x90) & ~0x124) WHERE Entrypoint='Windows.PartialTrustApplication';`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::ApplicationExtension::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(
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
           "UPDATE ApplicationExtension SET Flags=((Flags | 0x14) & ~0x1A0) WHERE Entrypoint='Windows.FullTrustApplication';",
           0,
           0);
    v2 = v3;
    if ( v3 >= 0 )
    {
      v3 = StateRepository::Database::Execute(
             a1,
             "UPDATE ApplicationExtension SET Flags=((Flags | 0x90) & ~0x124) WHERE Entrypoint='Windows.PartialTrustApplication';",
             0,
             0);
      v2 = v3;
      if ( v3 >= 0 )
      {
        v2 = 0;
        goto LABEL_9;
      }
      v4 = 1103;
    }
    else
    {
      v4 = 1097;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
      (const char *)(unsigned int)v3,
      v6);
LABEL_9:
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v8);
    return v2;
  }
  v2 = -2140733429;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x442,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-applicationextension-custom.cpp",
    (const char *)0x8067000BLL,
    v6);
  return v2;
}

```

## disassembly

```asm
0x18001dea8  mov     [rsp+arg_0], rbx
0x18001dead  push    rdi; int
0x18001deae  sub     rsp, 20h
0x18001deb2  mov     rdi, rcx
0x18001deb5  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001deba  test    al, al
0x18001debc  jz      short loc_18001DEDE
0x18001debe  mov     rcx, [rsp+28h]; this
0x18001dec3  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001deca  mov     ebx, 8067000Bh
0x18001decf  mov     edx, 442h; void *
0x18001ded4  mov     r9d, ebx; char *
0x18001ded7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001dedc  jmp     short loc_18001DF52
0x18001dede  xor     r8d, r8d
0x18001dee1  lea     rcx, [rsp+28h+arg_10]
0x18001dee6  mov     rdx, rdi
0x18001dee9  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x18001deee  xor     r9d, r9d; void *
0x18001def1  lea     rdx, aUpdateApplicat_5; "UPDATE ApplicationExtension SET Flags=("...
0x18001def8  xor     r8d, r8d; int (*)(void *)
0x18001defb  mov     rcx, rdi; this
0x18001defe  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18001df03  mov     ebx, eax
0x18001df05  test    eax, eax
0x18001df07  jns     short loc_18001DF10
0x18001df09  mov     edx, 449h
0x18001df0e  jmp     short loc_18001DF30
0x18001df10  xor     r9d, r9d; void *
0x18001df13  lea     rdx, aUpdateApplicat_0; "UPDATE ApplicationExtension SET Flags=("...
0x18001df1a  xor     r8d, r8d; int (*)(void *)
0x18001df1d  mov     rcx, rdi; this
0x18001df20  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18001df25  mov     ebx, eax
0x18001df27  test    eax, eax
0x18001df29  jns     short loc_18001DF46
0x18001df2b  mov     edx, 44Fh; void *
0x18001df30  mov     rcx, [rsp+28h]; this
0x18001df35  lea     r8, aOnecoreBaseApp_40; "onecore\\base\\appmodel\\staterepositor"...
0x18001df3c  mov     r9d, eax; char *
0x18001df3f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001df44  jmp     short loc_18001DF48
0x18001df46  xor     ebx, ebx
0x18001df48  lea     rcx, [rsp+28h+arg_10]; this
0x18001df4d  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x18001df52  mov     eax, ebx
0x18001df54  mov     rbx, [rsp+28h+arg_0]
0x18001df59  add     rsp, 20h
0x18001df5d  pop     rdi
0x18001df5e  retn
```
