# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x1800a0650`
- end: `0x1800a073f`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007ad5`
- `0x18009f2b8`
- `0x1800a0650`

## import_xrefs

- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1800a0677`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1800a0677`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a06f8`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a0725`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a06f8`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a0725`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  size_t v7; // rsi
  const void *v8; // rdx
  int v9; // ecx
  size_t v10; // rbx
  size_t v11; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsgetn();
  v7 = a3;
  v8 = **(const void ***)(a1 + 56);
  if ( v8 )
    v9 = **(_DWORD **)(a1 + 80);
  else
    v9 = 0;
  if ( v9 )
  {
    v10 = a3;
    if ( v9 < (unsigned __int64)a3 )
      v10 = v9;
    memcpy_0(a2, v8, v10);
    a2 += v10;
    v7 = a3 - v10;
    **(_DWORD **)(a1 + 80) -= v10;
    **(_QWORD **)(a1 + 56) += (int)v10;
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::filebuf::_Reset_back(a1);
    while ( v7 > 0xFFF )
    {
      v11 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
      v7 -= v11;
      if ( v11 != 4095 )
        return a3 - v7;
      a2 += 4095;
    }
    if ( v7 )
      v7 -= fread(a2, 1u, v7, *(FILE **)(a1 + 128));
  }
  return a3 - v7;
}

```

## disassembly

```asm
0x1800a0650  push    rbx
0x1800a0652  push    rbp
0x1800a0653  push    rsi
0x1800a0654  push    rdi
0x1800a0655  push    r14
0x1800a0657  sub     rsp, 20h
0x1800a065b  mov     rdi, r8
0x1800a065e  mov     r14, rdx
0x1800a0661  mov     rbp, rcx
0x1800a0664  test    r8, r8
0x1800a0667  jg      short loc_1800A0670
0x1800a0669  xor     eax, eax
0x1800a066b  jmp     loc_1800A0734
0x1800a0670  cmp     qword ptr [rcx+68h], 0
0x1800a0675  jz      short loc_1800A0682
0x1800a0677  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x1800a067d  jmp     loc_1800A0734
0x1800a0682  mov     rax, [rcx+38h]
0x1800a0686  mov     rsi, rdi
0x1800a0689  mov     rdx, [rax]; Src
0x1800a068c  test    rdx, rdx
0x1800a068f  jz      short loc_1800A0699
0x1800a0691  mov     rax, [rcx+50h]
0x1800a0695  mov     ecx, [rax]
0x1800a0697  jmp     short loc_1800A069B
0x1800a0699  xor     ecx, ecx
0x1800a069b  movsxd  rax, ecx
0x1800a069e  test    ecx, ecx
0x1800a06a0  jz      short loc_1800A06CD
0x1800a06a2  cmp     rax, rdi
0x1800a06a5  mov     rbx, rdi
0x1800a06a8  mov     rcx, r14; void *
0x1800a06ab  cmovb   rbx, rax
0x1800a06af  mov     r8, rbx; Size
0x1800a06b2  call    memcpy_0
0x1800a06b7  mov     rax, [rbp+50h]
0x1800a06bb  add     r14, rbx
0x1800a06be  sub     rsi, rbx
0x1800a06c1  sub     [rax], ebx
0x1800a06c3  mov     rcx, [rbp+38h]
0x1800a06c7  movsxd  rax, ebx
0x1800a06ca  add     [rcx], rax
0x1800a06cd  cmp     qword ptr [rbp+80h], 0
0x1800a06d5  jz      short loc_1800A072E
0x1800a06d7  mov     rcx, rbp
0x1800a06da  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1800a06df  mov     ebx, 0FFFh
0x1800a06e4  jmp     short loc_1800A0709
0x1800a06e6  mov     r9, [rbp+80h]; Stream
0x1800a06ed  mov     r8, rbx; ElementCount
0x1800a06f0  mov     edx, 1; ElementSize
0x1800a06f5  mov     rcx, r14; Buffer
0x1800a06f8  call    cs:__imp_fread
0x1800a06fe  sub     rsi, rax
0x1800a0701  cmp     rax, rbx
0x1800a0704  jnz     short loc_1800A072E
0x1800a0706  add     r14, rbx
0x1800a0709  cmp     rsi, rbx
0x1800a070c  ja      short loc_1800A06E6
0x1800a070e  test    rsi, rsi
0x1800a0711  jz      short loc_1800A072E
0x1800a0713  mov     r9, [rbp+80h]; Stream
0x1800a071a  mov     r8, rsi; ElementCount
0x1800a071d  mov     edx, 1; ElementSize
0x1800a0722  mov     rcx, r14; Buffer
0x1800a0725  call    cs:__imp_fread
0x1800a072b  sub     rsi, rax
0x1800a072e  sub     rdi, rsi
0x1800a0731  mov     rax, rdi
0x1800a0734  add     rsp, 20h
0x1800a0738  pop     r14
0x1800a073a  pop     rdi
0x1800a073b  pop     rsi
0x1800a073c  pop     rbp
0x1800a073d  pop     rbx
0x1800a073e  retn
```
