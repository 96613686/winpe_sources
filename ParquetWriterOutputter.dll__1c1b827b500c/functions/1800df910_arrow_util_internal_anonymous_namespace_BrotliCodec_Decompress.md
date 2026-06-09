# arrow::util::internal::_anonymous_namespace_::BrotliCodec::Decompress

- ea: `0x1800df910`
- end: `0x1800dfa26`
- name: `arrow::util::internal::_anonymous_namespace_::BrotliCodec::Decompress`
- size: `278`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x1800df910`
- `0x180298280`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800df967`: `Corrupt brotli compressed data.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::util::internal::_anonymous_namespace_::BrotliCodec::Decompress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v7; // r8
  __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  _BYTE *v10; // rcx
  __int64 v12; // [rsp+20h] [rbp-58h] BYREF
  char v13[8]; // [rsp+28h] [rbp-50h] BYREF
  arrow::Status::State *v14; // [rsp+30h] [rbp-48h]
  __int64 v15; // [rsp+38h] [rbp-40h]
  _BYTE *v16; // [rsp+40h] [rbp-38h] BYREF
  __m128i si128; // [rsp+50h] [rbp-28h]

  v15 = -2;
  v12 = a5;
  if ( (unsigned int)BrotliDecoderDecompress(a3, a4, &v12, a6) == 1 )
  {
    *(_QWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 16) = v12;
  }
  else
  {
    v7 = arrow::util::StringBuilder<char const (&)[13]>(&v16, "Corrupt brotli compressed data.");
    LOBYTE(v8) = 5;
    arrow::Status::Status(v13, v8, v7);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v9 = si128.m128i_i64[1] + 1;
      v10 = v16;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v9 = si128.m128i_i64[1] + 40;
        v10 = (_BYTE *)*((_QWORD *)v16 - 1);
        if ( (unsigned __int64)(v16 - v10 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v10, v9);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v16) = 0;
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v13);
    if ( v14 )
      arrow::Status::State::`scalar deleting destructor'(v14, 1u);
  }
  return a2;
}

```

## disassembly

```asm
0x1800df910  push    rbx
0x1800df912  sub     rsp, 70h
0x1800df916  mov     [rsp+78h+var_40], 0FFFFFFFFFFFFFFFEh
0x1800df91f  mov     rax, cs:__security_cookie
0x1800df926  xor     rax, rsp
0x1800df929  mov     [rsp+78h+var_18], rax
0x1800df92e  mov     r11, r9
0x1800df931  mov     rcx, r8
0x1800df934  mov     rbx, rdx
0x1800df937  mov     [rsp+78h+var_58], rdx
0x1800df93c  mov     r9, [rsp+78h+arg_28]
0x1800df944  mov     rax, [rsp+78h+arg_20]
0x1800df94c  mov     [rsp+78h+var_58], rax
0x1800df951  lea     r8, [rsp+78h+var_58]
0x1800df956  mov     rdx, r11
0x1800df959  call    BrotliDecoderDecompress
0x1800df95e  cmp     eax, 1
0x1800df961  jz      loc_1800DF9F9
0x1800df967  lea     rdx, aCorruptBrotliC; "Corrupt brotli compressed data."
0x1800df96e  lea     rcx, [rsp+78h+var_38]
0x1800df973  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800df978  nop
0x1800df979  mov     r8, rax
0x1800df97c  mov     dl, 5
0x1800df97e  lea     rcx, [rsp+78h+var_50]
0x1800df983  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800df988  nop
0x1800df989  mov     rdx, [rsp+78h+var_20]
0x1800df98e  cmp     rdx, 10h
0x1800df992  jb      short loc_1800DF9C2
0x1800df994  inc     rdx
0x1800df997  mov     rcx, [rsp+78h+var_38]
0x1800df99c  mov     rax, rcx
0x1800df99f  cmp     rdx, 1000h
0x1800df9a6  jb      short loc_1800DF9BD
0x1800df9a8  add     rdx, 27h ; '''; unsigned __int64
0x1800df9ac  mov     rcx, [rcx-8]; void *
0x1800df9b0  sub     rax, rcx
0x1800df9b3  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800df9b7  cmp     rax, 1Fh
0x1800df9bb  ja      short loc_1800DFA20
0x1800df9bd  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800df9c2  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800df9ca  movdqu  xmmword ptr [rsp+50h], xmm0
0x1800df9d0  mov     byte ptr [rsp+78h+var_38], 0
0x1800df9d5  lea     rdx, [rsp+78h+var_50]
0x1800df9da  mov     rcx, rbx
0x1800df9dd  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800df9e2  nop
0x1800df9e3  mov     rcx, [rsp+78h+var_48]; this
0x1800df9e8  test    rcx, rcx
0x1800df9eb  jz      short loc_1800DFA0A
0x1800df9ed  mov     edx, 1; unsigned int
0x1800df9f2  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800df9f7  jmp     short loc_1800DFA0A
0x1800df9f9  mov     qword ptr [rbx+8], 0
0x1800dfa01  mov     rax, [rsp+78h+var_58]
0x1800dfa06  mov     [rbx+10h], rax
0x1800dfa0a  mov     rax, rbx
0x1800dfa0d  mov     rcx, [rsp+78h+var_18]
0x1800dfa12  xor     rcx, rsp; StackCookie
0x1800dfa15  call    __security_check_cookie
0x1800dfa1a  add     rsp, 70h
0x1800dfa1e  pop     rbx
0x1800dfa1f  retn
0x1800dfa20  call    _invalid_parameter_noinfo_noreturn
```
