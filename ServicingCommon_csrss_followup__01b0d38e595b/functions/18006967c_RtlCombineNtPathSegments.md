# RtlCombineNtPathSegments

- ea: `0x18006967c`
- end: `0x180069a25`
- name: `RtlCombineNtPathSegments`
- size: `937`
- prototype: ``
- caller_count: `5`
- callee_count: `8`
- tags: `reparse_path, loader_planting, broker_com_uri`

## callers

- `0x1800431a8`
- `0x180043680`
- `0x180043db8`
- `0x180074910`
- `0x18008bc50`

## callees

- `0x180004a8c`
- `0x180019ea0`
- `0x18001f1d8`
- `0x18001f840`
- `0x18002d2b0`
- `0x18006967c`
- `0x18006a620`
- `0x1800981e0`

## import_xrefs

- `ntdll!RtlRaiseStatus` at `0x180069a18`
- `ntdll!RtlRaiseStatus` at `0x180069a18`

## string_xrefs

- `0x1800696c1`: `onecore\base\lstring\path.cpp`
- `0x180069729`: `onecore\base\lstring\path.cpp`
- `0x180069927`: `onecore\base\lstring\path.cpp`
- `0x180069956`: `onecore\base\lstring\path.cpp`
- `0x18006974f`: `Not-null check failed: PathOut`
- `0x1800696d8`: `RtlCombineNtPathSegments`
- `0x180069740`: `RtlCombineNtPathSegments`
- `0x18006993e`: `RtlCombineNtPathSegments`
- `0x18006996d`: `RtlCombineNtPathSegments`
- `0x1800696e7`: `(PathSegmentCount == 0) || (PathSegments != 0)`
- `0x180069978`: `BytesLeft >= BytesToCopy`

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
              RtlRaiseStatus(-1073741595);
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
0x18006967c  mov     rax, rsp
0x18006967f  mov     [rax+8], rbx
0x180069683  push    rbp
0x180069684  push    rsi
0x180069685  push    rdi
0x180069686  push    r12
0x180069688  push    r13
0x18006968a  push    r14
0x18006968c  push    r15
0x18006968e  lea     rbp, [rax-5Fh]
0x180069692  sub     rsp, 0C0h
0x180069699  movaps  xmmword ptr [rax-48h], xmm6
0x18006969d  mov     rax, cs:__security_cookie
0x1800696a4  xor     rax, rsp
0x1800696a7  mov     [rbp+57h+var_50], rax
0x1800696ab  mov     [rbp+57h+var_80], rdx
0x1800696af  mov     r15, r8
0x1800696b2  mov     [rbp+57h+var_58], 0
0x1800696b9  mov     r13, rdx
0x1800696bc  test    rdx, rdx
0x1800696bf  jnz     short loc_180069724
0x1800696c1  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x1800696c8  mov     [rbp+57h+var_A8], 25Ah
0x1800696d0  mov     qword ptr [rbp+57h+var_B8], rax
0x1800696d4  lea     rdx, [rbp+57h+var_B8]
0x1800696d8  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x1800696df  mov     qword ptr [rbp+57h+var_B8+8], rax
0x1800696e3  lea     rcx, [rbp+57h+var_58]
0x1800696e7  lea     rax, aPathsegmentcou; "(PathSegmentCount == 0) || (PathSegment"...
0x1800696ee  mov     [rbp+57h+var_A0], rax
0x1800696f2  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x1800696f7  mov     rcx, [rbp+57h+var_50]
0x1800696fb  xor     rcx, rsp; StackCookie
0x1800696fe  call    __security_check_cookie
0x180069703  lea     r11, [rsp+0F0h+var_30]
0x18006970b  mov     rbx, [r11+40h]
0x18006970f  movaps  xmm6, xmmword ptr [r11-10h]
0x180069714  mov     rsp, r11
0x180069717  pop     r15
0x180069719  pop     r14
0x18006971b  pop     r13
0x18006971d  pop     r12
0x18006971f  pop     rdi
0x180069720  pop     rsi
0x180069721  pop     rbp
0x180069722  retn
0x180069724  test    r15, r15
0x180069727  jnz     short loc_180069761
0x180069729  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x180069730  mov     [rbp+57h+var_A8], 25Bh
0x180069738  mov     qword ptr [rbp+57h+var_B8], rax
0x18006973c  lea     rdx, [rbp+57h+var_B8]
0x180069740  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180069747  mov     qword ptr [rbp+57h+var_B8+8], rax
0x18006974b  lea     rcx, [rbp+57h+var_58]
0x18006974f  lea     rax, aNotNullCheckFa_9; "Not-null check failed: PathOut"
0x180069756  mov     [rbp+57h+var_A0], rax
0x18006975a  call    ?OriginateInvalidParameter_NullPointer@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateInvalidParameter_NullPointer(Windows::ErrorHandling::_RTL_CALL_SITE const &)
0x18006975f  jmp     short loc_1800696F7
0x180069761  xor     edi, edi
0x180069763  xor     ebx, ebx
0x180069765  lea     rax, [rbx+rbx*2]
0x180069769  mov     [rbp+57h+var_C0], 0
0x180069771  lea     rcx, ds:0[rax*8]
0x180069779  mov     [rbp+57h+var_C8], 0
0x180069781  add     rcx, r13
0x180069784  lea     r8, [rbp+57h+var_C8]
0x180069788  lea     rdx, [rbp+57h+var_C0]
0x18006978c  mov     rsi, [rcx]
0x18006978f  call    RtlTrimNtPathSegment
0x180069794  test    eax, eax
0x180069796  js      loc_1800696F7
0x18006979c  mov     rdx, [rbp+57h+var_C0]
0x1800697a0  cmp     rdx, rsi
0x1800697a3  ja      loc_180069A13
0x1800697a9  mov     rax, rsi
0x1800697ac  sub     rax, rdx
0x1800697af  cmp     [rbp+57h+var_C8], rax
0x1800697b3  ja      loc_180069A13
0x1800697b9  mov     rax, rbx
0x1800697bc  neg     rax
0x1800697bf  sbb     rcx, rcx
0x1800697c2  sub     rsi, [rbp+57h+var_C8]
0x1800697c6  and     rcx, rdx
0x1800697c9  sub     rsi, rcx
0x1800697cc  jz      short loc_1800697E5
0x1800697ce  lea     rax, [rsi+rdi]
0x1800697d2  cmp     rax, rdi
0x1800697d5  jb      short loc_18006981C
0x1800697d7  test    rbx, rbx
0x1800697da  jz      short loc_180069811
0x1800697dc  lea     rdi, [rax+2]
0x1800697e0  cmp     rdi, rax
0x1800697e3  jb      short loc_18006981C
0x1800697e5  inc     rbx
0x1800697e8  cmp     rbx, 2
0x1800697ec  jb      loc_180069765
0x1800697f2  mov     rsi, [r15+8]
0x1800697f6  xor     eax, eax
0x1800697f8  mov     [rbp+57h+var_88], rax
0x1800697fc  xorps   xmm6, xmm6
0x1800697ff  movups  [rbp+57h+var_98], xmm6
0x180069803  cmp     rdi, rsi
0x180069806  ja      short loc_180069826
0x180069808  mov     r14, [r15+10h]
0x18006980c  mov     [rbp+57h+var_CF], al
0x18006980f  jmp     short loc_18006984C
0x180069811  mov     rdi, rax
0x180069814  inc     rbx
0x180069817  jmp     loc_180069765
0x18006981c  mov     eax, 0C0000095h
0x180069821  jmp     loc_1800696F7
0x180069826  lea     rdx, [rbp+57h+var_98]
0x18006982a  mov     rcx, rdi
0x18006982d  call    RtlAllocateLUnicodeString
0x180069832  mov     ebx, eax
0x180069834  test    eax, eax
0x180069836  js      loc_180069994
0x18006983c  mov     rsi, qword ptr [rbp+57h+var_98+8]
0x180069840  mov     r14, [rbp+57h+var_88]
0x180069844  movups  xmm6, [rbp+57h+var_98]
0x180069848  mov     [rbp+57h+var_CF], 1
0x18006984c  mov     [rbp+57h+var_D0], 1
0x180069850  xor     r12d, r12d
0x180069853  mov     rbx, r14
0x180069856  lea     rax, [r12+r12*2]
0x18006985a  mov     [rbp+57h+var_C0], 0
0x180069862  lea     r13, [r13+rax*8+0]
0x180069867  mov     [rbp+57h+var_C8], 0
0x18006986f  mov     rdi, [r13+0]
0x180069873  test    rdi, rdi
0x180069876  jz      loc_180069911
0x18006987c  lea     r8, [rbp+57h+var_C8]
0x180069880  mov     rcx, r13
0x180069883  lea     rdx, [rbp+57h+var_C0]
0x180069887  call    RtlTrimNtPathSegment
0x18006988c  test    eax, eax
0x18006988e  js      loc_180069992
0x180069894  mov     rcx, [rbp+57h+var_C0]
0x180069898  cmp     rcx, rdi
0x18006989b  ja      loc_180069A13
0x1800698a1  sub     rdi, rcx
0x1800698a4  cmp     [rbp+57h+var_C8], rdi
0x1800698a8  ja      loc_180069A13
0x1800698ae  cmp     [rbp+57h+var_D0], 0
0x1800698b2  jz      short loc_1800698B8
0x1800698b4  xor     ecx, ecx
0x1800698b6  jmp     short loc_1800698E5
0x1800698b8  cmp     rcx, 2
0x1800698bc  jnb     short loc_1800698E1
0x1800698be  mov     eax, 5Ch ; '\'
0x1800698c3  cmp     rbx, r14
0x1800698c6  jz      short loc_1800698CE
0x1800698c8  cmp     [rbx-2], ax
0x1800698cc  jz      short loc_1800698E5
0x1800698ce  cmp     rsi, 2
0x1800698d2  jb      short loc_180069927
0x1800698d4  mov     [rbx], ax
0x1800698d7  add     rbx, 2
0x1800698db  sub     rsi, 2
0x1800698df  jmp     short loc_1800698E5
0x1800698e1  sub     rcx, 2
0x1800698e5  mov     rdi, [r13+0]
0x1800698e9  sub     rdi, [rbp+57h+var_C8]
0x1800698ed  sub     rdi, rcx
0x1800698f0  cmp     rsi, rdi
0x1800698f3  jb      short loc_180069956
0x1800698f5  mov     rdx, [r13+10h]
0x1800698f9  mov     r8, rdi; Size
0x1800698fc  add     rdx, rcx; Src
0x1800698ff  mov     rcx, rbx; void *
0x180069902  call    memmove
0x180069907  add     rbx, rdi
0x18006990a  mov     [rbp+57h+var_D0], 0
0x18006990e  sub     rsi, rdi
0x180069911  inc     r12
0x180069914  cmp     r12, 2
0x180069918  jnb     loc_1800699A4
0x18006991e  mov     r13, [rbp+57h+var_80]
0x180069922  jmp     loc_180069856
0x180069927  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006992e  mov     [rbp+57h+var_A8], 2B6h
0x180069936  mov     qword ptr [rbp+57h+var_B8], rax
0x18006993a  lea     rdx, [rbp+57h+var_B8]
0x18006993e  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180069945  mov     qword ptr [rbp+57h+var_B8+8], rax
0x180069949  lea     rax, aBytesleftSizeo; "BytesLeft >= sizeof(WCHAR)"
0x180069950  mov     [rbp+57h+var_A0], rax
0x180069954  jmp     short loc_180069983
0x180069956  lea     rax, aOnecoreBaseLst; "onecore\\base\\lstring\\path.cpp"
0x18006995d  mov     [rbp+57h+var_68], 2C4h
0x180069965  mov     [rbp+57h+var_78], rax
0x180069969  lea     rdx, [rbp+57h+var_78]
0x18006996d  lea     rax, aRtlcombinentpa; "RtlCombineNtPathSegments"
0x180069974  mov     [rbp+57h+var_70], rax
0x180069978  lea     rax, aBytesleftBytes; "BytesLeft >= BytesToCopy"
0x18006997f  mov     [rbp+57h+var_60], rax
0x180069983  mov     r8d, 0C0000023h
0x180069989  lea     rcx, [rbp+57h+var_58]
0x18006998d  call    ?OriginateNtStatus@?$CBaseFrame@UCSimpleNtStatusCarryingFrame@Rtl@ErrorHandling@Windows@@J@Rtl@ErrorHandling@Windows@@QEAAJAEBU_RTL_CALL_SITE@34@J@Z; Windows::ErrorHandling::Rtl::CBaseFrame<Windows::ErrorHandling::Rtl::CSimpleNtStatusCarryingFrame,long>::OriginateNtStatus(Windows::ErrorHandling::_RTL_CALL_SITE const &,long)
0x180069992  mov     ebx, eax
0x180069994  lea     rcx, [rbp+57h+var_98]
0x180069998  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x18006999d  mov     eax, ebx
0x18006999f  jmp     loc_1800696F7
0x1800699a4  cmp     [rbp+57h+var_CF], 0
0x1800699a8  jz      short loc_1800699F8
0x1800699aa  xorps   xmm0, xmm0
0x1800699ad  lea     rcx, [rbp+57h+var_B8]
0x1800699b1  xor     eax, eax
0x1800699b3  movups  [rbp+57h+var_B8], xmm0
0x1800699b7  mov     [rbp+57h+var_A8], rax
0x1800699bb  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800699c0  movups  xmm0, xmmword ptr [r15]
0x1800699c4  lea     rcx, [rbp+57h+var_B8]
0x1800699c8  xor     eax, eax
0x1800699ca  movsd   xmm1, qword ptr [r15+10h]
0x1800699d0  movups  [rbp+57h+var_B8], xmm0
0x1800699d4  movsd   [rbp+57h+var_A8], xmm1
0x1800699d9  xorps   xmm0, xmm0
0x1800699dc  movsd   xmm1, [rbp+57h+var_88]
0x1800699e1  movups  xmmword ptr [r15], xmm6
0x1800699e5  mov     [rbp+57h+var_88], rax
0x1800699e9  movups  [rbp+57h+var_98], xmm0
0x1800699ed  movsd   qword ptr [r15+10h], xmm1
0x1800699f3  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x1800699f8  cmp     rbx, r14
0x1800699fb  jb      short loc_180069A13
0x1800699fd  sub     rbx, r14
0x180069a00  lea     rcx, [rbp+57h+var_98]
0x180069a04  mov     [r15], rbx
0x180069a07  call    ?Close@?$AutoString@U_LUTF8_STRING@@V?$Auto@U_LUTF8_STRING@@@Windows@@@Rtl@Windows@@QEAAXXZ; Windows::Rtl::AutoString<_LUTF8_STRING,Windows::Auto<_LUTF8_STRING>>::Close(void)
0x180069a0c  xor     eax, eax
0x180069a0e  jmp     loc_1800696F7
0x180069a13  mov     ecx, 0C00000E5h; Status
0x180069a18  call    cs:__imp_RtlRaiseStatus
0x180069a1f  nop     dword ptr [rax+rax+00h]
0x180069a24  int     3; Trap to Debugger
```
