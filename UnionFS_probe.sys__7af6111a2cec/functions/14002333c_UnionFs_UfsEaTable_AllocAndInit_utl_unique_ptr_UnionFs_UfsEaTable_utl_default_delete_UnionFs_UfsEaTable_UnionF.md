# UnionFs::UfsEaTable::AllocAndInit(utl::unique_ptr<UnionFs::UfsEaTable,utl::default_delete<UnionFs::UfsEaTable>> &,UnionFs::StackEventTracer &)

- ea: `0x14002333c`
- end: `0x140023496`
- name: `?AllocAndInit@UfsEaTable@UnionFs@@SAJAEAV?$unique_ptr@VUfsEaTable@UnionFs@@U?$default_delete@VUfsEaTable@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14005a6fc`
- `0x14005f20c`

## callees

- `0x140005c00`
- `0x1400096d4`
- `0x140022fc0`
- `0x14002333c`
- `0x140047e5c`
- `0x140056ac4`
- `0x140056afc`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x1400233f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002344e`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400233f4`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002344e`
- `ntoskrnl!ExAllocatePool2` at `0x140023359`
- `ntoskrnl!ExAllocatePool2` at `0x140023359`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400233da`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140023434`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400233da`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x140023434`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400233c2`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002341c`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400233c2`
- `ntoskrnl!ExDeleteResourceLite` at `0x14002341c`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsEaTable::AllocAndInit(__int64 *a1, struct UnionFs::StackEventTracer *a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rdi
  unsigned int v6; // ebx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v7; // rcx
  __int64 v8; // rbx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v9; // rcx
  const char *v11; // [rsp+28h] [rbp-30h]

  Pool2 = ExAllocatePool2(64, 152, 1952794197);
  v5 = Pool2;
  if ( !Pool2 )
  {
    v6 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a2,
      (struct UnionFs::StackEventTracer *)0x55300080024LL,
      (unsigned __int64)"UnionFs::UfsEaTable::AllocAndInit",
      "ORIGIN: Allocating ea table",
      v11);
    return v6;
  }
  UnionFs::UfsPathTable::UfsPathTable(Pool2, 6);
  v6 = UnionFs::UfsPathTable::InitializeRundown((UnionFs::UfsPathTable *)v5, a2);
  if ( (v6 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v6,
      (int)a2,
      (struct UnionFs::StackEventTracer *)0x55400080026LL,
      (unsigned __int64)"UnionFs::UfsEaTable::AllocAndInit",
      "PUSH: Initializing rundown",
      v11);
    UnionFs::UfsPathTable::EmptyAndRunDownTable((UnionFs::UfsPathTable *)v5);
    ExDeleteResourceLite((PERESOURCE)(v5 + 32));
    v7 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v5 + 136);
    if ( v7 )
      ExFreeCacheAwareRundownProtection(v7);
    utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(v5 + 8);
    ExFreePoolWithTag((PVOID)v5, 0);
    return v6;
  }
  v8 = *a1;
  *a1 = v5;
  if ( v8 )
  {
    UnionFs::UfsPathTable::EmptyAndRunDownTable((UnionFs::UfsPathTable *)v8);
    ExDeleteResourceLite((PERESOURCE)(v8 + 32));
    v9 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v8 + 136);
    if ( v9 )
      ExFreeCacheAwareRundownProtection(v9);
    utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(v8 + 8);
    ExFreePoolWithTag((PVOID)v8, 0);
  }
  return 0;
}

