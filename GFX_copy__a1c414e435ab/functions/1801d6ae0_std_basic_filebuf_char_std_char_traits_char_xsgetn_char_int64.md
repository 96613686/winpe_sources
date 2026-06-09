# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x1801d6ae0`
- end: `0x1801d6be2`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180055860`
- `0x1801d61c0`
- `0x1801d6ae0`

## import_xrefs

- `MSVCP140!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1801d6b3b`
- `MSVCP140!?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ` at `0x1801d6b3b`
- `MSVCP140!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1801d6b15`
- `MSVCP140!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1801d6b15`
- `MSVCP140!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1801d6b5a`
- `MSVCP140!?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z` at `0x1801d6b5a`
- `MSVCP140!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1801d6b23`
- `MSVCP140!?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ` at `0x1801d6b23`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1801d6b8e`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1801d6bb8`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1801d6b8e`
- `api-ms-win-crt-stdio-l1-1-0!fread` at `0x1801d6bb8`

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
0x1801d6ae0  mov     rax, rsp
0x1801d6ae3  mov     [rax+8], rbx
0x1801d6ae7  mov     [rax+10h], rbp
0x1801d6aeb  mov     [rax+18h], rsi
0x1801d6aef  mov     [rax+20h], rdi
0x1801d6af3  push    r14
0x1801d6af5  sub     rsp, 20h
0x1801d6af9  mov     rdi, r8
0x1801d6afc  mov     r14, rdx
0x1801d6aff  mov     rbp, rcx
0x1801d6b02  test    r8, r8
0x1801d6b05  jg      short loc_1801D6B0E
0x1801d6b07  xor     eax, eax
0x1801d6b09  jmp     loc_1801D6BC7
0x1801d6b0e  cmp     qword ptr [rcx+68h], 0
0x1801d6b13  jz      short loc_1801D6B20
0x1801d6b15  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x1801d6b1b  jmp     loc_1801D6BC7
0x1801d6b20  mov     rsi, rdi
0x1801d6b23  call    cs:__imp_?_Gnavail@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBA_JXZ; std::streambuf::_Gnavail(void)
0x1801d6b29  test    rax, rax
0x1801d6b2c  jz      short loc_1801D6B60
0x1801d6b2e  cmp     rax, rdi
0x1801d6b31  mov     rbx, rdi
0x1801d6b34  mov     rcx, rbp
0x1801d6b37  cmovb   rbx, rax
0x1801d6b3b  call    cs:__imp_?gptr@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEBAPEADXZ; std::streambuf::gptr(void)
0x1801d6b41  mov     r8, rbx; Size
0x1801d6b44  mov     rcx, r14; void *
0x1801d6b47  mov     rdx, rax; Src
0x1801d6b4a  call    memcpy_0
0x1801d6b4f  mov     edx, ebx
0x1801d6b51  mov     rcx, rbp
0x1801d6b54  add     r14, rbx
0x1801d6b57  sub     rsi, rbx
0x1801d6b5a  call    cs:__imp_?gbump@?$basic_streambuf@DU?$char_traits@D@std@@@std@@IEAAXH@Z; std::streambuf::gbump(int)
0x1801d6b60  cmp     qword ptr [rbp+80h], 0
0x1801d6b68  jz      short loc_1801D6BC1
0x1801d6b6a  mov     rcx, rbp
0x1801d6b6d  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1801d6b72  mov     ebx, 0FFFh
0x1801d6b77  cmp     rsi, rbx
0x1801d6b7a  jbe     short loc_1801D6BA1
0x1801d6b7c  mov     r9, [rbp+80h]; Stream
0x1801d6b83  mov     r8, rbx; ElementCount
0x1801d6b86  mov     edx, 1; ElementSize
0x1801d6b8b  mov     rcx, r14; Buffer
0x1801d6b8e  call    cs:__imp_fread
0x1801d6b94  add     r14, rax
0x1801d6b97  sub     rsi, rax
0x1801d6b9a  cmp     rax, rbx
0x1801d6b9d  jz      short loc_1801D6B77
0x1801d6b9f  jmp     short loc_1801D6BC1
0x1801d6ba1  test    rsi, rsi
0x1801d6ba4  jz      short loc_1801D6BC1
0x1801d6ba6  mov     r9, [rbp+80h]; Stream
0x1801d6bad  mov     r8, rsi; ElementCount
0x1801d6bb0  mov     edx, 1; ElementSize
0x1801d6bb5  mov     rcx, r14; Buffer
0x1801d6bb8  call    cs:__imp_fread
0x1801d6bbe  sub     rsi, rax
0x1801d6bc1  sub     rdi, rsi
0x1801d6bc4  mov     rax, rdi
0x1801d6bc7  mov     rbx, [rsp+28h+arg_0]
0x1801d6bcc  mov     rbp, [rsp+28h+arg_8]
0x1801d6bd1  mov     rsi, [rsp+28h+arg_10]
0x1801d6bd6  mov     rdi, [rsp+28h+arg_18]
0x1801d6bdb  add     rsp, 20h
0x1801d6bdf  pop     r14
0x1801d6be1  retn
```
