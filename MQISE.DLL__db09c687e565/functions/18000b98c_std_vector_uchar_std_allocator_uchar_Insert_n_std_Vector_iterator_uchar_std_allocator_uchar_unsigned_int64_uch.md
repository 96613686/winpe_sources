# std::vector<uchar,std::allocator<uchar>>::_Insert_n(std::_Vector_iterator<uchar,std::allocator<uchar>>,unsigned __int64,uchar const &)

- ea: `0x18000b98c`
- end: `0x18000bbe9`
- name: `?_Insert_n@?$vector@EV?$allocator@E@std@@@std@@IEAAXV?$_Vector_iterator@EV?$allocator@E@std@@@2@_KAEBE@Z`
- size: `605`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18000cc28`

## callees

- `0x180001c0c`
- `0x18000310c`
- `0x18000b98c`
- `0x18000bc60`
- `0x18000e61c`
- `0x18000f5c2`

## import_xrefs

- `msvcrt!free` at `0x18000bad5`
- `msvcrt!free` at `0x18000bad5`
- `msvcrt!memmove_s` at `0x18000ba92`
- `msvcrt!memmove_s` at `0x18000babc`
- `msvcrt!memmove_s` at `0x18000bb17`
- `msvcrt!memmove_s` at `0x18000bb61`
- `msvcrt!memmove_s` at `0x18000bb85`
- `msvcrt!memmove_s` at `0x18000ba92`
- `msvcrt!memmove_s` at `0x18000babc`
- `msvcrt!memmove_s` at `0x18000bb17`
- `msvcrt!memmove_s` at `0x18000bb61`
- `msvcrt!memmove_s` at `0x18000bb85`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall std::vector<unsigned char>::_Insert_n(__int64 a1, _BYTE *a2, size_t a3, char *a4)
{
  __int64 v7; // rdx
  size_t v8; // r8
  void **v9; // r14
  unsigned __int64 v10; // rax
  char v11; // r12
  char *v12; // rax
  unsigned __int64 v13; // rsi
  char *v14; // rax
  char *v15; // rax
  unsigned __int64 v16; // rcx
  char *v17; // rax
  int v18; // edx
  char *v19; // r15
  _BYTE *v20; // r8
  signed __int64 v21; // r12
  char *v22; // r12
  __int64 v23; // rcx
  __int64 v24; // r8
  _BYTE *v25; // rcx
  char *v26; // r15
  unsigned __int64 v27; // rsi
  size_t v28; // r15
  _BYTE *v29; // rcx
  size_t v30; // r8
  signed __int64 v31; // rsi
  _BYTE pExceptionObject[32]; // [rsp+20h] [rbp-48h] BYREF
  char Val; // [rsp+70h] [rbp+8h]
  char *v34; // [rsp+80h] [rbp+18h]

  v7 = *(_QWORD *)(a1 + 8);
  if ( v7 )
    v8 = *(_QWORD *)(a1 + 24) - v7;
  else
    v8 = 0;
  if ( !a3 )
    return;
  v9 = (void **)(a1 + 16);
  if ( v7 )
    v10 = (unsigned __int64)*v9 - v7;
  else
    v10 = 0;
  if ( ~v10 < a3 )
    std::vector<char>::_Xlen(a1, v7, v8);
  v11 = *a4;
  Val = *a4;
  if ( v7 )
    v12 = (char *)*v9 - v7;
  else
    v12 = 0;
  if ( v8 < (unsigned __int64)&v12[a3] )
  {
    v13 = 0;
    if ( ~(v8 >> 1) >= v8 )
      v13 = v8 + (v8 >> 1);
    if ( v7 )
      v14 = (char *)*v9 - v7;
    else
      v14 = 0;
    if ( v13 < (unsigned __int64)&v14[a3] )
    {
      if ( v7 )
        v15 = (char *)*v9 - v7;
      else
        v15 = 0;
      v13 = (unsigned __int64)&v15[a3];
    }
    if ( v13 )
    {
      if ( !(0xFFFFFFFFFFFFFFFFuLL / v13) )
      {
        std::bad_alloc::bad_alloc((std::bad_alloc *)pExceptionObject, 0);
        throw (std::bad_alloc *)pExceptionObject;
      }
      v16 = v13;
    }
    else
    {
      v16 = 0;
    }
    v17 = (char *)MmAllocate(v16);
    try
    {
      v19 = v17;
      v34 = v17;
      v20 = *(_BYTE **)(a1 + 8);
      v21 = a2 - v20;
      if ( a2 != v20 )
        memmove_s(v17, a2 - v20, v20, a2 - v20);
      v22 = &v19[v21];
      LOBYTE(v18) = Val;
      memset_0(v22, v18, a3);
      if ( *v9 != a2 )
        memmove_s(&v22[a3], (_BYTE *)*v9 - a2, a2, (_BYTE *)*v9 - a2);
    }
    catch ( ... )
    {
      std::allocator<std::_Tree_nod<std::_Tmap_traits<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>,RpcHandleInfo,std::less<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70>>,std::allocator<std::pair<std::basic_string<char,std::char_traits<char>,std::allocator_static<char>,_STL70> const,RpcHandleInfo>>,1>>::_Node>::deallocate(
        v23,
        v34,
        v24);
      throw;
    }
    v25 = *(_BYTE **)(a1 + 8);
    if ( v25 )
    {
      a3 += (_BYTE *)*v9 - v25;
      free(v25);
    }
    *(_QWORD *)(a1 + 24) = &v19[v13];
    *v9 = &v19[a3];
    *(_QWORD *)(a1 + 8) = v19;
    return;
  }
  v26 = (char *)*v9;
  v27 = (_BYTE *)*v9 - a2;
  if ( v27 >= a3 )
  {
    memmove_s(*v9, a3, &v26[-a3], a3);
    *v9 = &v26[a3];
    v31 = v27 - a3;
    if ( v31 > 0 )
      memmove_s(&v26[-v31], v31, a2, v31);
    if ( a2 > &a2[a3] )
      a3 = 0;
    if ( a3 )
    {
      v30 = a3;
LABEL_50:
      LOBYTE(v7) = v11;
      memset_0(a2, v7, v30);
    }
  }
  else
  {
    if ( v27 )
      memmove_s(&a2[a3], (_BYTE *)*v9 - a2, a2, (_BYTE *)*v9 - a2);
    v28 = &a2[a3] - (_BYTE *)*v9;
    if ( v28 )
    {
      LOBYTE(v7) = v11;
      memset_0(*v9, v7, v28);
    }
    v29 = *v9;
    *v9 = (char *)*v9 + a3;
    v30 = v29 - a2;
    if ( a2 > v29 )
      v30 = 0;
    if ( v30 )
      goto LABEL_50;
  }
}

```

