# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x18000bd08`
- end: `0x18000bdff`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c150`
- `0x18000c1c0`
- `0x18000c250`

## callees

- `0x180001de6`
- `0x18000b634`
- `0x18000ba60`
- `0x18000bc10`
- `0x18000bd08`

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
    std::wstring::_Xlen(v5);
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
0x18000bd08  mov     [rsp+arg_0], rbx
0x18000bd0d  mov     [rsp+arg_8], rsi
0x18000bd12  push    rdi
0x18000bd13  sub     rsp, 20h
0x18000bd17  mov     rdi, r8
0x18000bd1a  mov     rsi, rdx
0x18000bd1d  mov     rbx, rcx
0x18000bd20  test    rdx, rdx
0x18000bd23  jz      short loc_18000BD71
0x18000bd25  cmp     qword ptr [rcx+18h], 10h
0x18000bd2a  jb      short loc_18000BD31
0x18000bd2c  mov     rax, [rcx]
0x18000bd2f  jmp     short loc_18000BD34
0x18000bd31  mov     rax, rbx
0x18000bd34  cmp     rsi, rax
0x18000bd37  jb      short loc_18000BD71
0x18000bd39  cmp     qword ptr [rcx+18h], 10h
0x18000bd3e  jb      short loc_18000BD43
0x18000bd40  mov     rcx, [rcx]
0x18000bd43  add     rcx, [rbx+10h]
0x18000bd47  cmp     rcx, rsi
0x18000bd4a  jbe     short loc_18000BD71
0x18000bd4c  cmp     qword ptr [rbx+18h], 10h
0x18000bd51  jb      short loc_18000BD58
0x18000bd53  mov     rax, [rbx]
0x18000bd56  jmp     short loc_18000BD5B
0x18000bd58  mov     rax, rbx
0x18000bd5b  sub     rsi, rax
0x18000bd5e  mov     r9, rdi
0x18000bd61  mov     r8, rsi
0x18000bd64  mov     rdx, rbx
0x18000bd67  mov     rcx, rbx; void *
0x18000bd6a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18000bd6f  jmp     short loc_18000BDE6
0x18000bd71  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000bd75  ja      short loc_18000BDF6
0x18000bd77  cmp     [rbx+18h], rdi
0x18000bd7b  jnb     short loc_18000BD9D
0x18000bd7d  mov     r8, [rbx+10h]
0x18000bd81  mov     rdx, rdi
0x18000bd84  mov     rcx, rbx; Src
0x18000bd87  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18000bd8c  test    rdi, rdi
0x18000bd8f  jz      short loc_18000BDE3
0x18000bd91  cmp     qword ptr [rbx+18h], 10h
0x18000bd96  jb      short loc_18000BDBE
0x18000bd98  mov     rcx, [rbx]
0x18000bd9b  jmp     short loc_18000BDC1
0x18000bd9d  test    rdi, rdi
0x18000bda0  jnz     short loc_18000BD91
0x18000bda2  cmp     qword ptr [rbx+18h], 10h
0x18000bda7  jb      short loc_18000BDAE
0x18000bda9  mov     rax, [rbx]
0x18000bdac  jmp     short loc_18000BDB1
0x18000bdae  mov     rax, rbx
0x18000bdb1  mov     qword ptr [rbx+10h], 0
0x18000bdb9  mov     byte ptr [rax], 0
0x18000bdbc  jmp     short loc_18000BDE3
0x18000bdbe  mov     rcx, rbx; void *
0x18000bdc1  mov     r8, rdi; Size
0x18000bdc4  mov     rdx, rsi; Src
0x18000bdc7  call    memcpy_0
0x18000bdcc  cmp     qword ptr [rbx+18h], 10h
0x18000bdd1  jb      short loc_18000BDD8
0x18000bdd3  mov     rax, [rbx]
0x18000bdd6  jmp     short loc_18000BDDB
0x18000bdd8  mov     rax, rbx
0x18000bddb  mov     [rbx+10h], rdi
0x18000bddf  mov     byte ptr [rax+rdi], 0
0x18000bde3  mov     rax, rbx
0x18000bde6  mov     rbx, [rsp+28h+arg_0]
0x18000bdeb  mov     rsi, [rsp+28h+arg_8]
0x18000bdf0  add     rsp, 20h
0x18000bdf4  pop     rdi
0x18000bdf5  retn
0x18000bdf6  mov     rcx, rbx
0x18000bdf9  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
