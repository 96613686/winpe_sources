# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180002030`
- end: `0x180002127`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800022b0`
- `0x180002320`
- `0x1800023b0`

## callees

- `0x180001d28`
- `0x180001eb0`
- `0x180001f38`
- `0x180002030`
- `0x180002576`

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
0x180002030  mov     [rsp+arg_0], rbx
0x180002035  mov     [rsp+arg_8], rsi
0x18000203a  push    rdi
0x18000203b  sub     rsp, 20h
0x18000203f  mov     rdi, r8
0x180002042  mov     rsi, rdx
0x180002045  mov     rbx, rcx
0x180002048  test    rdx, rdx
0x18000204b  jz      short loc_180002099
0x18000204d  cmp     qword ptr [rcx+18h], 10h
0x180002052  jb      short loc_180002059
0x180002054  mov     rax, [rcx]
0x180002057  jmp     short loc_18000205C
0x180002059  mov     rax, rbx
0x18000205c  cmp     rsi, rax
0x18000205f  jb      short loc_180002099
0x180002061  cmp     qword ptr [rcx+18h], 10h
0x180002066  jb      short loc_18000206B
0x180002068  mov     rcx, [rcx]
0x18000206b  add     rcx, [rbx+10h]
0x18000206f  cmp     rcx, rsi
0x180002072  jbe     short loc_180002099
0x180002074  cmp     qword ptr [rbx+18h], 10h
0x180002079  jb      short loc_180002080
0x18000207b  mov     rax, [rbx]
0x18000207e  jmp     short loc_180002083
0x180002080  mov     rax, rbx
0x180002083  sub     rsi, rax
0x180002086  mov     r9, rdi
0x180002089  mov     r8, rsi
0x18000208c  mov     rdx, rbx
0x18000208f  mov     rcx, rbx; void *
0x180002092  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180002097  jmp     short loc_18000210E
0x180002099  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000209d  ja      short loc_18000211E
0x18000209f  cmp     [rbx+18h], rdi
0x1800020a3  jnb     short loc_1800020C5
0x1800020a5  mov     r8, [rbx+10h]
0x1800020a9  mov     rdx, rdi
0x1800020ac  mov     rcx, rbx; Src
0x1800020af  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800020b4  test    rdi, rdi
0x1800020b7  jz      short loc_18000210B
0x1800020b9  cmp     qword ptr [rbx+18h], 10h
0x1800020be  jb      short loc_1800020E6
0x1800020c0  mov     rcx, [rbx]
0x1800020c3  jmp     short loc_1800020E9
0x1800020c5  test    rdi, rdi
0x1800020c8  jnz     short loc_1800020B9
0x1800020ca  cmp     qword ptr [rbx+18h], 10h
0x1800020cf  jb      short loc_1800020D6
0x1800020d1  mov     rax, [rbx]
0x1800020d4  jmp     short loc_1800020D9
0x1800020d6  mov     rax, rbx
0x1800020d9  mov     qword ptr [rbx+10h], 0
0x1800020e1  mov     byte ptr [rax], 0
0x1800020e4  jmp     short loc_18000210B
0x1800020e6  mov     rcx, rbx; void *
0x1800020e9  mov     r8, rdi; Size
0x1800020ec  mov     rdx, rsi; Src
0x1800020ef  call    memcpy_0
0x1800020f4  cmp     qword ptr [rbx+18h], 10h
0x1800020f9  jb      short loc_180002100
0x1800020fb  mov     rax, [rbx]
0x1800020fe  jmp     short loc_180002103
0x180002100  mov     rax, rbx
0x180002103  mov     [rbx+10h], rdi
0x180002107  mov     byte ptr [rax+rdi], 0
0x18000210b  mov     rax, rbx
0x18000210e  mov     rbx, [rsp+28h+arg_0]
0x180002113  mov     rsi, [rsp+28h+arg_8]
0x180002118  add     rsp, 20h
0x18000211c  pop     rdi
0x18000211d  retn
0x18000211e  mov     rcx, rbx
0x180002121  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
