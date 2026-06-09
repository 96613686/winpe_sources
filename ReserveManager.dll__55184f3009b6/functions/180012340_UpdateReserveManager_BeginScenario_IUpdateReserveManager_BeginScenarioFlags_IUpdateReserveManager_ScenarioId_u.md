# UpdateReserveManager::BeginScenario(IUpdateReserveManager::BeginScenarioFlags,IUpdateReserveManager::ScenarioId,unsigned __int64 *,IUpdateReserveManager::ScenarioId *)

- ea: `0x180012340`
- end: `0x1800127bf`
- name: `?BeginScenario@UpdateReserveManager@@UEAAJW4BeginScenarioFlags@IUpdateReserveManager@@W4ScenarioId@3@PEA_KPEAW443@@Z`
- size: `1151`
- prototype: `__int64 __fastcall(char *, unsigned int, unsigned int, _QWORD *, unsigned int *)`
- caller_count: `0`
- callee_count: `11`
- tags: `installer_update`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180012340`
- `0x1800133c4`
- `0x180015ad0`
- `0x180015e20`
- `0x18001a8f0`
- `0x18001d43c`
- `0x18001fa18`
- `0x180021e80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800123bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800123ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012495`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800124cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001257e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800125c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800125f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012623`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012656`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800126c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001270d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001278d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800123bc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800123ed`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012495`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800124cf`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001257e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800125c0`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800125f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012623`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180012656`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800126c9`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001270d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001278d`

## string_xrefs

- `0x180012439`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180012522`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180012445`: `UpdateReserveManager::BeginScenario`
- `0x18001252e`: `UpdateReserveManager::BeginScenario`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::BeginScenario(
        char *a1,
        unsigned int a2,
        unsigned int a3,
        _QWORD *a4,
        unsigned int *a5)
{
  int v9; // eax
  unsigned int v10; // r14d
  __int64 result; // rax
  const char *v12; // r9
  int v13; // r14d
  int ActiveScenario; // r14d
  unsigned int v15; // r9d
  int active; // r14d
  int v17; // r14d
  int v18; // r14d
  int v19; // r14d
  int v20; // esi
  int v21; // esi
  HANDLE *v22; // [rsp+50h] [rbp-B8h] BYREF
  char v23; // [rsp+58h] [rbp-B0h]
  unsigned int v24; // [rsp+60h] [rbp-A8h] BYREF
  const char *v25; // [rsp+68h] [rbp-A0h] BYREF
  const char *v26; // [rsp+70h] [rbp-98h]
  __int64 v27; // [rsp+78h] [rbp-90h]
  const char *v28; // [rsp+80h] [rbp-88h]
  __int64 v29; // [rsp+88h] [rbp-80h]
  unsigned __int64 v30[2]; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v31; // [rsp+A0h] [rbp-68h]
  unsigned __int64 v32[2]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int64 v33; // [rsp+B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v29 = -2;
  v22 = (HANDLE *)(a1 + 1192);
  v23 = 0;
  v9 = AutoMutexLocker::Lock((AutoMutexLocker *)&v22, a2);
  v10 = v9;
  if ( v9 < 0 )
  {
    if ( v23 )
    {
      if ( *v22 )
        ReleaseMutex(*v22);
    }
    return v10;
  }
  try
  {
    v13 = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)a1);
    if ( v13 >= 0 )
    {
      if ( a3 - 3 <= 1 )
      {
        v24 = 0;
        ActiveScenario = UpdateReserveManager::GetActiveScenario(
                           (UpdateReserveManager *)a1,
                           (enum IUpdateReserveManager::ScenarioId *)&v24);
        if ( ActiveScenario >= 0 )
        {
          v15 = v24;
          if ( !v24 )
          {
            if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
            {
              active = UpdateReserveManager::SetActiveScenario(a1, a3);
              if ( active < 0 )
              {
                if ( v23 && *v22 )
                  ReleaseMutex(*v22);
                return (unsigned int)active;
              }
              v17 = UpdateReserveManager::ClearHardReserve((UpdateReserveManager *)a1);
              if ( v17 < 0 )
              {
                if ( v23 && *v22 )
                  ReleaseMutex(*v22);
                return (unsigned int)v17;
              }
            }
            else
            {
              v18 = UpdateReserveManager::ClearHardReserve((UpdateReserveManager *)a1);
              if ( v18 < 0 )
              {
                if ( v23 && *v22 )
                  ReleaseMutex(*v22);
                return (unsigned int)v18;
              }
              v19 = UpdateReserveManager::SetActiveScenario(a1, a3);
              if ( v19 < 0 )
              {
                if ( v23 && *v22 )
                  ReleaseMutex(*v22);
                return (unsigned int)v19;
              }
            }
            if ( a5 )
              *a5 = a3;
            *(_OWORD *)v30 = 0;
            v31 = 0;
            *(_OWORD *)v32 = 0;
            v33 = 0;
            v20 = (*(__int64 (__fastcall **)(char *, _QWORD, _QWORD, unsigned __int64 *))(*(_QWORD *)a1 + 32LL))(
                    a1,
                    0,
                    a3,
                    v30);
            if ( v20 >= 0 )
            {
              v21 = (*(__int64 (__fastcall **)(char *, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)a1 + 32LL))(
                      a1,
                      0,
                      2,
                      v32);
              if ( v21 >= 0 )
              {
                if ( a4 )
                  *a4 = v30[1];
                CUpdateReserveManagerDiagnostics::ReportBeginScenario(
                  a1 + 1200,
                  a2,
                  a3,
                  a3,
                  v30[0],
                  v31,
                  v32[0],
                  v33,
                  0);
                if ( v23 && *v22 )
                  ReleaseMutex(*v22);
                return 0;
              }
              else
              {
                if ( v23 && *v22 )
                  ReleaseMutex(*v22);
                return (unsigned int)v21;
              }
            }
            else
            {
              if ( v23 && *v22 )
                ReleaseMutex(*v22);
              return (unsigned int)v20;
            }
          }
          if ( a5 )
            *a5 = v24;
          CUpdateReserveManagerDiagnostics::ReportBeginScenario(a1 + 1200, a2, a3, v15, 0, 0, 0, 0, -2146498187);
          v25 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
          v26 = "UpdateReserveManager::BeginScenario";
          v27 = 482;
          v28 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x975))) )";
          RtlReportErrorOrigination(&v25, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469109LL);
          if ( v23 && *v22 )
            ReleaseMutex(*v22);
          result = 2148469109LL;
        }
        else
        {
          if ( v23 && *v22 )
            ReleaseMutex(*v22);
          result = (unsigned int)ActiveScenario;
        }
      }
      else
      {
        CUpdateReserveManagerDiagnostics::ReportBeginScenario(a1 + 1200, a2, a3, 0, 0, 0, 0, 0, -2146498189);
        v25 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v26 = "UpdateReserveManager::BeginScenario";
        v27 = 460;
        v28 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x973))) )";
        RtlReportErrorOrigination(&v25, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469107LL);
        if ( v23 && *v22 )
          ReleaseMutex(*v22);
        result = 2148469107LL;
      }
    }
    else
    {
      if ( v23 && *v22 )
        ReleaseMutex(*v22);
      result = (unsigned int)v13;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x217,
                           (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x180012340  mov     rax, rsp
0x180012343  push    rbx
0x180012344  push    rsi
0x180012345  push    rdi
0x180012346  push    r12
0x180012348  push    r13
0x18001234a  push    r14
0x18001234c  push    r15
0x18001234e  sub     rsp, 0D0h
0x180012355  mov     qword ptr [rax-80h], 0FFFFFFFFFFFFFFFEh
0x18001235d  mov     rax, cs:__security_cookie
0x180012364  xor     rax, rsp
0x180012367  mov     [rsp+108h+var_48], rax
0x18001236f  mov     r15, r9
0x180012372  mov     edi, r8d
0x180012375  mov     r12d, edx
0x180012378  mov     rbx, rcx
0x18001237b  mov     rsi, [rsp+108h+arg_20]
0x180012383  lea     rax, [rcx+4A8h]
0x18001238a  mov     [rsp+108h+var_B8], rax
0x18001238f  xor     r13d, r13d
0x180012392  mov     [rsp+108h+var_B0], r13b
0x180012397  lea     rcx, [rsp+108h+var_B8]; this
0x18001239c  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x1800123a1  mov     r14d, eax
0x1800123a4  test    eax, eax
0x1800123a6  jns     short loc_1800123CA
0x1800123a8  cmp     [rsp+108h+var_B0], r13b
0x1800123ad  jz      short loc_1800123C2
0x1800123af  mov     rcx, [rsp+108h+var_B8]
0x1800123b4  mov     rcx, [rcx]; hMutex
0x1800123b7  test    rcx, rcx
0x1800123ba  jz      short loc_1800123C2
0x1800123bc  call    cs:__imp_ReleaseMutex
0x1800123c2  mov     eax, r14d
0x1800123c5  jmp     loc_18001279B
0x1800123ca  mov     rcx, rbx; this
0x1800123cd  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x1800123d2  mov     r14d, eax
0x1800123d5  test    eax, eax
0x1800123d7  jns     short loc_1800123FB
0x1800123d9  cmp     [rsp+108h+var_B0], r13b
0x1800123de  jz      short loc_1800123F3
0x1800123e0  mov     rcx, [rsp+108h+var_B8]
0x1800123e5  mov     rcx, [rcx]; hMutex
0x1800123e8  test    rcx, rcx
0x1800123eb  jz      short loc_1800123F3
0x1800123ed  call    cs:__imp_ReleaseMutex
0x1800123f3  mov     eax, r14d
0x1800123f6  jmp     loc_18001279B
0x1800123fb  lea     eax, [rdi-3]
0x1800123fe  cmp     eax, 1
0x180012401  jbe     loc_1800124A2
0x180012407  lea     rcx, [rbx+4B0h]; char *
0x18001240e  mov     ebx, 800F0973h
0x180012413  mov     [rsp+108h+var_C8], ebx; int
0x180012417  mov     [rsp+108h+var_D0], r13; unsigned __int64
0x18001241c  mov     [rsp+108h+var_D8], r13; unsigned __int64
0x180012421  mov     [rsp+108h+var_E0], r13; unsigned __int64
0x180012426  mov     [rsp+108h+var_E8], r13; unsigned __int64
0x18001242b  xor     r9d, r9d; unsigned int
0x18001242e  mov     r8d, edi; unsigned int
0x180012431  mov     edx, r12d; unsigned int
0x180012434  call    ?ReportBeginScenario@CUpdateReserveManagerDiagnostics@@SAXPEBDKKK_K111J@Z; CUpdateReserveManagerDiagnostics::ReportBeginScenario(char const *,ulong,ulong,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,long)
0x180012439  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180012440  mov     [rsp+108h+var_A0], rax
0x180012445  lea     rax, aUpdatereservem_13; "UpdateReserveManager::BeginScenario"
0x18001244c  mov     [rsp+108h+var_98], rax
0x180012451  mov     [rsp+108h+var_90], 1CCh
0x18001245a  lea     rax, aScodeUnsignedL_3; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x180012461  mov     [rsp+108h+var_88], rax
0x180012469  mov     r8d, 800F0973h
0x18001246f  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180012476  lea     rcx, [rsp+108h+var_A0]
0x18001247b  call    RtlReportErrorOrigination
0x180012480  nop
0x180012481  cmp     [rsp+108h+var_B0], r13b
0x180012486  jz      short loc_18001249B
0x180012488  mov     rcx, [rsp+108h+var_B8]
0x18001248d  mov     rcx, [rcx]; hMutex
0x180012490  test    rcx, rcx
0x180012493  jz      short loc_18001249B
0x180012495  call    cs:__imp_ReleaseMutex
0x18001249b  mov     eax, ebx
0x18001249d  jmp     loc_18001279B
0x1800124a2  mov     [rsp+108h+var_A8], r13d
0x1800124a7  lea     rdx, [rsp+108h+var_A8]; enum IUpdateReserveManager::ScenarioId *
0x1800124ac  mov     rcx, rbx; this
0x1800124af  call    ?GetActiveScenario@UpdateReserveManager@@AEAAJPEAW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::GetActiveScenario(IUpdateReserveManager::ScenarioId *)
0x1800124b4  mov     r14d, eax
0x1800124b7  test    eax, eax
0x1800124b9  jns     short loc_1800124DD
0x1800124bb  cmp     [rsp+108h+var_B0], r13b
0x1800124c0  jz      short loc_1800124D5
0x1800124c2  mov     rcx, [rsp+108h+var_B8]
0x1800124c7  mov     rcx, [rcx]; hMutex
0x1800124ca  test    rcx, rcx
0x1800124cd  jz      short loc_1800124D5
0x1800124cf  call    cs:__imp_ReleaseMutex
0x1800124d5  mov     eax, r14d
0x1800124d8  jmp     loc_18001279B
0x1800124dd  mov     r9d, [rsp+108h+var_A8]; unsigned int
0x1800124e2  test    r9d, r9d
0x1800124e5  jz      loc_18001258B
0x1800124eb  test    rsi, rsi
0x1800124ee  jz      short loc_1800124F3
0x1800124f0  mov     [rsi], r9d
0x1800124f3  lea     rcx, [rbx+4B0h]; char *
0x1800124fa  mov     ebx, 800F0975h
0x1800124ff  mov     [rsp+108h+var_C8], ebx; int
0x180012503  mov     [rsp+108h+var_D0], r13; unsigned __int64
0x180012508  mov     [rsp+108h+var_D8], r13; unsigned __int64
0x18001250d  mov     [rsp+108h+var_E0], r13; unsigned __int64
0x180012512  mov     [rsp+108h+var_E8], r13; unsigned __int64
0x180012517  mov     r8d, edi; unsigned int
0x18001251a  mov     edx, r12d; unsigned int
0x18001251d  call    ?ReportBeginScenario@CUpdateReserveManagerDiagnostics@@SAXPEBDKKK_K111J@Z; CUpdateReserveManagerDiagnostics::ReportBeginScenario(char const *,ulong,ulong,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,long)
0x180012522  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180012529  mov     [rsp+108h+var_A0], rax
0x18001252e  lea     rax, aUpdatereservem_13; "UpdateReserveManager::BeginScenario"
0x180012535  mov     [rsp+108h+var_98], rax
0x18001253a  mov     [rsp+108h+var_90], 1E2h
0x180012543  lea     rax, aScodeUnsignedL_5; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x18001254a  mov     [rsp+108h+var_88], rax
0x180012552  mov     r8d, 800F0975h
0x180012558  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001255f  lea     rcx, [rsp+108h+var_A0]
0x180012564  call    RtlReportErrorOrigination
0x180012569  nop
0x18001256a  cmp     [rsp+108h+var_B0], r13b
0x18001256f  jz      short loc_180012584
0x180012571  mov     rcx, [rsp+108h+var_B8]
0x180012576  mov     rcx, [rcx]; hMutex
0x180012579  test    rcx, rcx
0x18001257c  jz      short loc_180012584
0x18001257e  call    cs:__imp_ReleaseMutex
0x180012584  mov     eax, ebx
0x180012586  jmp     loc_18001279B
0x18001258b  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180012592  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180012597  mov     rcx, rbx; this
0x18001259a  test    al, al
0x18001259c  jz      short loc_180012603
0x18001259e  mov     edx, edi
0x1800125a0  call    ?SetActiveScenario@UpdateReserveManager@@AEAAJW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::SetActiveScenario(IUpdateReserveManager::ScenarioId)
0x1800125a5  mov     r14d, eax
0x1800125a8  test    eax, eax
0x1800125aa  jns     short loc_1800125CE
0x1800125ac  cmp     [rsp+108h+var_B0], r13b
0x1800125b1  jz      short loc_1800125C6
0x1800125b3  mov     rcx, [rsp+108h+var_B8]
0x1800125b8  mov     rcx, [rcx]; hMutex
0x1800125bb  test    rcx, rcx
0x1800125be  jz      short loc_1800125C6
0x1800125c0  call    cs:__imp_ReleaseMutex
0x1800125c6  mov     eax, r14d
0x1800125c9  jmp     loc_18001279B
0x1800125ce  mov     rcx, rbx; this
0x1800125d1  call    ?ClearHardReserve@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::ClearHardReserve(void)
0x1800125d6  mov     r14d, eax
0x1800125d9  test    eax, eax
0x1800125db  jns     loc_180012664
0x1800125e1  cmp     [rsp+108h+var_B0], r13b
0x1800125e6  jz      short loc_1800125FB
0x1800125e8  mov     rcx, [rsp+108h+var_B8]
0x1800125ed  mov     rcx, [rcx]; hMutex
0x1800125f0  test    rcx, rcx
0x1800125f3  jz      short loc_1800125FB
0x1800125f5  call    cs:__imp_ReleaseMutex
0x1800125fb  mov     eax, r14d
0x1800125fe  jmp     loc_18001279B
0x180012603  call    ?ClearHardReserve@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::ClearHardReserve(void)
0x180012608  mov     r14d, eax
0x18001260b  test    eax, eax
0x18001260d  jns     short loc_180012631
0x18001260f  cmp     [rsp+108h+var_B0], r13b
0x180012614  jz      short loc_180012629
0x180012616  mov     rcx, [rsp+108h+var_B8]
0x18001261b  mov     rcx, [rcx]; hMutex
0x18001261e  test    rcx, rcx
0x180012621  jz      short loc_180012629
0x180012623  call    cs:__imp_ReleaseMutex
0x180012629  mov     eax, r14d
0x18001262c  jmp     loc_18001279B
0x180012631  mov     edx, edi
0x180012633  mov     rcx, rbx
0x180012636  call    ?SetActiveScenario@UpdateReserveManager@@AEAAJW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::SetActiveScenario(IUpdateReserveManager::ScenarioId)
0x18001263b  mov     r14d, eax
0x18001263e  test    eax, eax
0x180012640  jns     short loc_180012664
0x180012642  cmp     [rsp+108h+var_B0], r13b
0x180012647  jz      short loc_18001265C
0x180012649  mov     rcx, [rsp+108h+var_B8]
0x18001264e  mov     rcx, [rcx]; hMutex
0x180012651  test    rcx, rcx
0x180012654  jz      short loc_18001265C
0x180012656  call    cs:__imp_ReleaseMutex
0x18001265c  mov     eax, r14d
0x18001265f  jmp     loc_18001279B
0x180012664  test    rsi, rsi
0x180012667  jz      short loc_18001266B
0x180012669  mov     [rsi], edi
0x18001266b  xorps   xmm0, xmm0
0x18001266e  xor     eax, eax
0x180012670  movups  xmmword ptr [rsp+108h+var_78], xmm0
0x180012678  mov     [rsp+108h+var_68], rax
0x180012680  xorps   xmm1, xmm1
0x180012683  movups  xmmword ptr [rsp+108h+var_60], xmm1
0x18001268b  mov     [rsp+108h+var_50], rax
0x180012693  mov     rax, [rbx]
0x180012696  lea     r9, [rsp+108h+var_78]
0x18001269e  mov     r8d, edi
0x1800126a1  xor     edx, edx
0x1800126a3  mov     rcx, rbx
0x1800126a6  mov     rax, [rax+20h]
0x1800126aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126af  mov     esi, eax
0x1800126b1  test    eax, eax
0x1800126b3  jns     short loc_1800126D6
0x1800126b5  cmp     [rsp+108h+var_B0], r13b
0x1800126ba  jz      short loc_1800126CF
0x1800126bc  mov     rcx, [rsp+108h+var_B8]
0x1800126c1  mov     rcx, [rcx]; hMutex
0x1800126c4  test    rcx, rcx
0x1800126c7  jz      short loc_1800126CF
0x1800126c9  call    cs:__imp_ReleaseMutex
0x1800126cf  mov     eax, esi
0x1800126d1  jmp     loc_18001279B
0x1800126d6  mov     rax, [rbx]
0x1800126d9  lea     r9, [rsp+108h+var_60]
0x1800126e1  xor     edx, edx
0x1800126e3  lea     r8d, [rdx+2]
0x1800126e7  mov     rcx, rbx
0x1800126ea  mov     rax, [rax+20h]
0x1800126ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800126f3  mov     esi, eax
0x1800126f5  test    eax, eax
0x1800126f7  jns     short loc_18001271A
0x1800126f9  cmp     [rsp+108h+var_B0], r13b
0x1800126fe  jz      short loc_180012713
0x180012700  mov     rcx, [rsp+108h+var_B8]
0x180012705  mov     rcx, [rcx]; hMutex
0x180012708  test    rcx, rcx
0x18001270b  jz      short loc_180012713
0x18001270d  call    cs:__imp_ReleaseMutex
0x180012713  mov     eax, esi
0x180012715  jmp     loc_18001279B
0x18001271a  test    r15, r15
0x18001271d  jz      short loc_18001272A
0x18001271f  mov     rax, [rsp+108h+var_78+8]
0x180012727  mov     [r15], rax
0x18001272a  lea     rcx, [rbx+4B0h]; char *
0x180012731  mov     [rsp+108h+var_C8], r13d; int
0x180012736  mov     rax, [rsp+108h+var_50]
0x18001273e  mov     [rsp+108h+var_D0], rax; unsigned __int64
0x180012743  mov     rax, [rsp+108h+var_60]
0x18001274b  mov     [rsp+108h+var_D8], rax; unsigned __int64
0x180012750  mov     rax, [rsp+108h+var_68]
0x180012758  mov     [rsp+108h+var_E0], rax; unsigned __int64
0x18001275d  mov     rax, [rsp+108h+var_78]
0x180012765  mov     [rsp+108h+var_E8], rax; unsigned __int64
0x18001276a  mov     r9d, edi; unsigned int
0x18001276d  mov     r8d, edi; unsigned int
0x180012770  mov     edx, r12d; unsigned int
0x180012773  call    ?ReportBeginScenario@CUpdateReserveManagerDiagnostics@@SAXPEBDKKK_K111J@Z; CUpdateReserveManagerDiagnostics::ReportBeginScenario(char const *,ulong,ulong,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,long)
0x180012778  nop
0x180012779  cmp     [rsp+108h+var_B0], r13b
0x18001277e  jz      short loc_180012793
0x180012780  mov     rax, [rsp+108h+var_B8]
0x180012785  mov     rcx, [rax]; hMutex
0x180012788  test    rcx, rcx
0x18001278b  jz      short loc_180012793
0x18001278d  call    cs:__imp_ReleaseMutex
0x180012793  xor     eax, eax
0x180012795  jmp     short loc_18001279B
0x180012797  mov     eax, [rsp+108h+var_A8]
0x18001279b  mov     rcx, [rsp+108h+var_48]
0x1800127a3  xor     rcx, rsp; StackCookie
0x1800127a6  call    __security_check_cookie
0x1800127ab  add     rsp, 0D0h
0x1800127b2  pop     r15
0x1800127b4  pop     r14
0x1800127b6  pop     r13
0x1800127b8  pop     r12
0x1800127ba  pop     rdi
0x1800127bb  pop     rsi
0x1800127bc  pop     rbx
0x1800127bd  retn
```
