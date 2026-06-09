# WofCreateOpenContext

- ea: `0x140033930`
- end: `0x140034733`
- name: `WofCreateOpenContext`
- size: `3587`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, __int64, int, char, char)`
- caller_count: `2`
- callee_count: `16`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400331d0`
- `0x140035118`

## callees

- `0x1400014d0`
- `0x14000a914`
- `0x14000e198`
- `0x14000e36c`
- `0x14000ed74`
- `0x140011640`
- `0x140022c28`
- `0x140032c00`
- `0x140032d28`
- `0x140033930`
- `0x140034fa0`
- `0x140035ed0`
- `0x140035f04`
- `0x14003603c`
- `0x140036670`
- `0x140036954`

## import_xrefs

- `ntoskrnl!ExReleaseRundownProtection` at `0x1400345a9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400345cc`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400345a9`
- `ntoskrnl!ExReleaseRundownProtection` at `0x1400345cc`
- `ntoskrnl!ExAcquireFastMutex` at `0x140033e9c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140033ed1`
- `ntoskrnl!ExAcquireFastMutex` at `0x140033e9c`
- `ntoskrnl!ExAcquireFastMutex` at `0x140033ed1`
- `ntoskrnl!ObfReferenceObject` at `0x1400341e1`
- `ntoskrnl!ObfReferenceObject` at `0x1400341e1`
- `ntoskrnl!ExReleaseFastMutex` at `0x140033ebc`
- `ntoskrnl!ExReleaseFastMutex` at `0x140033ee9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140033ebc`
- `ntoskrnl!ExReleaseFastMutex` at `0x140033ee9`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033aef`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033e69`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033f00`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140034038`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400340b4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140034204`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140034214`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003428c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003445a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003465e`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033aef`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033e69`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140033f00`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140034038`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x1400340b4`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140034204`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x140034214`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003428c`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003445a`
- `ntoskrnl!ExReleaseFastMutexUnsafe` at `0x14003465e`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033c0b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033e31`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033fd5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140034015`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003407d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140034118`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003463f`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033c0b`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033e31`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140033fd5`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140034015`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003407d`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x140034118`
- `ntoskrnl!ExAcquireFastMutexUnsafe` at `0x14003463f`
- `FLTMGR!FltDeleteStreamContext` at `0x140033acc`
- `FLTMGR!FltDeleteStreamContext` at `0x14003440a`
- `FLTMGR!FltDeleteStreamContext` at `0x140033acc`
- `FLTMGR!FltDeleteStreamContext` at `0x14003440a`
- `FLTMGR!FltRetrieveFileInfoOnCreateCompletion` at `0x140033a52`
- `FLTMGR!FltRetrieveFileInfoOnCreateCompletion` at `0x140033a52`
- `FLTMGR!FltEnlistInTransaction` at `0x1400345fc`
- `FLTMGR!FltEnlistInTransaction` at `0x1400345fc`
- `FLTMGR!FltGetStreamContext` at `0x140033993`
- `FLTMGR!FltGetStreamContext` at `0x140033993`
- `FLTMGR!FltReleaseContext` at `0x140033b3b`
- `FLTMGR!FltReleaseContext` at `0x140033bcd`
- `FLTMGR!FltReleaseContext` at `0x140033ddb`
- `FLTMGR!FltReleaseContext` at `0x140033deb`
- `FLTMGR!FltReleaseContext` at `0x140034224`
- `FLTMGR!FltReleaseContext` at `0x140034234`
- `FLTMGR!FltReleaseContext` at `0x14003425f`
- `FLTMGR!FltReleaseContext` at `0x14003461a`
- `FLTMGR!FltReleaseContext` at `0x14003462a`
- `FLTMGR!FltReleaseContext` at `0x14003466e`
- `FLTMGR!FltReleaseContext` at `0x14003467e`
- `FLTMGR!FltReleaseContext` at `0x140033b3b`
- `FLTMGR!FltReleaseContext` at `0x140033bcd`
- `FLTMGR!FltReleaseContext` at `0x140033ddb`
- `FLTMGR!FltReleaseContext` at `0x140033deb`
- `FLTMGR!FltReleaseContext` at `0x140034224`
- `FLTMGR!FltReleaseContext` at `0x140034234`
- `FLTMGR!FltReleaseContext` at `0x14003425f`
- `FLTMGR!FltReleaseContext` at `0x14003461a`
- `FLTMGR!FltReleaseContext` at `0x14003462a`
- `FLTMGR!FltReleaseContext` at `0x14003466e`
- `FLTMGR!FltReleaseContext` at `0x14003467e`

## pseudocode

```c
__int64 __fastcall WofCreateOpenContext(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        __int64 a5,
        int a6,
        char a7,
        char a8)
{
  __int64 result; // rax
  char v9; // r13
  __int64 v10; // r14
  char *v12; // r12
  __int64 v13; // rdx
  NTSTATUS StreamContext; // ebx
  int v15; // r9d
  int v16; // edi
  __int64 v17; // r13
  __int64 v18; // rcx
  __int64 v19; // rax
  __int64 v20; // r8
  __int64 v21; // rdx
  void (__fastcall *v22)(char *, __int64, _QWORD); // rax
  int v23; // edx
  int v24; // r8d
  char v25; // r13
  PFLT_CONTEXT v26; // rcx
  int HandleContext; // eax
  struct _FAST_MUTEX *v28; // rcx
  __int64 v29; // r8
  __int64 (__fastcall *v30)(__int64, char *, __int64, _QWORD); // r10
  int v31; // eax
  __int64 v32; // rcx
  void (__fastcall *v33)(char *, char *, _QWORD); // rax
  _QWORD *v34; // rcx
  char v35; // dl
  __int64 v36; // rdx
  int v37; // eax
  struct _FLT_INSTANCE *v38; // rcx
  __int64 v39; // r9
  __int64 v40; // rdx
  ULONG *v41; // rdx
  PFAST_MUTEX *v42; // rcx
  __int64 (__fastcall *v43)(__int64, char *, __int64, __int64); // r10
  int v44; // eax
  int v45; // ecx
  PFLT_CONTEXT v46; // rcx
  __int64 v47; // rax
  __int64 v48; // r9
  _QWORD *v49; // rdx
  _QWORD *v50; // rcx
  char *v51; // r8
  __int64 v52; // r9
  PFLT_CONTEXT v53; // rdx
  __int64 v54; // r8
  __int64 v55; // rdx
  _QWORD *v56; // rcx
  _QWORD *v57; // rax
  _DWORD *v58; // rdx
  __int64 v59; // rax
  unsigned int v60; // r9d
  __int64 v61; // r10
  void (__fastcall *v62)(char *, char *, _QWORD); // rax
  __int64 v63; // rax
  int v64; // edx
  int v65; // r8d
  __int64 (__fastcall *v66)(__int64, __int64, char *, char *, __int64); // r10
  NTSTATUS v67; // eax
  int v68; // ecx
  int v69; // eax
  __int64 v70; // r13
  __int64 v71; // [rsp+20h] [rbp-69h]
  PFLT_CONTEXT Context; // [rsp+50h] [rbp-39h] BYREF
  char v73; // [rsp+58h] [rbp-31h] BYREF
  char v74; // [rsp+59h] [rbp-30h]
  bool v75; // [rsp+5Ah] [rbp-2Fh]
  char v76; // [rsp+5Bh] [rbp-2Eh]
  PFLT_CONTEXT v77; // [rsp+60h] [rbp-29h] BYREF
  PFLT_CONTEXT TransactionContext; // [rsp+68h] [rbp-21h] BYREF
  __int64 v79; // [rsp+70h] [rbp-19h]
  __int64 v80; // [rsp+78h] [rbp-11h]
  ULONG *v81; // [rsp+80h] [rbp-9h]
  char v83; // [rsp+E0h] [rbp+57h]

  result = 0;
  v9 = a7;
  v10 = a3;
  Context = 0;
  v12 = 0;
  v77 = 0;
  v80 = 0;
  if ( a3 < 4 || a7 && !a8 )
  {
    StreamContext = FltGetStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), &Context);
    if ( StreamContext >= 0 )
      goto LABEL_3;
    v38 = *(struct _FLT_INSTANCE **)(a2 + 24);
    TransactionContext = 0;
    WofGetVolumeContext(v38);
    v12 = (char *)v77;
    if ( (int)WofFindOrCreateFileContext(
                *(PFLT_INSTANCE *)(a2 + 24),
                *(PFILE_OBJECT *)(a2 + 32),
                (__int64)&TransactionContext) < 0 )
    {
      FltReleaseContext(v12);
    }
    else
    {
      StreamContext = WofFindOrCreateStreamContext(
                        *(PFLT_INSTANCE *)(a2 + 24),
                        *(PFILE_OBJECT *)(a2 + 32),
                        TransactionContext,
                        (__int64)&Context);
      FltReleaseContext(v12);
      FltReleaseContext(TransactionContext);
      if ( StreamContext >= 0 )
      {
LABEL_3:
        v83 = 0;
        v76 = 0;
        if ( !a8 )
          goto LABEL_4;
        v44 = WofEnsureExtdFileContext(*(_QWORD *)Context);
        v26 = Context;
        StreamContext = v44;
        if ( v44 < 0 )
        {
LABEL_30:
          FltReleaseContext(v26);
          return (unsigned int)StreamContext;
        }
        WofEnsureExtdFileContext(*(_QWORD *)Context);
        ExAcquireFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
        v45 = *((_DWORD *)Context + 2) & 0xF000000;
        if ( v45 == 0x1000000 )
        {
          if ( (*((_DWORD *)Context + 2) & 4) != 0 )
            goto LABEL_73;
          StreamContext = WofInflateFile(a1, a2, Context, 0);
          if ( StreamContext == -1073740690 )
            StreamContext = WofMarkFileAsInflated(a2, Context);
          if ( StreamContext >= 0 )
            goto LABEL_73;
        }
        else
        {
          if ( v45 != 0x2000000 )
          {
LABEL_73:
            v76 = 1;
            ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)Context + 32LL));
            v46 = Context;
            v47 = *((unsigned int *)Context + 3);
            if ( (unsigned int)v47 < 4 )
            {
              (*((void (__fastcall **)(char *))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * v47 + 12))((char *)Context + 64);
              *((_DWORD *)Context + 3) = -1;
              v46 = Context;
            }
            ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v46 + 32LL));
