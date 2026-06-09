# PimIMService::InitComponents(void)

- ea: `0x1800082c4`
- end: `0x180008599`
- name: `?InitComponents@PimIMService@@QEAAJXZ`
- size: `725`
- prototype: `__int64 __fastcall(PimIMService *__hidden this)`
- caller_count: `1`
- callee_count: `13`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180008720`

## callees

- `0x180002da8`
- `0x180003468`
- `0x180004260`
- `0x180004550`
- `0x180004aa8`
- `0x1800082c4`
- `0x180009aa4`
- `0x18000b674`
- `0x18000ba6c`
- `0x18000c800`
- `0x18000d63c`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008351`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000839f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800083f8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180008351`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000839f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800083f8`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000838c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800083de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000847e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000848c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000838c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800083de`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000847e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000848c`
- `PIMSTORE!GetAggregateCache` at `0x1800084e8`
- `PIMSTORE!GetAggregateCache` at `0x1800084e8`
- `unistore!CreateStoreManager` at `0x180008372`
- `unistore!CreateStoreManager` at `0x180008372`

## string_xrefs

- `0x18000846a`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800084a3`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x1800084cb`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000851b`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000853f`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000832e`: `Initializing startup components`

## pseudocode

```c
__int64 __fastcall PimIMService::InitComponents(PimIMService *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // r8
  int StoreManager; // eax
  unsigned int v8; // ebx
  __int64 v9; // r9
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  __int64 v16; // r10
  int AggregateCache; // eax
  __int64 v18; // r9
  int AggregateCacheFromFile; // eax
  int v20; // eax
  __int64 v21; // rdx
  int v22; // eax
  _BYTE v24[8]; // [rsp+30h] [rbp-59h] BYREF
  _QWORD v25[2]; // [rsp+38h] [rbp-51h] BYREF
  __int128 v26; // [rsp+48h] [rbp-41h]
  __int128 v27; // [rsp+58h] [rbp-31h]
  _BYTE v28[56]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE v29[16]; // [rsp+A0h] [rbp+17h] BYREF

  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x200) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context,
      SETUP_START,
      a3,
      1,
      v29);
  v24[1] = 1;
  if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x80u) != 0 )
    McTemplateU0s_EventWriteTransfer(this, a2, "Initializing startup components");
  if ( !*((_QWORD *)this + 28) )
  {
    EnterCriticalSection(&g_shutdownLock);
    StoreManager = FailOnServiceShutdown(v5, v4, v6);
    v8 = StoreManager;
    if ( StoreManager < 0 )
    {
      v9 = 839;
LABEL_22:
      Log_HREvent(
        (unsigned int)StoreManager,
        1,
        "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
        v9);
      LeaveCriticalSection(&g_shutdownLock);
      goto LABEL_36;
    }
    StoreManager = CreateStoreManager(0, (char *)this + 224);
    v8 = StoreManager;
    if ( StoreManager < 0 )
    {
      v9 = 840;
      goto LABEL_22;
    }
    LeaveCriticalSection(&g_shutdownLock);
  }
  if ( !*((_QWORD *)this + 27) )
  {
    EnterCriticalSection(&g_shutdownLock);
    StoreManager = FailOnServiceShutdown(v11, v10, v12);
    v8 = StoreManager;
    if ( StoreManager < 0 )
    {
      v9 = 847;
      goto LABEL_22;
    }
    StoreManager = (*(__int64 (__fastcall **)(PimIMService *))(*(_QWORD *)this + 120LL))(this);
    v8 = StoreManager;
    if ( StoreManager < 0 )
    {
      v9 = 848;
      goto LABEL_22;
    }
    LeaveCriticalSection(&g_shutdownLock);
  }
  if ( !*((_DWORD *)this + 58) )
  {
    EnterCriticalSection(&g_shutdownLock);
    StoreManager = FailOnServiceShutdown(v14, v13, v15);
    v8 = StoreManager;
    if ( StoreManager < 0 )
    {
      v9 = 854;
      goto LABEL_22;
    }
    v16 = *((_QWORD *)this + 28);
    v25[0] = 3221225471LL;
    v26 = 0;
    v25[1] = 18;
    v27 = 0;
    StoreManager = (*(__int64 (__fastcall **)(__int64, _QWORD *, unsigned __int64, char *))(*(_QWORD *)v16 + 232LL))(
                     v16,
                     v25,
                     ((unsigned __int64)this + 208) & -(__int64)(this != 0),
                     (char *)this + 232);
    v8 = StoreManager;
    if ( StoreManager < 0 )
    {
      v9 = 860;
      goto LABEL_22;
    }
    LeaveCriticalSection(&g_shutdownLock);
  }
  AggregateCache = FailOnServiceShutdown((__int64)this, a2, a3);
  v8 = AggregateCache;
  if ( AggregateCache < 0 )
  {
    v18 = 866;
LABEL_26:
    Log_HREvent(
      (unsigned int)AggregateCache,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v18);
    goto LABEL_36;
  }
  AggregateCacheFromFile = PimIMService::_LoadAggregateCacheFromFile(this);
  if ( AggregateCacheFromFile < 0 )
    Log_HREvent(
      (unsigned int)AggregateCacheFromFile,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      867);
  AggregateCache = GetAggregateCache(1, *((_QWORD *)this + 27));
  v8 = AggregateCache;
  if ( AggregateCache < 0 )
  {
    v18 = 872;
    goto LABEL_26;
  }
  TransactionData::TransactionData((TransactionData *)v28);
  v20 = PimIMService::SendCustomEvent(this, (const struct TransactionData *)v28);
  if ( v20 < 0 )
    Log_HREvent(
      (unsigned int)v20,
      0,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      879);
  v22 = PimIMService::_EnsureIndexesUpToDate((HANDLE *)this, v21);
  v8 = v22;
  if ( v22 >= 0 )
  {
    TransactionData::~TransactionData((TransactionData *)v28);
    v8 = 0;
  }
  else
  {
    Log_HREvent(
      (unsigned int)v22,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      886);
    TransactionData::~TransactionData((TransactionData *)v28);
  }
