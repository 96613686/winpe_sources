# StateRepository::Globals::GetDatabaseCorruptionLastReported(StateRepository::Partition,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1800237bc`
- end: `0x180023912`
- name: `?GetDatabaseCorruptionLastReported@Globals@StateRepository@@YAJW4Partition@2@PEA_K11@Z`
- size: `342`
- prototype: `int __high(enum StateRepository::Partition, unsigned __int64 *, unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180027fdc`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x18000d9a4`
- `0x1800237bc`
- `0x180023918`
- `0x180024ad8`
- `0x180024b74`
- `0x18002bb78`

## string_xrefs

- `0x18002380c`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x1800238b8`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::GetDatabaseCorruptionLastReported(
        __int64 a1,
        _QWORD *a2,
        _QWORD *a3,
        _QWORD *a4)
{
  unsigned __int16 *RegistrySubkeyStatusForPartition; // rax
  __int64 v8; // r8
  int PersistedRegKeyPath; // eax
  const unsigned __int16 *v10; // r8
  unsigned int v11; // edi
  int Value; // eax
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdx
  const unsigned __int16 *v15; // r8
  const unsigned __int16 *v16; // r8
  HKEY phkResult; // [rsp+20h] [rbp-20h] BYREF
  void *Block; // [rsp+28h] [rbp-18h] BYREF
  unsigned __int16 *v20; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]

  RegistrySubkeyStatusForPartition = (unsigned __int16 *)StateRepository::Globals::GetRegistrySubkeyStatusForPartition();
  if ( RegistrySubkeyStatusForPartition )
  {
    Block = 0;
    v20 = RegistrySubkeyStatusForPartition;
    PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(
                            (Common **)&qword_18004BF48,
                            (const unsigned __int16 **)&v20,
                            v8,
                            (unsigned __int16 **)&Block);
    v11 = PersistedRegKeyPath;
    if ( PersistedRegKeyPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x414,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)PersistedRegKeyPath,
        (int)phkResult);
LABEL_14:
      operator delete(Block);
      return v11;
    }
    phkResult = 0;
    Value = StateRepository::Globals::Registry::Open(&phkResult, (const WCHAR *)Block, v10);
    v11 = Value;
    if ( (unsigned int)(Value + 2147024894) <= 1 )
    {
      *a2 = 0;
      *a3 = 0;
      *a4 = 0;
    }
    else
    {
      if ( Value < 0 )
      {
        v14 = 1056;
LABEL_13:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v14,
          (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
          (const char *)(unsigned int)Value,
          (int)phkResult);
        Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
        goto LABEL_14;
      }
      Value = StateRepository::Globals::Registry::ReadValue(
                (StateRepository::Globals::Registry *)&phkResult,
                (struct Common::RegistryKey *)L"DatabaseCorruptionFirstDetectedUptime",
                v13,
                a2);
      v11 = Value;
      if ( Value < 0 )
      {
        v14 = 1057;
        goto LABEL_13;
      }
      Value = StateRepository::Globals::Registry::ReadValue(
                (StateRepository::Globals::Registry *)&phkResult,
                (struct Common::RegistryKey *)L"DatabaseCorruptionFirstDetectedWhen",
                v15,
                a3);
      v11 = Value;
      if ( Value < 0 )
      {
        v14 = 1058;
        goto LABEL_13;
      }
      Value = StateRepository::Globals::Registry::ReadValue(
                (StateRepository::Globals::Registry *)&phkResult,
                (struct Common::RegistryKey *)L"DatabaseCorruptionLastReported",
                v16,
                a4);
      v11 = Value;
      if ( Value < 0 )
      {
        v14 = 1059;
        goto LABEL_13;
      }
    }
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    operator delete(Block);
  }
  return 0;
}

