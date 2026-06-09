# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x180033df0`
- end: `0x180033edf`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `239`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800085bc`
- `0x1800307c4`
- `0x180033df0`

## import_xrefs

- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x180033e17`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x180033e17`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180033e98`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180033ec5`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180033e98`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x180033ec5`

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
0x180033df0  push    rbx
0x180033df2  push    rbp
0x180033df3  push    rsi
0x180033df4  push    rdi
0x180033df5  push    r14
0x180033df7  sub     rsp, 20h
0x180033dfb  mov     rdi, r8
0x180033dfe  mov     r14, rdx
0x180033e01  mov     rbp, rcx
0x180033e04  test    r8, r8
0x180033e07  jg      short loc_180033E10
0x180033e09  xor     eax, eax
0x180033e0b  jmp     loc_180033ED4
0x180033e10  cmp     qword ptr [rcx+68h], 0
0x180033e15  jz      short loc_180033E22
0x180033e17  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x180033e1d  jmp     loc_180033ED4
0x180033e22  mov     rax, [rcx+38h]
0x180033e26  mov     rsi, rdi
0x180033e29  mov     rdx, [rax]; Src
0x180033e2c  test    rdx, rdx
0x180033e2f  jz      short loc_180033E39
0x180033e31  mov     rax, [rcx+50h]
0x180033e35  mov     ecx, [rax]
0x180033e37  jmp     short loc_180033E3B
0x180033e39  xor     ecx, ecx
0x180033e3b  movsxd  rax, ecx
0x180033e3e  test    ecx, ecx
0x180033e40  jz      short loc_180033E6D
0x180033e42  cmp     rax, rdi
0x180033e45  mov     rbx, rdi
0x180033e48  mov     rcx, r14; void *
0x180033e4b  cmovb   rbx, rax
0x180033e4f  mov     r8, rbx; Size
0x180033e52  call    memcpy_0
0x180033e57  mov     rax, [rbp+50h]
0x180033e5b  add     r14, rbx
0x180033e5e  sub     rsi, rbx
0x180033e61  sub     [rax], ebx
0x180033e63  mov     rcx, [rbp+38h]
0x180033e67  movsxd  rax, ebx
0x180033e6a  add     [rcx], rax
0x180033e6d  cmp     qword ptr [rbp+80h], 0
0x180033e75  jz      short loc_180033ECE
0x180033e77  mov     rcx, rbp
0x180033e7a  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x180033e7f  mov     ebx, 0FFFh
0x180033e84  jmp     short loc_180033EA9
0x180033e86  mov     r9, [rbp+80h]; Stream
0x180033e8d  mov     r8, rbx; ElementCount
0x180033e90  mov     edx, 1; ElementSize
0x180033e95  mov     rcx, r14; Buffer
0x180033e98  call    cs:__imp_fread
0x180033e9e  sub     rsi, rax
0x180033ea1  cmp     rax, rbx
0x180033ea4  jnz     short loc_180033ECE
0x180033ea6  add     r14, rbx
0x180033ea9  cmp     rsi, rbx
0x180033eac  ja      short loc_180033E86
0x180033eae  test    rsi, rsi
0x180033eb1  jz      short loc_180033ECE
0x180033eb3  mov     r9, [rbp+80h]; Stream
0x180033eba  mov     r8, rsi; ElementCount
0x180033ebd  mov     edx, 1; ElementSize
0x180033ec2  mov     rcx, r14; Buffer
0x180033ec5  call    cs:__imp_fread
0x180033ecb  sub     rsi, rax
0x180033ece  sub     rdi, rsi
0x180033ed1  mov     rax, rdi
0x180033ed4  add     rsp, 20h
0x180033ed8  pop     r14
0x180033eda  pop     rdi
0x180033edb  pop     rsi
0x180033edc  pop     rbp
0x180033edd  pop     rbx
0x180033ede  retn
```
