# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180006a10`
- end: `0x180006b14`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `260`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180005678`
- `0x1800069b0`
- `0x1800165bc`
- `0x18002d9bc`
- `0x180035f08`
- `0x180041334`
- `0x180075bec`

## callees

- `0x180006a10`
- `0x180031f34`
- `0x180038682`
- `0x1800386f0`
- `0x180038708`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006b01`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180006b01`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006a7a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180006a7a`

## string_xrefs

- `0x180006ae5`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  result = a1;
  *a1 = v11;
  return result;
}

```

## disassembly

```asm
0x180006a10  mov     [rsp+arg_10], rbx
0x180006a15  push    rbp
0x180006a16  push    r14
0x180006a18  push    r15
0x180006a1a  sub     rsp, 20h
0x180006a1e  mov     rbp, r8
0x180006a21  mov     r14, rdx
0x180006a24  mov     r15, rcx
0x180006a27  test    rdx, rdx
0x180006a2a  jz      loc_180006AD5
0x180006a30  mov     ecx, 7FFFFFFFh
0x180006a35  mov     rax, r8
0x180006a38  cmp     r8, rcx
0x180006a3b  mov     rbx, rdx
0x180006a3e  cmovnb  rax, rcx
0x180006a42  test    rax, rax
0x180006a45  jz      short loc_180006A57
0x180006a47  cmp     word ptr [rbx], 0
0x180006a4b  jz      short loc_180006A57
0x180006a4d  add     rbx, 2
0x180006a51  sub     rax, 1
0x180006a55  jnz     short loc_180006A47
0x180006a57  sub     rbx, r14
0x180006a5a  sar     rbx, 1
0x180006a5d  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180006a61  cmovz   rbp, rbx
0x180006a65  mov     [rsp+38h+arg_0], rsi
0x180006a6a  lea     rsi, ds:2[rbp*2]
0x180006a72  mov     rcx, rsi; cb
0x180006a75  mov     [rsp+38h+arg_8], rdi
0x180006a7a  call    cs:__imp_CoTaskMemAlloc
0x180006a80  mov     rdi, rax
0x180006a83  test    rax, rax
0x180006a86  jz      short loc_180006AB6
0x180006a88  test    r14, r14
0x180006a8b  jz      short loc_180006AAD
0x180006a8d  add     rbx, rbx
0x180006a90  jz      short loc_180006AA5
0x180006a92  mov     rcx, rax; void *
0x180006a95  cmp     rsi, rbx
0x180006a98  jb      short loc_180006AF7
0x180006a9a  mov     r8, rbx; Size
0x180006a9d  mov     rdx, r14; Src
0x180006aa0  call    memcpy_0
0x180006aa5  xor     eax, eax
0x180006aa7  mov     [rbx+rdi], ax
0x180006aab  jmp     short loc_180006AB2
0x180006aad  xor     eax, eax
0x180006aaf  mov     [rdi], ax
0x180006ab2  mov     [rdi+rbp*2], ax
0x180006ab6  mov     rsi, [rsp+38h+arg_0]
0x180006abb  mov     rax, r15
0x180006abe  mov     rbx, [rsp+38h+arg_10]
0x180006ac3  mov     [r15], rdi
0x180006ac6  mov     rdi, [rsp+38h+arg_8]
0x180006acb  add     rsp, 20h
0x180006acf  pop     r15
0x180006ad1  pop     r14
0x180006ad3  pop     rbp
0x180006ad4  retn
0x180006ad5  cmp     rbp, 0FFFFFFFFFFFFFFFFh
0x180006ad9  jz      short loc_180006AE0
0x180006adb  mov     rbx, rbp
0x180006ade  jmp     short loc_180006A65
0x180006ae0  mov     rcx, [rsp+38h]; this
0x180006ae5  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180006aec  mov     edx, 0F89h; void *
0x180006af1  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180006af7  mov     r8, rsi; Size
0x180006afa  xor     edx, edx; Val
0x180006afc  call    memset_0
0x180006b01  call    cs:__imp__o__errno
0x180006b07  mov     dword ptr [rax], 22h ; '"'
0x180006b0d  call    _invalid_parameter_noinfo
0x180006b12  jmp     short loc_180006AA5
```
