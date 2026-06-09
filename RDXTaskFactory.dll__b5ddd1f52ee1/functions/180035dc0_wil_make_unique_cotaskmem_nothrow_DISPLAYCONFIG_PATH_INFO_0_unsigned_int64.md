# wil::make_unique_cotaskmem_nothrow<DISPLAYCONFIG_PATH_INFO [0]>(unsigned __int64)

- ea: `0x180035dc0`
- end: `0x180035e4a`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@UDISPLAYCONFIG_PATH_INFO@@@wil@@YA?AV?$unique_ptr@$$BY0A@UDISPLAYCONFIG_PATH_INFO@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `138`
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
- `0x180035dc0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035df0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180035df0`

## string_xrefs

- `0x180035e38`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<DISPLAYCONFIG_PATH_INFO [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rsi
  char *v6; // rax
  char *v7; // rbx
  char *v8; // rsi
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x38E38E38E38E38ELL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = 72 * a2;
  v6 = (char *)CoTaskMemAlloc(72 * a2);
  *a1 = v6;
  v7 = v6;
  if ( v6 )
  {
    v8 = &v6[v5];
    if ( v6 != v8 )
    {
      do
      {
        memset_0(v7, 0, 0x48u);
        v7 += 72;
      }
      while ( v7 != v8 );
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180035dc0  mov     [rsp+arg_0], rbx
0x180035dc5  mov     [rsp+arg_8], rsi
0x180035dca  push    rdi
0x180035dcb  sub     rsp, 20h
0x180035dcf  mov     rax, 38E38E38E38E38Eh
0x180035dd9  mov     rdi, rcx
0x180035ddc  cmp     rdx, rax
0x180035ddf  ja      short loc_180035E33
0x180035de1  lea     rax, [rdx+rdx*8]
0x180035de5  lea     rsi, ds:0[rax*8]
0x180035ded  mov     rcx, rsi; cb
0x180035df0  call    cs:__imp_CoTaskMemAlloc
0x180035df6  mov     [rdi], rax
0x180035df9  mov     rbx, rax
0x180035dfc  test    rax, rax
0x180035dff  jz      short loc_180035E20
0x180035e01  add     rsi, rax
0x180035e04  cmp     rax, rsi
0x180035e07  jz      short loc_180035E20
0x180035e09  xor     edx, edx; Val
0x180035e0b  mov     rcx, rbx; void *
0x180035e0e  lea     r8d, [rdx+48h]; Size
0x180035e12  call    memset_0
0x180035e17  add     rbx, 48h ; 'H'
0x180035e1b  cmp     rbx, rsi
0x180035e1e  jnz     short loc_180035E09
0x180035e20  mov     rbx, [rsp+28h+arg_0]
0x180035e25  mov     rax, rdi
0x180035e28  mov     rsi, [rsp+28h+arg_8]
0x180035e2d  add     rsp, 20h
0x180035e31  pop     rdi
0x180035e32  retn
0x180035e33  mov     rcx, [rsp+28h]; this
0x180035e38  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180035e3f  mov     edx, 1802h; void *
0x180035e44  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
