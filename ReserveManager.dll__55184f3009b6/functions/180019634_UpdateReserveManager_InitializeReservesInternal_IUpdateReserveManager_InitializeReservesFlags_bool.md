# UpdateReserveManager::InitializeReservesInternal(IUpdateReserveManager::InitializeReservesFlags,bool *)

- ea: `0x180019634`
- end: `0x180019d21`
- name: `?InitializeReservesInternal@UpdateReserveManager@@AEAAJW4InitializeReservesFlags@IUpdateReserveManager@@PEA_N@Z`
- size: `1773`
- prototype: `__int64 __fastcall(__int64, unsigned int)`
- caller_count: `3`
- callee_count: `15`
- tags: `loader_planting, installer_update`

## callers

- `0x1800155e0`
- `0x180015d74`
- `0x1800191f0`

## callees

- `0x180003870`
- `0x1800042f4`
- `0x18000fafc`
- `0x180013770`
- `0x180014854`
- `0x180015ad0`
- `0x180015e20`
- `0x1800166a8`
- `0x180016d98`
- `0x180019634`
- `0x18001dd04`
- `0x18001ee88`
- `0x18001faf0`
- `0x1800248e0`
- `0x1800287e4`

## import_xrefs

- `ntdll!NtFsControlFile` at `0x18001973e`
- `ntdll!NtFsControlFile` at `0x18001973e`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180019aba`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x180019aba`

## string_xrefs

