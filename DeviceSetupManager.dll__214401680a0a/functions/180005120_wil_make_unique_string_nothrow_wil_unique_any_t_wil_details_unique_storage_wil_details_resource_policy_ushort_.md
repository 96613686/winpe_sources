# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180005120`
- end: `0x1800051f5`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `213`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `5`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180004924`
- `0x180014f90`
- `0x18001503c`
- `0x180015358`
- `0x1800350a8`

## callees

- `0x180005120`
- `0x18001b98a`
- `0x18001ba48`
- `0x180020aa4`
- `0x1800419a0`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800051e2`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x1800051e2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005172`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180005172`

## string_xrefs

- `0x1800051c6`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

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
  size_t v8; // rdi
  size_t v9; // rsi
  char *v10; // rax
  char *v11; // rbx
  _QWORD *result; // rax
  __int64 v13; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xF89,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
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
        *(_DWORD *)_o__errno(v13) = 34;
        invalid_parameter_noinfo();
      }
      else
      {
        memcpy_0(v10, a2, v8);
      }
    }
    *(_WORD *)&v11[v8] = 0;
  }
  result = a1;
  *a1 = v11;
  return result;
}

```

## disassembly

```asm
0x180005120  mov     [rsp+arg_18], rbp
0x180005125  push    r14
0x180005127  sub     rsp, 20h
0x18000512b  mov     rbp, rdx
0x18000512e  mov     r14, rcx
0x180005131  test    rdx, rdx
0x180005134  jz      loc_1800051C1
0x18000513a  mov     [rsp+28h+arg_0], rbx
0x18000513f  mov     ecx, 7FFFFFFFh
0x180005144  mov     [rsp+28h+arg_8], rsi
0x180005149  mov     rax, rdx
0x18000514c  mov     [rsp+28h+arg_10], rdi
0x180005151  cmp     word ptr [rax], 0
0x180005155  jz      short loc_180005161
0x180005157  add     rax, 2
0x18000515b  sub     rcx, 1
0x18000515f  jnz     short loc_180005151
0x180005161  sub     rax, rbp
0x180005164  sar     rax, 1
0x180005167  lea     rdi, [rax+rax]
0x18000516b  lea     rsi, [rdi+2]
0x18000516f  mov     rcx, rsi; cb
0x180005172  call    cs:__imp_CoTaskMemAlloc
0x180005178  mov     rbx, rax
0x18000517b  test    rax, rax
0x18000517e  jnz     short loc_1800051A1
0x180005180  mov     rdi, [rsp+28h+arg_10]
0x180005185  mov     rax, r14
0x180005188  mov     rsi, [rsp+28h+arg_8]
0x18000518d  mov     rbp, [rsp+28h+arg_18]
0x180005192  mov     [r14], rbx
0x180005195  mov     rbx, [rsp+28h+arg_0]
0x18000519a  add     rsp, 20h
0x18000519e  pop     r14
0x1800051a0  retn
0x1800051a1  test    rdi, rdi
0x1800051a4  jz      short loc_1800051B9
0x1800051a6  mov     rcx, rbx; void *
0x1800051a9  cmp     rsi, rdi
0x1800051ac  jb      short loc_1800051D8
0x1800051ae  mov     r8, rdi; Size
0x1800051b1  mov     rdx, rbp; Src
0x1800051b4  call    memcpy_0
0x1800051b9  xor     eax, eax
0x1800051bb  mov     [rdi+rbx], ax
0x1800051bf  jmp     short loc_180005180
0x1800051c1  mov     rcx, [rsp+28h]; this
0x1800051c6  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800051cd  mov     edx, 0F89h; void *
0x1800051d2  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800051d8  mov     r8, rsi; Size
0x1800051db  xor     edx, edx; Val
0x1800051dd  call    memset_0
0x1800051e2  call    cs:__imp__o__errno
0x1800051e8  mov     dword ptr [rax], 22h ; '"'
0x1800051ee  call    _invalid_parameter_noinfo
0x1800051f3  jmp     short loc_1800051B9
```
