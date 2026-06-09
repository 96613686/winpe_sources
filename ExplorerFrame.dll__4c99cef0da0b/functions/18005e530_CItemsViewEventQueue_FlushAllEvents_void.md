# CItemsViewEventQueue::FlushAllEvents(void)

- ea: `0x18005e530`
- end: `0x18005e951`
- name: `?FlushAllEvents@CItemsViewEventQueue@@UEAAIXZ`
- size: `1057`
- prototype: `unsigned int __fastcall(CItemsViewEventQueue *__hidden this)`
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18001b8d0`
- `0x18005e530`
- `0x18005e99c`
- `0x18005f7a0`
- `0x18005faa0`
- `0x18005fb14`
- `0x180063f0c`
- `0x180064058`
- `0x180064194`
- `0x180197274`
- `0x1801e4538`
- `0x180210010`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18005e939`
- `SHCORE!SHCreateThread` at `0x18005e939`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18005e589`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18005e589`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005e5a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005e71e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005e862`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005e5a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005e71e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005e862`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e6f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e78f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e839`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e6f5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e78f`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005e839`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e55f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e55f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005e8d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005e8d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e8c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e8db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e8c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005e8db`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e943`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005e943`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005e903`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005e903`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005e8bf`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005e8bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CItemsViewEventQueue::FlushAllEvents(CItemsViewEventQueue *this)
{
  int v2; // r13d
  unsigned int v3; // edi
  unsigned __int64 v4; // rbx
  unsigned __int64 v5; // r15
  unsigned __int64 v6; // rdi
  __int64 v7; // r8
  __int64 v8; // rcx
  unsigned __int64 v9; // r14
  __int64 v10; // rbx
  __int64 *v11; // rdx
  __int64 *v13; // rdx
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v16; // rax
  _QWORD pData[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v18; // [rsp+50h] [rbp-29h] BYREF
  int v19; // [rsp+58h] [rbp-21h]
  __int64 v20; // [rsp+5Ch] [rbp-1Dh] BYREF
  _DWORD v21[8]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v22[8]; // [rsp+88h] [rbp+Fh] BYREF
  _BYTE v23[64]; // [rsp+90h] [rbp+17h] BYREF
  int v24; // [rsp+E0h] [rbp+67h] BYREF
  int Data; // [rsp+E8h] [rbp+6Fh] BYREF
  HANDLE TargetHandle; // [rsp+F0h] [rbp+77h] BYREF

  v2 = 0;
  v3 = 0;
  v24 = 0;
  if ( *((_DWORD *)this + 10) )
  {
    g_dwReentrantThreadId = GetCurrentThreadId();
    g_ReentrantCheck = 1;
    if ( !SHRegGetBoolUSValueW(
            L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
            L"ShellViewReentered",
            0,
            0) )
    {
      Data = 1;
      RegSetKeyValueW(
        HKEY_CURRENT_USER,
        L"Software\\Microsoft\\Windows\\CurrentVersion\\Explorer\\Advanced",
        L"ShellViewReentered",
        4u,
        &Data,
        4u);
      TargetHandle = 0;
      CurrentProcess = GetCurrentProcess();
      CurrentThread = GetCurrentThread();
      v16 = GetCurrentProcess();
      if ( DuplicateHandle(v16, CurrentThread, CurrentProcess, &TargetHandle, 0x1FFFFFu, 1, 0) )
      {
        pData[0] = TargetHandle;
        pData[1] = ComputeStackHash();
        SHCreateThread(
          DirectUI::PatternProvider<UIItemsViewScrollProvider,IScrollProvider,5>::GetProxyCreator,
          pData,
          0x200u,
          s_SendWERForReentrancy);
        CloseHandle(TargetHandle);
      }
      v3 = 0;
    }
  }
  if ( !*((_DWORD *)this + 10) )
  {
    AcquireSRWLockExclusive((PSRWLOCK)this + 6);
    if ( *((_DWORD *)this + 11) )
    {
      CItemsViewEventQueue::_PreProcessEventQueue(this, (int *)&TargetHandle, &Data, &v24);
    }
    else
    {
      v4 = *((_QWORD *)this + 2);
      v5 = v4;
      while ( 1 )
      {
        v6 = *((_QWORD *)this + 10);
        if ( *((_DWORD *)this + 11) )
          v4 = *((_QWORD *)this + 4);
        if ( v4 < v6 )
        {
          do
          {
            v7 = *((_QWORD *)this + 9) + 72 * v4;
            v8 = *(_QWORD *)v7;
            if ( *(_QWORD *)v7 )
            {
              Data = 0;
              (*(void (__fastcall **)(__int64, __int64, _QWORD, int *))(*(_QWORD *)v8 + 32LL))(
                v8,
                v7 + (*(_DWORD *)(v7 + 8) != 0 ? 24LL : 12LL),
                *((unsigned int *)this + 11),
                &Data);
              if ( Data )
              {
                if ( Data == 2 )
                {
                  ATL::CComPtrBase<ISelectionStateCallback>::Release(*((_QWORD *)this + 9) + 72 * v4);
                  --*((_QWORD *)this + 13);
                }
              }
              else if ( *((_DWORD *)this + 11) )
              {
                *((_DWORD *)this + 10) = 1;
                QueuedEvent::QueuedEvent(
                  (QueuedEvent *)&v18,
                  (const struct QueuedEvent *)(*((_QWORD *)this + 9) + 72 * v4));
                ATL::CComPtrBase<ISelectionStateCallback>::Release(*((_QWORD *)this + 9) + 72 * v4);
                ReleaseSRWLockExclusive((PSRWLOCK)this + 6);
                v13 = &v20;
                if ( v19 )
                  v13 = (__int64 *)v21;
                (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, v13);
                AcquireSRWLockExclusive((PSRWLOCK)this + 6);
                --*((_QWORD *)this + 13);
                *((_DWORD *)this + 10) = 0;
                CollectionEventParams::~CollectionEventParams((CollectionEventParams *)v21);
                ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v18);
              }
              else
              {
                CItemsViewEventQueue::_FlushEventsPriorTo(this, v4 + 1);
              }
            }
            ++v4;
          }
          while ( v4 < v6 );
          v5 = *((_QWORD *)this + 2);
        }
        if ( *((_DWORD *)this + 11) )
        {
          *((_QWORD *)this + 4) = v6;
        }
        else
        {
          *((_QWORD *)this + 2) = v6;
          v5 = v6;
        }
        if ( !*((_DWORD *)this + 10) )
        {
          *((_DWORD *)this + 10) = 1;
          v9 = *((_QWORD *)this + 3);
          while ( v9 < v5 && v9 < *((_QWORD *)this + 10) )
          {
            v10 = *((_QWORD *)this + 9) + 72 * v9;
            ATL::CComPtr<IVirtualUIGroupItem>::CComPtr<IVirtualUIGroupItem>(&v18, v10);
            v19 = *(_DWORD *)(v10 + 8);
            v20 = *(_QWORD *)(v10 + 12);
            v21[0] = *(_DWORD *)(v10 + 24);
            v21[1] = *(_DWORD *)(v10 + 28);
            v21[2] = *(_DWORD *)(v10 + 32);
            v21[3] = *(_DWORD *)(v10 + 36);
            v21[4] = *(_DWORD *)(v10 + 40);
            v21[5] = *(_DWORD *)(v10 + 44);
            v21[6] = *(_DWORD *)(v10 + 48);
            v21[7] = *(_DWORD *)(v10 + 52);
            ATL::CComPtr<IItem>::CComPtr<IItem>(v22, v10 + 56);
            ATL::CComPtr<IItem>::CComPtr<IItem>(v23, v10 + 64);
            ATL::CComPtrBase<ISelectionStateCallback>::Release(*((_QWORD *)this + 9) + 72 * v9);
            if ( v18 )
            {
              ReleaseSRWLockExclusive((PSRWLOCK)this + 6);
              v11 = &v20;
              if ( v19 )
                v11 = (__int64 *)v21;
              (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v18 + 24LL))(v18, v11);
              AcquireSRWLockExclusive((PSRWLOCK)this + 6);
              ++v2;
              --*((_QWORD *)this + 13);
            }
            *((_QWORD *)this + 3) = ++v9;
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(v23);
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(v22);
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v18);
          }
          *((_DWORD *)this + 10) = 0;
        }
        v3 = v2 + v24;
        v24 += v2;
        v4 = *((_QWORD *)this + 2);
        v5 = v4;
        if ( v4 >= *((_QWORD *)this + 10) )
          break;
        v2 = 0;
      }
      CTSimpleArray<QueuedEvent,4294967294,CTPolicyCoTaskMem<QueuedEvent>,CSimpleArrayStandardCompareHelper<QueuedEvent>,CSimpleArrayStandardMergeHelper<QueuedEvent>>::RemoveAll((char *)this + 72);
      *((_QWORD *)this + 13) = 0;
      *((_QWORD *)this + 2) = 0;
      *((_QWORD *)this + 3) = 0;
      *((_QWORD *)this + 4) = 0;
    }
    ReleaseSRWLockExclusive((PSRWLOCK)this + 6);
  }
  return v3;
}

```

