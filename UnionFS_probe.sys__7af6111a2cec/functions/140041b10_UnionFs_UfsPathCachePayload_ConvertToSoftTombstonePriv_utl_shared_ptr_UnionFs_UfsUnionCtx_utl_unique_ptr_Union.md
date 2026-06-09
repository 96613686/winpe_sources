# UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv(utl::shared_ptr<UnionFs::UfsUnionCtx>,utl::unique_ptr<UnionFs::UfsPathName,utl::default_delete<UnionFs::UfsPathName>> &&,UnionFs::SoftTombstoneReason,UnionFs::StackEventTracer &)

- ea: `0x140041b10`
- end: `0x1400420e1`
- name: `?ConvertToSoftTombstonePriv@UfsPathCachePayload@UnionFs@@AEAAJV?$shared_ptr@VUfsUnionCtx@UnionFs@@@utl@@$$QEAV?$unique_ptr@VUfsPathName@UnionFs@@U?$default_delete@VUfsPathName@UnionFs@@@utl@@@4@W4SoftTombstoneReason@2@AEAVStackEventTracer@2@@Z`
- size: `1489`
- prototype: ``
- caller_count: `2`
- callee_count: `9`
- tags: `installer_update, broker_com_uri`

## callers

- `0x140041840`
- `0x1400419a8`

## callees

- `0x1400029d0`
- `0x140002f28`
- `0x14000f7fc`
- `0x14003fdac`
- `0x140041b10`
- `0x140056ac4`
- `0x1400799a4`
- `0x140079c48`
- `0x14007af90`

## import_xrefs

