# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180002a74`
- end: `0x180002b6b`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `247`
- prototype: `size_t *__fastcall(size_t *, char *Src, size_t Size)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002e60`
- `0x180002ed0`
- `0x180002f60`

## callees

- `0x180001d06`
- `0x180002454`
- `0x18000272c`
- `0x18000297c`
- `0x180002a74`

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
0x180002a74  mov     [rsp+arg_0], rbx
0x180002a79  mov     [rsp+arg_8], rsi
0x180002a7e  push    rdi
0x180002a7f  sub     rsp, 20h
0x180002a83  mov     rdi, r8
0x180002a86  mov     rsi, rdx
0x180002a89  mov     rbx, rcx
0x180002a8c  test    rdx, rdx
0x180002a8f  jz      short loc_180002ADD
0x180002a91  cmp     qword ptr [rcx+18h], 10h
0x180002a96  jb      short loc_180002A9D
0x180002a98  mov     rax, [rcx]
0x180002a9b  jmp     short loc_180002AA0
0x180002a9d  mov     rax, rbx
0x180002aa0  cmp     rsi, rax
0x180002aa3  jb      short loc_180002ADD
0x180002aa5  cmp     qword ptr [rcx+18h], 10h
0x180002aaa  jb      short loc_180002AAF
0x180002aac  mov     rcx, [rcx]
0x180002aaf  add     rcx, [rbx+10h]
0x180002ab3  cmp     rcx, rsi
0x180002ab6  jbe     short loc_180002ADD
0x180002ab8  cmp     qword ptr [rbx+18h], 10h
0x180002abd  jb      short loc_180002AC4
0x180002abf  mov     rax, [rbx]
0x180002ac2  jmp     short loc_180002AC7
0x180002ac4  mov     rax, rbx
0x180002ac7  sub     rsi, rax
0x180002aca  mov     r9, rdi
0x180002acd  mov     r8, rsi
0x180002ad0  mov     rdx, rbx
0x180002ad3  mov     rcx, rbx; void *
0x180002ad6  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180002adb  jmp     short loc_180002B52
0x180002add  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180002ae1  ja      short loc_180002B62
0x180002ae3  cmp     [rbx+18h], rdi
0x180002ae7  jnb     short loc_180002B09
0x180002ae9  mov     r8, [rbx+10h]
0x180002aed  mov     rdx, rdi
0x180002af0  mov     rcx, rbx; Src
0x180002af3  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180002af8  test    rdi, rdi
0x180002afb  jz      short loc_180002B4F
0x180002afd  cmp     qword ptr [rbx+18h], 10h
0x180002b02  jb      short loc_180002B2A
0x180002b04  mov     rcx, [rbx]
0x180002b07  jmp     short loc_180002B2D
0x180002b09  test    rdi, rdi
0x180002b0c  jnz     short loc_180002AFD
0x180002b0e  cmp     qword ptr [rbx+18h], 10h
0x180002b13  jb      short loc_180002B1A
0x180002b15  mov     rax, [rbx]
0x180002b18  jmp     short loc_180002B1D
0x180002b1a  mov     rax, rbx
0x180002b1d  mov     qword ptr [rbx+10h], 0
0x180002b25  mov     byte ptr [rax], 0
0x180002b28  jmp     short loc_180002B4F
0x180002b2a  mov     rcx, rbx; void *
0x180002b2d  mov     r8, rdi; Size
0x180002b30  mov     rdx, rsi; Src
0x180002b33  call    memcpy_0
0x180002b38  cmp     qword ptr [rbx+18h], 10h
0x180002b3d  jb      short loc_180002B44
0x180002b3f  mov     rax, [rbx]
0x180002b42  jmp     short loc_180002B47
0x180002b44  mov     rax, rbx
0x180002b47  mov     [rbx+10h], rdi
0x180002b4b  mov     byte ptr [rax+rdi], 0
0x180002b4f  mov     rax, rbx
0x180002b52  mov     rbx, [rsp+28h+arg_0]
0x180002b57  mov     rsi, [rsp+28h+arg_8]
0x180002b5c  add     rsp, 20h
0x180002b60  pop     rdi
0x180002b61  retn
0x180002b62  mov     rcx, rbx
0x180002b65  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
