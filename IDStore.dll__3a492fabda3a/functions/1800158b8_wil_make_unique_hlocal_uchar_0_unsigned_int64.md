# wil::make_unique_hlocal<uchar [0]>(unsigned __int64)

- ea: `0x1800158b8`
- end: `0x1800158fa`
- name: `??$make_unique_hlocal@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z`
- size: `66`
- prototype: `_QWORD *__fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x18000edb4`

## callees

- `0x18000f018`
- `0x1800158b8`
- `0x180015900`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_hlocal<unsigned char [0]>(_QWORD *a1)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  wil::make_unique_hlocal_nothrow<unsigned char [0]>(a1);
  if ( !*a1 )
    wil::details::in1diag3::_Throw_NullAlloc(retaddr, (void *)0x1321, v2, v3);
  return a1;
}

```

## disassembly

```asm
0x1800158b8  mov     [rsp+arg_0], rcx
0x1800158bd  push    rbx
0x1800158be  sub     rsp, 30h
0x1800158c2  mov     rbx, rcx
0x1800158c5  mov     [rsp+38h+var_18], 0
0x1800158cd  call    ??$make_unique_hlocal_nothrow@$$BY0A@E@wil@@YA?AV?$unique_ptr@$$BY0A@EU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@_K@Z; wil::make_unique_hlocal_nothrow<uchar [0]>(unsigned __int64)
0x1800158d2  mov     [rsp+38h+var_18], 1
0x1800158da  mov     rcx, [rsp+38h]; this
0x1800158df  cmp     qword ptr [rbx], 0
0x1800158e3  jnz     short loc_1800158F0
0x1800158e5  mov     edx, 1321h; void *
0x1800158ea  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800158f0  mov     rax, rbx
0x1800158f3  add     rsp, 30h
0x1800158f7  pop     rbx
0x1800158f8  retn
```
