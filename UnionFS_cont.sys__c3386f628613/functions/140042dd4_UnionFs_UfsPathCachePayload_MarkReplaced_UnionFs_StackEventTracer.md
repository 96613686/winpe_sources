# UnionFs::UfsPathCachePayload::MarkReplaced(UnionFs::StackEventTracer &)

- ea: `0x140042dd4`
- end: `0x1400430f3`
- name: `?MarkReplaced@UfsPathCachePayload@UnionFs@@QEAAJAEAVStackEventTracer@2@@Z`
- size: `799`
- prototype: `int(UnionFs::UfsPathCachePayload *__hidden this, struct UnionFs::StackEventTracer *)`
- caller_count: `2`
- callee_count: `6`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140011a40`
- `0x14002c9f0`

## callees

- `0x140002500`
- `0x140002b20`
- `0x140042dd4`
- `0x140056ac4`
- `0x1400799a4`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!KeSetEvent` at `0x14004303e`
- `ntoskrnl!KeSetEvent` at `0x14004307c`
- `ntoskrnl!KeSetEvent` at `0x14004303e`
- `ntoskrnl!KeSetEvent` at `0x14004307c`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043091`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400430d2`
- `ntoskrnl!ExReleaseFastMutex` at `0x140043091`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400430d2`

## string_xrefs

- `0x140042e55`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140042e20`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x140042e5c`: `UnionFs::UfsPathCachePayload::MarkReplaced`
- `0x140042ec5`: `Marking Replaced tombstone`
- `0x1400430a1`: `ORIGIN: Marking replaced neither hard nor soft tombstone`

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
  FsFltWil::AcquireFastMutex(&FastMutex, *((_QWORD *)this + 17));
  if ( !*((_QWORD *)this + 23) || (v6 = (__int128 **)((char *)this + 200), !*((_QWORD *)this + 25)) )
  {
    MicrosoftTelemetryAssertTriggeredMsgKM("m_Tombstone.OwningUnion && m_Tombstone.ScratchPath");
    v6 = (__int128 **)((char *)this + 200);
  }
  if ( *((_BYTE *)this + 165) )
    v7 = *((_BYTE *)this + 164) == 0;
  else
    v7 = 1;
  v19 = **v6;
  if ( (unsigned int)dword_14009E178 > 5 && (qword_14009E188 & 0x40) != 0 && (qword_14009E190 & 0x40) == qword_14009E190 )
  {
    v8 = (const struct _UNICODE_STRING *)&v19;
    v20 = v7;
    if ( !*((_QWORD *)&v19 + 1) )
      v8 = &FsTlEmptyUnicodeString;
    v21 = 958;
    v22 = v8;
    v15 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
    v17 = "Marking Replaced tombstone";
    *(_QWORD *)v16 = "UnionFs::UfsPathCachePayload::MarkReplaced";
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>>(
      (unsigned int)&FsTlEmptyUnicodeString,
      (unsigned int)&dword_1400971BC,
      v4,
      v5,
      (__int64)&v17,
      (__int64)v16,
      (__int64)&v15,
      (__int64)&v21,
      (__int64)&v22,
      (__int64)&v20);
  }
  if ( _InterlockedCompareExchange16((volatile signed __int16 *)this + 80, 3, 2) == 2 )
  {
    *((_WORD *)this + 81) = 2;
    _mm_mfence();
    *((_BYTE *)this + 165) = *((_BYTE *)this + 164);
LABEL_21:
    if ( v7 )
    {
      *(_BYTE *)(*((_QWORD *)this + 23) + 208LL) = 1;
      v11 = *((_QWORD *)UnionFs::g_FilterState + 15);
      if ( !_InterlockedExchangeAdd((volatile signed __int32 *)(v11 + 8), 1u) )
        KeSetEvent((PRKEVENT)(v11 + 16), 0, 0);
    }
    if ( FastMutex )
      ExReleaseFastMutex(FastMutex);
    return 0;
  }
  if ( _InterlockedCompareExchange16((volatile signed __int16 *)this + 80, 3, 1) == 1 )
  {
    *((_WORD *)this + 81) = 1;
    _mm_mfence();
    v9 = *((_BYTE *)this + 165);
    *((_BYTE *)this + 165) = *((_BYTE *)this + 164);
    *((_BYTE *)this + 164) = v9;
    *((_DWORD *)this + 42) = 0;
    _mm_mfence();
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v17 = (const char *)this;
      v18 = "SoftCount zeroed";
      LODWORD(v22) = 995;
      *(_QWORD *)v16 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      v15 = "UnionFs::UfsPathCachePayload::MarkReplaced";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)&byte_1400973FF,
        v4,
        v5,
        (__int64)&v18,
        (__int64)&v15,
        (__int64)v16,
        (__int64)&v22,
        (__int64)&v17);
    }
    v10 = (struct _KEVENT *)(*((_QWORD *)this + 17) + 56LL);
    *((_DWORD *)this + 43) = 0;
    *((_QWORD *)this + 22) = 0;
    KeSetEvent(v10, 0, 0);
    goto LABEL_21;
  }
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC0ED0004LL,
    v2,
    (struct UnionFs::StackEventTracer *)0x355001203F1LL,
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
0x140042dd4  push    rbp
0x140042dd6  push    rbx
0x140042dd7  push    rsi
0x140042dd8  push    rdi
0x140042dd9  push    r12
0x140042ddb  push    r13
0x140042ddd  push    r14
0x140042ddf  lea     rbp, [rsp-27h]
0x140042de4  sub     rsp, 90h
0x140042deb  mov     r14, rdx
0x140042dee  mov     rbx, rcx
0x140042df1  mov     rdx, [rcx+88h]
0x140042df8  lea     rcx, [rbp+57h+FastMutex]
0x140042dfc  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140042e01  cmp     qword ptr [rbx+0B8h], 0
0x140042e09  jz      short loc_140042E18
0x140042e0b  lea     rcx, [rbx+0C8h]
0x140042e12  cmp     qword ptr [rcx], 0
0x140042e16  jnz     short loc_140042E30
0x140042e18  mov     edi, 0C8h
0x140042e1d  mov     rsi, rbx
0x140042e20  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x140042e27  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140042e2c  lea     rcx, [rbx+rdi]
0x140042e30  mov     al, [rbx+0A5h]
0x140042e36  mov     edi, 1
0x140042e3b  nop
0x140042e3c  test    al, al
0x140042e3e  jnz     short loc_140042E45
0x140042e40  mov     sil, dil
0x140042e43  jmp     short loc_140042E52
0x140042e45  mov     al, [rbx+0A4h]
0x140042e4b  nop
0x140042e4c  test    al, al
0x140042e4e  setz    sil
0x140042e52  mov     rax, [rcx]
0x140042e55  lea     r13, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140042e5c  lea     r12, aUnionfsUfspath_44; "UnionFs::UfsPathCachePayload::MarkRepla"...
0x140042e63  movups  xmm0, xmmword ptr [rax]
0x140042e66  mov     eax, cs:dword_14009E178
0x140042e6c  movdqu  [rbp+57h+var_48], xmm0
0x140042e71  cmp     eax, 5
0x140042e74  jbe     loc_140042F13
0x140042e7a  mov     rcx, cs:qword_14009E190
0x140042e81  mov     rax, cs:qword_14009E188
0x140042e88  test    al, 40h
0x140042e8a  jz      loc_140042F13
0x140042e90  mov     rax, rcx
0x140042e93  and     eax, 40h
0x140042e96  cmp     rax, rcx
0x140042e99  jnz     short loc_140042F13
0x140042e9b  cmp     qword ptr [rbp+57h+var_48+8], 0
0x140042ea0  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x140042ea7  lea     rax, [rbp+57h+var_48]
0x140042eab  mov     [rbp+57h+arg_0], sil
0x140042eaf  cmovz   rax, rcx
0x140042eb3  mov     [rbp+57h+arg_10], 3BEh
0x140042eba  mov     [rbp+57h+arg_18], rax
0x140042ebe  lea     rdx, dword_1400971BC
0x140042ec5  lea     rax, aMarkingReplace; "Marking Replaced tombstone"
0x140042ecc  mov     [rbp+57h+var_68], r13
0x140042ed0  mov     [rbp+57h+var_58], rax
0x140042ed4  lea     rax, [rbp+57h+arg_0]
0x140042ed8  mov     [rsp+0C0h+var_78], rax
0x140042edd  lea     rax, [rbp+57h+arg_18]
0x140042ee1  mov     [rsp+0C0h+var_80], rax
0x140042ee6  lea     rax, [rbp+57h+arg_10]
0x140042eea  mov     [rsp+0C0h+var_88], rax
0x140042eef  lea     rax, [rbp+57h+var_68]
0x140042ef3  mov     [rsp+0C0h+var_90], rax
0x140042ef8  lea     rax, [rbp+57h+var_60]
0x140042efc  mov     [rsp+0C0h+var_98], rax; char *
0x140042f01  lea     rax, [rbp+57h+var_58]
0x140042f05  mov     [rsp+0C0h+var_A0], rax
0x140042f0a  mov     qword ptr [rbp+57h+var_60], r12
0x140042f0e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@U?$_tlgWrapperByVal@$00@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@AEBU?$_tlgWrapperByVal@$00@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapBuffer<_UNICODE_STRING>,_tlgWrapperByVal<1>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapBuffer<_UNICODE_STRING> const &,_tlgWrapperByVal<1> const &)
0x140042f13  mov     ecx, 2
0x140042f18  nop
0x140042f19  mov     eax, ecx
0x140042f1b  lea     edx, [rcx+1]
0x140042f1e  lock cmpxchg [rbx+0A0h], dx
0x140042f27  cmp     ax, cx
0x140042f2a  nop
0x140042f2b  nop
0x140042f2c  setz    cl
0x140042f2f  test    cl, cl
0x140042f31  jz      short loc_140042F50
0x140042f33  mov     [rbx+0A2h], ax
0x140042f3a  mfence
0x140042f3d  mov     al, [rbx+0A4h]
0x140042f43  nop
0x140042f44  nop
0x140042f45  mov     [rbx+0A5h], al
0x140042f4b  jmp     loc_14004304A
0x140042f50  mov     eax, edi
0x140042f52  lock cmpxchg [rbx+0A0h], dx
0x140042f5b  nop
0x140042f5c  cmp     ax, di
0x140042f5f  jnz     loc_1400430A1
0x140042f65  nop
0x140042f66  mov     [rbx+0A2h], ax
0x140042f6d  mfence
0x140042f70  mov     cl, [rbx+0A5h]
0x140042f76  nop
0x140042f77  mov     al, [rbx+0A4h]
0x140042f7d  nop
0x140042f7e  nop
0x140042f7f  mov     [rbx+0A5h], al
0x140042f85  nop
0x140042f86  mov     [rbx+0A4h], cl
0x140042f8c  nop
0x140042f8d  mov     dword ptr [rbx+0A8h], 0
0x140042f97  mfence
0x140042f9a  mov     eax, cs:dword_14009E178
0x140042fa0  cmp     eax, 5
0x140042fa3  jbe     short loc_140043019
0x140042fa5  mov     rcx, cs:qword_14009E190
0x140042fac  mov     rax, cs:qword_14009E188
0x140042fb3  test    al, 40h
0x140042fb5  jz      short loc_140043019
0x140042fb7  mov     rax, rcx
0x140042fba  and     eax, 40h
0x140042fbd  cmp     rax, rcx
0x140042fc0  jnz     short loc_140043019
0x140042fc2  lea     rax, aSoftcountZeroe; "SoftCount zeroed"
0x140042fc9  mov     [rbp+57h+var_58], rbx
0x140042fcd  mov     [rbp+57h+var_50], rax
0x140042fd1  lea     rdx, byte_1400973FF
0x140042fd8  lea     rax, [rbp+57h+var_58]
0x140042fdc  mov     dword ptr [rbp+57h+arg_18], 3E3h
0x140042fe3  mov     [rsp+0C0h+var_80], rax
0x140042fe8  lea     rax, [rbp+57h+arg_18]
0x140042fec  mov     [rsp+0C0h+var_88], rax
0x140042ff1  lea     rax, [rbp+57h+var_60]
0x140042ff5  mov     [rsp+0C0h+var_90], rax
0x140042ffa  lea     rax, [rbp+57h+var_68]
0x140042ffe  mov     [rsp+0C0h+var_98], rax
0x140043003  lea     rax, [rbp+57h+var_50]
0x140043007  mov     [rsp+0C0h+var_A0], rax
0x14004300c  mov     qword ptr [rbp+57h+var_60], r13
0x140043010  mov     [rbp+57h+var_68], r12
0x140043014  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140043019  mov     rcx, [rbx+88h]
0x140043020  xor     r8d, r8d; Wait
0x140043023  add     rcx, 38h ; '8'; Event
0x140043027  mov     dword ptr [rbx+0ACh], 0
0x140043031  xor     edx, edx; Increment
0x140043033  mov     qword ptr [rbx+0B0h], 0
0x14004303e  call    cs:__imp_KeSetEvent
0x140043045  nop     dword ptr [rax+rax+00h]
0x14004304a  test    sil, sil
0x14004304d  jz      short loc_140043088
0x14004304f  mov     rax, [rbx+0B8h]
0x140043056  mov     [rax+0D0h], dil
0x14004305d  mov     rax, cs:?g_FilterState@UnionFs@@3PEAVUnionFsFilter@1@EA; UnionFs::UnionFsFilter * UnionFs::g_FilterState
0x140043064  mov     rcx, [rax+78h]
0x140043068  nop
0x140043069  lock xadd [rcx+8], edi
0x14004306e  nop
0x14004306f  test    edi, edi
0x140043071  jnz     short loc_140043088
0x140043073  add     rcx, 10h; Event
0x140043077  xor     r8d, r8d; Wait
0x14004307a  xor     edx, edx; Increment
0x14004307c  call    cs:__imp_KeSetEvent
0x140043083  nop     dword ptr [rax+rax+00h]
0x140043088  mov     rcx, [rbp+57h+FastMutex]; FastMutex
0x14004308c  test    rcx, rcx
0x14004308f  jz      short loc_14004309D
0x140043091  call    cs:__imp_ExReleaseFastMutex
0x140043098  nop     dword ptr [rax+rax+00h]
0x14004309d  xor     eax, eax
0x14004309f  jmp     short loc_1400430E0
0x1400430a1  lea     rax, aOriginMarkingR; "ORIGIN: Marking replaced neither hard n"...
0x1400430a8  mov     ebx, 0C0ED0004h
0x1400430ad  mov     ecx, ebx; this
0x1400430af  mov     [rsp+0C0h+var_A0], rax; char *
0x1400430b4  mov     r9, r12; unsigned __int64
0x1400430b7  mov     r8, 355001203F1h; struct UnionFs::StackEventTracer *
0x1400430c1  mov     rdx, r14; int
0x1400430c4  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
0x1400430c9  mov     rcx, [rbp+57h+FastMutex]; FastMutex
0x1400430cd  test    rcx, rcx
0x1400430d0  jz      short loc_1400430DE
0x1400430d2  call    cs:__imp_ExReleaseFastMutex
0x1400430d9  nop     dword ptr [rax+rax+00h]
0x1400430de  mov     eax, ebx
0x1400430e0  add     rsp, 90h
0x1400430e7  pop     r14
0x1400430e9  pop     r13
0x1400430eb  pop     r12
0x1400430ed  pop     rdi
0x1400430ee  pop     rsi
0x1400430ef  pop     rbx
0x1400430f0  pop     rbp
0x1400430f1  retn
```
