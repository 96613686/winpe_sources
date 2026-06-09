# UnionFs::UfsPathCachePayload::~UfsPathCachePayload(void)

- ea: `0x14003fcac`
- end: `0x14003fef1`
- name: `??1UfsPathCachePayload@UnionFs@@QEAA@XZ`
- size: `581`
- prototype: `void __fastcall(UnionFs::UfsPathCachePayload *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation`

## callers

- `0x14003f618`
- `0x140043860`

## callees

- `0x14000f81c`
- `0x14003b848`
- `0x14003d554`
- `0x14003fb68`
- `0x14003fc20`
- `0x14003fcac`
- `0x14003fef8`
- `0x140079dd4`
- `0x140079f68`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x14003fe06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fe1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fe9a`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fe06`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fe1d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14003fe9a`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fd55`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fdb9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fde6`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fd55`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fdb9`
- `ntoskrnl!ExFreeToLookasideListEx` at `0x14003fde6`
- `ntoskrnl!ObfDereferenceObject` at `0x14003fe57`
- `ntoskrnl!ObfDereferenceObject` at `0x14003fe57`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fd07`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fd70`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fd07`
- `ntoskrnl!ExReleaseResourceLite` at `0x14003fd70`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fd13`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fd7c`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fd13`
- `ntoskrnl!KeLeaveCriticalRegion` at `0x14003fd7c`
- `FLTMGR!FltClose` at `0x14003fe6c`
- `FLTMGR!FltClose` at `0x14003fe6c`
- `FLTMGR!FltReleaseContext` at `0x14003fe3a`
- `FLTMGR!FltReleaseContext` at `0x14003fe3a`

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
  void *v15; // rcx
  __int64 v16; // rdi
  utl::_RefCountBase *v17; // rcx
  volatile signed __int32 *v18; // rcx
  PERESOURCE Resource; // [rsp+50h] [rbp+8h] BYREF

  v1 = *((_QWORD *)this + 19) == 0;
  *(_QWORD *)this = &UnionFs::UfsPathCachePayload::`vftable';
  v2 = (UnionFs::UfsPathCachePayloadNP **)((char *)this + 144);
  if ( !v1 )
  {
    FsFltWil::AcquireResourceShared(&Resource, (char *)*v2 + 184);
    v4 = *((_QWORD *)this + 19);
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
  UnionFs::UfsPathCachePayload::TombstoneSupport::~TombstoneSupport((UnionFs::UfsPathCachePayload *)((char *)this + 168));
  v8 = (void *)*((_QWORD *)this + 19);
  if ( v8 )
  {
    UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(*((UnionFs::UfsPathCacheListItem **)this + 19));
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 992), v8);
  }
  v9 = *v2;
  if ( v9 )
  {
    UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(v9);
    ExFreeToLookasideListEx((PLOOKASIDE_LIST_EX)((char *)UnionFs::g_FilterState + 1568), v9);
  }
  utl::_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>::~_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>((char *)this + 104);
  v11 = (void *)*((_QWORD *)this + 12);
  if ( v11 )
    ExFreePoolWithTag(v11, 0);
  v12 = (void *)*((_QWORD *)this + 10);
  if ( v12 )
    ExFreePoolWithTag(v12, 0);
  v13 = (void *)*((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v13 )
    FltReleaseContext(v13);
  v14 = (void *)*((_QWORD *)this + 8);
  *((_QWORD *)this + 8) = 0;
  if ( v14 )
    ObfDereferenceObject(v14);
  v15 = (void *)*((_QWORD *)this + 7);
  if ( v15 )
    FltClose(v15);
  v16 = *((_QWORD *)this + 6);
  if ( v16 )
  {
    if ( !*(_BYTE *)(v16 + 16) )
      *(_OWORD *)v16 = 0;
    FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v16, v10);
    ExFreePoolWithTag((PVOID)v16, 0);
  }
  v17 = (utl::_RefCountBase *)*((_QWORD *)this + 5);
  if ( v17 )
    utl::_RefCountBase::_DecStrong(v17);
  v18 = (volatile signed __int32 *)*((_QWORD *)this + 3);
  if ( v18 )
  {
    if ( *((_DWORD *)v18 + 3) == 1 || _InterlockedExchangeAdd(v18 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v18 + 8LL))(v18);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x14003fcac  push    rbx
0x14003fcae  push    rbp
0x14003fcaf  push    rsi
0x14003fcb0  push    rdi
0x14003fcb1  sub     rsp, 28h
0x14003fcb5  cmp     qword ptr [rcx+98h], 0
0x14003fcbd  lea     rax, ??_7UfsPathCachePayload@UnionFs@@6B@; const UnionFs::UfsPathCachePayload::`vftable'
0x14003fcc4  mov     [rcx], rax
0x14003fcc7  lea     rdi, [rcx+90h]
0x14003fcce  mov     rbx, rcx
0x14003fcd1  jz      loc_14003FD88
0x14003fcd7  mov     rdx, [rdi]
0x14003fcda  lea     rcx, [rsp+48h+Resource]
0x14003fcdf  add     rdx, 0B8h
0x14003fce6  call    ?AcquireResourceShared@FsFltWil@@YA?AV?$unique_ptr@U_ERESOURCE@@U?$function_deleter@P6AXPEAU_ERESOURCE@@@Z$1?ReleaseResource@Details@FsFltWil@@YAX0@Z@wil@@@wistd@@AEAU_ERESOURCE@@@Z; FsFltWil::AcquireResourceShared(_ERESOURCE &)
0x14003fceb  mov     rax, [rbx+98h]
0x14003fcf2  test    rax, rax
0x14003fcf5  jz      short loc_14003FD63
0x14003fcf7  mov     rcx, [rsp+48h+Resource]; Resource
0x14003fcfc  xor     esi, esi
0x14003fcfe  mov     rbp, [rax+10h]
0x14003fd02  test    rcx, rcx
0x14003fd05  jz      short loc_14003FD1F
0x14003fd07  call    cs:__imp_ExReleaseResourceLite
0x14003fd0e  nop     dword ptr [rax+rax+00h]
0x14003fd13  call    cs:__imp_KeLeaveCriticalRegion
0x14003fd1a  nop     dword ptr [rax+rax+00h]
0x14003fd1f  xor     r9d, r9d
0x14003fd22  lea     rdx, [rsp+48h+Resource]
0x14003fd27  mov     r8, rbx
0x14003fd2a  mov     rcx, rbp
0x14003fd2d  call    ?RemoveFromCacheList@UfsPathCache@UnionFs@@QEAA?AV?$unique_ptr@VUfsPathCacheListItem@UnionFs@@U?$default_delete@VUfsPathCacheListItem@UnionFs@@@utl@@@utl@@AEAVUfsPathCachePayload@2@_N@Z; UnionFs::UfsPathCache::RemoveFromCacheList(UnionFs::UfsPathCachePayload &,bool)
0x14003fd32  mov     rbp, [rsp+48h+Resource]
0x14003fd37  test    rbp, rbp
0x14003fd3a  jz      short loc_14003FD68
0x14003fd3c  mov     rcx, rbp; this
0x14003fd3f  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x14003fd44  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003fd4b  mov     rdx, rbp; Entry
0x14003fd4e  add     rcx, 3E0h; Lookaside
0x14003fd55  call    cs:__imp_ExFreeToLookasideListEx
0x14003fd5c  nop     dword ptr [rax+rax+00h]
0x14003fd61  jmp     short loc_14003FD68
0x14003fd63  mov     rsi, [rsp+48h+Resource]
0x14003fd68  test    rsi, rsi
0x14003fd6b  jz      short loc_14003FD88
0x14003fd6d  mov     rcx, rsi; Resource
0x14003fd70  call    cs:__imp_ExReleaseResourceLite
0x14003fd77  nop     dword ptr [rax+rax+00h]
0x14003fd7c  call    cs:__imp_KeLeaveCriticalRegion
0x14003fd83  nop     dword ptr [rax+rax+00h]
0x14003fd88  lea     rcx, [rbx+0A8h]; this
0x14003fd8f  call    ??1TombstoneSupport@UfsPathCachePayload@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayload::TombstoneSupport::~TombstoneSupport(void)
0x14003fd94  mov     rsi, [rbx+98h]
0x14003fd9b  test    rsi, rsi
0x14003fd9e  jz      short loc_14003FDC5
0x14003fda0  mov     rcx, rsi; this
0x14003fda3  call    ??1UfsPathCacheListItem@UnionFs@@QEAA@XZ; UnionFs::UfsPathCacheListItem::~UfsPathCacheListItem(void)
0x14003fda8  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003fdaf  mov     rdx, rsi; Entry
0x14003fdb2  add     rcx, 3E0h; Lookaside
0x14003fdb9  call    cs:__imp_ExFreeToLookasideListEx
0x14003fdc0  nop     dword ptr [rax+rax+00h]
0x14003fdc5  mov     rdi, [rdi]
0x14003fdc8  test    rdi, rdi
0x14003fdcb  jz      short loc_14003FDF2
0x14003fdcd  mov     rcx, rdi; this
0x14003fdd0  call    ??1UfsPathCachePayloadNP@UnionFs@@QEAA@XZ; UnionFs::UfsPathCachePayloadNP::~UfsPathCachePayloadNP(void)
0x14003fdd5  mov     rcx, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14003fddc  mov     rdx, rdi; Entry
0x14003fddf  add     rcx, 620h; Lookaside
0x14003fde6  call    cs:__imp_ExFreeToLookasideListEx
0x14003fded  nop     dword ptr [rax+rax+00h]
0x14003fdf2  lea     rcx, [rbx+68h]
0x14003fdf6  call    ??1?$_HashTable@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@V12@USidHash@UfsPathCachePayload@UnionFs@@USidEqualsPred@45@V?$allocator@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@$0A@@utl@@IEAA@XZ; utl::_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>::~_HashTable<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>,UnionFs::UfsPathCachePayload::SidHash,UnionFs::UfsPathCachePayload::SidEqualsPred,utl::allocator<wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,0>(void)
0x14003fdfb  mov     rcx, [rbx+60h]; P
0x14003fdff  test    rcx, rcx
0x14003fe02  jz      short loc_14003FE12
0x14003fe04  xor     edx, edx; Tag
0x14003fe06  call    cs:__imp_ExFreePoolWithTag
0x14003fe0d  nop     dword ptr [rax+rax+00h]
0x14003fe12  mov     rcx, [rbx+50h]; P
0x14003fe16  test    rcx, rcx
0x14003fe19  jz      short loc_14003FE29
0x14003fe1b  xor     edx, edx; Tag
0x14003fe1d  call    cs:__imp_ExFreePoolWithTag
0x14003fe24  nop     dword ptr [rax+rax+00h]
0x14003fe29  mov     rcx, [rbx+48h]; Context
0x14003fe2d  mov     qword ptr [rbx+48h], 0
0x14003fe35  test    rcx, rcx
0x14003fe38  jz      short loc_14003FE46
0x14003fe3a  call    cs:__imp_FltReleaseContext
0x14003fe41  nop     dword ptr [rax+rax+00h]
0x14003fe46  mov     rcx, [rbx+40h]; Object
0x14003fe4a  mov     qword ptr [rbx+40h], 0
0x14003fe52  test    rcx, rcx
0x14003fe55  jz      short loc_14003FE63
0x14003fe57  call    cs:__imp_ObfDereferenceObject
0x14003fe5e  nop     dword ptr [rax+rax+00h]
0x14003fe63  mov     rcx, [rbx+38h]; FileHandle
0x14003fe67  test    rcx, rcx
0x14003fe6a  jz      short loc_14003FE78
0x14003fe6c  call    cs:__imp_FltClose
0x14003fe73  nop     dword ptr [rax+rax+00h]
0x14003fe78  mov     rdi, [rbx+30h]
0x14003fe7c  test    rdi, rdi
0x14003fe7f  jz      short loc_14003FEA6
0x14003fe81  cmp     byte ptr [rdi+10h], 0
0x14003fe85  jnz     short loc_14003FE8D
0x14003fe87  xorps   xmm0, xmm0
0x14003fe8a  movups  xmmword ptr [rdi], xmm0
0x14003fe8d  mov     rcx, rdi; UnicodeString
0x14003fe90  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14003fe95  xor     edx, edx; Tag
0x14003fe97  mov     rcx, rdi; P
0x14003fe9a  call    cs:__imp_ExFreePoolWithTag
0x14003fea1  nop     dword ptr [rax+rax+00h]
0x14003fea6  mov     rcx, [rbx+28h]; this
0x14003feaa  test    rcx, rcx
0x14003fead  jz      short loc_14003FEB4
0x14003feaf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14003feb4  mov     rcx, [rbx+18h]
0x14003feb8  test    rcx, rcx
0x14003febb  jz      short loc_14003FEE7
0x14003febd  mov     eax, [rcx+0Ch]
0x14003fec0  cmp     eax, 1
0x14003fec3  jz      short loc_14003FED2
0x14003fec5  or      eax, 0FFFFFFFFh
0x14003fec8  lock xadd [rcx+0Ch], eax
0x14003fecd  cmp     eax, 1
0x14003fed0  jnz     short loc_14003FEDF
0x14003fed2  nop
0x14003fed3  mov     rax, [rcx]
0x14003fed6  mov     rax, [rax+8]
0x14003feda  call    _guard_dispatch_icall
0x14003fedf  mov     qword ptr [rbx+18h], 0
0x14003fee7  add     rsp, 28h
0x14003feeb  pop     rdi
0x14003feec  pop     rsi
0x14003feed  pop     rbp
0x14003feee  pop     rbx
0x14003feef  retn
```
