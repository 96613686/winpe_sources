# PimIMService::_RebuildContactIndexes(int)

- ea: `0x18000bb20`
- end: `0x18000be75`
- name: `?_RebuildContactIndexes@PimIMService@@AEAAJH@Z`
- size: `853`
- prototype: `__int64 __fastcall(PimIMService *__hidden this, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x1800058d0`
- `0x18000b674`

## callees

- `0x180002da8`
- `0x180004260`
- `0x18000428c`
- `0x1800045b0`
- `0x180004aa8`
- `0x180006f48`
- `0x180007848`
- `0x180009aa4`
- `0x18000bb20`
- `0x18000c734`
- `0x180021240`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bbbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bbd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bc20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bd6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bdd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000be2e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bbbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bbd5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bc20`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bd6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000bdd4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18000be2e`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000bbe1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000bc2b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000bd77`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000bddf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000be39`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000bbe1`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000bc2b`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000bd77`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000bddf`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadPriority` at `0x18000be39`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000bbc8`
- `api-ms-win-core-processthreads-l1-1-0!GetThreadPriority` at `0x18000bbc8`
- `PIMSTORE!GetAggregateCache` at `0x18000bb62`
- `PIMSTORE!GetAggregateCache` at `0x18000bb62`

## string_xrefs

- `0x18000bb9d`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000bc0c`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000bd46`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000bd94`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`
- `0x18000bdb6`: `onecoreuap\base\appmodel\userdataaccess\services\pimindexmaintenance\service\lib\pimimservice.cpp`

## pseudocode

