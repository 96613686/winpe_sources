# arrow::util::internal::_anonymous_namespace_::BrotliCompressor::Compress

- ea: `0x1800df7b0`
- end: `0x1800df902`
- name: `arrow::util::internal::_anonymous_namespace_::BrotliCompressor::Compress`
- size: `338`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f8c0`
- `0x180042fd0`
- `0x180059010`
- `0x18009a010`
- `0x1800df7b0`
- `0x180265310`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800df82f`: `Brotli compress failed`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::util::internal::_anonymous_namespace_::BrotliCompressor::Compress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  _BYTE *v11; // rcx
  __int64 v14; // [rsp+48h] [rbp-41h] BYREF
  const char *v15; // [rsp+50h] [rbp-39h] BYREF
  arrow::Status::State *v16[2]; // [rsp+58h] [rbp-31h] BYREF
  __int64 v17[3]; // [rsp+68h] [rbp-21h] BYREF
  _BYTE *v18; // [rsp+80h] [rbp-9h] BYREF
  __m128i si128; // [rsp+90h] [rbp+7h]

  v17[2] = -2;
  v15 = (const char *)a2;
  v17[1] = a4;
  v17[0] = a6;
  v14 = a5;
  if ( (unsigned int)BrotliEncoderCompressStream(*(_QWORD *)(a1 + 8), (__int64)&v14, (__int64)v17, 0) )
  {
    v16[0] = (arrow::Status::State *)(a3 - a3);
    v16[1] = (arrow::Status::State *)(a5 - v14);
    *(_QWORD *)(a2 + 8) = 0;
    *(_OWORD *)(a2 + 16) = *(_OWORD *)v16;
  }
  else
  {
    v15 = "Brotli compress failed";
    v8 = arrow::util::StringBuilder<char const *>(&v18, &v15);
    LOBYTE(v9) = 5;
    arrow::Status::Status(v16, v9, v8);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v10 = si128.m128i_i64[1] + 1;
      v11 = v18;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v10 = si128.m128i_i64[1] + 40;
        v11 = (_BYTE *)*((_QWORD *)v18 - 1);
        if ( (unsigned __int64)(v18 - v11 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v11, v10);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v18) = 0;
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v16);
    if ( v16[1] )
      arrow::Status::State::`scalar deleting destructor'(v16[1], 1u);
  }
  return a2;
}

```

## disassembly

```asm
0x1800df7b0  push    rbp
0x1800df7b2  push    rbx
0x1800df7b3  push    rsi
0x1800df7b4  push    rdi
0x1800df7b5  lea     rbp, [rsp-2Fh]
0x1800df7ba  sub     rsp, 0B8h
0x1800df7c1  mov     [rbp+47h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800df7c9  mov     rax, cs:__security_cookie
0x1800df7d0  xor     rax, rsp
0x1800df7d3  mov     [rbp+47h+var_30], rax
0x1800df7d7  mov     rdi, r8
0x1800df7da  mov     rbx, rdx
0x1800df7dd  mov     [rbp+47h+var_80], rdx
0x1800df7e1  mov     [rbp+47h+var_60], r9
0x1800df7e5  mov     rax, [rbp+47h+arg_28]
0x1800df7e9  mov     [rbp+47h+var_68], rax
0x1800df7ed  mov     [rbp+47h+var_90], r8
0x1800df7f1  mov     rsi, [rbp+47h+arg_20]
0x1800df7f5  mov     [rbp+47h+var_88], rsi
0x1800df7f9  mov     [rsp+0D0h+var_A0], 0; __int64
0x1800df802  lea     rax, [rbp+47h+var_68]
0x1800df806  mov     [rsp+0D0h+var_A8], rax; __int64
0x1800df80b  lea     rax, [rbp+47h+var_88]
0x1800df80f  mov     [rsp+0D0h+var_B0], rax; __int64
0x1800df814  lea     r9, [rbp+47h+var_60]
0x1800df818  lea     r8, [rbp+47h+var_90]
0x1800df81c  xor     edx, edx
0x1800df81e  mov     rcx, [rcx+8]; __int64
0x1800df822  call    BrotliEncoderCompressStream
0x1800df827  test    eax, eax
0x1800df829  jnz     loc_1800DF8C1
0x1800df82f  lea     rax, aBrotliCompress; "Brotli compress failed"
0x1800df836  mov     [rbp+47h+var_80], rax
0x1800df83a  lea     rdx, [rbp+47h+var_80]
0x1800df83e  lea     rcx, [rbp+47h+var_50]
0x1800df842  call    ??$StringBuilder@PEBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@$$QEAPEBD@Z; arrow::util::StringBuilder<char const *>(char const * &&)
0x1800df847  nop
0x1800df848  mov     r8, rax
0x1800df84b  mov     dl, 5
0x1800df84d  lea     rcx, [rbp+47h+var_78]
0x1800df851  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800df856  nop
0x1800df857  mov     rdx, [rbp+47h+var_38]
0x1800df85b  cmp     rdx, 10h
0x1800df85f  jb      short loc_1800DF88E
0x1800df861  inc     rdx
0x1800df864  mov     rcx, [rbp+47h+var_50]
0x1800df868  mov     rax, rcx
0x1800df86b  cmp     rdx, 1000h
0x1800df872  jb      short loc_1800DF889
0x1800df874  add     rdx, 27h ; '''; unsigned __int64
0x1800df878  mov     rcx, [rcx-8]; void *
0x1800df87c  sub     rax, rcx
0x1800df87f  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800df883  cmp     rax, 1Fh
0x1800df887  ja      short loc_1800DF8FC
0x1800df889  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800df88e  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800df896  movdqu  xmmword ptr [rbp+7], xmm0
0x1800df89b  mov     byte ptr [rbp+47h+var_50], 0
0x1800df89f  lea     rdx, [rbp+47h+var_78]
0x1800df8a3  mov     rcx, rbx
0x1800df8a6  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800df8ab  nop
0x1800df8ac  mov     rcx, [rbp+47h+var_78+8]; this
0x1800df8b0  test    rcx, rcx
0x1800df8b3  jz      short loc_1800DF8E1
0x1800df8b5  mov     edx, 1; unsigned int
0x1800df8ba  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800df8bf  jmp     short loc_1800DF8E1
0x1800df8c1  sub     rdi, [rbp+47h+var_90]
0x1800df8c5  mov     [rbp+47h+var_78], rdi
0x1800df8c9  sub     rsi, [rbp+47h+var_88]
0x1800df8cd  mov     [rbp+47h+var_78+8], rsi
0x1800df8d1  mov     qword ptr [rbx+8], 0
0x1800df8d9  movups  xmm0, xmmword ptr [rbp+47h+var_78]
0x1800df8dd  movups  xmmword ptr [rbx+10h], xmm0
0x1800df8e1  mov     rax, rbx
0x1800df8e4  mov     rcx, [rbp+47h+var_30]
0x1800df8e8  xor     rcx, rsp; StackCookie
0x1800df8eb  call    __security_check_cookie
0x1800df8f0  add     rsp, 0B8h
0x1800df8f7  pop     rdi
0x1800df8f8  pop     rsi
0x1800df8f9  pop     rbx
0x1800df8fa  pop     rbp
0x1800df8fb  retn
0x1800df8fc  call    _invalid_parameter_noinfo_noreturn
```
