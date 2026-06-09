# IFilterImpl<CMapi2DirFilter>::BindRegion(tagFILTERREGION,_GUID const &,void * *)

- ea: `0x1800149f0`
- end: `0x180014a1c`
- name: `?BindRegion@?$IFilterImpl@VCMapi2DirFilter@@@@UEAAJUtagFILTERREGION@@AEBU_GUID@@PEAPEAX@Z`
- size: `44`
- prototype: `__int64()`
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x180017468`

## string_xrefs

- `0x180014a06`: `"onecoreuap\\base\\appmodel\\Search\\common\\include\\prothndlrhelp.hxx"`
- `0x1800149fa`: `[UtilCommon] IFilter::BindRegion: not implemented 0x%08x`

## pseudocode

```c
__int64 IFilterImpl<CMapi2DirFilter>::BindRegion()
{
  SearchIndexerTrace::Warning(
    (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\Search\\\\common\\\\include\\\\prothndlrhelp.hxx\"",
    (const wchar_t *)0x154,
    (unsigned int)L"[UtilCommon] IFilter::BindRegion: not implemented 0x%08x",
    (const wchar_t *)0x80004001LL);
  return 2147500033LL;
}

```

## disassembly

```asm
0x1800149f0  sub     rsp, 28h
0x1800149f4  mov     r9d, 80004001h; wchar_t *
0x1800149fa  lea     r8, aUtilcommonIfil_2; "[UtilCommon] IFilter::BindRegion: not i"...
0x180014a01  mov     edx, 154h; wchar_t *
0x180014a06  lea     rcx, aOnecoreuapBase_12; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x180014a0d  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x180014a12  mov     eax, 80004001h
0x180014a17  add     rsp, 28h
0x180014a1b  retn
```
