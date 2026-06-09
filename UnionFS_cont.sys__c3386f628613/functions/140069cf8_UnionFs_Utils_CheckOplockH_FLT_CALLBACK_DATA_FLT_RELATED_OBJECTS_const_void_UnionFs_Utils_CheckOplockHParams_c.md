# UnionFs::Utils::CheckOplockH(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,void * &,UnionFs::Utils::CheckOplockHParams const &,UnionFs::StackEventTracer &)

- ea: `0x140069cf8`
- end: `0x140069ee6`
- name: `?CheckOplockH@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAPEAXAEBUCheckOplockHParams@12@AEAVStackEventTracer@2@@Z`
- size: `494`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, struct _FLT_CALLBACK_DATA *@<rdx>, const struct _FLT_RELATED_OBJECTS *@<r8>, void **@<r9>, const struct UnionFs::Utils::CheckOplockHParams *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400114c4`
- `0x140058fbc`

## callees

- `0x140056a50`
- `0x140056afc`
- `0x140069348`
- `0x140069cf8`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069d8e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069e92`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069ecd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069d8e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069e92`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069ecd`
- `FLTMGR!FltOplockBreakH` at `0x140069e0f`
- `FLTMGR!FltOplockBreakH` at `0x140069e0f`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069d71`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069e75`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069eb0`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069d71`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069e75`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069eb0`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CheckOplockH(
        PFLT_CALLBACK_DATA CallbackData,
        struct _FLT_CALLBACK_DATA *a2,
        struct _FLT_RELATED_OBJECTS *a3,
        unsigned int **a4,
        const struct UnionFs::Utils::CheckOplockHParams *a5)
{
  int v8; // edi
  PVOID v9; // rbx
  struct _FLT_DEFERRED_IO_WORKITEM *v10; // rcx
  unsigned int v12; // r8d
  _QWORD *v13; // rdi
  enum _FLT_PREOP_CALLBACK_STATUS v14; // eax
  NTSTATUS Status; // ebx
  struct _FLT_DEFERRED_IO_WORKITEM *v16; // rcx
  struct _FLT_DEFERRED_IO_WORKITEM *v17; // rcx
  const char *PrePostCallbackDataRoutine; // [rsp+28h] [rbp-60h]
  const char *PrePostCallbackDataRoutinea; // [rsp+28h] [rbp-60h]
  PVOID Entry; // [rsp+50h] [rbp-38h] BYREF

  Entry = 0;
  v8 = UnionFs::Utils::CheckOplockContext::AllocAndInit((__int64)a2, (_QWORD **)&Entry, (int)a5);
  if ( v8 >= 0 )
  {
    v12 = (_DWORD)a4[2] & 0x7FFFFFFF;
    v13 = Entry;
    if ( UnionFs::Flt_OplockBreakH2 )
      v14 = UnionFs::Flt_OplockBreakH2(
              (void **)a3,
              CallbackData,
              v12,
              Entry,
              UnionFs::Utils::CheckOplockComplete,
              UnionFs::Utils::OplockPrePostCallbackData,
              *a4,
              (unsigned __int16 *)a4[1]);
    else
      v14 = FltOplockBreakH(
              (POPLOCK)a3,
              CallbackData,
              v12,
              Entry,
              UnionFs::Utils::CheckOplockComplete,
              UnionFs::Utils::OplockPrePostCallbackData);
    if ( v14 == FLT_PREOP_PENDING )
      Status = 259;
    else
      Status = CallbackData->IoStatus.Status;
    if ( Status == 259 )
    {
      return 259;
    }
    else if ( Status >= 0 )
    {
      if ( v13 )
      {
        v17 = (struct _FLT_DEFERRED_IO_WORKITEM *)v13[1];
        if ( v17 )
          FltFreeDeferredIoWorkItem(v17);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, v13);
      }
      return 0;
    }
    else
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)Status,
        (int)a5,
        (struct UnionFs::StackEventTracer *)0x6E100212879LL,
        (unsigned __int64)"UnionFs::Utils::CheckOplockH",
        "API: Oplock break check failed",
        PrePostCallbackDataRoutinea);
      if ( v13 )
      {
        v16 = (struct _FLT_DEFERRED_IO_WORKITEM *)v13[1];
        if ( v16 )
          FltFreeDeferredIoWorkItem(v16);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, v13);
      }
      return (unsigned int)Status;
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v8,
      (int)a5,
      (struct UnionFs::StackEventTracer *)0x6E000212854LL,
      (unsigned __int64)"UnionFs::Utils::CheckOplockH",
      "PUSH: Allocating oplock check context",
      PrePostCallbackDataRoutine);
    v9 = Entry;
    if ( Entry )
    {
      v10 = (struct _FLT_DEFERRED_IO_WORKITEM *)*((_QWORD *)Entry + 1);
      if ( v10 )
        FltFreeDeferredIoWorkItem(v10);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, v9);
    }
    return (unsigned int)v8;
  }
}

