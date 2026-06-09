# CmsDurableLog::WriteLog(void)

- ea: `0x1400c7fcc`
- end: `0x1400c8647`
- name: `?WriteLog@CmsDurableLog@@QEAAJXZ`
- size: `1659`
- prototype: `__int64 __fastcall(CmsDurableLog *__hidden this)`
- caller_count: `5`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400c4b60`
- `0x1400c77f0`
- `0x1400d1b38`
- `0x1401485a0`
- `0x14015e6a0`

## callees

- `0x140022ae0`
- `0x140022cd0`
- `0x140022e3c`
- `0x140022e80`
- `0x140023394`
- `0x140023700`
- `0x140024c60`
- `0x14007e800`
- `0x140080630`
- `0x1400813bc`
- `0x140081630`
- `0x14008cba0`
- `0x140096b90`
- `0x140098760`
- `0x1400ba070`
- `0x1400c7fcc`
- `0x1400cbe48`
- `0x140126378`
- `0x1401f4400`

## import_xrefs

- `ntoskrnl!IoClearActivityIdThread` at `0x1400c8627`
- `ntoskrnl!IoClearActivityIdThread` at `0x1400c8627`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400c800c`
- `ntoskrnl!IoSetActivityIdThread` at `0x1400c800c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c805d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c817f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c82ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c84a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c85af`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c805d`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c817f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c82ce`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c84a9`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x1400c85af`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c807f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c80b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c81f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c8356`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c8506`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c8609`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c807f`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c80b6`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c81f1`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c8356`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c8506`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400c8609`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x1400c8426`
- `ntoskrnl!RtlCopyMemoryNonTemporal` at `0x1400c8426`
- `ntoskrnl!IoTransferActivityId` at `0x1400c802a`
- `ntoskrnl!IoTransferActivityId` at `0x1400c8041`
- `ntoskrnl!IoTransferActivityId` at `0x1400c802a`
- `ntoskrnl!IoTransferActivityId` at `0x1400c8041`

## pseudocode

