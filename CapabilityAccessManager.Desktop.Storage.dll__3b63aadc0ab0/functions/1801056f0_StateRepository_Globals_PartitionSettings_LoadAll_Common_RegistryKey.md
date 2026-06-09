# StateRepository::Globals::PartitionSettings::LoadAll(Common::RegistryKey &)

- ea: `0x1801056f0`
- end: `0x180105a75`
- name: `?LoadAll@PartitionSettings@Globals@StateRepository@@SAJAEAVRegistryKey@Common@@@Z`
- size: `901`
- prototype: `__int64 __fastcall(struct Common::RegistryKey *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180105bbc`

## callees

- `0x1800eabf4`
- `0x1801052a8`
- `0x1801056f0`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18010570f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18010583b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180105952`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18010570f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18010583b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180105952`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18010578c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18010579b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801058b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801058c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801059cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801059de`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18010578c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18010579b`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801058b8`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801058c7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801059cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1801059de`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180105766`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180105892`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801059a9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180105766`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180105892`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801059a9`

## string_xrefs

- `0x1801059f1`: `DownlevelMachineDatabaseCacheSize`
- `0x1801058da`: `DeploymentDatabaseCacheSize`
- `0x1801057ae`: `MachineDatabaseCacheSize`
- `0x180105777`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180105825`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1801058a3`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1801059ba`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::PartitionSettings::LoadAll(struct Common::RegistryKey *a1)
{
  int v2; // ebx
  HLOCAL v3; // rcx
  __int64 v4; // rdx
  HLOCAL v6; // rcx
  HLOCAL v7; // rcx
  int v8; // [rsp+20h] [rbp-29h]
  int v9; // [rsp+20h] [rbp-29h]
  void *v10; // [rsp+68h] [rbp+1Fh] BYREF
  char v11; // [rsp+70h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+5Fh]

  AcquireSRWLockExclusive(&stru_180140488);
  if ( !qword_1801406B8 )
  {
    v10 = 0;
    v11 = 1;
    v2 = ((__int64 (__fastcall *)(__int64, void **))qword_180140670)(1, &v10);
    if ( v11 )
    {
      v3 = qword_1801406B8;
      qword_1801406B8 = v10;
      if ( v3 )
        LocalFree(v3);
    }
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A7,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v2,
        v8);
      ReleaseSRWLockExclusive(&stru_180140488);
LABEL_8:
      v4 = 367;
LABEL_9:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v4,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v2,
        v9);
      return (unsigned int)v2;
    }
  }
  ReleaseSRWLockExclusive(&stru_180140488);
  v2 = StateRepository::Globals::PartitionSettings::Load(
         (StateRepository::Globals::PartitionSettings *)&StateRepository::Globals::PartitionSettings::machine,
         a1,
         (wchar_t *)L"MachineDatabase",
         L"MachineDatabaseAutoCheckpoint",
         L"MachineDatabaseCheckpointThreshold",
         L"MachineDatabaseFileChunkSize",
         L"MachineDatabaseJournalSizeLimit",
         L"MachineDatabaseOptions",
         L"MachineDatabasePageSize",
         L"MachineDatabaseCacheSize",
         (wchar_t *)qword_1801406B8);
  if ( v2 < 0 )
    goto LABEL_8;
  AcquireSRWLockExclusive(&stru_180140488);
  if ( !qword_1801406C0 )
  {
    v10 = 0;
    v11 = 1;
    v2 = ((__int64 (__fastcall *)(__int64, void **))qword_180140670)(2, &v10);
    if ( v11 )
    {
      v6 = qword_1801406C0;
      qword_1801406C0 = v10;
      if ( v6 )
        LocalFree(v6);
    }
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1BF,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v2,
        v9);
      ReleaseSRWLockExclusive(&stru_180140488);
