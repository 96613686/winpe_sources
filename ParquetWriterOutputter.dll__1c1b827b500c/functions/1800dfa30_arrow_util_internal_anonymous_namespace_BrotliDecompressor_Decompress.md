# arrow::util::internal::_anonymous_namespace_::BrotliDecompressor::Decompress

- ea: `0x1800dfa30`
- end: `0x1800dfbaf`
- name: `arrow::util::internal::_anonymous_namespace_::BrotliDecompressor::Decompress`
- size: `383`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f8c0`
- `0x180059010`
- `0x18009a010`
- `0x1800df490`
- `0x1800dfa30`
- `0x180298340`
- `0x180299290`
- `0x180299420`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800dfaad`: `Brotli decompress failed: `

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::util::internal::_anonymous_namespace_::BrotliDecompressor::Decompress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  int v9; // eax
  unsigned int ErrorCode; // eax
  __int64 v11; // r8
  __int64 v12; // rdx
  unsigned __int64 v13; // rdx
  _BYTE *v14; // rcx
  __int64 v16; // [rsp+30h] [rbp-59h] BYREF
  __int64 v17; // [rsp+38h] [rbp-51h] BYREF
  const char *v18; // [rsp+40h] [rbp-49h] BYREF
  arrow::Status::State *v19[2]; // [rsp+48h] [rbp-41h] BYREF
  __int64 v20; // [rsp+58h] [rbp-31h]
  __int64 v21; // [rsp+60h] [rbp-29h] BYREF
  __int64 v22; // [rsp+68h] [rbp-21h] BYREF
  _QWORD v23[2]; // [rsp+70h] [rbp-19h] BYREF
  _BYTE *v24; // [rsp+80h] [rbp-9h] BYREF
  __m128i si128; // [rsp+90h] [rbp+7h]

  v23[1] = -2;
  v18 = (const char *)a2;
  v22 = a4;
  v21 = a6;
  v16 = a3;
  v17 = a5;
  v9 = BrotliDecoderDecompressStream(
         *(_QWORD *)(a1 + 8),
         (unsigned int)&v16,
         (unsigned int)&v22,
         (unsigned int)&v17,
         (__int64)&v21,
         0);
  if ( v9 )
  {
    v19[0] = (arrow::Status::State *)(a3 - v16);
    v19[1] = (arrow::Status::State *)(a5 - v17);
    LOBYTE(v20) = v9 == 3;
    *(_QWORD *)(a2 + 8) = 0;
    *(_OWORD *)(a2 + 16) = *(_OWORD *)v19;
    *(_QWORD *)(a2 + 32) = v20;
  }
  else
  {
    v18 = "Brotli decompress failed: ";
    ErrorCode = BrotliDecoderGetErrorCode(*(_QWORD *)(a1 + 8));
    v23[0] = BrotliDecoderErrorString(ErrorCode);
    v11 = arrow::util::StringBuilder<char const * &,char const *>(&v24, &v18, v23);
    LOBYTE(v12) = 5;
    arrow::Status::Status(v19, v12, v11);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v13 = si128.m128i_i64[1] + 1;
      v14 = v24;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v13 = si128.m128i_i64[1] + 40;
        v14 = (_BYTE *)*((_QWORD *)v24 - 1);
        if ( (unsigned __int64)(v24 - v14 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v14, v13);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v24) = 0;
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v19);
    if ( v19[1] )
      arrow::Status::State::`scalar deleting destructor'(v19[1], 1u);
  }
  return a2;
}

```

## disassembly

