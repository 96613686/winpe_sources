# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x140006594`
- end: `0x14000668b`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140006810`
- `0x140006880`
- `0x140006910`

## callees

- `0x1400020c6`
- `0x140006314`
- `0x14000646c`
- `0x14000649c`
- `0x140006594`

## pseudocode

```c
size_t *__fastcall std::string::assign(size_t *a1, char *Src, size_t Size)
{
  size_t *v5; // rbx
  char *v6; // rax
  void *v8; // rcx
  _BYTE *v9; // rax
  size_t v10; // rax

  v5 = a1;
  if ( Src )
  {
    v6 = a1[3] < 0x10 ? (char *)a1 : (char *)*a1;
    if ( Src >= v6 )
    {
      if ( a1[3] >= 0x10 )
        a1 = (size_t *)*a1;
      if ( (char *)a1 + v5[2] > Src )
        return (size_t *)std::string::assign(v5);
    }
  }
  if ( Size == -1 )
    std::wstring::_Xlen();
  if ( v5[3] >= Size )
  {
    if ( !Size )
    {
      if ( v5[3] < 0x10 )
        v9 = v5;
      else
        v9 = (_BYTE *)*v5;
      v5[2] = 0;
      *v9 = 0;
      return v5;
    }
    goto LABEL_13;
  }
  std::string::_Copy((const void **)v5, Size, v5[2]);
  if ( Size )
  {
LABEL_13:
    if ( v5[3] < 0x10 )
      v8 = v5;
    else
      v8 = (void *)*v5;
    memcpy_0(v8, Src, Size);
    if ( v5[3] < 0x10 )
      v10 = (size_t)v5;
    else
      v10 = *v5;
    v5[2] = Size;
    *(_BYTE *)(v10 + Size) = 0;
  }
  return v5;
}

```

## disassembly

```asm
0x140006594  mov     [rsp+arg_0], rbx
0x140006599  mov     [rsp+arg_8], rsi
0x14000659e  push    rdi
0x14000659f  sub     rsp, 20h
0x1400065a3  mov     rdi, r8
0x1400065a6  mov     rsi, rdx
0x1400065a9  mov     rbx, rcx
0x1400065ac  test    rdx, rdx
0x1400065af  jz      short loc_1400065FD
0x1400065b1  cmp     qword ptr [rcx+18h], 10h
0x1400065b6  jb      short loc_1400065BD
0x1400065b8  mov     rax, [rcx]
0x1400065bb  jmp     short loc_1400065C0
0x1400065bd  mov     rax, rbx
0x1400065c0  cmp     rsi, rax
0x1400065c3  jb      short loc_1400065FD
0x1400065c5  cmp     qword ptr [rcx+18h], 10h
0x1400065ca  jb      short loc_1400065CF
0x1400065cc  mov     rcx, [rcx]
0x1400065cf  add     rcx, [rbx+10h]
0x1400065d3  cmp     rcx, rsi
0x1400065d6  jbe     short loc_1400065FD
0x1400065d8  cmp     qword ptr [rbx+18h], 10h
0x1400065dd  jb      short loc_1400065E4
0x1400065df  mov     rax, [rbx]
0x1400065e2  jmp     short loc_1400065E7
0x1400065e4  mov     rax, rbx
0x1400065e7  sub     rsi, rax
0x1400065ea  mov     r9, rdi
0x1400065ed  mov     r8, rsi
0x1400065f0  mov     rdx, rbx
0x1400065f3  mov     rcx, rbx; void *
0x1400065f6  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x1400065fb  jmp     short loc_140006672
0x1400065fd  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x140006601  ja      short loc_140006682
0x140006603  cmp     [rbx+18h], rdi
0x140006607  jnb     short loc_140006629
0x140006609  mov     r8, [rbx+10h]
0x14000660d  mov     rdx, rdi
0x140006610  mov     rcx, rbx; Src
0x140006613  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x140006618  test    rdi, rdi
0x14000661b  jz      short loc_14000666F
0x14000661d  cmp     qword ptr [rbx+18h], 10h
0x140006622  jb      short loc_14000664A
0x140006624  mov     rcx, [rbx]
0x140006627  jmp     short loc_14000664D
0x140006629  test    rdi, rdi
0x14000662c  jnz     short loc_14000661D
0x14000662e  cmp     qword ptr [rbx+18h], 10h
0x140006633  jb      short loc_14000663A
0x140006635  mov     rax, [rbx]
0x140006638  jmp     short loc_14000663D
0x14000663a  mov     rax, rbx
0x14000663d  mov     qword ptr [rbx+10h], 0
0x140006645  mov     byte ptr [rax], 0
0x140006648  jmp     short loc_14000666F
0x14000664a  mov     rcx, rbx; void *
0x14000664d  mov     r8, rdi; Size
0x140006650  mov     rdx, rsi; Src
0x140006653  call    memcpy_0
0x140006658  cmp     qword ptr [rbx+18h], 10h
0x14000665d  jb      short loc_140006664
0x14000665f  mov     rax, [rbx]
0x140006662  jmp     short loc_140006667
0x140006664  mov     rax, rbx
0x140006667  mov     [rbx+10h], rdi
0x14000666b  mov     byte ptr [rax+rdi], 0
0x14000666f  mov     rax, rbx
0x140006672  mov     rbx, [rsp+28h+arg_0]
0x140006677  mov     rsi, [rsp+28h+arg_8]
0x14000667c  add     rsp, 20h
0x140006680  pop     rdi
0x140006681  retn
0x140006682  mov     rcx, rbx
0x140006685  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
