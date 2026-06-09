# UnionFs::UfsEaTable::AllocAndInit(utl::unique_ptr<UnionFs::UfsEaTable,utl::default_delete<UnionFs::UfsEaTable>> &,UnionFs::StackEventTracer &)

- ea: `0x1400233dc`
- end: `0x140023536`
- name: `?AllocAndInit@UfsEaTable@UnionFs@@SAJAEAV?$unique_ptr@VUfsEaTable@UnionFs@@U?$default_delete@VUfsEaTable@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
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
- `0x1400233dc`
- `0x140047fdc`
- `0x140056c44`
- `0x140056c7c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140023494`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400234ee`
- `ntoskrnl!ExFreePoolWithTag` at `0x140023494`
- `ntoskrnl!ExFreePoolWithTag` at `0x1400234ee`
- `ntoskrnl!ExAllocatePool2` at `0x1400233f9`
- `ntoskrnl!ExAllocatePool2` at `0x1400233f9`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14002347a`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400234d4`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14002347a`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x1400234d4`
- `ntoskrnl!ExDeleteResourceLite` at `0x140023462`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400234bc`
- `ntoskrnl!ExDeleteResourceLite` at `0x140023462`
- `ntoskrnl!ExDeleteResourceLite` at `0x1400234bc`

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
0x1400233dc  push    rbx
0x1400233de  push    rbp
0x1400233df  push    rsi
0x1400233e0  push    rdi
0x1400233e1  sub     rsp, 38h
0x1400233e5  mov     rbp, rdx
0x1400233e8  mov     rsi, rcx
0x1400233eb  mov     edx, 98h
0x1400233f0  mov     r8d, 74654655h
0x1400233f6  lea     ecx, [rdx-58h]
0x1400233f9  call    cs:__imp_ExAllocatePool2
0x140023400  nop     dword ptr [rax+rax+00h]
0x140023405  mov     rdi, rax
0x140023408  test    rax, rax
0x14002340b  jz      loc_1400234FE
0x140023411  mov     edx, 6
0x140023416  mov     rcx, rax
0x140023419  call    ??0UfsPathTable@UnionFs@@IEAA@W4PATH_TABLE_CONFIGURATION@1@@Z; UnionFs::UfsPathTable::UfsPathTable(UnionFs::PATH_TABLE_CONFIGURATION)
0x14002341e  mov     rdx, rbp; struct UnionFs::StackEventTracer *
0x140023421  mov     rcx, rdi; this
0x140023424  call    ?InitializeRundown@UfsPathTable@UnionFs@@IEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsPathTable::InitializeRundown(UnionFs::StackEventTracer &)
0x140023429  mov     ebx, eax
0x14002342b  test    eax, eax
0x14002342d  jns     short loc_1400234A5
0x14002342f  lea     rax, aPushInitializi; "PUSH: Initializing rundown"
0x140023436  mov     r8, 55400080026h; struct UnionFs::StackEventTracer *
0x140023440  lea     r9, aUnionfsUfseata; "UnionFs::UfsEaTable::AllocAndInit"
0x140023447  mov     [rsp+58h+var_38], rax; char *
0x14002344c  mov     rdx, rbp; int
0x14002344f  mov     ecx, ebx; this
0x140023451  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140023456  mov     rcx, rdi; this
0x140023459  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x14002345e  lea     rcx, [rdi+20h]; Resource
0x140023462  call    cs:__imp_ExDeleteResourceLite
0x140023469  nop     dword ptr [rax+rax+00h]
0x14002346e  mov     rcx, [rdi+88h]; RunRefCacheAware
0x140023475  test    rcx, rcx
0x140023478  jz      short loc_140023486
0x14002347a  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x140023481  nop     dword ptr [rax+rax+00h]
0x140023486  lea     rcx, [rdi+8]
0x14002348a  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x14002348f  xor     edx, edx; Tag
0x140023491  mov     rcx, rdi; P
0x140023494  call    cs:__imp_ExFreePoolWithTag
0x14002349b  nop     dword ptr [rax+rax+00h]
0x1400234a0  jmp     loc_14002352A
0x1400234a5  mov     rbx, [rsi]
0x1400234a8  mov     [rsi], rdi
0x1400234ab  test    rbx, rbx
0x1400234ae  jz      short loc_1400234FA
0x1400234b0  mov     rcx, rbx; this
0x1400234b3  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x1400234b8  lea     rcx, [rbx+20h]; Resource
0x1400234bc  call    cs:__imp_ExDeleteResourceLite
0x1400234c3  nop     dword ptr [rax+rax+00h]
0x1400234c8  mov     rcx, [rbx+88h]; RunRefCacheAware
0x1400234cf  test    rcx, rcx
0x1400234d2  jz      short loc_1400234E0
0x1400234d4  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x1400234db  nop     dword ptr [rax+rax+00h]
0x1400234e0  lea     rcx, [rbx+8]
0x1400234e4  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x1400234e9  xor     edx, edx; Tag
0x1400234eb  mov     rcx, rbx; P
0x1400234ee  call    cs:__imp_ExFreePoolWithTag
0x1400234f5  nop     dword ptr [rax+rax+00h]
0x1400234fa  xor     eax, eax
0x1400234fc  jmp     short loc_14002352C
0x1400234fe  lea     rax, aOriginAllocati_70; "ORIGIN: Allocating ea table"
0x140023505  mov     ebx, 0C000009Ah
0x14002350a  mov     ecx, ebx; this
0x14002350c  mov     [rsp+58h+var_38], rax; char *
0x140023511  lea     r9, aUnionfsUfseata; "UnionFs::UfsEaTable::AllocAndInit"
0x140023518  mov     r8, 55300080024h; struct UnionFs::StackEventTracer *
0x140023522  mov     rdx, rbp; int
0x140023525  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14002352a  mov     eax, ebx
0x14002352c  add     rsp, 38h
0x140023530  pop     rdi
0x140023531  pop     rsi
0x140023532  pop     rbp
0x140023533  pop     rbx
0x140023534  retn
```