LABEL_17:
      v4 = 368;
      goto LABEL_9;
    }
  }
  ReleaseSRWLockExclusive(&stru_180140488);
  v2 = StateRepository::Globals::PartitionSettings::Load(
         (StateRepository::Globals::PartitionSettings *)&StateRepository::Globals::PartitionSettings::deployment,
         a1,
         (wchar_t *)L"DeploymentDatabase",
         L"DeploymentDatabaseAutoCheckpoint",
         L"DeploymentDatabaseCheckpointThreshold",
         L"DeploymentDatabaseFileChunkSize",
         L"DeploymentDatabaseJournalSizeLimit",
         L"DeploymentDatabaseOptions",
         L"DeploymentDatabasePageSize",
         L"DeploymentDatabaseCacheSize",
         (wchar_t *)qword_1801406C0);
  if ( v2 < 0 )
    goto LABEL_17;
  AcquireSRWLockExclusive(&stru_180140488);
  if ( !qword_1801406C8 )
  {
    v10 = 0;
    v11 = 1;
    v2 = ((__int64 (__fastcall *)(__int64, void **))qword_180140670)(4, &v10);
    if ( v11 )
    {
      v7 = qword_1801406C8;
      qword_1801406C8 = v10;
      if ( v7 )
        LocalFree(v7);
    }
    if ( v2 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1D7,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v2,
        v9);
      ReleaseSRWLockExclusive(&stru_180140488);
LABEL_25:
      v4 = 369;
      goto LABEL_9;
    }
  }
  ReleaseSRWLockExclusive(&stru_180140488);
  v2 = StateRepository::Globals::PartitionSettings::Load(
         (StateRepository::Globals::PartitionSettings *)&StateRepository::Globals::PartitionSettings::downlevelMachine,
         a1,
         (wchar_t *)L"DownlevelMachineDatabase",
         L"DownlevelMachineDatabaseAutoCheckpoint",
         L"DownlevelMachineDatabaseCheckpointThreshold",
         L"DownlevelMachineDatabaseFileChunkSize",
         L"DownlevelMachineDatabaseJournalSizeLimit",
         L"DownlevelMachineDatabaseOptions",
         L"DownlevelMachineDatabasePageSize",
         L"DownlevelMachineDatabaseCacheSize",
         (wchar_t *)qword_1801406C8);
  if ( v2 < 0 )
    goto LABEL_25;
  return 0;
}

