# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800238cc`
- end: `0x1800239c8`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `252`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800237a0`
- `0x18003c9f4`
- `0x1800595dc`

## callees

- `0x1800238cc`
- `0x18002d486`
- `0x18002d500`
- `0x18002d518`
- `0x18002f268`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002398b`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18002398b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002394e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002394e`

## string_xrefs

- `0x1800238f7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800238cc  push    rbx
0x1800238ce  push    rbp
0x1800238cf  push    rsi
0x1800238d0  push    rdi
0x1800238d1  push    r12
0x1800238d3  push    r14
0x1800238d5  push    r15
0x1800238d7  sub     rsp, 20h
0x1800238db  xor     r12d, r12d
0x1800238de  mov     rbx, r8
0x1800238e1  mov     rbp, rdx
0x1800238e4  mov     r15, rcx
0x1800238e7  test    rdx, rdx
0x1800238ea  jnz     short loc_18002390E
0x1800238ec  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800238f0  jnz     short loc_180023909
0x1800238f2  mov     rcx, [rsp+58h]; this
0x1800238f7  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800238fe  mov     edx, 0F89h; void *
0x180023903  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180023909  mov     rdi, rbx
0x18002390c  jmp     short loc_180023943
0x18002390e  mov     ecx, 7FFFFFFFh
0x180023913  mov     rax, rbx
0x180023916  cmp     rbx, rcx
0x180023919  mov     rdi, rbp
0x18002391c  cmovnb  rax, rcx
0x180023920  test    rax, rax
0x180023923  jz      short loc_180023935
0x180023925  cmp     [rdi], r12w
0x180023929  jz      short loc_180023935
0x18002392b  add     rdi, 2
0x18002392f  sub     rax, 1
0x180023933  jnz     short loc_180023925
0x180023935  sub     rdi, rbp
0x180023938  sar     rdi, 1
0x18002393b  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002393f  cmovz   rbx, rdi
0x180023943  lea     r14, ds:2[rbx*2]
0x18002394b  mov     rcx, r14; cb
0x18002394e  call    cs:__imp_CoTaskMemAlloc
0x180023955  nop     dword ptr [rax+rax+00h]
0x18002395a  mov     rsi, rax
0x18002395d  test    rax, rax
0x180023960  jz      short loc_1800239B2
0x180023962  test    rbp, rbp
0x180023965  jz      short loc_1800239A9
0x180023967  add     rdi, rdi
0x18002396a  jz      short loc_1800239A2
0x18002396c  mov     rcx, rax; void *
0x18002396f  cmp     r14, rdi
0x180023972  jb      short loc_180023981
0x180023974  mov     r8, rdi; Size
0x180023977  mov     rdx, rbp; Src
0x18002397a  call    memcpy_0
0x18002397f  jmp     short loc_1800239A2
0x180023981  mov     r8, r14; Size
0x180023984  xor     edx, edx; Val
0x180023986  call    memset_0
0x18002398b  call    cs:__imp__o__errno
0x180023992  nop     dword ptr [rax+rax+00h]
0x180023997  mov     dword ptr [rax], 22h ; '"'
0x18002399d  call    _invalid_parameter_noinfo
0x1800239a2  mov     [rdi+rsi], r12w
0x1800239a7  jmp     short loc_1800239AD
0x1800239a9  mov     [rax], r12w
0x1800239ad  mov     [rsi+rbx*2], r12w
0x1800239b2  mov     [r15], rsi
0x1800239b5  mov     rax, r15
0x1800239b8  add     rsp, 20h
0x1800239bc  pop     r15
0x1800239be  pop     r14
0x1800239c0  pop     r12
0x1800239c2  pop     rdi
0x1800239c3  pop     rsi
0x1800239c4  pop     rbp
0x1800239c5  pop     rbx
0x1800239c6  retn
```
