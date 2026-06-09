# wil::make_unique_cotaskmem_nothrow<ushort [0]>(unsigned __int64)

- ea: `0x18004620c`
- end: `0x180046276`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `106`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18001a134`
- `0x18002b724`

## callees

- `0x180036994`
- `0x18004620c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046246`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180046246`

## string_xrefs

- `0x18004622d`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
0x18004620c  mov     [rsp+arg_0], rbx
0x180046211  push    rdi
0x180046212  sub     rsp, 20h
0x180046216  mov     rax, 7FFFFFFFFFFFFFFFh
0x180046220  mov     rbx, rcx
0x180046223  cmp     rdx, rax
0x180046226  jbe     short loc_18004623F
0x180046228  mov     rcx, [rsp+28h]; this
0x18004622d  lea     r8, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180046234  mov     edx, 1802h; void *
0x180046239  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18004623f  lea     rdi, [rdx+rdx]
0x180046243  mov     rcx, rdi; cb
0x180046246  call    cs:__imp_CoTaskMemAlloc
0x18004624c  mov     [rbx], rax
0x18004624f  test    rax, rax
0x180046252  jz      short loc_180046268
0x180046254  lea     rcx, [rdi+rax]
0x180046258  jmp     short loc_180046263
0x18004625a  xor     edx, edx
0x18004625c  mov     [rax], dx
0x18004625f  add     rax, 2
0x180046263  cmp     rax, rcx
0x180046266  jnz     short loc_18004625A
0x180046268  mov     rax, rbx
0x18004626b  mov     rbx, [rsp+28h+arg_0]
0x180046270  add     rsp, 20h
0x180046274  pop     rdi
0x180046275  retn
```
