# arrow::util::Codec::Create(arrow::Compression::type,int)

- ea: `0x180099980`
- end: `0x180099e80`
- name: `?Create@Codec@util@arrow@@SA?AV?$Result@V?$unique_ptr@VCodec@util@arrow@@U?$default_delete@VCodec@util@arrow@@@std@@@std@@@3@W4type@Compression@3@H@Z`
- size: `1280`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028ff0`

## callees

- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x1800997f0`
- `0x180099980`
- `0x18009a010`
- `0x1800dfed0`
- `0x1800e1580`
- `0x1800e20c0`
- `0x1800e3610`
- `0x1800e3690`
- `0x1800e4050`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`
- `0x180358070`

## string_xrefs

- `0x1800999ea`: `Compression level cannot be specified for UNCOMPRESSED.`
- `0x180099a86`: `Snappy doesn't support setting a compression level.`
- `0x180099b36`: `LZ0 doesn't support setting a compression level.`
- `0x180099bf1`: `LZ4 doesn't support setting a compression level.`
- `0x180099c27`: `LZ4 doesn't support setting a compression level.`

## pseudocode

```c
// Hidden C++ exception states: #wind=15
__int64 __fastcall arrow::util::Codec::Create(__int64 a1, int a2, __int64 a3)
{
  __int64 v4; // rbx
  __int64 v5; // r8
  __int64 v6; // rdx
  unsigned __int64 v7; // rdx
  _BYTE *v8; // rcx
  __int64 v9; // r8
  __int64 v10; // rdx
  unsigned __int64 v11; // rdx
  _BYTE *v12; // rcx
  __int64 *SnappyCodec; // rax
  __int64 v14; // rax
  __int64 v15; // rax
  __int64 v16; // rdx
  unsigned __int64 v17; // rdx
  _BYTE *v18; // rcx
  arrow::Status::State *v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  unsigned __int64 v24; // rdx
  _BYTE *v25; // rcx
  __int64 v26; // r8
  __int64 v27; // rdx
  unsigned __int64 v28; // rdx
  _BYTE *v29; // rcx
  __int64 v31; // [rsp+20h] [rbp-60h] BYREF
  __int64 v32; // [rsp+28h] [rbp-58h]
  void (__fastcall ***v33)(_QWORD, __int64); // [rsp+30h] [rbp-50h] BYREF
  arrow::Status::State *v34; // [rsp+38h] [rbp-48h]
  __m128i v35; // [rsp+40h] [rbp-40h]
  _BYTE *v36; // [rsp+50h] [rbp-30h] BYREF
  arrow::Status::State *v37; // [rsp+58h] [rbp-28h]
  __m128i si128; // [rsp+60h] [rbp-20h]

  v32 = -2;
  v33 = (void (__fastcall ***)(_QWORD, __int64))a1;
  v4 = 0;
  v31 = 0;
  switch ( a2 )
  {
    case 0:
      if ( (_DWORD)a3 != 0x80000000 )
      {
        v5 = arrow::util::StringBuilder<char const (&)[13]>(
               &v36,
               "Compression level cannot be specified for UNCOMPRESSED.");
        LOBYTE(v6) = 4;
        arrow::Status::Status(&v33, v6, v5);
        if ( si128.m128i_i64[1] >= 0x10uLL )
        {
          v7 = si128.m128i_i64[1] + 1;
          v8 = v36;
          if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
          {
            v7 = si128.m128i_i64[1] + 40;
            v8 = (_BYTE *)*((_QWORD *)v36 - 1);
            if ( (unsigned __int64)(v36 - v8 - 8) > 0x1F )
              invalid_parameter_noinfo_noreturn();
          }
          operator delete(v8, v7);
        }
        goto LABEL_23;
      }
      *(_QWORD *)(a1 + 8) = 0;
      *(_QWORD *)(a1 + 16) = 0;
      return a1;
    case 1:
      if ( (_DWORD)a3 == 0x80000000 )
      {
        SnappyCodec = (__int64 *)arrow::util::internal::MakeSnappyCodec(
                                   &v33,
                                   0x180000000uLL,
                                   a3,
                                   (unsigned int)a3,
                                   v31,
                                   v32);
        goto LABEL_31;
      }
      v9 = arrow::util::StringBuilder<char const (&)[13]>(&v36, "Snappy doesn't support setting a compression level.");
      LOBYTE(v10) = 4;
      arrow::Status::Status(&v33, v10, v9);
      if ( si128.m128i_i64[1] >= 0x10uLL )
      {
        v11 = si128.m128i_i64[1] + 1;
        v12 = v36;
        if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
        {
          v11 = si128.m128i_i64[1] + 40;
          v12 = (_BYTE *)*((_QWORD *)v36 - 1);
          if ( (unsigned __int64)(v36 - v12 - 8) > 0x1F )
            invalid_parameter_noinfo_noreturn();
        }
        operator delete(v12, v11);
      }
      goto LABEL_23;
    case 2:
      SnappyCodec = (__int64 *)arrow::util::internal::MakeGZipCodec(&v33, (unsigned int)a3, 2);
      goto LABEL_31;
    case 3:
      SnappyCodec = (__int64 *)arrow::util::internal::MakeBrotliCodec(&v33, (unsigned int)a3);
      goto LABEL_31;
    case 4:
      SnappyCodec = (__int64 *)arrow::util::internal::MakeZSTDCodec(&v33, (unsigned int)a3);
      goto LABEL_31;
    case 5:
      if ( (_DWORD)a3 != 0x80000000 )
        goto LABEL_26;
      SnappyCodec = (__int64 *)arrow::util::internal::MakeLz4RawCodec(
                                 &v33,
                                 0x180000000uLL,
                                 a3,
                                 (unsigned int)a3,
                                 v31,
                                 v32);
      goto LABEL_31;
    case 6:
      if ( (_DWORD)a3 != 0x80000000 )
      {
LABEL_26:
        v20 = arrow::Status::Invalid<char const (&)[65]>(&v36, "LZ4 doesn't support setting a compression level.");
        arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a1, v20);
        goto LABEL_52;
      }
      SnappyCodec = (__int64 *)arrow::util::internal::MakeLz4FrameCodec(
                                 &v33,
                                 0x180000000uLL,
                                 a3,
                                 (unsigned int)a3,
                                 v31,
                                 v32);
LABEL_31:
      if ( &v31 != SnappyCodec )
      {
        v4 = *SnappyCodec;
        *SnappyCodec = 0;
        v31 = v4;
      }
      if ( v33 )
        (**v33)(v33, 1);
      v21 = (*(__int64 (__fastcall **)(__int64, _BYTE **))(*(_QWORD *)v4 + 56LL))(v4, &v36);
      v34 = *(arrow::Status::State **)(v21 + 8);
      *(_QWORD *)(v21 + 8) = 0;
      if ( v37 )
      {
        arrow::Status::State::`scalar deleting destructor'(v37, 1u);
        v37 = 0;
      }
      if ( v34 )
      {
        arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a1, &v33);
        if ( v34 )
        {
          arrow::Status::State::`scalar deleting destructor'(v34, 1u);
          v34 = 0;
        }
        (**(void (__fastcall ***)(__int64, __int64))v4)(v4, 1);
      }
      else
      {
        *(_QWORD *)(a1 + 8) = 0;
        *(_QWORD *)(a1 + 16) = v4;
      }
      break;
    case 7:
      if ( (_DWORD)a3 == 0x80000000 )
      {
        v15 = arrow::util::StringBuilder<char const (&)[13]>(&v36, "LZO codec not implemented");
        LOBYTE(v16) = 10;
        arrow::Status::Status(&v33, v16, v15);
        if ( si128.m128i_i64[1] >= 0x10uLL )
        {
          v17 = si128.m128i_i64[1] + 1;
          v18 = v36;
          if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
          {
            v17 = si128.m128i_i64[1] + 40;
            v18 = (_BYTE *)*((_QWORD *)v36 - 1);
            if ( (unsigned __int64)(v36 - v18 - 8) > 0x1F )
              invalid_parameter_noinfo_noreturn();
          }
          operator delete(v18, v17);
        }
LABEL_23:
        si128 = _mm_load_si128((const __m128i *)&_xmm);
        LOBYTE(v36) = 0;
        arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a1, &v33);
        v19 = v34;
      }
      else
      {
        v14 = arrow::Status::Invalid<char const (&)[65]>(&v36, "LZ0 doesn't support setting a compression level.");
        arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a1, v14);
LABEL_52:
        v19 = v37;
      }
      if ( v19 )
        arrow::Status::State::`scalar deleting destructor'(v19, 1u);
      break;
    case 8:
      v22 = arrow::util::StringBuilder<char const (&)[13]>(&v33, "BZ2 codec support not built");
      LOBYTE(v23) = 10;
      arrow::Status::Status(&v36, v23, v22);
      if ( v35.m128i_i64[1] >= 0x10uLL )
      {
        v24 = v35.m128i_i64[1] + 1;
        v25 = v33;
        if ( (unsigned __int64)(v35.m128i_i64[1] + 1) >= 0x1000 )
        {
          v24 = v35.m128i_i64[1] + 40;
          v25 = *(v33 - 1);
          if ( (unsigned __int64)((char *)v33 - v25 - 8) > 0x1F )
            invalid_parameter_noinfo_noreturn();
        }
        operator delete(v25, v24);
      }
      goto LABEL_51;
    default:
      v26 = arrow::util::StringBuilder<char const (&)[13]>(&v33, "Unrecognized codec");
      LOBYTE(v27) = 4;
      arrow::Status::Status(&v36, v27, v26);
      if ( v35.m128i_i64[1] >= 0x10uLL )
      {
        v28 = v35.m128i_i64[1] + 1;
        v29 = v33;
        if ( (unsigned __int64)(v35.m128i_i64[1] + 1) >= 0x1000 )
        {
          v28 = v35.m128i_i64[1] + 40;
          v29 = *(v33 - 1);
          if ( (unsigned __int64)((char *)v33 - v29 - 8) > 0x1F )
            invalid_parameter_noinfo_noreturn();
        }
        operator delete(v29, v28);
      }
LABEL_51:
      v35 = _mm_load_si128((const __m128i *)&_xmm);
      LOBYTE(v33) = 0;
      arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a1, &v36);
      goto LABEL_52;
  }
  return a1;
}

