# _MapRegKeyPathIfNeeded_::_1_::catch$11

- ea: `0x1800179bf`
- end: `0x180017a12`
- name: `_MapRegKeyPathIfNeeded_::_1_::catch$11`
- size: `83`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800091e4`
- `0x18000c780`
- `0x180013c50`

## string_xrefs

- `0x1800179db`: `WSMIG - Exception in MapRegKeyPathIfNeeded, HRESULT=%08x`

## pseudocode

```c
void __fastcall __noreturn MapRegKeyPathIfNeeded_::_1_::catch_11(__int64 a1, __int64 a2)
{
  indexer::result::details::result_from_caught_exception<0>(*(_QWORD *)(a2 + 1288));
}

```

## disassembly

```asm
0x1800179bf  mov     [rsp+arg_8], rdx
0x1800179c4  push    rbp
0x1800179c5  sub     rsp, 40h
0x1800179c9  mov     rbp, rdx
0x1800179cc  mov     rcx, [rbp+508h]
0x1800179d3  call    ??$result_from_caught_exception@$0A@@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<0>(void *,uint,char const *)
0x1800179d8  mov     r9d, eax
0x1800179db  lea     r8, aWsmigException; "WSMIG - Exception in MapRegKeyPathIfNee"...
0x1800179e2  mov     edx, 208h; unsigned __int64
0x1800179e7  lea     rcx, [rbp+0B0h]; wchar_t *
0x1800179ee  call    ?StringCchPrintfW@@YAJPEA_W_KPEB_WZZ; StringCchPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x1800179f3  lea     rdx, [rbp+0B0h]
0x1800179fa  mov     rcx, [rbp+60h]
0x1800179fe  call    WSMigLog
0x180017a03  nop
0x180017a04  lea     rax, loc_18001150D
0x180017a0b  add     rsp, 40h
0x180017a0f  pop     rbp
0x180017a10  retn
```