```asm
0x1800dfa30  push    rbp
0x1800dfa32  push    rbx
0x1800dfa33  push    rsi
0x1800dfa34  push    rdi
0x1800dfa35  push    r14
0x1800dfa37  lea     rbp, [rsp-27h]
0x1800dfa3c  sub     rsp, 0B0h
0x1800dfa43  mov     [rbp+47h+var_58], 0FFFFFFFFFFFFFFFEh
0x1800dfa4b  mov     rax, cs:__security_cookie
0x1800dfa52  xor     rax, rsp
0x1800dfa55  mov     [rbp+47h+var_30], rax
0x1800dfa59  mov     rdi, r8
0x1800dfa5c  mov     rbx, rdx
0x1800dfa5f  mov     r14, rcx
0x1800dfa62  mov     [rbp+47h+var_90], rdx
0x1800dfa66  mov     [rbp+47h+var_68], r9
0x1800dfa6a  mov     rax, [rbp+47h+arg_28]
0x1800dfa6e  mov     [rbp+47h+var_70], rax
0x1800dfa72  mov     [rbp+47h+var_A0], r8
0x1800dfa76  mov     rsi, [rbp+47h+arg_20]
0x1800dfa7a  mov     [rbp+47h+var_98], rsi
0x1800dfa7e  mov     [rsp+0D0h+var_A8], 0
0x1800dfa87  lea     rax, [rbp+47h+var_70]
0x1800dfa8b  mov     [rsp+0D0h+var_B0], rax
0x1800dfa90  lea     r9, [rbp+47h+var_98]
0x1800dfa94  lea     r8, [rbp+47h+var_68]
0x1800dfa98  lea     rdx, [rbp+47h+var_A0]
0x1800dfa9c  mov     rcx, [rcx+8]
0x1800dfaa0  call    BrotliDecoderDecompressStream
0x1800dfaa5  test    eax, eax
0x1800dfaa7  jnz     loc_1800DFB5B
0x1800dfaad  lea     rax, aBrotliDecompre; "Brotli decompress failed: "
0x1800dfab4  mov     [rbp+47h+var_90], rax
0x1800dfab8  mov     rcx, [r14+8]
0x1800dfabc  call    BrotliDecoderGetErrorCode
0x1800dfac1  mov     ecx, eax
0x1800dfac3  call    BrotliDecoderErrorString
0x1800dfac8  mov     [rbp+47h+var_60], rax
0x1800dfacc  lea     r8, [rbp+47h+var_60]
0x1800dfad0  lea     rdx, [rbp+47h+var_90]
0x1800dfad4  lea     rcx, [rbp+47h+var_50]
0x1800dfad8  call    ??$StringBuilder@AEAPEBDPEBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAPEBD$$QEAPEBD@Z; arrow::util::StringBuilder<char const * &,char const *>(char const * &,char const * &&)
0x1800dfadd  nop
0x1800dfade  mov     r8, rax
0x1800dfae1  mov     dl, 5
0x1800dfae3  lea     rcx, [rbp+47h+var_88]
0x1800dfae7  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800dfaec  nop
0x1800dfaed  mov     rdx, [rbp+47h+var_38]
0x1800dfaf1  cmp     rdx, 10h
0x1800dfaf5  jb      short loc_1800DFB28
0x1800dfaf7  inc     rdx
0x1800dfafa  mov     rcx, [rbp+47h+var_50]
0x1800dfafe  mov     rax, rcx
0x1800dfb01  cmp     rdx, 1000h
0x1800dfb08  jb      short loc_1800DFB23
0x1800dfb0a  add     rdx, 27h ; '''; unsigned __int64
0x1800dfb0e  mov     rcx, [rcx-8]; void *
0x1800dfb12  sub     rax, rcx
0x1800dfb15  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800dfb19  cmp     rax, 1Fh
0x1800dfb1d  ja      loc_1800DFBA9
0x1800dfb23  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800dfb28  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800dfb30  movdqu  xmmword ptr [rbp+7], xmm0
0x1800dfb35  mov     byte ptr [rbp+47h+var_50], 0
0x1800dfb39  lea     rdx, [rbp+47h+var_88]
0x1800dfb3d  mov     rcx, rbx
0x1800dfb40  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800dfb45  nop
0x1800dfb46  mov     rcx, [rbp+47h+var_88+8]; this
0x1800dfb4a  test    rcx, rcx
0x1800dfb4d  jz      short loc_1800DFB8C
0x1800dfb4f  mov     edx, 1; unsigned int
0x1800dfb54  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800dfb59  jmp     short loc_1800DFB8C
0x1800dfb5b  sub     rdi, [rbp+47h+var_A0]
0x1800dfb5f  mov     [rbp+47h+var_88], rdi
0x1800dfb63  sub     rsi, [rbp+47h+var_98]
0x1800dfb67  mov     [rbp+47h+var_88+8], rsi
0x1800dfb6b  cmp     eax, 3
0x1800dfb6e  setz    byte ptr [rbp+47h+var_78]
0x1800dfb72  mov     qword ptr [rbx+8], 0
0x1800dfb7a  movups  xmm0, xmmword ptr [rbp+47h+var_88]
0x1800dfb7e  movups  xmmword ptr [rbx+10h], xmm0
0x1800dfb82  movsd   xmm1, [rbp+47h+var_78]
0x1800dfb87  movsd   qword ptr [rbx+20h], xmm1
0x1800dfb8c  mov     rax, rbx
0x1800dfb8f  mov     rcx, [rbp+47h+var_30]
0x1800dfb93  xor     rcx, rsp; StackCookie
0x1800dfb96  call    __security_check_cookie
0x1800dfb9b  add     rsp, 0B0h
0x1800dfba2  pop     r14
0x1800dfba4  pop     rdi
0x1800dfba5  pop     rsi
0x1800dfba6  pop     rbx
0x1800dfba7  pop     rbp
0x1800dfba8  retn
0x1800dfba9  call    _invalid_parameter_noinfo_noreturn
```
