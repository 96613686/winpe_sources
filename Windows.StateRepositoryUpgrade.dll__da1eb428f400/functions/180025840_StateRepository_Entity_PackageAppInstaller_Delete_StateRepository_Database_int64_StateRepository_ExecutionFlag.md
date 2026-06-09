# StateRepository::Entity::PackageAppInstaller::Delete(StateRepository::Database &,__int64,StateRepository::ExecutionFlags)

- ea: `0x180025840`
- end: `0x1800258ce`
- name: `?Delete@PackageAppInstaller@Entity@StateRepository@@SAJAEAVDatabase@3@_JW4ExecutionFlags@3@@Z`
- size: `142`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x180013c40`

## callees

- `0x18000a3c0`
- `0x180018f78`
- `0x18001b0f0`
- `0x18001b3bc`
- `0x180025840`
- `0x180029de4`

## string_xrefs

- `0x18002585e`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageappinstaller.cpp`
- `0x18002589f`: `onecore\base\appmodel\staterepository\dataaccesslayer\entity-packageappinstaller.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Entity::PackageAppInstaller::Delete(
        StateRepository::StatementExecution *a1,
        const char *a2)
{
  unsigned int v4; // ebx
  struct StateRepository::Database *v5; // rdx
  const char *v6; // r8
  int v7; // eax
  int v9; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  char v11; // [rsp+48h] [rbp+20h] BYREF

  if ( StateRepository::Database::IsInAutoCommitMode(a1) )
  {
    v4 = -2140733429;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BC,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageappinstaller.cpp",
      (const char *)0x8067000BLL,
      v9);
  }
  else
  {
    StateRepository::DatabaseTriggers::Disable(&v11, a1, 0);
    v7 = StateRepository::StatementExecution::PrepareAndBindAndDelete(a1, v5, v6, a2);
    v4 = v7;
    if ( v7 >= 0 )
      v4 = 0;
    else
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1C2,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\entity-packageappinstaller.cpp",
        (const char *)(unsigned int)v7,
        v9);
    StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit((StateRepository::AutoEnableTriggersScopeExit *)&v11);
  }
  return v4;
}

```

## disassembly

```asm
0x180025840  mov     [rsp+arg_0], rbx
0x180025845  push    rdi; int
0x180025846  sub     rsp, 20h
0x18002584a  mov     rdi, rdx
0x18002584d  mov     rbx, rcx
0x180025850  call    ?IsInAutoCommitMode@Database@StateRepository@@QEAA_NXZ; StateRepository::Database::IsInAutoCommitMode(void)
0x180025855  test    al, al
0x180025857  jz      short loc_180025879
0x180025859  mov     rcx, [rsp+28h]; this
0x18002585e  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x180025865  mov     ebx, 8067000Bh
0x18002586a  mov     edx, 1BCh; void *
0x18002586f  mov     r9d, ebx; char *
0x180025872  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180025877  jmp     short loc_1800258C1
0x180025879  xor     r8d, r8d
0x18002587c  lea     rcx, [rsp+28h+arg_18]
0x180025881  mov     rdx, rbx
0x180025884  call    ?Disable@DatabaseTriggers@StateRepository@@SA?AVAutoEnableTriggersScopeExit@2@PEAVDatabase@2@W4ExecutionFlags@2@@Z; StateRepository::DatabaseTriggers::Disable(StateRepository::Database *,StateRepository::ExecutionFlags)
0x180025889  mov     r9, rdi; char *
0x18002588c  mov     rcx, rbx; this
0x18002588f  call    ?PrepareAndBindAndDelete@StatementExecution@StateRepository@@YAJAEAVDatabase@2@PEBD1_J@Z; StateRepository::StatementExecution::PrepareAndBindAndDelete(StateRepository::Database &,char const *,char const *,__int64)
0x180025894  mov     ebx, eax
0x180025896  test    eax, eax
0x180025898  jns     short loc_1800258B5
0x18002589a  mov     rcx, [rsp+28h]; this
0x18002589f  lea     r8, aOnecoreBaseApp_5; "onecore\\base\\appmodel\\staterepositor"...
0x1800258a6  mov     r9d, eax; char *
0x1800258a9  mov     edx, 1C2h; void *
0x1800258ae  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800258b3  jmp     short loc_1800258B7
0x1800258b5  xor     ebx, ebx
0x1800258b7  lea     rcx, [rsp+28h+arg_18]; this
0x1800258bc  call    ??1AutoEnableTriggersScopeExit@StateRepository@@QEAA@XZ; StateRepository::AutoEnableTriggersScopeExit::~AutoEnableTriggersScopeExit(void)
0x1800258c1  mov     eax, ebx
0x1800258c3  mov     rbx, [rsp+28h+arg_0]
0x1800258c8  add     rsp, 20h
0x1800258cc  pop     rdi
0x1800258cd  retn
```
