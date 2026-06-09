# _split_string$_ResumeCoro$1_unsigned_short_std::basic_string_view_unsigned_short_std::char_traits_unsigned_short____(__cdecl_)(std::basic_string_view_unsigned_short_std::char_traits_unsigned_short___)__::_1_::catch$3

- ea: `0x180023776`
- end: `0x1800237f3`
- name: `_split_string$_ResumeCoro$1_unsigned_short_std::basic_string_view_unsigned_short_std::char_traits_unsigned_short____(__cdecl_)(std::basic_string_view_unsigned_short_std::char_traits_unsigned_short___)__::_1_::catch$3`
- size: `125`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800237bc`
- `msvcp_win!?__ExceptionPtrCurrentException@@YAXPEAX@Z` at `0x1800237bc`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800237af`
- `msvcp_win!?__ExceptionPtrCreate@@YAXPEAX@Z` at `0x1800237af`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800237cd`
- `msvcp_win!?__ExceptionPtrAssign@@YAXPEAXPEBX@Z` at `0x1800237cd`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800237da`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x1800237da`

## pseudocode

```c
__int64 __fastcall split_string__ResumeCoro_1_unsigned_short_std::basic_string_view_unsigned_short_std::char_traits_unsigned_short_______cdecl___std::basic_string_view_unsigned_short_std::char_traits_unsigned_short______::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // rbx

  v2 = *(_QWORD *)(a2 + 128);
  *(_WORD *)(v2 + 8) = -1;
  *(_QWORD *)(v2 + 144) = 0;
  *(_QWORD *)(v2 + 152) = 0;
  __ExceptionPtrCreate((void *)(v2 + 144));
  __ExceptionPtrCurrentException((void *)(v2 + 144));
  __ExceptionPtrAssign((void *)(v2 - 24), (const void *)(v2 + 144));
  __ExceptionPtrDestroy((void *)(v2 + 144));
  return 0;
}

```

## disassembly

```asm
0x180023776  mov     [rsp+arg_8], rdx
0x18002377b  push    rbx
0x18002377c  push    rbp
0x18002377d  sub     rsp, 28h
0x180023781  mov     rbp, rdx
0x180023784  or      eax, 0FFFFFFFFh
0x180023787  mov     rbx, [rbp+80h]
0x18002378e  mov     [rbx+8], ax
0x180023792  mov     qword ptr [rbx+90h], 0
0x18002379d  mov     qword ptr [rbx+98h], 0
0x1800237a8  lea     rcx, [rbx+90h]
0x1800237af  call    cs:__imp_?__ExceptionPtrCreate@@YAXPEAX@Z; __ExceptionPtrCreate(void *)
0x1800237b5  lea     rcx, [rbx+90h]
0x1800237bc  call    cs:__imp_?__ExceptionPtrCurrentException@@YAXPEAX@Z; __ExceptionPtrCurrentException(void *)
0x1800237c2  lea     rdx, [rbx+90h]
0x1800237c9  lea     rcx, [rbx-18h]
0x1800237cd  call    cs:__imp_?__ExceptionPtrAssign@@YAXPEAXPEBX@Z; __ExceptionPtrAssign(void *,void const *)
0x1800237d3  lea     rcx, [rbx+90h]
0x1800237da  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x1800237e0  nop
0x1800237e1  mov     rax, 0
0x1800237eb  add     rsp, 28h
0x1800237ef  pop     rbp
0x1800237f0  pop     rbx
0x1800237f1  retn
```
