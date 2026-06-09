# StateRepository::Globals::SetDatabaseCorruptionLastReported(StateRepository::Partition,unsigned __int64,unsigned __int64,unsigned __int64)

- ea: `0x180024d40`
- end: `0x180024ee5`
- name: `?SetDatabaseCorruptionLastReported@Globals@StateRepository@@YAJW4Partition@2@_K11@Z`
- size: `421`
- prototype: `int __high(enum StateRepository::Partition, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x180027fdc`

## callees

- `0x1800041cc`
- `0x18000a3c0`
- `0x18000c3bc`
- `0x18000d9a4`
- `0x180014ca0`
- `0x1800157a4`
- `0x180017c84`
- `0x180023110`
- `0x180023918`
- `0x180024d40`
- `0x180024f74`
- `0x18002bb78`

## string_xrefs

- `0x180024d83`: `onecore\internal\sdk\inc\wil\opensource/wil/token_helpers.h`
- `0x180024dc6`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180024dfa`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180024e4a`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180024e79`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`
- `0x180024ea8`: `onecore\base\appmodel\staterepository\dataaccesslayer\globals.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Globals::SetDatabaseCorruptionLastReported(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 *a4)
{
  __int64 v7; // rcx
  unsigned __int16 *RegistrySubkeyStatusForPartition; // rbx
  int v9; // eax
  unsigned __int64 v10; // r8
  int PersistedRegKeyPath; // eax
  const unsigned __int16 *v12; // r8
  unsigned int *v13; // r9
  void *v14; // rbx
  unsigned int v15; // edi
  int v16; // eax
  unsigned __int64 v17; // r9
  int v19; // eax
  unsigned __int64 v20; // r9
  int v21; // eax
  unsigned __int64 v22; // r9
  int v23; // eax
  HKEY phkResult; // [rsp+20h] [rbp-28h] BYREF
  __int64 v25; // [rsp+28h] [rbp-20h] BYREF
  void *Block; // [rsp+30h] [rbp-18h] BYREF
  unsigned __int16 *v27; // [rsp+38h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+30h]

  RegistrySubkeyStatusForPartition = (unsigned __int16 *)StateRepository::Globals::GetRegistrySubkeyStatusForPartition();
  if ( RegistrySubkeyStatusForPartition )
  {
    v25 = -1;
    v9 = wil::impersonate_token_nothrow(v7, (void **)&v25);
    if ( v9 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x1E8,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/token_helpers.h",
        (const char *)(unsigned int)v9,
        (int)phkResult);
    Block = 0;
    v27 = RegistrySubkeyStatusForPartition;
    PersistedRegKeyPath = Common::StateSeparation::GetPersistedRegKeyPath(
                            (const struct Common::StateSeparationRedirectionMapping *)&qword_18004BF48,
                            (const unsigned __int16 **)&v27,
                            v10,
                            (unsigned __int16 **)&Block);
    v14 = Block;
    v15 = PersistedRegKeyPath;
    if ( PersistedRegKeyPath < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x436,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)PersistedRegKeyPath,
        (int)phkResult);
LABEL_8:
      operator delete(v14);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v25);
      return v15;
    }
    phkResult = 0;
    v16 = StateRepository::Globals::Registry::Create(&phkResult, (struct Common::RegistryKey *)Block, v12, v13);
    v15 = v16;
    if ( v16 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x439,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v16,
        (int)phkResult);
      Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
      goto LABEL_8;
    }
    v19 = StateRepository::Globals::Registry::WriteValue(
            (StateRepository::Globals::Registry *)&phkResult,
            (struct Common::RegistryKey *)L"DatabaseCorruptionFirstDetectedUptime",
            a2,
            v17);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x43B,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v19,
        (int)phkResult);
    v21 = StateRepository::Globals::Registry::WriteValue(
            (StateRepository::Globals::Registry *)&phkResult,
            (struct Common::RegistryKey *)L"DatabaseCorruptionFirstDetectedWhen",
            a3,
            v20);
    if ( v21 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x43C,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v21,
        (int)phkResult);
    v23 = StateRepository::Globals::Registry::WriteValue(
            (StateRepository::Globals::Registry *)&phkResult,
            (struct Common::RegistryKey *)L"DatabaseCorruptionLastReported",
            a4,
            v22);
    if ( v23 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x43D,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\globals.cpp",
        (const char *)(unsigned int)v23,
        (int)phkResult);
    Common::AutoHandleCloseHKEY<HKEY__ *>(phkResult);
    operator delete(v14);
    wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(&v25);
  }
  return 0;
}

```

## disassembly

