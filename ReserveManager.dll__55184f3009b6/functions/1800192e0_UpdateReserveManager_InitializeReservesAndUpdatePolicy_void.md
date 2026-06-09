# UpdateReserveManager::InitializeReservesAndUpdatePolicy(void)

- ea: `0x1800192e0`
- end: `0x18001962e`
- name: `?InitializeReservesAndUpdatePolicy@UpdateReserveManager@@QEAAJXZ`
- size: `846`
- prototype: `__int64 __fastcall(UpdateReserveManager *this, unsigned int)`
- caller_count: `2`
- callee_count: `14`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000cad0`
- `0x180015240`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180012bf0`
- `0x180013770`
- `0x180015ad0`
- `0x180015e20`
- `0x180016cac`
- `0x1800192e0`
- `0x18001a8f0`
- `0x18001e330`
- `0x18001fd60`
- `0x180020778`
- `0x180021a28`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019343`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019372`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019488`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800194ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001953b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019580`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800195af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800195db`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019602`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019343`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019372`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019488`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800194ec`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001953b`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019580`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800195af`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800195db`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180019602`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180019412`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180019412`

## string_xrefs

- `0x18001941e`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001942a`: `UpdateReserveManager::ReevaluateReservePolicies`
- `0x18001943f`: `::RegSetKeyValueW(m_SoftwareKey, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"PassedPolicy", ( 4ul ), &NewPassedPolicyValue, sizeof(NewPassedPolicyValue))`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::InitializeReservesAndUpdatePolicy(UpdateReserveManager *this, unsigned int a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  __int64 result; // rax
  int v6; // ebx
  const char *v7; // r9
  int PassedPolicyValue; // ebx
  bool v9; // si
  bool v10; // bl
  bool v11; // si
  int v12; // ebx
  int ActiveScenario; // ebx
  int v14; // ebx
  int v15; // ebx
  int inited; // ebx
  HANDLE *v17; // [rsp+30h] [rbp-88h] BYREF
  char v18; // [rsp+38h] [rbp-80h]
  unsigned int v19; // [rsp+40h] [rbp-78h] BYREF
  _QWORD v20[5]; // [rsp+48h] [rbp-70h] BYREF
  bool v21; // [rsp+70h] [rbp-48h] BYREF
  unsigned int v22; // [rsp+74h] [rbp-44h] BYREF
  BOOL Data; // [rsp+78h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v20[4] = -2;
  v17 = (HANDLE *)((char *)this + 1192);
  v18 = 0;
  v3 = AutoMutexLocker::Lock((AutoMutexLocker *)&v17, a2);
  v4 = v3;
  if ( v3 < 0 )
  {
    if ( v18 )
    {
      if ( *v17 )
        ReleaseMutex(*v17);
    }
    return v4;
  }
  try
  {
    v6 = UpdateReserveManager::EnsureNotInSafeMode(this);
    if ( v6 >= 0 )
    {
      PassedPolicyValue = UpdateReserveManager::EnsureNotInSafeMode(this);
      if ( PassedPolicyValue >= 0 )
      {
        v19 = 0;
        PassedPolicyValue = UpdateReserveManager::GetPassedPolicyValue(this, &v19);
        if ( PassedPolicyValue >= 0 )
        {
          v9 = v19 != 0;
          v22 = 0;
          v21 = 0;
          PassedPolicyValue = UpdateReserveManager::CheckReservePolicies(
                                this,
                                (enum UpdateReserveManager::CheckReservePoliciesDisposition *)&v22,
                                &v21);
          if ( PassedPolicyValue >= 0 )
          {
            Data = v21;
            PassedPolicyValue = RegSetKeyValueW(
                                  *((HKEY *)this + 13),
                                  L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                                  L"PassedPolicy",
                                  4u,
                                  &Data,
                                  4u);
            if ( !PassedPolicyValue )
            {
              v10 = v21;
              v11 = v9 != v21;
              CUpdateReserveManagerDiagnostics::ReportReevaluatePolicy((const char *)this + 1200, v21, v11, v22);
              if ( v10 )
              {
                v12 = (*(__int64 (__fastcall **)(UpdateReserveManager *, __int64))(*(_QWORD *)this + 8LL))(this, 1);
                if ( v12 < 0 )
                {
                  if ( v18 && *v17 )
                    ReleaseMutex(*v17);
                  return (unsigned int)v12;
                }
              }
              else
              {
                if ( v11 )
                {
                  UpdateReserveManager::UntagFilesInReserve(this, 1u);
                  v22 = 0;
                  ActiveScenario = UpdateReserveManager::GetActiveScenario(
                                     (HKEY *)this,
                                     (enum IUpdateReserveManager::ScenarioId *)&v22);
                  if ( ActiveScenario < 0 )
                  {
                    if ( v18 && *v17 )
                      ReleaseMutex(*v17);
                    return (unsigned int)ActiveScenario;
                  }
                  if ( v22 )
                  {
                    v14 = (*(__int64 (__fastcall **)(UpdateReserveManager *, _QWORD, _QWORD, _QWORD))(*(_QWORD *)this + 24LL))(
                            this,
                            0,
                            v22,
                            0);
                    if ( v14 < 0 )
                    {
                      if ( v18 && *v17 )
                        ReleaseMutex(*v17);
                      return (unsigned int)v14;
                    }
                  }
                  v15 = UpdateReserveManager::SetReservesToZero(this);
                  if ( v15 < 0 )
                  {
                    if ( v18 && *v17 )
                      ReleaseMutex(*v17);
                    return (unsigned int)v15;
                  }
                }
                inited = UpdateReserveManager::ClearTemporaryReserveInitParams((HKEY *)this);
                if ( inited < 0 )
                {
                  if ( v18 && *v17 )
                    ReleaseMutex(*v17);
                  return (unsigned int)inited;
                }
              }
              UpdateReserveManager::ValidateSoftReserveParenting(this);
              if ( v18 && *v17 )
                ReleaseMutex(*v17);
              return 0;
            }
            v20[0] = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
            v20[1] = "UpdateReserveManager::ReevaluateReservePolicies";
            v20[2] = 3117;
            v20[3] = "::RegSetKeyValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\", L\""
                     "PassedPolicy\", ( 4ul ), &NewPassedPolicyValue, sizeof(NewPassedPolicyValue))";
            if ( PassedPolicyValue > 0 )
              PassedPolicyValue = (unsigned __int16)PassedPolicyValue | 0x80070000;
            RtlReportErrorOrigination(v20, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)PassedPolicyValue);
          }
        }
      }
      if ( v18 && *v17 )
        ReleaseMutex(*v17);
      result = (unsigned int)PassedPolicyValue;
    }
    else
    {
      if ( v18 && *v17 )
        ReleaseMutex(*v17);
      result = (unsigned int)v6;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x55D,
                           (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           v7);
  }
  return result;
}

