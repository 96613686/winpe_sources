# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Construct<1,char const *>(char const * const,unsigned __int64)

- ea: `0x180007850`
- end: `0x18000793a`
- name: `??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z`
- size: `234`
- prototype: `void *__fastcall(_QWORD *, const void *, size_t)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180008620`
- `0x18000b7a0`
- `0x18000b7f0`

## callees

- `0x18000260c`
- `0x180007850`
- `0x18000b278`
- `0x18000b37c`
- `0x18000bd94`

## pseudocode

```c
void *__fastcall std::string::_Construct<1,char const *>(_QWORD *a1, const void *a2, size_t a3)
{
  __int64 v3; // rsi
  void *result; // rax
  size_t v8; // rax
  void *v9; // rax
  size_t v10; // rcx
  _QWORD *v11; // rdi

  v3 = 0x7FFFFFFFFFFFFFFFLL;
  if ( a3 > 0x7FFFFFFFFFFFFFFFLL )
    std::_Xlen_string();
  if ( a3 <= 0xF )
  {
    a1[2] = a3;
    a1[3] = 15;
    result = memcpy_0(a1, a2, a3);
    *((_BYTE *)a1 + a3) = 0;
    return result;
  }
  if ( (a3 | 0xF) > 0x7FFFFFFFFFFFFFFFLL )
  {
    v8 = 0x8000000000000027uLL;
LABEL_6:
    v9 = operator new(v8);
    if ( !v9 )
      __fastfail(5u);
    v11 = (_QWORD *)(((unsigned __int64)v9 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
    *(v11 - 1) = v9;
    goto LABEL_17;
  }
  v3 = a3 | 0xF;
  if ( (a3 | 0xF) < 0x16 )
    v3 = 22;
  v10 = v3 + 1;
  if ( v3 == -1 )
  {
    v11 = 0;
  }
  else
  {
    if ( v10 >= 0x1000 )
    {
      v8 = v3 + 40;
      if ( v3 + 40 < (unsigned __int64)(v3 + 1) )
        __scrt_throw_std_bad_array_new_length();
      goto LABEL_6;
    }
    v11 = operator new(v10);
  }
LABEL_17:
  *a1 = v11;
  a1[2] = a3;
  a1[3] = v3;
  result = memcpy_0(v11, a2, a3);
  *((_BYTE *)v11 + a3) = 0;
  return result;
}

```

## disassembly

```asm
0x180007850  push    rbx
0x180007852  push    rbp
0x180007853  push    rsi
0x180007854  push    rdi
0x180007855  push    r14
0x180007857  sub     rsp, 20h
0x18000785b  mov     rsi, 7FFFFFFFFFFFFFFFh
0x180007865  mov     rbx, r8
0x180007868  mov     rbp, rdx
0x18000786b  mov     r14, rcx
0x18000786e  cmp     r8, rsi
0x180007871  ja      loc_18000792E
0x180007877  cmp     rbx, 0Fh
0x18000787b  ja      short loc_180007898
0x18000787d  mov     [rcx+10h], rbx
0x180007881  mov     qword ptr [rcx+18h], 0Fh
0x180007889  call    memcpy_0
0x18000788e  mov     byte ptr [rbx+r14], 0
0x180007893  jmp     loc_180007923
0x180007898  mov     rax, rbx
0x18000789b  or      rax, 0Fh
0x18000789f  cmp     rax, rsi
0x1800078a2  jbe     short loc_1800078C0
0x1800078a4  mov     rax, 8000000000000027h
0x1800078ae  mov     rcx, rax; Size
0x1800078b1  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800078b6  test    rax, rax
0x1800078b9  jnz     short loc_1800078F0
0x1800078bb  lea     ecx, [rax+5]
0x1800078be  int     29h; Win8: RtlFailFast(ecx)
0x1800078c0  mov     ecx, 16h
0x1800078c5  mov     rsi, rax
0x1800078c8  cmp     rax, rcx
0x1800078cb  cmovb   rsi, rcx
0x1800078cf  lea     rcx, [rsi+1]; Size
0x1800078d3  test    rcx, rcx
0x1800078d6  jnz     short loc_1800078DC
0x1800078d8  xor     edi, edi
0x1800078da  jmp     short loc_180007906
0x1800078dc  cmp     rcx, 1000h
0x1800078e3  jb      short loc_1800078FE
0x1800078e5  lea     rax, [rcx+27h]
0x1800078e9  cmp     rax, rcx
0x1800078ec  jbe     short loc_180007934
0x1800078ee  jmp     short loc_1800078AE
0x1800078f0  lea     rdi, [rax+27h]
0x1800078f4  and     rdi, 0FFFFFFFFFFFFFFE0h
0x1800078f8  mov     [rdi-8], rax
0x1800078fc  jmp     short loc_180007906
0x1800078fe  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007903  mov     rdi, rax
0x180007906  mov     r8, rbx; Size
0x180007909  mov     [r14], rdi
0x18000790c  mov     rdx, rbp; Src
0x18000790f  mov     [r14+10h], rbx
0x180007913  mov     rcx, rdi; void *
0x180007916  mov     [r14+18h], rsi
0x18000791a  call    memcpy_0
0x18000791f  mov     byte ptr [rdi+rbx], 0
0x180007923  add     rsp, 20h
0x180007927  pop     r14
0x180007929  pop     rdi
0x18000792a  pop     rsi
0x18000792b  pop     rbp
0x18000792c  pop     rbx
0x18000792d  retn
0x18000792e  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180007934  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