```

## disassembly

```asm
0x1801056f0  push    rbp
0x1801056f2  push    rbx
0x1801056f3  push    rdi
0x1801056f4  push    r14
0x1801056f6  lea     rbp, [rsp-3Fh]
0x1801056fb  sub     rsp, 88h
0x180105702  mov     rdi, rcx
0x180105705  lea     r14, stru_180140488
0x18010570c  mov     rcx, r14; SRWLock
0x18010570f  call    cs:__imp_AcquireSRWLockExclusive
0x180105715  cmp     cs:qword_1801406B8, 0
0x18010571d  jnz     short loc_180105798
0x18010571f  lea     rax, qword_1801406B8
0x180105726  mov     [rbp+57h+var_40], rax
0x18010572a  mov     [rbp+57h+var_38], 0
0x180105732  mov     [rbp+57h+var_30], 1
0x180105736  lea     rdx, [rbp+57h+var_38]
0x18010573a  mov     ecx, 1
0x18010573f  mov     rax, cs:qword_180140670
0x180105746  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010574b  mov     ebx, eax
0x18010574d  cmp     [rbp+57h+var_30], 0
0x180105751  jz      short loc_18010576C
0x180105753  mov     rdx, [rbp+57h+var_40]
0x180105757  mov     rcx, [rdx]; hMem
0x18010575a  mov     rax, [rbp+57h+var_38]
0x18010575e  mov     [rdx], rax
0x180105761  test    rcx, rcx
0x180105764  jz      short loc_18010576C
0x180105766  call    cs:__imp_LocalFree
0x18010576c  test    ebx, ebx
0x18010576e  jns     short loc_180105798
0x180105770  mov     rcx, [rbp+5Fh]; this
0x180105774  mov     r9d, ebx; char *
0x180105777  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18010577e  mov     edx, 1A7h; void *
0x180105783  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105788  nop
0x180105789  mov     rcx, r14; SRWLock
0x18010578c  call    cs:__imp_ReleaseSRWLockExclusive
0x180105792  nop
0x180105793  jmp     loc_180105819
0x180105798  mov     rcx, r14; SRWLock
0x18010579b  call    cs:__imp_ReleaseSRWLockExclusive
0x1801057a1  nop
0x1801057a2  mov     rax, cs:qword_1801406B8
0x1801057a9  mov     [rsp+0A0h+var_50], rax; wchar_t *
0x1801057ae  lea     rax, ?stateRepositoryRegistryNameMachineDatabaseCacheSize@StateRepository@@3QB_WB; "MachineDatabaseCacheSize"
0x1801057b5  mov     [rsp+0A0h+var_58], rax; wchar_t *
0x1801057ba  lea     rax, ?stateRepositoryRegistryNameMachineDatabasePageSize@StateRepository@@3QB_WB; "MachineDatabasePageSize"
0x1801057c1  mov     [rsp+0A0h+var_60], rax; wchar_t *
0x1801057c6  lea     rax, ?stateRepositoryRegistryNameMachineDatabaseOptions@StateRepository@@3QB_WB; "MachineDatabaseOptions"
0x1801057cd  mov     [rsp+0A0h+var_68], rax; wchar_t *
0x1801057d2  lea     rax, ?stateRepositoryRegistryNameMachineDatabaseJournalSizeLimit@StateRepository@@3QB_WB; "MachineDatabaseJournalSizeLimit"
0x1801057d9  mov     [rsp+0A0h+var_70], rax; wchar_t *
0x1801057de  lea     rax, ?stateRepositoryRegistryNameMachineDatabaseFileChunkSize@StateRepository@@3QB_WB; "MachineDatabaseFileChunkSize"
0x1801057e5  mov     [rsp+0A0h+var_78], rax; wchar_t *
0x1801057ea  lea     rax, ?stateRepositoryRegistryNameMachineDatabaseCheckpointThreshold@StateRepository@@3QB_WB; "MachineDatabaseCheckpointThreshold"
0x1801057f1  mov     [rsp+0A0h+var_80], rax; int
0x1801057f6  lea     r9, ?stateRepositoryRegistryNameMachineDatabaseAutoCheckpoint@StateRepository@@3QB_WB; "MachineDatabaseAutoCheckpoint"
0x1801057fd  lea     r8, ?stateRepositoryRegistryNameMachineDatabase@StateRepository@@3QB_WB; "MachineDatabase"
0x180105804  mov     rdx, rdi; struct Common::RegistryKey *
0x180105807  lea     rcx, ?machine@PartitionSettings@Globals@StateRepository@@0U123@A; this
0x18010580e  call    ?Load@PartitionSettings@Globals@StateRepository@@QEAAJAEAVRegistryKey@Common@@PEB_W11111111@Z; StateRepository::Globals::PartitionSettings::Load(Common::RegistryKey &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)
0x180105813  mov     ebx, eax
0x180105815  test    eax, eax
0x180105817  jns     short loc_180105838
0x180105819  mov     edx, 16Fh; void *
0x18010581e  mov     rcx, [rbp+5Fh]; this
0x180105822  mov     r9d, ebx; char *
0x180105825  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x18010582c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180105831  mov     eax, ebx
0x180105833  jmp     loc_180105A68
0x180105838  mov     rcx, r14; SRWLock
0x18010583b  call    cs:__imp_AcquireSRWLockExclusive
0x180105841  cmp     cs:qword_1801406C0, 0
0x180105849  jnz     short loc_1801058C4
0x18010584b  lea     rax, qword_1801406C0
0x180105852  mov     [rbp+57h+var_40], rax
0x180105856  mov     [rbp+57h+var_38], 0
0x18010585e  mov     [rbp+57h+var_30], 1
0x180105862  lea     rdx, [rbp+57h+var_38]
0x180105866  mov     ecx, 2
0x18010586b  mov     rax, cs:qword_180140670
0x180105872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180105877  mov     ebx, eax
0x180105879  cmp     [rbp+57h+var_30], 0
0x18010587d  jz      short loc_180105898
0x18010587f  mov     rdx, [rbp+57h+var_40]
0x180105883  mov     rcx, [rdx]; hMem
0x180105886  mov     rax, [rbp+57h+var_38]
0x18010588a  mov     [rdx], rax
0x18010588d  test    rcx, rcx
0x180105890  jz      short loc_180105898
0x180105892  call    cs:__imp_LocalFree
0x180105898  test    ebx, ebx
0x18010589a  jns     short loc_1801058C4
0x18010589c  mov     rcx, [rbp+5Fh]; this
0x1801058a0  mov     r9d, ebx; char *
0x1801058a3  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1801058aa  mov     edx, 1BFh; void *
0x1801058af  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801058b4  nop
0x1801058b5  mov     rcx, r14; SRWLock
0x1801058b8  call    cs:__imp_ReleaseSRWLockExclusive
0x1801058be  nop
0x1801058bf  jmp     loc_180105945
0x1801058c4  mov     rcx, r14; SRWLock
0x1801058c7  call    cs:__imp_ReleaseSRWLockExclusive
0x1801058cd  nop
0x1801058ce  mov     rax, cs:qword_1801406C0
0x1801058d5  mov     [rsp+0A0h+var_50], rax; wchar_t *
0x1801058da  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabaseCacheSize@StateRepository@@3QB_WB; "DeploymentDatabaseCacheSize"
0x1801058e1  mov     [rsp+0A0h+var_58], rax; wchar_t *
0x1801058e6  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabasePageSize@StateRepository@@3QB_WB; "DeploymentDatabasePageSize"
0x1801058ed  mov     [rsp+0A0h+var_60], rax; wchar_t *
0x1801058f2  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabaseOptions@StateRepository@@3QB_WB; "DeploymentDatabaseOptions"
0x1801058f9  mov     [rsp+0A0h+var_68], rax; wchar_t *
0x1801058fe  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabaseJournalSizeLimit@StateRepository@@3QB_WB; "DeploymentDatabaseJournalSizeLimit"
0x180105905  mov     [rsp+0A0h+var_70], rax; wchar_t *
0x18010590a  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabaseFileChunkSize@StateRepository@@3QB_WB; "DeploymentDatabaseFileChunkSize"
0x180105911  mov     [rsp+0A0h+var_78], rax; wchar_t *
0x180105916  lea     rax, ?stateRepositoryRegistryNameDeploymentDatabaseCheckpointThreshold@StateRepository@@3QB_WB; "DeploymentDatabaseCheckpointThreshold"
0x18010591d  mov     [rsp+0A0h+var_80], rax; int
0x180105922  lea     r9, ?stateRepositoryRegistryNameDeploymentDatabaseAutoCheckpoint@StateRepository@@3QB_WB; "DeploymentDatabaseAutoCheckpoint"
0x180105929  lea     r8, ?stateRepositoryRegistryNameDeploymentDatabase@StateRepository@@3QB_WB; "DeploymentDatabase"
0x180105930  mov     rdx, rdi; struct Common::RegistryKey *
0x180105933  lea     rcx, ?deployment@PartitionSettings@Globals@StateRepository@@0U123@A; this
0x18010593a  call    ?Load@PartitionSettings@Globals@StateRepository@@QEAAJAEAVRegistryKey@Common@@PEB_W11111111@Z; StateRepository::Globals::PartitionSettings::Load(Common::RegistryKey &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)
0x18010593f  mov     ebx, eax
0x180105941  test    eax, eax
0x180105943  jns     short loc_18010594F
0x180105945  mov     edx, 170h
0x18010594a  jmp     loc_18010581E
0x18010594f  mov     rcx, r14; SRWLock
0x180105952  call    cs:__imp_AcquireSRWLockExclusive
0x180105958  cmp     cs:qword_1801406C8, 0
0x180105960  jnz     short loc_1801059DB
0x180105962  lea     rax, qword_1801406C8
0x180105969  mov     [rbp+57h+var_40], rax
0x18010596d  mov     [rbp+57h+var_38], 0
0x180105975  mov     [rbp+57h+var_30], 1
0x180105979  lea     rdx, [rbp+57h+var_38]
0x18010597d  mov     ecx, 4
0x180105982  mov     rax, cs:qword_180140670
0x180105989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010598e  mov     ebx, eax
0x180105990  cmp     [rbp+57h+var_30], 0
0x180105994  jz      short loc_1801059AF
0x180105996  mov     rdx, [rbp+57h+var_40]
0x18010599a  mov     rcx, [rdx]; hMem
0x18010599d  mov     rax, [rbp+57h+var_38]
0x1801059a1  mov     [rdx], rax
0x1801059a4  test    rcx, rcx
0x1801059a7  jz      short loc_1801059AF
0x1801059a9  call    cs:__imp_LocalFree
0x1801059af  test    ebx, ebx
0x1801059b1  jns     short loc_1801059DB
0x1801059b3  mov     rcx, [rbp+5Fh]; this
0x1801059b7  mov     r9d, ebx; char *
0x1801059ba  lea     r8, aOnecoreBaseApp_24; "onecore\\base\\appmodel\\staterepositor"...
0x1801059c1  mov     edx, 1D7h; void *
0x1801059c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801059cb  nop
0x1801059cc  mov     rcx, r14; SRWLock
0x1801059cf  call    cs:__imp_ReleaseSRWLockExclusive
0x1801059d5  nop
0x1801059d6  jmp     loc_180105A5C
0x1801059db  mov     rcx, r14; SRWLock
0x1801059de  call    cs:__imp_ReleaseSRWLockExclusive
0x1801059e4  nop
0x1801059e5  mov     rax, cs:qword_1801406C8
0x1801059ec  mov     [rsp+0A0h+var_50], rax; wchar_t *
0x1801059f1  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabaseCacheSize@StateRepository@@3QB_WB; "DownlevelMachineDatabaseCacheSize"
0x1801059f8  mov     [rsp+0A0h+var_58], rax; wchar_t *
0x1801059fd  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabasePageSize@StateRepository@@3QB_WB; "DownlevelMachineDatabasePageSize"
0x180105a04  mov     [rsp+0A0h+var_60], rax; wchar_t *
0x180105a09  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabaseOptions@StateRepository@@3QB_WB; "DownlevelMachineDatabaseOptions"
0x180105a10  mov     [rsp+0A0h+var_68], rax; wchar_t *
0x180105a15  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabaseJournalSizeLimit@StateRepository@@3QB_WB; "DownlevelMachineDatabaseJournalSizeLimi"...
0x180105a1c  mov     [rsp+0A0h+var_70], rax; wchar_t *
0x180105a21  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabaseFileChunkSize@StateRepository@@3QB_WB; "DownlevelMachineDatabaseFileChunkSize"
0x180105a28  mov     [rsp+0A0h+var_78], rax; wchar_t *
0x180105a2d  lea     rax, ?stateRepositoryRegistryNameDownlevelMachineDatabaseCheckpointThreshold@StateRepository@@3QB_WB; "DownlevelMachineDatabaseCheckpointThres"...
0x180105a34  mov     [rsp+0A0h+var_80], rax; wchar_t *
0x180105a39  lea     r9, ?stateRepositoryRegistryNameDownlevelMachineDatabaseAutoCheckpoint@StateRepository@@3QB_WB; "DownlevelMachineDatabaseAutoCheckpoint"
0x180105a40  lea     r8, ?stateRepositoryRegistryNameDownlevelMachineDatabase@StateRepository@@3QB_WB; "DownlevelMachineDatabase"
0x180105a47  mov     rdx, rdi; struct Common::RegistryKey *
0x180105a4a  lea     rcx, ?downlevelMachine@PartitionSettings@Globals@StateRepository@@0U123@A; this
0x180105a51  call    ?Load@PartitionSettings@Globals@StateRepository@@QEAAJAEAVRegistryKey@Common@@PEB_W11111111@Z; StateRepository::Globals::PartitionSettings::Load(Common::RegistryKey &,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *,wchar_t const *)
0x180105a56  mov     ebx, eax
0x180105a58  test    eax, eax
0x180105a5a  jns     short loc_180105A66
0x180105a5c  mov     edx, 171h
0x180105a61  jmp     loc_18010581E
0x180105a66  xor     eax, eax
0x180105a68  add     rsp, 88h
0x180105a6f  pop     r14
0x180105a71  pop     rdi
0x180105a72  pop     rbx
0x180105a73  pop     rbp
0x180105a74  retn
```
