# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180064d10`
- end: `0x180064dff`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `239`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180066f30`
- `0x1800869ac`

## callees

- `0x1800049c6`
- `0x180004a70`
- `0x180006249`
- `0x1800081e8`
- `0x180064d10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180064dc9`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180064dc9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180064d92`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180064d92`

## string_xrefs

- `0x180064d3b`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180064d10  push    rbx
0x180064d12  push    rbp
0x180064d13  push    rsi
0x180064d14  push    rdi
0x180064d15  push    r12
0x180064d17  push    r14
0x180064d19  push    r15
0x180064d1b  sub     rsp, 20h
0x180064d1f  xor     r12d, r12d
0x180064d22  mov     rbx, r8
0x180064d25  mov     rbp, rdx
0x180064d28  mov     r15, rcx
0x180064d2b  test    rdx, rdx
0x180064d2e  jnz     short loc_180064D52
0x180064d30  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180064d34  jnz     short loc_180064D4D
0x180064d36  mov     rcx, [rsp+58h]; this
0x180064d3b  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180064d42  mov     edx, 0F89h; void *
0x180064d47  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180064d4d  mov     rdi, rbx
0x180064d50  jmp     short loc_180064D87
0x180064d52  mov     ecx, 7FFFFFFFh
0x180064d57  mov     rax, rbx
0x180064d5a  cmp     rbx, rcx
0x180064d5d  mov     rdi, rbp
0x180064d60  cmovnb  rax, rcx
0x180064d64  test    rax, rax
0x180064d67  jz      short loc_180064D79
0x180064d69  cmp     [rdi], r12w
0x180064d6d  jz      short loc_180064D79
0x180064d6f  add     rdi, 2
0x180064d73  sub     rax, 1
0x180064d77  jnz     short loc_180064D69
0x180064d79  sub     rdi, rbp
0x180064d7c  sar     rdi, 1
0x180064d7f  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180064d83  cmovz   rbx, rdi
0x180064d87  lea     r14, ds:2[rbx*2]
0x180064d8f  mov     rcx, r14; cb
0x180064d92  call    cs:__imp_CoTaskMemAlloc
0x180064d98  mov     rsi, rax
0x180064d9b  test    rax, rax
0x180064d9e  jz      short loc_180064DEA
0x180064da0  test    rbp, rbp
0x180064da3  jz      short loc_180064DE1
0x180064da5  add     rdi, rdi
0x180064da8  jz      short loc_180064DDA
0x180064daa  mov     rcx, rax; void *
0x180064dad  cmp     r14, rdi
0x180064db0  jb      short loc_180064DBF
0x180064db2  mov     r8, rdi; Size
0x180064db5  mov     rdx, rbp; Src
0x180064db8  call    memcpy_0
0x180064dbd  jmp     short loc_180064DDA
0x180064dbf  mov     r8, r14; Size
0x180064dc2  xor     edx, edx; Val
0x180064dc4  call    memset_0
0x180064dc9  call    cs:__imp__o__errno
0x180064dcf  mov     dword ptr [rax], 22h ; '"'
0x180064dd5  call    _invalid_parameter_noinfo
0x180064dda  mov     [rdi+rsi], r12w
0x180064ddf  jmp     short loc_180064DE5
0x180064de1  mov     [rax], r12w
0x180064de5  mov     [rsi+rbx*2], r12w
0x180064dea  mov     [r15], rsi
0x180064ded  mov     rax, r15
0x180064df0  add     rsp, 20h
0x180064df4  pop     r15
0x180064df6  pop     r14
0x180064df8  pop     r12
0x180064dfa  pop     rdi
0x180064dfb  pop     rsi
0x180064dfc  pop     rbp
0x180064dfd  pop     rbx
0x180064dfe  retn
```
