# UnionFs::UfsUnionCtx::~UfsUnionCtx(void)

- ea: `0x14005d780`
- end: `0x14005da3c`
- name: `??1UfsUnionCtx@UnionFs@@QEAA@XZ`
- size: `700`
- prototype: `void __fastcall(UnionFs::UfsUnionCtx *__hidden this)`
- caller_count: `2`
- callee_count: `12`
- tags: ``

## callers

- `0x14005d0b0`
- `0x140067340`

## callees

- `0x1400031a0`
- `0x1400055d0`
- `0x140006168`
- `0x14001f4c8`
- `0x140056c7c`
- `0x14005d458`
- `0x14005d780`
- `0x14005faa0`
- `0x14005feb4`
- `0x1400634c4`
- `0x14007baf0`
- `0x14007bbd0`

## import_xrefs

- `ntoskrnl!PsDereferenceSiloContext` at `0x14005d9e2`
- `ntoskrnl!PsDereferenceSiloContext` at `0x14005d9e2`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005d99b`
- `ntoskrnl!ExFreeCacheAwareRundownProtection` at `0x14005d99b`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d930`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d96b`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d930`
- `ntoskrnl!ObfDereferenceObject` at `0x14005d96b`
- `FLTMGR!FltClose` at `0x14005d948`
- `FLTMGR!FltClose` at `0x14005d983`
- `FLTMGR!FltClose` at `0x14005d948`
- `FLTMGR!FltClose` at `0x14005d983`

## string_xrefs

