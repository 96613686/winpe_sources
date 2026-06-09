# UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv(utl::shared_ptr<UnionFs::UfsUnionCtx>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::SoftTombstoneReason,UnionFs::StackEventTracer &)

- ea: `0x140041c98`
- end: `0x140042269`
- name: `?ConvertToSoftTombstonePriv@UfsPathCachePayload@UnionFs@@AEAAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@4@W4SoftTombstoneReason@2@AEAVStackEventTracer@2@@Z`
- size: `1489`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x1400419c8`
- `0x140041b30`

## callees

- `0x1400029d0`
- `0x140002f28`
- `0x14000f81c`
- `0x14003ff34`
- `0x140041c98`
- `0x140056c44`
- `0x140079cc4`
- `0x140079f68`
- `0x14007b2b0`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140041ef6`
- `ntoskrnl!KeClearEvent` at `0x140041ef6`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041fd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042160`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041fd3`
- `ntoskrnl!ExFreePoolWithTag` at `0x140042160`
- `ntoskrnl!KeSetEvent` at `0x1400421a9`
- `ntoskrnl!KeSetEvent` at `0x1400421a9`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400421f3`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042238`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400421f3`
- `ntoskrnl!ExReleaseFastMutex` at `0x140042238`

## string_xrefs

- `0x140041d3f`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140041e8d`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140041d25`: `UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv`
- `0x140041dac`: `UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv`
- `0x140041f63`: `!m_Tombstone.OwningUnion && !m_Tombstone.ScratchPath`
- `0x140042039`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x14004209f`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x140042182`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x140042223`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`

## pseudocode

```c
__int64 __fastcall UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv(
        __int64 a1,
        __int64 *a2,
        __int128 **a3,
        int a4,
        int a5)
{
  const char *v6; // r14
  int v9; // r8d
  int v10; // r9d
  int v11; // eax
  __int128 *v12; // rax
  __int16 *v13; // rdx
  const struct _UNICODE_STRING *v14; // rax
  signed __int16 v15; // ax
  __int64 v16; // rax
  struct _UNICODE_STRING *v17; // rdx
  utl::_RefCountBase *v18; // rcx
  __int128 *v19; // rax
  __int64 v20; // r14
  __int64 v21; // rax
  struct _UNICODE_STRING *v22; // rdx
  utl::_RefCountBase *v23; // rcx
  __int128 *v24; // rax
  __int64 v25; // r14
  utl::_RefCountBase *v26; // rcx
  utl::_RefCountBase *v28; // rcx
  char *v29; // [rsp+28h] [rbp-89h]
  PFAST_MUTEX FastMutex; // [rsp+60h] [rbp-51h] BYREF
  const char *v31; // [rsp+68h] [rbp-49h] BYREF
  char v32[8]; // [rsp+70h] [rbp-41h] BYREF
  const char *v33; // [rsp+78h] [rbp-39h] BYREF
  const char *v34; // [rsp+80h] [rbp-31h] BYREF
  const char *v35; // [rsp+88h] [rbp-29h] BYREF
  const char *v36; // [rsp+90h] [rbp-21h] BYREF
  __int128 v37; // [rsp+98h] [rbp-19h] BYREF
  __int64 v38; // [rsp+A8h] [rbp-9h] BYREF
  int v39; // [rsp+B0h] [rbp-1h]
  int v40; // [rsp+B4h] [rbp+3h]
  char v41; // [rsp+B8h] [rbp+7h]
  int v42; // [rsp+110h] [rbp+5Fh] BYREF

  v6 = (const char *)a4;
  FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(a1 + 144));
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 176)) > 1 )
  {
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v11 = *(_DWORD *)(a1 + 176);
      *(_QWORD *)v32 = v6;
      v35 = "UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv";
      v42 = v11;
      v34 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      v36 = "SoftCount > 1";
      v33 = (const char *)a1;
      LODWORD(v31) = 662;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)&word_14009730E,
        v9,
        v10,
        (__int64)&v36,
        (__int64)&v35,
        (__int64)&v34,
        (__int64)&v31,
        (__int64)&v33,
        (__int64)&v42,
        (__int64)v32);
    }
    goto LABEL_60;
  }
  v40 = HIDWORD(v37);
  v12 = *(__int128 **)(a1 + 208);
  v38 = a1;
  v39 = (int)v6;
  if ( v12 )
  {
    v37 = *v12;
    if ( (unsigned int)dword_14009E178 <= 5
      || (qword_14009E188 & 0x40) == 0
      || (qword_14009E190 & 0x40) != qword_14009E190 )
    {
      goto LABEL_19;
    }
    v42 = 688;
    v13 = (__int16 *)byte_140097143;
  }
  else
  {
    if ( !*a3 )
      goto LABEL_19;
    v37 = **a3;
    if ( (unsigned int)dword_14009E178 <= 5
      || (qword_14009E188 & 0x40) == 0
      || (qword_14009E190 & 0x40) != qword_14009E190 )
    {
      goto LABEL_19;
    }
    v42 = 697;
    v13 = word_1400975AA;
  }
  v14 = (const struct _UNICODE_STRING *)&v37;
  v35 = v6;
  if ( !*((_QWORD *)&v37 + 1) )
    v14 = &FsTlEmptyUnicodeString;
  v34 = (const char *)a1;
  v36 = (const char *)v14;
  v33 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
  v31 = "Converting to Soft";
  *(_QWORD *)v32 = "UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv";
  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(
    (unsigned int)&FsTlEmptyUnicodeString,
    (_DWORD)v13,
    v9,
    v10,
    (__int64)&v31,
    (__int64)v32,
    (__int64)&v33,
    (__int64)&v42,
    (__int64)&v34,
    (__int64)&v35,
    (__int64)&v36);