```c
__int64 __fastcall PimIMService::_RebuildContactIndexes(PimIMService *this, int a2)
{
  __int64 v2; // rdx
  int AggregateCache; // eax
  unsigned int v5; // ebx
  __int64 v6; // r9
  BOOL v7; // esi
  HANDLE CurrentThread; // rax
  int ThreadPriority; // ebx
  HANDLE v10; // rax
  int IndexManager; // eax
  int v12; // r14d
  HANDLE v13; // rax
  unsigned int v14; // r13d
  __int64 v15; // rcx
  unsigned int v16; // r14d
  unsigned int v17; // r14d
  int v18; // eax
  int v19; // r12d
  unsigned int i; // r12d
  int v21; // eax
  __int64 v22; // r9
  int v23; // eax
  HANDLE v24; // rax
  HANDLE v25; // rax
  HANDLE v26; // rax
  int v28; // [rsp+30h] [rbp-69h]
  struct IndexedFiltering::IIndexManager *v29; // [rsp+38h] [rbp-61h] BYREF
  unsigned int v30; // [rsp+40h] [rbp-59h] BYREF
  int v31; // [rsp+44h] [rbp-55h]
  __int64 v32; // [rsp+48h] [rbp-51h] BYREF
  struct IndexedFiltering::IIndexManager **v33; // [rsp+50h] [rbp-49h] BYREF
  char v34; // [rsp+58h] [rbp-41h]
  __int64 v35; // [rsp+60h] [rbp-39h] BYREF
  int v36; // [rsp+68h] [rbp-31h]
  _BYTE v37[56]; // [rsp+70h] [rbp-29h] BYREF

  v31 = a2;
  v2 = *((_QWORD *)this + 27);
  v32 = 0;
  AggregateCache = GetAggregateCache(0, v2);
  v5 = AggregateCache;
  if ( AggregateCache < 0 )
  {
    v6 = 1614;
LABEL_5:
    Log_HREvent(
      (unsigned int)AggregateCache,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      v6);
    goto LABEL_44;
  }
  v30 = 0;
  AggregateCache = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v32 + 24LL))(v32, &v30);
  v5 = AggregateCache;
  if ( AggregateCache < 0 )
  {
    v6 = 1617;
    goto LABEL_5;
  }
  v29 = 0;
  v7 = 0;
  CurrentThread = GetCurrentThread();
  ThreadPriority = GetThreadPriority(CurrentThread);
  if ( ThreadPriority != -2 )
  {
    v10 = GetCurrentThread();
    v7 = SetThreadPriority(v10, -2);
  }
  IndexManager = PimIMService::GetIndexManager((struct IndexedFiltering::IIndexManager **)this, 0, 1, &v29);
  v12 = IndexManager;
  if ( IndexManager >= 0 )
  {
    v14 = 0;
    TransactionData::TransactionData((TransactionData *)v37);
    while ( 2 )
    {
      v16 = v30;
      if ( v14 >= v30 )
      {
        if ( !v31 )
        {
          PimIMService::SendCustomEvent(this, (const struct TransactionData *)v37);
          v16 = v30;
        }
        if ( (Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits & 0x20) != 0 )
          McTemplateU0q_EventWriteTransfer(v15, PIMIndex_RebuildIndexes_Stop, v16);
        TransactionData::~TransactionData((TransactionData *)v37);
        if ( v7 )
        {
          v26 = GetCurrentThread();
          SetThreadPriority(v26, ThreadPriority);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
        v5 = 0;
      }
      else
      {
        v17 = v30 - v14;
        if ( g_dwBatchSize < v30 - v14 )
          v17 = g_dwBatchSize;
        v18 = (*(__int64 (**)(void))(*(_QWORD *)v29 + 48LL))();
        v19 = v18;
        if ( v18 < 0 )
        {
          Log_HREvent(
            (unsigned int)v18,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            1638);
        }
        else
        {
          v34 = 1;
          v33 = &v29;
          for ( i = 0; i < v17; ++i )
          {
            v35 = 0;
            v36 = 0;
            v21 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v32 + 96LL))(v32, i + v14, &v35);
            v28 = v21;
            if ( v21 < 0 )
            {
              v22 = 1647;
              goto LABEL_29;
            }
            if ( v31 )
            {
              v21 = (*(__int64 (__fastcall **)(PimIMService *, __int64 *, __int64))(*(_QWORD *)this + 144LL))(
                      this,
                      &v35,
                      1);
              v28 = v21;
              if ( v21 < 0 )
              {
                v22 = 1651;
LABEL_29:
                Log_HREvent(
                  (unsigned int)v21,
                  1,
                  "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
                  v22);
                tlx::_UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa___::__UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa___(&v33);
                TransactionData::~TransactionData((TransactionData *)v37);
                if ( v7 )
                {
                  v24 = GetCurrentThread();
                  SetThreadPriority(v24, ThreadPriority);
                }
                ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
                v5 = v28;
                goto LABEL_44;
              }
            }
            else
            {
              v21 = PimIMService::HandleAggregateUpdate(this, (struct OLITEMID *)&v35, (struct TransactionData *)v37);
              v28 = v21;
              if ( v21 < 0 )
              {
                v22 = 1655;
                goto LABEL_29;
              }
            }
          }
          v34 = 0;
          v23 = (*(__int64 (__fastcall **)(struct IndexedFiltering::IIndexManager *, __int64, _QWORD))(*(_QWORD *)v29 + 56LL))(
                  v29,
                  1,
                  0);
          v19 = v23;
          if ( v23 >= 0 )
          {
            v14 += v17;
            tlx::_UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa___::__UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa___(&v33);
            continue;
          }
          Log_HREvent(
            (unsigned int)v23,
            1,
            "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
            1663);
          tlx::_UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa___::__UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa___(&v33);
        }
        TransactionData::~TransactionData((TransactionData *)v37);
        if ( v7 )
        {
          v25 = GetCurrentThread();
          SetThreadPriority(v25, ThreadPriority);
        }
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
        v5 = v19;
      }
      break;
    }
  }
  else
  {
    Log_HREvent(
      (unsigned int)IndexManager,
      1,
      "onecoreuap\\base\\appmodel\\userdataaccess\\services\\pimindexmaintenance\\service\\lib\\pimimservice.cpp",
      1625);
    if ( v7 )
    {
      v13 = GetCurrentThread();
      SetThreadPriority(v13, ThreadPriority);
    }
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)&v29);
    v5 = v12;
  }
LABEL_44:
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  return v5;
}

```

## disassembly

