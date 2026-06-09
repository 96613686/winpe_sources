# std::vector<char,std::allocator<char>>::_Reallocate(unsigned __int64)

- ea: `0x182da87b0`
- end: `0x182da88c8`
- name: `?_Reallocate@?$vector@DV?$allocator@D@std@@@std@@IEAAX_K@Z`
- size: `280`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x182da8f00`
- `0x182fd7b40`
- `0x182fd7df0`
- `0x1830bc0f0`

## callees

- `0x182da87b0`
- `0x1832c3a30`
- `0x1832c3a50`

## import_xrefs

- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x182da87f2`
- `MSVCP140!?_Xbad_alloc@std@@YAXXZ` at `0x182da87f2`
- `VCRUNTIME140!memmove` at `0x182da8841`
- `VCRUNTIME140!memmove` at `0x182da8841`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da8803`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da8828`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da886b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da887b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da888b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da8898`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da8803`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da8828`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da886b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da887b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da888b`
- `api-ms-win-crt-runtime-l1-1-0!_invalid_parameter_noinfo_noreturn` at `0x182da8898`

## pseudocode

```c
char *__fastcall std::vector<char>::_Reallocate(__int64 a1, unsigned __int64 a2)
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
0x182da87b0  push    rsi
0x182da87b2  push    rdi
0x182da87b3  push    r14
0x182da87b5  sub     rsp, 40h
0x182da87b9  mov     [rsp+58h+var_20], 0FFFFFFFFFFFFFFFEh
0x182da87c2  mov     [rsp+58h+arg_10], rbx
0x182da87c7  mov     rdi, rdx
0x182da87ca  mov     rsi, rcx
0x182da87cd  mov     [rsp+58h+var_30], rcx
0x182da87d2  mov     [rsp+58h+var_28], rdx
0x182da87d7  test    rdx, rdx
0x182da87da  jnz     short loc_182DA87E0
0x182da87dc  xor     ebx, ebx
0x182da87de  jmp     short loc_182DA882F
0x182da87e0  cmp     rdi, 1000h
0x182da87e7  jb      short loc_182DA8818
0x182da87e9  lea     rcx, [rdx+27h]; unsigned __int64
0x182da87ed  cmp     rcx, rdi
0x182da87f0  ja      short loc_182DA87F9
0x182da87f2  call    cs:__imp_?_Xbad_alloc@std@@YAXXZ; std::_Xbad_alloc(void)
0x182da87f8  int     3; Trap to Debugger
0x182da87f9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x182da87fe  test    rax, rax
0x182da8801  jnz     short loc_182DA880A
0x182da8803  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da880a  lea     rbx, [rax+27h]
0x182da880e  and     rbx, 0FFFFFFFFFFFFFFE0h
0x182da8812  mov     [rbx-8], rax
0x182da8816  jmp     short loc_182DA882F
0x182da8818  mov     rcx, rdi; unsigned __int64
0x182da881b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x182da8820  mov     rbx, rax
0x182da8823  test    rax, rax
0x182da8826  jnz     short loc_182DA882F
0x182da8828  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da882f  mov     [rsp+58h+var_38], rbx
0x182da8834  mov     r8, [rsi+8]
0x182da8838  mov     rdx, [rsi]; Src
0x182da883b  sub     r8, rdx; Size
0x182da883e  mov     rcx, rbx; void *
0x182da8841  call    cs:__imp_memmove
0x182da8847  nop
0x182da8848  mov     rcx, [rsi]
0x182da884b  mov     r14, [rsi+8]
0x182da884f  sub     r14, rcx
0x182da8852  test    rcx, rcx
0x182da8855  jz      short loc_182DA88A7
0x182da8857  mov     rax, [rsi+10h]
0x182da885b  sub     rax, rcx
0x182da885e  cmp     rax, 1000h
0x182da8864  jb      short loc_182DA88A2
0x182da8866  test    cl, 1Fh
0x182da8869  jz      short loc_182DA8872
0x182da886b  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da8872  mov     rax, [rcx-8]
0x182da8876  cmp     rax, rcx
0x182da8879  jb      short loc_182DA8882
0x182da887b  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da8882  sub     rcx, rax
0x182da8885  cmp     rcx, 8
0x182da8889  jnb     short loc_182DA8892
0x182da888b  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da8892  cmp     rcx, 27h ; '''
0x182da8896  jbe     short loc_182DA889F
0x182da8898  call    cs:__imp__invalid_parameter_noinfo_noreturn
0x182da889f  mov     rcx, rax; void *
0x182da88a2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x182da88a7  lea     rax, [rdi+rbx]
0x182da88ab  mov     [rsi+10h], rax
0x182da88af  lea     rax, [rbx+r14]
0x182da88b3  mov     [rsi+8], rax
0x182da88b7  mov     [rsi], rbx
0x182da88ba  mov     rbx, [rsp+58h+arg_10]
0x182da88bf  add     rsp, 40h
0x182da88c3  pop     r14
0x182da88c5  pop     rdi
0x182da88c6  pop     rsi
0x182da88c7  retn
```
