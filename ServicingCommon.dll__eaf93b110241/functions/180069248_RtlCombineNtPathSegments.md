# RtlCombineNtPathSegments

- ea: `0x180069248`
- end: `0x1800695ea`
- name: `RtlCombineNtPathSegments`
- size: `930`
- prototype: ``
- caller_count: `5`
- callee_count: `9`
- tags: `reparse_path, broker_com_uri`

## callers

- `0x18003fdac`
- `0x18004027c`
- `0x180041a00`
- `0x1800748c4`
- `0x18008cd70`

## callees

- `0x180002564`
- `0x180002c00`
- `0x18001f4ac`
- `0x18001f5d4`
- `0x18001fd10`
- `0x1800293a0`
- `0x180069248`
- `0x18006a1cc`
- `0x18009a070`

## string_xrefs

- `0x18006928d`: `onecore\base\lstring\path.cpp`
- `0x1800692f5`: `onecore\base\lstring\path.cpp`
- `0x1800694f3`: `onecore\base\lstring\path.cpp`
- `0x180069522`: `onecore\base\lstring\path.cpp`
- `0x18006931b`: `Not-null check failed: PathOut`
- `0x1800692a4`: `RtlCombineNtPathSegments`
- `0x18006930c`: `RtlCombineNtPathSegments`
- `0x18006950a`: `RtlCombineNtPathSegments`
- `0x180069539`: `RtlCombineNtPathSegments`
- `0x1800692b3`: `(PathSegmentCount == 0) || (PathSegments != 0)`
- `0x180069544`: `BytesLeft >= BytesToCopy`

## pseudocode

