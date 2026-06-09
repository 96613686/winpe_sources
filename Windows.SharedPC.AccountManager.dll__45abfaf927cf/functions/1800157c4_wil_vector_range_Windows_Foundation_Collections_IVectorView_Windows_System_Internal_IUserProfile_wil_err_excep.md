# wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::vector_iterator::operator*(void)

- ea: `0x1800157c4`
- end: `0x180015821`
- name: `??Dvector_iterator@?$vector_range@U?$IVectorView@PEAUIUserProfile@Internal@System@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UIUserProfile@Internal@System@Windows@@@WRL@Microsoft@@XZ`
- size: `93`
- prototype: `unsigned int *__fastcall(unsigned int *)`
- caller_count: `4`
- callee_count: `4`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180014f80`
- `0x1800170ec`
- `0x180022f60`
- `0x1800230a8`

## callees

- `0x180005120`
- `0x18000ccd4`
- `0x1800157c4`
- `0x180026010`

## string_xrefs

- `0x180015800`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
unsigned int *__fastcall wil::vector_range<Windows::Foundation::Collections::IVectorView<Windows::System::Internal::IUserProfile *>,wil::err_exception_policy>::vector_iterator::operator*(
        unsigned int *a1)
{
  __int64 v1; // rdi
  unsigned int *v2; // rbp
  __int64 (__fastcall *v4)(__int64, _QWORD, unsigned int *); // rbx
  int v5; // eax
  int v7; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  v1 = *(_QWORD *)a1;
  v2 = a1 + 4;
  v4 = *(__int64 (__fastcall **)(__int64, _QWORD, unsigned int *))(**(_QWORD **)a1 + 48LL);
  Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(a1 + 4);
  v5 = v4(v1, a1[2], v2);
  if ( v5 < 0 )
    wil::details::in1diag3::_Throw_Hr(
      retaddr,
      (void *)0x1CBE,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\result_macros.h",
      (const char *)(unsigned int)v5,
      v7);
  return v2;
}

```

## disassembly

```asm
0x1800157c4  push    rbx
0x1800157c6  push    rbp
0x1800157c7  push    rsi
0x1800157c8  push    rdi
0x1800157c9  sub     rsp, 28h
0x1800157cd  mov     rdi, [rcx]
0x1800157d0  lea     rbp, [rcx+10h]
0x1800157d4  mov     rsi, rcx
0x1800157d7  mov     rcx, rbp
0x1800157da  mov     rax, [rdi]
0x1800157dd  mov     rbx, [rax+30h]
0x1800157e1  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800157e6  mov     edx, [rsi+8]
0x1800157e9  mov     r8, rbp
0x1800157ec  mov     rcx, rdi
0x1800157ef  mov     rax, rbx
0x1800157f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157f7  test    eax, eax
0x1800157f9  jns     short loc_180015815
0x1800157fb  mov     rcx, [rsp+48h]; this
0x180015800  lea     r8, aOnecoreInterna_3; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180015807  mov     r9d, eax; char *
0x18001580a  mov     edx, 1CBEh; void *
0x18001580f  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x180015815  mov     rax, rbp
0x180015818  add     rsp, 28h
0x18001581c  pop     rdi
0x18001581d  pop     rsi
0x18001581e  pop     rbp
0x18001581f  pop     rbx
0x180015820  retn
```
