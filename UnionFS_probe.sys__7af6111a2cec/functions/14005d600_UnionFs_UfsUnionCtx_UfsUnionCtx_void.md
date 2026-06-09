# UnionFs::UfsUnionCtx::~UfsUnionCtx(void)

- ea: `0x14005d600`
- end: `0x14005d8bc`
- name: `??1UfsUnionCtx@UnionFs@@QEAA@XZ`
- size: `700`
- prototype: `void __fastcall(UnionFs::UfsUnionCtx *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x14005cf30`
- `0x1400671c0`

## callees

- `0x1400031a0`
- `0x1400055d0`
- `0x140006168`
- `0x14001f428`
- `0x140056afc`
- `0x14005d2d8`
- `0x14005d600`
- `0x14005f920`
- `0x14005fd34`
- `0x140063344`
- `0x14007b7d0`
- `0x14007b8b0`

## import_xrefs

- `ntoskrnl!PsDereferenceSiloContext` at `0x14005d862`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005d862`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005d81b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005d81b`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d7b0`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d7eb`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d7b0`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d7eb`
- `FLTMGR!FltClose` at `0x14005d7c8`
- `FLTMGR!FltClose` at `0x14005d803`
- `FLTMGR!FltClose` at `0x14005d7c8`
- `FLTMGR!FltClose` at `0x14005d803`

## string_xrefs

- `0x14005d704`: `PUSH: RemoveUnionFromScratchMapping`
- `0x14005d76a`: `PUSH: DeleteUnionFromPathTables`
- `0x14005d75e`: `UnionFs::UfsUnionCtx::DeleteUnionFromPathTables`
- `0x14005d72a`: `PUSH: ClearPathCacheForUnion`

## pseudocode

