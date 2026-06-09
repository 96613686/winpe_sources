# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x1800143a0`
- end: `0x18001444e`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `174`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18002c8b4`
- `0x18004c768`

## callees

- `0x1800143a0`
- `0x1800154fc`
- `0x18004452c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800143ee`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800143ee`

## string_xrefs

- `0x180014422`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  rsize_t v8; // rdi
  char *v9; // rax
  char *v10; // rbx
  _QWORD *result; // rax
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

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
  v9 = (char *)CoTaskMemAlloc(v8 + 2);
  v10 = v9;
  if ( v9 )
  {
    memcpy_s_0(v9, v8 + 2, a2, v8);
    *(_WORD *)&v10[v8] = 0;
  }
  result = a1;
  *a1 = v10;
  return result;
}

```

## disassembly

```asm
0x1800143a0  mov     [rsp+arg_18], rbp
0x1800143a5  push    r14
0x1800143a7  sub     rsp, 20h
0x1800143ab  mov     rbp, rdx
0x1800143ae  mov     r14, rcx
0x1800143b1  test    rdx, rdx
0x1800143b4  jz      short loc_18001441D
0x1800143b6  mov     [rsp+28h+arg_0], rbx
0x1800143bb  mov     ecx, 7FFFFFFFh
0x1800143c0  mov     [rsp+28h+arg_8], rsi
0x1800143c5  mov     rax, rdx
0x1800143c8  mov     [rsp+28h+arg_10], rdi
0x1800143cd  nop     dword ptr [rax]
0x1800143d0  cmp     word ptr [rax], 0
0x1800143d4  jz      short loc_1800143E0
0x1800143d6  add     rax, 2
0x1800143da  sub     rcx, 1
0x1800143de  jnz     short loc_1800143D0
0x1800143e0  sub     rax, rbp
0x1800143e3  sar     rax, 1
0x1800143e6  lea     rdi, [rax+rax]
0x1800143ea  lea     rcx, [rdi+2]; cb
0x1800143ee  call    cs:__imp_CoTaskMemAlloc
0x1800143f4  mov     rbx, rax
0x1800143f7  test    rax, rax
0x1800143fa  jnz     short loc_180014434
0x1800143fc  mov     rdi, [rsp+28h+arg_10]
0x180014401  mov     rax, r14
0x180014404  mov     rsi, [rsp+28h+arg_8]
0x180014409  mov     rbp, [rsp+28h+arg_18]
0x18001440e  mov     [r14], rbx
0x180014411  mov     rbx, [rsp+28h+arg_0]
0x180014416  add     rsp, 20h
0x18001441a  pop     r14
0x18001441c  retn
0x18001441d  mov     rcx, [rsp+28h]; this
0x180014422  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180014429  mov     edx, 0F89h; void *
0x18001442e  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180014434  mov     r9, rdi; SourceSize
0x180014437  lea     rdx, [rdi+2]; DestinationSize
0x18001443b  mov     r8, rbp; Source
0x18001443e  mov     rcx, rbx; Destination
0x180014441  call    memcpy_s_0
0x180014446  xor     ecx, ecx
0x180014448  mov     [rdi+rbx], cx
0x18001444c  jmp     short loc_1800143FC
```
