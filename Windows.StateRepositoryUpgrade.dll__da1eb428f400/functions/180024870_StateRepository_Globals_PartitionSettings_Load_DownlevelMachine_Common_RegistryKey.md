# StateRepository::Globals::PartitionSettings::Load_DownlevelMachine(Common::RegistryKey &)

- ea: `0x180024870`
- end: `0x18002499e`
- name: `?Load_DownlevelMachine@PartitionSettings@Globals@StateRepository@@CAJAEAVRegistryKey@Common@@@Z`
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
- `0x180024870`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002488a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002488a`

## string_xrefs

- `0x1800248ea`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180024936`: `DownlevelMachineDatabaseCacheSize`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::PartitionSettings::Load_DownlevelMachine(struct Common::RegistryKey *a1)
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
  if ( qword_18004C318
    || (v6 = 0,
        v5 = &qword_18004C318,
        v7 = 1,
        v2 = ((__int64 (__fastcall *)(__int64, __int64 *))qword_18004C170)(4, &v6),
        wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(&v5),
        v2 >= 0) )
  {
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
    return StateRepository::Globals::PartitionSettings::Load(
             (StateRepository::Globals::PartitionSettings *)StateRepository::Globals::PartitionSettings::downlevelMachine,
             a1,
             L"DownlevelMachineDatabase",
             (struct Common::RegistryKey *)L"DownlevelMachineDatabaseAutoCheckpoint",
             (struct Common::RegistryKey *)L"DownlevelMachineDatabaseCheckpointThreshold",
             (struct Common::RegistryKey *)L"DownlevelMachineDatabaseFileChunkSize",
             (struct Common::RegistryKey *)L"DownlevelMachineDatabaseJournalSizeLimit",
             (struct Common::RegistryKey *)L"DownlevelMachineDatabaseOptions",
             (struct Common::RegistryKey *)L"DownlevelMachineDatabasePageSize",
             (struct Common::RegistryKey *)L"DownlevelMachineDatabaseCacheSize",
             qword_18004C318);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1D7,
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
0x180024870  mov     [rsp+arg_0], rbx
0x180024875  push    rdi
0x180024876  sub     rsp, 80h
0x18002487d  mov     rdi, rcx
0x180024880  lea     rbx, stru_18004BF40
0x180024887  mov     rcx, rbx; SRWLock
0x18002488a  call    cs:__imp_AcquireSRWLockExclusive
0x180024890  cmp     cs:qword_18004C318, 0
0x180024898  mov     [rsp+88h+arg_8], rbx
0x1800248a0  jnz     short loc_18002490F
0x1800248a2  lea     rax, qword_18004C318
0x1800248a9  mov     [rsp+88h+var_20], 0
0x1800248b2  mov     [rsp+88h+var_28], rax
0x1800248b7  lea     rdx, [rsp+88h+var_20]
0x1800248bc  mov     rax, cs:qword_18004C170
0x1800248c3  mov     ecx, 4
0x1800248c8  mov     [rsp+88h+var_18], 1
0x1800248cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248d2  lea     rcx, [rsp+88h+var_28]
0x1800248d7  mov     ebx, eax
0x1800248d9  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800248de  test    ebx, ebx
0x1800248e0  jns     short loc_18002490F
0x1800248e2  mov     rcx, [rsp+88h]; this
0x1800248ea  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x1800248f1  mov     r9d, ebx; char *
0x1800248f4  mov     edx, 1D7h; void *
0x1800248f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800248fe  lea     rcx, [rsp+88h+arg_8]
0x180024906  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002490b  mov     eax, ebx
0x18002490d  jmp     short loc_18002498D
0x18002490f  lea     rcx, [rsp+88h+arg_8]
0x180024917  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002491c  mov     rax, cs:qword_18004C318
0x180024923  lea     r9, ?stateRepositoryRegistryNameDownlevelMachineDatabaseAutoCheckpoint@StateRepository@@3QBGB; "DownlevelMachineDatabaseAutoCheckpoint"
0x18002492a  mov     [rsp+88h+var_38], rax; unsigned __int16 *
0x18002492f  lea     r8, ?stateRepositoryRegistryNameDownlevelMachineDatabase@StateRepository@@3QBGB; "DownlevelMachineDatabase"
0x180024936  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabaseCacheSize@StateRepository@@3QBGB; "DownlevelMachineDatabaseCacheSize"
0x18002493d  mov     rdx, rdi; struct Common::RegistryKey *
0x180024940  mov     [rsp+88h+var_40], rax; unsigned __int16 *
0x180024945  lea     rcx, ?downlevelMachine@PartitionSettings@Globals@StateRepository@@0U123@A; this
0x18002494c  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabasePageSize@StateRepository@@3QBGB; "DownlevelMachineDatabasePageSize"
0x180024953  mov     [rsp+88h+var_48], rax; unsigned __int16 *
0x180024958  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabaseOptions@StateRepository@@3QBGB; "DownlevelMachineDatabaseOptions"
0x18002495f  mov     [rsp+88h+var_50], rax; unsigned __int16 *
0x180024964  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabaseJournalSizeLimit@StateRepository@@3QBGB; "DownlevelMachineDatabaseJournalSizeLimi"...
0x18002496b  mov     [rsp+88h+var_58], rax; unsigned __int16 *
0x180024970  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabaseFileChunkSize@StateRepository@@3QBGB; "DownlevelMachineDatabaseFileChunkSize"
0x180024977  mov     [rsp+88h+var_60], rax; unsigned __int16 *
0x18002497c  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabaseCheckpointThreshold@StateRepository@@3QBGB; "DownlevelMachineDatabaseCheckpointThres"...
0x180024983  mov     [rsp+88h+var_68], rax; unsigned __int16 *
0x180024988  call    ?Load@PartitionSettings@Globals@StateRepository@@QEAAJAEAVRegistryKey@Common@@PEBG11111111@Z; StateRepository::Globals::PartitionSettings::Load(Common::RegistryKey &,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)
0x18002498d  mov     rbx, [rsp+88h+arg_0]
0x180024995  add     rsp, 80h
0x18002499c  pop     rdi
0x18002499d  retn
```