```c
void __fastcall UnionFs::UfsUnionCtx::~UfsUnionCtx(UnionFs::UfsUnionCtx *this)
{
  int v2; // r8d
  int v3; // r9d
  int v4; // edi
  __int64 v5; // r8
  const char *v6; // rax
  void *v7; // rcx
  void *v8; // rcx
  void *v9; // rcx
  void *v10; // rcx
  struct _EX_RUNDOWN_REF_CACHE_AWARE *v11; // rcx
  __int64 v12; // rcx
  volatile signed __int32 *v13; // rcx
  char *v14; // [rsp+28h] [rbp-D8h]
  char *v15; // [rsp+28h] [rbp-D8h]
  int v16; // [rsp+50h] [rbp-B0h] BYREF
  char *v17; // [rsp+58h] [rbp-A8h] BYREF
  const char *v18; // [rsp+60h] [rbp-A0h] BYREF
  char v19[8]; // [rsp+68h] [rbp-98h] BYREF
  const char *v20; // [rsp+70h] [rbp-90h] BYREF
  int v21[188]; // [rsp+78h] [rbp-88h] BYREF

  UnionFs::StackEventTracer::StackEventTracer((UnionFs::StackEventTracer *)v21, 0x2CD00200B00uLL);
  if ( (unsigned int)dword_14009E178 > 4
    && (qword_14009E188 & 0x100) != 0
    && (qword_14009E190 & 0x100) == qword_14009E190 )
  {
    v16 = 2820;
    v17 = (char *)this + 8;
    *(_QWORD *)v19 = "UnionFs::UfsUnionCtx::~UfsUnionCtx";
    v18 = "onecore\\base\\fs\\unionfs\\sys\\unionctx.cpp";
    v20 = "Destroying union context";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(
      qword_14009E190,
      (unsigned int)&word_14009922E,
      v2,
      v3,
      (__int64)&v20,
      (__int64)v19,
      (__int64)&v18,
      (__int64)&v16,
      (__int64)&v17);
  }
  v4 = UnionFs::UfsUnionCtx::RemoveScratchFromMappingTable(this, (struct UnionFs::StackEventTracer *)v21);
  if ( v4 >= 0 )
  {
    v4 = UnionFs::UfsUnionCtx::ClearPathCacheForUnion(this, (struct UnionFs::StackEventTracer *)v21);
    if ( v4 >= 0 )
    {
      v4 = UnionFs::UfsUnionCtx::ClearEaTableForUnion(this, (struct UnionFs::StackEventTracer *)v21);
      if ( v4 >= 0 )
        goto LABEL_12;
      v5 = 0x74D00200DB8LL;
      v6 = "PUSH: ClearEaTableForUnion";
    }
    else
    {
      v5 = 0x29B00200DB6LL;
      v6 = "PUSH: ClearPathCacheForUnion";
    }
  }
  else
  {
    v5 = 0x26200200DB4LL;
    v6 = "PUSH: RemoveUnionFromScratchMapping";
  }
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v4,
    (int)v21,
    (struct UnionFs::StackEventTracer *)v5,
    (unsigned __int64)"UnionFs::UfsUnionCtx::DeleteUnionFromPathTables",
    v6,
    v14);
  UnionFs::ProcessTraceStatusPushLocation(
    (UnionFs *)(unsigned int)v4,
    (int)v21,
    (struct UnionFs::StackEventTracer *)0x2C800200B0ALL,
    (unsigned __int64)"UnionFs::UfsUnionCtx::~UfsUnionCtx",
    "PUSH: DeleteUnionFromPathTables",
    v15);
LABEL_12:
  UnionFs::StackEventTracer::~StackEventTracer((UnionFs::StackEventTracer *)v21);
  v7 = (void *)*((_QWORD *)this + 46);
  *((_QWORD *)this + 46) = 0;
  if ( v7 )
    ObfDereferenceObject(v7);
  v8 = (void *)*((_QWORD *)this + 45);
  if ( v8 )
    FltClose(v8);
  v9 = (void *)*((_QWORD *)this + 44);
  *((_QWORD *)this + 44) = 0;
  if ( v9 )
    ObfDereferenceObject(v9);
  v10 = (void *)*((_QWORD *)this + 43);
  if ( v10 )
    FltClose(v10);
  v11 = (struct _EX_RUNDOWN_REF_CACHE_AWARE *)*((_QWORD *)this + 38);
  if ( v11 )
    ExFreeCacheAwareRundownProtection(v11);
  utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>((char *)this + 216);
  utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>((char *)this + 128);
  utl::_Tree<UnionFs::UfsFileID,utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::less<UnionFs::UfsFileID>,utl::allocator<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>>,0>::~_Tree<UnionFs::UfsFileID,utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::less<UnionFs::UfsFileID>,utl::allocator<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&void FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>>,0>((char *)this + 80);
  utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>((char *)this + 48);
  v12 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v12 )
    PsDereferenceSiloContext(v12);
  v13 = *(volatile signed __int32 **)this;
  if ( *(_QWORD *)this )
  {
    if ( *((_DWORD *)v13 + 3) == 1 || _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
    *(_QWORD *)this = 0;
  }
}

```

## disassembly

