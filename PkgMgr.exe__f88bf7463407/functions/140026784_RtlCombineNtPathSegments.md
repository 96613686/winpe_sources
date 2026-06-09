# RtlCombineNtPathSegments

- ea: `0x140026784`
- end: `0x140026b25`
- name: `RtlCombineNtPathSegments`
- size: `929`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x140025fb0`
- `0x1400263f8`

## callees

- `0x140002360`
- `0x14000731c`
- `0x140025934`
- `0x140026548`
- `0x140026574`
- `0x140026784`
- `0x140026b2c`
- `0x140029bf4`

## string_xrefs

- `0x1400267c9`: `onecore\base\lstring\path.cpp`
- `0x140026836`: `onecore\base\lstring\path.cpp`
- `0x140026a27`: `onecore\base\lstring\path.cpp`
- `0x140026a75`: `onecore\base\lstring\path.cpp`
- `0x140026854`: `Not-null check failed: PathOut`
- `0x1400267dc`: `RtlCombineNtPathSegments`
- `0x140026849`: `RtlCombineNtPathSegments`
- `0x140026a3e`: `RtlCombineNtPathSegments`
- `0x140026a8c`: `RtlCombineNtPathSegments`
- `0x1400267e7`: `(PathSegmentCount == 0) || (PathSegments != 0)`
- `0x140026a97`: `BytesLeft >= BytesToCopy`

## pseudocode

```c
__int64 __fastcall RtlCombineNtPathSegments(__int64 a1, __int64 a2, __int128 *a3)
{
  __int64 v4; // r13
  const char *v5; // rax
  __int64 result; // rax
  unsigned __int64 v7; // rdi
  unsigned __int64 i; // rbx
  unsigned __int64 *v9; // rcx
  unsigned __int64 v10; // rsi
  int v11; // ecx
  __int64 v12; // rcx
  __int64 v13; // rsi
  unsigned __int64 v14; // rax
  unsigned __int64 v15; // rsi
  __int128 v16; // xmm6
  _WORD *v17; // r14
  int v18; // ebx
  __int64 v19; // r12
  _WORD *v20; // rbx
  unsigned __int64 *v21; // r13
  unsigned __int64 v22; // rdi
  int v23; // eax
  __int64 v24; // rcx
  unsigned __int64 v25; // rdi
  __int128 *v26; // rdx
  __int64 v27; // xmm1_8
  _WORD *v28; // xmm1_8
  char v29; // [rsp+28h] [rbp-79h]
  char v30; // [rsp+29h] [rbp-78h]
  unsigned __int64 v31; // [rsp+30h] [rbp-71h] BYREF
  int v32[2]; // [rsp+38h] [rbp-69h] BYREF
  __int128 v33; // [rsp+40h] [rbp-61h] BYREF
  __int64 v34; // [rsp+50h] [rbp-51h]
  const char *v35; // [rsp+58h] [rbp-49h]
  __int128 v36; // [rsp+60h] [rbp-41h] BYREF
  _WORD *v37; // [rsp+70h] [rbp-31h]
  __int64 v38; // [rsp+78h] [rbp-29h]
  _QWORD v39[4]; // [rsp+80h] [rbp-21h] BYREF
  int v40; // [rsp+A0h] [rbp-1h] BYREF

  v38 = a2;
  v40 = 0;
  v4 = a2;
  if ( !a2 )
  {
    v34 = 602;
    *(_QWORD *)&v33 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v33 + 1) = "RtlCombineNtPathSegments";
    v5 = "(PathSegmentCount == 0) || (PathSegments != 0)";
LABEL_3:
    v35 = v5;
    return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
             &v40,
             &v33,
             3221225485LL);
  }
  if ( !a3 )
  {
    v34 = 603;
    *(_QWORD *)&v33 = "onecore\\base\\lstring\\path.cpp";
    *((_QWORD *)&v33 + 1) = "RtlCombineNtPathSegments";
    v5 = "Not-null check failed: PathOut";
    goto LABEL_3;
  }
  v7 = 0;
  for ( i = 0; i < 2; ++i )
  {
    while ( 1 )
    {
      *(_QWORD *)v32 = 0;
      v31 = 0;
      v9 = (unsigned __int64 *)(v4 + 24 * i);
      v10 = *v9;
      result = RtlTrimNtPathSegment(v9, v32, &v31);
      if ( (int)result < 0 )
        return result;
      if ( *(_QWORD *)v32 > v10 || v31 > v10 - *(_QWORD *)v32 )
        INTERNAL_ERROR_ACTION(v11);
      v12 = *(_QWORD *)v32 & -(__int64)(i != 0);
      v13 = v10 - v31 - v12;
      if ( !v13 )
        goto LABEL_15;
      v14 = v13 + v7;
      if ( v13 + v7 < v7 )
        return 3221225621LL;
      if ( i )
        break;
      v7 += v13;
      i = 1;
    }
    v7 = v14 + 2;
    if ( v14 + 2 < v14 )
      return 3221225621LL;
LABEL_15:
    ;
  }
  v15 = *((_QWORD *)a3 + 1);
  v37 = 0;
  v16 = 0;
  v36 = 0;
  if ( v7 > v15 )
  {
    v18 = RtlAllocateLUnicodeString(v7, &v36);
    if ( v18 < 0 )
    {
LABEL_42:
      Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v36);
      return (unsigned int)v18;
    }
    v15 = *((_QWORD *)&v36 + 1);
    v17 = v37;
    v16 = v36;
    v30 = 1;
  }
  else
  {
    v17 = (_WORD *)*((_QWORD *)a3 + 2);
    v30 = 0;
  }
  v29 = 1;
  v19 = 0;
  v20 = v17;
  while ( 2 )
  {
    *(_QWORD *)v32 = 0;
    v21 = (unsigned __int64 *)(v4 + 24 * v19);
    v31 = 0;
    v22 = *v21;
    if ( *v21 )
    {
      v23 = RtlTrimNtPathSegment(v21, v32, &v31);
      if ( v23 < 0 )
        goto LABEL_41;
      v24 = *(_QWORD *)v32;
      if ( *(_QWORD *)v32 > v22 || v31 > v22 - *(_QWORD *)v32 )
        INTERNAL_ERROR_ACTION(v32[0]);
      if ( v29 )
      {
        v24 = 0;
        goto LABEL_35;
      }
      if ( *(_QWORD *)v32 >= 2u )
      {
        v24 = *(_QWORD *)v32 - 2LL;
      }
      else if ( v20 == v17 || *(v20 - 1) != 92 )
      {
        if ( v15 >= 2 )
        {
          *v20++ = 92;
          v15 -= 2LL;
          goto LABEL_35;
        }
        v34 = 694;
        *(_QWORD *)&v33 = "onecore\\base\\lstring\\path.cpp";
        v26 = &v33;
        *((_QWORD *)&v33 + 1) = "RtlCombineNtPathSegments";
        v35 = "BytesLeft >= sizeof(WCHAR)";
LABEL_40:
        v23 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                &v40,
                v26,
                3221225507LL);
LABEL_41:
        v18 = v23;
        goto LABEL_42;
      }
LABEL_35:
      v25 = *v21 - v31 - v24;
      if ( v15 < v25 )
      {
        v39[2] = 708;
        v39[0] = "onecore\\base\\lstring\\path.cpp";
        v26 = (__int128 *)v39;
        v39[1] = "RtlCombineNtPathSegments";
        v39[3] = "BytesLeft >= BytesToCopy";
        goto LABEL_40;
      }
      memcpy_0(v20, (const void *)(v24 + v21[2]), *v21 - v31 - v24);
      v20 = (_WORD *)((char *)v20 + v25);
      v29 = 0;
      v15 -= v25;
    }
    if ( (unsigned __int64)++v19 < 2 )
    {
      v4 = v38;
      continue;
    }
    break;
  }
  if ( v30 )
  {
    v33 = 0;
    v34 = 0;
    Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v33);
    v27 = *((_QWORD *)a3 + 2);
    v33 = *a3;
    v34 = v27;
    v28 = v37;
    *a3 = v16;
    v37 = 0;
    v36 = 0;
    *((_QWORD *)a3 + 2) = v28;
    Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v33);
  }
  if ( v20 < v17 )
    INTERNAL_ERROR_ACTION(v12);
  *(_QWORD *)a3 = (char *)v20 - (char *)v17;
  Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(&v36);
  return 0;
}

