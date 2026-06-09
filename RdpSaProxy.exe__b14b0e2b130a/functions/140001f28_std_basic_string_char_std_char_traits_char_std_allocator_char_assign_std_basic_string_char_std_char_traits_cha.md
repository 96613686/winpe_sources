# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,unsigned __int64,unsigned __int64)

- ea: `0x140001f28`
- end: `0x140002018`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `240`
- prototype: `void **__fastcall(void **, void **, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x140002020`

## callees

- `0x140001d18`
- `0x140001ea0`
- `0x140001f10`
- `0x140001f28`
- `0x140002200`
- `0x140002516`

## pseudocode

```c
void **__fastcall std::string::assign(void **a1, void **a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rdi
  void **v6; // rsi
  void **v7; // rbx
  unsigned __int64 v8; // rdi
  void *v9; // rax
  void *v10; // rcx
  _BYTE *v11; // rax
  void **v12; // rax

  v4 = (unsigned __int64)a2[2];
  v6 = a2;
  v7 = a1;
  if ( v4 < a3 )
    goto LABEL_27;
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( a1 == a2 )
  {
    v9 = (void *)(v8 + a3);
    if ( (unsigned __int64)a1[2] >= v8 + a3 )
    {
      if ( (unsigned __int64)a1[3] >= 0x10 )
        a1 = (void **)*a1;
      v7[2] = v9;
      *((_BYTE *)a1 + (_QWORD)v9) = 0;
      std::string::erase(v7, 0);
      return v7;
    }
LABEL_27:
    std::string::_Xran();
  }
  if ( v8 == -1 )
    std::string::_Xlen();
  if ( (unsigned __int64)a1[3] >= v8 )
  {
    if ( !v8 )
    {
      if ( (unsigned __int64)a1[3] < 0x10 )
        v11 = a1;
      else
        v11 = *a1;
      a1[2] = 0;
      *v11 = 0;
      return v7;
    }
  }
  else
  {
    std::string::_Copy((const void **)a1, v8, (size_t)a1[2]);
    if ( !v8 )
      return v7;
  }
  if ( (unsigned __int64)v6[3] >= 0x10 )
    v6 = (void **)*v6;
  if ( (unsigned __int64)v7[3] < 0x10 )
    v10 = v7;
  else
    v10 = *v7;
  memcpy_0(v10, (char *)v6 + a3, v8);
  if ( (unsigned __int64)v7[3] < 0x10 )
    v12 = v7;
  else
    v12 = (void **)*v7;
  v7[2] = (void *)v8;
  *((_BYTE *)v12 + v8) = 0;
  return v7;
}

```

## disassembly

```asm
0x140001f28  push    rbx
0x140001f2a  push    rbp
0x140001f2b  push    rsi
0x140001f2c  push    rdi
0x140001f2d  sub     rsp, 28h
0x140001f31  mov     rdi, [rdx+10h]
0x140001f35  mov     rbp, r8
0x140001f38  mov     rsi, rdx
0x140001f3b  mov     rbx, rcx
0x140001f3e  cmp     rdi, r8
0x140001f41  jb      loc_14000200C
0x140001f47  sub     rdi, r8
0x140001f4a  cmp     r9, rdi
0x140001f4d  cmovb   rdi, r9
0x140001f51  cmp     rcx, rdx
0x140001f54  jnz     short loc_140001F82
0x140001f56  lea     rax, [rdi+r8]
0x140001f5a  cmp     [rcx+10h], rax
0x140001f5e  jb      loc_14000200C
0x140001f64  cmp     qword ptr [rcx+18h], 10h
0x140001f69  jb      short loc_140001F6E
0x140001f6b  mov     rcx, [rcx]
0x140001f6e  mov     [rbx+10h], rax
0x140001f72  xor     edx, edx
0x140001f74  mov     byte ptr [rax+rcx], 0
0x140001f78  mov     rcx, rbx
0x140001f7b  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x140001f80  jmp     short loc_140002000
0x140001f82  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x140001f86  ja      loc_140002012
0x140001f8c  cmp     [rcx+18h], rdi
0x140001f90  jnb     short loc_140001FB9
0x140001f92  mov     r8, [rcx+10h]
0x140001f96  mov     rdx, rdi
0x140001f99  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x140001f9e  test    rdi, rdi
0x140001fa1  jz      short loc_140002000
0x140001fa3  cmp     qword ptr [rsi+18h], 10h
0x140001fa8  jb      short loc_140001FAD
0x140001faa  mov     rsi, [rsi]
0x140001fad  cmp     qword ptr [rbx+18h], 10h
0x140001fb2  jb      short loc_140001FDA
0x140001fb4  mov     rcx, [rbx]
0x140001fb7  jmp     short loc_140001FDD
0x140001fb9  test    rdi, rdi
0x140001fbc  jnz     short loc_140001FA3
0x140001fbe  cmp     qword ptr [rcx+18h], 10h
0x140001fc3  jb      short loc_140001FCA
0x140001fc5  mov     rax, [rcx]
0x140001fc8  jmp     short loc_140001FCD
0x140001fca  mov     rax, rbx
0x140001fcd  mov     qword ptr [rcx+10h], 0
0x140001fd5  mov     byte ptr [rax], 0
0x140001fd8  jmp     short loc_140002000
0x140001fda  mov     rcx, rbx; void *
0x140001fdd  lea     rdx, [rsi+rbp]; Src
0x140001fe1  mov     r8, rdi; Size
0x140001fe4  call    memcpy_0
0x140001fe9  cmp     qword ptr [rbx+18h], 10h
0x140001fee  jb      short loc_140001FF5
0x140001ff0  mov     rax, [rbx]
0x140001ff3  jmp     short loc_140001FF8
0x140001ff5  mov     rax, rbx
0x140001ff8  mov     [rbx+10h], rdi
0x140001ffc  mov     byte ptr [rax+rdi], 0
0x140002000  mov     rax, rbx
0x140002003  add     rsp, 28h
0x140002007  pop     rdi
0x140002008  pop     rsi
0x140002009  pop     rbp
0x14000200a  pop     rbx
0x14000200b  retn
0x14000200c  call    ?_Xran@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xran(void)
0x140002012  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
