# UnionFs::UfsPathCachePayload::RevertSoftTombstone(void)

- ea: `0x1400430fc`
- end: `0x14004346d`
- name: `?RevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAA_NXZ`
- size: `881`
- prototype: `bool __fastcall(UnionFs::UfsPathCachePayload *__hidden this)`
- caller_count: `9`
- callee_count: `8`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011a40`
- `0x140019438`
- `0x14002bbcc`
- `0x14002c9f0`
- `0x14002d340`
- `0x14003b798`
- `0x140043474`
- `0x140065184`
- `0x140067cb4`

## callees

- `0x140002158`
- `0x140002500`
- `0x14000f7fc`
- `0x1400424ec`
- `0x1400430fc`
- `0x1400799a4`
- `0x140079c48`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140043410`
- `ntoskrnl!ExFreePoolWithTag` at `0x140043410`
- `ntoskrnl!KeSetEvent` at `0x140043444`
- `ntoskrnl!KeSetEvent` at `0x140043444`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400431c8`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043459`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400431c8`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043459`

## string_xrefs

- `0x14004315a`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140043286`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140043318`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140043170`: `UnionFs::UfsPathCachePayload::RevertSoftTombstone`
- `0x140043295`: `UnionFs::UfsPathCachePayload::RevertSoftTombstone`
- `0x14004332e`: `UnionFs::UfsPathCachePayload::RevertSoftTombstone`
- `0x140043182`: `SoftCount already zero`
- `0x140043219`: `m_Tombstone.PreviousState == TombstoneState::None || m_Tombstone.PreviousState == TombstoneState::Hard || m_Tombstone.PreviousState == TombstoneState::Replaced || m_Tombstone.PreviousState == TombstoneState::Renamed`

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

  FsFltWil::AcquireFastMutex(&FastMutex, *((_QWORD *)this + 17));
  if ( !*((_DWORD *)this + 42) )
  {
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v12 = this;
      v14 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      v11 = 874;
      v8 = "UnionFs::UfsPathCachePayload::RevertSoftTombstone";
      v9 = "SoftCount already zero";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)byte_140097079,
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
  if ( *((_WORD *)this + 81) && *((_WORD *)this + 81) != 2 && *((_WORD *)this + 81) != 3 && *((_WORD *)this + 81) != 4 )
    MicrosoftTelemetryAssertTriggeredMsgKM(
      "m_Tombstone.PreviousState == TombstoneState::None || m_Tombstone.PreviousState == TombstoneState::Hard || m_Tombst"
      "one.PreviousState == TombstoneState::Replaced || m_Tombstone.PreviousState == TombstoneState::Renamed");
  if ( _InterlockedExchangeAdd((volatile signed __int32 *)this + 42, 0xFFFFFFFF) <= 1 )
  {
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v12 = this;
      v14 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      v11 = 901;
      v10[0] = "UnionFs::UfsPathCachePayload::RevertSoftTombstone";
      v9 = "Reverting Soft";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)word_140097172,
        v3,
        v4,
        (__int64)&v9,
        (__int64)v10,
        (__int64)&v14,
        (__int64)&v11,
        (__int64)&v12);
    }
    if ( _InterlockedCompareExchange16((volatile signed __int16 *)this + 80, *((_WORD *)this + 81), 1) != 1 )
      goto LABEL_6;
    *((_DWORD *)this + 43) = 0;
    *((_QWORD *)this + 22) = 0;
    *((_BYTE *)this + 164) = *((_BYTE *)this + 165);
    if ( !*((_WORD *)this + 81) )
    {
      v6 = (utl::_RefCountBase *)*((_QWORD *)this + 24);
      *((_QWORD *)this + 23) = 0;
      *((_QWORD *)this + 24) = 0;
      if ( v6 )
        utl::_RefCountBase::_DecStrong(v6);
      v7 = *((_QWORD *)this + 25);
      *((_QWORD *)this + 25) = 0;
      if ( v7 )
      {
        if ( !*(_BYTE *)(v7 + 16) )
          *(_OWORD *)v7 = 0;
        FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v7, v2);
        ExFreePoolWithTag((PVOID)v7, 0);
      }
      if ( !*((_QWORD *)this + 4) )
        UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(this, 0x4110012039DLL);
    }
    KeSetEvent((PRKEVENT)(*((_QWORD *)this + 17) + 56LL), 0, 0);
  }
  else if ( (unsigned int)dword_14009E178 > 5
         && (qword_14009E188 & 0x40) != 0
         && (qword_14009E190 & 0x40) == qword_14009E190 )
  {
    v11 = *((_DWORD *)this + 42);
    v14 = (const char *)this;
    v9 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
    v8 = "UnionFs::UfsPathCachePayload::RevertSoftTombstone";
    v10[0] = "SoftCount > 0";
    LODWORD(v12) = 894;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(
      qword_14009E190,
      (unsigned int)byte_140097013,
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
0x1400430fc  push    rbp
0x1400430fe  push    rbx
0x1400430ff  push    rsi
0x140043100  push    rdi
0x140043101  push    r14
0x140043103  mov     rbp, rsp
0x140043106  sub     rsp, 70h
0x14004310a  mov     rdx, [rcx+88h]
0x140043111  mov     rbx, rcx
0x140043114  lea     rcx, [rbp+FastMutex]
0x140043118  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x14004311d  mov     eax, [rbx+0A8h]
0x140043123  xor     esi, esi
0x140043125  nop
0x140043126  test    eax, eax
0x140043128  jnz     loc_1400431E2
0x14004312e  mov     eax, cs:dword_14009E178
0x140043134  cmp     eax, 5
0x140043137  jbe     loc_1400431BF
0x14004313d  mov     rcx, cs:qword_14009E190
0x140043144  mov     rax, cs:qword_14009E188
0x14004314b  test    al, 40h
0x14004314d  jz      short loc_1400431BF
0x14004314f  mov     rax, rcx
0x140043152  and     eax, 40h
0x140043155  cmp     rax, rcx
0x140043158  jnz     short loc_1400431BF
0x14004315a  lea     rax, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140043161  mov     [rbp+arg_8], rbx
0x140043165  mov     [rbp+arg_18], rax
0x140043169  lea     rdx, byte_140097079
0x140043170  lea     rax, aUnionfsUfspath_9; "UnionFs::UfsPathCachePayload::RevertSof"...
0x140043177  mov     [rbp+arg_0], 36Ah
0x14004317e  mov     [rbp+var_20], rax
0x140043182  lea     rax, aSoftcountAlrea; "SoftCount already zero"
0x140043189  mov     [rbp+var_18], rax
0x14004318d  lea     rax, [rbp+arg_8]
0x140043191  mov     [rsp+70h+var_30], rax
0x140043196  lea     rax, [rbp+arg_0]
0x14004319a  mov     [rsp+70h+var_38], rax
0x14004319f  lea     rax, [rbp+arg_18]
0x1400431a3  mov     [rsp+70h+var_40], rax
0x1400431a8  lea     rax, [rbp+var_20]
0x1400431ac  mov     [rsp+70h+var_48], rax
0x1400431b1  lea     rax, [rbp+var_18]
0x1400431b5  mov     [rsp+70h+var_50], rax
0x1400431ba  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x1400431bf  mov     rcx, [rbp+FastMutex]; FastMutex
0x1400431c3  test    rcx, rcx
0x1400431c6  jz      short loc_1400431D4
0x1400431c8  call    cs:__imp_ExReleaseFastMutex
0x1400431cf  nop     dword ptr [rax+rax+00h]
0x1400431d4  xor     al, al
0x1400431d6  add     rsp, 70h
0x1400431da  pop     r14
0x1400431dc  pop     rdi
0x1400431dd  pop     rsi
0x1400431de  pop     rbx
0x1400431df  pop     rbp
0x1400431e0  retn
0x1400431e2  movzx   eax, word ptr [rbx+0A2h]
0x1400431e9  nop
0x1400431ea  test    ax, ax
0x1400431ed  jz      short loc_140043225
0x1400431ef  movzx   eax, word ptr [rbx+0A2h]
0x1400431f6  nop
0x1400431f7  cmp     ax, 2
0x1400431fb  jz      short loc_140043225
0x1400431fd  movzx   eax, word ptr [rbx+0A2h]
0x140043204  nop
0x140043205  cmp     ax, 3
0x140043209  jz      short loc_140043225
0x14004320b  movzx   eax, word ptr [rbx+0A2h]
0x140043212  nop
0x140043213  cmp     ax, 4
0x140043217  jz      short loc_140043225
0x140043219  lea     rcx, aMTombstonePrev; "m_Tombstone.PreviousState == TombstoneS"...
0x140043220  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140043225  nop
0x140043226  or      eax, 0FFFFFFFFh
0x140043229  lock xadd [rbx+0A8h], eax
0x140043231  mov     r14d, 1
0x140043237  nop
0x140043238  sub     eax, r14d
0x14004323b  mov     eax, cs:dword_14009E178
0x140043241  jle     loc_1400432F2
0x140043247  cmp     eax, 5
0x14004324a  jbe     loc_140043450
0x140043250  mov     rcx, cs:qword_14009E190
0x140043257  mov     rax, cs:qword_14009E188
0x14004325e  test    al, 40h
0x140043260  jz      loc_140043450
0x140043266  mov     rax, rcx
0x140043269  and     eax, 40h
0x14004326c  cmp     rax, rcx
0x14004326f  jnz     loc_140043450
0x140043275  mov     eax, [rbx+0A8h]
0x14004327b  lea     rdx, byte_140097013
0x140043282  nop
0x140043283  mov     [rbp+arg_0], eax
0x140043286  lea     rax, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x14004328d  mov     [rbp+arg_18], rbx
0x140043291  mov     [rbp+var_18], rax
0x140043295  lea     rax, aUnionfsUfspath_9; "UnionFs::UfsPathCachePayload::RevertSof"...
0x14004329c  mov     [rbp+var_20], rax
0x1400432a0  lea     rax, aSoftcount0; "SoftCount > 0"
0x1400432a7  mov     [rbp+var_10], rax
0x1400432ab  lea     rax, [rbp+arg_0]
0x1400432af  mov     [rsp+70h+var_28], rax
0x1400432b4  lea     rax, [rbp+arg_18]
0x1400432b8  mov     [rsp+70h+var_30], rax
0x1400432bd  lea     rax, [rbp+arg_8]
0x1400432c1  mov     [rsp+70h+var_38], rax
0x1400432c6  lea     rax, [rbp+var_18]
0x1400432ca  mov     [rsp+70h+var_40], rax
0x1400432cf  lea     rax, [rbp+var_20]
0x1400432d3  mov     [rsp+70h+var_48], rax
0x1400432d8  lea     rax, [rbp+var_10]
0x1400432dc  mov     [rsp+70h+var_50], rax
0x1400432e1  mov     dword ptr [rbp+arg_8], 37Eh
0x1400432e8  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@4@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &)
0x1400432ed  jmp     loc_140043450
0x1400432f2  cmp     eax, 5
0x1400432f5  jbe     loc_14004337D
0x1400432fb  mov     rcx, cs:qword_14009E190
0x140043302  mov     rax, cs:qword_14009E188
0x140043309  test    al, 40h
0x14004330b  jz      short loc_14004337D
0x14004330d  mov     rax, rcx
0x140043310  and     eax, 40h
0x140043313  cmp     rax, rcx
0x140043316  jnz     short loc_14004337D
0x140043318  lea     rax, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x14004331f  mov     [rbp+arg_8], rbx
0x140043323  mov     [rbp+arg_18], rax
0x140043327  lea     rdx, word_140097172
0x14004332e  lea     rax, aUnionfsUfspath_9; "UnionFs::UfsPathCachePayload::RevertSof"...
0x140043335  mov     [rbp+arg_0], 385h
0x14004333c  mov     [rbp+var_10], rax
0x140043340  lea     rax, aRevertingSoft; "Reverting Soft"
0x140043347  mov     [rbp+var_18], rax
0x14004334b  lea     rax, [rbp+arg_8]
0x14004334f  mov     [rsp+70h+var_30], rax
0x140043354  lea     rax, [rbp+arg_0]
0x140043358  mov     [rsp+70h+var_38], rax
0x14004335d  lea     rax, [rbp+arg_18]
0x140043361  mov     [rsp+70h+var_40], rax
0x140043366  lea     rax, [rbp+var_10]
0x14004336a  mov     [rsp+70h+var_48], rax
0x14004336f  lea     rax, [rbp+var_18]
0x140043373  mov     [rsp+70h+var_50], rax
0x140043378  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x14004337d  movzx   ecx, word ptr [rbx+0A2h]
0x140043384  mov     eax, r14d
0x140043387  nop
0x140043388  nop
0x140043389  lock cmpxchg [rbx+0A0h], cx
0x140043392  nop
0x140043393  cmp     ax, r14w
0x140043397  jnz     loc_1400431BF
0x14004339d  mov     [rbx+0ACh], esi
0x1400433a3  mov     [rbx+0B0h], rsi
0x1400433aa  mov     al, [rbx+0A5h]
0x1400433b0  nop
0x1400433b1  nop
0x1400433b2  mov     [rbx+0A4h], al
0x1400433b8  movzx   eax, word ptr [rbx+0A2h]
0x1400433bf  nop
0x1400433c0  test    ax, ax
0x1400433c3  jnz     short loc_140043434
0x1400433c5  mov     rcx, [rbx+0C0h]; this
0x1400433cc  mov     [rbx+0B8h], rsi
0x1400433d3  mov     [rbx+0C0h], rsi
0x1400433da  test    rcx, rcx
0x1400433dd  jz      short loc_1400433E4
0x1400433df  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1400433e4  mov     rdi, [rbx+0C8h]
0x1400433eb  mov     [rbx+0C8h], rsi
0x1400433f2  test    rdi, rdi
0x1400433f5  jz      short loc_14004341C
0x1400433f7  cmp     [rdi+10h], sil
0x1400433fb  jnz     short loc_140043403
0x1400433fd  xorps   xmm0, xmm0
0x140043400  movups  xmmword ptr [rdi], xmm0
0x140043403  mov     rcx, rdi; UnicodeString
0x140043406  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004340b  xor     edx, edx; Tag
0x14004340d  mov     rcx, rdi; P
0x140043410  call    cs:__imp_ExFreePoolWithTag
0x140043417  nop     dword ptr [rax+rax+00h]
0x14004341c  cmp     [rbx+20h], rsi
0x140043420  jnz     short loc_140043434
0x140043422  mov     rdx, 4110012039Dh
0x14004342c  mov     rcx, rbx
0x14004342f  call    ?InvalidateNoRevertSoftTombstone@UfsPathCachePayload@UnionFs@@AEAAXT_TAGGED_SOURCE@@@Z; UnionFs::UfsPathCachePayload::InvalidateNoRevertSoftTombstone(_TAGGED_SOURCE)
0x140043434  mov     rcx, [rbx+88h]
0x14004343b  xor     r8d, r8d; Wait
0x14004343e  add     rcx, 38h ; '8'; Event
0x140043442  xor     edx, edx; Increment
0x140043444  call    cs:__imp_KeSetEvent
0x14004344b  nop     dword ptr [rax+rax+00h]
0x140043450  mov     rcx, [rbp+FastMutex]; FastMutex
0x140043454  test    rcx, rcx
0x140043457  jz      short loc_140043465
0x140043459  call    cs:__imp_ExReleaseFastMutex
0x140043460  nop     dword ptr [rax+rax+00h]
0x140043465  mov     al, r14b
0x140043468  jmp     loc_1400431D6
```
