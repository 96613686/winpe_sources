# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::_Construct<1,ushort const *>(ushort const * const,unsigned __int64)

- ea: `0x18000b238`
- end: `0x18000b33b`
- name: `??$_Construct@$00PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXQEBG_K@Z`
- size: `259`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000bc5c`
- `0x18000e640`
- `0x18000e950`

## callees

- `0x180002ec0`
- `0x180003a08`
- `0x18000b238`
- `0x180010e54`
- `0x180010f50`

## pseudocode

```c
void *__fastcall std::wstring::_Construct<1,unsigned short const *>(_QWORD *a1, const void *a2, unsigned __int64 a3)
{
  __int64 v3; // rbp
  __int64 v7; // rbx
  void *result; // rax
  size_t v9; // rcx
  void *v10; // rax
  _QWORD *v11; // rdi
  size_t v12; // rbx

  v3 = 0x7FFFFFFFFFFFFFFELL;
  if ( a3 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( a3 <= 7 )
  {
    a1[2] = a3;
    v7 = 2 * a3;
    a1[3] = 7;
    result = memcpy_0(a1, a2, 2 * a3);
    *(_WORD *)((char *)a1 + v7) = 0;
    return result;
  }
  if ( (a3 | 7) <= 0x7FFFFFFFFFFFFFFELL )
  {
    v3 = a3 | 7;
    if ( (a3 | 7) < 0xA )
      v3 = 10;
    if ( (unsigned __int64)(v3 + 1) > 0x7FFFFFFFFFFFFFFFLL )
      goto LABEL_19;
    v9 = 2 * (v3 + 1);
    if ( !v9 )
    {
      v11 = 0;
      goto LABEL_17;
    }
  }
  else
  {
    v9 = -2;
  }
  if ( v9 >= 0x1000 )
  {
    if ( v9 + 39 >= v9 )
    {
      v10 = operator new(v9 + 39);
      if ( !v10 )
        __fastfail(5u);
      v11 = (_QWORD *)(((unsigned __int64)v10 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v11 - 1) = v10;
      goto LABEL_17;
    }
LABEL_19:
    __scrt_throw_std_bad_array_new_length();
  }
  v11 = operator new(v9);
LABEL_17:
  a1[2] = a3;
  v12 = 2 * a3;
  *a1 = v11;
  a1[3] = v3;
  result = memcpy_0(v11, a2, v12);
  *(_WORD *)((char *)v11 + v12) = 0;
  return result;
}

```

## disassembly

```asm
0x18000b238  push    rbx
0x18000b23a  push    rbp
0x18000b23b  push    rsi
0x18000b23c  push    rdi
0x18000b23d  push    r14
0x18000b23f  push    r15
0x18000b241  sub     rsp, 28h
0x18000b245  mov     rbp, 7FFFFFFFFFFFFFFEh
0x18000b24f  mov     rbx, r8
0x18000b252  mov     r15, rdx
0x18000b255  mov     r14, rcx
0x18000b258  cmp     r8, rbp
0x18000b25b  ja      loc_18000B32F
0x18000b261  cmp     rbx, 7
0x18000b265  ja      short loc_18000B292
0x18000b267  mov     [rcx+10h], rbx
0x18000b26b  add     rbx, rbx
0x18000b26e  mov     r8, rbx; Size
0x18000b271  mov     qword ptr [rcx+18h], 7
0x18000b279  call    memcpy_0
0x18000b27e  xor     esi, esi
0x18000b280  mov     [rbx+r14], si
0x18000b285  add     rsp, 28h
0x18000b289  pop     r15
0x18000b28b  pop     r14
0x18000b28d  pop     rdi
0x18000b28e  pop     rsi
0x18000b28f  pop     rbp
0x18000b290  pop     rbx
0x18000b291  retn
0x18000b292  mov     rax, rbx
0x18000b295  xor     esi, esi
0x18000b297  or      rax, 7
0x18000b29b  cmp     rax, rbp
0x18000b29e  jbe     short loc_18000B2C8
0x18000b2a0  lea     rcx, [rsi-2]; Size
0x18000b2a4  cmp     rcx, 1000h
0x18000b2ab  jb      short loc_18000B302
0x18000b2ad  lea     rax, [rcx+27h]
0x18000b2b1  cmp     rax, rcx
0x18000b2b4  jbe     short loc_18000B335
0x18000b2b6  mov     rcx, rax; Size
0x18000b2b9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b2be  test    rax, rax
0x18000b2c1  jnz     short loc_18000B2F4
0x18000b2c3  lea     ecx, [rax+5]
0x18000b2c6  int     29h; Win8: RtlFailFast(ecx)
0x18000b2c8  mov     ecx, 0Ah
0x18000b2cd  mov     rbp, rax
0x18000b2d0  cmp     rax, rcx
0x18000b2d3  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000b2dd  cmovb   rbp, rcx
0x18000b2e1  lea     rcx, [rbp+1]
0x18000b2e5  cmp     rcx, rax
0x18000b2e8  ja      short loc_18000B335
0x18000b2ea  add     rcx, rcx
0x18000b2ed  jnz     short loc_18000B2A4
0x18000b2ef  mov     rdi, rsi
0x18000b2f2  jmp     short loc_18000B30A
0x18000b2f4  lea     rdi, [rax+27h]
0x18000b2f8  and     rdi, 0FFFFFFFFFFFFFFE0h
0x18000b2fc  mov     [rdi-8], rax
0x18000b300  jmp     short loc_18000B30A
0x18000b302  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000b307  mov     rdi, rax
0x18000b30a  mov     [r14+10h], rbx
0x18000b30e  mov     rdx, r15; Src
0x18000b311  add     rbx, rbx
0x18000b314  mov     [r14], rdi
0x18000b317  mov     r8, rbx; Size
0x18000b31a  mov     [r14+18h], rbp
0x18000b31e  mov     rcx, rdi; void *
0x18000b321  call    memcpy_0
0x18000b326  mov     [rbx+rdi], si
0x18000b32a  jmp     loc_18000B285
0x18000b32f  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x18000b335  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
