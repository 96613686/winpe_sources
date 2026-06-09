# ArgumentWriter::FormatArguments(wchar_t const *,wchar_t const *,std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> &)

- ea: `0x180001db0`
- end: `0x180001f37`
- name: `?FormatArguments@ArgumentWriter@@CA?AV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@PEB_W0AEAV23@@Z`
- size: `391`
- prototype: ``
- caller_count: `7`
- callee_count: `6`
- tags: ``

## callers

- `0x180001cc8`
- `0x180004994`
- `0x180004b58`
- `0x180009244`
- `0x180009c90`
- `0x180024300`
- `0x180024fac`

## callees

- `0x180001db0`
- `0x180001f38`
- `0x180003f4c`
- `0x180004544`
- `0x18000465c`
- `0x1800266e0`

## import_xrefs

- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180001f30`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180001f30`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180001ec4`
- `api-ms-win-crt-heap-l1-1-0!free` at `0x180001ec4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned __int64 __fastcall ArgumentWriter::FormatArguments(
        unsigned __int64 a1,
        unsigned __int16 *a2,
        unsigned __int16 *a3,
        _QWORD *a4)
{
  unsigned __int16 *v6; // rdi
  __m128i si128; // xmm6
  unsigned __int16 v9; // r8
  unsigned __int16 *v10; // rbp
  void *v11; // rcx
  __int64 v12; // r8
  unsigned __int64 v14[3]; // [rsp+30h] [rbp-88h] BYREF
  __int128 v15; // [rsp+48h] [rbp-70h] BYREF
  __m128i v16; // [rsp+58h] [rbp-60h]

  v6 = a2;
  v14[2] = a1;
  if ( a2 < a3 )
  {
    _mm_lfence();
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    do
    {
      v15 = 0;
      v16 = si128;
      LOWORD(v15) = 0;
      v9 = *v6;
      v10 = v6 + 1;
      v6 = v10;
      v14[0] = (unsigned __int64)v10;
      if ( v9 == 37 )
      {
        if ( v10 == a3 || *v10 != 37 )
        {
          if ( ArgumentWriter::TryParseFormatSpecificationField(v14, a3, a4, (__int64)&v15) )
            std::wstring::append(a4);
          v6 = (unsigned __int16 *)v14[0];
        }
        else
        {
          std::wstring::append(a4);
          v6 = v10 + 1;
        }
      }
      else
      {
        std::wstring::append(a4);
      }
      if ( v16.m128i_i64[1] > 7uLL )
      {
        v11 = (void *)v15;
        if ( (unsigned __int64)(2 * v16.m128i_i64[1] + 2) >= 0x1000 )
        {
          v11 = *(void **)(v15 - 8);
          if ( (unsigned __int64)(v15 - (_QWORD)v11 - 8) > 0x1F )
            _invoke_watson(0, 0, 0, 0, 0);
        }
        free(v11);
      }
    }
    while ( v6 < a3 );
  }
  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  *(_QWORD *)(a1 + 24) = 0;
  v12 = a4[2];
  if ( a4[3] > 7u )
    a4 = (_QWORD *)*a4;
  std::wstring::_Construct<2,wchar_t const *>(a1, a4, v12);
  return a1;
}