- `0x14005d884`: `PUSH: RemoveUnionFromScratchMapping`
- `0x14005d8ea`: `PUSH: DeleteUnionFromPathTables`
- `0x14005d8aa`: `PUSH: ClearPathCacheForUnion`
- `0x14005d8de`: `UnionFs::UfsUnionCtx::DeleteUnionFromPathTables`

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
      (unsigned int)&byte_14009931F,
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
0x14005d780  push    rbp
0x14005d782  push    rbx
0x14005d783  push    rdi
0x14005d784  push    r14
0x14005d786  lea     rbp, [rsp-278h]
0x14005d78e  sub     rsp, 378h
0x14005d795  mov     rax, cs:__security_cookie
0x14005d79c  xor     rax, rsp
0x14005d79f  mov     [rbp+290h+var_28], rax
0x14005d7a6  mov     rbx, rcx
0x14005d7a9  mov     rdx, 2CD00200B00h; unsigned __int64
0x14005d7b3  lea     rcx, [rsp+390h+var_318]; this
0x14005d7b8  call    ??0StackEventTracer@UnionFs@@QEAA@_K@Z; UnionFs::StackEventTracer::StackEventTracer(unsigned __int64)
0x14005d7bd  mov     eax, cs:dword_14009E178
0x14005d7c3  lea     r14, aUnionfsUfsunio_31; "UnionFs::UfsUnionCtx::~UfsUnionCtx"
0x14005d7ca  cmp     eax, 4
0x14005d7cd  jbe     loc_14005D862
0x14005d7d3  mov     rcx, cs:qword_14009E190
0x14005d7da  mov     edx, 100h
0x14005d7df  mov     rax, cs:qword_14009E188
0x14005d7e6  test    rdx, rax
0x14005d7e9  jz      short loc_14005D862
0x14005d7eb  mov     rax, rcx
0x14005d7ee  and     rax, rdx
0x14005d7f1  cmp     rax, rcx
0x14005d7f4  jnz     short loc_14005D862
0x14005d7f6  lea     rax, [rbx+8]
0x14005d7fa  mov     [rsp+390h+var_340], 0B04h
0x14005d802  mov     [rsp+390h+var_338], rax
0x14005d807  lea     rdx, byte_14009931F
0x14005d80e  lea     rax, aOnecoreBaseFsU_7; "onecore\\base\\fs\\unionfs\\sys\\unionc"...
0x14005d815  mov     qword ptr [rsp+390h+var_328], r14
0x14005d81a  mov     [rsp+390h+var_330], rax
0x14005d81f  lea     rax, aDestroyingUnio; "Destroying union context"
0x14005d826  mov     [rsp+390h+var_320], rax
0x14005d82b  lea     rax, [rsp+390h+var_338]
0x14005d830  mov     [rsp+390h+var_350], rax
0x14005d835  lea     rax, [rsp+390h+var_340]
0x14005d83a  mov     [rsp+390h+var_358], rax
0x14005d83f  lea     rax, [rsp+390h+var_330]
0x14005d844  mov     [rsp+390h+var_360], rax
0x14005d849  lea     rax, [rsp+390h+var_328]
0x14005d84e  mov     [rsp+390h+var_368], rax; char *
0x14005d853  lea     rax, [rsp+390h+var_320]
0x14005d858  mov     [rsp+390h+var_370], rax
0x14005d85d  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByRef<16> const &)
0x14005d862  lea     rdx, [rsp+390h+var_318]; struct UnionFs::StackEventTracer *
0x14005d867  mov     rcx, rbx; this
0x14005d86a  call    ?RemoveScratchFromMappingTable@UfsUnionCtx@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::RemoveScratchFromMappingTable(UnionFs::StackEventTracer &)
0x14005d86f  lea     rdx, [rsp+390h+var_318]; struct UnionFs::StackEventTracer *
0x14005d874  mov     edi, eax
0x14005d876  test    eax, eax
0x14005d878  jns     short loc_14005D88D
0x14005d87a  mov     r8, 26200200DB4h
0x14005d884  lea     rax, aPushRemoveunio; "PUSH: RemoveUnionFromScratchMapping"
0x14005d88b  jmp     short loc_14005D8D7
0x14005d88d  mov     rcx, rbx; this
0x14005d890  call    ?ClearPathCacheForUnion@UfsUnionCtx@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::ClearPathCacheForUnion(UnionFs::StackEventTracer &)
0x14005d895  lea     rdx, [rsp+390h+var_318]; struct UnionFs::StackEventTracer *
0x14005d89a  mov     edi, eax
0x14005d89c  test    eax, eax
0x14005d89e  jns     short loc_14005D8B3
0x14005d8a0  mov     r8, 29B00200DB6h
0x14005d8aa  lea     rax, aPushClearpathc; "PUSH: ClearPathCacheForUnion"
0x14005d8b1  jmp     short loc_14005D8D7
0x14005d8b3  mov     rcx, rbx; this
0x14005d8b6  call    ?ClearEaTableForUnion@UfsUnionCtx@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z; UnionFs::UfsUnionCtx::ClearEaTableForUnion(UnionFs::StackEventTracer &)
0x14005d8bb  mov     edi, eax
0x14005d8bd  test    eax, eax
0x14005d8bf  jns     short loc_14005D90F
0x14005d8c1  lea     rdx, [rsp+390h+var_318]; int
0x14005d8c6  mov     r8, 74D00200DB8h; struct UnionFs::StackEventTracer *
0x14005d8d0  lea     rax, aPushCleareatab; "PUSH: ClearEaTableForUnion"
0x14005d8d7  mov     ecx, edi; this
0x14005d8d9  mov     [rsp+390h+var_370], rax; char *
0x14005d8de  lea     r9, aUnionfsUfsunio_13; "UnionFs::UfsUnionCtx::DeleteUnionFromPa"...
0x14005d8e5  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005d8ea  lea     rax, aPushDeleteunio; "PUSH: DeleteUnionFromPathTables"
0x14005d8f1  mov     r9, r14; unsigned __int64
0x14005d8f4  mov     r8, 2C800200B0Ah; struct UnionFs::StackEventTracer *
0x14005d8fe  mov     [rsp+390h+var_370], rax; char *
0x14005d903  lea     rdx, [rsp+390h+var_318]; int
0x14005d908  mov     ecx, edi; this
0x14005d90a  call    ?ProcessTraceStatusPushLocation@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusPushLocation(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14005d90f  lea     rcx, [rsp+390h+var_318]; this
0x14005d914  call    ??1StackEventTracer@UnionFs@@QEAA@XZ; UnionFs::StackEventTracer::~StackEventTracer(void)
0x14005d919  mov     rcx, [rbx+170h]; Object
0x14005d920  mov     qword ptr [rbx+170h], 0
0x14005d92b  test    rcx, rcx
0x14005d92e  jz      short loc_14005D93C
0x14005d930  call    cs:__imp_ObfDereferenceObject
0x14005d937  nop     dword ptr [rax+rax+00h]
0x14005d93c  mov     rcx, [rbx+168h]; FileHandle
0x14005d943  test    rcx, rcx
0x14005d946  jz      short loc_14005D954
0x14005d948  call    cs:__imp_FltClose
0x14005d94f  nop     dword ptr [rax+rax+00h]
0x14005d954  mov     rcx, [rbx+160h]; Object
0x14005d95b  mov     qword ptr [rbx+160h], 0
0x14005d966  test    rcx, rcx
0x14005d969  jz      short loc_14005D977
0x14005d96b  call    cs:__imp_ObfDereferenceObject
0x14005d972  nop     dword ptr [rax+rax+00h]
0x14005d977  mov     rcx, [rbx+158h]; FileHandle
0x14005d97e  test    rcx, rcx
0x14005d981  jz      short loc_14005D98F
0x14005d983  call    cs:__imp_FltClose
0x14005d98a  nop     dword ptr [rax+rax+00h]
0x14005d98f  mov     rcx, [rbx+130h]; RunRefCacheAware
0x14005d996  test    rcx, rcx
0x14005d999  jz      short loc_14005D9A7
0x14005d99b  call    cs:__imp_ExFreeCacheAwareRundownProtection
0x14005d9a2  nop     dword ptr [rax+rax+00h]
0x14005d9a7  lea     rcx, [rbx+0D8h]
0x14005d9ae  call    ??1?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(void)
0x14005d9b3  lea     rcx, [rbx+80h]
0x14005d9ba  call    ??1?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(void)
0x14005d9bf  lea     rcx, [rbx+50h]
0x14005d9c3  call    ??1?$_Tree@VUfsFileID@UnionFs@@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@U?$less@VUfsFileID@UnionFs@@@4@V?$allocator@U?$pair@$$CBVUfsFileID@UnionFs@@V?$unique_struct@U_UNICODE_STRING@@P6AXPEAU1@@Z$1?FreeUnicodeString@Details@FsFltWil@@YAX0@Z$$T$0A@@wil@@@utl@@@4@$0A@@utl@@IEAA@XZ; utl::_Tree<UnionFs::UfsFileID,utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::less<UnionFs::UfsFileID>,utl::allocator<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>>,0>::~_Tree<UnionFs::UfsFileID,utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>,utl::less<UnionFs::UfsFileID>,utl::allocator<utl::pair<UnionFs::UfsFileID const,wil::unique_struct<_UNICODE_STRING,void (*)(_UNICODE_STRING *),&FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *),std::nullptr_t,0>>>,0>(void)
0x14005d9c8  lea     rcx, [rbx+30h]
0x14005d9cc  call    ??1?$vector@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@V?$allocator@V?$shared_ptr@VUfsTablePayload@UnionFs@@@utl@@@2@@utl@@QEAA@XZ; utl::vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>::~vector<utl::shared_ptr<UnionFs::UfsTablePayload>,utl::allocator<utl::shared_ptr<UnionFs::UfsTablePayload>>>(void)
0x14005d9d1  mov     rcx, [rbx+20h]
0x14005d9d5  mov     qword ptr [rbx+20h], 0
0x14005d9dd  test    rcx, rcx
0x14005d9e0  jz      short loc_14005D9EE
0x14005d9e2  call    cs:__imp_PsDereferenceSiloContext
0x14005d9e9  nop     dword ptr [rax+rax+00h]
0x14005d9ee  mov     rcx, [rbx]
0x14005d9f1  test    rcx, rcx
0x14005d9f4  jz      short loc_14005DA1F
0x14005d9f6  mov     eax, [rcx+0Ch]
0x14005d9f9  cmp     eax, 1
0x14005d9fc  jz      short loc_14005DA0B
0x14005d9fe  or      eax, 0FFFFFFFFh
0x14005da01  lock xadd [rcx+0Ch], eax
0x14005da06  cmp     eax, 1
0x14005da09  jnz     short loc_14005DA18
0x14005da0b  nop
0x14005da0c  mov     rax, [rcx]
0x14005da0f  mov     rax, [rax+8]
0x14005da13  call    _guard_dispatch_icall
0x14005da18  mov     qword ptr [rbx], 0
0x14005da1f  mov     rcx, [rbp+290h+var_28]
0x14005da26  xor     rcx, rsp; StackCookie
0x14005da29  call    __security_check_cookie
0x14005da2e  add     rsp, 378h
0x14005da35  pop     r14
0x14005da37  pop     rdi
0x14005da38  pop     rbx
0x14005da39  pop     rbp
0x14005da3a  retn
```
