# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800150c0`
- end: `0x1800151cb`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `267`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `4`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800149f8`
- `0x180014bdc`
- `0x180014f0c`
- `0x1800153c0`

## callees

- `0x1800150c0`
- `0x180032736`
- `0x1800327e0`
- `0x1800327f8`
- `0x180036994`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800151b1`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800151b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001512a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001512a`

## string_xrefs

- `0x18001518d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        unsigned __int64 a3,
        const char *a4)
{
  unsigned __int64 v4; // rbp
  __int64 v7; // rax
  char *v8; // rbx
  __int64 v9; // rbx
  _WORD *v10; // rax
  _WORD *v11; // rdi
  size_t v12; // rbx
  _QWORD *result; // rax
  __int64 v14; // rdx
  __int64 v15; // rcx
  __int64 v16; // r8
  __int64 v17; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = a3;
  if ( a2 )
  {
    v7 = a3;
    v8 = a2;
    if ( a3 >= 0x7FFFFFFF )
      v7 = 0x7FFFFFFF;
    for ( ; v7; --v7 )
    {
      if ( !*(_WORD *)v8 )
        break;
      v8 += 2;
    }
    v9 = (v8 - a2) >> 1;
    if ( a3 == -1 )
      v4 = v9;
  }
  else
  {
    if ( a3 == -1 )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0xF89,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v9 = a3;
  }
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
          *(_DWORD *)_o__errno(v15, v14, v16, v17) = 34;
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
  result = a1;
  *a1 = v11;
  return result;
}

```

## disassembly

```asm
0x1800150c0  mov     [rsp+arg_10], rbx
0x1800150c5  push    rbp
0x1800150c6  push    r14
0x1800150c8  push    r15
0x1800150ca  sub     rsp, 20h
0x1800150ce  mov     rbp, r8
0x1800150d1  mov     r14, rdx
0x1800150d4  mov     r15, rcx
0x1800150d7  test    rdx, rdx
0x1800150da  jz      loc_180015182
0x1800150e0  mov     ecx, 7FFFFFFFh
0x1800150e5  mov     rax, r8
0x1800150e8  cmp     r8, rcx
0x1800150eb  mov     rbx, rdx
0x1800150ee  cmovnb  rax, rcx
0x1800150f2  test    rax, rax
0x1800150f5  jz      short loc_180015107
0x1800150f7  cmp     word ptr [rbx], 0
0x1800150fb  jz      short loc_180015107
0x1800150fd  add     rbx, 2
0x180015101  sub     rax, 1
0x180015105  jnz     short loc_1800150F7
0x180015107  sub     rbx, r14
0x18001510a  sar     rbx, 1
0x18001510d  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180015111  cmovz   rbp, rbx
0x180015115  mov     [rsp+38h+arg_0], rsi
0x18001511a  lea     rsi, ds:2[rbp*2]
0x180015122  mov     rcx, rsi; cb
0x180015125  mov     [rsp+38h+arg_8], rdi
0x18001512a  call    cs:__imp_CoTaskMemAlloc
0x180015130  mov     rdi, rax
0x180015133  test    rax, rax
0x180015136  jz      short loc_180015163
0x180015138  test    r14, r14
0x18001513b  jz      loc_1800151C4
0x180015141  add     rbx, rbx
0x180015144  jz      short loc_180015159
0x180015146  mov     rcx, rax; void *
0x180015149  cmp     rsi, rbx
0x18001514c  jb      short loc_1800151A7
0x18001514e  mov     r8, rbx; Size
0x180015151  mov     rdx, r14; Src
0x180015154  call    memcpy_0
0x180015159  xor     eax, eax
0x18001515b  mov     [rbx+rdi], ax
0x18001515f  mov     [rdi+rbp*2], ax
0x180015163  mov     rsi, [rsp+38h+arg_0]
0x180015168  mov     rax, r15
0x18001516b  mov     rbx, [rsp+38h+arg_10]
0x180015170  mov     [r15], rdi
0x180015173  mov     rdi, [rsp+38h+arg_8]
0x180015178  add     rsp, 20h
0x18001517c  pop     r15
0x18001517e  pop     r14
0x180015180  pop     rbp
0x180015181  retn
0x180015182  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180015186  jnz     short loc_18001519F
0x180015188  mov     rcx, [rsp+38h]; this
0x18001518d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015194  mov     edx, 0F89h; void *
0x180015199  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001519f  mov     rbx, rbp
0x1800151a2  jmp     loc_180015115
0x1800151a7  mov     r8, rsi; Size
0x1800151aa  xor     edx, edx; Val
0x1800151ac  call    memset_0
0x1800151b1  call    cs:__imp__o__errno
0x1800151b7  mov     dword ptr [rax], 22h ; '"'
0x1800151bd  call    _invalid_parameter_noinfo
0x1800151c2  jmp     short loc_180015159
0x1800151c4  xor     eax, eax
0x1800151c6  mov     [rdi], ax
0x1800151c9  jmp     short loc_18001515F
```
