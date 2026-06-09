# StateRepository::Entity::PackageExtension::ResetActivationByCentennialEntrypoint(StateRepository::Database &,StateRepository::ExecutionFlags)

- ea: `0x18001ebe0`
- end: `0x18001ec6c`
- name: `?ResetActivationByCentennialEntrypoint@PackageExtension@Entity@StateRepository@@SAJAEAVDatabase@3@W4ExecutionFlags@3@@Z`
- size: `140`
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
- `0x18001ebe0`

## string_xrefs

- `0x18001ebf7`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension-custom.cpp`
- `0x18001ec42`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageextension-custom.cpp`
- `0x18001ec25`: `UPDATE PackageExtension SET Activation=0 WHERE Entrypoint IN ('Windows.FullTrustApplication', 'Windows.PartialTrustApplication');`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::PackageExtension::ResetActivationByCentennialEntrypoint(
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
      (void *)0x256,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension-custom.cpp",
      (const char *)0x8067000BLL,
      v5);
  }
  else
  {
    StateRepository::DatabaseTriggers::Disable(&v7, a1, 0);
    v3 = StateRepository::Database::Execute(
           a1,
           "UPDATE PackageExtension SET Activation=0 WHERE Entrypoint IN ('Windows.FullTrustApplication', 'Windows.Partia"
           "lTrustApplication');",
           0,
           0);
    v2 = v3;
    if ( v3 >= 0 )
      v2 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x25B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageextension-custom.cpp",
        (const char *)(unsigned int)v3,
        v5);
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v7);
  }
  return v2;
}

```

## disassembly

```asm
0x18001ebe0  push    rbx; int
0x18001ebe2  sub     rsp, 20h
0x18001ebe6  mov     rbx, rcx
0x18001ebe9  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x18001ebee  test    al, al
0x18001ebf0  jz      short loc_18001EC12
0x18001ebf2  mov     rcx, [rsp+28h]; this
0x18001ebf7  lea     r8, aOnecoreBaseApp_60; "onecore\\base\\appmodel\\staterepositor"...
0x18001ebfe  mov     ebx, 8067000Bh
0x18001ec03  mov     edx, 256h; void *
0x18001ec08  mov     r9d, ebx; char *
0x18001ec0b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ec10  jmp     short loc_18001EC64
0x18001ec12  xor     r8d, r8d
0x18001ec15  lea     rcx, [rsp+28h+arg_10]
0x18001ec1a  mov     rdx, rbx
0x18001ec1d  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x18001ec22  xor     r9d, r9d; void *
0x18001ec25  lea     rdx, aUpdatePackagee_2; "UPDATE PackageExtension SET Activation="...
0x18001ec2c  xor     r8d, r8d; int (*)(void *)
0x18001ec2f  mov     rcx, rbx; this
0x18001ec32  call    ?Execute@Database@StateRepository@@QEAAJPEBDP6AJPEAX@Z1@Z; StateRepository::Database::Execute(char const *,long (*)(void *),void *)
0x18001ec37  mov     ebx, eax
0x18001ec39  test    eax, eax
0x18001ec3b  jns     short loc_18001EC58
0x18001ec3d  mov     rcx, [rsp+28h]; this
0x18001ec42  lea     r8, aOnecoreBaseApp_60; "onecore\\base\\appmodel\\staterepositor"...
0x18001ec49  mov     r9d, eax; char *
0x18001ec4c  mov     edx, 25Bh; void *
0x18001ec51  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ec56  jmp     short loc_18001EC5A
0x18001ec58  xor     ebx, ebx
0x18001ec5a  lea     rcx, [rsp+28h+arg_10]; this
0x18001ec5f  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x18001ec64  mov     eax, ebx
0x18001ec66  add     rsp, 20h
0x18001ec6a  pop     rbx
0x18001ec6b  retn
```
