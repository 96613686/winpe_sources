# StateRepository::Globals::PartitionSettings::Load_Machine(Common::RegistryKey &)

- ea: `0x1800249a4`
- end: `0x180024ad2`
- name: `?Load_Machine@PartitionSettings@Globals@StateRepository@@CAJAEAVRegistryKey@Common@@@Z`
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
- `0x1800249a4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800249be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800249be`

## string_xrefs

- `0x180024a1e`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180024a6a`: `MachineDatabaseCacheSize`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::PartitionSettings::Load_Machine(struct Common::RegistryKey *a1)
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
  if ( qword_18004C308
    || (v6 = 0,
        v5 = &qword_18004C308,
        v7 = 1,
        v2 = ((__int64 (__fastcall *)(__int64, __int64 *))qword_18004C170)(1, &v6),
        wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v5),
        v2 >= 0) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    return StateRepository::Globals::PartitionSettings::Load(
             (StateRepository::Globals::PartitionSettings *)StateRepository::Globals::PartitionSettings::machine,
             a1,
             L"MachineDatabase",
             (struct Common::RegistryKey *)L"MachineDatabaseAutoCheckpoint",
             (struct Common::RegistryKey *)L"MachineDatabaseCheckpointThreshold",
             (struct Common::RegistryKey *)L"MachineDatabaseFileChunkSize",
             (struct Common::RegistryKey *)L"MachineDatabaseJournalSizeLimit",
             (struct Common::RegistryKey *)L"MachineDatabaseOptions",
             (struct Common::RegistryKey *)L"MachineDatabasePageSize",
             (struct Common::RegistryKey *)L"MachineDatabaseCacheSize",
             qword_18004C308);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A7,
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
0x1800249a4  mov     [rsp+arg_0], rbx
0x1800249a9  push    rdi
0x1800249aa  sub     rsp, 80h
0x1800249b1  mov     rdi, rcx
0x1800249b4  lea     rbx, stru_18004BF40
0x1800249bb  mov     rcx, rbx; SRWLock
0x1800249be  call    cs:__imp_AcquireSRWLockExclusive
0x1800249c4  cmp     cs:qword_18004C308, 0
0x1800249cc  mov     [rsp+88h+arg_8], rbx
0x1800249d4  jnz     short loc_180024A43
0x1800249d6  lea     rax, qword_18004C308
0x1800249dd  mov     [rsp+88h+var_20], 0
0x1800249e6  mov     [rsp+88h+var_28], rax
0x1800249eb  lea     rdx, [rsp+88h+var_20]
0x1800249f0  mov     rax, cs:qword_18004C170
0x1800249f7  mov     ecx, 1
0x1800249fc  mov     [rsp+88h+var_18], 1
0x180024a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a06  lea     rcx, [rsp+88h+var_28]
0x180024a0b  mov     ebx, eax
0x180024a0d  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x180024a12  test    ebx, ebx
0x180024a14  jns     short loc_180024A43
0x180024a16  mov     rcx, [rsp+88h]; this
0x180024a1e  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180024a25  mov     r9d, ebx; char *
0x180024a28  mov     edx, 1A7h; void *
0x180024a2d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024a32  lea     rcx, [rsp+88h+arg_8]
0x180024a3a  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180024a3f  mov     eax, ebx
0x180024a41  jmp     short loc_180024AC1
0x180024a43  lea     rcx, [rsp+88h+arg_8]
0x180024a4b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180024a50  mov     rax, cs:qword_18004C308
0x180024a57  lea     r9, ?stateRepositoryRegistryNameMachineDatabaseAutoCheckpoint@StateRepository@@3QBGB; "MachineDatabaseAutoCheckpoint"
0x180024a5e  mov     [rsp+88h+var_38], rax; unsigned __int16 *
0x180024a63  lea     r8, ?stateRepositoryRegistryNameMachineDatabase@StateRepository@@3QBGB; "MachineDatabase"
0x180024a6a  lea     rax, ?stateRepositoryRegistryNameMachineDatabaseCacheSize@StateRepository@@3QBGB; "MachineDatabaseCacheSize"
0x180024a71  mov     rdx, rdi; struct Common::RegistryKey *
0x180024a74  mov     [rsp+88h+var_40], rax; unsigned __int16 *
0x180024a79  lea     rcx, ?machine@PartitionSettings@Globals@StateRepository@@0U123@A; this
0x180024a80  lea     rax, ?stateRepositoryRegistryNameMachineDatabasePageSize@StateRepository@@3QBGB; "MachineDatabasePageSize"
0x180024a87  mov     [rsp+88h+var_48], rax; unsigned __int16 *
0x180024a8c  lea     rax, ?stateRepositoryRegistryNameMachineDatabaseOptions@StateRepository@@3QBGB; "MachineDatabaseOptions"
0x180024a93  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x180024a98  lea     rax, ?stateRepositoryRegistryNameMachineDatabaseJournalSizeLimit@StateRepository@@3QBGB; "MachineDatabaseJournalSizeLimit"
0x180024a9f  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x180024aa4  lea     rax, ?stateRepositoryRegistryNameMachineDatabaseFileChunkSize@StateRepository@@3QBGB; "MachineDatabaseFileChunkSize"
0x180024aab  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x180024ab0  lea     rax, ?stateRepositoryRegistryNameMachineDatabaseCheckpointThreshold@StateRepository@@3QBGB; "MachineDatabaseCheckpointThreshold"
0x180024ab7  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x180024abc  call    ?Load@PartitionSettings@Globals@StateRepository@@QEAAJAEAVRegistryKey@Common@@PEBG11111111@Z; StateRepository::Globals::PartitionSettings::Load(Common::RegistryKey &,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x180024ac1  mov     rbx, [rsp+88h+arg_0]
0x180024ac9  add     rsp, 80h
0x180024ad0  pop     rdi
0x180024ad1  retn
```
