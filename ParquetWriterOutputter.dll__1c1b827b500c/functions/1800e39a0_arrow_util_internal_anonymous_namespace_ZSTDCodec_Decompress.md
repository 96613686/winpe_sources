# arrow::util::internal::_anonymous_namespace_::ZSTDCodec::Decompress

- ea: `0x1800e39a0`
- end: `0x1800e3b00`
- name: `arrow::util::internal::_anonymous_namespace_::ZSTDCodec::Decompress`
- size: `352`
- prototype: ``
- caller_count: `0`
- callee_count: `11`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x1800e39a0`
- `0x1800e4130`
- `0x1802ad410`
- `0x1802af140`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800e3a06`: `ZSTD decompression failed: `
- `0x1800e3a52`: `Corrupt ZSTD compressed data.`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall arrow::util::internal::_anonymous_namespace_::ZSTDCodec::Decompress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 *a6)
{
  __int64 *v7; // rcx
  __int64 v8; // rdi
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 v11; // rdx
  unsigned __int64 v12; // rdx
  _BYTE *v13; // rcx
  __int64 v15; // [rsp+20h] [rbp-48h] BYREF
  arrow::Status::State *v16; // [rsp+28h] [rbp-40h]
  __int64 v17; // [rsp+30h] [rbp-38h]
  _BYTE *v18; // [rsp+38h] [rbp-30h] BYREF
  __m128i si128; // [rsp+48h] [rbp-20h]

  v17 = -2;
  v15 = a2;
  v7 = &`arrow::util::internal::`anonymous namespace'::ZSTDCodec::Decompress'::`5'::empty_buffer;
  if ( a6 )
    v7 = a6;
  v8 = ZSTD_decompress(v7, a5, a4, a3, v15);
  if ( (unsigned int)ZSTD_isError(v8) )
  {
    v9 = arrow::util::internal::_anonymous_namespace_::ZSTDError(&v15, v8, "ZSTD decompression failed: ");
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, v9);
  }
  else
  {
    if ( v8 == a5 )
    {
      *(_QWORD *)(a2 + 8) = 0;
      *(_QWORD *)(a2 + 16) = v8;
      return a2;
    }
    v10 = arrow::util::StringBuilder<char const (&)[13]>(&v18, "Corrupt ZSTD compressed data.");
    LOBYTE(v11) = 5;
    arrow::Status::Status(&v15, v11, v10);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v12 = si128.m128i_i64[1] + 1;
      v13 = v18;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v12 = si128.m128i_i64[1] + 40;
        v13 = (_BYTE *)*((_QWORD *)v18 - 1);
        if ( (unsigned __int64)(v18 - v13 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v13, v12);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v18) = 0;
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, &v15);
  }
  if ( v16 )
    arrow::Status::State::`scalar deleting destructor'(v16, 1u);
  return a2;
}

