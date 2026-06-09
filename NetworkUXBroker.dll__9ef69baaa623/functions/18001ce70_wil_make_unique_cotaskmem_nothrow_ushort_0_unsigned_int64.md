# wil::make_unique_cotaskmem_nothrow<ushort [0]>(unsigned __int64)

- ea: `0x18001ce70`
- end: `0x18001ceda`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `106`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001ce20`

## callees

- `0x18001ce70`
- `0x18001fcb4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ceaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18001ceaa`

## string_xrefs

- `0x18001ce91`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<unsigned short [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  _WORD *v6; // rax
  _WORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x7FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = a2;
  v6 = CoTaskMemAlloc(2 * a2);
  *a1 = v6;
  if ( v6 )
  {
    v7 = &v6[v5];
    while ( v6 != v7 )
      *v6++ = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x18001ce70  mov     [rsp+arg_0], rbx
0x18001ce75  push    rdi
0x18001ce76  sub     rsp, 20h
0x18001ce7a  mov     rax, 7FFFFFFFFFFFFFFFh
0x18001ce84  mov     rbx, rcx
0x18001ce87  cmp     rdx, rax
0x18001ce8a  jbe     short loc_18001CEA3
0x18001ce8c  mov     rcx, [rsp+28h]; this
0x18001ce91  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001ce98  mov     edx, 1802h; void *
0x18001ce9d  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18001cea3  lea     rdi, [rdx+rdx]
0x18001cea7  mov     rcx, rdi; cb
0x18001ceaa  call    cs:__imp_CoTaskMemAlloc
0x18001ceb0  mov     [rbx], rax
0x18001ceb3  test    rax, rax
0x18001ceb6  jz      short loc_18001CECC
0x18001ceb8  lea     rcx, [rdi+rax]
0x18001cebc  jmp     short loc_18001CEC7
0x18001cebe  xor     edx, edx
0x18001cec0  mov     [rax], dx
0x18001cec3  add     rax, 2
0x18001cec7  cmp     rax, rcx
0x18001ceca  jnz     short loc_18001CEBE
0x18001cecc  mov     rax, rbx
0x18001cecf  mov     rbx, [rsp+28h+arg_0]
0x18001ced4  add     rsp, 20h
0x18001ced8  pop     rdi
0x18001ced9  retn
```
