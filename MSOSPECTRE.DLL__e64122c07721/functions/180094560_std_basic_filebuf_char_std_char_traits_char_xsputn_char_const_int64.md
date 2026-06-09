# std::basic_filebuf<char,std::char_traits<char>>::xsputn(char const *,__int64)

- ea: `0x180094560`
- end: `0x180094618`
- name: `?xsputn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z`
- size: `184`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180094560`
- `0x18039f8f0`

## import_xrefs

- `MSVCP140!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800945ce`
- `MSVCP140!?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800945ce`
- `MSVCP140!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x180094595`
- `MSVCP140!?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x180094595`
- `MSVCP140!?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z` at `0x180094581`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800945b2`
- `MSVCP140!?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800945b2`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x1800945f6`
- `api-ms-win-crt-stdio-l1-1-0!fwrite` at `0x1800945f6`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsputn(__int64 a1, char *a2, signed __int64 a3)
{
  signed __int64 v3; // rbx
  __int64 v8; // rax
  size_t v9; // rbp
  void *v10; // rax
  FILE *v11; // r9

  v3 = a3;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsputn();
  v8 = std::streambuf::_Pnavail();
  v9 = v8;
  if ( v3 > 0 )
  {
    if ( v8 <= 0 )
      goto LABEL_8;
    if ( v3 < v8 )
      v9 = v3;
    v10 = (void *)std::streambuf::pptr(a1);
    memcpy_0(v10, a2, v9);
    v3 -= v9;
    std::streambuf::pbump(a1, (unsigned int)v9);
    a2 += v9;
    if ( v3 > 0 )
    {
LABEL_8:
      v11 = *(FILE **)(a1 + 128);
      if ( v11 )
      {
        _mm_lfence();
        v3 -= fwrite(a2, 1u, v3, v11);
      }
    }
  }
  return a3 - v3;
}

```

## disassembly

```asm
0x180094560  push    rbx
0x180094562  push    rdi
0x180094563  push    r14
0x180094565  sub     rsp, 20h
0x180094569  cmp     qword ptr [rcx+68h], 0
0x18009456e  mov     rbx, r8
0x180094571  mov     r14, rdx
0x180094574  mov     rdi, rcx
0x180094577  jz      short loc_180094588
0x180094579  add     rsp, 20h
0x18009457d  pop     r14
0x18009457f  pop     rdi
0x180094580  pop     rbx
0x180094581  jmp     cs:__imp_?xsputn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEBD_J@Z; std::streambuf::xsputn(char const *,__int64)
0x180094588  mov     [rsp+38h+arg_0], rbp
0x18009458d  mov     [rsp+38h+arg_8], rsi
0x180094592  mov     rsi, rbx
0x180094595  call    cs:__imp_?_Pnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Pnavail(void)
0x18009459b  mov     rbp, rax
0x18009459e  test    rbx, rbx
0x1800945a1  jle     short loc_1800945FF
0x1800945a3  test    rax, rax
0x1800945a6  jle     short loc_1800945DC
0x1800945a8  cmp     rbx, rax
0x1800945ab  mov     rcx, rdi
0x1800945ae  cmovl   rbp, rbx
0x1800945b2  call    cs:__imp_?pptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::pptr(void)
0x1800945b8  mov     r8, rbp; Size
0x1800945bb  mov     rdx, r14; Src
0x1800945be  mov     rcx, rax; void *
0x1800945c1  call    memcpy_0
0x1800945c6  mov     edx, ebp
0x1800945c8  mov     rcx, rdi
0x1800945cb  sub     rbx, rbp
0x1800945ce  call    cs:__imp_?pbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::pbump(int)
0x1800945d4  add     r14, rbp
0x1800945d7  test    rbx, rbx
0x1800945da  jle     short loc_1800945FF
0x1800945dc  mov     r9, [rdi+80h]; Stream
0x1800945e3  test    r9, r9
0x1800945e6  jz      short loc_1800945FF
0x1800945e8  lfence
0x1800945eb  mov     r8, rbx; ElementCount
0x1800945ee  mov     edx, 1; ElementSize
0x1800945f3  mov     rcx, r14; Buffer
0x1800945f6  call    cs:__imp_fwrite
0x1800945fc  sub     rbx, rax
0x1800945ff  mov     rbp, [rsp+38h+arg_0]
0x180094604  sub     rsi, rbx
0x180094607  mov     rax, rsi
0x18009460a  mov     rsi, [rsp+38h+arg_8]
0x18009460f  add     rsp, 20h
0x180094613  pop     r14
0x180094615  pop     rdi
0x180094616  pop     rbx
0x180094617  retn
```