- `ntoskrnl!KeClearEvent` at `0x140041d6e`
- `ntoskrnl!KeClearEvent` at `0x140041d6e`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041e4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041fd8`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041e4b`
- `ntoskrnl!ExFreePoolWithTag` at `0x140041fd8`
- `ntoskrnl!KeSetEvent` at `0x140042021`
- `ntoskrnl!KeSetEvent` at `0x140042021`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004206b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400420b0`
- `ntoskrnl!ExReleaseFastMutex` at `0x14004206b`
- `ntoskrnl!ExReleaseFastMutex` at `0x1400420b0`

## string_xrefs

- `0x140041bb7`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140041d05`: `onecore\base\fs\unionfs\sys\pathcachepayload.cpp`
- `0x140041b9d`: `UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv`
- `0x140041c24`: `UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv`
- `0x140041ddb`: `!m_Tombstone.OwningUnion && !m_Tombstone.ScratchPath`
- `0x140041eb1`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x140041f17`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x140041ffa`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`
- `0x14004209b`: `m_Tombstone.OwningUnion && m_Tombstone.ScratchPath`

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
  char *v13; // rdx
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
  FsFltWil::AcquireFastMutex(&FastMutex, *(_QWORD *)(a1 + 136));
  if ( _InterlockedIncrement((volatile signed __int32 *)(a1 + 168)) > 1 )
  {
    if ( (unsigned int)dword_14009E178 > 5
      && (qword_14009E188 & 0x40) != 0
      && (qword_14009E190 & 0x40) == qword_14009E190 )
    {
      v11 = *(_DWORD *)(a1 + 168);
      *(_QWORD *)v32 = v6;
      v35 = "UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv";
      v42 = v11;
      v34 = "onecore\\base\\fs\\unionfs\\sys\\pathcachepayload.cpp";
      v36 = "SoftCount > 1";
      v33 = (const char *)a1;
      LODWORD(v31) = 637;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(
        qword_14009E190,
        (unsigned int)byte_140097221,
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
  v12 = *(__int128 **)(a1 + 200);
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
    v42 = 663;
    v13 = byte_1400970C3;
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
    v42 = 672;
    v13 = byte_1400974BD;
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
  KeClearEvent((PRKEVENT)(*(_QWORD *)(a1 + 136) + 56LL));
  *(_BYTE *)(a1 + 165) = *(_BYTE *)(a1 + 164);
  *(_BYTE *)(a1 + 164) = 1;
  v15 = _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 160), 1, 0);
  if ( !v15 )
  {
    *(_WORD *)(a1 + 162) = 0;
    _mm_mfence();
    *(_DWORD *)(a1 + 172) = (_DWORD)v6;
    *(_QWORD *)(a1 + 176) = KeGetCurrentThread();
    if ( *(_QWORD *)(a1 + 184) || *(_QWORD *)(a1 + 200) )
      MicrosoftTelemetryAssertTriggeredMsgKM("!m_Tombstone.OwningUnion && !m_Tombstone.ScratchPath");
    v16 = *a2;
    v17 = (struct _UNICODE_STRING *)a2[1];
    *a2 = 0;
    a2[1] = 0;
    v18 = *(utl::_RefCountBase **)(a1 + 192);
    *(_QWORD *)(a1 + 184) = v16;
    *(_QWORD *)(a1 + 192) = v17;
    if ( v18 )
      utl::_RefCountBase::_DecStrong(v18);
    v19 = *a3;
    *a3 = 0;
    v20 = *(_QWORD *)(a1 + 200);
    *(_QWORD *)(a1 + 200) = v19;
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
    v15 = _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 160), 1, 2);
    if ( v15 == 2 )
    {
      *(_WORD *)(a1 + 162) = 2;
      _mm_mfence();
      *(_DWORD *)(a1 + 172) = (_DWORD)v6;
      *(_QWORD *)(a1 + 176) = KeGetCurrentThread();
      if ( *(_QWORD *)(a1 + 184) && *(_QWORD *)(a1 + 200) )
        goto LABEL_60;
      goto LABEL_59;
    }
  }
  if ( v15 == 3 )
  {
    v15 = _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 160), 1, 3);
    if ( v15 == 3 )
    {
      *(_WORD *)(a1 + 162) = 3;
      _mm_mfence();
      *(_DWORD *)(a1 + 172) = (_DWORD)v6;
      *(_QWORD *)(a1 + 176) = KeGetCurrentThread();
      if ( *(_QWORD *)(a1 + 184) && *(_QWORD *)(a1 + 200) )
        goto LABEL_60;
      goto LABEL_59;
    }
  }
  if ( v15 == 4 )
  {
    v15 = _InterlockedCompareExchange16((volatile signed __int16 *)(a1 + 160), 1, 4);
    if ( v15 == 4 )
    {
      *(_WORD *)(a1 + 162) = 4;
      _mm_mfence();
      *(_DWORD *)(a1 + 172) = (_DWORD)v6;
      *(_QWORD *)(a1 + 176) = KeGetCurrentThread();
      v21 = *a2;
      v22 = (struct _UNICODE_STRING *)a2[1];
      *a2 = 0;
      a2[1] = 0;
      v23 = *(utl::_RefCountBase **)(a1 + 192);
      *(_QWORD *)(a1 + 184) = v21;
      *(_QWORD *)(a1 + 192) = v22;
      if ( v23 )
        utl::_RefCountBase::_DecStrong(v23);
      if ( !*(_QWORD *)(a1 + 200) )
      {
        v24 = *a3;
        *a3 = 0;
        v25 = *(_QWORD *)(a1 + 200);
        *(_QWORD *)(a1 + 200) = v24;
        if ( v25 )
        {
          if ( !*(_BYTE *)(v25 + 16) )
            *(_OWORD *)v25 = 0;
          FsFltWil::Details::FreeUnicodeString((PUNICODE_STRING)v25, v22);
          ExFreePoolWithTag((PVOID)v25, 0);
        }
      }
      if ( *(_QWORD *)(a1 + 184) && *(_QWORD *)(a1 + 200) )
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
    if ( *(_QWORD *)(a1 + 184) && *(_QWORD *)(a1 + 200) )
      goto LABEL_60;
    goto LABEL_59;
  }
  KeSetEvent((PRKEVENT)(*(_QWORD *)(a1 + 136) + 56LL), 0, 0);
  UnionFs::ProcessTraceStatusOrigin(
    (UnionFs *)0xC0ED0004LL,
    a5,
    (struct UnionFs::StackEventTracer *)0x32700120307LL,
    (unsigned __int64)"UnionFs::UfsPathCachePayload::ConvertToSoftTombstonePriv",
    "ORIGIN: Tombstone wasn't in expected state",
    v29);
  v41 = 0;
  lambda_49872cc42997c25cd88c05ba76f82c84_::operator()(&v38);
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
0x140041b10  push    rbp
0x140041b12  push    rbx
0x140041b13  push    rsi
0x140041b14  push    rdi
0x140041b15  push    r12
0x140041b17  push    r13
0x140041b19  push    r14
0x140041b1b  push    r15
0x140041b1d  lea     rbp, [rsp-17h]
0x140041b22  sub     rsp, 0C8h
0x140041b29  mov     rsi, rdx
0x140041b2c  movsxd  r14, r9d
0x140041b2f  mov     rdx, [rcx+88h]
0x140041b36  mov     rdi, rcx
0x140041b39  lea     rcx, [rbp+4Fh+FastMutex]
0x140041b3d  mov     r15, r8
0x140041b40  call    ?AcquireFastMutex@FsFltWil@@YA?AV?$unique_ptr@U_FAST_MUTEX@@U?$function_deleter@P6AXPEAU_FAST_MUTEX@@@Z$1?ExReleaseFastMutex@@YAX0@Z@wil@@@wistd@@AEAU_FAST_MUTEX@@@Z; FsFltWil::AcquireFastMutex(_FAST_MUTEX &)
0x140041b45  mov     r13d, 1
0x140041b4b  nop
0x140041b4c  mov     eax, r13d
0x140041b4f  lock xadd [rdi+0A8h], eax
0x140041b57  inc     eax
0x140041b59  nop
0x140041b5a  cmp     eax, r13d
0x140041b5d  jle     loc_140041C21
0x140041b63  mov     eax, cs:dword_14009E178
0x140041b69  cmp     eax, 5
0x140041b6c  jbe     loc_1400420A7
0x140041b72  mov     rcx, cs:qword_14009E190
0x140041b79  mov     rax, cs:qword_14009E188
0x140041b80  test    al, 40h
0x140041b82  jz      loc_1400420A7
0x140041b88  mov     rax, rcx
0x140041b8b  and     eax, 40h
0x140041b8e  cmp     rax, rcx
0x140041b91  jnz     loc_1400420A7
0x140041b97  mov     eax, [rdi+0A8h]
0x140041b9d  lea     r12, aUnionfsUfspath_17; "UnionFs::UfsPathCachePayload::ConvertTo"...
0x140041ba4  mov     qword ptr [rbp+4Fh+var_90], r14
0x140041ba8  lea     rdx, byte_140097221
0x140041baf  nop
0x140041bb0  mov     [rbp+4Fh+var_78], r12
0x140041bb4  mov     [rbp+4Fh+arg_0], eax
0x140041bb7  lea     rax, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140041bbe  mov     [rbp+4Fh+var_80], rax
0x140041bc2  lea     rax, aSoftcount1; "SoftCount > 1"
0x140041bc9  mov     [rbp+4Fh+var_70], rax
0x140041bcd  lea     rax, [rbp+4Fh+var_90]
0x140041bd1  mov     [rsp+100h+var_B0], rax
0x140041bd6  lea     rax, [rbp+4Fh+arg_0]
0x140041bda  mov     [rsp+100h+var_B8], rax
0x140041bdf  lea     rax, [rbp+4Fh+var_88]
0x140041be3  mov     [rsp+100h+var_C0], rax
0x140041be8  lea     rax, [rbp+4Fh+var_98]
0x140041bec  mov     [rsp+100h+var_C8], rax
0x140041bf1  lea     rax, [rbp+4Fh+var_80]
0x140041bf5  mov     [rsp+100h+var_D0], rax
0x140041bfa  lea     rax, [rbp+4Fh+var_78]
0x140041bfe  mov     [rsp+100h+var_D8], rax
0x140041c03  lea     rax, [rbp+4Fh+var_70]
0x140041c07  mov     [rsp+100h+var_E0], rax
0x140041c0c  mov     [rbp+4Fh+var_88], rdi
0x140041c10  mov     dword ptr [rbp+4Fh+var_98], 27Dh
0x140041c17  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U2@U3@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@45@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &)
0x140041c1c  jmp     loc_1400420A7
0x140041c21  mov     eax, [rbp+4Fh+var_5C]
0x140041c24  lea     r12, aUnionfsUfspath_17; "UnionFs::UfsPathCachePayload::ConvertTo"...
0x140041c2b  mov     [rbp+4Fh+var_4C], eax
0x140041c2e  xor     ebx, ebx
0x140041c30  mov     rax, [rdi+0C8h]
0x140041c37  mov     [rbp+4Fh+var_58], rdi
0x140041c3b  mov     [rbp+4Fh+var_50], r14d
0x140041c3f  test    rax, rax
0x140041c42  jz      short loc_140041C90
0x140041c44  movups  xmm0, xmmword ptr [rax]
0x140041c47  mov     eax, cs:dword_14009E178
0x140041c4d  movdqu  xmmword ptr [rbp-19h], xmm0
0x140041c52  cmp     eax, 5
0x140041c55  jbe     loc_140041D63
0x140041c5b  mov     rcx, cs:qword_14009E190
0x140041c62  mov     rax, cs:qword_14009E188
0x140041c69  test    al, 40h
0x140041c6b  jz      loc_140041D63
0x140041c71  mov     rax, rcx
0x140041c74  and     eax, 40h
0x140041c77  cmp     rax, rcx
0x140041c7a  jnz     loc_140041D63
0x140041c80  mov     [rbp+4Fh+arg_0], 297h
0x140041c87  lea     rdx, byte_1400970C3
0x140041c8e  jmp     short loc_140041CE6
0x140041c90  mov     rax, [r15]
0x140041c93  test    rax, rax
0x140041c96  jz      loc_140041D63
0x140041c9c  movups  xmm0, xmmword ptr [rax]
0x140041c9f  mov     eax, cs:dword_14009E178
0x140041ca5  movdqu  xmmword ptr [rbp-19h], xmm0
0x140041caa  cmp     eax, 5
0x140041cad  jbe     loc_140041D63
0x140041cb3  mov     rcx, cs:qword_14009E190
0x140041cba  mov     rax, cs:qword_14009E188
0x140041cc1  test    al, 40h
0x140041cc3  jz      loc_140041D63
0x140041cc9  mov     rax, rcx
0x140041ccc  and     eax, 40h
0x140041ccf  cmp     rax, rcx
0x140041cd2  jnz     loc_140041D63
0x140041cd8  mov     [rbp+4Fh+arg_0], 2A0h
0x140041cdf  lea     rdx, byte_1400974BD
0x140041ce6  cmp     [rbp-11h], rbx
0x140041cea  lea     rcx, ?FsTlEmptyUnicodeString@@3U_UNICODE_STRING@@B; _UNICODE_STRING const FsTlEmptyUnicodeString
0x140041cf1  lea     rax, [rbp+4Fh+var_68]
0x140041cf5  mov     [rbp+4Fh+var_78], r14
0x140041cf9  cmovz   rax, rcx
0x140041cfd  mov     [rbp+4Fh+var_80], rdi
0x140041d01  mov     [rbp+4Fh+var_70], rax
0x140041d05  lea     rax, aOnecoreBaseFsU_5; "onecore\\base\\fs\\unionfs\\sys\\pathca"...
0x140041d0c  mov     [rbp+4Fh+var_88], rax
0x140041d10  lea     rax, aConvertingToSo; "Converting to Soft"
0x140041d17  mov     [rbp+4Fh+var_98], rax
0x140041d1b  lea     rax, [rbp+4Fh+var_70]
0x140041d1f  mov     [rsp+100h+var_B0], rax
0x140041d24  lea     rax, [rbp+4Fh+var_78]
0x140041d28  mov     [rsp+100h+var_B8], rax
0x140041d2d  lea     rax, [rbp+4Fh+var_80]
0x140041d31  mov     [rsp+100h+var_C0], rax
0x140041d36  lea     rax, [rbp+4Fh+arg_0]
0x140041d3a  mov     [rsp+100h+var_C8], rax
0x140041d3f  lea     rax, [rbp+4Fh+var_88]
0x140041d43  mov     [rsp+100h+var_D0], rax
0x140041d48  lea     rax, [rbp+4Fh+var_90]
0x140041d4c  mov     [rsp+100h+var_D8], rax; char *
0x140041d51  lea     rax, [rbp+4Fh+var_98]
0x140041d55  mov     [rsp+100h+var_E0], rax
0x140041d5a  mov     qword ptr [rbp+4Fh+var_90], r12
0x140041d5e  call    ??$Write@U?$_tlgWrapSz@D@@U1@U1@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapperByVal@$07@@U3@U?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@33AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapperByVal@$07@@5AEBU?$_tlgWrapBuffer@U_UNICODE_STRING@@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<8>,_tlgWrapBuffer<_UNICODE_STRING>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<8> const &,_tlgWrapBuffer<_UNICODE_STRING> const &)
0x140041d63  mov     rcx, [rdi+88h]
0x140041d6a  add     rcx, 38h ; '8'; Event
0x140041d6e  call    cs:__imp_KeClearEvent
0x140041d75  nop     dword ptr [rax+rax+00h]
0x140041d7a  mov     al, [rdi+0A4h]
0x140041d80  nop
0x140041d81  nop
0x140041d82  mov     [rdi+0A5h], al
0x140041d88  nop
0x140041d89  xor     eax, eax
0x140041d8b  mov     [rdi+0A4h], r13b
0x140041d92  nop
0x140041d93  lock cmpxchg [rdi+0A0h], r13w
0x140041d9d  nop
0x140041d9e  test    ax, ax
0x140041da1  jnz     loc_140041E5C
0x140041da7  nop
0x140041da8  mov     [rdi+0A2h], bx
0x140041daf  mfence
0x140041db2  mov     [rdi+0ACh], r14d
0x140041db9  mov     rax, gs:188h
0x140041dc2  mov     [rdi+0B0h], rax
0x140041dc9  cmp     [rdi+0B8h], rbx
0x140041dd0  jnz     short loc_140041DDB
0x140041dd2  cmp     [rdi+0C8h], rbx
0x140041dd9  jz      short loc_140041DE7
0x140041ddb  lea     rcx, aMTombstoneOwni_0; "!m_Tombstone.OwningUnion && !m_Tombston"...
0x140041de2  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140041de7  mov     rax, [rsi]
0x140041dea  mov     rdx, [rsi+8]
0x140041dee  mov     [rsi], rbx
0x140041df1  mov     [rsi+8], rbx
0x140041df5  mov     rcx, [rdi+0C0h]; this
0x140041dfc  mov     [rdi+0B8h], rax
0x140041e03  mov     [rdi+0C0h], rdx
0x140041e0a  test    rcx, rcx
0x140041e0d  jz      short loc_140041E14
0x140041e0f  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140041e14  mov     rax, [r15]
0x140041e17  mov     [r15], rbx
0x140041e1a  mov     r14, [rdi+0C8h]
0x140041e21  mov     [rdi+0C8h], rax
0x140041e28  test    r14, r14
0x140041e2b  jz      loc_1400420A7
0x140041e31  cmp     [r14+10h], bl
0x140041e35  jnz     short loc_140041E3E
0x140041e37  xorps   xmm0, xmm0
0x140041e3a  movups  xmmword ptr [r14], xmm0
0x140041e3e  mov     rcx, r14; UnicodeString
0x140041e41  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140041e46  xor     edx, edx; Tag
0x140041e48  mov     rcx, r14; P
0x140041e4b  call    cs:__imp_ExFreePoolWithTag
0x140041e52  nop     dword ptr [rax+rax+00h]
0x140041e57  jmp     loc_1400420A7
0x140041e5c  mov     ecx, 2
0x140041e61  cmp     ax, cx
0x140041e64  jnz     short loc_140041EC2
0x140041e66  nop
0x140041e67  mov     eax, ecx
0x140041e69  lock cmpxchg [rdi+0A0h], r13w
0x140041e73  nop
0x140041e74  cmp     ax, cx
0x140041e77  jnz     short loc_140041EC2
0x140041e79  nop
0x140041e7a  mov     [rdi+0A2h], cx
0x140041e81  mfence
0x140041e84  mov     [rdi+0ACh], r14d
0x140041e8b  mov     rax, gs:188h
0x140041e94  mov     [rdi+0B0h], rax
0x140041e9b  cmp     [rdi+0B8h], rbx
0x140041ea2  jz      short loc_140041EB1
0x140041ea4  cmp     [rdi+0C8h], rbx
0x140041eab  jnz     loc_1400420A7
0x140041eb1  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x140041eb8  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140041ebd  jmp     loc_1400420A7
0x140041ec2  mov     ecx, 3
0x140041ec7  cmp     ax, cx
0x140041eca  jnz     short loc_140041F28
0x140041ecc  nop
0x140041ecd  mov     eax, ecx
0x140041ecf  lock cmpxchg [rdi+0A0h], r13w
0x140041ed9  nop
0x140041eda  cmp     ax, cx
0x140041edd  jnz     short loc_140041F28
0x140041edf  nop
0x140041ee0  mov     [rdi+0A2h], cx
0x140041ee7  mfence
0x140041eea  mov     [rdi+0ACh], r14d
0x140041ef1  mov     rax, gs:188h
0x140041efa  mov     [rdi+0B0h], rax
0x140041f01  cmp     [rdi+0B8h], rbx
0x140041f08  jz      short loc_140041F17
0x140041f0a  cmp     [rdi+0C8h], rbx
0x140041f11  jnz     loc_1400420A7
0x140041f17  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x140041f1e  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140041f23  jmp     loc_1400420A7
0x140041f28  mov     ecx, 4
0x140041f2d  cmp     ax, cx
0x140041f30  jnz     loc_14004200B
0x140041f36  nop
0x140041f37  mov     eax, ecx
0x140041f39  lock cmpxchg [rdi+0A0h], r13w
0x140041f43  nop
0x140041f44  cmp     ax, cx
0x140041f47  jnz     loc_14004200B
0x140041f4d  nop
0x140041f4e  mov     [rdi+0A2h], cx
0x140041f55  mfence
0x140041f58  mov     [rdi+0ACh], r14d
0x140041f5f  mov     rax, gs:188h
0x140041f68  mov     [rdi+0B0h], rax
0x140041f6f  mov     rax, [rsi]
0x140041f72  mov     rdx, [rsi+8]
0x140041f76  mov     [rsi], rbx
0x140041f79  mov     [rsi+8], rbx
0x140041f7d  mov     rcx, [rdi+0C0h]; this
0x140041f84  mov     [rdi+0B8h], rax
0x140041f8b  mov     [rdi+0C0h], rdx
0x140041f92  test    rcx, rcx
0x140041f95  jz      short loc_140041F9C
0x140041f97  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x140041f9c  cmp     [rdi+0C8h], rbx
0x140041fa3  jnz     short loc_140041FE4
0x140041fa5  mov     rax, [r15]
0x140041fa8  mov     [r15], rbx
0x140041fab  mov     r14, [rdi+0C8h]
0x140041fb2  mov     [rdi+0C8h], rax
0x140041fb9  test    r14, r14
0x140041fbc  jz      short loc_140041FE4
0x140041fbe  cmp     [r14+10h], bl
0x140041fc2  jnz     short loc_140041FCB
0x140041fc4  xorps   xmm0, xmm0
0x140041fc7  movups  xmmword ptr [r14], xmm0
0x140041fcb  mov     rcx, r14; UnicodeString
0x140041fce  call    ?FreeUnicodeString@Details@FsFltWil@@YAXPEAU_UNICODE_STRING@@@Z; FsFltWil::Details::FreeUnicodeString(_UNICODE_STRING *)
0x140041fd3  xor     edx, edx; Tag
0x140041fd5  mov     rcx, r14; P
0x140041fd8  call    cs:__imp_ExFreePoolWithTag
0x140041fdf  nop     dword ptr [rax+rax+00h]
0x140041fe4  cmp     [rdi+0B8h], rbx
0x140041feb  jz      short loc_140041FFA
0x140041fed  cmp     [rdi+0C8h], rbx
0x140041ff4  jnz     loc_1400420A7
0x140041ffa  lea     rcx, aMTombstoneOwni; "m_Tombstone.OwningUnion && m_Tombstone."...
0x140042001  call    MicrosoftTelemetryAssertTriggeredMsgKM
0x140042006  jmp     loc_1400420A7
0x14004200b  cmp     ax, r13w
0x14004200f  jz      short loc_140042089
0x140042011  mov     rcx, [rdi+88h]
0x140042018  xor     r8d, r8d; Wait
0x14004201b  add     rcx, 38h ; '8'; Event
0x14004201f  xor     edx, edx; Increment
0x140042021  call    cs:__imp_KeSetEvent
0x140042028  nop     dword ptr [rax+rax+00h]
0x14004202d  mov     rdx, qword ptr [rbp+4Fh+arg_20]; int
0x140042031  lea     rax, aOriginTombston_0; "ORIGIN: Tombstone wasn't in expected st"...
0x140042038  mov     edi, 0C0ED0004h
0x14004203d  mov     [rsp+100h+var_E0], rax; char *
0x140042042  mov     ecx, edi; this
0x140042044  mov     r9, r12; unsigned __int64
0x140042047  mov     r8, 32700120307h; struct UnionFs::StackEventTracer *
0x140042051  call    ?ProcessTraceStatusOrigin@UnionFs@@YAXJAEAVStackEventTracer@1@_KPEBD2@Z; UnionFs::ProcessTraceStatusOrigin(long,UnionFs::StackEventTracer &,unsigned __int64,char const *,char const *)
  ... truncated ...
```
