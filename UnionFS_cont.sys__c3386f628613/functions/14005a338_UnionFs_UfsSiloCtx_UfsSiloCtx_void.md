# UnionFs::UfsSiloCtx::~UfsSiloCtx(void)

- ea: `0x14005a338`
- end: `0x14005a419`
- name: `??1UfsSiloCtx@UnionFs@@QEAA@XZ`
- size: `225`
- prototype: `void __fastcall(UnionFs::UfsSiloCtx *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14005a420`

## callees

- `0x140005c00`
- `0x1400096d4`
- `0x14003b6d4`
- `0x14005a338`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14005a38c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a3ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a401`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a38c`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a3ae`
- `ntoskrnl!ExFreePoolWithTag` at `0x14005a401`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005a372`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005a3e7`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005a372`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005a3e7`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005a35a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005a3cf`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005a35a`
- `ntoskrnl!ExDeleteResourceLite` at `0x14005a3cf`

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
0x14005a338  mov     [rsp+arg_0], rbx
0x14005a33d  push    rdi
0x14005a33e  sub     rsp, 20h
0x14005a342  mov     rbx, [rcx+18h]
0x14005a346  mov     rdi, rcx
0x14005a349  test    rbx, rbx
0x14005a34c  jz      short loc_14005A398
0x14005a34e  mov     rcx, rbx; this
0x14005a351  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x14005a356  lea     rcx, [rbx+20h]; Resource
0x14005a35a  call    cs:__imp_ExDeleteResourceLite
0x14005a361  nop     dword ptr [rax+rax+00h]
0x14005a366  mov     rcx, [rbx+88h]; RunRefCacheAware
0x14005a36d  test    rcx, rcx
0x14005a370  jz      short loc_14005A37E
0x14005a372  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14005a379  nop     dword ptr [rax+rax+00h]
0x14005a37e  lea     rcx, [rbx+8]
0x14005a382  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x14005a387  xor     edx, edx; Tag
0x14005a389  mov     rcx, rbx; P
0x14005a38c  call    cs:__imp_ExFreePoolWithTag
0x14005a393  nop     dword ptr [rax+rax+00h]
0x14005a398  mov     rbx, [rdi+10h]
0x14005a39c  test    rbx, rbx
0x14005a39f  jz      short loc_14005A3BA
0x14005a3a1  mov     rcx, rbx; this
0x14005a3a4  call    ??1UfsPathCache@UnionFs@@QEAA@XZ; UnionFs::UfsPathCache::~UfsPathCache(void)
0x14005a3a9  xor     edx, edx; Tag
0x14005a3ab  mov     rcx, rbx; P
0x14005a3ae  call    cs:__imp_ExFreePoolWithTag
0x14005a3b5  nop     dword ptr [rax+rax+00h]
0x14005a3ba  mov     rbx, [rdi+8]
0x14005a3be  test    rbx, rbx
0x14005a3c1  jz      short loc_14005A40D
0x14005a3c3  mov     rcx, rbx; this
0x14005a3c6  call    ?EmptyAndRunDownTable@UfsPathTable@UnionFs@@QEAAXXZ; UnionFs::UfsPathTable::EmptyAndRunDownTable(void)
0x14005a3cb  lea     rcx, [rbx+20h]; Resource
0x14005a3cf  call    cs:__imp_ExDeleteResourceLite
0x14005a3d6  nop     dword ptr [rax+rax+00h]
0x14005a3db  mov     rcx, [rbx+88h]; RunRefCacheAware
0x14005a3e2  test    rcx, rcx
0x14005a3e5  jz      short loc_14005A3F3
0x14005a3e7  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14005a3ee  nop     dword ptr [rax+rax+00h]
0x14005a3f3  lea     rcx, [rbx+8]
0x14005a3f7  call    ??1?$list@VUfsInstanceTierNode@UnionFs@@V?$allocator@VUfsInstanceTierNode@UnionFs@@@utl@@@utl@@QEAA@XZ; utl::list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>::~list<UnionFs::UfsInstanceTierNode,utl::allocator<UnionFs::UfsInstanceTierNode>>(void)
0x14005a3fc  xor     edx, edx; Tag
0x14005a3fe  mov     rcx, rbx; P
0x14005a401  call    cs:__imp_ExFreePoolWithTag
0x14005a408  nop     dword ptr [rax+rax+00h]
0x14005a40d  mov     rbx, [rsp+28h+arg_0]
0x14005a412  add     rsp, 20h
0x14005a416  pop     rdi
0x14005a417  retn
```
