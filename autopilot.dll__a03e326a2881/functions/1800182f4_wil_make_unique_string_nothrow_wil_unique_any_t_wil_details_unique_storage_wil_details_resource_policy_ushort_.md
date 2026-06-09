# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800182f4`
- end: `0x1800183e9`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `245`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18001891c`
- `0x18001b290`
- `0x1800270e0`

## callees

- `0x180005306`
- `0x180005374`
- `0x18000994b`
- `0x180012130`
- `0x1800182f4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001839c`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001839c`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018365`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180018365`

## string_xrefs

- `0x1800183d7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rdi
  __int64 v7; // rbx
  __int64 v8; // rax
  char *v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rbx
  __int64 v13; // rdx
  __int64 v14; // rcx
  __int64 v15; // r8
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v8 = a3;
    v9 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v8 = 0x7FFFFFFF;
    for ( ; v8; --v8 )
    {
      if ( !*(_WORD *)v9 )
        break;
      v9 += 2;
    }
    v7 = (v9 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v7;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v7 = a3;
  }
  v10 = LocalAlloc(0, 2 * v4 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( a2 )
    {
      v12 = 2 * v7;
      if ( v12 )
      {
        if ( 2 * v4 + 2 < v12 )
        {
          memset_0(v10, 0, 2 * v4 + 2);
          *(_DWORD *)_o__errno(v14, v13, v15) = 34;
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
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x1800182f4  push    rbx
0x1800182f6  push    rbp
0x1800182f7  push    rsi
0x1800182f8  push    rdi
0x1800182f9  push    r12
0x1800182fb  push    r14
0x1800182fd  push    r15
0x1800182ff  sub     rsp, 20h
0x180018303  xor     r12d, r12d
0x180018306  mov     rdi, r8
0x180018309  mov     rbp, rdx
0x18001830c  mov     r15, rcx
0x18001830f  test    rdx, rdx
0x180018312  jnz     short loc_180018323
0x180018314  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180018318  jz      loc_1800183D2
0x18001831e  mov     rbx, r8
0x180018321  jmp     short loc_180018358
0x180018323  mov     ecx, 7FFFFFFFh
0x180018328  mov     rax, rdi
0x18001832b  cmp     rdi, rcx
0x18001832e  mov     rbx, rbp
0x180018331  cmovnb  rax, rcx
0x180018335  test    rax, rax
0x180018338  jz      short loc_18001834A
0x18001833a  cmp     [rbx], r12w
0x18001833e  jz      short loc_18001834A
0x180018340  add     rbx, 2
0x180018344  sub     rax, 1
0x180018348  jnz     short loc_18001833A
0x18001834a  sub     rbx, rbp
0x18001834d  sar     rbx, 1
0x180018350  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180018354  cmovz   rdi, rbx
0x180018358  lea     r14, ds:2[rdi*2]
0x180018360  xor     ecx, ecx; uFlags
0x180018362  mov     rdx, r14; uBytes
0x180018365  call    cs:__imp_LocalAlloc
0x18001836b  mov     rsi, rax
0x18001836e  test    rax, rax
0x180018371  jz      short loc_1800183BD
0x180018373  test    rbp, rbp
0x180018376  jz      short loc_1800183B4
0x180018378  add     rbx, rbx
0x18001837b  jz      short loc_1800183AD
0x18001837d  mov     rcx, rax; void *
0x180018380  cmp     r14, rbx
0x180018383  jb      short loc_180018392
0x180018385  mov     r8, rbx; Size
0x180018388  mov     rdx, rbp; Src
0x18001838b  call    memcpy_0
0x180018390  jmp     short loc_1800183AD
0x180018392  mov     r8, r14; Size
0x180018395  xor     edx, edx; Val
0x180018397  call    memset_0
0x18001839c  call    cs:__imp__o__errno
0x1800183a2  mov     dword ptr [rax], 22h ; '"'
0x1800183a8  call    _invalid_parameter_noinfo
0x1800183ad  mov     [rbx+rsi], r12w
0x1800183b2  jmp     short loc_1800183B8
0x1800183b4  mov     [rax], r12w
0x1800183b8  mov     [rsi+rdi*2], r12w
0x1800183bd  mov     [r15], rsi
0x1800183c0  mov     rax, r15
0x1800183c3  add     rsp, 20h
0x1800183c7  pop     r15
0x1800183c9  pop     r14
0x1800183cb  pop     r12
0x1800183cd  pop     rdi
0x1800183ce  pop     rsi
0x1800183cf  pop     rbp
0x1800183d0  pop     rbx
0x1800183d1  retn
0x1800183d2  mov     rcx, [rsp+58h]; this
0x1800183d7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800183de  mov     edx, 0F89h; void *
0x1800183e3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
