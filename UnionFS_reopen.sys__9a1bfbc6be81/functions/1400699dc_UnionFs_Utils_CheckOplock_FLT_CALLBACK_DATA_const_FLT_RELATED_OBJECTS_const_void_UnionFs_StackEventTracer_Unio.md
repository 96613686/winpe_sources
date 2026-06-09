# UnionFs::Utils::CheckOplock(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,void * &,UnionFs::StackEventTracer &,UnionFs::Utils::CheckOplockFlags)

- ea: `0x1400699dc`
- end: `0x140069bad`
- name: `?CheckOplock@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAPEAXAEAVStackEventTracer@2@W4CheckOplockFlags@12@@Z`
- size: `465`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x14000cce0`
- `0x1400114c4`
- `0x1400545c0`
- `0x140057894`
- `0x140057e88`
- `0x140058374`
- `0x140058fbc`
- `0x1400696ac`

## callees

- `0x140056a50`
- `0x140056afc`
- `0x140069348`
- `0x1400699dc`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069a7e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069b52`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069b8d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069a7e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069b52`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069b8d`
- `FLTMGR!FltCheckOplockEx` at `0x140069ad6`
- `FLTMGR!FltCheckOplockEx` at `0x140069ad6`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069a61`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069b35`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069b70`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069a61`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069b35`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069b70`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CheckOplock(
        struct _FLT_CALLBACK_DATA *a1,
        __int64 a2,
        PVOID *a3,
        int a4,
        signed int a5)
{
  signed int v5; // edi
  int v9; // esi
  PVOID v10; // rbx
  struct _FLT_DEFERRED_IO_WORKITEM *v11; // rcx
  _QWORD *v13; // rbx
  void (__stdcall *v14)(PFLT_CALLBACK_DATA, PVOID); // rdx
  PVOID v15; // r9
  void (__stdcall *WaitCompletionRoutine)(PFLT_CALLBACK_DATA, PVOID); // rcx
  int Status; // edi
  struct _FLT_DEFERRED_IO_WORKITEM *v18; // rcx
  struct _FLT_DEFERRED_IO_WORKITEM *v19; // rcx
  const char *PrePostCallbackDataRoutine; // [rsp+28h] [rbp-50h]
  const char *PrePostCallbackDataRoutinea; // [rsp+28h] [rbp-50h]
  PVOID Entry; // [rsp+30h] [rbp-48h] BYREF

  v5 = a5;
  if ( (a5 & 6) != 0 )
    v5 = a5 | 0x80000000;
  Entry = 0;
  v9 = UnionFs::Utils::CheckOplockContext::AllocAndInit(a2, (_QWORD **)&Entry, a4);
  if ( v9 >= 0 )
  {
    v13 = Entry;
    v14 = 0;
    v15 = Entry;
    if ( v5 >= 0 )
      v14 = UnionFs::Utils::OplockPrePostCallbackData;
    WaitCompletionRoutine = 0;
    if ( v5 < 0 )
      v15 = 0;
    else
      WaitCompletionRoutine = UnionFs::Utils::CheckOplockComplete;
    if ( FltCheckOplockEx(a3, a1, v5 & 0x7FFFFFFF, v15, WaitCompletionRoutine, v14) == FLT_PREOP_PENDING )
      return 259;
    Status = a1->IoStatus.Status;
    if ( Status == 259 )
    {
      return 259;
    }
    else if ( Status >= 0 )
    {
      if ( v13 )
      {
        v19 = (struct _FLT_DEFERRED_IO_WORKITEM *)v13[1];
        if ( v19 )
          FltFreeDeferredIoWorkItem(v19);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, v13);
      }
      return 0;
    }
    else
    {
      UnionFs::ProcessTraceStatusFromApi(
        (UnionFs *)(unsigned int)Status,
        a4,
        (struct UnionFs::StackEventTracer *)0x6D900212842LL,
        (unsigned __int64)"UnionFs::Utils::CheckOplock",
        "API: Oplock break check failed",
        PrePostCallbackDataRoutinea);
      if ( v13 )
      {
        v18 = (struct _FLT_DEFERRED_IO_WORKITEM *)v13[1];
        if ( v18 )
          FltFreeDeferredIoWorkItem(v18);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, v13);
      }
      return (unsigned int)Status;
    }
  }
  else
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)(unsigned int)v9,
      a4,
      (struct UnionFs::StackEventTracer *)0x6D400212827LL,
      (unsigned __int64)"UnionFs::Utils::CheckOplock",
      "PUSH: Allocating oplock check context",
      PrePostCallbackDataRoutine);
    v10 = Entry;
    if ( Entry )
    {
      v11 = (struct _FLT_DEFERRED_IO_WORKITEM *)*((_QWORD *)Entry + 1);
      if ( v11 )
        FltFreeDeferredIoWorkItem(v11);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, v10);
    }
    return (unsigned int)v9;
  }
}

