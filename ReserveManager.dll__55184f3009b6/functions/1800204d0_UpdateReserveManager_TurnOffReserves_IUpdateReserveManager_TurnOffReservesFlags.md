# UpdateReserveManager::TurnOffReserves(IUpdateReserveManager::TurnOffReservesFlags)

- ea: `0x1800204d0`
- end: `0x180020771`
- name: `?TurnOffReserves@UpdateReserveManager@@UEAAJW4TurnOffReservesFlags@IUpdateReserveManager@@@Z`
- size: `673`
- prototype: `__int64 __fastcall(__int64, int)`
- caller_count: `0`
- callee_count: `8`
- tags: `installer_update`

## callees

- `0x180015ad0`
- `0x18001a8f0`
- `0x18001cb28`
- `0x18001e534`
- `0x18001fd00`
- `0x18001fd60`
- `0x1800204d0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020524`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020553`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800205a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002060d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020647`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020680`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800206ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800206e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002074e`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020524`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020553`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800205a1`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002060d`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020647`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x180020680`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800206ba`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x1800206e6`
- `api-ms-win-core-synch-l1-1-0!ReleaseMutex` at `0x18002074e`

## pseudocode

```c
__int64 __fastcall UpdateReserveManager::TurnOffReserves(__int64 a1, int a2)
{
  signed int v4; // eax
  unsigned int v5; // edi
  __int64 result; // rax
  int v7; // edi
  const char *v8; // r9
  __int64 v9; // rdx
  int v10; // edi
  int ReserveAreaByReserveId; // edi
  int v12; // edi
  int v13; // edi
  int v14; // edi
  int v15; // edi
  HANDLE *v16; // [rsp+40h] [rbp-88h] BYREF
  char v17; // [rsp+48h] [rbp-80h]
  unsigned __int64 v18[2]; // [rsp+58h] [rbp-70h] BYREF
  unsigned __int64 v19; // [rsp+68h] [rbp-60h]
  unsigned __int64 v20[2]; // [rsp+70h] [rbp-58h] BYREF
  unsigned __int64 v21; // [rsp+80h] [rbp-48h]
  unsigned __int64 v22[2]; // [rsp+88h] [rbp-40h] BYREF
  unsigned __int64 v23; // [rsp+98h] [rbp-30h]
  __int64 v24; // [rsp+A0h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  v24 = -2;
  v16 = (HANDLE *)(a1 + 1192);
  v17 = 0;
  v4 = AutoMutexLocker::Lock(&v16);
  v5 = v4;
  if ( v4 < 0 )
  {
    if ( v17 )
    {
      if ( *v16 )
        ReleaseMutex(*v16);
    }
    return v5;
  }
  try
  {
    v7 = UpdateReserveManager::EnsureNotInSafeMode((UpdateReserveManager *)a1);
    if ( v7 >= 0 )
    {
      if ( (a2 & 1) != 0 )
        goto LABEL_19;
      v9 = 1;
      if ( (a2 & 2) != 0 )
        v9 = 3;
      v10 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)a1 + 112LL))(a1, v9);
      if ( v10 >= 0 )
      {
LABEL_19:
        *(_OWORD *)v22 = 0;
        v23 = 0;
        *(_OWORD *)v20 = 0;
        v21 = 0;
        *(_OWORD *)v18 = 0;
        v19 = 0;
        ReserveAreaByReserveId = UpdateReserveManager::QueryReserveAreaByReserveId((WCHAR *)a1, 0, 1u, v22);
        if ( ReserveAreaByReserveId >= 0 )
        {
          v12 = UpdateReserveManager::QueryReserveAreaByReserveId((WCHAR *)a1, 0, 2u, v20);
          if ( v12 >= 0 )
          {
            v13 = UpdateReserveManager::QueryReserveAreaByReserveId((WCHAR *)a1, 0, 3u, v18);
            if ( v13 >= 0 )
            {
              if ( (a2 & 4) != 0 )
              {
                v14 = UpdateReserveManager::SetReserveToZero((UpdateReserveManager *)a1, StorageReserveIdSoft);
                if ( v14 < 0 )
                {
                  if ( v17 && *v16 )
                    ReleaseMutex(*v16);
                  return (unsigned int)v14;
                }
              }
              else
              {
                v15 = UpdateReserveManager::SetReservesToZero((UpdateReserveManager *)a1);
                if ( v15 < 0 )
                {
                  if ( v17 && *v16 )
                    ReleaseMutex(*v16);
                  return (unsigned int)v15;
                }
              }
              CUpdateReserveManagerDiagnostics::ReportTurnOffReserves(
                (const wchar_t *)(a1 + 1200),
                a2,
                v22[0],
                v23,
                v20[0],
                v21,
                v18[0],
                v19);
              if ( v17 && *v16 )
                ReleaseMutex(*v16);
              return 0;
            }
            if ( v17 && *v16 )
              ReleaseMutex(*v16);
            result = (unsigned int)v13;
          }
          else
          {
            if ( v17 && *v16 )
              ReleaseMutex(*v16);
            result = (unsigned int)v12;
          }
        }
        else
        {
          if ( v17 && *v16 )
            ReleaseMutex(*v16);
          result = (unsigned int)ReserveAreaByReserveId;
        }
      }
      else
      {
        if ( v17 && *v16 )
          ReleaseMutex(*v16);
        result = (unsigned int)v10;
      }
    }
    else
    {
      if ( v17 && *v16 )
        ReleaseMutex(*v16);
      result = (unsigned int)v7;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x4C0,
                           (int)"onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp",
                           v8);
  }
  return result;
}

```

