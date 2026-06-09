# UnionFs::Utils::CheckOplockH(_FLT_CALLBACK_DATA &,_FLT_RELATED_OBJECTS const &,void * &,UnionFs::Utils::CheckOplockHParams const &,UnionFs::StackEventTracer &)

- ea: `0x140069ee8`
- end: `0x14006a0d6`
- name: `?CheckOplockH@Utils@UnionFs@@YAJAEAU_FLT_CALLBACK_DATA@@AEBU_FLT_RELATED_OBJECTS@@AEAPEAXAEBUCheckOplockHParams@12@AEAVStackEventTracer@2@@Z`
- size: `494`
- prototype: `__int64 __usercall@<rax>(PFLT_CALLBACK_DATA CallbackData@<rcx>, struct _FLT_CALLBACK_DATA *@<rdx>, const struct _FLT_RELATED_OBJECTS *@<r8>, void **@<r9>, const struct UnionFs::Utils::CheckOplockHParams *, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1400114e4`
- `0x14005913c`

## callees

- `0x140056bd0`
- `0x140056c7c`
- `0x140069538`
- `0x140069ee8`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069f7e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006a082`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006a0bd`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069f7e`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006a082`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14006a0bd`
- `FLTMGR!FltOplockBreakH` at `0x140069fff`
- `FLTMGR!FltOplockBreakH` at `0x140069fff`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069f61`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14006a065`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14006a0a0`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069f61`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14006a065`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14006a0a0`

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
        (struct UnionFs::StackEventTracer *)0x6E1002128AFLL,
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
      (struct UnionFs::StackEventTracer *)0x6E00021288ALL,
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
0x140069ee8  push    rbx
0x140069eea  push    rbp
0x140069eeb  push    rdi
0x140069eec  push    r14
0x140069eee  sub     rsp, 68h
0x140069ef2  mov     rax, rdx
0x140069ef5  mov     [rsp+88h+Entry], 0
0x140069efe  mov     rbp, r8
0x140069f01  lea     rdx, [rsp+88h+Entry]
0x140069f06  mov     r8, [rsp+88h+arg_20]
0x140069f0e  mov     rbx, rcx
0x140069f11  mov     rcx, rax
0x140069f14  mov     r14, r9
0x140069f17  call    ?AllocAndInit@CheckOplockContext@Utils@UnionFs@@SAJAEBU_FLT_RELATED_OBJECTS@@AEAV?$unique_ptr@VCheckOplockContext@Utils@UnionFs@@U?$default_delete@VCheckOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@3@@Z; UnionFs::Utils::CheckOplockContext::AllocAndInit(_FLT_RELATED_OBJECTS const &,utl::unique_ptr<UnionFs::Utils::CheckOplockContext,utl::default_delete<UnionFs::Utils::CheckOplockContext>> &,UnionFs::StackEventTracer &)
0x140069f1c  mov     edi, eax
0x140069f1e  test    eax, eax
0x140069f20  jns     short loc_140069F91
0x140069f22  mov     rdx, [rsp+88h+arg_20]; int
0x140069f2a  lea     rax, aPushAllocating_34; "PUSH: Allocating oplock check context"
0x140069f31  lea     r9, aUnionfsUtilsCh_4; "UnionFs::Utils::CheckOplockH"
0x140069f38  mov     [rsp+88h+WaitCompletionRoutine], rax; char *
0x140069f3d  mov     r8, 6E00021288Ah; struct UnionFs::StackEventTracer *
0x140069f47  mov     ecx, edi; this
0x140069f49  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069f4e  mov     rbx, [rsp+88h+Entry]
0x140069f53  test    rbx, rbx
0x140069f56  jz      short loc_140069F8A
0x140069f58  mov     rcx, [rbx+8]; FltWorkItem
0x140069f5c  test    rcx, rcx
0x140069f5f  jz      short loc_140069F6D
0x140069f61  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069f68  nop     dword ptr [rax+rax+00h]
0x140069f6d  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069f74  mov     rdx, rbx; Entry
0x140069f77  add     rcx, 0A80h; Lookaside
0x140069f7e  call    cs:__imp_ExFreeToLookasideListEx
0x140069f85  nop     dword ptr [rax+rax+00h]
0x140069f8a  mov     eax, edi
0x140069f8c  jmp     loc_14006A0CB
0x140069f91  mov     r8d, [r14+10h]
0x140069f95  mov     rdx, rbx; CallbackData
0x140069f98  mov     rax, cs:?Flt_OplockBreakH2@UnionFs@@3P6A?AW4_FLT_PREOP_CALLBACK_STATUS@@PEAPEAXPEAU_FLT_CALLBACK_DATA@@KPEAXP6AX12@Z3PEAKPEAG@ZEA; _FLT_PREOP_CALLBACK_STATUS (*UnionFs::Flt_OplockBreakH2)(void * *,_FLT_CALLBACK_DATA *,ulong,void *,void (*)(_FLT_CALLBACK_DATA *,void *),void (*)(_FLT_CALLBACK_DATA *,void *),ulong *,ushort *)
0x140069f9f  btr     r8d, 1Fh; Flags
0x140069fa4  mov     rdi, [rsp+88h+Entry]
0x140069fa9  mov     r9, rdi; Context
0x140069fac  test    rax, rax
0x140069faf  jz      short loc_140069FE4
0x140069fb1  mov     rcx, [r14+8]
0x140069fb5  mov     [rsp+88h+var_50], rcx
0x140069fba  mov     rcx, [r14]
0x140069fbd  mov     [rsp+88h+var_58], rcx
0x140069fc2  lea     rcx, ?OplockPrePostCallbackData@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::OplockPrePostCallbackData(_FLT_CALLBACK_DATA *,void *)
0x140069fc9  mov     [rsp+88h+PrePostCallbackDataRoutine], rcx
0x140069fce  lea     rcx, ?CheckOplockComplete@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::CheckOplockComplete(_FLT_CALLBACK_DATA *,void *)
0x140069fd5  mov     [rsp+88h+WaitCompletionRoutine], rcx
0x140069fda  mov     rcx, rbp
0x140069fdd  call    _guard_dispatch_icall
0x140069fe2  jmp     short loc_14006A00B
0x140069fe4  lea     rcx, ?OplockPrePostCallbackData@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::OplockPrePostCallbackData(_FLT_CALLBACK_DATA *,void *)
0x140069feb  mov     [rsp+88h+PrePostCallbackDataRoutine], rcx; char *
0x140069ff0  lea     rcx, ?CheckOplockComplete@Utils@UnionFs@@YAXPEAU_FLT_CALLBACK_DATA@@PEAX@Z; UnionFs::Utils::CheckOplockComplete(_FLT_CALLBACK_DATA *,void *)
0x140069ff7  mov     [rsp+88h+WaitCompletionRoutine], rcx; WaitCompletionRoutine
0x140069ffc  mov     rcx, rbp; Oplock
0x140069fff  call    cs:__imp_FltOplockBreakH
0x14006a006  nop     dword ptr [rax+rax+00h]
0x14006a00b  mov     ecx, 103h
0x14006a010  cmp     eax, 2
0x14006a013  jnz     short loc_14006A019
0x14006a015  mov     ebx, ecx
0x14006a017  jmp     short loc_14006A01C
0x14006a019  mov     ebx, [rbx+18h]
0x14006a01c  cmp     ebx, ecx
0x14006a01e  jnz     short loc_14006A027
0x14006a020  mov     eax, ecx
0x14006a022  jmp     loc_14006A0CB
0x14006a027  test    ebx, ebx
0x14006a029  jns     short loc_14006A092
0x14006a02b  mov     rdx, [rsp+88h+arg_20]; int
0x14006a033  lea     rax, aApiOplockBreak; "API: Oplock break check failed"
0x14006a03a  lea     r9, aUnionfsUtilsCh_4; "UnionFs::Utils::CheckOplockH"
0x14006a041  mov     [rsp+88h+WaitCompletionRoutine], rax; char *
0x14006a046  mov     r8, 6E1002128AFh; struct UnionFs::StackEventTracer *
0x14006a050  mov     ecx, ebx; this
0x14006a052  call    ?ProcessTraceStatusFromApi@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusFromApi(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14006a057  test    rdi, rdi
0x14006a05a  jz      short loc_14006A08E
0x14006a05c  mov     rcx, [rdi+8]; FltWorkItem
0x14006a060  test    rcx, rcx
0x14006a063  jz      short loc_14006A071
0x14006a065  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14006a06c  nop     dword ptr [rax+rax+00h]
0x14006a071  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006a078  mov     rdx, rdi; Entry
0x14006a07b  add     rcx, 0A80h; Lookaside
0x14006a082  call    cs:__imp_ExFreeToLookasideListEx
0x14006a089  nop     dword ptr [rax+rax+00h]
0x14006a08e  mov     eax, ebx
0x14006a090  jmp     short loc_14006A0CB
0x14006a092  test    rdi, rdi
0x14006a095  jz      short loc_14006A0C9
0x14006a097  mov     rcx, [rdi+8]; FltWorkItem
0x14006a09b  test    rcx, rcx
0x14006a09e  jz      short loc_14006A0AC
0x14006a0a0  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14006a0a7  nop     dword ptr [rax+rax+00h]
0x14006a0ac  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006a0b3  mov     rdx, rdi; Entry
0x14006a0b6  add     rcx, 0A80h; Lookaside
0x14006a0bd  call    cs:__imp_ExFreeToLookasideListEx
0x14006a0c4  nop     dword ptr [rax+rax+00h]
0x14006a0c9  xor     eax, eax
0x14006a0cb  add     rsp, 68h
0x14006a0cf  pop     r14
0x14006a0d1  pop     rdi
0x14006a0d2  pop     rbp
0x14006a0d3  pop     rbx
0x14006a0d4  retn
```
