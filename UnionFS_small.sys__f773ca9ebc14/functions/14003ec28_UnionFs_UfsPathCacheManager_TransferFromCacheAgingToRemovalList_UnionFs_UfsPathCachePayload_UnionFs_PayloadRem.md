# UnionFs::UfsPathCacheManager::TransferFromCacheAgingToRemovalList(UnionFs::UfsPathCachePayload &,UnionFs::PayloadRemovalReason,bool)

- ea: `0x14003ec28`
- end: `0x14003ed6d`
- name: `?TransferFromCacheAgingToRemovalList@UfsPathCacheManager@UnionFs@@QEAA_NAEAVUfsPathCachePayload@2@W4PayloadRemovalReason@2@_N@Z`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14003d6fc`
- `0x1400424ec`

## callees

- `0x14003b728`
- `0x14003d434`
- `0x14003e08c`
- `0x14003ec28`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ed2b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ed2b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ec8c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ecb8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ed3f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ec8c`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ecb8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ed3f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ec98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ecc4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ed4b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ec98`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ecc4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ed4b`

## pseudocode

```c
char __fastcall UnionFs::UfsPathCacheManager::TransferFromCacheAgingToRemovalList(
        __int64 a1,
        __int64 a2,
        int a3,
        char a4)
{
  struct _ERESOURCE *v8; // rbx
  __int64 v9; // r9
  struct _ERESOURCE **v10; // rax
  struct _ERESOURCE *v11; // rcx
  __int64 v12; // rcx
  PERESOURCE v14; // rdi
  PERESOURCE Resource; // [rsp+48h] [rbp+10h] BYREF

  v8 = 0;
  if ( !(*(unsigned __int8 (__fastcall **)(__int64))(*(_QWORD *)a2 + 40LL))(a2) )
  {
    v10 = (struct _ERESOURCE **)(*(__int64 (__fastcall **)(__int64, PERESOURCE *))(*(_QWORD *)a2 + 16LL))(a2, &Resource);
    v8 = *v10;
    *v10 = 0;
    v11 = Resource;
    Resource = 0;
    if ( v11 )
    {
      ExReleaseResourceLite(v11);
      KeLeaveCriticalRegion();
    }
  }
  v12 = *(_QWORD *)(a2 + 144);
  if ( v12 )
  {
    LOBYTE(v9) = a4;
    UnionFs::UfsPathCache::RemoveFromCacheList(*(_QWORD *)(v12 + 16), &Resource, a2, v9);
    if ( Resource )
    {
      *(_DWORD *)(a2 + 156) = a3;
      UnionFs::UfsPathCacheManager::AddToRemovalList(a1, &Resource);
      v14 = Resource;
      if ( Resource )
      {
        UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem((UnionFs::UfsPathCacheListItem *)Resource);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 992), v14);
      }
    }
    if ( v8 )
    {
      ExReleaseResourceLite(v8);
      KeLeaveCriticalRegion();
    }
    return 1;
  }
  else
  {
    if ( v8 )
    {
      ExReleaseResourceLite(v8);
      KeLeaveCriticalRegion();
    }
    return 0;
  }
}

```

## disassembly

