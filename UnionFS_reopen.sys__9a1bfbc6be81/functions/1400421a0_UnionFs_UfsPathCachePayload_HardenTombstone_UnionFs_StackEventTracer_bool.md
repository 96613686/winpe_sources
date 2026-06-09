# UnionFs::UfsPathCachePayload::HardenTombstone(UnionFs::StackEventTracer &,bool)

- ea: `0x1400421a0`
- end: `0x1400424e4`
- name: `?HardenTombstone@UfsPathCachePayload@UnionFs@@QEAAJAEAVStackEventTracer@2@_N@Z`
- size: `836`
- prototype: `int(UnionFs::UfsPathCachePayload *__hidden this, struct UnionFs::StackEventTracer *, bool)`
- caller_count: `3`
- callee_count: `8`
- tags: `installer_update, broker_com_uri`

## callers

- `0x14002c9f0`
- `0x1400666bc`
- `0x1400700c8`

## callees

- `0x140002500`
- `0x140002b20`
- `0x14000f7fc`
- `0x1400421a0`
- `0x140056ac4`
- `0x14005f124`
- `0x1400799a4`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x140042442`
- `ntoskrnl!KeSetEvent` at `0x1400424a4`
- `ntoskrnl!KeSetEvent` at `0x140042442`
- `ntoskrnl!KeSetEvent` at `0x1400424a4`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004231c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400424b9`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004231c`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400424b9`

## string_xrefs

