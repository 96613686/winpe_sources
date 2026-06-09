# win_musl::consumption::readExtras<uchar const *>(win_musl::ZipFileLocal *,uchar const *,uchar const *,uint *)

- ea: `0x180024108`
- end: `0x1800243bb`
- name: `??$readExtras@PEBE@consumption@win_musl@@YAXPEAVZipFileLocal@1@PEBE1PEAI@Z`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x18008c920`

## callees

- `0x1800079d8`
- `0x180022f9c`
- `0x180024108`
- `0x180025528`
- `0x1800517a0`
- `0x18008e058`
- `0x18008e2fc`
- `0x18008e328`
- `0x180090838`
- `0x1800cd38c`
- `0x180117740`

## string_xrefs

- `0x1800241f9`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x180024233`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x18002434e`: `onecore\internal\printscan\inc\private\lib\external\win7.zipio\ZipModelReaders.inl`
- `0x1800241e8`: `win_musl::consumption::readExtras`
- `0x180024228`: `win_musl::consumption::readExtras`
- `0x18002433f`: `win_musl::consumption::readExtras`

## pseudocode

```c
__int64 __fastcall win_musl::consumption::readExtras<unsigned char const *>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        _DWORD *a4)
{
  __int64 v6; // rcx
  _BYTE *v9; // rdx
  unsigned __int64 v10; // rdx
  _QWORD *v11; // r8
  unsigned __int64 v12; // rax
  unsigned __int64 v13; // rcx
  __int64 result; // rax
  __int16 Then; // bx
  unsigned __int16 v16; // ax
  __int64 v17; // r12
  unsigned __int64 v18; // rsi
  unsigned __int64 v19; // rax
  __int64 v20; // rbx
  __int64 v21; // rax
  unsigned __int64 v22; // rax
  __int64 v23; // r8
  __int64 v24; // r9
  unsigned __int64 v25; // rdx
  __int128 v26; // [rsp+40h] [rbp-C0h] BYREF
  __int16 v27; // [rsp+50h] [rbp-B0h] BYREF
  int v28; // [rsp+52h] [rbp-AEh]
  __int16 v29; // [rsp+56h] [rbp-AAh]
  int v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+5Ch] [rbp-A4h]
  __int64 v32; // [rsp+60h] [rbp-A0h]
  _DWORD v33[2]; // [rsp+70h] [rbp-90h] BYREF
  __int64 v34; // [rsp+78h] [rbp-88h]
  __int128 v35; // [rsp+80h] [rbp-80h] BYREF
  _BYTE pExceptionObject[160]; // [rsp+90h] [rbp-70h] BYREF

  v6 = (__int64)(a1 + 7);
  v9 = *(_BYTE **)(v6 + 8);
  if ( v9 != *(_BYTE **)(v6 + 16) )
    *(_QWORD *)(v6 + 16) = v9;
  std::vector<unsigned char>::_Insert<unsigned char const *>(v6, v9, a2, a3);
  v10 = a1[8];
  v11 = a1 + 9;
  if ( v10 )
    v12 = *v11 - v10;
  else
    LODWORD(v12) = 0;
  v26 = (unsigned int)v12;
  v13 = 0;
  if ( v10 && *v11 != v10 )
  {
    *((_QWORD *)&v26 + 1) = v10;
    v13 = v10;
  }
  for ( result = (unsigned int)v26; ; *(_QWORD *)&v26 = (unsigned int)result )
  {
    *((_QWORD *)&v26 + 1) = v13;
    if ( !(_DWORD)result || !v13 )
      break;
    v35 = v26;
    Then = win_musl::detail::readThenLog<unsigned short>(
             (unsigned int)"onecore\\internal\\printscan\\inc\\private\\lib\\external\\win7.zipio\\ZipModelReaders.inl",
             65,
             (unsigned int)"win_musl::consumption::readExtras",
             (unsigned int)"type",
             (__int64)&v35,
             (__int64)&v26);
    v35 = v26;
    v16 = win_musl::detail::readThenLog<unsigned short>(
            (unsigned int)"onecore\\internal\\printscan\\inc\\private\\lib\\external\\win7.zipio\\ZipModelReaders.inl",
            69,
            (unsigned int)"win_musl::consumption::readExtras",
            (unsigned int)"size",
            (__int64)&v35,
            (__int64)&v26);
    v17 = v16;
    if ( v16 > (unsigned int)v26 )
    {
      win_musl::detail::ThrowBuilder<SplException::THResultException>(
        (SplException::TSystemException *)pExceptionObject,
        0x4Cu,
        0x80511002,
        (struct win_musl::TStringEllipseBase *)L"Unexpected size of extra field. Archive may be corrupted.");
      throw (SplException::THResultException *)pExceptionObject;
    }
    v18 = *((_QWORD *)&v26 + 1);
    v29 = 0;
    v31 = DWORD1(v26);
    v28 = 0;
    v27 = Then;
    v32 = *((_QWORD *)&v26 + 1);
    v30 = v16;
    if ( Then == 1 )
    {
      v33[0] = v16;
      v33[1] = DWORD1(v26);
      v34 = *((_QWORD *)&v26 + 1);
      win_musl::consumption::readZip64Extra(
        a1,
        (const struct __MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0008 *)v33,
        a4);
    }
    else
    {
      v20 = a1[13];
      v21 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(a1 + 11);
      v22 = std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::capacity(a1 + 11, v21);
      if ( v25 >= v22 )
      {
        std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::_Insert_n(a1 + 11, v20, v23, &v27);
      }
      else
      {
        std::_Uninit_fill_n<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,unsigned __int64,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>>(
          v20,
          v24,
          &v27);
        a1[13] = v20 + 24;
      }
    }
    if ( (_DWORD)v26 && v18 && (v13 = v18 + v17, v19 = v18 + (unsigned int)v26, v19 != v18 + v17) )
    {
      if ( v18 > v13 || v13 > v19 )
      {
        win_musl::detail::ThrowBuilder<SplException::THResultException>(
          (SplException::TSystemException *)pExceptionObject,
          0x65u,
          0x80070057,
          (struct win_musl::TStringEllipseBase *)L"new_begin is out-of-range: vector expression (extraCursor), new_begin e"
                                                  "xpression (dd::vector_begin(extraCursor) + size)");
        throw (SplException::THResultException *)pExceptionObject;
      }
      result = (unsigned int)(v19 - v13);
    }
    else
    {
      result = 0;
      v13 = 0;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180024108  push    rbp
0x18002410a  push    rbx
0x18002410b  push    rsi
0x18002410c  push    rdi
0x18002410d  push    r12
0x18002410f  push    r13
0x180024111  push    r14
0x180024113  lea     rbp, [rsp-40h]
0x180024118  sub     rsp, 140h
0x18002411f  mov     rax, cs:__security_cookie
0x180024126  xor     rax, rsp
0x180024129  mov     [rbp+70h+var_40], rax
0x18002412d  mov     r14, rcx
0x180024130  mov     r13, r9
0x180024133  add     rcx, 38h ; '8'
0x180024137  mov     r9, r8
0x18002413a  mov     r8, rdx
0x18002413d  mov     rdx, [rcx+8]
0x180024141  cmp     rdx, [rcx+10h]
0x180024145  jz      short loc_18002414B
0x180024147  mov     [rcx+10h], rdx
0x18002414b  call    ??$_Insert@PEBE@?$vector@EV?$allocator@E@std@@@std@@QEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@1@PEBE1Uforward_iterator_tag@1@@Z; std::vector<uchar>::_Insert<uchar const *>(std::_Vector_iterator<uchar>,uchar const *,uchar const *,std::forward_iterator_tag)
0x180024150  mov     rdx, [r14+40h]
0x180024154  lea     rdi, [r14+58h]
0x180024158  lea     r8, [r14+48h]
0x18002415c  test    rdx, rdx
0x18002415f  jz      short loc_1800241C5
0x180024161  mov     rax, [r8]
0x180024164  sub     rax, rdx
0x180024167  mov     dword ptr [rsp+170h+var_130], eax
0x18002416b  xor     ecx, ecx
0x18002416d  xor     eax, eax
0x18002416f  mov     dword ptr [rsp+170h+var_130+4], eax
0x180024173  mov     qword ptr [rsp+170h+var_130+8], rax
0x180024178  test    rdx, rdx
0x18002417b  jz      short loc_18002418A
0x18002417d  cmp     [r8], rdx
0x180024180  jz      short loc_18002418A
0x180024182  mov     qword ptr [rsp+170h+var_130+8], rdx
0x180024187  mov     rcx, rdx
0x18002418a  movaps  xmm0, [rsp+170h+var_130]
0x18002418f  movdqa  [rsp+170h+var_130], xmm0
0x180024195  mov     eax, dword ptr [rsp+170h+var_130]
0x180024199  mov     qword ptr [rsp+170h+var_130+8], rcx
0x18002419e  test    eax, eax
0x1800241a0  jz      short loc_1800241A7
0x1800241a2  test    rcx, rcx
0x1800241a5  jnz     short loc_1800241C9
0x1800241a7  mov     rcx, [rbp+70h+var_40]
0x1800241ab  xor     rcx, rsp; StackCookie
0x1800241ae  call    __security_check_cookie
0x1800241b3  add     rsp, 140h
0x1800241ba  pop     r14
0x1800241bc  pop     r13
0x1800241be  pop     r12
0x1800241c0  pop     rdi
0x1800241c1  pop     rsi
0x1800241c2  pop     rbx
0x1800241c3  pop     rbp
0x1800241c4  retn
0x1800241c5  xor     eax, eax
0x1800241c7  jmp     short loc_180024167
0x1800241c9  movaps  xmm0, [rsp+170h+var_130]
0x1800241ce  lea     rax, [rsp+170h+var_130]
0x1800241d3  mov     qword ptr [rsp+170h+var_148], rax
0x1800241d8  lea     r9, aType_1; "type"
0x1800241df  lea     rax, [rbp+70h+var_F0]
0x1800241e3  movdqa  [rbp+70h+var_F0], xmm0
0x1800241e8  lea     r8, aWinMuslConsump_6; "win_musl::consumption::readExtras"
0x1800241ef  mov     qword ptr [rsp+170h+var_150], rax
0x1800241f4  mov     edx, 41h ; 'A'
0x1800241f9  lea     rcx, aOnecoreInterna_1; "onecore\\internal\\printscan\\inc\\priv"...
0x180024200  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180024205  movaps  xmm0, [rsp+170h+var_130]
0x18002420a  lea     r9, aSize_1; "size"
0x180024211  movzx   ebx, ax
0x180024214  movdqa  [rbp+70h+var_F0], xmm0
0x180024219  lea     rax, [rsp+170h+var_130]
0x18002421e  mov     edx, 45h ; 'E'
0x180024223  mov     qword ptr [rsp+170h+var_148], rax
0x180024228  lea     r8, aWinMuslConsump_6; "win_musl::consumption::readExtras"
0x18002422f  lea     rax, [rbp+70h+var_F0]
0x180024233  lea     rcx, aOnecoreInterna_1; "onecore\\internal\\printscan\\inc\\priv"...
0x18002423a  mov     qword ptr [rsp+170h+var_150], rax
0x18002423f  call    ??$readThenLog@G@detail@win_musl@@YAGPEBDK00U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAU2@@Z; win_musl::detail::readThenLog<ushort>(char const *,ulong,char const *,char const *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001 *)
0x180024244  movzx   r12d, ax
0x180024248  mov     edx, r12d
0x18002424b  cmp     r12d, dword ptr [rsp+170h+var_130]
0x180024250  ja      loc_180024377
0x180024256  mov     rsi, qword ptr [rsp+170h+var_130+8]
0x18002425b  xor     ecx, ecx
0x18002425d  mov     r9d, 1
0x180024263  mov     [rsp+170h+var_11A], cx
0x180024268  mov     ecx, dword ptr [rsp+170h+var_130+4]
0x18002426c  mov     [rsp+170h+var_114], ecx
0x180024270  mov     [rsp+170h+var_11E], 0
0x180024278  mov     [rsp+170h+var_120], bx
0x18002427d  mov     [rsp+170h+var_110], rsi
0x180024282  mov     [rsp+170h+var_118], edx
0x180024286  cmp     r9w, bx
0x18002428a  jnz     short loc_1800242E0
0x18002428c  mov     [rsp+170h+var_100], edx
0x180024290  mov     r8, r13
0x180024293  mov     [rsp+170h+var_FC], ecx
0x180024297  lea     rdx, [rsp+170h+var_100]
0x18002429c  mov     rcx, r14
0x18002429f  mov     [rsp+170h+var_F8], rsi
0x1800242a4  call    ?readZip64Extra@consumption@win_musl@@YAXPEAVZipFileLocal@2@U__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001@@PEAI@Z; win_musl::consumption::readZip64Extra(win_musl::ZipFileLocal *,__MIDL___MIDL_itf_dox2Ecommon_0000_0000_0001,uint *)
0x1800242a9  cmp     dword ptr [rsp+170h+var_130], 0
0x1800242ae  jz      short loc_180024316
0x1800242b0  test    rsi, rsi
0x1800242b3  jz      short loc_180024316
0x1800242b5  mov     eax, dword ptr [rsp+170h+var_130]
0x1800242b9  lea     rcx, [rsi+r12]
0x1800242bd  add     rax, rsi
0x1800242c0  cmp     rax, rcx
0x1800242c3  jz      short loc_180024316
0x1800242c5  cmp     rsi, rcx
0x1800242c8  ja      short loc_180024333
0x1800242ca  cmp     rcx, rax
0x1800242cd  ja      short loc_180024333
0x1800242cf  sub     eax, ecx
0x1800242d1  xor     edx, edx
0x1800242d3  mov     dword ptr [rsp+170h+var_130], eax
0x1800242d7  mov     dword ptr [rsp+170h+var_130+4], edx
0x1800242db  jmp     loc_180024199
0x1800242e0  mov     rbx, [rdi+10h]
0x1800242e4  mov     rcx, rdi
0x1800242e7  call    ?size@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::size(void)
0x1800242ec  mov     rcx, rdi
0x1800242ef  mov     rdx, rax
0x1800242f2  call    ?capacity@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@QEBA_KXZ; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::capacity(void)
0x1800242f7  cmp     rdx, rax
0x1800242fa  jnb     short loc_18002431E
0x1800242fc  lea     r8, [rsp+170h+var_120]
0x180024301  mov     rdx, r9
0x180024304  mov     rcx, rbx
0x180024307  call    ??$_Uninit_fill_n@PEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@_KU1@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@YAXPEAU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@_KAEBU1@AEAV?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@0@U_Nonscalar_ptr_iterator_tag@0@U_Range_checked_iterator_tag@0@@Z; std::_Uninit_fill_n<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,unsigned __int64,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>>(__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 *,unsigned __int64,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 const &,std::allocator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001> &,std::_Nonscalar_ptr_iterator_tag,std::_Range_checked_iterator_tag)
0x18002430c  add     rbx, 18h
0x180024310  mov     [rdi+10h], rbx
0x180024314  jmp     short loc_1800242A9
0x180024316  xor     eax, eax
0x180024318  xor     edx, edx
0x18002431a  xor     ecx, ecx
0x18002431c  jmp     short loc_1800242D3
0x18002431e  lea     r9, [rsp+170h+var_120]
0x180024323  mov     rdx, rbx
0x180024326  mov     rcx, rdi
0x180024329  call    ?_Insert_n@?$vector@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@std@@IEAAXV?$_Vector_iterator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@V?$allocator@U__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@std@@@2@_KAEBU__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001@@@Z; std::vector<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>::_Insert_n(std::_Vector_iterator<__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001>,unsigned __int64,__MIDL___MIDL_itf_win72Ezip2Ebase_0000_0000_0001 const &)
0x18002432e  jmp     loc_1800242A9
0x180024333  lea     rax, aNewBeginIsOutO_1; "new_begin is out-of-range: vector expre"...
0x18002433a  mov     [rsp+170h+var_140], rax; struct win_musl::TStringEllipseBase *
0x18002433f  lea     r9, aWinMuslConsump_6; "win_musl::consumption::readExtras"
0x180024346  mov     [rsp+170h+var_148], 80070057h; unsigned int
0x18002434e  lea     r8, aOnecoreInterna_1; "onecore\\internal\\printscan\\inc\\priv"...
0x180024355  lea     rcx, [rbp+70h+pExceptionObject]; this
0x180024359  mov     [rsp+170h+var_150], 65h ; 'e'; unsigned int
0x180024361  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x180024366  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x18002436d  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x180024371  call    _CxxThrowException_0
0x180024377  lea     rax, aUnexpectedSize; "Unexpected size of extra field. Archive"...
0x18002437e  mov     [rsp+170h+var_140], rax; struct win_musl::TStringEllipseBase *
0x180024383  lea     r9, word_18013A0B6
0x18002438a  mov     [rsp+170h+var_148], 80511002h; unsigned int
0x180024392  lea     r8, aNoFilename; "(no filename)"
0x180024399  lea     rcx, [rbp+70h+pExceptionObject]; this
0x18002439d  mov     [rsp+170h+var_150], 4Ch ; 'L'; unsigned int
0x1800243a5  call    ??$ThrowBuilder@VTHResultException@SplException@@@detail@win_musl@@YA?AVTHResultException@SplException@@P6AXPEBD0IW4LOG_CATEGORY@1@JPEB_W@Z00IJ2@Z; win_musl::detail::ThrowBuilder<SplException::THResultException>(void (*)(char const *,char const *,uint,win_musl::LOG_CATEGORY,long,wchar_t const *),char const *,char const *,uint,long,wchar_t const *)
0x1800243aa  lea     rdx, _TI3?AVTHResultException@SplException@@; pThrowInfo
0x1800243b1  lea     rcx, [rbp+70h+pExceptionObject]; pExceptionObject
0x1800243b5  call    _CxxThrowException_0
```