LABEL_4:
            v16 = 0;
            v74 = 0;
            v12 = *(char **)(*(_QWORD *)Context + 8LL);
            if ( (*((_DWORD *)Context + 2) & 1) == 0 || a8 )
            {
              v29 = *(_QWORD *)(a2 + 32);
              v77 = *(PFLT_CONTEXT *)(v29 + 24);
              if ( WofBreakOnExternalFileOpen && !a8 )
                WofCheckForFilenameBreak(&WofBreakOnExternalFileOpen, v13, v29 + 88);
              if ( !a7 )
              {
                v43 = (__int64 (__fastcall *)(__int64, char *, __int64, __int64))*((_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                 + 53 * v10
                                                                                 + 22);
                if ( v43 )
                {
                  v71 = a5;
                  StreamContext = v43(a1, &v12[*(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 106 * v10 + 5)], a2, a4);
                  if ( StreamContext < 0 )
                    goto LABEL_24;
                }
              }
              ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)Context + 32LL));
              if ( a8 )
              {
                v58 = Context;
                v83 = 1;
                v59 = *((unsigned int *)Context + 3);
                v60 = *((_DWORD *)Context + 4);
                LODWORD(TransactionContext) = v60;
                if ( (unsigned int)v59 < 4 )
                {
                  v61 = 424 * v59;
                  v62 = (void (__fastcall *)(char *, char *, _QWORD))*((_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                     + 53 * v59
                                                                     + 25);
                  if ( v62 )
                  {
                    if ( v60 && (*((_DWORD *)Context + 2) & 4) == 0 )
                    {
                      v62(
                        &v12[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v61 + 20)],
                        (char *)Context + 64,
                        v60);
                      v58 = Context;
                    }
                  }
                }
                v63 = (unsigned int)v58[3];
                if ( (unsigned int)v63 < 4 && (_DWORD)v10 != (_DWORD)v63 )
                {
                  (*((void (__fastcall **)(_DWORD *))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * v63 + 12))(v58 + 16);
                  v58 = Context;
                }
                v58[2] &= ~1u;
                if ( *((_DWORD *)Context + 3) != (_DWORD)v10 )
                {
                  *((_DWORD *)Context + 3) = v10;
                  StreamContext = (*((__int64 (__fastcall **)(char *))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                   + 53 * v10
                                   + 19))((char *)Context + 64);
                  if ( StreamContext < 0 )
                  {
                    *((_DWORD *)Context + 3) = -1;
                    FltDeleteStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), 0);
                    v83 = 0;
                    if ( WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v64) = 2;
                      WPP_RECORDER_SF_qd(
                        WPP_GLOBAL_Control->DeviceExtension,
                        v64,
                        v65,
                        18,
                        v71,
                        (char)Context,
                        StreamContext);
                    }
                    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)Context + 32LL));
                    goto LABEL_24;
                  }
                }
              }
              else
              {
                LODWORD(TransactionContext) = 0;
              }
              if ( (*((_DWORD *)Context + 2) & 1) == 0 )
              {
                if ( a7 )
                {
                  *((_DWORD *)Context + 2) &= 0xF0FFFFFF;
                  *((_DWORD *)Context + 2) |= 0x4000006u;
                }
                else
                {
                  v79 = 424 * v10;
                  v30 = (__int64 (__fastcall *)(__int64, char *, __int64, _QWORD))*((_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                  + 53 * v10
                                                                                  + 23);
                  v81 = &WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 106 * v10 + 5;
                  v71 = a4;
                  v31 = v30(a1, &v12[*v81], a2, *((_QWORD *)v77 + 4));
                  StreamContext = v31;
                  v16 = v31;
                  if ( v31 < 0 || v31 == 51314689 )
                  {
                    FltDeleteStreamContext(*(PFLT_INSTANCE *)(a2 + 24), *(PFILE_OBJECT *)(a2 + 32), 0);
                    v83 = 0;
                    if ( StreamContext < 0 && WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
                    {
                      LOBYTE(v23) = 2;
                      WPP_RECORDER_SF_qd(
                        WPP_GLOBAL_Control->DeviceExtension,
                        v23,
                        v24,
                        19,
                        a4,
                        (char)Context,
                        StreamContext);
                    }
                    ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)Context + 32LL));
LABEL_23:
                    if ( StreamContext >= 0 )
                    {
                      if ( !v16 || (StreamContext = v16, v16 >= 0) )
                      {
LABEL_77:
                        if ( StreamContext != 51314689 && !v9 )
                        {
                          v25 = v83;
                          goto LABEL_80;
                        }
LABEL_26:
                        v25 = v83;
                        if ( !v83 )
                        {
LABEL_27:
                          if ( v80 )
                          {
                            LOBYTE(v71) = a8;
                            (*((void (__fastcall **)(char *, __int64, __int64, __int64, __int64, __int64))&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                             + 53 * v10
                             + 21))(
                              &v12[*(&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 106 * v10 + 5)],
                              a2,
                              a4,
                              a5,
                              v71,
                              v80);
                          }
                          v26 = Context;
                          goto LABEL_30;
                        }
LABEL_80:
                        ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)Context + 32LL));
                        if ( (unsigned int)v10 < 4 )
                        {
                          v77 = (PFLT_CONTEXT)(424 * v10);
                          if ( *((_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * v10 + 26) )
                          {
                            if ( v25 )
                            {
                              v69 = WofMarkProviderHandle(a1, a2, Context, 0);
                              v70 = (__int64)v77;
                              if ( v69 >= 0 )
                                (*(void (__fastcall **)(char *, char *, __int64))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                + (_QWORD)v77
                                                                                + 200))(
                                  &v12[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                       + (_QWORD)v77
                                                       + 20)],
                                  (char *)Context + 64,
                                  1);
                            }
                            else
                            {
                              v70 = 424 * v10;
                            }
                            LOBYTE(v48) = 1;
                            if ( (int)WofMarkProviderHandle(a1, a2, Context, v48) >= 0 )
                              (*(void (__fastcall **)(char *, char *, __int64))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                              + v70
                                                                              + 208))(
                                &v12[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v70 + 20)],
                                (char *)Context + 64,
                                1);
                          }
                        }
                        ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)Context + 32LL));
                        goto LABEL_27;
                      }
                    }
