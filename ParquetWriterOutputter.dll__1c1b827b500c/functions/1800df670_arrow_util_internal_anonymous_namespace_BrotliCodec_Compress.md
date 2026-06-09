# arrow::util::internal::_anonymous_namespace_::BrotliCodec::Compress

- ea: `0x1800df670`
- end: `0x1800df7a4`
- name: `arrow::util::internal::_anonymous_namespace_::BrotliCodec::Compress`
- size: `308`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x1800df670`
- `0x180265110`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800df6df`: `Brotli compression failure.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::util::internal::_anonymous_namespace_::BrotliCodec::Compress(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4,
        __int64 a5,
        __int64 a6)
{
  __int64 v7; // r8
  __int64 v8; // rdx
  unsigned __int64 v9; // rdx
  _BYTE *v10; // rcx
  __int64 v12; // [rsp+40h] [rbp-58h] BYREF
  char v13[8]; // [rsp+48h] [rbp-50h] BYREF
  arrow::Status::State *v14; // [rsp+50h] [rbp-48h]
  __int64 v15; // [rsp+58h] [rbp-40h]
  _BYTE *v16; // [rsp+60h] [rbp-38h] BYREF
  __m128i si128; // [rsp+70h] [rbp-28h]

  v15 = -2;
  v12 = a5;
  if ( (unsigned int)BrotliEncoderCompress(*(_DWORD *)(a1 + 8), 22, 0, a3, a4, (__int64)&v12, a6) )
  {
    *(_QWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 16) = v12;
  }
  else
  {
    v7 = arrow::util::StringBuilder<char const (&)[13]>(&v16, "Brotli compression failure.");
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
0x1800df670  push    rbx
0x1800df672  sub     rsp, 90h
0x1800df679  mov     [rsp+98h+var_40], 0FFFFFFFFFFFFFFFEh
0x1800df682  mov     rax, cs:__security_cookie
0x1800df689  xor     rax, rsp
0x1800df68c  mov     [rsp+98h+var_18], rax
0x1800df694  mov     rbx, rdx
0x1800df697  mov     [rsp+98h+var_58], rdx
0x1800df69c  mov     rdx, [rsp+98h+arg_28]
0x1800df6a4  mov     rax, [rsp+98h+arg_20]
0x1800df6ac  mov     [rsp+98h+var_58], rax
0x1800df6b1  mov     [rsp+98h+var_68], rdx
0x1800df6b6  lea     rax, [rsp+98h+var_58]
0x1800df6bb  mov     [rsp+98h+var_70], rax
0x1800df6c0  mov     [rsp+98h+var_78], r9
0x1800df6c5  mov     r9, r8
0x1800df6c8  xor     r8d, r8d
0x1800df6cb  lea     edx, [r8+16h]
0x1800df6cf  mov     ecx, [rcx+8]
0x1800df6d2  call    BrotliEncoderCompress
0x1800df6d7  test    eax, eax
0x1800df6d9  jnz     loc_1800DF771
0x1800df6df  lea     rdx, aBrotliCompress_0; "Brotli compression failure."
0x1800df6e6  lea     rcx, [rsp+98h+var_38]
0x1800df6eb  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800df6f0  nop
0x1800df6f1  mov     r8, rax
0x1800df6f4  mov     dl, 5
0x1800df6f6  lea     rcx, [rsp+98h+var_50]
0x1800df6fb  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800df700  nop
0x1800df701  mov     rdx, [rsp+98h+var_20]
0x1800df706  cmp     rdx, 10h
0x1800df70a  jb      short loc_1800DF73A
0x1800df70c  inc     rdx
0x1800df70f  mov     rcx, [rsp+98h+var_38]
0x1800df714  mov     rax, rcx
0x1800df717  cmp     rdx, 1000h
0x1800df71e  jb      short loc_1800DF735
0x1800df720  add     rdx, 27h ; '''; unsigned __int64
0x1800df724  mov     rcx, [rcx-8]; void *
0x1800df728  sub     rax, rcx
0x1800df72b  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800df72f  cmp     rax, 1Fh
0x1800df733  ja      short loc_1800DF79E
0x1800df735  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800df73a  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800df742  movdqu  xmmword ptr [rsp+70h], xmm0
0x1800df748  mov     byte ptr [rsp+98h+var_38], 0
0x1800df74d  lea     rdx, [rsp+98h+var_50]
0x1800df752  mov     rcx, rbx
0x1800df755  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800df75a  nop
0x1800df75b  mov     rcx, [rsp+98h+var_48]; this
0x1800df760  test    rcx, rcx
0x1800df763  jz      short loc_1800DF782
0x1800df765  mov     edx, 1; unsigned int
0x1800df76a  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800df76f  jmp     short loc_1800DF782
0x1800df771  mov     qword ptr [rbx+8], 0
0x1800df779  mov     rax, [rsp+98h+var_58]
0x1800df77e  mov     [rbx+10h], rax
0x1800df782  mov     rax, rbx
0x1800df785  mov     rcx, [rsp+98h+var_18]
0x1800df78d  xor     rcx, rsp; StackCookie
0x1800df790  call    __security_check_cookie
0x1800df795  add     rsp, 90h
0x1800df79c  pop     rbx
0x1800df79d  retn
0x1800df79e  call    _invalid_parameter_noinfo_noreturn
```
