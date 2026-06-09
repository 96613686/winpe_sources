# UnionFs::UfsPathCachePayload::~UfsPathCachePayload(void)

- ea: `0x14003fb3c`
- end: `0x14003fd6a`
- name: `??1UfsPathCachePayload@UnionFs@@QEAA@XZ`
- size: `558`
- prototype: `void __fastcall(UnionFs::UfsPathCachePayload *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14003f4f8`
- `0x1400436e0`

## callees

- `0x14000f7fc`
- `0x14003b728`
- `0x14003d434`
- `0x14003fa40`
- `0x14003fab0`
- `0x14003fb3c`
- `0x14003fd70`
- `0x140079ab4`
- `0x140079c48`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003fc96`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fd13`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fc96`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fd13`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fbe5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fc49`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fc76`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fbe5`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fc49`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fc76`
- `ntoskrnl!ObfDereferenceObject` at `0x14003fcd0`
- `ntoskrnl!ObfDereferenceObject` at `0x14003fcd0`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fb97`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fc00`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fb97`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fc00`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fba3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fc0c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fba3`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fc0c`
- `FLTMGR!FltClose` at `0x14003fce5`
- `FLTMGR!FltClose` at `0x14003fce5`
- `FLTMGR!FltReleaseContext` at `0x14003fcb3`
- `FLTMGR!FltReleaseContext` at `0x14003fcb3`

## pseudocode

```c
void __fastcall UnionFs::UfsPathCachePayload::~UfsPathCachePayload(UnionFs::UfsPathCachePayload *this)
{
  bool v1; // zf
  UnionFs::UfsPathCachePayloadNP **v2; // rdi
  __int64 v4; // rax
  struct _ERESOURCE *v5; // rsi
  __int64 v6; // rbp
  PERESOURCE v7; // rbp
  void *v8; // rsi
  UnionFs::UfsPathCachePayloadNP *v9; // rdi
  struct _UNICODE_STRING *v10; // rdx
  void *v11; // rcx
  void *v12; // rcx
  void *v13; // rcx
  void *v14; // rcx
  __int64 v15; // rdi
  utl::_RefCountBase *v16; // rcx
  volatile signed __int32 *v17; // rcx
  PERESOURCE Resource; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 18) == 0;
  *(_QWORD *)this = &UnionFs::UfsPathCachePayload::`vftable';
  v2 = (UnionFs::UfsPathCachePayloadNP **)((char *)this + 136);
  if ( !v1 )
  {
    FsFltWil::AcquireResourceShared(&Resource, (char *)*v2 + 184);
    v4 = *((_QWORD *)this + 18);
    if ( v4 )
    {
      v5 = 0;
      v6 = *(_QWORD *)(v4 + 16);
      if ( Resource )
      {
        ExReleaseResourceLite(Resource);
        KeLeaveCriticalRegion();
      }
      UnionFs::UfsPathCache::RemoveFromCacheList(v6, &Resource, this, 0);
      v7 = Resource;
      if ( Resource )
      {
        UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem((UnionFs::UfsPathCacheListItem *)Resource);
        ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 992), v7);
      }
    }
    else
    {
      v5 = Resource;
    }
    if ( v5 )
    {
      ExReleaseResourceLite(v5);
      KeLeaveCriticalRegion();
    }
  }
  UnionFs::UfsPathCachePayload::TombstoneSupport::~TombstoneSupport((UnionFs::UfsPathCachePayload *)((char *)this + 160));
  v8 = (void *)*((_QWORD *)this + 18);
  if ( v8 )
  {
    UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(*((UnionFs::UfsPathCacheListItem **)this + 18));
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 992), v8);
  }
  v9 = *v2;
  if ( v9 )
  {
    UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v9);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v9);
  }
  utl::_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>::~_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>((char *)this + 96);
  v11 = (void *)*((_QWORD *)this + 10);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  v12 = (void *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v12 )
    FltReleaseContext(v12);
  v13 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v13 )
    ObfDereferenceObject(v13);
  v14 = (void *)*((_QWORD *)this + 7);
  if ( v14 )
    FltClose(v14);
  v15 = *((_QWORD *)this + 6);
  if ( v15 )
  {
    if ( !*(_BYTE *)(v15 + 16) )
      *(_OWORD *)v15 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v15, v10);
    ExFreePoolWithTag((PVOID)v15, 0);
  }
  v16 = (utl::_RefCountBase *)*((_QWORD *)this + 5);
  if ( v16 )
    utl::_RefCountBase::_DecStrong(v16);
  v17 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v17 )
  {
    if ( *((_DWORD *)v17 + 3) == 1 || _InterlockedExchangeAdd(v17 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v17 + 8LL))(v17);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x14003fb3c  push    rbx
0x14003fb3e  push    rbp
0x14003fb3f  push    rsi
0x14003fb40  push    rdi
0x14003fb41  sub     rsp, 28h
0x14003fb45  cmp     qword ptr [rcx+90h], 0
0x14003fb4d  lea     rax, ??_7UfsPathCachePayload@UnionFs@@6B@; const UnionFs::UfsPathCachePayload::`vftable'
0x14003fb54  mov     [rcx], rax
0x14003fb57  lea     rdi, [rcx+88h]
0x14003fb5e  mov     rbx, rcx
0x14003fb61  jz      loc_14003FC18
0x14003fb67  mov     rdx, [rdi]
0x14003fb6a  lea     rcx, [rsp+48h+Resource]
0x14003fb6f  add     rdx, 0B8h
0x14003fb76  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x14003fb7b  mov     rax, [rbx+90h]
0x14003fb82  test    rax, rax
0x14003fb85  jz      short loc_14003FBF3
0x14003fb87  mov     rcx, [rsp+48h+Resource]; Resource
0x14003fb8c  xor     esi, esi
0x14003fb8e  mov     rbp, [rax+10h]
0x14003fb92  test    rcx, rcx
0x14003fb95  jz      short loc_14003FBAF
0x14003fb97  call    cs:__imp_ExReleaseResourceLite
0x14003fb9e  nop     dword ptr [rax+rax+00h]
0x14003fba3  call    cs:__imp_KeLeaveCriticalRegion
0x14003fbaa  nop     dword ptr [rax+rax+00h]
0x14003fbaf  xor     r9d, r9d
0x14003fbb2  lea     rdx, [rsp+48h+Resource]
0x14003fbb7  mov     r8, rbx
0x14003fbba  mov     rcx, rbp
0x14003fbbd  call    ?RemoveFromCacheList@UfsPathCache@UnionFs@@QEAA?AV?$unique_ptr@VUfsPathCacheListItem@UnionFs@@U?$default_delete@VUfsPathCacheListItem@UnionFs@@@utl@@@utl@@AEAVUfsPathCachePayload@2@_N@Z; UnionFs::UfsPathCache::RemoveFromCacheList(UnionFs::UfsPathCachePayload &,bool)
0x14003fbc2  mov     rbp, [rsp+48h+Resource]
0x14003fbc7  test    rbp, rbp
0x14003fbca  jz      short loc_14003FBF8
0x14003fbcc  mov     rcx, rbp; this
0x14003fbcf  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x14003fbd4  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003fbdb  mov     rdx, rbp; Entry
0x14003fbde  add     rcx, 3E0h; Lookaside
0x14003fbe5  call    cs:__imp_ExFreeToLookasideListEx
0x14003fbec  nop     dword ptr [rax+rax+00h]
0x14003fbf1  jmp     short loc_14003FBF8
0x14003fbf3  mov     rsi, [rsp+48h+Resource]
0x14003fbf8  test    rsi, rsi
0x14003fbfb  jz      short loc_14003FC18
0x14003fbfd  mov     rcx, rsi; Resource
0x14003fc00  call    cs:__imp_ExReleaseResourceLite
0x14003fc07  nop     dword ptr [rax+rax+00h]
0x14003fc0c  call    cs:__imp_KeLeaveCriticalRegion
0x14003fc13  nop     dword ptr [rax+rax+00h]
0x14003fc18  lea     rcx, [rbx+0A0h]; this
0x14003fc1f  call    ??1TombstoneSupport@UfsPathCachePayload@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayload::TombstoneSupport::~TombstoneSupport(void)
0x14003fc24  mov     rsi, [rbx+90h]
0x14003fc2b  test    rsi, rsi
0x14003fc2e  jz      short loc_14003FC55
0x14003fc30  mov     rcx, rsi; this
0x14003fc33  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x14003fc38  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003fc3f  mov     rdx, rsi; Entry
0x14003fc42  add     rcx, 3E0h; Lookaside
0x14003fc49  call    cs:__imp_ExFreeToLookasideListEx
0x14003fc50  nop     dword ptr [rax+rax+00h]
0x14003fc55  mov     rdi, [rdi]
0x14003fc58  test    rdi, rdi
0x14003fc5b  jz      short loc_14003FC82
0x14003fc5d  mov     rcx, rdi; this
0x14003fc60  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x14003fc65  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003fc6c  mov     rdx, rdi; Entry
0x14003fc6f  add     rcx, 620h; Lookaside
0x14003fc76  call    cs:__imp_ExFreeToLookasideListEx
0x14003fc7d  nop     dword ptr [rax+rax+00h]
0x14003fc82  lea     rcx, [rbx+60h]
0x14003fc86  call    ??1?$_HashTable@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@V12@USidHash@UfsPathCachePayload@UnionFs@@USidEqualsPred@45@V?$allocator@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@$0A@@utl@@IEAA@XZ; utl::_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>::~_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>(void)
0x14003fc8b  mov     rcx, [rbx+50h]; P
0x14003fc8f  test    rcx, rcx
0x14003fc92  jz      short loc_14003FCA2
0x14003fc94  xor     edx, edx; Tag
0x14003fc96  call    cs:__imp_ExFreePoolWithTag
0x14003fc9d  nop     dword ptr [rax+rax+00h]
0x14003fca2  mov     rcx, [rbx+48h]; Context
0x14003fca6  mov     qword ptr [rbx+48h], 0
0x14003fcae  test    rcx, rcx
0x14003fcb1  jz      short loc_14003FCBF
0x14003fcb3  call    cs:__imp_FltReleaseContext
0x14003fcba  nop     dword ptr [rax+rax+00h]
0x14003fcbf  mov     rcx, [rbx+40h]; Object
0x14003fcc3  mov     qword ptr [rbx+40h], 0
0x14003fccb  test    rcx, rcx
0x14003fcce  jz      short loc_14003FCDC
0x14003fcd0  call    cs:__imp_ObfDereferenceObject
0x14003fcd7  nop     dword ptr [rax+rax+00h]
0x14003fcdc  mov     rcx, [rbx+38h]; FileHandle
0x14003fce0  test    rcx, rcx
0x14003fce3  jz      short loc_14003FCF1
0x14003fce5  call    cs:__imp_FltClose
0x14003fcec  nop     dword ptr [rax+rax+00h]
0x14003fcf1  mov     rdi, [rbx+30h]
0x14003fcf5  test    rdi, rdi
0x14003fcf8  jz      short loc_14003FD1F
0x14003fcfa  cmp     byte ptr [rdi+10h], 0
0x14003fcfe  jnz     short loc_14003FD06
0x14003fd00  xorps   xmm0, xmm0
0x14003fd03  movups  xmmword ptr [rdi], xmm0
0x14003fd06  mov     rcx, rdi; UnicodeString
0x14003fd09  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003fd0e  xor     edx, edx; Tag
0x14003fd10  mov     rcx, rdi; P
0x14003fd13  call    cs:__imp_ExFreePoolWithTag
0x14003fd1a  nop     dword ptr [rax+rax+00h]
0x14003fd1f  mov     rcx, [rbx+28h]; this
0x14003fd23  test    rcx, rcx
0x14003fd26  jz      short loc_14003FD2D
0x14003fd28  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003fd2d  mov     rcx, [rbx+18h]
0x14003fd31  test    rcx, rcx
0x14003fd34  jz      short loc_14003FD60
0x14003fd36  mov     eax, [rcx+0Ch]
0x14003fd39  cmp     eax, 1
0x14003fd3c  jz      short loc_14003FD4B
0x14003fd3e  or      eax, 0FFFFFFFFh
0x14003fd41  lock xadd [rcx+0Ch], eax
0x14003fd46  cmp     eax, 1
0x14003fd49  jnz     short loc_14003FD58
0x14003fd4b  nop
0x14003fd4c  mov     rax, [rcx]
0x14003fd4f  mov     rax, [rax+8]
0x14003fd53  call    _guard_dispatch_icall
0x14003fd58  mov     qword ptr [rbx+18h], 0
0x14003fd60  add     rsp, 28h
0x14003fd64  pop     rdi
0x14003fd65  pop     rsi
0x14003fd66  pop     rbp
0x14003fd67  pop     rbx
0x14003fd68  retn
```
