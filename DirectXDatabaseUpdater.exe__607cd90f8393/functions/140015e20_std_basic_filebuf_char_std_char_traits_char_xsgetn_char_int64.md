# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x140015e20`
- end: `0x140015f09`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `233`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x140003aa0`
- `0x140015490`
- `0x140015e20`

## import_xrefs

- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x140015e6a`
- `msvcp_win!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x140015e6a`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x140015e8c`
- `msvcp_win!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x140015e8c`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x140015e52`
- `msvcp_win!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x140015e52`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x140015e47`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x140015e47`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140015ec5`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140015eef`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140015ec5`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x140015eef`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  unsigned __int64 v7; // rax
  size_t v8; // rbx
  const void *v9; // rax
  size_t v10; // rsi
  size_t v11; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsgetn();
  v7 = std::streambuf::_Gnavail();
  if ( v7 )
  {
    v8 = a3;
    if ( v7 < a3 )
      v8 = v7;
    v9 = (const void *)std::streambuf::gptr(a1);
    memcpy_0(a2, v9, v8);
    a2 += v8;
    v10 = a3 - v8;
    std::streambuf::gbump(a1, (unsigned int)v8);
  }
  else
  {
    v10 = a3;
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::filebuf::_Reset_back(a1);
    while ( v10 > 0xFFF )
    {
      v11 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
      a2 += v11;
      v10 -= v11;
      if ( v11 != 4095 )
        return a3 - v10;
    }
    if ( v10 )
      v10 -= fread(a2, 1u, v10, *(FILE **)(a1 + 128));
  }
  return a3 - v10;
}

```

## disassembly

```asm
0x140015e20  push    rbx
0x140015e22  push    rbp
0x140015e23  push    rsi
0x140015e24  push    rdi
0x140015e25  push    r14
0x140015e27  sub     rsp, 20h
0x140015e2b  mov     rdi, r8
0x140015e2e  mov     r14, rdx
0x140015e31  mov     rbp, rcx
0x140015e34  test    r8, r8
0x140015e37  jg      short loc_140015E40
0x140015e39  xor     eax, eax
0x140015e3b  jmp     loc_140015EFE
0x140015e40  cmp     qword ptr [rcx+68h], 0
0x140015e45  jz      short loc_140015E52
0x140015e47  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x140015e4d  jmp     loc_140015EFE
0x140015e52  call    cs:__imp_?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Gnavail(void)
0x140015e58  test    rax, rax
0x140015e5b  jz      short loc_140015E94
0x140015e5d  cmp     rax, rdi
0x140015e60  mov     rbx, rdi
0x140015e63  mov     rcx, rbp
0x140015e66  cmovb   rbx, rax
0x140015e6a  call    cs:__imp_?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::gptr(void)
0x140015e70  mov     r8, rbx; Size
0x140015e73  mov     rcx, r14; void *
0x140015e76  mov     rdx, rax; Src
0x140015e79  call    memcpy_0
0x140015e7e  mov     rsi, rdi
0x140015e81  add     r14, rbx
0x140015e84  sub     rsi, rbx
0x140015e87  mov     edx, ebx
0x140015e89  mov     rcx, rbp
0x140015e8c  call    cs:__imp_?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::gbump(int)
0x140015e92  jmp     short loc_140015E97
0x140015e94  mov     rsi, rdi
0x140015e97  cmp     qword ptr [rbp+80h], 0
0x140015e9f  jz      short loc_140015EF8
0x140015ea1  mov     rcx, rbp
0x140015ea4  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x140015ea9  mov     ebx, 0FFFh
0x140015eae  cmp     rsi, rbx
0x140015eb1  jbe     short loc_140015ED8
0x140015eb3  mov     r9, [rbp+80h]; Stream
0x140015eba  mov     r8, rbx; ElementCount
0x140015ebd  mov     edx, 1; ElementSize
0x140015ec2  mov     rcx, r14; Buffer
0x140015ec5  call    cs:__imp_fread
0x140015ecb  add     r14, rax
0x140015ece  sub     rsi, rax
0x140015ed1  cmp     rax, rbx
0x140015ed4  jz      short loc_140015EAE
0x140015ed6  jmp     short loc_140015EF8
0x140015ed8  test    rsi, rsi
0x140015edb  jz      short loc_140015EF8
0x140015edd  mov     r9, [rbp+80h]; Stream
0x140015ee4  mov     r8, rsi; ElementCount
0x140015ee7  mov     edx, 1; ElementSize
0x140015eec  mov     rcx, r14; Buffer
0x140015eef  call    cs:__imp_fread
0x140015ef5  sub     rsi, rax
0x140015ef8  sub     rdi, rsi
0x140015efb  mov     rax, rdi
0x140015efe  add     rsp, 20h
0x140015f02  pop     r14
0x140015f04  pop     rdi
0x140015f05  pop     rsi
0x140015f06  pop     rbp
0x140015f07  pop     rbx
0x140015f08  retn
```