```asm
0x180024d40  push    rbp
0x180024d42  push    rbx
0x180024d43  push    rsi
0x180024d44  push    rdi
0x180024d45  push    r14
0x180024d47  push    r15
0x180024d49  mov     rbp, rsp
0x180024d4c  sub     rsp, 48h
0x180024d50  mov     r15, r9
0x180024d53  mov     r14, r8
0x180024d56  mov     rsi, rdx
0x180024d59  call    ?GetRegistrySubkeyStatusForPartition@Globals@StateRepository@@YAPEBGW4Partition@2@@Z; StateRepository::Globals::GetRegistrySubkeyStatusForPartition(StateRepository::Partition)
0x180024d5e  mov     rbx, rax
0x180024d61  test    rax, rax
0x180024d64  jz      loc_180024ED6
0x180024d6a  lea     rdx, [rbp+var_20]
0x180024d6e  mov     [rbp+var_20], 0FFFFFFFFFFFFFFFFh
0x180024d76  call    ?impersonate_token_nothrow@wil@@YAJPEAXAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@@Z; wil::impersonate_token_nothrow(void *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>> &)
0x180024d7b  test    eax, eax
0x180024d7d  jns     short loc_180024D98
0x180024d7f  mov     rcx, [rbp+30h]; this
0x180024d83  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180024d8a  mov     r9d, eax; char *
0x180024d8d  mov     edx, 1E8h; void *
0x180024d92  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180024d98  lea     r9, [rbp+Block]; unsigned __int16 **
0x180024d9c  mov     [rbp+Block], 0
0x180024da4  lea     rdx, [rbp+var_10]; unsigned __int16 **
0x180024da8  mov     [rbp+var_10], rbx
0x180024dac  lea     rcx, qword_18004BF48; struct Common::StateSeparationRedirectionMapping *
0x180024db3  call    ?GetPersistedRegKeyPath@StateSeparation@Common@@SAJAEBUStateSeparationRedirectionMapping@2@PEAPEBG_KPEAPEAG@Z; Common::StateSeparation::GetPersistedRegKeyPath(Common::StateSeparationRedirectionMapping const &,ushort const * *,unsigned __int64,ushort * *)
0x180024db8  mov     rbx, [rbp+Block]
0x180024dbc  mov     edi, eax
0x180024dbe  test    eax, eax
0x180024dc0  jns     short loc_180024DDC
0x180024dc2  mov     rcx, [rbp+30h]; this
0x180024dc6  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180024dcd  mov     r9d, eax; char *
0x180024dd0  mov     edx, 436h; void *
0x180024dd5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024dda  jmp     short loc_180024E17
0x180024ddc  mov     rdx, rbx; struct Common::RegistryKey *
0x180024ddf  mov     [rbp+phkResult], 0
0x180024de7  lea     rcx, [rbp+phkResult]; phkResult
0x180024deb  call    ?Create@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBGPEAK@Z; StateRepository::Globals::Registry::Create(Common::RegistryKey &,ushort const *,ulong *)
0x180024df0  mov     edi, eax
0x180024df2  test    eax, eax
0x180024df4  jns     short loc_180024E2F
0x180024df6  mov     rcx, [rbp+30h]; this
0x180024dfa  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180024e01  mov     r9d, eax; char *
0x180024e04  mov     edx, 439h; void *
0x180024e09  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024e0e  mov     rcx, [rbp+phkResult]
0x180024e12  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180024e17  mov     rcx, rbx; Block
0x180024e1a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024e1f  lea     rcx, [rbp+var_20]
0x180024e23  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180024e28  mov     eax, edi
0x180024e2a  jmp     loc_180024ED8
0x180024e2f  mov     r8, rsi; unsigned __int16 *
0x180024e32  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionFirstDetectedUptime@StateRepository@@3QBGB; "DatabaseCorruptionFirstDetectedUptime"
0x180024e39  lea     rcx, [rbp+phkResult]; this
0x180024e3d  call    ?WriteValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_K@Z; StateRepository::Globals::Registry::WriteValue(Common::RegistryKey &,ushort const *,unsigned __int64)
0x180024e42  test    eax, eax
0x180024e44  jns     short loc_180024E5E
0x180024e46  mov     rcx, [rbp+30h]; this
0x180024e4a  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180024e51  mov     r9d, eax; char *
0x180024e54  mov     edx, 43Bh; void *
0x180024e59  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024e5e  mov     r8, r14; unsigned __int16 *
0x180024e61  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionFirstDetectedWhen@StateRepository@@3QBGB; "DatabaseCorruptionFirstDetectedWhen"
0x180024e68  lea     rcx, [rbp+phkResult]; this
0x180024e6c  call    ?WriteValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_K@Z; StateRepository::Globals::Registry::WriteValue(Common::RegistryKey &,ushort const *,unsigned __int64)
0x180024e71  test    eax, eax
0x180024e73  jns     short loc_180024E8D
0x180024e75  mov     rcx, [rbp+30h]; this
0x180024e79  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180024e80  mov     r9d, eax; char *
0x180024e83  mov     edx, 43Ch; void *
0x180024e88  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024e8d  mov     r8, r15; unsigned __int16 *
0x180024e90  lea     rdx, ?stateRepositoryRegistryNameDatabaseCorruptionLastReported@StateRepository@@3QBGB; "DatabaseCorruptionLastReported"
0x180024e97  lea     rcx, [rbp+phkResult]; this
0x180024e9b  call    ?WriteValue@Registry@Globals@StateRepository@@YAJAEAVRegistryKey@Common@@PEBG_K@Z; StateRepository::Globals::Registry::WriteValue(Common::RegistryKey &,ushort const *,unsigned __int64)
0x180024ea0  test    eax, eax
0x180024ea2  jns     short loc_180024EBC
0x180024ea4  mov     rcx, [rbp+30h]; this
0x180024ea8  lea     r8, aOnecoreBaseApp_53; "onecore\\base\\appmodel\\staterepositor"...
0x180024eaf  mov     r9d, eax; char *
0x180024eb2  mov     edx, 43Dh; void *
0x180024eb7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180024ebc  mov     rcx, [rbp+phkResult]
0x180024ec0  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x180024ec5  mov     rcx, rbx; Block
0x180024ec8  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180024ecd  lea     rcx, [rbp+var_20]
0x180024ed1  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x180024ed6  xor     eax, eax
0x180024ed8  add     rsp, 48h
0x180024edc  pop     r15
0x180024ede  pop     r14
0x180024ee0  pop     rdi
0x180024ee1  pop     rsi
0x180024ee2  pop     rbx
0x180024ee3  pop     rbp
0x180024ee4  retn
```
