# wil::make_unique_cotaskmem_nothrow<DISPLAYCONFIG_MODE_INFO [0]>(unsigned __int64)

- ea: `0x180035d34`
- end: `0x180035db9`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@UDISPLAYCONFIG_MODE_INFO@@@wil@@YA?AV?$unique_ptr@$$BY0A@UDISPLAYCONFIG_MODE_INFO@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `133`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003a290`
- `0x180040c14`

## callees

- `0x180003e00`
- `0x18000c0f8`
- `0x180035d34`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035d5f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035d5f`

## string_xrefs

- `0x180035da7`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<DISPLAYCONFIG_MODE_INFO [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  unsigned __int64 v5; // rdi
  char *v6; // rax
  char *v7; // rbx
  char *v8; // rdi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x3FFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = a2 << 6;
  v6 = (char *)CoTaskMemAlloc(a2 << 6);
  *a1 = v6;
  v7 = v6;
  if ( v6 )
  {
    v8 = &v6[v5];
    if ( v6 != v8 )
    {
      do
      {
        memset_0(v7, 0, 0x40u);
        v7 += 64;
      }
      while ( v7 != v8 );
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180035d34  mov     [rsp+arg_0], rbx
0x180035d39  mov     [rsp+arg_8], rsi
0x180035d3e  push    rdi
0x180035d3f  sub     rsp, 20h
0x180035d43  mov     rax, 3FFFFFFFFFFFFFFh
0x180035d4d  mov     rdi, rdx
0x180035d50  mov     rsi, rcx
0x180035d53  cmp     rdx, rax
0x180035d56  ja      short loc_180035DA2
0x180035d58  shl     rdi, 6
0x180035d5c  mov     rcx, rdi; cb
0x180035d5f  call    cs:__imp_CoTaskMemAlloc
0x180035d65  mov     [rsi], rax
0x180035d68  mov     rbx, rax
0x180035d6b  test    rax, rax
0x180035d6e  jz      short loc_180035D8F
0x180035d70  add     rdi, rax
0x180035d73  cmp     rax, rdi
0x180035d76  jz      short loc_180035D8F
0x180035d78  xor     edx, edx; Val
0x180035d7a  mov     rcx, rbx; void *
0x180035d7d  lea     r8d, [rdx+40h]; Size
0x180035d81  call    memset_0
0x180035d86  add     rbx, 40h ; '@'
0x180035d8a  cmp     rbx, rdi
0x180035d8d  jnz     short loc_180035D78
0x180035d8f  mov     rbx, [rsp+28h+arg_0]
0x180035d94  mov     rax, rsi
0x180035d97  mov     rsi, [rsp+28h+arg_8]
0x180035d9c  add     rsp, 20h
0x180035da0  pop     rdi
0x180035da1  retn
0x180035da2  mov     rcx, [rsp+28h]; this
0x180035da7  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035dae  mov     edx, 1802h; void *
0x180035db3  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
