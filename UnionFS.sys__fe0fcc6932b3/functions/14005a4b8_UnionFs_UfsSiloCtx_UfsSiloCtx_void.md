# UnionFs::UfsSiloCtx::~UfsSiloCtx(void)

- ea: `0x14005a4b8`
- end: `0x14005a599`
- name: `??1UfsSiloCtx@UnionFs@@QEAA@XZ`
- size: `225`
- prototype: `void __fastcall(UnionFs::UfsSiloCtx *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14005a5a0`

## callees

- `0x140005c00`
- `0x1400096a4`
- `0x14003b7f4`
- `0x14005a4b8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005a50c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a52e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a581`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a50c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a52e`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a581`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005a4f2`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005a567`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005a4f2`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005a567`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005a4da`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005a54f`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005a4da`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005a54f`

## pseudocode

```c
void __fastcall UnionFs::UfsSiloCtx::~UfsSiloCtx(UnionFs::UfsSiloCtx *this)
{
  __int64 v1; // rbx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v3; // rcx
  void *v4; // rbx
  __int64 v5; // rbx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v6; // rcx

  v1 = *((_QWORD *)this + 3);
  if ( v1 )
  {
    UnionFs::UfsPathTable::EmptyAndRunDownTable(*((UnionFs::UfsPathTable **)this + 3));
    ExDeleteResourceLite((PERESOURCE)(v1 + 32));
    v3 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v1 + 136);
    if ( v3 )
      ExFreeCacheAwareRundownProtection(v3);
    utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(v1 + 8);
    ExFreePoolWithTag((PVOID)v1, 0);
  }
  v4 = (void *)*((_QWORD *)this + 2);
  if ( v4 )
  {
    UnionFs::UfsPathCache::~UfsPathCache(*((UnionFs::UfsPathCache **)this + 2));
    ExFreePoolWithTag(v4, 0);
  }
  v5 = *((_QWORD *)this + 1);
  if ( v5 )
  {
    UnionFs::UfsPathTable::EmptyAndRunDownTable(*((UnionFs::UfsPathTable **)this + 1));
    ExDeleteResourceLite((PERESOURCE)(v5 + 32));
    v6 = *(struct _EX_RUNDOWN_REF_CACHE_AWARE **)(v5 + 136);
    if ( v6 )
      ExFreeCacheAwareRundownProtection(v6);
    utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(v5 + 8);
    ExFreePoolWithTag((PVOID)v5, 0);
  }
}

```

## disassembly

```asm
0x14005a4b8  mov     [rsp+arg_0], rbx
0x14005a4bd  push    rdi
0x14005a4be  sub     rsp, 20h
0x14005a4c2  mov     rbx, [rcx+18h]
0x14005a4c6  mov     rdi, rcx
0x14005a4c9  test    rbx, rbx
0x14005a4cc  jz      short loc_14005A518
0x14005a4ce  mov     rcx, rbx; this
0x14005a4d1  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x14005a4d6  lea     rcx, [rbx+20h]; Resource
0x14005a4da  call    cs:__imp_ExDeleteResourceLite
0x14005a4e1  nop     dword ptr [rax+rax+00h]
0x14005a4e6  mov     rcx, [rbx+88h]; RunRefCacheAware
0x14005a4ed  test    rcx, rcx
0x14005a4f0  jz      short loc_14005A4FE
0x14005a4f2  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14005a4f9  nop     dword ptr [rax+rax+00h]
0x14005a4fe  lea     rcx, [rbx+8]
0x14005a502  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x14005a507  xor     edx, edx; Tag
0x14005a509  mov     rcx, rbx; P
0x14005a50c  call    cs:__imp_ExFreePoolWithTag
0x14005a513  nop     dword ptr [rax+rax+00h]
0x14005a518  mov     rbx, [rdi+10h]
0x14005a51c  test    rbx, rbx
0x14005a51f  jz      short loc_14005A53A
0x14005a521  mov     rcx, rbx; this
0x14005a524  call    ??1UfsPathCache@UnionFs@@QEAA@XZ; UnionFs::UfsPathCache::~UfsPathCache(void)
0x14005a529  xor     edx, edx; Tag
0x14005a52b  mov     rcx, rbx; P
0x14005a52e  call    cs:__imp_ExFreePoolWithTag
0x14005a535  nop     dword ptr [rax+rax+00h]
0x14005a53a  mov     rbx, [rdi+8]
0x14005a53e  test    rbx, rbx
0x14005a541  jz      short loc_14005A58D
0x14005a543  mov     rcx, rbx; this
0x14005a546  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x14005a54b  lea     rcx, [rbx+20h]; Resource
0x14005a54f  call    cs:__imp_ExDeleteResourceLite
0x14005a556  nop     dword ptr [rax+rax+00h]
0x14005a55b  mov     rcx, [rbx+88h]; RunRefCacheAware
0x14005a562  test    rcx, rcx
0x14005a565  jz      short loc_14005A573
0x14005a567  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14005a56e  nop     dword ptr [rax+rax+00h]
0x14005a573  lea     rcx, [rbx+8]
0x14005a577  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x14005a57c  xor     edx, edx; Tag
0x14005a57e  mov     rcx, rbx; P
0x14005a581  call    cs:__imp_ExFreePoolWithTag
0x14005a588  nop     dword ptr [rax+rax+00h]
0x14005a58d  mov     rbx, [rsp+28h+arg_0]
0x14005a592  add     rsp, 20h
0x14005a596  pop     rdi
0x14005a597  retn
```
