# CItemsViewEventQueue::PreProcessEventQueue(int *,int *,int *)

- ea: `0x18005f0a0`
- end: `0x18005f4a9`
- name: `?PreProcessEventQueue@CItemsViewEventQueue@@UEAAXPEAH00@Z`
- size: `1033`
- prototype: `void __fastcall(CItemsViewEventQueue *__hidden this, int *, int *, int *)`
- caller_count: `0`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18001b8d0`
- `0x18005e99c`
- `0x18005f0a0`
- `0x18005faa0`
- `0x18005fb14`
- `0x180064194`
- `0x180197274`
- `0x1801e4538`
- `0x180210010`

## import_xrefs

- `SHCORE!SHCreateThread` at `0x18005f494`
- `SHCORE!SHCreateThread` at `0x18005f494`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18005f0fc`
- `SHLWAPI!SHRegGetBoolUSValueW` at `0x18005f0fc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005f111`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005f2d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005f3a5`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005f111`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005f2d7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005f3a5`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005f2ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005f37c`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005f1dd`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005f2ae`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18005f37c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f0d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f0d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f429`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18005f429`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f420`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f432`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f420`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x18005f432`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f49e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005f49e`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005f45a`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x18005f45a`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005f416`
- `api-ms-win-core-registry-l1-1-1!RegSetKeyValueW` at `0x18005f416`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CItemsViewEventQueue::PreProcessEventQueue(CItemsViewEventQueue *this, int *a2, int *a3, int *a4)
{
  RTL_SRWLOCK *v5; // rdi
  int v6; // r13d
  int v7; // edx
  int v8; // r15d
  unsigned __int64 v9; // r12
  unsigned __int64 i; // r14
  __int64 v11; // r8
  __int64 v12; // rcx
  int v13; // ebx
  unsigned __int64 v14; // r15
  __int64 v15; // rbx
  __int64 *v16; // rdx
  __int64 *v17; // rdx
  HANDLE CurrentProcess; // rdi
  HANDLE CurrentThread; // rbx
  HANDLE v20; // rax
  int v21; // [rsp+48h] [rbp-69h]
  HANDLE TargetHandle; // [rsp+50h] [rbp-61h] BYREF
  _DWORD v23[4]; // [rsp+58h] [rbp-59h] BYREF
  __int64 v24; // [rsp+68h] [rbp-49h] BYREF
  int v25; // [rsp+70h] [rbp-41h]
  __int64 v26; // [rsp+74h] [rbp-3Dh] BYREF
  _DWORD v27[8]; // [rsp+80h] [rbp-31h] BYREF
  _BYTE v28[8]; // [rsp+A0h] [rbp-11h] BYREF
  _BYTE v29[16]; // [rsp+A8h] [rbp-9h] BYREF
  HANDLE pData; // [rsp+B8h] [rbp+7h] BYREF
  __int64 v31; // [rsp+C0h] [rbp+Fh]
  int Data; // [rsp+118h] [rbp+67h] BYREF
  int *v33; // [rsp+120h] [rbp+6Fh]
  int *v34; // [rsp+128h] [rbp+77h]
  int *v35; // [rsp+130h] [rbp+7Fh]

  v35 = a4;
  v34 = a3;
  v33 = a2;
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
      v20 = GetCurrentProcess();
      if ( DuplicateHandle(v20, CurrentThread, CurrentProcess, &TargetHandle, 0x1FFFFFu, 1, 0) )
      {
        v31 = 0;
        pData = TargetHandle;
        LODWORD(v31) = ComputeStackHash();
        SHCreateThread(
          DirectUI::PatternProvider<UIItemsViewScrollProvider,IScrollProvider,5>::GetProxyCreator,
          &pData,
          0x200u,
          s_SendWERForReentrancy);
        CloseHandle(TargetHandle);
      }
    }
  }
  v5 = (RTL_SRWLOCK *)((char *)this + 48);
  AcquireSRWLockExclusive((PSRWLOCK)this + 6);
  *((_DWORD *)this + 16) = 0;
  v6 = 0;
  v7 = 0;
  Data = 0;
  v8 = 0;
  LODWORD(TargetHandle) = 0;
  v9 = *((_QWORD *)this + 10);
  for ( i = *(_QWORD *)((char *)this + (*((_DWORD *)this + 11) != 0 ? 0x10 : 0) + 16); i < v9; ++i )
  {
    v11 = *((_QWORD *)this + 9) + 72 * i;
    v12 = *(_QWORD *)v11;
    if ( !*(_QWORD *)v11 )
      goto LABEL_9;
    v23[0] = 0;
    (*(void (__fastcall **)(__int64, __int64, _QWORD, _DWORD *))(*(_QWORD *)v12 + 32LL))(
      v12,
      v11 + (*(_DWORD *)(v11 + 8) != 0 ? 24LL : 12LL),
      *((unsigned int *)this + 11),
      v23);
    if ( !v23[0] )
    {
      if ( *((_DWORD *)this + 11) )
      {
        *((_DWORD *)this + 10) = 1;
        QueuedEvent::QueuedEvent((QueuedEvent *)&v24, (const struct QueuedEvent *)(*((_QWORD *)this + 9) + 72 * i));
        ATL::CComPtrBase<ISelectionStateCallback>::Release(*((_QWORD *)this + 9) + 72 * i);
        ReleaseSRWLockExclusive(v5);
        v17 = &v26;
        if ( v25 )
          v17 = (__int64 *)v27;
        (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 24LL))(v24, v17);
        AcquireSRWLockExclusive(v5);
        --*((_QWORD *)this + 13);
        ++v6;
        *((_DWORD *)this + 10) = 0;
        CollectionEventParams::~CollectionEventParams((CollectionEventParams *)v27);
        ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v24);
      }
      else
      {
        v13 = 0;
        v21 = 0;
        if ( !*((_DWORD *)this + 10) )
        {
          *((_DWORD *)this + 10) = 1;
          v14 = *((_QWORD *)this + 3);
          while ( v14 < i + 1 && v14 < *((_QWORD *)this + 10) )
          {
            v15 = *((_QWORD *)this + 9) + 72 * v14;
            ATL::CComPtr<IVirtualUIGroupItem>::CComPtr<IVirtualUIGroupItem>(&v24, v15);
            v25 = *(_DWORD *)(v15 + 8);
            v26 = *(_QWORD *)(v15 + 12);
            v27[0] = *(_DWORD *)(v15 + 24);
            v27[1] = *(_DWORD *)(v15 + 28);
            v27[2] = *(_DWORD *)(v15 + 32);
            v27[3] = *(_DWORD *)(v15 + 36);
            v27[4] = *(_DWORD *)(v15 + 40);
            v27[5] = *(_DWORD *)(v15 + 44);
            v27[6] = *(_DWORD *)(v15 + 48);
            v27[7] = *(_DWORD *)(v15 + 52);
            ATL::CComPtr<IItem>::CComPtr<IItem>(v28, v15 + 56);
            ATL::CComPtr<IItem>::CComPtr<IItem>(v29, v15 + 64);
            ATL::CComPtrBase<ISelectionStateCallback>::Release(*((_QWORD *)this + 9) + 72 * v14);
            v5 = (RTL_SRWLOCK *)((char *)this + 48);
            if ( v24 )
            {
              ReleaseSRWLockExclusive((PSRWLOCK)this + 6);
              v16 = &v26;
              if ( v25 )
                v16 = (__int64 *)v27;
              (*(void (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v24 + 24LL))(v24, v16);
              AcquireSRWLockExclusive((PSRWLOCK)this + 6);
              v13 = ++v21;
              --*((_QWORD *)this + 13);
            }
            else
            {
              v13 = v21;
            }
            *((_QWORD *)this + 3) = ++v14;
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(v29);
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(v28);
            ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v24);
          }
          *((_DWORD *)this + 10) = 0;
          v8 = (int)TargetHandle;
        }
        v6 += v13;
      }
      goto LABEL_9;
    }
    if ( v23[0] == 1 )
      goto LABEL_8;
    if ( v23[0] != 2 )
    {
      if ( v23[0] == 3 )
LABEL_8:
        LODWORD(TargetHandle) = ++v8;
LABEL_9:
      v7 = Data;
      continue;
    }
    ATL::CComPtrBase<ISelectionStateCallback>::Release(*((_QWORD *)this + 9) + 72 * i);
    v7 = ++Data;
    --*((_QWORD *)this + 13);
  }
  if ( *((_DWORD *)this + 11) )
    *((_QWORD *)this + 4) = v9;
  else
    *((_QWORD *)this + 2) = v9;
  *v33 = v6;
  *v34 = v7;
  *v35 = v8;
  ReleaseSRWLockExclusive(v5);
}

