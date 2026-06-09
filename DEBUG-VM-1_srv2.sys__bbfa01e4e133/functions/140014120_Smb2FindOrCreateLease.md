# Smb2FindOrCreateLease

- ea: `0x140014120`
- end: `0x1400149ce`
- name: `Smb2FindOrCreateLease`
- size: `2222`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x140013bf0`
- `0x14007d3e4`

## callees

- `0x14000e340`
- `0x140014120`
- `0x14001d724`
- `0x14002019c`
- `0x1400222ec`
- `0x140022a10`
- `0x14002f934`
- `0x140038490`
- `0x1400384d0`
- `0x140038560`
- `0x140084bd0`

## import_xrefs

- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001431f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014554`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001470c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014760`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001431f`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014554`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x14001470c`
- `ntoskrnl!KeAcquireSpinLockRaiseToDpc` at `0x140014760`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014576`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014591`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400145fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014750`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400147c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014837`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001486a`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014576`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014591`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400145fc`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014750`
- `ntoskrnl!KeReleaseSpinLock` at `0x1400147c9`
- `ntoskrnl!KeReleaseSpinLock` at `0x140014837`
- `ntoskrnl!KeReleaseSpinLock` at `0x14001486a`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c692`
- `ntoskrnl!RtlCaptureStackBackTrace` at `0x14003c692`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140014268`
- `ntoskrnl!ExAcquirePushLockSharedEx` at `0x140014268`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400142cf`
- `ntoskrnl!ExReleasePushLockSharedEx` at `0x1400142cf`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001481a`
- `ntoskrnl!ExAcquirePushLockExclusiveEx` at `0x14001481a`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014802`
- `ntoskrnl!ExReleasePushLockExclusiveEx` at `0x140014802`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400146b5`
- `ntoskrnl!RtlUpcaseUnicodeString` at `0x1400146b5`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400146d2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400146f4`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400146d2`
- `ntoskrnl!RtlEqualUnicodeString` at `0x1400146f4`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400147ad`
- `ntoskrnl!ExAcquireSpinLockShared` at `0x1400147ad`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14001479c`
- `ntoskrnl!ExReleaseSpinLockShared` at `0x14001479c`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140014450`
- `ntoskrnl!ExAcquireSpinLockExclusive` at `0x140014450`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400144fc`
- `ntoskrnl!ExReleaseSpinLockExclusive` at `0x1400144fc`

## pseudocode

```c
__int64 __fastcall Smb2FindOrCreateLease(_QWORD *a1, unsigned int *a2, char a3, char a4, _WORD *a5)
{
  __int64 v5; // r12
  __int64 v8; // rsi
  __int64 v9; // rdi
  unsigned int *v10; // rax
  unsigned int *v11; // rcx
  unsigned int *v12; // r13
  _QWORD *v13; // r8
  __m128i v14; // xmm2
  __m128i v15; // xmm2
  __int64 v16; // r13
  _QWORD *i; // rsi
  __int64 v18; // rbx
  void (__fastcall *v19)(__int64); // rax
  KIRQL v20; // r14
  __int128 v21; // xmm0
  __m128i v22; // xmm2
  __m128i v23; // xmm2
  __int64 v24; // r13
  char *v25; // rsi
  char *v26; // r14
  unsigned int v27; // ecx
  __int64 v28; // rdx
  int v29; // esi
  _QWORD *v30; // rcx
  signed __int64 v31; // rdi
  KIRQL v32; // al
  KIRQL v33; // dl
  KSPIN_LOCK *v34; // rcx
  unsigned int v35; // ebx
  UNICODE_STRING *v37; // rsi
  PWSTR Buffer; // r14
  __int64 v39; // r14
  UNICODE_STRING *v40; // rsi
  __int64 v41; // r13
  KIRQL v42; // al
  KIRQL v43; // al
  __int64 v44; // rdx
  KIRQL v45; // [rsp+60h] [rbp-98h]
  KIRQL v46; // [rsp+60h] [rbp-98h]
  KIRQL v47; // [rsp+60h] [rbp-98h]
  KIRQL v48; // [rsp+61h] [rbp-97h]
  int v51; // [rsp+64h] [rbp-94h]
  unsigned int *v52; // [rsp+68h] [rbp-90h]
  __int64 v53; // [rsp+70h] [rbp-88h]
  unsigned int *v54; // [rsp+78h] [rbp-80h]
  unsigned int *v55; // [rsp+80h] [rbp-78h]
  PVOID BackTrace[2]; // [rsp+90h] [rbp-68h] BYREF
  __int128 v57; // [rsp+A0h] [rbp-58h]
  __int64 v58; // [rsp+B0h] [rbp-48h]

  v5 = a1[70];
  if ( *(_QWORD *)(v5 + 104) )
    return 0;
  v8 = *(_QWORD *)(a1[12] + 496LL);
  v53 = v8;
  v9 = *(_QWORD *)(v8 + 64);
  if ( !v9 )
    return 3221225987LL;
  v10 = a2 + 2;
  v11 = a2 + 3;
  v12 = a2 + 1;
  v13 = (_QWORD *)(v9 + 56);
  v52 = a2 + 1;
  v51 = 0;
  v54 = a2 + 2;
  v55 = a2 + 3;
  while ( !*(_QWORD *)(v9 + 32) || !a2 )
  {
LABEL_17:
    if ( !a3 )
      goto LABEL_77;
    v18 = Smb2LeaseAllocate(v5);
    if ( !v18 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 62, &WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids);
      }
      return 3221225626LL;
    }
    v20 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(a1[12] + 184LL));
    v48 = v20;
    if ( *(_DWORD *)(a1[12] + 12LL) != 220 )
    {
      *(_BYTE *)(v18 + 128) = 1;
      Smb2DereferenceLease((char *)v18);
      KeReleaseSpinLock((PKSPIN_LOCK)(a1[12] + 184LL), v20);
LABEL_77:
      v35 = -1073741772;
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 64, &WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids, a1);
      }
      return v35;
    }
    v52 = v12;
    *(_DWORD *)(v18 + 12) = 220;
    if ( a5 )
    {
      *(_BYTE *)(v18 + 135) = 1;
      *(_WORD *)(v18 + 168) = *a5;
    }
    v21 = *(_OWORD *)a2;
    *(_QWORD *)(v18 + 200) = v9;
    *(_OWORD *)(v18 + 80) = v21;
    _InterlockedIncrement((volatile signed __int32 *)(v9 + 12));
    *(_QWORD *)(v18 + 368) = *(_QWORD *)(v8 + 24);
    if ( ((_InterlockedExchangeAdd64(*(volatile signed __int64 **)(v8 + 24), 1u) + 2) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
      __int2c();
    v22 = _mm_add_epi32(
            _mm_add_epi32(
              _mm_add_epi32(
                _mm_unpacklo_epi16(_mm_unpacklo_epi8(_mm_cvtsi32_si128(*v54), (__m128i)0LL), (__m128i)0LL),
                _mm_unpacklo_epi16(_mm_unpacklo_epi8(_mm_cvtsi32_si128(*v12), (__m128i)0LL), (__m128i)0LL)),
              _mm_unpacklo_epi16(_mm_unpacklo_epi8(_mm_cvtsi32_si128(*v55), (__m128i)0LL), (__m128i)0LL)),
            _mm_unpacklo_epi16(_mm_unpacklo_epi8(_mm_cvtsi32_si128(*a2), (__m128i)0LL), (__m128i)0LL));
    v23 = _mm_add_epi32(v22, _mm_srli_si128(v22, 8));
    v24 = *(_QWORD *)(v9 + 56)
        + 32LL * ((unsigned int)_mm_cvtsi128_si32(_mm_add_epi32(v23, _mm_srli_si128(v23, 4))) % *(_DWORD *)v9);
    if ( (*(_DWORD *)(v24 + 12) & 1) != 0 )
    {
      v46 = ExAcquireSpinLockExclusive((PEX_SPIN_LOCK)v24);
    }
    else
    {
      v46 = 0;
      ExAcquirePushLockExclusiveEx(v24, 0);
    }
    if ( !*(_QWORD *)(v9 + 32) )
      goto LABEL_39;
    v25 = *(char **)(v24 + 16);
    v26 = (char *)(v24 + 16);
    while ( v25 != v26 )
    {
      if ( (*(unsigned __int8 (__fastcall **)(char *, unsigned int *, __int64))(v9 + 32))(
             &v25[-*(_DWORD *)(v9 + 4)],
             a2,
             16) )
      {
        v29 = -1073741270;
        goto LABEL_35;
      }
      v25 = *(char **)v25;
    }
    v27 = *(_DWORD *)(v9 + 16);
    if ( _InterlockedIncrement((volatile signed __int32 *)(v9 + 8)) > v27 )
    {
      _InterlockedDecrement((volatile signed __int32 *)(v9 + 8));
      v29 = -1073741670;
    }
    else
    {
      ++*(_DWORD *)(v24 + 8);
      v28 = *(_QWORD *)v26;
      if ( *(char **)(*(_QWORD *)v26 + 8LL) != v26 )
        __fastfail(3u);
      v29 = 0;
      v30 = (_QWORD *)(v18 + *(unsigned int *)(v9 + 4));
      *v30 = v28;
      v30[1] = v26;
      *(_QWORD *)(v28 + 8) = v30;
      *(_QWORD *)v26 = v30;
    }
LABEL_35:
    if ( (*(_DWORD *)(v24 + 12) & 1) != 0 )
      ExReleaseSpinLockExclusive((PEX_SPIN_LOCK)v24, v46);
    else
      ExReleasePushLockExclusiveEx(v24, 0);
    if ( v29 != -1073741270 )
    {
      v20 = v48;
LABEL_39:
      v31 = _InterlockedIncrement64((volatile signed __int64 *)v18);
      if ( ((v31 + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
        __int2c();
      if ( (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0 )
      {
        v58 = 0;
        *(_OWORD *)BackTrace = 0;
        v57 = 0;
        RtlCaptureStackBackTrace(1u, 5u, BackTrace, 0);
        if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
          && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
          && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
        {
          WPP_SF_qPPqqqqq(
            WPP_GLOBAL_Control->AttachedDevice,
            13,
            &WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids,
            v18,
            v31 - 1,
            v31,
            BackTrace[0],
            BackTrace[1],
            v57,
            *((_QWORD *)&v57 + 1),
            v58);
        }
      }
      if ( a4 )
      {
        v32 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v18 + 96));
        if ( !*(_BYTE *)(v18 + 128) )
          ++*(_DWORD *)(v18 + 172);
        KeReleaseSpinLock((PKSPIN_LOCK)(v18 + 96), v32);
      }
      v33 = v20;
      v34 = (KSPIN_LOCK *)(a1[12] + 184LL);
LABEL_47:
      KeReleaseSpinLock(v34, v33);
      *(_QWORD *)(v5 + 104) = v18;
      return 0;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(a1[12] + 184LL), v48);
    *(_BYTE *)(v18 + 128) = 1;
    Smb2DereferenceLease((char *)v18);
    if ( (unsigned int)++v51 > 3 )
    {
      if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
        && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
        && BYTE1(WPP_GLOBAL_Control->Timer) )
      {
        WPP_SF_(WPP_GLOBAL_Control->AttachedDevice, 63, &WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids);
      }
      return 3221225524LL;
    }
    v8 = v53;
    v12 = v52;
    v10 = v54;
    v11 = v55;
    v13 = (_QWORD *)(v9 + 56);
  }
  v14 = _mm_add_epi32(
          _mm_add_epi32(
            _mm_add_epi32(
              _mm_unpacklo_epi16(_mm_unpacklo_epi8(_mm_cvtsi32_si128(*v12), (__m128i)0LL), (__m128i)0LL),
              _mm_unpacklo_epi16(_mm_unpacklo_epi8(_mm_cvtsi32_si128(*v10), (__m128i)0LL), (__m128i)0LL)),
            _mm_unpacklo_epi16(_mm_unpacklo_epi8(_mm_cvtsi32_si128(*v11), (__m128i)0LL), (__m128i)0LL)),
          _mm_unpacklo_epi16(_mm_unpacklo_epi8(_mm_cvtsi32_si128(*a2), (__m128i)0LL), (__m128i)0LL));
  v15 = _mm_add_epi32(v14, _mm_srli_si128(v14, 8));
  v16 = *v13 + 32LL * ((unsigned int)_mm_cvtsi128_si32(_mm_add_epi32(v15, _mm_srli_si128(v15, 4))) % *(_DWORD *)v9);
  if ( (*(_DWORD *)(v16 + 12) & 1) != 0 )
  {
    v45 = ExAcquireSpinLockShared((PEX_SPIN_LOCK)v16);
  }
  else
  {
    v45 = 0;
    ExAcquirePushLockSharedEx(v16, 0);
  }
  for ( i = *(_QWORD **)(v16 + 16); ; i = (_QWORD *)*i )
  {
    if ( i == (_QWORD *)(v16 + 16) )
    {
      v18 = 0;
      goto LABEL_13;
    }
    v18 = (__int64)i - *(_DWORD *)(v9 + 4);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, unsigned int *, __int64))(v9 + 32))(v18, a2, 16) )
      break;
  }
  v19 = *(void (__fastcall **)(__int64))(v9 + 24);
  if ( v19 )
    v19(v18);
