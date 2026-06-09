# CreateCrossfadeEffectFactory$catch$66

- ea: `0x18002c85a`
- end: `0x18002c896`
- name: `CreateCrossfadeEffectFactory$catch$66`
- size: `60`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x1800266dc`

## string_xrefs

- `0x18002c86e`: `onecoreuap\windows\dwm\effects\compiler\global\materialbrushfactory.cpp`

## pseudocode

```c
__int64 __fastcall CreateCrossfadeEffectFactory_catch_66(__int64 a1, __int64 a2, __int64 a3, const char *a4)
{
  *(_DWORD *)(a2 + 160) = wil::details::in1diag3::Return_CaughtException(
                            *(wil::details::in1diag3 **)(a2 + 152),
                            (void *)0xDB,
                            (unsigned int)"onecoreuap\\windows\\dwm\\effects\\compiler\\global\\materialbrushfactory.cpp",
                            a4);
  return 0;
}

```

## disassembly

```asm
0x18002c85a  mov     [rsp+arg_8], rdx
0x18002c85f  push    rbp
0x18002c860  sub     rsp, 20h
0x18002c864  mov     rbp, rdx
0x18002c867  mov     rcx, [rbp+98h]; this
0x18002c86e  lea     r8, aOnecoreuapWind_2; "onecoreuap\\windows\\dwm\\effects\\comp"...
0x18002c875  mov     edx, 0DBh; void *
0x18002c87a  call    ?Return_CaughtException@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_CaughtException(void *,uint,char const *)
0x18002c87f  mov     [rbp+0A0h], eax
0x18002c885  mov     rax, 0
0x18002c88f  add     rsp, 20h
0x18002c893  pop     rbp
0x18002c894  retn
```
