# UpdateReserveManager::EndScenario(IUpdateReserveManager::EndScenarioFlags,IUpdateReserveManager::ScenarioId,IUpdateReserveManager::ScenarioId *)

- ea: `0x1800155e0`
- end: `0x180015ac9`
- name: `?EndScenario@UpdateReserveManager@@UEAAJW4EndScenarioFlags@IUpdateReserveManager@@W4ScenarioId@3@PEAW443@@Z`
- size: `1257`
- prototype: `__int64 __fastcall(char *, unsigned int, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `14`
- tags: `registry_config, installer_update`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x1800133c4`
- `0x1800155e0`
- `0x180015ad0`
- `0x180015e20`
- `0x180016cac`
- `0x180019634`
- `0x18001a8f0`
- `0x18001d868`
- `0x18001fa18`
- `0x180020200`
- `0x180021e80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015652`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015683`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015730`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001576a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015827`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015857`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001588a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800158cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001590c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015993`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800159d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015a99`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015652`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015683`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015730`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001576a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015827`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015857`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001588a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800158cc`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001590c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015993`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800159d7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015a99`

## string_xrefs

- `0x1800156d4`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800157cb`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800156e0`: `UpdateReserveManager::EndScenario`
- `0x1800157d7`: `UpdateReserveManager::EndScenario`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::EndScenario(char *a1, unsigned int a2, unsigned int a3, unsigned int *a4)
{
  int v8; // eax
  unsigned int v9; // r14d
  __int64 result; // rax
  const char *v11; // r9
  int v12; // r14d
  int ActiveScenario; // r14d
  unsigned int v14; // r9d
  int v15; // r14d
  int active; // r14d
  int PassedPolicyValue; // edi
  int v18; // r14d
  int v19; // edi
  int v20; // edi
  int v21; // edi
  char IsEnabled; // al
  const char *v23; // rcx
  unsigned int v24; // [rsp+50h] [rbp-B8h] BYREF
  HANDLE *v25; // [rsp+58h] [rbp-B0h] BYREF
  char v26; // [rsp+60h] [rbp-A8h]
  const char *v27; // [rsp+68h] [rbp-A0h] BYREF
  const char *v28; // [rsp+70h] [rbp-98h]
  __int64 v29; // [rsp+78h] [rbp-90h]
  const char *v30; // [rsp+80h] [rbp-88h]
  __int64 v31; // [rsp+88h] [rbp-80h]
  unsigned __int64 v32[2]; // [rsp+90h] [rbp-78h] BYREF
  unsigned __int64 v33; // [rsp+A0h] [rbp-68h]
  unsigned __int64 v34[2]; // [rsp+A8h] [rbp-60h] BYREF
  unsigned __int64 v35; // [rsp+B8h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  v31 = -2;
  v25 = (HANDLE *)(a1 + 1192);
  v26 = 0;
  v8 = AutoMutexLocker::Lock((AutoMutexLocker *)&v25, a2);
  v9 = v8;
  if ( v8 < 0 )
  {
    if ( v26 )
    {
      if ( *v25 )
        ReleaseMutex(*v25);
    }
    return v9;
  }
  try
  {
    v12 = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)a1);
    if ( v12 >= 0 )
    {
      if ( a3 - 3 <= 1 )
      {
        v24 = 0;
        ActiveScenario = UpdateReserveManager::GetActiveScenario(
                           (UpdateReserveManager *)a1,
                           (enum IUpdateReserveManager::ScenarioId *)&v24);
        if ( ActiveScenario >= 0 )
        {
          v14 = v24;
          if ( !v24 || v24 == a3 )
          {
            v15 = UpdateReserveManager::ClearHardReserve((UpdateReserveManager *)a1);
            if ( v15 >= 0 )
            {
              active = UpdateReserveManager::SetActiveScenario(a1, 0);
              if ( active >= 0 )
              {
                if ( a4 )
                  *a4 = 0;
                v24 = 0;
                PassedPolicyValue = UpdateReserveManager::GetPassedPolicyValue((UpdateReserveManager *)a1, &v24);
                if ( PassedPolicyValue >= 0 )
                {
                  v18 = 0;
                  if ( v24 )
                  {
                    v19 = UpdateReserveManager::InitializeReservesInternal(a1, 2);
                    if ( v19 < 0 )
                    {
                      if ( v26 && *v25 )
                        ReleaseMutex(*v25);
                      return (unsigned int)v19;
                    }
                    if ( wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl) )
                      v18 = UpdateReserveManager::TagSnapshots((UpdateReserveManager *)a1);
                  }
                  *(_OWORD *)v34 = 0;
                  v35 = 0;
                  *(_OWORD *)v32 = 0;
                  v33 = 0;
                  v20 = (*(__int64 (__fastcall **)(char *, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)a1 + 32LL))(
                          a1,
                          0,
                          1,
                          v34);
                  if ( v20 >= 0 )
                  {
                    v21 = (*(__int64 (__fastcall **)(char *, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)a1 + 32LL))(
                            a1,
                            0,
                            2,
                            v32);
                    if ( v21 >= 0 )
                    {
                      IsEnabled = wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled((__int64)`wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl'::`2'::impl);
                      v23 = a1 + 1200;
                      if ( IsEnabled )
                        CUpdateReserveManagerDiagnostics::ReportEndScenario(
                          v23,
                          a2,
                          a3,
                          0,
                          v34[0],
                          v35,
                          v32[0],
                          v33,
                          0,
                          v18);
                      else
                        CUpdateReserveManagerDiagnostics::ReportEndScenario(
                          v23,
                          a2,
                          a3,
                          0,
                          v34[0],
                          v35,
                          v32[0],
                          v33,
                          0,
                          0);
                      if ( v26 && *v25 )
                        ReleaseMutex(*v25);
                      return 0;
                    }
                    else
                    {
                      if ( v26 && *v25 )
                        ReleaseMutex(*v25);
                      return (unsigned int)v21;
                    }
                  }
                  else
                  {
                    if ( v26 && *v25 )
                      ReleaseMutex(*v25);
                    return (unsigned int)v20;
                  }
                }
                if ( v26 && *v25 )
                  ReleaseMutex(*v25);
                result = (unsigned int)PassedPolicyValue;
              }
              else
              {
                if ( v26 && *v25 )
                  ReleaseMutex(*v25);
                result = (unsigned int)active;
              }
            }
            else
            {
              if ( v26 && *v25 )
                ReleaseMutex(*v25);
              result = (unsigned int)v15;
            }
          }
          else
          {
            if ( a4 )
              *a4 = v24;
            CUpdateReserveManagerDiagnostics::ReportEndScenario(a1 + 1200, a2, a3, v14, 0, 0, 0, 0, -2146498187, 0);
            v27 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v28 = "UpdateReserveManager::EndScenario";
            v29 = 591;
            v30 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x975))) )";
            RtlReportErrorOrigination(&v27, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469109LL);
            if ( v26 && *v25 )
              ReleaseMutex(*v25);
            result = 2148469109LL;
          }
        }
        else
        {
          if ( v26 && *v25 )
            ReleaseMutex(*v25);
          result = (unsigned int)ActiveScenario;
        }
      }
      else
      {
        CUpdateReserveManagerDiagnostics::ReportEndScenario(a1 + 1200, a2, a3, 0, 0, 0, 0, 0, -2146498189, 0);
        v27 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v28 = "UpdateReserveManager::EndScenario";
        v29 = 567;
        v30 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x973))) )";
        RtlReportErrorOrigination(&v27, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469107LL);
        if ( v26 && *v25 )
          ReleaseMutex(*v25);
        result = 2148469107LL;
      }
    }
    else
    {
      if ( v26 && *v25 )
        ReleaseMutex(*v25);
      result = (unsigned int)v12;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x294,
                           (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x1800155e0  mov     rax, rsp
0x1800155e3  push    rbx
0x1800155e4  push    rsi
0x1800155e5  push    rdi
0x1800155e6  push    r12
0x1800155e8  push    r14
0x1800155ea  push    r15
0x1800155ec  sub     rsp, 0D8h
0x1800155f3  mov     qword ptr [rax-80h], 0FFFFFFFFFFFFFFFEh
0x1800155fb  mov     rax, cs:__security_cookie
0x180015602  xor     rax, rsp
0x180015605  mov     [rsp+108h+var_48], rax
0x18001560d  mov     rdi, r9
0x180015610  mov     esi, r8d
0x180015613  mov     r15d, edx
0x180015616  mov     rbx, rcx
0x180015619  lea     rax, [rcx+4A8h]
0x180015620  mov     [rsp+108h+var_B0], rax
0x180015625  xor     r12d, r12d
0x180015628  mov     [rsp+108h+var_A8], r12b
0x18001562d  lea     rcx, [rsp+108h+var_B0]; this
0x180015632  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x180015637  mov     r14d, eax
0x18001563a  test    eax, eax
0x18001563c  jns     short loc_180015660
0x18001563e  cmp     [rsp+108h+var_A8], r12b
0x180015643  jz      short loc_180015658
0x180015645  mov     rcx, [rsp+108h+var_B0]
0x18001564a  mov     rcx, [rcx]; hMutex
0x18001564d  test    rcx, rcx
0x180015650  jz      short loc_180015658
0x180015652  call    cs:__imp_ReleaseMutex
0x180015658  mov     eax, r14d
0x18001565b  jmp     loc_180015AA7
0x180015660  mov     rcx, rbx; this
0x180015663  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180015668  mov     r14d, eax
0x18001566b  test    eax, eax
0x18001566d  jns     short loc_180015691
0x18001566f  cmp     [rsp+108h+var_A8], r12b
0x180015674  jz      short loc_180015689
0x180015676  mov     rcx, [rsp+108h+var_B0]
0x18001567b  mov     rcx, [rcx]; hMutex
0x18001567e  test    rcx, rcx
0x180015681  jz      short loc_180015689
0x180015683  call    cs:__imp_ReleaseMutex
0x180015689  mov     eax, r14d
0x18001568c  jmp     loc_180015AA7
0x180015691  lea     eax, [rsi-3]
0x180015694  cmp     eax, 1
0x180015697  jbe     loc_18001573D
0x18001569d  lea     rcx, [rbx+4B0h]; char *
0x1800156a4  mov     [rsp+108h+var_C0], r12d; int
0x1800156a9  mov     ebx, 800F0973h
0x1800156ae  mov     [rsp+108h+var_C8], ebx; int
0x1800156b2  mov     [rsp+108h+var_D0], r12; unsigned __int64
0x1800156b7  mov     [rsp+108h+var_D8], r12; unsigned __int64
0x1800156bc  mov     [rsp+108h+var_E0], r12; unsigned __int64
0x1800156c1  mov     [rsp+108h+var_E8], r12; unsigned __int64
0x1800156c6  xor     r9d, r9d; unsigned int
0x1800156c9  mov     r8d, esi; unsigned int
0x1800156cc  mov     edx, r15d; unsigned int
0x1800156cf  call    ?ReportEndScenario@CUpdateReserveManagerDiagnostics@@SAXPEBDKKK_K111JJ@Z; CUpdateReserveManagerDiagnostics::ReportEndScenario(char const *,ulong,ulong,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,long,long)
0x1800156d4  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800156db  mov     [rsp+108h+var_A0], rax
0x1800156e0  lea     rax, aUpdatereservem_30; "UpdateReserveManager::EndScenario"
0x1800156e7  mov     [rsp+108h+var_98], rax
0x1800156ec  mov     [rsp+108h+var_90], 237h
0x1800156f5  lea     rax, aScodeUnsignedL_3; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x1800156fc  mov     [rsp+108h+var_88], rax
0x180015704  mov     r8d, 800F0973h
0x18001570a  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180015711  lea     rcx, [rsp+108h+var_A0]
0x180015716  call    RtlReportErrorOrigination
0x18001571b  nop
0x18001571c  cmp     [rsp+108h+var_A8], r12b
0x180015721  jz      short loc_180015736
0x180015723  mov     rcx, [rsp+108h+var_B0]
0x180015728  mov     rcx, [rcx]; hMutex
0x18001572b  test    rcx, rcx
0x18001572e  jz      short loc_180015736
0x180015730  call    cs:__imp_ReleaseMutex
0x180015736  mov     eax, ebx
0x180015738  jmp     loc_180015AA7
0x18001573d  mov     [rsp+108h+var_B8], r12d
0x180015742  lea     rdx, [rsp+108h+var_B8]; enum IUpdateReserveManager::ScenarioId *
0x180015747  mov     rcx, rbx; this
0x18001574a  call    ?GetActiveScenario@UpdateReserveManager@@AEAAJPEAW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::GetActiveScenario(IUpdateReserveManager::ScenarioId *)
0x18001574f  mov     r14d, eax
0x180015752  test    eax, eax
0x180015754  jns     short loc_180015778
0x180015756  cmp     [rsp+108h+var_A8], r12b
0x18001575b  jz      short loc_180015770
0x18001575d  mov     rcx, [rsp+108h+var_B0]
0x180015762  mov     rcx, [rcx]; hMutex
0x180015765  test    rcx, rcx
0x180015768  jz      short loc_180015770
0x18001576a  call    cs:__imp_ReleaseMutex
0x180015770  mov     eax, r14d
0x180015773  jmp     loc_180015AA7
0x180015778  mov     r9d, [rsp+108h+var_B8]; unsigned int
0x18001577d  test    r9d, r9d
0x180015780  jz      loc_180015834
0x180015786  cmp     r9d, esi
0x180015789  jz      loc_180015834
0x18001578f  test    rdi, rdi
0x180015792  jz      short loc_180015797
0x180015794  mov     [rdi], r9d
0x180015797  lea     rcx, [rbx+4B0h]; char *
0x18001579e  mov     [rsp+108h+var_C0], r12d; int
0x1800157a3  mov     ebx, 800F0975h
0x1800157a8  mov     [rsp+108h+var_C8], ebx; int
0x1800157ac  mov     [rsp+108h+var_D0], r12; unsigned __int64
0x1800157b1  mov     [rsp+108h+var_D8], r12; unsigned __int64
0x1800157b6  mov     [rsp+108h+var_E0], r12; unsigned __int64
0x1800157bb  mov     [rsp+108h+var_E8], r12; unsigned __int64
0x1800157c0  mov     r8d, esi; unsigned int
0x1800157c3  mov     edx, r15d; unsigned int
0x1800157c6  call    ?ReportEndScenario@CUpdateReserveManagerDiagnostics@@SAXPEBDKKK_K111JJ@Z; CUpdateReserveManagerDiagnostics::ReportEndScenario(char const *,ulong,ulong,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,long,long)
0x1800157cb  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800157d2  mov     [rsp+108h+var_A0], rax
0x1800157d7  lea     rax, aUpdatereservem_30; "UpdateReserveManager::EndScenario"
0x1800157de  mov     [rsp+108h+var_98], rax
0x1800157e3  mov     [rsp+108h+var_90], 24Fh
0x1800157ec  lea     rax, aScodeUnsignedL_5; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x1800157f3  mov     [rsp+108h+var_88], rax
0x1800157fb  mov     r8d, 800F0975h
0x180015801  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180015808  lea     rcx, [rsp+108h+var_A0]
0x18001580d  call    RtlReportErrorOrigination
0x180015812  nop
0x180015813  cmp     [rsp+108h+var_A8], r12b
0x180015818  jz      short loc_18001582D
0x18001581a  mov     rcx, [rsp+108h+var_B0]
0x18001581f  mov     rcx, [rcx]; hMutex
0x180015822  test    rcx, rcx
0x180015825  jz      short loc_18001582D
0x180015827  call    cs:__imp_ReleaseMutex
0x18001582d  mov     eax, ebx
0x18001582f  jmp     loc_180015AA7
0x180015834  mov     rcx, rbx; this
0x180015837  call    ?ClearHardReserve@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::ClearHardReserve(void)
0x18001583c  mov     r14d, eax
0x18001583f  test    eax, eax
0x180015841  jns     short loc_180015865
0x180015843  cmp     [rsp+108h+var_A8], r12b
0x180015848  jz      short loc_18001585D
0x18001584a  mov     rcx, [rsp+108h+var_B0]
0x18001584f  mov     rcx, [rcx]; hMutex
0x180015852  test    rcx, rcx
0x180015855  jz      short loc_18001585D
0x180015857  call    cs:__imp_ReleaseMutex
0x18001585d  mov     eax, r14d
0x180015860  jmp     loc_180015AA7
0x180015865  xor     edx, edx
0x180015867  mov     rcx, rbx
0x18001586a  call    ?SetActiveScenario@UpdateReserveManager@@AEAAJW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::SetActiveScenario(IUpdateReserveManager::ScenarioId)
0x18001586f  mov     r14d, eax
0x180015872  test    eax, eax
0x180015874  jns     short loc_180015898
0x180015876  cmp     [rsp+108h+var_A8], r12b
0x18001587b  jz      short loc_180015890
0x18001587d  mov     rcx, [rsp+108h+var_B0]
0x180015882  mov     rcx, [rcx]; hMutex
0x180015885  test    rcx, rcx
0x180015888  jz      short loc_180015890
0x18001588a  call    cs:__imp_ReleaseMutex
0x180015890  mov     eax, r14d
0x180015893  jmp     loc_180015AA7
0x180015898  test    rdi, rdi
0x18001589b  jz      short loc_1800158A0
0x18001589d  mov     [rdi], r12d
0x1800158a0  mov     [rsp+108h+var_B8], r12d
0x1800158a5  lea     rdx, [rsp+108h+var_B8]; unsigned int *
0x1800158aa  mov     rcx, rbx; this
0x1800158ad  call    ?GetPassedPolicyValue@UpdateReserveManager@@AEAAJPEAK@Z; UpdateReserveManager::GetPassedPolicyValue(ulong *)
0x1800158b2  mov     edi, eax
0x1800158b4  test    eax, eax
0x1800158b6  jns     short loc_1800158D9
0x1800158b8  cmp     [rsp+108h+var_A8], r12b
0x1800158bd  jz      short loc_1800158D2
0x1800158bf  mov     rcx, [rsp+108h+var_B0]
0x1800158c4  mov     rcx, [rcx]; hMutex
0x1800158c7  test    rcx, rcx
0x1800158ca  jz      short loc_1800158D2
0x1800158cc  call    cs:__imp_ReleaseMutex
0x1800158d2  mov     eax, edi
0x1800158d4  jmp     loc_180015AA7
0x1800158d9  mov     r14d, r12d
0x1800158dc  cmp     [rsp+108h+var_B8], r12d
0x1800158e1  jz      short loc_180015934
0x1800158e3  xor     r8d, r8d
0x1800158e6  lea     edx, [r8+2]
0x1800158ea  mov     rcx, rbx
0x1800158ed  call    ?InitializeReservesInternal@UpdateReserveManager@@AEAAJW4InitializeReservesFlags@IUpdateReserveManager@@PEA_N@Z; UpdateReserveManager::InitializeReservesInternal(IUpdateReserveManager::InitializeReservesFlags,bool *)
0x1800158f2  mov     edi, eax
0x1800158f4  test    eax, eax
0x1800158f6  jns     short loc_180015919
0x1800158f8  cmp     [rsp+108h+var_A8], r12b
0x1800158fd  jz      short loc_180015912
0x1800158ff  mov     rcx, [rsp+108h+var_B0]
0x180015904  mov     rcx, [rcx]; hMutex
0x180015907  test    rcx, rcx
0x18001590a  jz      short loc_180015912
0x18001590c  call    cs:__imp_ReleaseMutex
0x180015912  mov     eax, edi
0x180015914  jmp     loc_180015AA7
0x180015919  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x180015920  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x180015925  test    al, al
0x180015927  jz      short loc_180015934
0x180015929  mov     rcx, rbx; this
0x18001592c  call    ?TagSnapshots@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::TagSnapshots(void)
0x180015931  mov     r14d, eax
0x180015934  xorps   xmm0, xmm0
0x180015937  xor     eax, eax
0x180015939  movups  xmmword ptr [rsp+108h+var_60], xmm0
0x180015941  mov     [rsp+108h+var_50], rax
0x180015949  xorps   xmm1, xmm1
0x18001594c  movups  xmmword ptr [rsp+108h+var_78], xmm1
0x180015954  mov     [rsp+108h+var_68], rax
0x18001595c  mov     rax, [rbx]
0x18001595f  lea     r9, [rsp+108h+var_60]
0x180015967  xor     edx, edx
0x180015969  lea     r8d, [rdx+1]
0x18001596d  mov     rcx, rbx
0x180015970  mov     rax, [rax+20h]
0x180015974  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015979  mov     edi, eax
0x18001597b  test    eax, eax
0x18001597d  jns     short loc_1800159A0
0x18001597f  cmp     [rsp+108h+var_A8], r12b
0x180015984  jz      short loc_180015999
0x180015986  mov     rcx, [rsp+108h+var_B0]
0x18001598b  mov     rcx, [rcx]; hMutex
0x18001598e  test    rcx, rcx
0x180015991  jz      short loc_180015999
0x180015993  call    cs:__imp_ReleaseMutex
0x180015999  mov     eax, edi
0x18001599b  jmp     loc_180015AA7
0x1800159a0  mov     rax, [rbx]
0x1800159a3  lea     r9, [rsp+108h+var_78]
0x1800159ab  xor     edx, edx
0x1800159ad  lea     r8d, [rdx+2]
0x1800159b1  mov     rcx, rbx
0x1800159b4  mov     rax, [rax+20h]
0x1800159b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800159bd  mov     edi, eax
0x1800159bf  test    eax, eax
0x1800159c1  jns     short loc_1800159E4
0x1800159c3  cmp     [rsp+108h+var_A8], r12b
0x1800159c8  jz      short loc_1800159DD
0x1800159ca  mov     rcx, [rsp+108h+var_B0]
0x1800159cf  mov     rcx, [rcx]; hMutex
0x1800159d2  test    rcx, rcx
0x1800159d5  jz      short loc_1800159DD
0x1800159d7  call    cs:__imp_ReleaseMutex
0x1800159dd  mov     eax, edi
0x1800159df  jmp     loc_180015AA7
0x1800159e4  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA> `wil::Feature<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::GetImpl(void)'::`2'::impl
0x1800159eb  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_PointInTimeRestore_GA>::__private_IsEnabled(void)
0x1800159f0  lea     rcx, [rbx+4B0h]; char *
0x1800159f7  xor     r9d, r9d; unsigned int
0x1800159fa  mov     r8d, esi; unsigned int
0x1800159fd  mov     edx, r15d; unsigned int
0x180015a00  test    al, al
0x180015a02  mov     rax, [rsp+108h+var_68]
0x180015a0a  jz      short loc_180015A49
0x180015a0c  mov     [rsp+108h+var_C0], r14d; int
0x180015a11  mov     [rsp+108h+var_C8], r12d; int
0x180015a16  mov     [rsp+108h+var_D0], rax; unsigned __int64
0x180015a1b  mov     rax, [rsp+108h+var_78]
0x180015a23  mov     [rsp+108h+var_D8], rax; unsigned __int64
0x180015a28  mov     rax, [rsp+108h+var_50]
0x180015a30  mov     [rsp+108h+var_E0], rax; unsigned __int64
0x180015a35  mov     rax, [rsp+108h+var_60]
0x180015a3d  mov     [rsp+108h+var_E8], rax; unsigned __int64
0x180015a42  call    ?ReportEndScenario@CUpdateReserveManagerDiagnostics@@SAXPEBDKKK_K111JJ@Z; CUpdateReserveManagerDiagnostics::ReportEndScenario(char const *,ulong,ulong,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,long,long)
0x180015a47  jmp     short loc_180015A85
0x180015a49  mov     [rsp+108h+var_C0], r12d; int
0x180015a4e  mov     [rsp+108h+var_C8], r12d; int
0x180015a53  mov     [rsp+108h+var_D0], rax; unsigned __int64
0x180015a58  mov     rax, [rsp+108h+var_78]
0x180015a60  mov     [rsp+108h+var_D8], rax; unsigned __int64
0x180015a65  mov     rax, [rsp+108h+var_50]
0x180015a6d  mov     [rsp+108h+var_E0], rax; unsigned __int64
0x180015a72  mov     rax, [rsp+108h+var_60]
0x180015a7a  mov     [rsp+108h+var_E8], rax; unsigned __int64
0x180015a7f  call    ?ReportEndScenario@CUpdateReserveManagerDiagnostics@@SAXPEBDKKK_K111JJ@Z; CUpdateReserveManagerDiagnostics::ReportEndScenario(char const *,ulong,ulong,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,long,long)
0x180015a84  nop
0x180015a85  cmp     [rsp+108h+var_A8], r12b
0x180015a8a  jz      short loc_180015A9F
0x180015a8c  mov     rax, [rsp+108h+var_B0]
0x180015a91  mov     rcx, [rax]; hMutex
0x180015a94  test    rcx, rcx
0x180015a97  jz      short loc_180015A9F
0x180015a99  call    cs:__imp_ReleaseMutex
0x180015a9f  xor     eax, eax
0x180015aa1  jmp     short loc_180015AA7
0x180015aa3  mov     eax, [rsp+108h+var_B8]
  ... truncated ...
```