```c
__int64 __fastcall RtlCombineNtPathSegments(__int64 a1, __int64 a2, __int128 *a3)
{
  __int64 v4; // r13
  __int64 result; // rax
  unsigned __int64 v6; // rdi
  __int64 i; // rbx
  unsigned __int64 *v8; // rcx
  unsigned __int64 v9; // rsi
  __int64 v10; // rsi
  unsigned __int64 v11; // rax
  unsigned __int64 v12; // rsi
  __int128 v13; // xmm6
  _WORD *v14; // r14
  int v15; // ebx
  __int64 v16; // r12
  _WORD *v17; // rbx
  unsigned __int64 *v18; // r13
  unsigned __int64 v19; // rdi
  int v20; // eax
  unsigned __int64 v21; // rcx
  unsigned __int64 v22; // rdi
  __int128 *v23; // rdx
  __int64 v24; // xmm1_8
  _WORD *v25; // xmm1_8
  char v26; // [rsp+28h] [rbp-79h]
  char v27; // [rsp+29h] [rbp-78h]
  unsigned __int64 v28; // [rsp+30h] [rbp-71h] BYREF
  unsigned __int64 v29; // [rsp+38h] [rbp-69h] BYREF
  __int128 v30; // [rsp+40h] [rbp-61h] BYREF
  __int64 v31; // [rsp+50h] [rbp-51h]
  const char *v32; // [rsp+58h] [rbp-49h]
  __int128 v33; // [rsp+60h] [rbp-41h] BYREF
  _WORD *v34; // [rsp+70h] [rbp-31h]
  __int64 v35; // [rsp+78h] [rbp-29h]
  _QWORD v36[4]; // [rsp+80h] [rbp-21h] BYREF
  int v37; // [rsp+A0h] [rbp-1h] BYREF

  v35 = a2;
  v37 = 0;
  v4 = a2;
  if ( a2 )
  {
    if ( !a3 )
    {
      v31 = 603;
      *(_QWORD *)&v30 = "onecore\\base\\lstring\\path.cpp";
      *((_QWORD *)&v30 + 1) = "RtlCombineNtPathSegments";
      v32 = "Not-null check failed: PathOut";
      return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
               &v37,
               &v30);
    }
    v6 = 0;
    for ( i = 0; ; i = 1 )
    {
      while ( 1 )
      {
        v29 = 0;
        v28 = 0;
        v8 = (unsigned __int64 *)(v4 + 24 * i);
        v9 = *v8;
        result = RtlTrimNtPathSegment(v8, &v29, &v28);
        if ( (int)result < 0 )
          return result;
        if ( v29 > v9 || v28 > v9 - v29 )
          goto LABEL_47;
        v10 = v9 - v28 - (v29 & -(__int64)(i != 0));
        if ( v10 )
          break;
LABEL_14:
        if ( (unsigned __int64)++i >= 2 )
        {
          v12 = *((_QWORD *)a3 + 1);
          v34 = 0;
          v13 = 0;
          v33 = 0;
          if ( v6 > v12 )
          {
            v15 = RtlAllocateLUnicodeString(v6, &v33);
            if ( v15 < 0 )
              goto LABEL_42;
            v12 = *((_QWORD *)&v33 + 1);
            v14 = v34;
            v13 = v33;
            v27 = 1;
          }
          else
          {
            v14 = (_WORD *)*((_QWORD *)a3 + 2);
            v27 = 0;
          }
          v26 = 1;
          v16 = 0;
          v17 = v14;
          while ( 1 )
          {
            v29 = 0;
            v18 = (unsigned __int64 *)(v4 + 24 * v16);
            v28 = 0;
            v19 = *v18;
            if ( *v18 )
            {
              v20 = RtlTrimNtPathSegment(v18, &v29, &v28);
              if ( v20 < 0 )
                goto LABEL_41;
              v21 = v29;
              if ( v29 > v19 || v28 > v19 - v29 )
                goto LABEL_47;
              if ( v26 )
              {
                v21 = 0;
              }
              else if ( v29 >= 2 )
              {
                v21 = v29 - 2;
              }
              else if ( v17 == v14 || *(v17 - 1) != 92 )
              {
                if ( v12 < 2 )
                {
                  v31 = 694;
                  *(_QWORD *)&v30 = "onecore\\base\\lstring\\path.cpp";
                  v23 = &v30;
                  *((_QWORD *)&v30 + 1) = "RtlCombineNtPathSegments";
                  v32 = "BytesLeft >= sizeof(WCHAR)";
LABEL_40:
                  v20 = Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(
                          &v37,
                          v23,
                          3221225507LL);
LABEL_41:
                  v15 = v20;
LABEL_42:
                  Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v33);
                  return (unsigned int)v15;
                }
                *v17++ = 92;
                v12 -= 2LL;
              }
              v22 = *v18 - v28 - v21;
              if ( v12 < v22 )
              {
                v36[2] = 708;
                v36[0] = "onecore\\base\\lstring\\path.cpp";
                v23 = (__int128 *)v36;
                v36[1] = "RtlCombineNtPathSegments";
                v36[3] = "BytesLeft >= BytesToCopy";
                goto LABEL_40;
              }
              memmove(v17, (const void *)(v21 + v18[2]), *v18 - v28 - v21);
              v17 = (_WORD *)((char *)v17 + v22);
              v26 = 0;
              v12 -= v22;
            }
            if ( (unsigned __int64)++v16 >= 2 )
            {
              if ( v27 )
              {
                v30 = 0;
                v31 = 0;
                Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v30);
                v24 = *((_QWORD *)a3 + 2);
                v30 = *a3;
                v31 = v24;
                v25 = v34;
                *a3 = v13;
                v34 = 0;
                v33 = 0;
                *((_QWORD *)a3 + 2) = v25;
                Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v30);
              }
              if ( v17 >= v14 )
              {
                *(_QWORD *)a3 = (char *)v17 - (char *)v14;
                Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(&v33);
                return 0;
              }
LABEL_47:
              INTERNAL_ERROR_ACTION(-1073741595);
              JUMPOUT(0x1800695E9LL);
            }
            v4 = v35;
          }
        }
      }
      v11 = v10 + v6;
      if ( v10 + v6 < v6 )
        return 3221225621LL;
      if ( i )
      {
        v6 = v11 + 2;
        if ( v11 + 2 < v11 )
          return 3221225621LL;
        goto LABEL_14;
      }
      v6 += v10;
    }
  }
  v31 = 602;
  *(_QWORD *)&v30 = "onecore\\base\\lstring\\path.cpp";
  *((_QWORD *)&v30 + 1) = "RtlCombineNtPathSegments";
  v32 = "(PathSegmentCount == 0) || (PathSegments != 0)";
  return Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(
           &v37,
           &v30);
}

```