```

## disassembly

```asm
0x1800192e0  push    rbx
0x1800192e2  push    rsi
0x1800192e3  push    rdi
0x1800192e4  push    r14
0x1800192e6  sub     rsp, 98h
0x1800192ed  mov     [rsp+0B8h+var_50], 0FFFFFFFFFFFFFFFEh
0x1800192f6  mov     rax, cs:__security_cookie
0x1800192fd  xor     rax, rsp
0x180019300  mov     [rsp+0B8h+var_38], rax
0x180019308  mov     rdi, rcx
0x18001930b  lea     rax, [rcx+4A8h]
0x180019312  mov     [rsp+0B8h+var_88], rax
0x180019317  xor     r14d, r14d
0x18001931a  mov     [rsp+0B8h+var_80], r14b
0x18001931f  lea     rcx, [rsp+0B8h+var_88]; this
0x180019324  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x180019329  mov     ebx, eax
0x18001932b  test    eax, eax
0x18001932d  jns     short loc_180019350
0x18001932f  cmp     [rsp+0B8h+var_80], r14b
0x180019334  jz      short loc_180019349
0x180019336  mov     rcx, [rsp+0B8h+var_88]
0x18001933b  mov     rcx, [rcx]; hMutex
0x18001933e  test    rcx, rcx
0x180019341  jz      short loc_180019349
0x180019343  call    cs:__imp_ReleaseMutex
0x180019349  mov     eax, ebx
0x18001934b  jmp     loc_180019610
0x180019350  mov     rcx, rdi; this
0x180019353  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180019358  mov     ebx, eax
0x18001935a  test    eax, eax
0x18001935c  jns     short loc_18001937F
0x18001935e  cmp     [rsp+0B8h+var_80], r14b
0x180019363  jz      short loc_180019378
0x180019365  mov     rcx, [rsp+0B8h+var_88]
0x18001936a  mov     rcx, [rcx]; hMutex
0x18001936d  test    rcx, rcx
0x180019370  jz      short loc_180019378
0x180019372  call    cs:__imp_ReleaseMutex
0x180019378  mov     eax, ebx
0x18001937a  jmp     loc_180019610
0x18001937f  mov     rcx, rdi; this
0x180019382  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180019387  mov     ebx, eax
0x180019389  test    eax, eax
0x18001938b  js      loc_180019474
0x180019391  mov     [rsp+0B8h+var_78], r14d
0x180019396  lea     rdx, [rsp+0B8h+var_78]; unsigned int *
0x18001939b  mov     rcx, rdi; this
0x18001939e  call    ?GetPassedPolicyValue@UpdateReserveManager@@AEAAJPEAK@Z; UpdateReserveManager::GetPassedPolicyValue(ulong *)
0x1800193a3  mov     ebx, eax
0x1800193a5  test    eax, eax
0x1800193a7  js      loc_180019474
0x1800193ad  cmp     [rsp+0B8h+var_78], r14d
0x1800193b2  setnz   sil
0x1800193b6  mov     [rsp+0B8h+var_44], r14d
0x1800193bb  mov     [rsp+0B8h+var_48], r14b
0x1800193c0  lea     r8, [rsp+0B8h+var_48]; bool *
0x1800193c5  lea     rdx, [rsp+0B8h+var_44]; enum UpdateReserveManager::CheckReservePoliciesDisposition *
0x1800193ca  mov     rcx, rdi; this
0x1800193cd  call    ?CheckReservePolicies@UpdateReserveManager@@AEAAJPEAW4CheckReservePoliciesDisposition@1@PEA_N@Z; UpdateReserveManager::CheckReservePolicies(UpdateReserveManager::CheckReservePoliciesDisposition *,bool *)
0x1800193d2  mov     ebx, eax
0x1800193d4  test    eax, eax
0x1800193d6  js      loc_180019474
0x1800193dc  mov     eax, r14d
0x1800193df  cmp     [rsp+0B8h+var_48], r14b
0x1800193e4  setnz   al
0x1800193e7  mov     [rsp+0B8h+Data], eax
0x1800193eb  mov     r9d, 4; dwType
0x1800193f1  mov     [rsp+0B8h+cbData], r9d; cbData
0x1800193f6  lea     rax, [rsp+0B8h+Data]
0x1800193fb  mov     [rsp+0B8h+lpData], rax; lpData
0x180019400  lea     r8, aPassedpolicy; "PassedPolicy"
0x180019407  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x18001940e  mov     rcx, [rdi+68h]; hKey
0x180019412  call    cs:__imp_RegSetKeyValueW
0x180019418  mov     ebx, eax
0x18001941a  test    eax, eax
0x18001941c  jz      short loc_180019495
0x18001941e  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180019425  mov     [rsp+0B8h+var_70], rax
0x18001942a  lea     rax, aUpdatereservem_43; "UpdateReserveManager::ReevaluateReserve"...
0x180019431  mov     [rsp+0B8h+var_68], rax
0x180019436  mov     [rsp+0B8h+var_60], 0C2Dh
0x18001943f  lea     rax, aRegsetkeyvalue_1; "::RegSetKeyValueW(m_SoftwareKey, L\"Mic"...
0x180019446  mov     [rsp+0B8h+var_58], rax
0x18001944b  test    ebx, ebx
0x18001944d  jle     short loc_180019458
0x18001944f  movzx   ebx, bx
0x180019452  or      ebx, 80070000h
0x180019458  mov     r8d, ebx
0x18001945b  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180019462  lea     rcx, [rsp+0B8h+var_70]
0x180019467  call    RtlReportErrorOrigination
0x18001946c  test    ebx, ebx
0x18001946e  jns     loc_1800195B9
0x180019474  cmp     [rsp+0B8h+var_80], r14b
0x180019479  jz      short loc_18001948E
0x18001947b  mov     rcx, [rsp+0B8h+var_88]
0x180019480  mov     rcx, [rcx]; hMutex
0x180019483  test    rcx, rcx
0x180019486  jz      short loc_18001948E
0x180019488  call    cs:__imp_ReleaseMutex
0x18001948e  mov     eax, ebx
0x180019490  jmp     loc_180019610
0x180019495  mov     bl, [rsp+0B8h+var_48]
0x180019499  cmp     sil, bl
0x18001949c  setnz   sil
0x1800194a0  lea     rcx, [rdi+4B0h]; char *
0x1800194a7  mov     r9d, [rsp+0B8h+var_44]; unsigned int
0x1800194ac  mov     r8b, sil; bool
0x1800194af  mov     dl, bl; bool
0x1800194b1  call    ?ReportReevaluatePolicy@CUpdateReserveManagerDiagnostics@@SAXPEBD_N1K@Z; CUpdateReserveManagerDiagnostics::ReportReevaluatePolicy(char const *,bool,bool,ulong)
0x1800194b6  test    bl, bl
0x1800194b8  jz      short loc_1800194F9
0x1800194ba  mov     rax, [rdi]
0x1800194bd  mov     edx, 1
0x1800194c2  mov     rcx, rdi
0x1800194c5  mov     rax, [rax+8]
0x1800194c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800194ce  mov     ebx, eax
0x1800194d0  test    eax, eax
0x1800194d2  jns     loc_1800195E5
0x1800194d8  cmp     [rsp+0B8h+var_80], r14b
0x1800194dd  jz      short loc_1800194F2
0x1800194df  mov     rcx, [rsp+0B8h+var_88]
0x1800194e4  mov     rcx, [rcx]; hMutex
0x1800194e7  test    rcx, rcx
0x1800194ea  jz      short loc_1800194F2
0x1800194ec  call    cs:__imp_ReleaseMutex
0x1800194f2  mov     eax, ebx
0x1800194f4  jmp     loc_180019610
0x1800194f9  test    sil, sil
0x1800194fc  jz      loc_1800195B9
0x180019502  mov     edx, 1; enum _STORAGE_RESERVE_ID
0x180019507  mov     rcx, rdi; this
0x18001950a  call    ?UntagFilesInReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@@Z; UpdateReserveManager::UntagFilesInReserve(_STORAGE_RESERVE_ID)
0x18001950f  mov     [rsp+0B8h+var_44], r14d
0x180019514  lea     rdx, [rsp+0B8h+var_44]; enum IUpdateReserveManager::ScenarioId *
0x180019519  mov     rcx, rdi; this
0x18001951c  call    ?GetActiveScenario@UpdateReserveManager@@AEAAJPEAW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::GetActiveScenario(IUpdateReserveManager::ScenarioId *)
0x180019521  mov     ebx, eax
0x180019523  test    eax, eax
0x180019525  jns     short loc_180019548
0x180019527  cmp     [rsp+0B8h+var_80], r14b
0x18001952c  jz      short loc_180019541
0x18001952e  mov     rcx, [rsp+0B8h+var_88]
0x180019533  mov     rcx, [rcx]; hMutex
0x180019536  test    rcx, rcx
0x180019539  jz      short loc_180019541
0x18001953b  call    cs:__imp_ReleaseMutex
0x180019541  mov     eax, ebx
0x180019543  jmp     loc_180019610
0x180019548  mov     r8d, [rsp+0B8h+var_44]
0x18001954d  test    r8d, r8d
0x180019550  jz      short loc_18001958D
0x180019552  mov     rax, [rdi]
0x180019555  xor     r9d, r9d
0x180019558  xor     edx, edx
0x18001955a  mov     rcx, rdi
0x18001955d  mov     rax, [rax+18h]
0x180019561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019566  mov     ebx, eax
0x180019568  test    eax, eax
0x18001956a  jns     short loc_18001958D
0x18001956c  cmp     [rsp+0B8h+var_80], r14b
0x180019571  jz      short loc_180019586
0x180019573  mov     rcx, [rsp+0B8h+var_88]
0x180019578  mov     rcx, [rcx]; hMutex
0x18001957b  test    rcx, rcx
0x18001957e  jz      short loc_180019586
0x180019580  call    cs:__imp_ReleaseMutex
0x180019586  mov     eax, ebx
0x180019588  jmp     loc_180019610
0x18001958d  mov     rcx, rdi; this
0x180019590  call    ?SetReservesToZero@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::SetReservesToZero(void)
0x180019595  mov     ebx, eax
0x180019597  test    eax, eax
0x180019599  jns     short loc_1800195B9
0x18001959b  cmp     [rsp+0B8h+var_80], r14b
0x1800195a0  jz      short loc_1800195B5
0x1800195a2  mov     rcx, [rsp+0B8h+var_88]
0x1800195a7  mov     rcx, [rcx]; hMutex
0x1800195aa  test    rcx, rcx
0x1800195ad  jz      short loc_1800195B5
0x1800195af  call    cs:__imp_ReleaseMutex
0x1800195b5  mov     eax, ebx
0x1800195b7  jmp     short loc_180019610
0x1800195b9  mov     rcx, rdi; this
0x1800195bc  call    ?ClearTemporaryReserveInitParams@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::ClearTemporaryReserveInitParams(void)
0x1800195c1  mov     ebx, eax
0x1800195c3  test    eax, eax
0x1800195c5  jns     short loc_1800195E5
0x1800195c7  cmp     [rsp+0B8h+var_80], r14b
0x1800195cc  jz      short loc_1800195E1
0x1800195ce  mov     rcx, [rsp+0B8h+var_88]
0x1800195d3  mov     rcx, [rcx]; hMutex
0x1800195d6  test    rcx, rcx
0x1800195d9  jz      short loc_1800195E1
0x1800195db  call    cs:__imp_ReleaseMutex
0x1800195e1  mov     eax, ebx
0x1800195e3  jmp     short loc_180019610
0x1800195e5  mov     rcx, rdi; this
0x1800195e8  call    ?ValidateSoftReserveParenting@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::ValidateSoftReserveParenting(void)
0x1800195ed  nop
0x1800195ee  cmp     [rsp+0B8h+var_80], r14b
0x1800195f3  jz      short loc_180019608
0x1800195f5  mov     rax, [rsp+0B8h+var_88]
0x1800195fa  mov     rcx, [rax]; hMutex
0x1800195fd  test    rcx, rcx
0x180019600  jz      short loc_180019608
0x180019602  call    cs:__imp_ReleaseMutex
0x180019608  xor     eax, eax
0x18001960a  jmp     short loc_180019610
0x18001960c  mov     eax, [rsp+0B8h+Data]
0x180019610  mov     rcx, [rsp+0B8h+var_38]
0x180019618  xor     rcx, rsp; StackCookie
0x18001961b  call    __security_check_cookie
0x180019620  add     rsp, 98h
0x180019627  pop     r14
0x180019629  pop     rdi
0x18001962a  pop     rsi
0x18001962b  pop     rbx
0x18001962c  retn
```
