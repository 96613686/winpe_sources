# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x18002f4b0`
- end: `0x18002f5c3`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `275`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18001a9f0`
- `0x18002f4b0`
- `0x180065144`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18002f57c`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18002f5a9`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18002f57c`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18002f5a9`

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
0x18002f4b0  push    rbx
0x18002f4b2  push    rbp
0x18002f4b3  push    rsi
0x18002f4b4  push    rdi
0x18002f4b5  push    r14
0x18002f4b7  sub     rsp, 20h
0x18002f4bb  mov     rdi, r8
0x18002f4be  mov     r14, rdx
0x18002f4c1  mov     rsi, rcx
0x18002f4c4  test    r8, r8
0x18002f4c7  jg      short loc_18002F4D0
0x18002f4c9  xor     eax, eax
0x18002f4cb  jmp     loc_18002F5B8
0x18002f4d0  cmp     qword ptr [rcx+68h], 0
0x18002f4d5  jz      short loc_18002F4E1
0x18002f4d7  call    ?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x18002f4dc  jmp     loc_18002F5B8
0x18002f4e1  mov     rax, [rcx+38h]
0x18002f4e5  mov     rbp, rdi
0x18002f4e8  mov     rdx, [rax]; Src
0x18002f4eb  test    rdx, rdx
0x18002f4ee  jz      short loc_18002F4F8
0x18002f4f0  mov     rax, [rcx+50h]
0x18002f4f4  mov     ecx, [rax]
0x18002f4f6  jmp     short loc_18002F4FA
0x18002f4f8  xor     ecx, ecx
0x18002f4fa  movsxd  rax, ecx
0x18002f4fd  test    ecx, ecx
0x18002f4ff  jz      short loc_18002F52C
0x18002f501  cmp     rax, rdi
0x18002f504  mov     rbx, rdi
0x18002f507  mov     rcx, r14; void *
0x18002f50a  cmovb   rbx, rax
0x18002f50e  mov     r8, rbx; Size
0x18002f511  call    memcpy_0
0x18002f516  mov     rax, [rsi+50h]
0x18002f51a  add     r14, rbx
0x18002f51d  sub     rbp, rbx
0x18002f520  sub     [rax], ebx
0x18002f522  mov     rcx, [rsi+38h]
0x18002f526  movsxd  rax, ebx
0x18002f529  add     [rcx], rax
0x18002f52c  cmp     qword ptr [rsi+80h], 0
0x18002f534  jz      short loc_18002F5B2
0x18002f536  mov     r8, [rsi+18h]
0x18002f53a  lea     rax, [rsi+70h]
0x18002f53e  cmp     [r8], rax
0x18002f541  jnz     short loc_18002F563
0x18002f543  mov     rcx, [rsi+88h]
0x18002f54a  mov     rdx, [rsi+90h]
0x18002f551  mov     [r8], rcx
0x18002f554  sub     edx, ecx
0x18002f556  mov     rax, [rsi+38h]
0x18002f55a  mov     [rax], rcx
0x18002f55d  mov     rax, [rsi+50h]
0x18002f561  mov     [rax], edx
0x18002f563  mov     ebx, 0FFFh
0x18002f568  jmp     short loc_18002F58D
0x18002f56a  mov     r9, [rsi+80h]; Stream
0x18002f571  mov     r8, rbx; ElementCount
0x18002f574  mov     edx, 1; ElementSize
0x18002f579  mov     rcx, r14; Buffer
0x18002f57c  call    cs:__imp_fread
0x18002f582  sub     rbp, rax
0x18002f585  cmp     rax, rbx
0x18002f588  jnz     short loc_18002F5B2
0x18002f58a  add     r14, rbx
0x18002f58d  cmp     rbp, rbx
0x18002f590  ja      short loc_18002F56A
0x18002f592  test    rbp, rbp
0x18002f595  jz      short loc_18002F5B2
0x18002f597  mov     r9, [rsi+80h]; Stream
0x18002f59e  mov     r8, rbp; ElementCount
0x18002f5a1  mov     edx, 1; ElementSize
0x18002f5a6  mov     rcx, r14; Buffer
0x18002f5a9  call    cs:__imp_fread
0x18002f5af  sub     rbp, rax
0x18002f5b2  sub     rdi, rbp
0x18002f5b5  mov     rax, rdi
0x18002f5b8  add     rsp, 20h
0x18002f5bc  pop     r14
0x18002f5be  pop     rdi
0x18002f5bf  pop     rsi
0x18002f5c0  pop     rbp
0x18002f5c1  pop     rbx
0x18002f5c2  retn
```
