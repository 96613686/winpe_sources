# _ipx::mtf::CMtfSuggestionClient::RepairServerConnection_::_1_::catch$30

- ea: `0x18002d57b`
- end: `0x18002d5b4`
- name: `_ipx::mtf::CMtfSuggestionClient::RepairServerConnection_::_1_::catch$30`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `installer_update`

## callees

- `0x18000befc`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfSuggestionClient::RepairServerConnection_::_1_::catch_30(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 128) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 120),
                            (void *)0x928,
                            (int)"mincore\\textinput\\dev\\mtf\\client\\client.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18002d57b  mov     [rsp+arg_8], rdx
0x18002d580  push    rbp
0x18002d581  sub     rsp, 50h
0x18002d585  mov     rbp, rdx
0x18002d588  mov     rcx, [rbp+78h]; this
0x18002d58c  lea     r8, aMincoreTextinp_5; "mincore\\textinput\\dev\\mtf\\client\\c"...
0x18002d593  mov     edx, 928h; void *
0x18002d598  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002d59d  mov     [rbp+80h], eax
0x18002d5a3  mov     rax, 0
0x18002d5ad  add     rsp, 50h
0x18002d5b1  pop     rbp
0x18002d5b2  retn
```
