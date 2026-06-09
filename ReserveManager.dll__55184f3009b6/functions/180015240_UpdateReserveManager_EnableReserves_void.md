# UpdateReserveManager::EnableReserves(void)

- ea: `0x180015240`
- end: `0x1800155ce`
- name: `?EnableReserves@UpdateReserveManager@@QEAAJXZ`
- size: `910`
- prototype: `__int64 __fastcall(HKEY *this, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18000c610`

## callees

- `0x180003870`
- `0x18000fafc`
- `0x180013770`
- `0x180015240`
- `0x180015ad0`
- `0x1800170ec`
- `0x1800192e0`
- `0x180019d28`
- `0x18001a8f0`
- `0x180021c38`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800152a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015311`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015343`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001537c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800153a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800153dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001544a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800154f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015527`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015553`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001557f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001559d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800152a2`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015311`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015343`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001537c`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800153a4`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800153dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001544a`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800154f8`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015527`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180015553`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001557f`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18001559d`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180015489`
- `api-ms-win-core-registry-l2-1-0!RegSetKeyValueW` at `0x180015489`

## string_xrefs

- `0x1800152b8`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800153f1`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180015495`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800154b6`: `::RegSetKeyValueW(m_SoftwareKey, L"Microsoft\\Windows\\CurrentVersion\\ReserveManager", L"MiscPolicyInfo", ( 4ul ), &PolicyInfoValue, sizeof(PolicyInfoValue))`
- `0x1800152c4`: `UpdateReserveManager::EnableReserves`
- `0x1800153fd`: `UpdateReserveManager::EnableReserves`
- `0x1800154a1`: `UpdateReserveManager::EnableReserves`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::EnableReserves(HKEY *this, unsigned int a2)
{
  int v3; // eax
  unsigned int v4; // edi
  __int64 result; // rax
  const char *v6; // r9
  int v7; // edi
  int ReserveState; // edi
  int IsAnotherReserveManagerInitialized; // edi
  int v10; // edi
  int inited; // edi
  int v12; // edi
  int updated; // ebx
  bool v14; // [rsp+30h] [rbp-58h] BYREF
  HANDLE *v15; // [rsp+38h] [rbp-50h] BYREF
  char v16; // [rsp+40h] [rbp-48h]
  const char *v17; // [rsp+48h] [rbp-40h] BYREF
  const char *v18; // [rsp+50h] [rbp-38h]
  __int64 v19; // [rsp+58h] [rbp-30h]
  const char *v20; // [rsp+60h] [rbp-28h]
  __int64 v21; // [rsp+68h] [rbp-20h]
  int Data; // [rsp+70h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v21 = -2;
  v15 = (HANDLE *)(this + 149);
  v16 = 0;
  v3 = AutoMutexLocker::Lock((AutoMutexLocker *)&v15, a2);
  v4 = v3;
  if ( v3 >= 0 )
  {
    try
    {
      if ( *((_BYTE *)this + 1176) )
      {
        v17 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v18 = "UpdateReserveManager::EnableReserves";
        v19 = 1621;
        v20 = "static_cast<DWORD>(50L)";
        RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942450LL);
        if ( v16 && *v15 )
          ReleaseMutex(*v15);
        result = 2147942450LL;
      }
      else
      {
        v7 = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)this);
        if ( v7 >= 0 )
        {
          v14 = 0;
          ReserveState = UpdateReserveManager::GetReserveState((UpdateReserveManager *)this, &v14);
          if ( ReserveState >= 0 )
          {
            if ( v14 )
            {
              if ( v16 && *v15 )
                ReleaseMutex(*v15);
              result = 0;
            }
            else
            {
              v14 = 0;
              IsAnotherReserveManagerInitialized = UpdateReserveManager::IsAnotherReserveManagerInitialized(
                                                     (UpdateReserveManager *)this,
                                                     &v14);
              if ( IsAnotherReserveManagerInitialized >= 0 )
              {
                if ( v14 )
                {
                  v17 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
                  v18 = "UpdateReserveManager::EnableReserves";
                  v19 = 1640;
                  v20 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x978))) )";
                  RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469112LL);
                  if ( v16 && *v15 )
                    ReleaseMutex(*v15);
                  result = 2148469112LL;
                }
                else
                {
                  Data = 1;
                  v10 = RegSetKeyValueW(
                          this[13],
                          L"Microsoft\\Windows\\CurrentVersion\\ReserveManager",
                          L"MiscPolicyInfo",
                          4u,
                          &Data,
                          4u);
                  if ( v10 )
                  {
                    v17 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
                    v18 = "UpdateReserveManager::EnableReserves";
                    v19 = 1649;
                    v20 = "::RegSetKeyValueW(m_SoftwareKey, L\"Microsoft\\\\Windows\\\\CurrentVersion\\\\ReserveManager\""
                          ", L\"MiscPolicyInfo\", ( 4ul ), &PolicyInfoValue, sizeof(PolicyInfoValue))";
                    if ( v10 > 0 )
                      v10 = (unsigned __int16)v10 | 0x80070000;
                    RtlReportErrorOrigination(&v17, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, (unsigned int)v10);
                    if ( v16 && *v15 )
                      ReleaseMutex(*v15);
                    result = (unsigned int)v10;
                  }
                  else
                  {
                    inited = UpdateReserveManager::ClearTemporaryReserveInitParams(this);
                    if ( inited >= 0 )
                    {
                      v12 = UpdateReserveManager::WriteMinAcceptableUserFreeSpaceValue((UpdateReserveManager *)this);
                      if ( v12 >= 0 )
                      {
                        updated = UpdateReserveManager::InitializeReservesAndUpdatePolicy((UpdateReserveManager *)this);
                        if ( updated >= 0 )
                        {
                          if ( v16 && *v15 )
                            ReleaseMutex(*v15);
                          result = 0;
                        }
                        else
                        {
                          if ( v16 && *v15 )
                            ReleaseMutex(*v15);
                          result = (unsigned int)updated;
                        }
                      }
                      else
                      {
                        if ( v16 && *v15 )
                          ReleaseMutex(*v15);
                        result = (unsigned int)v12;
                      }
                    }
                    else
                    {
                      if ( v16 && *v15 )
                        ReleaseMutex(*v15);
                      result = (unsigned int)inited;
                    }
                  }
                }
              }
              else
              {
                if ( v16 && *v15 )
                  ReleaseMutex(*v15);
                result = (unsigned int)IsAnotherReserveManagerInitialized;
              }
            }
          }
          else
          {
            if ( v16 && *v15 )
              ReleaseMutex(*v15);
            result = (unsigned int)ReserveState;
          }
        }
        else
        {
          if ( v16 && *v15 )
            ReleaseMutex(*v15);
          result = (unsigned int)v7;
        }
      }
    }
    catch ( ... )
    {
      return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                             retaddr,
                             (void *)0x67E,
                             (unsigned int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                             v6);
    }
  }
  else
  {
    if ( v16 )
    {
      if ( *v15 )
        ReleaseMutex(*v15);
    }
    return v4;
  }
  return result;
}

```

