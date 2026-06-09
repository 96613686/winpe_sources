# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x1400216c0`
- end: `0x1400217d4`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x140004a60`
- `0x1400216c0`

## import_xrefs

- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1400216e7`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1400216e7`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x14002178d`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1400217ba`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x14002178d`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1400217ba`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  size_t v7; // rbp
  const void *v8; // rdx
  int v9; // ecx
  size_t v10; // rbx
  _QWORD *v11; // r8
  __int64 v12; // rcx
  __int64 v13; // rdx
  size_t v14; // rax

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
    v11 = *(_QWORD **)(a1 + 24);
    if ( *v11 == a1 + 112 )
    {
      v12 = *(_QWORD *)(a1 + 136);
      v13 = *(_QWORD *)(a1 + 144);
      *v11 = v12;
      **(_QWORD **)(a1 + 56) = v12;
      **(_DWORD **)(a1 + 80) = v13 - v12;
    }
    while ( v7 > 0xFFF )
    {
      v14 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
      v7 -= v14;
      if ( v14 != 4095 )
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
0x1400216c0  push    rbx
0x1400216c2  push    rbp
0x1400216c3  push    rsi
0x1400216c4  push    rdi
0x1400216c5  push    r14
0x1400216c7  sub     rsp, 20h
0x1400216cb  mov     rdi, r8
0x1400216ce  mov     r14, rdx
0x1400216d1  mov     rsi, rcx
0x1400216d4  test    r8, r8
0x1400216d7  jg      short loc_1400216E0
0x1400216d9  xor     eax, eax
0x1400216db  jmp     loc_1400217C9
0x1400216e0  cmp     qword ptr [rcx+68h], 0
0x1400216e5  jz      short loc_1400216F2
0x1400216e7  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x1400216ed  jmp     loc_1400217C9
0x1400216f2  mov     rax, [rcx+38h]
0x1400216f6  mov     rbp, rdi
0x1400216f9  mov     rdx, [rax]; Src
0x1400216fc  test    rdx, rdx
0x1400216ff  jz      short loc_140021709
0x140021701  mov     rax, [rcx+50h]
0x140021705  mov     ecx, [rax]
0x140021707  jmp     short loc_14002170B
0x140021709  xor     ecx, ecx
0x14002170b  movsxd  rax, ecx
0x14002170e  test    ecx, ecx
0x140021710  jz      short loc_14002173D
0x140021712  cmp     rax, rdi
0x140021715  mov     rbx, rdi
0x140021718  mov     rcx, r14; void *
0x14002171b  cmovb   rbx, rax
0x14002171f  mov     r8, rbx; Size
0x140021722  call    memcpy_0
0x140021727  mov     rax, [rsi+50h]
0x14002172b  add     r14, rbx
0x14002172e  sub     rbp, rbx
0x140021731  sub     [rax], ebx
0x140021733  mov     rcx, [rsi+38h]
0x140021737  movsxd  rax, ebx
0x14002173a  add     [rcx], rax
0x14002173d  cmp     qword ptr [rsi+80h], 0
0x140021745  jz      short loc_1400217C3
0x140021747  mov     r8, [rsi+18h]
0x14002174b  lea     rax, [rsi+70h]
0x14002174f  cmp     [r8], rax
0x140021752  jnz     short loc_140021774
0x140021754  mov     rcx, [rsi+88h]
0x14002175b  mov     rdx, [rsi+90h]
0x140021762  mov     [r8], rcx
0x140021765  sub     edx, ecx
0x140021767  mov     rax, [rsi+38h]
0x14002176b  mov     [rax], rcx
0x14002176e  mov     rax, [rsi+50h]
0x140021772  mov     [rax], edx
0x140021774  mov     ebx, 0FFFh
0x140021779  jmp     short loc_14002179E
0x14002177b  mov     r9, [rsi+80h]; Stream
0x140021782  mov     r8, rbx; ElementCount
0x140021785  mov     edx, 1; ElementSize
0x14002178a  mov     rcx, r14; Buffer
0x14002178d  call    cs:__imp_fread
0x140021793  sub     rbp, rax
0x140021796  cmp     rax, rbx
0x140021799  jnz     short loc_1400217C3
0x14002179b  add     r14, rbx
0x14002179e  cmp     rbp, rbx
0x1400217a1  ja      short loc_14002177B
0x1400217a3  test    rbp, rbp
0x1400217a6  jz      short loc_1400217C3
0x1400217a8  mov     r9, [rsi+80h]; Stream
0x1400217af  mov     r8, rbp; ElementCount
0x1400217b2  mov     edx, 1; ElementSize
0x1400217b7  mov     rcx, r14; Buffer
0x1400217ba  call    cs:__imp_fread
0x1400217c0  sub     rbp, rax
0x1400217c3  sub     rdi, rbp
0x1400217c6  mov     rax, rdi
0x1400217c9  add     rsp, 20h
0x1400217cd  pop     r14
0x1400217cf  pop     rdi
0x1400217d0  pop     rsi
0x1400217d1  pop     rbp
0x1400217d2  pop     rbx
0x1400217d3  retn
```