LABEL_36:
  tlx::_UndoSolo__lambda_7388b6b5fd27cdc8154165a3ea707add___::__UndoSolo__lambda_7388b6b5fd27cdc8154165a3ea707add___(v24);
  return v8;
}

```

## disassembly

```asm
0x1800082c4  mov     [rsp-8+arg_8], rbx
0x1800082c9  mov     [rsp-8+arg_10], rsi
0x1800082ce  push    rbp
0x1800082cf  push    rdi
0x1800082d0  push    r12
0x1800082d2  push    r13
0x1800082d4  push    r14
0x1800082d6  lea     rbp, [rsp-37h]
0x1800082db  sub     rsp, 0C0h
0x1800082e2  mov     rax, cs:__security_cookie
0x1800082e9  xor     rax, rsp
0x1800082ec  mov     [rbp+57h+var_30], rax
0x1800082f0  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits+1, 2
0x1800082f7  mov     rdi, rcx
0x1800082fa  mov     r12d, 1
0x180008300  jz      short loc_180008321
0x180008302  lea     rax, [rbp+57h+var_40]
0x180008306  mov     r9d, r12d
0x180008309  lea     rdx, SETUP_START
0x180008310  mov     [rsp+0E0h+var_C0], rax
0x180008315  lea     rcx, MICROSOFT_WINDOWS_USERDATAACCESS_PIMINDEXMAINTENANCE_Context
0x18000831c  call    McGenEventWrite_EventWriteTransfer
0x180008321  cmp     byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 0
0x180008328  mov     [rbp+57h+var_AF], r12b
0x18000832c  jge     short loc_18000833A
0x18000832e  lea     r8, aInitializingSt; "Initializing startup components"
0x180008335  call    McTemplateU0s_EventWriteTransfer
0x18000833a  lea     rsi, [rdi+0E0h]
0x180008341  cmp     qword ptr [rsi], 0
0x180008345  lea     r13, ?g_shutdownLock@@3Vrecursive_mutex@utl@@A; utl::recursive_mutex g_shutdownLock
0x18000834c  jnz     short loc_180008392
0x18000834e  mov     rcx, r13; lpCriticalSection
0x180008351  call    cs:__imp_EnterCriticalSection
0x180008357  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x18000835c  mov     ebx, eax
0x18000835e  test    eax, eax
0x180008360  jns     short loc_18000836D
0x180008362  mov     r9d, 347h
0x180008368  jmp     loc_18000846A
0x18000836d  mov     rdx, rsi
0x180008370  xor     ecx, ecx
0x180008372  call    cs:__imp_CreateStoreManager
0x180008378  mov     ebx, eax
0x18000837a  test    eax, eax
0x18000837c  jns     short loc_180008389
0x18000837e  mov     r9d, 348h
0x180008384  jmp     loc_18000846A
0x180008389  mov     rcx, r13; lpCriticalSection
0x18000838c  call    cs:__imp_LeaveCriticalSection
0x180008392  cmp     qword ptr [rdi+0D8h], 0
0x18000839a  jnz     short loc_1800083E4
0x18000839c  mov     rcx, r13; lpCriticalSection
0x18000839f  call    cs:__imp_EnterCriticalSection
0x1800083a5  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x1800083aa  mov     ebx, eax
0x1800083ac  test    eax, eax
0x1800083ae  jns     short loc_1800083BB
0x1800083b0  mov     r9d, 34Fh
0x1800083b6  jmp     loc_18000846A
0x1800083bb  mov     rax, [rdi]
0x1800083be  mov     rcx, rdi
0x1800083c1  mov     rax, [rax+78h]
0x1800083c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800083ca  mov     ebx, eax
0x1800083cc  test    eax, eax
0x1800083ce  jns     short loc_1800083DB
0x1800083d0  mov     r9d, 350h
0x1800083d6  jmp     loc_18000846A
0x1800083db  mov     rcx, r13; lpCriticalSection
0x1800083de  call    cs:__imp_LeaveCriticalSection
0x1800083e4  lea     r14, [rdi+0E8h]
0x1800083eb  cmp     dword ptr [r14], 0
0x1800083ef  jnz     loc_180008492
0x1800083f5  mov     rcx, r13; lpCriticalSection
0x1800083f8  call    cs:__imp_EnterCriticalSection
0x1800083fe  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x180008403  mov     ebx, eax
0x180008405  test    eax, eax
0x180008407  jns     short loc_180008411
0x180008409  mov     r9d, 356h
0x18000840f  jmp     short loc_18000846A
0x180008411  mov     r10, [rsi]
0x180008414  lea     rcx, [rdi+0D0h]
0x18000841b  xorps   xmm0, xmm0
0x18000841e  mov     rax, rdi
0x180008421  movups  [rbp+57h+var_A8], xmm0
0x180008425  neg     rax
0x180008428  mov     dword ptr [rbp+57h+var_A8], 0BFFFFFFFh
0x18000842f  movups  [rbp+57h+var_98], xmm0
0x180008433  mov     qword ptr [rbp+57h+var_A8+8], 12h
0x18000843b  sbb     r8, r8
0x18000843e  movups  [rbp+57h+var_88], xmm0
0x180008442  mov     rdx, [r10]
0x180008445  and     r8, rcx
0x180008448  mov     r9, r14
0x18000844b  mov     rcx, r10
0x18000844e  mov     rax, [rdx+0E8h]
0x180008455  lea     rdx, [rbp+57h+var_A8]
0x180008459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000845e  mov     ebx, eax
0x180008460  test    eax, eax
0x180008462  jns     short loc_180008489
0x180008464  mov     r9d, 35Ch
0x18000846a  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008471  mov     edx, r12d
0x180008474  mov     ecx, eax
0x180008476  call    Log_HREvent
0x18000847b  mov     rcx, r13; lpCriticalSection
0x18000847e  call    cs:__imp_LeaveCriticalSection
0x180008484  jmp     loc_180008566
0x180008489  mov     rcx, r13; lpCriticalSection
0x18000848c  call    cs:__imp_LeaveCriticalSection
0x180008492  call    ?FailOnServiceShutdown@@YAJXZ; FailOnServiceShutdown(void)
0x180008497  mov     ebx, eax
0x180008499  test    eax, eax
0x18000849b  jns     short loc_1800084B9
0x18000849d  mov     r9d, 362h
0x1800084a3  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800084aa  mov     edx, r12d
0x1800084ad  mov     ecx, eax
0x1800084af  call    Log_HREvent
0x1800084b4  jmp     loc_180008566
0x1800084b9  mov     rcx, rdi; this
0x1800084bc  call    ?_LoadAggregateCacheFromFile@PimIMService@@AEAAJXZ; PimIMService::_LoadAggregateCacheFromFile(void)
0x1800084c1  test    eax, eax
0x1800084c3  jns     short loc_1800084DB
0x1800084c5  mov     r9d, 363h
0x1800084cb  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x1800084d2  xor     edx, edx
0x1800084d4  mov     ecx, eax
0x1800084d6  call    Log_HREvent
0x1800084db  mov     rdx, [rdi+0D8h]
0x1800084e2  xor     r8d, r8d
0x1800084e5  mov     ecx, r12d
0x1800084e8  call    cs:__imp_GetAggregateCache
0x1800084ee  mov     ebx, eax
0x1800084f0  test    eax, eax
0x1800084f2  jns     short loc_1800084FC
0x1800084f4  mov     r9d, 368h
0x1800084fa  jmp     short loc_1800084A3
0x1800084fc  lea     rcx, [rbp+57h+var_78]; this
0x180008500  call    ??0TransactionData@@QEAA@XZ; TransactionData::TransactionData(void)
0x180008505  lea     rdx, [rbp+57h+var_78]; struct TransactionData *
0x180008509  mov     rcx, rdi; this
0x18000850c  call    ?SendCustomEvent@PimIMService@@AEAAJPEBUTransactionData@@@Z; PimIMService::SendCustomEvent(TransactionData const *)
0x180008511  test    eax, eax
0x180008513  jns     short loc_18000852B
0x180008515  mov     r9d, 36Fh
0x18000851b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008522  xor     edx, edx
0x180008524  mov     ecx, eax
0x180008526  call    Log_HREvent
0x18000852b  mov     rcx, rdi; this
0x18000852e  call    ?_EnsureIndexesUpToDate@PimIMService@@AEAAJXZ; PimIMService::_EnsureIndexesUpToDate(void)
0x180008533  mov     ebx, eax
0x180008535  test    eax, eax
0x180008537  jns     short loc_18000855B
0x180008539  mov     r9d, 376h
0x18000853f  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x180008546  mov     edx, r12d
0x180008549  mov     ecx, eax
0x18000854b  call    Log_HREvent
0x180008550  lea     rcx, [rbp+57h+var_78]; this
0x180008554  call    ??1TransactionData@@QEAA@XZ; TransactionData::~TransactionData(void)
0x180008559  jmp     short loc_180008566
0x18000855b  lea     rcx, [rbp+57h+var_78]; this
0x18000855f  call    ??1TransactionData@@QEAA@XZ; TransactionData::~TransactionData(void)
0x180008564  xor     ebx, ebx
0x180008566  lea     rcx, [rbp+57h+var_B0]
0x18000856a  call    tlx___UndoSolo__lambda_7388b6b5fd27cdc8154165a3ea707add_______UndoSolo__lambda_7388b6b5fd27cdc8154165a3ea707add___
0x18000856f  mov     eax, ebx
0x180008571  mov     rcx, [rbp+57h+var_30]
0x180008575  xor     rcx, rsp; StackCookie
0x180008578  call    __security_check_cookie
0x18000857d  lea     r11, [rsp+0E0h+var_20]
0x180008585  mov     rbx, [r11+38h]
0x180008589  mov     rsi, [r11+40h]
0x18000858d  mov     rsp, r11
0x180008590  pop     r14
0x180008592  pop     r13
0x180008594  pop     r12
0x180008596  pop     rdi
0x180008597  pop     rbp
0x180008598  retn
```
