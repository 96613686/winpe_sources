# UnionFs::UfsPathCachePayload::HardenTombstone(UnionFs::StackEventTracer &,bool)

- ea: `0x140042328`
- end: `0x14004266c`
- name: `?HardenTombstone@UfsPathCachePayload@UnionFs@@QEAAJAEAVStackEventTracer@2@_N@Z`
- size: `836`
- prototype: `int(UnionFs::UfsPathCachePayload *__hidden this, struct UnionFs::StackEventTracer *, bool)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002ca90`
- `0x14006683c`
- `0x1400702b8`

## callees

- `0x140002500`
- `0x140002b20`
- `0x14000f81c`
- `0x140042328`
- `0x140056c44`
- `0x14005f2a4`
- `0x140079cc4`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400425ca`
- `ntoskrnl!KeSetEvent` at `0x14004262c`
- `ntoskrnl!KeSetEvent` at `0x1400425ca`
- `ntoskrnl!KeSetEvent` at `0x14004262c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400424a4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042641`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400424a4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042641`

## string_xrefs

- `0x140042388`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140042451`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x14004256d`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x14004238f`: `UnionFs::UfsPathCachePayload::HardenTombstone`
- `0x14004244a`: `UnionFs::UfsPathCachePayload::HardenTombstone`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::HardenTombstone(
        unsigned __int64 this,
        struct UnionFs::StackEventTracer *a2,
        char a3)
{
  int v3; // r12d
  int v6; // r9d
  bool v7; // si
  const char *v8; // r8
  const char *v9; // rdx
  const struct _UNICODE_STRING *v10; // rax
  signed __int16 v11; // r15
  bool v13; // zf
  __int64 v14; // rcx
  __int64 v15; // rcx
  utl::_RefCountBase *v16; // rdi
  char *v17; // [rsp+28h] [rbp-31h]
  const struct _UNICODE_STRING *v18; // [rsp+50h] [rbp-9h] BYREF
  PFAST_MUTEX FastMutex; // [rsp+58h] [rbp-1h] BYREF
  const char *v20; // [rsp+60h] [rbp+7h] BYREF
  char v21[8]; // [rsp+68h] [rbp+Fh] BYREF
  const char *v22; // [rsp+70h] [rbp+17h] BYREF
  const char *v23; // [rsp+78h] [rbp+1Fh] BYREF
  __int128 v24; // [rsp+80h] [rbp+27h] BYREF
  bool v25; // [rsp+C0h] [rbp+67h] BYREF
  int v26; // [rsp+D8h] [rbp+7Fh] BYREF

  v3 = (int)a2;
  FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(this + 144));
  if ( *(_BYTE *)(this + 173) )
    v7 = *(_BYTE *)(this + 172) == 0;
  else
    v7 = 1;
  v8 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
  v9 = "UnionFs::UfsPathCachePayload::HardenTombstone";
  v24 = *(_OWORD *)*(_QWORD *)(this + 208);
  if ( (unsigned int)dword_14009E178 > 5 && (qword_14009E188 & 0x40) != 0 && (qword_14009E190 & 0x40) == qword_14009E190 )
  {
    *(_QWORD *)v21 = "UnionFs::UfsPathCachePayload::HardenTombstone";
    v10 = (const struct _UNICODE_STRING *)&v24;
    if ( !*((_QWORD *)&v24 + 1) )
      v10 = &FsTlEmptyUnicodeString;
    v25 = v7;
    v18 = v10;
    v26 = 828;
    v22 = "Hardening tombstone";
    v20 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>>(
      (unsigned int)&FsTlEmptyUnicodeString,
      (unsigned int)byte_14009765D,
      (unsigned int)"onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp",
      v6,
      (__int64)&v22,
      (__int64)v21,
      (__int64)&v20,
      (__int64)&v26,
      (__int64)&v18,
      (__int64)&v25);
    v9 = "UnionFs::UfsPathCachePayload::HardenTombstone";
    v8 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
  }
  v11 = _InterlockedCompareExchange16((volatile signed __int16 *)(this + 168), 2, 1);
  if ( v11 == 1 )
  {
    *(_DWORD *)(this + 176) = 0;
    _mm_mfence();
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v20 = "UnionFs::UfsPathCachePayload::HardenTombstone";
      v23 = "SoftCount zeroed";
      v22 = (const char *)this;
      LODWORD(v18) = 848;
      *(_QWORD *)v21 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)word_1400974A2,
        (unsigned int)"onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp",
        v6,
        (__int64)&v23,
        (__int64)&v20,
        (__int64)v21,
        (__int64)&v18,
        (__int64)&v22);
    }
    v13 = *(_QWORD *)(this + 192) == 0;
    *(_DWORD *)(this + 180) = 0;
    *(_QWORD *)(this + 184) = 0;
    if ( v13 || !*(_QWORD *)(this + 208) )
      MicrosoftTelemetryAssertTriggeredMsgKM("m_Tombstone.OwningUnion && m_Tombstone.ScratchPath", v9, v8);
    *(_WORD *)(this + 170) = v11;
    *(_BYTE *)(this + 173) = *(_BYTE *)(this + 172);
    *(_BYTE *)(this + 172) = a3;
    if ( v7 )
    {
      *(_BYTE *)(*(_QWORD *)(this + 192) + 208LL) = 1;
      v14 = *((_QWORD *)UnionFs::g_FilterState + 15);
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 8), 1u) )
        KeSetEvent((PRKEVENT)(v14 + 16), 0, 0);
    }
    else if ( !a3 )
    {
      v15 = *(_QWORD *)(this + 192);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(this + 24) + 8LL));
      *((_QWORD *)&v24 + 1) = *(_QWORD *)(this + 24);
      v16 = (utl::_RefCountBase *)*((_QWORD *)&v24 + 1);
      *(_QWORD *)&v24 = this & ((unsigned __int128)-(__int128)(this + 24) >> 64);
      UnionFs::UfsUnionCtx::AddTombstoneToList(v15, &v24);
      if ( v16 )
        utl::_RefCountBase::_DecStrong(v16);
    }
    KeSetEvent((PRKEVENT)(*(_QWORD *)(this + 144) + 56LL), 0, 0);
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0004LL,
      v3,
      (struct UnionFs::StackEventTracer *)0x32800120348LL,
      (unsigned __int64)"UnionFs::UfsPathCachePayload::HardenTombstone",
      "ORIGIN: Tombstone wasn't soft",
      v17);
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    return 3236757508LL;
  }
}

```

