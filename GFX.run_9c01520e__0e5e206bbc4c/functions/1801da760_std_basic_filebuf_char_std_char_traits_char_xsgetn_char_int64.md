# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x1801da760`
- end: `0x1801da862`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180056300`
- `0x1801d9e40`
- `0x1801da760`

## import_xrefs

- `MSVCP140!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1801da7bb`
- `MSVCP140!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1801da7bb`
- `MSVCP140!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1801da795`
- `MSVCP140!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1801da795`
- `MSVCP140!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1801da7da`
- `MSVCP140!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1801da7da`
- `MSVCP140!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1801da7a3`
- `MSVCP140!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1801da7a3`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1801da80e`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1801da838`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1801da80e`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1801da838`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  size_t v7; // rsi
  unsigned __int64 v8; // rax
  size_t v9; // rbx
  const void *v10; // rax
  size_t v11; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsgetn();
  v7 = a3;
  v8 = std::streambuf::_Gnavail();
  if ( v8 )
  {
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
    while ( v7 > 0xFFF )
    {
      v11 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
      a2 += v11;
      v7 -= v11;
      if ( v11 != 4095 )
        return a3 - v7;
    }
    if ( v7 )
      v7 -= fread(a2, 1u, v7, *(FILE **)(a1 + 128));
  }
  return a3 - v7;
}

```

## disassembly

```asm
0x1801da760  mov     rax, rsp
0x1801da763  mov     [rax+8], rbx
0x1801da767  mov     [rax+10h], rbp
0x1801da76b  mov     [rax+18h], rsi
0x1801da76f  mov     [rax+20h], rdi
0x1801da773  push    r14
0x1801da775  sub     rsp, 20h
0x1801da779  mov     rdi, r8
0x1801da77c  mov     r14, rdx
0x1801da77f  mov     rbp, rcx
0x1801da782  test    r8, r8
0x1801da785  jg      short loc_1801DA78E
0x1801da787  xor     eax, eax
0x1801da789  jmp     loc_1801DA847
0x1801da78e  cmp     qword ptr [rcx+68h], 0
0x1801da793  jz      short loc_1801DA7A0
0x1801da795  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x1801da79b  jmp     loc_1801DA847
0x1801da7a0  mov     rsi, rdi
0x1801da7a3  call    cs:__imp_?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Gnavail(void)
0x1801da7a9  test    rax, rax
0x1801da7ac  jz      short loc_1801DA7E0
0x1801da7ae  cmp     rax, rdi
0x1801da7b1  mov     rbx, rdi
0x1801da7b4  mov     rcx, rbp
0x1801da7b7  cmovb   rbx, rax
0x1801da7bb  call    cs:__imp_?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::gptr(void)
0x1801da7c1  mov     r8, rbx; Size
0x1801da7c4  mov     rcx, r14; void *
0x1801da7c7  mov     rdx, rax; Src
0x1801da7ca  call    memcpy_0
0x1801da7cf  mov     edx, ebx
0x1801da7d1  mov     rcx, rbp
0x1801da7d4  add     r14, rbx
0x1801da7d7  sub     rsi, rbx
0x1801da7da  call    cs:__imp_?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::gbump(int)
0x1801da7e0  cmp     qword ptr [rbp+80h], 0
0x1801da7e8  jz      short loc_1801DA841
0x1801da7ea  mov     rcx, rbp
0x1801da7ed  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1801da7f2  mov     ebx, 0FFFh
0x1801da7f7  cmp     rsi, rbx
0x1801da7fa  jbe     short loc_1801DA821
0x1801da7fc  mov     r9, [rbp+80h]; Stream
0x1801da803  mov     r8, rbx; ElementCount
0x1801da806  mov     edx, 1; ElementSize
0x1801da80b  mov     rcx, r14; Buffer
0x1801da80e  call    cs:__imp_fread
0x1801da814  add     r14, rax
0x1801da817  sub     rsi, rax
0x1801da81a  cmp     rax, rbx
0x1801da81d  jz      short loc_1801DA7F7
0x1801da81f  jmp     short loc_1801DA841
0x1801da821  test    rsi, rsi
0x1801da824  jz      short loc_1801DA841
0x1801da826  mov     r9, [rbp+80h]; Stream
0x1801da82d  mov     r8, rsi; ElementCount
0x1801da830  mov     edx, 1; ElementSize
0x1801da835  mov     rcx, r14; Buffer
0x1801da838  call    cs:__imp_fread
0x1801da83e  sub     rsi, rax
0x1801da841  sub     rdi, rsi
0x1801da844  mov     rax, rdi
0x1801da847  mov     rbx, [rsp+28h+arg_0]
0x1801da84c  mov     rbp, [rsp+28h+arg_8]
0x1801da851  mov     rsi, [rsp+28h+arg_10]
0x1801da856  mov     rdi, [rsp+28h+arg_18]
0x1801da85b  add     rsp, 20h
0x1801da85f  pop     r14
0x1801da861  retn
```
