# arrow::util::_anonymous_namespace_::Lz4Codec::MakeCompressor

- ea: `0x1800e3180`
- end: `0x1800e3252`
- name: `arrow::util::_anonymous_namespace_::Lz4Codec::MakeCompressor`
- size: `210`
- prototype: ``
- caller_count: `0`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x1800e3180`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800e31a6`: `Streaming compression unsupported with LZ4 raw format. Try using LZ4 frame format instead.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::util::_anonymous_namespace_::Lz4Codec::MakeCompressor(__int64 a1, __int64 a2)
{
  __int64 v3; // r8
  __int64 v4; // rdx
  unsigned __int64 v5; // rdx
  _BYTE *v6; // rcx
  __int64 v8; // [rsp+20h] [rbp-48h] BYREF
  arrow::Status::State *v9; // [rsp+28h] [rbp-40h]
  __int64 v10; // [rsp+30h] [rbp-38h]
  _BYTE *v11; // [rsp+38h] [rbp-30h] BYREF
  __m128i si128; // [rsp+48h] [rbp-20h]

  v10 = -2;
  v8 = a2;
  v3 = arrow::util::StringBuilder<char const (&)[13]>(
         &v11,
         "Streaming compression unsupported with LZ4 raw format. Try using LZ4 frame format instead.");
  LOBYTE(v4) = 10;
  arrow::Status::Status(&v8, v4, v3);
  if ( si128.m128i_i64[1] >= 0x10uLL )
  {
    v5 = si128.m128i_i64[1] + 1;
    v6 = v11;
    if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
    {
      v5 = si128.m128i_i64[1] + 40;
      v6 = (_BYTE *)*((_QWORD *)v11 - 1);
      if ( (unsigned __int64)(v11 - v6 - 8) > 0x1F )
        invalid_parameter_noinfo_noreturn();
    }
    operator delete(v6, v5);
  }
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  LOBYTE(v11) = 0;
  arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, &v8);
  if ( v9 )
    arrow::Status::State::`scalar deleting destructor'(v9, 1u);
  return a2;
}

```

## disassembly

```asm
0x1800e3180  push    rbx
0x1800e3182  sub     rsp, 60h
0x1800e3186  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800e318f  mov     rax, cs:__security_cookie
0x1800e3196  xor     rax, rsp
0x1800e3199  mov     [rsp+68h+var_10], rax
0x1800e319e  mov     rbx, rdx
0x1800e31a1  mov     [rsp+68h+var_48], rdx
0x1800e31a6  lea     rdx, aStreamingCompr_0; "Streaming compression unsupported with "...
0x1800e31ad  lea     rcx, [rsp+68h+var_30]
0x1800e31b2  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800e31b7  nop
0x1800e31b8  mov     r8, rax
0x1800e31bb  mov     dl, 0Ah
0x1800e31bd  lea     rcx, [rsp+68h+var_48]
0x1800e31c2  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800e31c7  nop
0x1800e31c8  mov     rdx, [rsp+68h+var_18]
0x1800e31cd  cmp     rdx, 10h
0x1800e31d1  jb      short loc_1800E3201
0x1800e31d3  inc     rdx
0x1800e31d6  mov     rcx, [rsp+68h+var_30]
0x1800e31db  mov     rax, rcx
0x1800e31de  cmp     rdx, 1000h
0x1800e31e5  jb      short loc_1800E31FC
0x1800e31e7  add     rdx, 27h ; '''; unsigned __int64
0x1800e31eb  mov     rcx, [rcx-8]; void *
0x1800e31ef  sub     rax, rcx
0x1800e31f2  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e31f6  cmp     rax, 1Fh
0x1800e31fa  ja      short loc_1800E324C
0x1800e31fc  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e3201  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800e3209  movdqu  xmmword ptr [rsp+48h], xmm0
0x1800e320f  mov     byte ptr [rsp+68h+var_30], 0
0x1800e3214  lea     rdx, [rsp+68h+var_48]
0x1800e3219  mov     rcx, rbx
0x1800e321c  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e3221  nop
0x1800e3222  mov     rcx, [rsp+68h+var_40]; this
0x1800e3227  test    rcx, rcx
0x1800e322a  jz      short loc_1800E3236
0x1800e322c  mov     edx, 1; unsigned int
0x1800e3231  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e3236  mov     rax, rbx
0x1800e3239  mov     rcx, [rsp+68h+var_10]
0x1800e323e  xor     rcx, rsp; StackCookie
0x1800e3241  call    __security_check_cookie
0x1800e3246  add     rsp, 60h
0x1800e324a  pop     rbx
0x1800e324b  retn
0x1800e324c  call    _invalid_parameter_noinfo_noreturn
```
