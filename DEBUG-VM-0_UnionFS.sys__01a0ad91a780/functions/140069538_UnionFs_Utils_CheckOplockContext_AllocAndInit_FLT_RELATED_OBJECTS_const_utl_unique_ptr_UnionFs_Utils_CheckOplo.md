# UnionFs::Utils::CheckOplockContext::AllocAndInit(_FLT_RELATED_OBJECTS const &,utl::unique_ptr<UnionFs::Utils::CheckOplockContext,utl::default_delete<UnionFs::Utils::CheckOplockContext>> &,UnionFs::StackEventTracer &)

- ea: `0x140069538`
- end: `0x140069682`
- name: `?AllocAndInit@CheckOplockContext@Utils@UnionFs@@SAJAEBU_FLT_RELATED_OBJECTS@@AEAV?$unique_ptr@VCheckOplockContext@Utils@UnionFs@@U?$default_delete@VCheckOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@3@@Z`
- size: `330`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x140069bcc`
- `0x140069ee8`

## callees

- `0x140056c44`
- `0x140069538`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069581`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069629`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069581`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069629`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400695e0`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400695e0`
- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x14006958d`
- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x14006958d`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069564`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14006960c`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069668`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069564`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14006960c`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069668`

## pseudocode

```c
__int64 __fastcall UnionFs::Utils::CheckOplockContext::AllocAndInit(__int64 a1, _QWORD **a2, int a3)
{
  _QWORD *v3; // rbx
  struct _FLT_DEFERRED_IO_WORKITEM *v7; // rcx
  struct _FLT_DEFERRED_IO_WORKITEM *DeferredIoWorkItem; // rsi
  _QWORD *v9; // rax
  _QWORD *v10; // rbx
  struct _FLT_DEFERRED_IO_WORKITEM *v11; // rcx
  const char *v13; // [rsp+28h] [rbp-30h]

  v3 = *a2;
  *a2 = 0;
  if ( v3 )
  {
    v7 = (struct _FLT_DEFERRED_IO_WORKITEM *)v3[1];
    if ( v7 )
      FltFreeDeferredIoWorkItem(v7);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, v3);
  }
  DeferredIoWorkItem = FltAllocateDeferredIoWorkItem();
  if ( !DeferredIoWorkItem )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a3,
      (struct UnionFs::StackEventTracer *)0x6D00021278FLL,
      (unsigned __int64)"UnionFs::Utils::CheckOplockContext::AllocAndInit",
      "ORIGIN: Allocating deferred work item",
      v13);
    return 3221225626LL;
  }
  v9 = ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28);
  if ( !v9 )
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a3,
      (struct UnionFs::StackEventTracer *)0x6D50021279ALL,
      (unsigned __int64)"UnionFs::Utils::CheckOplockContext::AllocAndInit",
      "ORIGIN: Allocating CheckOplockContext",
      v13);
    FltFreeDeferredIoWorkItem(DeferredIoWorkItem);
    return 3221225626LL;
  }
  *v9 = a1;
  v9[1] = DeferredIoWorkItem;
  v10 = *a2;
  *a2 = v9;
  if ( v10 )
  {
    v11 = (struct _FLT_DEFERRED_IO_WORKITEM *)v10[1];
    if ( v11 )
      FltFreeDeferredIoWorkItem(v11);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)UnionFs::g_FilterState + 28, v10);
  }
  return 0;
}

```

## disassembly

```asm
0x140069538  push    rbx
0x14006953a  push    rbp
0x14006953b  push    rsi
0x14006953c  push    rdi
0x14006953d  push    r14
0x14006953f  sub     rsp, 30h
0x140069543  mov     rbx, [rdx]
0x140069546  mov     rbp, r8
0x140069549  mov     qword ptr [rdx], 0
0x140069550  mov     rdi, rdx
0x140069553  mov     r14, rcx
0x140069556  test    rbx, rbx
0x140069559  jz      short loc_14006958D
0x14006955b  mov     rcx, [rbx+8]; FltWorkItem
0x14006955f  test    rcx, rcx
0x140069562  jz      short loc_140069570
0x140069564  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14006956b  nop     dword ptr [rax+rax+00h]
0x140069570  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069577  mov     rdx, rbx; Entry
0x14006957a  add     rcx, 0A80h; Lookaside
0x140069581  call    cs:__imp_ExFreeToLookasideListEx
0x140069588  nop     dword ptr [rax+rax+00h]
0x14006958d  call    cs:__imp_FltAllocateDeferredIoWorkItem
0x140069594  nop     dword ptr [rax+rax+00h]
0x140069599  mov     rsi, rax
0x14006959c  test    rax, rax
0x14006959f  jnz     short loc_1400695D2
0x1400695a1  lea     rax, aOriginAllocati_43; "ORIGIN: Allocating deferred work item"
0x1400695a8  mov     ebx, 0C000009Ah
0x1400695ad  mov     ecx, ebx; this
0x1400695af  mov     [rsp+58h+var_38], rax; char *
0x1400695b4  lea     r9, aUnionfsUtilsCh_5; "UnionFs::Utils::CheckOplockContext::All"...
0x1400695bb  mov     r8, 6D00021278Fh; struct UnionFs::StackEventTracer *
0x1400695c5  mov     rdx, rbp; int
0x1400695c8  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400695cd  jmp     loc_140069674
0x1400695d2  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400695d9  add     rcx, 0A80h; Lookaside
0x1400695e0  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400695e7  nop     dword ptr [rax+rax+00h]
0x1400695ec  test    rax, rax
0x1400695ef  jz      short loc_140069639
0x1400695f1  mov     [rax], r14
0x1400695f4  mov     [rax+8], rsi
0x1400695f8  mov     rbx, [rdi]
0x1400695fb  mov     [rdi], rax
0x1400695fe  test    rbx, rbx
0x140069601  jz      short loc_140069635
0x140069603  mov     rcx, [rbx+8]; FltWorkItem
0x140069607  test    rcx, rcx
0x14006960a  jz      short loc_140069618
0x14006960c  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069613  nop     dword ptr [rax+rax+00h]
0x140069618  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006961f  mov     rdx, rbx; Entry
0x140069622  add     rcx, 0A80h; Lookaside
0x140069629  call    cs:__imp_ExFreeToLookasideListEx
0x140069630  nop     dword ptr [rax+rax+00h]
0x140069635  xor     eax, eax
0x140069637  jmp     short loc_140069676
0x140069639  lea     rax, aOriginAllocati_63; "ORIGIN: Allocating CheckOplockContext"
0x140069640  mov     ebx, 0C000009Ah
0x140069645  mov     ecx, ebx; this
0x140069647  mov     [rsp+58h+var_38], rax; char *
0x14006964c  lea     r9, aUnionfsUtilsCh_5; "UnionFs::Utils::CheckOplockContext::All"...
0x140069653  mov     r8, 6D50021279Ah; struct UnionFs::StackEventTracer *
0x14006965d  mov     rdx, rbp; int
0x140069660  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069665  mov     rcx, rsi; FltWorkItem
0x140069668  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14006966f  nop     dword ptr [rax+rax+00h]
0x140069674  mov     eax, ebx
0x140069676  add     rsp, 30h
0x14006967a  pop     r14
0x14006967c  pop     rdi
0x14006967d  pop     rsi
0x14006967e  pop     rbp
0x14006967f  pop     rbx
0x140069680  retn
```