```asm
0x14005d600  push    rbp
0x14005d602  push    rbx
0x14005d603  push    rdi
0x14005d604  push    r14
0x14005d606  lea     rbp, [rsp-278h]
0x14005d60e  sub     rsp, 378h
0x14005d615  mov     rax, cs:__security_cookie
0x14005d61c  xor     rax, rsp
0x14005d61f  mov     [rbp+290h+var_28], rax
0x14005d626  mov     rbx, rcx
0x14005d629  mov     rdx, 2CD00200B00h; unsigned __int64
0x14005d633  lea     rcx, [rsp+390h+var_318]; this
0x14005d638  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x14005d63d  mov     eax, cs:dword_14009E178
0x14005d643  lea     r14, aUnionfsUfsunio_31; "UnionFs::UfsUnionCtx::~UfsUnionCtx"
0x14005d64a  cmp     eax, 4
0x14005d64d  jbe     loc_14005D6E2
0x14005d653  mov     rcx, cs:qword_14009E190
0x14005d65a  mov     edx, 100h
0x14005d65f  mov     rax, cs:qword_14009E188
0x14005d666  test    rdx, rax
0x14005d669  jz      short loc_14005D6E2
0x14005d66b  mov     rax, rcx
0x14005d66e  and     rax, rdx
0x14005d671  cmp     rax, rcx
0x14005d674  jnz     short loc_14005D6E2
0x14005d676  lea     rax, [rbx+8]
0x14005d67a  mov     [rsp+390h+var_340], 0B04h
0x14005d682  mov     [rsp+390h+var_338], rax
0x14005d687  lea     rdx, word_14009922E
0x14005d68e  lea     rax, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x14005d695  mov     qword ptr [rsp+390h+var_328], r14
0x14005d69a  mov     [rsp+390h+var_330], rax
0x14005d69f  lea     rax, aDestroyingUnio; "Destroying union context"
0x14005d6a6  mov     [rsp+390h+var_320], rax
0x14005d6ab  lea     rax, [rsp+390h+var_338]
0x14005d6b0  mov     [rsp+390h+var_350], rax
0x14005d6b5  lea     rax, [rsp+390h+var_340]
0x14005d6ba  mov     [rsp+390h+var_358], rax
0x14005d6bf  lea     rax, [rsp+390h+var_330]
0x14005d6c4  mov     [rsp+390h+var_360], rax
0x14005d6c9  lea     rax, [rsp+390h+var_328]
0x14005d6ce  mov     [rsp+390h+var_368], rax; char *
0x14005d6d3  lea     rax, [rsp+390h+var_320]
0x14005d6d8  mov     [rsp+390h+var_370], rax
0x14005d6dd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x14005d6e2  lea     rdx, [rsp+390h+var_318]; struct UnionFs::StackEventTracer *
0x14005d6e7  mov     rcx, rbx; this
0x14005d6ea  call    ?RemoveScratchFromMappingTable@UfsUnionCtx@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::RemoveScratchFromMappingTable(UnionFs::StackEventTracer &)
0x14005d6ef  lea     rdx, [rsp+390h+var_318]; struct UnionFs::StackEventTracer *
0x14005d6f4  mov     edi, eax
0x14005d6f6  test    eax, eax
0x14005d6f8  jns     short loc_14005D70D
0x14005d6fa  mov     r8, 26200200DB4h
0x14005d704  lea     rax, aPushRemoveunio; "PUSH: RemoveUnionFromScratchMapping"
0x14005d70b  jmp     short loc_14005D757
0x14005d70d  mov     rcx, rbx; this
0x14005d710  call    ?ClearPathCacheForUnion@UfsUnionCtx@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::ClearPathCacheForUnion(UnionFs::StackEventTracer &)
0x14005d715  lea     rdx, [rsp+390h+var_318]; struct UnionFs::StackEventTracer *
0x14005d71a  mov     edi, eax
0x14005d71c  test    eax, eax
0x14005d71e  jns     short loc_14005D733
0x14005d720  mov     r8, 29B00200DB6h
0x14005d72a  lea     rax, aPushClearpathc; "PUSH: ClearPathCacheForUnion"
0x14005d731  jmp     short loc_14005D757
0x14005d733  mov     rcx, rbx; this
0x14005d736  call    ?ClearEaTableForUnion@UfsUnionCtx@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::ClearEaTableForUnion(UnionFs::StackEventTracer &)
0x14005d73b  mov     edi, eax
0x14005d73d  test    eax, eax
0x14005d73f  jns     short loc_14005D78F
0x14005d741  lea     rdx, [rsp+390h+var_318]; int
0x14005d746  mov     r8, 74D00200DB8h; struct UnionFs::StackEventTracer *
0x14005d750  lea     rax, aPushCleareatab; "PUSH: ClearEaTableForUnion"
0x14005d757  mov     ecx, edi; this
0x14005d759  mov     [rsp+390h+var_370], rax; char *
0x14005d75e  lea     r9, aUnionfsUfsunio_13; "UnionFs::UfsUnionCtx::DeleteUnionFromPa"...
0x14005d765  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005d76a  lea     rax, aPushDeleteunio; "PUSH: DeleteUnionFromPathTables"
0x14005d771  mov     r9, r14; unsigned __int64
0x14005d774  mov     r8, 2C800200B0Ah; struct UnionFs::StackEventTracer *
0x14005d77e  mov     [rsp+390h+var_370], rax; char *
0x14005d783  lea     rdx, [rsp+390h+var_318]; int
0x14005d788  mov     ecx, edi; this
0x14005d78a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005d78f  lea     rcx, [rsp+390h+var_318]; this
0x14005d794  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x14005d799  mov     rcx, [rbx+170h]; Object
0x14005d7a0  mov     qword ptr [rbx+170h], 0
0x14005d7ab  test    rcx, rcx
0x14005d7ae  jz      short loc_14005D7BC
0x14005d7b0  call    cs:__imp_ObfDereferenceObject
0x14005d7b7  nop     dword ptr [rax+rax+00h]
0x14005d7bc  mov     rcx, [rbx+168h]; FileHandle
0x14005d7c3  test    rcx, rcx
0x14005d7c6  jz      short loc_14005D7D4
0x14005d7c8  call    cs:__imp_FltClose
0x14005d7cf  nop     dword ptr [rax+rax+00h]
0x14005d7d4  mov     rcx, [rbx+160h]; Object
0x14005d7db  mov     qword ptr [rbx+160h], 0
0x14005d7e6  test    rcx, rcx
0x14005d7e9  jz      short loc_14005D7F7
0x14005d7eb  call    cs:__imp_ObfDereferenceObject
0x14005d7f2  nop     dword ptr [rax+rax+00h]
0x14005d7f7  mov     rcx, [rbx+158h]; FileHandle
0x14005d7fe  test    rcx, rcx
0x14005d801  jz      short loc_14005D80F
0x14005d803  call    cs:__imp_FltClose
0x14005d80a  nop     dword ptr [rax+rax+00h]
0x14005d80f  mov     rcx, [rbx+130h]; RunRefCacheAware
0x14005d816  test    rcx, rcx
0x14005d819  jz      short loc_14005D827
0x14005d81b  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14005d822  nop     dword ptr [rax+rax+00h]
0x14005d827  lea     rcx, [rbx+0D8h]
0x14005d82e  call    ??1?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(void)
0x14005d833  lea     rcx, [rbx+80h]
0x14005d83a  call    ??1?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(void)
0x14005d83f  lea     rcx, [rbx+50h]
0x14005d843  call    ??1?$_Tree@VUfsFileID@UnionFs@@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@U?$less@VUfsFileID@UnionFs@@@4@V?$allocator@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@@4@$0A@@utl@@IEAA@XZ; utl::_Tree<UnionFs::UfsFileID,utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::less<UnionFs::UfsFileID>,utl::allocator<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>>,0>::~_Tree<UnionFs::UfsFileID,utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::less<UnionFs::UfsFileID>,utl::allocator<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>>,0>(void)
0x14005d848  lea     rcx, [rbx+30h]
0x14005d84c  call    ??1?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(void)
0x14005d851  mov     rcx, [rbx+20h]
0x14005d855  mov     qword ptr [rbx+20h], 0
0x14005d85d  test    rcx, rcx
0x14005d860  jz      short loc_14005D86E
0x14005d862  call    cs:__imp_PsDereferenceSiloContext
0x14005d869  nop     dword ptr [rax+rax+00h]
0x14005d86e  mov     rcx, [rbx]
0x14005d871  test    rcx, rcx
0x14005d874  jz      short loc_14005D89F
0x14005d876  mov     eax, [rcx+0Ch]
0x14005d879  cmp     eax, 1
0x14005d87c  jz      short loc_14005D88B
0x14005d87e  or      eax, 0FFFFFFFFh
0x14005d881  lock xadd [rcx+0Ch], eax
0x14005d886  cmp     eax, 1
0x14005d889  jnz     short loc_14005D898
0x14005d88b  nop
0x14005d88c  mov     rax, [rcx]
0x14005d88f  mov     rax, [rax+8]
0x14005d893  call    _guard_dispatch_icall
0x14005d898  mov     qword ptr [rbx], 0
0x14005d89f  mov     rcx, [rbp+290h+var_28]
0x14005d8a6  xor     rcx, rsp; StackCookie
0x14005d8a9  call    __security_check_cookie
0x14005d8ae  add     rsp, 378h
0x14005d8b5  pop     r14
0x14005d8b7  pop     rdi
0x14005d8b8  pop     rbx
0x14005d8b9  pop     rbp
0x14005d8ba  retn
```
