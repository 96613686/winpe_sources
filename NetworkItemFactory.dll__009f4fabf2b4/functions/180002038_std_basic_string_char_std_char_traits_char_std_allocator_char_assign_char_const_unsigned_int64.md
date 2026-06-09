# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x180002038`
- end: `0x18000212f`
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

- `0x180001916`
- `0x180001dbc`
- `0x180001f10`
- `0x180001f40`
- `0x180002038`

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
0x180002038  mov     [rsp+arg_0], rbx
0x18000203d  mov     [rsp+arg_8], rsi
0x180002042  push    rdi
0x180002043  sub     rsp, 20h
0x180002047  mov     rdi, r8
0x18000204a  mov     rsi, rdx
0x18000204d  mov     rbx, rcx
0x180002050  test    rdx, rdx
0x180002053  jz      short loc_1800020A1
0x180002055  cmp     qword ptr [rcx+18h], 10h
0x18000205a  jb      short loc_180002061
0x18000205c  mov     rax, [rcx]
0x18000205f  jmp     short loc_180002064
0x180002061  mov     rax, rbx
0x180002064  cmp     rsi, rax
0x180002067  jb      short loc_1800020A1
0x180002069  cmp     qword ptr [rcx+18h], 10h
0x18000206e  jb      short loc_180002073
0x180002070  mov     rcx, [rcx]
0x180002073  add     rcx, [rbx+10h]
0x180002077  cmp     rcx, rsi
0x18000207a  jbe     short loc_1800020A1
0x18000207c  cmp     qword ptr [rbx+18h], 10h
0x180002081  jb      short loc_180002088
0x180002083  mov     rax, [rbx]
0x180002086  jmp     short loc_18000208B
0x180002088  mov     rax, rbx
0x18000208b  sub     rsi, rax
0x18000208e  mov     r9, rdi
0x180002091  mov     r8, rsi
0x180002094  mov     rdx, rbx
0x180002097  mov     rcx, rbx; void *
0x18000209a  call    ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x18000209f  jmp     short loc_180002116
0x1800020a1  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x1800020a5  ja      short loc_180002126
0x1800020a7  cmp     [rbx+18h], rdi
0x1800020ab  jnb     short loc_1800020CD
0x1800020ad  mov     r8, [rbx+10h]
0x1800020b1  mov     rdx, rdi
0x1800020b4  mov     rcx, rbx; Src
0x1800020b7  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800020bc  test    rdi, rdi
0x1800020bf  jz      short loc_180002113
0x1800020c1  cmp     qword ptr [rbx+18h], 10h
0x1800020c6  jb      short loc_1800020EE
0x1800020c8  mov     rcx, [rbx]
0x1800020cb  jmp     short loc_1800020F1
0x1800020cd  test    rdi, rdi
0x1800020d0  jnz     short loc_1800020C1
0x1800020d2  cmp     qword ptr [rbx+18h], 10h
0x1800020d7  jb      short loc_1800020DE
0x1800020d9  mov     rax, [rbx]
0x1800020dc  jmp     short loc_1800020E1
0x1800020de  mov     rax, rbx
0x1800020e1  mov     qword ptr [rbx+10h], 0
0x1800020e9  mov     byte ptr [rax], 0
0x1800020ec  jmp     short loc_180002113
0x1800020ee  mov     rcx, rbx; void *
0x1800020f1  mov     r8, rdi; Size
0x1800020f4  mov     rdx, rsi; Src
0x1800020f7  call    memcpy_0
0x1800020fc  cmp     qword ptr [rbx+18h], 10h
0x180002101  jb      short loc_180002108
0x180002103  mov     rax, [rbx]
0x180002106  jmp     short loc_18000210B
0x180002108  mov     rax, rbx
0x18000210b  mov     [rbx+10h], rdi
0x18000210f  mov     byte ptr [rax+rdi], 0
0x180002113  mov     rax, rbx
0x180002116  mov     rbx, [rsp+28h+arg_0]
0x18000211b  mov     rsi, [rsp+28h+arg_8]
0x180002120  add     rsp, 20h
0x180002124  pop     rdi
0x180002125  retn
0x180002126  mov     rcx, rbx
0x180002129  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