```

## disassembly

```asm
0x14002333c  push    rbx
0x14002333e  push    rbp
0x14002333f  push    rsi
0x140023340  push    rdi
0x140023341  sub     rsp, 38h
0x140023345  mov     rbp, rdx
0x140023348  mov     rsi, rcx
0x14002334b  mov     edx, 98h
0x140023350  mov     r8d, 74654655h
0x140023356  lea     ecx, [rdx-58h]
0x140023359  call    cs:__imp_ExAllocatePool2
0x140023360  nop     dword ptr [rax+rax+00h]
0x140023365  mov     rdi, rax
0x140023368  test    rax, rax
0x14002336b  jz      loc_14002345E
0x140023371  mov     edx, 6
0x140023376  mov     rcx, rax
0x140023379  call    ??0UfsPathTable@UnionFs@@IEAA@W4PATH_TABLE_CONFIGURATION@1@@Z; UnionFs::UfsPathTable::UfsPathTable(UnionFs::PATH_TABLE_CONFIGURATION)
0x14002337e  mov     rdx, rbp; struct UnionFs::StackEventTracer *
0x140023381  mov     rcx, rdi; this
0x140023384  call    ?InitializeRundown@UfsPathTable@UnionFs@@IEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsPathTable::InitializeRundown(UnionFs::StackEventTracer &)
0x140023389  mov     ebx, eax
0x14002338b  test    eax, eax
0x14002338d  jns     short loc_140023405
0x14002338f  lea     rax, aPushInitializi; "PUSH: Initializing rundown"
0x140023396  mov     r8, 55400080026h; struct UnionFs::StackEventTracer *
0x1400233a0  lea     r9, aUnionfsUfseata; "UnionFs::UfsEaTable::AllocAndInit"
0x1400233a7  mov     [rsp+58h+var_38], rax; char *
0x1400233ac  mov     rdx, rbp; int
0x1400233af  mov     ecx, ebx; this
0x1400233b1  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400233b6  mov     rcx, rdi; this
0x1400233b9  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x1400233be  lea     rcx, [rdi+20h]; Resource
0x1400233c2  call    cs:__imp_ExDeleteResourceLite
0x1400233c9  nop     dword ptr [rax+rax+00h]
0x1400233ce  mov     rcx, [rdi+88h]; RunRefCacheAware
0x1400233d5  test    rcx, rcx
0x1400233d8  jz      short loc_1400233E6
0x1400233da  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400233e1  nop     dword ptr [rax+rax+00h]
0x1400233e6  lea     rcx, [rdi+8]
0x1400233ea  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x1400233ef  xor     edx, edx; Tag
0x1400233f1  mov     rcx, rdi; P
0x1400233f4  call    cs:__imp_ExFreePoolWithTag
0x1400233fb  nop     dword ptr [rax+rax+00h]
0x140023400  jmp     loc_14002348A
0x140023405  mov     rbx, [rsi]
0x140023408  mov     [rsi], rdi
0x14002340b  test    rbx, rbx
0x14002340e  jz      short loc_14002345A
0x140023410  mov     rcx, rbx; this
0x140023413  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x140023418  lea     rcx, [rbx+20h]; Resource
0x14002341c  call    cs:__imp_ExDeleteResourceLite
0x140023423  nop     dword ptr [rax+rax+00h]
0x140023428  mov     rcx, [rbx+88h]; RunRefCacheAware
0x14002342f  test    rcx, rcx
0x140023432  jz      short loc_140023440
0x140023434  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14002343b  nop     dword ptr [rax+rax+00h]
0x140023440  lea     rcx, [rbx+8]
0x140023444  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x140023449  xor     edx, edx; Tag
0x14002344b  mov     rcx, rbx; P
0x14002344e  call    cs:__imp_ExFreePoolWithTag
0x140023455  nop     dword ptr [rax+rax+00h]
0x14002345a  xor     eax, eax
0x14002345c  jmp     short loc_14002348C
0x14002345e  lea     rax, aOriginAllocati_69; "ORIGIN: Allocating ea table"
0x140023465  mov     ebx, 0C000009Ah
0x14002346a  mov     ecx, ebx; this
0x14002346c  mov     [rsp+58h+var_38], rax; char *
0x140023471  lea     r9, aUnionfsUfseata; "UnionFs::UfsEaTable::AllocAndInit"
0x140023478  mov     r8, 55300080024h; struct UnionFs::StackEventTracer *
0x140023482  mov     rdx, rbp; int
0x140023485  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002348a  mov     eax, ebx
0x14002348c  add     rsp, 38h
0x140023490  pop     rdi
0x140023491  pop     rsi
0x140023492  pop     rbp
0x140023493  pop     rbx
0x140023494  retn
```
