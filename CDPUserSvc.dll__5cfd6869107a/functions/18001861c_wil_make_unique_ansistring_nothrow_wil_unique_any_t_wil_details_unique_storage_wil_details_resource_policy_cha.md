# wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(char const *,unsigned __int64)

- ea: `0x18001861c`
- end: `0x18001868f`
- name: `??$make_unique_ansistring_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEADP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEADPEAD$0A@$$T@details@wil@@@details@wil@@@0@PEBD_K@Z`
- size: `115`
- prototype: `_QWORD *__fastcall(_QWORD *, _BYTE *, __int64, const char *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800185d8`

## callees

- `0x180015f14`
- `0x18001861c`
- `0x180044a50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001865a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001865a`

## string_xrefs

- `0x180018637`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_ansistring_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<char *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,char *,char *,0,std::nullptr_t>>>>(
        _QWORD *a1,
        _BYTE *a2,
        __int64 a3,
        const char *a4)
{
  rsize_t v6; // rbx
  _BYTE *v7; // rax
  _BYTE *v8; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !a2 )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0xFBD,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v6 = -1;
  do
    ++v6;
  while ( a2[v6] );
  v7 = CoTaskMemAlloc(v6 + 1);
  v8 = v7;
  if ( v7 )
  {
    memcpy_s_0(v7, v6 + 1, a2, v6);
    v8[v6] = 0;
  }
  *a1 = v8;
  return a1;
}

```

## disassembly

```asm
0x18001861c  push    rbx
0x18001861e  push    rbp
0x18001861f  push    rsi
0x180018620  push    rdi
0x180018621  push    r14
0x180018623  sub     rsp, 20h
0x180018627  mov     rbp, rdx
0x18001862a  mov     rsi, rcx
0x18001862d  test    rdx, rdx
0x180018630  jnz     short loc_180018649
0x180018632  mov     rcx, [rsp+48h]; this
0x180018637  lea     r8, aOnecoreInterna_6; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001863e  mov     edx, 0FBDh; void *
0x180018643  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180018649  or      rbx, 0FFFFFFFFFFFFFFFFh
0x18001864d  inc     rbx
0x180018650  cmp     byte ptr [rbx+rdx], 0
0x180018654  jnz     short loc_18001864D
0x180018656  lea     rcx, [rbx+1]; cb
0x18001865a  call    cs:__imp_CoTaskMemAlloc
0x180018660  mov     rdi, rax
0x180018663  test    rax, rax
0x180018666  jz      short loc_18001867E
0x180018668  mov     r9, rbx; SourceSize
0x18001866b  lea     rdx, [rbx+1]; DestinationSize
0x18001866f  mov     r8, rbp; Source
0x180018672  mov     rcx, rax; Destination
0x180018675  call    memcpy_s_0
0x18001867a  mov     byte ptr [rbx+rdi], 0
0x18001867e  mov     [rsi], rdi
0x180018681  mov     rax, rsi
0x180018684  add     rsp, 20h
0x180018688  pop     r14
0x18001868a  pop     rdi
0x18001868b  pop     rsi
0x18001868c  pop     rbp
0x18001868d  pop     rbx
0x18001868e  retn
```
