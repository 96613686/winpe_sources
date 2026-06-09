# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18001c560`
- end: `0x18001c64f`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `239`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18001e468`
- `0x18001e93c`

## callees

- `0x18000372a`
- `0x1800037ac`
- `0x180013ddc`
- `0x18001c560`
- `0x18002b540`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c619`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x18001c619`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c5e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001c5e2`

## string_xrefs

- `0x18001c58b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
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
0x18001c560  push    rbx
0x18001c562  push    rbp
0x18001c563  push    rsi
0x18001c564  push    rdi
0x18001c565  push    r12
0x18001c567  push    r14
0x18001c569  push    r15
0x18001c56b  sub     rsp, 20h
0x18001c56f  xor     r12d, r12d
0x18001c572  mov     rbx, r8
0x18001c575  mov     rbp, rdx
0x18001c578  mov     r15, rcx
0x18001c57b  test    rdx, rdx
0x18001c57e  jnz     short loc_18001C5A2
0x18001c580  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001c584  jnz     short loc_18001C59D
0x18001c586  mov     rcx, [rsp+58h]; this
0x18001c58b  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001c592  mov     edx, 0F89h; void *
0x18001c597  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001c59d  mov     rdi, rbx
0x18001c5a0  jmp     short loc_18001C5D7
0x18001c5a2  mov     ecx, 7FFFFFFFh
0x18001c5a7  mov     rax, rbx
0x18001c5aa  cmp     rbx, rcx
0x18001c5ad  mov     rdi, rbp
0x18001c5b0  cmovnb  rax, rcx
0x18001c5b4  test    rax, rax
0x18001c5b7  jz      short loc_18001C5C9
0x18001c5b9  cmp     [rdi], r12w
0x18001c5bd  jz      short loc_18001C5C9
0x18001c5bf  add     rdi, 2
0x18001c5c3  sub     rax, 1
0x18001c5c7  jnz     short loc_18001C5B9
0x18001c5c9  sub     rdi, rbp
0x18001c5cc  sar     rdi, 1
0x18001c5cf  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18001c5d3  cmovz   rbx, rdi
0x18001c5d7  lea     r14, ds:2[rbx*2]
0x18001c5df  mov     rcx, r14; cb
0x18001c5e2  call    cs:__imp_CoTaskMemAlloc
0x18001c5e8  mov     rsi, rax
0x18001c5eb  test    rax, rax
0x18001c5ee  jz      short loc_18001C63A
0x18001c5f0  test    rbp, rbp
0x18001c5f3  jz      short loc_18001C631
0x18001c5f5  add     rdi, rdi
0x18001c5f8  jz      short loc_18001C62A
0x18001c5fa  mov     rcx, rax; void *
0x18001c5fd  cmp     r14, rdi
0x18001c600  jb      short loc_18001C60F
0x18001c602  mov     r8, rdi; Size
0x18001c605  mov     rdx, rbp; Src
0x18001c608  call    memcpy_0
0x18001c60d  jmp     short loc_18001C62A
0x18001c60f  mov     r8, r14; Size
0x18001c612  xor     edx, edx; Val
0x18001c614  call    memset_0
0x18001c619  call    cs:__imp__o__errno
0x18001c61f  mov     dword ptr [rax], 22h ; '"'
0x18001c625  call    _invalid_parameter_noinfo
0x18001c62a  mov     [rdi+rsi], r12w
0x18001c62f  jmp     short loc_18001C635
0x18001c631  mov     [rax], r12w
0x18001c635  mov     [rsi+rbx*2], r12w
0x18001c63a  mov     [r15], rsi
0x18001c63d  mov     rax, r15
0x18001c640  add     rsp, 20h
0x18001c644  pop     r15
0x18001c646  pop     r14
0x18001c648  pop     r12
0x18001c64a  pop     rdi
0x18001c64b  pop     rsi
0x18001c64c  pop     rbp
0x18001c64d  pop     rbx
0x18001c64e  retn
```
