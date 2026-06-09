# _IFilterImpl_CMapi2RowFilter_::GetValue_::_1_::catch$0

- ea: `0x18003c00b`
- end: `0x18003c05d`
- name: `_IFilterImpl_CMapi2RowFilter_::GetValue_::_1_::catch$0`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800134d8`
- `0x180015024`

## string_xrefs

- `0x18003c01c`: `onecoreuap\base\appmodel\Search\common\include\prothndlrhelp.hxx`
- `0x18003c03f`: `"onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx"`
- `0x18003c033`: `[UtilCommon] IFilterImpl::GetValue: exception! 0x%08x`

## pseudocode

```c
void __fastcall __noreturn IFilterImpl_CMapi2RowFilter_::GetValue_::_1_::catch_0(__int64 a1, __int64 a2)
{
  indexer::result::details::result_from_caught_exception<1>(
    *(_QWORD *)(a2 + 40),
    327,
    "onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx");
}

```

## disassembly

```asm
0x18003c00b  mov     [rsp+arg_8], rdx
0x18003c010  push    rbp
0x18003c011  sub     rsp, 20h
0x18003c015  mov     rbp, rdx
0x18003c018  mov     rcx, [rbp+28h]
0x18003c01c  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003c023  mov     edx, 147h
0x18003c028  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x18003c02d  mov     [rbp+30h], eax
0x18003c030  mov     r9d, eax; wchar_t *
0x18003c033  lea     r8, aUtilcommonIfil_3; "[UtilCommon] IFilterImpl::GetValue: exc"...
0x18003c03a  mov     edx, 148h; wchar_t *
0x18003c03f  lea     rcx, aOnecoreuapBase_12; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x18003c046  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18003c04b  nop
0x18003c04c  mov     rax, 0
0x18003c056  add     rsp, 20h
0x18003c05a  pop     rbp
0x18003c05b  retn
```
