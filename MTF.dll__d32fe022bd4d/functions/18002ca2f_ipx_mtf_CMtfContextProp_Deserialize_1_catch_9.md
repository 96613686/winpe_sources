# _ipx::mtf::CMtfContextProp::Deserialize_::_1_::catch$9

- ea: `0x18002ca2f`
- end: `0x18002ca68`
- name: `_ipx::mtf::CMtfContextProp::Deserialize_::_1_::catch$9`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000befc`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfContextProp::Deserialize_::_1_::catch_9(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 48) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 136),
                           (void *)0x159,
                           (int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\contextproperty.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002ca2f  mov     [rsp+arg_8], rdx
0x18002ca34  push    rbp
0x18002ca35  sub     rsp, 30h
0x18002ca39  mov     rbp, rdx
0x18002ca3c  mov     rcx, [rbp+88h]; this
0x18002ca43  lea     r8, aMincoreTextinp_7; "mincore\\textinput\\dev\\mtf\\predictio"...
0x18002ca4a  mov     edx, 159h; void *
0x18002ca4f  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002ca54  mov     [rbp+30h], eax
0x18002ca57  mov     rax, 0
0x18002ca61  add     rsp, 30h
0x18002ca65  pop     rbp
0x18002ca66  retn
```
