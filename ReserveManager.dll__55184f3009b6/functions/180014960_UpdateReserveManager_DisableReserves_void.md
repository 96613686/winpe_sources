# UpdateReserveManager::DisableReserves(void)

- ea: `0x180014960`
- end: `0x180014e2c`
- name: `?DisableReserves@UpdateReserveManager@@QEAAJXZ`
- size: `1228`
- prototype: `__int64 __fastcall(HKEY *this, unsigned int)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c520`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180013770`
- `0x180014960`
- `0x180015ad0`
- `0x180015e20`
- `0x1800170ec`
- `0x180019d28`
- `0x18001a8f0`
- `0x18001fd60`
- `0x180020778`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800149c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014a34`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014a66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014a9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014ac7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014b00`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014b6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014ba8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014c14`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014c53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014c82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014d2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014dda`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014df8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800149c5`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014a34`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014a66`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014a9f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014ac7`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014b00`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014b6d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014ba8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014c14`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014c53`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014c82`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014d2c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014dda`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180014df8`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180014cbd`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180014d6b`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180014cbd`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180014d6b`

## string_xrefs

- `0x1800149db`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014b14`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014bbb`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014cc9`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180014d77`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800149e7`: `UpdateReserveManager::DisableReserves`
- `0x180014b20`: `UpdateReserveManager::DisableReserves`
- `0x180014bc7`: `UpdateReserveManager::DisableReserves`
- `0x180014cd5`: `UpdateReserveManager::DisableReserves`
- `0x180014d83`: `UpdateReserveManager::DisableReserves`
- `0x180014cea`: `::RegSetKeyValueW(m_SoftwareKey, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"PassedPolicy", ( 4ul ), &PassedPolicyValue, sizeof(PassedPolicyValue))`
- `0x180014d98`: `::RegSetKeyValueW(m_SoftwareKey, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"MiscPolicyInfo", ( 4ul ), &PolicyInfoValue, sizeof(PolicyInfoValue))`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::DisableReserves(HKEY *this, unsigned int a2)
{
  int v3; // eax
  unsigned int v4; // edi
  __int64 result; // rax
  const char *v6; // r9
  int v7; // edi
  int ReserveState; // edi
  int IsAnotherReserveManagerInitialized; // edi
  int ActiveScenario; // edi
  int v11; // edi
  int inited; // edi
  int v13; // edi
  int v14; // ebx
  bool v15; // [rsp+30h] [rbp-68h] BYREF
  HANDLE *v16; // [rsp+38h] [rbp-60h] BYREF
  char v17; // [rsp+40h] [rbp-58h]
  const char *v18; // [rsp+48h] [rbp-50h] BYREF
  const char *v19; // [rsp+50h] [rbp-48h]
  __int64 v20; // [rsp+58h] [rbp-40h]
  const char *v21; // [rsp+60h] [rbp-38h]
  int v22; // [rsp+68h] [rbp-30h] BYREF
  __int64 v23; // [rsp+70h] [rbp-28h]
  int lpData; // [rsp+78h] [rbp-20h] BYREF
  int Data; // [rsp+7Ch] [rbp-1Ch] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  v23 = -2;
  v16 = (HANDLE *)(this + 149);
  v17 = 0;
  v3 = AutoMutexLocker::Lock((AutoMutexLocker *)&v16, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    try
    {
      if ( *((_BYTE *)this + 1176) )
      {
        v18 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v19 = "UpdateReserveManager::DisableReserves";
        v20 = 1546;
        v21 = "static_cast<DWORD>(50L)";
        RtlReportErrorOrigination(&v18, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942450LL);
        if ( v17 && *v16 )
          ReleaseMutex(*v16);
        result = 2147942450LL;
      }
      else
      {
        v7 = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)this);
        if ( v7 >= 0 )
        {
          v15 = 0;
          ReserveState = UpdateReserveManager::GetReserveState((UpdateReserveManager *)this, &v15);
          if ( ReserveState >= 0 )
          {
            if ( v15 )
            {
              v15 = 0;
              IsAnotherReserveManagerInitialized = UpdateReserveManager::IsAnotherReserveManagerInitialized(
                                                     (UpdateReserveManager *)this,
                                                     &v15);
              if ( IsAnotherReserveManagerInitialized >= 0 )
              {
                if ( v15 )
                {
                  v18 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
                  v19 = "UpdateReserveManager::DisableReserves";
                  v20 = 1565;
                  v21 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x978))) )";
                  RtlReportErrorOrigination(&v18, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469112LL);
                  if ( v17 && *v16 )
                    ReleaseMutex(*v16);
                  result = 2148469112LL;
                }
                else
                {
                  v22 = 0;
                  ActiveScenario = UpdateReserveManager::GetActiveScenario(
                                     (UpdateReserveManager *)this,
                                     (enum IUpdateReserveManager::ScenarioId *)&v22);
                  if ( ActiveScenario >= 0 )
                  {
                    if ( v22 )
                    {
                      v18 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
                      v19 = "UpdateReserveManager::DisableReserves";
                      v20 = 1573;
                      v21 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x975))) )";
                      RtlReportErrorOrigination(&v18, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469109LL);
                      if ( v17 && *v16 )
                        ReleaseMutex(*v16);
                      result = 2148469109LL;
                    }
                    else
                    {
                      UpdateReserveManager::UntagFilesInReserve((UpdateReserveManager *)this, 1u);
                      v11 = UpdateReserveManager::SetReservesToZero((UpdateReserveManager *)this);
                      if ( v11 >= 0 )
                      {
                        inited = UpdateReserveManager::ClearTemporaryReserveInitParams(this);
                        if ( inited >= 0 )
                        {
                          Data = 0;
                          v13 = RegSetKeyValueW(
                                  this[13],
                                  L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                                  L"PassedPolicy",
                                  4u,
                                  &Data,
                                  4u);
                          if ( v13 )
                          {
                            v18 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
                            v19 = "UpdateReserveManager::DisableReserves";
                            v20 = 1593;
                            v21 = "::RegSetKeyValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveM"
                                  "anager\", L\"PassedPolicy\", ( 4ul ), &PassedPolicyValue, sizeof(PassedPolicyValue))";
                            if ( v13 > 0 )
                              v13 = (unsigned __int16)v13 | 0x80070000;
                            RtlReportErrorOrigination(
                              &v18,
                              &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627,
                              (unsigned int)v13);
                            if ( v17 && *v16 )
                              ReleaseMutex(*v16);
                            result = (unsigned int)v13;
                          }
                          else
                          {
                            lpData = 2;
                            v14 = RegSetKeyValueW(
                                    this[13],
                                    L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                                    L"MiscPolicyInfo",
                                    4u,
                                    &lpData,
                                    4u);
                            if ( v14 )
                            {
                              v18 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
                              v19 = "UpdateReserveManager::DisableReserves";
                              v20 = 1601;
                              v21 = "::RegSetKeyValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\Reserv"
                                    "eManager\", L\"MiscPolicyInfo\", ( 4ul ), &PolicyInfoValue, sizeof(PolicyInfoValue))";
                              if ( v14 > 0 )
                                v14 = (unsigned __int16)v14 | 0x80070000;
                              RtlReportErrorOrigination(
                                &v18,
                                &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627,
                                (unsigned int)v14);
                              if ( v17 && *v16 )
                                ReleaseMutex(*v16);
                              result = (unsigned int)v14;
                            }
                            else
                            {
                              if ( v17 && *v16 )
                                ReleaseMutex(*v16);
                              result = 0;
                            }
                          }
                        }
                        else
                        {
                          if ( v17 && *v16 )
                            ReleaseMutex(*v16);
                          result = (unsigned int)inited;
                        }
                      }
                      else
                      {
                        if ( v17 && *v16 )
                          ReleaseMutex(*v16);
                        result = (unsigned int)v11;
                      }
                    }
                  }
                  else
                  {
                    if ( v17 && *v16 )
                      ReleaseMutex(*v16);
                    result = (unsigned int)ActiveScenario;
                  }
                }
              }
              else
              {
                if ( v17 && *v16 )
                  ReleaseMutex(*v16);
                result = (unsigned int)IsAnotherReserveManagerInitialized;
              }
            }
            else
            {
              if ( v17 && *v16 )
                ReleaseMutex(*v16);
              result = 0;
            }
          }
          else
          {
            if ( v17 && *v16 )
              ReleaseMutex(*v16);
            result = (unsigned int)ReserveState;
          }
        }
        else
        {
          if ( v17 && *v16 )
            ReleaseMutex(*v16);
          result = (unsigned int)v7;
        }
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x645,
                             (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                             v6);
    }
  }
  else
  {
    if ( v17 )
    {
      if ( *v16 )
        ReleaseMutex(*v16);
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180014960  mov     r11, rsp
0x180014963  push    rdi
0x180014964  sub     rsp, 90h
0x18001496b  mov     qword ptr [r11-28h], 0FFFFFFFFFFFFFFFEh
0x180014973  mov     [r11+10h], rbx
0x180014977  mov     [r11+18h], rsi
0x18001497b  mov     rax, cs:__security_cookie
0x180014982  xor     rax, rsp
0x180014985  mov     [rsp+98h+var_18], rax
0x18001498d  mov     rbx, rcx
0x180014990  lea     rax, [rcx+4A8h]
0x180014997  mov     [r11-60h], rax
0x18001499b  xor     esi, esi
0x18001499d  mov     [rsp+98h+var_58], sil
0x1800149a2  lea     rcx, [r11-60h]; this
0x1800149a6  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x1800149ab  mov     edi, eax
0x1800149ad  test    eax, eax
0x1800149af  jns     short loc_1800149D2
0x1800149b1  cmp     [rsp+98h+var_58], sil
0x1800149b6  jz      short loc_1800149CB
0x1800149b8  mov     rcx, [rsp+98h+var_60]
0x1800149bd  mov     rcx, [rcx]; hMutex
0x1800149c0  test    rcx, rcx
0x1800149c3  jz      short loc_1800149CB
0x1800149c5  call    cs:__imp_ReleaseMutex
0x1800149cb  mov     eax, edi
0x1800149cd  jmp     loc_180014E06
0x1800149d2  cmp     [rbx+498h], sil
0x1800149d9  jz      short loc_180014A44
0x1800149db  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800149e2  mov     [rsp+98h+var_50], rax
0x1800149e7  lea     rax, aUpdatereservem_36; "UpdateReserveManager::DisableReserves"
0x1800149ee  mov     [rsp+98h+var_48], rax
0x1800149f3  mov     [rsp+98h+var_40], 60Ah
0x1800149fc  lea     rax, aStaticCastDwor; "static_cast<DWORD>(50L)"
0x180014a03  mov     [rsp+98h+var_38], rax
0x180014a08  mov     r8d, 80070032h
0x180014a0e  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180014a15  lea     rcx, [rsp+98h+var_50]
0x180014a1a  call    RtlReportErrorOrigination
0x180014a1f  nop
0x180014a20  cmp     [rsp+98h+var_58], sil
0x180014a25  jz      short loc_180014A3A
0x180014a27  mov     rax, [rsp+98h+var_60]
0x180014a2c  mov     rcx, [rax]; hMutex
0x180014a2f  test    rcx, rcx
0x180014a32  jz      short loc_180014A3A
0x180014a34  call    cs:__imp_ReleaseMutex
0x180014a3a  mov     eax, 80070032h
0x180014a3f  jmp     loc_180014E06
0x180014a44  mov     rcx, rbx; this
0x180014a47  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180014a4c  mov     edi, eax
0x180014a4e  test    eax, eax
0x180014a50  jns     short loc_180014A73
0x180014a52  cmp     [rsp+98h+var_58], sil
0x180014a57  jz      short loc_180014A6C
0x180014a59  mov     rcx, [rsp+98h+var_60]
0x180014a5e  mov     rcx, [rcx]; hMutex
0x180014a61  test    rcx, rcx
0x180014a64  jz      short loc_180014A6C
0x180014a66  call    cs:__imp_ReleaseMutex
0x180014a6c  mov     eax, edi
0x180014a6e  jmp     loc_180014E06
0x180014a73  mov     [rsp+98h+var_68], sil
0x180014a78  lea     rdx, [rsp+98h+var_68]; bool *
0x180014a7d  mov     rcx, rbx; this
0x180014a80  call    ?GetReserveState@UpdateReserveManager@@QEAAJPEA_N@Z; UpdateReserveManager::GetReserveState(bool *)
0x180014a85  mov     edi, eax
0x180014a87  test    eax, eax
0x180014a89  jns     short loc_180014AAC
0x180014a8b  cmp     [rsp+98h+var_58], sil
0x180014a90  jz      short loc_180014AA5
0x180014a92  mov     rcx, [rsp+98h+var_60]
0x180014a97  mov     rcx, [rcx]; hMutex
0x180014a9a  test    rcx, rcx
0x180014a9d  jz      short loc_180014AA5
0x180014a9f  call    cs:__imp_ReleaseMutex
0x180014aa5  mov     eax, edi
0x180014aa7  jmp     loc_180014E06
0x180014aac  cmp     [rsp+98h+var_68], sil
0x180014ab1  jnz     short loc_180014AD4
0x180014ab3  cmp     [rsp+98h+var_58], sil
0x180014ab8  jz      short loc_180014ACD
0x180014aba  mov     rax, [rsp+98h+var_60]
0x180014abf  mov     rcx, [rax]; hMutex
0x180014ac2  test    rcx, rcx
0x180014ac5  jz      short loc_180014ACD
0x180014ac7  call    cs:__imp_ReleaseMutex
0x180014acd  xor     eax, eax
0x180014acf  jmp     loc_180014E06
0x180014ad4  mov     [rsp+98h+var_68], sil
0x180014ad9  lea     rdx, [rsp+98h+var_68]; bool *
0x180014ade  mov     rcx, rbx; this
0x180014ae1  call    ?IsAnotherReserveManagerInitialized@UpdateReserveManager@@AEAAJPEA_N@Z; UpdateReserveManager::IsAnotherReserveManagerInitialized(bool *)
0x180014ae6  mov     edi, eax
0x180014ae8  test    eax, eax
0x180014aea  jns     short loc_180014B0D
0x180014aec  cmp     [rsp+98h+var_58], sil
0x180014af1  jz      short loc_180014B06
0x180014af3  mov     rcx, [rsp+98h+var_60]
0x180014af8  mov     rcx, [rcx]; hMutex
0x180014afb  test    rcx, rcx
0x180014afe  jz      short loc_180014B06
0x180014b00  call    cs:__imp_ReleaseMutex
0x180014b06  mov     eax, edi
0x180014b08  jmp     loc_180014E06
0x180014b0d  cmp     [rsp+98h+var_68], sil
0x180014b12  jz      short loc_180014B7D
0x180014b14  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180014b1b  mov     [rsp+98h+var_50], rax
0x180014b20  lea     rax, aUpdatereservem_36; "UpdateReserveManager::DisableReserves"
0x180014b27  mov     [rsp+98h+var_48], rax
0x180014b2c  mov     [rsp+98h+var_40], 61Dh
0x180014b35  lea     rax, aScodeUnsignedL_1; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x180014b3c  mov     [rsp+98h+var_38], rax
0x180014b41  mov     r8d, 800F0978h
0x180014b47  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180014b4e  lea     rcx, [rsp+98h+var_50]
0x180014b53  call    RtlReportErrorOrigination
0x180014b58  nop
0x180014b59  cmp     [rsp+98h+var_58], sil
0x180014b5e  jz      short loc_180014B73
0x180014b60  mov     rax, [rsp+98h+var_60]
0x180014b65  mov     rcx, [rax]; hMutex
0x180014b68  test    rcx, rcx
0x180014b6b  jz      short loc_180014B73
0x180014b6d  call    cs:__imp_ReleaseMutex
0x180014b73  mov     eax, 800F0978h
0x180014b78  jmp     loc_180014E06
0x180014b7d  mov     [rsp+98h+var_30], esi
0x180014b81  lea     rdx, [rsp+98h+var_30]; enum IUpdateReserveManager::ScenarioId *
0x180014b86  mov     rcx, rbx; this
0x180014b89  call    ?GetActiveScenario@UpdateReserveManager@@AEAAJPEAW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::GetActiveScenario(IUpdateReserveManager::ScenarioId *)
0x180014b8e  mov     edi, eax
0x180014b90  test    eax, eax
0x180014b92  jns     short loc_180014BB5
0x180014b94  cmp     [rsp+98h+var_58], sil
0x180014b99  jz      short loc_180014BAE
0x180014b9b  mov     rcx, [rsp+98h+var_60]
0x180014ba0  mov     rcx, [rcx]; hMutex
0x180014ba3  test    rcx, rcx
0x180014ba6  jz      short loc_180014BAE
0x180014ba8  call    cs:__imp_ReleaseMutex
0x180014bae  mov     eax, edi
0x180014bb0  jmp     loc_180014E06
0x180014bb5  cmp     [rsp+98h+var_30], esi
0x180014bb9  jz      short loc_180014C24
0x180014bbb  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180014bc2  mov     [rsp+98h+var_50], rax
0x180014bc7  lea     rax, aUpdatereservem_36; "UpdateReserveManager::DisableReserves"
0x180014bce  mov     [rsp+98h+var_48], rax
0x180014bd3  mov     [rsp+98h+var_40], 625h
0x180014bdc  lea     rax, aScodeUnsignedL_5; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x180014be3  mov     [rsp+98h+var_38], rax
0x180014be8  mov     r8d, 800F0975h
0x180014bee  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180014bf5  lea     rcx, [rsp+98h+var_50]
0x180014bfa  call    RtlReportErrorOrigination
0x180014bff  nop
0x180014c00  cmp     [rsp+98h+var_58], sil
0x180014c05  jz      short loc_180014C1A
0x180014c07  mov     rax, [rsp+98h+var_60]
0x180014c0c  mov     rcx, [rax]; hMutex
0x180014c0f  test    rcx, rcx
0x180014c12  jz      short loc_180014C1A
0x180014c14  call    cs:__imp_ReleaseMutex
0x180014c1a  mov     eax, 800F0975h
0x180014c1f  jmp     loc_180014E06
0x180014c24  mov     edx, 1; enum _STORAGE_RESERVE_ID
0x180014c29  mov     rcx, rbx; this
0x180014c2c  call    ?UntagFilesInReserve@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@@Z; UpdateReserveManager::UntagFilesInReserve(_STORAGE_RESERVE_ID)
0x180014c31  mov     rcx, rbx; this
0x180014c34  call    ?SetReservesToZero@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::SetReservesToZero(void)
0x180014c39  mov     edi, eax
0x180014c3b  test    eax, eax
0x180014c3d  jns     short loc_180014C60
0x180014c3f  cmp     [rsp+98h+var_58], sil
0x180014c44  jz      short loc_180014C59
0x180014c46  mov     rcx, [rsp+98h+var_60]
0x180014c4b  mov     rcx, [rcx]; hMutex
0x180014c4e  test    rcx, rcx
0x180014c51  jz      short loc_180014C59
0x180014c53  call    cs:__imp_ReleaseMutex
0x180014c59  mov     eax, edi
0x180014c5b  jmp     loc_180014E06
0x180014c60  mov     rcx, rbx; this
0x180014c63  call    ?ClearTemporaryReserveInitParams@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::ClearTemporaryReserveInitParams(void)
0x180014c68  mov     edi, eax
0x180014c6a  test    eax, eax
0x180014c6c  jns     short loc_180014C8F
0x180014c6e  cmp     [rsp+98h+var_58], sil
0x180014c73  jz      short loc_180014C88
0x180014c75  mov     rcx, [rsp+98h+var_60]
0x180014c7a  mov     rcx, [rcx]; hMutex
0x180014c7d  test    rcx, rcx
0x180014c80  jz      short loc_180014C88
0x180014c82  call    cs:__imp_ReleaseMutex
0x180014c88  mov     eax, edi
0x180014c8a  jmp     loc_180014E06
0x180014c8f  mov     [rsp+98h+Data], esi
0x180014c93  mov     [rsp+98h+cbData], 4; cbData
0x180014c9b  lea     rax, [rsp+98h+Data]
0x180014ca0  mov     [rsp+98h+lpData], rax; lpData
0x180014ca5  mov     r9d, 4; dwType
0x180014cab  lea     r8, aPassedpolicy; "PassedPolicy"
0x180014cb2  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180014cb9  mov     rcx, [rbx+68h]; hKey
0x180014cbd  call    cs:__imp_RegSetKeyValueW
0x180014cc3  mov     edi, eax
0x180014cc5  test    eax, eax
0x180014cc7  jz      short loc_180014D39
0x180014cc9  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180014cd0  mov     [rsp+98h+var_50], rax
0x180014cd5  lea     rax, aUpdatereservem_36; "UpdateReserveManager::DisableReserves"
0x180014cdc  mov     [rsp+98h+var_48], rax
0x180014ce1  mov     [rsp+98h+var_40], 639h
0x180014cea  lea     rax, aRegsetkeyvalue_0; "::RegSetKeyValueW(m_SoftwareKey, L\"Mic"...
0x180014cf1  mov     [rsp+98h+var_38], rax
0x180014cf6  test    edi, edi
0x180014cf8  jle     short loc_180014D03
0x180014cfa  movzx   edi, di
0x180014cfd  or      edi, 80070000h
0x180014d03  mov     r8d, edi
0x180014d06  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180014d0d  lea     rcx, [rsp+98h+var_50]
0x180014d12  call    RtlReportErrorOrigination
0x180014d17  nop
0x180014d18  cmp     [rsp+98h+var_58], sil
0x180014d1d  jz      short loc_180014D32
0x180014d1f  mov     rcx, [rsp+98h+var_60]
0x180014d24  mov     rcx, [rcx]; hMutex
0x180014d27  test    rcx, rcx
0x180014d2a  jz      short loc_180014D32
0x180014d2c  call    cs:__imp_ReleaseMutex
0x180014d32  mov     eax, edi
0x180014d34  jmp     loc_180014E06
0x180014d39  mov     [rsp+98h+var_20], 2
0x180014d41  mov     [rsp+98h+cbData], 4; cbData
0x180014d49  lea     rax, [rsp+98h+var_20]
0x180014d4e  mov     [rsp+98h+lpData], rax; lpData
0x180014d53  mov     r9d, 4; dwType
0x180014d59  lea     r8, aMiscpolicyinfo; "MiscPolicyInfo"
0x180014d60  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180014d67  mov     rcx, [rbx+68h]; hKey
0x180014d6b  call    cs:__imp_RegSetKeyValueW
0x180014d71  mov     ebx, eax
0x180014d73  test    eax, eax
0x180014d75  jz      short loc_180014DE4
0x180014d77  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180014d7e  mov     [rsp+98h+var_50], rax
0x180014d83  lea     rax, aUpdatereservem_36; "UpdateReserveManager::DisableReserves"
0x180014d8a  mov     [rsp+98h+var_48], rax
0x180014d8f  mov     [rsp+98h+var_40], 641h
0x180014d98  lea     rax, aRegsetkeyvalue; "::RegSetKeyValueW(m_SoftwareKey, L\"Mic"...
0x180014d9f  mov     [rsp+98h+var_38], rax
0x180014da4  test    ebx, ebx
0x180014da6  jle     short loc_180014DB1
0x180014da8  movzx   ebx, bx
0x180014dab  or      ebx, 80070000h
0x180014db1  mov     r8d, ebx
0x180014db4  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180014dbb  lea     rcx, [rsp+98h+var_50]
0x180014dc0  call    RtlReportErrorOrigination
0x180014dc5  nop
0x180014dc6  cmp     [rsp+98h+var_58], sil
0x180014dcb  jz      short loc_180014DE0
0x180014dcd  mov     rcx, [rsp+98h+var_60]
0x180014dd2  mov     rcx, [rcx]; hMutex
0x180014dd5  test    rcx, rcx
0x180014dd8  jz      short loc_180014DE0
0x180014dda  call    cs:__imp_ReleaseMutex
0x180014de0  mov     eax, ebx
0x180014de2  jmp     short loc_180014E06
0x180014de4  cmp     [rsp+98h+var_58], sil
0x180014de9  jz      short loc_180014DFE
0x180014deb  mov     rax, [rsp+98h+var_60]
0x180014df0  mov     rcx, [rax]; hMutex
0x180014df3  test    rcx, rcx
0x180014df6  jz      short loc_180014DFE
0x180014df8  call    cs:__imp_ReleaseMutex
0x180014dfe  xor     eax, eax
0x180014e00  jmp     short loc_180014E06
0x180014e02  mov     eax, [rsp+98h+var_20]
0x180014e06  mov     rcx, [rsp+98h+var_18]
0x180014e0e  xor     rcx, rsp; StackCookie
0x180014e11  call    __security_check_cookie
0x180014e16  lea     r11, [rsp+98h+var_8]
0x180014e1e  mov     rbx, [r11+18h]
0x180014e22  mov     rsi, [r11+20h]
0x180014e26  mov     rsp, r11
0x180014e29  pop     rdi
0x180014e2a  retn
```