```c
__int64 __fastcall CmsDurableLog::WriteLog(CmsDurableLog *this)
{
  struct _MSENV_IO_REQUEST *IoRequest; // rbp
  char *v4; // rdi
  __int64 v5; // rsi
  unsigned int **v6; // r15
  KIRQL v7; // al
  int v8; // edi
  void **v9; // r14
  __int64 v10; // rcx
  struct _SmsMergeState *v11; // rsi
  unsigned int RunCount; // edi
  KSPIN_LOCK *v13; // rdi
  KIRQL v14; // al
  unsigned int *v15; // r14
  unsigned int v16; // eax
  int v17; // eax
  int v18; // eax
  __int64 v19; // r8
  void *v20; // rax
  _QWORD *IoRun; // rdi
  unsigned int v22; // r12d
  struct _MS_IO_RUN *Run; // rax
  struct _MS_IO_RUN *v24; // r15
  _QWORD *v25; // r14
  __int64 v26; // rdx
  unsigned int v27; // ecx
  __int64 v28; // rcx
  unsigned int v29; // eax
  bool v30; // zf
  size_t v31; // [rsp+28h] [rbp-90h]
  int v32; // [rsp+30h] [rbp-88h]
  int v33; // [rsp+30h] [rbp-88h]
  __int64 v34; // [rsp+38h] [rbp-80h]
  unsigned __int64 v35; // [rsp+38h] [rbp-80h]
  __int64 v36; // [rsp+60h] [rbp-58h] BYREF
  __int64 v37; // [rsp+68h] [rbp-50h]
  char v38; // [rsp+C0h] [rbp+8h]
  unsigned int v39; // [rsp+C8h] [rbp+10h]
  unsigned int v40; // [rsp+D0h] [rbp+18h]
  __int64 v41; // [rsp+D8h] [rbp+20h] BYREF

  IoRequest = 0;
  v41 = 0;
  if ( _InterlockedExchange((volatile __int32 *)this + 50, 1) == 1 )
    return 259;
  v4 = (char *)this + 300;
  v5 = IoSetActivityIdThread((char *)this + 300);
  v37 = v5;
  IoTransferActivityId(v4, &MsActivityIdLogWrite);
  if ( v5 )
    IoTransferActivityId(v4, v5);
  v6 = (unsigned int **)((char *)this + 88);
  if ( *((_QWORD *)this + 11) )
  {
    v9 = (void **)((char *)this + 88);
LABEL_12:
    v10 = *((_QWORD *)this + 10);
    if ( (*(_DWORD *)(v10 + 3396) & 0x20000000) != 0 || (*((_DWORD *)this + 74) & 4) == 0 )
    {
      CmsDurableLog::DeleteOutstandingWrites(this);
      v8 = -1073741202;
      v38 = 0;
      goto LABEL_62;
    }
    v11 = 0;
    v39 = 0;
    IoRequest = (struct _MSENV_IO_REQUEST *)MsKmeAllocateIoRequest(
                                              *(_QWORD *)(v10 + 48),
                                              (unsigned int)MsPerfParams,
                                              516);
    RunCount = MsKmeGetRunCount(IoRequest, 0);
    v40 = RunCount;
    _InterlockedIncrement64((volatile signed __int64 *)(*((_QWORD *)this + 10) + 896LL));
    if ( RunCount > 1 )
    {
      v11 = CmsDurableLog::ShouldDoubleBufferWrites((KSPIN_LOCK *)this);
      if ( v11 )
        v40 = RunCount - 1;
    }
    MsKmeSetCallbackIoRequest(
      IoRequest,
      (int (*)(struct _MSENV_IO_REQUEST *, int, void *, void *, void *, void *))CmsDurableLog::LogWriteBatchCompletion,
      this,
      v11,
      0,
      0);
    v13 = (KSPIN_LOCK *)((char *)this + 40);
    v14 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
    v15 = (unsigned int *)*v9;
    *((_BYTE *)this + 48) = v14;
    if ( v15 )
    {
      v8 = 0;
      v16 = 0;
      while ( 1 )
      {
        v38 = 1;
        if ( v16 >= v40 )
        {
LABEL_29:
          if ( v8 < 0 )
          {
LABEL_30:
            if ( v8 != -1073741670 && v8 != -1073741802 )
              goto LABEL_62;
          }
          v13 = (KSPIN_LOCK *)((char *)this + 40);
          goto LABEL_33;
        }
        v38 = 1;
        if ( v8 < 0 )
          goto LABEL_30;
        v36 = *((_QWORD *)v15 + 7);
        *((_QWORD *)this + 11) = *((_QWORD *)v15 + 6);
        *((_QWORD *)v15 + 6) = 0;
        if ( *((unsigned int **)this + 12) == v15 )
          *((_QWORD *)this + 12) = 0;
        KeReleaseSpinLock((PKSPIN_LOCK)this + 5, *((_BYTE *)this + 48));
        v17 = *((_DWORD *)this + 74);
        if ( (v17 & 2) == 0 )
          *((_DWORD *)this + 74) = v17 | 2;
        memset((void *)(*((_QWORD *)v15 + 1) + v15[8]), 0, v15[6] - v15[8]);
        LODWORD(v31) = v15[6];
        v18 = MlLogWriteLogRecord(
                *((_QWORD *)this + 9),
                (int)IoRequest,
                *(_QWORD *)v15,
                v15[9],
                *((void **)v15 + 1),
                v31,
                v32,
                v34,
                *((_QWORD *)v15 + 7),
                (__int64)&v41);
        v8 = v18;
        if ( v18 == -1073741670 )
        {
          v13 = (KSPIN_LOCK *)((char *)this + 40);
          *((_BYTE *)this + 48) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
          *((_QWORD *)v15 + 6) = *v6;
          v30 = *((_QWORD *)this + 12) == 0;
          *v6 = v15;
          if ( v30 )
            *((_QWORD *)this + 12) = v15;
          goto LABEL_33;
        }
        _InterlockedAdd((volatile signed __int32 *)this + 73, -v15[11]);
        if ( v18 < 0 )
        {
          v38 = 0;
          if ( v18 != -1073741802 )
            break;
        }
        *((_QWORD *)MsKmeGetRun(IoRequest, v39) + 6) = v15;
        *((_QWORD *)v15 + 8) = v41;
        CmsDurableLog::CheckForVirtualWaiterMigration(this, (struct _SmsLsn *)&v36, (union _ML_LSN *)&v41, 0);
        *((_BYTE *)this + 48) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
        *((_QWORD *)this + 14) = *((_QWORD *)v15 + 7);
        *((_QWORD *)this + 16) = v41;
        v15 = *v6;
        v16 = v39 + 1;
        v38 = 1;
        ++v39;
        if ( !*v6 )
          goto LABEL_29;
      }
      v28 = *((_QWORD *)this + 10);
      if ( (*(_DWORD *)(v28 + 3396) & 0x20000000) == 0 )
      {
        LOBYTE(v19) = 1;
        CmsVolume::ChangeVolumeOptionDynamically(v28, 0x20000000, v19);
      }
      LOBYTE(v31) = 1;
      CmsVolume::NotifyUnrecoverableMetadata(*((_QWORD *)this + 10), (unsigned int)v8, 0xC40170F0BLL, 0, 0, v31);
      v29 = v15[11];
      if ( v29 )
      {
        _InterlockedAdd((volatile signed __int32 *)this + 72, -v29);
        v15[11] = 0;
      }
      CmsTxMemLog::FreeRedoBlock(v15);
      CmsDurableLog::DeleteOutstandingWrites(this);
      if ( v11 )
      {
        if ( *(_QWORD *)v11 )
          CmsLookasides::Free(*(void **)v11);
        CmsLookasides::Free(v11);
      }
LABEL_62:
      CmsDurableLog::ReleaseActiveLogWriter(this);
      if ( v38 )
        KeReleaseSpinLock((PKSPIN_LOCK)this + 5, *((_BYTE *)this + 48));
      if ( IoRequest )
        MsKmeReleaseIoRequest(IoRequest);
      goto LABEL_66;
    }
LABEL_33:
    if ( v11 && v39 >= dword_14026914C )
    {
      KeReleaseSpinLock(v13, *((_BYTE *)this + 48));
      v20 = *(void **)v11;
      v35 = ~(unsigned __int64)(unsigned int)(*((_DWORD *)v11 + 2) + 256);
      v33 = *((_DWORD *)v11 + 2);
      *((_QWORD *)v11 + 2) = v35;
      IoRun = (_QWORD *)MsKmeAllocateIoRun(IoRequest, 0, 0, 0, 3, v20, v33, v35);
      if ( IoRun )
      {
        IoRun[5] = 0;
        IoRun[4] = LogWriteDoubleBufferWriteCompletion;
        IoRun[6] = 0;
        IoRun[7] = 0;
        v22 = 0;
        if ( MsKmeGetRunCount(IoRequest, 1u) != 1 )
        {
          do
          {
            Run = MsKmeGetRun(IoRequest, v22);
            v24 = Run;
            v25 = (_QWORD *)((char *)Run + 16);
            if ( !*((_DWORD *)v11 + 6) )
              *((_QWORD *)v11 + 2) = *v25;
            v26 = *((unsigned int *)v11 + 3);
            if ( *v25 != v26 + *((_QWORD *)v11 + 2) )
              break;
            v27 = *((_DWORD *)Run + 2);
            if ( v27 > *((_DWORD *)v11 + 2) - (int)v26 )
              break;
            RtlCopyMemoryNonTemporal((void *)(v26 + *(_QWORD *)v11), *(const void **)Run, v27);
            *((_DWORD *)v11 + 3) += *((_DWORD *)v24 + 2);
            ++*((_DWORD *)v11 + 6);
            MsKmeSetIoRun(IoRequest, v24, 0, 2, *((_DWORD *)v24 + 2), *v25);
            ++v22;
          }
          while ( v22 < MsKmeGetRunCount(IoRequest, 1u) - 1 );
        }
      }
      if ( *((_DWORD *)v11 + 6) )
        MsKmeSetIoRun(IoRequest, IoRun, 0, 1, *((_DWORD *)v11 + 3), *((_QWORD *)v11 + 2));
      v13 = (KSPIN_LOCK *)((char *)this + 40);
      *((_BYTE *)this + 48) = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
    }
    _InterlockedAdd((volatile signed __int32 *)this + 48, MsKmeGetRunCount(IoRequest, 1u));
    if ( MsPerfStats < v39 )
      MsPerfStats = v39;
    if ( (unsigned int)dword_140268EC4 < *((_DWORD *)this + 48) )
      dword_140268EC4 = *((_DWORD *)this + 48);
    CmsDurableLog::ReleaseActiveLogWriter(this);
    KeReleaseSpinLock(v13, *((_BYTE *)this + 48));
    MsKmeSubmitIoRequest(IoRequest);
    goto LABEL_50;
  }
  v7 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)this + 5);
  *((_BYTE *)this + 48) = v7;
  if ( *v6 )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)this + 5, v7);
    v9 = (void **)((char *)this + 88);
    goto LABEL_12;
  }
  CmsDurableLog::ReleaseActiveLogWriter(this);
  KeReleaseSpinLock((PKSPIN_LOCK)this + 5, *((_BYTE *)this + 48));
  if ( !_bittest((const signed __int32 *)(*((_QWORD *)this + 10) + 3396LL), 0x1Du) && (*((_DWORD *)this + 74) & 4) != 0 )
  {
LABEL_50:
    v8 = 259;
    goto LABEL_66;
  }
  v8 = -1073741202;
LABEL_66:
  IoClearActivityIdThread(v37);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1400c7fcc  mov     rax, rsp
0x1400c7fcf  push    rbx
0x1400c7fd0  push    rbp
0x1400c7fd1  push    rsi
0x1400c7fd2  push    rdi
0x1400c7fd3  push    r12
0x1400c7fd5  push    r13
0x1400c7fd7  push    r14
0x1400c7fd9  push    r15
0x1400c7fdb  sub     rsp, 78h
0x1400c7fdf  xor     ebp, ebp
0x1400c7fe1  mov     rbx, rcx
0x1400c7fe4  mov     [rax+20h], rbp
0x1400c7fe8  nop
0x1400c7fe9  lea     eax, [rbp+1]
0x1400c7fec  xchg    eax, [rcx+0C8h]
0x1400c7ff2  nop
0x1400c7ff3  cmp     eax, 1
0x1400c7ff6  jnz     short loc_1400C8002
0x1400c7ff8  mov     eax, 103h
0x1400c7ffd  jmp     loc_1400C8635
0x1400c8002  lea     rdi, [rcx+12Ch]
0x1400c8009  mov     rcx, rdi
0x1400c800c  call    cs:__imp_IoSetActivityIdThread
0x1400c8013  nop     dword ptr [rax+rax+00h]
0x1400c8018  lea     rdx, ?MsActivityIdLogWrite@@3U_GUID@@B; _GUID const MsActivityIdLogWrite
0x1400c801f  mov     rcx, rdi
0x1400c8022  mov     rsi, rax
0x1400c8025  mov     [rsp+0B8h+var_50], rax
0x1400c802a  call    cs:__imp_IoTransferActivityId
0x1400c8031  nop     dword ptr [rax+rax+00h]
0x1400c8036  test    rsi, rsi
0x1400c8039  jz      short loc_1400C804D
0x1400c803b  mov     rdx, rsi
0x1400c803e  mov     rcx, rdi
0x1400c8041  call    cs:__imp_IoTransferActivityId
0x1400c8048  nop     dword ptr [rax+rax+00h]
0x1400c804d  lea     r15, [rbx+58h]
0x1400c8051  lea     r13, [rbx+28h]
0x1400c8055  cmp     [r15], rbp
0x1400c8058  jnz     short loc_1400C80C8
0x1400c805a  mov     rcx, r13; SpinLock
0x1400c805d  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400c8064  nop     dword ptr [rax+rax+00h]
0x1400c8069  mov     [rbx+30h], al
0x1400c806c  cmp     [r15], rbp
0x1400c806f  jnz     short loc_1400C80B1
0x1400c8071  mov     rcx, rbx; this
0x1400c8074  call    ?ReleaseActiveLogWriter@CmsDurableLog@@AEAAXXZ; CmsDurableLog::ReleaseActiveLogWriter(void)
0x1400c8079  mov     dl, [rbx+30h]; NewIrql
0x1400c807c  mov     rcx, r13; SpinLock
0x1400c807f  call    cs:__imp_KeReleaseSpinLock
0x1400c8086  nop     dword ptr [rax+rax+00h]
0x1400c808b  mov     rax, [rbx+50h]
0x1400c808f  bt      dword ptr [rax+0D44h], 1Dh
0x1400c8097  jb      short loc_1400C80A7
0x1400c8099  mov     eax, [rbx+128h]
0x1400c809f  test    al, 4
0x1400c80a1  jnz     loc_1400C851A
0x1400c80a7  mov     edi, 0C000026Eh
0x1400c80ac  jmp     loc_1400C8622
0x1400c80b1  mov     dl, al; NewIrql
0x1400c80b3  mov     rcx, r13; SpinLock
0x1400c80b6  call    cs:__imp_KeReleaseSpinLock
0x1400c80bd  nop     dword ptr [rax+rax+00h]
0x1400c80c2  lea     r14, [rbx+58h]
0x1400c80c6  jmp     short loc_1400C80CB
0x1400c80c8  mov     r14, r15
0x1400c80cb  mov     rcx, [rbx+50h]
0x1400c80cf  mov     r12d, 20000000h
0x1400c80d5  test    [rcx+0D44h], r12d
0x1400c80dc  jnz     loc_1400C85DC
0x1400c80e2  mov     eax, [rbx+128h]
0x1400c80e8  test    al, 4
0x1400c80ea  jz      loc_1400C85DC
0x1400c80f0  mov     edx, cs:MsPerfParams
0x1400c80f6  mov     r8d, 204h
0x1400c80fc  mov     rcx, [rcx+30h]
0x1400c8100  mov     rsi, rbp
0x1400c8103  mov     [rsp+0B8h+arg_8], ebp
0x1400c810a  call    ?MsKmeAllocateIoRequest@@YAPEAU_MSENV_IO_REQUEST@@PEAU_VCB@@KW4_EMS_IO_REQUEST_FLAGS@@@Z; MsKmeAllocateIoRequest(_VCB *,ulong,_EMS_IO_REQUEST_FLAGS)
0x1400c810f  xor     edx, edx; unsigned __int8
0x1400c8111  mov     rcx, rax; struct _MSENV_IO_REQUEST *
0x1400c8114  mov     rbp, rax
0x1400c8117  call    ?MsKmeGetRunCount@@YAKPEAU_MSENV_IO_REQUEST@@E@Z; MsKmeGetRunCount(_MSENV_IO_REQUEST *,uchar)
0x1400c811c  mov     rcx, [rbx+50h]
0x1400c8120  mov     edi, eax
0x1400c8122  nop
0x1400c8123  mov     [rsp+0B8h+arg_10], eax
0x1400c812a  lock inc qword ptr [rcx+380h]
0x1400c8132  nop
0x1400c8133  cmp     eax, 1
0x1400c8136  jbe     short loc_1400C8151
0x1400c8138  mov     rcx, rbx; this
0x1400c813b  call    ?ShouldDoubleBufferWrites@CmsDurableLog@@AEAAPEAU_SmsMergeState@@XZ; CmsDurableLog::ShouldDoubleBufferWrites(void)
0x1400c8140  mov     rsi, rax
0x1400c8143  test    rax, rax
0x1400c8146  jz      short loc_1400C8151
0x1400c8148  dec     edi
0x1400c814a  mov     [rsp+0B8h+arg_10], edi
0x1400c8151  mov     [rsp+0B8h+var_90], 0; void *
0x1400c815a  lea     rdx, ?LogWriteBatchCompletion@CmsDurableLog@@CAJPEAU_MSENV_IO_REQUEST@@JPEAX111@Z; int (*)(struct _MSENV_IO_REQUEST *, int, void *, void *, void *, void *)
0x1400c8161  mov     r9, rsi; void *
0x1400c8164  mov     [rsp+0B8h+var_98], 0; void *
0x1400c816d  mov     r8, rbx; void *
0x1400c8170  mov     rcx, rbp; struct _MSENV_IO_REQUEST *
0x1400c8173  call    ?MsKmeSetCallbackIoRequest@@YAXPEAU_MSENV_IO_REQUEST@@P6AJ0JPEAX111@Z1111@Z; MsKmeSetCallbackIoRequest(_MSENV_IO_REQUEST *,long (*)(_MSENV_IO_REQUEST *,long,void *,void *,void *,void *),void *,void *,void *,void *)
0x1400c8178  lea     rdi, [rbx+28h]
0x1400c817c  mov     rcx, rdi; SpinLock
0x1400c817f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400c8186  nop     dword ptr [rax+rax+00h]
0x1400c818b  mov     r14, [r14]
0x1400c818e  mov     [rbx+30h], al
0x1400c8191  test    r14, r14
0x1400c8194  jz      loc_1400C8334
0x1400c819a  xor     edi, edi
0x1400c819c  mov     eax, edi
0x1400c819e  mov     [rsp+0B8h+arg_0], 1
0x1400c81a6  cmp     eax, [rsp+0B8h+arg_10]
0x1400c81ad  jnb     loc_1400C8318
0x1400c81b3  mov     [rsp+0B8h+arg_0], 1
0x1400c81bb  test    edi, edi
0x1400c81bd  js      loc_1400C831C
0x1400c81c3  mov     rax, [r14+38h]
0x1400c81c7  mov     [rsp+0B8h+var_58], rax
0x1400c81cc  mov     rax, [r14+30h]
0x1400c81d0  mov     [rbx+58h], rax
0x1400c81d4  mov     qword ptr [r14+30h], 0
0x1400c81dc  cmp     [rbx+60h], r14
0x1400c81e0  jnz     short loc_1400C81EA
0x1400c81e2  mov     qword ptr [rbx+60h], 0
0x1400c81ea  mov     dl, [rbx+30h]; NewIrql
0x1400c81ed  lea     rcx, [rbx+28h]; SpinLock
0x1400c81f1  call    cs:__imp_KeReleaseSpinLock
0x1400c81f8  nop     dword ptr [rax+rax+00h]
0x1400c81fd  mov     eax, [rbx+128h]
0x1400c8203  test    al, 2
0x1400c8205  jnz     short loc_1400C8210
0x1400c8207  or      eax, 2
0x1400c820a  mov     [rbx+128h], eax
0x1400c8210  mov     ecx, [r14+20h]
0x1400c8214  xor     edx, edx; Val
0x1400c8216  mov     r8d, [r14+18h]
0x1400c821a  sub     r8d, ecx; Size
0x1400c821d  add     rcx, [r14+8]; void *
0x1400c8221  call    memset
0x1400c8226  mov     r9d, [r14+24h]; int
0x1400c822a  lea     rax, [rsp+0B8h+arg_18]
0x1400c8232  mov     r8, [r14]; int
0x1400c8235  mov     rdx, rbp; int
0x1400c8238  mov     rcx, [rbx+48h]; int
0x1400c823c  mov     [rsp+0B8h+var_70], rax; __int64
0x1400c8241  mov     rax, [r14+38h]
0x1400c8245  mov     [rsp+0B8h+var_78], rax; __int64
0x1400c824a  mov     eax, [r14+18h]
0x1400c824e  mov     dword ptr [rsp+0B8h+var_90], eax; size_t
0x1400c8252  mov     rax, [r14+8]
0x1400c8256  mov     [rsp+0B8h+var_98], rax; void *
0x1400c825b  call    MlLogWriteLogRecord
0x1400c8260  mov     edi, eax
0x1400c8262  cmp     eax, 0C000009Ah
0x1400c8267  jz      loc_1400C85A8
0x1400c826d  mov     ecx, [r14+2Ch]
0x1400c8271  nop
0x1400c8272  neg     ecx
0x1400c8274  lock add [rbx+124h], ecx
0x1400c827b  nop
0x1400c827c  test    eax, eax
0x1400c827e  jns     short loc_1400C8293
0x1400c8280  mov     [rsp+0B8h+arg_0], 0
0x1400c8288  cmp     eax, 0C0000016h
0x1400c828d  jnz     loc_1400C8524
0x1400c8293  mov     edx, [rsp+0B8h+arg_8]; unsigned int
0x1400c829a  mov     rcx, rbp; struct _MSENV_IO_REQUEST *
0x1400c829d  call    ?MsKmeGetRun@@YAPEAU_MS_IO_RUN@@PEAU_MSENV_IO_REQUEST@@K@Z; MsKmeGetRun(_MSENV_IO_REQUEST *,ulong)
0x1400c82a2  xor     r9d, r9d; unsigned __int8
0x1400c82a5  lea     r8, [rsp+0B8h+arg_18]; union _ML_LSN *
0x1400c82ad  lea     rdx, [rsp+0B8h+var_58]; struct _SmsLsn *
0x1400c82b2  mov     rcx, rbx; this
0x1400c82b5  mov     [rax+30h], r14
0x1400c82b9  mov     rax, [rsp+0B8h+arg_18]
0x1400c82c1  mov     [r14+40h], rax
0x1400c82c5  call    ?CheckForVirtualWaiterMigration@CmsDurableLog@@AEAAXPEAU_SmsLsn@@PEAT_ML_LSN@@E@Z; CmsDurableLog::CheckForVirtualWaiterMigration(_SmsLsn *,_ML_LSN *,uchar)
0x1400c82ca  lea     rcx, [rbx+28h]; SpinLock
0x1400c82ce  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x1400c82d5  nop     dword ptr [rax+rax+00h]
0x1400c82da  mov     [rbx+30h], al
0x1400c82dd  mov     rax, [r14+38h]
0x1400c82e1  mov     [rbx+70h], rax
0x1400c82e5  mov     rax, [rsp+0B8h+arg_18]
0x1400c82ed  mov     [rbx+80h], rax
0x1400c82f4  mov     eax, [rsp+0B8h+arg_8]
0x1400c82fb  mov     r14, [r15]
0x1400c82fe  inc     eax
0x1400c8300  mov     [rsp+0B8h+arg_0], 1
0x1400c8308  mov     [rsp+0B8h+arg_8], eax
0x1400c830f  test    r14, r14
0x1400c8312  jnz     loc_1400C819E
0x1400c8318  test    edi, edi
0x1400c831a  jns     short loc_1400C8330
0x1400c831c  cmp     edi, 0C000009Ah
0x1400c8322  jz      short loc_1400C8330
0x1400c8324  cmp     edi, 0C0000016h
0x1400c832a  jnz     loc_1400C85F1
0x1400c8330  lea     rdi, [rbx+28h]
0x1400c8334  test    rsi, rsi
0x1400c8337  jz      loc_1400C84B8
0x1400c833d  mov     eax, [rsp+0B8h+arg_8]
0x1400c8344  cmp     eax, cs:dword_14026914C
0x1400c834a  jb      loc_1400C84B8
0x1400c8350  mov     dl, [rbx+30h]; NewIrql
0x1400c8353  mov     rcx, rdi; SpinLock
0x1400c8356  call    cs:__imp_KeReleaseSpinLock
0x1400c835d  nop     dword ptr [rax+rax+00h]
0x1400c8362  mov     edx, [rsi+8]
0x1400c8365  xor     r9d, r9d
0x1400c8368  mov     rax, [rsi]
0x1400c836b  xor     r8d, r8d
0x1400c836e  lea     ecx, [rdx+100h]
0x1400c8374  not     rcx
0x1400c8377  mov     [rsp+0B8h+var_80], rcx
0x1400c837c  mov     [rsp+0B8h+var_88], edx
0x1400c8380  xor     edx, edx
0x1400c8382  mov     [rsi+10h], rcx
0x1400c8386  mov     rcx, rbp
0x1400c8389  mov     [rsp+0B8h+var_90], rax
0x1400c838e  mov     dword ptr [rsp+0B8h+var_98], 3
0x1400c8396  call    ?MsKmeAllocateIoRun@@YAPEAU_MS_IO_RUN@@PEAU_MSENV_IO_REQUEST@@PEAXPEATSmsBigIdentifier@@EW4_EMS_IO_RUN_FLAGS@@1K_J@Z; MsKmeAllocateIoRun(_MSENV_IO_REQUEST *,void *,SmsBigIdentifier *,uchar,_EMS_IO_RUN_FLAGS,void *,ulong,__int64)
0x1400c839b  mov     rdi, rax
0x1400c839e  test    rax, rax
0x1400c83a1  jz      loc_1400C8478
0x1400c83a7  lea     rax, ?LogWriteDoubleBufferWriteCompletion@@YAJPEAX0KJ0@Z; LogWriteDoubleBufferWriteCompletion(void *,void *,ulong,long,void *)
0x1400c83ae  mov     qword ptr [rdi+28h], 0
0x1400c83b6  mov     dl, 1; unsigned __int8
0x1400c83b8  mov     [rdi+20h], rax
0x1400c83bc  mov     rcx, rbp; struct _MSENV_IO_REQUEST *
0x1400c83bf  mov     qword ptr [rdi+30h], 0
0x1400c83c7  mov     qword ptr [rdi+38h], 0
0x1400c83cf  xor     r12d, r12d
0x1400c83d2  call    ?MsKmeGetRunCount@@YAKPEAU_MSENV_IO_REQUEST@@E@Z; MsKmeGetRunCount(_MSENV_IO_REQUEST *,uchar)
0x1400c83d7  cmp     eax, 1
0x1400c83da  jz      loc_1400C8478
0x1400c83e0  mov     edx, r12d; unsigned int
0x1400c83e3  mov     rcx, rbp; struct _MSENV_IO_REQUEST *
0x1400c83e6  call    ?MsKmeGetRun@@YAPEAU_MS_IO_RUN@@PEAU_MSENV_IO_REQUEST@@K@Z; MsKmeGetRun(_MSENV_IO_REQUEST *,ulong)
0x1400c83eb  cmp     dword ptr [rsi+18h], 0
0x1400c83ef  mov     r15, rax
0x1400c83f2  lea     r14, [rax+10h]
0x1400c83f6  jnz     short loc_1400C83FF
0x1400c83f8  mov     rcx, [r14]
0x1400c83fb  mov     [rsi+10h], rcx
0x1400c83ff  mov     edx, [rsi+0Ch]
0x1400c8402  mov     rcx, [rsi+10h]
0x1400c8406  add     rcx, rdx
0x1400c8409  cmp     [r14], rcx
0x1400c840c  jnz     short loc_1400C8478
0x1400c840e  mov     ecx, [rax+8]
0x1400c8411  mov     eax, [rsi+8]
0x1400c8414  sub     eax, edx
0x1400c8416  cmp     ecx, eax
0x1400c8418  ja      short loc_1400C8478
0x1400c841a  mov     r8d, ecx; Length
0x1400c841d  mov     rcx, [rsi]
0x1400c8420  add     rcx, rdx; Destination
0x1400c8423  mov     rdx, [r15]; Source
0x1400c8426  call    cs:__imp_RtlCopyMemoryNonTemporal
0x1400c842d  nop     dword ptr [rax+rax+00h]
0x1400c8432  mov     eax, [r15+8]
0x1400c8436  mov     r9d, 2
0x1400c843c  add     [rsi+0Ch], eax
0x1400c843f  xor     r8d, r8d
0x1400c8442  inc     dword ptr [rsi+18h]
0x1400c8445  mov     rdx, r15
0x1400c8448  mov     rax, [r14]
0x1400c844b  mov     rcx, rbp
0x1400c844e  mov     [rsp+0B8h+var_90], rax
0x1400c8453  mov     eax, [r15+8]
0x1400c8457  mov     dword ptr [rsp+0B8h+var_98], eax
0x1400c845b  call    ?MsKmeSetIoRun@@YAXPEAU_MSENV_IO_REQUEST@@PEAU_MS_IO_RUN@@EW4_EMS_IO_RUN_FLAGS@@K_J@Z; MsKmeSetIoRun(_MSENV_IO_REQUEST *,_MS_IO_RUN *,uchar,_EMS_IO_RUN_FLAGS,ulong,__int64)
0x1400c8460  mov     dl, 1; unsigned __int8
0x1400c8462  mov     rcx, rbp; struct _MSENV_IO_REQUEST *
0x1400c8465  inc     r12d
0x1400c8468  call    ?MsKmeGetRunCount@@YAKPEAU_MSENV_IO_REQUEST@@E@Z; MsKmeGetRunCount(_MSENV_IO_REQUEST *,uchar)
0x1400c846d  dec     eax
0x1400c846f  cmp     r12d, eax
0x1400c8472  jb      loc_1400C83E0
0x1400c8478  cmp     dword ptr [rsi+18h], 0
0x1400c847c  jbe     short loc_1400C84A2
0x1400c847e  mov     rax, [rsi+10h]
0x1400c8482  mov     r9d, 1
0x1400c8488  mov     [rsp+0B8h+var_90], rax
0x1400c848d  xor     r8d, r8d
0x1400c8490  mov     eax, [rsi+0Ch]
0x1400c8493  mov     rdx, rdi
0x1400c8496  mov     rcx, rbp
0x1400c8499  mov     dword ptr [rsp+0B8h+var_98], eax
0x1400c849d  call    ?MsKmeSetIoRun@@YAXPEAU_MSENV_IO_REQUEST@@PEAU_MS_IO_RUN@@EW4_EMS_IO_RUN_FLAGS@@K_J@Z; MsKmeSetIoRun(_MSENV_IO_REQUEST *,_MS_IO_RUN *,uchar,_EMS_IO_RUN_FLAGS,ulong,__int64)
0x1400c84a2  lea     rdi, [rbx+28h]
0x1400c84a6  mov     rcx, rdi; SpinLock
0x1400c84a9  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
  ... truncated ...
```