```

## disassembly

```asm
0x180099980  push    rbp
0x180099982  push    rsi
0x180099983  push    rdi
0x180099984  mov     rbp, rsp
0x180099987  sub     rsp, 80h
0x18009998e  mov     [rbp+var_58], 0FFFFFFFFFFFFFFFEh
0x180099996  mov     [rsp+80h+arg_8], rbx
0x18009999e  mov     rax, cs:__security_cookie
0x1800999a5  xor     rax, rsp
0x1800999a8  mov     [rbp+var_10], rax
0x1800999ac  mov     r9d, r8d
0x1800999af  mov     rdi, rcx
0x1800999b2  mov     [rbp+var_50], rcx
0x1800999b6  xor     esi, esi
0x1800999b8  mov     ebx, esi
0x1800999ba  mov     [rbp+var_60], rbx
0x1800999be  cmp     edx, 8; switch 9 cases
0x1800999c1  ja      def_1800999DB; jumptable 00000001800999DB default case
0x1800999c7  movsxd  rax, edx
0x1800999ca  lea     rdx, cs:180000000h
0x1800999d1  mov     ecx, ds:(jpt_1800999DB - 180000000h)[rdx+rax*4]
0x1800999d8  add     rcx, rdx
0x1800999db  jmp     rcx; switch jump
0x1800999dd  cmp     r9d, 80000000h; jumptable 00000001800999DB case 0
0x1800999e4  jz      loc_180099A6C
0x1800999ea  lea     rdx, aCompressionLev; "Compression level cannot be specified f"...
0x1800999f1  lea     rcx, [rbp+var_30]
0x1800999f5  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800999fa  nop
0x1800999fb  mov     r8, rax
0x1800999fe  mov     dl, 4
0x180099a00  lea     rcx, [rbp+var_50]
0x180099a04  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x180099a09  nop
0x180099a0a  mov     rdx, [rbp+var_18]
0x180099a0e  cmp     rdx, 10h
0x180099a12  jb      short loc_180099A45
0x180099a14  inc     rdx
0x180099a17  mov     rcx, [rbp+var_30]
0x180099a1b  mov     rax, rcx
0x180099a1e  cmp     rdx, 1000h
0x180099a25  jb      short loc_180099A40
0x180099a27  add     rdx, 27h ; '''; unsigned __int64
0x180099a2b  mov     rcx, [rcx-8]; void *
0x180099a2f  sub     rax, rcx
0x180099a32  add     rax, 0FFFFFFFFFFFFFFF8h
0x180099a36  cmp     rax, 1Fh
0x180099a3a  ja      loc_180099E41
0x180099a40  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180099a45  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180099a4d  movdqu  xmmword ptr [rbp-20h], xmm0
0x180099a52  mov     byte ptr [rbp+var_30], 0
0x180099a56  lea     rdx, [rbp+var_50]
0x180099a5a  mov     rcx, rdi
0x180099a5d  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x180099a62  nop
0x180099a63  mov     rcx, [rbp+var_48]
0x180099a67  jmp     loc_180099E09
0x180099a6c  mov     [rdi+8], rsi
0x180099a70  mov     [rdi+10h], rsi
0x180099a74  jmp     loc_180099E19
0x180099a79  cmp     r9d, 80000000h; jumptable 00000001800999DB case 1
0x180099a80  jz      loc_180099B08
0x180099a86  lea     rdx, aSnappyDoesnTSu; "Snappy doesn't support setting a compre"...
0x180099a8d  lea     rcx, [rbp+var_30]
0x180099a91  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x180099a96  nop
0x180099a97  mov     r8, rax
0x180099a9a  mov     dl, 4
0x180099a9c  lea     rcx, [rbp+var_50]
0x180099aa0  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x180099aa5  nop
0x180099aa6  mov     rdx, [rbp+var_18]
0x180099aaa  cmp     rdx, 10h
0x180099aae  jb      short loc_180099AE1
0x180099ab0  inc     rdx
0x180099ab3  mov     rcx, [rbp+var_30]
0x180099ab7  mov     rax, rcx
0x180099aba  cmp     rdx, 1000h
0x180099ac1  jb      short loc_180099ADC
0x180099ac3  add     rdx, 27h ; '''; unsigned __int64
0x180099ac7  mov     rcx, [rcx-8]; void *
0x180099acb  sub     rax, rcx
0x180099ace  add     rax, 0FFFFFFFFFFFFFFF8h
0x180099ad2  cmp     rax, 1Fh
0x180099ad6  ja      loc_180099E47
0x180099adc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180099ae1  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180099ae9  movdqu  xmmword ptr [rbp-20h], xmm0
0x180099aee  mov     byte ptr [rbp+var_30], 0
0x180099af2  lea     rdx, [rbp+var_50]
0x180099af6  mov     rcx, rdi
0x180099af9  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x180099afe  nop
0x180099aff  mov     rcx, [rbp+var_48]
0x180099b03  jmp     loc_180099E09
0x180099b08  lea     rcx, [rbp+var_50]
0x180099b0c  call    ?MakeSnappyCodec@internal@util@arrow@@YA?AV?$unique_ptr@VCodec@util@arrow@@U?$default_delete@VCodec@util@arrow@@@std@@@std@@XZ; arrow::util::internal::MakeSnappyCodec(void)
0x180099b11  jmp     loc_180099C60
0x180099b16  mov     r8d, 2; jumptable 00000001800999DB case 2
0x180099b1c  mov     edx, r9d
0x180099b1f  lea     rcx, [rbp+var_50]
0x180099b23  call    ?MakeGZipCodec@internal@util@arrow@@YA?AV?$unique_ptr@VCodec@util@arrow@@U?$default_delete@VCodec@util@arrow@@@std@@@std@@HW4type@GZipFormat@123@@Z; arrow::util::internal::MakeGZipCodec(int,arrow::util::internal::GZipFormat::type)
0x180099b28  jmp     loc_180099C60
0x180099b2d  cmp     r9d, 80000000h; jumptable 00000001800999DB case 7
0x180099b34  jz      short loc_180099B58
0x180099b36  lea     rdx, aLz0DoesnTSuppo; "LZ0 doesn't support setting a compressi"...
0x180099b3d  lea     rcx, [rbp+var_30]
0x180099b41  call    ??$Invalid@AEAY0EB@$$CBD@Status@arrow@@SA?AV01@AEAY0EB@$$CBD@Z; arrow::Status::Invalid<char const (&)[65]>(char const (&)[65])
0x180099b46  nop
0x180099b47  mov     rdx, rax
0x180099b4a  mov     rcx, rdi
0x180099b4d  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x180099b52  nop
0x180099b53  jmp     loc_180099E05
0x180099b58  lea     rdx, aLzoCodecNotImp; "LZO codec not implemented"
0x180099b5f  lea     rcx, [rbp+var_30]
0x180099b63  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x180099b68  nop
0x180099b69  mov     r8, rax
0x180099b6c  mov     dl, 0Ah
0x180099b6e  lea     rcx, [rbp+var_50]
0x180099b72  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x180099b77  nop
0x180099b78  mov     rdx, [rbp+var_18]
0x180099b7c  cmp     rdx, 10h
0x180099b80  jb      short loc_180099BB3
0x180099b82  inc     rdx
0x180099b85  mov     rcx, [rbp+var_30]
0x180099b89  mov     rax, rcx
0x180099b8c  cmp     rdx, 1000h
0x180099b93  jb      short loc_180099BAE
0x180099b95  add     rdx, 27h ; '''; unsigned __int64
0x180099b99  mov     rcx, [rcx-8]; void *
0x180099b9d  sub     rax, rcx
0x180099ba0  add     rax, 0FFFFFFFFFFFFFFF8h
0x180099ba4  cmp     rax, 1Fh
0x180099ba8  ja      loc_180099E4D
0x180099bae  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180099bb3  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180099bbb  movdqu  xmmword ptr [rbp-20h], xmm0
0x180099bc0  mov     byte ptr [rbp+var_30], 0
0x180099bc4  lea     rdx, [rbp+var_50]
0x180099bc8  mov     rcx, rdi
0x180099bcb  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x180099bd0  nop
0x180099bd1  mov     rcx, [rbp+var_48]
0x180099bd5  jmp     loc_180099E09
0x180099bda  mov     edx, r9d; jumptable 00000001800999DB case 3
0x180099bdd  lea     rcx, [rbp+var_50]
0x180099be1  call    ?MakeBrotliCodec@internal@util@arrow@@YA?AV?$unique_ptr@VCodec@util@arrow@@U?$default_delete@VCodec@util@arrow@@@std@@@std@@H@Z; arrow::util::internal::MakeBrotliCodec(int)
0x180099be6  jmp     short loc_180099C60
0x180099be8  cmp     r9d, 80000000h; jumptable 00000001800999DB case 5
0x180099bef  jz      short loc_180099C13
0x180099bf1  lea     rdx, aLz4DoesnTSuppo; "LZ4 doesn't support setting a compressi"...
0x180099bf8  lea     rcx, [rbp+var_30]
0x180099bfc  call    ??$Invalid@AEAY0EB@$$CBD@Status@arrow@@SA?AV01@AEAY0EB@$$CBD@Z; arrow::Status::Invalid<char const (&)[65]>(char const (&)[65])
0x180099c01  nop
0x180099c02  mov     rdx, rax
0x180099c05  mov     rcx, rdi
0x180099c08  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x180099c0d  nop
0x180099c0e  jmp     loc_180099E05
0x180099c13  lea     rcx, [rbp+var_50]
0x180099c17  call    ?MakeLz4RawCodec@internal@util@arrow@@YA?AV?$unique_ptr@VCodec@util@arrow@@U?$default_delete@VCodec@util@arrow@@@std@@@std@@XZ; arrow::util::internal::MakeLz4RawCodec(void)
0x180099c1c  jmp     short loc_180099C60
0x180099c1e  cmp     r9d, 80000000h; jumptable 00000001800999DB case 6
0x180099c25  jz      short loc_180099C49
0x180099c27  lea     rdx, aLz4DoesnTSuppo; "LZ4 doesn't support setting a compressi"...
0x180099c2e  lea     rcx, [rbp+var_30]
0x180099c32  call    ??$Invalid@AEAY0EB@$$CBD@Status@arrow@@SA?AV01@AEAY0EB@$$CBD@Z; arrow::Status::Invalid<char const (&)[65]>(char const (&)[65])
0x180099c37  nop
0x180099c38  mov     rdx, rax
0x180099c3b  mov     rcx, rdi
0x180099c3e  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x180099c43  nop
0x180099c44  jmp     loc_180099E05
0x180099c49  lea     rcx, [rbp+var_50]
0x180099c4d  call    ?MakeLz4FrameCodec@internal@util@arrow@@YA?AV?$unique_ptr@VCodec@util@arrow@@U?$default_delete@VCodec@util@arrow@@@std@@@std@@XZ; arrow::util::internal::MakeLz4FrameCodec(void)
0x180099c52  jmp     short loc_180099C60
0x180099c54  mov     edx, r9d; jumptable 00000001800999DB case 4
0x180099c57  lea     rcx, [rbp+var_50]
0x180099c5b  call    ?MakeZSTDCodec@internal@util@arrow@@YA?AV?$unique_ptr@VCodec@util@arrow@@U?$default_delete@VCodec@util@arrow@@@std@@@std@@H@Z; arrow::util::internal::MakeZSTDCodec(int)
0x180099c60  lea     rcx, [rbp+var_60]
0x180099c64  cmp     rcx, rax
0x180099c67  jz      short loc_180099C73
0x180099c69  mov     rbx, [rax]
0x180099c6c  mov     [rax], rsi
0x180099c6f  mov     [rbp+var_60], rbx
0x180099c73  mov     rcx, [rbp+var_50]
0x180099c77  test    rcx, rcx
0x180099c7a  jz      short loc_180099C8D
0x180099c7c  mov     rax, [rcx]
0x180099c7f  mov     edx, 1
0x180099c84  mov     rax, [rax]
0x180099c87  call    cs:__guard_dispatch_icall_fptr
0x180099c8d  mov     rax, [rbx]
0x180099c90  lea     rdx, [rbp+var_30]
0x180099c94  mov     rcx, rbx
0x180099c97  mov     rax, [rax+38h]
0x180099c9b  call    cs:__guard_dispatch_icall_fptr
0x180099ca1  mov     rcx, [rax+8]
0x180099ca5  mov     [rbp+var_48], rcx
0x180099ca9  mov     [rax+8], rsi
0x180099cad  mov     rcx, [rbp+var_28]; this
0x180099cb1  test    rcx, rcx
0x180099cb4  jz      short loc_180099CC4
0x180099cb6  mov     edx, 1; unsigned int
0x180099cbb  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180099cc0  mov     [rbp+var_28], rsi
0x180099cc4  cmp     [rbp+var_48], 0
0x180099cc9  jz      short loc_180099D08
0x180099ccb  lea     rdx, [rbp+var_50]
0x180099ccf  mov     rcx, rdi
0x180099cd2  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x180099cd7  nop
0x180099cd8  mov     rcx, [rbp+var_48]; this
0x180099cdc  test    rcx, rcx
0x180099cdf  jz      short loc_180099CEF
0x180099ce1  mov     edx, 1; unsigned int
0x180099ce6  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180099ceb  mov     [rbp+var_48], rsi
0x180099cef  mov     rax, [rbx]
0x180099cf2  mov     edx, 1
0x180099cf7  mov     rcx, rbx
0x180099cfa  mov     rax, [rax]
0x180099cfd  call    cs:__guard_dispatch_icall_fptr
0x180099d03  jmp     loc_180099E19
0x180099d08  mov     [rdi+8], rsi
0x180099d0c  mov     [rdi+10h], rbx
0x180099d10  jmp     loc_180099E19
0x180099d15  lea     rdx, aBz2CodecSuppor; jumptable 00000001800999DB case 8
0x180099d1c  lea     rcx, [rbp+var_50]
0x180099d20  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x180099d25  nop
0x180099d26  mov     r8, rax
0x180099d29  mov     dl, 0Ah
0x180099d2b  lea     rcx, [rbp+var_30]
0x180099d2f  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x180099d34  nop
0x180099d35  mov     rdx, [rbp+var_38]
0x180099d39  cmp     rdx, 10h
0x180099d3d  jb      short loc_180099D70
0x180099d3f  inc     rdx
0x180099d42  mov     rcx, [rbp+var_50]
0x180099d46  mov     rax, rcx
0x180099d49  cmp     rdx, 1000h
0x180099d50  jb      short loc_180099D6B
0x180099d52  add     rdx, 27h ; '''; unsigned __int64
0x180099d56  mov     rcx, [rcx-8]; void *
0x180099d5a  sub     rax, rcx
0x180099d5d  add     rax, 0FFFFFFFFFFFFFFF8h
0x180099d61  cmp     rax, 1Fh
0x180099d65  ja      loc_180099E53
0x180099d6b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180099d70  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180099d78  movdqu  xmmword ptr [rbp-40h], xmm0
0x180099d7d  mov     byte ptr [rbp+var_50], 0
0x180099d81  lea     rdx, [rbp+var_30]
0x180099d85  mov     rcx, rdi
0x180099d88  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x180099d8d  nop
0x180099d8e  jmp     short loc_180099E05
0x180099d90  lea     rdx, aUnrecognizedCo; jumptable 00000001800999DB default case
0x180099d97  lea     rcx, [rbp+var_50]
0x180099d9b  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x180099da0  nop
0x180099da1  mov     r8, rax
0x180099da4  mov     dl, 4
0x180099da6  lea     rcx, [rbp+var_30]
0x180099daa  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x180099daf  nop
0x180099db0  mov     rdx, [rbp+var_38]
0x180099db4  cmp     rdx, 10h
0x180099db8  jb      short loc_180099DE7
0x180099dba  inc     rdx
0x180099dbd  mov     rcx, [rbp+var_50]
0x180099dc1  mov     rax, rcx
0x180099dc4  cmp     rdx, 1000h
0x180099dcb  jb      short loc_180099DE2
0x180099dcd  add     rdx, 27h ; '''; unsigned __int64
0x180099dd1  mov     rcx, [rcx-8]; void *
0x180099dd5  sub     rax, rcx
0x180099dd8  add     rax, 0FFFFFFFFFFFFFFF8h
0x180099ddc  cmp     rax, 1Fh
0x180099de0  ja      short loc_180099E3B
0x180099de2  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180099de7  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x180099def  movdqu  xmmword ptr [rbp-40h], xmm0
0x180099df4  mov     byte ptr [rbp+var_50], 0
0x180099df8  lea     rdx, [rbp+var_30]
0x180099dfc  mov     rcx, rdi
0x180099dff  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x180099e04  nop
0x180099e05  mov     rcx, [rbp+var_28]; this
0x180099e09  test    rcx, rcx
0x180099e0c  jz      short loc_180099E19
0x180099e0e  mov     edx, 1; unsigned int
0x180099e13  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x180099e18  nop
  ... truncated ...
```
