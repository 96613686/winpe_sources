# UnionFs::UfsPathCachePayload::AllocateCacheControl(UnionFs::UfsPathCache &,_FLT_INSTANCE const &,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::StackEventTracer &)

- ea: `0x140041490`
- end: `0x140041647`
- name: `?AllocateCacheControl@UfsPathCachePayload@UnionFs@@QEAAJAEAVUfsPathCache@2@AEBU_FLT_INSTANCE@@$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@utl@@AEAVStackEventTracer@2@@Z`
- size: `439`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, installer_update`

## callers

- `0x14003c20c`

## callees

- `0x14003b848`
- `0x140041490`
- `0x140056c44`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreeToLookasideListEx` at `0x140041598`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x140041598`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400414e2`
- `ntoskrnl!ExAllocateFromLookasideListEx` at `0x1400414e2`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041562`
- `ntoskrnl!ExReleaseResourceLite` at `0x140041562`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004156e`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14004156e`

## string_xrefs

- `0x1400415da`: `ORIGIN: Allocating cache control`
- `0x1400415ed`: `UnionFs::UfsPathCachePayload::AllocateCacheControl`

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
    v17 = *(UnionFs::UfsPathCacheListItem **)(a1 + 152);
    *(_QWORD *)(a1 + 152) = v14;
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
      (struct UnionFs::StackEventTracer *)0x42D001204C1LL,
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
0x140041490  mov     [rsp+arg_8], rbx
0x140041495  mov     [rsp+arg_10], rbp
0x14004149a  push    rsi
0x14004149b  push    rdi
0x14004149c  push    r12
0x14004149e  push    r14
0x1400414a0  push    r15
0x1400414a2  sub     rsp, 30h
0x1400414a6  lea     rax, [rcx+18h]
0x1400414aa  mov     r14, rcx
0x1400414ad  mov     rcx, [rax]
0x1400414b0  mov     r15, r9
0x1400414b3  mov     rbp, r8
0x1400414b6  mov     r12, rdx
0x1400414b9  test    rcx, rcx
0x1400414bc  jz      short loc_1400414D0
0x1400414be  lock inc dword ptr [rcx+0Ch]
0x1400414c2  mov     rbx, [rax]
0x1400414c5  neg     rax
0x1400414c8  sbb     rsi, rsi
0x1400414cb  and     rsi, r14
0x1400414ce  jmp     short loc_1400414D4
0x1400414d0  xor     ebx, ebx
0x1400414d2  xor     esi, esi
0x1400414d4  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400414db  add     rcx, 3E0h; Lookaside
0x1400414e2  call    cs:__imp_ExAllocateFromLookasideListEx
0x1400414e9  nop     dword ptr [rax+rax+00h]
0x1400414ee  mov     rdi, rax
0x1400414f1  test    rax, rax
0x1400414f4  jz      loc_1400415D2
0x1400414fa  xorps   xmm0, xmm0
0x1400414fd  movups  xmmword ptr [rax], xmm0
0x140041500  mov     [rax+10h], r12
0x140041504  mov     [rax+18h], rbp
0x140041508  mov     rcx, [r15]
0x14004150b  mov     qword ptr [r15], 0
0x140041512  mov     [rax+20h], rcx
0x140041516  mov     [rax+28h], rsi
0x14004151a  mov     [rax+30h], rbx
0x14004151e  test    rbx, rbx
0x140041521  jz      short loc_140041527
0x140041523  lock inc dword ptr [rbx+0Ch]
0x140041527  xor     eax, eax
0x140041529  lea     rdx, [rsp+58h+Resource]
0x14004152e  mov     [rdi+38h], rax
0x140041532  mov     rcx, r14
0x140041535  mov     rax, [r14]
0x140041538  mov     rax, [rax+10h]
0x14004153c  call    _guard_dispatch_icall
0x140041541  mov     rcx, [rsp+58h+Resource]; Resource
0x140041546  mov     rsi, [r14+98h]
0x14004154d  mov     [r14+98h], rdi
0x140041554  mov     [rsp+58h+Resource], 0
0x14004155d  test    rcx, rcx
0x140041560  jz      short loc_14004157A
0x140041562  call    cs:__imp_ExReleaseResourceLite
0x140041569  nop     dword ptr [rax+rax+00h]
0x14004156e  call    cs:__imp_KeLeaveCriticalRegion
0x140041575  nop     dword ptr [rax+rax+00h]
0x14004157a  test    rsi, rsi
0x14004157d  jz      short loc_1400415A4
0x14004157f  mov     rcx, rsi; this
0x140041582  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x140041587  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14004158e  mov     rdx, rsi; Entry
0x140041591  add     rcx, 3E0h; Lookaside
0x140041598  call    cs:__imp_ExFreeToLookasideListEx
0x14004159f  nop     dword ptr [rax+rax+00h]
0x1400415a4  test    rbx, rbx
0x1400415a7  jz      short loc_1400415CE
0x1400415a9  mov     eax, [rbx+0Ch]
0x1400415ac  cmp     eax, 1
0x1400415af  jz      short loc_1400415BE
0x1400415b1  or      eax, 0FFFFFFFFh
0x1400415b4  lock xadd [rbx+0Ch], eax
0x1400415b9  cmp     eax, 1
0x1400415bc  jnz     short loc_1400415CE
0x1400415be  nop
0x1400415bf  mov     rcx, rbx
0x1400415c2  mov     rax, [rbx]
0x1400415c5  mov     rax, [rax+8]
0x1400415c9  call    _guard_dispatch_icall
0x1400415ce  xor     eax, eax
0x1400415d0  jmp     short loc_14004162F
0x1400415d2  mov     rdx, qword ptr [rsp+58h+arg_20]; int
0x1400415da  lea     rax, aOriginAllocati_13; "ORIGIN: Allocating cache control"
0x1400415e1  mov     edi, 0C000009Ah
0x1400415e6  mov     [rsp+58h+var_38], rax; char *
0x1400415eb  mov     ecx, edi; this
0x1400415ed  lea     r9, aUnionfsUfspath_20; "UnionFs::UfsPathCachePayload::AllocateC"...
0x1400415f4  mov     r8, 42D001204C1h; struct UnionFs::StackEventTracer *
0x1400415fe  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140041603  test    rbx, rbx
0x140041606  jz      short loc_14004162D
0x140041608  mov     eax, [rbx+0Ch]
0x14004160b  cmp     eax, 1
0x14004160e  jz      short loc_14004161D
0x140041610  or      eax, 0FFFFFFFFh
0x140041613  lock xadd [rbx+0Ch], eax
0x140041618  cmp     eax, 1
0x14004161b  jnz     short loc_14004162D
0x14004161d  nop
0x14004161e  mov     rcx, [rbx]
0x140041621  mov     rax, [rcx+8]
0x140041625  mov     rcx, rbx
0x140041628  call    _guard_dispatch_icall
0x14004162d  mov     eax, edi
0x14004162f  mov     rbx, [rsp+58h+arg_8]
0x140041634  mov     rbp, [rsp+58h+arg_10]
0x140041639  add     rsp, 30h
0x14004163d  pop     r15
0x14004163f  pop     r14
0x140041641  pop     r12
0x140041643  pop     rdi
0x140041644  pop     rsi
0x140041645  retn
```
