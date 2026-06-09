# CDbOperationManager::CommitTransaction(CReplicaMetadata *)

- ea: `0x1800e90e8`
- end: `0x1800e9358`
- name: `?CommitTransaction@CDbOperationManager@@QEAAJPEAVCReplicaMetadata@@@Z`
- size: `624`
- prototype: `__int64 __fastcall(CDbOperationManager *__hidden this, struct CReplicaMetadata *)`
- caller_count: `4`
- callee_count: `16`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800d3b60`
- `0x1800d8638`
- `0x1800d9270`
- `0x1800ead0c`

## callees

- `0x180011314`
- `0x18001133c`
- `0x18001137c`
- `0x18002dad0`
- `0x1800d6154`
- `0x1800d6e58`
- `0x1800d6eb4`
- `0x1800e7fe4`
- `0x1800e8120`
- `0x1800e82cc`
- `0x1800e8410`
- `0x1800e8adc`
- `0x1800e90e8`
- `0x1800e99a0`
- `0x1800ea844`
- `0x1800eac7c`

## import_xrefs

- `KERNEL32!ReleaseSemaphore` at `0x1800e92d1`
- `KERNEL32!ReleaseSemaphore` at `0x1800e92d1`
- `KERNEL32!GetLastError` at `0x1800e92db`
- `KERNEL32!GetLastError` at `0x1800e92db`
- `ESENT!JetCommitTransaction` at `0x1800e924c`
- `ESENT!JetCommitTransaction` at `0x1800e924c`

## string_xrefs

- `0x1800e911d`: `CDbOperationManager::CommitTransaction`
- `0x1800e9333`: `CDbOperationManager::CommitTransaction`

## pseudocode

```c
__int64 __fastcall CDbOperationManager::CommitTransaction(CDbOperationManager *this, struct CReplicaMetadata *a2)
{
  CDbOperationManager *v4; // rcx
  struct CDbTransactionContext *TransactionContext; // rsi
  int v6; // ebx
  JET_ERR v7; // eax
  int v8; // eax
  __int64 v9; // r10
  signed int LastError; // eax
  _BYTE v12[16]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v13[16]; // [rsp+40h] [rbp-48h] BYREF
  int v14; // [rsp+50h] [rbp-38h]

  v4 = (CDbOperationManager *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      48,
      &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
      "CDbOperationManager::CommitTransaction");
  TransactionContext = CDbOperationManager::FindTransactionContext(v4, a2);
  if ( !TransactionContext )
  {
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
      WPP_SF_S(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        49,
        &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
        *((_QWORD *)this + 9));
    v6 = -2147216750;
    goto LABEL_35;
  }
  CDbOperationManager::CImpersonateEseDbUser::CImpersonateEseDbUser(
    (CDbOperationManager::CImpersonateEseDbUser *)v13,
    this);
  CAcquireReleaseSemaphore::CAcquireReleaseSemaphore(
    (CAcquireReleaseSemaphore *)v12,
    *(void **)&lpCriticalSection[1].LockCount);
  v6 = v14;
  if ( v14 >= 0 )
  {
    if ( *((_DWORD *)TransactionContext + 2) )
    {
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
        WPP_SF_S(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          51,
          &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          *((_QWORD *)this + 9));
      v6 = ResultFromJetError(-1090);
    }
    else
    {
      if ( CDbOperationManager::s_SimulateNeedToInitializeFailure )
      {
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
          WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 52, &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids);
        v7 = -1022;
      }
      else
      {
        v7 = JetCommitTransaction(*((_QWORD *)TransactionContext + 5), *((_DWORD *)this + 27) != 0);
      }
      v8 = ResultFromJetError(v7);
      v6 = v8;
      if ( v8 >= 0 )
        goto LABEL_29;
      if ( (PVOID *)v9 != &WPP_GLOBAL_Control && (*(_BYTE *)(v9 + 28) & 1) != 0 )
        WPP_SF_Sd(
          *(_QWORD *)(v9 + 16),
          53,
          (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          *((_QWORD *)this + 9),
          v8);
    }
  }
  else if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_Sd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      50,
      (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
      *((_QWORD *)this + 9),
      v14);
  }
  CDbOperationManager::RollbackTransactionHelper(this, TransactionContext);