LABEL_13:
  if ( (*(_DWORD *)(v16 + 12) & 1) != 0 )
    ExReleaseSpinLockShared((PEX_SPIN_LOCK)v16, v45);
  else
    ExReleasePushLockSharedEx(v16, 0);
  if ( !v18 )
  {
LABEL_16:
    v12 = v52;
    v8 = v53;
    goto LABEL_17;
  }
  if ( *(_BYTE *)(v18 + 129) || *(_WORD *)(*(_QWORD *)(a1[38] + 24LL) + 12LL) != 5 )
  {
LABEL_62:
    v43 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v18 + 96));
    if ( !*(_BYTE *)(v18 + 128) && *(_DWORD *)(v18 + 12) != 221 )
    {
      if ( a4 )
        ++*(_DWORD *)(v18 + 172);
      v33 = v43;
      v34 = (KSPIN_LOCK *)(v18 + 96);
      goto LABEL_47;
    }
    KeReleaseSpinLock((PKSPIN_LOCK)(v18 + 96), v43);
    if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
      && BYTE1(WPP_GLOBAL_Control->Timer) )
    {
      WPP_SF_q(WPP_GLOBAL_Control->AttachedDevice, 61, &WPP_3d8eb6e120b9357e636b6f5c4c47d988_Traceguids, v18);
    }
    Smb2DereferenceLease((char *)v18);
    goto LABEL_16;
  }
  v37 = (UNICODE_STRING *)a1[70];
  if ( !v37 )
    goto LABEL_87;
  Buffer = v37[3].Buffer;
  if ( !Buffer )
    goto LABEL_87;
  v39 = *((_QWORD *)Buffer + 12);
  if ( !v39 )
    goto LABEL_87;
  v40 = v37 + 12;
  RtlUpcaseUnicodeString(v40, v40, 0);
  v41 = v39 + 88;
  if ( !RtlEqualUnicodeString((PCUNICODE_STRING)(v18 + 376), (PCUNICODE_STRING)(v39 + 88), 1u)
    || !RtlEqualUnicodeString((PCUNICODE_STRING)(v18 + 392), (PCUNICODE_STRING)(v39 + 72), 1u) )
  {
    goto LABEL_97;
  }
  v42 = KeAcquireSpinLockRaiseToDpc((PKSPIN_LOCK)(v18 + 96));
  v47 = v42;
  if ( *(_WORD *)(v18 + 408) != v40->Length )
    goto LABEL_75;
  if ( !memcmp(*(const void **)(v18 + 416), v40->Buffer, *(unsigned __int16 *)(v18 + 408)) )
  {
    KeReleaseSpinLock((PKSPIN_LOCK)(v18 + 96), v47);
    goto LABEL_62;
  }
  v42 = v47;
