# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180026d18`
- end: `0x180026e0d`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `245`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, unsigned __int64, const char *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x18002545c`
- `0x180029348`

## callees

- `0x180002f3a`
- `0x180002f98`
- `0x180003b51`
- `0x180006cb8`
- `0x180026d18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026dc0`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180026dc0`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026d89`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x180026d89`

## string_xrefs

- `0x180026dfb`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int64 v13; // rcx
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
          *(_DWORD *)_o__errno(v13) = 34;
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
0x180026d18  push    rbx
0x180026d1a  push    rbp
0x180026d1b  push    rsi
0x180026d1c  push    rdi
0x180026d1d  push    r12
0x180026d1f  push    r14
0x180026d21  push    r15
0x180026d23  sub     rsp, 20h
0x180026d27  xor     r12d, r12d
0x180026d2a  mov     rdi, r8
0x180026d2d  mov     rbp, rdx
0x180026d30  mov     r15, rcx
0x180026d33  test    rdx, rdx
0x180026d36  jnz     short loc_180026D47
0x180026d38  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x180026d3c  jz      loc_180026DF6
0x180026d42  mov     rbx, r8
0x180026d45  jmp     short loc_180026D7C
0x180026d47  mov     ecx, 7FFFFFFFh
0x180026d4c  mov     rax, rdi
0x180026d4f  cmp     rdi, rcx
0x180026d52  mov     rbx, rbp
0x180026d55  cmovnb  rax, rcx
0x180026d59  test    rax, rax
0x180026d5c  jz      short loc_180026D6E
0x180026d5e  cmp     [rbx], r12w
0x180026d62  jz      short loc_180026D6E
0x180026d64  add     rbx, 2
0x180026d68  sub     rax, 1
0x180026d6c  jnz     short loc_180026D5E
0x180026d6e  sub     rbx, rbp
0x180026d71  sar     rbx, 1
0x180026d74  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180026d78  cmovz   rdi, rbx
0x180026d7c  lea     r14, ds:2[rdi*2]
0x180026d84  xor     ecx, ecx; uFlags
0x180026d86  mov     rdx, r14; uBytes
0x180026d89  call    cs:__imp_LocalAlloc
0x180026d8f  mov     rsi, rax
0x180026d92  test    rax, rax
0x180026d95  jz      short loc_180026DE1
0x180026d97  test    rbp, rbp
0x180026d9a  jz      short loc_180026DD8
0x180026d9c  add     rbx, rbx
0x180026d9f  jz      short loc_180026DD1
0x180026da1  mov     rcx, rax; void *
0x180026da4  cmp     r14, rbx
0x180026da7  jb      short loc_180026DB6
0x180026da9  mov     r8, rbx; Size
0x180026dac  mov     rdx, rbp; Src
0x180026daf  call    memcpy_0
0x180026db4  jmp     short loc_180026DD1
0x180026db6  mov     r8, r14; Size
0x180026db9  xor     edx, edx; Val
0x180026dbb  call    memset_0
0x180026dc0  call    cs:__imp__o__errno
0x180026dc6  mov     dword ptr [rax], 22h ; '"'
0x180026dcc  call    _invalid_parameter_noinfo
0x180026dd1  mov     [rbx+rsi], r12w
0x180026dd6  jmp     short loc_180026DDC
0x180026dd8  mov     [rax], r12w
0x180026ddc  mov     [rsi+rdi*2], r12w
0x180026de1  mov     [r15], rsi
0x180026de4  mov     rax, r15
0x180026de7  add     rsp, 20h
0x180026deb  pop     r15
0x180026ded  pop     r14
0x180026def  pop     r12
0x180026df1  pop     rdi
0x180026df2  pop     rsi
0x180026df3  pop     rbp
0x180026df4  pop     rbx
0x180026df5  retn
0x180026df6  mov     rcx, [rsp+58h]; this
0x180026dfb  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180026e02  mov     edx, 0F89h; void *
0x180026e07  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
