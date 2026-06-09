# std::deque__TagDirectoryTree_::_2_::DirQueItem_std::allocator__TagDirectoryTree_::_2_::DirQueItem___::_Growmap

- ea: `0x18001ec30`
- end: `0x18001ed76`
- name: `std::deque__TagDirectoryTree_::_2_::DirQueItem_std::allocator__TagDirectoryTree_::_2_::DirQueItem___::_Growmap`
- size: `326`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x18001cb04`

## callees

- `0x180005c94`
- `0x18000eab8`
- `0x18000eb18`
- `0x180017588`
- `0x18001ec30`
- `0x18001f148`
- `0x18002af9c`

## pseudocode

```c
void __fastcall std::deque__TagDirectoryTree_::_2_::DirQueItem_std::allocator__TagDirectoryTree_::_2_::DirQueItem___::_Growmap(
        _QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  size_t size_of; // rax
  _QWORD *v6; // r14
  __int64 v7; // r15
  char *v8; // r12
  unsigned __int64 v9; // rax
  __int64 v10; // rax
  unsigned __int64 v11; // rsi
  size_t v12; // rbx
  const void *v13; // rdx
  char *v14; // rbx
  size_t v15; // r8
  char *v16; // rcx
  _QWORD *v17; // rcx

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0x7E07E07E07E07ELL - v2 < v2 )
      std::deque__TagDirectoryTree_::_2_::DirQueItem_std::allocator__TagDirectoryTree_::_2_::DirQueItem___::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3];
  size_of = std::_Get_size_of_n<8>(v2);
  v6 = std::_Allocate<16,std::_Default_allocate_traits>(size_of);
  v7 = 8 * v4;
  v8 = (char *)&v6[v4];
  v9 = v2 >> 1;
  while ( v2 <= v9 )
    v2 *= 2LL;
  v10 = a1[2];
  v11 = v2 - v10;
  v12 = 8 * v10 - v7;
  memmove_0(v8, (const void *)(a1[1] + v7), v12);
  v13 = (const void *)a1[1];
  v14 = &v8[v12];
  if ( v4 > v11 )
  {
    memmove_0(v14, v13, 8 * v11);
    memmove_0(v6, (const void *)(8 * v11 + a1[1]), v7 - 8 * v11);
    v16 = (char *)v6 + v7 - 8 * v11;
    v15 = 8 * v11;
  }
  else
  {
    memmove_0(v14, v13, 8 * v4);
    memset_0(&v14[v7], 0, 8 * (v11 - v4));
    v15 = 8 * v4;
    v16 = (char *)v6;
  }
  memset_0(v16, 0, v15);
  v17 = (_QWORD *)a1[1];
  if ( v17 )
    std::_Deallocate<16>(v17, 8LL * a1[2]);
  a1[2] += v11;
  a1[1] = v6;
}