LABEL_19:
  KeClearEvent((PRKEVENT)(*(_QWORD *)(a1 + 144) + 56LL));
  *(_BYTE *)(a1 + 173) = *(_BYTE *)(a1 + 172);
  *(_BYTE *)(a1 + 172) = 1;
  v15 = _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 168), 1, 0);
  if ( !v15 )
  {
    *(_WORD *)(a1 + 170) = 0;
    _mm_mfence();
    *(_DWORD *)(a1 + 180) = (_DWORD)v6;
    *(_QWORD *)(a1 + 184) = KeGetCurrentThread();
    if ( *(_QWORD *)(a1 + 192) || *(_QWORD *)(a1 + 208) )
      MicrosoftTelemetryAssertTriggeredMsgKM("!m_Tombstone.OwningUnion && !m_Tombstone.ScratchPath");
    v16 = *a2;
    v17 = (struct _UNICODE_STRING *)a2[1];
    *a2 = 0;
    a2[1] = 0;
    v18 = *(utl::_RefCountBase **)(a1 + 200);
    *(_QWORD *)(a1 + 192) = v16;
    *(_QWORD *)(a1 + 200) = v17;
    if ( v18 )
      utl::_RefCountBase::_DecStrong(v18);
    v19 = *a3;
    *a3 = 0;
    v20 = *(_QWORD *)(a1 + 208);
    *(_QWORD *)(a1 + 208) = v19;
    if ( v20 )
    {
      if ( !*(_BYTE *)(v20 + 16) )
        *(_OWORD *)v20 = 0;
      FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v20, v17);
      ExFreePoolWithTag((PVOID)v20, 0);
    }
    goto LABEL_60;
  }
  if ( v15 == 2 )
  {
    v15 = _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 168), 1, 2);
    if ( v15 == 2 )
    {
      *(_WORD *)(a1 + 170) = 2;
      _mm_mfence();
      *(_DWORD *)(a1 + 180) = (_DWORD)v6;
      *(_QWORD *)(a1 + 184) = KeGetCurrentThread();
      if ( *(_QWORD *)(a1 + 192) && *(_QWORD *)(a1 + 208) )
        goto LABEL_60;
      goto LABEL_59;
    }
  }
  if ( v15 == 3 )
  {
    v15 = _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 168), 1, 3);
    if ( v15 == 3 )
    {
      *(_WORD *)(a1 + 170) = 3;
      _mm_mfence();
      *(_DWORD *)(a1 + 180) = (_DWORD)v6;
      *(_QWORD *)(a1 + 184) = KeGetCurrentThread();
      if ( *(_QWORD *)(a1 + 192) && *(_QWORD *)(a1 + 208) )
        goto LABEL_60;
      goto LABEL_59;
    }
  }
  if ( v15 == 4 )
  {
    v15 = _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 168), 1, 4);
    if ( v15 == 4 )
    {
      *(_WORD *)(a1 + 170) = 4;
      _mm_mfence();
      *(_DWORD *)(a1 + 180) = (_DWORD)v6;
      *(_QWORD *)(a1 + 184) = KeGetCurrentThread();
      v21 = *a2;
      v22 = (struct _UNICODE_STRING *)a2[1];
      *a2 = 0;
      a2[1] = 0;
      v23 = *(utl::_RefCountBase **)(a1 + 200);
      *(_QWORD *)(a1 + 192) = v21;
      *(_QWORD *)(a1 + 200) = v22;
      if ( v23 )
        utl::_RefCountBase::_DecStrong(v23);
      if ( !*(_QWORD *)(a1 + 208) )
      {
        v24 = *a3;
        *a3 = 0;
        v25 = *(_QWORD *)(a1 + 208);
        *(_QWORD *)(a1 + 208) = v24;
        if ( v25 )
        {
          if ( !*(_BYTE *)(v25 + 16) )
            *(_OWORD *)v25 = 0;
          FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v25, v22);
          ExFreePoolWithTag((PVOID)v25, 0);
        }
      }
      if ( *(_QWORD *)(a1 + 192) && *(_QWORD *)(a1 + 208) )
        goto LABEL_60;
