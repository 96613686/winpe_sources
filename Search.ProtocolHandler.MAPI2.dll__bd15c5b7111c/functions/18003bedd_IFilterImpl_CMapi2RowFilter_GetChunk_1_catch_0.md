# _IFilterImpl_CMapi2RowFilter_::GetChunk_::_1_::catch$0

- ea: `0x18003bedd`
- end: `0x18003bf2f`
- name: `_IFilterImpl_CMapi2RowFilter_::GetChunk_::_1_::catch$0`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800134d8`
- `0x180015024`

## string_xrefs

- `0x18003beee`: `onecoreuap\base\appmodel\Search\common\include\prothndlrhelp.hxx`
- `0x18003bf11`: `"onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx"`
- `0x18003bf05`: `[UtilCommon] IFilterImpl::GetChunk: exception! 0x%08x`

## pseudocode

```c
void __fastcall __noreturn IFilterImpl_CMapi2RowFilter_::GetChunk_::_1_::catch_0(__int64 a1, __int64 a2)
{
  indexer::result::details::result_from_caught_exception<1>(
    *(_QWORD *)(a2 + 40),
    282,
    "onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx");
}

```

## disassembly

```asm
0x18003bedd  mov     [rsp+arg_8], rdx
0x18003bee2  push    rbp
0x18003bee3  sub     rsp, 20h
0x18003bee7  mov     rbp, rdx
0x18003beea  mov     rcx, [rbp+28h]
0x18003beee  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003bef5  mov     edx, 11Ah
0x18003befa  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x18003beff  mov     [rbp+30h], eax
0x18003bf02  mov     r9d, eax; wchar_t *
0x18003bf05  lea     r8, aUtilcommonIfil_0; "[UtilCommon] IFilterImpl::GetChunk: exc"...
0x18003bf0c  mov     edx, 11Bh; wchar_t *
0x18003bf11  lea     rcx, aOnecoreuapBase_12; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x18003bf18  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18003bf1d  nop
0x18003bf1e  mov     rax, 0
0x18003bf28  add     rsp, 20h
0x18003bf2c  pop     rbp
0x18003bf2d  retn
```