- `0x1800196af`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001974a`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019acc`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019af9`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019b26`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019b58`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019c5a`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019c84`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019cae`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x1800196cb`: `UpdateReserveManager::InitializeReservesInternal`
- `0x18001975f`: `UpdateReserveManager::InitializeReservesInternal`
- `0x180019ae1`: `UpdateReserveManager::InitializeReservesInternal`
- `0x180019b0e`: `UpdateReserveManager::InitializeReservesInternal`
- `0x180019b3b`: `UpdateReserveManager::InitializeReservesInternal`
- `0x180019b6d`: `UpdateReserveManager::InitializeReservesInternal`
- `0x180019c6f`: `UpdateReserveManager::InitializeReservesInternal`
- `0x180019c99`: `UpdateReserveManager::InitializeReservesInternal`
- `0x180019cc3`: `UpdateReserveManager::InitializeReservesInternal`
- `0x18001976b`: `::NtFsControlFile(m_VolumePathHandle, nullptr, nullptr, nullptr, &IoStatusBlock, ( ((0x00000009) << 16) | ((0) << 14) | ((263) << 2) | (0) ), nullptr, 0, nullptr, 0)`
- `0x180019aed`: `::ULongLongAdd(StorageState.UsedSpaceInUpdateScratch, FreeSpaceToLeaveInUpdateScratch, &FinalScratchReserveSize)`
- `0x180019ca5`: `::ULongLongAdd(FreeSpaceForResizing, AvailableFreeSpaceInUpdateScratch, &FreeSpaceForResizing)`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::InitializeReservesInternal(__int64 a1, unsigned int a2)
{
  __int64 result; // rax
  bool v5; // r14
  unsigned int v6; // esi
  void *v7; // rcx
  int v8; // ecx
  unsigned int v9; // ebx
  unsigned __int64 v10; // r12
  unsigned __int64 v11; // r15
  unsigned __int64 v12; // r13
  unsigned __int64 v13; // rdi
  unsigned int v14; // r12d
  __int64 v15; // r9
  unsigned __int64 v16; // rax
  unsigned __int64 v17; // r10
  unsigned __int64 v18; // r13
  __int64 v19; // rdx
  unsigned __int64 v20; // r8
  unsigned __int64 v21; // rax
  unsigned __int64 v22; // rcx
  unsigned __int64 v23; // rcx
  unsigned __int64 v24; // rdx
  unsigned __int64 v25; // r8
  unsigned __int64 v26; // r9
  unsigned __int64 v27; // r8
  const unsigned __int16 *v28; // rdx
  const char *v29; // rax
  unsigned __int64 v30; // rdi
  unsigned __int64 v31; // r15
  const char *v32; // [rsp+50h] [rbp-B0h] BYREF
  const char *v33; // [rsp+58h] [rbp-A8h]
  __int64 v34; // [rsp+60h] [rbp-A0h]
  const char *v35; // [rsp+68h] [rbp-98h]
  int v36; // [rsp+70h] [rbp-90h] BYREF
  unsigned __int64 v37; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int64 v38; // [rsp+80h] [rbp-80h]
  unsigned __int64 v39; // [rsp+88h] [rbp-78h]
  unsigned __int64 v40; // [rsp+90h] [rbp-70h]
  unsigned __int64 v41; // [rsp+98h] [rbp-68h] BYREF
  unsigned __int64 v42; // [rsp+A0h] [rbp-60h] BYREF
  unsigned __int64 v43; // [rsp+A8h] [rbp-58h]
  unsigned __int64 v44; // [rsp+B0h] [rbp-50h]
  unsigned __int64 v45; // [rsp+B8h] [rbp-48h]
  unsigned __int64 v46; // [rsp+C0h] [rbp-40h]
  char v47[8]; // [rsp+D0h] [rbp-30h] BYREF
  unsigned __int64 v48; // [rsp+D8h] [rbp-28h]
  unsigned __int64 v49; // [rsp+E8h] [rbp-18h] BYREF
  _QWORD v50[2]; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+100h] [rbp+0h]
  __int64 v52; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v53[2]; // [rsp+118h] [rbp+18h] BYREF
  unsigned __int64 v54; // [rsp+128h] [rbp+28h]
  unsigned __int64 v55; // [rsp+130h] [rbp+30h]
  __int64 v56; // [rsp+138h] [rbp+38h]
  _BYTE v57[112]; // [rsp+140h] [rbp+40h] BYREF
  __int128 v58; // [rsp+1B0h] [rbp+B0h] BYREF
  __int128 v59; // [rsp+1C0h] [rbp+C0h]
  unsigned __int64 v60[2]; // [rsp+1D0h] [rbp+D0h]
  unsigned __int64 v61; // [rsp+1E0h] [rbp+E0h]
  struct _IO_STATUS_BLOCK IoStatusBlock; // [rsp+1E8h] [rbp+E8h] BYREF

  result = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)a1);
  if ( (int)result >= 0 )
  {
    v36 = 0;
    v5 = 1;
    v6 = a2 | 1;
    if ( (a2 & 2) == 0 )
      v6 = a2;
    result = UpdateReserveManager::GetActiveScenario((HKEY *)a1, (enum IUpdateReserveManager::ScenarioId *)&v36);
    if ( (int)result >= 0 )
    {
      if ( (v6 & 1) == 0 && v36 )
      {
        v34 = 1835;
        v32 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v33 = "UpdateReserveManager::InitializeReservesInternal";
        v35 = "((SCODE) (((unsigned long)(1)<<31) | ((unsigned long)(15)<<16) | ((unsigned long)(0x975))) )";
        RtlReportErrorOrigination(&v32, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2148469109LL);
        return 2148469109LL;
      }
      v7 = *(void **)(a1 + 128);
      IoStatusBlock = 0;
      v8 = NtFsControlFile(v7, 0, 0, 0, &IoStatusBlock, 0x9041Cu, 0, 0, 0, 0);
      if ( v8 < 0 )
      {
        v34 = 1852;
        v32 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
        v33 = "UpdateReserveManager::InitializeReservesInternal";
        v35 = "::NtFsControlFile(m_VolumePathHandle, nullptr, nullptr, nullptr, &IoStatusBlock, ( ((0x00000009) << 16) | "
              "((0) << 14) | ((263) << 2) | (0) ), nullptr, 0, nullptr, 0)";
        v9 = ConvertNtStatusToHResult(v8);
        RtlReportErrorOrigination(&v32, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, v9);
        return v9;
      }
      v58 = 0;
      v61 = 0;
      v59 = 0;
      *(_OWORD *)v60 = 0;
      result = UpdateReserveManager::GetInitializationParameters(
                 (UpdateReserveManager *)a1,
                 (struct ReserveInitParams *)&v58);
      if ( (int)result >= 0 )
      {
        v10 = v60[0];
        v11 = *((_QWORD *)&v58 + 1);
        v12 = v59;
        v13 = v60[1];
        v40 = v58;
        v38 = *((_QWORD *)&v59 + 1);
        v44 = v61;
        v39 = v60[0];
        memset_0(v57, 0, sizeof(v57));
        result = UpdateReserveManager::GetReserveAndUserState(
                   (WCHAR *)a1,
                   v40,
                   v38,
                   v10,
                   (struct DiskStorageState *)v57);
        if ( (int)result >= 0 )
        {
          v46 = v12;
          v14 = 0;
          v45 = v11;
          while ( 1 )
          {
            memset_0(v47, 0, 0x70u);
            result = UpdateReserveManager::GetReserveAndUserState(
                       (WCHAR *)a1,
                       v40,
                       v38,
                       v39,
                       (struct DiskStorageState *)v47);
            if ( (int)result < 0 )
              return result;
            v15 = v56;
            v16 = 0;
            v36 = v6 & 2;
            if ( (v6 & 2) != 0 )
              v15 = 0;
            v17 = 0;
            v56 = v15;
            if ( (v6 & 2) == 0 )
            {
              v17 = v12 & -(__int64)(v14 < 3);
              v16 = v11;
            }
            v11 = v16;
            v43 = v17;
            if ( v54 <= v44 )
            {
              v18 = v53[1];
              v19 = 0;
            }
            else
            {
              v18 = v55 + v44;
              if ( v55 + v44 < v55 )
              {
                v34 = 1928;
                v32 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
                v33 = "UpdateReserveManager::InitializeReservesInternal";
                v29 = "::ULongLongAdd(StorageState.UsedSpaceInUpdateScratch, FreeSpaceToLeaveInUpdateScratch, &FinalScratchReserveSize)";
LABEL_64:
                v35 = v29;
                RtlReportErrorOrigination(&v32, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942934LL);
                return 2147942934LL;
              }
              v19 = v54 - v44;
            }
            v20 = v48 + v51;
            if ( v48 + v51 < v48 )
            {
              v34 = 1937;
              v32 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
              v33 = "UpdateReserveManager::InitializeReservesInternal";
              v29 = "::ULongLongAdd(StorageState.FreeSpaceInHard, StorageState.FreeSpaceInSoft, &FreeSpaceForResizing)";
              goto LABEL_64;
            }
            v21 = v20 + v19;
            if ( v20 + v19 < v20 )
            {
              v34 = 1938;
              v32 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
              v33 = "UpdateReserveManager::InitializeReservesInternal";
              v29 = "::ULongLongAdd(FreeSpaceForResizing, AvailableFreeSpaceInUpdateScratch, &FreeSpaceForResizing)";
              goto LABEL_64;
            }
            v22 = v21 + v15;
            if ( v21 + v15 < v21 )
            {
              v34 = 1939;
              v32 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
              v33 = "UpdateReserveManager::InitializeReservesInternal";
              v29 = "::ULongLongAdd(FreeSpaceForResizing, StorageState.FreeSpaceInUser, &FreeSpaceForResizing)";
              goto LABEL_64;
            }
            if ( v11 <= v22 )
            {
              v23 = v22 - v11;
            }
            else
            {
              v37 = v11 - v22;
              result = UpdateReserveManager::ReturnSpaceToUser(a1, 0, v13, &v49, v50, &v52, v53, &v37);
              if ( (int)result < 0 )
                return result;
              v17 = v43;
              v23 = 0;
            }
            v24 = v49;
            if ( v49 >= v13 || !v23 )
              goto LABEL_34;
            if ( v13 < v49 )
            {
              v34 = 1972;
              v32 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
              v33 = "UpdateReserveManager::InitializeReservesInternal";
              v29 = "::ULongLongSub(MinDesirableHardReserveSize, StorageState.UsedSpaceInHardTowardsTarget, &NeedForHard)";
              goto LABEL_64;
            }
            if ( v13 - v49 < v23 )
              break;
            v24 = v23 + v49;
            if ( v23 + v49 < v49 )
            {
              v34 = 1981;
              v32 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
              v33 = "UpdateReserveManager::InitializeReservesInternal";
              v29 = "::ULongLongAdd(StorageState.UsedSpaceInHardTowardsTarget, FreeSpaceForResizing, &StorageState.UsedSp"
                    "aceInHardTowardsTarget)";
              goto LABEL_64;
            }
            v23 = 0;
            v49 = v24;
            v25 = 0;
LABEL_35:
            if ( v14 >= 3 )
            {
              if ( v24 > v13 )
                v24 = v13;
              result = UpdateReserveManager::SetReserveSizes((UpdateReserveManager *)a1, v24, 0, 0, 0);
              if ( (int)result >= 0 )
              {
LABEL_55:
                if ( !*(_BYTE *)(a1 + 1177) )
                  StorageReserveHelper::MarkPredefinedSoftReserveLocations((StorageReserveHelper *)(a1 + 656), v28);
                if ( v36
                  || (result = UpdateReserveManager::ClearTemporaryReserveInitParams((HKEY *)a1), (int)result >= 0) )
                {
                  memset_0(v47, 0, 0x70u);
                  v30 = v39;
                  v31 = v38;
                  result = UpdateReserveManager::GetReserveAndUserState(
                             (WCHAR *)a1,
                             v40,
                             v38,
                             v39,
                             (struct DiskStorageState *)v47);
                  if ( (int)result >= 0 )
                  {
                    CUpdateReserveManagerDiagnostics::ReportInitializeReserves(
                      (const char *)(a1 + 1200),
                      v6,
                      v5,
                      v31,
                      v30,
                      v46,
                      v45,
                      v44,
                      (struct DiskStorageState *)v57,
                      (struct DiskStorageState *)v47);
                    return 0;
                  }
                }
              }
              return result;
            }
            v26 = (v17 - v11) & -(__int64)(v11 < v17);
            if ( v26 <= v23 )
            {
              if ( v25 < v26 )
              {
                v34 = 2058;
                v32 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
                v33 = "UpdateReserveManager::InitializeReservesInternal";
                v29 = "::ULongLongSub(FreeSpaceForResizing, AdjustmentForUser, &FreeSpaceForResizing)";
                goto LABEL_64;
              }
              v27 = v25 - v26;
            }
            else
            {
              v37 = v26 - v23;
              result = UpdateReserveManager::ReturnSpaceToUser(a1, 1, v13, &v49, v50, &v52, v53, &v37);
              if ( (int)result < 0 )
                return result;
              v24 = v49;
              v27 = 0;
            }
            v41 = v27;
            v37 = 0;
            v42 = 0;
            result = UpdateReserveManager::DetermineReserveSize(
                       (UpdateReserveManager *)a1,
                       v50[0] + v24,
                       v38,
                       &v41,
                       &v37);
            if ( (int)result < 0 )
              return result;
            result = UpdateReserveManager::DetermineReserveSize(
                       (UpdateReserveManager *)a1,
                       v52 + v53[0],
                       v39,
                       &v41,
                       &v42);
            if ( (int)result < 0 )
              return result;
            if ( (int)UpdateReserveManager::SetReserveSizes((UpdateReserveManager *)a1, v37, v42, v18, 1) >= 0 )
            {
              v5 = 0;
              goto LABEL_55;
            }
            Sleep(0x3E8u);
            v12 = v43;
            ++v14;
          }
          v24 = v13;
          v23 -= v13 - v49;
          v49 = v13;
LABEL_34:
          v25 = v23;
          goto LABEL_35;
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180019634  mov     [rsp-8+arg_10], rbx
0x180019639  push    rbp
0x18001963a  push    rsi
0x18001963b  push    rdi
0x18001963c  push    r12
0x18001963e  push    r13
0x180019640  push    r14
0x180019642  push    r15
0x180019644  lea     rbp, [rsp-100h]
0x18001964c  sub     rsp, 200h
0x180019653  mov     rax, cs:__security_cookie
0x18001965a  xor     rax, rsp
0x18001965d  mov     [rbp+130h+var_38], rax
0x180019664  mov     edi, edx
0x180019666  mov     rbx, rcx
0x180019669  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x18001966e  xor     r15d, r15d
0x180019671  test    eax, eax
0x180019673  js      loc_180019CF7
0x180019679  mov     esi, edi
0x18001967b  mov     [rsp+230h+var_1C0], r15d
0x180019680  lea     r14d, [r15+1]
0x180019684  mov     rcx, rbx; this
0x180019687  or      esi, r14d
0x18001968a  lea     rdx, [rsp+230h+var_1C0]; enum IUpdateReserveManager::ScenarioId *
0x18001968f  test    dil, 2
0x180019693  cmovz   esi, edi
0x180019696  call    ?GetActiveScenario@UpdateReserveManager@@AEAAJPEAW4ScenarioId@IUpdateReserveManager@@@Z; UpdateReserveManager::GetActiveScenario(IUpdateReserveManager::ScenarioId *)
0x18001969b  test    eax, eax
0x18001969d  js      loc_180019CF7
0x1800196a3  test    r14b, sil
0x1800196a6  jnz     short loc_1800196FD
0x1800196a8  cmp     [rsp+230h+var_1C0], r15d
0x1800196ad  jz      short loc_1800196FD
0x1800196af  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x1800196b6  mov     [rsp+230h+var_1D0], 72Bh
0x1800196bf  mov     [rsp+230h+var_1E0], rax
0x1800196c4  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x1800196cb  lea     rax, aUpdatereservem_44; "UpdateReserveManager::InitializeReserve"...
0x1800196d2  mov     r8d, 800F0975h
0x1800196d8  mov     [rsp+230h+var_1D8], rax
0x1800196dd  lea     rcx, [rsp+230h+var_1E0]
0x1800196e2  lea     rax, aScodeUnsignedL_5; "((SCODE) (((unsigned long)(1)<<31) | (("...
0x1800196e9  mov     [rsp+230h+var_1C8], rax
0x1800196ee  call    RtlReportErrorOrigination
0x1800196f3  mov     eax, 800F0975h
0x1800196f8  jmp     loc_180019CF7
0x1800196fd  mov     rcx, [rbx+80h]; FileHandle
0x180019704  lea     rax, [rbp+130h+var_48]
0x18001970b  mov     [rsp+230h+OutputBufferLength], r15d; OutputBufferLength
0x180019710  xorps   xmm0, xmm0
0x180019713  mov     [rsp+230h+OutputBuffer], r15; OutputBuffer
0x180019718  xor     r9d, r9d; ApcContext
0x18001971b  mov     [rsp+230h+InputBufferLength], r15d; InputBufferLength
0x180019720  xor     r8d, r8d; ApcRoutine
0x180019723  mov     [rsp+230h+InputBuffer], r15; InputBuffer
0x180019728  xor     edx, edx; Event
0x18001972a  mov     [rsp+230h+FsControlCode], 9041Ch; FsControlCode
0x180019732  mov     [rsp+230h+IoStatusBlock], rax; IoStatusBlock
0x180019737  movups  xmmword ptr [rbp+130h+var_48], xmm0
0x18001973e  call    cs:__imp_NtFsControlFile
0x180019744  mov     ecx, eax; Status
0x180019746  test    eax, eax
0x180019748  jns     short loc_180019799
0x18001974a  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180019751  mov     [rsp+230h+var_1D0], 73Ch
0x18001975a  mov     [rsp+230h+var_1E0], rax
0x18001975f  lea     rax, aUpdatereservem_44; "UpdateReserveManager::InitializeReserve"...
0x180019766  mov     [rsp+230h+var_1D8], rax
0x18001976b  lea     rax, aNtfscontrolfil; "::NtFsControlFile(m_VolumePathHandle, n"...
0x180019772  mov     [rsp+230h+var_1C8], rax
0x180019777  call    ConvertNtStatusToHResult
0x18001977c  mov     r8d, eax
0x18001977f  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180019786  lea     rcx, [rsp+230h+var_1E0]
0x18001978b  mov     ebx, eax
0x18001978d  call    RtlReportErrorOrigination
0x180019792  mov     eax, ebx
0x180019794  jmp     loc_180019CF7
0x180019799  xorps   xmm0, xmm0
0x18001979c  lea     rdx, [rbp+130h+var_80]; struct ReserveInitParams *
0x1800197a3  xor     eax, eax
0x1800197a5  mov     rcx, rbx; this
0x1800197a8  movups  [rbp+130h+var_80], xmm0
0x1800197af  mov     [rbp+130h+var_50], rax
0x1800197b6  movups  [rbp+130h+var_70], xmm0
0x1800197bd  movups  xmmword ptr [rbp+130h+var_60], xmm0
0x1800197c4  call    ?GetInitializationParameters@UpdateReserveManager@@AEAAJPEAUReserveInitParams@@@Z; UpdateReserveManager::GetInitializationParameters(ReserveInitParams *)
0x1800197c9  test    eax, eax
0x1800197cb  js      loc_180019CF7
0x1800197d1  mov     rax, qword ptr [rbp+130h+var_80]
0x1800197d8  lea     rcx, [rbp+130h+var_F0]; void *
0x1800197dc  mov     r12, [rbp+130h+var_60]
0x1800197e3  xor     edx, edx; Val
0x1800197e5  mov     r15, qword ptr [rbp+130h+var_80+8]
0x1800197ec  mov     r13, qword ptr [rbp+130h+var_70]
0x1800197f3  mov     rdi, [rbp+130h+var_60+8]
0x1800197fa  mov     [rbp+130h+var_1A0], rax
0x1800197fe  lea     r8d, [rdx+70h]; Size
0x180019802  mov     rax, qword ptr [rbp+130h+var_70+8]
0x180019809  mov     [rbp+130h+var_1B0], rax
0x18001980d  mov     rax, [rbp+130h+var_50]
0x180019814  mov     [rbp+130h+var_180], rax
0x180019818  mov     [rbp+130h+var_1A8], r12
0x18001981c  call    memset_0
0x180019821  mov     r8, [rbp+130h+var_1B0]; unsigned __int64
0x180019825  lea     rax, [rbp+130h+var_F0]
0x180019829  mov     rdx, [rbp+130h+var_1A0]; unsigned __int64
0x18001982d  mov     r9, r12; unsigned __int64
0x180019830  mov     rcx, rbx; this
0x180019833  mov     [rsp+230h+IoStatusBlock], rax; struct DiskStorageState *
0x180019838  call    ?GetReserveAndUserState@UpdateReserveManager@@AEAAJ_K00PEAUDiskStorageState@@@Z; UpdateReserveManager::GetReserveAndUserState(unsigned __int64,unsigned __int64,unsigned __int64,DiskStorageState *)
0x18001983d  test    eax, eax
0x18001983f  js      loc_180019CF7
0x180019845  mov     [rbp+130h+var_170], r13
0x180019849  xor     r12d, r12d
0x18001984c  mov     [rbp+130h+var_178], r15
0x180019850  xor     edx, edx; Val
0x180019852  lea     rcx, [rbp+130h+var_160]; void *
0x180019856  lea     r8d, [rdx+70h]; Size
0x18001985a  call    memset_0
0x18001985f  mov     r9, [rbp+130h+var_1A8]; unsigned __int64
0x180019863  lea     rax, [rbp+130h+var_160]
0x180019867  mov     r8, [rbp+130h+var_1B0]; unsigned __int64
0x18001986b  mov     rcx, rbx; this
0x18001986e  mov     rdx, [rbp+130h+var_1A0]; unsigned __int64
0x180019872  mov     [rsp+230h+IoStatusBlock], rax; struct DiskStorageState *
0x180019877  call    ?GetReserveAndUserState@UpdateReserveManager@@AEAAJ_K00PEAUDiskStorageState@@@Z; UpdateReserveManager::GetReserveAndUserState(unsigned __int64,unsigned __int64,unsigned __int64,DiskStorageState *)
0x18001987c  test    eax, eax
0x18001987e  js      loc_180019CF7
0x180019884  mov     r9, [rbp+130h+var_F8]
0x180019888  cmp     r12d, 3
0x18001988c  mov     edx, esi
0x18001988e  mov     eax, 0
0x180019893  sbb     rcx, rcx
0x180019896  and     rcx, r13
0x180019899  and     edx, 2
0x18001989c  mov     [rsp+230h+var_1C0], edx
0x1800198a0  cmovnz  r9, rax
0x1800198a4  xor     r10d, r10d
0x1800198a7  test    edx, edx
0x1800198a9  mov     [rbp+130h+var_F8], r9
0x1800198ad  mov     rdx, [rbp+130h+var_108]
0x1800198b1  cmovz   r10, rcx
0x1800198b5  cmovz   rax, r15
0x1800198b9  mov     rcx, [rbp+130h+var_180]
0x1800198bd  mov     r15, rax
0x1800198c0  mov     [rbp+130h+var_188], r10
0x1800198c4  cmp     rdx, rcx
0x1800198c7  jbe     short loc_1800198DF
0x1800198c9  mov     rax, [rbp+130h+var_100]
0x1800198cd  lea     r13, [rax+rcx]
0x1800198d1  cmp     r13, rax
0x1800198d4  jb      loc_180019ACC
0x1800198da  sub     rdx, rcx
0x1800198dd  jmp     short loc_1800198E5
0x1800198df  mov     r13, [rbp+130h+var_110]
0x1800198e3  xor     edx, edx
0x1800198e5  mov     r8, [rbp+130h+var_130]
0x1800198e9  add     r8, [rbp+130h+var_158]
0x1800198ed  cmp     r8, [rbp+130h+var_158]
0x1800198f1  jb      loc_180019CAE
0x1800198f7  lea     rax, [r8+rdx]
0x1800198fb  cmp     rax, r8
0x1800198fe  jb      loc_180019C84
0x180019904  lea     rcx, [rax+r9]
0x180019908  cmp     rcx, rax
0x18001990b  jb      loc_180019C5A
0x180019911  cmp     r15, rcx
0x180019914  jbe     short loc_180019967
0x180019916  mov     rax, r15
0x180019919  lea     r9, [rbp+130h+var_148]
0x18001991d  sub     rax, rcx
0x180019920  mov     r8, rdi
0x180019923  mov     [rsp+230h+var_1B8], rax
0x180019928  xor     edx, edx
0x18001992a  lea     rax, [rsp+230h+var_1B8]
0x18001992f  mov     rcx, rbx
0x180019932  mov     qword ptr [rsp+230h+InputBufferLength], rax
0x180019937  lea     rax, [rbp+130h+var_118]
0x18001993b  mov     [rsp+230h+InputBuffer], rax
0x180019940  lea     rax, [rbp+130h+var_120]
0x180019944  mov     qword ptr [rsp+230h+FsControlCode], rax
0x180019949  lea     rax, [rbp+130h+var_140]
0x18001994d  mov     [rsp+230h+IoStatusBlock], rax
0x180019952  call    ?ReturnSpaceToUser@UpdateReserveManager@@AEAAJW4ReturnSpaceToUserFlags@1@_KPEA_K2222@Z; UpdateReserveManager::ReturnSpaceToUser(UpdateReserveManager::ReturnSpaceToUserFlags,unsigned __int64,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x180019957  test    eax, eax
0x180019959  js      loc_180019CF7
0x18001995f  mov     r10, [rbp+130h+var_188]
0x180019963  xor     ecx, ecx
0x180019965  jmp     short loc_18001996A
0x180019967  sub     rcx, r15
0x18001996a  mov     rdx, [rbp+130h+var_148]
0x18001996e  cmp     rdx, rdi
0x180019971  jnb     short loc_180019996
0x180019973  test    rcx, rcx
0x180019976  jz      short loc_180019996
0x180019978  cmp     rdi, rdx
0x18001997b  jb      loc_180019B26
0x180019981  mov     rax, rdi
0x180019984  sub     rax, rdx
0x180019987  cmp     rax, rcx
0x18001998a  jnb     short loc_180019A07
0x18001998c  mov     rdx, rdi
0x18001998f  sub     rcx, rax
0x180019992  mov     [rbp+130h+var_148], rdx
0x180019996  mov     r8, rcx
0x180019999  cmp     r12d, 3
0x18001999d  jnb     loc_180019B85
0x1800199a3  mov     rax, r10
0x1800199a6  sub     rax, r15
0x1800199a9  cmp     r15, r10
0x1800199ac  sbb     r9, r9
0x1800199af  and     r9, rax
0x1800199b2  cmp     r9, rcx
0x1800199b5  jbe     short loc_180019A24
0x1800199b7  sub     r9, rcx
0x1800199ba  lea     rax, [rsp+230h+var_1B8]
0x1800199bf  mov     qword ptr [rsp+230h+InputBufferLength], rax
0x1800199c4  mov     r8, rdi
0x1800199c7  lea     rax, [rbp+130h+var_118]
0x1800199cb  mov     [rsp+230h+var_1B8], r9
0x1800199d0  mov     [rsp+230h+InputBuffer], rax
0x1800199d5  lea     r9, [rbp+130h+var_148]
0x1800199d9  lea     rax, [rbp+130h+var_120]
0x1800199dd  mov     edx, r14d
0x1800199e0  mov     qword ptr [rsp+230h+FsControlCode], rax
0x1800199e5  mov     rcx, rbx
0x1800199e8  lea     rax, [rbp+130h+var_140]
0x1800199ec  mov     [rsp+230h+IoStatusBlock], rax
0x1800199f1  call    ?ReturnSpaceToUser@UpdateReserveManager@@AEAAJW4ReturnSpaceToUserFlags@1@_KPEA_K2222@Z; UpdateReserveManager::ReturnSpaceToUser(UpdateReserveManager::ReturnSpaceToUserFlags,unsigned __int64,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *,unsigned __int64 *)
0x1800199f6  test    eax, eax
0x1800199f8  js      loc_180019CF7
0x1800199fe  mov     rdx, [rbp+130h+var_148]
0x180019a02  xor     r8d, r8d
0x180019a05  jmp     short loc_180019A30
0x180019a07  mov     rax, rdx
0x180019a0a  add     rdx, rcx
0x180019a0d  cmp     rdx, rax
0x180019a10  jb      loc_180019AF9
0x180019a16  xor     ecx, ecx
0x180019a18  mov     [rbp+130h+var_148], rdx
0x180019a1c  xor     r8d, r8d
0x180019a1f  jmp     loc_180019999
0x180019a24  cmp     r8, r9
0x180019a27  jb      loc_180019B58
0x180019a2d  sub     r8, r9
0x180019a30  add     rdx, [rbp+130h+var_140]; unsigned __int64
0x180019a34  lea     rax, [rsp+230h+var_1B8]
0x180019a39  mov     [rbp+130h+var_198], r8
0x180019a3d  lea     r9, [rbp+130h+var_198]; unsigned __int64 *
0x180019a41  mov     r8, [rbp+130h+var_1B0]; unsigned __int64
0x180019a45  mov     rcx, rbx; this
0x180019a48  mov     [rsp+230h+IoStatusBlock], rax; unsigned __int64 *
0x180019a4d  mov     [rsp+230h+var_1B8], 0
0x180019a56  mov     [rbp+130h+var_190], 0
0x180019a5e  call    ?DetermineReserveSize@UpdateReserveManager@@AEAAJ_K0PEA_K1@Z; UpdateReserveManager::DetermineReserveSize(unsigned __int64,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x180019a63  test    eax, eax
0x180019a65  js      loc_180019CF7
0x180019a6b  mov     rdx, [rbp+130h+var_118]
0x180019a6f  lea     rax, [rbp+130h+var_190]
0x180019a73  add     rdx, [rbp+130h+var_120]; unsigned __int64
0x180019a77  lea     r9, [rbp+130h+var_198]; unsigned __int64 *
0x180019a7b  mov     r8, [rbp+130h+var_1A8]; unsigned __int64
0x180019a7f  mov     rcx, rbx; this
0x180019a82  mov     [rsp+230h+IoStatusBlock], rax; unsigned __int64 *
0x180019a87  call    ?DetermineReserveSize@UpdateReserveManager@@AEAAJ_K0PEA_K1@Z; UpdateReserveManager::DetermineReserveSize(unsigned __int64,unsigned __int64,unsigned __int64 *,unsigned __int64 *)
0x180019a8c  test    eax, eax
0x180019a8e  js      loc_180019CF7
0x180019a94  mov     r8, [rbp+130h+var_190]; unsigned __int64
0x180019a98  mov     r9, r13; unsigned __int64
0x180019a9b  mov     rdx, [rsp+230h+var_1B8]; unsigned __int64
0x180019aa0  mov     rcx, rbx; this
0x180019aa3  mov     byte ptr [rsp+230h+IoStatusBlock], r14b; bool
0x180019aa8  call    ?SetReserveSizes@UpdateReserveManager@@AEAAJ_K00_N@Z; UpdateReserveManager::SetReserveSizes(unsigned __int64,unsigned __int64,unsigned __int64,bool)
0x180019aad  test    eax, eax
0x180019aaf  jns     loc_180019B53
0x180019ab5  mov     ecx, 3E8h; dwMilliseconds
0x180019aba  call    cs:__imp_Sleep
0x180019ac0  mov     r13, [rbp+130h+var_188]
0x180019ac4  add     r12d, r14d
0x180019ac7  jmp     loc_180019850
0x180019acc  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180019ad3  mov     [rsp+230h+var_1D0], 788h
0x180019adc  mov     [rsp+230h+var_1E0], rax
0x180019ae1  lea     rax, aUpdatereservem_44; "UpdateReserveManager::InitializeReserve"...
0x180019ae8  mov     [rsp+230h+var_1D8], rax
0x180019aed  lea     rax, aUlonglongaddSt_1; "::ULongLongAdd(StorageState.UsedSpaceIn"...
0x180019af4  jmp     loc_180019CD6
0x180019af9  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180019b00  mov     [rsp+230h+var_1D0], 7BDh
0x180019b09  mov     [rsp+230h+var_1E0], rax
0x180019b0e  lea     rax, aUpdatereservem_44; "UpdateReserveManager::InitializeReserve"...
0x180019b15  mov     [rsp+230h+var_1D8], rax
0x180019b1a  lea     rax, aUlonglongaddSt_0; "::ULongLongAdd(StorageState.UsedSpaceIn"...
0x180019b21  jmp     loc_180019CD6
0x180019b26  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180019b2d  mov     [rsp+230h+var_1D0], 7B4h
0x180019b36  mov     [rsp+230h+var_1E0], rax
0x180019b3b  lea     rax, aUpdatereservem_44; "UpdateReserveManager::InitializeReserve"...
  ... truncated ...
```