## disassembly

```asm
0x140042328  mov     [rsp-8+arg_8], rbx
0x14004232d  mov     [rsp-8+arg_10], rsi
0x140042332  push    rbp
0x140042333  push    rdi
0x140042334  push    r12
0x140042336  push    r14
0x140042338  push    r15
0x14004233a  lea     rbp, [rsp-37h]
0x14004233f  sub     rsp, 90h
0x140042346  mov     r12, rdx
0x140042349  mov     rbx, rcx
0x14004234c  mov     rdx, [rcx+90h]
0x140042353  mov     r14b, r8b
0x140042356  lea     rcx, [rbp+57h+FastMutex]
0x14004235a  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x14004235f  mov     al, [rbx+0ADh]
0x140042365  mov     edi, 1
0x14004236a  nop
0x14004236b  test    al, al
0x14004236d  jnz     short loc_140042374
0x14004236f  mov     sil, dil
0x140042372  jmp     short loc_140042381
0x140042374  mov     al, [rbx+0ACh]
0x14004237a  nop
0x14004237b  test    al, al
0x14004237d  setz    sil
0x140042381  mov     rax, [rbx+0D0h]
0x140042388  lea     r8, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x14004238f  lea     rdx, aUnionfsUfspath_71; "UnionFs::UfsPathCachePayload::HardenTom"...
0x140042396  movups  xmm0, xmmword ptr [rax]
0x140042399  mov     eax, cs:dword_14009E178
0x14004239f  movdqu  [rbp+57h+var_30], xmm0
0x1400423a4  cmp     eax, 5
0x1400423a7  jbe     loc_140042458
0x1400423ad  mov     rcx, cs:qword_14009E190
0x1400423b4  mov     rax, cs:qword_14009E188
0x1400423bb  test    al, 40h
0x1400423bd  jz      loc_140042458
0x1400423c3  mov     rax, rcx
0x1400423c6  and     eax, 40h
0x1400423c9  cmp     rax, rcx
0x1400423cc  jnz     loc_140042458
0x1400423d2  cmp     qword ptr [rbp+57h+var_30+8], 0
0x1400423d7  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x1400423de  mov     qword ptr [rbp+57h+var_48], rdx
0x1400423e2  lea     rax, [rbp+57h+var_30]
0x1400423e6  cmovz   rax, rcx
0x1400423ea  mov     [rbp+57h+arg_0], sil
0x1400423ee  mov     [rbp+57h+var_60], rax
0x1400423f2  lea     rdx, byte_14009765D
0x1400423f9  lea     rax, aHardeningTombs; "Hardening tombstone"
0x140042400  mov     [rbp+57h+arg_18], 33Ch
0x140042407  mov     [rbp+57h+var_40], rax
0x14004240b  lea     rax, [rbp+57h+arg_0]
0x14004240f  mov     [rsp+0B0h+var_68], rax
0x140042414  lea     rax, [rbp+57h+var_60]
0x140042418  mov     [rsp+0B0h+var_70], rax
0x14004241d  lea     rax, [rbp+57h+arg_18]
0x140042421  mov     [rsp+0B0h+var_78], rax
0x140042426  lea     rax, [rbp+57h+var_50]
0x14004242a  mov     [rsp+0B0h+var_80], rax
0x14004242f  lea     rax, [rbp+57h+var_48]
0x140042433  mov     [rsp+0B0h+var_88], rax; char *
0x140042438  lea     rax, [rbp+57h+var_40]
0x14004243c  mov     [rsp+0B0h+var_90], rax
0x140042441  mov     [rbp+57h+var_50], r8
0x140042445  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<1> const &)
0x14004244a  lea     rdx, aUnionfsUfspath_71; "UnionFs::UfsPathCachePayload::HardenTom"...
0x140042451  lea     r8, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140042458  nop
0x140042459  mov     eax, edi
0x14004245b  mov     ecx, 2
0x140042460  lock cmpxchg [rbx+0A8h], cx
0x140042469  movzx   r15d, ax
0x14004246d  nop
0x14004246e  cmp     ax, di
0x140042471  jz      short loc_1400424B7
0x140042473  lea     rax, aOriginTombston_3; "ORIGIN: Tombstone wasn't soft"
0x14004247a  mov     r9, rdx; unsigned __int64
0x14004247d  mov     ebx, 0C0ED0004h
0x140042482  mov     [rsp+0B0h+var_90], rax; char *
0x140042487  mov     ecx, ebx; this
0x140042489  mov     r8, 32800120348h; struct UnionFs::StackEventTracer *
0x140042493  mov     rdx, r12; int
0x140042496  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x14004249b  mov     rcx, [rbp+57h+FastMutex]; FastMutex
0x14004249f  test    rcx, rcx
0x1400424a2  jz      short loc_1400424B0
0x1400424a4  call    cs:__imp_ExReleaseFastMutex
0x1400424ab  nop     dword ptr [rax+rax+00h]
0x1400424b0  mov     eax, ebx
0x1400424b2  jmp     loc_14004264F
0x1400424b7  nop
0x1400424b8  mov     dword ptr [rbx+0B0h], 0
0x1400424c2  mfence
0x1400424c5  mov     eax, cs:dword_14009E178
0x1400424cb  cmp     eax, 5
0x1400424ce  jbe     short loc_140042544
0x1400424d0  mov     rcx, cs:qword_14009E190
0x1400424d7  mov     rax, cs:qword_14009E188
0x1400424de  test    al, 40h
0x1400424e0  jz      short loc_140042544
0x1400424e2  mov     rax, rcx
0x1400424e5  and     eax, 40h
0x1400424e8  cmp     rax, rcx
0x1400424eb  jnz     short loc_140042544
0x1400424ed  lea     rax, aSoftcountZeroe; "SoftCount zeroed"
0x1400424f4  mov     [rbp+57h+var_50], rdx
0x1400424f8  mov     [rbp+57h+var_38], rax
0x1400424fc  lea     rdx, word_1400974A2
0x140042503  lea     rax, [rbp+57h+var_40]
0x140042507  mov     [rbp+57h+var_40], rbx
0x14004250b  mov     [rsp+0B0h+var_70], rax
0x140042510  lea     rax, [rbp+57h+var_60]
0x140042514  mov     [rsp+0B0h+var_78], rax
0x140042519  lea     rax, [rbp+57h+var_48]
0x14004251d  mov     [rsp+0B0h+var_80], rax
0x140042522  lea     rax, [rbp+57h+var_50]
0x140042526  mov     [rsp+0B0h+var_88], rax
0x14004252b  lea     rax, [rbp+57h+var_38]
0x14004252f  mov     [rsp+0B0h+var_90], rax
0x140042534  mov     dword ptr [rbp+57h+var_60], 350h
0x14004253b  mov     qword ptr [rbp+57h+var_48], r8
0x14004253f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140042544  cmp     qword ptr [rbx+0C0h], 0
0x14004254c  mov     dword ptr [rbx+0B4h], 0
0x140042556  mov     qword ptr [rbx+0B8h], 0
0x140042561  jz      short loc_14004256D
0x140042563  cmp     qword ptr [rbx+0D0h], 0
0x14004256b  jnz     short loc_140042579
0x14004256d  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x140042574  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140042579  nop
0x14004257a  mov     [rbx+0AAh], r15w
0x140042582  mov     al, [rbx+0ACh]
0x140042588  nop
0x140042589  nop
0x14004258a  mov     [rbx+0ADh], al
0x140042590  nop
0x140042591  mov     [rbx+0ACh], r14b
0x140042598  test    sil, sil
0x14004259b  jz      short loc_1400425D8
0x14004259d  mov     rax, [rbx+0C0h]
0x1400425a4  mov     [rax+0D0h], dil
0x1400425ab  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400425b2  mov     rcx, [rax+78h]
0x1400425b6  nop
0x1400425b7  lock xadd [rcx+8], edi
0x1400425bc  nop
0x1400425bd  test    edi, edi
0x1400425bf  jnz     short loc_14004261C
0x1400425c1  add     rcx, 10h; Event
0x1400425c5  xor     r8d, r8d; Wait
0x1400425c8  xor     edx, edx; Increment
0x1400425ca  call    cs:__imp_KeSetEvent
0x1400425d1  nop     dword ptr [rax+rax+00h]
0x1400425d6  jmp     short loc_14004261C
0x1400425d8  test    r14b, r14b
0x1400425db  jnz     short loc_14004261C
0x1400425dd  mov     rcx, [rbx+0C0h]
0x1400425e4  lea     r8, [rbx+18h]
0x1400425e8  mov     rax, [r8]
0x1400425eb  lock inc dword ptr [rax+8]
0x1400425ef  mov     rdi, [r8]
0x1400425f2  mov     rax, r8
0x1400425f5  neg     rax
0x1400425f8  mov     qword ptr [rbp+57h+var_30+8], rdi
0x1400425fc  sbb     rdx, rdx
0x1400425ff  and     rdx, rbx
0x140042602  mov     qword ptr [rbp+57h+var_30], rdx
0x140042606  lea     rdx, [rbp+57h+var_30]
0x14004260a  call    ?AddTombstoneToList@UfsUnionCtx@UnionFs@@QEAAX$$QEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@Z; UnionFs::UfsUnionCtx::AddTombstoneToList(utl::shared_ptr<UnionFs::UfsPathCachePayload> &&)
0x14004260f  test    rdi, rdi
0x140042612  jz      short loc_14004261C
0x140042614  mov     rcx, rdi; this
0x140042617  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x14004261c  mov     rcx, [rbx+90h]
0x140042623  xor     r8d, r8d; Wait
0x140042626  add     rcx, 38h ; '8'; Event
0x14004262a  xor     edx, edx; Increment
0x14004262c  call    cs:__imp_KeSetEvent
0x140042633  nop     dword ptr [rax+rax+00h]
0x140042638  mov     rcx, [rbp+57h+FastMutex]; FastMutex
0x14004263c  test    rcx, rcx
0x14004263f  jz      short loc_14004264D
0x140042641  call    cs:__imp_ExReleaseFastMutex
0x140042648  nop     dword ptr [rax+rax+00h]
0x14004264d  xor     eax, eax
0x14004264f  lea     r11, [rsp+0B0h+var_20]
0x140042657  mov     rbx, [r11+38h]
0x14004265b  mov     rsi, [r11+40h]
0x14004265f  mov     rsp, r11
0x140042662  pop     r15
0x140042664  pop     r14
0x140042666  pop     r12
0x140042668  pop     rdi
0x140042669  pop     rbp
0x14004266a  retn
```
