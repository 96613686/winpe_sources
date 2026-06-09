# _ipx::mtf::CMtfPredictionInputQuery::Deserialize_::_1_::catch$19

- ea: `0x18002cb08`
- end: `0x18002cb41`
- name: `_ipx::mtf::CMtfPredictionInputQuery::Deserialize_::_1_::catch$19`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000befc`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfPredictionInputQuery::Deserialize_::_1_::catch_19(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 60) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 168),
                           (void *)0x3FE,
                           (int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\inputquery.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002cb08  mov     [rsp+arg_8], rdx
0x18002cb0d  push    rbp
0x18002cb0e  sub     rsp, 30h
0x18002cb12  mov     rbp, rdx
0x18002cb15  mov     rcx, [rbp+0A8h]; this
0x18002cb1c  lea     r8, aMincoreTextinp_3; "mincore\\textinput\\dev\\mtf\\predictio"...
0x18002cb23  mov     edx, 3FEh; void *
0x18002cb28  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002cb2d  mov     [rbp+3Ch], eax
0x18002cb30  mov     rax, 0
0x18002cb3a  add     rsp, 30h
0x18002cb3e  pop     rbp
0x18002cb3f  retn
```