## disassembly

```asm
0x180069248  mov     rax, rsp
0x18006924b  mov     [rax+8], rbx
0x18006924f  push    rbp
0x180069250  push    rsi
0x180069251  push    rdi
0x180069252  push    r12
0x180069254  push    r13
0x180069256  push    r14
0x180069258  push    r15
0x18006925a  lea     rbp, [rax-5Fh]
0x18006925e  sub     rsp, 0C0h
0x180069265  movaps  xmmword ptr [rax-48h], xmm6
0x180069269  mov     rax, cs:__security_cookie
0x180069270  xor     rax, rsp
0x180069273  mov     [rbp+57h+var_50], rax
0x180069277  mov     [rbp+57h+var_80], rdx
0x18006927b  mov     r15, r8
0x18006927e  mov     [rbp+57h+var_58], 0
0x180069285  mov     r13, rdx
0x180069288  test    rdx, rdx
0x18006928b  jnz     short loc_1800692F0
0x18006928d  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069294  mov     [rbp+57h+var_A8], 25Ah
0x18006929c  mov     qword ptr [rbp+57h+var_B8], rax
0x1800692a0  lea     rdx, [rbp+57h+var_B8]
0x1800692a4  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x1800692ab  mov     qword ptr [rbp+57h+var_B8+8], rax
0x1800692af  lea     rcx, [rbp+57h+var_58]
0x1800692b3  lea     rax, aPathsegmentcou; "(PathSegmentCount == 0) || (PathSegment"...
0x1800692ba  mov     [rbp+57h+var_A0], rax
0x1800692be  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800692c3  mov     rcx, [rbp+57h+var_50]
0x1800692c7  xor     rcx, rsp; StackCookie
0x1800692ca  call    __security_check_cookie
0x1800692cf  lea     r11, [rsp+0F0h+var_30]
0x1800692d7  mov     rbx, [r11+40h]
0x1800692db  movaps  xmm6, xmmword ptr [r11-10h]
0x1800692e0  mov     rsp, r11
0x1800692e3  pop     r15
0x1800692e5  pop     r14
0x1800692e7  pop     r13
0x1800692e9  pop     r12
0x1800692eb  pop     rdi
0x1800692ec  pop     rsi
0x1800692ed  pop     rbp
0x1800692ee  retn
0x1800692f0  test    r15, r15
0x1800692f3  jnz     short loc_18006932D
0x1800692f5  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800692fc  mov     [rbp+57h+var_A8], 25Bh
0x180069304  mov     qword ptr [rbp+57h+var_B8], rax
0x180069308  lea     rdx, [rbp+57h+var_B8]
0x18006930c  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180069313  mov     qword ptr [rbp+57h+var_B8+8], rax
0x180069317  lea     rcx, [rbp+57h+var_58]
0x18006931b  lea     rax, aNotNullCheckFa_9; "Not-null check failed: PathOut"
0x180069322  mov     [rbp+57h+var_A0], rax
0x180069326  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006932b  jmp     short loc_1800692C3
0x18006932d  xor     edi, edi
0x18006932f  xor     ebx, ebx
0x180069331  lea     rax, [rbx+rbx*2]
0x180069335  mov     [rbp+57h+var_C0], 0
0x18006933d  lea     rcx, ds:0[rax*8]
0x180069345  mov     [rbp+57h+var_C8], 0
0x18006934d  add     rcx, r13
0x180069350  lea     r8, [rbp+57h+var_C8]
0x180069354  lea     rdx, [rbp+57h+var_C0]
0x180069358  mov     rsi, [rcx]
0x18006935b  call    RtlTrimNtPathSegment
0x180069360  test    eax, eax
0x180069362  js      loc_1800692C3
0x180069368  mov     rdx, [rbp+57h+var_C0]
0x18006936c  cmp     rdx, rsi
0x18006936f  ja      loc_1800695DF
0x180069375  mov     rax, rsi
0x180069378  sub     rax, rdx
0x18006937b  cmp     [rbp+57h+var_C8], rax
0x18006937f  ja      loc_1800695DF
0x180069385  mov     rax, rbx
0x180069388  neg     rax
0x18006938b  sbb     rcx, rcx
0x18006938e  sub     rsi, [rbp+57h+var_C8]
0x180069392  and     rcx, rdx
0x180069395  sub     rsi, rcx
0x180069398  jz      short loc_1800693B1
0x18006939a  lea     rax, [rsi+rdi]
0x18006939e  cmp     rax, rdi
0x1800693a1  jb      short loc_1800693E8
0x1800693a3  test    rbx, rbx
0x1800693a6  jz      short loc_1800693DD
0x1800693a8  lea     rdi, [rax+2]
0x1800693ac  cmp     rdi, rax
0x1800693af  jb      short loc_1800693E8
0x1800693b1  inc     rbx
0x1800693b4  cmp     rbx, 2
0x1800693b8  jb      loc_180069331
0x1800693be  mov     rsi, [r15+8]
0x1800693c2  xor     eax, eax
0x1800693c4  mov     [rbp+57h+var_88], rax
0x1800693c8  xorps   xmm6, xmm6
0x1800693cb  movups  [rbp+57h+var_98], xmm6
0x1800693cf  cmp     rdi, rsi
0x1800693d2  ja      short loc_1800693F2
0x1800693d4  mov     r14, [r15+10h]
0x1800693d8  mov     [rbp+57h+var_CF], al
0x1800693db  jmp     short loc_180069418
0x1800693dd  mov     rdi, rax
0x1800693e0  inc     rbx
0x1800693e3  jmp     loc_180069331
0x1800693e8  mov     eax, 0C0000095h
0x1800693ed  jmp     loc_1800692C3
0x1800693f2  lea     rdx, [rbp+57h+var_98]
0x1800693f6  mov     rcx, rdi
0x1800693f9  call    RtlAllocateLUnicodeString
0x1800693fe  mov     ebx, eax
0x180069400  test    eax, eax
0x180069402  js      loc_180069560
0x180069408  mov     rsi, qword ptr [rbp+57h+var_98+8]
0x18006940c  mov     r14, [rbp+57h+var_88]
0x180069410  movups  xmm6, [rbp+57h+var_98]
0x180069414  mov     [rbp+57h+var_CF], 1
0x180069418  mov     [rbp+57h+var_D0], 1
0x18006941c  xor     r12d, r12d
0x18006941f  mov     rbx, r14
0x180069422  lea     rax, [r12+r12*2]
0x180069426  mov     [rbp+57h+var_C0], 0
0x18006942e  lea     r13, [r13+rax*8+0]
0x180069433  mov     [rbp+57h+var_C8], 0
0x18006943b  mov     rdi, [r13+0]
0x18006943f  test    rdi, rdi
0x180069442  jz      loc_1800694DD
0x180069448  lea     r8, [rbp+57h+var_C8]
0x18006944c  mov     rcx, r13
0x18006944f  lea     rdx, [rbp+57h+var_C0]
0x180069453  call    RtlTrimNtPathSegment
0x180069458  test    eax, eax
0x18006945a  js      loc_18006955E
0x180069460  mov     rcx, [rbp+57h+var_C0]
0x180069464  cmp     rcx, rdi
0x180069467  ja      loc_1800695DF
0x18006946d  sub     rdi, rcx
0x180069470  cmp     [rbp+57h+var_C8], rdi
0x180069474  ja      loc_1800695DF
0x18006947a  cmp     [rbp+57h+var_D0], 0
0x18006947e  jz      short loc_180069484
0x180069480  xor     ecx, ecx
0x180069482  jmp     short loc_1800694B1
0x180069484  cmp     rcx, 2
0x180069488  jnb     short loc_1800694AD
0x18006948a  mov     eax, 5Ch ; '\'
0x18006948f  cmp     rbx, r14
0x180069492  jz      short loc_18006949A
0x180069494  cmp     [rbx-2], ax
0x180069498  jz      short loc_1800694B1
0x18006949a  cmp     rsi, 2
0x18006949e  jb      short loc_1800694F3
0x1800694a0  mov     [rbx], ax
0x1800694a3  add     rbx, 2
0x1800694a7  sub     rsi, 2
0x1800694ab  jmp     short loc_1800694B1
0x1800694ad  sub     rcx, 2
0x1800694b1  mov     rdi, [r13+0]
0x1800694b5  sub     rdi, [rbp+57h+var_C8]
0x1800694b9  sub     rdi, rcx
0x1800694bc  cmp     rsi, rdi
0x1800694bf  jb      short loc_180069522
0x1800694c1  mov     rdx, [r13+10h]
0x1800694c5  mov     r8, rdi; Size
0x1800694c8  add     rdx, rcx; Src
0x1800694cb  mov     rcx, rbx; void *
0x1800694ce  call    memmove
0x1800694d3  add     rbx, rdi
0x1800694d6  mov     [rbp+57h+var_D0], 0
0x1800694da  sub     rsi, rdi
0x1800694dd  inc     r12
0x1800694e0  cmp     r12, 2
0x1800694e4  jnb     loc_180069570
0x1800694ea  mov     r13, [rbp+57h+var_80]
0x1800694ee  jmp     loc_180069422
0x1800694f3  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800694fa  mov     [rbp+57h+var_A8], 2B6h
0x180069502  mov     qword ptr [rbp+57h+var_B8], rax
0x180069506  lea     rdx, [rbp+57h+var_B8]
0x18006950a  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180069511  mov     qword ptr [rbp+57h+var_B8+8], rax
0x180069515  lea     rax, aBytesleftSizeo; "BytesLeft >= sizeof(WCHAR)"
0x18006951c  mov     [rbp+57h+var_A0], rax
0x180069520  jmp     short loc_18006954F
0x180069522  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069529  mov     [rbp+57h+var_68], 2C4h
0x180069531  mov     [rbp+57h+var_78], rax
0x180069535  lea     rdx, [rbp+57h+var_78]
0x180069539  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180069540  mov     [rbp+57h+var_70], rax
0x180069544  lea     rax, aBytesleftBytes; "BytesLeft >= BytesToCopy"
0x18006954b  mov     [rbp+57h+var_60], rax
0x18006954f  mov     r8d, 0C0000023h
0x180069555  lea     rcx, [rbp+57h+var_58]
0x180069559  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x18006955e  mov     ebx, eax
0x180069560  lea     rcx, [rbp+57h+var_98]
0x180069564  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180069569  mov     eax, ebx
0x18006956b  jmp     loc_1800692C3
0x180069570  cmp     [rbp+57h+var_CF], 0
0x180069574  jz      short loc_1800695C4
0x180069576  xorps   xmm0, xmm0
0x180069579  lea     rcx, [rbp+57h+var_B8]
0x18006957d  xor     eax, eax
0x18006957f  movups  [rbp+57h+var_B8], xmm0
0x180069583  mov     [rbp+57h+var_A8], rax
0x180069587  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18006958c  movups  xmm0, xmmword ptr [r15]
0x180069590  lea     rcx, [rbp+57h+var_B8]
0x180069594  xor     eax, eax
0x180069596  movsd   xmm1, qword ptr [r15+10h]
0x18006959c  movups  [rbp+57h+var_B8], xmm0
0x1800695a0  movsd   [rbp+57h+var_A8], xmm1
0x1800695a5  xorps   xmm0, xmm0
0x1800695a8  movsd   xmm1, [rbp+57h+var_88]
0x1800695ad  movups  xmmword ptr [r15], xmm6
0x1800695b1  mov     [rbp+57h+var_88], rax
0x1800695b5  movups  [rbp+57h+var_98], xmm0
0x1800695b9  movsd   qword ptr [r15+10h], xmm1
0x1800695bf  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800695c4  cmp     rbx, r14
0x1800695c7  jb      short loc_1800695DF
0x1800695c9  sub     rbx, r14
0x1800695cc  lea     rcx, [rbp+57h+var_98]
0x1800695d0  mov     [r15], rbx
0x1800695d3  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800695d8  xor     eax, eax
0x1800695da  jmp     loc_1800692C3
0x1800695df  mov     ecx, 0C00000E5h; int
0x1800695e4  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