```

## disassembly

```asm
0x1800237bc  push    rbp
0x1800237be  push    rsi
0x1800237bf  push    rdi
0x1800237c0  push    r14
0x1800237c2  push    r15
0x1800237c4  mov     rbp, rsp
0x1800237c7  sub     rsp, 40h
0x1800237cb  mov     r15, r9
0x1800237ce  mov     r14, r8
0x1800237d1  mov     rsi, rdx
0x1800237d4  call    ?GetRegistrySubkeyStatusForPartition@Globals@StateRepository@@YAPEBGW4Partition@2@@Z; StateRepository::Globals::GetRegistrySubkeyStatusForPartition(StateRepository::Partition)
0x1800237d9  test    rax, rax
0x1800237dc  jz      loc_180023904
0x1800237e2  lea     r9, [rbp+Block]; unsigned __int16 **
0x1800237e6  mov     [rbp+Block], 0
0x1800237ee  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x1800237f2  mov     [rbp+var_10], rax
0x1800237f6  lea     rcx, qword_18004BF48; struct Common::StateSeparationRedirectionMapping *
0x1800237fd  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x180023802  mov     edi, eax
0x180023804  test    eax, eax
0x180023806  jns     short loc_180023825
0x180023808  mov     rcx, [rbp+28h]; this
0x18002380c  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180023813  mov     r9d, eax; char *
0x180023816  mov     edx, 414h; void *
0x18002381b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180023820  jmp     loc_1800238D0
0x180023825  mov     rdx, [rbp+Block]; struct Common::RegistryKey *
0x180023829  lea     rcx, [rbp+phkResult]; phkResult
0x18002382d  mov     [rbp+phkResult], 0
0x180023835  call    ?Open@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGK_N@Z; StateRepository::Globals::Registry::Open(Common::RegistryKey &,ushort const *,ulong,bool)
0x18002383a  mov     edi, eax
0x18002383c  lea     ecx, [rax+7FF8FFFEh]
0x180023842  cmp     ecx, 1
0x180023845  jbe     loc_1800238DD
0x18002384b  test    eax, eax
0x18002384d  jns     short loc_180023856
0x18002384f  mov     edx, 420h
0x180023854  jmp     short loc_1800238B4
0x180023856  mov     r9, rsi; unsigned __int64
0x180023859  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionFirstDetectedUptime@StateRepository@@3QBGB; "DatabaseCorruptionFirstDetectedUptime"
0x180023860  lea     rcx, [rbp+phkResult]; this
0x180023864  call    ?ReadValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::Registry::ReadValue(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180023869  mov     edi, eax
0x18002386b  test    eax, eax
0x18002386d  jns     short loc_180023876
0x18002386f  mov     edx, 421h
0x180023874  jmp     short loc_1800238B4
0x180023876  mov     r9, r14; unsigned __int64
0x180023879  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionFirstDetectedWhen@StateRepository@@3QBGB; "DatabaseCorruptionFirstDetectedWhen"
0x180023880  lea     rcx, [rbp+phkResult]; this
0x180023884  call    ?ReadValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::Registry::ReadValue(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x180023889  mov     edi, eax
0x18002388b  test    eax, eax
0x18002388d  jns     short loc_180023896
0x18002388f  mov     edx, 422h
0x180023894  jmp     short loc_1800238B4
0x180023896  mov     r9, r15; unsigned __int64
0x180023899  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionLastReported@StateRepository@@3QBGB; "DatabaseCorruptionLastReported"
0x1800238a0  lea     rcx, [rbp+phkResult]; this
0x1800238a4  call    ?ReadValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_KPEA_K@Z; StateRepository::Globals::Registry::ReadValue(Common::RegistryKey &,ushort const *,unsigned __int64,unsigned __int64 *)
0x1800238a9  mov     edi, eax
0x1800238ab  test    eax, eax
0x1800238ad  jns     short loc_1800238F2
0x1800238af  mov     edx, 423h; void *
0x1800238b4  mov     rcx, [rbp+28h]; this
0x1800238b8  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x1800238bf  mov     r9d, eax; char *
0x1800238c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800238c7  mov     rcx, [rbp+phkResult]
0x1800238cb  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800238d0  mov     rcx, [rbp+Block]; Block
0x1800238d4  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800238d9  mov     eax, edi
0x1800238db  jmp     short loc_180023906
0x1800238dd  mov     qword ptr [rsi], 0
0x1800238e4  mov     qword ptr [r14], 0
0x1800238eb  mov     qword ptr [r15], 0
0x1800238f2  mov     rcx, [rbp+phkResult]
0x1800238f6  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x1800238fb  mov     rcx, [rbp+Block]; Block
0x1800238ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180023904  xor     eax, eax
0x180023906  add     rsp, 40h
0x18002390a  pop     r15
0x18002390c  pop     r14
0x18002390e  pop     rdi
0x18002390f  pop     rsi
0x180023910  pop     rbp
0x180023911  retn
```
