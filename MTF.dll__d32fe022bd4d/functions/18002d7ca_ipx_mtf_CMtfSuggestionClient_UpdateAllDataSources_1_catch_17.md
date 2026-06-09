# _ipx::mtf::CMtfSuggestionClient::UpdateAllDataSources_::_1_::catch$17

- ea: `0x18002d7ca`
- end: `0x18002d803`
- name: `_ipx::mtf::CMtfSuggestionClient::UpdateAllDataSources_::_1_::catch$17`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000befc`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::UpdateAllDataSources_::_1_::catch_17(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 80) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 472),
                           (void *)0x9C3,
                           (int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002d7ca  mov     [rsp+arg_8], rdx
0x18002d7cf  push    rbp
0x18002d7d0  sub     rsp, 50h
0x18002d7d4  mov     rbp, rdx
0x18002d7d7  mov     rcx, [rbp+1D8h]; this
0x18002d7de  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18002d7e5  mov     edx, 9C3h; void *
0x18002d7ea  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002d7ef  mov     [rbp+50h], eax
0x18002d7f2  mov     rax, 0
0x18002d7fc  add     rsp, 50h
0x18002d800  pop     rbp
0x18002d801  retn
```
