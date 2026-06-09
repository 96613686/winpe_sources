# wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::end(void)

- ea: `0x14000fdc0`
- end: `0x14000fe2d`
- name: `?end@?$vector_range@U?$IVectorView@PEAVDynamicAppUriHandler@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ`
- size: `109`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14000b114`
- `0x14000c3ec`

## callees

- `0x14000fbb0`
- `0x14000fdc0`
- `0x140012010`

## string_xrefs

- `0x14000fdf5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::DynamicAppUriHandler *>,wil::err_exception_policy>::end(
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
      (int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
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
0x14000fdc0  mov     [rsp+arg_8], rbx
0x14000fdc5  push    rdi
0x14000fdc6  sub     rsp, 30h
0x14000fdca  mov     rdi, rcx
0x14000fdcd  mov     [rsp+38h+arg_0], 0
0x14000fdd5  mov     rcx, [rcx]
0x14000fdd8  mov     rbx, rdx
0x14000fddb  lea     rdx, [rsp+38h+arg_0]
0x14000fde0  mov     rax, [rcx]
0x14000fde3  mov     rax, [rax+38h]
0x14000fde7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fdec  test    eax, eax
0x14000fdee  jns     short loc_14000FE0A
0x14000fdf0  mov     rcx, [rsp+38h]; this
0x14000fdf5  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000fdfc  mov     r9d, eax; char *
0x14000fdff  mov     edx, 1CBEh; void *
0x14000fe04  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000fe0a  mov     rax, [rdi]
0x14000fe0d  mov     [rbx], rax
0x14000fe10  mov     eax, [rsp+38h+arg_0]
0x14000fe14  mov     [rbx+8], eax
0x14000fe17  mov     rax, rbx
0x14000fe1a  mov     qword ptr [rbx+10h], 0
0x14000fe22  mov     rbx, [rsp+38h+arg_8]
0x14000fe27  add     rsp, 30h
0x14000fe2b  pop     rdi
0x14000fe2c  retn
```
