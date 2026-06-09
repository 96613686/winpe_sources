# UnionFs::UfsPathCachePayload::AllocateCacheControl(UnionFs::UfsPathCache &,_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::StackEventTracer &)

- ea: `0x140041308`
- end: `0x1400414bf`
- name: `?AllocateCacheControl@UfsPathCachePayload@UnionFs@@QEAAJAEAVUfsPathCache@2@AEBU_FLT_INSTANCE@@$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14003c0ec`

## callees

- `0x14003b728`
- `0x140041308`
- `0x140056ac4`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140041410`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140041410`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004135a`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x14004135a`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400413da`
- `ntoskrnl!ExReleaseResourceLite` at `0x1400413da`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400413e6`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x1400413e6`

## string_xrefs

- `0x140041452`: `ORIGIN: Allocating cache control`
- `0x140041465`: `UnionFs::UfsPathCachePayload::AllocateCacheControl`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::AllocateCacheControl(
        unsigned __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 *a4,
        int a5)
{
  volatile signed __int32 **v5; // rax
  volatile signed __int32 *v7; // rcx
  volatile signed __int32 *v11; // rbx
  __int64 v12; // rsi
  volatile signed __int32 *v13; // rax
  volatile signed __int32 *v14; // rdi
  __int64 v15; // rcx
  struct _ERESOURCE *v16; // rcx
  UnionFs::UfsPathCacheListItem *v17; // rsi
  const char *v19; // [rsp+28h] [rbp-30h]
  PERESOURCE Resource; // [rsp+60h] [rbp+8h] BYREF

  v5 = (volatile signed __int32 **)(a1 + 24);
  v7 = *(volatile signed __int32 **)(a1 + 24);
  if ( v7 )
  {
    _InterlockedIncrement(v7 + 3);
    v11 = *v5;
    v12 = a1 & -(__int64)(v5 != 0);
  }
  else
  {
    v11 = 0;
    v12 = 0;
  }
  v13 = (volatile signed __int32 *)ExAllocateFromLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState
                                                                                    + 992));
  v14 = v13;
  if ( v13 )
  {
    *(_OWORD *)v13 = 0;
    *((_QWORD *)v13 + 2) = a2;
    *((_QWORD *)v13 + 3) = a3;
    v15 = *a4;
    *a4 = 0;
    *((_QWORD *)v13 + 4) = v15;
    *((_QWORD *)v13 + 5) = v12;
    *((_QWORD *)v13 + 6) = v11;
    if ( v11 )
      _InterlockedIncrement(v11 + 3);
    *((_QWORD *)v13 + 7) = 0;
    (*(void (__fastcall **)(unsigned __int64, PERESOURCE *))(*(_QWORD *)a1 + 16LL))(a1, &Resource);
    v16 = Resource;
    v17 = *(UnionFs::UfsPathCacheListItem **)(a1 + 144);
    *(_QWORD *)(a1 + 144) = v14;
    Resource = 0;
    if ( v16 )
    {
      ExReleaseResourceLite(v16);
      KeLeaveCriticalRegion();
    }
    if ( v17 )
    {
      UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(v17);
      ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 992), v17);
    }
    if ( v11 && (*((_DWORD *)v11 + 3) == 1 || _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC000009ALL,
      a5,
      (struct UnionFs::StackEventTracer *)0x42D001204A8LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::AllocateCacheControl",
      "ORIGIN: Allocating cache control",
      v19);
    if ( v11 && (*((_DWORD *)v11 + 3) == 1 || _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1) )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
    return 3221225626LL;
  }
}

```

## disassembly

