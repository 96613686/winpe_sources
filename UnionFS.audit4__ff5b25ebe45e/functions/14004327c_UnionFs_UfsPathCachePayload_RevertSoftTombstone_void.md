# UnionFs::UfsPathCachePayload::RevertSoftTombstone(void)

- ea: `0x14004327c`
- end: `0x1400435ed`
- name: `?RevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAA_NXZ`
- size: `881`
- prototype: `bool __fastcall(UnionFs::UfsPathCachePayload *__hidden this)`
- caller_count: `9`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x140011a60`
- `0x1400194b8`
- `0x14002bce4`
- `0x14002ca90`
- `0x14002d3e0`
- `0x14003b8b8`
- `0x1400435f4`
- `0x140065304`
- `0x140067ea4`

## callees

- `0x140002158`
- `0x140002500`
- `0x14000f81c`
- `0x140042674`
- `0x14004327c`
- `0x140079cc4`
- `0x140079f68`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043590`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043590`
- `ntoskrnl!KeSetEvent` at `0x1400435c4`
- `ntoskrnl!KeSetEvent` at `0x1400435c4`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043348`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400435d9`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043348`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400435d9`

## string_xrefs

- `0x1400432da`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140043406`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140043498`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x1400432f0`: `UnionFs::UfsPathCachePayload::RevertSoftTombstone`
- `0x140043415`: `UnionFs::UfsPathCachePayload::RevertSoftTombstone`
- `0x1400434ae`: `UnionFs::UfsPathCachePayload::RevertSoftTombstone`
- `0x140043302`: `SoftCount already zero`
- `0x140043399`: `m_Tombstone.PreviousState == TombstoneState::None || m_Tombstone.PreviousState == TombstoneState::Hard || m_Tombstone.PreviousState == TombstoneState::Replaced || m_Tombstone.PreviousState == TombstoneState::Renamed`

## pseudocode

```c
char __fastcall UnionFs::UfsPathCachePayload::RevertSoftTombstone(UnionFs::UfsPathCachePayload *this)
{
  struct _UNICODE_STRING *v2; // rdx
  int v3; // r8d
  int v4; // r9d
  utl::_RefCountBase *v6; // rcx
  __int64 v7; // rdi
  const char *v8; // [rsp+50h] [rbp-20h] BYREF
  const char *v9; // [rsp+58h] [rbp-18h] BYREF
  _QWORD v10[2]; // [rsp+60h] [rbp-10h] BYREF
  int v11; // [rsp+A0h] [rbp+30h] BYREF
  UnionFs::UfsPathCachePayload *v12; // [rsp+A8h] [rbp+38h] BYREF
  PFAST_MUTEX FastMutex; // [rsp+B0h] [rbp+40h] BYREF
  const char *v14; // [rsp+B8h] [rbp+48h] BYREF

  FsFltWil::AcquireFastMutex(&FastMutex, *((_QWORD *)this + 18));
  if ( !*((_DWORD *)this + 44) )
  {
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v12 = this;
      v14 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      v11 = 899;
      v8 = "UnionFs::UfsPathCachePayload::RevertSoftTombstone";
      v9 = "SoftCount already zero";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)byte_1400970F9,
        v3,
        v4,
        (__int64)&v9,
        (__int64)&v8,
        (__int64)&v14,
        (__int64)&v11,
        (__int64)&v12);
    }
LABEL_6:
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    return 0;
  }
  if ( *((_WORD *)this + 85) && *((_WORD *)this + 85) != 2 && *((_WORD *)this + 85) != 3 && *((_WORD *)this + 85) != 4 )
    MicrosoftTelemetryAssertTriggeredMsgKM(
      "m_Tombstone.PreviousState == TombstoneState::None || m_Tombstone.PreviousState == TombstoneState::Hard || m_Tombst"
      "one.PreviousState == TombstoneState::Replaced || m_Tombstone.PreviousState == TombstoneState::Renamed");
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 44, 0xFFFFFFFF) <= 1 )
  {
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v12 = this;
      v14 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      v11 = 926;
      v10[0] = "UnionFs::UfsPathCachePayload::RevertSoftTombstone";
      v9 = "Reverting Soft";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)&byte_14009725F,
        v3,
        v4,
        (__int64)&v9,
        (__int64)v10,
        (__int64)&v14,
        (__int64)&v11,
        (__int64)&v12);
    }
    if ( _InterlockedCompareExchange16((volatile signed __int16 *)this + 84, *((_WORD *)this + 85), 1) != 1 )
      goto LABEL_6;
    *((_DWORD *)this + 45) = 0;
    *((_QWORD *)this + 23) = 0;
    *((_BYTE *)this + 172) = *((_BYTE *)this + 173);
    if ( !*((_WORD *)this + 85) )
    {
      v6 = (utl::_RefCountBase *)*((_QWORD *)this + 25);
      *((_QWORD *)this + 24) = 0;
      *((_QWORD *)this + 25) = 0;
      if ( v6 )
        utl::_RefCountBase::_DecStrong(v6);
      v7 = *((_QWORD *)this + 26);
      *((_QWORD *)this + 26) = 0;
      if ( v7 )
      {
        if ( !*(_BYTE *)(v7 + 16) )
          *(_OWORD *)v7 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v7, v2);
        ExFreePoolWithTag((PVOID)v7, 0);
      }
      if ( !*((_QWORD *)this + 4) )
        UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(this, 0x411001203B6LL);
    }
    KeSetEvent((PRKEVENT)(*((_QWORD *)this + 18) + 56LL), 0, 0);
  }
  else if ( (unsigned int)dword_14009E178 > 5
         && (qword_14009E188 & 0x40) != 0
         && (qword_14009E190 & 0x40) == qword_14009E190 )
  {
    v11 = *((_DWORD *)this + 44);
    v14 = (const char *)this;
    v9 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
    v8 = "UnionFs::UfsPathCachePayload::RevertSoftTombstone";
    v10[0] = "SoftCount > 0";
    LODWORD(v12) = 919;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)byte_140097093,
      v3,
      v4,
      (__int64)v10,
      (__int64)&v8,
      (__int64)&v9,
      (__int64)&v12,
      (__int64)&v14,
      (__int64)&v11);
  }
  if ( FastMutex )
    ExReleaseFastMutex(FastMutex);
  return 1;
}

```

