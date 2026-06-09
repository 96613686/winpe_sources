# std::vector<uchar,std::allocator<uchar>>::_Reallocate(unsigned __int64)

- ea: `0x182da88d0`
- end: `0x182da89e8`
- name: `?_Reallocate@?$vector@EV?$allocator@E@std@@@std@@IEAAX_K@Z`
- size: `280`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x182da8f80`
- `0x182dcbea0`
- `0x182dea0f0`
- `0x183034d30`

## callees

- `0x182da88d0`
- `0x1832c3a30`
- `0x1832c3a50`

## import_xrefs

- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x182da8912`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x182da8912`
- `VCRUNTIME140!memmove` at `0x182da8961`
- `VCRUNTIME140!memmove` at `0x182da8961`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da8923`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da8948`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da898b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da899b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da89ab`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da89b8`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da8923`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da8948`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da898b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da899b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da89ab`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da89b8`

## pseudocode

```c
char *__fastcall std::vector<unsigned char>::_Reallocate(__int64 a1, unsigned __int64 a2)
{
  _QWORD *v4; // rbx
  void *v5; // rax
  char *v6; // rcx
  __int64 v7; // r14
  char *v8; // rax
  unsigned __int64 v9; // rcx
  char *result; // rax
  struct CxVector *Pointer; // rax

  if ( a2 )
  {
    if ( a2 < 0x1000 )
    {
      v4 = operator new(a2);
      if ( !v4 )
        _invalid_parameter_noinfo_noreturn();
    }
    else
    {
      if ( a2 + 39 <= a2 )
      {
        std::_Xbad_alloc();
        __debugbreak();
      }
      v5 = operator new(a2 + 39);
      if ( !v5 )
        _invalid_parameter_noinfo_noreturn();
      v4 = (_QWORD *)(((unsigned __int64)v5 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
      *(v4 - 1) = v5;
    }
  }
  else
  {
    v4 = 0;
  }
  try
  {
    memmove(v4, *(const void **)a1, *(_QWORD *)(a1 + 8) - *(_QWORD *)a1);
  }
  catch ( ... )
  {
    Pointer = CxVector::GetPointer((CxVector *)a1);
    std::_Wrap_alloc<std::allocator<unsigned char>>::deallocate(Pointer, v4, a2);
    throw;
  }
  v6 = *(char **)a1;
  v7 = *(_QWORD *)(a1 + 8) - *(_QWORD *)a1;
  if ( *(_QWORD *)a1 )
  {
    if ( *(_QWORD *)(a1 + 16) - (_QWORD)v6 >= 0x1000u )
    {
      if ( ((unsigned __int8)v6 & 0x1F) != 0 )
        _invalid_parameter_noinfo_noreturn();
      v8 = (char *)*((_QWORD *)v6 - 1);
      if ( v8 >= v6 )
        _invalid_parameter_noinfo_noreturn();
      v9 = v6 - v8;
      if ( v9 < 8 )
        _invalid_parameter_noinfo_noreturn();
      if ( v9 > 0x27 )
        _invalid_parameter_noinfo_noreturn();
      v6 = v8;
    }
    operator delete(v6);
  }
  *(_QWORD *)(a1 + 16) = (char *)v4 + a2;
  result = (char *)v4 + v7;
  *(_QWORD *)(a1 + 8) = (char *)v4 + v7;
  *(_QWORD *)a1 = v4;
  return result;
}

```

## disassembly

```asm
0x182da88d0  push    rsi
0x182da88d2  push    rdi
0x182da88d3  push    r14
0x182da88d5  sub     rsp, 40h
0x182da88d9  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x182da88e2  mov     [rsp+58h+arg_10], rbx
0x182da88e7  mov     rdi, rdx
0x182da88ea  mov     rsi, rcx
0x182da88ed  mov     [rsp+58h+var_30], rcx
0x182da88f2  mov     [rsp+58h+var_28], rdx
0x182da88f7  test    rdx, rdx
0x182da88fa  jnz     short loc_182DA8900
0x182da88fc  xor     ebx, ebx
0x182da88fe  jmp     short loc_182DA894F
0x182da8900  cmp     rdi, 1000h
0x182da8907  jb      short loc_182DA8938
0x182da8909  lea     rcx, [rdx+27h]; unsigned __int64
0x182da890d  cmp     rcx, rdi
0x182da8910  ja      short loc_182DA8919
0x182da8912  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x182da8918  int     3; Trap to Debugger
0x182da8919  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x182da891e  test    rax, rax
0x182da8921  jnz     short loc_182DA892A
0x182da8923  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da892a  lea     rbx, [rax+27h]
0x182da892e  and     rbx, 0FFFFFFFFFFFFFFE0h
0x182da8932  mov     [rbx-8], rax
0x182da8936  jmp     short loc_182DA894F
0x182da8938  mov     rcx, rdi; unsigned __int64
0x182da893b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x182da8940  mov     rbx, rax
0x182da8943  test    rax, rax
0x182da8946  jnz     short loc_182DA894F
0x182da8948  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da894f  mov     [rsp+58h+var_38], rbx
0x182da8954  mov     r8, [rsi+8]
0x182da8958  mov     rdx, [rsi]; Src
0x182da895b  sub     r8, rdx; Size
0x182da895e  mov     rcx, rbx; void *
0x182da8961  call    cs:__imp_memmove
0x182da8967  nop
0x182da8968  mov     rcx, [rsi]
0x182da896b  mov     r14, [rsi+8]
0x182da896f  sub     r14, rcx
0x182da8972  test    rcx, rcx
0x182da8975  jz      short loc_182DA89C7
0x182da8977  mov     rax, [rsi+10h]
0x182da897b  sub     rax, rcx
0x182da897e  cmp     rax, 1000h
0x182da8984  jb      short loc_182DA89C2
0x182da8986  test    cl, 1Fh
0x182da8989  jz      short loc_182DA8992
0x182da898b  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da8992  mov     rax, [rcx-8]
0x182da8996  cmp     rax, rcx
0x182da8999  jb      short loc_182DA89A2
0x182da899b  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da89a2  sub     rcx, rax
0x182da89a5  cmp     rcx, 8
0x182da89a9  jnb     short loc_182DA89B2
0x182da89ab  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da89b2  cmp     rcx, 27h ; '''
0x182da89b6  jbe     short loc_182DA89BF
0x182da89b8  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da89bf  mov     rcx, rax; void *
0x182da89c2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x182da89c7  lea     rax, [rdi+rbx]
0x182da89cb  mov     [rsi+10h], rax
0x182da89cf  lea     rax, [rbx+r14]
0x182da89d3  mov     [rsi+8], rax
0x182da89d7  mov     [rsi], rbx
0x182da89da  mov     rbx, [rsp+58h+arg_10]
0x182da89df  add     rsp, 40h
0x182da89e3  pop     r14
0x182da89e5  pop     rdi
0x182da89e6  pop     rsi
0x182da89e7  retn
```
