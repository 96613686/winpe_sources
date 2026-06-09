# std::basic_filebuf<char,std::char_traits<char>>::xsgetn(char *,__int64)

- ea: `0x18000f680`
- end: `0x18000f767`
- name: `?xsgetn@?$basic_filebuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z`
- size: `231`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000c390`
- `0x18000c938`
- `0x18000f680`
- `0x18000f770`
- `0x1800efc6c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000f723`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000f74d`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000f723`
- `api-ms-win-crt-private-l1-1-0!_o_fread` at `0x18000f74d`

## pseudocode

```c
__int64 __fastcall std::filebuf::xsgetn(__int64 a1, char *a2, __int64 a3)
{
  unsigned __int64 v7; // rax
  size_t v8; // rbx
  size_t v9; // rsi
  size_t v10; // rax

  if ( a3 <= 0 )
    return 0;
  if ( *(_QWORD *)(a1 + 104) )
    return std::streambuf::xsgetn();
  v7 = std::wstreambuf::_Gnavail();
  if ( v7 )
  {
    v8 = a3;
    if ( v7 < a3 )
      v8 = v7;
    memcpy_0(a2, **(const void ***)(a1 + 56), v8);
    a2 += v8;
    v9 = a3 - v8;
    **(_DWORD **)(a1 + 80) -= v8;
    **(_QWORD **)(a1 + 56) += (int)v8;
  }
  else
  {
    v9 = a3;
  }
  if ( *(_QWORD *)(a1 + 128) )
  {
    std::filebuf::_Reset_back(a1);
    while ( v9 > 0xFFF )
    {
      v10 = fread(a2, 1u, 0xFFFu, *(FILE **)(a1 + 128));
      a2 += v10;
      v9 -= v10;
      if ( v10 != 4095 )
        return a3 - v9;
    }
    if ( v9 )
      v9 -= fread(a2, 1u, v9, *(FILE **)(a1 + 128));
  }
  return a3 - v9;
}

```

## disassembly

```asm
0x18000f680  push    rbx
0x18000f682  push    rbp
0x18000f683  push    rsi
0x18000f684  push    rdi
0x18000f685  push    r14
0x18000f687  sub     rsp, 20h
0x18000f68b  mov     rdi, r8
0x18000f68e  mov     r14, rdx
0x18000f691  mov     rbp, rcx
0x18000f694  test    r8, r8
0x18000f697  jg      short loc_18000F6A0
0x18000f699  xor     eax, eax
0x18000f69b  jmp     loc_18000F75C
0x18000f6a0  cmp     qword ptr [rcx+68h], 0
0x18000f6a5  jz      short loc_18000F6B1
0x18000f6a7  call    ?xsgetn@?$basic_streambuf@DU?$char_traits@D@std@@@std@@MEAA_JPEAD_J@Z; std::streambuf::xsgetn(char *,__int64)
0x18000f6ac  jmp     loc_18000F75C
0x18000f6b1  call    ?_Gnavail@?$basic_streambuf@_WU?$char_traits@_W@std@@@std@@IEBA_JXZ; std::wstreambuf::_Gnavail(void)
0x18000f6b6  test    rax, rax
0x18000f6b9  jz      short loc_18000F6F2
0x18000f6bb  mov     rdx, [rbp+38h]
0x18000f6bf  cmp     rax, rdi
0x18000f6c2  mov     rbx, rdi
0x18000f6c5  mov     rcx, r14; void *
0x18000f6c8  cmovb   rbx, rax
0x18000f6cc  mov     r8, rbx; Size
0x18000f6cf  mov     rdx, [rdx]; Src
0x18000f6d2  call    memcpy_0
0x18000f6d7  mov     rax, [rbp+50h]
0x18000f6db  mov     rsi, rdi
0x18000f6de  add     r14, rbx
0x18000f6e1  sub     rsi, rbx
0x18000f6e4  sub     [rax], ebx
0x18000f6e6  mov     rcx, [rbp+38h]
0x18000f6ea  movsxd  rax, ebx
0x18000f6ed  add     [rcx], rax
0x18000f6f0  jmp     short loc_18000F6F5
0x18000f6f2  mov     rsi, rdi
0x18000f6f5  cmp     qword ptr [rbp+80h], 0
0x18000f6fd  jz      short loc_18000F756
0x18000f6ff  mov     rcx, rbp
0x18000f702  call    ?_Reset_back@?$basic_filebuf@DU?$char_traits@D@std@@@std@@AEAAXXZ; std::filebuf::_Reset_back(void)
0x18000f707  mov     ebx, 0FFFh
0x18000f70c  cmp     rsi, rbx
0x18000f70f  jbe     short loc_18000F736
0x18000f711  mov     r9, [rbp+80h]; Stream
0x18000f718  mov     r8, rbx; ElementCount
0x18000f71b  mov     edx, 1; ElementSize
0x18000f720  mov     rcx, r14; Buffer
0x18000f723  call    cs:__imp_fread
0x18000f729  add     r14, rax
0x18000f72c  sub     rsi, rax
0x18000f72f  cmp     rax, rbx
0x18000f732  jz      short loc_18000F70C
0x18000f734  jmp     short loc_18000F756
0x18000f736  test    rsi, rsi
0x18000f739  jz      short loc_18000F756
0x18000f73b  mov     r9, [rbp+80h]; Stream
0x18000f742  mov     r8, rsi; ElementCount
0x18000f745  mov     edx, 1; ElementSize
0x18000f74a  mov     rcx, r14; Buffer
0x18000f74d  call    cs:__imp_fread
0x18000f753  sub     rsi, rax
0x18000f756  sub     rdi, rsi
0x18000f759  mov     rax, rdi
0x18000f75c  add     rsp, 20h
0x18000f760  pop     r14
0x18000f762  pop     rdi
0x18000f763  pop     rsi
0x18000f764  pop     rbp
0x18000f765  pop     rbx
0x18000f766  retn
```
