# wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)

- ea: `0x180015ebc`
- end: `0x180015f4c`
- name: `??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z`
- size: `144`
- prototype: `_QWORD *__fastcall(_QWORD *, char *, __int64, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180015e6c`
- `0x180038914`

## callees

- `0x18000c0f8`
- `0x18000cc94`
- `0x180015ebc`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015f14`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180015f14`

## string_xrefs

- `0x180015edc`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x180015ebc  push    rbx
0x180015ebe  push    rbp
0x180015ebf  push    rsi
0x180015ec0  push    rdi
0x180015ec1  push    r14
0x180015ec3  push    r15
0x180015ec5  sub     rsp, 28h
0x180015ec9  xor     r15d, r15d
0x180015ecc  mov     rbx, rdx
0x180015ecf  mov     rsi, rcx
0x180015ed2  test    rdx, rdx
0x180015ed5  jnz     short loc_180015EEE
0x180015ed7  mov     rcx, [rsp+58h]; this
0x180015edc  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015ee3  mov     edx, 0F89h; void *
0x180015ee8  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180015eee  mov     ecx, 7FFFFFFFh
0x180015ef3  mov     rax, rbx
0x180015ef6  cmp     [rax], r15w
0x180015efa  jz      short loc_180015F06
0x180015efc  add     rax, 2
0x180015f00  sub     rcx, 1
0x180015f04  jnz     short loc_180015EF6
0x180015f06  sub     rax, rbx
0x180015f09  sar     rax, 1
0x180015f0c  lea     r14, [rax+rax]
0x180015f10  lea     rcx, [r14+2]; cb
0x180015f14  call    cs:__imp_CoTaskMemAlloc
0x180015f1a  mov     rdi, rax
0x180015f1d  test    rax, rax
0x180015f20  jz      short loc_180015F39
0x180015f22  mov     r9, r14; SourceSize
0x180015f25  lea     rdx, [r14+2]; DestinationSize
0x180015f29  mov     r8, rbx; Source
0x180015f2c  mov     rcx, rax; Destination
0x180015f2f  call    memcpy_s
0x180015f34  mov     [r14+rdi], r15w
0x180015f39  mov     [rsi], rdi
0x180015f3c  mov     rax, rsi
0x180015f3f  add     rsp, 28h
0x180015f43  pop     r15
0x180015f45  pop     r14
0x180015f47  pop     rdi
0x180015f48  pop     rsi
0x180015f49  pop     rbp
0x180015f4a  pop     rbx
0x180015f4b  retn
```