```

## disassembly

```asm
0x140026784  mov     rax, rsp
0x140026787  mov     [rax+8], rbx
0x14002678b  push    rbp
0x14002678c  push    rsi
0x14002678d  push    rdi
0x14002678e  push    r12
0x140026790  push    r13
0x140026792  push    r14
0x140026794  push    r15
0x140026796  lea     rbp, [rax-5Fh]
0x14002679a  sub     rsp, 0C0h
0x1400267a1  movaps  xmmword ptr [rax-48h], xmm6
0x1400267a5  mov     rax, cs:__security_cookie
0x1400267ac  xor     rax, rsp
0x1400267af  mov     [rbp+57h+var_50], rax
0x1400267b3  mov     [rbp+57h+var_80], rdx
0x1400267b7  mov     r15, r8
0x1400267ba  mov     [rbp+57h+var_58], 0
0x1400267c1  mov     r13, rdx
0x1400267c4  test    rdx, rdx
0x1400267c7  jnz     short loc_140026831
0x1400267c9  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1400267d0  mov     [rbp+57h+var_A8], 25Ah
0x1400267d8  mov     qword ptr [rbp+57h+var_B8], rax
0x1400267dc  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x1400267e3  mov     qword ptr [rbp+57h+var_B8+8], rax
0x1400267e7  lea     rax, aPathsegmentcou; "(PathSegmentCount == 0) || (PathSegment"...
0x1400267ee  mov     r8d, 0C000000Dh
0x1400267f4  mov     [rbp+57h+var_A0], rax
0x1400267f8  lea     rdx, [rbp+57h+var_B8]
0x1400267fc  lea     rcx, [rbp+57h+var_58]
0x140026800  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026805  mov     rcx, [rbp+57h+var_50]
0x140026809  xor     rcx, rsp; StackCookie
0x14002680c  call    __security_check_cookie
0x140026811  lea     r11, [rsp+0F0h+var_30]
0x140026819  mov     rbx, [r11+40h]
0x14002681d  movaps  xmm6, xmmword ptr [r11-10h]
0x140026822  mov     rsp, r11
0x140026825  pop     r15
0x140026827  pop     r14
0x140026829  pop     r13
0x14002682b  pop     r12
0x14002682d  pop     rdi
0x14002682e  pop     rsi
0x14002682f  pop     rbp
0x140026830  retn
0x140026831  test    r15, r15
0x140026834  jnz     short loc_14002685D
0x140026836  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x14002683d  mov     [rbp+57h+var_A8], 25Bh
0x140026845  mov     qword ptr [rbp+57h+var_B8], rax
0x140026849  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x140026850  mov     qword ptr [rbp+57h+var_B8+8], rax
0x140026854  lea     rax, aNotNullCheckFa; "Not-null check failed: PathOut"
0x14002685b  jmp     short loc_1400267EE
0x14002685d  xor     edi, edi
0x14002685f  xor     ebx, ebx
0x140026861  lea     rax, [rbx+rbx*2]
0x140026865  mov     qword ptr [rbp+57h+var_C0], 0
0x14002686d  lea     rcx, ds:0[rax*8]
0x140026875  mov     [rbp+57h+var_C8], 0
0x14002687d  add     rcx, r13
0x140026880  lea     r8, [rbp+57h+var_C8]
0x140026884  lea     rdx, [rbp+57h+var_C0]
0x140026888  mov     rsi, [rcx]
0x14002688b  call    RtlTrimNtPathSegment
0x140026890  test    eax, eax
0x140026892  js      loc_140026805
0x140026898  mov     rdx, qword ptr [rbp+57h+var_C0]
0x14002689c  cmp     rdx, rsi
0x14002689f  ja      loc_140026B19
0x1400268a5  mov     rax, rsi
0x1400268a8  sub     rax, rdx
0x1400268ab  cmp     [rbp+57h+var_C8], rax
0x1400268af  ja      loc_140026B19
0x1400268b5  mov     rax, rbx
0x1400268b8  neg     rax
0x1400268bb  sbb     rcx, rcx
0x1400268be  sub     rsi, [rbp+57h+var_C8]
0x1400268c2  and     rcx, rdx
0x1400268c5  sub     rsi, rcx
0x1400268c8  jz      short loc_1400268E1
0x1400268ca  lea     rax, [rsi+rdi]
0x1400268ce  cmp     rax, rdi
0x1400268d1  jb      short loc_140026918
0x1400268d3  test    rbx, rbx
0x1400268d6  jz      short loc_14002690D
0x1400268d8  lea     rdi, [rax+2]
0x1400268dc  cmp     rdi, rax
0x1400268df  jb      short loc_140026918
0x1400268e1  inc     rbx
0x1400268e4  cmp     rbx, 2
0x1400268e8  jb      loc_140026861
0x1400268ee  mov     rsi, [r15+8]
0x1400268f2  xor     eax, eax
0x1400268f4  mov     [rbp+57h+var_88], rax
0x1400268f8  xorps   xmm6, xmm6
0x1400268fb  movups  [rbp+57h+var_98], xmm6
0x1400268ff  cmp     rdi, rsi
0x140026902  ja      short loc_140026922
0x140026904  mov     r14, [r15+10h]
0x140026908  mov     [rbp+57h+var_CF], al
0x14002690b  jmp     short loc_140026948
0x14002690d  mov     rdi, rax
0x140026910  inc     rbx
0x140026913  jmp     loc_140026861
0x140026918  mov     eax, 0C0000095h
0x14002691d  jmp     loc_140026805
0x140026922  lea     rdx, [rbp+57h+var_98]
0x140026926  mov     rcx, rdi
0x140026929  call    RtlAllocateLUnicodeString
0x14002692e  mov     ebx, eax
0x140026930  test    eax, eax
0x140026932  js      loc_140026A65
0x140026938  mov     rsi, qword ptr [rbp+57h+var_98+8]
0x14002693c  mov     r14, [rbp+57h+var_88]
0x140026940  movups  xmm6, [rbp+57h+var_98]
0x140026944  mov     [rbp+57h+var_CF], 1
0x140026948  mov     [rbp+57h+var_D0], 1
0x14002694c  xor     r12d, r12d
0x14002694f  mov     rbx, r14
0x140026952  lea     rax, [r12+r12*2]
0x140026956  mov     qword ptr [rbp+57h+var_C0], 0
0x14002695e  lea     r13, [r13+rax*8+0]
0x140026963  mov     [rbp+57h+var_C8], 0
0x14002696b  mov     rdi, [r13+0]
0x14002696f  test    rdi, rdi
0x140026972  jz      loc_140026A11
0x140026978  lea     r8, [rbp+57h+var_C8]
0x14002697c  mov     rcx, r13
0x14002697f  lea     rdx, [rbp+57h+var_C0]
0x140026983  call    RtlTrimNtPathSegment
0x140026988  test    eax, eax
0x14002698a  js      loc_140026A63
0x140026990  mov     rcx, qword ptr [rbp+57h+var_C0]; int
0x140026994  cmp     rcx, rdi
0x140026997  ja      loc_140026B1F
0x14002699d  sub     rdi, rcx
0x1400269a0  cmp     [rbp+57h+var_C8], rdi
0x1400269a4  ja      loc_140026B1F
0x1400269aa  cmp     [rbp+57h+var_D0], 0
0x1400269ae  jz      short loc_1400269B4
0x1400269b0  xor     ecx, ecx
0x1400269b2  jmp     short loc_1400269E1
0x1400269b4  cmp     rcx, 2
0x1400269b8  jnb     short loc_1400269DD
0x1400269ba  mov     eax, 5Ch ; '\'
0x1400269bf  cmp     rbx, r14
0x1400269c2  jz      short loc_1400269CA
0x1400269c4  cmp     [rbx-2], ax
0x1400269c8  jz      short loc_1400269E1
0x1400269ca  cmp     rsi, 2
0x1400269ce  jb      short loc_140026A27
0x1400269d0  mov     [rbx], ax
0x1400269d3  add     rbx, 2
0x1400269d7  sub     rsi, 2
0x1400269db  jmp     short loc_1400269E1
0x1400269dd  sub     rcx, 2
0x1400269e1  mov     rdi, [r13+0]
0x1400269e5  sub     rdi, [rbp+57h+var_C8]
0x1400269e9  sub     rdi, rcx
0x1400269ec  cmp     rsi, rdi
0x1400269ef  jb      loc_140026A75
0x1400269f5  mov     rdx, [r13+10h]
0x1400269f9  mov     r8, rdi; Size
0x1400269fc  add     rdx, rcx; Src
0x1400269ff  mov     rcx, rbx; void *
0x140026a02  call    memcpy_0
0x140026a07  add     rbx, rdi
0x140026a0a  mov     [rbp+57h+var_D0], 0
0x140026a0e  sub     rsi, rdi
0x140026a11  inc     r12
0x140026a14  cmp     r12, 2
0x140026a18  jnb     loc_140026AA4
0x140026a1e  mov     r13, [rbp+57h+var_80]
0x140026a22  jmp     loc_140026952
0x140026a27  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x140026a2e  mov     [rbp+57h+var_A8], 2B6h
0x140026a36  mov     qword ptr [rbp+57h+var_B8], rax
0x140026a3a  lea     rdx, [rbp+57h+var_B8]
0x140026a3e  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x140026a45  mov     qword ptr [rbp+57h+var_B8+8], rax
0x140026a49  lea     rax, aBytesleftSizeo; "BytesLeft >= sizeof(WCHAR)"
0x140026a50  mov     [rbp+57h+var_A0], rax
0x140026a54  mov     r8d, 0C0000023h
0x140026a5a  lea     rcx, [rbp+57h+var_58]
0x140026a5e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x140026a63  mov     ebx, eax
0x140026a65  lea     rcx, [rbp+57h+var_98]
0x140026a69  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x140026a6e  mov     eax, ebx
0x140026a70  jmp     loc_140026805
0x140026a75  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x140026a7c  mov     [rbp+57h+var_68], 2C4h
0x140026a84  mov     [rbp+57h+var_78], rax
0x140026a88  lea     rdx, [rbp+57h+var_78]
0x140026a8c  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x140026a93  mov     [rbp+57h+var_70], rax
0x140026a97  lea     rax, aBytesleftBytes; "BytesLeft >= BytesToCopy"
0x140026a9e  mov     [rbp+57h+var_60], rax
0x140026aa2  jmp     short loc_140026A54
0x140026aa4  cmp     [rbp+57h+var_CF], 0
0x140026aa8  jz      short loc_140026AF8
0x140026aaa  xorps   xmm0, xmm0
0x140026aad  lea     rcx, [rbp+57h+var_B8]
0x140026ab1  xor     eax, eax
0x140026ab3  movups  [rbp+57h+var_B8], xmm0
0x140026ab7  mov     [rbp+57h+var_A8], rax
0x140026abb  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x140026ac0  movups  xmm0, xmmword ptr [r15]
0x140026ac4  lea     rcx, [rbp+57h+var_B8]
0x140026ac8  xor     eax, eax
0x140026aca  movsd   xmm1, qword ptr [r15+10h]
0x140026ad0  movups  [rbp+57h+var_B8], xmm0
0x140026ad4  movsd   [rbp+57h+var_A8], xmm1
0x140026ad9  xorps   xmm0, xmm0
0x140026adc  movsd   xmm1, [rbp+57h+var_88]
0x140026ae1  movups  xmmword ptr [r15], xmm6
0x140026ae5  mov     [rbp+57h+var_88], rax
0x140026ae9  movups  [rbp+57h+var_98], xmm0
0x140026aed  movsd   qword ptr [r15+10h], xmm1
0x140026af3  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x140026af8  cmp     rbx, r14
0x140026afb  jb      short loc_140026B13
0x140026afd  sub     rbx, r14
0x140026b00  lea     rcx, [rbp+57h+var_98]
0x140026b04  mov     [r15], rbx
0x140026b07  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x140026b0c  xor     eax, eax
0x140026b0e  jmp     loc_140026805
0x140026b13  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x140026b19  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x140026b1f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
