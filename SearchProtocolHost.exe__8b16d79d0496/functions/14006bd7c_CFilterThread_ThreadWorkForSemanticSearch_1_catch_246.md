# _CFilterThread::ThreadWorkForSemanticSearch_::_1_::catch$246

- ea: `0x14006bd7c`
- end: `0x14006bdfd`
- name: `_CFilterThread::ThreadWorkForSemanticSearch_::_1_::catch$246`
- size: `129`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x14000c754`
- `0x140015958`
- `0x140029998`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14006bde8`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14006bde8`

## string_xrefs

- `0x14006bdd5`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx"`
- `0x14006bd90`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrdaemon.cxx`
- `0x14006bdc9`: `[SrchFilterDaemon] Exception caught in filter daemon (thread): %ws\n`

## pseudocode

```c
void __fastcall __noreturn CFilterThread::ThreadWorkForSemanticSearch_::_1_::catch_246(__int64 a1, __int64 a2)
{
  indexer::result::details::result_from_caught_exception<1>(
    *(_QWORD *)(a2 + 23752),
    5552,
    "onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx");
}

```

## disassembly

```asm
0x14006bd7c  mov     [rsp+arg_8], rdx
0x14006bd81  push    rbp
0x14006bd82  sub     rsp, 60h
0x14006bd86  mov     rbp, rdx
0x14006bd89  mov     rcx, [rbp+5CC8h]
0x14006bd90  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14006bd97  mov     edx, 15B0h
0x14006bd9c  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x14006bda1  mov     [rbp+4D8h], eax
0x14006bda7  mov     r9d, eax
0x14006bdaa  lea     r8, a0x08x; "0x%08x"
0x14006bdb1  mov     edx, 16h; unsigned __int64
0x14006bdb6  lea     rcx, [rbp+4C0h]; wchar_t *
0x14006bdbd  call    ?StringCbPrintfW@@YAJPEA_W_KPEB_WZZ; StringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14006bdc2  lea     r9, [rbp+4C0h]; wchar_t *
0x14006bdc9  lea     r8, aSrchfilterdaem_28; "[SrchFilterDaemon] Exception caught in "...
0x14006bdd0  mov     edx, 15B1h; wchar_t *
0x14006bdd5  lea     rcx, aOnecoreuapBase_54; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14006bddc  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14006bde1  mov     rcx, cs:?g_hShutdownEv@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hEvent
0x14006bde8  call    cs:__imp_SetEvent
0x14006bdee  nop
0x14006bdef  lea     rax, loc_14003151E
0x14006bdf6  add     rsp, 60h
0x14006bdfa  pop     rbp
0x14006bdfb  retn
```
