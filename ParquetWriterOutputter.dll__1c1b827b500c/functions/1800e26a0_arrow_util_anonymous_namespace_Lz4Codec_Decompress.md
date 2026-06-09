# arrow::util::_anonymous_namespace_::Lz4Codec::Decompress

- ea: `0x1800e26a0`
- end: `0x1800e27a3`
- name: `arrow::util::_anonymous_namespace_::Lz4Codec::Decompress`
- size: `259`
- prototype: ``
- caller_count: `0`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004f80`
- `0x18001f8c0`
- `0x180059010`
- `0x180086ed0`
- `0x18009a010`
- `0x1800e26a0`
- `0x18030c180`
- `0x18030c3f0`
- `0x180334640`

## string_xrefs

- `0x1800e26e9`: `Corrupt Lz4 compressed data.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall arrow::util::_anonymous_namespace_::Lz4Codec::Decompress(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        unsigned int a5,
        __int64 a6)
{
  int v7; // eax
  __int64 v8; // r8
  __int64 v9; // rdx
  unsigned __int64 v10; // rdx
  _BYTE *v11; // rcx
  __int64 v13; // [rsp+20h] [rbp-48h] BYREF
  arrow::Status::State *v14; // [rsp+28h] [rbp-40h]
  __int64 v15; // [rsp+30h] [rbp-38h]
  _BYTE *v16; // [rsp+38h] [rbp-30h] BYREF
  __m128i si128; // [rsp+48h] [rbp-20h]

  v15 = -2;
  v7 = LZ4_decompress_safe(a4, a6, a3, a5, a2);
  if ( v7 >= 0 )
  {
    *(_QWORD *)(a2 + 8) = 0;
    *(_QWORD *)(a2 + 16) = v7;
  }
  else
  {
    v8 = arrow::util::StringBuilder<char const (&)[13]>(&v16, "Corrupt Lz4 compressed data.");
    LOBYTE(v9) = 5;
    arrow::Status::Status(&v13, v9, v8);
    if ( si128.m128i_i64[1] >= 0x10uLL )
    {
      v10 = si128.m128i_i64[1] + 1;
      v11 = v16;
      if ( (unsigned __int64)(si128.m128i_i64[1] + 1) >= 0x1000 )
      {
        v10 = si128.m128i_i64[1] + 40;
        v11 = (_BYTE *)*((_QWORD *)v16 - 1);
        if ( (unsigned __int64)(v16 - v11 - 8) > 0x1F )
          invalid_parameter_noinfo_noreturn();
      }
      operator delete(v11, v10);
    }
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    LOBYTE(v16) = 0;
    arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(a2, &v13);
    if ( v14 )
      arrow::Status::State::`scalar deleting destructor'(v14, 1u);
  }
  return a2;
}

```

## disassembly

```asm
0x1800e26a0  push    rbx
0x1800e26a2  sub     rsp, 60h
0x1800e26a6  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh
0x1800e26af  mov     rax, cs:__security_cookie
0x1800e26b6  xor     rax, rsp
0x1800e26b9  mov     [rsp+68h+var_10], rax
0x1800e26be  mov     rcx, r9
0x1800e26c1  mov     rbx, rdx
0x1800e26c4  mov     [rsp+68h+var_48], rdx
0x1800e26c9  mov     rdx, [rsp+68h+arg_28]
0x1800e26d1  mov     r9d, [rsp+68h+arg_20]
0x1800e26d9  call    LZ4_decompress_safe
0x1800e26de  movsxd  rcx, eax
0x1800e26e1  test    eax, eax
0x1800e26e3  jns     loc_1800E277B
0x1800e26e9  lea     rdx, aCorruptLz4Comp; "Corrupt Lz4 compressed data."
0x1800e26f0  lea     rcx, [rsp+68h+var_30]
0x1800e26f5  call    ??$StringBuilder@AEAY0N@$$CBD@util@arrow@@YA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAY0N@$$CBD@Z; arrow::util::StringBuilder<char const (&)[13]>(char const (&)[13])
0x1800e26fa  nop
0x1800e26fb  mov     r8, rax
0x1800e26fe  mov     dl, 5
0x1800e2700  lea     rcx, [rsp+68h+var_48]
0x1800e2705  call    ??0Status@arrow@@QEAA@W4StatusCode@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@Z; arrow::Status::Status(arrow::StatusCode,std::string const &)
0x1800e270a  nop
0x1800e270b  mov     rdx, [rsp+68h+var_18]
0x1800e2710  cmp     rdx, 10h
0x1800e2714  jb      short loc_1800E2744
0x1800e2716  inc     rdx
0x1800e2719  mov     rcx, [rsp+68h+var_30]
0x1800e271e  mov     rax, rcx
0x1800e2721  cmp     rdx, 1000h
0x1800e2728  jb      short loc_1800E273F
0x1800e272a  add     rdx, 27h ; '''; unsigned __int64
0x1800e272e  mov     rcx, [rcx-8]; void *
0x1800e2732  sub     rax, rcx
0x1800e2735  add     rax, 0FFFFFFFFFFFFFFF8h
0x1800e2739  cmp     rax, 1Fh
0x1800e273d  ja      short loc_1800E279D
0x1800e273f  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800e2744  movdqa  xmm0, cs:__xmm@000000000000000f0000000000000000
0x1800e274c  movdqu  xmmword ptr [rsp+48h], xmm0
0x1800e2752  mov     byte ptr [rsp+68h+var_30], 0
0x1800e2757  lea     rdx, [rsp+68h+var_48]
0x1800e275c  mov     rcx, rbx
0x1800e275f  call    ??0?$Result@VDecimal128@arrow@@@arrow@@QEAA@AEBVStatus@1@@Z; arrow::Result<arrow::Decimal128>::Result<arrow::Decimal128>(arrow::Status const &)
0x1800e2764  nop
0x1800e2765  mov     rcx, [rsp+68h+var_40]; this
0x1800e276a  test    rcx, rcx
0x1800e276d  jz      short loc_1800E2787
0x1800e276f  mov     edx, 1; unsigned int
0x1800e2774  call    ??_GState@Status@arrow@@QEAAPEAXI@Z; arrow::Status::State::`scalar deleting destructor'(uint)
0x1800e2779  jmp     short loc_1800E2787
0x1800e277b  mov     qword ptr [rbx+8], 0
0x1800e2783  mov     [rbx+10h], rcx
0x1800e2787  mov     rax, rbx
0x1800e278a  mov     rcx, [rsp+68h+var_10]
0x1800e278f  xor     rcx, rsp; StackCookie
0x1800e2792  call    __security_check_cookie
0x1800e2797  add     rsp, 60h
0x1800e279b  pop     rbx
0x1800e279c  retn
0x1800e279d  call    _invalid_parameter_noinfo_noreturn
```
