# arrow::util::internal::_anonymous_namespace_::SnappyCodec::Decompress

- ea: `0x1800e1ca0`
- end: `0x1800e1efb`
- name: `arrow::util::internal::_anonymous_namespace_::SnappyCodec::Decompress`
- size: `603`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x1800e1a70`
- `0x1800e1ca0`
- `0x18029f6e0`
- `0x18029f9e0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800e1cef`: `Corrupt snappy compressed data.`
- `0x1800e1e42`: `Corrupt snappy compressed data.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
unsigned __int64 __fastcall arrow::util::internal::_anonymous_namespace_::SnappyCodec::Decompress(
        __int64 a1,
        unsigned __int64 a2,
        const char *a3,
        snappy *a4,
        signed __int64 a5,
        unsigned __int64 a6)
{
  unsigned __int64 v9; // r14
  char *v10; // r9
  __int64 v11; // rax
  __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  void *v14; // rcx
  __int64 v15; // r8
  __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  void *v18; // rcx
  __int64 v19; // rax
  __int64 v20; // rdx
  unsigned __int64 v21; // rdx
  void *v22; // rcx
  unsigned __int64 v24; // [rsp+30h] [rbp-50h] BYREF
  _BYTE v25[8]; // [rsp+38h] [rbp-48h] BYREF
  arrow::Status::State *v26; // [rsp+40h] [rbp-40h]
  __int64 v27; // [rsp+48h] [rbp-38h]
  _QWORD v28[2]; // [rsp+50h] [rbp-30h] BYREF
  __m128i si128; // [rsp+60h] [rbp-20h]

  v27 = -2;
  v24 = a2;
  v9 = a6;
  if ( snappy::GetUncompressedLength(a4, a3, (unsigned __int64)&v24, (unsigned __int64 *)a4) )
  {
    if ( a5 >= (__int64)v24 )
    {
      if ( snappy::RawUncompress(a4, a3, v9, v10) )
      {
        *(_QWORD *)(a2 + 8) = 0;
        *(_QWORD *)(a2 + 16) = v24;
        return a2;
      }
      v19 = arrow::util::StringBuilder<char const (&)[13]>(v28, "Corrupt snappy compressed data.");
      LOBYTE(v20) = 5;
      arrow::Status::Status(v25, v20, v19);
      if ( si128.m128i_i64[1] >= 0x10uLL )
      {
        v21 = si128.m128i_i64[1] + 1;
        v22 = (void *)v28[0];
        if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
        {
          v21 = si128.m128i_i64[1] + 40;
          v22 = *(void **)(v28[0] - 8LL);
          if ( (unsigned __int64)(v28[0] - (_QWORD)v22 - 8LL) > 0x1F )
            invalid_parameter_noinfo_noreturn();
        }
        operator delete(v22, v21);
      }
    }
    else
    {
      v15 = arrow::util::StringBuilder<char const (&)[21],__int64 &,char const (&)[11],unsigned __int64 &,char const (&)[12]>(
              (unsigned int)v28,
              (unsigned int)"Output buffer size (",
              (unsigned int)&a5,
              (unsigned int)") must be ",
              (__int64)&v24,
              (__int64)" or larger.");
      LOBYTE(v16) = 4;
      arrow::Status::Status(v25, v16, v15);
      if ( si128.m128i_i64[1] >= 0x10uLL )
      {
        v17 = si128.m128i_i64[1] + 1;
        v18 = (void *)v28[0];
        if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
        {
          v17 = si128.m128i_i64[1] + 40;
          v18 = *(void **)(v28[0] - 8LL);
          if ( (unsigned __int64)(v28[0] - (_QWORD)v18 - 8LL) > 0x1F )
            invalid_parameter_noinfo_noreturn();
        }
        operator delete(v18, v17);
      }
    }
  }
  else
  {
    v11 = arrow::util::StringBuilder<char const (&)[13]>(v28, "Corrupt snappy compressed data.");
    LOBYTE(v12) = 5;
    arrow::Status::Status(v25, v12, v11);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v13 = si128.m128i_i64[1] + 1;
      v14 = (void *)v28[0];
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v13 = si128.m128i_i64[1] + 40;
        v14 = *(void **)(v28[0] - 8LL);
        if ( (unsigned __int64)(v28[0] - (_QWORD)v14 - 8LL) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v14, v13);
    }
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v28[0]) = 0;
  arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v25);
  if ( v26 )
    arrow::Status::State::`scalar deleting destructor'(v26, 1u);
  return a2;
}

```

## disassembly