LABEL_29:
  CAcquireReleaseSemaphore::~CAcquireReleaseSemaphore((CAcquireReleaseSemaphore *)v12);
  CDbOperationManager::CImpersonateEseDbUser::~CImpersonateEseDbUser((CDbOperationManager::CImpersonateEseDbUser *)v13);
  CDbOperationManager::ReleaseTransactionContext(this, TransactionContext, v6 >= 0);
  if ( !ReleaseSemaphore(lpCriticalSection[1].DebugInfo, 1, 0) )
  {
    LastError = GetLastError();
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_d(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        54,
        &WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
        (unsigned int)LastError);
  }
LABEL_35:
  CDbOperationManager::CheckForFatalInstanceError(this, v6);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 4) != 0 )
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      55,
      (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
      (unsigned int)"CDbOperationManager::CommitTransaction",
      v6);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800e90e8  push    rbx
0x1800e90ea  push    rbp
0x1800e90eb  push    rsi
0x1800e90ec  push    rdi
0x1800e90ed  push    r14
0x1800e90ef  sub     rsp, 60h
0x1800e90f3  mov     rbx, rdx
0x1800e90f6  mov     rdi, rcx
0x1800e90f9  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9100  lea     rbp, WPP_GLOBAL_Control
0x1800e9107  lea     r14, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e910e  cmp     rcx, rbp
0x1800e9111  jz      short loc_1800E9131
0x1800e9113  test    byte ptr [rcx+1Ch], 4
0x1800e9117  jz      short loc_1800E9131
0x1800e9119  mov     rcx, [rcx+10h]
0x1800e911d  lea     r9, aCdboperationma_6; "CDbOperationManager::CommitTransaction"
0x1800e9124  mov     edx, 30h ; '0'
0x1800e9129  mov     r8, r14
0x1800e912c  call    WPP_SF_s
0x1800e9131  mov     rdx, rbx; struct CReplicaMetadata *
0x1800e9134  call    ?FindTransactionContext@CDbOperationManager@@AEAAPEAVCDbTransactionContext@@PEAVCReplicaMetadata@@@Z; CDbOperationManager::FindTransactionContext(CReplicaMetadata *)
0x1800e9139  mov     rsi, rax
0x1800e913c  test    rax, rax
0x1800e913f  jnz     short loc_1800E9170
0x1800e9141  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9148  cmp     rcx, rbp
0x1800e914b  jz      short loc_1800E9166
0x1800e914d  test    byte ptr [rcx+1Ch], 2
0x1800e9151  jz      short loc_1800E9166
0x1800e9153  mov     r9, [rdi+48h]
0x1800e9157  lea     edx, [rax+31h]
0x1800e915a  mov     rcx, [rcx+10h]
0x1800e915e  mov     r8, r14
0x1800e9161  call    WPP_SF_S
0x1800e9166  mov     ebx, 80041292h
0x1800e916b  jmp     loc_1800E9313
0x1800e9170  mov     rdx, rdi; struct CDbOperationManager *
0x1800e9173  lea     rcx, [rsp+88h+var_48]; this
0x1800e9178  call    ??0CImpersonateEseDbUser@CDbOperationManager@@QEAA@PEAV1@@Z; CDbOperationManager::CImpersonateEseDbUser::CImpersonateEseDbUser(CDbOperationManager *)
0x1800e917d  mov     rdx, cs:lpCriticalSection
0x1800e9184  lea     rcx, [rsp+88h+var_58]; this
0x1800e9189  mov     rdx, [rdx+30h]; void *
0x1800e918d  call    ??0CAcquireReleaseSemaphore@@QEAA@PEAX@Z; CAcquireReleaseSemaphore::CAcquireReleaseSemaphore(void *)
0x1800e9192  mov     ebx, [rsp+88h+var_38]
0x1800e9196  test    ebx, ebx
0x1800e9198  jns     short loc_1800E91C6
0x1800e919a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e91a1  cmp     rcx, rbp
0x1800e91a4  jz      loc_1800E928B
0x1800e91aa  test    byte ptr [rcx+1Ch], 1
0x1800e91ae  jz      loc_1800E928B
0x1800e91b4  mov     rcx, [rcx+10h]
0x1800e91b8  mov     edx, 32h ; '2'
0x1800e91bd  mov     [rsp+88h+var_68], ebx
0x1800e91c1  jmp     loc_1800E927F
0x1800e91c6  mov     eax, [rsi+8]
0x1800e91c9  test    eax, eax
0x1800e91cb  jz      short loc_1800E9205
0x1800e91cd  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e91d4  cmp     rcx, rbp
0x1800e91d7  jz      short loc_1800E91F4
0x1800e91d9  test    byte ptr [rcx+1Ch], 4
0x1800e91dd  jz      short loc_1800E91F4
0x1800e91df  mov     r9, [rdi+48h]
0x1800e91e3  mov     edx, 33h ; '3'
0x1800e91e8  mov     rcx, [rcx+10h]
0x1800e91ec  mov     r8, r14
0x1800e91ef  call    WPP_SF_S
0x1800e91f4  mov     ecx, 0FFFFFBBEh; int
0x1800e91f9  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e91fe  mov     ebx, eax
0x1800e9200  jmp     loc_1800E928B
0x1800e9205  cmp     cs:?s_SimulateNeedToInitializeFailure@CDbOperationManager@@0HA, 0; int CDbOperationManager::s_SimulateNeedToInitializeFailure
0x1800e920c  jz      short loc_1800E9240
0x1800e920e  mov     r10, cs:WPP_GLOBAL_Control
0x1800e9215  cmp     r10, rbp
0x1800e9218  jz      short loc_1800E9239
0x1800e921a  test    byte ptr [r10+1Ch], 2
0x1800e921f  jz      short loc_1800E9239
0x1800e9221  mov     rcx, [r10+10h]
0x1800e9225  mov     edx, 34h ; '4'
0x1800e922a  mov     r8, r14
0x1800e922d  call    WPP_SF_
0x1800e9232  mov     r10, cs:WPP_GLOBAL_Control
0x1800e9239  mov     eax, 0FFFFFC02h
0x1800e923e  jmp     short loc_1800E9259
0x1800e9240  mov     rcx, [rsi+28h]; sesid
0x1800e9244  xor     edx, edx
0x1800e9246  cmp     [rdi+6Ch], edx
0x1800e9249  setnz   dl; grbit
0x1800e924c  call    cs:__imp_JetCommitTransaction
0x1800e9252  mov     r10, cs:WPP_GLOBAL_Control
0x1800e9259  mov     ecx, eax; int
0x1800e925b  call    ?ResultFromJetError@@YAJJ@Z; ResultFromJetError(long)
0x1800e9260  mov     ebx, eax
0x1800e9262  test    eax, eax
0x1800e9264  jns     short loc_1800E9296
0x1800e9266  cmp     r10, rbp
0x1800e9269  jz      short loc_1800E928B
0x1800e926b  test    byte ptr [r10+1Ch], 1
0x1800e9270  jz      short loc_1800E928B
0x1800e9272  mov     rcx, [r10+10h]
0x1800e9276  mov     edx, 35h ; '5'
0x1800e927b  mov     [rsp+88h+var_68], eax
0x1800e927f  mov     r9, [rdi+48h]
0x1800e9283  mov     r8, r14
0x1800e9286  call    WPP_SF_Sd
0x1800e928b  mov     rdx, rsi; struct CDbTransactionContext *
0x1800e928e  mov     rcx, rdi; this
0x1800e9291  call    ?RollbackTransactionHelper@CDbOperationManager@@AEAAJPEAVCDbTransactionContext@@@Z; CDbOperationManager::RollbackTransactionHelper(CDbTransactionContext *)
0x1800e9296  lea     rcx, [rsp+88h+var_58]; this
0x1800e929b  call    ??1CAcquireReleaseSemaphore@@QEAA@XZ; CAcquireReleaseSemaphore::~CAcquireReleaseSemaphore(void)
0x1800e92a0  lea     rcx, [rsp+88h+var_48]; this
0x1800e92a5  call    ??1CImpersonateEseDbUser@CDbOperationManager@@QEAA@XZ; CDbOperationManager::CImpersonateEseDbUser::~CImpersonateEseDbUser(void)
0x1800e92aa  mov     r8d, ebx
0x1800e92ad  mov     rdx, rsi; struct CDbTransactionContext *
0x1800e92b0  not     r8d
0x1800e92b3  mov     rcx, rdi; this
0x1800e92b6  shr     r8d, 1Fh; int
0x1800e92ba  call    ?ReleaseTransactionContext@CDbOperationManager@@AEAAXPEAVCDbTransactionContext@@H@Z; CDbOperationManager::ReleaseTransactionContext(CDbTransactionContext *,int)
0x1800e92bf  mov     rcx, cs:lpCriticalSection
0x1800e92c6  xor     r8d, r8d; lpPreviousCount
0x1800e92c9  mov     rcx, [rcx+28h]; hSemaphore
0x1800e92cd  lea     edx, [r8+1]; lReleaseCount
0x1800e92d1  call    cs:__imp_ReleaseSemaphore
0x1800e92d7  test    eax, eax
0x1800e92d9  jnz     short loc_1800E9313
0x1800e92db  call    cs:__imp_GetLastError
0x1800e92e1  test    eax, eax
0x1800e92e3  jle     short loc_1800E92ED
0x1800e92e5  movzx   eax, ax
0x1800e92e8  or      eax, 80070000h
0x1800e92ed  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e92f4  cmp     rcx, rbp
0x1800e92f7  jz      short loc_1800E9313
0x1800e92f9  test    byte ptr [rcx+1Ch], 1
0x1800e92fd  jz      short loc_1800E9313
0x1800e92ff  mov     rcx, [rcx+10h]
0x1800e9303  mov     edx, 36h ; '6'
0x1800e9308  mov     r9d, eax
0x1800e930b  mov     r8, r14
0x1800e930e  call    WPP_SF_d
0x1800e9313  mov     edx, ebx; int
0x1800e9315  mov     rcx, rdi; this
0x1800e9318  call    ?CheckForFatalInstanceError@CDbOperationManager@@AEAAXJ@Z; CDbOperationManager::CheckForFatalInstanceError(long)
0x1800e931d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e9324  cmp     rcx, rbp
0x1800e9327  jz      short loc_1800E934B
0x1800e9329  test    byte ptr [rcx+1Ch], 4
0x1800e932d  jz      short loc_1800E934B
0x1800e932f  mov     rcx, [rcx+10h]
0x1800e9333  lea     r9, aCdboperationma_6; "CDbOperationManager::CommitTransaction"
0x1800e933a  mov     edx, 37h ; '7'
0x1800e933f  mov     [rsp+88h+var_68], ebx
0x1800e9343  mov     r8, r14
0x1800e9346  call    WPP_SF_sD
0x1800e934b  mov     eax, ebx
0x1800e934d  add     rsp, 60h
0x1800e9351  pop     r14
0x1800e9353  pop     rdi
0x1800e9354  pop     rsi
0x1800e9355  pop     rbp
0x1800e9356  pop     rbx
0x1800e9357  retn
```