```asm
0x140041308  mov     [rsp+arg_8], rbx
0x14004130d  mov     [rsp+arg_10], rbp
0x140041312  push    rsi
0x140041313  push    rdi
0x140041314  push    r12
0x140041316  push    r14
0x140041318  push    r15
0x14004131a  sub     rsp, 30h
0x14004131e  lea     rax, [rcx+18h]
0x140041322  mov     r14, rcx
0x140041325  mov     rcx, [rax]
0x140041328  mov     r15, r9
0x14004132b  mov     rbp, r8
0x14004132e  mov     r12, rdx
0x140041331  test    rcx, rcx
0x140041334  jz      short loc_140041348
0x140041336  lock inc dword ptr [rcx+0Ch]
0x14004133a  mov     rbx, [rax]
0x14004133d  neg     rax
0x140041340  sbb     rsi, rsi
0x140041343  and     rsi, r14
0x140041346  jmp     short loc_14004134C
0x140041348  xor     ebx, ebx
0x14004134a  xor     esi, esi
0x14004134c  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140041353  add     rcx, 3E0h; Lookaside
0x14004135a  call    cs:__imp_ExAllocateFromLookasideListEx
0x140041361  nop     dword ptr [rax+rax+00h]
0x140041366  mov     rdi, rax
0x140041369  test    rax, rax
0x14004136c  jz      loc_14004144A
0x140041372  xorps   xmm0, xmm0
0x140041375  movups  xmmword ptr [rax], xmm0
0x140041378  mov     [rax+10h], r12
0x14004137c  mov     [rax+18h], rbp
0x140041380  mov     rcx, [r15]
0x140041383  mov     qword ptr [r15], 0
0x14004138a  mov     [rax+20h], rcx
0x14004138e  mov     [rax+28h], rsi
0x140041392  mov     [rax+30h], rbx
0x140041396  test    rbx, rbx
0x140041399  jz      short loc_14004139F
0x14004139b  lock inc dword ptr [rbx+0Ch]
0x14004139f  xor     eax, eax
0x1400413a1  lea     rdx, [rsp+58h+Resource]
0x1400413a6  mov     [rdi+38h], rax
0x1400413aa  mov     rcx, r14
0x1400413ad  mov     rax, [r14]
0x1400413b0  mov     rax, [rax+10h]
0x1400413b4  call    _guard_dispatch_icall
0x1400413b9  mov     rcx, [rsp+58h+Resource]; Resource
0x1400413be  mov     rsi, [r14+90h]
0x1400413c5  mov     [r14+90h], rdi
0x1400413cc  mov     [rsp+58h+Resource], 0
0x1400413d5  test    rcx, rcx
0x1400413d8  jz      short loc_1400413F2
0x1400413da  call    cs:__imp_ExReleaseResourceLite
0x1400413e1  nop     dword ptr [rax+rax+00h]
0x1400413e6  call    cs:__imp_KeLeaveCriticalRegion
0x1400413ed  nop     dword ptr [rax+rax+00h]
0x1400413f2  test    rsi, rsi
0x1400413f5  jz      short loc_14004141C
0x1400413f7  mov     rcx, rsi; this
0x1400413fa  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x1400413ff  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140041406  mov     rdx, rsi; Entry
0x140041409  add     rcx, 3E0h; Lookaside
0x140041410  call    cs:__imp_ExFreeToLookasideListEx
0x140041417  nop     dword ptr [rax+rax+00h]
0x14004141c  test    rbx, rbx
0x14004141f  jz      short loc_140041446
0x140041421  mov     eax, [rbx+0Ch]
0x140041424  cmp     eax, 1
0x140041427  jz      short loc_140041436
0x140041429  or      eax, 0FFFFFFFFh
0x14004142c  lock xadd [rbx+0Ch], eax
0x140041431  cmp     eax, 1
0x140041434  jnz     short loc_140041446
0x140041436  nop
0x140041437  mov     rcx, rbx
0x14004143a  mov     rax, [rbx]
0x14004143d  mov     rax, [rax+8]
0x140041441  call    _guard_dispatch_icall
0x140041446  xor     eax, eax
0x140041448  jmp     short loc_1400414A7
0x14004144a  mov     rdx, qword ptr [rsp+58h+arg_20]; int
0x140041452  lea     rax, aOriginAllocati_13; "ORIGIN: Allocating cache control"
0x140041459  mov     edi, 0C000009Ah
0x14004145e  mov     [rsp+58h+var_38], rax; char *
0x140041463  mov     ecx, edi; this
0x140041465  lea     r9, aUnionfsUfspath_20; "UnionFs::UfsPathCachePayload::AllocateC"...
0x14004146c  mov     r8, 42D001204A8h; struct UnionFs::StackEventTracer *
0x140041476  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004147b  test    rbx, rbx
0x14004147e  jz      short loc_1400414A5
0x140041480  mov     eax, [rbx+0Ch]
0x140041483  cmp     eax, 1
0x140041486  jz      short loc_140041495
0x140041488  or      eax, 0FFFFFFFFh
0x14004148b  lock xadd [rbx+0Ch], eax
0x140041490  cmp     eax, 1
0x140041493  jnz     short loc_1400414A5
0x140041495  nop
0x140041496  mov     rcx, [rbx]
0x140041499  mov     rax, [rcx+8]
0x14004149d  mov     rcx, rbx
0x1400414a0  call    _guard_dispatch_icall
0x1400414a5  mov     eax, edi
0x1400414a7  mov     rbx, [rsp+58h+arg_8]
0x1400414ac  mov     rbp, [rsp+58h+arg_10]
0x1400414b1  add     rsp, 30h
0x1400414b5  pop     r15
0x1400414b7  pop     r14
0x1400414b9  pop     r12
0x1400414bb  pop     rdi
0x1400414bc  pop     rsi
0x1400414bd  retn
```
