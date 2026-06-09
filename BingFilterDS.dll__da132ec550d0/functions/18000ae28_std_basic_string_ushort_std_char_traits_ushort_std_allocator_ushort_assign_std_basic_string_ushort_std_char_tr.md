# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &,unsigned __int64,unsigned __int64)

- ea: `0x18000ae28`
- end: `0x18000af97`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `367`
- prototype: `_QWORD *__fastcall(_QWORD *, _QWORD *, unsigned __int64, unsigned __int64)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x18000a870`
- `0x18000afa0`

## callees

- `0x180002766`
- `0x180002772`
- `0x180007170`
- `0x180007188`
- `0x18000a6a8`
- `0x18000ae28`

## pseudocode

```c
_QWORD *__fastcall std::wstring::assign(_QWORD *a1, _QWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  _QWORD *v6; // r14
  _QWORD *v7; // rbx
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // r14
  _WORD *v11; // rax
  char *v12; // rcx
  unsigned __int64 v13; // r14
  _QWORD *v14; // rax
  unsigned __int64 v15; // rax
  void *v16; // rcx
  _QWORD *v17; // rax

  v4 = a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
    std::wstring::_Xran();
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = v8 + a3;
    if ( a1[2] < v8 + a3 )
      std::wstring::_Xran();
    if ( a1[3] >= 8u )
      a1 = (_QWORD *)*a1;
    v7[2] = v9;
    *((_WORD *)a1 + v9) = 0;
    v10 = v7[2];
    if ( v10 <= a3 )
    {
      if ( v7[3] < 8u )
        v11 = v7;
      else
        v11 = (_WORD *)*v7;
      v7[2] = 0;
LABEL_13:
      *v11 = 0;
      return v7;
    }
    if ( a3 )
    {
      if ( v7[3] < 8u )
        v12 = (char *)v7;
      else
        v12 = (char *)*v7;
      v13 = v10 - a3;
      if ( v13 )
        memmove_0(v12, &v12[2 * a3], 2 * v13);
      if ( v7[3] < 8u )
        v14 = v7;
      else
        v14 = (_QWORD *)*v7;
      v7[2] = v13;
      *((_WORD *)v14 + v13) = 0;
    }
  }
  else
  {
    if ( v8 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    v15 = a1[3];
    if ( v15 >= v8 )
    {
      if ( !v8 )
      {
        if ( v15 < 8 )
          v11 = a1;
        else
          v11 = (_WORD *)*a1;
        a1[2] = 0;
        goto LABEL_13;
      }
    }
    else
    {
      std::wstring::_Copy((const void **)a1, v8, a1[2]);
      if ( !v8 )
        return v7;
    }
    if ( v6[3] >= 8u )
      v6 = (_QWORD *)*v6;
    if ( v7[3] < 8u )
      v16 = v7;
    else
      v16 = (void *)*v7;
    memcpy_0(v16, (char *)v6 + 2 * a3, 2 * v8);
    if ( v7[3] < 8u )
      v17 = v7;
    else
      v17 = (_QWORD *)*v7;
    v7[2] = v8;
    *((_WORD *)v17 + v8) = 0;
  }
  return v7;
}

```

## disassembly