## disassembly

```asm
0x18005e530  mov     [rsp-8+arg_18], rbx
0x18005e535  push    rbp
0x18005e536  push    rsi
0x18005e537  push    rdi
0x18005e538  push    r12
0x18005e53a  push    r13
0x18005e53c  push    r14
0x18005e53e  push    r15
0x18005e540  lea     rbp, [rsp-27h]
0x18005e545  sub     rsp, 0A0h
0x18005e54c  mov     rsi, rcx
0x18005e54f  xor     r13d, r13d
0x18005e552  mov     edi, r13d
0x18005e555  mov     [rbp+57h+arg_0], r13d
0x18005e559  cmp     [rcx+28h], r13d
0x18005e55d  jz      short loc_18005E597
0x18005e55f  call    cs:__imp_GetCurrentThreadId
0x18005e565  mov     cs:?g_dwReentrantThreadId@@3KC, eax; ulong volatile g_dwReentrantThreadId
0x18005e56b  mov     cs:?g_ReentrantCheck@@3W4REENTRANCYCHECKTHATFAILED@@C, 1; REENTRANCYCHECKTHATFAILED volatile g_ReentrantCheck
0x18005e575  xor     r9d, r9d; fDefault
0x18005e578  xor     r8d, r8d; fIgnoreHKCU
0x18005e57b  lea     rdx, ValueName; "ShellViewReentered"
0x18005e582  lea     rcx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005e589  call    cs:__imp_SHRegGetBoolUSValueW
0x18005e58f  test    eax, eax
0x18005e591  jz      loc_18005E88F
0x18005e597  cmp     [rsi+28h], r13d
0x18005e59b  jnz     loc_18005E795
0x18005e5a1  lea     r12, [rsi+30h]
0x18005e5a5  mov     rcx, r12; SRWLock
0x18005e5a8  call    cs:__imp_AcquireSRWLockExclusive
0x18005e5ae  cmp     [rsi+2Ch], r13d
0x18005e5b2  jnz     loc_18005E7D2
0x18005e5b8  mov     rbx, [rsi+10h]
0x18005e5bc  mov     r15, rbx
0x18005e5bf  mov     rdi, [rsi+50h]
0x18005e5c3  cmp     [rsi+2Ch], r13d
0x18005e5c7  jnz     loc_18005E7C9
0x18005e5cd  cmp     rbx, rdi
0x18005e5d0  jnb     short loc_18005E631
0x18005e5d2  lea     r14, [rbx+rbx*8]
0x18005e5d6  mov     rax, [rsi+48h]
0x18005e5da  lea     r8, [rax+r14*8]
0x18005e5de  mov     rcx, [r8]
0x18005e5e1  test    rcx, rcx
0x18005e5e4  jz      short loc_18005E625
0x18005e5e6  mov     [rbp+57h+Data], r13d
0x18005e5ea  mov     r10, [rcx]
0x18005e5ed  mov     eax, [r8+8]
0x18005e5f1  neg     eax
0x18005e5f3  sbb     rdx, rdx
0x18005e5f6  and     edx, 0Ch
0x18005e5f9  add     rdx, 0Ch
0x18005e5fd  add     rdx, r8
0x18005e600  lea     r9, [rbp+57h+Data]
0x18005e604  mov     r8d, [rsi+2Ch]
0x18005e608  mov     rax, [r10+20h]
0x18005e60c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e611  mov     ecx, [rbp+57h+Data]
0x18005e614  test    ecx, ecx
0x18005e616  jz      loc_18005E7B2
0x18005e61c  sub     ecx, 1
0x18005e61f  jnz     loc_18005E7F1
0x18005e625  inc     rbx
0x18005e628  cmp     rbx, rdi
0x18005e62b  jb      short loc_18005E5D2
0x18005e62d  mov     r15, [rsi+10h]
0x18005e631  cmp     [rsi+2Ch], r13d
0x18005e635  jnz     loc_18005E7E8
0x18005e63b  mov     [rsi+10h], rdi
0x18005e63f  mov     r15, rdi
0x18005e642  xor     r14d, r14d
0x18005e645  cmp     [rsi+28h], r14d
0x18005e649  jnz     loc_18005E759
0x18005e64f  mov     dword ptr [rsi+28h], 1
0x18005e656  mov     r14, [rsi+18h]
0x18005e65a  cmp     r14, r15
0x18005e65d  jnb     loc_18005E752
0x18005e663  cmp     r14, [rsi+50h]
0x18005e667  jnb     loc_18005E752
0x18005e66d  lea     rdi, [r14+r14*8]
0x18005e671  mov     rax, [rsi+48h]
0x18005e675  lea     rbx, [rax+rdi*8]
0x18005e679  mov     rdx, rbx
0x18005e67c  lea     rcx, [rbp+57h+var_80]
0x18005e680  call    ??0?$CComPtr@UIVirtualUIGroupItem@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IVirtualUIGroupItem>::CComPtr<IVirtualUIGroupItem>(ATL::CComPtr<IVirtualUIGroupItem> const &)
0x18005e685  mov     eax, [rbx+8]
0x18005e688  mov     [rbp+57h+var_78], eax
0x18005e68b  mov     rax, [rbx+0Ch]
0x18005e68f  mov     [rbp+57h+var_74], rax
0x18005e693  mov     eax, [rbx+18h]
0x18005e696  mov     [rbp+57h+var_68], eax
0x18005e699  mov     eax, [rbx+1Ch]
0x18005e69c  mov     [rbp+57h+var_64], eax
0x18005e69f  mov     eax, [rbx+20h]
0x18005e6a2  mov     [rbp+57h+var_60], eax
0x18005e6a5  mov     eax, [rbx+24h]
0x18005e6a8  mov     [rbp+57h+var_5C], eax
0x18005e6ab  mov     eax, [rbx+28h]
0x18005e6ae  mov     [rbp+57h+var_58], eax
0x18005e6b1  mov     eax, [rbx+2Ch]
0x18005e6b4  mov     [rbp+57h+var_54], eax
0x18005e6b7  mov     eax, [rbx+30h]
0x18005e6ba  mov     [rbp+57h+var_50], eax
0x18005e6bd  mov     eax, [rbx+34h]
0x18005e6c0  mov     [rbp+57h+var_4C], eax
0x18005e6c3  lea     rdx, [rbx+38h]
0x18005e6c7  lea     rcx, [rbp+57h+var_48]
0x18005e6cb  call    ??0?$CComPtr@UIItem@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IItem>::CComPtr<IItem>(ATL::CComPtr<IItem> const &)
0x18005e6d0  lea     rdx, [rbx+40h]
0x18005e6d4  lea     rcx, [rbp+57h+var_40]
0x18005e6d8  call    ??0?$CComPtr@UIItem@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IItem>::CComPtr<IItem>(ATL::CComPtr<IItem> const &)
0x18005e6dd  nop
0x18005e6de  mov     rax, [rsi+48h]
0x18005e6e2  lea     rcx, [rax+rdi*8]
0x18005e6e6  call    ?Release@?$CComPtrBase@UISelectionStateCallback@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISelectionStateCallback>::Release(void)
0x18005e6eb  cmp     [rbp+57h+var_80], 0
0x18005e6f0  jz      short loc_18005E72B
0x18005e6f2  mov     rcx, r12; SRWLock
0x18005e6f5  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e6fb  mov     rcx, [rbp+57h+var_80]
0x18005e6ff  mov     rax, [rcx]
0x18005e702  lea     rdx, [rbp+57h+var_74]
0x18005e706  lea     r8, [rbp+57h+var_68]
0x18005e70a  cmp     [rbp+57h+var_78], 0
0x18005e70e  cmovnz  rdx, r8
0x18005e712  mov     rax, [rax+18h]
0x18005e716  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e71b  mov     rcx, r12; SRWLock
0x18005e71e  call    cs:__imp_AcquireSRWLockExclusive
0x18005e724  inc     r13d
0x18005e727  dec     qword ptr [rsi+68h]
0x18005e72b  inc     r14
0x18005e72e  mov     [rsi+18h], r14
0x18005e732  lea     rcx, [rbp+57h+var_40]; void *
0x18005e736  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18005e73b  lea     rcx, [rbp+57h+var_48]; void *
0x18005e73f  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18005e744  lea     rcx, [rbp+57h+var_80]; void *
0x18005e748  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18005e74d  jmp     loc_18005E65A
0x18005e752  xor     r14d, r14d
0x18005e755  mov     [rsi+28h], r14d
0x18005e759  mov     edi, [rbp+57h+arg_0]
0x18005e75c  add     edi, r13d
0x18005e75f  mov     [rbp+57h+arg_0], edi
0x18005e762  mov     rbx, [rsi+10h]
0x18005e766  mov     r15, rbx
0x18005e769  cmp     rbx, [rsi+50h]
0x18005e76d  jb      loc_18005E887
0x18005e773  lea     rcx, [rsi+48h]
0x18005e777  call    ?RemoveAll@?$CTSimpleArray@UQueuedEvent@@$0PPPPPPPO@V?$CTPolicyCoTaskMem@UQueuedEvent@@@@V?$CSimpleArrayStandardCompareHelper@UQueuedEvent@@@@V?$CSimpleArrayStandardMergeHelper@UQueuedEvent@@@@@@QEAAXXZ; CTSimpleArray<QueuedEvent,4294967294,CTPolicyCoTaskMem<QueuedEvent>,CSimpleArrayStandardCompareHelper<QueuedEvent>,CSimpleArrayStandardMergeHelper<QueuedEvent>>::RemoveAll(void)
0x18005e77c  mov     [rsi+68h], r14
0x18005e780  mov     [rsi+10h], r14
0x18005e784  mov     [rsi+18h], r14
0x18005e788  mov     [rsi+20h], r14
0x18005e78c  mov     rcx, r12; SRWLock
0x18005e78f  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e795  mov     eax, edi
0x18005e797  mov     rbx, [rsp+0D0h+arg_18]
0x18005e79f  add     rsp, 0A0h
0x18005e7a6  pop     r15
0x18005e7a8  pop     r14
0x18005e7aa  pop     r13
0x18005e7ac  pop     r12
0x18005e7ae  pop     rdi
0x18005e7af  pop     rsi
0x18005e7b0  pop     rbp
0x18005e7b1  retn
0x18005e7b2  cmp     [rsi+2Ch], r13d
0x18005e7b6  jnz     short loc_18005E810
0x18005e7b8  lea     rdx, [rbx+1]; unsigned __int64
0x18005e7bc  mov     rcx, rsi; this
0x18005e7bf  call    ?_FlushEventsPriorTo@CItemsViewEventQueue@@AEAAI_K@Z; CItemsViewEventQueue::_FlushEventsPriorTo(unsigned __int64)
0x18005e7c4  jmp     loc_18005E625
0x18005e7c9  mov     rbx, [rsi+20h]
0x18005e7cd  jmp     loc_18005E5CD
0x18005e7d2  lea     r9, [rbp+57h+arg_0]; int *
0x18005e7d6  lea     r8, [rbp+57h+Data]; int *
0x18005e7da  lea     rdx, [rbp+57h+TargetHandle]; int *
0x18005e7de  mov     rcx, rsi; this
0x18005e7e1  call    ?_PreProcessEventQueue@CItemsViewEventQueue@@AEAAXPEAH00@Z; CItemsViewEventQueue::_PreProcessEventQueue(int *,int *,int *)
0x18005e7e6  jmp     short loc_18005E78C
0x18005e7e8  mov     [rsi+20h], rdi
0x18005e7ec  jmp     loc_18005E642
0x18005e7f1  cmp     ecx, 1
0x18005e7f4  jnz     loc_18005E625
0x18005e7fa  mov     rax, [rsi+48h]
0x18005e7fe  lea     rcx, [rax+r14*8]
0x18005e802  call    ?Release@?$CComPtrBase@UISelectionStateCallback@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISelectionStateCallback>::Release(void)
0x18005e807  dec     qword ptr [rsi+68h]
0x18005e80b  jmp     loc_18005E625
0x18005e810  mov     dword ptr [rsi+28h], 1
0x18005e817  mov     rax, [rsi+48h]
0x18005e81b  lea     rdx, [rax+r14*8]; struct QueuedEvent *
0x18005e81f  lea     rcx, [rbp+57h+var_80]; this
0x18005e823  call    ??0QueuedEvent@@QEAA@AEBU0@@Z; QueuedEvent::QueuedEvent(QueuedEvent const &)
0x18005e828  nop
0x18005e829  mov     rax, [rsi+48h]
0x18005e82d  lea     rcx, [rax+r14*8]
0x18005e831  call    ?Release@?$CComPtrBase@UISelectionStateCallback@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISelectionStateCallback>::Release(void)
0x18005e836  mov     rcx, r12; SRWLock
0x18005e839  call    cs:__imp_ReleaseSRWLockExclusive
0x18005e83f  mov     rcx, [rbp+57h+var_80]
0x18005e843  mov     rax, [rcx]
0x18005e846  lea     rdx, [rbp+57h+var_74]
0x18005e84a  lea     r8, [rbp+57h+var_68]
0x18005e84e  cmp     [rbp+57h+var_78], r13d
0x18005e852  cmovnz  rdx, r8
0x18005e856  mov     rax, [rax+18h]
0x18005e85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e85f  mov     rcx, r12; SRWLock
0x18005e862  call    cs:__imp_AcquireSRWLockExclusive
0x18005e868  dec     qword ptr [rsi+68h]
0x18005e86c  mov     [rsi+28h], r13d
0x18005e870  lea     rcx, [rbp+57h+var_68]; this
0x18005e874  call    ??1CollectionEventParams@@QEAA@XZ; CollectionEventParams::~CollectionEventParams(void)
0x18005e879  lea     rcx, [rbp+57h+var_80]; void *
0x18005e87d  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18005e882  jmp     loc_18005E625
0x18005e887  xor     r13d, r13d
0x18005e88a  jmp     loc_18005E5BF
0x18005e88f  mov     [rbp+57h+Data], 1
0x18005e896  mov     r9d, 4; dwType
0x18005e89c  mov     [rsp+0D0h+cbData], r9d; cbData
0x18005e8a1  lea     rax, [rbp+57h+Data]
0x18005e8a5  mov     [rsp+0D0h+lpData], rax; lpData
0x18005e8aa  lea     r8, ValueName; "ShellViewReentered"
0x18005e8b1  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005e8b8  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005e8bf  call    cs:__imp_RegSetKeyValueW
0x18005e8c5  mov     [rbp+57h+TargetHandle], r13
0x18005e8c9  call    cs:__imp_GetCurrentProcess
0x18005e8cf  mov     rdi, rax
0x18005e8d2  call    cs:__imp_GetCurrentThread
0x18005e8d8  mov     rbx, rax
0x18005e8db  call    cs:__imp_GetCurrentProcess
0x18005e8e1  mov     [rsp+0D0h+dwOptions], r13d; dwOptions
0x18005e8e6  mov     [rsp+0D0h+cbData], 1; bInheritHandle
0x18005e8ee  mov     dword ptr [rsp+0D0h+lpData], 1FFFFFh; dwDesiredAccess
0x18005e8f6  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x18005e8fa  mov     r8, rdi; hTargetProcessHandle
0x18005e8fd  mov     rdx, rbx; hSourceHandle
0x18005e900  mov     rcx, rax; hSourceProcessHandle
0x18005e903  call    cs:__imp_DuplicateHandle
0x18005e909  test    eax, eax
0x18005e90b  jz      short loc_18005E949
0x18005e90d  mov     [rbp+57h+var_88], r13
0x18005e911  mov     rax, [rbp+57h+TargetHandle]
0x18005e915  mov     [rbp+57h+pData], rax
0x18005e919  call    ?ComputeStackHash@@YAKXZ; ComputeStackHash(void)
0x18005e91e  mov     dword ptr [rbp+57h+var_88], eax
0x18005e921  lea     r9, ?s_SendWERForReentrancy@@YAKPEAX@Z; pfnCallback
0x18005e928  mov     r8d, 200h; flags
0x18005e92e  lea     rdx, [rbp+57h+pData]; pData
0x18005e932  lea     rcx, ?GetProxyCreator@?$PatternProvider@VUIItemsViewScrollProvider@@UIScrollProvider@@$04@DirectUI@@UEAAP6APEAVProviderProxy@2@PEAVElement@2@@ZXZ; pfnThreadProc
0x18005e939  call    cs:__imp_SHCreateThread
0x18005e93f  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x18005e943  call    cs:__imp_CloseHandle
0x18005e949  mov     edi, r13d
0x18005e94c  jmp     loc_18005E597
```
