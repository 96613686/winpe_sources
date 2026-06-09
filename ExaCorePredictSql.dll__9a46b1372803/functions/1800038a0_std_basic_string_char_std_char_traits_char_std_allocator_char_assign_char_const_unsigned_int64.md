# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(char const *,unsigned __int64)

- ea: `0x1800038a0`
- end: `0x1800039c9`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@PEBD_K@Z`
- size: `297`
- prototype: `__int64 __fastcall(void *, void *Src, size_t Size)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180003310`

## callees

- `0x1800017a0`
- `0x180003470`
- `0x180003640`
- `0x1800038a0`
- `0x180004acc`

## pseudocode

```c
unsigned __int64 *__fastcall std::string::assign(unsigned __int64 *a1, unsigned __int64 Src, size_t Size)
{
  unsigned __int64 *v4; // rsi
  unsigned __int64 *v5; // rbx
  char *v6; // rax
  unsigned __int64 v7; // rax
  unsigned __int64 *result; // rax
  void *v9; // rcx
  bool v10; // cf
  unsigned __int64 v11; // rax

  v4 = (unsigned __int64 *)Src;
  v5 = a1;
  if ( !Src )
    goto LABEL_13;
  Src = a1[3];
  v6 = Src < 0x10 ? (char *)a1 : (char *)*a1;
  if ( v4 < (unsigned __int64 *)v6 )
    goto LABEL_13;
  if ( Src >= 0x10 )
    a1 = (unsigned __int64 *)*a1;
  a1 = (unsigned __int64 *)((char *)a1 + v5[2]);
  if ( a1 <= v4 )
  {
LABEL_13:
    if ( Size == -1 )
      std::string::_Xlen(a1, Src);
    if ( v5[3] >= Size )
    {
      if ( !Size )
      {
        v10 = v5[3] < 0x10;
        v5[2] = 0;
        if ( v10 )
        {
          result = v5;
          *(_BYTE *)v5 = 0;
        }
        else
        {
          *(_BYTE *)*v5 = 0;
          return v5;
        }
        return result;
      }
    }
    else
    {
      std::string::_Copy(v5, Size, v5[2]);
      if ( !Size )
        return v5;
    }
    if ( v5[3] < 0x10 )
      v9 = v5;
    else
      v9 = (void *)*v5;
    if ( Size )
      memcpy_0(v9, v4, Size);
    v10 = v5[3] < 0x10;
    v5[2] = Size;
    if ( v10 )
      v11 = (unsigned __int64)v5;
    else
      v11 = *v5;
    *(_BYTE *)(v11 + Size) = 0;
    return v5;
  }
  if ( Src < 0x10 )
    v7 = (unsigned __int64)v5;
  else
    v7 = *v5;
  return std::string::assign(v5, v5, (unsigned __int64)v4 - v7, Size);
}

```

## disassembly

```asm
0x1800038a0  mov     [rsp+arg_0], rbx
0x1800038a5  mov     [rsp+arg_8], rsi
0x1800038aa  push    rdi
0x1800038ab  sub     rsp, 20h
0x1800038af  mov     rdi, r8
0x1800038b2  mov     rsi, rdx
0x1800038b5  mov     rbx, rcx
0x1800038b8  test    rdx, rdx
0x1800038bb  jz      short loc_180003917
0x1800038bd  mov     rdx, [rcx+18h]
0x1800038c1  cmp     rdx, 10h
0x1800038c5  jb      short loc_1800038CC
0x1800038c7  mov     rax, [rcx]
0x1800038ca  jmp     short loc_1800038CF
0x1800038cc  mov     rax, rbx
0x1800038cf  cmp     rsi, rax
0x1800038d2  jb      short loc_180003917
0x1800038d4  cmp     rdx, 10h
0x1800038d8  jb      short loc_1800038DD
0x1800038da  mov     rcx, [rcx]
0x1800038dd  add     rcx, [rbx+10h]
0x1800038e1  cmp     rcx, rsi
0x1800038e4  jbe     short loc_180003917
0x1800038e6  cmp     rdx, 10h
0x1800038ea  jb      short loc_1800038F1
0x1800038ec  mov     rax, [rbx]
0x1800038ef  jmp     short loc_1800038F4
0x1800038f1  mov     rax, rbx
0x1800038f4  sub     rsi, rax
0x1800038f7  mov     r9, rdi
0x1800038fa  mov     r8, rsi
0x1800038fd  mov     rdx, rbx
0x180003900  mov     rcx, rbx; void *
0x180003903  mov     rbx, [rsp+28h+arg_0]
0x180003908  mov     rsi, [rsp+28h+arg_8]
0x18000390d  add     rsp, 20h
0x180003911  pop     rdi
0x180003912  jmp     ?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::string::assign(std::string const &,unsigned __int64,unsigned __int64)
0x180003917  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x18000391b  ja      loc_1800039C3
0x180003921  cmp     [rbx+18h], rdi
0x180003925  jnb     short loc_180003947
0x180003927  mov     r8, [rbx+10h]
0x18000392b  mov     rdx, rdi
0x18000392e  mov     rcx, rbx; Src
0x180003931  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x180003936  test    rdi, rdi
0x180003939  jz      short loc_1800039B0
0x18000393b  cmp     qword ptr [rbx+18h], 10h
0x180003940  jb      short loc_180003986
0x180003942  mov     rcx, [rbx]
0x180003945  jmp     short loc_180003989
0x180003947  test    rdi, rdi
0x18000394a  jnz     short loc_18000393B
0x18000394c  cmp     qword ptr [rbx+18h], 10h
0x180003951  mov     [rbx+10h], rdi
0x180003955  jb      short loc_180003970
0x180003957  mov     rax, [rbx]
0x18000395a  mov     [rax], dil
0x18000395d  mov     rax, rbx
0x180003960  mov     rbx, [rsp+28h+arg_0]
0x180003965  mov     rsi, [rsp+28h+arg_8]
0x18000396a  add     rsp, 20h
0x18000396e  pop     rdi
0x18000396f  retn
0x180003970  mov     rax, rbx
0x180003973  mov     byte ptr [rbx], 0
0x180003976  mov     rbx, [rsp+28h+arg_0]
0x18000397b  mov     rsi, [rsp+28h+arg_8]
0x180003980  add     rsp, 20h
0x180003984  pop     rdi
0x180003985  retn
0x180003986  mov     rcx, rbx; void *
0x180003989  test    rdi, rdi
0x18000398c  jz      short loc_180003999
0x18000398e  mov     r8, rdi; Size
0x180003991  mov     rdx, rsi; Src
0x180003994  call    memcpy_0
0x180003999  cmp     qword ptr [rbx+18h], 10h
0x18000399e  mov     [rbx+10h], rdi
0x1800039a2  jb      short loc_1800039A9
0x1800039a4  mov     rax, [rbx]
0x1800039a7  jmp     short loc_1800039AC
0x1800039a9  mov     rax, rbx
0x1800039ac  mov     byte ptr [rax+rdi], 0
0x1800039b0  mov     rsi, [rsp+28h+arg_8]
0x1800039b5  mov     rax, rbx
0x1800039b8  mov     rbx, [rsp+28h+arg_0]
0x1800039bd  add     rsp, 20h
0x1800039c1  pop     rdi
0x1800039c2  retn
0x1800039c3  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
