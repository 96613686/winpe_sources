# CDbOperationManager::CloseEseInstance(long)

- ea: `0x1800e8dc8`
- end: `0x1800e90e2`
- name: `?CloseEseInstance@CDbOperationManager@@AEAAXJ@Z`
- size: `794`
- prototype: `void __fastcall(CDbOperationManager *__hidden this, int)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, service_task`

## callers

- `0x1800d6b1c`
- `0x1800e8348`

## callees

- `0x18002dad0`
- `0x1800d8a68`
- `0x1800e8120`
- `0x1800e8410`
- `0x1800e8dc8`
- `0x1800ea580`
- `0x1800ea5bc`
- `0x1800ea9d4`
- `0x1800eef68`
- `0x1800eefa0`
- `0x1800eefc4`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e8df8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e8e01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e9021`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e8df8`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e8e01`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x1800e9021`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8e52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8e64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8eef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8efd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e9071`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8e52`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8e64`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8eef`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e8efd`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1800e9071`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e9081`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800e9081`
- `ESENT!JetStopServiceInstance` at `0x1800e8fd7`
- `ESENT!JetStopServiceInstance` at `0x1800e8fd7`

## pseudocode

```c
void __fastcall CDbOperationManager::CloseEseInstance(CDbOperationManager *this, int a2)
{
  struct _RTL_CRITICAL_SECTION *v2; // rsi
  __int64 v5; // rax
  __int64 v6; // r10
  int v7; // r14d
  char *v8; // r11
  __int64 v9; // rax
  __int64 v10; // r10
  __int64 v11; // rcx
  __int64 i; // rcx
  CDbTransactionContext *v13; // rsi
  int v14; // eax
  int v15; // eax
  __int64 v16; // rdx
  JET_ERR v17; // eax
  int j; // esi
  struct _RTL_CRITICAL_SECTION *v19; // rbp
  __int64 v20; // rcx
  int v21; // r14d
  __int64 k; // rcx
  __int64 v23; // rax
  int v24; // eax
  __int64 v25; // [rsp+30h] [rbp-68h] BYREF
  __int128 v26; // [rsp+38h] [rbp-60h]
  _BYTE v27[80]; // [rsp+48h] [rbp-50h] BYREF

  v2 = lpCriticalSection;
  v25 = 176;
  v26 = 0;
  EnterCriticalSection(lpCriticalSection);
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  if ( *((_DWORD *)this + 11) )
  {
    while ( *((_QWORD *)this + 21) )
    {
      v5 = CDoublyLinkedList<CDbTransactionContext>::PopFront((char *)this + 160);
      CDoublyLinkedList<CDbTransactionContext>::DListEntry::Remove(v5 + 152);
      if ( v6 )
        (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v6 + 64LL))(v6, 1);
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    if ( v2 )
      LeaveCriticalSection(v2);
  }
  else
  {
    v7 = 0;
    *((_DWORD *)this + 11) = 1;
    *((_DWORD *)this + 12) = 1;
    v8 = (char *)this + 160;
    *((_DWORD *)this + 13) = a2;
    while ( *((_QWORD *)v8 + 1) )
    {
      v9 = CDoublyLinkedList<CDbTransactionContext>::PopFront(v8);
      CDoublyLinkedList<CDbTransactionContext>::DListEntry::Remove(v9 + 152);
      CDoublyLinkedList<CDbTransactionContext>::PushBack(&v25, v10);
    }
    v11 = *((_QWORD *)this + 24);
    if ( v11 )
    {
      for ( i = v11 - *((_QWORD *)this + 23);
            i;
            i = (*(_QWORD *)(*((_QWORD *)this + 23) + i + 16) - *((_QWORD *)this + 23))
              & -(__int64)(*(_QWORD *)(*((_QWORD *)this + 23) + i + 16) != 0) )
      {
        *(_DWORD *)(i + 8) = 1;
        v7 = 1;
        ++*((_DWORD *)this + 14);
        *(_DWORD *)(i + 12) = 1;
      }
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    if ( v2 )
      LeaveCriticalSection(v2);
    CDbOperationManager::CImpersonateEseDbUser::CImpersonateEseDbUser(
      (CDbOperationManager::CImpersonateEseDbUser *)v27,
      this);
    while ( (_QWORD)v26 )
    {
      v13 = (CDbTransactionContext *)CDoublyLinkedList<CDbTransactionContext>::PopFront(&v25);
      CDbTransactionContext::ReleaseAllResources(v13);
      if ( v13 )
        (*(void (__fastcall **)(CDbTransactionContext *, __int64))(*(_QWORD *)v13 + 64LL))(v13, 1);
    }
    v14 = CJetDatabase::Close((CDbOperationManager *)((char *)this + 136));
    if ( v14 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        85,
        (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
        *((_QWORD *)this + 9),
        v14);
    v15 = CJetSession::Close((CDbOperationManager *)((char *)this + 128));
    if ( v15 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        86,
        (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
        *((_QWORD *)this + 9),
        v15);
    if ( *((_QWORD *)this + 15) != -1 )
    {
      v17 = JetStopServiceInstance(*((_QWORD *)this + 15));
      if ( v17 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_Sd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          87,
          (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
          *((_QWORD *)this + 9),
          v17);
    }
    if ( v7 )
    {
      for ( j = 0; j < 8; ++j )
      {
        v19 = lpCriticalSection;
        EnterCriticalSection(lpCriticalSection);
        v20 = *((_QWORD *)this + 24);
        if ( v20 )
        {
          v21 = 1;
          if ( j == 7 )
          {
            for ( k = v20 - *((_QWORD *)this + 23);
                  k;
                  k = (*(_QWORD *)(v23 + k + 16) - v23) & -(__int64)(*(_QWORD *)(v23 + k + 16) != 0) )
            {
              *(_DWORD *)(k + 16) = 1;
              v23 = *((_QWORD *)this + 23);
              v16 = -*(_QWORD *)(v23 + k + 16);
            }
          }
        }
        else
        {
          v21 = 0;
        }
        if ( v19 )
          LeaveCriticalSection(v19);
        if ( !v21 )
          break;
        Sleep(0xFAu);
      }
    }
    v24 = CJetInstance::Close((CDbOperationManager *)((char *)this + 120), v16);
    if ( v24 < 0 && WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_Sd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        88,
        (unsigned int)&WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids,
        *((_QWORD *)this + 9),
        v24);
    CDbOperationManager::CImpersonateEseDbUser::~CImpersonateEseDbUser((CDbOperationManager::CImpersonateEseDbUser *)v27);
  }
}

```

