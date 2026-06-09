# RtlCombineNtPathSegments

- ea: `0x180079174`
- end: `0x180079515`
- name: `RtlCombineNtPathSegments`
- size: `929`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `8`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18007890c`

## callees

- `0x18000d030`
- `0x18000dd98`
- `0x18006a198`
- `0x18006a2a8`
- `0x180078ed8`
- `0x180078efc`
- `0x180079174`
- `0x18007951c`

## string_xrefs

- `0x180079244`: `Not-null check failed: PathOut`
- `0x1800791b9`: `onecore\base\lstring\path.cpp`
- `0x180079226`: `onecore\base\lstring\path.cpp`
- `0x180079417`: `onecore\base\lstring\path.cpp`
- `0x180079465`: `onecore\base\lstring\path.cpp`
- `0x1800791cc`: `RtlCombineNtPathSegments`
- `0x180079239`: `RtlCombineNtPathSegments`
- `0x18007942e`: `RtlCombineNtPathSegments`
- `0x18007947c`: `RtlCombineNtPathSegments`
- `0x1800791d7`: `(PathSegmentCount == 0) || (PathSegments != 0)`
- `0x180079487`: `BytesLeft >= BytesToCopy`

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
0x180079174  mov     rax, rsp
0x180079177  mov     [rax+8], rbx
0x18007917b  push    rbp
0x18007917c  push    rsi
0x18007917d  push    rdi
0x18007917e  push    r12
0x180079180  push    r13
0x180079182  push    r14
0x180079184  push    r15
0x180079186  lea     rbp, [rax-5Fh]
0x18007918a  sub     rsp, 0C0h
0x180079191  movaps  xmmword ptr [rax-48h], xmm6
0x180079195  mov     rax, cs:__security_cookie
0x18007919c  xor     rax, rsp
0x18007919f  mov     [rbp+57h+var_50], rax
0x1800791a3  mov     [rbp+57h+var_80], rdx
0x1800791a7  mov     r15, r8
0x1800791aa  mov     [rbp+57h+var_58], 0
0x1800791b1  mov     r13, rdx
0x1800791b4  test    rdx, rdx
0x1800791b7  jnz     short loc_180079221
0x1800791b9  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800791c0  mov     [rbp+57h+var_A8], 25Ah
0x1800791c8  mov     qword ptr [rbp+57h+var_B8], rax
0x1800791cc  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x1800791d3  mov     qword ptr [rbp+57h+var_B8+8], rax
0x1800791d7  lea     rax, aPathsegmentcou; "(PathSegmentCount == 0) || (PathSegment"...
0x1800791de  mov     r8d, 0C000000Dh
0x1800791e4  mov     [rbp+57h+var_A0], rax
0x1800791e8  lea     rdx, [rbp+57h+var_B8]
0x1800791ec  lea     rcx, [rbp+57h+var_58]
0x1800791f0  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x1800791f5  mov     rcx, [rbp+57h+var_50]
0x1800791f9  xor     rcx, rsp; StackCookie
0x1800791fc  call    __security_check_cookie
0x180079201  lea     r11, [rsp+0F0h+var_30]
0x180079209  mov     rbx, [r11+40h]
0x18007920d  movaps  xmm6, xmmword ptr [r11-10h]
0x180079212  mov     rsp, r11
0x180079215  pop     r15
0x180079217  pop     r14
0x180079219  pop     r13
0x18007921b  pop     r12
0x18007921d  pop     rdi
0x18007921e  pop     rsi
0x18007921f  pop     rbp
0x180079220  retn
0x180079221  test    r15, r15
0x180079224  jnz     short loc_18007924D
0x180079226  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18007922d  mov     [rbp+57h+var_A8], 25Bh
0x180079235  mov     qword ptr [rbp+57h+var_B8], rax
0x180079239  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180079240  mov     qword ptr [rbp+57h+var_B8+8], rax
0x180079244  lea     rax, aNotNullCheckFa; "Not-null check failed: PathOut"
0x18007924b  jmp     short loc_1800791DE
0x18007924d  xor     edi, edi
0x18007924f  xor     ebx, ebx
0x180079251  lea     rax, [rbx+rbx*2]
0x180079255  mov     qword ptr [rbp+57h+var_C0], 0
0x18007925d  lea     rcx, ds:0[rax*8]
0x180079265  mov     [rbp+57h+var_C8], 0
0x18007926d  add     rcx, r13
0x180079270  lea     r8, [rbp+57h+var_C8]
0x180079274  lea     rdx, [rbp+57h+var_C0]
0x180079278  mov     rsi, [rcx]
0x18007927b  call    RtlTrimNtPathSegment
0x180079280  test    eax, eax
0x180079282  js      loc_1800791F5
0x180079288  mov     rdx, qword ptr [rbp+57h+var_C0]
0x18007928c  cmp     rdx, rsi
0x18007928f  ja      loc_180079509
0x180079295  mov     rax, rsi
0x180079298  sub     rax, rdx
0x18007929b  cmp     [rbp+57h+var_C8], rax
0x18007929f  ja      loc_180079509
0x1800792a5  mov     rax, rbx
0x1800792a8  neg     rax
0x1800792ab  sbb     rcx, rcx
0x1800792ae  sub     rsi, [rbp+57h+var_C8]
0x1800792b2  and     rcx, rdx
0x1800792b5  sub     rsi, rcx
0x1800792b8  jz      short loc_1800792D1
0x1800792ba  lea     rax, [rsi+rdi]
0x1800792be  cmp     rax, rdi
0x1800792c1  jb      short loc_180079308
0x1800792c3  test    rbx, rbx
0x1800792c6  jz      short loc_1800792FD
0x1800792c8  lea     rdi, [rax+2]
0x1800792cc  cmp     rdi, rax
0x1800792cf  jb      short loc_180079308
0x1800792d1  inc     rbx
0x1800792d4  cmp     rbx, 2
0x1800792d8  jb      loc_180079251
0x1800792de  mov     rsi, [r15+8]
0x1800792e2  xor     eax, eax
0x1800792e4  mov     [rbp+57h+var_88], rax
0x1800792e8  xorps   xmm6, xmm6
0x1800792eb  movups  [rbp+57h+var_98], xmm6
0x1800792ef  cmp     rdi, rsi
0x1800792f2  ja      short loc_180079312
0x1800792f4  mov     r14, [r15+10h]
0x1800792f8  mov     [rbp+57h+var_CF], al
0x1800792fb  jmp     short loc_180079338
0x1800792fd  mov     rdi, rax
0x180079300  inc     rbx
0x180079303  jmp     loc_180079251
0x180079308  mov     eax, 0C0000095h
0x18007930d  jmp     loc_1800791F5
0x180079312  lea     rdx, [rbp+57h+var_98]
0x180079316  mov     rcx, rdi
0x180079319  call    RtlAllocateLUnicodeString
0x18007931e  mov     ebx, eax
0x180079320  test    eax, eax
0x180079322  js      loc_180079455
0x180079328  mov     rsi, qword ptr [rbp+57h+var_98+8]
0x18007932c  mov     r14, [rbp+57h+var_88]
0x180079330  movups  xmm6, [rbp+57h+var_98]
0x180079334  mov     [rbp+57h+var_CF], 1
0x180079338  mov     [rbp+57h+var_D0], 1
0x18007933c  xor     r12d, r12d
0x18007933f  mov     rbx, r14
0x180079342  lea     rax, [r12+r12*2]
0x180079346  mov     qword ptr [rbp+57h+var_C0], 0
0x18007934e  lea     r13, [r13+rax*8+0]
0x180079353  mov     [rbp+57h+var_C8], 0
0x18007935b  mov     rdi, [r13+0]
0x18007935f  test    rdi, rdi
0x180079362  jz      loc_180079401
0x180079368  lea     r8, [rbp+57h+var_C8]
0x18007936c  mov     rcx, r13
0x18007936f  lea     rdx, [rbp+57h+var_C0]
0x180079373  call    RtlTrimNtPathSegment
0x180079378  test    eax, eax
0x18007937a  js      loc_180079453
0x180079380  mov     rcx, qword ptr [rbp+57h+var_C0]; int
0x180079384  cmp     rcx, rdi
0x180079387  ja      loc_18007950F
0x18007938d  sub     rdi, rcx
0x180079390  cmp     [rbp+57h+var_C8], rdi
0x180079394  ja      loc_18007950F
0x18007939a  cmp     [rbp+57h+var_D0], 0
0x18007939e  jz      short loc_1800793A4
0x1800793a0  xor     ecx, ecx
0x1800793a2  jmp     short loc_1800793D1
0x1800793a4  cmp     rcx, 2
0x1800793a8  jnb     short loc_1800793CD
0x1800793aa  mov     eax, 5Ch ; '\'
0x1800793af  cmp     rbx, r14
0x1800793b2  jz      short loc_1800793BA
0x1800793b4  cmp     [rbx-2], ax
0x1800793b8  jz      short loc_1800793D1
0x1800793ba  cmp     rsi, 2
0x1800793be  jb      short loc_180079417
0x1800793c0  mov     [rbx], ax
0x1800793c3  add     rbx, 2
0x1800793c7  sub     rsi, 2
0x1800793cb  jmp     short loc_1800793D1
0x1800793cd  sub     rcx, 2
0x1800793d1  mov     rdi, [r13+0]
0x1800793d5  sub     rdi, [rbp+57h+var_C8]
0x1800793d9  sub     rdi, rcx
0x1800793dc  cmp     rsi, rdi
0x1800793df  jb      loc_180079465
0x1800793e5  mov     rdx, [r13+10h]
0x1800793e9  mov     r8, rdi; Size
0x1800793ec  add     rdx, rcx; Src
0x1800793ef  mov     rcx, rbx; void *
0x1800793f2  call    memcpy_0
0x1800793f7  add     rbx, rdi
0x1800793fa  mov     [rbp+57h+var_D0], 0
0x1800793fe  sub     rsi, rdi
0x180079401  inc     r12
0x180079404  cmp     r12, 2
0x180079408  jnb     loc_180079494
0x18007940e  mov     r13, [rbp+57h+var_80]
0x180079412  jmp     loc_180079342
0x180079417  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18007941e  mov     [rbp+57h+var_A8], 2B6h
0x180079426  mov     qword ptr [rbp+57h+var_B8], rax
0x18007942a  lea     rdx, [rbp+57h+var_B8]
0x18007942e  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180079435  mov     qword ptr [rbp+57h+var_B8+8], rax
0x180079439  lea     rax, aBytesleftSizeo; "BytesLeft >= sizeof(WCHAR)"
0x180079440  mov     [rbp+57h+var_A0], rax
0x180079444  mov     r8d, 0C0000023h
0x18007944a  lea     rcx, [rbp+57h+var_58]
0x18007944e  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180079453  mov     ebx, eax
0x180079455  lea     rcx, [rbp+57h+var_98]
0x180079459  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x18007945e  mov     eax, ebx
0x180079460  jmp     loc_1800791F5
0x180079465  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18007946c  mov     [rbp+57h+var_68], 2C4h
0x180079474  mov     [rbp+57h+var_78], rax
0x180079478  lea     rdx, [rbp+57h+var_78]
0x18007947c  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180079483  mov     [rbp+57h+var_70], rax
0x180079487  lea     rax, aBytesleftBytes; "BytesLeft >= BytesToCopy"
0x18007948e  mov     [rbp+57h+var_60], rax
0x180079492  jmp     short loc_180079444
0x180079494  cmp     [rbp+57h+var_CF], 0
0x180079498  jz      short loc_1800794E8
0x18007949a  xorps   xmm0, xmm0
0x18007949d  lea     rcx, [rbp+57h+var_B8]
0x1800794a1  xor     eax, eax
0x1800794a3  movups  [rbp+57h+var_B8], xmm0
0x1800794a7  mov     [rbp+57h+var_A8], rax
0x1800794ab  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x1800794b0  movups  xmm0, xmmword ptr [r15]
0x1800794b4  lea     rcx, [rbp+57h+var_B8]
0x1800794b8  xor     eax, eax
0x1800794ba  movsd   xmm1, qword ptr [r15+10h]
0x1800794c0  movups  [rbp+57h+var_B8], xmm0
0x1800794c4  movsd   [rbp+57h+var_A8], xmm1
0x1800794c9  xorps   xmm0, xmm0
0x1800794cc  movsd   xmm1, [rbp+57h+var_88]
0x1800794d1  movups  xmmword ptr [r15], xmm6
0x1800794d5  mov     [rbp+57h+var_88], rax
0x1800794d9  movups  [rbp+57h+var_98], xmm0
0x1800794dd  movsd   qword ptr [r15+10h], xmm1
0x1800794e3  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x1800794e8  cmp     rbx, r14
0x1800794eb  jb      short loc_180079503
0x1800794ed  sub     rbx, r14
0x1800794f0  lea     rcx, [rbp+57h+var_98]
0x1800794f4  mov     [r15], rbx
0x1800794f7  call    ?Close@?$AutoString@U_LUNICODE_STRING@@V?$Auto@U_LUNICODE_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUNICODE_STRING,Windows::Auto<_LUNICODE_STRING>>::Close(void)
0x1800794fc  xor     eax, eax
0x1800794fe  jmp     loc_1800791F5
0x180079503  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x180079509  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x18007950f  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
