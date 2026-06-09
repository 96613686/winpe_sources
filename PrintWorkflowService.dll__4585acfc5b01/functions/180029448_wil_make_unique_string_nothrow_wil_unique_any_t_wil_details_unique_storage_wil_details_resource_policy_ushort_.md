# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180029448`
- end: `0x180029537`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `239`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002cec8`
- `0x180056188`

## callees

- `0x1800048d6`
- `0x180004944`
- `0x18000495c`
- `0x18000c1cc`
- `0x180029448`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029501`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180029501`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800294ca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800294ca`

## string_xrefs

- `0x180029473`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180029448  push    rbx
0x18002944a  push    rbp
0x18002944b  push    rsi
0x18002944c  push    rdi
0x18002944d  push    r12
0x18002944f  push    r14
0x180029451  push    r15
0x180029453  sub     rsp, 20h
0x180029457  xor     r12d, r12d
0x18002945a  mov     rbx, r8
0x18002945d  mov     rbp, rdx
0x180029460  mov     r15, rcx
0x180029463  test    rdx, rdx
0x180029466  jnz     short loc_18002948A
0x180029468  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18002946c  jnz     short loc_180029485
0x18002946e  mov     rcx, [rsp+58h]; this
0x180029473  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002947a  mov     edx, 0F89h; void *
0x18002947f  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180029485  mov     rdi, rbx
0x180029488  jmp     short loc_1800294BF
0x18002948a  mov     ecx, 7FFFFFFFh
0x18002948f  mov     rax, rbx
0x180029492  cmp     rbx, rcx
0x180029495  mov     rdi, rbp
0x180029498  cmovnb  rax, rcx
0x18002949c  test    rax, rax
0x18002949f  jz      short loc_1800294B1
0x1800294a1  cmp     [rdi], r12w
0x1800294a5  jz      short loc_1800294B1
0x1800294a7  add     rdi, 2
0x1800294ab  sub     rax, 1
0x1800294af  jnz     short loc_1800294A1
0x1800294b1  sub     rdi, rbp
0x1800294b4  sar     rdi, 1
0x1800294b7  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x1800294bb  cmovz   rbx, rdi
0x1800294bf  lea     r14, ds:2[rbx*2]
0x1800294c7  mov     rcx, r14; cb
0x1800294ca  call    cs:__imp_CoTaskMemAlloc
0x1800294d0  mov     rsi, rax
0x1800294d3  test    rax, rax
0x1800294d6  jz      short loc_180029522
0x1800294d8  test    rbp, rbp
0x1800294db  jz      short loc_180029519
0x1800294dd  add     rdi, rdi
0x1800294e0  jz      short loc_180029512
0x1800294e2  mov     rcx, rax; void *
0x1800294e5  cmp     r14, rdi
0x1800294e8  jb      short loc_1800294F7
0x1800294ea  mov     r8, rdi; Size
0x1800294ed  mov     rdx, rbp; Src
0x1800294f0  call    memcpy_0
0x1800294f5  jmp     short loc_180029512
0x1800294f7  mov     r8, r14; Size
0x1800294fa  xor     edx, edx; Val
0x1800294fc  call    memset_0
0x180029501  call    cs:__imp__o__errno
0x180029507  mov     dword ptr [rax], 22h ; '"'
0x18002950d  call    _invalid_parameter_noinfo
0x180029512  mov     [rdi+rsi], r12w
0x180029517  jmp     short loc_18002951D
0x180029519  mov     [rax], r12w
0x18002951d  mov     [rsi+rbx*2], r12w
0x180029522  mov     [r15], rsi
0x180029525  mov     rax, r15
0x180029528  add     rsp, 20h
0x18002952c  pop     r15
0x18002952e  pop     r14
0x180029530  pop     r12
0x180029532  pop     rdi
0x180029533  pop     rsi
0x180029534  pop     rbp
0x180029535  pop     rbx
0x180029536  retn
```
