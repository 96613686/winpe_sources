# _CFilterThread::Thread_::_1_::catch$169

- ea: `0x14006bafd`
- end: `0x14006bb7e`
- name: `_CFilterThread::Thread_::_1_::catch$169`
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

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14006bb69`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x14006bb69`

## string_xrefs

- `0x14006bb56`: `"onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx"`
- `0x14006bb11`: `onecoreuap\base\appmodel\search\searchprotocolhost\fltrdaemon.cxx`
- `0x14006bb4a`: `[SrchFilterDaemon] Exception caught in filter daemon (thread): %ws\n`

## pseudocode

```c
void __fastcall __noreturn CFilterThread::Thread_::_1_::catch_169(__int64 a1, __int64 a2)
{
  indexer::result::details::result_from_caught_exception<1>(
    *(_QWORD *)(a2 + 23448),
    3732,
    "onecoreuap\\base\\appmodel\\search\\searchprotocolhost\\fltrdaemon.cxx");
}

```

## disassembly

```asm
0x14006bafd  mov     [rsp+arg_8], rdx
0x14006bb02  push    rbp
0x14006bb03  sub     rsp, 60h
0x14006bb07  mov     rbp, rdx
0x14006bb0a  mov     rcx, [rbp+5B98h]
0x14006bb11  lea     r8, aOnecoreuapBase_19; "onecoreuap\\base\\appmodel\\search\\sea"...
0x14006bb18  mov     edx, 0E94h
0x14006bb1d  call    ??$result_from_caught_exception@$00@details@result@indexer@@YAJPEAXIPEBD@Z; indexer::result::details::result_from_caught_exception<1>(void *,uint,char const *)
0x14006bb22  mov     [rbp+388h], eax
0x14006bb28  mov     r9d, eax
0x14006bb2b  lea     r8, a0x08x; "0x%08x"
0x14006bb32  mov     edx, 16h; unsigned __int64
0x14006bb37  lea     rcx, [rbp+370h]; wchar_t *
0x14006bb3e  call    ?StringCbPrintfW@@YAJPEA_W_KPEB_WZZ; StringCbPrintfW(wchar_t *,unsigned __int64,wchar_t const *,...)
0x14006bb43  lea     r9, [rbp+370h]; wchar_t *
0x14006bb4a  lea     r8, aSrchfilterdaem_28; "[SrchFilterDaemon] Exception caught in "...
0x14006bb51  mov     edx, 0E95h; wchar_t *
0x14006bb56  lea     rcx, aOnecoreuapBase_54; "\"onecoreuap\\\\base\\\\appmodel\\\\sea"...
0x14006bb5d  call    ?Error@SearchIndexerTrace@@YAXPEB_WI0ZZ; SearchIndexerTrace::Error(wchar_t const *,uint,wchar_t const *,...)
0x14006bb62  mov     rcx, cs:?g_hShutdownEv@@3V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@A; hEvent
0x14006bb69  call    cs:__imp_SetEvent
0x14006bb6f  nop
0x14006bb70  lea     rax, loc_14002CEF7
0x14006bb77  add     rsp, 60h
0x14006bb7b  pop     rbp
0x14006bb7c  retn
```