LABEL_24:
                    if ( !v76 )
                      goto LABEL_25;
                    goto LABEL_100;
                  }
                  *((_DWORD *)Context + 3) = v10;
                  *((_DWORD *)Context + 2) |= 1u;
                  v32 = v79;
                  v33 = *(void (__fastcall **)(char *, char *, _QWORD))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                      + v79
                                                                      + 208);
                  if ( v33 && (_DWORD)TransactionContext )
                  {
                    v33(&v12[*v81], (char *)Context + 64, (unsigned int)TransactionContext);
                    v32 = v79;
                  }
                  if ( !a8
                    || (unsigned int)v10 >= 4
                    || !*((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v32)
                    || !*(_QWORD *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v32 + 120) )
                  {
                    *((_DWORD *)Context + 2) &= 0xF0FFFFFB;
                    *((_DWORD *)Context + 2) |= 0x1000000u;
                  }
                  v34 = *(_QWORD **)(*(_QWORD *)(a2 + 32) + 40LL);
                  if ( v34 && *v34 )
                    v74 = 1;
                }
              }
              v35 = *((_BYTE *)v77 + 6);
              if ( (v35 & 4) != 0 )
              {
                if ( (*((_BYTE *)v77 + 4) & 0x40) != 0 )
                {
                  ExAcquireFastMutex(*((PFAST_MUTEX *)v77 + 6));
                  v42 = (PFAST_MUTEX *)v77;
                  *((_BYTE *)v77 + 6) &= ~4u;
                  ExReleaseFastMutex(v42[6]);
                }
                else
                {
                  *((_BYTE *)v77 + 6) = v35 & 0xFB;
                }
              }
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)Context + 32LL));
            }
            v75 = 0;
            if ( (unsigned int)v10 < 4 )
            {
              v17 = 424 * v10;
              if ( *((_QWORD *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + 53 * v10 + 29) )
              {
                v73 = 0;
                v77 = 0;
                if ( (int)WofIsDataInFilesystemEx(Context, a2, &v73, &v77) >= 0 && !v73 )
                {
                  v66 = *(__int64 (__fastcall **)(__int64, __int64, char *, char *, __int64))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                                            + v17
                                                                                            + 232);
                  if ( v66 )
                  {
                    LODWORD(v71) = a6;
                    StreamContext = v66(
                                      a1,
                                      a2,
                                      &v12[*(unsigned int *)((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v17 + 20)],
                                      (char *)Context + 64,
                                      v71);
                    v75 = StreamContext == 51314693;
                    if ( StreamContext < 0 )
                    {
                      if ( v77 )
                        ExReleaseRundownProtection((PEX_RUNDOWN_REF)v77);
                      v9 = a7;
                      goto LABEL_24;
                    }
                  }
                }
                if ( v77 )
                  ExReleaseRundownProtection((PEX_RUNDOWN_REF)v77);
              }
              v9 = a7;
            }
            if ( !*(_QWORD *)(a2 + 40) )
            {
LABEL_10:
              if ( v74 )
              {
                if ( !a8 )
                {
                  LOBYTE(v15) = 1;
                  StreamContext = WofFlushFile(a1, *(_QWORD *)(a2 + 24), *(_QWORD *)(a2 + 32), v15, 0);
                  if ( StreamContext < 0 )
                  {
                    *(_DWORD *)(a1 + 24) = StreamContext;
                    goto LABEL_24;
                  }
                }
              }
              if ( !v9 && !a8 )
              {
                v18 = *(_QWORD *)(a2 + 8);
                LODWORD(TransactionContext) = 0;
                v19 = FltRetrieveFileInfoOnCreateCompletion(v18, a1, 1, &TransactionContext);
                v79 = v19;
                v20 = v19;
                if ( v19 )
                {
                  *(_DWORD *)(v19 + 60) = 0;
                  v36 = *((_DWORD *)Context + 2) >> 1;
                  LOBYTE(v36) = (*((_DWORD *)Context + 2) & 2) != 0;
                  v37 = WofSanitizeAttributes(*(unsigned int *)(v19 + 56), v36, v19);
                  *(_DWORD *)(v20 + 56) = v37;
                }
                if ( v75
                  || (v21 = 424 * v10, (unsigned int)v10 < 4)
                  && (*(ULONG *)((_BYTE *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels + v21 + 24) & a6) != 0 )
                {
                  StreamContext = WofEnsureExtdFileContext(*(_QWORD *)Context);
                  if ( StreamContext < 0 )
                    goto LABEL_24;
                  WofEnsureExtdFileContext(*(_QWORD *)Context);
                  ExAcquireFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
                  if ( (*((_DWORD *)Context + 2) & 4) == 0 )
                  {
                    LOBYTE(v39) = 1;
                    StreamContext = WofInflateFile(a1, a2, Context, v39);
                  }
                  ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
                  if ( v79 )
                  {
                    v40 = *(_QWORD *)(*(_QWORD *)(a2 + 32) + 24LL);
                    v81 = (ULONG *)v40;
                    if ( (*(_BYTE *)(v40 + 4) & 0x40) != 0 )
                    {
                      ExAcquireFastMutex(*(PFAST_MUTEX *)(v40 + 48));
                      v41 = v81;
                      *(_QWORD *)(v79 + 40) = *((_QWORD *)v81 + 3);
                      ExReleaseFastMutex(*((PFAST_MUTEX *)v41 + 6));
                    }
                    else
                    {
                      *(_QWORD *)(v79 + 40) = *(_QWORD *)(v40 + 24);
                    }
                  }
                }
                else if ( v20 )
                {
                  v22 = *(void (__fastcall **)(char *, __int64, _QWORD))((char *)&WPP_MAIN_CB.Queue.Wcb.NumberOfChannels
                                                                       + v21
                                                                       + 328);
                  if ( v22 )
                    v22((char *)Context + 64, v20 + 40, 0);
                }
              }
              goto LABEL_23;
            }
            v77 = 0;
            TransactionContext = 0;
            StreamContext = WofEnsureExtdFileContext(*(_QWORD *)Context);
            if ( StreamContext < 0 )
              goto LABEL_24;
            StreamContext = WofFindOrCreateTransactionContext(a1, *(_QWORD *)(a2 + 40), &TransactionContext);
            if ( StreamContext < 0 )
              goto LABEL_24;
            HandleContext = WofFindOrCreateHandleContext(
                              *(PFLT_INSTANCE *)(*(_QWORD *)(a1 + 16) + 16LL),
                              *(PFILE_OBJECT *)(*(_QWORD *)(a1 + 16) + 8LL));
            v28 = (struct _FAST_MUTEX *)TransactionContext;
            StreamContext = HandleContext;
            if ( HandleContext < 0 )
            {
              FltReleaseContext(TransactionContext);
              goto LABEL_24;
            }
            *(_DWORD *)v77 |= 2u;
            if ( (v28[1].Count & 1) == 0 )
            {
              v67 = FltEnlistInTransaction(*(PFLT_INSTANCE *)(a2 + 24), *(PKTRANSACTION *)(a2 + 40), v28, 0xCu);
              StreamContext = 0;
              if ( v67 != -1071906789 )
                StreamContext = v67;
              if ( StreamContext < 0 )
              {
                FltReleaseContext(v77);
                FltReleaseContext(TransactionContext);
                goto LABEL_24;
              }
              v28 = (struct _FAST_MUTEX *)TransactionContext;
            }
            ExAcquireFastMutexUnsafe(v28);
            v68 = *((_DWORD *)TransactionContext + 14);
            if ( (v68 & 2) != 0 )
            {
              ExReleaseFastMutexUnsafe((PFAST_MUTEX)TransactionContext);
              FltReleaseContext(v77);
              FltReleaseContext(TransactionContext);
              StreamContext = -1072103421;
              goto LABEL_24;
            }
            *((_DWORD *)TransactionContext + 14) = v68 | 1;
            ExAcquireFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)Context + 32LL));
            v49 = v77;
            v50 = TransactionContext;
            v51 = (char *)TransactionContext + 80;
            *((_QWORD *)v77 + 1) = *(_QWORD *)(a2 + 40);
            v49[2] = v50;
            v52 = *(_QWORD *)v51;
            if ( *(char **)(*(_QWORD *)v51 + 8LL) == v51 )
            {
              v49[3] = v52;
              v49[4] = v51;
              *(_QWORD *)(v52 + 8) = v49 + 3;
              *(_QWORD *)v51 = v49 + 3;
              if ( (a6 & 6) == 0 )
                goto LABEL_92;
              v53 = Context;
              v54 = *(_QWORD *)(*(_QWORD *)Context + 16LL);
              if ( *(_QWORD *)(v54 + 56) || (*((_DWORD *)Context + 2) & 0xF000000) != 0x1000000 )
                goto LABEL_93;
              *(_QWORD *)(v54 + 56) = *(_QWORD *)(a2 + 40);
              if ( v9 )
              {
LABEL_92:
                v53 = Context;
LABEL_93:
                ExReleaseFastMutexUnsafe((PFAST_MUTEX)(*(_QWORD *)v53 + 32LL));
                ExReleaseFastMutexUnsafe((PFAST_MUTEX)TransactionContext);
                FltReleaseContext(v77);
                FltReleaseContext(TransactionContext);
                goto LABEL_10;
              }
              v55 = v50[8];
              v56 = v50 + 8;
              if ( *(_QWORD **)(v55 + 8) == v56 )
              {
                v57 = Context;
                *((_QWORD *)Context + 4) = v55;
                v57 += 4;
                v57[1] = v56;
                *(_QWORD *)(v55 + 8) = v57;
                *v56 = v57;
                *((_DWORD *)Context + 2) &= 0xF0FFFFFF;
                *((_DWORD *)Context + 2) |= 0x2000000u;
                ObfReferenceObject(*(PVOID *)(a2 + 32));
                *((_QWORD *)Context + 3) = *(_QWORD *)(a2 + 32);
                goto LABEL_92;
              }
            }
            __fastfail(3u);
          }
          StreamContext = -1072103423;
        }