```

## disassembly

```asm
0x1400699dc  push    rbx
0x1400699de  push    rbp
0x1400699df  push    rsi
0x1400699e0  push    rdi
0x1400699e1  push    r14
0x1400699e3  push    r15
0x1400699e5  sub     rsp, 48h
0x1400699e9  mov     edi, [rsp+78h+arg_20]
0x1400699f0  mov     rbp, r9
0x1400699f3  mov     r15, r8
0x1400699f6  mov     rax, rdx
0x1400699f9  mov     r14, rcx
0x1400699fc  test    dil, 6
0x140069a00  jz      short loc_140069A08
0x140069a02  or      edi, 80000000h
0x140069a08  mov     r8, rbp
0x140069a0b  mov     [rsp+78h+Entry], 0
0x140069a14  lea     rdx, [rsp+78h+Entry]
0x140069a19  mov     rcx, rax
0x140069a1c  call    ?AllocAndInit@CheckOplockContext@Utils@UnionFs@@SAJAEBU_FLT_RELATED_OBJECTS@@AEAV?$unique_ptr@VCheckOplockContext@Utils@UnionFs@@U?$default_delete@VCheckOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@3@@Z; UnionFs::Utils::CheckOplockContext::AllocAndInit(_FLT_RELATED_OBJECTS const &,utl::unique_ptr<UnionFs::Utils::CheckOplockContext,utl::default_delete<UnionFs::Utils::CheckOplockContext>> &,UnionFs::StackEventTracer &)
0x140069a21  mov     esi, eax
0x140069a23  test    eax, eax
0x140069a25  jns     short loc_140069A91
0x140069a27  lea     rax, aPushAllocating_34; "PUSH: Allocating oplock check context"
0x140069a2e  mov     r8, 6D400212827h; struct UnionFs::StackEventTracer *
0x140069a38  lea     r9, aUnionfsUtilsCh_3; "UnionFs::Utils::CheckOplock"
0x140069a3f  mov     [rsp+78h+WaitCompletionRoutine], rax; char *
0x140069a44  mov     rdx, rbp; int
0x140069a47  mov     ecx, esi; this
0x140069a49  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069a4e  mov     rbx, [rsp+78h+Entry]
0x140069a53  test    rbx, rbx
0x140069a56  jz      short loc_140069A8A
0x140069a58  mov     rcx, [rbx+8]; FltWorkItem
0x140069a5c  test    rcx, rcx
0x140069a5f  jz      short loc_140069A6D
0x140069a61  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069a68  nop     dword ptr [rax+rax+00h]
0x140069a6d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069a74  mov     rdx, rbx; Entry
0x140069a77  add     rcx, 0A80h; Lookaside
0x140069a7e  call    cs:__imp_ExFreeToLookasideListEx
0x140069a85  nop     dword ptr [rax+rax+00h]
0x140069a8a  mov     eax, esi
0x140069a8c  jmp     loc_140069B9F
0x140069a91  mov     rbx, [rsp+78h+Entry]
0x140069a96  lea     rax, ?OplockPrePostCallbackData@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::OplockPrePostCallbackData(_FLT_CALLBACK_DATA *,void *)
0x140069a9d  xor     edx, edx
0x140069a9f  mov     r9, rbx
0x140069aa2  test    edi, edi
0x140069aa4  cmovns  rdx, rax
0x140069aa8  xor     ecx, ecx
0x140069aaa  test    edi, edi
0x140069aac  mov     [rsp+78h+PrePostCallbackDataRoutine], rdx; char *
0x140069ab1  lea     rax, ?CheckOplockComplete@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::CheckOplockComplete(_FLT_CALLBACK_DATA *,void *)
0x140069ab8  mov     rdx, r14; CallbackData
0x140069abb  cmovns  rcx, rax
0x140069abf  xor     eax, eax
0x140069ac1  test    edi, edi
0x140069ac3  mov     [rsp+78h+WaitCompletionRoutine], rcx; WaitCompletionRoutine
0x140069ac8  mov     rcx, r15; Oplock
0x140069acb  cmovs   r9, rax; Context
0x140069acf  btr     edi, 1Fh
0x140069ad3  mov     r8d, edi; Flags
0x140069ad6  call    cs:__imp_FltCheckOplockEx
0x140069add  nop     dword ptr [rax+rax+00h]
0x140069ae2  mov     ecx, 103h
0x140069ae7  cmp     eax, 2
0x140069aea  jz      loc_140069B9D
0x140069af0  mov     edi, [r14+18h]
0x140069af4  cmp     edi, ecx
0x140069af6  jz      loc_140069B9D
0x140069afc  test    edi, edi
0x140069afe  jns     short loc_140069B62
0x140069b00  lea     rax, aApiOplockBreak; "API: Oplock break check failed"
0x140069b07  mov     r8, 6D900212842h; struct UnionFs::StackEventTracer *
0x140069b11  lea     r9, aUnionfsUtilsCh_3; "UnionFs::Utils::CheckOplock"
0x140069b18  mov     [rsp+78h+WaitCompletionRoutine], rax; char *
0x140069b1d  mov     rdx, rbp; int
0x140069b20  mov     ecx, edi; this
0x140069b22  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069b27  test    rbx, rbx
0x140069b2a  jz      short loc_140069B5E
0x140069b2c  mov     rcx, [rbx+8]; FltWorkItem
0x140069b30  test    rcx, rcx
0x140069b33  jz      short loc_140069B41
0x140069b35  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069b3c  nop     dword ptr [rax+rax+00h]
0x140069b41  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069b48  mov     rdx, rbx; Entry
0x140069b4b  add     rcx, 0A80h; Lookaside
0x140069b52  call    cs:__imp_ExFreeToLookasideListEx
0x140069b59  nop     dword ptr [rax+rax+00h]
0x140069b5e  mov     eax, edi
0x140069b60  jmp     short loc_140069B9F
0x140069b62  test    rbx, rbx
0x140069b65  jz      short loc_140069B99
0x140069b67  mov     rcx, [rbx+8]; FltWorkItem
0x140069b6b  test    rcx, rcx
0x140069b6e  jz      short loc_140069B7C
0x140069b70  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069b77  nop     dword ptr [rax+rax+00h]
0x140069b7c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069b83  mov     rdx, rbx; Entry
0x140069b86  add     rcx, 0A80h; Lookaside
0x140069b8d  call    cs:__imp_ExFreeToLookasideListEx
0x140069b94  nop     dword ptr [rax+rax+00h]
0x140069b99  xor     eax, eax
0x140069b9b  jmp     short loc_140069B9F
0x140069b9d  mov     eax, ecx
0x140069b9f  add     rsp, 48h
0x140069ba3  pop     r15
0x140069ba5  pop     r14
0x140069ba7  pop     rdi
0x140069ba8  pop     rsi
0x140069ba9  pop     rbp
0x140069baa  pop     rbx
0x140069bab  retn
```
