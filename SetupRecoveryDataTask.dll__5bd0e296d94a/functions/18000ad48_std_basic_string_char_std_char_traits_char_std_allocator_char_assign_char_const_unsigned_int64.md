# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x18000ad48`
- end: `0x18000ae3f`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b180`
- `0x18000b1f0`
- `0x18000b280`

## callees

- `0x180001d06`
- `0x18000aa14`
- `0x18000abc0`
- `0x18000ac50`
- `0x18000ad48`

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
    std::string::_Xlen(v5);
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
0x18000ad48  mov     [rsp+arg_0], rbx
0x18000ad4d  mov     [rsp+arg_8], rsi
0x18000ad52  push    rdi
0x18000ad53  sub     rsp, 20h
0x18000ad57  mov     rdi, r8
0x18000ad5a  mov     rsi, rdx
0x18000ad5d  mov     rbx, rcx
0x18000ad60  test    rdx, rdx
0x18000ad63  jz      short loc_18000ADB1
0x18000ad65  cmp     qword ptr [rcx+18h], 10h
0x18000ad6a  jb      short loc_18000AD71
0x18000ad6c  mov     rax, [rcx]
0x18000ad6f  jmp     short loc_18000AD74
0x18000ad71  mov     rax, rbx
0x18000ad74  cmp     rsi, rax
0x18000ad77  jb      short loc_18000ADB1
0x18000ad79  cmp     qword ptr [rcx+18h], 10h
0x18000ad7e  jb      short loc_18000AD83
0x18000ad80  mov     rcx, [rcx]
0x18000ad83  add     rcx, [rbx+10h]
0x18000ad87  cmp     rcx, rsi
0x18000ad8a  jbe     short loc_18000ADB1
0x18000ad8c  cmp     qword ptr [rbx+18h], 10h
0x18000ad91  jb      short loc_18000AD98
0x18000ad93  mov     rax, [rbx]
0x18000ad96  jmp     short loc_18000AD9B
0x18000ad98  mov     rax, rbx
0x18000ad9b  sub     rsi, rax
0x18000ad9e  mov     r9, rdi
0x18000ada1  mov     r8, rsi
0x18000ada4  mov     rdx, rbx
0x18000ada7  mov     rcx, rbx; void *
0x18000adaa  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18000adaf  jmp     short loc_18000AE26
0x18000adb1  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000adb5  ja      short loc_18000AE36
0x18000adb7  cmp     [rbx+18h], rdi
0x18000adbb  jnb     short loc_18000ADDD
0x18000adbd  mov     r8, [rbx+10h]
0x18000adc1  mov     rdx, rdi
0x18000adc4  mov     rcx, rbx; Src
0x18000adc7  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18000adcc  test    rdi, rdi
0x18000adcf  jz      short loc_18000AE23
0x18000add1  cmp     qword ptr [rbx+18h], 10h
0x18000add6  jb      short loc_18000ADFE
0x18000add8  mov     rcx, [rbx]
0x18000addb  jmp     short loc_18000AE01
0x18000addd  test    rdi, rdi
0x18000ade0  jnz     short loc_18000ADD1
0x18000ade2  cmp     qword ptr [rbx+18h], 10h
0x18000ade7  jb      short loc_18000ADEE
0x18000ade9  mov     rax, [rbx]
0x18000adec  jmp     short loc_18000ADF1
0x18000adee  mov     rax, rbx
0x18000adf1  mov     qword ptr [rbx+10h], 0
0x18000adf9  mov     byte ptr [rax], 0
0x18000adfc  jmp     short loc_18000AE23
0x18000adfe  mov     rcx, rbx; void *
0x18000ae01  mov     r8, rdi; Size
0x18000ae04  mov     rdx, rsi; Src
0x18000ae07  call    memcpy_0
0x18000ae0c  cmp     qword ptr [rbx+18h], 10h
0x18000ae11  jb      short loc_18000AE18
0x18000ae13  mov     rax, [rbx]
0x18000ae16  jmp     short loc_18000AE1B
0x18000ae18  mov     rax, rbx
0x18000ae1b  mov     [rbx+10h], rdi
0x18000ae1f  mov     byte ptr [rax+rdi], 0
0x18000ae23  mov     rax, rbx
0x18000ae26  mov     rbx, [rsp+28h+arg_0]
0x18000ae2b  mov     rsi, [rsp+28h+arg_8]
0x18000ae30  add     rsp, 20h
0x18000ae34  pop     rdi
0x18000ae35  retn
0x18000ae36  mov     rcx, rbx
0x18000ae39  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
