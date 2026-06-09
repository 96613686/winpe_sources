# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x18000e96c`
- end: `0x18000e9fc`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `144`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000e928`

## callees

- `0x180006c38`
- `0x1800092f8`
- `0x18000e96c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e9c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000e9c4`

## string_xrefs

- `0x18000e98c`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  rsize_t v8; // r14
  char *v9; // rax
  char *v10; // rdi
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
  v9 = (char *)CoTaskMemAlloc(v8 + 2);
  v10 = v9;
  if ( v9 )
  {
    memcpy_s(v9, v8 + 2, a2, v8);
    *(_WORD *)&v10[v8] = 0;
  }
  *a1 = v10;
  return a1;
}

```

## disassembly

```asm
0x18000e96c  push    rbx
0x18000e96e  push    rbp
0x18000e96f  push    rsi
0x18000e970  push    rdi
0x18000e971  push    r14
0x18000e973  push    r15
0x18000e975  sub     rsp, 28h
0x18000e979  xor     r15d, r15d
0x18000e97c  mov     rbx, rdx
0x18000e97f  mov     rsi, rcx
0x18000e982  test    rdx, rdx
0x18000e985  jnz     short loc_18000E99E
0x18000e987  mov     rcx, [rsp+58h]; this
0x18000e98c  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e993  mov     edx, 0F89h; void *
0x18000e998  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18000e99e  mov     ecx, 7FFFFFFFh
0x18000e9a3  mov     rax, rbx
0x18000e9a6  cmp     [rax], r15w
0x18000e9aa  jz      short loc_18000E9B6
0x18000e9ac  add     rax, 2
0x18000e9b0  sub     rcx, 1
0x18000e9b4  jnz     short loc_18000E9A6
0x18000e9b6  sub     rax, rbx
0x18000e9b9  sar     rax, 1
0x18000e9bc  lea     r14, [rax+rax]
0x18000e9c0  lea     rcx, [r14+2]; cb
0x18000e9c4  call    cs:__imp_CoTaskMemAlloc
0x18000e9ca  mov     rdi, rax
0x18000e9cd  test    rax, rax
0x18000e9d0  jz      short loc_18000E9E9
0x18000e9d2  mov     r9, r14; SourceSize
0x18000e9d5  lea     rdx, [r14+2]; DestinationSize
0x18000e9d9  mov     r8, rbx; Source
0x18000e9dc  mov     rcx, rax; Destination
0x18000e9df  call    memcpy_s
0x18000e9e4  mov     [r14+rdi], r15w
0x18000e9e9  mov     [rsi], rdi
0x18000e9ec  mov     rax, rsi
0x18000e9ef  add     rsp, 28h
0x18000e9f3  pop     r15
0x18000e9f5  pop     r14
0x18000e9f7  pop     rdi
0x18000e9f8  pop     rsi
0x18000e9f9  pop     rbp
0x18000e9fa  pop     rbx
0x18000e9fb  retn
```
