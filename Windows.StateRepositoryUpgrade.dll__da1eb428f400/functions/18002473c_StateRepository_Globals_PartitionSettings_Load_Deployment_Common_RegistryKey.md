# StateRepository::Globals::PartitionSettings::Load_Deployment(Common::RegistryKey &)

- ea: `0x18002473c`
- end: `0x18002486a`
- name: `?Load_Deployment@PartitionSettings@Globals@StateRepository@@CAJAEAVRegistryKey@Common@@@Z`
- size: `302`
- prototype: `__int64 __fastcall(struct Common::RegistryKey *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024114`

## callees

- `0x18000a3c0`
- `0x18000f460`
- `0x180023080`
- `0x180023ccc`
- `0x18002473c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024756`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180024756`

## string_xrefs

- `0x1800247b6`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180024802`: `DeploymentDatabaseCacheSize`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::PartitionSettings::Load_Deployment(struct Common::RegistryKey *a1)
{
  int v2; // ebx
  int v4; // [rsp+20h] [rbp-68h]
  unsigned __int16 **v5; // [rsp+60h] [rbp-28h] BYREF
  __int64 v6; // [rsp+68h] [rbp-20h] BYREF
  char v7; // [rsp+70h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  RTL_SRWLOCK *v9; // [rsp+98h] [rbp+10h] BYREF

  AcquireSRWLockExclusive(&stru_18004BF40);
  v9 = &stru_18004BF40;
  if ( qword_18004C310
    || (v6 = 0,
        v5 = &qword_18004C310,
        v7 = 1,
        v2 = ((__int64 (__fastcall *)(__int64, __int64 *))qword_18004C170)(2, &v6),
        wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v5),
        v2 >= 0) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    return StateRepository::Globals::PartitionSettings::Load(
             (StateRepository::Globals::PartitionSettings *)StateRepository::Globals::PartitionSettings::deployment,
             a1,
             L"DeploymentDatabase",
             (struct Common::RegistryKey *)L"DeploymentDatabaseAutoCheckpoint",
             (struct Common::RegistryKey *)L"DeploymentDatabaseCheckpointThreshold",
             (struct Common::RegistryKey *)L"DeploymentDatabaseFileChunkSize",
             (struct Common::RegistryKey *)L"DeploymentDatabaseJournalSizeLimit",
             (struct Common::RegistryKey *)L"DeploymentDatabaseOptions",
             (struct Common::RegistryKey *)L"DeploymentDatabasePageSize",
             (struct Common::RegistryKey *)L"DeploymentDatabaseCacheSize",
             qword_18004C310);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1BF,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
      (const char *)(unsigned int)v2,
      v4);
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    return (unsigned int)v2;
  }
}

```

## disassembly

```asm
0x18002473c  mov     [rsp+arg_0], rbx
0x180024741  push    rdi
0x180024742  sub     rsp, 80h
0x180024749  mov     rdi, rcx
0x18002474c  lea     rbx, stru_18004BF40
0x180024753  mov     rcx, rbx; SRWLock
0x180024756  call    cs:__imp_AcquireSRWLockExclusive
0x18002475c  cmp     cs:qword_18004C310, 0
0x180024764  mov     [rsp+88h+arg_8], rbx
0x18002476c  jnz     short loc_1800247DB
0x18002476e  lea     rax, qword_18004C310
0x180024775  mov     [rsp+88h+var_20], 0
0x18002477e  mov     [rsp+88h+var_28], rax
0x180024783  lea     rdx, [rsp+88h+var_20]
0x180024788  mov     rax, cs:qword_18004C170
0x18002478f  mov     ecx, 2
0x180024794  mov     [rsp+88h+var_18], 1
0x180024799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002479e  lea     rcx, [rsp+88h+var_28]
0x1800247a3  mov     ebx, eax
0x1800247a5  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800247aa  test    ebx, ebx
0x1800247ac  jns     short loc_1800247DB
0x1800247ae  mov     rcx, [rsp+88h]; this
0x1800247b6  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x1800247bd  mov     r9d, ebx; char *
0x1800247c0  mov     edx, 1BFh; void *
0x1800247c5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800247ca  lea     rcx, [rsp+88h+arg_8]
0x1800247d2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800247d7  mov     eax, ebx
0x1800247d9  jmp     short loc_180024859
0x1800247db  lea     rcx, [rsp+88h+arg_8]
0x1800247e3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800247e8  mov     rax, cs:qword_18004C310
0x1800247ef  lea     r9, ?stateRepositoryRegistryNameDeploymentDatabaseAutoCheckpoint@StateRepository@@3QBGB; "DeploymentDatabaseAutoCheckpoint"
0x1800247f6  mov     [rsp+88h+var_38], rax; unsigned __int16 *
0x1800247fb  lea     r8, ?stateRepositoryRegistryNameDeploymentDatabase@StateRepository@@3QBGB; "DeploymentDatabase"
0x180024802  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabaseCacheSize@StateRepository@@3QBGB; "DeploymentDatabaseCacheSize"
0x180024809  mov     rdx, rdi; struct Common::RegistryKey *
0x18002480c  mov     [rsp+88h+var_40], rax; unsigned __int16 *
0x180024811  lea     rcx, ?deployment@PartitionSettings@Globals@StateRepository@@0U123@A; this
0x180024818  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabasePageSize@StateRepository@@3QBGB; "DeploymentDatabasePageSize"
0x18002481f  mov     [rsp+88h+var_48], rax; unsigned __int16 *
0x180024824  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabaseOptions@StateRepository@@3QBGB; "DeploymentDatabaseOptions"
0x18002482b  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x180024830  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabaseJournalSizeLimit@StateRepository@@3QBGB; "DeploymentDatabaseJournalSizeLimit"
0x180024837  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x18002483c  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabaseFileChunkSize@StateRepository@@3QBGB; "DeploymentDatabaseFileChunkSize"
0x180024843  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180024848  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabaseCheckpointThreshold@StateRepository@@3QBGB; "DeploymentDatabaseCheckpointThreshold"
0x18002484f  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x180024854  call    ?Load@PartitionSettings@Globals@StateRepository@@QEAAJAEAVRegistryKey@Common@@PEBG11111111@Z; StateRepository::Globals::PartitionSettings::Load(Common::RegistryKey &,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180024859  mov     rbx, [rsp+88h+arg_0]
0x180024861  add     rsp, 80h
0x180024868  pop     rdi
0x180024869  retn
```