```asm
0x18000bb20  push    rbp
0x18000bb22  push    rbx
0x18000bb23  push    rsi
0x18000bb24  push    rdi
0x18000bb25  push    r12
0x18000bb27  push    r13
0x18000bb29  push    r14
0x18000bb2b  push    r15
0x18000bb2d  lea     rbp, [rsp-1Fh]
0x18000bb32  sub     rsp, 0B8h
0x18000bb39  mov     rax, cs:__security_cookie
0x18000bb40  xor     rax, rsp
0x18000bb43  mov     [rbp+57h+var_48], rax
0x18000bb47  mov     [rbp+57h+var_AC], edx
0x18000bb4a  lea     r8, [rbp+57h+var_A8]
0x18000bb4e  mov     rdx, [rcx+0D8h]
0x18000bb55  mov     r15, rcx
0x18000bb58  xor     ecx, ecx
0x18000bb5a  mov     [rbp+57h+var_A8], 0
0x18000bb62  call    cs:__imp_GetAggregateCache
0x18000bb68  mov     ebx, eax
0x18000bb6a  test    eax, eax
0x18000bb6c  jns     short loc_18000BB76
0x18000bb6e  mov     r9d, 64Eh
0x18000bb74  jmp     short loc_18000BB9D
0x18000bb76  mov     rcx, [rbp+57h+var_A8]
0x18000bb7a  lea     rdx, [rbp+57h+var_B0]
0x18000bb7e  mov     [rbp+57h+var_B0], 0
0x18000bb85  mov     rax, [rcx]
0x18000bb88  mov     rax, [rax+18h]
0x18000bb8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb91  mov     ebx, eax
0x18000bb93  test    eax, eax
0x18000bb95  jns     short loc_18000BBB5
0x18000bb97  mov     r9d, 651h
0x18000bb9d  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bba4  mov     edx, 1
0x18000bba9  mov     ecx, eax
0x18000bbab  call    Log_HREvent
0x18000bbb0  jmp     loc_18000BE4A
0x18000bbb5  mov     [rbp+57h+var_B8], 0
0x18000bbbd  xor     esi, esi
0x18000bbbf  call    cs:__imp_GetCurrentThread
0x18000bbc5  mov     rcx, rax; hThread
0x18000bbc8  call    cs:__imp_GetThreadPriority
0x18000bbce  mov     ebx, eax
0x18000bbd0  cmp     eax, 0FFFFFFFEh
0x18000bbd3  jz      short loc_18000BBE9
0x18000bbd5  call    cs:__imp_GetCurrentThread
0x18000bbdb  mov     rcx, rax; hThread
0x18000bbde  lea     edx, [rsi-2]; nPriority
0x18000bbe1  call    cs:__imp_SetThreadPriority
0x18000bbe7  mov     esi, eax
0x18000bbe9  mov     edi, 1
0x18000bbee  lea     r9, [rbp+57h+var_B8]; struct IndexedFiltering::IIndexManager **
0x18000bbf2  mov     r8d, edi; int
0x18000bbf5  xor     edx, edx; int
0x18000bbf7  mov     rcx, r15; this
0x18000bbfa  call    ?GetIndexManager@PimIMService@@AEAAJHHPEAPEAUIIndexManager@IndexedFiltering@@@Z; PimIMService::GetIndexManager(int,int,IndexedFiltering::IIndexManager * *)
0x18000bbff  mov     r14d, eax
0x18000bc02  test    eax, eax
0x18000bc04  jns     short loc_18000BC42
0x18000bc06  mov     r9d, 659h
0x18000bc0c  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bc13  mov     edx, edi
0x18000bc15  mov     ecx, eax
0x18000bc17  call    Log_HREvent
0x18000bc1c  test    esi, esi
0x18000bc1e  jz      short loc_18000BC31
0x18000bc20  call    cs:__imp_GetCurrentThread
0x18000bc26  mov     rcx, rax; hThread
0x18000bc29  mov     edx, ebx; nPriority
0x18000bc2b  call    cs:__imp_SetThreadPriority
0x18000bc31  lea     rcx, [rbp+57h+var_B8]
0x18000bc35  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000bc3a  mov     ebx, r14d
0x18000bc3d  jmp     loc_18000BE4A
0x18000bc42  xor     r13d, r13d
0x18000bc45  lea     rcx, [rbp+57h+var_80]; this
0x18000bc49  call    ??0TransactionData@@QEAA@XZ; TransactionData::TransactionData(void)
0x18000bc4e  mov     r14d, [rbp+57h+var_B0]
0x18000bc52  cmp     r13d, r14d
0x18000bc55  jnb     loc_18000BDF3
0x18000bc5b  mov     rcx, [rbp+57h+var_B8]
0x18000bc5f  sub     r14d, r13d
0x18000bc62  cmp     cs:?g_dwBatchSize@@3KA, r14d; ulong g_dwBatchSize
0x18000bc69  cmovb   r14d, cs:?g_dwBatchSize@@3KA; ulong g_dwBatchSize
0x18000bc71  mov     rax, [rcx]
0x18000bc74  mov     rax, [rax+30h]
0x18000bc78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bc7d  mov     r12d, eax
0x18000bc80  test    eax, eax
0x18000bc82  js      loc_18000BDB0
0x18000bc88  lea     rax, [rbp+57h+var_B8]
0x18000bc8c  mov     [rbp+57h+var_98], dil
0x18000bc90  mov     [rbp+57h+var_A0], rax
0x18000bc94  xor     r12d, r12d
0x18000bc97  cmp     r12d, r14d
0x18000bc9a  jnb     short loc_18000BD07
0x18000bc9c  mov     rcx, [rbp+57h+var_A8]
0x18000bca0  lea     edx, [r12+r13]
0x18000bca4  xor     eax, eax
0x18000bca6  lea     r8, [rbp+57h+var_90]
0x18000bcaa  mov     [rbp+57h+var_90], rax
0x18000bcae  mov     [rbp+57h+var_88], eax
0x18000bcb1  mov     rax, [rcx]
0x18000bcb4  mov     rax, [rax+60h]
0x18000bcb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bcbd  mov     [rbp+57h+var_C0], eax
0x18000bcc0  test    eax, eax
0x18000bcc2  js      short loc_18000BD40
0x18000bcc4  cmp     [rbp+57h+var_AC], 0
0x18000bcc8  lea     rdx, [rbp+57h+var_90]; struct OLITEMID *
0x18000bccc  mov     rcx, r15; this
0x18000bccf  jz      short loc_18000BCF2
0x18000bcd1  mov     rax, [r15]
0x18000bcd4  mov     r8d, edi
0x18000bcd7  mov     rax, [rax+90h]
0x18000bcde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bce3  mov     [rbp+57h+var_C0], eax
0x18000bce6  test    eax, eax
0x18000bce8  jns     short loc_18000BD02
0x18000bcea  mov     r9d, 673h
0x18000bcf0  jmp     short loc_18000BD46
0x18000bcf2  lea     r8, [rbp+57h+var_80]; struct TransactionData *
0x18000bcf6  call    ?HandleAggregateUpdate@PimIMService@@AEAAJPEAUOLITEMID@@PEAUTransactionData@@@Z; PimIMService::HandleAggregateUpdate(OLITEMID *,TransactionData *)
0x18000bcfb  mov     [rbp+57h+var_C0], eax
0x18000bcfe  test    eax, eax
0x18000bd00  js      short loc_18000BD38
0x18000bd02  add     r12d, edi
0x18000bd05  jmp     short loc_18000BC97
0x18000bd07  mov     rcx, [rbp+57h+var_B8]
0x18000bd0b  xor     r8d, r8d
0x18000bd0e  mov     edx, edi
0x18000bd10  mov     [rbp+57h+var_98], 0
0x18000bd14  mov     rax, [rcx]
0x18000bd17  mov     rax, [rax+38h]
0x18000bd1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bd20  mov     r12d, eax
0x18000bd23  test    eax, eax
0x18000bd25  js      short loc_18000BD8E
0x18000bd27  add     r13d, r14d
0x18000bd2a  lea     rcx, [rbp+57h+var_A0]
0x18000bd2e  call    tlx___UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa_______UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa___
0x18000bd33  jmp     loc_18000BC4E
0x18000bd38  mov     r9d, 677h
0x18000bd3e  jmp     short loc_18000BD46
0x18000bd40  mov     r9d, 66Fh
0x18000bd46  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bd4d  mov     edx, edi
0x18000bd4f  mov     ecx, eax
0x18000bd51  call    Log_HREvent
0x18000bd56  lea     rcx, [rbp+57h+var_A0]
0x18000bd5a  call    tlx___UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa_______UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa___
0x18000bd5f  lea     rcx, [rbp+57h+var_80]; this
0x18000bd63  call    ??1TransactionData@@QEAA@XZ; TransactionData::~TransactionData(void)
0x18000bd68  test    esi, esi
0x18000bd6a  jz      short loc_18000BD7D
0x18000bd6c  call    cs:__imp_GetCurrentThread
0x18000bd72  mov     rcx, rax; hThread
0x18000bd75  mov     edx, ebx; nPriority
0x18000bd77  call    cs:__imp_SetThreadPriority
0x18000bd7d  lea     rcx, [rbp+57h+var_B8]
0x18000bd81  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000bd86  mov     ebx, [rbp+57h+var_C0]
0x18000bd89  jmp     loc_18000BE4A
0x18000bd8e  mov     r9d, 67Fh
0x18000bd94  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bd9b  mov     edx, edi
0x18000bd9d  mov     ecx, r12d
0x18000bda0  call    Log_HREvent
0x18000bda5  lea     rcx, [rbp+57h+var_A0]
0x18000bda9  call    tlx___UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa_______UndoSolo__lambda_85cc40121e0a06f98af216f7335d9aaa___
0x18000bdae  jmp     short loc_18000BDC7
0x18000bdb0  mov     r9d, 666h
0x18000bdb6  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\userdataacc"...
0x18000bdbd  mov     edx, edi
0x18000bdbf  mov     ecx, r12d
0x18000bdc2  call    Log_HREvent
0x18000bdc7  lea     rcx, [rbp+57h+var_80]; this
0x18000bdcb  call    ??1TransactionData@@QEAA@XZ; TransactionData::~TransactionData(void)
0x18000bdd0  test    esi, esi
0x18000bdd2  jz      short loc_18000BDE5
0x18000bdd4  call    cs:__imp_GetCurrentThread
0x18000bdda  mov     rcx, rax; hThread
0x18000bddd  mov     edx, ebx; nPriority
0x18000bddf  call    cs:__imp_SetThreadPriority
0x18000bde5  lea     rcx, [rbp+57h+var_B8]
0x18000bde9  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000bdee  mov     ebx, r12d
0x18000bdf1  jmp     short loc_18000BE4A
0x18000bdf3  cmp     [rbp+57h+var_AC], 0
0x18000bdf7  jnz     short loc_18000BE09
0x18000bdf9  lea     rdx, [rbp+57h+var_80]; struct TransactionData *
0x18000bdfd  mov     rcx, r15; this
0x18000be00  call    ?SendCustomEvent@PimIMService@@AEAAJPEBUTransactionData@@@Z; PimIMService::SendCustomEvent(TransactionData const *)
0x18000be05  mov     r14d, [rbp+57h+var_B0]
0x18000be09  test    byte ptr cs:Microsoft_Windows_UserDataAccess_PimIndexMaintenanceEnableBits, 20h
0x18000be10  jz      short loc_18000BE21
0x18000be12  mov     r8d, r14d
0x18000be15  lea     rdx, PIMIndex_RebuildIndexes_Stop
0x18000be1c  call    McTemplateU0q_EventWriteTransfer
0x18000be21  lea     rcx, [rbp+57h+var_80]; this
0x18000be25  call    ??1TransactionData@@QEAA@XZ; TransactionData::~TransactionData(void)
0x18000be2a  test    esi, esi
0x18000be2c  jz      short loc_18000BE3F
0x18000be2e  call    cs:__imp_GetCurrentThread
0x18000be34  mov     rcx, rax; hThread
0x18000be37  mov     edx, ebx; nPriority
0x18000be39  call    cs:__imp_SetThreadPriority
0x18000be3f  lea     rcx, [rbp+57h+var_B8]
0x18000be43  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000be48  xor     ebx, ebx
0x18000be4a  lea     rcx, [rbp+57h+var_A8]
0x18000be4e  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18000be53  mov     eax, ebx
0x18000be55  mov     rcx, [rbp+57h+var_48]
0x18000be59  xor     rcx, rsp; StackCookie
0x18000be5c  call    __security_check_cookie
0x18000be61  add     rsp, 0B8h
0x18000be68  pop     r15
0x18000be6a  pop     r14
0x18000be6c  pop     r13
0x18000be6e  pop     r12
0x18000be70  pop     rdi
0x18000be71  pop     rsi
0x18000be72  pop     rbx
0x18000be73  pop     rbp
0x18000be74  retn
```
