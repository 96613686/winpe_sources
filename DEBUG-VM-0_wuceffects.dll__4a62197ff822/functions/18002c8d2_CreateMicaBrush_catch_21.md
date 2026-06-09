# CreateMicaBrush$catch$21

- ea: `0x18002c8d2`
- end: `0x18002c90b`
- name: `CreateMicaBrush$catch$21`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800266dc`

## string_xrefs

- `0x18002c8e3`: `onecoreuap\windows\dwm\effects\compiler\global\materialbrushfactory.cpp`

## pseudocode

```c
__int64 __fastcall CreateMicaBrush_catch_21(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 160) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 120),
                            (void *)0xA6,
                            (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\global\\materialbrushfactory.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18002c8d2  mov     [rsp+arg_8], rdx
0x18002c8d7  push    rbp
0x18002c8d8  sub     rsp, 30h
0x18002c8dc  mov     rbp, rdx
0x18002c8df  mov     rcx, [rbp+78h]; this
0x18002c8e3  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18002c8ea  mov     edx, 0A6h; void *
0x18002c8ef  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002c8f4  mov     [rbp+0A0h], eax
0x18002c8fa  mov     rax, 0
0x18002c904  add     rsp, 30h
0x18002c908  pop     rbp
0x18002c909  retn
```
