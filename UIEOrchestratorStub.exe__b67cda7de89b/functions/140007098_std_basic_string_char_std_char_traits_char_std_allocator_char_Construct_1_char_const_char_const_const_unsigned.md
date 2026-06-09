# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::_Construct<1,char const *>(char const * const,unsigned __int64)

- ea: `0x140007098`
- end: `0x140007182`
- name: `??$_Construct@$00PEBD@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXQEBD_K@Z`
- size: `234`
- prototype: `void *__fastcall(_QWORD *, const void *, size_t)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140007e8c`
- `0x14000a540`
- `0x14000a590`

## callees

- `0x1400023ec`
- `0x140007098`
- `0x14000a1a8`
- `0x14000a2ac`
- `0x14000ad14`

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
0x140007098  push    rbx
0x14000709a  push    rbp
0x14000709b  push    rsi
0x14000709c  push    rdi
0x14000709d  push    r14
0x14000709f  sub     rsp, 20h
0x1400070a3  mov     rsi, 7FFFFFFFFFFFFFFFh
0x1400070ad  mov     rbx, r8
0x1400070b0  mov     rbp, rdx
0x1400070b3  mov     r14, rcx
0x1400070b6  cmp     r8, rsi
0x1400070b9  ja      loc_140007176
0x1400070bf  cmp     rbx, 0Fh
0x1400070c3  ja      short loc_1400070E0
0x1400070c5  mov     [rcx+10h], rbx
0x1400070c9  mov     qword ptr [rcx+18h], 0Fh
0x1400070d1  call    memcpy_0
0x1400070d6  mov     byte ptr [rbx+r14], 0
0x1400070db  jmp     loc_14000716B
0x1400070e0  mov     rax, rbx
0x1400070e3  or      rax, 0Fh
0x1400070e7  cmp     rax, rsi
0x1400070ea  jbe     short loc_140007108
0x1400070ec  mov     rax, 8000000000000027h
0x1400070f6  mov     rcx, rax; Size
0x1400070f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400070fe  test    rax, rax
0x140007101  jnz     short loc_140007138
0x140007103  lea     ecx, [rax+5]
0x140007106  int     29h; Win8: RtlFailFast(ecx)
0x140007108  mov     ecx, 16h
0x14000710d  mov     rsi, rax
0x140007110  cmp     rax, rcx
0x140007113  cmovb   rsi, rcx
0x140007117  lea     rcx, [rsi+1]; Size
0x14000711b  test    rcx, rcx
0x14000711e  jnz     short loc_140007124
0x140007120  xor     edi, edi
0x140007122  jmp     short loc_14000714E
0x140007124  cmp     rcx, 1000h
0x14000712b  jb      short loc_140007146
0x14000712d  lea     rax, [rcx+27h]
0x140007131  cmp     rax, rcx
0x140007134  jbe     short loc_14000717C
0x140007136  jmp     short loc_1400070F6
0x140007138  lea     rdi, [rax+27h]
0x14000713c  and     rdi, 0FFFFFFFFFFFFFFE0h
0x140007140  mov     [rdi-8], rax
0x140007144  jmp     short loc_14000714E
0x140007146  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000714b  mov     rdi, rax
0x14000714e  mov     r8, rbx; Size
0x140007151  mov     [r14], rdi
0x140007154  mov     rdx, rbp; Src
0x140007157  mov     [r14+10h], rbx
0x14000715b  mov     rcx, rdi; void *
0x14000715e  mov     [r14+18h], rsi
0x140007162  call    memcpy_0
0x140007167  mov     byte ptr [rdi+rbx], 0
0x14000716b  add     rsp, 20h
0x14000716f  pop     r14
0x140007171  pop     rdi
0x140007172  pop     rsi
0x140007173  pop     rbp
0x140007174  pop     rbx
0x140007175  retn
0x140007176  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x14000717c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
