# wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::CustomInstallWork *>,wil::err_exception_policy>::end(void)

- ea: `0x14000b8c0`
- end: `0x14000b92d`
- name: `?end@?$vector_range@U?$IVectorView@PEAVCustomInstallWork@StateRepository@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAA?AVvector_iterator@12@XZ`
- size: `109`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, installer_update`

## callers

- `0x140009cd8`

## callees

- `0x140007d78`
- `0x14000b8c0`
- `0x14000f010`

## string_xrefs

- `0x14000b8f5`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
__int64 __fastcall wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::Internal::StateRepository::CustomInstallWork *>,wil::err_exception_policy>::end(
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
0x14000b8c0  mov     [rsp+arg_8], rbx
0x14000b8c5  push    rdi
0x14000b8c6  sub     rsp, 30h
0x14000b8ca  mov     rdi, rcx
0x14000b8cd  mov     [rsp+38h+arg_0], 0
0x14000b8d5  mov     rcx, [rcx]
0x14000b8d8  mov     rbx, rdx
0x14000b8db  lea     rdx, [rsp+38h+arg_0]
0x14000b8e0  mov     rax, [rcx]
0x14000b8e3  mov     rax, [rax+38h]
0x14000b8e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b8ec  test    eax, eax
0x14000b8ee  jns     short loc_14000B90A
0x14000b8f0  mov     rcx, [rsp+38h]; this
0x14000b8f5  lea     r8, aOnecoreInterna_1; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x14000b8fc  mov     r9d, eax; char *
0x14000b8ff  mov     edx, 1CBEh; void *
0x14000b904  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000b90a  mov     rax, [rdi]
0x14000b90d  mov     [rbx], rax
0x14000b910  mov     eax, [rsp+38h+arg_0]
0x14000b914  mov     [rbx+8], eax
0x14000b917  mov     rax, rbx
0x14000b91a  mov     qword ptr [rbx+10h], 0
0x14000b922  mov     rbx, [rsp+38h+arg_8]
0x14000b927  add     rsp, 30h
0x14000b92b  pop     rdi
0x14000b92c  retn
```