- `0x140042200`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x1400422c9`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x1400423e5`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x140042207`: `UnionFs::UfsPathCachePayload::HardenTombstone`
- `0x1400422c2`: `UnionFs::UfsPathCachePayload::HardenTombstone`

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
  FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(this + 136));
  if ( *(_BYTE *)(this + 165) )
    v7 = *(_BYTE *)(this + 164) == 0;
  else
    v7 = 1;
  v8 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
  v9 = "UnionFs::UfsPathCachePayload::HardenTombstone";
  v24 = *(_OWORD *)*(_QWORD *)(this + 200);
  if ( (unsigned int)dword_14009E178 > 5 && (qword_14009E188 & 0x40) != 0 && (qword_14009E190 & 0x40) == qword_14009E190 )
  {
    *(_QWORD *)v21 = "UnionFs::UfsPathCachePayload::HardenTombstone";
    v10 = (const struct _UNICODE_STRING *)&v24;
    if ( !*((_QWORD *)&v24 + 1) )
      v10 = &FsTlEmptyUnicodeString;
    v25 = v7;
    v18 = v10;
    v26 = 803;
    v22 = "Hardening tombstone";
    v20 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>>(
      (unsigned int)&FsTlEmptyUnicodeString,
      (unsigned int)byte_1400975DD,
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
  v11 = _InterlockedCompareExchange16((volatile signed __int16 *)(this + 160), 2, 1);
  if ( v11 == 1 )
  {
    *(_DWORD *)(this + 168) = 0;
    _mm_mfence();
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v20 = "UnionFs::UfsPathCachePayload::HardenTombstone";
      v23 = "SoftCount zeroed";
      v22 = (const char *)this;
      LODWORD(v18) = 823;
      *(_QWORD *)v21 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)byte_1400973B5,
        (unsigned int)"onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp",
        v6,
        (__int64)&v23,
        (__int64)&v20,
        (__int64)v21,
        (__int64)&v18,
        (__int64)&v22);
    }
    v13 = *(_QWORD *)(this + 184) == 0;
    *(_DWORD *)(this + 172) = 0;
    *(_QWORD *)(this + 176) = 0;
    if ( v13 || !*(_QWORD *)(this + 200) )
      MicrosoftTelemetryAssertTriggeredMsgKM("m_Tombstone.OwningUnion && m_Tombstone.ScratchPath", v9, v8);
    *(_WORD *)(this + 162) = v11;
    *(_BYTE *)(this + 165) = *(_BYTE *)(this + 164);
    *(_BYTE *)(this + 164) = a3;
    if ( v7 )
    {
      *(_BYTE *)(*(_QWORD *)(this + 184) + 208LL) = 1;
      v14 = *((_QWORD *)UnionFs::g_FilterState + 15);
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v14 + 8), 1u) )
        KeSetEvent((PRKEVENT)(v14 + 16), 0, 0);
    }
    else if ( !a3 )
    {
      v15 = *(_QWORD *)(this + 184);
      _InterlockedIncrement((volatile signed __int32 *)(*(_QWORD *)(this + 24) + 8LL));
      *((_QWORD *)&v24 + 1) = *(_QWORD *)(this + 24);
      v16 = (utl::_RefCountBase *)*((_QWORD *)&v24 + 1);
      *(_QWORD *)&v24 = this & ((unsigned __int128)-(__int128)(this + 24) >> 64);
      UnionFs::UfsUnionCtx::AddTombstoneToList(v15, &v24);
      if ( v16 )
        utl::_RefCountBase::_DecStrong(v16);
    }
    KeSetEvent((PRKEVENT)(*(_QWORD *)(this + 136) + 56LL), 0, 0);
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    return 0;
  }
  else
  {
    UnionFs::ProcessTraceStatusOrigin(
      (UnionFs *)0xC0ED0004LL,
      v3,
      (struct UnionFs::StackEventTracer *)0x3280012032FLL,
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
0x1400421a0  mov     [rsp-8+arg_8], rbx
0x1400421a5  mov     [rsp-8+arg_10], rsi
0x1400421aa  push    rbp
0x1400421ab  push    rdi
0x1400421ac  push    r12
0x1400421ae  push    r14
0x1400421b0  push    r15
0x1400421b2  lea     rbp, [rsp-37h]
0x1400421b7  sub     rsp, 90h
0x1400421be  mov     r12, rdx
0x1400421c1  mov     rbx, rcx
0x1400421c4  mov     rdx, [rcx+88h]
0x1400421cb  mov     r14b, r8b
0x1400421ce  lea     rcx, [rbp+57h+FastMutex]
0x1400421d2  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x1400421d7  mov     al, [rbx+0A5h]
0x1400421dd  mov     edi, 1
0x1400421e2  nop
0x1400421e3  test    al, al
0x1400421e5  jnz     short loc_1400421EC
0x1400421e7  mov     sil, dil
0x1400421ea  jmp     short loc_1400421F9
0x1400421ec  mov     al, [rbx+0A4h]
0x1400421f2  nop
0x1400421f3  test    al, al
0x1400421f5  setz    sil
0x1400421f9  mov     rax, [rbx+0C8h]
0x140042200  lea     r8, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140042207  lea     rdx, aUnionfsUfspath_71; "UnionFs::UfsPathCachePayload::HardenTom"...
0x14004220e  movups  xmm0, xmmword ptr [rax]
0x140042211  mov     eax, cs:dword_14009E178
0x140042217  movdqu  [rbp+57h+var_30], xmm0
0x14004221c  cmp     eax, 5
0x14004221f  jbe     loc_1400422D0
0x140042225  mov     rcx, cs:qword_14009E190
0x14004222c  mov     rax, cs:qword_14009E188
0x140042233  test    al, 40h
0x140042235  jz      loc_1400422D0
0x14004223b  mov     rax, rcx
0x14004223e  and     eax, 40h
0x140042241  cmp     rax, rcx
0x140042244  jnz     loc_1400422D0
0x14004224a  cmp     qword ptr [rbp+57h+var_30+8], 0
0x14004224f  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x140042256  mov     qword ptr [rbp+57h+var_48], rdx
0x14004225a  lea     rax, [rbp+57h+var_30]
0x14004225e  cmovz   rax, rcx
0x140042262  mov     [rbp+57h+arg_0], sil
0x140042266  mov     [rbp+57h+var_60], rax
0x14004226a  lea     rdx, byte_1400975DD
0x140042271  lea     rax, aHardeningTombs; "Hardening tombstone"
0x140042278  mov     [rbp+57h+arg_18], 323h
0x14004227f  mov     [rbp+57h+var_40], rax
0x140042283  lea     rax, [rbp+57h+arg_0]
0x140042287  mov     [rsp+0B0h+var_68], rax
0x14004228c  lea     rax, [rbp+57h+var_60]
0x140042290  mov     [rsp+0B0h+var_70], rax
0x140042295  lea     rax, [rbp+57h+arg_18]
0x140042299  mov     [rsp+0B0h+var_78], rax
0x14004229e  lea     rax, [rbp+57h+var_50]
0x1400422a2  mov     [rsp+0B0h+var_80], rax
0x1400422a7  lea     rax, [rbp+57h+var_48]
0x1400422ab  mov     [rsp+0B0h+var_88], rax; char *
0x1400422b0  lea     rax, [rbp+57h+var_40]
0x1400422b4  mov     [rsp+0B0h+var_90], rax
0x1400422b9  mov     [rbp+57h+var_50], r8
0x1400422bd  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<1> const &)
0x1400422c2  lea     rdx, aUnionfsUfspath_71; "UnionFs::UfsPathCachePayload::HardenTom"...
0x1400422c9  lea     r8, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x1400422d0  nop
0x1400422d1  mov     eax, edi
0x1400422d3  mov     ecx, 2
0x1400422d8  lock cmpxchg [rbx+0A0h], cx
0x1400422e1  movzx   r15d, ax
0x1400422e5  nop
0x1400422e6  cmp     ax, di
0x1400422e9  jz      short loc_14004232F
0x1400422eb  lea     rax, aOriginTombston_3; "ORIGIN: Tombstone wasn't soft"
0x1400422f2  mov     r9, rdx; unsigned __int64
0x1400422f5  mov     ebx, 0C0ED0004h
0x1400422fa  mov     [rsp+0B0h+var_90], rax; char *
0x1400422ff  mov     ecx, ebx; this
0x140042301  mov     r8, 3280012032Fh; struct UnionFs::StackEventTracer *
0x14004230b  mov     rdx, r12; int
0x14004230e  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140042313  mov     rcx, [rbp+57h+FastMutex]; FastMutex
0x140042317  test    rcx, rcx
0x14004231a  jz      short loc_140042328
0x14004231c  call    cs:__imp_ExReleaseFastMutex
0x140042323  nop     dword ptr [rax+rax+00h]
0x140042328  mov     eax, ebx
0x14004232a  jmp     loc_1400424C7
0x14004232f  nop
0x140042330  mov     dword ptr [rbx+0A8h], 0
0x14004233a  mfence
0x14004233d  mov     eax, cs:dword_14009E178
0x140042343  cmp     eax, 5
0x140042346  jbe     short loc_1400423BC
0x140042348  mov     rcx, cs:qword_14009E190
0x14004234f  mov     rax, cs:qword_14009E188
0x140042356  test    al, 40h
0x140042358  jz      short loc_1400423BC
0x14004235a  mov     rax, rcx
0x14004235d  and     eax, 40h
0x140042360  cmp     rax, rcx
0x140042363  jnz     short loc_1400423BC
0x140042365  lea     rax, aSoftcountZeroe; "SoftCount zeroed"
0x14004236c  mov     [rbp+57h+var_50], rdx
0x140042370  mov     [rbp+57h+var_38], rax
0x140042374  lea     rdx, byte_1400973B5
0x14004237b  lea     rax, [rbp+57h+var_40]
0x14004237f  mov     [rbp+57h+var_40], rbx
0x140042383  mov     [rsp+0B0h+var_70], rax
0x140042388  lea     rax, [rbp+57h+var_60]
0x14004238c  mov     [rsp+0B0h+var_78], rax
0x140042391  lea     rax, [rbp+57h+var_48]
0x140042395  mov     [rsp+0B0h+var_80], rax
0x14004239a  lea     rax, [rbp+57h+var_50]
0x14004239e  mov     [rsp+0B0h+var_88], rax
0x1400423a3  lea     rax, [rbp+57h+var_38]
0x1400423a7  mov     [rsp+0B0h+var_90], rax
0x1400423ac  mov     dword ptr [rbp+57h+var_60], 337h
0x1400423b3  mov     qword ptr [rbp+57h+var_48], r8
0x1400423b7  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400423bc  cmp     qword ptr [rbx+0B8h], 0
0x1400423c4  mov     dword ptr [rbx+0ACh], 0
0x1400423ce  mov     qword ptr [rbx+0B0h], 0
0x1400423d9  jz      short loc_1400423E5
0x1400423db  cmp     qword ptr [rbx+0C8h], 0
0x1400423e3  jnz     short loc_1400423F1
0x1400423e5  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x1400423ec  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400423f1  nop
0x1400423f2  mov     [rbx+0A2h], r15w
0x1400423fa  mov     al, [rbx+0A4h]
0x140042400  nop
0x140042401  nop
0x140042402  mov     [rbx+0A5h], al
0x140042408  nop
0x140042409  mov     [rbx+0A4h], r14b
0x140042410  test    sil, sil
0x140042413  jz      short loc_140042450
0x140042415  mov     rax, [rbx+0B8h]
0x14004241c  mov     [rax+0D0h], dil
0x140042423  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x14004242a  mov     rcx, [rax+78h]
0x14004242e  nop
0x14004242f  lock xadd [rcx+8], edi
0x140042434  nop
0x140042435  test    edi, edi
0x140042437  jnz     short loc_140042494
0x140042439  add     rcx, 10h; Event
0x14004243d  xor     r8d, r8d; Wait
0x140042440  xor     edx, edx; Increment
0x140042442  call    cs:__imp_KeSetEvent
0x140042449  nop     dword ptr [rax+rax+00h]
0x14004244e  jmp     short loc_140042494
0x140042450  test    r14b, r14b
0x140042453  jnz     short loc_140042494
0x140042455  mov     rcx, [rbx+0B8h]
0x14004245c  lea     r8, [rbx+18h]
0x140042460  mov     rax, [r8]
0x140042463  lock inc dword ptr [rax+8]
0x140042467  mov     rdi, [r8]
0x14004246a  mov     rax, r8
0x14004246d  neg     rax
0x140042470  mov     qword ptr [rbp+57h+var_30+8], rdi
0x140042474  sbb     rdx, rdx
0x140042477  and     rdx, rbx
0x14004247a  mov     qword ptr [rbp+57h+var_30], rdx
0x14004247e  lea     rdx, [rbp+57h+var_30]
0x140042482  call    ?AddTombstoneToList@UfsUnionCtx@UnionFs@@QEAAX$$QEAV?$shared_ptr@VUfsPathCachePayload@UnionFs@@@utl@@@Z; UnionFs::UfsUnionCtx::AddTombstoneToList(utl::shared_ptr<UnionFs::UfsPathCachePayload> &&)
0x140042487  test    rdi, rdi
0x14004248a  jz      short loc_140042494
0x14004248c  mov     rcx, rdi; this
0x14004248f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140042494  mov     rcx, [rbx+88h]
0x14004249b  xor     r8d, r8d; Wait
0x14004249e  add     rcx, 38h ; '8'; Event
0x1400424a2  xor     edx, edx; Increment
0x1400424a4  call    cs:__imp_KeSetEvent
0x1400424ab  nop     dword ptr [rax+rax+00h]
0x1400424b0  mov     rcx, [rbp+57h+FastMutex]; FastMutex
0x1400424b4  test    rcx, rcx
0x1400424b7  jz      short loc_1400424C5
0x1400424b9  call    cs:__imp_ExReleaseFastMutex
0x1400424c0  nop     dword ptr [rax+rax+00h]
0x1400424c5  xor     eax, eax
0x1400424c7  lea     r11, [rsp+0B0h+var_20]
0x1400424cf  mov     rbx, [r11+38h]
0x1400424d3  mov     rsi, [r11+40h]
0x1400424d7  mov     rsp, r11
0x1400424da  pop     r15
0x1400424dc  pop     r14
0x1400424de  pop     r12
0x1400424e0  pop     rdi
0x1400424e1  pop     rbp
0x1400424e2  retn
```
