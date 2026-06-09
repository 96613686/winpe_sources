# TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::operator&(void)

- ea: `0x18002d270`
- end: `0x18002d2a0`
- name: `??I?$TPointer@V?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@@@QEAAPEAPEAV?$CSimpleArray@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@V?$CSimpleArrayEqualHelper@V?$CStringT@_WV?$StrTraitATL@_WV?$ChTraitsCRT@_W@ATL@@@ATL@@@ATL@@@2@@ATL@@XZ`
- size: `48`
- prototype: `_QWORD *__fastcall(_QWORD *, __int64, __int64, const wchar_t *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18002e1c8`
- `0x18002e9f4`
- `0x18002f07c`

## callees

- `0x180017468`
- `0x18002d270`

## string_xrefs

- `0x18002d27f`: `[UtilCommon] TPointer::operator&: Possible resource leak - m_pT not zero`
- `0x18002d28b`: `"onecoreuap\\base\\appmodel\\Search\\common\\include\\smartcls_common.hxx"`

## pseudocode

```c
_QWORD *__fastcall TPointer<ATL::CSimpleArray<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>,ATL::CSimpleArrayEqualHelper<ATL::CStringT<wchar_t,ATL::StrTraitATL<wchar_t,ATL::ChTraitsCRT<wchar_t>>>>>>::operator&(
        _QWORD *a1,
        __int64 a2,
        __int64 a3,
        const wchar_t *a4)
{
  if ( *a1 )
    SearchIndexerTrace::Warning(
      (wchar_t *)L"\"onecoreuap\\\\base\\\\appmodel\\\\Search\\\\common\\\\include\\\\smartcls_common.hxx\"",
      (const wchar_t *)0x70,
      (unsigned int)L"[UtilCommon] TPointer::operator&: Possible resource leak - m_pT not zero",
      a4);
  return a1;
}

```

## disassembly

```asm
0x18002d270  push    rbx
0x18002d272  sub     rsp, 20h
0x18002d276  cmp     qword ptr [rcx], 0
0x18002d27a  mov     rbx, rcx
0x18002d27d  jz      short loc_18002D297
0x18002d27f  lea     r8, aUtilcommonTpoi; "[UtilCommon] TPointer::operator&: Possi"...
0x18002d286  mov     edx, 70h ; 'p'; wchar_t *
0x18002d28b  lea     rcx, aOnecoreuapBase_2; "\"onecoreuap\\\\base\\\\appmodel\\\\Sea"...
0x18002d292  call    ?Warning@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Warning(wchar_t const *,uint,wchar_t const *,...)
0x18002d297  mov     rax, rbx
0x18002d29a  add     rsp, 20h
0x18002d29e  pop     rbx
0x18002d29f  retn
```
