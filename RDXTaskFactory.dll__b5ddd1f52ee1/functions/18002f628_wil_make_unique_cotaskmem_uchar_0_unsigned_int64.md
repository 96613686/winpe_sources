# wil::make_unique_cotaskmem<uchar [0]>(unsigned __int64)

- ea: `0x18002f628`
- end: `0x18002f69b`
- name: `??$make_unique_cotaskmem@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `115`
- prototype: `_QWORD *__fastcall(_QWORD *, SIZE_T)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180030a64`

## callees

- `0x18001096c`
- `0x18002f628`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f648`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18002f648`

## string_xrefs

- `0x18002f689`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall wil::make_unique_cotaskmem<unsigned char [0]>(_QWORD *a1, SIZE_T a2)
{
  _BYTE *v4; // rax
  const char *v5; // r9
  _BYTE *v6; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  v4 = CoTaskMemAlloc(a2);
  *a1 = v4;
  if ( v4 )
  {
    v6 = &v4[a2];
    while ( v4 != v6 )
      *v4++ = 0;
  }
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(
      retaddr,
      (void *)0x1854,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      v5);
  return a1;
}

```

## disassembly

```asm
0x18002f628  mov     [rsp+arg_8], rbx
0x18002f62d  mov     [rsp+arg_0], rcx
0x18002f632  push    rdi
0x18002f633  sub     rsp, 30h
0x18002f637  mov     rdi, rdx
0x18002f63a  mov     rbx, rcx
0x18002f63d  mov     [rsp+38h+var_18], 0
0x18002f645  mov     rcx, rdx; cb
0x18002f648  call    cs:__imp_CoTaskMemAlloc
0x18002f64e  mov     [rbx], rax
0x18002f651  test    rax, rax
0x18002f654  jz      short loc_18002F668
0x18002f656  lea     rcx, [rax+rdi]
0x18002f65a  jmp     short loc_18002F663
0x18002f65c  xor     edx, edx
0x18002f65e  mov     [rax], dl
0x18002f660  inc     rax
0x18002f663  cmp     rax, rcx
0x18002f666  jnz     short loc_18002F65C
0x18002f668  mov     [rsp+38h+var_18], 1
0x18002f670  mov     rcx, [rsp+38h]; this
0x18002f675  cmp     qword ptr [rbx], 0
0x18002f679  jz      short loc_18002F689
0x18002f67b  mov     rax, rbx
0x18002f67e  mov     rbx, [rsp+38h+arg_8]
0x18002f683  add     rsp, 30h
0x18002f687  pop     rdi
0x18002f688  retn
0x18002f689  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18002f690  mov     edx, 1854h; void *
0x18002f695  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
```
