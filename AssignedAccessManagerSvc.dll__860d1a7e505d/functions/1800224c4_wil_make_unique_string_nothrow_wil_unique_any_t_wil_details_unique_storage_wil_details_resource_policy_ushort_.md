# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800224c4`
- end: `0x1800225b3`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `239`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180024544`
- `0x180025e1c`
- `0x180034000`

## callees

- `0x180007056`
- `0x1800070f4`
- `0x180008d95`
- `0x18001ff70`
- `0x1800224c4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002257d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002257d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022546`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180022546`

## string_xrefs

- `0x1800224ef`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rbx
  __int64 v7; // rdi
  __int64 v8; // rax
  char *v9; // rdi
  _WORD *v10; // rax
  _WORD *v11; // rsi
  size_t v12; // rdi
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
  v10 = CoTaskMemAlloc(2 * v4 + 2);
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
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x1800224c4  push    rbx
0x1800224c6  push    rbp
0x1800224c7  push    rsi
0x1800224c8  push    rdi
0x1800224c9  push    r12
0x1800224cb  push    r14
0x1800224cd  push    r15
0x1800224cf  sub     rsp, 20h
0x1800224d3  xor     r12d, r12d
0x1800224d6  mov     rbx, r8
0x1800224d9  mov     rbp, rdx
0x1800224dc  mov     r15, rcx
0x1800224df  test    rdx, rdx
0x1800224e2  jnz     short loc_180022506
0x1800224e4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800224e8  jnz     short loc_180022501
0x1800224ea  mov     rcx, [rsp+58h]; this
0x1800224ef  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800224f6  mov     edx, 0F89h; void *
0x1800224fb  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180022501  mov     rdi, rbx
0x180022504  jmp     short loc_18002253B
0x180022506  mov     ecx, 7FFFFFFFh
0x18002250b  mov     rax, rbx
0x18002250e  cmp     rbx, rcx
0x180022511  mov     rdi, rbp
0x180022514  cmovnb  rax, rcx
0x180022518  test    rax, rax
0x18002251b  jz      short loc_18002252D
0x18002251d  cmp     [rdi], r12w
0x180022521  jz      short loc_18002252D
0x180022523  add     rdi, 2
0x180022527  sub     rax, 1
0x18002252b  jnz     short loc_18002251D
0x18002252d  sub     rdi, rbp
0x180022530  sar     rdi, 1
0x180022533  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180022537  cmovz   rbx, rdi
0x18002253b  lea     r14, ds:2[rbx*2]
0x180022543  mov     rcx, r14; cb
0x180022546  call    cs:__imp_CoTaskMemAlloc
0x18002254c  mov     rsi, rax
0x18002254f  test    rax, rax
0x180022552  jz      short loc_18002259E
0x180022554  test    rbp, rbp
0x180022557  jz      short loc_180022595
0x180022559  add     rdi, rdi
0x18002255c  jz      short loc_18002258E
0x18002255e  mov     rcx, rax; void *
0x180022561  cmp     r14, rdi
0x180022564  jb      short loc_180022573
0x180022566  mov     r8, rdi; Size
0x180022569  mov     rdx, rbp; Src
0x18002256c  call    memcpy_0
0x180022571  jmp     short loc_18002258E
0x180022573  mov     r8, r14; Size
0x180022576  xor     edx, edx; Val
0x180022578  call    memset_0
0x18002257d  call    cs:__imp__o__errno
0x180022583  mov     dword ptr [rax], 22h ; '"'
0x180022589  call    _invalid_parameter_noinfo
0x18002258e  mov     [rdi+rsi], r12w
0x180022593  jmp     short loc_180022599
0x180022595  mov     [rax], r12w
0x180022599  mov     [rsi+rbx*2], r12w
0x18002259e  mov     [r15], rsi
0x1800225a1  mov     rax, r15
0x1800225a4  add     rsp, 20h
0x1800225a8  pop     r15
0x1800225aa  pop     r14
0x1800225ac  pop     r12
0x1800225ae  pop     rdi
0x1800225af  pop     rsi
0x1800225b0  pop     rbp
0x1800225b1  pop     rbx
0x1800225b2  retn
```
