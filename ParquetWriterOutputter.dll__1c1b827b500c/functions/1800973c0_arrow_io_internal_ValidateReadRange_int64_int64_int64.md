# arrow::io::internal::ValidateReadRange(__int64,__int64,__int64)

- ea: `0x1800973c0`
- end: `0x1800975a2`
- name: `?ValidateReadRange@internal@io@arrow@@YA?AV?$Result@_J@3@_J00@Z`
- size: `482`
- prototype: ``
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops`

## callers

- `0x18009f360`
- `0x18009f7a0`
- `0x1800a08b0`

## callees

- `0x18001f8c0`
- `0x180059010`
- `0x180086fc0`
- `0x180095970`
- `0x1800973c0`
- `0x18009a010`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800974f5`: `Invalid read (offset = `
- `0x18009743c`: `Read out of bounds (offset = `

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall arrow::io::internal::ValidateReadRange(__int64 a1, __int64 a2, __int64 a3, __int64 a4)
{
  __int64 v5; // r8
  __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  void *v8; // rcx
  __int64 v9; // r9
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  void *v13; // rcx
  __int64 v15; // [rsp+40h] [rbp-19h] BYREF
  __int64 v16; // [rsp+48h] [rbp-11h] BYREF
  __int64 v17; // [rsp+50h] [rbp-9h] BYREF
  char v18[8]; // [rsp+58h] [rbp-1h] BYREF
  arrow::Status::State *v19; // [rsp+60h] [rbp+7h]
  __int64 v20; // [rsp+68h] [rbp+Fh]
  _QWORD v21[2]; // [rsp+70h] [rbp+17h] BYREF
  __m128i si128; // [rsp+80h] [rbp+27h]

  v20 = -2;
  v16 = a2;
  v15 = a3;
  v17 = a4;
  if ( a2 < 0 || a3 < 0 )
  {
    v10 = arrow::util::StringBuilder<char const (&)[27],__int64 &,char const (&)[20],__int64,char const (&)[6]>(
            (unsigned int)v21,
            (unsigned int)"Invalid read (offset = ",
            (unsigned int)&v16,
            (unsigned int)", size = ",
            (__int64)&v15,
            (__int64)")");
    LOBYTE(v11) = 4;
    arrow::Status::Status(v18, v11, v10);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v12 = si128.m128i_i64[1] + 1;
      v13 = (void *)v21[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v12 = si128.m128i_i64[1] + 40;
        v13 = *(void **)(v21[0] - 8LL);
        if ( (unsigned __int64)(v21[0] - (_QWORD)v13 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v13, v12);
    }
    goto LABEL_16;
  }
  if ( a2 > a4 )
  {
    v5 = arrow::util::StringBuilder<char const (&)[30],__int64 &,char const (&)[10],__int64 &,char const (&)[19],__int64 &>(
           (unsigned int)v21,
           (unsigned int)"Read out of bounds (offset = ",
           (unsigned int)&v16,
           (unsigned int)", size = ",
           (__int64)&v15,
           (__int64)") in file of size ",
           (__int64)&v17);
    LOBYTE(v6) = 5;
    arrow::Status::Status(v18, v6, v5);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v7 = si128.m128i_i64[1] + 1;
      v8 = (void *)v21[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v7 = si128.m128i_i64[1] + 40;
        v8 = *(void **)(v21[0] - 8LL);
        if ( (unsigned __int64)(v21[0] - (_QWORD)v8 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v8, v7);
    }
LABEL_16:
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v21[0]) = 0;
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a1, v18);
    if ( v19 )
      arrow::Status::State::`scalar deleting destructor'(v19, 1u);
    return a1;
  }
  v9 = a4 - a2;
  *(_QWORD *)(a1 + 8) = 0;
  if ( v9 >= a3 )
    v9 = a3;
  *(_QWORD *)(a1 + 16) = v9;
  return a1;
}

```

## disassembly

```asm
0x1800973c0  push    rbp
0x1800973c2  push    rbx
0x1800973c3  lea     rbp, [rsp-4Fh]
0x1800973c8  sub     rsp, 0A8h
0x1800973cf  mov     [rbp+57h+var_48], 0FFFFFFFFFFFFFFFEh
0x1800973d7  mov     rax, cs:__security_cookie
0x1800973de  xor     rax, rsp
0x1800973e1  mov     [rbp+57h+var_20], rax
0x1800973e5  mov     rbx, rcx
0x1800973e8  mov     [rbp+57h+var_60], rcx
0x1800973ec  mov     [rbp+57h+var_68], rdx
0x1800973f0  mov     [rbp+57h+var_70], r8
0x1800973f4  mov     [rbp+57h+var_60], r9
0x1800973f8  test    rdx, rdx
0x1800973fb  js      loc_1800974D5
0x180097401  test    r8, r8
0x180097404  js      loc_1800974D5
0x18009740a  cmp     rdx, r9
0x18009740d  jle     loc_1800974BA
0x180097413  lea     rax, [rbp+57h+var_60]
0x180097417  mov     [rsp+0B0h+var_80], rax
0x18009741c  lea     rax, aInFileOfSize; ") in file of size "
0x180097423  mov     [rsp+0B0h+var_88], rax
0x180097428  lea     rax, [rbp+57h+var_70]
0x18009742c  mov     [rsp+0B0h+var_90], rax
0x180097431  lea     r9, aSize; ", size = "
0x180097438  lea     r8, [rbp+57h+var_68]
0x18009743c  lea     rdx, aReadOutOfBound; "Read out of bounds (offset = "
0x180097443  lea     rcx, [rbp+57h+var_40]
0x180097447  call    ??$StringBuilder@AEAY0BO@$$CBDAEA_JAEAY09$$CBDAEA_JAEAY0BD@$$CBDAEA_J@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0BO@$$CBDAEA_JAEAY09$$CBD1AEAY0BD@$$CBD1@Z; arrow::util::StringBuilder<char const (&)[30],__int64 &,char const (&)[10],__int64 &,char const (&)[19],__int64 &>(char const (&)[30],__int64 &,char const (&)[10],__int64 &,char const (&)[19],__int64 &)
0x18009744c  nop
0x18009744d  mov     r8, rax
0x180097450  mov     dl, 5
0x180097452  lea     rcx, [rbp+57h+var_58]
0x180097456  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x18009745b  nop
0x18009745c  mov     rdx, [rbp+57h+var_28]
0x180097460  cmp     rdx, 10h
0x180097464  jb      short loc_180097497
0x180097466  inc     rdx
0x180097469  mov     rcx, [rbp+57h+var_40]
0x18009746d  mov     rax, rcx
0x180097470  cmp     rdx, 1000h
0x180097477  jb      short loc_180097492
0x180097479  add     rdx, 27h ; '''; unsigned __int64
0x18009747d  mov     rcx, [rcx-8]; void *
0x180097481  sub     rax, rcx
0x180097484  add     rax, 0FFFFFFFFFFFFFFF8h
0x180097488  cmp     rax, 1Fh
0x18009748c  ja      loc_18009759C
0x180097492  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180097497  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x18009749f  movdqu  xmmword ptr [rbp+27h], xmm0
0x1800974a4  mov     byte ptr [rbp+57h+var_40], 0
0x1800974a8  lea     rdx, [rbp+57h+var_58]
0x1800974ac  mov     rcx, rbx
0x1800974af  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800974b4  nop
0x1800974b5  jmp     loc_18009756A
0x1800974ba  sub     r9, rdx
0x1800974bd  mov     qword ptr [rcx+8], 0
0x1800974c5  cmp     r9, r8
0x1800974c8  cmovge  r9, r8
0x1800974cc  mov     [rcx+10h], r9
0x1800974d0  jmp     loc_18009757D
0x1800974d5  lea     rax, asc_180375DE0; ")"
0x1800974dc  mov     [rsp+0B0h+var_88], rax
0x1800974e1  lea     rax, [rbp+57h+var_70]
0x1800974e5  mov     [rsp+0B0h+var_90], rax
0x1800974ea  lea     r9, aSize; ", size = "
0x1800974f1  lea     r8, [rbp+57h+var_68]
0x1800974f5  lea     rdx, aInvalidReadOff; "Invalid read (offset = "
0x1800974fc  lea     rcx, [rbp+57h+var_40]
0x180097500  call    ??$StringBuilder@AEAY0BL@$$CBDAEA_JAEAY0BE@$$CBD_JAEAY05$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0BL@$$CBDAEA_JAEAY0BE@$$CBD$$QEA_JAEAY05$$CBD@Z; arrow::util::StringBuilder<char const (&)[27],__int64 &,char const (&)[20],__int64,char const (&)[6]>(char const (&)[27],__int64 &,char const (&)[20],__int64 &&,char const (&)[6])
0x180097505  nop
0x180097506  mov     r8, rax
0x180097509  mov     dl, 4
0x18009750b  lea     rcx, [rbp+57h+var_58]
0x18009750f  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x180097514  nop
0x180097515  mov     rdx, [rbp+57h+var_28]
0x180097519  cmp     rdx, 10h
0x18009751d  jb      short loc_18009754C
0x18009751f  inc     rdx
0x180097522  mov     rcx, [rbp+57h+var_40]
0x180097526  mov     rax, rcx
0x180097529  cmp     rdx, 1000h
0x180097530  jb      short loc_180097547
0x180097532  add     rdx, 27h ; '''; unsigned __int64
0x180097536  mov     rcx, [rcx-8]; void *
0x18009753a  sub     rax, rcx
0x18009753d  add     rax, 0FFFFFFFFFFFFFFF8h
0x180097541  cmp     rax, 1Fh
0x180097545  ja      short loc_180097596
0x180097547  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009754c  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180097554  movdqu  xmmword ptr [rbp+27h], xmm0
0x180097559  mov     byte ptr [rbp+57h+var_40], 0
0x18009755d  lea     rdx, [rbp+57h+var_58]
0x180097561  mov     rcx, rbx
0x180097564  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x180097569  nop
0x18009756a  mov     rcx, [rbp+57h+var_50]; this
0x18009756e  test    rcx, rcx
0x180097571  jz      short loc_18009757D
0x180097573  mov     edx, 1; unsigned int
0x180097578  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x18009757d  mov     rax, rbx
0x180097580  mov     rcx, [rbp+57h+var_20]
0x180097584  xor     rcx, rsp; StackCookie
0x180097587  call    __security_check_cookie
0x18009758c  add     rsp, 0A8h
0x180097593  pop     rbx
0x180097594  pop     rbp
0x180097595  retn
0x180097596  call    _invalid_parameter_noinfo_noreturn
0x18009759c  call    _invalid_parameter_noinfo_noreturn
```
