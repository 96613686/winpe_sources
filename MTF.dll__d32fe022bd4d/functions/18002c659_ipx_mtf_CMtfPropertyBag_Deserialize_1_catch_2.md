# _ipx::mtf::CMtfPropertyBag::Deserialize_::_1_::catch$2

- ea: `0x18002c659`
- end: `0x18002c68f`
- name: `_ipx::mtf::CMtfPropertyBag::Deserialize_::_1_::catch$2`
- size: `54`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18000befc`

## pseudocode

```c
__int64 __fastcall ipx::mtf::CMtfPropertyBag::Deserialize_::_1_::catch_2(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        const char *a4)
{
  *(_DWORD *)(a2 + 56) = wil::details::in1diag3::Return_CaughtException(
                           *(wil::details::in1diag3 **)(a2 + 120),
                           (void *)0x288,
                           (int)"mincore\\textinput\\dev\\mtf\\predictionengine\\containers\\propertybag.cpp",
                           a4);
  return 0;
}

```

## disassembly

```asm
0x18002c659  mov     [rsp+arg_8], rdx
0x18002c65e  push    rbp
0x18002c65f  sub     rsp, 30h
0x18002c663  mov     rbp, rdx
0x18002c666  mov     rcx, [rbp+78h]; this
0x18002c66a  lea     r8, aMincoreTextinp_0; "mincore\\textinput\\dev\\mtf\\predictio"...
0x18002c671  mov     edx, 288h; void *
0x18002c676  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002c67b  mov     [rbp+38h], eax
0x18002c67e  mov     rax, 0
0x18002c688  add     rsp, 30h
0x18002c68c  pop     rbp
0x18002c68d  retn
```
