# UnionFs::Utils::CheckOplockContext::AllocAndInit(_FLT_RELATED_OBJECTS const &,utl::unique_ptr<UnionFs::Utils::CheckOplockContext,utl::default_delete<UnionFs::Utils::CheckOplockContext>> &,UnionFs::StackEventTracer &)

- ea: `0x140069348`
- end: `0x140069492`
- name: `?AllocAndInit@CheckOplockContext@Utils@UnionFs@@SAJAEBU_FLT_RELATED_OBJECTS@@AEAV?$unique_ptr@VCheckOplockContext@Utils@UnionFs@@U?$default_delete@VCheckOplockContext@Utils@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@3@@Z`
- size: `330`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `authz_impersonation, installer_update`

## callers

- `0x1400699dc`
- `0x140069cf8`

## callees

- `0x140056ac4`
- `0x140069348`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069391`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069439`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069391`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140069439`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400693f0`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400693f0`
- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x14006939d`
- `FLTMGR!FltAllocateDeferredIoWorkItem` at `0x14006939d`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069374`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14006941c`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069478`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069374`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x14006941c`
- `FLTMGR!FltFreeDeferredIoWorkItem` at `0x140069478`

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
      (struct UnionFs::StackEventTracer *)0x6D000212759LL,
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
      (struct UnionFs::StackEventTracer *)0x6D500212764LL,
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
0x140069348  push    rbx
0x14006934a  push    rbp
0x14006934b  push    rsi
0x14006934c  push    rdi
0x14006934d  push    r14
0x14006934f  sub     rsp, 30h
0x140069353  mov     rbx, [rdx]
0x140069356  mov     rbp, r8
0x140069359  mov     qword ptr [rdx], 0
0x140069360  mov     rdi, rdx
0x140069363  mov     r14, rcx
0x140069366  test    rbx, rbx
0x140069369  jz      short loc_14006939D
0x14006936b  mov     rcx, [rbx+8]; FltWorkItem
0x14006936f  test    rcx, rcx
0x140069372  jz      short loc_140069380
0x140069374  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14006937b  nop     dword ptr [rax+rax+00h]
0x140069380  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140069387  mov     rdx, rbx; Entry
0x14006938a  add     rcx, 0A80h; Lookaside
0x140069391  call    cs:__imp_ExFreeToLookasideListEx
0x140069398  nop     dword ptr [rax+rax+00h]
0x14006939d  call    cs:__imp_FltAllocateDeferredIoWorkItem
0x1400693a4  nop     dword ptr [rax+rax+00h]
0x1400693a9  mov     rsi, rax
0x1400693ac  test    rax, rax
0x1400693af  jnz     short loc_1400693E2
0x1400693b1  lea     rax, aOriginAllocati_42; "ORIGIN: Allocating deferred work item"
0x1400693b8  mov     ebx, 0C000009Ah
0x1400693bd  mov     ecx, ebx; this
0x1400693bf  mov     [rsp+58h+var_38], rax; char *
0x1400693c4  lea     r9, aUnionfsUtilsCh_5; "UnionFs::Utils::CheckOplockContext::All"...
0x1400693cb  mov     r8, 6D000212759h; struct UnionFs::StackEventTracer *
0x1400693d5  mov     rdx, rbp; int
0x1400693d8  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400693dd  jmp     loc_140069484
0x1400693e2  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400693e9  add     rcx, 0A80h; Lookaside
0x1400693f0  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400693f7  nop     dword ptr [rax+rax+00h]
0x1400693fc  test    rax, rax
0x1400693ff  jz      short loc_140069449
0x140069401  mov     [rax], r14
0x140069404  mov     [rax+8], rsi
0x140069408  mov     rbx, [rdi]
0x14006940b  mov     [rdi], rax
0x14006940e  test    rbx, rbx
0x140069411  jz      short loc_140069445
0x140069413  mov     rcx, [rbx+8]; FltWorkItem
0x140069417  test    rcx, rcx
0x14006941a  jz      short loc_140069428
0x14006941c  call    cs:__imp_FltFreeDeferredIoWorkItem
0x140069423  nop     dword ptr [rax+rax+00h]
0x140069428  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14006942f  mov     rdx, rbx; Entry
0x140069432  add     rcx, 0A80h; Lookaside
0x140069439  call    cs:__imp_ExFreeToLookasideListEx
0x140069440  nop     dword ptr [rax+rax+00h]
0x140069445  xor     eax, eax
0x140069447  jmp     short loc_140069486
0x140069449  lea     rax, aOriginAllocati_62; "ORIGIN: Allocating CheckOplockContext"
0x140069450  mov     ebx, 0C000009Ah
0x140069455  mov     ecx, ebx; this
0x140069457  mov     [rsp+58h+var_38], rax; char *
0x14006945c  lea     r9, aUnionfsUtilsCh_5; "UnionFs::Utils::CheckOplockContext::All"...
0x140069463  mov     r8, 6D500212764h; struct UnionFs::StackEventTracer *
0x14006946d  mov     rdx, rbp; int
0x140069470  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140069475  mov     rcx, rsi; FltWorkItem
0x140069478  call    cs:__imp_FltFreeDeferredIoWorkItem
0x14006947f  nop     dword ptr [rax+rax+00h]
0x140069484  mov     eax, ebx
0x140069486  add     rsp, 30h
0x14006948a  pop     r14
0x14006948c  pop     rdi
0x14006948d  pop     rsi
0x14006948e  pop     rbp
0x14006948f  pop     rbx
0x140069490  retn
```