## disassembly

```asm
0x14004327c  push    rbp
0x14004327e  push    rbx
0x14004327f  push    rsi
0x140043280  push    rdi
0x140043281  push    r14
0x140043283  mov     rbp, rsp
0x140043286  sub     rsp, 70h
0x14004328a  mov     rdx, [rcx+90h]
0x140043291  mov     rbx, rcx
0x140043294  lea     rcx, [rbp+FastMutex]
0x140043298  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x14004329d  mov     eax, [rbx+0B0h]
0x1400432a3  xor     esi, esi
0x1400432a5  nop
0x1400432a6  test    eax, eax
0x1400432a8  jnz     loc_140043362
0x1400432ae  mov     eax, cs:dword_14009E178
0x1400432b4  cmp     eax, 5
0x1400432b7  jbe     loc_14004333F
0x1400432bd  mov     rcx, cs:qword_14009E190
0x1400432c4  mov     rax, cs:qword_14009E188
0x1400432cb  test    al, 40h
0x1400432cd  jz      short loc_14004333F
0x1400432cf  mov     rax, rcx
0x1400432d2  and     eax, 40h
0x1400432d5  cmp     rax, rcx
0x1400432d8  jnz     short loc_14004333F
0x1400432da  lea     rax, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x1400432e1  mov     [rbp+arg_8], rbx
0x1400432e5  mov     [rbp+arg_18], rax
0x1400432e9  lea     rdx, byte_1400970F9
0x1400432f0  lea     rax, aUnionfsUfspath_9; "UnionFs::UfsPathCachePayload::RevertSof"...
0x1400432f7  mov     [rbp+arg_0], 383h
0x1400432fe  mov     [rbp+var_20], rax
0x140043302  lea     rax, aSoftcountAlrea; "SoftCount already zero"
0x140043309  mov     [rbp+var_18], rax
0x14004330d  lea     rax, [rbp+arg_8]
0x140043311  mov     [rsp+70h+var_30], rax
0x140043316  lea     rax, [rbp+arg_0]
0x14004331a  mov     [rsp+70h+var_38], rax
0x14004331f  lea     rax, [rbp+arg_18]
0x140043323  mov     [rsp+70h+var_40], rax
0x140043328  lea     rax, [rbp+var_20]
0x14004332c  mov     [rsp+70h+var_48], rax
0x140043331  lea     rax, [rbp+var_18]
0x140043335  mov     [rsp+70h+var_50], rax
0x14004333a  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14004333f  mov     rcx, [rbp+FastMutex]; FastMutex
0x140043343  test    rcx, rcx
0x140043346  jz      short loc_140043354
0x140043348  call    cs:__imp_ExReleaseFastMutex
0x14004334f  nop     dword ptr [rax+rax+00h]
0x140043354  xor     al, al
0x140043356  add     rsp, 70h
0x14004335a  pop     r14
0x14004335c  pop     rdi
0x14004335d  pop     rsi
0x14004335e  pop     rbx
0x14004335f  pop     rbp
0x140043360  retn
0x140043362  movzx   eax, word ptr [rbx+0AAh]
0x140043369  nop
0x14004336a  test    ax, ax
0x14004336d  jz      short loc_1400433A5
0x14004336f  movzx   eax, word ptr [rbx+0AAh]
0x140043376  nop
0x140043377  cmp     ax, 2
0x14004337b  jz      short loc_1400433A5
0x14004337d  movzx   eax, word ptr [rbx+0AAh]
0x140043384  nop
0x140043385  cmp     ax, 3
0x140043389  jz      short loc_1400433A5
0x14004338b  movzx   eax, word ptr [rbx+0AAh]
0x140043392  nop
0x140043393  cmp     ax, 4
0x140043397  jz      short loc_1400433A5
0x140043399  lea     rcx, aMTombstonePrev; "m_Tombstone.PreviousState == TombstoneS"...
0x1400433a0  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400433a5  nop
0x1400433a6  or      eax, 0FFFFFFFFh
0x1400433a9  lock xadd [rbx+0B0h], eax
0x1400433b1  mov     r14d, 1
0x1400433b7  nop
0x1400433b8  sub     eax, r14d
0x1400433bb  mov     eax, cs:dword_14009E178
0x1400433c1  jle     loc_140043472
0x1400433c7  cmp     eax, 5
0x1400433ca  jbe     loc_1400435D0
0x1400433d0  mov     rcx, cs:qword_14009E190
0x1400433d7  mov     rax, cs:qword_14009E188
0x1400433de  test    al, 40h
0x1400433e0  jz      loc_1400435D0
0x1400433e6  mov     rax, rcx
0x1400433e9  and     eax, 40h
0x1400433ec  cmp     rax, rcx
0x1400433ef  jnz     loc_1400435D0
0x1400433f5  mov     eax, [rbx+0B0h]
0x1400433fb  lea     rdx, byte_140097093
0x140043402  nop
0x140043403  mov     [rbp+arg_0], eax
0x140043406  lea     rax, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x14004340d  mov     [rbp+arg_18], rbx
0x140043411  mov     [rbp+var_18], rax
0x140043415  lea     rax, aUnionfsUfspath_9; "UnionFs::UfsPathCachePayload::RevertSof"...
0x14004341c  mov     [rbp+var_20], rax
0x140043420  lea     rax, aSoftcount0; "SoftCount > 0"
0x140043427  mov     [rbp+var_10], rax
0x14004342b  lea     rax, [rbp+arg_0]
0x14004342f  mov     [rsp+70h+var_28], rax
0x140043434  lea     rax, [rbp+arg_18]
0x140043438  mov     [rsp+70h+var_30], rax
0x14004343d  lea     rax, [rbp+arg_8]
0x140043441  mov     [rsp+70h+var_38], rax
0x140043446  lea     rax, [rbp+var_18]
0x14004344a  mov     [rsp+70h+var_40], rax
0x14004344f  lea     rax, [rbp+var_20]
0x140043453  mov     [rsp+70h+var_48], rax
0x140043458  lea     rax, [rbp+var_10]
0x14004345c  mov     [rsp+70h+var_50], rax
0x140043461  mov     dword ptr [rbp+arg_8], 397h
0x140043468  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x14004346d  jmp     loc_1400435D0
0x140043472  cmp     eax, 5
0x140043475  jbe     loc_1400434FD
0x14004347b  mov     rcx, cs:qword_14009E190
0x140043482  mov     rax, cs:qword_14009E188
0x140043489  test    al, 40h
0x14004348b  jz      short loc_1400434FD
0x14004348d  mov     rax, rcx
0x140043490  and     eax, 40h
0x140043493  cmp     rax, rcx
0x140043496  jnz     short loc_1400434FD
0x140043498  lea     rax, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x14004349f  mov     [rbp+arg_8], rbx
0x1400434a3  mov     [rbp+arg_18], rax
0x1400434a7  lea     rdx, byte_14009725F
0x1400434ae  lea     rax, aUnionfsUfspath_9; "UnionFs::UfsPathCachePayload::RevertSof"...
0x1400434b5  mov     [rbp+arg_0], 39Eh
0x1400434bc  mov     [rbp+var_10], rax
0x1400434c0  lea     rax, aRevertingSoft; "Reverting Soft"
0x1400434c7  mov     [rbp+var_18], rax
0x1400434cb  lea     rax, [rbp+arg_8]
0x1400434cf  mov     [rsp+70h+var_30], rax
0x1400434d4  lea     rax, [rbp+arg_0]
0x1400434d8  mov     [rsp+70h+var_38], rax
0x1400434dd  lea     rax, [rbp+arg_18]
0x1400434e1  mov     [rsp+70h+var_40], rax
0x1400434e6  lea     rax, [rbp+var_10]
0x1400434ea  mov     [rsp+70h+var_48], rax
0x1400434ef  lea     rax, [rbp+var_18]
0x1400434f3  mov     [rsp+70h+var_50], rax
0x1400434f8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400434fd  movzx   ecx, word ptr [rbx+0AAh]
0x140043504  mov     eax, r14d
0x140043507  nop
0x140043508  nop
0x140043509  lock cmpxchg [rbx+0A8h], cx
0x140043512  nop
0x140043513  cmp     ax, r14w
0x140043517  jnz     loc_14004333F
0x14004351d  mov     [rbx+0B4h], esi
0x140043523  mov     [rbx+0B8h], rsi
0x14004352a  mov     al, [rbx+0ADh]
0x140043530  nop
0x140043531  nop
0x140043532  mov     [rbx+0ACh], al
0x140043538  movzx   eax, word ptr [rbx+0AAh]
0x14004353f  nop
0x140043540  test    ax, ax
0x140043543  jnz     short loc_1400435B4
0x140043545  mov     rcx, [rbx+0C8h]; this
0x14004354c  mov     [rbx+0C0h], rsi
0x140043553  mov     [rbx+0C8h], rsi
0x14004355a  test    rcx, rcx
0x14004355d  jz      short loc_140043564
0x14004355f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140043564  mov     rdi, [rbx+0D0h]
0x14004356b  mov     [rbx+0D0h], rsi
0x140043572  test    rdi, rdi
0x140043575  jz      short loc_14004359C
0x140043577  cmp     [rdi+10h], sil
0x14004357b  jnz     short loc_140043583
0x14004357d  xorps   xmm0, xmm0
0x140043580  movups  xmmword ptr [rdi], xmm0
0x140043583  mov     rcx, rdi; UnicodeString
0x140043586  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004358b  xor     edx, edx; Tag
0x14004358d  mov     rcx, rdi; P
0x140043590  call    cs:__imp_ExFreePoolWithTag
0x140043597  nop     dword ptr [rax+rax+00h]
0x14004359c  cmp     [rbx+20h], rsi
0x1400435a0  jnz     short loc_1400435B4
0x1400435a2  mov     rdx, 411001203B6h
0x1400435ac  mov     rcx, rbx
0x1400435af  call    ?InvalidateNoRevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAAXT_TAGGED_SOURCE@@@Z; UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(_TAGGED_SOURCE)
0x1400435b4  mov     rcx, [rbx+90h]
0x1400435bb  xor     r8d, r8d; Wait
0x1400435be  add     rcx, 38h ; '8'; Event
0x1400435c2  xor     edx, edx; Increment
0x1400435c4  call    cs:__imp_KeSetEvent
0x1400435cb  nop     dword ptr [rax+rax+00h]
0x1400435d0  mov     rcx, [rbp+FastMutex]; FastMutex
0x1400435d4  test    rcx, rcx
0x1400435d7  jz      short loc_1400435E5
0x1400435d9  call    cs:__imp_ExReleaseFastMutex
0x1400435e0  nop     dword ptr [rax+rax+00h]
0x1400435e5  mov     al, r14b
0x1400435e8  jmp     loc_140043356
```
