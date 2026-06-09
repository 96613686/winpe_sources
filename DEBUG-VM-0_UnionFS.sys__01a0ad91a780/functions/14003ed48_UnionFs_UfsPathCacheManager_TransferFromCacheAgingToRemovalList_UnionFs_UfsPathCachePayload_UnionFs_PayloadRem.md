# UnionFs::UfsPathCacheManager::TransferFromCacheAgingToRemovalList(UnionFs::UfsPathCachePayload &,UnionFs::PayloadRemovalReason,bool)

- ea: `0x14003ed48`
- end: `0x14003ee8d`
- name: `?TransferFromCacheAgingToRemovalList@UfsPathCacheManager@UnionFs@@QEAA_NAEAVUfsPathCachePayload@2@W4PayloadRemovalReason@2@_N@Z`
- size: `325`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation`

## callers

- `0x14003d81c`
- `0x140042674`

## callees

- `0x14003b848`
- `0x14003d554`
- `0x14003e1ac`
- `0x14003ed48`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ee4b`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003ee4b`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003edac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003edd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ee5f`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003edac`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003edd8`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003ee5f`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003edb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ede4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ee6b`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003edb8`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ede4`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003ee6b`

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
  v12 = *(_QWORD *)(a2 + 152);
  if ( v12 )
  {
    LOBYTE(v9) = a4;
    UnionFs::UfsPathCache::RemoveFromCacheList(*(_QWORD *)(v12 + 16), &Resource, a2, v9);
    if ( Resource )
    {
      *(_DWORD *)(a2 + 164) = a3;
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
0x14003ed48  mov     [rsp+arg_0], rbx
0x14003ed4d  mov     [rsp+arg_10], rbp
0x14003ed52  push    rsi
0x14003ed53  push    rdi
0x14003ed54  push    r14
0x14003ed56  sub     rsp, 20h
0x14003ed5a  mov     rax, [rdx]
0x14003ed5d  mov     r14, rcx
0x14003ed60  mov     rcx, rdx
0x14003ed63  mov     dil, r9b
0x14003ed66  mov     ebp, r8d
0x14003ed69  mov     rsi, rdx
0x14003ed6c  xor     ebx, ebx
0x14003ed6e  mov     rax, [rax+28h]
0x14003ed72  call    _guard_dispatch_icall
0x14003ed77  test    al, al
0x14003ed79  jnz     short loc_14003EDC4
0x14003ed7b  mov     rax, [rsi]
0x14003ed7e  lea     rdx, [rsp+38h+Resource]
0x14003ed83  mov     rcx, rsi
0x14003ed86  mov     rax, [rax+10h]
0x14003ed8a  call    _guard_dispatch_icall
0x14003ed8f  mov     rbx, [rax]
0x14003ed92  mov     qword ptr [rax], 0
0x14003ed99  mov     rcx, [rsp+38h+Resource]; Resource
0x14003ed9e  mov     [rsp+38h+Resource], 0
0x14003eda7  test    rcx, rcx
0x14003edaa  jz      short loc_14003EDC4
0x14003edac  call    cs:__imp_ExReleaseResourceLite
0x14003edb3  nop     dword ptr [rax+rax+00h]
0x14003edb8  call    cs:__imp_KeLeaveCriticalRegion
0x14003edbf  nop     dword ptr [rax+rax+00h]
0x14003edc4  mov     rcx, [rsi+98h]
0x14003edcb  test    rcx, rcx
0x14003edce  jnz     short loc_14003EDF7
0x14003edd0  test    rbx, rbx
0x14003edd3  jz      short loc_14003EDF0
0x14003edd5  mov     rcx, rbx; Resource
0x14003edd8  call    cs:__imp_ExReleaseResourceLite
0x14003eddf  nop     dword ptr [rax+rax+00h]
0x14003ede4  call    cs:__imp_KeLeaveCriticalRegion
0x14003edeb  nop     dword ptr [rax+rax+00h]
0x14003edf0  xor     al, al
0x14003edf2  jmp     loc_14003EE79
0x14003edf7  mov     rcx, [rcx+10h]
0x14003edfb  lea     rdx, [rsp+38h+Resource]
0x14003ee00  mov     r9b, dil
0x14003ee03  mov     r8, rsi
0x14003ee06  call    ?RemoveFromCacheList@UfsPathCache@UnionFs@@QEAA?AV?$unique_ptr@VUfsPathCacheListItem@UnionFs@@U?$default_delete@VUfsPathCacheListItem@UnionFs@@@utl@@@utl@@AEAVUfsPathCachePayload@2@_N@Z; UnionFs::UfsPathCache::RemoveFromCacheList(UnionFs::UfsPathCachePayload &,bool)
0x14003ee0b  mov     rdi, [rsp+38h+Resource]
0x14003ee10  test    rdi, rdi
0x14003ee13  jz      short loc_14003EE57
0x14003ee15  lea     rdx, [rsp+38h+Resource]
0x14003ee1a  mov     [rsi+0A4h], ebp
0x14003ee20  mov     rcx, r14
0x14003ee23  call    ?AddToRemovalList@UfsPathCacheManager@UnionFs@@QEAAX$$QEAV?$unique_ptr@VUfsPathCacheListItem@UnionFs@@U?$default_delete@VUfsPathCacheListItem@UnionFs@@@utl@@@utl@@@Z; UnionFs::UfsPathCacheManager::AddToRemovalList(utl::unique_ptr<UnionFs::UfsPathCacheListItem,utl::default_delete<UnionFs::UfsPathCacheListItem>> &&)
0x14003ee28  mov     rdi, [rsp+38h+Resource]
0x14003ee2d  test    rdi, rdi
0x14003ee30  jz      short loc_14003EE57
0x14003ee32  mov     rcx, rdi; this
0x14003ee35  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x14003ee3a  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003ee41  mov     rdx, rdi; Entry
0x14003ee44  add     rcx, 3E0h; Lookaside
0x14003ee4b  call    cs:__imp_ExFreeToLookasideListEx
0x14003ee52  nop     dword ptr [rax+rax+00h]
0x14003ee57  test    rbx, rbx
0x14003ee5a  jz      short loc_14003EE77
0x14003ee5c  mov     rcx, rbx; Resource
0x14003ee5f  call    cs:__imp_ExReleaseResourceLite
0x14003ee66  nop     dword ptr [rax+rax+00h]
0x14003ee6b  call    cs:__imp_KeLeaveCriticalRegion
0x14003ee72  nop     dword ptr [rax+rax+00h]
0x14003ee77  mov     al, 1
0x14003ee79  mov     rbx, [rsp+38h+arg_0]
0x14003ee7e  mov     rbp, [rsp+38h+arg_10]
0x14003ee83  add     rsp, 20h
0x14003ee87  pop     r14
0x14003ee89  pop     rdi
0x14003ee8a  pop     rsi
0x14003ee8b  retn
```
