# wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)

- ea: `0x1800077ec`
- end: `0x1800078ef`
- name: `?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z`
- size: `259`
- prototype: `_QWORD(wil *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: `service_task, broker_com_uri`

## callers

- `0x180006c80`
- `0x180006e78`
- `0x1800165bc`

## callees

- `0x1800077ec`
- `0x180031f34`
- `0x180038682`
- `0x1800386f0`
- `0x180038708`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800078dc`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800078dc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007859`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007859`

## string_xrefs

- `0x1800078b8`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
wil *__fastcall wil::make_cotaskmem_string_nothrow(
        wil *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rsi
  __int64 v7; // rax
  const unsigned __int16 *v8; // rbx
  __int64 v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( !a2 && a3 == -1 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  if ( a2 )
  {
    v7 = a3;
    v8 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v7 = 0x7FFFFFFF;
    for ( ; v7; --v7 )
    {
      if ( !*v8 )
        break;
      ++v8;
    }
    v9 = v8 - a2;
  }
  else
  {
    v9 = a3;
  }
  if ( a3 == -1 )
    v4 = v9;
  v10 = CoTaskMemAlloc(2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v9;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno() = 34;
          invalid_parameter_noinfo();
        }
        else
        {
          memcpy_0(v10, a2, v12);
        }
      }
      v11[v12 / 2] = 0;
    }
    else
    {
      *v10 = 0;
    }
    v11[v4] = 0;
  }
  *(_QWORD *)this = v11;
  return this;
}

```

## disassembly

```asm
0x1800077ec  push    rbx
0x1800077ee  push    rbp
0x1800077ef  push    rsi
0x1800077f0  push    rdi
0x1800077f1  push    r12
0x1800077f3  push    r14
0x1800077f5  push    r15
0x1800077f7  sub     rsp, 20h
0x1800077fb  xor     r12d, r12d
0x1800077fe  mov     rsi, r8
0x180007801  mov     rbp, rdx
0x180007804  mov     r15, rcx
0x180007807  test    rdx, rdx
0x18000780a  jz      loc_1800078A9
0x180007810  test    rbp, rbp
0x180007813  jz      loc_1800078CA
0x180007819  mov     ecx, 7FFFFFFFh
0x18000781e  mov     rax, rsi
0x180007821  cmp     rsi, rcx
0x180007824  mov     rbx, rbp
0x180007827  cmovnb  rax, rcx
0x18000782b  test    rax, rax
0x18000782e  jz      short loc_180007840
0x180007830  cmp     [rbx], r12w
0x180007834  jz      short loc_180007840
0x180007836  add     rbx, 2
0x18000783a  sub     rax, 1
0x18000783e  jnz     short loc_180007830
0x180007840  sub     rbx, rbp
0x180007843  sar     rbx, 1
0x180007846  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x18000784a  cmovz   rsi, rbx
0x18000784e  lea     r14, ds:2[rsi*2]
0x180007856  mov     rcx, r14; cb
0x180007859  call    cs:__imp_CoTaskMemAlloc
0x18000785f  mov     rdi, rax
0x180007862  test    rax, rax
0x180007865  jz      short loc_180007894
0x180007867  test    rbp, rbp
0x18000786a  jz      short loc_18000788B
0x18000786c  add     rbx, rbx
0x18000786f  jz      short loc_180007884
0x180007871  mov     rcx, rax; void *
0x180007874  cmp     r14, rbx
0x180007877  jb      short loc_1800078D2
0x180007879  mov     r8, rbx; Size
0x18000787c  mov     rdx, rbp; Src
0x18000787f  call    memcpy_0
0x180007884  mov     [rbx+rdi], r12w
0x180007889  jmp     short loc_18000788F
0x18000788b  mov     [rax], r12w
0x18000788f  mov     [rdi+rsi*2], r12w
0x180007894  mov     [r15], rdi
0x180007897  mov     rax, r15
0x18000789a  add     rsp, 20h
0x18000789e  pop     r15
0x1800078a0  pop     r14
0x1800078a2  pop     r12
0x1800078a4  pop     rdi
0x1800078a5  pop     rsi
0x1800078a6  pop     rbp
0x1800078a7  pop     rbx
0x1800078a8  retn
0x1800078a9  cmp     rsi, 0FFFFFFFFFFFFFFFFh
0x1800078ad  jnz     loc_180007810
0x1800078b3  mov     rcx, [rsp+58h]; this
0x1800078b8  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800078bf  mov     edx, 0F89h; void *
0x1800078c4  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800078ca  mov     rbx, rsi
0x1800078cd  jmp     loc_180007846
0x1800078d2  mov     r8, r14; Size
0x1800078d5  xor     edx, edx; Val
0x1800078d7  call    memset_0
0x1800078dc  call    cs:__imp__o__errno
0x1800078e2  mov     dword ptr [rax], 22h ; '"'
0x1800078e8  call    _invalid_parameter_noinfo
0x1800078ed  jmp     short loc_180007884
```
