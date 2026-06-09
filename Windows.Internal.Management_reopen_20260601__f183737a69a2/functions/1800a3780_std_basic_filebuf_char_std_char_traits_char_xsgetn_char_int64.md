# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x1800a3780`
- end: `0x1800a3882`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `258`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180007c45`
- `0x1800a2320`
- `0x1800a3780`

## import_xrefs

- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1800a37a7`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x1800a37a7`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a382e`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a3861`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a382e`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x1800a3861`

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
0x1800a3780  push    rbx
0x1800a3782  push    rbp
0x1800a3783  push    rsi
0x1800a3784  push    rdi
0x1800a3785  push    r14
0x1800a3787  sub     rsp, 20h
0x1800a378b  mov     rdi, r8
0x1800a378e  mov     r14, rdx
0x1800a3791  mov     rbp, rcx
0x1800a3794  test    r8, r8
0x1800a3797  jg      short loc_1800A37A0
0x1800a3799  xor     eax, eax
0x1800a379b  jmp     loc_1800A3876
0x1800a37a0  cmp     qword ptr [rcx+68h], 0
0x1800a37a5  jz      short loc_1800A37B8
0x1800a37a7  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x1800a37ae  nop     dword ptr [rax+rax+00h]
0x1800a37b3  jmp     loc_1800A3876
0x1800a37b8  mov     rax, [rcx+38h]
0x1800a37bc  mov     rsi, rdi
0x1800a37bf  mov     rdx, [rax]; Src
0x1800a37c2  test    rdx, rdx
0x1800a37c5  jz      short loc_1800A37CF
0x1800a37c7  mov     rax, [rcx+50h]
0x1800a37cb  mov     ecx, [rax]
0x1800a37cd  jmp     short loc_1800A37D1
0x1800a37cf  xor     ecx, ecx
0x1800a37d1  movsxd  rax, ecx
0x1800a37d4  test    ecx, ecx
0x1800a37d6  jz      short loc_1800A3803
0x1800a37d8  cmp     rax, rdi
0x1800a37db  mov     rbx, rdi
0x1800a37de  mov     rcx, r14; void *
0x1800a37e1  cmovb   rbx, rax
0x1800a37e5  mov     r8, rbx; Size
0x1800a37e8  call    memcpy_0
0x1800a37ed  mov     rax, [rbp+50h]
0x1800a37f1  add     r14, rbx
0x1800a37f4  sub     rsi, rbx
0x1800a37f7  sub     [rax], ebx
0x1800a37f9  mov     rcx, [rbp+38h]
0x1800a37fd  movsxd  rax, ebx
0x1800a3800  add     [rcx], rax
0x1800a3803  cmp     qword ptr [rbp+80h], 0
0x1800a380b  jz      short loc_1800A3870
0x1800a380d  mov     rcx, rbp
0x1800a3810  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x1800a3815  mov     ebx, 0FFFh
0x1800a381a  jmp     short loc_1800A3845
0x1800a381c  mov     r9, [rbp+80h]; Stream
0x1800a3823  mov     r8, rbx; ElementCount
0x1800a3826  mov     edx, 1; ElementSize
0x1800a382b  mov     rcx, r14; Buffer
0x1800a382e  call    cs:__imp_fread
0x1800a3835  nop     dword ptr [rax+rax+00h]
0x1800a383a  sub     rsi, rax
0x1800a383d  cmp     rax, rbx
0x1800a3840  jnz     short loc_1800A3870
0x1800a3842  add     r14, rbx
0x1800a3845  cmp     rsi, rbx
0x1800a3848  ja      short loc_1800A381C
0x1800a384a  test    rsi, rsi
0x1800a384d  jz      short loc_1800A3870
0x1800a384f  mov     r9, [rbp+80h]; Stream
0x1800a3856  mov     r8, rsi; ElementCount
0x1800a3859  mov     edx, 1; ElementSize
0x1800a385e  mov     rcx, r14; Buffer
0x1800a3861  call    cs:__imp_fread
0x1800a3868  nop     dword ptr [rax+rax+00h]
0x1800a386d  sub     rsi, rax
0x1800a3870  sub     rdi, rsi
0x1800a3873  mov     rax, rdi
0x1800a3876  add     rsp, 20h
0x1800a387a  pop     r14
0x1800a387c  pop     rdi
0x1800a387d  pop     rsi
0x1800a387e  pop     rbp
0x1800a387f  pop     rbx
0x1800a3880  retn
```
