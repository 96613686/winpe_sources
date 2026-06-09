# wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_exception_policy>::vector_iterator::operator*(void)

- ea: `0x18000e2ac`
- end: `0x18000e309`
- name: `??Dvector_iterator@?$vector_range@U?$IVector@PEAVCapturableItem@Capture@PlatformExtensions@Internal@Windows@@@Collections@Foundation@Windows@@Uerr_exception_policy@wil@@@wil@@QEAAAEBV?$ComPtr@UICapturableItem@Capture@PlatformExtensions@Internal@Windows@@@WRL@Microsoft@@XZ`
- size: `93`
- prototype: `unsigned int *__fastcall(unsigned int *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x180016dc4`
- `0x180017318`

## callees

- `0x180007630`
- `0x18000e2ac`
- `0x180017da0`
- `0x180022010`

## string_xrefs

- `0x18000e2e8`: `onecore\internal\sdk\inc\wil\opensource\wil\result_macros.h`

## pseudocode

```c
unsigned int *__fastcall wil::vector_range<Windows::Foundation::Collections::IVector<Windows::Internal::PlatformExtensions::Capture::CapturableItem *>,wil::err_exception_policy>::vector_iterator::operator*(
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
0x18000e2ac  push    rbx
0x18000e2ae  push    rbp
0x18000e2af  push    rsi
0x18000e2b0  push    rdi
0x18000e2b1  sub     rsp, 28h
0x18000e2b5  mov     rdi, [rcx]
0x18000e2b8  lea     rbp, [rcx+10h]
0x18000e2bc  mov     rsi, rcx
0x18000e2bf  mov     rcx, rbp
0x18000e2c2  mov     rax, [rdi]
0x18000e2c5  mov     rbx, [rax+30h]
0x18000e2c9  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18000e2ce  mov     edx, [rsi+8]
0x18000e2d1  mov     r8, rbp
0x18000e2d4  mov     rcx, rdi
0x18000e2d7  mov     rax, rbx
0x18000e2da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2df  test    eax, eax
0x18000e2e1  jns     short loc_18000E2FD
0x18000e2e3  mov     rcx, [rsp+48h]; this
0x18000e2e8  lea     r8, aOnecoreInterna_4; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000e2ef  mov     r9d, eax; char *
0x18000e2f2  mov     edx, 1CBEh; void *
0x18000e2f7  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18000e2fd  mov     rax, rbp
0x18000e300  add     rsp, 28h
0x18000e304  pop     rdi
0x18000e305  pop     rsi
0x18000e306  pop     rbp
0x18000e307  pop     rbx
0x18000e308  retn
```
