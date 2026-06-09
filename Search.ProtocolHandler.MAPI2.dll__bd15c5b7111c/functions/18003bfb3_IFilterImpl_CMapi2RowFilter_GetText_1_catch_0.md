# _IFilterImpl_CMapi2RowFilter_::GetText_::_1_::catch$0

- ea: `0x18003bfb3`
- end: `0x18003c005`
- name: `_IFilterImpl_CMapi2RowFilter_::GetText_::_1_::catch$0`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800134d8`
- `0x180015024`

## string_xrefs

- `0x18003bfc4`: `onecoreuap\base\appmodel\Search\common\include\prothndlrhelp.hxx`
- `0x18003bfe7`: `"onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx"`
- `0x18003bfdb`: `[UtilCommon] IFilterImpl::GetText: exception! 0x%08x`

## pseudocode

```c
void __fastcall __noreturn IFilterImpl_CMapi2RowFilter_::GetText_::_1_::catch_0(__int64 a1, __int64 a2)
{
  indexer::result::details::result_from_caught_exception<1>(
    *(_QWORD *)(a2 + 40),
    305,
    "onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx");
}

```

## disassembly

```asm
0x18003bfb3  mov     [rsp+arg_8], rdx
0x18003bfb8  push    rbp
0x18003bfb9  sub     rsp, 20h
0x18003bfbd  mov     rbp, rdx
0x18003bfc0  mov     rcx, [rbp+28h]
0x18003bfc4  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003bfcb  mov     edx, 131h
0x18003bfd0  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x18003bfd5  mov     [rbp+30h], eax
0x18003bfd8  mov     r9d, eax; wchar_t *
0x18003bfdb  lea     r8, aUtilcommonIfil; "[UtilCommon] IFilterImpl::GetText: exce"...
0x18003bfe2  mov     edx, 132h; wchar_t *
0x18003bfe7  lea     rcx, aOnecoreuapBase_12; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x18003bfee  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18003bff3  nop
0x18003bff4  mov     rax, 0
0x18003bffe  add     rsp, 20h
0x18003c002  pop     rbp
0x18003c003  retn
```