```asm
0x1800e1ca0  push    rbp
0x1800e1ca2  push    rbx
0x1800e1ca3  push    rsi
0x1800e1ca4  push    rdi
0x1800e1ca5  push    r14
0x1800e1ca7  mov     rbp, rsp
0x1800e1caa  sub     rsp, 80h
0x1800e1cb1  mov     [rbp+var_38], 0FFFFFFFFFFFFFFFEh
0x1800e1cb9  mov     rax, cs:__security_cookie
0x1800e1cc0  xor     rax, rsp
0x1800e1cc3  mov     [rbp+var_10], rax
0x1800e1cc7  mov     rsi, r9
0x1800e1cca  mov     rdi, r8
0x1800e1ccd  mov     rbx, rdx
0x1800e1cd0  mov     [rbp+var_50], rdx
0x1800e1cd4  mov     r14, [rbp+arg_28]
0x1800e1cd8  lea     r8, [rbp+var_50]; unsigned __int64
0x1800e1cdc  mov     rdx, rdi; char *
0x1800e1cdf  mov     rcx, r9; this
0x1800e1ce2  call    ?GetUncompressedLength@snappy@@YA_NPEBD_KPEA_K@Z; snappy::GetUncompressedLength(char const *,unsigned __int64,unsigned __int64 *)
0x1800e1ce7  test    al, al
0x1800e1ce9  jnz     loc_1800E1D84
0x1800e1cef  lea     rdx, aCorruptSnappyC; "Corrupt snappy compressed data."
0x1800e1cf6  lea     rcx, [rbp+var_30]
0x1800e1cfa  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800e1cff  nop
0x1800e1d00  mov     r8, rax
0x1800e1d03  mov     dl, 5
0x1800e1d05  lea     rcx, [rbp+var_48]
0x1800e1d09  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800e1d0e  nop
0x1800e1d0f  mov     rdx, [rbp+var_18]
0x1800e1d13  cmp     rdx, 10h
0x1800e1d17  jb      short loc_1800E1D4A
0x1800e1d19  inc     rdx
0x1800e1d1c  mov     rcx, [rbp+var_30]
0x1800e1d20  mov     rax, rcx
0x1800e1d23  cmp     rdx, 1000h
0x1800e1d2a  jb      short loc_1800E1D45
0x1800e1d2c  add     rdx, 27h ; '''; unsigned __int64
0x1800e1d30  mov     rcx, [rcx-8]; void *
0x1800e1d34  sub     rax, rcx
0x1800e1d37  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e1d3b  cmp     rax, 1Fh
0x1800e1d3f  ja      loc_1800E1EEF
0x1800e1d45  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e1d4a  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800e1d52  movdqu  xmmword ptr [rbp-20h], xmm0
0x1800e1d57  mov     byte ptr [rbp+var_30], 0
0x1800e1d5b  lea     rdx, [rbp+var_48]
0x1800e1d5f  mov     rcx, rbx
0x1800e1d62  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e1d67  nop
0x1800e1d68  mov     rcx, [rbp+var_40]; this
0x1800e1d6c  test    rcx, rcx
0x1800e1d6f  jz      loc_1800E1ECC
0x1800e1d75  mov     edx, 1; unsigned int
0x1800e1d7a  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e1d7f  jmp     loc_1800E1ECC
0x1800e1d84  mov     rax, [rbp+var_50]
0x1800e1d88  cmp     [rbp+arg_20], rax
0x1800e1d8c  jge     loc_1800E1E30
0x1800e1d92  lea     rax, aOrLarger; " or larger."
0x1800e1d99  mov     [rsp+80h+var_58], rax
0x1800e1d9e  lea     rax, [rbp+var_50]
0x1800e1da2  mov     [rsp+80h+var_60], rax
0x1800e1da7  lea     r9, aMustBe; ") must be "
0x1800e1dae  lea     r8, [rbp+arg_20]
0x1800e1db2  lea     rdx, aOutputBufferSi; "Output buffer size ("
0x1800e1db9  lea     rcx, [rbp+var_30]
0x1800e1dbd  call    ??$StringBuilder@AEAY0BF@$$CBDAEA_JAEAY0L@$$CBDAEA_KAEAY0M@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0BF@$$CBDAEA_JAEAY0L@$$CBDAEA_KAEAY0M@$$CBD@Z; arrow::util::StringBuilder<char const (&)[21],__int64 &,char const (&)[11],unsigned __int64 &,char const (&)[12]>(char const (&)[21],__int64 &,char const (&)[11],unsigned __int64 &,char const (&)[12])
0x1800e1dc2  nop
0x1800e1dc3  mov     r8, rax
0x1800e1dc6  mov     dl, 4
0x1800e1dc8  lea     rcx, [rbp+var_48]
0x1800e1dcc  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800e1dd1  nop
0x1800e1dd2  mov     rdx, [rbp+var_18]
0x1800e1dd6  cmp     rdx, 10h
0x1800e1dda  jb      short loc_1800E1E0D
0x1800e1ddc  inc     rdx
0x1800e1ddf  mov     rcx, [rbp+var_30]
0x1800e1de3  mov     rax, rcx
0x1800e1de6  cmp     rdx, 1000h
0x1800e1ded  jb      short loc_1800E1E08
0x1800e1def  add     rdx, 27h ; '''; unsigned __int64
0x1800e1df3  mov     rcx, [rcx-8]; void *
0x1800e1df7  sub     rax, rcx
0x1800e1dfa  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e1dfe  cmp     rax, 1Fh
0x1800e1e02  ja      loc_1800E1EF5
0x1800e1e08  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e1e0d  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800e1e15  movdqu  xmmword ptr [rbp-20h], xmm0
0x1800e1e1a  mov     byte ptr [rbp+var_30], 0
0x1800e1e1e  lea     rdx, [rbp+var_48]
0x1800e1e22  mov     rcx, rbx
0x1800e1e25  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e1e2a  nop
0x1800e1e2b  jmp     loc_1800E1D68
0x1800e1e30  mov     r8, r14; unsigned __int64
0x1800e1e33  mov     rdx, rdi; char *
0x1800e1e36  mov     rcx, rsi; this
0x1800e1e39  call    ?RawUncompress@snappy@@YA_NPEBD_KPEAD@Z; snappy::RawUncompress(char const *,unsigned __int64,char *)
0x1800e1e3e  test    al, al
0x1800e1e40  jnz     short loc_1800E1EBC
0x1800e1e42  lea     rdx, aCorruptSnappyC; "Corrupt snappy compressed data."
0x1800e1e49  lea     rcx, [rbp+var_30]
0x1800e1e4d  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800e1e52  nop
0x1800e1e53  mov     r8, rax
0x1800e1e56  mov     dl, 5
0x1800e1e58  lea     rcx, [rbp+var_48]
0x1800e1e5c  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800e1e61  nop
0x1800e1e62  mov     rdx, [rbp+var_18]
0x1800e1e66  cmp     rdx, 10h
0x1800e1e6a  jb      short loc_1800E1E99
0x1800e1e6c  inc     rdx
0x1800e1e6f  mov     rcx, [rbp+var_30]
0x1800e1e73  mov     rax, rcx
0x1800e1e76  cmp     rdx, 1000h
0x1800e1e7d  jb      short loc_1800E1E94
0x1800e1e7f  add     rdx, 27h ; '''; unsigned __int64
0x1800e1e83  mov     rcx, [rcx-8]; void *
0x1800e1e87  sub     rax, rcx
0x1800e1e8a  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e1e8e  cmp     rax, 1Fh
0x1800e1e92  ja      short loc_1800E1EE9
0x1800e1e94  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e1e99  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800e1ea1  movdqu  xmmword ptr [rbp-20h], xmm0
0x1800e1ea6  mov     byte ptr [rbp+var_30], 0
0x1800e1eaa  lea     rdx, [rbp+var_48]
0x1800e1eae  mov     rcx, rbx
0x1800e1eb1  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e1eb6  nop
0x1800e1eb7  jmp     loc_1800E1D68
0x1800e1ebc  mov     qword ptr [rbx+8], 0
0x1800e1ec4  mov     rax, [rbp+var_50]
0x1800e1ec8  mov     [rbx+10h], rax
0x1800e1ecc  mov     rax, rbx
0x1800e1ecf  mov     rcx, [rbp+var_10]
0x1800e1ed3  xor     rcx, rsp; StackCookie
0x1800e1ed6  call    __security_check_cookie
0x1800e1edb  add     rsp, 80h
0x1800e1ee2  pop     r14
0x1800e1ee4  pop     rdi
0x1800e1ee5  pop     rsi
0x1800e1ee6  pop     rbx
0x1800e1ee7  pop     rbp
0x1800e1ee8  retn
0x1800e1ee9  call    _invalid_parameter_noinfo_noreturn
0x1800e1eef  call    _invalid_parameter_noinfo_noreturn
0x1800e1ef5  call    _invalid_parameter_noinfo_noreturn
```
