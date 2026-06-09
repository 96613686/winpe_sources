# wil::make_unique_cotaskmem_nothrow<CDPComPolicySource [0]>(unsigned __int64)

- ea: `0x180012fac`
- end: `0x180013019`
- name: `??$make_unique_cotaskmem_nothrow@$$BY0A@W4CDPComPolicySource@@@wil@@YA?AV?$unique_ptr@$$BY0A@W4CDPComPolicySource@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@_K@Z`
- size: `109`
- prototype: `_QWORD *__fastcall(_QWORD *, unsigned __int64, __int64, const char *)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180012b90`

## callees

- `0x180012fac`
- `0x180044a50`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012fd3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180012fd3`

## string_xrefs

- `0x180013007`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
_QWORD *__fastcall wil::make_unique_cotaskmem_nothrow<enum CDPComPolicySource [0]>(
        _QWORD *a1,
        unsigned __int64 a2,
        __int64 a3,
        const char *a4)
{
  __int64 v5; // rdi
  _DWORD *v6; // rax
  _DWORD *v7; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( a2 > 0x3FFFFFFFFFFFFFFFLL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v5 = a2;
  v6 = CoTaskMemAlloc(4 * a2);
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
0x180012fac  mov     [rsp+arg_0], rbx
0x180012fb1  push    rdi
0x180012fb2  sub     rsp, 20h
0x180012fb6  mov     rax, 3FFFFFFFFFFFFFFFh
0x180012fc0  mov     rbx, rcx
0x180012fc3  cmp     rdx, rax
0x180012fc6  ja      short loc_180013002
0x180012fc8  lea     rdi, ds:0[rdx*4]
0x180012fd0  mov     rcx, rdi; cb
0x180012fd3  call    cs:__imp_CoTaskMemAlloc
0x180012fd9  mov     [rbx], rax
0x180012fdc  test    rax, rax
0x180012fdf  jz      short loc_180012FF4
0x180012fe1  lea     rcx, [rdi+rax]
0x180012fe5  jmp     short loc_180012FEF
0x180012fe7  xor     edx, edx
0x180012fe9  mov     [rax], edx
0x180012feb  add     rax, 4
0x180012fef  cmp     rax, rcx
0x180012ff2  jnz     short loc_180012FE7
0x180012ff4  mov     rax, rbx
0x180012ff7  mov     rbx, [rsp+28h+arg_0]
0x180012ffc  add     rsp, 20h
0x180013000  pop     rdi
0x180013001  retn
0x180013002  mov     rcx, [rsp+28h]; this
0x180013007  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001300e  mov     edx, 1802h; void *
0x180013013  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
```