LABEL_59:
      MicrosoftTelemetryAssertTriggeredMsgKM("m_Tombstone.OwningUnion && m_Tombstone.ScratchPath");
LABEL_60:
      if ( FastMutex )
        ExReleaseFastMutex(FastMutex);
      v28 = (utl::_RefCountBase *)a2[1];
      if ( v28 )
        utl::_RefCountBase::_DecStrong(v28);
      return 0;
    }
  }
  if ( v15 == 1 )
  {
    if ( *(_QWORD *)(a1 + 192) && *(_QWORD *)(a1 + 208) )
      goto LABEL_60;
    goto LABEL_59;
  }
  KeSetEvent((PRKEVENT)(*(_QWORD *)(a1 + 144) + 56LL), 0, 0);
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC0ED0004LL,
    a5,
    (struct UnionFs::StackEventTracer *)0x32700120320LL,
    (unsigned __int64)"UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv",
    "ORIGIN: Tombstone wasn't in expected state",
    v29);
  v41 = 0;
  lambda_1f7054299923819f6004ef867da713ee_::operator()(&v38);
  if ( FastMutex )
    ExReleaseFastMutex(FastMutex);
  v26 = (utl::_RefCountBase *)a2[1];
  if ( v26 )
    utl::_RefCountBase::_DecStrong(v26);
  return 3236757508LL;
}

