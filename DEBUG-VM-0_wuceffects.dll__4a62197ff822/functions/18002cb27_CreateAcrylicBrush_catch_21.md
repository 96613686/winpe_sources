# CreateAcrylicBrush$catch$21

- ea: `0x18002cb27`
- end: `0x18002cb60`
- name: `CreateAcrylicBrush$catch$21`
- size: `57`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800266dc`

## string_xrefs

- `0x18002cb38`: `onecoreuap\windows\dwm\effects\compiler\global\materialbrushfactory.cpp`

## pseudocode

```c
__int64 __fastcall CreateAcrylicBrush_catch_21(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 160) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 120),
                            (void *)0xC3,
                            (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\global\\materialbrushfactory.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18002cb27  mov     [rsp+arg_8], rdx
0x18002cb2c  push    rbp
0x18002cb2d  sub     rsp, 30h
0x18002cb31  mov     rbp, rdx
0x18002cb34  mov     rcx, [rbp+78h]; this
0x18002cb38  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18002cb3f  mov     edx, 0C3h; void *
0x18002cb44  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002cb49  mov     [rbp+0A0h], eax
0x18002cb4f  mov     rax, 0
0x18002cb59  add     rsp, 30h
0x18002cb5d  pop     rbp
0x18002cb5e  retn
```