```asm
0x14003ec28  mov     [rsp+arg_0], rbx
0x14003ec2d  mov     [rsp+arg_10], rbp
0x14003ec32  push    rsi
0x14003ec33  push    rdi
0x14003ec34  push    r14
0x14003ec36  sub     rsp, 20h
0x14003ec3a  mov     rax, [rdx]
0x14003ec3d  mov     r14, rcx
0x14003ec40  mov     rcx, rdx
0x14003ec43  mov     dil, r9b
0x14003ec46  mov     ebp, r8d
0x14003ec49  mov     rsi, rdx
0x14003ec4c  xor     ebx, ebx
0x14003ec4e  mov     rax, [rax+28h]
0x14003ec52  call    _guard_dispatch_icall
0x14003ec57  test    al, al
0x14003ec59  jnz     short loc_14003ECA4
0x14003ec5b  mov     rax, [rsi]
0x14003ec5e  lea     rdx, [rsp+38h+Resource]
0x14003ec63  mov     rcx, rsi
0x14003ec66  mov     rax, [rax+10h]
0x14003ec6a  call    _guard_dispatch_icall
0x14003ec6f  mov     rbx, [rax]
0x14003ec72  mov     qword ptr [rax], 0
0x14003ec79  mov     rcx, [rsp+38h+Resource]; Resource
0x14003ec7e  mov     [rsp+38h+Resource], 0
0x14003ec87  test    rcx, rcx
0x14003ec8a  jz      short loc_14003ECA4
0x14003ec8c  call    cs:__imp_ExReleaseResourceLite
0x14003ec93  nop     dword ptr [rax+rax+00h]
0x14003ec98  call    cs:__imp_KeLeaveCriticalRegion
0x14003ec9f  nop     dword ptr [rax+rax+00h]
0x14003eca4  mov     rcx, [rsi+90h]
0x14003ecab  test    rcx, rcx
0x14003ecae  jnz     short loc_14003ECD7
0x14003ecb0  test    rbx, rbx
0x14003ecb3  jz      short loc_14003ECD0
0x14003ecb5  mov     rcx, rbx; Resource
0x14003ecb8  call    cs:__imp_ExReleaseResourceLite
0x14003ecbf  nop     dword ptr [rax+rax+00h]
0x14003ecc4  call    cs:__imp_KeLeaveCriticalRegion
0x14003eccb  nop     dword ptr [rax+rax+00h]
0x14003ecd0  xor     al, al
0x14003ecd2  jmp     loc_14003ED59
0x14003ecd7  mov     rcx, [rcx+10h]
0x14003ecdb  lea     rdx, [rsp+38h+Resource]
0x14003ece0  mov     r9b, dil
0x14003ece3  mov     r8, rsi
0x14003ece6  call    ?RemoveFromCacheList@UfsPathCache@UnionFs@@QEAA?AV?$unique_ptr@VUfsPathCacheListItem@UnionFs@@U?$default_delete@VUfsPathCacheListItem@UnionFs@@@utl@@@utl@@AEAVUfsPathCachePayload@2@_N@Z; UnionFs::UfsPathCache::RemoveFromCacheList(UnionFs::UfsPathCachePayload &,bool)
0x14003eceb  mov     rdi, [rsp+38h+Resource]
0x14003ecf0  test    rdi, rdi
0x14003ecf3  jz      short loc_14003ED37
0x14003ecf5  lea     rdx, [rsp+38h+Resource]
0x14003ecfa  mov     [rsi+9Ch], ebp
0x14003ed00  mov     rcx, r14
0x14003ed03  call    ?AddToRemovalList@UfsPathCacheManager@UnionFs@@QEAAX$$QEAV?$unique_ptr@VUfsPathCacheListItem@UnionFs@@U?$default_delete@VUfsPathCacheListItem@UnionFs@@@utl@@@utl@@@Z; UnionFs::UfsPathCacheManager::AddToRemovalList(utl::unique_ptr<UnionFs::UfsPathCacheListItem,utl::default_delete<UnionFs::UfsPathCacheListItem>> &&)
0x14003ed08  mov     rdi, [rsp+38h+Resource]
0x14003ed0d  test    rdi, rdi
0x14003ed10  jz      short loc_14003ED37
0x14003ed12  mov     rcx, rdi; this
0x14003ed15  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x14003ed1a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003ed21  mov     rdx, rdi; Entry
0x14003ed24  add     rcx, 3E0h; Lookaside
0x14003ed2b  call    cs:__imp_ExFreeToLookasideListEx
0x14003ed32  nop     dword ptr [rax+rax+00h]
0x14003ed37  test    rbx, rbx
0x14003ed3a  jz      short loc_14003ED57
0x14003ed3c  mov     rcx, rbx; Resource
0x14003ed3f  call    cs:__imp_ExReleaseResourceLite
0x14003ed46  nop     dword ptr [rax+rax+00h]
0x14003ed4b  call    cs:__imp_KeLeaveCriticalRegion
0x14003ed52  nop     dword ptr [rax+rax+00h]
0x14003ed57  mov     al, 1
0x14003ed59  mov     rbx, [rsp+38h+arg_0]
0x14003ed5e  mov     rbp, [rsp+38h+arg_10]
0x14003ed63  add     rsp, 20h
0x14003ed67  pop     r14
0x14003ed69  pop     rdi
0x14003ed6a  pop     rsi
0x14003ed6b  retn
```
