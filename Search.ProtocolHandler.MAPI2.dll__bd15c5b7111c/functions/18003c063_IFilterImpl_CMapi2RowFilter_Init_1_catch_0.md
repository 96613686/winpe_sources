# _IFilterImpl_CMapi2RowFilter_::Init_::_1_::catch$0

- ea: `0x18003c063`
- end: `0x18003c0b5`
- name: `_IFilterImpl_CMapi2RowFilter_::Init_::_1_::catch$0`
- size: `82`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800134d8`
- `0x180015024`

## string_xrefs

- `0x18003c074`: `onecoreuap\base\appmodel\Search\common\include\prothndlrhelp.hxx`
- `0x18003c08b`: `[UtilCommon] IFilterImpl::Init: exception! 0x%08x`
- `0x18003c097`: `"onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx"`

## pseudocode

```c
void __fastcall __noreturn IFilterImpl_CMapi2RowFilter_::Init_::_1_::catch_0(__int64 a1, __int64 a2)
{
  indexer::result::details::result_from_caught_exception<1>(
    *(_QWORD *)(a2 + 40),
    248,
    "onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx");
}

```

## disassembly

```asm
0x18003c063  mov     [rsp+arg_8], rdx
0x18003c068  push    rbp
0x18003c069  sub     rsp, 20h
0x18003c06d  mov     rbp, rdx
0x18003c070  mov     rcx, [rbp+28h]
0x18003c074  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\Search\\com"...
0x18003c07b  mov     edx, 0F8h
0x18003c080  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x18003c085  mov     [rbp+40h], eax
0x18003c088  mov     r9d, eax; wchar_t *
0x18003c08b  lea     r8, aUtilcommonIfil_1; "[UtilCommon] IFilterImpl::Init: excepti"...
0x18003c092  mov     edx, 0F9h; wchar_t *
0x18003c097  lea     rcx, aOnecoreuapBase_12; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x18003c09e  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x18003c0a3  nop
0x18003c0a4  mov     rax, 0
0x18003c0ae  add     rsp, 20h
0x18003c0b2  pop     rbp
0x18003c0b3  retn
```