## disassembly

```asm
0x1800e8dc8  push    rbx
0x1800e8dca  push    rbp
0x1800e8dcb  push    rsi
0x1800e8dcc  push    rdi
0x1800e8dcd  push    r13
0x1800e8dcf  push    r14
0x1800e8dd1  push    r15
0x1800e8dd3  sub     rsp, 60h
0x1800e8dd7  mov     rsi, cs:lpCriticalSection
0x1800e8dde  mov     rbx, rcx
0x1800e8de1  xorps   xmm0, xmm0
0x1800e8de4  mov     [rsp+98h+var_68], 0B0h
0x1800e8ded  mov     rcx, rsi; lpCriticalSection
0x1800e8df0  mov     ebp, edx
0x1800e8df2  movdqu  [rsp+98h+var_60], xmm0
0x1800e8df8  call    cs:__imp_EnterCriticalSection
0x1800e8dfe  mov     rcx, rbx; lpCriticalSection
0x1800e8e01  call    cs:__imp_EnterCriticalSection
0x1800e8e07  cmp     dword ptr [rbx+2Ch], 0
0x1800e8e0b  mov     edi, 1
0x1800e8e10  jz      short loc_1800E8E6F
0x1800e8e12  cmp     qword ptr [rbx+0A8h], 0
0x1800e8e1a  jz      short loc_1800E8E4F
0x1800e8e1c  lea     rcx, [rbx+0A0h]
0x1800e8e23  call    ?PopFront@?$CDoublyLinkedList@VCDbTransactionContext@@@@QEAAPEAVCDbTransactionContext@@XZ; CDoublyLinkedList<CDbTransactionContext>::PopFront(void)
0x1800e8e28  mov     r10, rax
0x1800e8e2b  lea     rcx, [rax+98h]
0x1800e8e32  call    ?Remove@DListEntry@?$CDoublyLinkedList@VCDbTransactionContext@@@@QEAAXXZ; CDoublyLinkedList<CDbTransactionContext>::DListEntry::Remove(void)
0x1800e8e37  test    r10, r10
0x1800e8e3a  jz      short loc_1800E8E12
0x1800e8e3c  mov     rcx, [r10]
0x1800e8e3f  mov     edx, edi
0x1800e8e41  mov     rax, [rcx+40h]
0x1800e8e45  mov     rcx, r10
0x1800e8e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8e4d  jmp     short loc_1800E8E12
0x1800e8e4f  mov     rcx, rbx; lpCriticalSection
0x1800e8e52  call    cs:__imp_LeaveCriticalSection
0x1800e8e58  test    rsi, rsi
0x1800e8e5b  jz      loc_1800E90D3
0x1800e8e61  mov     rcx, rsi; lpCriticalSection
0x1800e8e64  call    cs:__imp_LeaveCriticalSection
0x1800e8e6a  jmp     loc_1800E90D3
0x1800e8e6f  xor     r14d, r14d
0x1800e8e72  mov     [rbx+2Ch], edi
0x1800e8e75  mov     [rbx+30h], edi
0x1800e8e78  lea     r11, [rbx+0A0h]
0x1800e8e7f  mov     [rbx+34h], ebp
0x1800e8e82  cmp     [r11+8], r14
0x1800e8e86  jz      short loc_1800E8EAE
0x1800e8e88  mov     rcx, r11
0x1800e8e8b  call    ?PopFront@?$CDoublyLinkedList@VCDbTransactionContext@@@@QEAAPEAVCDbTransactionContext@@XZ; CDoublyLinkedList<CDbTransactionContext>::PopFront(void)
0x1800e8e90  mov     r10, rax
0x1800e8e93  lea     rcx, [rax+98h]
0x1800e8e9a  call    ?Remove@DListEntry@?$CDoublyLinkedList@VCDbTransactionContext@@@@QEAAXXZ; CDoublyLinkedList<CDbTransactionContext>::DListEntry::Remove(void)
0x1800e8e9f  mov     rdx, r10
0x1800e8ea2  lea     rcx, [rsp+98h+var_68]
0x1800e8ea7  call    ?PushBack@?$CDoublyLinkedList@VCDbTransactionContext@@@@QEAAXPEAVCDbTransactionContext@@@Z; CDoublyLinkedList<CDbTransactionContext>::PushBack(CDbTransactionContext *)
0x1800e8eac  jmp     short loc_1800E8E82
0x1800e8eae  mov     rcx, [rbx+0C0h]
0x1800e8eb5  test    rcx, rcx
0x1800e8eb8  jz      short loc_1800E8EEC
0x1800e8eba  sub     rcx, [rbx+0B8h]
0x1800e8ec1  jz      short loc_1800E8EEC
0x1800e8ec3  mov     [rcx+8], edi
0x1800e8ec6  mov     r14d, edi
0x1800e8ec9  add     [rbx+38h], edi
0x1800e8ecc  mov     [rcx+0Ch], edi
0x1800e8ecf  mov     rax, [rbx+0B8h]
0x1800e8ed6  mov     rcx, [rax+rcx+10h]
0x1800e8edb  mov     rdx, rcx
0x1800e8ede  sub     rdx, rax
0x1800e8ee1  neg     rcx
0x1800e8ee4  sbb     rcx, rcx
0x1800e8ee7  and     rcx, rdx
0x1800e8eea  jnz     short loc_1800E8EC3
0x1800e8eec  mov     rcx, rbx; lpCriticalSection
0x1800e8eef  call    cs:__imp_LeaveCriticalSection
0x1800e8ef5  test    rsi, rsi
0x1800e8ef8  jz      short loc_1800E8F03
0x1800e8efa  mov     rcx, rsi; lpCriticalSection
0x1800e8efd  call    cs:__imp_LeaveCriticalSection
0x1800e8f03  mov     rdx, rbx; struct CDbOperationManager *
0x1800e8f06  lea     rcx, [rsp+98h+var_50]; this
0x1800e8f0b  call    ??0CImpersonateEseDbUser@CDbOperationManager@@QEAA@PEAV1@@Z; CDbOperationManager::CImpersonateEseDbUser::CImpersonateEseDbUser(CDbOperationManager *)
0x1800e8f10  cmp     qword ptr [rsp+98h+var_60], 0
0x1800e8f16  jz      short loc_1800E8F45
0x1800e8f18  lea     rcx, [rsp+98h+var_68]
0x1800e8f1d  call    ?PopFront@?$CDoublyLinkedList@VCDbTransactionContext@@@@QEAAPEAVCDbTransactionContext@@XZ; CDoublyLinkedList<CDbTransactionContext>::PopFront(void)
0x1800e8f22  mov     rcx, rax; this
0x1800e8f25  mov     rsi, rax
0x1800e8f28  call    ?ReleaseAllResources@CDbTransactionContext@@AEAAXXZ; CDbTransactionContext::ReleaseAllResources(void)
0x1800e8f2d  test    rsi, rsi
0x1800e8f30  jz      short loc_1800E8F10
0x1800e8f32  mov     rcx, [rsi]
0x1800e8f35  mov     edx, edi
0x1800e8f37  mov     rax, [rcx+40h]
0x1800e8f3b  mov     rcx, rsi
0x1800e8f3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e8f43  jmp     short loc_1800E8F10
0x1800e8f45  lea     rcx, [rbx+88h]; this
0x1800e8f4c  call    ?Close@CJetDatabase@@QEAAJXZ; CJetDatabase::Close(void)
0x1800e8f51  lea     r13, WPP_GLOBAL_Control
0x1800e8f58  test    eax, eax
0x1800e8f5a  jns     short loc_1800E8F8B
0x1800e8f5c  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8f63  cmp     rcx, r13
0x1800e8f66  jz      short loc_1800E8F8B
0x1800e8f68  test    [rcx+1Ch], dil
0x1800e8f6c  jz      short loc_1800E8F8B
0x1800e8f6e  mov     r9, [rbx+48h]
0x1800e8f72  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e8f79  mov     rcx, [rcx+10h]
0x1800e8f7d  mov     edx, 55h ; 'U'
0x1800e8f82  mov     [rsp+98h+var_78], eax
0x1800e8f86  call    WPP_SF_Sd
0x1800e8f8b  lea     rcx, [rbx+80h]; this
0x1800e8f92  call    ?Close@CJetSession@@QEAAJXZ; CJetSession::Close(void)
0x1800e8f97  test    eax, eax
0x1800e8f99  jns     short loc_1800E8FCA
0x1800e8f9b  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8fa2  cmp     rcx, r13
0x1800e8fa5  jz      short loc_1800E8FCA
0x1800e8fa7  test    [rcx+1Ch], dil
0x1800e8fab  jz      short loc_1800E8FCA
0x1800e8fad  mov     r9, [rbx+48h]
0x1800e8fb1  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e8fb8  mov     rcx, [rcx+10h]
0x1800e8fbc  mov     edx, 56h ; 'V'
0x1800e8fc1  mov     [rsp+98h+var_78], eax
0x1800e8fc5  call    WPP_SF_Sd
0x1800e8fca  lea     r15, [rbx+78h]
0x1800e8fce  cmp     qword ptr [r15], 0FFFFFFFFFFFFFFFFh
0x1800e8fd2  jz      short loc_1800E9010
0x1800e8fd4  mov     rcx, [r15]; instance
0x1800e8fd7  call    cs:__imp_JetStopServiceInstance
0x1800e8fdd  test    eax, eax
0x1800e8fdf  jns     short loc_1800E9010
0x1800e8fe1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e8fe8  cmp     rcx, r13
0x1800e8feb  jz      short loc_1800E9010
0x1800e8fed  test    [rcx+1Ch], dil
0x1800e8ff1  jz      short loc_1800E9010
0x1800e8ff3  mov     r9, [rbx+48h]
0x1800e8ff7  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e8ffe  mov     rcx, [rcx+10h]
0x1800e9002  mov     edx, 57h ; 'W'
0x1800e9007  mov     [rsp+98h+var_78], eax
0x1800e900b  call    WPP_SF_Sd
0x1800e9010  test    r14d, r14d
0x1800e9013  jz      short loc_1800E908E
0x1800e9015  xor     esi, esi
0x1800e9017  mov     rbp, cs:lpCriticalSection
0x1800e901e  mov     rcx, rbp; lpCriticalSection
0x1800e9021  call    cs:__imp_EnterCriticalSection
0x1800e9027  mov     rcx, [rbx+0C0h]
0x1800e902e  test    rcx, rcx
0x1800e9031  jnz     short loc_1800E9038
0x1800e9033  xor     r14d, r14d
0x1800e9036  jmp     short loc_1800E9069
0x1800e9038  mov     r14d, edi
0x1800e903b  cmp     esi, 7
0x1800e903e  jnz     short loc_1800E9069
0x1800e9040  sub     rcx, [rbx+0B8h]
0x1800e9047  jz      short loc_1800E9069
0x1800e9049  mov     [rcx+10h], edi
0x1800e904c  mov     rax, [rbx+0B8h]
0x1800e9053  mov     rdx, [rax+rcx+10h]
0x1800e9058  mov     r8, rdx
0x1800e905b  sub     r8, rax
0x1800e905e  neg     rdx
0x1800e9061  sbb     rcx, rcx
0x1800e9064  and     rcx, r8
0x1800e9067  jnz     short loc_1800E9049
0x1800e9069  test    rbp, rbp
0x1800e906c  jz      short loc_1800E9077
0x1800e906e  mov     rcx, rbp; lpCriticalSection
0x1800e9071  call    cs:__imp_LeaveCriticalSection
0x1800e9077  test    r14d, r14d
0x1800e907a  jz      short loc_1800E908E
0x1800e907c  mov     ecx, 0FAh; dwMilliseconds
0x1800e9081  call    cs:__imp_Sleep
0x1800e9087  add     esi, edi
0x1800e9089  cmp     esi, 8
0x1800e908c  jl      short loc_1800E9017
0x1800e908e  mov     rcx, r15; this
0x1800e9091  call    ?Close@CJetInstance@@QEAAJK@Z; CJetInstance::Close(ulong)
0x1800e9096  test    eax, eax
0x1800e9098  jns     short loc_1800E90C9
0x1800e909a  mov     rcx, cs:WPP_GLOBAL_Control
0x1800e90a1  cmp     rcx, r13
0x1800e90a4  jz      short loc_1800E90C9
0x1800e90a6  test    [rcx+1Ch], dil
0x1800e90aa  jz      short loc_1800E90C9
0x1800e90ac  mov     r9, [rbx+48h]
0x1800e90b0  lea     r8, WPP_bbf747101dc030c08db8ff9d4150e8cf_Traceguids
0x1800e90b7  mov     rcx, [rcx+10h]
0x1800e90bb  mov     edx, 58h ; 'X'
0x1800e90c0  mov     [rsp+98h+var_78], eax
0x1800e90c4  call    WPP_SF_Sd
0x1800e90c9  lea     rcx, [rsp+98h+var_50]; this
0x1800e90ce  call    ??1CImpersonateEseDbUser@CDbOperationManager@@QEAA@XZ; CDbOperationManager::CImpersonateEseDbUser::~CImpersonateEseDbUser(void)
0x1800e90d3  add     rsp, 60h
0x1800e90d7  pop     r15
0x1800e90d9  pop     r14
0x1800e90db  pop     r13
0x1800e90dd  pop     rdi
0x1800e90de  pop     rsi
0x1800e90df  pop     rbp
0x1800e90e0  pop     rbx
0x1800e90e1  retn
```