```

## disassembly

```asm
0x18005f0a0  mov     rax, rsp
0x18005f0a3  mov     [rax+20h], r9
0x18005f0a7  mov     [rax+18h], r8
0x18005f0ab  mov     [rax+10h], rdx
0x18005f0af  push    rbp
0x18005f0b0  push    rbx
0x18005f0b1  push    rsi
0x18005f0b2  push    rdi
0x18005f0b3  push    r12
0x18005f0b5  push    r13
0x18005f0b7  push    r14
0x18005f0b9  push    r15
0x18005f0bb  lea     rbp, [rax-5Fh]
0x18005f0bf  sub     rsp, 0C8h
0x18005f0c6  mov     rsi, rcx
0x18005f0c9  xor     r14d, r14d
0x18005f0cc  cmp     [rcx+28h], r14d
0x18005f0d0  jz      short loc_18005F10A
0x18005f0d2  call    cs:__imp_GetCurrentThreadId
0x18005f0d8  mov     cs:?g_dwReentrantThreadId@@3KC, eax; ulong volatile g_dwReentrantThreadId
0x18005f0de  mov     cs:?g_ReentrantCheck@@3W4REENTRANCYCHECKTHATFAILED@@C, 1; REENTRANCYCHECKTHATFAILED volatile g_ReentrantCheck
0x18005f0e8  xor     r9d, r9d; fDefault
0x18005f0eb  xor     r8d, r8d; fIgnoreHKCU
0x18005f0ee  lea     rdx, ValueName; "ShellViewReentered"
0x18005f0f5  lea     rcx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005f0fc  call    cs:__imp_SHRegGetBoolUSValueW
0x18005f102  test    eax, eax
0x18005f104  jz      loc_18005F3E6
0x18005f10a  lea     rdi, [rsi+30h]
0x18005f10e  mov     rcx, rdi; SRWLock
0x18005f111  call    cs:__imp_AcquireSRWLockExclusive
0x18005f117  mov     [rsi+40h], r14d
0x18005f11b  mov     r13d, r14d
0x18005f11e  mov     edx, r14d
0x18005f121  mov     [rbp+57h+Data], edx
0x18005f124  mov     r15d, r14d
0x18005f127  mov     dword ptr [rbp+57h+TargetHandle], r14d
0x18005f12b  mov     r12, [rsi+50h]
0x18005f12f  mov     eax, [rsi+2Ch]
0x18005f132  neg     eax
0x18005f134  sbb     rcx, rcx
0x18005f137  and     ecx, 10h
0x18005f13a  mov     r14, [rcx+rsi+10h]
0x18005f13f  cmp     r14, r12
0x18005f142  jnb     short loc_18005F1A5
0x18005f144  lea     rbx, [r14+r14*8]
0x18005f148  mov     rax, [rsi+48h]
0x18005f14c  lea     r8, [rax+rbx*8]
0x18005f150  mov     rcx, [r8]
0x18005f153  test    rcx, rcx
0x18005f156  jz      short loc_18005F19D
0x18005f158  mov     [rbp+57h+var_B0], 0
0x18005f15f  mov     r10, [rcx]
0x18005f162  mov     eax, [r8+8]
0x18005f166  neg     eax
0x18005f168  sbb     rdx, rdx
0x18005f16b  and     edx, 0Ch
0x18005f16e  add     rdx, 0Ch
0x18005f172  add     rdx, r8
0x18005f175  lea     r9, [rbp+57h+var_B0]
0x18005f179  mov     r8d, [rsi+2Ch]
0x18005f17d  mov     rax, [r10+20h]
0x18005f181  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f186  mov     ecx, [rbp+57h+var_B0]
0x18005f189  test    ecx, ecx
0x18005f18b  jz      short loc_18005F1E4
0x18005f18d  sub     ecx, 1
0x18005f190  jnz     loc_18005F32C
0x18005f196  inc     r15d
0x18005f199  mov     dword ptr [rbp+57h+TargetHandle], r15d
0x18005f19d  mov     edx, [rbp+57h+Data]
0x18005f1a0  inc     r14
0x18005f1a3  jmp     short loc_18005F13F
0x18005f1a5  cmp     dword ptr [rsi+2Ch], 0
0x18005f1a9  jnz     loc_18005F323
0x18005f1af  mov     [rsi+10h], r12
0x18005f1b3  mov     rax, [rbp+57h+arg_8]
0x18005f1b7  mov     [rax], r13d
0x18005f1ba  mov     rax, [rbp+57h+arg_10]
0x18005f1be  mov     [rax], edx
0x18005f1c0  mov     rax, [rbp+57h+arg_18]
0x18005f1c4  mov     [rax], r15d
0x18005f1c7  mov     rcx, rdi
0x18005f1ca  add     rsp, 0C8h
0x18005f1d1  pop     r15
0x18005f1d3  pop     r14
0x18005f1d5  pop     r13
0x18005f1d7  pop     r12
0x18005f1d9  pop     rdi
0x18005f1da  pop     rsi
0x18005f1db  pop     rbx
0x18005f1dc  pop     rbp
0x18005f1dd  jmp     cs:__imp_ReleaseSRWLockExclusive
0x18005f1e4  cmp     dword ptr [rsi+2Ch], 0
0x18005f1e8  jnz     loc_18005F353
0x18005f1ee  xor     ebx, ebx
0x18005f1f0  mov     [rbp+57h+var_C0], ebx
0x18005f1f3  cmp     [rsi+28h], ebx
0x18005f1f6  jnz     loc_18005F31B
0x18005f1fc  mov     dword ptr [rsi+28h], 1
0x18005f203  mov     r15, [rsi+18h]
0x18005f207  lea     rax, [r14+1]
0x18005f20b  cmp     r15, rax
0x18005f20e  jnb     loc_18005F310
0x18005f214  cmp     r15, [rsi+50h]
0x18005f218  jnb     loc_18005F310
0x18005f21e  lea     rdi, [r15+r15*8]
0x18005f222  mov     rax, [rsi+48h]
0x18005f226  lea     rbx, [rax+rdi*8]
0x18005f22a  mov     rdx, rbx
0x18005f22d  lea     rcx, [rbp+57h+var_A0]
0x18005f231  call    ??0?$CComPtr@UIVirtualUIGroupItem@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IVirtualUIGroupItem>::CComPtr<IVirtualUIGroupItem>(ATL::CComPtr<IVirtualUIGroupItem> const &)
0x18005f236  mov     eax, [rbx+8]
0x18005f239  mov     [rbp+57h+var_98], eax
0x18005f23c  mov     rax, [rbx+0Ch]
0x18005f240  mov     [rbp+57h+var_94], rax
0x18005f244  mov     eax, [rbx+18h]
0x18005f247  mov     [rbp+57h+var_88], eax
0x18005f24a  mov     eax, [rbx+1Ch]
0x18005f24d  mov     [rbp+57h+var_84], eax
0x18005f250  mov     eax, [rbx+20h]
0x18005f253  mov     [rbp+57h+var_80], eax
0x18005f256  mov     eax, [rbx+24h]
0x18005f259  mov     [rbp+57h+var_7C], eax
0x18005f25c  mov     eax, [rbx+28h]
0x18005f25f  mov     [rbp+57h+var_78], eax
0x18005f262  mov     eax, [rbx+2Ch]
0x18005f265  mov     [rbp+57h+var_74], eax
0x18005f268  mov     eax, [rbx+30h]
0x18005f26b  mov     [rbp+57h+var_70], eax
0x18005f26e  mov     eax, [rbx+34h]
0x18005f271  mov     [rbp+57h+var_6C], eax
0x18005f274  lea     rdx, [rbx+38h]
0x18005f278  lea     rcx, [rbp+57h+var_68]
0x18005f27c  call    ??0?$CComPtr@UIItem@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IItem>::CComPtr<IItem>(ATL::CComPtr<IItem> const &)
0x18005f281  lea     rdx, [rbx+40h]
0x18005f285  lea     rcx, [rbp+57h+var_60]
0x18005f289  call    ??0?$CComPtr@UIItem@@@ATL@@QEAA@AEBV01@@Z; ATL::CComPtr<IItem>::CComPtr<IItem>(ATL::CComPtr<IItem> const &)
0x18005f28e  nop
0x18005f28f  mov     rax, [rsi+48h]
0x18005f293  lea     rcx, [rax+rdi*8]
0x18005f297  call    ?Release@?$CComPtrBase@UISelectionStateCallback@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISelectionStateCallback>::Release(void)
0x18005f29c  lea     rdi, [rsi+30h]
0x18005f2a0  cmp     [rbp+57h+var_A0], 0
0x18005f2a5  jz      loc_18005F3DE
0x18005f2ab  mov     rcx, rdi; SRWLock
0x18005f2ae  call    cs:__imp_ReleaseSRWLockExclusive
0x18005f2b4  mov     rcx, [rbp+57h+var_A0]
0x18005f2b8  mov     rax, [rcx]
0x18005f2bb  lea     rdx, [rbp+57h+var_94]
0x18005f2bf  lea     r8, [rbp+57h+var_88]
0x18005f2c3  cmp     [rbp+57h+var_98], 0
0x18005f2c7  cmovnz  rdx, r8
0x18005f2cb  mov     rax, [rax+18h]
0x18005f2cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f2d4  mov     rcx, rdi; SRWLock
0x18005f2d7  call    cs:__imp_AcquireSRWLockExclusive
0x18005f2dd  mov     ebx, [rbp+57h+var_C0]
0x18005f2e0  inc     ebx
0x18005f2e2  mov     [rbp+57h+var_C0], ebx
0x18005f2e5  dec     qword ptr [rsi+68h]
0x18005f2e9  inc     r15
0x18005f2ec  mov     [rsi+18h], r15
0x18005f2f0  lea     rcx, [rbp+57h+var_60]; void *
0x18005f2f4  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18005f2f9  lea     rcx, [rbp+57h+var_68]; void *
0x18005f2fd  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18005f302  lea     rcx, [rbp+57h+var_A0]; void *
0x18005f306  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18005f30b  jmp     loc_18005F207
0x18005f310  mov     dword ptr [rsi+28h], 0
0x18005f317  mov     r15d, dword ptr [rbp+57h+TargetHandle]
0x18005f31b  add     r13d, ebx
0x18005f31e  jmp     loc_18005F19D
0x18005f323  mov     [rsi+20h], r12
0x18005f327  jmp     loc_18005F1B3
0x18005f32c  sub     ecx, 1
0x18005f32f  jnz     loc_18005F3D0
0x18005f335  mov     rax, [rsi+48h]
0x18005f339  lea     rcx, [rax+rbx*8]
0x18005f33d  call    ?Release@?$CComPtrBase@UISelectionStateCallback@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISelectionStateCallback>::Release(void)
0x18005f342  mov     edx, [rbp+57h+Data]
0x18005f345  inc     edx
0x18005f347  mov     [rbp+57h+Data], edx
0x18005f34a  dec     qword ptr [rsi+68h]
0x18005f34e  jmp     loc_18005F1A0
0x18005f353  mov     dword ptr [rsi+28h], 1
0x18005f35a  mov     rax, [rsi+48h]
0x18005f35e  lea     rdx, [rax+rbx*8]; struct QueuedEvent *
0x18005f362  lea     rcx, [rbp+57h+var_A0]; this
0x18005f366  call    ??0QueuedEvent@@QEAA@AEBU0@@Z; QueuedEvent::QueuedEvent(QueuedEvent const &)
0x18005f36b  nop
0x18005f36c  mov     rax, [rsi+48h]
0x18005f370  lea     rcx, [rax+rbx*8]
0x18005f374  call    ?Release@?$CComPtrBase@UISelectionStateCallback@@@ATL@@QEAAXXZ; ATL::CComPtrBase<ISelectionStateCallback>::Release(void)
0x18005f379  mov     rcx, rdi; SRWLock
0x18005f37c  call    cs:__imp_ReleaseSRWLockExclusive
0x18005f382  mov     rcx, [rbp+57h+var_A0]
0x18005f386  mov     rax, [rcx]
0x18005f389  lea     rdx, [rbp+57h+var_94]
0x18005f38d  lea     r8, [rbp+57h+var_88]
0x18005f391  cmp     [rbp+57h+var_98], 0
0x18005f395  cmovnz  rdx, r8
0x18005f399  mov     rax, [rax+18h]
0x18005f39d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005f3a2  mov     rcx, rdi; SRWLock
0x18005f3a5  call    cs:__imp_AcquireSRWLockExclusive
0x18005f3ab  dec     qword ptr [rsi+68h]
0x18005f3af  inc     r13d
0x18005f3b2  mov     dword ptr [rsi+28h], 0
0x18005f3b9  lea     rcx, [rbp+57h+var_88]; this
0x18005f3bd  call    ??1CollectionEventParams@@QEAA@XZ; CollectionEventParams::~CollectionEventParams(void)
0x18005f3c2  lea     rcx, [rbp+57h+var_A0]; void *
0x18005f3c6  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x18005f3cb  jmp     loc_18005F19D
0x18005f3d0  cmp     ecx, 1
0x18005f3d3  jnz     loc_18005F19D
0x18005f3d9  jmp     loc_18005F196
0x18005f3de  mov     ebx, [rbp+57h+var_C0]
0x18005f3e1  jmp     loc_18005F2E9
0x18005f3e6  mov     [rbp+57h+Data], 1
0x18005f3ed  mov     r9d, 4; dwType
0x18005f3f3  mov     [rsp+100h+cbData], r9d; cbData
0x18005f3f8  lea     rax, [rbp+57h+Data]
0x18005f3fc  mov     [rsp+100h+lpData], rax; lpData
0x18005f401  lea     r8, ValueName; "ShellViewReentered"
0x18005f408  lea     rdx, SubKey; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005f40f  mov     rcx, 0FFFFFFFF80000001h; hKey
0x18005f416  call    cs:__imp_RegSetKeyValueW
0x18005f41c  mov     [rbp+57h+TargetHandle], r14
0x18005f420  call    cs:__imp_GetCurrentProcess
0x18005f426  mov     rdi, rax
0x18005f429  call    cs:__imp_GetCurrentThread
0x18005f42f  mov     rbx, rax
0x18005f432  call    cs:__imp_GetCurrentProcess
0x18005f438  mov     [rsp+30h], r14d; dwOptions
0x18005f43d  mov     [rsp+100h+cbData], 1; bInheritHandle
0x18005f445  mov     dword ptr [rsp+100h+lpData], 1FFFFFh; dwDesiredAccess
0x18005f44d  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x18005f451  mov     r8, rdi; hTargetProcessHandle
0x18005f454  mov     rdx, rbx; hSourceHandle
0x18005f457  mov     rcx, rax; hSourceProcessHandle
0x18005f45a  call    cs:__imp_DuplicateHandle
0x18005f460  test    eax, eax
0x18005f462  jz      loc_18005F10A
0x18005f468  mov     [rbp+57h+var_48], r14
0x18005f46c  mov     rax, [rbp+57h+TargetHandle]
0x18005f470  mov     [rbp+57h+pData], rax
0x18005f474  call    ?ComputeStackHash@@YAKXZ; ComputeStackHash(void)
0x18005f479  mov     dword ptr [rbp+57h+var_48], eax
0x18005f47c  lea     r9, ?s_SendWERForReentrancy@@YAKPEAX@Z; pfnCallback
0x18005f483  mov     r8d, 200h; flags
0x18005f489  lea     rdx, [rbp+57h+pData]; pData
0x18005f48d  lea     rcx, ?GetProxyCreator@?$PatternProvider@VUIItemsViewScrollProvider@@UIScrollProvider@@$04@DirectUI@@UEAAP6APEAVProviderProxy@2@PEAVElement@2@@ZXZ; pfnThreadProc
0x18005f494  call    cs:__imp_SHCreateThread
0x18005f49a  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x18005f49e  call    cs:__imp_CloseHandle
0x18005f4a4  jmp     loc_18005F10A
```