LABEL_75:
  KeReleaseSpinLock((PKSPIN_LOCK)(v18 + 96), v42);
  v41 = v39 + 88;
LABEL_97:
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 0x40000000) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) )
  {
    WPP_SF_qqZZZZZZ(
      WPP_GLOBAL_Control->AttachedDevice,
      v18 + 408,
      v39 + 72,
      (_DWORD)a1,
      v18,
      (__int64)v40,
      v39 + 72,
      v41,
      v18 + 408,
      v18 + 392,
      v18 + 376);
  }
LABEL_87:
  Smb2DereferenceLease((char *)v18);
  Smb2LkmdTelCollectParsingFailure2(v5, v44, 20, 0);
  return 3221225485LL;
}

```

## disassembly

```asm
0x140014120  mov     r11, rsp
0x140014123  push    rbp
0x140014124  push    r12
0x140014126  push    r15
0x140014128  sub     rsp, 0E0h
0x14001412f  mov     rax, cs:__security_cookie
0x140014136  xor     rax, rsp
0x140014139  mov     [rsp+0F8h+var_40], rax
0x140014141  mov     r12, [rcx+230h]
0x140014148  mov     rbp, rdx
0x14001414b  mov     [rsp+0F8h+var_96], r9b
0x140014150  mov     r15, rcx
0x140014153  mov     [rsp+0F8h+var_95], r8b
0x140014158  cmp     qword ptr [r12+68h], 0
0x14001415e  jnz     loc_1400148C6
0x140014164  mov     rax, [rcx+60h]
0x140014168  mov     [r11-20h], rsi
0x14001416c  mov     [r11-28h], rdi
0x140014170  mov     rsi, [rax+1F0h]
0x140014177  mov     [rsp+0F8h+var_88], rsi
0x14001417c  mov     rdi, [rsi+40h]
0x140014180  test    rdi, rdi
0x140014183  jz      loc_1400148CD
0x140014189  mov     [r11+18h], rbx
0x14001418d  lea     rax, [rdx+8]
0x140014191  mov     [r11-30h], r13
0x140014195  lea     rcx, [rdx+0Ch]
0x140014199  lea     r13, [rdx+4]
0x14001419d  mov     [r11-38h], r14
0x1400141a1  lea     r8, [rdi+38h]
0x1400141a5  mov     [rsp+0F8h+var_90], r13
0x1400141aa  mov     [rsp+0F8h+var_94], 0
0x1400141b2  mov     [rsp+0F8h+var_80], rax
0x1400141b7  mov     [rsp+0F8h+var_78], rcx
0x1400141bf  mov     [rsp+0F8h+var_70], r8
0x1400141c7  lea     r14, WPP_GLOBAL_Control
0x1400141ce  xchg    ax, ax
0x1400141d0  cmp     qword ptr [rdi+20h], 0
0x1400141d5  jz      loc_1400142F5
0x1400141db  test    rbp, rbp
0x1400141de  jz      loc_1400142F5
0x1400141e4  movd    xmm2, dword ptr [r13+0]
0x1400141ea  xorps   xmm0, xmm0
0x1400141ed  movd    xmm1, dword ptr [rax]
0x1400141f1  xor     edx, edx
0x1400141f3  punpcklbw xmm1, xmm0
0x1400141f7  punpcklwd xmm1, xmm0
0x1400141fb  punpcklbw xmm2, xmm0
0x1400141ff  punpcklwd xmm2, xmm0
0x140014203  paddd   xmm2, xmm1
0x140014207  movd    xmm1, dword ptr [rcx]
0x14001420b  punpcklbw xmm1, xmm0
0x14001420f  punpcklwd xmm1, xmm0
0x140014213  paddd   xmm2, xmm1
0x140014217  movd    xmm1, dword ptr [rbp+0]
0x14001421c  punpcklbw xmm1, xmm0
0x140014220  punpcklwd xmm1, xmm0
0x140014224  paddd   xmm2, xmm1
0x140014228  movdqa  xmm0, xmm2
0x14001422c  psrldq  xmm0, 8
0x140014231  paddd   xmm2, xmm0
0x140014235  movdqa  xmm0, xmm2
0x140014239  psrldq  xmm0, 4
0x14001423e  paddd   xmm2, xmm0
0x140014242  movd    eax, xmm2
0x140014246  div     dword ptr [rdi]
0x140014248  mov     r13d, edx
0x14001424b  shl     r13, 5
0x14001424f  add     r13, [r8]
0x140014252  mov     rcx, r13; SpinLock
0x140014255  mov     eax, [r13+0Ch]
0x140014259  test    al, 1
0x14001425b  jnz     loc_1400147AD
0x140014261  xor     edx, edx
0x140014263  mov     [rsp+0F8h+var_98], 0
0x140014268  call    cs:__imp_ExAcquirePushLockSharedEx
0x14001426f  nop     dword ptr [rax+rax+00h]
0x140014274  mov     rsi, [r13+10h]
0x140014278  lea     r14, [r13+10h]
0x14001427c  cmp     rsi, r14
0x14001427f  jz      loc_1400147F9
0x140014285  mov     eax, [rdi+4]
0x140014288  mov     r8d, 10h
0x14001428e  neg     eax
0x140014290  mov     rdx, rbp
0x140014293  movsxd  rbx, eax
0x140014296  mov     rax, [rdi+20h]
0x14001429a  add     rbx, rsi
0x14001429d  mov     rcx, rbx
0x1400142a0  call    _guard_dispatch_icall
0x1400142a5  test    al, al
0x1400142a7  jz      loc_1400144A2
0x1400142ad  mov     rax, [rdi+18h]
0x1400142b1  test    rax, rax
0x1400142b4  jz      short loc_1400142BE
0x1400142b6  mov     rcx, rbx
0x1400142b9  call    _guard_dispatch_icall
0x1400142be  mov     eax, [r13+0Ch]
0x1400142c2  mov     rcx, r13; SpinLock
0x1400142c5  test    al, 1
0x1400142c7  jnz     loc_140014797
0x1400142cd  xor     edx, edx
0x1400142cf  call    cs:__imp_ExReleasePushLockSharedEx
0x1400142d6  nop     dword ptr [rax+rax+00h]
0x1400142db  test    rbx, rbx
0x1400142de  jnz     loc_140014658
0x1400142e4  lea     r14, WPP_GLOBAL_Control
0x1400142eb  mov     r13, [rsp+0F8h+var_90]
0x1400142f0  mov     rsi, [rsp+0F8h+var_88]
0x1400142f5  cmp     [rsp+0F8h+var_95], 0
0x1400142fa  jz      loc_140014876
0x140014300  mov     rcx, r12
0x140014303  call    Smb2LeaseAllocate
0x140014308  mov     rbx, rax
0x14001430b  test    rax, rax
0x14001430e  jz      loc_14001498C
0x140014314  mov     rcx, [r15+60h]
0x140014318  add     rcx, 0B8h; SpinLock
0x14001431f  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x140014326  nop     dword ptr [rax+rax+00h]
0x14001432b  movzx   r14d, al
0x14001432f  mov     [rsp+0F8h+var_97], al
0x140014333  mov     rax, [r15+60h]
0x140014337  cmp     dword ptr [rax+0Ch], 0DCh
0x14001433e  jnz     loc_14001484C
0x140014344  mov     rax, [rsp+0F8h+arg_20]
0x14001434c  mov     r9, [rsp+0F8h+var_70]
0x140014354  mov     r8, [rsp+0F8h+var_78]
0x14001435c  mov     rdx, [rsp+0F8h+var_80]
0x140014361  mov     [rsp+0F8h+var_70], r9
0x140014369  mov     [rsp+0F8h+var_78], r8
0x140014371  mov     [rsp+0F8h+var_80], rdx
0x140014376  mov     [rsp+0F8h+var_90], r13
0x14001437b  mov     dword ptr [rbx+0Ch], 0DCh
0x140014382  test    rax, rax
0x140014385  jz      short loc_140014398
0x140014387  mov     byte ptr [rbx+87h], 1
0x14001438e  movzx   eax, word ptr [rax]
0x140014391  mov     [rbx+0A8h], ax
0x140014398  movups  xmm0, xmmword ptr [rbp+0]
0x14001439c  mov     [rbx+0C8h], rdi
0x1400143a3  movups  xmmword ptr [rbx+50h], xmm0
0x1400143a7  lock inc dword ptr [rdi+0Ch]
0x1400143ab  mov     rax, [rsi+18h]
0x1400143af  mov     ecx, 1
0x1400143b4  mov     [rbx+170h], rax
0x1400143bb  mov     rax, [rsi+18h]
0x1400143bf  lock xadd [rax], rcx
0x1400143c4  lea     rax, [rcx+2]
0x1400143c8  test    rax, 0FFFFFFFFFFFFFFFEh
0x1400143ce  jnz     short loc_1400143D2
0x1400143d0  int     2Ch; Windows NT - assertion failure
0x1400143d2  movd    xmm1, dword ptr [r13+0]
0x1400143d8  xorps   xmm0, xmm0
0x1400143db  movd    xmm2, dword ptr [rdx]
0x1400143df  xor     edx, edx
0x1400143e1  punpcklbw xmm1, xmm0
0x1400143e5  punpcklwd xmm1, xmm0
0x1400143e9  punpcklbw xmm2, xmm0
0x1400143ed  punpcklwd xmm2, xmm0
0x1400143f1  paddd   xmm2, xmm1
0x1400143f5  movd    xmm1, dword ptr [r8]
0x1400143fa  punpcklbw xmm1, xmm0
0x1400143fe  punpcklwd xmm1, xmm0
0x140014402  paddd   xmm2, xmm1
0x140014406  movd    xmm1, dword ptr [rbp+0]
0x14001440b  punpcklbw xmm1, xmm0
0x14001440f  punpcklwd xmm1, xmm0
0x140014413  paddd   xmm2, xmm1
0x140014417  movdqa  xmm0, xmm2
0x14001441b  psrldq  xmm0, 8
0x140014420  paddd   xmm2, xmm0
0x140014424  movdqa  xmm0, xmm2
0x140014428  psrldq  xmm0, 4
0x14001442d  paddd   xmm2, xmm0
0x140014431  movd    eax, xmm2
0x140014435  div     dword ptr [rdi]
0x140014437  mov     r13d, edx
0x14001443a  shl     r13, 5
0x14001443e  add     r13, [r9]
0x140014441  mov     rcx, r13; SpinLock
0x140014444  mov     eax, [r13+0Ch]
0x140014448  test    al, 1
0x14001444a  jz      loc_140014813
0x140014450  call    cs:__imp_ExAcquireSpinLockExclusive
0x140014457  nop     dword ptr [rax+rax+00h]
0x14001445c  mov     [rsp+0F8h+var_98], al
0x140014460  cmp     qword ptr [rdi+20h], 0
0x140014465  jz      loc_14001451A
0x14001446b  mov     rsi, [r13+10h]
0x14001446f  lea     r14, [r13+10h]
0x140014473  cmp     rsi, r14
0x140014476  jz      short loc_1400144AA
0x140014478  mov     eax, [rdi+4]
0x14001447b  mov     r8d, 10h
0x140014481  neg     eax
0x140014483  mov     rdx, rbp
0x140014486  movsxd  rcx, eax
0x140014489  mov     rax, [rdi+20h]
0x14001448d  add     rcx, rsi
0x140014490  call    _guard_dispatch_icall
0x140014495  test    al, al
0x140014497  jnz     loc_14001464E
0x14001449d  mov     rsi, [rsi]
0x1400144a0  jmp     short loc_140014473
0x1400144a2  mov     rsi, [rsi]
0x1400144a5  jmp     loc_14001427C
0x1400144aa  mov     ecx, [rdi+10h]
0x1400144ad  mov     eax, 1
0x1400144b2  lock xadd [rdi+8], eax
0x1400144b7  inc     eax
0x1400144b9  cmp     eax, ecx
0x1400144bb  ja      loc_14001490B
0x1400144c1  inc     dword ptr [r13+8]
0x1400144c5  mov     rdx, [r14]
0x1400144c8  cmp     [rdx+8], r14
0x1400144cc  jnz     loc_140014985
0x1400144d2  mov     ecx, [rdi+4]
0x1400144d5  xor     esi, esi
0x1400144d7  add     rcx, rbx
0x1400144da  mov     [rcx], rdx
0x1400144dd  mov     [rcx+8], r14
0x1400144e1  mov     [rdx+8], rcx
0x1400144e5  mov     [r14], rcx
0x1400144e8  mov     eax, [r13+0Ch]
0x1400144ec  mov     rcx, r13; SpinLock
0x1400144ef  test    al, 1
0x1400144f1  jz      loc_140014800
0x1400144f7  movzx   edx, [rsp+0F8h+var_98]; OldIrql
0x1400144fc  call    cs:__imp_ExReleaseSpinLockExclusive
0x140014503  nop     dword ptr [rax+rax+00h]
0x140014508  cmp     esi, 0C000022Ah
0x14001450e  jz      loc_1400145EC
0x140014514  movzx   r14d, [rsp+0F8h+var_97]
0x14001451a  mov     edi, 1
0x14001451f  lock xadd [rbx], rdi
0x140014524  inc     rdi
0x140014527  lea     rax, [rdi+1]
0x14001452b  test    rax, 0FFFFFFFFFFFFFFFEh
0x140014531  jnz     short loc_140014535
0x140014533  int     2Ch; Windows NT - assertion failure
0x140014535  mov     rax, cs:WPP_GLOBAL_Control
0x14001453c  test    dword ptr [rax+2Ch], 40000000h
0x140014543  jnz     loc_14003C660
0x140014549  cmp     [rsp+0F8h+var_96], 0
0x14001454e  jz      short loc_140014582
0x140014550  lea     rcx, [rbx+60h]; SpinLock
0x140014554  call    cs:__imp_KeAcquireSpinLockRaiseToDpc
0x14001455b  nop     dword ptr [rax+rax+00h]
0x140014560  cmp     byte ptr [rbx+80h], 0
0x140014567  jnz     short loc_14001456F
0x140014569  inc     dword ptr [rbx+0ACh]
0x14001456f  movzx   edx, al; NewIrql
0x140014572  lea     rcx, [rbx+60h]; SpinLock
0x140014576  call    cs:__imp_KeReleaseSpinLock
0x14001457d  nop     dword ptr [rax+rax+00h]
0x140014582  mov     rcx, [r15+60h]
0x140014586  movzx   edx, r14b; NewIrql
0x14001458a  add     rcx, 0B8h; SpinLock
0x140014591  call    cs:__imp_KeReleaseSpinLock
0x140014598  nop     dword ptr [rax+rax+00h]
0x14001459d  mov     [r12+68h], rbx
0x1400145a2  xor     ebx, ebx
0x1400145a4  mov     eax, ebx
0x1400145a6  mov     r13, [rsp+0F8h+var_30]
0x1400145ae  mov     rbx, [rsp+0F8h+arg_10]
0x1400145b6  mov     r14, [rsp+0F8h+var_38]
0x1400145be  mov     rsi, [rsp+0F8h+var_20]
0x1400145c6  mov     rdi, [rsp+0F8h+var_28]
0x1400145ce  mov     rcx, [rsp+0F8h+var_40]
0x1400145d6  xor     rcx, rsp; StackCookie
0x1400145d9  call    __security_check_cookie
0x1400145de  add     rsp, 0E0h
0x1400145e5  pop     r15
0x1400145e7  pop     r12
0x1400145e9  pop     rbp
0x1400145ea  retn
0x1400145ec  mov     rcx, [r15+60h]
0x1400145f0  movzx   edx, [rsp+0F8h+var_97]; NewIrql
0x1400145f5  add     rcx, 0B8h; SpinLock
0x1400145fc  call    cs:__imp_KeReleaseSpinLock
0x140014603  nop     dword ptr [rax+rax+00h]
0x140014608  mov     rcx, rbx
0x14001460b  mov     byte ptr [rbx+80h], 1
0x140014612  call    Smb2DereferenceLease
0x140014617  mov     edx, [rsp+0F8h+var_94]
0x14001461b  inc     edx
0x14001461d  mov     [rsp+0F8h+var_94], edx
0x140014621  cmp     edx, 3
0x140014624  ja      loc_14001493C
0x14001462a  mov     rsi, [rsp+0F8h+var_88]
0x14001462f  mov     r13, [rsp+0F8h+var_90]
0x140014634  mov     rax, [rsp+0F8h+var_80]
0x140014639  mov     rcx, [rsp+0F8h+var_78]
0x140014641  mov     r8, [rsp+0F8h+var_70]
0x140014649  jmp     loc_1400141C7
0x14001464e  mov     esi, 0C000022Ah
0x140014653  jmp     loc_1400144E8
0x140014658  cmp     byte ptr [rbx+81h], 0
0x14001465f  jnz     loc_14001475C
  ... truncated ...
```
