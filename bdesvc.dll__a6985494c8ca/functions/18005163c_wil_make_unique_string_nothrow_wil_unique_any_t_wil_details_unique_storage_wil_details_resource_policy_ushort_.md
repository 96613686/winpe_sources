# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18005163c`
- end: `0x180051738`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `252`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180058f40`

## callees

- `0x180034c72`
- `0x180034d10`
- `0x180034d28`
- `0x180036178`
- `0x18005163c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800516fb`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800516fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800516be`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800516be`

## string_xrefs

- `0x180051667`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
0x18005163c  push    rbx
0x18005163e  push    rbp
0x18005163f  push    rsi
0x180051640  push    rdi
0x180051641  push    r12
0x180051643  push    r14
0x180051645  push    r15
0x180051647  sub     rsp, 20h
0x18005164b  xor     r12d, r12d
0x18005164e  mov     rbx, r8
0x180051651  mov     rbp, rdx
0x180051654  mov     r15, rcx
0x180051657  test    rdx, rdx
0x18005165a  jnz     short loc_18005167E
0x18005165c  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x180051660  jnz     short loc_180051679
0x180051662  mov     rcx, [rsp+58h]; this
0x180051667  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18005166e  mov     edx, 0F89h; void *
0x180051673  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180051679  mov     rdi, rbx
0x18005167c  jmp     short loc_1800516B3
0x18005167e  mov     ecx, 7FFFFFFFh
0x180051683  mov     rax, rbx
0x180051686  cmp     rbx, rcx
0x180051689  mov     rdi, rbp
0x18005168c  cmovnb  rax, rcx
0x180051690  test    rax, rax
0x180051693  jz      short loc_1800516A5
0x180051695  cmp     [rdi], r12w
0x180051699  jz      short loc_1800516A5
0x18005169b  add     rdi, 2
0x18005169f  sub     rax, 1
0x1800516a3  jnz     short loc_180051695
0x1800516a5  sub     rdi, rbp
0x1800516a8  sar     rdi, 1
0x1800516ab  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800516af  cmovz   rbx, rdi
0x1800516b3  lea     r14, ds:2[rbx*2]
0x1800516bb  mov     rcx, r14; cb
0x1800516be  call    cs:__imp_CoTaskMemAlloc
0x1800516c5  nop     dword ptr [rax+rax+00h]
0x1800516ca  mov     rsi, rax
0x1800516cd  test    rax, rax
0x1800516d0  jz      short loc_180051722
0x1800516d2  test    rbp, rbp
0x1800516d5  jz      short loc_180051719
0x1800516d7  add     rdi, rdi
0x1800516da  jz      short loc_180051712
0x1800516dc  mov     rcx, rax; void *
0x1800516df  cmp     r14, rdi
0x1800516e2  jb      short loc_1800516F1
0x1800516e4  mov     r8, rdi; Size
0x1800516e7  mov     rdx, rbp; Src
0x1800516ea  call    memcpy_0
0x1800516ef  jmp     short loc_180051712
0x1800516f1  mov     r8, r14; Size
0x1800516f4  xor     edx, edx; Val
0x1800516f6  call    memset_0
0x1800516fb  call    cs:__imp__o__errno
0x180051702  nop     dword ptr [rax+rax+00h]
0x180051707  mov     dword ptr [rax], 22h ; '"'
0x18005170d  call    _invalid_parameter_noinfo
0x180051712  mov     [rdi+rsi], r12w
0x180051717  jmp     short loc_18005171D
0x180051719  mov     [rax], r12w
0x18005171d  mov     [rsi+rbx*2], r12w
0x180051722  mov     [r15], rsi
0x180051725  mov     rax, r15
0x180051728  add     rsp, 20h
0x18005172c  pop     r15
0x18005172e  pop     r14
0x180051730  pop     r12
0x180051732  pop     rdi
0x180051733  pop     rsi
0x180051734  pop     rbp
0x180051735  pop     rbx
0x180051736  retn
```
