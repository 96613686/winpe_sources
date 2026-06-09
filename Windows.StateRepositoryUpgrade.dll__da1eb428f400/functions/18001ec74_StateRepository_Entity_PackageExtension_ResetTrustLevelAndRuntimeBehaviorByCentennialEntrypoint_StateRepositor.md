# StateRepository::Entity::PackageExtension::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x18001ec74`
- end: `0x18001ed2b`
- name: `?ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint@PackageExtension@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `183`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update, broker_com_uri`

## callers

- `0x18000d734`

## callees

- `0x18000a3c0`
- `0x180018c40`
- `0x180018f78`
- `0x18001b0f0`
- `0x18001b3bc`
- `0x18001ec74`

## string_xrefs

- `0x18001ec8f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension-custom.cpp`
- `0x18001ed01`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension-custom.cpp`
- `0x18001ecbd`: `UPDATE PackageExtension SET Flags=((Flags | 0x14) & ~0x1A0) WHERE Entrypoint='Windows.FullTrustApplication';`
- `0x18001ecdf`: `UPDATE PackageExtension SET Flags=((Flags | 0x90) & ~0x124) WHERE Entrypoint='Windows.PartialTrustApplication';`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::PackageExtension::ResetTrustLevelAndRuntimeBehaviorByCentennialEntrypoint(
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
           "UPDATE PackageExtension SET Flags=((Flags | 0x14) & ~0x1A0) WHERE Entrypoint='Windows.FullTrustApplication';",
           0,
           0);
    v2 = v3;
    if ( v3 >= 0 )
    {
      v3 = StateRepository::Database::Execute(
             a1,
             "UPDATE PackageExtension SET Flags=((Flags | 0x90) & ~0x124) WHERE Entrypoint='Windows.PartialTrustApplication';",
             0,
             0);
      v2 = v3;
      if ( v3 >= 0 )
      {
        v2 = 0;
        goto LABEL_9;
      }
      v4 = 588;
    }
    else
    {
      v4 = 582;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v4,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension-custom.cpp",
      (const char *)(unsigned int)v3,
      v6);
LABEL_9:
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v8);
    return v2;
  }
  v2 = -2140733429;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x23F,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension-custom.cpp",
    (const char *)0x8067000BLL,
    v6);
  return v2;
}

```

## disassembly

```asm
0x18001ec74  mov     [rsp+arg_0], rbx
0x18001ec79  push    rdi; int
0x18001ec7a  sub     rsp, 20h
0x18001ec7e  mov     rdi, rcx
0x18001ec81  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001ec86  test    al, al
0x18001ec88  jz      short loc_18001ECAA
0x18001ec8a  mov     rcx, [rsp+28h]; this
0x18001ec8f  lea     r8, aOnecoreBaseApp_60; "onecore\\base\\appmodel\\staterepositor"...
0x18001ec96  mov     ebx, 8067000Bh
0x18001ec9b  mov     edx, 23Fh; void *
0x18001eca0  mov     r9d, ebx; char *
0x18001eca3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001eca8  jmp     short loc_18001ED1E
0x18001ecaa  xor     r8d, r8d
0x18001ecad  lea     rcx, [rsp+28h+arg_10]
0x18001ecb2  mov     rdx, rdi
0x18001ecb5  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x18001ecba  xor     r9d, r9d; void *
0x18001ecbd  lea     rdx, aUpdatePackagee_0; "UPDATE PackageExtension SET Flags=((Fla"...
0x18001ecc4  xor     r8d, r8d; int (*)(void *)
0x18001ecc7  mov     rcx, rdi; this
0x18001ecca  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18001eccf  mov     ebx, eax
0x18001ecd1  test    eax, eax
0x18001ecd3  jns     short loc_18001ECDC
0x18001ecd5  mov     edx, 246h
0x18001ecda  jmp     short loc_18001ECFC
0x18001ecdc  xor     r9d, r9d; void *
0x18001ecdf  lea     rdx, aUpdatePackagee_1; "UPDATE PackageExtension SET Flags=((Fla"...
0x18001ece6  xor     r8d, r8d; int (*)(void *)
0x18001ece9  mov     rcx, rdi; this
0x18001ecec  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18001ecf1  mov     ebx, eax
0x18001ecf3  test    eax, eax
0x18001ecf5  jns     short loc_18001ED12
0x18001ecf7  mov     edx, 24Ch; void *
0x18001ecfc  mov     rcx, [rsp+28h]; this
0x18001ed01  lea     r8, aOnecoreBaseApp_60; "onecore\\base\\appmodel\\staterepositor"...
0x18001ed08  mov     r9d, eax; char *
0x18001ed0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ed10  jmp     short loc_18001ED14
0x18001ed12  xor     ebx, ebx
0x18001ed14  lea     rcx, [rsp+28h+arg_10]; this
0x18001ed19  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x18001ed1e  mov     eax, ebx
0x18001ed20  mov     rbx, [rsp+28h+arg_0]
0x18001ed25  add     rsp, 20h
0x18001ed29  pop     rdi
0x18001ed2a  retn
```