```

## disassembly

```asm
0x18001ec30  push    rbx
0x18001ec32  push    rbp
0x18001ec33  push    rsi
0x18001ec34  push    rdi
0x18001ec35  push    r12
0x18001ec37  push    r14
0x18001ec39  push    r15
0x18001ec3b  sub     rsp, 20h
0x18001ec3f  mov     rbp, rcx
0x18001ec42  mov     esi, 1
0x18001ec47  mov     rcx, [rcx+10h]
0x18001ec4b  test    rcx, rcx
0x18001ec4e  cmovnz  rsi, rcx
0x18001ec52  mov     rax, rsi
0x18001ec55  sub     rax, rcx
0x18001ec58  cmp     rax, 1
0x18001ec5c  jb      short loc_18001EC64
0x18001ec5e  cmp     rsi, 8
0x18001ec62  jnb     short loc_18001EC7F
0x18001ec64  mov     rax, 7E07E07E07E07Eh
0x18001ec6e  sub     rax, rsi
0x18001ec71  cmp     rax, rsi
0x18001ec74  jb      loc_18001ED70
0x18001ec7a  add     rsi, rsi
0x18001ec7d  jmp     short loc_18001EC52
0x18001ec7f  mov     rdi, [rbp+18h]
0x18001ec83  mov     rcx, rsi
0x18001ec86  call    ??$_Get_size_of_n@$07@std@@YA_K_K@Z; std::_Get_size_of_n<8>(unsigned __int64)
0x18001ec8b  mov     rcx, rax
0x18001ec8e  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x18001ec93  mov     r14, rax
0x18001ec96  lea     r15, ds:0[rdi*8]
0x18001ec9e  lea     r12, [r15+rax]
0x18001eca2  mov     rax, rsi
0x18001eca5  shr     rax, 1
0x18001eca8  jmp     short loc_18001ECAD
0x18001ecaa  add     rsi, rsi
0x18001ecad  cmp     rsi, rax
0x18001ecb0  jbe     short loc_18001ECAA
0x18001ecb2  mov     rcx, [rbp+8]
0x18001ecb6  mov     rax, [rbp+10h]
0x18001ecba  sub     rsi, rax
0x18001ecbd  shl     rax, 3
0x18001ecc1  lea     rdx, [rcx+r15]; Src
0x18001ecc5  sub     rax, rdx
0x18001ecc8  lea     rbx, [rax+rcx]
0x18001eccc  mov     rcx, r12; void *
0x18001eccf  mov     r8, rbx; Size
0x18001ecd2  call    memmove_0
0x18001ecd7  mov     rdx, [rbp+8]; Src
0x18001ecdb  add     rbx, r12
0x18001ecde  mov     rcx, rbx; void *
0x18001ece1  cmp     rdi, rsi
0x18001ece4  ja      short loc_18001ED0B
0x18001ece6  mov     r8, r15; Size
0x18001ece9  call    memmove_0
0x18001ecee  mov     r8, rsi
0x18001ecf1  lea     rcx, [rbx+r15]; void *
0x18001ecf5  sub     r8, rdi
0x18001ecf8  xor     edx, edx; Val
0x18001ecfa  shl     r8, 3; Size
0x18001ecfe  call    memset_0
0x18001ed03  mov     r8, r15
0x18001ed06  mov     rcx, r14
0x18001ed09  jmp     short loc_18001ED3C
0x18001ed0b  lea     rdi, ds:0[rsi*8]
0x18001ed13  mov     r8, rdi; Size
0x18001ed16  call    memmove_0
0x18001ed1b  mov     rax, [rbp+8]
0x18001ed1f  mov     rcx, r14; void *
0x18001ed22  lea     rdx, [rdi+rax]; Src
0x18001ed26  sub     rax, rdx
0x18001ed29  lea     rbx, [rax+r15]
0x18001ed2d  mov     r8, rbx; Size
0x18001ed30  call    memmove_0
0x18001ed35  lea     rcx, [rbx+r14]; void *
0x18001ed39  mov     r8, rdi; Size
0x18001ed3c  xor     edx, edx; Val
0x18001ed3e  call    memset_0
0x18001ed43  mov     rcx, [rbp+8]
0x18001ed47  test    rcx, rcx
0x18001ed4a  jz      short loc_18001ED59
0x18001ed4c  mov     rdx, [rbp+10h]
0x18001ed50  shl     rdx, 3
0x18001ed54  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x18001ed59  add     [rbp+10h], rsi
0x18001ed5d  mov     [rbp+8], r14
0x18001ed61  add     rsp, 20h
0x18001ed65  pop     r15
0x18001ed67  pop     r14
0x18001ed69  pop     r12
0x18001ed6b  pop     rdi
0x18001ed6c  pop     rsi
0x18001ed6d  pop     rbp
0x18001ed6e  pop     rbx
0x18001ed6f  retn
0x18001ed70  call    std__deque__TagDirectoryTree____2___DirQueItem_std__allocator__TagDirectoryTree____2___DirQueItem______Xlen
```
