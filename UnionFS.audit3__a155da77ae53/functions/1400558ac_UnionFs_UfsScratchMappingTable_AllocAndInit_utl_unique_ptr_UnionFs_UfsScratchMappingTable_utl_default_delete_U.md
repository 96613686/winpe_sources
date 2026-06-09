# UnionFs::UfsScratchMappingTable::AllocAndInit(utl::unique_ptr<UnionFs::UfsScratchMappingTable,utl::default_delete<UnionFs::UfsScratchMappingTable>> &,UnionFs::StackEventTracer &)

- ea: `0x1400558ac`
- end: `0x140055a06`
- name: `?AllocAndInit@UfsScratchMappingTable@UnionFs@@SAJAEAV?$unique_ptr@VUfsScratchMappingTable@UnionFs@@U?$default_delete@VUfsScratchMappingTable@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `346`
- prototype: ``
- caller_count: `2`
- callee_count: `7`
- tags: `installer_update`

## callers

- `0x14005a87c`
- `0x14005f38c`

## callees

- `0x140005c00`
- `0x1400096a4`
- `0x140023060`
- `0x140047fdc`
- `0x1400558ac`
- `0x140056c44`
- `0x140056c7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140055964`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400559be`
- `ntoskrnl!ExFreePoolWithTag` at `0x140055964`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400559be`
- `ntoskrnl!ExAllocatePool2` at `0x1400558c9`
- `ntoskrnl!ExAllocatePool2` at `0x1400558c9`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005594a`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400559a4`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005594a`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400559a4`
- `ntoskrnl!ExDeleteResourceLite` at `0x140055932`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005598c`
- `ntoskrnl!ExDeleteResourceLite` at `0x140055932`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005598c`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsScratchMappingTable::AllocAndInit(__int64 *a1, struct UnionFs::StackEventTracer *a2)
{
  __int64 Pool2; // rax
  __int64 v5; // rdi
  unsigned int v6; // ebx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v7; // rcx
  __int64 v8; // rbx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v9; // rcx
  const char *v11; // [rsp+28h] [rbp-30h]

  Pool2 = ExAllocatePool2(64, 152, 1953318485);
  v5 = Pool2;
  if ( !Pool2 )
  {
    v6 = -1073741670;
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      (int)a2,
      (struct UnionFs::StackEventTracer *)0x1F4000E0025LL,
      (unsigned __int64)"UnionFs::UfsScratchMappingTable::AllocAndInit",
      "ORIGIN: Allocating mapping table",
      v11);
    return v6;
  }
  UnionFs::UfsPathTable::UfsPathTable(Pool2, 11);
  v6 = UnionFs::UfsPathTable::InitializeRundown((UnionFs::UfsPathTable *)v5, a2);
  if ( (v6 & 0x80000000) != 0 )
  {
    UnionFs::ProcessTraceStatusPushLocation(
      (UnionFs *)v6,
      (int)a2,
      (struct UnionFs::StackEventTracer *)0x470000E0027LL,
      (unsigned __int64)"UnionFs::UfsScratchMappingTable::AllocAndInit",
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
0x1400558ac  push    rbx
0x1400558ae  push    rbp
0x1400558af  push    rsi
0x1400558b0  push    rdi
0x1400558b1  sub     rsp, 38h
0x1400558b5  mov     rbp, rdx
0x1400558b8  mov     rsi, rcx
0x1400558bb  mov     edx, 98h
0x1400558c0  mov     r8d, 746D4655h
0x1400558c6  lea     ecx, [rdx-58h]
0x1400558c9  call    cs:__imp_ExAllocatePool2
0x1400558d0  nop     dword ptr [rax+rax+00h]
0x1400558d5  mov     rdi, rax
0x1400558d8  test    rax, rax
0x1400558db  jz      loc_1400559CE
0x1400558e1  mov     edx, 0Bh
0x1400558e6  mov     rcx, rax
0x1400558e9  call    ??0UfsPathTable@UnionFs@@IEAA@W4PATH_TABLE_CONFIGURATION@1@@Z; UnionFs::UfsPathTable::UfsPathTable(UnionFs::PATH_TABLE_CONFIGURATION)
0x1400558ee  mov     rdx, rbp; struct UnionFs::StackEventTracer *
0x1400558f1  mov     rcx, rdi; this
0x1400558f4  call    ?InitializeRundown@UfsPathTable@UnionFs@@IEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsPathTable::InitializeRundown(UnionFs::StackEventTracer &)
0x1400558f9  mov     ebx, eax
0x1400558fb  test    eax, eax
0x1400558fd  jns     short loc_140055975
0x1400558ff  lea     rax, aPushInitializi; "PUSH: Initializing rundown"
0x140055906  mov     r8, 470000E0027h; struct UnionFs::StackEventTracer *
0x140055910  lea     r9, aUnionfsUfsscra_3; "UnionFs::UfsScratchMappingTable::AllocA"...
0x140055917  mov     [rsp+58h+var_38], rax; char *
0x14005591c  mov     rdx, rbp; int
0x14005591f  mov     ecx, ebx; this
0x140055921  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140055926  mov     rcx, rdi; this
0x140055929  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x14005592e  lea     rcx, [rdi+20h]; Resource
0x140055932  call    cs:__imp_ExDeleteResourceLite
0x140055939  nop     dword ptr [rax+rax+00h]
0x14005593e  mov     rcx, [rdi+88h]; RunRefCacheAware
0x140055945  test    rcx, rcx
0x140055948  jz      short loc_140055956
0x14005594a  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140055951  nop     dword ptr [rax+rax+00h]
0x140055956  lea     rcx, [rdi+8]
0x14005595a  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x14005595f  xor     edx, edx; Tag
0x140055961  mov     rcx, rdi; P
0x140055964  call    cs:__imp_ExFreePoolWithTag
0x14005596b  nop     dword ptr [rax+rax+00h]
0x140055970  jmp     loc_1400559FA
0x140055975  mov     rbx, [rsi]
0x140055978  mov     [rsi], rdi
0x14005597b  test    rbx, rbx
0x14005597e  jz      short loc_1400559CA
0x140055980  mov     rcx, rbx; this
0x140055983  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x140055988  lea     rcx, [rbx+20h]; Resource
0x14005598c  call    cs:__imp_ExDeleteResourceLite
0x140055993  nop     dword ptr [rax+rax+00h]
0x140055998  mov     rcx, [rbx+88h]; RunRefCacheAware
0x14005599f  test    rcx, rcx
0x1400559a2  jz      short loc_1400559B0
0x1400559a4  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400559ab  nop     dword ptr [rax+rax+00h]
0x1400559b0  lea     rcx, [rbx+8]
0x1400559b4  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x1400559b9  xor     edx, edx; Tag
0x1400559bb  mov     rcx, rbx; P
0x1400559be  call    cs:__imp_ExFreePoolWithTag
0x1400559c5  nop     dword ptr [rax+rax+00h]
0x1400559ca  xor     eax, eax
0x1400559cc  jmp     short loc_1400559FC
0x1400559ce  lea     rax, aOriginAllocati_84; "ORIGIN: Allocating mapping table"
0x1400559d5  mov     ebx, 0C000009Ah
0x1400559da  mov     ecx, ebx; this
0x1400559dc  mov     [rsp+58h+var_38], rax; char *
0x1400559e1  lea     r9, aUnionfsUfsscra_3; "UnionFs::UfsScratchMappingTable::AllocA"...
0x1400559e8  mov     r8, 1F4000E0025h; struct UnionFs::StackEventTracer *
0x1400559f2  mov     rdx, rbp; int
0x1400559f5  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400559fa  mov     eax, ebx
0x1400559fc  add     rsp, 38h
0x140055a00  pop     rdi
0x140055a01  pop     rsi
0x140055a02  pop     rbp
0x140055a03  pop     rbx
0x140055a04  retn
```
