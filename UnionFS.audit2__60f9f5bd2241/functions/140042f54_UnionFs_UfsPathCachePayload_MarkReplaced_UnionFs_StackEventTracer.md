# UnionFs::UfsPathCachePayload::MarkReplaced(UnionFs::StackEventTracer &)

- ea: `0x140042f54`
- end: `0x140043273`
- name: `?MarkReplaced@UfsPathCachePayload@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z`
- size: `799`
- prototype: `int(UnionFs::UfsPathCachePayload *__hidden this, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140011a60`
- `0x14002ca90`

## callees

- `0x140002500`
- `0x140002b20`
- `0x140042f54`
- `0x140056c44`
- `0x140079cc4`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x1400431be`
- `ntoskrnl!KeSetEvent` at `0x1400431fc`
- `ntoskrnl!KeSetEvent` at `0x1400431be`
- `ntoskrnl!KeSetEvent` at `0x1400431fc`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043211`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043252`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043211`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043252`

## string_xrefs

- `0x140042fd5`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140042fa0`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x140042fdc`: `UnionFs::UfsPathCachePayload::MarkReplaced`
- `0x140043045`: `Marking Replaced tombstone`
- `0x140043221`: `ORIGIN: Marking replaced neither hard nor soft tombstone`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::MarkReplaced(
        UnionFs::UfsPathCachePayload *this,
        struct UnionFs::StackEventTracer *a2)
{
  int v2; // r14d
  int v4; // r8d
  int v5; // r9d
  __int128 **v6; // rcx
  bool v7; // si
  const struct _UNICODE_STRING *v8; // rax
  char v9; // cl
  struct _KEVENT *v10; // rcx
  __int64 v11; // rcx
  char *v13; // [rsp+28h] [rbp-41h]
  PFAST_MUTEX FastMutex; // [rsp+50h] [rbp-19h] BYREF
  const char *v15; // [rsp+58h] [rbp-11h] BYREF
  char v16[8]; // [rsp+60h] [rbp-9h] BYREF
  const char *v17; // [rsp+68h] [rbp-1h] BYREF
  const char *v18; // [rsp+70h] [rbp+7h] BYREF
  __int128 v19; // [rsp+78h] [rbp+Fh] BYREF
  bool v20; // [rsp+D0h] [rbp+67h] BYREF
  int v21; // [rsp+E0h] [rbp+77h] BYREF
  const struct _UNICODE_STRING *v22; // [rsp+E8h] [rbp+7Fh] BYREF

  v2 = (int)a2;
  FsFltWil::AcquireFastMutex(&FastMutex, *((_QWORD *)this + 18));
  if ( !*((_QWORD *)this + 24) || (v6 = (__int128 **)((char *)this + 208), !*((_QWORD *)this + 26)) )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("m_Tombstone.OwningUnion && m_Tombstone.ScratchPath");
    v6 = (__int128 **)((char *)this + 208);
  }
  if ( *((_BYTE *)this + 173) )
    v7 = *((_BYTE *)this + 172) == 0;
  else
    v7 = 1;
  v19 = **v6;
  if ( (unsigned int)dword_14009E178 > 5 && (qword_14009E188 & 0x40) != 0 && (qword_14009E190 & 0x40) == qword_14009E190 )
  {
    v8 = (const struct _UNICODE_STRING *)&v19;
    v20 = v7;
    if ( !*((_QWORD *)&v19 + 1) )
      v8 = &FsTlEmptyUnicodeString;
    v21 = 983;
    v22 = v8;
    v15 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
    v17 = "Marking Replaced tombstone";
    *(_QWORD *)v16 = "UnionFs::UfsPathCachePayload::MarkReplaced";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>>(
      (unsigned int)&FsTlEmptyUnicodeString,
      (unsigned int)byte_1400972A9,
      v4,
      v5,
      (__int64)&v17,
      (__int64)v16,
      (__int64)&v15,
      (__int64)&v21,
      (__int64)&v22,
      (__int64)&v20);
  }
  if ( _InterlockedCompareExchange16((volatile signed __int16 *)this + 84, 3, 2) == 2 )
  {
    *((_WORD *)this + 85) = 2;
    _mm_mfence();
    *((_BYTE *)this + 173) = *((_BYTE *)this + 172);
LABEL_21:
    if ( v7 )
    {
      *(_BYTE *)(*((_QWORD *)this + 24) + 208LL) = 1;
      v11 = *((_QWORD *)UnionFs::g_FilterState + 15);
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 8), 1u) )
        KeSetEvent((PRKEVENT)(v11 + 16), 0, 0);
    }
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    return 0;
  }
  if ( _InterlockedCompareExchange16((volatile signed __int16 *)this + 84, 3, 1) == 1 )
  {
    *((_WORD *)this + 85) = 1;
    _mm_mfence();
    v9 = *((_BYTE *)this + 173);
    *((_BYTE *)this + 173) = *((_BYTE *)this + 172);
    *((_BYTE *)this + 172) = v9;
    *((_DWORD *)this + 44) = 0;
    _mm_mfence();
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v17 = (const char *)this;
      v18 = "SoftCount zeroed";
      LODWORD(v22) = 1020;
      *(_QWORD *)v16 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      v15 = "UnionFs::UfsPathCachePayload::MarkReplaced";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)&dword_1400974EC,
        v4,
        v5,
        (__int64)&v18,
        (__int64)&v15,
        (__int64)v16,
        (__int64)&v22,
        (__int64)&v17);
    }
    v10 = (struct _KEVENT *)(*((_QWORD *)this + 18) + 56LL);
    *((_DWORD *)this + 45) = 0;
    *((_QWORD *)this + 23) = 0;
    KeSetEvent(v10, 0, 0);
    goto LABEL_21;
  }
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC0ED0004LL,
    v2,
    (struct UnionFs::StackEventTracer *)0x3550012040ALL,
    (unsigned __int64)"UnionFs::UfsPathCachePayload::MarkReplaced",
    "ORIGIN: Marking replaced neither hard nor soft tombstone",
    v13);
  if ( FastMutex )
    ExReleaseFastMutex(FastMutex);
  return 3236757508LL;
}

```

