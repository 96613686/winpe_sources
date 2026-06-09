# wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_exception_policy>::end(void)

- ea: `0x180017f44`
- end: `0x180017fb1`
- name: `?end@?$vector_range@U?$IVectorView@PEAVWindowingEnvironment@WindowManagement@UI@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ`
- size: `109`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180010f5c`
- `0x180016dc4`
- `0x180017318`

## callees

- `0x180017da0`
- `0x180017f44`
- `0x180022010`

## string_xrefs

- `0x180017f79`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::UI::WindowManagement::WindowingEnvironment *>,wil::err_exception_policy>::end(
        _QWORD *a1,
        __int64 a2)
{
  int v4; // eax
  __int64 result; // rax
  int v6; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  int v8; // [rsp+40h] [rbp+8h] BYREF

  v8 = 0;
  v4 = (*(__int64 (__fastcall **)(_QWORD, int *))(*(_QWORD *)*a1 + 56LL))(*a1, &v8);
  if ( v4 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v4,
      v6);
  *(_QWORD *)a2 = *a1;
  *(_DWORD *)(a2 + 8) = v8;
  result = a2;
  *(_QWORD *)(a2 + 16) = 0;
  return result;
}

```

## disassembly

```asm
0x180017f44  mov     [rsp+arg_8], rbx
0x180017f49  push    rdi
0x180017f4a  sub     rsp, 30h
0x180017f4e  mov     rdi, rcx
0x180017f51  mov     [rsp+38h+arg_0], 0
0x180017f59  mov     rcx, [rcx]
0x180017f5c  mov     rbx, rdx
0x180017f5f  lea     rdx, [rsp+38h+arg_0]
0x180017f64  mov     rax, [rcx]
0x180017f67  mov     rax, [rax+38h]
0x180017f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017f70  test    eax, eax
0x180017f72  jns     short loc_180017F8E
0x180017f74  mov     rcx, [rsp+38h]; this
0x180017f79  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180017f80  mov     r9d, eax; char *
0x180017f83  mov     edx, 1CBEh; void *
0x180017f88  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180017f8e  mov     rax, [rdi]
0x180017f91  mov     [rbx], rax
0x180017f94  mov     eax, [rsp+38h+arg_0]
0x180017f98  mov     [rbx+8], eax
0x180017f9b  mov     rax, rbx
0x180017f9e  mov     qword ptr [rbx+10h], 0
0x180017fa6  mov     rbx, [rsp+38h+arg_8]
0x180017fab  add     rsp, 30h
0x180017faf  pop     rdi
0x180017fb0  retn
```
