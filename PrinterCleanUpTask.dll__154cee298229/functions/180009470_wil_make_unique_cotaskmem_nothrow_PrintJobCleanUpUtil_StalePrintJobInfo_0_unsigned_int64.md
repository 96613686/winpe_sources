# wil::make_unique_cotaskmem_nothrow<PrintJobCleanUpUtil::StalePrintJobInfo [0]>(unsigned __int64)

- ea: `0x180009470`
- end: `0x1800094e7`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@UStalePrintJobInfo@PrintJobCleanUpUtil@@@wil@@YA?AV?$unique_ptr@$$BY0A@UStalePrintJobInfo@PrintJobCleanUpUtil@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `119`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180009428`

## callees

- `0x180009470`
- `0x18000f094`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800094ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800094ad`

## string_xrefs

- `0x180009494`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<PrintJobCleanUpUtil::StalePrintJobInfo [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rbx
  _QWORD *v6; // rax
  _QWORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0xFFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
      a4);
  v5 = 2 * a2;
  v6 = CoTaskMemAlloc(16 * a2);
  *a1 = v6;
  if ( v6 )
  {
    v7 = &v6[v5];
    while ( v6 != v7 )
    {
      *v6 = 0;
      v6[1] = 0;
      v6 += 2;
    }
  }
  return a1;
}

```

## disassembly

```asm
0x180009470  mov     [rsp+arg_0], rbx
0x180009475  push    rdi
0x180009476  sub     rsp, 20h
0x18000947a  mov     rax, 0FFFFFFFFFFFFFFFh
0x180009484  mov     rbx, rdx
0x180009487  mov     rdi, rcx
0x18000948a  cmp     rdx, rax
0x18000948d  jbe     short loc_1800094A6
0x18000948f  mov     rcx, [rsp+28h]; this
0x180009494  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000949b  mov     edx, 1802h; void *
0x1800094a0  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x1800094a6  shl     rbx, 4
0x1800094aa  mov     rcx, rbx; cb
0x1800094ad  call    cs:__imp_CoTaskMemAlloc
0x1800094b3  mov     [rdi], rax
0x1800094b6  test    rax, rax
0x1800094b9  jz      short loc_1800094D9
0x1800094bb  lea     rcx, [rbx+rax]
0x1800094bf  jmp     short loc_1800094D4
0x1800094c1  mov     qword ptr [rax], 0
0x1800094c8  mov     qword ptr [rax+8], 0
0x1800094d0  add     rax, 10h
0x1800094d4  cmp     rax, rcx
0x1800094d7  jnz     short loc_1800094C1
0x1800094d9  mov     rbx, [rsp+28h+arg_0]
0x1800094de  mov     rax, rdi
0x1800094e1  add     rsp, 20h
0x1800094e5  pop     rdi
0x1800094e6  retn
```