```asm
0x18000ae28  push    rbx
0x18000ae2a  push    rbp
0x18000ae2b  push    rsi
0x18000ae2c  push    rdi
0x18000ae2d  push    r14
0x18000ae2f  push    r15
0x18000ae31  sub     rsp, 28h
0x18000ae35  mov     rdi, [rdx+10h]
0x18000ae39  mov     rbp, r8
0x18000ae3c  mov     r14, rdx
0x18000ae3f  mov     rbx, rcx
0x18000ae42  cmp     rdi, r8
0x18000ae45  jb      loc_18000AF85
0x18000ae4b  sub     rdi, r8
0x18000ae4e  cmp     r9, rdi
0x18000ae51  cmovb   rdi, r9
0x18000ae55  cmp     rcx, rdx
0x18000ae58  jnz     loc_18000AEED
0x18000ae5e  lea     rax, [rdi+r8]
0x18000ae62  cmp     [rcx+10h], rax
0x18000ae66  jb      loc_18000AF8B
0x18000ae6c  cmp     qword ptr [rcx+18h], 8
0x18000ae71  jb      short loc_18000AE76
0x18000ae73  mov     rcx, [rcx]
0x18000ae76  xor     esi, esi
0x18000ae78  mov     [rbx+10h], rax
0x18000ae7c  mov     [rcx+rax*2], si
0x18000ae80  mov     r14, [rbx+10h]
0x18000ae84  cmp     r14, rbp
0x18000ae87  ja      short loc_18000AEA4
0x18000ae89  cmp     qword ptr [rbx+18h], 8
0x18000ae8e  jb      short loc_18000AE95
0x18000ae90  mov     rax, [rbx]
0x18000ae93  jmp     short loc_18000AE98
0x18000ae95  mov     rax, rbx
0x18000ae98  mov     [rbx+10h], rsi
0x18000ae9c  mov     [rax], si
0x18000ae9f  jmp     loc_18000AF75
0x18000aea4  test    rbp, rbp
0x18000aea7  jz      loc_18000AF75
0x18000aead  cmp     qword ptr [rbx+18h], 8
0x18000aeb2  jb      short loc_18000AEB9
0x18000aeb4  mov     rcx, [rbx]
0x18000aeb7  jmp     short loc_18000AEBC
0x18000aeb9  mov     rcx, rbx; void *
0x18000aebc  sub     r14, rbp
0x18000aebf  lea     rdi, [r14+r14]
0x18000aec3  jz      short loc_18000AED1
0x18000aec5  lea     rdx, [rcx+r8*2]; Src
0x18000aec9  mov     r8, rdi; Size
0x18000aecc  call    memmove_0
0x18000aed1  cmp     qword ptr [rbx+18h], 8
0x18000aed6  jb      short loc_18000AEDD
0x18000aed8  mov     rax, [rbx]
0x18000aedb  jmp     short loc_18000AEE0
0x18000aedd  mov     rax, rbx
0x18000aee0  mov     [rbx+10h], r14
0x18000aee4  mov     [rdi+rax], si
0x18000aee8  jmp     loc_18000AF75
0x18000aeed  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000aef7  cmp     rdi, rax
0x18000aefa  ja      loc_18000AF91
0x18000af00  mov     rax, [rcx+18h]
0x18000af04  xor     esi, esi
0x18000af06  cmp     rax, rdi
0x18000af09  jnb     short loc_18000AF32
0x18000af0b  mov     r8, [rcx+10h]
0x18000af0f  mov     rdx, rdi
0x18000af12  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000af17  test    rdi, rdi
0x18000af1a  jz      short loc_18000AF75
0x18000af1c  cmp     qword ptr [r14+18h], 8
0x18000af21  jb      short loc_18000AF26
0x18000af23  mov     r14, [r14]
0x18000af26  cmp     qword ptr [rbx+18h], 8
0x18000af2b  jb      short loc_18000AF4E
0x18000af2d  mov     rcx, [rbx]
0x18000af30  jmp     short loc_18000AF51
0x18000af32  test    rdi, rdi
0x18000af35  jnz     short loc_18000AF1C
0x18000af37  cmp     rax, 8
0x18000af3b  jb      short loc_18000AF42
0x18000af3d  mov     rax, [rcx]
0x18000af40  jmp     short loc_18000AF45
0x18000af42  mov     rax, rbx
0x18000af45  mov     [rcx+10h], rsi
0x18000af49  jmp     loc_18000AE9C
0x18000af4e  mov     rcx, rbx; void *
0x18000af51  lea     r8, [rdi+rdi]; Size
0x18000af55  lea     rdx, [r14+rbp*2]; Src
0x18000af59  call    memcpy_0
0x18000af5e  cmp     qword ptr [rbx+18h], 8
0x18000af63  jb      short loc_18000AF6A
0x18000af65  mov     rax, [rbx]
0x18000af68  jmp     short loc_18000AF6D
0x18000af6a  mov     rax, rbx
0x18000af6d  mov     [rbx+10h], rdi
0x18000af71  mov     [rax+rdi*2], si
0x18000af75  mov     rax, rbx
0x18000af78  add     rsp, 28h
0x18000af7c  pop     r15
0x18000af7e  pop     r14
0x18000af80  pop     rdi
0x18000af81  pop     rsi
0x18000af82  pop     rbp
0x18000af83  pop     rbx
0x18000af84  retn
0x18000af85  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18000af8b  call    ?_Xran@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18000af91  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
