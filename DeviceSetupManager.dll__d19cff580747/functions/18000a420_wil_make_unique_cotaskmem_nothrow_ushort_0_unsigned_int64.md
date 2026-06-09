# wil::make_unique_cotaskmem_nothrow<ushort [0]>(unsigned __int64)

- ea: `0x18000a420`
- end: `0x18000a497`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a9e4`

## callees

- `0x18000a420`
- `0x180020aa4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a444`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a444`

## string_xrefs

- `0x18000a485`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<unsigned short [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rbx
  _WORD *v6; // rax
  _WORD *i; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v5 = a2;
  v6 = CoTaskMemAlloc(2 * a2);
  *a1 = v6;
  if ( v6 )
  {
    for ( i = &v6[v5]; v6 != i; ++v6 )
      *v6 = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18000a420  push    rdi
0x18000a422  sub     rsp, 20h
0x18000a426  mov     rax, 7FFFFFFFFFFFFFFFh
0x18000a430  mov     rdi, rcx
0x18000a433  cmp     rdx, rax
0x18000a436  ja      short loc_18000A480
0x18000a438  mov     [rsp+28h+arg_0], rbx
0x18000a43d  lea     rbx, [rdx+rdx]
0x18000a441  mov     rcx, rbx; cb
0x18000a444  call    cs:__imp_CoTaskMemAlloc
0x18000a44a  mov     [rdi], rax
0x18000a44d  test    rax, rax
0x18000a450  jnz     short loc_18000A460
0x18000a452  mov     rbx, [rsp+28h+arg_0]
0x18000a457  mov     rax, rdi
0x18000a45a  add     rsp, 20h
0x18000a45e  pop     rdi
0x18000a45f  retn
0x18000a460  lea     rcx, [rbx+rax]
0x18000a464  cmp     rax, rcx
0x18000a467  jz      short loc_18000A452
0x18000a469  nop     dword ptr [rax+00000000h]
0x18000a470  xor     edx, edx
0x18000a472  mov     [rax], dx
0x18000a475  add     rax, 2
0x18000a479  cmp     rax, rcx
0x18000a47c  jnz     short loc_18000A470
0x18000a47e  jmp     short loc_18000A452
0x18000a480  mov     rcx, [rsp+28h]; this
0x18000a485  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000a48c  mov     edx, 1802h; void *
0x18000a491  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
