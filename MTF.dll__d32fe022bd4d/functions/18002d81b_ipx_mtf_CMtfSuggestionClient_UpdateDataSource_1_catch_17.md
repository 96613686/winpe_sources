# _ipx::mtf::CMtfSuggestionClient::UpdateDataSource_::_1_::catch$17

- ea: `0x18002d81b`
- end: `0x18002d854`
- name: `_ipx::mtf::CMtfSuggestionClient::UpdateDataSource_::_1_::catch$17`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000befc`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::UpdateDataSource_::_1_::catch_17(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 504),
                           (void *)0x99E,
                           (int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002d81b  mov     [rsp+arg_8], rdx
0x18002d820  push    rbp
0x18002d821  sub     rsp, 50h
0x18002d825  mov     rbp, rdx
0x18002d828  mov     rcx, [rbp+1F8h]; this
0x18002d82f  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18002d836  mov     edx, 99Eh; void *
0x18002d83b  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002d840  mov     [rbp+50h], eax
0x18002d843  mov     rax, 0
0x18002d84d  add     rsp, 50h
0x18002d851  pop     rbp
0x18002d852  retn
```
