# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x18005aa60`
- end: `0x18005ab74`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `276`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180008554`
- `0x18005aa60`

## import_xrefs

- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x18005aa87`
- `msvcp_win!?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z` at `0x18005aa87`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18005ab2d`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18005ab5a`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18005ab2d`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18005ab5a`

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
0x18005aa60  push    rbx
0x18005aa62  push    rbp
0x18005aa63  push    rsi
0x18005aa64  push    rdi
0x18005aa65  push    r14
0x18005aa67  sub     rsp, 20h
0x18005aa6b  mov     rdi, r8
0x18005aa6e  mov     r14, rdx
0x18005aa71  mov     rsi, rcx
0x18005aa74  test    r8, r8
0x18005aa77  jg      short loc_18005AA80
0x18005aa79  xor     eax, eax
0x18005aa7b  jmp     loc_18005AB69
0x18005aa80  cmp     qword ptr [rcx+68h], 0
0x18005aa85  jz      short loc_18005AA92
0x18005aa87  call    cs:__imp_?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x18005aa8d  jmp     loc_18005AB69
0x18005aa92  mov     rax, [rcx+38h]
0x18005aa96  mov     rbp, rdi
0x18005aa99  mov     rdx, [rax]; Src
0x18005aa9c  test    rdx, rdx
0x18005aa9f  jz      short loc_18005AAA9
0x18005aaa1  mov     rax, [rcx+50h]
0x18005aaa5  mov     ecx, [rax]
0x18005aaa7  jmp     short loc_18005AAAB
0x18005aaa9  xor     ecx, ecx
0x18005aaab  movsxd  rax, ecx
0x18005aaae  test    ecx, ecx
0x18005aab0  jz      short loc_18005AADD
0x18005aab2  cmp     rax, rdi
0x18005aab5  mov     rbx, rdi
0x18005aab8  mov     rcx, r14; void *
0x18005aabb  cmovb   rbx, rax
0x18005aabf  mov     r8, rbx; Size
0x18005aac2  call    memcpy_0
0x18005aac7  mov     rax, [rsi+50h]
0x18005aacb  add     r14, rbx
0x18005aace  sub     rbp, rbx
0x18005aad1  sub     [rax], ebx
0x18005aad3  mov     rcx, [rsi+38h]
0x18005aad7  movsxd  rax, ebx
0x18005aada  add     [rcx], rax
0x18005aadd  cmp     qword ptr [rsi+80h], 0
0x18005aae5  jz      short loc_18005AB63
0x18005aae7  mov     r8, [rsi+18h]
0x18005aaeb  lea     rax, [rsi+70h]
0x18005aaef  cmp     [r8], rax
0x18005aaf2  jnz     short loc_18005AB14
0x18005aaf4  mov     rcx, [rsi+88h]
0x18005aafb  mov     rdx, [rsi+90h]
0x18005ab02  mov     [r8], rcx
0x18005ab05  sub     edx, ecx
0x18005ab07  mov     rax, [rsi+38h]
0x18005ab0b  mov     [rax], rcx
0x18005ab0e  mov     rax, [rsi+50h]
0x18005ab12  mov     [rax], edx
0x18005ab14  mov     ebx, 0FFFh
0x18005ab19  jmp     short loc_18005AB3E
0x18005ab1b  mov     r9, [rsi+80h]; Stream
0x18005ab22  mov     r8, rbx; ElementCount
0x18005ab25  mov     edx, 1; ElementSize
0x18005ab2a  mov     rcx, r14; Buffer
0x18005ab2d  call    cs:__imp_fread
0x18005ab33  sub     rbp, rax
0x18005ab36  cmp     rax, rbx
0x18005ab39  jnz     short loc_18005AB63
0x18005ab3b  add     r14, rbx
0x18005ab3e  cmp     rbp, rbx
0x18005ab41  ja      short loc_18005AB1B
0x18005ab43  test    rbp, rbp
0x18005ab46  jz      short loc_18005AB63
0x18005ab48  mov     r9, [rsi+80h]; Stream
0x18005ab4f  mov     r8, rbp; ElementCount
0x18005ab52  mov     edx, 1; ElementSize
0x18005ab57  mov     rcx, r14; Buffer
0x18005ab5a  call    cs:__imp_fread
0x18005ab60  sub     rbp, rax
0x18005ab63  sub     rdi, rbp
0x18005ab66  mov     rax, rdi
0x18005ab69  add     rsp, 20h
0x18005ab6d  pop     r14
0x18005ab6f  pop     rdi
0x18005ab70  pop     rsi
0x18005ab71  pop     rbp
0x18005ab72  pop     rbx
0x18005ab73  retn
```
