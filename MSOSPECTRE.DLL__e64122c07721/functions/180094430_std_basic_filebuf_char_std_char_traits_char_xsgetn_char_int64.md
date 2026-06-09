# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x180094430`
- end: `0x180094560`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `304`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800935f0`
- `0x180094430`
- `0x18039f8f0`

## import_xrefs

- `MSVCP140!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x18009448a`
- `MSVCP140!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x18009448a`
- `MSVCP140!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x18009447b`
- `MSVCP140!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800944c9`
- `MSVCP140!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1800944c9`
- `MSVCP140!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800944aa`
- `MSVCP140!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1800944aa`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x180094505`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x180094538`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x180094505`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x180094538`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  __int64 result; // rax
  size_t v7; // rbx
  unsigned __int64 v8; // rax
  size_t v9; // rdi
  const void *v10; // rax
  size_t v11; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
  {
    _mm_lfence();
    return std::streambuf::xsgetn();
  }
  else
  {
    v7 = a3;
    v8 = std::streambuf::_Gnavail();
    if ( v8 )
    {
      _mm_lfence();
      v9 = a3;
      if ( v8 < a3 )
        v9 = v8;
      v10 = (const void *)std::streambuf::gptr(a1);
      memcpy_0(a2, v10, v9);
      a2 += v9;
      v7 = a3 - v9;
      std::streambuf::gbump(a1, (unsigned int)v9);
    }
    if ( *(_QWORD *)(a1 + 128) )
    {
      std::filebuf::_Reset_back(a1);
      if ( v7 <= 0xFFF )
      {
LABEL_13:
        if ( v7 )
        {
          _mm_lfence();
          v7 -= fread(a2, 1u, v7, *(FILE **)(a1 + 128));
        }
      }
      else
      {
        while ( 1 )
        {
          v11 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
          a2 += v11;
          v7 -= v11;
          if ( v11 != 4095 )
            break;
          if ( v7 <= 0xFFF )
            goto LABEL_13;
        }
      }
    }
    result = a3 - v7;
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x180094430  mov     [rsp+arg_10], rbp
0x180094435  mov     [rsp+arg_18], rsi
0x18009443a  push    r14
0x18009443c  sub     rsp, 20h
0x180094440  mov     rsi, r8
0x180094443  mov     rbp, rdx
0x180094446  mov     r14, rcx
0x180094449  test    r8, r8
0x18009444c  jg      short loc_180094461
0x18009444e  xor     eax, eax
0x180094450  mov     rbp, [rsp+28h+arg_10]
0x180094455  mov     rsi, [rsp+28h+arg_18]
0x18009445a  add     rsp, 20h
0x18009445e  pop     r14
0x180094460  retn
0x180094461  cmp     qword ptr [rcx+68h], 0
0x180094466  jz      short loc_180094482
0x180094468  lfence
0x18009446b  mov     rbp, [rsp+28h+arg_10]
0x180094470  mov     rsi, [rsp+28h+arg_18]
0x180094475  add     rsp, 20h
0x180094479  pop     r14
0x18009447b  jmp     cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x180094482  mov     [rsp+28h+arg_0], rbx
0x180094487  mov     rbx, rsi
0x18009448a  call    cs:__imp_?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Gnavail(void)
0x180094490  test    rax, rax
0x180094493  jz      short loc_1800944D4
0x180094495  mov     [rsp+28h+arg_8], rdi
0x18009449a  lfence
0x18009449d  cmp     rax, rsi
0x1800944a0  mov     rdi, rsi
0x1800944a3  mov     rcx, r14
0x1800944a6  cmovb   rdi, rax
0x1800944aa  call    cs:__imp_?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::gptr(void)
0x1800944b0  mov     r8, rdi; Size
0x1800944b3  mov     rcx, rbp; void *
0x1800944b6  mov     rdx, rax; Src
0x1800944b9  call    memcpy_0
0x1800944be  mov     edx, edi
0x1800944c0  mov     rcx, r14
0x1800944c3  add     rbp, rdi
0x1800944c6  sub     rbx, rdi
0x1800944c9  call    cs:__imp_?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::gbump(int)
0x1800944cf  mov     rdi, [rsp+28h+arg_8]
0x1800944d4  cmp     qword ptr [r14+80h], 0
0x1800944dc  jz      short loc_180094541
0x1800944de  mov     rcx, r14
0x1800944e1  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1800944e6  cmp     rbx, 0FFFh
0x1800944ed  jbe     short loc_18009451E
0x1800944ef  nop
0x1800944f0  mov     r9, [r14+80h]; Stream
0x1800944f7  mov     edx, 1; ElementSize
0x1800944fc  mov     r8d, 0FFFh; ElementCount
0x180094502  mov     rcx, rbp; Buffer
0x180094505  call    cs:__imp_fread
0x18009450b  add     rbp, rax
0x18009450e  sub     rbx, rax
0x180094511  cmp     rax, 0FFFh
0x180094517  jnz     short loc_180094541
0x180094519  cmp     rbx, rax
0x18009451c  ja      short loc_1800944F0
0x18009451e  test    rbx, rbx
0x180094521  jz      short loc_180094541
0x180094523  lfence
0x180094526  mov     r9, [r14+80h]; Stream
0x18009452d  mov     r8, rbx; ElementCount
0x180094530  mov     edx, 1; ElementSize
0x180094535  mov     rcx, rbp; Buffer
0x180094538  call    cs:__imp_fread
0x18009453e  sub     rbx, rax
0x180094541  sub     rsi, rbx
0x180094544  mov     rax, rsi
0x180094547  lfence
0x18009454a  mov     rbx, [rsp+28h+arg_0]
0x18009454f  mov     rbp, [rsp+28h+arg_10]
0x180094554  mov     rsi, [rsp+28h+arg_18]
0x180094559  add     rsp, 20h
0x18009455d  pop     r14
0x18009455f  retn
```