```

## disassembly

```asm
0x140041c98  push    rbp
0x140041c9a  push    rbx
0x140041c9b  push    rsi
0x140041c9c  push    rdi
0x140041c9d  push    r12
0x140041c9f  push    r13
0x140041ca1  push    r14
0x140041ca3  push    r15
0x140041ca5  lea     rbp, [rsp-17h]
0x140041caa  sub     rsp, 0C8h
0x140041cb1  mov     rsi, rdx
0x140041cb4  movsxd  r14, r9d
0x140041cb7  mov     rdx, [rcx+90h]
0x140041cbe  mov     rdi, rcx
0x140041cc1  lea     rcx, [rbp+4Fh+FastMutex]
0x140041cc5  mov     r15, r8
0x140041cc8  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140041ccd  mov     r13d, 1
0x140041cd3  nop
0x140041cd4  mov     eax, r13d
0x140041cd7  lock xadd [rdi+0B0h], eax
0x140041cdf  inc     eax
0x140041ce1  nop
0x140041ce2  cmp     eax, r13d
0x140041ce5  jle     loc_140041DA9
0x140041ceb  mov     eax, cs:dword_14009E178
0x140041cf1  cmp     eax, 5
0x140041cf4  jbe     loc_14004222F
0x140041cfa  mov     rcx, cs:qword_14009E190
0x140041d01  mov     rax, cs:qword_14009E188
0x140041d08  test    al, 40h
0x140041d0a  jz      loc_14004222F
0x140041d10  mov     rax, rcx
0x140041d13  and     eax, 40h
0x140041d16  cmp     rax, rcx
0x140041d19  jnz     loc_14004222F
0x140041d1f  mov     eax, [rdi+0B0h]
0x140041d25  lea     r12, aUnionfsUfspath_17; "UnionFs::UfsPathCachePayload::ConvertTo"...
0x140041d2c  mov     qword ptr [rbp+4Fh+var_90], r14
0x140041d30  lea     rdx, word_14009730E
0x140041d37  nop
0x140041d38  mov     [rbp+4Fh+var_78], r12
0x140041d3c  mov     [rbp+4Fh+arg_0], eax
0x140041d3f  lea     rax, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140041d46  mov     [rbp+4Fh+var_80], rax
0x140041d4a  lea     rax, aSoftcount1; "SoftCount > 1"
0x140041d51  mov     [rbp+4Fh+var_70], rax
0x140041d55  lea     rax, [rbp+4Fh+var_90]
0x140041d59  mov     [rsp+100h+var_B0], rax
0x140041d5e  lea     rax, [rbp+4Fh+arg_0]
0x140041d62  mov     [rsp+100h+var_B8], rax
0x140041d67  lea     rax, [rbp+4Fh+var_88]
0x140041d6b  mov     [rsp+100h+var_C0], rax
0x140041d70  lea     rax, [rbp+4Fh+var_98]
0x140041d74  mov     [rsp+100h+var_C8], rax
0x140041d79  lea     rax, [rbp+4Fh+var_80]
0x140041d7d  mov     [rsp+100h+var_D0], rax
0x140041d82  lea     rax, [rbp+4Fh+var_78]
0x140041d86  mov     [rsp+100h+var_D8], rax
0x140041d8b  lea     rax, [rbp+4Fh+var_70]
0x140041d8f  mov     [rsp+100h+var_E0], rax
0x140041d94  mov     [rbp+4Fh+var_88], rdi
0x140041d98  mov     dword ptr [rbp+4Fh+var_98], 296h
0x140041d9f  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140041da4  jmp     loc_14004222F
0x140041da9  mov     eax, [rbp+4Fh+var_5C]
0x140041dac  lea     r12, aUnionfsUfspath_17; "UnionFs::UfsPathCachePayload::ConvertTo"...
0x140041db3  mov     [rbp+4Fh+var_4C], eax
0x140041db6  xor     ebx, ebx
0x140041db8  mov     rax, [rdi+0D0h]
0x140041dbf  mov     [rbp+4Fh+var_58], rdi
0x140041dc3  mov     [rbp+4Fh+var_50], r14d
0x140041dc7  test    rax, rax
0x140041dca  jz      short loc_140041E18
0x140041dcc  movups  xmm0, xmmword ptr [rax]
0x140041dcf  mov     eax, cs:dword_14009E178
0x140041dd5  movdqu  xmmword ptr [rbp-19h], xmm0
0x140041dda  cmp     eax, 5
0x140041ddd  jbe     loc_140041EEB
0x140041de3  mov     rcx, cs:qword_14009E190
0x140041dea  mov     rax, cs:qword_14009E188
0x140041df1  test    al, 40h
0x140041df3  jz      loc_140041EEB
0x140041df9  mov     rax, rcx
0x140041dfc  and     eax, 40h
0x140041dff  cmp     rax, rcx
0x140041e02  jnz     loc_140041EEB
0x140041e08  mov     [rbp+4Fh+arg_0], 2B0h
0x140041e0f  lea     rdx, byte_140097143
0x140041e16  jmp     short loc_140041E6E
0x140041e18  mov     rax, [r15]
0x140041e1b  test    rax, rax
0x140041e1e  jz      loc_140041EEB
0x140041e24  movups  xmm0, xmmword ptr [rax]
0x140041e27  mov     eax, cs:dword_14009E178
0x140041e2d  movdqu  xmmword ptr [rbp-19h], xmm0
0x140041e32  cmp     eax, 5
0x140041e35  jbe     loc_140041EEB
0x140041e3b  mov     rcx, cs:qword_14009E190
0x140041e42  mov     rax, cs:qword_14009E188
0x140041e49  test    al, 40h
0x140041e4b  jz      loc_140041EEB
0x140041e51  mov     rax, rcx
0x140041e54  and     eax, 40h
0x140041e57  cmp     rax, rcx
0x140041e5a  jnz     loc_140041EEB
0x140041e60  mov     [rbp+4Fh+arg_0], 2B9h
0x140041e67  lea     rdx, word_1400975AA
0x140041e6e  cmp     [rbp-11h], rbx
0x140041e72  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x140041e79  lea     rax, [rbp+4Fh+var_68]
0x140041e7d  mov     [rbp+4Fh+var_78], r14
0x140041e81  cmovz   rax, rcx
0x140041e85  mov     [rbp+4Fh+var_80], rdi
0x140041e89  mov     [rbp+4Fh+var_70], rax
0x140041e8d  lea     rax, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140041e94  mov     [rbp+4Fh+var_88], rax
0x140041e98  lea     rax, aConvertingToSo; "Converting to Soft"
0x140041e9f  mov     [rbp+4Fh+var_98], rax
0x140041ea3  lea     rax, [rbp+4Fh+var_70]
0x140041ea7  mov     [rsp+100h+var_B0], rax
0x140041eac  lea     rax, [rbp+4Fh+var_78]
0x140041eb0  mov     [rsp+100h+var_B8], rax
0x140041eb5  lea     rax, [rbp+4Fh+var_80]
0x140041eb9  mov     [rsp+100h+var_C0], rax
0x140041ebe  lea     rax, [rbp+4Fh+arg_0]
0x140041ec2  mov     [rsp+100h+var_C8], rax
0x140041ec7  lea     rax, [rbp+4Fh+var_88]
0x140041ecb  mov     [rsp+100h+var_D0], rax
0x140041ed0  lea     rax, [rbp+4Fh+var_90]
0x140041ed4  mov     [rsp+100h+var_D8], rax; char *
0x140041ed9  lea     rax, [rbp+4Fh+var_98]
0x140041edd  mov     [rsp+100h+var_E0], rax
0x140041ee2  mov     qword ptr [rbp+4Fh+var_90], r12
0x140041ee6  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@5AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x140041eeb  mov     rcx, [rdi+90h]
0x140041ef2  add     rcx, 38h ; '8'; Event
0x140041ef6  call    cs:__imp_KeClearEvent
0x140041efd  nop     dword ptr [rax+rax+00h]
0x140041f02  mov     al, [rdi+0ACh]
0x140041f08  nop
0x140041f09  nop
0x140041f0a  mov     [rdi+0ADh], al
0x140041f10  nop
0x140041f11  xor     eax, eax
0x140041f13  mov     [rdi+0ACh], r13b
0x140041f1a  nop
0x140041f1b  lock cmpxchg [rdi+0A8h], r13w
0x140041f25  nop
0x140041f26  test    ax, ax
0x140041f29  jnz     loc_140041FE4
0x140041f2f  nop
0x140041f30  mov     [rdi+0AAh], bx
0x140041f37  mfence
0x140041f3a  mov     [rdi+0B4h], r14d
0x140041f41  mov     rax, gs:188h
0x140041f4a  mov     [rdi+0B8h], rax
0x140041f51  cmp     [rdi+0C0h], rbx
0x140041f58  jnz     short loc_140041F63
0x140041f5a  cmp     [rdi+0D0h], rbx
0x140041f61  jz      short loc_140041F6F
0x140041f63  lea     rcx, aMTombstoneOwni_0; "!m_Tombstone.OwningUnion && !m_Tombston"...
0x140041f6a  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140041f6f  mov     rax, [rsi]
0x140041f72  mov     rdx, [rsi+8]
0x140041f76  mov     [rsi], rbx
0x140041f79  mov     [rsi+8], rbx
0x140041f7d  mov     rcx, [rdi+0C8h]; this
0x140041f84  mov     [rdi+0C0h], rax
0x140041f8b  mov     [rdi+0C8h], rdx
0x140041f92  test    rcx, rcx
0x140041f95  jz      short loc_140041F9C
0x140041f97  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140041f9c  mov     rax, [r15]
0x140041f9f  mov     [r15], rbx
0x140041fa2  mov     r14, [rdi+0D0h]
0x140041fa9  mov     [rdi+0D0h], rax
0x140041fb0  test    r14, r14
0x140041fb3  jz      loc_14004222F
0x140041fb9  cmp     [r14+10h], bl
0x140041fbd  jnz     short loc_140041FC6
0x140041fbf  xorps   xmm0, xmm0
0x140041fc2  movups  xmmword ptr [r14], xmm0
0x140041fc6  mov     rcx, r14; UnicodeString
0x140041fc9  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140041fce  xor     edx, edx; Tag
0x140041fd0  mov     rcx, r14; P
0x140041fd3  call    cs:__imp_ExFreePoolWithTag
0x140041fda  nop     dword ptr [rax+rax+00h]
0x140041fdf  jmp     loc_14004222F
0x140041fe4  mov     ecx, 2
0x140041fe9  cmp     ax, cx
0x140041fec  jnz     short loc_14004204A
0x140041fee  nop
0x140041fef  mov     eax, ecx
0x140041ff1  lock cmpxchg [rdi+0A8h], r13w
0x140041ffb  nop
0x140041ffc  cmp     ax, cx
0x140041fff  jnz     short loc_14004204A
0x140042001  nop
0x140042002  mov     [rdi+0AAh], cx
0x140042009  mfence
0x14004200c  mov     [rdi+0B4h], r14d
0x140042013  mov     rax, gs:188h
0x14004201c  mov     [rdi+0B8h], rax
0x140042023  cmp     [rdi+0C0h], rbx
0x14004202a  jz      short loc_140042039
0x14004202c  cmp     [rdi+0D0h], rbx
0x140042033  jnz     loc_14004222F
0x140042039  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x140042040  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140042045  jmp     loc_14004222F
0x14004204a  mov     ecx, 3
0x14004204f  cmp     ax, cx
0x140042052  jnz     short loc_1400420B0
0x140042054  nop
0x140042055  mov     eax, ecx
0x140042057  lock cmpxchg [rdi+0A8h], r13w
0x140042061  nop
0x140042062  cmp     ax, cx
0x140042065  jnz     short loc_1400420B0
0x140042067  nop
0x140042068  mov     [rdi+0AAh], cx
0x14004206f  mfence
0x140042072  mov     [rdi+0B4h], r14d
0x140042079  mov     rax, gs:188h
0x140042082  mov     [rdi+0B8h], rax
0x140042089  cmp     [rdi+0C0h], rbx
0x140042090  jz      short loc_14004209F
0x140042092  cmp     [rdi+0D0h], rbx
0x140042099  jnz     loc_14004222F
0x14004209f  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x1400420a6  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x1400420ab  jmp     loc_14004222F
0x1400420b0  mov     ecx, 4
0x1400420b5  cmp     ax, cx
0x1400420b8  jnz     loc_140042193
0x1400420be  nop
0x1400420bf  mov     eax, ecx
0x1400420c1  lock cmpxchg [rdi+0A8h], r13w
0x1400420cb  nop
0x1400420cc  cmp     ax, cx
0x1400420cf  jnz     loc_140042193
0x1400420d5  nop
0x1400420d6  mov     [rdi+0AAh], cx
0x1400420dd  mfence
0x1400420e0  mov     [rdi+0B4h], r14d
0x1400420e7  mov     rax, gs:188h
0x1400420f0  mov     [rdi+0B8h], rax
0x1400420f7  mov     rax, [rsi]
0x1400420fa  mov     rdx, [rsi+8]
0x1400420fe  mov     [rsi], rbx
0x140042101  mov     [rsi+8], rbx
0x140042105  mov     rcx, [rdi+0C8h]; this
0x14004210c  mov     [rdi+0C0h], rax
0x140042113  mov     [rdi+0C8h], rdx
0x14004211a  test    rcx, rcx
0x14004211d  jz      short loc_140042124
0x14004211f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140042124  cmp     [rdi+0D0h], rbx
0x14004212b  jnz     short loc_14004216C
0x14004212d  mov     rax, [r15]
0x140042130  mov     [r15], rbx
0x140042133  mov     r14, [rdi+0D0h]
0x14004213a  mov     [rdi+0D0h], rax
0x140042141  test    r14, r14
0x140042144  jz      short loc_14004216C
0x140042146  cmp     [r14+10h], bl
0x14004214a  jnz     short loc_140042153
0x14004214c  xorps   xmm0, xmm0
0x14004214f  movups  xmmword ptr [r14], xmm0
0x140042153  mov     rcx, r14; UnicodeString
0x140042156  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x14004215b  xor     edx, edx; Tag
0x14004215d  mov     rcx, r14; P
0x140042160  call    cs:__imp_ExFreePoolWithTag
0x140042167  nop     dword ptr [rax+rax+00h]
0x14004216c  cmp     [rdi+0C0h], rbx
0x140042173  jz      short loc_140042182
0x140042175  cmp     [rdi+0D0h], rbx
0x14004217c  jnz     loc_14004222F
0x140042182  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x140042189  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x14004218e  jmp     loc_14004222F
0x140042193  cmp     ax, r13w
0x140042197  jz      short loc_140042211
0x140042199  mov     rcx, [rdi+90h]
0x1400421a0  xor     r8d, r8d; Wait
0x1400421a3  add     rcx, 38h ; '8'; Event
0x1400421a7  xor     edx, edx; Increment
0x1400421a9  call    cs:__imp_KeSetEvent
0x1400421b0  nop     dword ptr [rax+rax+00h]
0x1400421b5  mov     rdx, qword ptr [rbp+4Fh+arg_20]; int
0x1400421b9  lea     rax, aOriginTombston_0; "ORIGIN: Tombstone wasn't in expected st"...
0x1400421c0  mov     edi, 0C0ED0004h
0x1400421c5  mov     [rsp+100h+var_E0], rax; char *
0x1400421ca  mov     ecx, edi; this
0x1400421cc  mov     r9, r12; unsigned __int64
0x1400421cf  mov     r8, 32700120320h; struct UnionFs::StackEventTracer *
0x1400421d9  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
  ... truncated ...
```