LABEL_100:
        ExReleaseFastMutexUnsafe(*(PFAST_MUTEX *)(*(_QWORD *)Context + 16LL));
LABEL_25:
        if ( StreamContext < 0 )
          goto LABEL_26;
        goto LABEL_77;
      }
    }
    return 3221225506LL;
  }
  return result;
}

```

## disassembly

```asm
0x140033930  mov     [rsp-8+arg_18], r9
0x140033935  mov     [rsp-8+arg_0], rcx
0x14003393a  push    rbp
0x14003393b  push    rsi
0x14003393c  push    rdi
0x14003393d  push    r12
0x14003393f  push    r13
0x140033941  push    r14
0x140033943  push    r15
0x140033945  lea     rbp, [rsp-7]
0x14003394a  sub     rsp, 90h
0x140033951  movzx   r15d, [rbp+37h+arg_38]
0x140033956  xor     eax, eax
0x140033958  movzx   r13d, [rbp+37h+arg_30]
0x14003395d  mov     rdi, r9
0x140033960  mov     r14d, r8d
0x140033963  mov     rsi, rdx
0x140033966  mov     [rbp+37h+Context], rax
0x14003396a  mov     r12d, eax
0x14003396d  mov     [rbp+37h+var_60], rax
0x140033971  mov     [rbp+37h+var_48], rax
0x140033975  cmp     r8d, 4
0x140033979  jnb     loc_140034245
0x14003397f  mov     rdx, [rdx+20h]; FileObject
0x140033983  lea     r8, [rbp+37h+Context]; Context
0x140033987  mov     rcx, [rsi+18h]; Instance
0x14003398b  mov     [rsp+0C0h+arg_8], rbx
0x140033993  call    cs:__imp_FltGetStreamContext
0x14003399a  nop     dword ptr [rax+rax+00h]
0x14003399f  mov     ebx, eax
0x1400339a1  test    eax, eax
0x1400339a3  js      loc_140033D7C
0x1400339a9  mov     [rbp+37h+arg_10], 0
0x1400339ad  lea     rdi, WPP_MAIN_CB.Queue+10h
0x1400339b4  mov     [rbp+37h+var_65], 0
0x1400339b8  test    r15b, r15b
0x1400339bb  jnz     loc_140033FA8
0x1400339c1  mov     rcx, [rbp+37h+Context]
0x1400339c5  xor     edi, edi
0x1400339c7  mov     [rbp+37h+var_67], dil
0x1400339cb  mov     rax, [rcx]
0x1400339ce  mov     r12, [rax+8]
0x1400339d2  mov     eax, [rcx+8]
0x1400339d5  test    al, 1
0x1400339d7  jz      loc_140033BDE
0x1400339dd  test    r15b, r15b
0x1400339e0  jnz     loc_140033BDE
0x1400339e6  mov     [rbp+37h+var_66], 0
0x1400339ea  cmp     r14d, 4
0x1400339ee  jnb     short loc_140033A12
0x1400339f0  imul    r13, r14, 1A8h
0x1400339f7  lea     rax, WPP_MAIN_CB.Queue+10h
0x1400339fe  cmp     qword ptr [rax+r13+0E8h], 0
0x140033a07  jnz     loc_14003452D
0x140033a0d  movzx   r13d, [rbp+37h+arg_30]
0x140033a12  cmp     qword ptr [rsi+28h], 0
0x140033a17  jnz     loc_140033B65
0x140033a1d  cmp     [rbp+37h+var_67], 0
0x140033a21  jnz     loc_140033F70
0x140033a27  test    r13b, r13b
0x140033a2a  jnz     loc_140033AFB
0x140033a30  test    r15b, r15b
0x140033a33  jnz     loc_140033AFB
0x140033a39  mov     rdx, [rbp+37h+arg_0]
0x140033a3d  lea     r9, [rbp+37h+TransactionContext]
0x140033a41  mov     rcx, [rsi+8]
0x140033a45  mov     r8d, 1
0x140033a4b  mov     dword ptr [rbp+37h+TransactionContext], 0
0x140033a52  call    cs:__imp_FltRetrieveFileInfoOnCreateCompletion
0x140033a59  nop     dword ptr [rax+rax+00h]
0x140033a5e  mov     [rbp+37h+var_50], rax
0x140033a62  mov     r8, rax
0x140033a65  test    rax, rax
0x140033a68  jnz     loc_140033D58
0x140033a6e  cmp     [rbp+37h+var_66], 0
0x140033a72  jnz     loc_140033E04
0x140033a78  imul    rdx, r14, 1A8h
0x140033a7f  lea     rcx, WPP_MAIN_CB.Queue+10h
0x140033a86  cmp     r14d, 4
0x140033a8a  jnb     short loc_140033A99
0x140033a8c  mov     eax, [rdx+rcx+18h]
0x140033a90  test    [rbp+37h+arg_28], eax
0x140033a93  jnz     loc_140033E04
0x140033a99  test    r8, r8
0x140033a9c  jz      short loc_140033AFB
0x140033a9e  mov     rax, [rdx+rcx+148h]
0x140033aa6  test    rax, rax
0x140033aa9  jz      short loc_140033AFB
0x140033aab  mov     rcx, [rbp+37h+Context]
0x140033aaf  lea     rdx, [r8+28h]
0x140033ab3  add     rcx, 40h ; '@'
0x140033ab7  xor     r8d, r8d
0x140033aba  call    _guard_dispatch_icall
0x140033abf  jmp     short loc_140033AFB
0x140033ac1  mov     rdx, [rsi+20h]; FileObject
0x140033ac5  xor     r8d, r8d; OldContext
0x140033ac8  mov     rcx, [rsi+18h]; Instance
0x140033acc  call    cs:__imp_FltDeleteStreamContext
0x140033ad3  nop     dword ptr [rax+rax+00h]
0x140033ad8  mov     [rbp+37h+arg_10], 0
0x140033adc  test    ebx, ebx
0x140033ade  js      loc_1400344EF
0x140033ae4  mov     rax, [rbp+37h+Context]
0x140033ae8  mov     rcx, [rax]
0x140033aeb  add     rcx, 20h ; ' '; FastMutex
0x140033aef  call    cs:__imp_ExReleaseFastMutexUnsafe
0x140033af6  nop     dword ptr [rax+rax+00h]
0x140033afb  test    ebx, ebx
0x140033afd  jns     loc_1400340FA
0x140033b03  cmp     [rbp+37h+var_65], 0
0x140033b07  jnz     loc_14003427A
0x140033b0d  lea     rdi, WPP_MAIN_CB.Queue+10h
0x140033b14  test    ebx, ebx
0x140033b16  jns     loc_140034058
0x140033b1c  movzx   r13d, [rbp+37h+arg_10]
0x140033b21  test    r13b, r13b
0x140033b24  jnz     loc_140034072
0x140033b2a  mov     r8, [rbp+37h+var_48]
0x140033b2e  test    r8, r8
0x140033b31  jnz     loc_1400340C5
0x140033b37  mov     rcx, [rbp+37h+Context]; Context
0x140033b3b  call    cs:__imp_FltReleaseContext
0x140033b42  nop     dword ptr [rax+rax+00h]
0x140033b47  mov     eax, ebx
0x140033b49  mov     rbx, [rsp+0C0h+arg_8]
0x140033b51  add     rsp, 90h
0x140033b58  pop     r15
0x140033b5a  pop     r14
0x140033b5c  pop     r13
0x140033b5e  pop     r12
0x140033b60  pop     rdi
0x140033b61  pop     rsi
0x140033b62  pop     rbp
0x140033b63  retn
0x140033b65  mov     rcx, [rbp+37h+Context]
0x140033b69  mov     [rbp+37h+var_60], 0
0x140033b71  mov     [rbp+37h+TransactionContext], 0
0x140033b79  mov     rcx, [rcx]
0x140033b7c  call    WofEnsureExtdFileContext
0x140033b81  mov     ebx, eax
0x140033b83  test    eax, eax
0x140033b85  js      loc_140033B03
0x140033b8b  mov     rdx, [rsi+28h]
0x140033b8f  lea     r8, [rbp+37h+TransactionContext]
0x140033b93  mov     rcx, [rbp+37h+arg_0]
0x140033b97  call    WofFindOrCreateTransactionContext
0x140033b9c  mov     ebx, eax
0x140033b9e  test    eax, eax
0x140033ba0  js      loc_140033B03
0x140033ba6  mov     rax, [rbp+37h+arg_0]
0x140033baa  lea     r9, [rbp+37h+var_60]
0x140033bae  mov     rcx, [rax+10h]
0x140033bb2  mov     rdx, [rcx+8]; FileObject
0x140033bb6  mov     rcx, [rcx+10h]; Instance
0x140033bba  call    WofFindOrCreateHandleContext
0x140033bbf  mov     rcx, [rbp+37h+TransactionContext]; Context
0x140033bc3  mov     ebx, eax
0x140033bc5  test    eax, eax
0x140033bc7  jns     loc_1400345DD
0x140033bcd  call    cs:__imp_FltReleaseContext
0x140033bd4  nop     dword ptr [rax+rax+00h]
0x140033bd9  jmp     loc_140033B03
0x140033bde  cmp     cs:WofBreakOnExternalFileOpen, di
0x140033be5  mov     r8, [rsi+20h]
0x140033be9  mov     rax, [r8+18h]
0x140033bed  mov     [rbp+37h+var_60], rax
0x140033bf1  jnz     loc_140034309
0x140033bf7  test    r13b, r13b
0x140033bfa  jz      loc_140033F11
0x140033c00  mov     rax, [rbp+37h+Context]
0x140033c04  mov     rcx, [rax]
0x140033c07  add     rcx, 20h ; ' '; FastMutex
0x140033c0b  call    cs:__imp_ExAcquireFastMutexUnsafe
0x140033c12  nop     dword ptr [rax+rax+00h]
0x140033c17  test    r15b, r15b
0x140033c1a  jnz     loc_140034327
0x140033c20  xor     r9d, r9d
0x140033c23  mov     dword ptr [rbp+37h+TransactionContext], r9d
0x140033c27  lea     r8, WPP_MAIN_CB.Queue+10h
0x140033c2e  mov     rcx, [rbp+37h+Context]
0x140033c32  mov     eax, [rcx+8]
0x140033c35  test    al, 1
0x140033c37  jnz     loc_140033D32
0x140033c3d  test    r13b, r13b
0x140033c40  jnz     loc_14003446B
0x140033c46  mov     rax, [rbp+37h+Context]
0x140033c4a  add     rax, 40h ; '@'
0x140033c4e  mov     [rsp+0C0h+var_80], rax
0x140033c53  lea     rax, [rbp+37h+var_48]
0x140033c57  mov     [rsp+0C0h+var_88], rax
0x140033c5c  mov     rax, [rbp+37h+arg_20]
0x140033c60  imul    rcx, r14, 1A8h
0x140033c67  mov     byte ptr [rsp+0C0h+var_90], 1
0x140033c6c  mov     [rsp+0C0h+var_98], rax
0x140033c71  mov     rax, [rbp+37h+arg_18]
0x140033c75  mov     [rbp+37h+var_50], rcx
0x140033c79  mov     r10, [rcx+r8+0B8h]
0x140033c81  lea     rdx, [rcx+14h]
0x140033c85  mov     rcx, [rbp+37h+var_60]
0x140033c89  add     rdx, r8
0x140033c8c  mov     [rbp+37h+var_40], rdx
0x140033c90  mov     r8, rsi
0x140033c93  mov     [rsp+0C0h+var_A0], rax
0x140033c98  mov     rax, r10
0x140033c9b  mov     edx, [rdx]
0x140033c9d  mov     r9, [rcx+20h]
0x140033ca1  add     rdx, r12
0x140033ca4  mov     rcx, [rbp+37h+arg_0]
0x140033ca8  call    _guard_dispatch_icall
0x140033cad  mov     ebx, eax
0x140033caf  mov     edi, eax
0x140033cb1  test    eax, eax
0x140033cb3  js      loc_140033AC1
0x140033cb9  cmp     eax, 30F0001h
0x140033cbe  jz      loc_140033AC1
0x140033cc4  mov     rax, [rbp+37h+Context]
0x140033cc8  lea     r8, WPP_MAIN_CB.Queue+10h
0x140033ccf  mov     [rax+0Ch], r14d
0x140033cd3  mov     rcx, [rbp+37h+Context]
0x140033cd7  mov     eax, [rcx+8]
0x140033cda  or      eax, 1
0x140033cdd  mov     [rcx+8], eax
0x140033ce0  mov     rcx, [rbp+37h+var_50]
0x140033ce4  mov     rax, [rcx+r8+0D0h]
0x140033cec  test    rax, rax
0x140033cef  jnz     loc_14003448A
0x140033cf5  test    r15b, r15b
0x140033cf8  jnz     loc_1400344C0
0x140033cfe  mov     rcx, [rbp+37h+Context]
0x140033d02  mov     eax, [rcx+8]
0x140033d05  and     eax, 0F0FFFFFBh
0x140033d0a  mov     [rcx+8], eax
0x140033d0d  mov     rcx, [rbp+37h+Context]
0x140033d11  mov     eax, [rcx+8]
0x140033d14  bts     eax, 18h
0x140033d18  mov     [rcx+8], eax
0x140033d1b  mov     rax, [rsi+20h]
0x140033d1f  mov     rcx, [rax+28h]
0x140033d23  test    rcx, rcx
0x140033d26  jz      short loc_140033D32
0x140033d28  cmp     qword ptr [rcx], 0
0x140033d2c  jnz     loc_1400344E6
0x140033d32  mov     rcx, [rbp+37h+var_60]
0x140033d36  movzx   edx, byte ptr [rcx+6]
0x140033d3a  test    dl, 4
0x140033d3d  jz      loc_140033EF5
0x140033d43  test    byte ptr [rcx+4], 40h
0x140033d47  jnz     loc_140033ECD
0x140033d4d  and     dl, 0FBh
0x140033d50  mov     [rcx+6], dl
0x140033d53  jmp     loc_140033EF5
0x140033d58  mov     dword ptr [rax+3Ch], 0
0x140033d5f  mov     rcx, [rbp+37h+Context]
0x140033d63  mov     edx, [rcx+8]
0x140033d66  mov     ecx, [rax+38h]
0x140033d69  shr     edx, 1
0x140033d6b  and     dl, 1
0x140033d6e  call    WofSanitizeAttributes
0x140033d73  mov     [r8+38h], eax
0x140033d77  jmp     loc_140033A6E
0x140033d7c  mov     rcx, [rsi+18h]; Instance
0x140033d80  lea     rdx, [rbp+37h+var_60]
0x140033d84  mov     [rbp+37h+TransactionContext], r12
0x140033d88  call    WofGetVolumeContext
0x140033d8d  mov     r12, [rbp+37h+var_60]
0x140033d91  lea     rax, [rbp+37h+TransactionContext]
0x140033d95  mov     rdx, [rsi+20h]; FileObject
0x140033d99  test    rdi, rdi
0x140033d9c  mov     rcx, [rsi+18h]; Instance
0x140033da0  mov     r8, r12
0x140033da3  setz    r9b
0x140033da7  mov     [rsp+0C0h+var_A0], rax; __int64
0x140033dac  call    WofFindOrCreateFileContext
0x140033db1  test    eax, eax
0x140033db3  js      loc_14003425C
0x140033db9  mov     r8, [rbp+37h+TransactionContext]; Context
0x140033dbd  lea     rax, [rbp+37h+Context]
0x140033dc1  mov     rdx, [rsi+20h]; FileObject
0x140033dc5  mov     r9d, r14d
0x140033dc8  mov     rcx, [rsi+18h]; Instance
0x140033dcc  mov     [rsp+0C0h+var_A0], rax; __int64
0x140033dd1  call    WofFindOrCreateStreamContext
0x140033dd6  mov     rcx, r12; Context
0x140033dd9  mov     ebx, eax
0x140033ddb  call    cs:__imp_FltReleaseContext
0x140033de2  nop     dword ptr [rax+rax+00h]
0x140033de7  mov     rcx, [rbp+37h+TransactionContext]; Context
0x140033deb  call    cs:__imp_FltReleaseContext
0x140033df2  nop     dword ptr [rax+rax+00h]
0x140033df7  test    ebx, ebx
0x140033df9  jns     loc_1400339A9
0x140033dff  jmp     loc_14003426B
0x140033e04  mov     rcx, [rbp+37h+Context]
0x140033e08  mov     rcx, [rcx]
0x140033e0b  call    WofEnsureExtdFileContext
0x140033e10  mov     ebx, eax
0x140033e12  test    eax, eax
0x140033e14  js      loc_140033B03
0x140033e1a  mov     rcx, [rbp+37h+Context]
0x140033e1e  mov     rcx, [rcx]
  ... truncated ...
```