## disassembly

```asm
0x18000b98c  mov     [rsp+arg_8], rbx
0x18000b991  mov     [rsp+arg_18], rsi
0x18000b996  push    rdi
0x18000b997  push    r12
0x18000b999  push    r13
0x18000b99b  push    r14
0x18000b99d  push    r15
0x18000b99f  sub     rsp, 40h
0x18000b9a3  mov     rdi, r8
0x18000b9a6  mov     rbx, rdx
0x18000b9a9  mov     r13, rcx
0x18000b9ac  mov     rdx, [rcx+8]
0x18000b9b0  test    rdx, rdx
0x18000b9b3  jnz     short loc_18000B9BA
0x18000b9b5  xor     r8d, r8d
0x18000b9b8  jmp     short loc_18000B9C1
0x18000b9ba  mov     r8, [rcx+18h]
0x18000b9be  sub     r8, rdx
0x18000b9c1  test    rdi, rdi
0x18000b9c4  jz      loc_18000BBAB
0x18000b9ca  lea     r14, [rcx+10h]
0x18000b9ce  test    rdx, rdx
0x18000b9d1  jnz     short loc_18000B9D7
0x18000b9d3  xor     eax, eax
0x18000b9d5  jmp     short loc_18000B9DD
0x18000b9d7  mov     rax, [r14]
0x18000b9da  sub     rax, rdx
0x18000b9dd  not     rax
0x18000b9e0  cmp     rax, rdi
0x18000b9e3  jb      loc_18000BBC5
0x18000b9e9  mov     r12b, [r9]
0x18000b9ec  mov     byte ptr [rsp+68h+Val], r12b
0x18000b9f1  test    rdx, rdx
0x18000b9f4  jnz     short loc_18000B9FA
0x18000b9f6  xor     eax, eax
0x18000b9f8  jmp     short loc_18000BA00
0x18000b9fa  mov     rax, [r14]
0x18000b9fd  sub     rax, rdx
0x18000ba00  add     rax, rdi
0x18000ba03  cmp     r8, rax
0x18000ba06  jnb     loc_18000BAF4
0x18000ba0c  mov     rax, r8
0x18000ba0f  shr     rax, 1
0x18000ba12  mov     rcx, rax
0x18000ba15  not     rcx
0x18000ba18  add     rax, r8
0x18000ba1b  xor     esi, esi
0x18000ba1d  cmp     rcx, r8
0x18000ba20  cmovnb  rsi, rax
0x18000ba24  test    rdx, rdx
0x18000ba27  jnz     short loc_18000BA2D
0x18000ba29  xor     eax, eax
0x18000ba2b  jmp     short loc_18000BA33
0x18000ba2d  mov     rax, [r14]
0x18000ba30  sub     rax, rdx
0x18000ba33  add     rax, rdi
0x18000ba36  cmp     rsi, rax
0x18000ba39  jnb     short loc_18000BA4E
0x18000ba3b  test    rdx, rdx
0x18000ba3e  jnz     short loc_18000BA44
0x18000ba40  xor     eax, eax
0x18000ba42  jmp     short loc_18000BA4A
0x18000ba44  mov     rax, [r14]
0x18000ba47  sub     rax, rdx
0x18000ba4a  lea     rsi, [rax+rdi]
0x18000ba4e  test    rsi, rsi
0x18000ba51  jnz     short loc_18000BA57
0x18000ba53  xor     ecx, ecx
0x18000ba55  jmp     short loc_18000BA6D
0x18000ba57  xor     edx, edx
0x18000ba59  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000ba5d  div     rsi
0x18000ba60  cmp     rax, 1
0x18000ba64  jb      loc_18000BBCB
0x18000ba6a  mov     rcx, rsi; unsigned __int64
0x18000ba6d  call    ?MmAllocate@@YAPEAX_K@Z; MmAllocate(unsigned __int64)
0x18000ba72  mov     r15, rax
0x18000ba75  mov     [rsp+68h+arg_10], rax
0x18000ba7d  mov     r8, [r13+8]; Source
0x18000ba81  mov     r12, rbx
0x18000ba84  sub     r12, r8
0x18000ba87  jz      short loc_18000BA98
0x18000ba89  mov     r9, r12; SourceSize
0x18000ba8c  mov     rdx, r12; DestinationSize
0x18000ba8f  mov     rcx, rax; Destination
0x18000ba92  call    cs:__imp_memmove_s
0x18000ba98  add     r12, r15
0x18000ba9b  mov     r8, rdi; Size
0x18000ba9e  mov     dl, byte ptr [rsp+68h+Val]; Val
0x18000baa2  mov     rcx, r12; void *
0x18000baa5  call    memset_0
0x18000baaa  mov     rdx, [r14]
0x18000baad  sub     rdx, rbx; DestinationSize
0x18000bab0  jz      short loc_18000BAC3
0x18000bab2  lea     rcx, [r12+rdi]; Destination
0x18000bab6  mov     r9, rdx; SourceSize
0x18000bab9  mov     r8, rbx; Source
0x18000babc  call    cs:__imp_memmove_s
0x18000bac2  nop
0x18000bac3  mov     rcx, [r13+8]; Block
0x18000bac7  test    rcx, rcx
0x18000baca  jz      short loc_18000BADC
0x18000bacc  mov     rax, [r14]
0x18000bacf  sub     rax, rcx
0x18000bad2  add     rdi, rax
0x18000bad5  call    cs:__imp_free
0x18000badb  nop
0x18000badc  lea     rax, [r15+rsi]
0x18000bae0  mov     [r13+18h], rax
0x18000bae4  lea     rax, [rdi+r15]
0x18000bae8  mov     [r14], rax
0x18000baeb  mov     [r13+8], r15
0x18000baef  jmp     loc_18000BBAB
0x18000baf4  mov     r15, [r14]
0x18000baf7  mov     rsi, r15
0x18000bafa  sub     rsi, rbx
0x18000bafd  cmp     rsi, rdi
0x18000bb00  jnb     short loc_18000BB52
0x18000bb02  lea     r15, [rbx+rdi]
0x18000bb06  test    rsi, rsi
0x18000bb09  jz      short loc_18000BB1E
0x18000bb0b  mov     r9, rsi; SourceSize
0x18000bb0e  mov     r8, rbx; Source
0x18000bb11  mov     rdx, rsi; DestinationSize
0x18000bb14  mov     rcx, r15; Destination
0x18000bb17  call    cs:__imp_memmove_s
0x18000bb1d  nop
0x18000bb1e  sub     r15, [r14]
0x18000bb21  jz      short loc_18000BB32
0x18000bb23  mov     r8, r15; Size
0x18000bb26  mov     dl, r12b; Val
0x18000bb29  mov     rcx, [r14]; void *
0x18000bb2c  call    memset_0
0x18000bb31  nop
0x18000bb32  mov     rcx, [r14]
0x18000bb35  lea     rax, [rcx+rdi]
0x18000bb39  mov     [r14], rax
0x18000bb3c  mov     r8, rcx
0x18000bb3f  sub     r8, rbx
0x18000bb42  xor     eax, eax
0x18000bb44  cmp     rbx, rcx
0x18000bb47  cmova   r8, rax
0x18000bb4b  test    r8, r8
0x18000bb4e  jz      short loc_18000BBAB
0x18000bb50  jmp     short loc_18000BBA0
0x18000bb52  mov     r8, r15
0x18000bb55  sub     r8, rdi; Source
0x18000bb58  mov     r9, rdi; SourceSize
0x18000bb5b  mov     rdx, rdi; DestinationSize
0x18000bb5e  mov     rcx, r15; Destination
0x18000bb61  call    cs:__imp_memmove_s
0x18000bb67  lea     rax, [r15+rdi]
0x18000bb6b  mov     [r14], rax
0x18000bb6e  sub     rsi, rdi
0x18000bb71  test    rsi, rsi
0x18000bb74  jle     short loc_18000BB8B
0x18000bb76  sub     r15, rsi
0x18000bb79  mov     r9, rsi; SourceSize
0x18000bb7c  mov     r8, rbx; Source
0x18000bb7f  mov     rdx, rsi; DestinationSize
0x18000bb82  mov     rcx, r15; Destination
0x18000bb85  call    cs:__imp_memmove_s
0x18000bb8b  lea     rcx, [rbx+rdi]
0x18000bb8f  xor     eax, eax
0x18000bb91  cmp     rbx, rcx
0x18000bb94  cmova   rdi, rax
0x18000bb98  test    rdi, rdi
0x18000bb9b  jz      short loc_18000BBAB
0x18000bb9d  mov     r8, rdi; Size
0x18000bba0  mov     dl, r12b; Val
0x18000bba3  mov     rcx, rbx; void *
0x18000bba6  call    memset_0
0x18000bbab  lea     r11, [rsp+68h+var_28]
0x18000bbb0  mov     rbx, [r11+38h]
0x18000bbb4  mov     rsi, [r11+48h]
0x18000bbb8  mov     rsp, r11
0x18000bbbb  pop     r15
0x18000bbbd  pop     r14
0x18000bbbf  pop     r13
0x18000bbc1  pop     r12
0x18000bbc3  pop     rdi
0x18000bbc4  retn
0x18000bbc5  call    ?_Xlen@?$vector@DV?$allocator@D@std@@@std@@KAXXZ; std::vector<char>::_Xlen(void)
0x18000bbcb  xor     edx, edx; char *
0x18000bbcd  lea     rcx, [rsp+68h+pExceptionObject]; this
0x18000bbd2  call    ??0bad_alloc@std@@QEAA@PEBD@Z; std::bad_alloc::bad_alloc(char const *)
0x18000bbd7  lea     rdx, _TI2?AVbad_alloc@std@@; pThrowInfo
0x18000bbde  lea     rcx, [rsp+68h+pExceptionObject]; pExceptionObject
0x18000bbe3  call    _CxxThrowException_0
```
