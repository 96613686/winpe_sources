# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800115f4`
- end: `0x1800116aa`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `182`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180011890`
- `0x180011ea0`
- `0x180011f10`

## callees

- `0x18000566a`
- `0x1800056e0`
- `0x18000d0b0`
- `0x1800115f4`
- `0x18001364c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011681`
- `api-ms-win-crt-private-l1-1-0!_o__errno` at `0x180011681`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001164f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001164f`

## string_xrefs

- `0x180011614`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x1800115f4  push    rbx
0x1800115f6  push    rbp
0x1800115f7  push    rsi
0x1800115f8  push    rdi
0x1800115f9  push    r14
0x1800115fb  push    r15
0x1800115fd  sub     rsp, 28h
0x180011601  xor     r15d, r15d
0x180011604  mov     rsi, rdx
0x180011607  mov     r14, rcx
0x18001160a  test    rdx, rdx
0x18001160d  jnz     short loc_180011626
0x18001160f  mov     rcx, [rsp+58h]; this
0x180011614  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001161b  mov     edx, 0F89h; void *
0x180011620  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180011626  mov     ecx, 7FFFFFFFh
0x18001162b  mov     rax, rsi
0x18001162e  cmp     [rax], r15w
0x180011632  jz      short loc_18001163E
0x180011634  add     rax, 2
0x180011638  sub     rcx, 1
0x18001163c  jnz     short loc_18001162E
0x18001163e  sub     rax, rsi
0x180011641  sar     rax, 1
0x180011644  lea     rbx, [rax+rax]
0x180011648  lea     rbp, [rbx+2]
0x18001164c  mov     rcx, rbp; cb
0x18001164f  call    cs:__imp_CoTaskMemAlloc
0x180011655  mov     rdi, rax
0x180011658  test    rax, rax
0x18001165b  jz      short loc_180011697
0x18001165d  test    rbx, rbx
0x180011660  jz      short loc_180011692
0x180011662  mov     rcx, rax; void *
0x180011665  cmp     rbp, rbx
0x180011668  jb      short loc_180011677
0x18001166a  mov     r8, rbx; Size
0x18001166d  mov     rdx, rsi; Src
0x180011670  call    memcpy_0
0x180011675  jmp     short loc_180011692
0x180011677  mov     r8, rbp; Size
0x18001167a  xor     edx, edx; Val
0x18001167c  call    memset_0
0x180011681  call    cs:__imp__o__errno
0x180011687  mov     dword ptr [rax], 22h ; '"'
0x18001168d  call    _invalid_parameter_noinfo
0x180011692  mov     [rbx+rdi], r15w
0x180011697  mov     [r14], rdi
0x18001169a  mov     rax, r14
0x18001169d  add     rsp, 28h
0x1800116a1  pop     r15
0x1800116a3  pop     r14
0x1800116a5  pop     rdi
0x1800116a6  pop     rsi
0x1800116a7  pop     rbp
0x1800116a8  pop     rbx
0x1800116a9  retn
```
