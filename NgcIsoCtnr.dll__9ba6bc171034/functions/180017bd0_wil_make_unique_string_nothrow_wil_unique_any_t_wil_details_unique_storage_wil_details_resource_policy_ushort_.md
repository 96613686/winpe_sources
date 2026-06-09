# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180017bd0`
- end: `0x180017c86`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `182`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180017b80`

## callees

- `0x180008406`
- `0x1800084b0`
- `0x1800084c8`
- `0x18000acd8`
- `0x180017bd0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017c5d`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180017c5d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017c2b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180017c2b`

## string_xrefs

- `0x180017bf0`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        char *a2,
        __int64 a3,
        const char *a4)
{
  __int64 v6; // rcx
  char *v7; // rax
  size_t v8; // rbx
  size_t v9; // rbp
  char *v10; // rax
  char *v11; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v6 = 0x7FFFFFFF;
  v7 = a2;
  do
  {
    if ( !*(_WORD *)v7 )
      break;
    v7 += 2;
    --v6;
  }
  while ( v6 );
  v8 = 2 * ((v7 - a2) >> 1);
  v9 = v8 + 2;
  v10 = (char *)CoTaskMemAlloc(v8 + 2);
  v11 = v10;
  if ( v10 )
  {
    if ( v8 )
    {
      if ( v9 < v8 )
      {
        memset_0(v10, 0, v9);
        *(_DWORD *)_o__errno() = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v10, a2, v8);
      }
    }
    *(_WORD *)&v11[v8] = 0;
  }
  *a1 = v11;
  return a1;
}

```

## disassembly

```asm
0x180017bd0  push    rbx
0x180017bd2  push    rbp
0x180017bd3  push    rsi
0x180017bd4  push    rdi
0x180017bd5  push    r14
0x180017bd7  push    r15
0x180017bd9  sub     rsp, 28h
0x180017bdd  xor     r15d, r15d
0x180017be0  mov     rsi, rdx
0x180017be3  mov     r14, rcx
0x180017be6  test    rdx, rdx
0x180017be9  jnz     short loc_180017C02
0x180017beb  mov     rcx, [rsp+58h]; this
0x180017bf0  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017bf7  mov     edx, 0F89h; void *
0x180017bfc  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180017c02  mov     ecx, 7FFFFFFFh
0x180017c07  mov     rax, rsi
0x180017c0a  cmp     [rax], r15w
0x180017c0e  jz      short loc_180017C1A
0x180017c10  add     rax, 2
0x180017c14  sub     rcx, 1
0x180017c18  jnz     short loc_180017C0A
0x180017c1a  sub     rax, rsi
0x180017c1d  sar     rax, 1
0x180017c20  lea     rbx, [rax+rax]
0x180017c24  lea     rbp, [rbx+2]
0x180017c28  mov     rcx, rbp; cb
0x180017c2b  call    cs:__imp_CoTaskMemAlloc
0x180017c31  mov     rdi, rax
0x180017c34  test    rax, rax
0x180017c37  jz      short loc_180017C73
0x180017c39  test    rbx, rbx
0x180017c3c  jz      short loc_180017C6E
0x180017c3e  mov     rcx, rax; void *
0x180017c41  cmp     rbp, rbx
0x180017c44  jb      short loc_180017C53
0x180017c46  mov     r8, rbx; Size
0x180017c49  mov     rdx, rsi; Src
0x180017c4c  call    memcpy_0
0x180017c51  jmp     short loc_180017C6E
0x180017c53  mov     r8, rbp; Size
0x180017c56  xor     edx, edx; Val
0x180017c58  call    memset_0
0x180017c5d  call    cs:__imp__o__errno
0x180017c63  mov     dword ptr [rax], 22h ; '"'
0x180017c69  call    _invalid_parameter_noinfo
0x180017c6e  mov     [rbx+rdi], r15w
0x180017c73  mov     [r14], rdi
0x180017c76  mov     rax, r14
0x180017c79  add     rsp, 28h
0x180017c7d  pop     r15
0x180017c7f  pop     r14
0x180017c81  pop     rdi
0x180017c82  pop     rsi
0x180017c83  pop     rbp
0x180017c84  pop     rbx
0x180017c85  retn
```