```

## disassembly

```asm
0x180001db0  push    rbx
0x180001db2  push    rbp
0x180001db3  push    rsi
0x180001db4  push    rdi
0x180001db5  push    r12
0x180001db7  push    r14
0x180001db9  push    r15
0x180001dbb  sub     rsp, 80h
0x180001dc2  movaps  [rsp+0B8h+var_48], xmm6
0x180001dc7  mov     rax, cs:__security_cookie
0x180001dce  xor     rax, rsp
0x180001dd1  mov     [rsp+0B8h+var_50], rax
0x180001dd6  mov     rbx, r9
0x180001dd9  mov     r14, r8
0x180001ddc  mov     rdi, rdx
0x180001ddf  mov     rsi, rcx
0x180001de2  mov     [rsp+0B8h+var_78], rcx
0x180001de7  xor     r15d, r15d
0x180001dea  cmp     rdx, r8
0x180001ded  jnb     loc_180001ED3
0x180001df3  lfence
0x180001df6  lea     r12d, [r15+25h]
0x180001dfa  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x180001e02  xorps   xmm0, xmm0
0x180001e05  movups  [rsp+0B8h+var_70], xmm0
0x180001e0a  movdqu  [rsp+0B8h+var_60], xmm6
0x180001e10  mov     word ptr [rsp+0B8h+var_70], r15w
0x180001e16  movzx   r8d, word ptr [rdi]
0x180001e1a  lea     rbp, [rdi+2]
0x180001e1e  mov     rdi, rbp
0x180001e21  mov     [rsp+0B8h+var_88], rbp
0x180001e26  cmp     r8w, r12w
0x180001e2a  jz      short loc_180001E3B
0x180001e2c  mov     edx, 1
0x180001e31  mov     rcx, rbx; Src
0x180001e34  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180001e39  jmp     short loc_180001E90
0x180001e3b  cmp     rbp, r14
0x180001e3e  jz      short loc_180001E5D
0x180001e40  cmp     [rbp+0], r12w
0x180001e45  jnz     short loc_180001E5D
0x180001e47  mov     r8d, r12d
0x180001e4a  mov     edx, 1
0x180001e4f  mov     rcx, rbx; Src
0x180001e52  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K_W@Z; std::wstring::append(unsigned __int64,wchar_t)
0x180001e57  lea     rdi, [rbp+2]
0x180001e5b  jmp     short loc_180001E90
0x180001e5d  lea     r9, [rsp+0B8h+var_70]
0x180001e62  mov     r8, rbx
0x180001e65  mov     rdx, r14
0x180001e68  lea     rcx, [rsp+0B8h+var_88]
0x180001e6d  call    ?TryParseFormatSpecificationField@ArgumentWriter@@CA_NAEAPEB_WPEB_WAEAV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@2@Z; ArgumentWriter::TryParseFormatSpecificationField(wchar_t const * &,wchar_t const *,std::wstring &,std::wstring &)
0x180001e72  test    al, al
0x180001e74  jz      short loc_180001E8B
0x180001e76  mov     r8d, 24h ; '$'
0x180001e7c  lea     rdx, aFormatErrorNot; "!format error: not enough arguments!"
0x180001e83  mov     rcx, rbx; Src
0x180001e86  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W_K@Z; std::wstring::append(wchar_t const * const,unsigned __int64)
0x180001e8b  mov     rdi, [rsp+0B8h+var_88]
0x180001e90  mov     rax, qword ptr [rsp+0B8h+var_60+8]
0x180001e95  cmp     rax, 7
0x180001e99  jbe     short loc_180001ECA
0x180001e9b  mov     rcx, qword ptr [rsp+0B8h+var_70]
0x180001ea0  mov     rdx, rcx
0x180001ea3  lea     rax, ds:2[rax*2]
0x180001eab  cmp     rax, 1000h
0x180001eb1  jb      short loc_180001EC4
0x180001eb3  mov     rcx, [rcx-8]; Block
0x180001eb7  sub     rdx, rcx
0x180001eba  lea     rax, [rdx-8]
0x180001ebe  cmp     rax, 1Fh
0x180001ec2  ja      short loc_180001F21
0x180001ec4  call    cs:__imp_free
0x180001eca  cmp     rdi, r14
0x180001ecd  jb      loc_180001E02
0x180001ed3  xorps   xmm0, xmm0
0x180001ed6  movups  xmmword ptr [rsi], xmm0
0x180001ed9  mov     [rsi+10h], r15
0x180001edd  mov     [rsi+18h], r15
0x180001ee1  mov     r8, [rbx+10h]
0x180001ee5  cmp     qword ptr [rbx+18h], 7
0x180001eea  jbe     short loc_180001EEF
0x180001eec  mov     rbx, [rbx]
0x180001eef  mov     rdx, rbx
0x180001ef2  mov     rcx, rsi
0x180001ef5  call    ??$_Construct@$01PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<2,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x180001efa  mov     rax, rsi
0x180001efd  mov     rcx, [rsp+0B8h+var_50]
0x180001f02  xor     rcx, rsp; StackCookie
0x180001f05  call    __security_check_cookie
0x180001f0a  movaps  xmm6, [rsp+0B8h+var_48]
0x180001f0f  add     rsp, 80h
0x180001f16  pop     r15
0x180001f18  pop     r14
0x180001f1a  pop     r12
0x180001f1c  pop     rdi
0x180001f1d  pop     rsi
0x180001f1e  pop     rbp
0x180001f1f  pop     rbx
0x180001f20  retn
0x180001f21  mov     [rsp+0B8h+Reserved], r15; Reserved
0x180001f26  xor     r9d, r9d; LineNo
0x180001f29  xor     r8d, r8d; FileName
0x180001f2c  xor     edx, edx; FunctionName
0x180001f2e  xor     ecx, ecx; Expression
0x180001f30  call    cs:__imp__invoke_watson
```