## disassembly

```asm
0x1800204d0  mov     rax, rsp
0x1800204d3  push    rsi
0x1800204d4  push    rdi
0x1800204d5  push    r14
0x1800204d7  sub     rsp, 0B0h
0x1800204de  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x1800204e6  mov     [rax+18h], rbx
0x1800204ea  mov     esi, edx
0x1800204ec  mov     rbx, rcx
0x1800204ef  lea     rax, [rcx+4A8h]
0x1800204f6  mov     [rsp+0C8h+var_88], rax
0x1800204fb  mov     [rsp+0C8h+var_80], 0
0x180020500  lea     rcx, [rsp+0C8h+var_88]; this
0x180020505  call    ?Lock@AutoMutexLocker@@QEAAJK@Z; AutoMutexLocker::Lock(ulong)
0x18002050a  mov     edi, eax
0x18002050c  test    eax, eax
0x18002050e  jns     short loc_180020531
0x180020510  cmp     [rsp+0C8h+var_80], 0
0x180020515  jz      short loc_18002052A
0x180020517  mov     rcx, [rsp+0C8h+var_88]
0x18002051c  mov     rcx, [rcx]; hMutex
0x18002051f  test    rcx, rcx
0x180020522  jz      short loc_18002052A
0x180020524  call    cs:__imp_ReleaseMutex
0x18002052a  mov     eax, edi
0x18002052c  jmp     loc_18002075C
0x180020531  mov     rcx, rbx; this
0x180020534  call    ?EnsureNotInSafeMode@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::EnsureNotInSafeMode(void)
0x180020539  mov     edi, eax
0x18002053b  test    eax, eax
0x18002053d  jns     short loc_180020560
0x18002053f  cmp     [rsp+0C8h+var_80], 0
0x180020544  jz      short loc_180020559
0x180020546  mov     rcx, [rsp+0C8h+var_88]
0x18002054b  mov     rcx, [rcx]; hMutex
0x18002054e  test    rcx, rcx
0x180020551  jz      short loc_180020559
0x180020553  call    cs:__imp_ReleaseMutex
0x180020559  mov     eax, edi
0x18002055b  jmp     loc_18002075C
0x180020560  mov     r14d, 3
0x180020566  test    sil, 1
0x18002056a  jnz     short loc_1800205AE
0x18002056c  test    sil, 2
0x180020570  lea     edx, [r14-2]
0x180020574  cmovnz  edx, r14d
0x180020578  mov     rax, [rbx]
0x18002057b  mov     rcx, rbx
0x18002057e  mov     rax, [rax+70h]
0x180020582  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020587  mov     edi, eax
0x180020589  test    eax, eax
0x18002058b  jns     short loc_1800205AE
0x18002058d  cmp     [rsp+0C8h+var_80], 0
0x180020592  jz      short loc_1800205A7
0x180020594  mov     rcx, [rsp+0C8h+var_88]
0x180020599  mov     rcx, [rcx]; hMutex
0x18002059c  test    rcx, rcx
0x18002059f  jz      short loc_1800205A7
0x1800205a1  call    cs:__imp_ReleaseMutex
0x1800205a7  mov     eax, edi
0x1800205a9  jmp     loc_18002075C
0x1800205ae  xorps   xmm0, xmm0
0x1800205b1  xor     eax, eax
0x1800205b3  movups  xmmword ptr [rsp+0C8h+var_40], xmm0
0x1800205bb  mov     [rsp+0C8h+var_30], rax
0x1800205c3  xorps   xmm1, xmm1
0x1800205c6  movups  xmmword ptr [rsp+0C8h+var_58], xmm1
0x1800205cb  mov     [rsp+0C8h+var_48], rax
0x1800205d3  movups  xmmword ptr [rsp+0C8h+var_70], xmm0
0x1800205d8  mov     [rsp+0C8h+var_60], rax
0x1800205dd  lea     r9, [rsp+0C8h+var_40]
0x1800205e5  xor     edx, edx
0x1800205e7  lea     r8d, [rax+1]
0x1800205eb  mov     rcx, rbx
0x1800205ee  call    ?QueryReserveAreaByReserveId@UpdateReserveManager@@AEAAJW4QueryReserveAreaFlags@IUpdateReserveManager@@W4_STORAGE_RESERVE_ID@@PEAURESERVE_AREA_INFORMATION@3@@Z; UpdateReserveManager::QueryReserveAreaByReserveId(IUpdateReserveManager::QueryReserveAreaFlags,_STORAGE_RESERVE_ID,IUpdateReserveManager::RESERVE_AREA_INFORMATION *)
0x1800205f3  mov     edi, eax
0x1800205f5  test    eax, eax
0x1800205f7  jns     short loc_18002061A
0x1800205f9  cmp     [rsp+0C8h+var_80], 0
0x1800205fe  jz      short loc_180020613
0x180020600  mov     rcx, [rsp+0C8h+var_88]
0x180020605  mov     rcx, [rcx]; hMutex
0x180020608  test    rcx, rcx
0x18002060b  jz      short loc_180020613
0x18002060d  call    cs:__imp_ReleaseMutex
0x180020613  mov     eax, edi
0x180020615  jmp     loc_18002075C
0x18002061a  lea     r9, [rsp+0C8h+var_58]
0x18002061f  xor     edx, edx
0x180020621  lea     r8d, [rdx+2]
0x180020625  mov     rcx, rbx
0x180020628  call    ?QueryReserveAreaByReserveId@UpdateReserveManager@@AEAAJW4QueryReserveAreaFlags@IUpdateReserveManager@@W4_STORAGE_RESERVE_ID@@PEAURESERVE_AREA_INFORMATION@3@@Z; UpdateReserveManager::QueryReserveAreaByReserveId(IUpdateReserveManager::QueryReserveAreaFlags,_STORAGE_RESERVE_ID,IUpdateReserveManager::RESERVE_AREA_INFORMATION *)
0x18002062d  mov     edi, eax
0x18002062f  test    eax, eax
0x180020631  jns     short loc_180020654
0x180020633  cmp     [rsp+0C8h+var_80], 0
0x180020638  jz      short loc_18002064D
0x18002063a  mov     rcx, [rsp+0C8h+var_88]
0x18002063f  mov     rcx, [rcx]; hMutex
0x180020642  test    rcx, rcx
0x180020645  jz      short loc_18002064D
0x180020647  call    cs:__imp_ReleaseMutex
0x18002064d  mov     eax, edi
0x18002064f  jmp     loc_18002075C
0x180020654  lea     r9, [rsp+0C8h+var_70]
0x180020659  mov     r8d, r14d
0x18002065c  xor     edx, edx
0x18002065e  mov     rcx, rbx
0x180020661  call    ?QueryReserveAreaByReserveId@UpdateReserveManager@@AEAAJW4QueryReserveAreaFlags@IUpdateReserveManager@@W4_STORAGE_RESERVE_ID@@PEAURESERVE_AREA_INFORMATION@3@@Z; UpdateReserveManager::QueryReserveAreaByReserveId(IUpdateReserveManager::QueryReserveAreaFlags,_STORAGE_RESERVE_ID,IUpdateReserveManager::RESERVE_AREA_INFORMATION *)
0x180020666  mov     edi, eax
0x180020668  test    eax, eax
0x18002066a  jns     short loc_18002068D
0x18002066c  cmp     [rsp+0C8h+var_80], 0
0x180020671  jz      short loc_180020686
0x180020673  mov     rcx, [rsp+0C8h+var_88]
0x180020678  mov     rcx, [rcx]; hMutex
0x18002067b  test    rcx, rcx
0x18002067e  jz      short loc_180020686
0x180020680  call    cs:__imp_ReleaseMutex
0x180020686  mov     eax, edi
0x180020688  jmp     loc_18002075C
0x18002068d  mov     rcx, rbx; this
0x180020690  test    sil, 4
0x180020694  jz      short loc_1800206C7
0x180020696  mov     edx, 2; enum _STORAGE_RESERVE_ID
0x18002069b  call    ?SetReserveToZero@UpdateReserveManager@@AEAAJW4_STORAGE_RESERVE_ID@@@Z; UpdateReserveManager::SetReserveToZero(_STORAGE_RESERVE_ID)
0x1800206a0  mov     edi, eax
0x1800206a2  test    eax, eax
0x1800206a4  jns     short loc_1800206F0
0x1800206a6  cmp     [rsp+0C8h+var_80], 0
0x1800206ab  jz      short loc_1800206C0
0x1800206ad  mov     rcx, [rsp+0C8h+var_88]
0x1800206b2  mov     rcx, [rcx]; hMutex
0x1800206b5  test    rcx, rcx
0x1800206b8  jz      short loc_1800206C0
0x1800206ba  call    cs:__imp_ReleaseMutex
0x1800206c0  mov     eax, edi
0x1800206c2  jmp     loc_18002075C
0x1800206c7  call    ?SetReservesToZero@UpdateReserveManager@@AEAAJXZ; UpdateReserveManager::SetReservesToZero(void)
0x1800206cc  mov     edi, eax
0x1800206ce  test    eax, eax
0x1800206d0  jns     short loc_1800206F0
0x1800206d2  cmp     [rsp+0C8h+var_80], 0
0x1800206d7  jz      short loc_1800206EC
0x1800206d9  mov     rcx, [rsp+0C8h+var_88]
0x1800206de  mov     rcx, [rcx]; hMutex
0x1800206e1  test    rcx, rcx
0x1800206e4  jz      short loc_1800206EC
0x1800206e6  call    cs:__imp_ReleaseMutex
0x1800206ec  mov     eax, edi
0x1800206ee  jmp     short loc_18002075C
0x1800206f0  lea     rcx, [rbx+4B0h]; char *
0x1800206f7  mov     rax, [rsp+0C8h+var_60]
0x1800206fc  mov     [rsp+0C8h+var_90], rax; unsigned __int64
0x180020701  mov     rax, [rsp+0C8h+var_70]
0x180020706  mov     [rsp+0C8h+var_98], rax; unsigned __int64
0x18002070b  mov     rax, [rsp+0C8h+var_48]
0x180020713  mov     [rsp+0C8h+var_A0], rax; unsigned __int64
0x180020718  mov     rax, [rsp+0C8h+var_58]
0x18002071d  mov     [rsp+0C8h+var_A8], rax; unsigned __int64
0x180020722  mov     r9, [rsp+0C8h+var_30]; unsigned __int64
0x18002072a  mov     r8, [rsp+0C8h+var_40]; unsigned __int64
0x180020732  mov     edx, esi; unsigned int
0x180020734  call    ?ReportTurnOffReserves@CUpdateReserveManagerDiagnostics@@SAXPEBDK_K11111@Z; CUpdateReserveManagerDiagnostics::ReportTurnOffReserves(char const *,ulong,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64,unsigned __int64)
0x180020739  nop
0x18002073a  cmp     [rsp+0C8h+var_80], 0
0x18002073f  jz      short loc_180020754
0x180020741  mov     rax, [rsp+0C8h+var_88]
0x180020746  mov     rcx, [rax]; hMutex
0x180020749  test    rcx, rcx
0x18002074c  jz      short loc_180020754
0x18002074e  call    cs:__imp_ReleaseMutex
0x180020754  xor     eax, eax
0x180020756  jmp     short loc_18002075C
0x180020758  mov     eax, [rsp+0C8h+var_78]
0x18002075c  mov     rbx, [rsp+0C8h+arg_10]
0x180020764  add     rsp, 0B0h
0x18002076b  pop     r14
0x18002076d  pop     rdi
0x18002076e  pop     rsi
0x18002076f  retn
```