```

## disassembly

```asm
0x1800e39a0  push    rdi
0x1800e39a2  sub     rsp, 60h
0x1800e39a6  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800e39af  mov     [rsp+68h+arg_0], rbx
0x1800e39b4  mov     rax, cs:__security_cookie
0x1800e39bb  xor     rax, rsp
0x1800e39be  mov     [rsp+68h+var_10], rax
0x1800e39c3  mov     r10, r9
0x1800e39c6  mov     rbx, rdx
0x1800e39c9  mov     rax, [rsp+68h+arg_28]
0x1800e39d1  mov     [rsp+68h+var_48], rdx
0x1800e39d6  lea     rcx, ?empty_buffer@?4??Decompress@ZSTDCodec@?A0xa77fb3b7@internal@util@arrow@@UEAA?AV?$Result@_J@6@_JPEBE0PEAE@Z@4PAEA; uchar near * `arrow::util::internal::`anonymous namespace'::ZSTDCodec::Decompress(__int64,uchar const *,__int64,uchar *)'::`5'::empty_buffer
0x1800e39dd  test    rax, rax
0x1800e39e0  cmovnz  rcx, rax
0x1800e39e4  mov     r9, r8
0x1800e39e7  mov     r8, r10
0x1800e39ea  mov     rdx, [rsp+68h+arg_20]
0x1800e39f2  call    ZSTD_decompress
0x1800e39f7  mov     rdi, rax
0x1800e39fa  mov     rcx, rax
0x1800e39fd  call    ZSTD_isError
0x1800e3a02  test    eax, eax
0x1800e3a04  jz      short loc_1800E3A44
0x1800e3a06  lea     r8, aZstdDecompress; "ZSTD decompression failed: "
0x1800e3a0d  mov     rdx, rdi
0x1800e3a10  lea     rcx, [rsp+68h+var_48]
0x1800e3a15  call    arrow__util__internal___anonymous_namespace___ZSTDError
0x1800e3a1a  nop
0x1800e3a1b  mov     rdx, rax
0x1800e3a1e  mov     rcx, rbx
0x1800e3a21  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e3a26  nop
0x1800e3a27  mov     rcx, [rsp+68h+var_40]; this
0x1800e3a2c  test    rcx, rcx
0x1800e3a2f  jz      loc_1800E3ADF
0x1800e3a35  mov     edx, 1; unsigned int
0x1800e3a3a  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e3a3f  jmp     loc_1800E3ADF
0x1800e3a44  cmp     rdi, [rsp+68h+arg_20]
0x1800e3a4c  jz      loc_1800E3AD3
0x1800e3a52  lea     rdx, aCorruptZstdCom; "Corrupt ZSTD compressed data."
0x1800e3a59  lea     rcx, [rsp+68h+var_30]
0x1800e3a5e  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800e3a63  nop
0x1800e3a64  mov     r8, rax
0x1800e3a67  mov     dl, 5
0x1800e3a69  lea     rcx, [rsp+68h+var_48]
0x1800e3a6e  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800e3a73  nop
0x1800e3a74  mov     rdx, [rsp+68h+var_18]
0x1800e3a79  cmp     rdx, 10h
0x1800e3a7d  jb      short loc_1800E3AAD
0x1800e3a7f  inc     rdx
0x1800e3a82  mov     rcx, [rsp+68h+var_30]
0x1800e3a87  mov     rax, rcx
0x1800e3a8a  cmp     rdx, 1000h
0x1800e3a91  jb      short loc_1800E3AA8
0x1800e3a93  add     rdx, 27h ; '''; unsigned __int64
0x1800e3a97  mov     rcx, [rcx-8]; void *
0x1800e3a9b  sub     rax, rcx
0x1800e3a9e  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e3aa2  cmp     rax, 1Fh
0x1800e3aa6  ja      short loc_1800E3AFA
0x1800e3aa8  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e3aad  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800e3ab5  movdqu  xmmword ptr [rsp+48h], xmm0
0x1800e3abb  mov     byte ptr [rsp+68h+var_30], 0
0x1800e3ac0  lea     rdx, [rsp+68h+var_48]
0x1800e3ac5  mov     rcx, rbx
0x1800e3ac8  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e3acd  nop
0x1800e3ace  jmp     loc_1800E3A27
0x1800e3ad3  mov     qword ptr [rbx+8], 0
0x1800e3adb  mov     [rbx+10h], rdi
0x1800e3adf  mov     rax, rbx
0x1800e3ae2  mov     rcx, [rsp+68h+var_10]
0x1800e3ae7  xor     rcx, rsp; StackCookie
0x1800e3aea  call    __security_check_cookie
0x1800e3aef  mov     rbx, [rsp+68h+arg_0]
0x1800e3af4  add     rsp, 60h
0x1800e3af8  pop     rdi
0x1800e3af9  retn
0x1800e3afa  call    _invalid_parameter_noinfo_noreturn
```
