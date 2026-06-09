# UnionFs::Utils::CheckOplock(_FLT_CALLBACK_DATA const &,_FLT_RELATED_OBJECTS const &,void * &,UnionFs::StackEventTracer &,UnionFs::Utils::CheckOplockFlags)

- ea: `0x140069bcc`
- end: `0x140069d9d`
- name: `?CheckOplock@Utils@UnionFs@@YAJAEBU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAPEAXAEAVStackEventTracer@2@W4CheckOplockFlags@12@@Z`
- size: `465`
- prototype: ``
- caller_count: `8`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000ccb0`
- `0x1400114e4`
- `0x140054740`
- `0x140057a14`
- `0x140058008`
- `0x1400584f4`
- `0x14005913c`
- `0x14006989c`

## callees

- `0x140056bd0`
- `0x140056c7c`
- `0x140069538`
- `0x140069bcc`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069c6e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069d42`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069d7d`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069c6e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069d42`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069d7d`
- `FLTMGR!FltCheckOplockEx` at `0x140069cc6`
- `FLTMGR!FltCheckOplockEx` at `0x140069cc6`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069c51`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069d25`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069d60`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069c51`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069d25`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069d60`

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
        (struct UnionFs::StackEventTracer *)0x6D900212878LL,
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
      (struct UnionFs::StackEventTracer *)0x6D40021285DLL,
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
0x140069bcc  push    rbx
0x140069bce  push    rbp
0x140069bcf  push    rsi
0x140069bd0  push    rdi
0x140069bd1  push    r14
0x140069bd3  push    r15
0x140069bd5  sub     rsp, 48h
0x140069bd9  mov     edi, [rsp+78h+arg_20]
0x140069be0  mov     rbp, r9
0x140069be3  mov     r15, r8
0x140069be6  mov     rax, rdx
0x140069be9  mov     r14, rcx
0x140069bec  test    dil, 6
0x140069bf0  jz      short loc_140069BF8
0x140069bf2  or      edi, 80000000h
0x140069bf8  mov     r8, rbp
0x140069bfb  mov     [rsp+78h+Entry], 0
0x140069c04  lea     rdx, [rsp+78h+Entry]
0x140069c09  mov     rcx, rax
0x140069c0c  call    ?AllocAndInit@CheckOplockContext@Utils@UnionFs@@SAJAEBU_FLT_RELATED_OBJECTS@@AEAV?$unique_ptr@VCheckOplockContext@Utils@UnionFs@@U?$default_delete@VCheckOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@3@@Z; UnionFs::Utils::CheckOplockContext::AllocAndInit(_FLT_RELATED_OBJECTS const &,utl::unique_ptr<UnionFs::Utils::CheckOplockContext,utl::default_delete<UnionFs::Utils::CheckOplockContext>> &,UnionFs::StackEventTracer &)
0x140069c11  mov     esi, eax
0x140069c13  test    eax, eax
0x140069c15  jns     short loc_140069C81
0x140069c17  lea     rax, aPushAllocating_34; "PUSH: Allocating oplock check context"
0x140069c1e  mov     r8, 6D40021285Dh; struct UnionFs::StackEventTracer *
0x140069c28  lea     r9, aUnionfsUtilsCh_3; "UnionFs::Utils::CheckOplock"
0x140069c2f  mov     [rsp+78h+WaitCompletionRoutine], rax; char *
0x140069c34  mov     rdx, rbp; int
0x140069c37  mov     ecx, esi; this
0x140069c39  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069c3e  mov     rbx, [rsp+78h+Entry]
0x140069c43  test    rbx, rbx
0x140069c46  jz      short loc_140069C7A
0x140069c48  mov     rcx, [rbx+8]; FltWorkItem
0x140069c4c  test    rcx, rcx
0x140069c4f  jz      short loc_140069C5D
0x140069c51  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069c58  nop     dword ptr [rax+rax+00h]
0x140069c5d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069c64  mov     rdx, rbx; Entry
0x140069c67  add     rcx, 0A80h; Lookaside
0x140069c6e  call    cs:__imp_ExFreeToLookasideListEx
0x140069c75  nop     dword ptr [rax+rax+00h]
0x140069c7a  mov     eax, esi
0x140069c7c  jmp     loc_140069D8F
0x140069c81  mov     rbx, [rsp+78h+Entry]
0x140069c86  lea     rax, ?OplockPrePostCallbackData@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::OplockPrePostCallbackData(_FLT_CALLBACK_DATA *,void *)
0x140069c8d  xor     edx, edx
0x140069c8f  mov     r9, rbx
0x140069c92  test    edi, edi
0x140069c94  cmovns  rdx, rax
0x140069c98  xor     ecx, ecx
0x140069c9a  test    edi, edi
0x140069c9c  mov     [rsp+78h+PrePostCallbackDataRoutine], rdx; char *
0x140069ca1  lea     rax, ?CheckOplockComplete@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::CheckOplockComplete(_FLT_CALLBACK_DATA *,void *)
0x140069ca8  mov     rdx, r14; CallbackData
0x140069cab  cmovns  rcx, rax
0x140069caf  xor     eax, eax
0x140069cb1  test    edi, edi
0x140069cb3  mov     [rsp+78h+WaitCompletionRoutine], rcx; WaitCompletionRoutine
0x140069cb8  mov     rcx, r15; Oplock
0x140069cbb  cmovs   r9, rax; Context
0x140069cbf  btr     edi, 1Fh
0x140069cc3  mov     r8d, edi; Flags
0x140069cc6  call    cs:__imp_FltCheckOplockEx
0x140069ccd  nop     dword ptr [rax+rax+00h]
0x140069cd2  mov     ecx, 103h
0x140069cd7  cmp     eax, 2
0x140069cda  jz      loc_140069D8D
0x140069ce0  mov     edi, [r14+18h]
0x140069ce4  cmp     edi, ecx
0x140069ce6  jz      loc_140069D8D
0x140069cec  test    edi, edi
0x140069cee  jns     short loc_140069D52
0x140069cf0  lea     rax, aApiOplockBreak; "API: Oplock break check failed"
0x140069cf7  mov     r8, 6D900212878h; struct UnionFs::StackEventTracer *
0x140069d01  lea     r9, aUnionfsUtilsCh_3; "UnionFs::Utils::CheckOplock"
0x140069d08  mov     [rsp+78h+WaitCompletionRoutine], rax; char *
0x140069d0d  mov     rdx, rbp; int
0x140069d10  mov     ecx, edi; this
0x140069d12  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069d17  test    rbx, rbx
0x140069d1a  jz      short loc_140069D4E
0x140069d1c  mov     rcx, [rbx+8]; FltWorkItem
0x140069d20  test    rcx, rcx
0x140069d23  jz      short loc_140069D31
0x140069d25  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069d2c  nop     dword ptr [rax+rax+00h]
0x140069d31  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069d38  mov     rdx, rbx; Entry
0x140069d3b  add     rcx, 0A80h; Lookaside
0x140069d42  call    cs:__imp_ExFreeToLookasideListEx
0x140069d49  nop     dword ptr [rax+rax+00h]
0x140069d4e  mov     eax, edi
0x140069d50  jmp     short loc_140069D8F
0x140069d52  test    rbx, rbx
0x140069d55  jz      short loc_140069D89
0x140069d57  mov     rcx, [rbx+8]; FltWorkItem
0x140069d5b  test    rcx, rcx
0x140069d5e  jz      short loc_140069D6C
0x140069d60  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069d67  nop     dword ptr [rax+rax+00h]
0x140069d6c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069d73  mov     rdx, rbx; Entry
0x140069d76  add     rcx, 0A80h; Lookaside
0x140069d7d  call    cs:__imp_ExFreeToLookasideListEx
0x140069d84  nop     dword ptr [rax+rax+00h]
0x140069d89  xor     eax, eax
0x140069d8b  jmp     short loc_140069D8F
0x140069d8d  mov     eax, ecx
0x140069d8f  add     rsp, 48h
0x140069d93  pop     r15
0x140069d95  pop     r14
0x140069d97  pop     rdi
0x140069d98  pop     rsi
0x140069d99  pop     rbp
0x140069d9a  pop     rbx
0x140069d9b  retn
```
