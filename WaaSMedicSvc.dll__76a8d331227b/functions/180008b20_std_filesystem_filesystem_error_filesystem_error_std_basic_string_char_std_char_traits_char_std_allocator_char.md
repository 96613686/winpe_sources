# std::filesystem::filesystem_error::filesystem_error(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,std::filesystem::path const &,std::error_code)

- ea: `0x180008b20`
- end: `0x180008bf8`
- name: `??0filesystem_error@filesystem@std@@QEAA@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@2@AEBVpath@12@Verror_code@2@@Z`
- size: `216`
- prototype: `__int64 __fastcall(__int64, __int64, const struct std::filesystem::path *, __int128 *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000b2a0`

## callees

- `0x180002200`
- `0x180008794`
- `0x180008b20`
- `0x180008c00`
- `0x180008f20`
- `0x18000ae6c`

## pseudocode

```c
__int64 __fastcall std::filesystem::filesystem_error::filesystem_error(
        __int64 a1,
        __int64 a2,
        const struct std::filesystem::path *a3,
        __int128 *a4)
{
  const char *v6; // rax
  __int64 v7; // rcx
  __int128 v9; // [rsp+20h] [rbp-50h] BYREF
  __int64 v10; // [rsp+30h] [rbp-40h]
  _OWORD v11[2]; // [rsp+40h] [rbp-30h] BYREF

  v10 = a1;
  v9 = *a4;
  std::_System_error::_System_error(a1, &v9, a2);
  *(_QWORD *)a1 = &std::filesystem::filesystem_error::`vftable';
  std::filesystem::path::path((std::filesystem::path *)(a1 + 40), a3);
  *(_OWORD *)(a1 + 72) = 0;
  *(_QWORD *)(a1 + 88) = 0;
  *(_QWORD *)(a1 + 96) = 7;
  *(_WORD *)(a1 + 72) = 0;
  v11[0] = 0;
  v11[1] = _mm_load_si128((const __m128i *)&_xmm);
  LOWORD(v11[0]) = 0;
  v6 = "Unknown exception";
  if ( *(_QWORD *)(a1 + 8) )
    v6 = *(const char **)(a1 + 8);
  v7 = -1;
  do
    ++v7;
  while ( v6[v7] );
  *(_QWORD *)&v9 = v6;
  *((_QWORD *)&v9 + 1) = v7;
  std::filesystem::filesystem_error::_Pretty_message((void *)(a1 + 104));
  std::wstring::~wstring(v11);
  return a1;
}

```

## disassembly

```asm
0x180008b20  push    rbp
0x180008b22  push    rbx
0x180008b23  push    rdi
0x180008b24  mov     rbp, rsp
0x180008b27  sub     rsp, 70h
0x180008b2b  mov     rax, cs:__security_cookie
0x180008b32  xor     rax, rsp
0x180008b35  mov     [rbp+var_10], rax
0x180008b39  mov     rdi, r8
0x180008b3c  mov     rbx, rcx
0x180008b3f  mov     [rbp+var_40], rcx
0x180008b43  movaps  xmm0, xmmword ptr [r9]
0x180008b47  movdqa  [rbp+var_50], xmm0
0x180008b4c  mov     r8, rdx
0x180008b4f  lea     rdx, [rbp+var_50]
0x180008b53  call    ??0_System_error@std@@IEAA@Verror_code@1@AEBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@1@@Z; std::_System_error::_System_error(std::error_code,std::string const &)
0x180008b58  nop
0x180008b59  lea     rax, ??_7filesystem_error@filesystem@std@@6B@; const std::filesystem::filesystem_error::`vftable'
0x180008b60  mov     [rbx], rax
0x180008b63  lea     rcx, [rbx+28h]; this
0x180008b67  mov     rdx, rdi; struct std::filesystem::path *
0x180008b6a  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x180008b6f  nop
0x180008b70  xorps   xmm0, xmm0
0x180008b73  movups  xmmword ptr [rbx+48h], xmm0
0x180008b77  xor     edx, edx
0x180008b79  mov     [rbx+58h], rdx
0x180008b7d  mov     qword ptr [rbx+60h], 7
0x180008b85  mov     [rbx+48h], dx
0x180008b89  movups  [rbp+var_30], xmm0
0x180008b8d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x180008b95  movdqu  [rbp+var_20], xmm1
0x180008b9a  mov     word ptr [rbp+var_30], dx
0x180008b9e  lea     rax, aUnknownExcepti; "Unknown exception"
0x180008ba5  cmp     [rbx+8], rdx
0x180008ba9  cmovnz  rax, [rbx+8]
0x180008bae  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180008bb2  inc     rcx
0x180008bb5  cmp     [rax+rcx], dl
0x180008bb8  jnz     short loc_180008BB2
0x180008bba  mov     qword ptr [rbp+var_50], rax
0x180008bbe  mov     qword ptr [rbp+var_50+8], rcx
0x180008bc2  lea     rcx, [rbx+68h]; Src
0x180008bc6  lea     r9, [rbp+var_30]
0x180008bca  mov     r8, rdi
0x180008bcd  lea     rdx, [rbp+var_50]
0x180008bd1  call    ?_Pretty_message@filesystem_error@filesystem@std@@CA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@3@V?$basic_string_view@DU?$char_traits@D@std@@@3@AEBVpath@23@1@Z; std::filesystem::filesystem_error::_Pretty_message(std::string_view,std::filesystem::path const &,std::filesystem::path const &)
0x180008bd6  nop
0x180008bd7  lea     rcx, [rbp+var_30]
0x180008bdb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x180008be0  nop
0x180008be1  mov     rax, rbx
0x180008be4  mov     rcx, [rbp+var_10]
0x180008be8  xor     rcx, rsp; StackCookie
0x180008beb  call    __security_check_cookie
0x180008bf0  add     rsp, 70h
0x180008bf4  pop     rdi
0x180008bf5  pop     rbx
0x180008bf6  pop     rbp
0x180008bf7  retn
```