## disassembly

```asm
0x180015240  mov     r11, rsp
0x180015243  push    rdi
0x180015244  sub     rsp, 80h
0x18001524b  mov     qword ptr [r11-20h], 0FFFFFFFFFFFFFFFEh
0x180015253  mov     [r11+10h], rbx
0x180015257  mov     [r11+18h], rsi
0x18001525b  mov     rax, cs:__security_cookie
0x180015262  xor     rax, rsp
0x180015265  mov     [rsp+88h+var_10], rax
0x18001526a  mov     rbx, rcx
0x18001526d  lea     rax, [rcx+4A8h]
0x180015274  mov     [r11-50h], rax
0x180015278  xor     esi, esi
0x18001527a  mov     [rsp+88h+var_48], sil
0x18001527f  lea     rcx, [r11-50h]; this
0x180015283  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x180015288  mov     edi, eax
0x18001528a  test    eax, eax
0x18001528c  jns     short loc_1800152AF
0x18001528e  cmp     [rsp+88h+var_48], sil
0x180015293  jz      short loc_1800152A8
0x180015295  mov     rcx, [rsp+88h+var_50]
0x18001529a  mov     rcx, [rcx]; hMutex
0x18001529d  test    rcx, rcx
0x1800152a0  jz      short loc_1800152A8
0x1800152a2  call    cs:__imp_ReleaseMutex
0x1800152a8  mov     eax, edi
0x1800152aa  jmp     loc_1800155AB
0x1800152af  cmp     [rbx+498h], sil
0x1800152b6  jz      short loc_180015321
0x1800152b8  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800152bf  mov     [rsp+88h+var_40], rax
0x1800152c4  lea     rax, aUpdatereservem_25; "UpdateReserveManager::EnableReserves"
0x1800152cb  mov     [rsp+88h+var_38], rax
0x1800152d0  mov     [rsp+88h+var_30], 655h
0x1800152d9  lea     rax, aStaticCastDwor; "static_cast<DWORD>(50L)"
0x1800152e0  mov     [rsp+88h+var_28], rax
0x1800152e5  mov     r8d, 80070032h
0x1800152eb  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800152f2  lea     rcx, [rsp+88h+var_40]
0x1800152f7  call    RtlReportErrorOrigination
0x1800152fc  nop
0x1800152fd  cmp     [rsp+88h+var_48], sil
0x180015302  jz      short loc_180015317
0x180015304  mov     rax, [rsp+88h+var_50]
0x180015309  mov     rcx, [rax]; hMutex
0x18001530c  test    rcx, rcx
0x18001530f  jz      short loc_180015317
0x180015311  call    cs:__imp_ReleaseMutex
0x180015317  mov     eax, 80070032h
0x18001531c  jmp     loc_1800155AB
0x180015321  mov     rcx, rbx; this
0x180015324  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180015329  mov     edi, eax
0x18001532b  test    eax, eax
0x18001532d  jns     short loc_180015350
0x18001532f  cmp     [rsp+88h+var_48], sil
0x180015334  jz      short loc_180015349
0x180015336  mov     rcx, [rsp+88h+var_50]
0x18001533b  mov     rcx, [rcx]; hMutex
0x18001533e  test    rcx, rcx
0x180015341  jz      short loc_180015349
0x180015343  call    cs:__imp_ReleaseMutex
0x180015349  mov     eax, edi
0x18001534b  jmp     loc_1800155AB
0x180015350  mov     [rsp+88h+var_58], sil
0x180015355  lea     rdx, [rsp+88h+var_58]; bool *
0x18001535a  mov     rcx, rbx; this
0x18001535d  call    ?GetReserveState@UpdateReserveManager@@QEAAJPEA_N@Z; UpdateReserveManager::GetReserveState(bool *)
0x180015362  mov     edi, eax
0x180015364  test    eax, eax
0x180015366  jns     short loc_180015389
0x180015368  cmp     [rsp+88h+var_48], sil
0x18001536d  jz      short loc_180015382
0x18001536f  mov     rcx, [rsp+88h+var_50]
0x180015374  mov     rcx, [rcx]; hMutex
0x180015377  test    rcx, rcx
0x18001537a  jz      short loc_180015382
0x18001537c  call    cs:__imp_ReleaseMutex
0x180015382  mov     eax, edi
0x180015384  jmp     loc_1800155AB
0x180015389  cmp     [rsp+88h+var_58], sil
0x18001538e  jz      short loc_1800153B1
0x180015390  cmp     [rsp+88h+var_48], sil
0x180015395  jz      short loc_1800153AA
0x180015397  mov     rax, [rsp+88h+var_50]
0x18001539c  mov     rcx, [rax]; hMutex
0x18001539f  test    rcx, rcx
0x1800153a2  jz      short loc_1800153AA
0x1800153a4  call    cs:__imp_ReleaseMutex
0x1800153aa  xor     eax, eax
0x1800153ac  jmp     loc_1800155AB
0x1800153b1  mov     [rsp+88h+var_58], sil
0x1800153b6  lea     rdx, [rsp+88h+var_58]; bool *
0x1800153bb  mov     rcx, rbx; this
0x1800153be  call    ?IsAnotherReserveManagerInitialized@UpdateReserveManager@@AEAAJPEA_N@Z; UpdateReserveManager::IsAnotherReserveManagerInitialized(bool *)
0x1800153c3  mov     edi, eax
0x1800153c5  test    eax, eax
0x1800153c7  jns     short loc_1800153EA
0x1800153c9  cmp     [rsp+88h+var_48], sil
0x1800153ce  jz      short loc_1800153E3
0x1800153d0  mov     rcx, [rsp+88h+var_50]
0x1800153d5  mov     rcx, [rcx]; hMutex
0x1800153d8  test    rcx, rcx
0x1800153db  jz      short loc_1800153E3
0x1800153dd  call    cs:__imp_ReleaseMutex
0x1800153e3  mov     eax, edi
0x1800153e5  jmp     loc_1800155AB
0x1800153ea  cmp     [rsp+88h+var_58], sil
0x1800153ef  jz      short loc_18001545A
0x1800153f1  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800153f8  mov     [rsp+88h+var_40], rax
0x1800153fd  lea     rax, aUpdatereservem_25; "UpdateReserveManager::EnableReserves"
0x180015404  mov     [rsp+88h+var_38], rax
0x180015409  mov     [rsp+88h+var_30], 668h
0x180015412  lea     rax, aScodeUnsignedL_1; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x180015419  mov     [rsp+88h+var_28], rax
0x18001541e  mov     r8d, 800F0978h
0x180015424  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001542b  lea     rcx, [rsp+88h+var_40]
0x180015430  call    RtlReportErrorOrigination
0x180015435  nop
0x180015436  cmp     [rsp+88h+var_48], sil
0x18001543b  jz      short loc_180015450
0x18001543d  mov     rax, [rsp+88h+var_50]
0x180015442  mov     rcx, [rax]; hMutex
0x180015445  test    rcx, rcx
0x180015448  jz      short loc_180015450
0x18001544a  call    cs:__imp_ReleaseMutex
0x180015450  mov     eax, 800F0978h
0x180015455  jmp     loc_1800155AB
0x18001545a  mov     [rsp+88h+Data], 1
0x180015462  mov     r9d, 4; dwType
0x180015468  mov     [rsp+88h+cbData], r9d; cbData
0x18001546d  lea     rax, [rsp+88h+Data]
0x180015472  mov     [rsp+88h+lpData], rax; lpData
0x180015477  lea     r8, aMiscpolicyinfo; "MiscPolicyInfo"
0x18001547e  lea     rdx, aMicrosoftWindo_2; "Microsoft\\Windows\\CurrentVersion\\Res"...
0x180015485  mov     rcx, [rbx+68h]; hKey
0x180015489  call    cs:__imp_RegSetKeyValueW
0x18001548f  mov     edi, eax
0x180015491  test    eax, eax
0x180015493  jz      short loc_180015505
0x180015495  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001549c  mov     [rsp+88h+var_40], rax
0x1800154a1  lea     rax, aUpdatereservem_25; "UpdateReserveManager::EnableReserves"
0x1800154a8  mov     [rsp+88h+var_38], rax
0x1800154ad  mov     [rsp+88h+var_30], 671h
0x1800154b6  lea     rax, aRegsetkeyvalue; "::RegSetKeyValueW(m_SoftwareKey, L\"Mic"...
0x1800154bd  mov     [rsp+88h+var_28], rax
0x1800154c2  test    edi, edi
0x1800154c4  jle     short loc_1800154CF
0x1800154c6  movzx   edi, di
0x1800154c9  or      edi, 80070000h
0x1800154cf  mov     r8d, edi
0x1800154d2  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800154d9  lea     rcx, [rsp+88h+var_40]
0x1800154de  call    RtlReportErrorOrigination
0x1800154e3  nop
0x1800154e4  cmp     [rsp+88h+var_48], sil
0x1800154e9  jz      short loc_1800154FE
0x1800154eb  mov     rcx, [rsp+88h+var_50]
0x1800154f0  mov     rcx, [rcx]; hMutex
0x1800154f3  test    rcx, rcx
0x1800154f6  jz      short loc_1800154FE
0x1800154f8  call    cs:__imp_ReleaseMutex
0x1800154fe  mov     eax, edi
0x180015500  jmp     loc_1800155AB
0x180015505  mov     rcx, rbx; this
0x180015508  call    ?ClearTemporaryReserveInitParams@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::ClearTemporaryReserveInitParams(void)
0x18001550d  mov     edi, eax
0x18001550f  test    eax, eax
0x180015511  jns     short loc_180015531
0x180015513  cmp     [rsp+88h+var_48], sil
0x180015518  jz      short loc_18001552D
0x18001551a  mov     rcx, [rsp+88h+var_50]
0x18001551f  mov     rcx, [rcx]; hMutex
0x180015522  test    rcx, rcx
0x180015525  jz      short loc_18001552D
0x180015527  call    cs:__imp_ReleaseMutex
0x18001552d  mov     eax, edi
0x18001552f  jmp     short loc_1800155AB
0x180015531  mov     rcx, rbx; this
0x180015534  call    ?WriteMinAcceptableUserFreeSpaceValue@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::WriteMinAcceptableUserFreeSpaceValue(void)
0x180015539  mov     edi, eax
0x18001553b  test    eax, eax
0x18001553d  jns     short loc_18001555D
0x18001553f  cmp     [rsp+88h+var_48], sil
0x180015544  jz      short loc_180015559
0x180015546  mov     rcx, [rsp+88h+var_50]
0x18001554b  mov     rcx, [rcx]; hMutex
0x18001554e  test    rcx, rcx
0x180015551  jz      short loc_180015559
0x180015553  call    cs:__imp_ReleaseMutex
0x180015559  mov     eax, edi
0x18001555b  jmp     short loc_1800155AB
0x18001555d  mov     rcx, rbx; this
0x180015560  call    ?InitializeReservesAndUpdatePolicy@UpdateReserveManager@@QEAAJXZ; UpdateReserveManager::InitializeReservesAndUpdatePolicy(void)
0x180015565  mov     ebx, eax
0x180015567  test    eax, eax
0x180015569  jns     short loc_180015589
0x18001556b  cmp     [rsp+88h+var_48], sil
0x180015570  jz      short loc_180015585
0x180015572  mov     rcx, [rsp+88h+var_50]
0x180015577  mov     rcx, [rcx]; hMutex
0x18001557a  test    rcx, rcx
0x18001557d  jz      short loc_180015585
0x18001557f  call    cs:__imp_ReleaseMutex
0x180015585  mov     eax, ebx
0x180015587  jmp     short loc_1800155AB
0x180015589  cmp     [rsp+88h+var_48], sil
0x18001558e  jz      short loc_1800155A3
0x180015590  mov     rax, [rsp+88h+var_50]
0x180015595  mov     rcx, [rax]; hMutex
0x180015598  test    rcx, rcx
0x18001559b  jz      short loc_1800155A3
0x18001559d  call    cs:__imp_ReleaseMutex
0x1800155a3  xor     eax, eax
0x1800155a5  jmp     short loc_1800155AB
0x1800155a7  mov     eax, [rsp+88h+Data]
0x1800155ab  mov     rcx, [rsp+88h+var_10]
0x1800155b0  xor     rcx, rsp; StackCookie
0x1800155b3  call    __security_check_cookie
0x1800155b8  lea     r11, [rsp+88h+var_8]
0x1800155c0  mov     rbx, [r11+18h]
0x1800155c4  mov     rsi, [r11+20h]
0x1800155c8  mov     rsp, r11
0x1800155cb  pop     rdi
0x1800155cc  retn
```