## disassembly

```asm
0x140042f54  push    rbp
0x140042f56  push    rbx
0x140042f57  push    rsi
0x140042f58  push    rdi
0x140042f59  push    r12
0x140042f5b  push    r13
0x140042f5d  push    r14
0x140042f5f  lea     rbp, [rsp-27h]
0x140042f64  sub     rsp, 90h
0x140042f6b  mov     r14, rdx
0x140042f6e  mov     rbx, rcx
0x140042f71  mov     rdx, [rcx+90h]
0x140042f78  lea     rcx, [rbp+57h+FastMutex]
0x140042f7c  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140042f81  cmp     qword ptr [rbx+0C0h], 0
0x140042f89  jz      short loc_140042F98
0x140042f8b  lea     rcx, [rbx+0D0h]
0x140042f92  cmp     qword ptr [rcx], 0
0x140042f96  jnz     short loc_140042FB0
0x140042f98  mov     edi, 0D0h
0x140042f9d  mov     rsi, rbx
0x140042fa0  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x140042fa7  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140042fac  lea     rcx, [rbx+rdi]
0x140042fb0  mov     al, [rbx+0ADh]
0x140042fb6  mov     edi, 1
0x140042fbb  nop
0x140042fbc  test    al, al
0x140042fbe  jnz     short loc_140042FC5
0x140042fc0  mov     sil, dil
0x140042fc3  jmp     short loc_140042FD2
0x140042fc5  mov     al, [rbx+0ACh]
0x140042fcb  nop
0x140042fcc  test    al, al
0x140042fce  setz    sil
0x140042fd2  mov     rax, [rcx]
0x140042fd5  lea     r13, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140042fdc  lea     r12, aUnionfsUfspath_43; "UnionFs::UfsPathCachePayload::MarkRepla"...
0x140042fe3  movups  xmm0, xmmword ptr [rax]
0x140042fe6  mov     eax, cs:dword_14009E178
0x140042fec  movdqu  [rbp+57h+var_48], xmm0
0x140042ff1  cmp     eax, 5
0x140042ff4  jbe     loc_140043093
0x140042ffa  mov     rcx, cs:qword_14009E190
0x140043001  mov     rax, cs:qword_14009E188
0x140043008  test    al, 40h
0x14004300a  jz      loc_140043093
0x140043010  mov     rax, rcx
0x140043013  and     eax, 40h
0x140043016  cmp     rax, rcx
0x140043019  jnz     short loc_140043093
0x14004301b  cmp     qword ptr [rbp+57h+var_48+8], 0
0x140043020  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x140043027  lea     rax, [rbp+57h+var_48]
0x14004302b  mov     [rbp+57h+arg_0], sil
0x14004302f  cmovz   rax, rcx
0x140043033  mov     [rbp+57h+arg_10], 3D7h
0x14004303a  mov     [rbp+57h+arg_18], rax
0x14004303e  lea     rdx, byte_1400972A9
0x140043045  lea     rax, aMarkingReplace; "Marking Replaced tombstone"
0x14004304c  mov     [rbp+57h+var_68], r13
0x140043050  mov     [rbp+57h+var_58], rax
0x140043054  lea     rax, [rbp+57h+arg_0]
0x140043058  mov     [rsp+0C0h+var_78], rax
0x14004305d  lea     rax, [rbp+57h+arg_18]
0x140043061  mov     [rsp+0C0h+var_80], rax
0x140043066  lea     rax, [rbp+57h+arg_10]
0x14004306a  mov     [rsp+0C0h+var_88], rax
0x14004306f  lea     rax, [rbp+57h+var_68]
0x140043073  mov     [rsp+0C0h+var_90], rax
0x140043078  lea     rax, [rbp+57h+var_60]
0x14004307c  mov     [rsp+0C0h+var_98], rax; char *
0x140043081  lea     rax, [rbp+57h+var_58]
0x140043085  mov     [rsp+0C0h+var_A0], rax
0x14004308a  mov     qword ptr [rbp+57h+var_60], r12
0x14004308e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<1> const &)
0x140043093  mov     ecx, 2
0x140043098  nop
0x140043099  mov     eax, ecx
0x14004309b  lea     edx, [rcx+1]
0x14004309e  lock cmpxchg [rbx+0A8h], dx
0x1400430a7  cmp     ax, cx
0x1400430aa  nop
0x1400430ab  nop
0x1400430ac  setz    cl
0x1400430af  test    cl, cl
0x1400430b1  jz      short loc_1400430D0
0x1400430b3  mov     [rbx+0AAh], ax
0x1400430ba  mfence
0x1400430bd  mov     al, [rbx+0ACh]
0x1400430c3  nop
0x1400430c4  nop
0x1400430c5  mov     [rbx+0ADh], al
0x1400430cb  jmp     loc_1400431CA
0x1400430d0  mov     eax, edi
0x1400430d2  lock cmpxchg [rbx+0A8h], dx
0x1400430db  nop
0x1400430dc  cmp     ax, di
0x1400430df  jnz     loc_140043221
0x1400430e5  nop
0x1400430e6  mov     [rbx+0AAh], ax
0x1400430ed  mfence
0x1400430f0  mov     cl, [rbx+0ADh]
0x1400430f6  nop
0x1400430f7  mov     al, [rbx+0ACh]
0x1400430fd  nop
0x1400430fe  nop
0x1400430ff  mov     [rbx+0ADh], al
0x140043105  nop
0x140043106  mov     [rbx+0ACh], cl
0x14004310c  nop
0x14004310d  mov     dword ptr [rbx+0B0h], 0
0x140043117  mfence
0x14004311a  mov     eax, cs:dword_14009E178
0x140043120  cmp     eax, 5
0x140043123  jbe     short loc_140043199
0x140043125  mov     rcx, cs:qword_14009E190
0x14004312c  mov     rax, cs:qword_14009E188
0x140043133  test    al, 40h
0x140043135  jz      short loc_140043199
0x140043137  mov     rax, rcx
0x14004313a  and     eax, 40h
0x14004313d  cmp     rax, rcx
0x140043140  jnz     short loc_140043199
0x140043142  lea     rax, aSoftcountZeroe; "SoftCount zeroed"
0x140043149  mov     [rbp+57h+var_58], rbx
0x14004314d  mov     [rbp+57h+var_50], rax
0x140043151  lea     rdx, dword_1400974EC
0x140043158  lea     rax, [rbp+57h+var_58]
0x14004315c  mov     dword ptr [rbp+57h+arg_18], 3FCh
0x140043163  mov     [rsp+0C0h+var_80], rax
0x140043168  lea     rax, [rbp+57h+arg_18]
0x14004316c  mov     [rsp+0C0h+var_88], rax
0x140043171  lea     rax, [rbp+57h+var_60]
0x140043175  mov     [rsp+0C0h+var_90], rax
0x14004317a  lea     rax, [rbp+57h+var_68]
0x14004317e  mov     [rsp+0C0h+var_98], rax
0x140043183  lea     rax, [rbp+57h+var_50]
0x140043187  mov     [rsp+0C0h+var_A0], rax
0x14004318c  mov     qword ptr [rbp+57h+var_60], r13
0x140043190  mov     [rbp+57h+var_68], r12
0x140043194  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140043199  mov     rcx, [rbx+90h]
0x1400431a0  xor     r8d, r8d; Wait
0x1400431a3  add     rcx, 38h ; '8'; Event
0x1400431a7  mov     dword ptr [rbx+0B4h], 0
0x1400431b1  xor     edx, edx; Increment
0x1400431b3  mov     qword ptr [rbx+0B8h], 0
0x1400431be  call    cs:__imp_KeSetEvent
0x1400431c5  nop     dword ptr [rax+rax+00h]
0x1400431ca  test    sil, sil
0x1400431cd  jz      short loc_140043208
0x1400431cf  mov     rax, [rbx+0C0h]
0x1400431d6  mov     [rax+0D0h], dil
0x1400431dd  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x1400431e4  mov     rcx, [rax+78h]
0x1400431e8  nop
0x1400431e9  lock xadd [rcx+8], edi
0x1400431ee  nop
0x1400431ef  test    edi, edi
0x1400431f1  jnz     short loc_140043208
0x1400431f3  add     rcx, 10h; Event
0x1400431f7  xor     r8d, r8d; Wait
0x1400431fa  xor     edx, edx; Increment
0x1400431fc  call    cs:__imp_KeSetEvent
0x140043203  nop     dword ptr [rax+rax+00h]
0x140043208  mov     rcx, [rbp+57h+FastMutex]; FastMutex
0x14004320c  test    rcx, rcx
0x14004320f  jz      short loc_14004321D
0x140043211  call    cs:__imp_ExReleaseFastMutex
0x140043218  nop     dword ptr [rax+rax+00h]
0x14004321d  xor     eax, eax
0x14004321f  jmp     short loc_140043260
0x140043221  lea     rax, aOriginMarkingR; "ORIGIN: Marking replaced neither hard n"...
0x140043228  mov     ebx, 0C0ED0004h
0x14004322d  mov     ecx, ebx; this
0x14004322f  mov     [rsp+0C0h+var_A0], rax; char *
0x140043234  mov     r9, r12; unsigned __int64
0x140043237  mov     r8, 3550012040Ah; struct UnionFs::StackEventTracer *
0x140043241  mov     rdx, r14; int
0x140043244  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x140043249  mov     rcx, [rbp+57h+FastMutex]; FastMutex
0x14004324d  test    rcx, rcx
0x140043250  jz      short loc_14004325E
0x140043252  call    cs:__imp_ExReleaseFastMutex
0x140043259  nop     dword ptr [rax+rax+00h]
0x14004325e  mov     eax, ebx
0x140043260  add     rsp, 90h
0x140043267  pop     r14
0x140043269  pop     r13
0x14004326b  pop     r12
0x14004326d  pop     rdi
0x14004326e  pop     rsi
0x14004326f  pop     rbx
0x140043270  pop     rbp
0x140043271  retn
```