```

## disassembly

```asm
0x140069cf8  push    rbx
0x140069cfa  push    rbp
0x140069cfb  push    rdi
0x140069cfc  push    r14
0x140069cfe  sub     rsp, 68h
0x140069d02  mov     rax, rdx
0x140069d05  mov     [rsp+88h+Entry], 0
0x140069d0e  mov     rbp, r8
0x140069d11  lea     rdx, [rsp+88h+Entry]
0x140069d16  mov     r8, [rsp+88h+arg_20]
0x140069d1e  mov     rbx, rcx
0x140069d21  mov     rcx, rax
0x140069d24  mov     r14, r9
0x140069d27  call    ?AllocAndInit@CheckOplockContext@Utils@UnionFs@@SAJAEBU_FLT_RELATED_OBJECTS@@AEAV?$unique_ptr@VCheckOplockContext@Utils@UnionFs@@U?$default_delete@VCheckOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@3@@Z; UnionFs::Utils::CheckOplockContext::AllocAndInit(_FLT_RELATED_OBJECTS const &,utl::unique_ptr<UnionFs::Utils::CheckOplockContext,utl::default_delete<UnionFs::Utils::CheckOplockContext>> &,UnionFs::StackEventTracer &)
0x140069d2c  mov     edi, eax
0x140069d2e  test    eax, eax
0x140069d30  jns     short loc_140069DA1
0x140069d32  mov     rdx, [rsp+88h+arg_20]; int
0x140069d3a  lea     rax, aPushAllocating_34; "PUSH: Allocating oplock check context"
0x140069d41  lea     r9, aUnionfsUtilsCh_4; "UnionFs::Utils::CheckOplockH"
0x140069d48  mov     [rsp+88h+WaitCompletionRoutine], rax; char *
0x140069d4d  mov     r8, 6E000212854h; struct UnionFs::StackEventTracer *
0x140069d57  mov     ecx, edi; this
0x140069d59  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069d5e  mov     rbx, [rsp+88h+Entry]
0x140069d63  test    rbx, rbx
0x140069d66  jz      short loc_140069D9A
0x140069d68  mov     rcx, [rbx+8]; FltWorkItem
0x140069d6c  test    rcx, rcx
0x140069d6f  jz      short loc_140069D7D
0x140069d71  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069d78  nop     dword ptr [rax+rax+00h]
0x140069d7d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069d84  mov     rdx, rbx; Entry
0x140069d87  add     rcx, 0A80h; Lookaside
0x140069d8e  call    cs:__imp_ExFreeToLookasideListEx
0x140069d95  nop     dword ptr [rax+rax+00h]
0x140069d9a  mov     eax, edi
0x140069d9c  jmp     loc_140069EDB
0x140069da1  mov     r8d, [r14+10h]
0x140069da5  mov     rdx, rbx; CallbackData
0x140069da8  mov     rax, cs:?Flt_OplockBreakH2@UnionFs@@3P6A?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAPEAXPEAU_FLT_CALLBACK_DATA@@KPEAXP6AX12@Z3PEAKPEAG@ZEA; _FLT_PREOP_CALLBACK_STATUS (*UnionFs::Flt_OplockBreakH2)(void * *,_FLT_CALLBACK_DATA *,ulong,void *,void (*)(_FLT_CALLBACK_DATA *,void *),void (*)(_FLT_CALLBACK_DATA *,void *),ulong *,ushort *)
0x140069daf  btr     r8d, 1Fh; Flags
0x140069db4  mov     rdi, [rsp+88h+Entry]
0x140069db9  mov     r9, rdi; Context
0x140069dbc  test    rax, rax
0x140069dbf  jz      short loc_140069DF4
0x140069dc1  mov     rcx, [r14+8]
0x140069dc5  mov     [rsp+88h+var_50], rcx
0x140069dca  mov     rcx, [r14]
0x140069dcd  mov     [rsp+88h+var_58], rcx
0x140069dd2  lea     rcx, ?OplockPrePostCallbackData@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::OplockPrePostCallbackData(_FLT_CALLBACK_DATA *,void *)
0x140069dd9  mov     [rsp+88h+PrePostCallbackDataRoutine], rcx
0x140069dde  lea     rcx, ?CheckOplockComplete@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::CheckOplockComplete(_FLT_CALLBACK_DATA *,void *)
0x140069de5  mov     [rsp+88h+WaitCompletionRoutine], rcx
0x140069dea  mov     rcx, rbp
0x140069ded  call    _guard_dispatch_icall
0x140069df2  jmp     short loc_140069E1B
0x140069df4  lea     rcx, ?OplockPrePostCallbackData@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::OplockPrePostCallbackData(_FLT_CALLBACK_DATA *,void *)
0x140069dfb  mov     [rsp+88h+PrePostCallbackDataRoutine], rcx; char *
0x140069e00  lea     rcx, ?CheckOplockComplete@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::CheckOplockComplete(_FLT_CALLBACK_DATA *,void *)
0x140069e07  mov     [rsp+88h+WaitCompletionRoutine], rcx; WaitCompletionRoutine
0x140069e0c  mov     rcx, rbp; Oplock
0x140069e0f  call    cs:__imp_FltOplockBreakH
0x140069e16  nop     dword ptr [rax+rax+00h]
0x140069e1b  mov     ecx, 103h
0x140069e20  cmp     eax, 2
0x140069e23  jnz     short loc_140069E29
0x140069e25  mov     ebx, ecx
0x140069e27  jmp     short loc_140069E2C
0x140069e29  mov     ebx, [rbx+18h]
0x140069e2c  cmp     ebx, ecx
0x140069e2e  jnz     short loc_140069E37
0x140069e30  mov     eax, ecx
0x140069e32  jmp     loc_140069EDB
0x140069e37  test    ebx, ebx
0x140069e39  jns     short loc_140069EA2
0x140069e3b  mov     rdx, [rsp+88h+arg_20]; int
0x140069e43  lea     rax, aApiOplockBreak; "API: Oplock break check failed"
0x140069e4a  lea     r9, aUnionfsUtilsCh_4; "UnionFs::Utils::CheckOplockH"
0x140069e51  mov     [rsp+88h+WaitCompletionRoutine], rax; char *
0x140069e56  mov     r8, 6E100212879h; struct UnionFs::StackEventTracer *
0x140069e60  mov     ecx, ebx; this
0x140069e62  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069e67  test    rdi, rdi
0x140069e6a  jz      short loc_140069E9E
0x140069e6c  mov     rcx, [rdi+8]; FltWorkItem
0x140069e70  test    rcx, rcx
0x140069e73  jz      short loc_140069E81
0x140069e75  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069e7c  nop     dword ptr [rax+rax+00h]
0x140069e81  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069e88  mov     rdx, rdi; Entry
0x140069e8b  add     rcx, 0A80h; Lookaside
0x140069e92  call    cs:__imp_ExFreeToLookasideListEx
0x140069e99  nop     dword ptr [rax+rax+00h]
0x140069e9e  mov     eax, ebx
0x140069ea0  jmp     short loc_140069EDB
0x140069ea2  test    rdi, rdi
0x140069ea5  jz      short loc_140069ED9
0x140069ea7  mov     rcx, [rdi+8]; FltWorkItem
0x140069eab  test    rcx, rcx
0x140069eae  jz      short loc_140069EBC
0x140069eb0  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069eb7  nop     dword ptr [rax+rax+00h]
0x140069ebc  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069ec3  mov     rdx, rdi; Entry
0x140069ec6  add     rcx, 0A80h; Lookaside
0x140069ecd  call    cs:__imp_ExFreeToLookasideListEx
0x140069ed4  nop     dword ptr [rax+rax+00h]
0x140069ed9  xor     eax, eax
0x140069edb  add     rsp, 68h
0x140069edf  pop     r14
0x140069ee1  pop     rdi
0x140069ee2  pop     rbp
0x140069ee3  pop     rbx
0x140069ee4  retn
```
